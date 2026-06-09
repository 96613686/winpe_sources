# CDCMPool::GetCurrentSID(void * *)

- ea: `0x180065390`
- end: `0x1800655c6`
- name: `?GetCurrentSID@CDCMPool@@QEAAJPEAPEAX@Z`
- size: `566`
- prototype: `__int64 __fastcall(CDCMPool *__hidden this, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180064720`
- `0x180065d04`

## callees

- `0x180011bcc`
- `0x180013870`
- `0x180029560`
- `0x180065390`
- `0x18007e6ca`
- `0x18007e700`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x1800654c9`
- `MSDART!MpHeapAlloc` at `0x18006551e`
- `MSDART!MpHeapAlloc` at `0x1800654c9`
- `MSDART!MpHeapAlloc` at `0x18006551e`
- `KERNEL32!GetLastError` at `0x180065412`
- `KERNEL32!GetLastError` at `0x180065412`
- `KERNEL32!GetCurrentProcess` at `0x18006541f`
- `KERNEL32!GetCurrentProcess` at `0x18006541f`
- `KERNEL32!CloseHandle` at `0x180065554`
- `KERNEL32!CloseHandle` at `0x180065554`
- `KERNEL32!GetCurrentThread` at `0x1800653ed`
- `KERNEL32!GetCurrentThread` at `0x1800653ed`
- `ADVAPI32!OpenProcessToken` at `0x180065431`
- `ADVAPI32!OpenProcessToken` at `0x180065431`
- `ADVAPI32!GetTokenInformation` at `0x18006547d`
- `ADVAPI32!GetTokenInformation` at `0x1800654f3`
- `ADVAPI32!GetTokenInformation` at `0x18006547d`
- `ADVAPI32!GetTokenInformation` at `0x1800654f3`
- `ADVAPI32!OpenThreadToken` at `0x180065403`
- `ADVAPI32!OpenThreadToken` at `0x180065403`
- `ADVAPI32!CopySid` at `0x180065535`
- `ADVAPI32!CopySid` at `0x180065535`
- `ADVAPI32!GetLengthSid` at `0x180065506`
- `ADVAPI32!GetLengthSid` at `0x180065506`

## string_xrefs

- `0x18006544e`: `<CDCMPool::GetCurrentSID|OLEDB|ERR> `
- `0x1800654a3`: `<CDCMPool::GetCurrentSID|OLEDB|ERR> `
- `0x18006558f`: `<CDCMPool::GetCurrentSID|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CDCMPool::GetCurrentSID(CDCMPool *this, void **a2)
{
  int v3; // r15d
  PSID *v4; // rdi
  HANDLE CurrentThread; // rax
  unsigned int v6; // ebx
  HANDLE CurrentProcess; // rax
  DWORD v8; // eax
  DWORD LengthSid; // r14d
  void *v10; // rax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ReturnLength[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE TokenInformation[1024]; // [rsp+50h] [rbp-B0h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 0;
  memset_0(TokenInformation, 0, sizeof(TokenInformation));
  v3 = 0;
  v4 = (PSID *)TokenInformation;
  *a2 = 0;
  CurrentThread = GetCurrentThread();
  v6 = -2147467259;
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
    || GetLastError() == 1008
    && (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 8u, &TokenHandle)) )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x400u, &TokenInformationLength) )
      goto LABEL_12;
    v8 = TokenInformationLength;
    if ( TokenInformationLength > 0x400 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147467259, L"<CDCMPool::GetCurrentSID|OLEDB|ERR> ", 0x71Eu);
        v8 = TokenInformationLength;
      }
      ReturnLength[0] = 0;
      v4 = (PSID *)MpHeapAlloc(g_hHeapHandle, 19922944, v8);
      if ( v4 )
      {
        v3 = 1;
        if ( GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, ReturnLength) )
        {
LABEL_12:
          LengthSid = GetLengthSid(*v4);
          v10 = (void *)MpHeapAlloc(g_hHeapHandle, 19922944, LengthSid);
          *a2 = v10;
          if ( v10 )
            v6 = !CopySid(LengthSid, v10, *v4) ? 0x80004005 : 0;
          else
            v6 = -2147024882;
        }
      }
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(-2147467259, L"<CDCMPool::GetCurrentSID|OLEDB|ERR> ", 0x70Cu);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v3 )
    operator delete(v4);
  if ( (v6 & 0x80000000) != 0 && *a2 )
  {
    operator delete(*a2);
    *a2 = 0;
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C8440[0], 1933321, L"<CDCMPool::GetCurrentSID|Trace|HR> ", v6);
  return v6;
}

