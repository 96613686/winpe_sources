# CBrokeredClipDataObject::InvokeAsClipboard(IRunAsClipboard *)

- ea: `0x180090530`
- end: `0x1800906cb`
- name: `?InvokeAsClipboard@CBrokeredClipDataObject@@UEAAJPEAUIRunAsClipboard@@@Z`
- size: `411`
- prototype: `HRESULT __fastcall(CBrokeredClipDataObject *this, IRunAsClipboard *pTarget)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18008c104`
- `0x180090530`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800905f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800905f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090647`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800905e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800905e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800905c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800905c8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180090637`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180090696`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180090637`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180090696`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800906a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800906a7`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800905ac`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800905ac`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180090556`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18009061d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180090666`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180090556`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18009061d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180090666`

## pseudocode

```c
HRESULT __fastcall CBrokeredClipDataObject::InvokeAsClipboard(CBrokeredClipDataObject *this, IRunAsClipboard *pTarget)
{
  signed int v4; // ebx
  HRESULT result; // eax
  HRESULT v6; // eax
  HANDLE CurrentThread; // rax
  char v8; // bp
  signed int LastError; // eax
  signed int v10; // eax
  void *hRevert; // [rsp+58h] [rbp+10h] BYREF

  if ( !pTarget )
  {
    v4 = -2147024809;
    RoOriginateError(2147942487LL, 0);
    return v4;
  }
  if ( !*(_QWORD *)&this->m_refs )
    return -2147024891;
  result = CheckCallerIntegrityLevelIsAtLeast((unsigned int)this);
  if ( result >= 0 )
  {
    v6 = CoSetProxyBlanket(
           pTarget,
           0xFFFFFFFF,
           0xFFFFFFFF,
           (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
           0,
           3u,
           (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
           0x800u);
    hRevert = 0;
    v4 = v6;
    if ( v6 >= 0 )
    {
      CurrentThread = GetCurrentThread();
      v8 = 1;
      if ( OpenThreadToken(CurrentThread, 4u, 1, &hRevert) )
        goto LABEL_21;
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError == 1008 )
        goto LABEL_21;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      RoOriginateError((unsigned int)v4, 0);
      if ( v4 >= 0 )
      {
LABEL_21:
        if ( SetThreadToken(0, *(HANDLE *)&this->m_refs) )
          goto LABEL_16;
        v10 = GetLastError();
        v4 = v10;
        if ( v10 > 0 )
          v4 = (unsigned __int16)v10 | 0x80070000;
        RoOriginateError((unsigned int)v4, 0);
        v8 = 0;
        if ( v4 >= 0 )
        {
LABEL_16:
          v4 = ((__int64 (__fastcall *)(IRunAsClipboard *))pTarget->lpVtbl[1].QueryInterface)(pTarget);
          if ( v8 )
          {
            SetThreadToken(0, hRevert);
            CloseHandle(hRevert);
          }
        }
      }
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180090530  mov     [rsp+arg_0], rbx
0x180090535  mov     [rsp+arg_10], rbp
0x18009053a  mov     [rsp+arg_18], rsi
0x18009053f  push    rdi
0x180090540  sub     rsp, 40h
0x180090544  mov     rdi, pTarget
0x180090547  mov     rsi, this
0x18009054a  test    pTarget, pTarget
0x18009054d  jnz     short loc_180090567
0x18009054f  mov     ebx, 80070057h
0x180090554  mov     ecx, ebx
0x180090556  call    cs:__imp_RoOriginateError
0x18009055d  nop     dword ptr [rax+rax+00h]
0x180090562  jmp     loc_1800906B3
0x180090567  cmp     qword ptr [this+10h], 0
0x18009056c  jnz     short loc_180090578
0x18009056e  mov     eax, 80070005h
0x180090573  jmp     loc_1800906B5
0x180090578  call    ?CheckCallerIntegrityLevelIsAtLeast@@YAJK@Z; CheckCallerIntegrityLevelIsAtLeast(ulong)
0x18009057d  test    eax, eax
0x18009057f  js      loc_1800906B5
0x180090585  mov     [rsp+48h+dwCapabilities], 800h; dwCapabilities
0x18009058d  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180090591  mov     [rsp+48h+pAuthInfo], r9; pAuthInfo
0x180090596  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180090599  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x1800905a1  mov     r8d, edx; dwAuthzSvc
0x1800905a4  and     [rsp+48h+var_28], 0
0x1800905a9  mov     this, rdi; pProxy
0x1800905ac  call    cs:__imp_CoSetProxyBlanket
0x1800905b3  nop     dword ptr [rax+rax+00h]
0x1800905b8  and     [rsp+48h+hRevert], 0
0x1800905be  mov     ebx, eax
0x1800905c0  test    eax, eax
0x1800905c2  js      loc_1800906B3
0x1800905c8  call    cs:__imp_GetCurrentThread
0x1800905cf  nop     dword ptr [rax+rax+00h]
0x1800905d4  mov     ebp, 1
0x1800905d9  lea     r9, [rsp+48h+hRevert]; TokenHandle
0x1800905de  mov     this, rax; ThreadHandle
0x1800905e1  mov     r8d, ebp; OpenAsSelf
0x1800905e4  lea     edx, [rbp+3]; DesiredAccess
0x1800905e7  call    cs:__imp_OpenThreadToken
0x1800905ee  nop     dword ptr [rax+rax+00h]
0x1800905f3  test    eax, eax
0x1800905f5  jnz     short loc_180090631
0x1800905f7  call    cs:__imp_GetLastError
0x1800905fe  nop     dword ptr [rax+rax+00h]
0x180090603  mov     ebx, eax
0x180090605  cmp     eax, 3F0h
0x18009060a  jz      short loc_180090631
0x18009060c  test    eax, eax
0x18009060e  jle     short loc_180090619
0x180090610  movzx   ebx, ax
0x180090613  or      ebx, 80070000h
0x180090619  xor     edx, edx
0x18009061b  mov     ecx, ebx
0x18009061d  call    cs:__imp_RoOriginateError
0x180090624  nop     dword ptr [rax+rax+00h]
0x180090629  test    ebx, ebx
0x18009062b  js      loc_1800906B3
0x180090631  mov     pTarget, [rsi+10h]; Token
0x180090635  xor     ecx, ecx; Thread
0x180090637  call    cs:__imp_SetThreadToken
0x18009063e  nop     dword ptr [rax+rax+00h]
0x180090643  test    eax, eax
0x180090645  jnz     short loc_180090679
0x180090647  call    cs:__imp_GetLastError
0x18009064e  nop     dword ptr [rax+rax+00h]
0x180090653  mov     ebx, eax
0x180090655  test    eax, eax
0x180090657  jle     short loc_180090662
0x180090659  movzx   ebx, ax
0x18009065c  or      ebx, 80070000h
0x180090662  xor     edx, edx
0x180090664  mov     ecx, ebx
0x180090666  call    cs:__imp_RoOriginateError
0x18009066d  nop     dword ptr [rax+rax+00h]
0x180090672  xor     bpl, bpl
0x180090675  test    ebx, ebx
0x180090677  js      short loc_1800906B3
0x180090679  mov     rax, [rdi]
0x18009067c  mov     this, rdi
0x18009067f  mov     rax, [rax+18h]
0x180090683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090688  mov     ebx, eax
0x18009068a  test    bpl, bpl
0x18009068d  jz      short loc_1800906B3
0x18009068f  mov     pTarget, [rsp+48h+hRevert]; Token
0x180090694  xor     ecx, ecx; Thread
0x180090696  call    cs:__imp_SetThreadToken
0x18009069d  nop     dword ptr [rax+rax+00h]
0x1800906a2  mov     this, [rsp+48h+hRevert]; hObject
0x1800906a7  call    cs:__imp_CloseHandle
0x1800906ae  nop     dword ptr [rax+rax+00h]
0x1800906b3  mov     eax, ebx
0x1800906b5  mov     rbx, [rsp+48h+arg_0]
0x1800906ba  mov     rbp, [rsp+48h+arg_10]
0x1800906bf  mov     rsi, [rsp+48h+arg_18]
0x1800906c4  add     rsp, 40h
0x1800906c8  pop     rdi
0x1800906c9  retn
```
