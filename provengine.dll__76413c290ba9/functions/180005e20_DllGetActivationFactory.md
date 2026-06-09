# DllGetActivationFactory

- ea: `0x180005e20`
- end: `0x180005fcb`
- name: `DllGetActivationFactory`
- size: `427`
- prototype: `__int64 __fastcall(HSTRING string, PVOID Ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800042c4`
- `0x180005e20`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180005e5b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180005e5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005eae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005eae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180005e90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180005e90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180005e7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180005e7a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005f35`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005f35`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180005fa0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180005fa0`

## string_xrefs

- `0x180005f69`: `activatibleClassId`

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
  byte_18005AD88 = 1;
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
0x180005e20  mov     [rsp+arg_10], rbx
0x180005e25  mov     [rsp+arg_18], rbp
0x180005e2a  push    rsi
0x180005e2b  push    rdi
0x180005e2c  push    r14
0x180005e2e  sub     rsp, 70h
0x180005e32  mov     rax, cs:__security_cookie
0x180005e39  xor     rax, rsp
0x180005e3c  mov     [rsp+88h+var_28], rax
0x180005e41  mov     rsi, rdx
0x180005e44  mov     rdi, rcx
0x180005e47  xor     r9d, r9d; Context
0x180005e4a  xor     r8d, r8d; Parameter
0x180005e4d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180005e54  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180005e5b  call    cs:__imp_InitOnceExecuteOnce
0x180005e61  mov     cs:byte_18005AD88, 1
0x180005e68  mov     qword ptr [rsi], 0
0x180005e6f  mov     [rsp+88h+hasEmbedNull], 0
0x180005e77  mov     rcx, rdi; string
0x180005e7a  call    cs:__imp_WindowsIsStringEmpty
0x180005e80  test    eax, eax
0x180005e82  jnz     loc_180005F69
0x180005e88  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x180005e8d  mov     rcx, rdi; string
0x180005e90  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180005e96  test    eax, eax
0x180005e98  js      loc_180005F69
0x180005e9e  cmp     [rsp+88h+hasEmbedNull], 1
0x180005ea3  jz      loc_180005F69
0x180005ea9  xor     edx, edx; length
0x180005eab  mov     rcx, rdi; string
0x180005eae  call    cs:__imp_WindowsGetStringRawBuffer
0x180005eb4  mov     r14, rax
0x180005eb7  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180005ebe  mov     rax, [rcx+28h]
0x180005ec2  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180005ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ece  lea     rbx, [rax+8]
0x180005ed2  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180005ed9  mov     rax, [rcx+30h]
0x180005edd  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180005ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ee9  mov     rbp, rax
0x180005eec  cmp     rbx, rax
0x180005eef  jnb     short loc_180005F2B
0x180005ef1  mov     rax, [rbx]
0x180005ef4  test    rax, rax
0x180005ef7  jz      short loc_180005F22
0x180005ef9  mov     rax, [rax+8]
0x180005efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f02  mov     rcx, r14
0x180005f05  sub     rax, r14
0x180005f08  movzx   edx, word ptr [rcx]
0x180005f0b  movzx   r8d, word ptr [rcx+rax]
0x180005f10  sub     edx, r8d
0x180005f13  jnz     short loc_180005F1E
0x180005f15  add     rcx, 2
0x180005f19  test    r8d, r8d
0x180005f1c  jnz     short loc_180005F08
0x180005f1e  test    edx, edx
0x180005f20  jz      short loc_180005F3D
0x180005f22  add     rbx, 8
0x180005f26  cmp     rbx, rbp
0x180005f29  jb      short loc_180005EF1
0x180005f2b  mov     rdx, rdi
0x180005f2e  mov     ebx, 80040111h
0x180005f33  mov     ecx, ebx
0x180005f35  call    cs:__imp_RoOriginateError
0x180005f3b  jmp     short loc_180005FA7
0x180005f3d  mov     [rsp+88h+var_54], 1
0x180005f45  mov     [rsp+88h+Ptr], rsi; Ptr
0x180005f4a  mov     r9, [rbx]; struct _GUID *
0x180005f4d  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x180005f54  lea     rdx, [rsp+88h+var_54]; struct Microsoft::WRL::Details::ModuleBase *
0x180005f59  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180005f60  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180005f65  mov     ebx, eax
0x180005f67  jmp     short loc_180005FA7
0x180005f69  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180005f70  movups  [rsp+88h+var_50], xmm0
0x180005f75  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180005f7c  movups  xmmword ptr [rsp+88h+var_40], xmm1
0x180005f81  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180005f89  movsd   qword ptr [rsp+88h+var_40+0Eh], xmm0
0x180005f8f  lea     r8, [rsp+88h+var_50]
0x180005f94  mov     edx, 12h
0x180005f99  mov     ebx, 80070057h
0x180005f9e  mov     ecx, ebx
0x180005fa0  call    cs:__imp_RoOriginateErrorW
0x180005fa6  nop
0x180005fa7  mov     eax, ebx
0x180005fa9  mov     rcx, [rsp+88h+var_28]
0x180005fae  xor     rcx, rsp; StackCookie
0x180005fb1  call    __security_check_cookie
0x180005fb6  lea     r11, [rsp+88h+var_18]
0x180005fbb  mov     rbx, [r11+30h]
0x180005fbf  mov     rbp, [r11+38h]
0x180005fc3  mov     rsp, r11
0x180005fc6  pop     r14
0x180005fc8  pop     rdi
0x180005fc9  pop     rsi
0x180005fca  retn
```