```

## disassembly

```asm
0x180065390  push    rbp
0x180065392  push    rbx
0x180065393  push    rsi
0x180065394  push    rdi
0x180065395  push    r14
0x180065397  push    r15
0x180065399  lea     rbp, [rsp-368h]
0x1800653a1  sub     rsp, 468h
0x1800653a8  mov     rax, cs:__security_cookie
0x1800653af  xor     rax, rsp
0x1800653b2  mov     [rbp+390h+var_40], rax
0x1800653b9  mov     rsi, rdx
0x1800653bc  mov     [rsp+490h+TokenHandle], 0
0x1800653c5  mov     r14d, 400h
0x1800653cb  mov     [rsp+490h+TokenInformationLength], 0
0x1800653d3  mov     r8d, r14d; Size
0x1800653d6  lea     rcx, [rsp+490h+TokenInformation]; void *
0x1800653db  xor     edx, edx; Val
0x1800653dd  call    memset_0
0x1800653e2  xor     r15d, r15d
0x1800653e5  lea     rdi, [rsp+490h+TokenInformation]
0x1800653ea  mov     [rsi], r15
0x1800653ed  call    cs:__imp_GetCurrentThread
0x1800653f3  mov     rcx, rax; ThreadHandle
0x1800653f6  lea     r9, [rsp+490h+TokenHandle]; TokenHandle
0x1800653fb  lea     edx, [r15+8]; DesiredAccess
0x1800653ff  lea     r8d, [r15+1]; OpenAsSelf
0x180065403  call    cs:__imp_OpenThreadToken
0x180065409  mov     ebx, 80004005h
0x18006540e  test    eax, eax
0x180065410  jnz     short loc_180065461
0x180065412  call    cs:__imp_GetLastError
0x180065418  cmp     eax, 3F0h
0x18006541d  jnz     short loc_18006543B
0x18006541f  call    cs:__imp_GetCurrentProcess
0x180065425  mov     rcx, rax; ProcessHandle
0x180065428  lea     r8, [rsp+490h+TokenHandle]; TokenHandle
0x18006542d  lea     edx, [r15+8]; DesiredAccess
0x180065431  call    cs:__imp_OpenProcessToken
0x180065437  test    eax, eax
0x180065439  jnz     short loc_180065461
0x18006543b  test    byte ptr cs:_bidGblFlags, 2
0x180065442  jz      loc_18006554A
0x180065448  mov     r8d, 70Ch; unsigned int
0x18006544e  lea     rdx, aCdcmpoolGetcur_1; "<CDCMPool::GetCurrentSID|OLEDB|ERR> "
0x180065455  mov     ecx, ebx; int
0x180065457  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006545c  jmp     loc_18006554A
0x180065461  mov     rcx, [rsp+490h+TokenHandle]; TokenHandle
0x180065466  lea     rax, [rsp+490h+TokenInformationLength]
0x18006546b  mov     r9d, r14d; TokenInformationLength
0x18006546e  mov     [rsp+490h+ReturnLength], rax; ReturnLength
0x180065473  lea     r8, [rsp+490h+TokenInformation]; TokenInformation
0x180065478  mov     edx, 1; TokenInformationClass
0x18006547d  call    cs:__imp_GetTokenInformation
0x180065483  test    eax, eax
0x180065485  jnz     short loc_180065503
0x180065487  mov     eax, [rsp+490h+TokenInformationLength]
0x18006548b  cmp     eax, r14d
0x18006548e  jbe     loc_18006554A
0x180065494  test    byte ptr cs:_bidGblFlags, 2
0x18006549b  jz      short loc_1800654B5
0x18006549d  mov     r8d, 71Eh; unsigned int
0x1800654a3  lea     rdx, aCdcmpoolGetcur_1; "<CDCMPool::GetCurrentSID|OLEDB|ERR> "
0x1800654aa  mov     ecx, ebx; int
0x1800654ac  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800654b1  mov     eax, [rsp+490h+TokenInformationLength]
0x1800654b5  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800654bc  mov     edx, 1300000h
0x1800654c1  mov     r8d, eax
0x1800654c4  mov     [rsp+490h+var_450], r15d
0x1800654c9  call    cs:__imp_MpHeapAlloc
0x1800654cf  mov     rdi, rax
0x1800654d2  test    rax, rax
0x1800654d5  jz      short loc_18006554A
0x1800654d7  mov     r9d, [rsp+490h+TokenInformationLength]; TokenInformationLength
0x1800654dc  lea     rax, [rsp+490h+var_450]
0x1800654e1  mov     rcx, [rsp+490h+TokenHandle]; TokenHandle
0x1800654e6  mov     r8, rdi; TokenInformation
0x1800654e9  mov     edx, 1; TokenInformationClass
0x1800654ee  mov     [rsp+490h+ReturnLength], rax; ReturnLength
0x1800654f3  call    cs:__imp_GetTokenInformation
0x1800654f9  mov     r15d, 1
0x1800654ff  test    eax, eax
0x180065501  jz      short loc_18006554A
0x180065503  mov     rcx, [rdi]; pSid
0x180065506  call    cs:__imp_GetLengthSid
0x18006550c  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180065513  mov     edx, 1300000h
0x180065518  mov     r8d, eax
0x18006551b  mov     r14d, eax
0x18006551e  call    cs:__imp_MpHeapAlloc
0x180065524  mov     [rsi], rax
0x180065527  test    rax, rax
0x18006552a  jz      short loc_180065545
0x18006552c  mov     r8, [rdi]; pSourceSid
0x18006552f  mov     rdx, rax; pDestinationSid
0x180065532  mov     ecx, r14d; nDestinationSidLength
0x180065535  call    cs:__imp_CopySid
0x18006553b  neg     eax
0x18006553d  sbb     ecx, ecx
0x18006553f  not     ecx
0x180065541  and     ebx, ecx
0x180065543  jmp     short loc_18006554A
0x180065545  mov     ebx, 8007000Eh
0x18006554a  mov     rcx, [rsp+490h+TokenHandle]; hObject
0x18006554f  test    rcx, rcx
0x180065552  jz      short loc_18006555A
0x180065554  call    cs:__imp_CloseHandle
0x18006555a  test    r15d, r15d
0x18006555d  jz      short loc_180065567
0x18006555f  mov     rcx, rdi; void *
0x180065562  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180065567  test    ebx, ebx
0x180065569  jns     short loc_18006557F
0x18006556b  mov     rcx, [rsi]; void *
0x18006556e  test    rcx, rcx
0x180065571  jz      short loc_18006557F
0x180065573  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180065578  mov     qword ptr [rsi], 0
0x18006557f  test    byte ptr cs:_bidGblFlags, 2
0x180065586  jz      short loc_1800655A5
0x180065588  mov     rcx, cs:off_1800C8440; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006558f  lea     r8, aCdcmpoolGetcur_0; "<CDCMPool::GetCurrentSID|Trace|HR> "
0x180065596  mov     r9d, ebx
0x180065599  mov     edx, 1D8009h
0x18006559e  call    _bidTraceHR
0x1800655a3  mov     ebx, eax
0x1800655a5  mov     eax, ebx
0x1800655a7  mov     rcx, [rbp+390h+var_40]
0x1800655ae  xor     rcx, rsp; StackCookie
0x1800655b1  call    __security_check_cookie
0x1800655b6  add     rsp, 468h
0x1800655bd  pop     r15
0x1800655bf  pop     r14
0x1800655c1  pop     rdi
0x1800655c2  pop     rsi
0x1800655c3  pop     rbx
0x1800655c4  pop     rbp
0x1800655c5  retn
```
