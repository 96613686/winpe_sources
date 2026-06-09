# DllGetActivationFactory

- ea: `0x180008c40`
- end: `0x180008deb`
- name: `DllGetActivationFactory`
- size: `427`
- prototype: `__int64 __fastcall(HSTRING string, PVOID Ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005bac`
- `0x180008c40`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008c7b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008c7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008cce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008cce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180008c9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180008c9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180008cb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180008cb0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180008dc0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180008dc0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008d55`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008d55`

## string_xrefs

- `0x180008d89`: `activatibleClassId`

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
  byte_180052FF8 = 1;
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
0x180008c40  mov     [rsp+arg_10], rbx
0x180008c45  mov     [rsp+arg_18], rbp
0x180008c4a  push    rsi
0x180008c4b  push    rdi
0x180008c4c  push    r14
0x180008c4e  sub     rsp, 70h
0x180008c52  mov     rax, cs:__security_cookie
0x180008c59  xor     rax, rsp
0x180008c5c  mov     [rsp+88h+var_28], rax
0x180008c61  mov     rsi, rdx
0x180008c64  mov     rdi, rcx
0x180008c67  xor     r9d, r9d; Context
0x180008c6a  xor     r8d, r8d; Parameter
0x180008c6d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180008c74  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180008c7b  call    cs:__imp_InitOnceExecuteOnce
0x180008c81  mov     cs:byte_180052FF8, 1
0x180008c88  mov     qword ptr [rsi], 0
0x180008c8f  mov     [rsp+88h+hasEmbedNull], 0
0x180008c97  mov     rcx, rdi; string
0x180008c9a  call    cs:__imp_WindowsIsStringEmpty
0x180008ca0  test    eax, eax
0x180008ca2  jnz     loc_180008D89
0x180008ca8  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x180008cad  mov     rcx, rdi; string
0x180008cb0  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180008cb6  test    eax, eax
0x180008cb8  js      loc_180008D89
0x180008cbe  cmp     [rsp+88h+hasEmbedNull], 1
0x180008cc3  jz      loc_180008D89
0x180008cc9  xor     edx, edx; length
0x180008ccb  mov     rcx, rdi; string
0x180008cce  call    cs:__imp_WindowsGetStringRawBuffer
0x180008cd4  mov     r14, rax
0x180008cd7  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008cde  mov     rax, [rcx+28h]
0x180008ce2  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cee  lea     rbx, [rax+8]
0x180008cf2  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008cf9  mov     rax, [rcx+30h]
0x180008cfd  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d09  mov     rbp, rax
0x180008d0c  cmp     rbx, rax
0x180008d0f  jnb     short loc_180008D4B
0x180008d11  mov     rax, [rbx]
0x180008d14  test    rax, rax
0x180008d17  jz      short loc_180008D42
0x180008d19  mov     rax, [rax+8]
0x180008d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d22  mov     rcx, r14
0x180008d25  sub     rax, r14
0x180008d28  movzx   edx, word ptr [rcx]
0x180008d2b  movzx   r8d, word ptr [rcx+rax]
0x180008d30  sub     edx, r8d
0x180008d33  jnz     short loc_180008D3E
0x180008d35  add     rcx, 2
0x180008d39  test    r8d, r8d
0x180008d3c  jnz     short loc_180008D28
0x180008d3e  test    edx, edx
0x180008d40  jz      short loc_180008D5D
0x180008d42  add     rbx, 8
0x180008d46  cmp     rbx, rbp
0x180008d49  jb      short loc_180008D11
0x180008d4b  mov     rdx, rdi
0x180008d4e  mov     ebx, 80040111h
0x180008d53  mov     ecx, ebx
0x180008d55  call    cs:__imp_RoOriginateError
0x180008d5b  jmp     short loc_180008DC7
0x180008d5d  mov     [rsp+88h+var_54], 1
0x180008d65  mov     [rsp+88h+Ptr], rsi; Ptr
0x180008d6a  mov     r9, [rbx]; struct _GUID *
0x180008d6d  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x180008d74  lea     rdx, [rsp+88h+var_54]; struct Microsoft::WRL::Details::ModuleBase *
0x180008d79  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180008d80  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180008d85  mov     ebx, eax
0x180008d87  jmp     short loc_180008DC7
0x180008d89  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180008d90  movups  [rsp+88h+var_50], xmm0
0x180008d95  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180008d9c  movups  xmmword ptr [rsp+88h+var_40], xmm1
0x180008da1  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180008da9  movsd   qword ptr [rsp+88h+var_40+0Eh], xmm0
0x180008daf  lea     r8, [rsp+88h+var_50]
0x180008db4  mov     edx, 12h
0x180008db9  mov     ebx, 80070057h
0x180008dbe  mov     ecx, ebx
0x180008dc0  call    cs:__imp_RoOriginateErrorW
0x180008dc6  nop
0x180008dc7  mov     eax, ebx
0x180008dc9  mov     rcx, [rsp+88h+var_28]
0x180008dce  xor     rcx, rsp; StackCookie
0x180008dd1  call    __security_check_cookie
0x180008dd6  lea     r11, [rsp+88h+var_18]
0x180008ddb  mov     rbx, [r11+30h]
0x180008ddf  mov     rbp, [r11+38h]
0x180008de3  mov     rsp, r11
0x180008de6  pop     r14
0x180008de8  pop     rdi
0x180008de9  pop     rsi
0x180008dea  retn
```
