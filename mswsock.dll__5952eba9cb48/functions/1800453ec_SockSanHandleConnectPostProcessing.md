# SockSanHandleConnectPostProcessing

- ea: `0x1800453ec`
- end: `0x1800456a5`
- name: `SockSanHandleConnectPostProcessing`
- size: `697`
- prototype: `__int64 __fastcall(PVOID CompletionContext)`
- caller_count: `4`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180044800`
- `0x1800485dc`
- `0x18004958c`
- `0x18004bf20`

## callees

- `0x1800052a0`
- `0x180008250`
- `0x180009a08`
- `0x180024e84`
- `0x180038a20`
- `0x18003ae8c`
- `0x1800411a8`
- `0x180042128`
- `0x180044800`
- `0x1800453ec`
- `0x1800456ac`
- `0x1800462b0`

## import_xrefs

- `ntdll!NtSetEvent` at `0x180045669`
- `ntdll!NtSetEvent` at `0x180045669`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045457`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045598`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004567d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045457`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045598`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004567d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004543a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004543a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004546a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004546a`

## pseudocode

```c
__int64 __fastcall SockSanHandleConnectPostProcessing(char *CompletionContext, char a2, unsigned int a3)
{
  __int64 v4; // rbp
  char v7; // r15
  struct _RTL_CRITICAL_SECTION *v8; // r14
  __int64 v10; // rcx
  volatile signed __int32 *v11; // rax
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // edi
  _QWORD *v16; // rax
  unsigned int v17; // edi
  unsigned int v18; // ebx
  unsigned int v19; // eax
  unsigned int v20; // [rsp+90h] [rbp+8h] BYREF

  v4 = *(_QWORD *)CompletionContext;
  if ( *((_QWORD *)CompletionContext + 85) || *((_DWORD *)CompletionContext + 42) == 1 )
  {
    v8 = (struct _RTL_CRITICAL_SECTION *)(v4 + 224);
    v7 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 224));
  }
  else
  {
    v7 = 1;
    v8 = (struct _RTL_CRITICAL_SECTION *)(v4 + 224);
  }
  if ( *((_DWORD *)CompletionContext + 39) != -1 )
  {
    if ( !v7 )
      LeaveCriticalSection(v8);
    return 0;
  }
  *((_DWORD *)CompletionContext + 39) = GetTickCount();
  while ( !a3 )
  {
    v11 = (volatile signed __int32 *)*((_QWORD *)CompletionContext + 1);
    *((_DWORD *)CompletionContext + 38) = 1;
    _InterlockedIncrement(v11);
    v12 = AfdCementSocketToSan(v10, *(_QWORD *)(v4 + 8), *((_QWORD *)CompletionContext + 27) + 24LL);
    v15 = v12;
    if ( v12 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_d(1025, 45, WPP_f1e7b1a0c21837fa07930ef9896de5d8_Traceguids, v12);
      if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)CompletionContext + 1), 0xFFFFFFFF) == 1 )
        SockDestroySocket(*((_QWORD *)CompletionContext + 1), v13, v14);
      a3 = NtStatusToSocketError(v15);
    }
    else
    {
      *(_BYTE *)(v4 + 69) |= 8u;
      *(_DWORD *)(v4 + 24) = 3;
      a3 = SockSetHandleContext(v4);
      if ( !a3 )
        goto LABEL_18;
    }
  }
  AbortSanConnection(CompletionContext);
  if ( *((_DWORD *)CompletionContext + 38) == 4 )
    *(_BYTE *)(*(_QWORD *)CompletionContext + 69LL) &= ~8u;
  if ( !a2 && !v7 )
  {
    v18 = HandleSanConnectIndication(CompletionContext);
    LeaveCriticalSection(v8);
    return v18;
  }
LABEL_18:
  v16 = (_QWORD *)*((_QWORD *)CompletionContext + 85);
  if ( !v16 )
  {
    v17 = a3;
    if ( *((_DWORD *)CompletionContext + 42) == 1 )
    {
      *((_DWORD *)CompletionContext + 42) = 0;
      SockSanHandleConnectSignalling(v4, a3);
    }
    else
    {
      *(_DWORD *)(v4 + 100) = a3;
      NtSetEvent(*((HANDLE *)CompletionContext + 18), 0);
    }
    goto LABEL_35;
  }
  v20 = 0;
  if ( a3 )
  {
    v17 = a3;
  }
  else
  {
    v19 = HandleApplicationSend(CompletionContext, CompletionContext + 624, 1u, &v20, 0, v16, 0, 0, 1, 0, 0);
    v17 = v19;
    if ( !v19 )
      goto LABEL_35;
    if ( v19 != 997 )
    {
      if ( (BYTE2(xmmword_180063D60) & 1) != 0 )
        WPP_SF_qD(1040, 46, WPP_f1e7b1a0c21837fa07930ef9896de5d8_Traceguids, *(_QWORD *)(v4 + 8), v19);
      goto LABEL_22;
    }
  }
  if ( v17 != 997 )
LABEL_22:
    CompleteOverlappedIO(*(_QWORD *)(v4 + 8), *((_QWORD *)CompletionContext + 85), 0, 0, v17, 0);
LABEL_35:
  if ( !v7 )
    LeaveCriticalSection(v8);
  return v17;
}

```

