# Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)

- ea: `0x180008a70`
- end: `0x180008be0`
- name: `??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(HSTRING string, struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001770`
- `0x180008a70`
- `0x180009a80`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180008bb6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180008bb6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008b56`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008b56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180008aab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180008aab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180008ac1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180008ac1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008adf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008adf`

## string_xrefs

- `0x180008b7f`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ActivationFactoryCallback<2>(
        HSTRING string,
        struct Microsoft::WRL::Details::CreatorMap *a2)
{
  Microsoft::WRL::Details *v4; // rsi
  PCWSTR StringRawBuffer; // r15
  const struct _GUID **v6; // rbx
  unsigned __int64 v7; // rbp
  __int64 v8; // rax
  unsigned __int16 *v9; // rcx
  __int64 v10; // rax
  unsigned int *v11; // r8
  int v12; // edx
  unsigned int v13; // ebx
  struct IUnknown **v15; // [rsp+28h] [rbp-70h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  int v17; // [rsp+34h] [rbp-64h] BYREF
  __int128 v18; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v19[22]; // [rsp+48h] [rbp-50h]

  v4 = Microsoft::WRL::Details::ModuleBase::module_;
  *(_QWORD *)a2 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v18 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v19 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v19[14] = *(_QWORD *)L"sId";
    v13 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v18);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v6 = (const struct _GUID **)((*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)v4 + 40LL))(v4) + 8);
    v7 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)v4 + 48LL))(v4);
    if ( (unsigned __int64)v6 >= v7 )
    {
LABEL_11:
      v13 = -2147221231;
      RoOriginateError(2147746065LL, string);
    }
    else
    {
      while ( 1 )
      {
        if ( *v6 )
        {
          v8 = (*(__int64 (**)(void))(*v6)->Data4)();
          v9 = (unsigned __int16 *)StringRawBuffer;
          v10 = v8 - (_QWORD)StringRawBuffer;
          do
          {
            v11 = (unsigned int *)*(unsigned __int16 *)((char *)v9 + v10);
            v12 = *v9 - (_DWORD)v11;
            if ( v12 )
              break;
            ++v9;
          }
          while ( (_DWORD)v11 );
          if ( !v12 )
            break;
        }
        if ( (unsigned __int64)++v6 >= v7 )
          goto LABEL_11;
      }
      v17 = 2;
      return (unsigned int)Microsoft::WRL::Details::GetCacheEntry(
                             v4,
                             (struct Microsoft::WRL::Details::ModuleBase *)&v17,
                             v11,
                             *v6,
                             a2,
                             v15);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x180008a70  mov     [rsp+arg_10], rbx
0x180008a75  push    rbp
0x180008a76  push    rsi
0x180008a77  push    rdi
0x180008a78  push    r14
0x180008a7a  push    r15
0x180008a7c  sub     rsp, 70h
0x180008a80  mov     rax, cs:__security_cookie
0x180008a87  xor     rax, rsp
0x180008a8a  mov     [rsp+98h+var_38], rax
0x180008a8f  mov     r14, rdx
0x180008a92  mov     rdi, rcx
0x180008a95  mov     rsi, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180008a9c  mov     qword ptr [rdx], 0
0x180008aa3  mov     [rsp+98h+hasEmbedNull], 0
0x180008aab  call    cs:__imp_WindowsIsStringEmpty
0x180008ab1  test    eax, eax
0x180008ab3  jnz     loc_180008B7F
0x180008ab9  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180008abe  mov     rcx, rdi; string
0x180008ac1  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180008ac7  test    eax, eax
0x180008ac9  js      loc_180008B7F
0x180008acf  cmp     [rsp+98h+hasEmbedNull], 1
0x180008ad4  jz      loc_180008B7F
0x180008ada  xor     edx, edx; length
0x180008adc  mov     rcx, rdi; string
0x180008adf  call    cs:__imp_WindowsGetStringRawBuffer
0x180008ae5  mov     r15, rax
0x180008ae8  mov     rcx, [rsi]
0x180008aeb  mov     rax, [rcx+28h]
0x180008aef  mov     rcx, rsi
0x180008af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008af7  lea     rbx, [rax+8]
0x180008afb  mov     rcx, [rsi]
0x180008afe  mov     rax, [rcx+30h]
0x180008b02  mov     rcx, rsi
0x180008b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b0a  mov     rbp, rax
0x180008b0d  cmp     rbx, rax
0x180008b10  jnb     short loc_180008B4C
0x180008b12  mov     rax, [rbx]
0x180008b15  test    rax, rax
0x180008b18  jz      short loc_180008B43
0x180008b1a  mov     rax, [rax+8]
0x180008b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b23  mov     rcx, r15
0x180008b26  sub     rax, r15
0x180008b29  movzx   edx, word ptr [rcx]
0x180008b2c  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x180008b31  sub     edx, r8d
0x180008b34  jnz     short loc_180008B3F
0x180008b36  add     rcx, 2
0x180008b3a  test    r8d, r8d
0x180008b3d  jnz     short loc_180008B29
0x180008b3f  test    edx, edx
0x180008b41  jz      short loc_180008B5E
0x180008b43  add     rbx, 8
0x180008b47  cmp     rbx, rbp
0x180008b4a  jb      short loc_180008B12
0x180008b4c  mov     rdx, rdi
0x180008b4f  mov     ebx, 80040111h
0x180008b54  mov     ecx, ebx
0x180008b56  call    cs:__imp_RoOriginateError
0x180008b5c  jmp     short loc_180008BBD
0x180008b5e  mov     [rsp+98h+var_64], 2
0x180008b66  mov     [rsp+98h+var_78], r14; struct Microsoft::WRL::Details::CreatorMap *
0x180008b6b  mov     r9, [rbx]; struct _GUID *
0x180008b6e  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180008b73  mov     rcx, rsi; this
0x180008b76  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180008b7b  mov     ebx, eax
0x180008b7d  jmp     short loc_180008BBD
0x180008b7f  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180008b86  movups  [rsp+98h+var_60], xmm0
0x180008b8b  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180008b92  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180008b97  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180008b9f  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x180008ba5  lea     r8, [rsp+98h+var_60]
0x180008baa  mov     edx, 12h
0x180008baf  mov     ebx, 80070057h
0x180008bb4  mov     ecx, ebx
0x180008bb6  call    cs:__imp_RoOriginateErrorW
0x180008bbc  nop
0x180008bbd  mov     eax, ebx
0x180008bbf  mov     rcx, [rsp+98h+var_38]
0x180008bc4  xor     rcx, rsp; StackCookie
0x180008bc7  call    __security_check_cookie
0x180008bcc  mov     rbx, [rsp+98h+arg_10]
0x180008bd4  add     rsp, 70h
0x180008bd8  pop     r15
0x180008bda  pop     r14
0x180008bdc  pop     rdi
0x180008bdd  pop     rsi
0x180008bde  pop     rbp
0x180008bdf  retn
```
