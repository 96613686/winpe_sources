# EapLm::Peer::ThirdPartyDispatcherRuntime::GetIdentity(_EAP_METHOD_TYPE *,ulong,__int64,ulong,uchar const *,ulong,uchar const *,int *,ulong *,uchar * *,wchar_t * *,_EAP_ERROR * *)

- ea: `0x180007980`
- end: `0x180007c97`
- name: `?GetIdentity@ThirdPartyDispatcherRuntime@Peer@EapLm@@UEAAJPEAU_EAP_METHOD_TYPE@@K_JKPEBEK2PEAHPEAKPEAPEAEPEAPEA_WPEAPEAU_EAP_ERROR@@@Z`
- size: `791`
- prototype: `__int64 __fastcall(EapLm::BaseEapLibraryManager **this, struct _EAP_METHOD_TYPE *, unsigned int, __int64, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, int *, unsigned int *, unsigned __int8 **, wchar_t **, struct _EAP_ERROR **)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x18000439c`
- `0x18000503c`
- `0x180005894`
- `0x180007980`
- `0x1800122d8`
- `0x180012620`
- `0x180012a00`
- `0x180012c10`
- `0x180022234`
- `0x18002f4c8`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007b80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007b80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c68`

## string_xrefs

- `0x180007b8e`: `ComCopy`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EapLm::Peer::ThirdPartyDispatcherRuntime::GetIdentity(
        EapLm::BaseEapLibraryManager **this,
        struct _EAP_METHOD_TYPE *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        const unsigned __int8 *a6,
        unsigned int a7,
        const unsigned __int8 *a8,
        int *a9,
        unsigned int *a10,
        unsigned __int8 **a11,
        wchar_t **a12,
        struct _EAP_ERROR **a13)
{
  unsigned int v14; // edi
  int *v15; // rsi
  unsigned __int8 **v16; // r13
  unsigned int *v17; // r12
  ReferenceCounted *v18; // r14
  __int64 v19; // r15
  __int64 v20; // r9
  __int64 *v21; // r14
  __int64 v22; // rax
  SIZE_T v23; // r15
  wchar_t *v24; // rax
  wchar_t *v25; // rsi
  int *v26; // r9
  unsigned __int8 **v27; // rsi
  wchar_t **v28; // rsi
  struct _EAP_ERROR *v30; // [rsp+50h] [rbp-B8h] BYREF
  void *Src; // [rsp+58h] [rbp-B0h] BYREF
  void **v32; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+68h] [rbp-A0h]
  void *v34; // [rsp+70h] [rbp-98h] BYREF
  size_t Size; // [rsp+78h] [rbp-90h]
  ReferenceCounted *v36; // [rsp+80h] [rbp-88h]
  void *v37; // [rsp+88h] [rbp-80h] BYREF
  BYTE type; // [rsp+90h] [rbp-78h]
  __int64 v39; // [rsp+94h] [rbp-74h]
  DWORD dwAuthorId; // [rsp+A0h] [rbp-68h]
  void (__fastcall *v41)(ReferenceCounted *, _QWORD, void ***, __int64, __int64, void **, void **, char *); // [rsp+A8h] [rbp-60h]
  const ATL::CAtlException *v42; // [rsp+B0h] [rbp-58h] BYREF
  const EapHost::EapException *v43; // [rsp+B8h] [rbp-50h] BYREF
  const Exception *v44; // [rsp+C0h] [rbp-48h] BYREF
  void *v45; // [rsp+C8h] [rbp-40h] BYREF
  char v46; // [rsp+118h] [rbp+10h] BYREF
  unsigned int v47; // [rsp+120h] [rbp+18h]

  v47 = a3;
  v14 = 0;
  LODWORD(v30) = 0;
  if ( !a2 )
    return 2147500035LL;
  v15 = a9;
  if ( !a9 )
    return 2147500035LL;
  if ( !a13 )
    return 2147500035LL;
  v16 = a11;
  if ( !a11 )
    return 2147500035LL;
  v17 = a10;
  if ( !a10 || !a12 )
    return 2147500035LL;
  *a11 = 0;
  *v17 = 0;
  type = a2->eapType.type;
  v39 = *(_QWORD *)&a2->eapType.dwVendorId;
  if ( type != 0xFE )
    v39 = 0;
  try
  {
    v37 = &EapHost::EapMethodType::`vftable';
    dwAuthorId = a2->dwAuthorId;
    EapLm::Peer::EapLibraryManagerRuntime::GetEapMethodRuntime(*(this - 13));
    v46 = 0;
    Src = 0;
    v34 = 0;
    Size = 0;
    v32 = &ObjectHandle::`vftable';
    v33 = 0;
    ObjectHandle::Clear((ObjectHandle *)&v32);
    v33 = a4;
    v18 = v36;
    v41 = *(void (__fastcall **)(ReferenceCounted *, _QWORD, void ***, __int64, __int64, void **, void **, char *))(*(_QWORD *)v36 + 32LL);
    v19 = TempBuffer<0>::TempBuffer<0>((__int64)&v37, a7, a8);
    v20 = TempBuffer<0>::TempBuffer<0>((__int64)&v45, a5, a6);
    v41(v18, v47, &v32, v20, v19, &v34, &Src, &v46);
    HeapAllocator::Free(v45);
    HeapAllocator::Free(v37);
    *v15 = v46 != 0;
    v21 = &`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
    if ( Src )
      v21 = (__int64 *)Src;
    v22 = -1;
    do
      ++v22;
    while ( *((_WORD *)v21 + v22) );
    v23 = 2 * v22 + 2;
    v24 = (wchar_t *)CoTaskMemAlloc(v23);
    v25 = v24;
    if ( !v24 )
      LowMemoryError::Throw(L"ComCopy");
    memcpy_0(v24, v21, v23);
    *a12 = v25;
    if ( Size )
    {
      *v16 = (unsigned __int8 *)Copy<TaskAllocator>(v34, Size);
      *v17 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(Size);
    }
    v32 = &ObjectHandle::`vftable';
    ObjectHandle::Clear((ObjectHandle *)&v32);
    HeapAllocator::Free(v34);
    HeapAllocator::Free(Src);
    Src = 0;
    if ( v36 )
      ReferenceCounted::Release(v36);
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v30) = -2147024882;
    *a13 = 0;
    v14 = (unsigned int)v30;
    goto LABEL_21;
  }
  catch ( const ATL::CAtlException *v42 )
  {
    LODWORD(v30) = *(_DWORD *)v42;
    *a13 = 0;
    goto LABEL_20;
  }
  catch ( const EapHost::EapException *v43 )
  {
    EapHost::EapException2EapErrorOle(v43, (const struct EapHost::EapException *)a13, &v30, v26);
    goto LABEL_20;
  }
  catch ( const Exception *v44 )
  {
    EapHost::Exception2EapErrorOle(v44, (const struct Exception *)a13, &v30, v26);
LABEL_20:
    v14 = (unsigned int)v30;
    if ( (int)v30 < 0 )
    {
LABEL_21:
      *a9 = 0;
      v27 = a11;
      if ( *a11 )
      {
        CoTaskMemFree(*a11);
        *v27 = 0;
      }
      v28 = a12;
      if ( *a12 )
      {
        CoTaskMemFree(*a12);
        *v28 = 0;
      }
    }
  }
  v37 = &EapHost::EapMethodType::`vftable';
}

