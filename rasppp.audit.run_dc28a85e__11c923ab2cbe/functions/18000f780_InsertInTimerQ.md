# InsertInTimerQ

- ea: `0x18000f780`
- end: `0x18000f97e`
- name: `InsertInTimerQ`
- size: `510`
- prototype: ``
- caller_count: `13`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800023c0`
- `0x18000442c`
- `0x18000b720`
- `0x18000cf3c`
- `0x18000d6b4`
- `0x18000e358`
- `0x1800102bc`
- `0x180012d54`
- `0x18001427c`
- `0x180014724`
- `0x180016260`
- `0x180017cf0`
- `0x1800181b0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000f780`
- `0x18002b0dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f7c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f7c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f814`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f8ed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f8ed`

## string_xrefs

- `0x18000f847`: `InsertInTimerQ called portid=%d,Id=%d,Protocol=%x,EventType=%d,fAuth=%d,Timeout=%d`

## pseudocode

```c
DWORD __fastcall InsertInTimerQ(unsigned int a1, __int64 a2, unsigned int a3, int a4, int a5, int a6, int a7)
{
  _DWORD *v11; // rbx
  unsigned int v13; // edi
  _DWORD *v14; // rcx
  _QWORD *v15; // rdx
  int v16; // [rsp+50h] [rbp-848h] BYREF
  _BYTE v17[2044]; // [rsp+54h] [rbp-844h] BYREF

  v11 = HeapAlloc(hHeap, 8u, 0x30u);
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( v11 )
  {
    v13 = a7;
    if ( (byte_18004DF34 & 1) != 0 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(
        &v16,
        L"InsertInTimerQ called portid=%d,Id=%d,Protocol=%x,EventType=%d,fAuth=%d,Timeout=%d",
        a1,
        a3,
        a4,
        a6,
        a5,
        a7);
      if ( (byte_18004DF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v16);
    }
    v11[5] = a1;
    v11[9] = a3;
    v11[8] = a4;
    *((_QWORD *)v11 + 3) = a2;
    v11[4] = a6;
    v11[10] = a5;
    v14 = TimerQ;
    v15 = TimerQ;
    if ( TimerQ )
    {
      do
      {
        if ( v14[11] >= v13 )
          break;
        v13 -= v14[11];
        v15 = v14;
        v14 = *(_DWORD **)v14;
      }
      while ( v14 );
    }
    if ( v14 )
    {
      if ( v14 == TimerQ )
      {
        *(_QWORD *)v11 = TimerQ;
        *((_QWORD *)TimerQ + 1) = v11;
        *((_DWORD *)TimerQ + 11) -= v13;
        *((_QWORD *)v11 + 1) = 0;
        TimerQ = v11;
      }
      else
      {
        *(_QWORD *)v11 = *v15;
        *v15 = v11;
        *((_QWORD *)v11 + 1) = v15;
        v14[11] -= v13;
        *((_QWORD *)v14 + 1) = v11;
      }
    }
    else if ( TimerQ )
    {
      *v15 = v11;
      *((_QWORD *)v11 + 1) = v15;
      *(_QWORD *)v11 = 0;
    }
    else
    {
      TimerQ = v11;
      *(_QWORD *)v11 = 0;
      *((_QWORD *)v11 + 1) = 0;
      SetEvent(*(&TimerQ + 1));
    }
    v11[11] = v13;
    return 0;
  }
  else
  {
    if ( byte_18004DF33 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasPppTraceError,
        L"InsertInTimerQ failed: out of memory");
    return GetLastError();
  }
}

```

## disassembly