## disassembly

```asm
0x1800453ec  mov     [rsp+arg_8], rbx
0x1800453f1  mov     [rsp+arg_10], rbp
0x1800453f6  push    rsi
0x1800453f7  push    rdi
0x1800453f8  push    r12
0x1800453fa  push    r14
0x1800453fc  push    r15
0x1800453fe  sub     rsp, 60h
0x180045402  cmp     qword ptr [rcx+2A8h], 0
0x18004540a  mov     esi, r8d
0x18004540d  mov     rbp, [rcx]
0x180045410  mov     r12b, dl
0x180045413  mov     rbx, rcx
0x180045416  jnz     short loc_18004542D
0x180045418  cmp     dword ptr [rcx+0A8h], 1
0x18004541f  jz      short loc_18004542D
0x180045421  mov     r15b, 1
0x180045424  lea     r14, [rbp+0E0h]
0x18004542b  jmp     short loc_180045446
0x18004542d  lea     r14, [rbp+0E0h]
0x180045434  xor     r15b, r15b
0x180045437  mov     rcx, r14; lpCriticalSection
0x18004543a  call    cs:__imp_EnterCriticalSection
0x180045441  nop     dword ptr [rax+rax+00h]
0x180045446  cmp     dword ptr [rbx+9Ch], 0FFFFFFFFh
0x18004544d  jz      short loc_18004546A
0x18004544f  test    r15b, r15b
0x180045452  jnz     short loc_180045463
0x180045454  mov     rcx, r14; lpCriticalSection
0x180045457  call    cs:__imp_LeaveCriticalSection
0x18004545e  nop     dword ptr [rax+rax+00h]
0x180045463  xor     eax, eax
0x180045465  jmp     loc_18004568B
0x18004546a  call    cs:__imp_GetTickCount
0x180045471  nop     dword ptr [rax+rax+00h]
0x180045476  mov     [rbx+9Ch], eax
0x18004547c  test    esi, esi
0x18004547e  jnz     loc_180045567
0x180045484  mov     rax, [rbx+8]
0x180045488  mov     dword ptr [rbx+98h], 1
0x180045492  lock inc dword ptr [rax]
0x180045495  mov     r8, [rbx+0D8h]
0x18004549c  mov     rdx, [rbp+8]
0x1800454a0  add     r8, 18h
0x1800454a4  call    AfdCementSocketToSan
0x1800454a9  mov     edi, eax
0x1800454ab  test    eax, eax
0x1800454ad  jz      short loc_1800454F3
0x1800454af  test    byte ptr cs:xmmword_180063D60, 2
0x1800454b6  jz      short loc_1800454CF
0x1800454b8  lea     edx, [rsi+2Dh]
0x1800454bb  mov     ecx, 401h
0x1800454c0  mov     r9d, eax
0x1800454c3  lea     r8, WPP_f1e7b1a0c21837fa07930ef9896de5d8_Traceguids
0x1800454ca  call    WPP_SF_d
0x1800454cf  mov     rax, [rbx+8]
0x1800454d3  or      ecx, 0FFFFFFFFh
0x1800454d6  lock xadd [rax], ecx
0x1800454da  cmp     ecx, 1
0x1800454dd  jnz     short loc_1800454E8
0x1800454df  mov     rcx, [rbx+8]
0x1800454e3  call    SockDestroySocket
0x1800454e8  mov     ecx, edi
0x1800454ea  call    NtStatusToSocketError
0x1800454ef  mov     esi, eax
0x1800454f1  jmp     short loc_18004547C
0x1800454f3  or      byte ptr [rbp+45h], 8
0x1800454f7  mov     rcx, rbp
0x1800454fa  mov     dword ptr [rbp+18h], 3
0x180045501  call    SockSetHandleContext
0x180045506  mov     esi, eax
0x180045508  test    eax, eax
0x18004550a  jnz     loc_18004547C
0x180045510  mov     rax, [rbx+2A8h]
0x180045517  test    rax, rax
0x18004551a  jz      loc_18004563C
0x180045520  mov     [rsp+88h+arg_0], 0
0x18004552b  mov     r12d, 3E5h
0x180045531  test    esi, esi
0x180045533  jz      short loc_1800455AB
0x180045535  mov     edi, esi
0x180045537  cmp     edi, r12d
0x18004553a  jz      loc_180045675
0x180045540  mov     rdx, [rbx+2A8h]
0x180045547  xor     r9d, r9d
0x18004554a  mov     rcx, [rbp+8]
0x18004554e  xor     r8d, r8d
0x180045551  mov     dword ptr [rsp+88h+var_60], 0
0x180045559  mov     [rsp+88h+var_68], edi
0x18004555d  call    CompleteOverlappedIO
0x180045562  jmp     loc_180045675
0x180045567  mov     rcx, rbx
0x18004556a  call    AbortSanConnection
0x18004556f  cmp     dword ptr [rbx+98h], 4
0x180045576  jnz     short loc_18004557F
0x180045578  mov     rax, [rbx]
0x18004557b  and     byte ptr [rax+45h], 0F7h
0x18004557f  test    r12b, r12b
0x180045582  jnz     short loc_180045510
0x180045584  test    r15b, r15b
0x180045587  jnz     short loc_180045510
0x180045589  mov     edx, esi
0x18004558b  mov     rcx, rbx
0x18004558e  call    HandleSanConnectIndication
0x180045593  mov     rcx, r14; lpCriticalSection
0x180045596  mov     ebx, eax
0x180045598  call    cs:__imp_LeaveCriticalSection
0x18004559f  nop     dword ptr [rax+rax+00h]
0x1800455a4  mov     eax, ebx
0x1800455a6  jmp     loc_18004568B
0x1800455ab  mov     [rsp+88h+var_38], 0; int
0x1800455b3  lea     rdx, [rbx+270h]; Src
0x1800455ba  mov     [rsp+88h+var_40], 0; __int64
0x1800455c3  lea     r9, [rsp+88h+arg_0]
0x1800455cb  mov     [rsp+88h+var_48], 1; char
0x1800455d0  mov     r8d, 1
0x1800455d6  mov     [rsp+88h+var_50], 0; __int64
0x1800455df  mov     rcx, rbx; CompletionContext
0x1800455e2  mov     [rsp+88h+var_58], 0; __int64
0x1800455eb  mov     [rsp+88h+var_60], rax; __int64
0x1800455f0  mov     [rsp+88h+var_68], 0; int
0x1800455f8  call    HandleApplicationSend
0x1800455fd  mov     edi, eax
0x1800455ff  test    eax, eax
0x180045601  jz      short loc_180045675
0x180045603  cmp     eax, r12d
0x180045606  jz      loc_180045537
0x18004560c  test    byte ptr cs:xmmword_180063D60+2, 1
0x180045613  jz      loc_180045540
0x180045619  mov     r9, [rbp+8]
0x18004561d  lea     r8, WPP_f1e7b1a0c21837fa07930ef9896de5d8_Traceguids
0x180045624  mov     edx, 2Eh ; '.'
0x180045629  mov     [rsp+88h+var_68], eax
0x18004562d  mov     ecx, 410h
0x180045632  call    WPP_SF_qD
0x180045637  jmp     loc_180045540
0x18004563c  cmp     dword ptr [rbx+0A8h], 1
0x180045643  mov     edi, esi
0x180045645  jnz     short loc_18004565D
0x180045647  mov     edx, esi
0x180045649  mov     dword ptr [rbx+0A8h], 0
0x180045653  mov     rcx, rbp
0x180045656  call    SockSanHandleConnectSignalling
0x18004565b  jmp     short loc_180045675
0x18004565d  mov     [rbp+64h], esi
0x180045660  xor     edx, edx; PreviousState
0x180045662  mov     rcx, [rbx+90h]; EventHandle
0x180045669  call    cs:__imp_NtSetEvent
0x180045670  nop     dword ptr [rax+rax+00h]
0x180045675  test    r15b, r15b
0x180045678  jnz     short loc_180045689
0x18004567a  mov     rcx, r14; lpCriticalSection
0x18004567d  call    cs:__imp_LeaveCriticalSection
0x180045684  nop     dword ptr [rax+rax+00h]
0x180045689  mov     eax, edi
0x18004568b  lea     r11, [rsp+88h+var_28]
0x180045690  mov     rbx, [r11+38h]
0x180045694  mov     rbp, [r11+40h]
0x180045698  mov     rsp, r11
0x18004569b  pop     r15
0x18004569d  pop     r14
0x18004569f  pop     r12
0x1800456a1  pop     rdi
0x1800456a2  pop     rsi
0x1800456a3  retn
```
