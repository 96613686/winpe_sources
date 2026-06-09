# MkvMfSourceLib::MkvMfSource::LoadComplete(long)

- ea: `0x180014bd0`
- end: `0x180014e53`
- name: `?LoadComplete@MkvMfSource@MkvMfSourceLib@@AEAA?AW4OperationState@12@J@Z`
- size: `643`
- prototype: ``
- caller_count: `8`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010fd0`
- `0x18001e500`
- `0x18001e810`
- `0x18001ea70`
- `0x18001ec50`
- `0x18001efb0`
- `0x18001f300`
- `0x18001f9b0`

## callees

- `0x1800023e0`
- `0x180005ab8`
- `0x1800097f0`
- `0x1800098b8`
- `0x18000be8c`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x18000db40`
- `0x180014bd0`
- `0x180020ccc`
- `0x18002a864`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFInvokeCallback` at `0x180014e01`
- `MFPlat!MFInvokeCallback` at `0x180014e01`

## string_xrefs

- `0x180014c0c`: `MkvMfSourceLib::MkvMfSource::LoadComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall MkvMfSourceLib::MkvMfSource::LoadComplete(__int64 a1, int a2)
{
  __int64 v3; // r14
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 result; // rax
  _BYTE v11[4]; // [rsp+20h] [rbp-68h] BYREF
  HRESULT v12; // [rsp+24h] [rbp-64h] BYREF
  __int64 v13; // [rsp+28h] [rbp-60h] BYREF
  __int64 v14; // [rsp+30h] [rbp-58h] BYREF
  __int64 v15; // [rsp+38h] [rbp-50h] BYREF
  __int64 v16; // [rsp+40h] [rbp-48h] BYREF
  __int64 v17; // [rsp+48h] [rbp-40h]
  _QWORD v18[2]; // [rsp+50h] [rbp-38h] BYREF

  v3 = a1;
  v17 = a1;
  v12 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v11,
    "MkvMfSourceLib::MkvMfSource::LoadComplete",
    2881);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *(_QWORD *)(v3 + 688) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v3 + 688) + 296LL))(*(_QWORD *)(v3 + 688));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)(v3 + 688) + 280LL))(
                                                            *(_QWORD *)(v3 + 688),
                                                            v18);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
  }
  v18[0] = v3;
  v18[1] = &v12;
  v6 = **(_QWORD **)(v3 + 576);
  v16 = v6;
  while ( v6 != *(_QWORD *)(v3 + 576) )
  {
    v14 = 0;
    v15 = *(_QWORD *)(v6 + 40);
    v8 = v15;
    Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(&v15);
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 64LL))(v8, &v14) >= 0 )
    {
      try
      {
        v13 = v14;
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
        std::vector<Microsoft::WRL::ComPtr<IMFStreamDescriptor>>::push_back(v3 + 160, &v13);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      }
      catch ( ... )
      {
        LODWORD(v13) = -2147024882;
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
        v3 = v17;
        a2 = v13;
LABEL_22:
        v9 = *(_QWORD *)(v3 + 152);
        if ( v9 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 40LL))(v9, (unsigned int)a2);
          if ( v12 >= 0 )
            v12 = MFInvokeCallback(*(IMFAsyncResult **)(v3 + 152));
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v3 + 152);
        }
        *(_BYTE *)(v3 + 457) = a2 >= 0;
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v11);
        result = 3;
      }
    }
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(&v16);
    v6 = v16;
  }
  if ( a2 >= 0 )
  {
    v16 = *(_QWORD *)(*(_QWORD *)(v3 + 416) + 152LL);
    v15 = v3 + 576;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v3 + 704);
    v7 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMetadataHandler,MkvMfSourceLib::MkvMetadataHandler,std::map<unsigned long,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>> *,mkvparser::Tags const *>(
           v3 + 704,
           &v15,
           &v16);
    if ( v7 >= 0 )
      v7 = MkvMfSourceLib::MkvMetadataHandler::PopulateMetadataTags(*(MkvMfSourceLib::MkvMetadataHandler **)(v3 + 704));
    if ( *(_BYTE *)(v3 + 524) )
      v12 = v7;
  }
  goto LABEL_22;
}