```asm
0x18000f780  mov     [rsp+arg_8], rbx
0x18000f785  push    rbp
0x18000f786  push    rsi
0x18000f787  push    rdi
0x18000f788  push    r12
0x18000f78a  push    r13
0x18000f78c  push    r14
0x18000f78e  push    r15
0x18000f790  sub     rsp, 860h
0x18000f797  mov     rax, cs:__security_cookie
0x18000f79e  xor     rax, rsp
0x18000f7a1  mov     [rsp+898h+var_48], rax
0x18000f7a9  mov     r13, rdx
0x18000f7ac  mov     r15d, r8d
0x18000f7af  mov     edx, 8; dwFlags
0x18000f7b4  mov     r14d, ecx
0x18000f7b7  mov     rcx, cs:hHeap; hHeap
0x18000f7be  mov     r12d, r9d
0x18000f7c1  lea     r8d, [rdx+28h]; dwBytes
0x18000f7c5  call    cs:__imp_HeapAlloc
0x18000f7cc  nop     dword ptr [rax+rax+00h]
0x18000f7d1  xor     edx, edx; Val
0x18000f7d3  lea     rcx, [rsp+898h+var_844]; void *
0x18000f7d8  mov     rbx, rax
0x18000f7db  mov     r8d, 7FCh; Size
0x18000f7e1  xor     eax, eax
0x18000f7e3  mov     [rsp+898h+var_848], eax
0x18000f7e7  call    memset_0
0x18000f7ec  test    rbx, rbx
0x18000f7ef  jnz     short loc_18000F825
0x18000f7f1  test    cs:byte_18004DF33, 80h
0x18000f7f8  jz      short loc_18000F814
0x18000f7fa  lea     r8, aInsertintimerq_1; "InsertInTimerQ failed: out of memory"
0x18000f801  lea     rdx, RasPppTraceError
0x18000f808  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f80f  call    McTemplateU0z_EventWriteTransfer
0x18000f814  call    cs:__imp_GetLastError
0x18000f81b  nop     dword ptr [rax+rax+00h]
0x18000f820  jmp     loc_18000F952
0x18000f825  test    cs:byte_18004DF34, 1
0x18000f82c  mov     edi, [rsp+898h+arg_30]
0x18000f833  mov     esi, [rsp+898h+arg_28]
0x18000f83a  mov     ebp, [rsp+898h+arg_20]
0x18000f841  jz      short loc_18000F893
0x18000f843  mov     [rsp+898h+var_860], edi
0x18000f847  lea     rdx, aInsertintimerq_0; "InsertInTimerQ called portid=%d,Id=%d,P"...
0x18000f84e  mov     [rsp+898h+var_868], ebp
0x18000f852  lea     rcx, [rsp+898h+var_848]
0x18000f857  xor     eax, eax
0x18000f859  mov     [rsp+898h+var_870], esi
0x18000f85d  mov     r9d, r15d
0x18000f860  mov     [rsp+898h+var_878], r12d
0x18000f865  mov     r8d, r14d
0x18000f868  mov     word ptr [rsp+898h+var_848], ax
0x18000f86d  call    FormatRRASErrorString
0x18000f872  test    cs:byte_18004DF34, 1
0x18000f879  jz      short loc_18000F893
0x18000f87b  lea     r8, [rsp+898h+var_848]
0x18000f880  lea     rdx, RasPppTraceInfo
0x18000f887  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000f88e  call    McTemplateU0z_EventWriteTransfer
0x18000f893  mov     [rbx+14h], r14d
0x18000f897  mov     [rbx+24h], r15d
0x18000f89b  mov     [rbx+20h], r12d
0x18000f89f  mov     [rbx+18h], r13
0x18000f8a3  mov     [rbx+10h], esi
0x18000f8a6  mov     [rbx+28h], ebp
0x18000f8a9  mov     rax, qword ptr cs:TimerQ
0x18000f8b0  mov     rcx, rax
0x18000f8b3  mov     rdx, rax
0x18000f8b6  test    rax, rax
0x18000f8b9  jz      short loc_18000F8CE
0x18000f8bb  cmp     [rcx+2Ch], edi
0x18000f8be  jnb     short loc_18000F8CE
0x18000f8c0  sub     edi, [rcx+2Ch]
0x18000f8c3  mov     rdx, rcx
0x18000f8c6  mov     rcx, [rcx]
0x18000f8c9  test    rcx, rcx
0x18000f8cc  jnz     short loc_18000F8BB
0x18000f8ce  test    rcx, rcx
0x18000f8d1  jnz     short loc_18000F90B
0x18000f8d3  test    rax, rax
0x18000f8d6  jnz     short loc_18000F8FB
0x18000f8d8  mov     qword ptr cs:TimerQ, rbx
0x18000f8df  mov     [rbx], rax
0x18000f8e2  mov     [rbx+8], rax
0x18000f8e6  mov     rcx, qword ptr cs:TimerQ+8; hEvent
0x18000f8ed  call    cs:__imp_SetEvent
0x18000f8f4  nop     dword ptr [rax+rax+00h]
0x18000f8f9  jmp     short loc_18000F94D
0x18000f8fb  mov     [rdx], rbx
0x18000f8fe  mov     [rbx+8], rdx
0x18000f902  mov     qword ptr [rbx], 0
0x18000f909  jmp     short loc_18000F94D
0x18000f90b  cmp     rcx, rax
0x18000f90e  jnz     short loc_18000F939
0x18000f910  mov     [rbx], rax
0x18000f913  mov     rax, qword ptr cs:TimerQ
0x18000f91a  mov     [rax+8], rbx
0x18000f91e  mov     rax, qword ptr cs:TimerQ
0x18000f925  sub     [rax+2Ch], edi
0x18000f928  mov     qword ptr [rbx+8], 0
0x18000f930  mov     qword ptr cs:TimerQ, rbx
0x18000f937  jmp     short loc_18000F94D
0x18000f939  mov     rax, [rdx]
0x18000f93c  mov     [rbx], rax
0x18000f93f  mov     [rdx], rbx
0x18000f942  mov     [rbx+8], rdx
0x18000f946  sub     [rcx+2Ch], edi
0x18000f949  mov     [rcx+8], rbx
0x18000f94d  mov     [rbx+2Ch], edi
0x18000f950  xor     eax, eax
0x18000f952  mov     rcx, [rsp+898h+var_48]
0x18000f95a  xor     rcx, rsp; StackCookie
0x18000f95d  call    __security_check_cookie
0x18000f962  mov     rbx, [rsp+898h+arg_8]
0x18000f96a  add     rsp, 860h
0x18000f971  pop     r15
0x18000f973  pop     r14
0x18000f975  pop     r13
0x18000f977  pop     r12
0x18000f979  pop     rdi
0x18000f97a  pop     rsi
0x18000f97b  pop     rbp
0x18000f97c  retn
```
