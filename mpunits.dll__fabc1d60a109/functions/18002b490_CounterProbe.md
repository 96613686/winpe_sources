# CounterProbe

- ea: `0x18002b490`
- end: `0x18002b800`
- name: `CounterProbe`
- size: `880`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x180008b40`
- `0x18000ac44`
- `0x18000b12c`
- `0x18000b3b4`
- `0x18000b408`
- `0x18000b45c`
- `0x18002b490`
- `0x18002c558`
- `0x180044842`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!malloc` at `0x18002b5d7`
- `msvcrt!malloc` at `0x18002b5fd`
- `msvcrt!malloc` at `0x18002b5d7`
- `msvcrt!malloc` at `0x18002b5fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002b684`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002b684`
- `pdh!PdhAddCounterW` at `0x18002b651`
- `pdh!PdhAddCounterW` at `0x18002b651`
- `pdh!PdhOpenQueryW` at `0x18002b5ad`
- `pdh!PdhOpenQueryW` at `0x18002b5ad`

## string_xrefs

- `0x18002b672`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall CounterProbe(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  unsigned int v5; // r15d
  int v6; // edi
  __int64 v7; // r12
  __int64 v8; // rdx
  unsigned int v9; // ebx
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rsi
  __int64 v13; // r14
  int v14; // edx
  unsigned int v15; // eax
  __int64 v16; // rdx
  unsigned int v17; // edi
  void *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  void *v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // rbx
  HMODULE ModuleHandleA; // rax
  int v26; // eax
  int ResultCallback; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-30h] BYREF
  int v32; // [rsp+50h] [rbp-20h]
  int v33; // [rsp+54h] [rbp-1Ch]

  v5 = 0;
  v6 = a1;
  v7 = a2;
  *(_QWORD *)&EventDescriptor.Id = 0;
  if ( a3 )
  {
    if ( !a4 )
    {
      v8 = 250;
      goto LABEL_3;
    }
    if ( !a5 )
    {
      v8 = 251;
      goto LABEL_3;
    }
    v10 = Observable_New(CounterProbe_OnSubscribe, CounterProbe_OnDestroy, &EventDescriptor, 112);
    v9 = v10;
    if ( v10 )
    {
      trace_MI(v10, v11, 255);
      return v9;
    }
    v12 = *(_QWORD *)&EventDescriptor.Id;
    v13 = *(_QWORD *)&EventDescriptor.Id + 40LL;
    memset_0((void *)(*(_QWORD *)&EventDescriptor.Id + 40LL), 0, 0x70u);
    v14 = dword_18006E1E0 + 1;
    *(_QWORD *)v13 = v12;
    v9 = 4;
    dword_18006E1E0 = v14;
    *(_DWORD *)(v13 + 28) = v14;
    *(_DWORD *)&EventDescriptor.Id = 10300;
    *(_DWORD *)&EventDescriptor.Level = 4;
    EventDescriptor.Keyword = 1;
    Etw_Trace1_int(&EventDescriptor);
    *(_QWORD *)(v13 + 16) = 0;
    *(_DWORD *)(v13 + 24) = v6;
    *(_QWORD *)(v13 + 64) = 0;
    *(_QWORD *)(v13 + 88) = Counter_PumpCallback;
    *(_QWORD *)(v13 + 72) = 0;
    *(_QWORD *)(v13 + 80) = 0;
    *(_QWORD *)(v13 + 96) = v13;
    *(_QWORD *)(v13 + 104) = 0;
    v15 = PdhOpenQueryW(0, 0, (PDH_HQUERY *)(v13 + 8));
    v17 = v15;
    if ( v15 )
    {
      trace_PDH(v15, v16, 270);
LABEL_28:
      TryCreatePdhErrorDetails(v17);
      v9 = 1;
      if ( NITS_PRESENCE_STUB != 1 )
      {
        ResultCallback = JobQueryResultCallback();
        *(_QWORD *)&EventDescriptor.Id = 0;
        v32 = 304;
        EventDescriptor.Keyword = (ULONGLONG)"admin\\wmi\\winomi\\mp\\perf\\formattedprobe.c";
        v33 = -1;
        AssertW_Checked(
          ResultCallback == 0,
          (int)"!((NITS_PRESENCE_STUB != NitsStubbedOut) ? NITS_STUB.DidFault() : NitsFalse)",
          (int)L"Ignoring error deliberately",
          (int)&EventDescriptor,
          0);
      }
      goto LABEL_30;
    }
    *(_DWORD *)(v13 + 32) = v7;
    v18 = malloc(4 * v7);
    *(_QWORD *)(v13 + 40) = v18;
    if ( v18 )
    {
      v21 = malloc(8 * v7);
      *(_QWORD *)(v13 + 48) = v21;
      if ( v21 )
      {
        if ( !(_DWORD)v7 )
        {
LABEL_26:
          *a5 = v12;
          return 0;
        }
        v22 = a3;
        while ( 1 )
        {
          trace_ProbeCounter(*(unsigned int *)(v13 + 28), *(_QWORD *)(v22 + 8LL * v5));
          *(_DWORD *)(*(_QWORD *)(v13 + 40) + 4LL * v5) = *(_DWORD *)(a4 + 4LL * v5);
          v17 = PdhAddCounterW(
                  *(PDH_HQUERY *)(v13 + 8),
                  *(LPCWSTR *)(v22 + 8LL * v5),
                  0,
                  (PDH_HCOUNTER *)(*(_QWORD *)(v13 + 48) + 8LL * v5));
          if ( v17 + 1073738817 <= 1 || v17 == -1073738823 )
          {
            EventDescriptor = 0;
            v24 = *(_QWORD *)(v22 + 8LL * v5);
            ModuleHandleA = GetModuleHandleA("mpunits.dll");
            *(_QWORD *)&EventDescriptor.Id = Intlstr_FormatString_FormatMessage(ModuleHandleA, 2030, v24);
            LOBYTE(EventDescriptor.Keyword) = 1;
            MI_ReportErrorDetails_ForCustomError(v17, (int)L"WIN32", 0, 0);
            if ( NITS_PRESENCE_STUB != 1 )
            {
              v26 = JobQueryResultCallback();
              *(_QWORD *)&EventDescriptor.Id = 0;
              v32 = 290;
              EventDescriptor.Keyword = (ULONGLONG)"admin\\wmi\\winomi\\mp\\perf\\formattedprobe.c";
              v33 = -1;
              AssertW_Checked(
                v26 == 0,
                (int)"!((NITS_PRESENCE_STUB != NitsStubbedOut) ? NITS_STUB.DidFault() : NitsFalse)",
                (int)L"Ignoring error deliberately",
                (int)&EventDescriptor,
                0);
            }
            v22 = a3;
          }
          if ( v17 )
            break;
          if ( ++v5 >= (unsigned int)v7 )
            goto LABEL_26;
        }
        trace_PDH(v17, v23, 292);
        goto LABEL_28;
      }
      v20 = 276;
    }
    else
    {
      v20 = 274;
    }
    trace_EH_Check(v19, v20);
LABEL_30:
    if ( v12 )
    {
      if ( *(_QWORD *)v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v9;
  }
  v8 = 249;
LABEL_3:
  trace_EH_Check(a1, v8);
  return 4;
}

```

