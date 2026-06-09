# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x1800218a0`
- end: `0x180021a10`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `368`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::ModuleBase *modulePtr, const wchar_t *activatibleClassId, HSTRING ppFactory, IUnknown **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022490`

## callees

- `0x180002790`
- `0x1800218a0`
- `0x180021ef0`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800219a8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800219a8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800219e7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800219e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800218f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800218f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002190e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002190e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800218da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800218da`

## string_xrefs

- `0x1800219b0`: `activatibleClassId`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Details::GetActivationFactory<1>(
        Microsoft::WRL::Details::ModuleBase *modulePtr,
        const wchar_t *activatibleClassId,
        HSTRING ppFactory,
        IUnknown **a4)
{
  PCWSTR StringRawBuffer; // r15
  const Microsoft::WRL::Details::CreatorMap **v8; // rbx
  const Microsoft::WRL::Details::CreatorMap **v9; // rbp
  __int64 v10; // rax
  unsigned __int16 *v11; // rcx
  __int64 v12; // rax
  int v13; // r8d
  int v14; // edx
  int v16; // ebx
  int hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  unsigned int currentFlags; // [rsp+34h] [rbp-64h] BYREF
  wchar_t pszParamName[20]; // [rsp+38h] [rbp-60h] BYREF

  *a4 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(ppFactory)
    || WindowsStringHasEmbeddedNull(ppFactory, &hasEmbedNull) < 0
    || hasEmbedNull == 1 )
  {
    wcscpy(pszParamName, L"activatibleClasId");
    v16 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, pszParamName);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(ppFactory, 0);
    v8 = modulePtr->GetMidEntryPointer(modulePtr) + 1;
    v9 = modulePtr->GetLastEntryPointer(modulePtr);
    while ( v8 < v9 )
    {
      if ( *v8 )
      {
        v10 = ((__int64 (*)(void))(*v8)->activationId.clsid)();
        v11 = (unsigned __int16 *)StringRawBuffer;
        v12 = v10 - (_QWORD)StringRawBuffer;
        do
        {
          v13 = *(unsigned __int16 *)((char *)v11 + v12);
          v14 = *v11 - v13;
          if ( v14 )
            break;
          ++v11;
        }
        while ( v13 );
        if ( !v14 )
        {
          currentFlags = 1;
          return Microsoft::WRL::Details::GetCacheEntry(
                   modulePtr,
                   &currentFlags,
                   &GUID_00000035_0000_0000_c000_000000000046,
                   *v8,
                   a4);
        }
      }
      ++v8;
    }
    v16 = -2147221231;
    RoOriginateError(2147746065LL, ppFactory);
  }
  return v16;
}

```

## disassembly

```asm
0x1800218a0  mov     [rsp+arg_8], rbx
0x1800218a5  push    rbp
0x1800218a6  push    rsi
0x1800218a7  push    rdi
0x1800218a8  push    r14
0x1800218aa  push    r15
0x1800218ac  sub     rsp, 70h
0x1800218b0  mov     rax, cs:__security_cookie
0x1800218b7  xor     rax, rsp
0x1800218ba  mov     [rsp+98h+var_38], rax
0x1800218bf  mov     r14, ppFactory
0x1800218c2  mov     rdi, activatibleClassId
0x1800218c5  mov     rsi, modulePtr
0x1800218c8  mov     qword ptr [ppFactory], 0
0x1800218cf  mov     [rsp+98h+hasEmbedNull], 0
0x1800218d7  mov     modulePtr, activatibleClassId; string
0x1800218da  call    cs:__imp_WindowsIsStringEmpty
0x1800218e0  test    eax, eax
0x1800218e2  jnz     loc_1800219B0
0x1800218e8  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x1800218ed  mov     modulePtr, rdi; string
0x1800218f0  call    cs:__imp_WindowsStringHasEmbeddedNull
0x1800218f6  test    eax, eax
0x1800218f8  js      loc_1800219B0
0x1800218fe  cmp     [rsp+98h+hasEmbedNull], 1
0x180021903  jz      loc_1800219B0
0x180021909  xor     edx, edx; length
0x18002190b  mov     modulePtr, rdi; string
0x18002190e  call    cs:__imp_WindowsGetStringRawBuffer
0x180021914  mov     r15, rax
0x180021917  mov     modulePtr, [rsi]
0x18002191a  mov     rax, [modulePtr+28h]
0x18002191e  mov     modulePtr, rsi
0x180021921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021926  lea     rbx, [rax+8]
0x18002192a  mov     modulePtr, [rsi]
0x18002192d  mov     rax, [modulePtr+30h]
0x180021931  mov     modulePtr, rsi
0x180021934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021939  mov     rbp, rax
0x18002193c  cmp     rbx, rbp
0x18002193f  jnb     short loc_18002199E
0x180021941  mov     rax, [rbx]
0x180021944  test    rax, rax
0x180021947  jz      short loc_180021972
0x180021949  mov     rax, [rax+8]
0x18002194d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021952  mov     modulePtr, r15
0x180021955  sub     rax, r15
0x180021958  movzx   edx, word ptr [modulePtr]
0x18002195b  movzx   r8d, word ptr [modulePtr+rax]
0x180021960  sub     edx, r8d
0x180021963  jnz     short loc_18002196E
0x180021965  add     modulePtr, 2
0x180021969  test    r8d, r8d
0x18002196c  jnz     short loc_180021958
0x18002196e  test    edx, edx
0x180021970  jz      short loc_180021978
0x180021972  add     rbx, 8
0x180021976  jmp     short loc_18002193C
0x180021978  mov     [rsp+98h+currentFlags], 1
0x180021980  mov     [rsp+98h+var_78], r14; ppFactory
0x180021985  mov     ppFactory, [rbx]; entry
0x180021988  lea     activatibleClassId, _GUID_00000035_0000_0000_c000_000000000046; riid
0x18002198f  lea     rdx, [rsp+98h+currentFlags]; flags
0x180021994  mov     modulePtr, rsi; modulePtr
0x180021997  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18002199c  jmp     short loc_1800219EF
0x18002199e  mov     rdx, rdi
0x1800219a1  mov     ebx, 80040111h
0x1800219a6  mov     ecx, ebx
0x1800219a8  call    cs:__imp_RoOriginateError
0x1800219ae  jmp     short loc_1800219ED
0x1800219b0  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x1800219b7  movups  xmmword ptr [rsp+98h+pszParamName], xmm0
0x1800219bc  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x1800219c3  movups  xmmword ptr [rsp+98h+pszParamName+10h], xmm1
0x1800219c8  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x1800219d0  movsd   qword ptr [rsp+98h+pszParamName+1Eh], xmm0
0x1800219d6  lea     activatibleClassId, [rsp+98h+pszParamName]
0x1800219db  mov     edx, 12h
0x1800219e0  mov     ebx, 80070057h
0x1800219e5  mov     ecx, ebx
0x1800219e7  call    cs:__imp_RoOriginateErrorW
0x1800219ed  mov     eax, ebx
0x1800219ef  mov     modulePtr, [rsp+98h+var_38]
0x1800219f4  xor     modulePtr, rsp; StackCookie
0x1800219f7  call    __security_check_cookie
0x1800219fc  mov     rbx, [rsp+98h+arg_8]
0x180021a04  add     rsp, 70h
0x180021a08  pop     r15
0x180021a0a  pop     r14
0x180021a0c  pop     rdi
0x180021a0d  pop     rsi
0x180021a0e  pop     rbp
0x180021a0f  retn
```