```

## disassembly

```asm
0x180014bd0  mov     [rsp+arg_10], rbx
0x180014bd5  mov     [rsp+arg_18], rdi
0x180014bda  push    r12
0x180014bdc  push    r14
0x180014bde  push    r15
0x180014be0  sub     rsp, 70h
0x180014be4  mov     rax, cs:__security_cookie
0x180014beb  xor     rax, rsp
0x180014bee  mov     [rsp+88h+var_28], rax
0x180014bf3  mov     r15d, edx
0x180014bf6  mov     r14, rcx
0x180014bf9  mov     [rsp+88h+var_40], rcx
0x180014bfe  mov     [rsp+88h+var_64], 0
0x180014c06  mov     r8d, 0B41h; int
0x180014c0c  lea     rdx, aMkvmfsourcelib_4; "MkvMfSourceLib::MkvMfSource::LoadComple"...
0x180014c13  lea     rcx, [rsp+88h+var_68]; this
0x180014c18  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180014c1d  nop
0x180014c1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180014c25  cmp     byte ptr [rcx+8], 0
0x180014c29  jz      short loc_180014C81
0x180014c2b  cmp     qword ptr [r14+2B0h], 0
0x180014c33  jz      short loc_180014C81
0x180014c35  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180014c3a  mov     rdi, rax
0x180014c3d  mov     rcx, [r14+2B0h]
0x180014c44  mov     rdx, [rcx]
0x180014c47  mov     rax, [rdx+128h]
0x180014c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c53  mov     ebx, eax
0x180014c55  mov     rcx, [r14+2B0h]
0x180014c5c  mov     rdx, [rcx]
0x180014c5f  mov     rax, [rdx+118h]
0x180014c66  lea     rdx, [rsp+88h+var_38]
0x180014c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c70  movups  xmm0, xmmword ptr [rax]
0x180014c73  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180014c7b  mov     [rdi+7E0h], ebx
0x180014c81  mov     [rsp+88h+var_38], r14
0x180014c86  lea     rax, [rsp+88h+var_64]
0x180014c8b  mov     [rsp+88h+var_30], rax
0x180014c90  lea     rdi, [r14+240h]
0x180014c97  mov     rax, [rdi]
0x180014c9a  mov     rax, [rax]
0x180014c9d  mov     [rsp+88h+var_48], rax
0x180014ca2  cmp     rax, [rdi]
0x180014ca5  jnz     short loc_180014D0C
0x180014ca7  test    r15d, r15d
0x180014caa  js      loc_180014DD8
0x180014cb0  mov     rax, [r14+1A0h]
0x180014cb7  mov     rcx, [rax+98h]
0x180014cbe  mov     [rsp+88h+var_48], rcx
0x180014cc3  mov     [rsp+88h+var_50], rdi
0x180014cc8  lea     rbx, [r14+2C0h]
0x180014ccf  mov     rcx, rbx
0x180014cd2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014cd7  lea     r8, [rsp+88h+var_48]
0x180014cdc  lea     rdx, [rsp+88h+var_50]
0x180014ce1  mov     rcx, rbx
0x180014ce4  call    ??$MakeAndInitialize@VMkvMetadataHandler@MkvMfSourceLib@@V12@PEAV?$map@KV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@5@@std@@PEBVTags@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAVMkvMetadataHandler@MkvMfSourceLib@@$$QEAPEAV?$map@KV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@5@@std@@$$QEAPEBVTags@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMetadataHandler,MkvMfSourceLib::MkvMetadataHandler,std::map<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>> *,mkvparser::Tags const *>(MkvMfSourceLib::MkvMetadataHandler * *,std::map<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>> * &&,mkvparser::Tags const * &&)
0x180014ce9  test    eax, eax
0x180014ceb  js      short loc_180014CF5
0x180014ced  mov     rcx, [rbx]; this
0x180014cf0  call    ?PopulateMetadataTags@MkvMetadataHandler@MkvMfSourceLib@@QEAAJXZ; MkvMfSourceLib::MkvMetadataHandler::PopulateMetadataTags(void)
0x180014cf5  cmp     byte ptr [r14+20Ch], 0
0x180014cfd  jz      loc_180014DD8
0x180014d03  mov     [rsp+88h+var_64], eax
0x180014d07  jmp     loc_180014DD8
0x180014d0c  mov     [rsp+88h+var_58], 0
0x180014d15  mov     rbx, [rax+28h]
0x180014d19  mov     [rsp+88h+var_50], rbx
0x180014d1e  lea     rcx, [rsp+88h+var_50]
0x180014d23  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x180014d28  nop
0x180014d29  mov     rax, [rbx]
0x180014d2c  lea     rdx, [rsp+88h+var_58]
0x180014d31  mov     rcx, rbx
0x180014d34  mov     rax, [rax+40h]
0x180014d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d3d  test    eax, eax
0x180014d3f  js      short loc_180014D7A
0x180014d41  mov     rcx, [rsp+88h+var_58]
0x180014d46  mov     [rsp+88h+var_60], rcx
0x180014d4b  test    rcx, rcx
0x180014d4e  jz      short loc_180014D5D
0x180014d50  mov     rax, [rcx]
0x180014d53  mov     rax, [rax+8]
0x180014d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d5c  nop
0x180014d5d  lea     rdx, [rsp+88h+var_60]
0x180014d62  lea     rcx, [r14+0A0h]
0x180014d69  call    ?push_back@?$vector@V?$ComPtr@UIMFStreamDescriptor@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMFStreamDescriptor@@@WRL@Microsoft@@@std@@@std@@QEAAX$$QEAV?$ComPtr@UIMFStreamDescriptor@@@WRL@Microsoft@@@Z; std::vector<Microsoft::WRL::ComPtr<IMFStreamDescriptor>>::push_back(Microsoft::WRL::ComPtr<IMFStreamDescriptor> &&)
0x180014d6e  nop
0x180014d6f  lea     rcx, [rsp+88h+var_60]
0x180014d74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014d79  nop
0x180014d7a  test    rbx, rbx
0x180014d7d  jz      short loc_180014D8F
0x180014d7f  mov     rax, [rbx]
0x180014d82  mov     rcx, rbx
0x180014d85  mov     rax, [rax+10h]
0x180014d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d8e  nop
0x180014d8f  lea     rcx, [rsp+88h+var_58]
0x180014d94  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014d99  lea     rcx, [rsp+88h+var_48]
0x180014d9e  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(void)
0x180014da3  mov     rax, [rsp+88h+var_48]
0x180014da8  jmp     loc_180014CA2
0x180014dad  mov     rcx, [rsp+88h+var_50]
0x180014db2  test    rcx, rcx
0x180014db5  jz      short loc_180014DC4
0x180014db7  mov     rax, [rcx]
0x180014dba  mov     rax, [rax+10h]
0x180014dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dc3  nop
0x180014dc4  lea     rcx, [rsp+88h+var_58]
0x180014dc9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014dce  mov     r14, [rsp+88h+var_40]
0x180014dd3  mov     r15d, dword ptr [rsp+88h+var_60]
0x180014dd8  lea     rbx, [r14+98h]
0x180014ddf  mov     rcx, [rbx]
0x180014de2  test    rcx, rcx
0x180014de5  jz      short loc_180014E13
0x180014de7  mov     rax, [rcx]
0x180014dea  mov     edx, r15d
0x180014ded  mov     rax, [rax+28h]
0x180014df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014df6  mov     [rsp+88h+var_64], eax
0x180014dfa  test    eax, eax
0x180014dfc  js      short loc_180014E0B
0x180014dfe  mov     rcx, [rbx]; pAsyncResult
0x180014e01  call    cs:__imp_MFInvokeCallback
0x180014e07  mov     [rsp+88h+var_64], eax
0x180014e0b  mov     rcx, rbx
0x180014e0e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014e13  test    r15d, r15d
0x180014e16  setns   al
0x180014e19  mov     [r14+1C9h], al
0x180014e20  lea     rcx, [rsp+88h+var_68]; this
0x180014e25  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180014e2a  mov     eax, 3
0x180014e2f  mov     rcx, [rsp+88h+var_28]
0x180014e34  xor     rcx, rsp; StackCookie
0x180014e37  call    __security_check_cookie
0x180014e3c  lea     r11, [rsp+88h+var_18]
0x180014e41  mov     rbx, [r11+30h]
0x180014e45  mov     rdi, [r11+38h]
0x180014e49  mov     rsp, r11
0x180014e4c  pop     r15
0x180014e4e  pop     r14
0x180014e50  pop     r12
0x180014e52  retn
```