## disassembly

```asm
0x18002b490  mov     [rsp-38h+arg_0], rbx
0x18002b495  push    rbp
0x18002b496  push    rsi
0x18002b497  push    rdi
0x18002b498  push    r12
0x18002b49a  push    r13
0x18002b49c  push    r14
0x18002b49e  push    r15
0x18002b4a0  mov     rbp, rsp
0x18002b4a3  sub     rsp, 70h
0x18002b4a7  mov     rax, cs:__security_cookie
0x18002b4ae  xor     rax, rsp
0x18002b4b1  mov     [rbp+var_10], rax
0x18002b4b5  mov     r13, [rbp+arg_20]
0x18002b4b9  xor     r15d, r15d
0x18002b4bc  mov     [rbp+var_38], r9
0x18002b4c0  mov     edi, ecx
0x18002b4c2  mov     [rbp+var_40], r8
0x18002b4c6  mov     r12d, edx
0x18002b4c9  mov     qword ptr [rbp+EventDescriptor.Id], r15
0x18002b4cd  test    r8, r8
0x18002b4d0  jnz     short loc_18002B4E6
0x18002b4d2  mov     edx, 0F9h
0x18002b4d7  call    trace_EH_Check
0x18002b4dc  mov     ebx, 4
0x18002b4e1  jmp     loc_18002B7F9
0x18002b4e6  test    r9, r9
0x18002b4e9  jnz     short loc_18002B4F2
0x18002b4eb  mov     edx, 0FAh
0x18002b4f0  jmp     short loc_18002B4D7
0x18002b4f2  test    r13, r13
0x18002b4f5  jnz     short loc_18002B4FE
0x18002b4f7  mov     edx, 0FBh
0x18002b4fc  jmp     short loc_18002B4D7
0x18002b4fe  mov     r9d, 70h ; 'p'
0x18002b504  lea     r8, [rbp+EventDescriptor]
0x18002b508  lea     rdx, CounterProbe_OnDestroy
0x18002b50f  lea     rcx, CounterProbe_OnSubscribe
0x18002b516  call    Observable_New
0x18002b51b  mov     ebx, eax
0x18002b51d  test    eax, eax
0x18002b51f  jz      short loc_18002B533
0x18002b521  mov     r8d, 0FFh
0x18002b527  mov     ecx, eax
0x18002b529  call    trace_MI
0x18002b52e  jmp     loc_18002B7F9
0x18002b533  mov     rsi, qword ptr [rbp+EventDescriptor.Id]
0x18002b537  xor     edx, edx; Val
0x18002b539  lea     r14, [rsi+28h]
0x18002b53d  mov     rcx, r14; void *
0x18002b540  lea     r8d, [rdx+70h]; Size
0x18002b544  call    memset_0
0x18002b549  mov     edx, cs:dword_18006E1E0
0x18002b54f  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x18002b553  inc     edx
0x18002b555  mov     [r14], rsi
0x18002b558  mov     ebx, 4
0x18002b55d  mov     cs:dword_18006E1E0, edx
0x18002b563  mov     [r14+1Ch], edx
0x18002b567  mov     dword ptr [rbp+EventDescriptor.Id], 283Ch
0x18002b56e  mov     dword ptr [rbp+EventDescriptor.Level], ebx
0x18002b571  mov     [rbp+EventDescriptor.Keyword], 1
0x18002b579  call    Etw_Trace1_int
0x18002b57e  lea     rax, Counter_PumpCallback
0x18002b585  mov     [r14+10h], r15
0x18002b589  mov     [r14+18h], edi
0x18002b58d  lea     r8, [r14+8]; phQuery
0x18002b591  mov     [r14+40h], r15
0x18002b595  xor     edx, edx; dwUserData
0x18002b597  xor     ecx, ecx; szDataSource
0x18002b599  mov     [r14+58h], rax
0x18002b59d  mov     [r14+48h], r15
0x18002b5a1  mov     [r14+50h], r15
0x18002b5a5  mov     [r14+60h], r14
0x18002b5a9  mov     [r14+68h], r15
0x18002b5ad  call    cs:__imp_PdhOpenQueryW
0x18002b5b3  mov     edi, eax
0x18002b5b5  test    eax, eax
0x18002b5b7  jz      short loc_18002B5CB
0x18002b5b9  mov     r8d, 10Eh
0x18002b5bf  mov     ecx, eax
0x18002b5c1  call    trace_PDH
0x18002b5c6  jmp     loc_18002B777
0x18002b5cb  lea     rcx, ds:0[r12*4]; Size
0x18002b5d3  mov     [r14+20h], r12d
0x18002b5d7  call    cs:__imp_malloc
0x18002b5dd  mov     [r14+28h], rax
0x18002b5e1  test    rax, rax
0x18002b5e4  jnz     short loc_18002B5F5
0x18002b5e6  mov     edx, 112h
0x18002b5eb  call    trace_EH_Check
0x18002b5f0  jmp     loc_18002B7E0
0x18002b5f5  lea     rcx, ds:0[r12*8]; Size
0x18002b5fd  call    cs:__imp_malloc
0x18002b603  mov     [r14+30h], rax
0x18002b607  test    rax, rax
0x18002b60a  jnz     short loc_18002B613
0x18002b60c  mov     edx, 114h
0x18002b611  jmp     short loc_18002B5EB
0x18002b613  test    r12d, r12d
0x18002b616  jz      loc_18002B73D
0x18002b61c  mov     rbx, [rbp+var_40]
0x18002b620  mov     ecx, [r14+1Ch]
0x18002b624  mov     edi, r15d
0x18002b627  mov     rdx, [rbx+rdi*8]
0x18002b62b  call    trace_ProbeCounter
0x18002b630  mov     rcx, [r14+28h]
0x18002b634  xor     r8d, r8d; dwUserData
0x18002b637  mov     rax, [rbp+var_38]
0x18002b63b  mov     eax, [rax+rdi*4]
0x18002b63e  mov     [rcx+rdi*4], eax
0x18002b641  mov     rax, [r14+30h]
0x18002b645  mov     rdx, [rbx+rdi*8]; szFullCounterPath
0x18002b649  mov     rcx, [r14+8]; hQuery
0x18002b64d  lea     r9, [rax+rdi*8]; phCounter
0x18002b651  call    cs:__imp_PdhAddCounterW
0x18002b657  mov     edi, eax
0x18002b659  add     eax, 3FFFF441h
0x18002b65e  cmp     eax, 1
0x18002b661  jbe     short loc_18002B66F
0x18002b663  cmp     edi, 0C0000BB9h
0x18002b669  jnz     loc_18002B72D
0x18002b66f  mov     eax, r15d
0x18002b672  lea     rcx, ModuleName; "mpunits.dll"
0x18002b679  xorps   xmm0, xmm0
0x18002b67c  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18002b680  mov     rbx, [rbx+rax*8]
0x18002b684  call    cs:__imp_GetModuleHandleA
0x18002b68a  mov     r8, rbx
0x18002b68d  mov     edx, 7EEh
0x18002b692  mov     rcx, rax
0x18002b695  call    _Intlstr_FormatString_FormatMessage
0x18002b69a  xor     ebx, ebx
0x18002b69c  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x18002b6a0  mov     byte ptr [rbp+EventDescriptor.Keyword], 1
0x18002b6a4  lea     r9, [rbp+EventDescriptor]
0x18002b6a8  movaps  xmm0, xmmword ptr [rbp+EventDescriptor.Id]
0x18002b6ac  lea     rdx, aWin32; "WIN32"
0x18002b6b3  mov     [rsp+70h+var_48], rbx; __int64
0x18002b6b8  mov     ecx, edi; int
0x18002b6ba  lea     r8d, [rbx+5]
0x18002b6be  movdqa  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18002b6c3  mov     [rsp+70h+var_50], rbx; __int64
0x18002b6c8  call    MI_ReportErrorDetails_ForCustomError
0x18002b6cd  cmp     cs:NITS_PRESENCE_STUB, 1
0x18002b6d5  jz      short loc_18002B729
0x18002b6d7  mov     rax, cs:off_180047AB8
0x18002b6de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6e3  test    eax, eax
0x18002b6e5  mov     qword ptr [rbp+EventDescriptor.Id], rbx
0x18002b6e9  lea     rax, aAdminWmiWinomi_15; "admin\\wmi\\winomi\\mp\\perf\\formatted"...
0x18002b6f0  mov     [rbp+var_20], 122h
0x18002b6f7  mov     ecx, ebx
0x18002b6f9  mov     [rbp+EventDescriptor.Keyword], rax
0x18002b6fd  mov     rax, cs:off_180047A80
0x18002b704  lea     r9, [rbp+EventDescriptor]
0x18002b708  setz    cl
0x18002b70b  mov     [rbp+var_1C], 0FFFFFFFFh
0x18002b712  lea     r8, aIgnoringErrorD; "Ignoring error deliberately"
0x18002b719  mov     dword ptr [rsp+70h+var_50], ebx
0x18002b71d  lea     rdx, aNitsPresenceSt_0; "!((NITS_PRESENCE_STUB != NitsStubbedOut"...
0x18002b724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b729  mov     rbx, [rbp+var_40]
0x18002b72d  test    edi, edi
0x18002b72f  jnz     short loc_18002B767
0x18002b731  inc     r15d
0x18002b734  cmp     r15d, r12d
0x18002b737  jb      loc_18002B620
0x18002b73d  mov     [r13+0], rsi
0x18002b741  xor     eax, eax
0x18002b743  mov     rcx, [rbp+var_10]
0x18002b747  xor     rcx, rsp; StackCookie
0x18002b74a  call    __security_check_cookie
0x18002b74f  mov     rbx, [rsp+70h+arg_0]
0x18002b757  add     rsp, 70h
0x18002b75b  pop     r15
0x18002b75d  pop     r14
0x18002b75f  pop     r13
0x18002b761  pop     r12
0x18002b763  pop     rdi
0x18002b764  pop     rsi
0x18002b765  pop     rbp
0x18002b766  retn
0x18002b767  mov     r8d, 124h
0x18002b76d  mov     ecx, edi
0x18002b76f  call    trace_PDH
0x18002b774  xor     r15d, r15d
0x18002b777  mov     ecx, edi; int
0x18002b779  call    TryCreatePdhErrorDetails
0x18002b77e  mov     ebx, 1
0x18002b783  cmp     cs:NITS_PRESENCE_STUB, rbx
0x18002b78a  jz      short loc_18002B7E0
0x18002b78c  mov     rax, cs:off_180047AB8
0x18002b793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b798  test    eax, eax
0x18002b79a  mov     qword ptr [rbp+EventDescriptor.Id], r15
0x18002b79e  lea     rax, aAdminWmiWinomi_15; "admin\\wmi\\winomi\\mp\\perf\\formatted"...
0x18002b7a5  mov     [rbp+var_20], 130h
0x18002b7ac  mov     ecx, r15d
0x18002b7af  mov     [rbp+EventDescriptor.Keyword], rax
0x18002b7b3  mov     rax, cs:off_180047A80
0x18002b7ba  lea     r9, [rbp+EventDescriptor]
0x18002b7be  setz    cl
0x18002b7c1  mov     [rbp+var_1C], 0FFFFFFFFh
0x18002b7c8  lea     r8, aIgnoringErrorD; "Ignoring error deliberately"
0x18002b7cf  mov     dword ptr [rsp+70h+var_50], r15d
0x18002b7d4  lea     rdx, aNitsPresenceSt_0; "!((NITS_PRESENCE_STUB != NitsStubbedOut"...
0x18002b7db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7e0  test    rsi, rsi
0x18002b7e3  jz      short loc_18002B7F9
0x18002b7e5  mov     rax, [rsi]
0x18002b7e8  test    rax, rax
0x18002b7eb  jz      short loc_18002B7F9
0x18002b7ed  mov     rax, [rax+10h]
0x18002b7f1  mov     rcx, rsi
0x18002b7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7f9  mov     eax, ebx
0x18002b7fb  jmp     loc_18002B743
```
