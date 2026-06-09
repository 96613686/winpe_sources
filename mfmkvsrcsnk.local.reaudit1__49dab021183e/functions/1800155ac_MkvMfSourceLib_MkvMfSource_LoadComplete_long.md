# MkvMfSourceLib::MkvMfSource::LoadComplete(long)

- ea: `0x1800155ac`
- end: `0x180015836`
- name: `?LoadComplete@MkvMfSource@MkvMfSourceLib@@AEAA?AW4OperationState@12@J@Z`
- size: `650`
- prototype: ``
- caller_count: `8`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011720`
- `0x18001f310`
- `0x18001f620`
- `0x18001f880`
- `0x18001fa60`
- `0x18001fdc0`
- `0x180020110`
- `0x1800207c0`

## callees

- `0x180002400`
- `0x180005c68`
- `0x180009b04`
- `0x180009bec`
- `0x18000c36c`
- `0x18000d554`
- `0x18000ddc0`
- `0x18000e148`
- `0x1800155ac`
- `0x180021ae0`
- `0x18002bb28`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFInvokeCallback` at `0x1800157dd`
- `MFPlat!MFInvokeCallback` at `0x1800157dd`

## string_xrefs

- `0x1800155e8`: `MkvMfSourceLib::MkvMfSource::LoadComplete`

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
0x1800155ac  mov     [rsp+arg_10], rbx
0x1800155b1  mov     [rsp+arg_18], rdi
0x1800155b6  push    r12
0x1800155b8  push    r14
0x1800155ba  push    r15
0x1800155bc  sub     rsp, 70h
0x1800155c0  mov     rax, cs:__security_cookie
0x1800155c7  xor     rax, rsp
0x1800155ca  mov     [rsp+88h+var_28], rax
0x1800155cf  mov     r15d, edx
0x1800155d2  mov     r14, rcx
0x1800155d5  mov     [rsp+88h+var_40], rcx
0x1800155da  mov     [rsp+88h+var_64], 0
0x1800155e2  mov     r8d, 0B41h; int
0x1800155e8  lea     rdx, aMkvmfsourcelib_4; "MkvMfSourceLib::MkvMfSource::LoadComple"...
0x1800155ef  lea     rcx, [rsp+88h+var_68]; this
0x1800155f4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800155f9  nop
0x1800155fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180015601  cmp     byte ptr [rcx+8], 0
0x180015605  jz      short loc_18001565D
0x180015607  cmp     qword ptr [r14+2B0h], 0
0x18001560f  jz      short loc_18001565D
0x180015611  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015616  mov     rdi, rax
0x180015619  mov     rcx, [r14+2B0h]
0x180015620  mov     rdx, [rcx]
0x180015623  mov     rax, [rdx+128h]
0x18001562a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001562f  mov     ebx, eax
0x180015631  mov     rcx, [r14+2B0h]
0x180015638  mov     rdx, [rcx]
0x18001563b  mov     rax, [rdx+118h]
0x180015642  lea     rdx, [rsp+88h+var_38]
0x180015647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001564c  movups  xmm0, xmmword ptr [rax]
0x18001564f  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180015657  mov     [rdi+7E0h], ebx
0x18001565d  mov     [rsp+88h+var_38], r14
0x180015662  lea     rax, [rsp+88h+var_64]
0x180015667  mov     [rsp+88h+var_30], rax
0x18001566c  lea     rdi, [r14+240h]
0x180015673  mov     rax, [rdi]
0x180015676  mov     rax, [rax]
0x180015679  mov     [rsp+88h+var_48], rax
0x18001567e  cmp     rax, [rdi]
0x180015681  jnz     short loc_1800156E8
0x180015683  test    r15d, r15d
0x180015686  js      loc_1800157B4
0x18001568c  mov     rax, [r14+1A0h]
0x180015693  mov     rcx, [rax+98h]
0x18001569a  mov     [rsp+88h+var_48], rcx
0x18001569f  mov     [rsp+88h+var_50], rdi
0x1800156a4  lea     rbx, [r14+2C0h]
0x1800156ab  mov     rcx, rbx
0x1800156ae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800156b3  lea     r8, [rsp+88h+var_48]
0x1800156b8  lea     rdx, [rsp+88h+var_50]
0x1800156bd  mov     rcx, rbx
0x1800156c0  call    ??$MakeAndInitialize@VMkvMetadataHandler@MkvMfSourceLib@@V12@PEAV?$map@KV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@5@@std@@PEBVTags@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAVMkvMetadataHandler@MkvMfSourceLib@@$$QEAPEAV?$map@KV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@5@@std@@$$QEAPEBVTags@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMetadataHandler,MkvMfSourceLib::MkvMetadataHandler,std::map<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>> *,mkvparser::Tags const *>(MkvMfSourceLib::MkvMetadataHandler * *,std::map<ulong,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>> * &&,mkvparser::Tags const * &&)
0x1800156c5  test    eax, eax
0x1800156c7  js      short loc_1800156D1
0x1800156c9  mov     rcx, [rbx]; this
0x1800156cc  call    ?PopulateMetadataTags@MkvMetadataHandler@MkvMfSourceLib@@QEAAJXZ; MkvMfSourceLib::MkvMetadataHandler::PopulateMetadataTags(void)
0x1800156d1  cmp     byte ptr [r14+20Ch], 0
0x1800156d9  jz      loc_1800157B4
0x1800156df  mov     [rsp+88h+var_64], eax
0x1800156e3  jmp     loc_1800157B4
0x1800156e8  mov     [rsp+88h+var_58], 0
0x1800156f1  mov     rbx, [rax+28h]
0x1800156f5  mov     [rsp+88h+var_50], rbx
0x1800156fa  lea     rcx, [rsp+88h+var_50]
0x1800156ff  call    ?InternalAddRef@?$ComPtr@VMkvMfStreamSubtitle@MkvMfSourceLib@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(void)
0x180015704  nop
0x180015705  mov     rax, [rbx]
0x180015708  lea     rdx, [rsp+88h+var_58]
0x18001570d  mov     rcx, rbx
0x180015710  mov     rax, [rax+40h]
0x180015714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015719  test    eax, eax
0x18001571b  js      short loc_180015756
0x18001571d  mov     rcx, [rsp+88h+var_58]
0x180015722  mov     [rsp+88h+var_60], rcx
0x180015727  test    rcx, rcx
0x18001572a  jz      short loc_180015739
0x18001572c  mov     rax, [rcx]
0x18001572f  mov     rax, [rax+8]
0x180015733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015738  nop
0x180015739  lea     rdx, [rsp+88h+var_60]
0x18001573e  lea     rcx, [r14+0A0h]
0x180015745  call    ?push_back@?$vector@V?$ComPtr@UIMFStreamDescriptor@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMFStreamDescriptor@@@WRL@Microsoft@@@std@@@std@@QEAAX$$QEAV?$ComPtr@UIMFStreamDescriptor@@@WRL@Microsoft@@@Z; std::vector<Microsoft::WRL::ComPtr<IMFStreamDescriptor>>::push_back(Microsoft::WRL::ComPtr<IMFStreamDescriptor> &&)
0x18001574a  nop
0x18001574b  lea     rcx, [rsp+88h+var_60]
0x180015750  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015755  nop
0x180015756  test    rbx, rbx
0x180015759  jz      short loc_18001576B
0x18001575b  mov     rax, [rbx]
0x18001575e  mov     rcx, rbx
0x180015761  mov     rax, [rax+10h]
0x180015765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001576a  nop
0x18001576b  lea     rcx, [rsp+88h+var_58]
0x180015770  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015775  lea     rcx, [rsp+88h+var_48]
0x18001577a  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$ComPtr@VMkvMfStream@MkvMfSourceLib@@@WRL@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(void)
0x18001577f  mov     rax, [rsp+88h+var_48]
0x180015784  jmp     loc_18001567E
0x180015789  mov     rcx, [rsp+88h+var_50]
0x18001578e  test    rcx, rcx
0x180015791  jz      short loc_1800157A0
0x180015793  mov     rax, [rcx]
0x180015796  mov     rax, [rax+10h]
0x18001579a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001579f  nop
0x1800157a0  lea     rcx, [rsp+88h+var_58]
0x1800157a5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800157aa  mov     r14, [rsp+88h+var_40]
0x1800157af  mov     r15d, dword ptr [rsp+88h+var_60]
0x1800157b4  lea     rbx, [r14+98h]
0x1800157bb  mov     rcx, [rbx]
0x1800157be  test    rcx, rcx
0x1800157c1  jz      short loc_1800157F5
0x1800157c3  mov     rax, [rcx]
0x1800157c6  mov     edx, r15d
0x1800157c9  mov     rax, [rax+28h]
0x1800157cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157d2  mov     [rsp+88h+var_64], eax
0x1800157d6  test    eax, eax
0x1800157d8  js      short loc_1800157ED
0x1800157da  mov     rcx, [rbx]; pAsyncResult
0x1800157dd  call    cs:__imp_MFInvokeCallback
0x1800157e4  nop     dword ptr [rax+rax+00h]
0x1800157e9  mov     [rsp+88h+var_64], eax
0x1800157ed  mov     rcx, rbx
0x1800157f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800157f5  test    r15d, r15d
0x1800157f8  setns   al
0x1800157fb  mov     [r14+1C9h], al
0x180015802  lea     rcx, [rsp+88h+var_68]; this
0x180015807  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001580c  mov     eax, 3
0x180015811  mov     rcx, [rsp+88h+var_28]
0x180015816  xor     rcx, rsp; StackCookie
0x180015819  call    __security_check_cookie
0x18001581e  lea     r11, [rsp+88h+var_18]
0x180015823  mov     rbx, [r11+30h]
0x180015827  mov     rdi, [r11+38h]
0x18001582b  mov     rsp, r11
0x18001582e  pop     r15
0x180015830  pop     r14
0x180015832  pop     r12
0x180015834  retn
```
