# DllGetActivationFactory

- ea: `0x180008af0`
- end: `0x180008c9b`
- name: `DllGetActivationFactory`
- size: `427`
- prototype: `__int64 __fastcall(HSTRING string, PVOID Ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005c84`
- `0x180008af0`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008b2b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008b2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180008b60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180008b60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180008b4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180008b4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008b7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008b7e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008c05`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008c05`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180008c70`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180008c70`

## string_xrefs

- `0x180008c39`: `activatibleClassId`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DllGetActivationFactory(HSTRING string, _QWORD *Ptr)
{
  PCWSTR StringRawBuffer; // r14
  const struct _GUID **v5; // rbx
  unsigned __int64 v6; // rbp
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // r8d
  int v11; // edx
  unsigned int v12; // ebx
  BOOL hasEmbedNull; // [rsp+30h] [rbp-58h] BYREF
  int v15; // [rsp+34h] [rbp-54h] BYREF
  __int128 v16; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v17[22]; // [rsp+48h] [rbp-40h]

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_18004AEA8 = 1;
  *Ptr = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v16 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v17 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v17[14] = *(_QWORD *)L"sId";
    v12 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v16);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v5 = (const struct _GUID **)((*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                   + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                               + 8);
    v6 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                           + 48LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
    if ( (unsigned __int64)v5 >= v6 )
    {
LABEL_11:
      v12 = -2147221231;
      RoOriginateError(2147746065LL, string);
    }
    else
    {
      while ( 1 )
      {
        if ( *v5 )
        {
          v7 = (*(__int64 (**)(void))(*v5)->Data4)();
          v8 = (unsigned __int16 *)StringRawBuffer;
          v9 = v7 - (_QWORD)StringRawBuffer;
          do
          {
            v10 = *(unsigned __int16 *)((char *)v8 + v9);
            v11 = *v8 - v10;
            if ( v11 )
              break;
            ++v8;
          }
          while ( v10 );
          if ( !v11 )
            break;
        }
        if ( (unsigned __int64)++v5 >= v6 )
          goto LABEL_11;
      }
      v15 = 1;
      return (unsigned int)Microsoft::WRL::Details::GetCacheEntry(
                             (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
                             (struct Microsoft::WRL::Details::ModuleBase *)&v15,
                             &GUID_00000035_0000_0000_c000_000000000046.Data1,
                             *v5,
                             Ptr);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180008af0  mov     [rsp+arg_10], rbx
0x180008af5  mov     [rsp+arg_18], rbp
0x180008afa  push    rsi
0x180008afb  push    rdi
0x180008afc  push    r14
0x180008afe  sub     rsp, 70h
0x180008b02  mov     rax, cs:__security_cookie
0x180008b09  xor     rax, rsp
0x180008b0c  mov     [rsp+88h+var_28], rax
0x180008b11  mov     rsi, rdx
0x180008b14  mov     rdi, rcx
0x180008b17  xor     r9d, r9d; Context
0x180008b1a  xor     r8d, r8d; Parameter
0x180008b1d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180008b24  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180008b2b  call    cs:__imp_InitOnceExecuteOnce
0x180008b31  mov     cs:byte_18004AEA8, 1
0x180008b38  mov     qword ptr [rsi], 0
0x180008b3f  mov     [rsp+88h+hasEmbedNull], 0
0x180008b47  mov     rcx, rdi; string
0x180008b4a  call    cs:__imp_WindowsIsStringEmpty
0x180008b50  test    eax, eax
0x180008b52  jnz     loc_180008C39
0x180008b58  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x180008b5d  mov     rcx, rdi; string
0x180008b60  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180008b66  test    eax, eax
0x180008b68  js      loc_180008C39
0x180008b6e  cmp     [rsp+88h+hasEmbedNull], 1
0x180008b73  jz      loc_180008C39
0x180008b79  xor     edx, edx; length
0x180008b7b  mov     rcx, rdi; string
0x180008b7e  call    cs:__imp_WindowsGetStringRawBuffer
0x180008b84  mov     r14, rax
0x180008b87  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008b8e  mov     rax, [rcx+28h]
0x180008b92  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b9e  lea     rbx, [rax+8]
0x180008ba2  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008ba9  mov     rax, [rcx+30h]
0x180008bad  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bb9  mov     rbp, rax
0x180008bbc  cmp     rbx, rax
0x180008bbf  jnb     short loc_180008BFB
0x180008bc1  mov     rax, [rbx]
0x180008bc4  test    rax, rax
0x180008bc7  jz      short loc_180008BF2
0x180008bc9  mov     rax, [rax+8]
0x180008bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bd2  mov     rcx, r14
0x180008bd5  sub     rax, r14
0x180008bd8  movzx   edx, word ptr [rcx]
0x180008bdb  movzx   r8d, word ptr [rcx+rax]
0x180008be0  sub     edx, r8d
0x180008be3  jnz     short loc_180008BEE
0x180008be5  add     rcx, 2
0x180008be9  test    r8d, r8d
0x180008bec  jnz     short loc_180008BD8
0x180008bee  test    edx, edx
0x180008bf0  jz      short loc_180008C0D
0x180008bf2  add     rbx, 8
0x180008bf6  cmp     rbx, rbp
0x180008bf9  jb      short loc_180008BC1
0x180008bfb  mov     rdx, rdi
0x180008bfe  mov     ebx, 80040111h
0x180008c03  mov     ecx, ebx
0x180008c05  call    cs:__imp_RoOriginateError
0x180008c0b  jmp     short loc_180008C77
0x180008c0d  mov     [rsp+88h+var_54], 1
0x180008c15  mov     [rsp+88h+Ptr], rsi; Ptr
0x180008c1a  mov     r9, [rbx]; struct _GUID *
0x180008c1d  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x180008c24  lea     rdx, [rsp+88h+var_54]; struct Microsoft::WRL::Details::ModuleBase *
0x180008c29  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180008c30  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180008c35  mov     ebx, eax
0x180008c37  jmp     short loc_180008C77
0x180008c39  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180008c40  movups  [rsp+88h+var_50], xmm0
0x180008c45  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180008c4c  movups  xmmword ptr [rsp+88h+var_40], xmm1
0x180008c51  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180008c59  movsd   qword ptr [rsp+88h+var_40+0Eh], xmm0
0x180008c5f  lea     r8, [rsp+88h+var_50]
0x180008c64  mov     edx, 12h
0x180008c69  mov     ebx, 80070057h
0x180008c6e  mov     ecx, ebx
0x180008c70  call    cs:__imp_RoOriginateErrorW
0x180008c76  nop
0x180008c77  mov     eax, ebx
0x180008c79  mov     rcx, [rsp+88h+var_28]
0x180008c7e  xor     rcx, rsp; StackCookie
0x180008c81  call    __security_check_cookie
0x180008c86  lea     r11, [rsp+88h+var_18]
0x180008c8b  mov     rbx, [r11+30h]
0x180008c8f  mov     rbp, [r11+38h]
0x180008c93  mov     rsp, r11
0x180008c96  pop     r14
0x180008c98  pop     rdi
0x180008c99  pop     rsi
0x180008c9a  retn
```
