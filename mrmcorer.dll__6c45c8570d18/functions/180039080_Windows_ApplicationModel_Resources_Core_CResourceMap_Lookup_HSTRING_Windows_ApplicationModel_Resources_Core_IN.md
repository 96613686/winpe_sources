# Windows::ApplicationModel::Resources::Core::CResourceMap::Lookup(HSTRING__ *,Windows::ApplicationModel::Resources::Core::INamedResource * *)

- ea: `0x180039080`
- end: `0x1800392af`
- name: `?Lookup@CResourceMap@Core@Resources@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUINamedResource@2345@@Z`
- size: `559`
- prototype: `int(Windows::ApplicationModel::Resources::Core::CResourceMap *__hidden this, HSTRING, struct Windows::ApplicationModel::Resources::Core::INamedResource **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002c8d0`
- `0x18002d0c0`
- `0x180039080`
- `0x1800392b8`
- `0x18003930c`
- `0x180039d1c`
- `0x180054bc8`
- `0x1800795ac`
- `0x1800867dc`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800390f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800390f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800391d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800391d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800391bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800391bc`

## string_xrefs

- `0x18003923e`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemap.cpp`
- `0x180039265`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemap.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceMap::Lookup(
        Windows::ApplicationModel::Resources::Core::CResourceMap *this,
        HSTRING a2,
        struct Windows::ApplicationModel::Resources::Core::INamedResource **a3)
{
  Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal *v6; // rax
  Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal *v7; // r14
  PCWSTR StringRawBuffer; // rax
  int Value; // eax
  unsigned int v10; // ebx
  Windows::ApplicationModel::Resources::Core::CNamedResource *v11; // rax
  char *v12; // rdi
  _QWORD *v13; // rsi
  HRESULT v14; // edi
  HSTRING v15; // rcx
  __int64 v16; // rax
  unsigned int v17; // edx
  int v19; // [rsp+20h] [rbp-60h]
  __int64 v20; // [rsp+60h] [rbp-20h]
  Windows::ApplicationModel::Resources::Core::CNamedResource *v21; // [rsp+68h] [rbp-18h] BYREF
  HSTRING newString[2]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  *a3 = 0;
  v6 = (Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal *)operator new(
                                                                               0x88u,
                                                                               (const struct std::nothrow_t *)&std::nothrow);
  if ( v6 )
    v7 = (Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal *)Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal::CResolvedInstanceCollectionInternal(v6);
  else
    v7 = 0;
  newString[0] = (HSTRING)&Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal>::`vftable';
  newString[1] = (HSTRING)v7;
  if ( !v7 )
  {
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemap.cpp",
      (const char *)0x8007000ELL,
      v19);
    return v10;
  }
  v20 = *((_QWORD *)this + 8);
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  Value = Microsoft::Resources::Runtime::CResourceIndexInternal::_GetValue(v20, StringRawBuffer, 0, 0);
  v10 = Value;
  if ( Value < 0 )
  {
    if ( Value != -2147009769 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB5,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemap.cpp",
        (const char *)(unsigned int)Value,
        0);
    Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal>::~AutoDeletePtr<Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal>(newString);
    return v10;
  }
  *a3 = 0;
  v11 = (Windows::ApplicationModel::Resources::Core::CNamedResource *)operator new(
                                                                        0x60u,
                                                                        (const struct std::nothrow_t *)&std::nothrow);
  v21 = v11;
  if ( !v11 )
  {
    Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v21);
    v14 = -2147024882;
LABEL_18:
    Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal::`scalar deleting destructor'(v7, v17);
    return (unsigned int)v14;
  }
  v12 = (char *)this - 16;
  v13 = (_QWORD *)Windows::ApplicationModel::Resources::Core::CNamedResource::CNamedResource(v11);
  v21 = 0;
  v13[8] = v12;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 8LL))(v12);
  v13[9] = v20;
  v13[10] = v7;
  newString[0] = 0;
  v14 = WindowsDuplicateString(a2, newString);
  if ( v14 >= 0 )
  {
    v15 = (HSTRING)v13[11];
    v13[11] = newString[0];
    WindowsDeleteString(v15);
  }
  v16 = *v13;
  if ( v14 < 0 )
  {
    (*(void (__fastcall **)(_QWORD *))(v16 + 16))(v13);
    Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v21);
  }
  else
  {
    v14 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct Windows::ApplicationModel::Resources::Core::INamedResource **))v16)(
            v13,
            &GUID_1c98c219_0b13_4240_89a5_d495dc189a00,
            a3);
    (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
  }
  if ( v14 == -2147024882 )
    goto LABEL_18;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180039080  push    rbp