```

## disassembly

```asm
0x180007980  mov     r11, rsp
0x180007983  mov     [r11+8], rbx
0x180007987  mov     [r11+20h], rsi
0x18000798b  mov     [r11+18h], r8d
0x18000798f  push    rdi
0x180007990  push    r12
0x180007992  push    r13
0x180007994  push    r14
0x180007996  push    r15
0x180007998  sub     rsp, 0E0h
0x18000799f  mov     r14, r9
0x1800079a2  mov     r10, rcx
0x1800079a5  xor     ebx, ebx
0x1800079a7  mov     edi, ebx
0x1800079a9  mov     dword ptr [rsp+108h+var_B8], ebx
0x1800079ad  test    rdx, rdx
0x1800079b0  jz      loc_180007C75
0x1800079b6  mov     rsi, [rsp+108h+arg_40]
0x1800079be  test    rsi, rsi
0x1800079c1  jz      loc_180007C75
0x1800079c7  cmp     [rsp+108h+arg_60], rbx
0x1800079cf  jz      loc_180007C75
0x1800079d5  mov     r13, [rsp+108h+arg_50]
0x1800079dd  test    r13, r13
0x1800079e0  jz      loc_180007C75
0x1800079e6  mov     r12, [rsp+108h+arg_48]
0x1800079ee  test    r12, r12
0x1800079f1  jz      loc_180007C75
0x1800079f7  cmp     [rsp+108h+arg_58], rbx
0x1800079ff  jz      loc_180007C75
0x180007a05  mov     [r13+0], rbx
0x180007a09  mov     [r12], ebx
0x180007a0d  mov     cl, [rdx]
0x180007a0f  mov     [r11-78h], cl
0x180007a13  mov     eax, [rdx+4]
0x180007a16  mov     [r11-74h], eax
0x180007a1a  mov     eax, [rdx+8]
0x180007a1d  mov     [r11-70h], eax
0x180007a21  cmp     cl, 0FEh
0x180007a24  jz      short loc_180007A2A
0x180007a26  mov     [r11-74h], rbx
0x180007a2a  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180007a31  mov     [rsp+108h+var_80], rax
0x180007a39  mov     eax, [rdx+0Ch]
0x180007a3c  mov     [rsp+108h+var_68], eax
0x180007a43  lea     r8, [rsp+108h+var_80]
0x180007a4b  lea     rdx, [rsp+108h+var_88]
0x180007a53  mov     rcx, [r10-68h]; this
0x180007a57  call    ?GetEapMethodRuntime@EapLibraryManagerRuntime@Peer@EapLm@@QEAA?AV?$SmartPointer@UIEapMethodRuntime@Peer@EapLm@@@@AEBVEapMethodType@EapHost@@@Z; EapLm::Peer::EapLibraryManagerRuntime::GetEapMethodRuntime(EapHost::EapMethodType const &)
0x180007a5c  nop
0x180007a5d  mov     [rsp+108h+arg_8], bl
0x180007a64  mov     [rsp+108h+Src], rbx
0x180007a69  mov     [rsp+108h+var_98], rbx
0x180007a6e  mov     [rsp+108h+Size], rbx
0x180007a73  lea     rax, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x180007a7a  mov     [rsp+108h+var_A8], rax
0x180007a7f  mov     [rsp+108h+var_A0], rbx
0x180007a84  lea     rcx, [rsp+108h+var_A8]; this
0x180007a89  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x180007a8e  mov     [rsp+108h+var_A0], r14
0x180007a93  mov     r14, [rsp+108h+var_88]
0x180007a9b  mov     rax, [r14]
0x180007a9e  mov     rax, [rax+20h]
0x180007aa2  mov     [rsp+108h+var_60], rax
0x180007aaa  mov     edx, [rsp+108h+arg_30]
0x180007ab1  mov     r8, [rsp+108h+arg_38]
0x180007ab9  lea     rcx, [rsp+108h+var_80]
0x180007ac1  call    ??0?$TempBuffer@$0A@@@QEAA@_KPEBX@Z; TempBuffer<0>::TempBuffer<0>(unsigned __int64,void const *)
0x180007ac6  mov     r15, rax
0x180007ac9  mov     edx, [rsp+108h+arg_20]
0x180007ad0  mov     r8, [rsp+108h+arg_28]
0x180007ad8  lea     rcx, [rsp+108h+var_40]
0x180007ae0  call    ??0?$TempBuffer@$0A@@@QEAA@_KPEBX@Z; TempBuffer<0>::TempBuffer<0>(unsigned __int64,void const *)
0x180007ae5  nop
0x180007ae6  lea     rcx, [rsp+108h+arg_8]
0x180007aee  mov     [rsp+108h+var_D0], rcx
0x180007af3  lea     rcx, [rsp+108h+Src]
0x180007af8  mov     [rsp+108h+var_D8], rcx
0x180007afd  lea     rcx, [rsp+108h+var_98]
0x180007b02  mov     [rsp+108h+var_E0], rcx
0x180007b07  mov     [rsp+108h+var_E8], r15
0x180007b0c  mov     r9, rax
0x180007b0f  lea     r8, [rsp+108h+var_A8]
0x180007b14  mov     edx, [rsp+108h+arg_10]
0x180007b1b  mov     rcx, r14
0x180007b1e  mov     rax, [rsp+108h+var_60]
0x180007b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b2b  nop
0x180007b2c  mov     rcx, [rsp+108h+var_40]; void *
0x180007b34  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180007b39  nop
0x180007b3a  mov     rcx, [rsp+108h+var_80]; void *
0x180007b42  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180007b47  mov     eax, ebx
0x180007b49  cmp     [rsp+108h+arg_8], bl
0x180007b50  setnz   al
0x180007b53  mov     [rsi], eax
0x180007b55  lea     r14, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x180007b5c  cmp     [rsp+108h+Src], rbx
0x180007b61  cmovnz  r14, [rsp+108h+Src]
0x180007b67  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007b6b  inc     rax
0x180007b6e  cmp     [r14+rax*2], bx
0x180007b73  jnz     short loc_180007B6B
0x180007b75  lea     r15, ds:2[rax*2]
0x180007b7d  mov     rcx, r15; cb
0x180007b80  call    cs:__imp_CoTaskMemAlloc
0x180007b86  mov     rsi, rax
0x180007b89  test    rax, rax
0x180007b8c  jnz     short loc_180007B9A
0x180007b8e  lea     rcx, aComcopy; "ComCopy"
0x180007b95  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x180007b9a  mov     r8, r15; Size
0x180007b9d  mov     rdx, r14; Src
0x180007ba0  mov     rcx, rsi; void *
0x180007ba3  call    memcpy_0
0x180007ba8  mov     rax, [rsp+108h+arg_58]
0x180007bb0  mov     [rax], rsi
0x180007bb3  mov     rdx, [rsp+108h+Size]; Size
0x180007bb8  test    rdx, rdx
0x180007bbb  jz      short loc_180007BD9
0x180007bbd  mov     rcx, [rsp+108h+var_98]; Src
0x180007bc2  call    ??$Copy@VTaskAllocator@@@@YAPEAEPEBE_K@Z; Copy<TaskAllocator>(uchar const *,unsigned __int64)
0x180007bc7  mov     [r13+0], rax
0x180007bcb  mov     rcx, [rsp+108h+Size]
0x180007bd0  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180007bd5  mov     [r12], eax
0x180007bd9  lea     rax, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x180007be0  mov     [rsp+108h+var_A8], rax
0x180007be5  lea     rcx, [rsp+108h+var_A8]; this
0x180007bea  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x180007bef  nop
0x180007bf0  mov     rcx, [rsp+108h+var_98]; void *
0x180007bf5  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180007bfa  nop
0x180007bfb  mov     rcx, [rsp+108h+Src]; void *
0x180007c00  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180007c05  mov     [rsp+108h+Src], rbx
0x180007c0a  mov     rcx, [rsp+108h+var_88]; this
0x180007c12  test    rcx, rcx
0x180007c15  jz      short loc_180007C1D
0x180007c17  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x180007c1c  nop
0x180007c1d  jmp     short loc_180007C71
0x180007c1f  xor     ebx, ebx
0x180007c21  mov     edi, dword ptr [rsp+108h+var_B8]
0x180007c25  jmp     short loc_180007C35
0x180007c27  jmp     short loc_180007C2B
0x180007c29  jmp     short $+2
0x180007c2b  mov     edi, dword ptr [rsp+108h+var_B8]
0x180007c2f  xor     ebx, ebx
0x180007c31  test    edi, edi
0x180007c33  jns     short loc_180007C71
0x180007c35  mov     rax, [rsp+108h+arg_40]
0x180007c3d  mov     [rax], ebx
0x180007c3f  mov     rsi, [rsp+108h+arg_50]
0x180007c47  cmp     [rsi], rbx
0x180007c4a  jz      short loc_180007C58
0x180007c4c  mov     rcx, [rsi]; pv
0x180007c4f  call    cs:__imp_CoTaskMemFree
0x180007c55  mov     [rsi], rbx
0x180007c58  mov     rsi, [rsp+108h+arg_58]
0x180007c60  cmp     [rsi], rbx
0x180007c63  jz      short loc_180007C71
0x180007c65  mov     rcx, [rsi]; pv
0x180007c68  call    cs:__imp_CoTaskMemFree
0x180007c6e  mov     [rsi], rbx
0x180007c71  mov     eax, edi
0x180007c73  jmp     short loc_180007C7A
0x180007c75  mov     eax, 80004003h
0x180007c7a  lea     r11, [rsp+108h+var_28]
0x180007c82  mov     rbx, [r11+30h]
0x180007c86  mov     rsi, [r11+48h]
0x180007c8a  mov     rsp, r11
0x180007c8d  pop     r15
0x180007c8f  pop     r14
0x180007c91  pop     r13
0x180007c93  pop     r12
0x180007c95  pop     rdi
0x180007c96  retn
```