0x180039082  push    rbx
0x180039083  push    rsi
0x180039084  push    rdi
0x180039085  push    r12
0x180039087  push    r14
0x180039089  push    r15
0x18003908b  mov     rbp, rsp
0x18003908e  sub     rsp, 80h
0x180039095  mov     r15, r8
0x180039098  mov     r12, rdx
0x18003909b  mov     rdi, rcx
0x18003909e  mov     qword ptr [r8], 0
0x1800390a5  mov     [rbp+var_20], 0
0x1800390ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800390b4  mov     ecx, 88h; unsigned __int64
0x1800390b9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800390be  test    rax, rax
0x1800390c1  jz      loc_18003922A
0x1800390c7  mov     rcx, rax; this
0x1800390ca  call    ??0CResolvedInstanceCollectionInternal@Runtime@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal::CResolvedInstanceCollectionInternal(void)
0x1800390cf  mov     r14, rax
0x1800390d2  lea     rax, ??_7?$AutoDeletePtr@VCResolvedInstanceCollectionInternal@Runtime@Resources@Microsoft@@@Resources@Microsoft@@6B@; const Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal>::`vftable'
0x1800390d9  mov     [rbp+newString], rax
0x1800390dd  mov     [rbp+var_8], r14
0x1800390e1  test    r14, r14
0x1800390e4  jz      loc_180039232
0x1800390ea  mov     rbx, [rdi+40h]
0x1800390ee  mov     [rbp+var_20], rbx
0x1800390f2  xor     edx, edx; length
0x1800390f4  mov     rcx, r12; string
0x1800390f7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800390fd  lea     rcx, [rbp+var_20]
0x180039101  mov     [rsp+80h+var_30], rcx
0x180039106  mov     [rsp+80h+var_38], 0
0x18003910f  mov     [rsp+80h+var_40], r14
0x180039114  mov     [rsp+80h+var_48], 0
0x18003911d  mov     [rsp+80h+var_50], 0
0x180039126  mov     [rsp+80h+var_58], 0Ch
0x18003912e  mov     qword ptr [rsp+80h+var_60], 0; int
0x180039137  xor     r9d, r9d
0x18003913a  xor     r8d, r8d
0x18003913d  mov     rdx, rax
0x180039140  mov     rcx, rbx
0x180039143  call    ?_GetValue@CResourceIndexInternal@Runtime@Resources@Microsoft@@AEAAJPEBGPEAUIUri@@0PEAVCContext@234@W4RESOURCE_SEARCH_OPTIONS@234@PEAPEBGPEAVCResolvedInstanceInternal@234@PEAVCResolvedInstanceCollectionInternal@234@PEA_NPEAPEAV1234@@Z; Microsoft::Resources::Runtime::CResourceIndexInternal::_GetValue(ushort const *,IUri *,ushort const *,Microsoft::Resources::Runtime::CContext *,Microsoft::Resources::Runtime::RESOURCE_SEARCH_OPTIONS,ushort const * *,Microsoft::Resources::Runtime::CResolvedInstanceInternal *,Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal *,bool *,Microsoft::Resources::Runtime::CResourceIndexInternal * *)
0x180039148  mov     ebx, eax
0x18003914a  test    eax, eax
0x18003914c  js      loc_180039253
0x180039152  mov     qword ptr [r15], 0
0x180039159  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180039160  mov     ecx, 60h ; '`'; unsigned __int64
0x180039165  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003916a  mov     [rbp+var_18], rax
0x18003916e  test    rax, rax
0x180039171  jz      loc_18003927C
0x180039177  add     rdi, 0FFFFFFFFFFFFFFF0h
0x18003917b  mov     rcx, rax; this
0x18003917e  call    ??0CNamedResource@Core@Resources@ApplicationModel@Windows@@QEAA@XZ; Windows::ApplicationModel::Resources::Core::CNamedResource::CNamedResource(void)
0x180039183  mov     rsi, rax
0x180039186  mov     [rbp+var_18], 0
0x18003918e  mov     rbx, [rbp+var_20]
0x180039192  mov     [rax+40h], rdi
0x180039196  mov     rdx, [rdi]
0x180039199  mov     rcx, rdi
0x18003919c  mov     rax, [rdx+8]
0x1800391a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391a5  mov     [rsi+48h], rbx
0x1800391a9  mov     [rsi+50h], r14
0x1800391ad  mov     [rbp+newString], 0
0x1800391b5  lea     rdx, [rbp+newString]; newString
0x1800391b9  mov     rcx, r12; string
0x1800391bc  call    cs:__imp_WindowsDuplicateString
0x1800391c2  mov     edi, eax
0x1800391c4  test    eax, eax
0x1800391c6  js      short loc_1800391DB
0x1800391c8  mov     rcx, [rsi+58h]; string
0x1800391cc  mov     rax, [rbp+newString]
0x1800391d0  mov     [rsi+58h], rax
0x1800391d4  call    cs:__imp_WindowsDeleteString
0x1800391da  nop
0x1800391db  mov     rax, [rsi]
0x1800391de  test    edi, edi
0x1800391e0  js      loc_180039294
0x1800391e6  mov     r8, r15
0x1800391e9  lea     rdx, _GUID_1c98c219_0b13_4240_89a5_d495dc189a00
0x1800391f0  mov     rcx, rsi
0x1800391f3  mov     rax, [rax]
0x1800391f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391fb  mov     edi, eax
0x1800391fd  mov     rax, [rsi]
0x180039200  mov     rcx, rsi
0x180039203  mov     rax, [rax+10h]
0x180039207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003920c  nop
0x18003920d  mov     ebx, 8007000Eh
0x180039212  cmp     edi, ebx
0x180039214  jz      short loc_18003928A
0x180039216  mov     eax, edi
0x180039218  add     rsp, 80h
0x18003921f  pop     r15
0x180039221  pop     r14
0x180039223  pop     r12
0x180039225  pop     rdi
0x180039226  pop     rsi
0x180039227  pop     rbx
0x180039228  pop     rbp
0x180039229  retn
0x18003922a  xor     r14d, r14d
0x18003922d  jmp     loc_1800390D2
0x180039232  mov     rcx, [rbp+38h]; this
0x180039236  mov     ebx, 8007000Eh
0x18003923b  mov     r9d, ebx; char *
0x18003923e  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180039245  mov     edx, 0A8h; void *
0x18003924a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003924f  mov     edi, ebx
0x180039251  jmp     short loc_180039216
0x180039253  cmp     eax, 80073B17h
0x180039258  jz      loc_1800C2392
0x18003925e  mov     rcx, [rbp+38h]; this
0x180039262  mov     r9d, eax; char *
0x180039265  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18003926c  mov     edx, 0B5h; void *
0x180039271  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039276  nop
0x180039277  jmp     loc_1800C2392
0x18003927c  lea     rcx, [rbp+var_18]
0x180039280  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x180039285  mov     edi, 8007000Eh
0x18003928a  mov     rcx, r14; this
0x18003928d  call    ??_GCResolvedInstanceCollectionInternal@Runtime@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal::`scalar deleting destructor'(uint)
0x180039292  jmp     short loc_180039216
0x180039294  mov     rcx, rsi
0x180039297  mov     rax, [rax+10h]
0x18003929b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392a0  nop
0x1800392a1  lea     rcx, [rbp+var_18]
0x1800392a5  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x1800392aa  jmp     loc_18003920D
0x1800c2392  lea     rcx, [rbp+newString]
0x1800c2396  call    ??1?$AutoDeletePtr@VCResolvedInstanceCollectionInternal@Runtime@Resources@Microsoft@@@Resources@Microsoft@@UEAA@XZ; Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal>::~AutoDeletePtr<Microsoft::Resources::Runtime::CResolvedInstanceCollectionInternal>(void)
0x1800c239b  nop
0x1800c239c  jmp     loc_18003924F
```
