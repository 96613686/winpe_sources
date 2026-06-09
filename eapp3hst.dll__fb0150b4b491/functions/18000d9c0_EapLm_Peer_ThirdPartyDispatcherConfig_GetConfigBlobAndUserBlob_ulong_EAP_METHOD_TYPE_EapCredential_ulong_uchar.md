# EapLm::Peer::ThirdPartyDispatcherConfig::GetConfigBlobAndUserBlob(ulong,_EAP_METHOD_TYPE,_EapCredential,ulong *,uchar * *,ulong *,uchar * *,_EAP_ERROR * *)

- ea: `0x18000d9c0`
- end: `0x18000db73`
- name: `?GetConfigBlobAndUserBlob@ThirdPartyDispatcherConfig@Peer@EapLm@@UEAAJKU_EAP_METHOD_TYPE@@U_EapCredential@@PEAKPEAPEAE23PEAPEAU_EAP_ERROR@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(EapLm::Peer::ThirdPartyDispatcherConfig *__hidden this, unsigned int, struct _EAP_METHOD_TYPE *, struct _EapCredential *, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int8 **, struct _EAP_ERROR **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000439c`
- `0x1800067cc`
- `0x180006c0c`
- `0x18000d9c0`
- `0x180012c10`
- `0x180016e44`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::ThirdPartyDispatcherConfig::GetConfigBlobAndUserBlob(
        EapLm::Peer::ThirdPartyDispatcherConfig *this,
        unsigned int a2,
        struct _EAP_METHOD_TYPE *a3,
        struct _EapCredential *a4,
        unsigned int *a5,
        unsigned __int8 **a6,
        unsigned int *a7,
        unsigned __int8 **a8,
        struct _EAP_ERROR **a9)
{
  __int64 v11; // r9
  unsigned __int8 *v12; // rcx
  unsigned __int8 *v13; // rcx
  int *v14; // r9
  unsigned __int8 *v16; // [rsp+30h] [rbp-88h] BYREF
  ReferenceCounted *v17; // [rsp+38h] [rbp-80h] BYREF
  void *v18; // [rsp+40h] [rbp-78h] BYREF
  size_t v19; // [rsp+48h] [rbp-70h]
  void *v20; // [rsp+50h] [rbp-68h] BYREF
  size_t v21; // [rsp+58h] [rbp-60h]
  __m256i v22; // [rsp+60h] [rbp-58h] BYREF
  LPWSTR password; // [rsp+80h] [rbp-38h]
  const ATL::CAtlException *v24; // [rsp+90h] [rbp-28h] BYREF
  const EapHost::EapException *v25; // [rsp+98h] [rbp-20h] BYREF
  const Exception *v26; // [rsp+A0h] [rbp-18h] BYREF
  struct _EAP_ERROR *v27; // [rsp+C0h] [rbp+8h] BYREF
  unsigned __int8 *v28; // [rsp+D0h] [rbp+18h] BYREF

  LODWORD(v27) = 0;
  v16 = 0;
  v28 = 0;
  v11 = *((_QWORD *)this - 12);
  v22.m256i_i8[8] = a3->eapType.type;
  *(__int64 *)((char *)&v22.m256i_i64[1] + 4) = *(_QWORD *)&a3->eapType.dwVendorId;
  if ( v22.m256i_i8[8] != -2 )
    *(__int64 *)((char *)&v22.m256i_i64[1] + 4) = 0;
  try
  {
    v22.m256i_i64[0] = (__int64)&EapHost::EapMethodType::`vftable';
    v22.m256i_i32[6] = a3->dwAuthorId;
    EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(v11, &v17, &v22);
    v20 = 0;
    v21 = 0;
    v18 = 0;
    v19 = 0;
    v22 = *(__m256i *)&a4->credType;
    password = a4->credData.certificate.password;
    (*(void (__fastcall **)(ReferenceCounted *, _QWORD, __m256i *, void **, void **))(*(_QWORD *)v17 + 144LL))(
      v17,
      a2,
      &v22,
      &v20,
      &v18);
    if ( v21 )
    {
      com_ptr<unsigned char>::Assign(&v16, v20, v21);
      v12 = v16;
      v16 = 0;
      *a6 = v12;
    }
    if ( v19 )
    {
      com_ptr<unsigned char>::Assign(&v28, v18, v19);
      v13 = v28;
      v28 = 0;
      *a8 = v13;
    }
    HeapAllocator::Free(v18);
    HeapAllocator::Free(v20);
    if ( v17 )
      ReferenceCounted::Release(v17);
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v27) = -2147024882;
    if ( a9 )
      *a9 = 0;
  }
  catch ( const ATL::CAtlException *v24 )
  {
    LODWORD(v27) = *(_DWORD *)v24;
    if ( a9 )
      *a9 = 0;
  }
  catch ( const EapHost::EapException *v25 )
  {
    EapHost::EapException2EapErrorOle(v25, (const struct EapHost::EapException *)a9, &v27, v14);
  }
  catch ( const Exception *v26 )
  {
    EapHost::Exception2EapErrorOle(v26, (const struct Exception *)a9, &v27, v14);
  }
  v22.m256i_i64[0] = (__int64)&EapHost::EapMethodType::`vftable';
  v22.m256i_i32[6] = a3->dwAuthorId;
  EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(v11, &v17, &v22);
}

```

## disassembly

```asm
0x18000d9c0  mov     rax, rsp
0x18000d9c3  mov     [rax+10h], rbx
0x18000d9c7  push    rdi
0x18000d9c8  sub     rsp, 0B0h
0x18000d9cf  mov     rbx, r9
0x18000d9d2  mov     edi, edx
0x18000d9d4  mov     dword ptr [rax+8], 0
0x18000d9db  mov     [rsp+0B8h+var_88], 0
0x18000d9e4  mov     qword ptr [rax+18h], 0
0x18000d9ec  mov     r9, [rcx-60h]
0x18000d9f0  mov     cl, [r8]
0x18000d9f3  mov     [rax-50h], cl
0x18000d9f6  mov     eax, [r8+4]
0x18000d9fa  mov     dword ptr [rsp+0B8h+var_58+0Ch], eax
0x18000d9fe  mov     eax, [r8+8]
0x18000da02  mov     dword ptr [rsp+0B8h+var_58+10h], eax
0x18000da06  cmp     cl, 0FEh
0x18000da09  jz      short loc_18000DA14
0x18000da0b  mov     qword ptr [rsp+0B8h+var_58+0Ch], 0
0x18000da14  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18000da1b  mov     qword ptr [rsp+0B8h+var_58], rax
0x18000da20  mov     eax, [r8+0Ch]
0x18000da24  mov     [rsp+0B8h+var_40], eax
0x18000da28  lea     r8, [rsp+0B8h+var_58]
0x18000da2d  lea     rdx, [rsp+0B8h+var_80]
0x18000da32  mov     rcx, r9
0x18000da35  call    ?GetEapMethodConfig@EapLibraryManagerConfig@Peer@EapLm@@QEAA?AV?$SmartPointer@UIEapMethodConfig@Peer@EapLm@@@@AEBVEapMethodType@EapHost@@@Z; EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(EapHost::EapMethodType const &)
0x18000da3a  nop
0x18000da3b  mov     [rsp+0B8h+var_68], 0
0x18000da44  mov     [rsp+0B8h+var_60], 0
0x18000da4d  mov     [rsp+0B8h+var_78], 0
0x18000da56  mov     [rsp+0B8h+var_70], 0
0x18000da5f  mov     rcx, [rsp+0B8h+var_80]
0x18000da64  movups  xmm0, xmmword ptr [rbx]
0x18000da67  movaps  xmmword ptr [rsp+0B8h+var_58], xmm0
0x18000da6c  movups  xmm1, xmmword ptr [rbx+10h]
0x18000da70  movaps  xmmword ptr [rsp+70h], xmm1
0x18000da75  movsd   xmm0, qword ptr [rbx+20h]
0x18000da7a  movsd   [rsp+0B8h+var_38], xmm0
0x18000da83  mov     rax, [rcx]
0x18000da86  lea     rdx, [rsp+0B8h+var_78]
0x18000da8b  mov     [rsp+0B8h+var_98], rdx
0x18000da90  lea     r9, [rsp+0B8h+var_68]
0x18000da95  lea     r8, [rsp+0B8h+var_58]
0x18000da9a  mov     edx, edi
0x18000da9c  mov     rax, [rax+90h]
0x18000daa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daa8  mov     r8, [rsp+0B8h+var_60]
0x18000daad  test    r8, r8
0x18000dab0  jz      short loc_18000DADA
0x18000dab2  mov     rdx, [rsp+0B8h+var_68]
0x18000dab7  lea     rcx, [rsp+0B8h+var_88]
0x18000dabc  call    ?Assign@?$com_ptr@E@@QEAAXPEBE_K@Z; com_ptr<uchar>::Assign(uchar const *,unsigned __int64)
0x18000dac1  mov     rcx, [rsp+0B8h+var_88]
0x18000dac6  mov     [rsp+0B8h+var_88], 0
0x18000dacf  mov     rax, [rsp+0B8h+arg_28]
0x18000dad7  mov     [rax], rcx
0x18000dada  mov     r8, [rsp+0B8h+var_70]
0x18000dadf  test    r8, r8
0x18000dae2  jz      short loc_18000DB15
0x18000dae4  mov     rdx, [rsp+0B8h+var_78]
0x18000dae9  lea     rcx, [rsp+0B8h+arg_10]
0x18000daf1  call    ?Assign@?$com_ptr@E@@QEAAXPEBE_K@Z; com_ptr<uchar>::Assign(uchar const *,unsigned __int64)
0x18000daf6  mov     rcx, [rsp+0B8h+arg_10]
0x18000dafe  mov     [rsp+0B8h+arg_10], 0
0x18000db0a  mov     rax, [rsp+0B8h+arg_38]
0x18000db12  mov     [rax], rcx
0x18000db15  mov     rcx, [rsp+0B8h+var_78]; void *
0x18000db1a  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18000db1f  nop
0x18000db20  mov     rcx, [rsp+0B8h+var_68]; void *
0x18000db25  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18000db2a  nop
0x18000db2b  mov     rcx, [rsp+0B8h+var_80]; this
0x18000db30  test    rcx, rcx
0x18000db33  jz      short loc_18000DB3B
0x18000db35  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18000db3a  nop
0x18000db3b  jmp     short loc_18000DB43
0x18000db3d  jmp     short loc_18000DB43
0x18000db3f  jmp     short loc_18000DB43
0x18000db41  jmp     short $+2
0x18000db43  lea     rcx, [rsp+0B8h+arg_10]
0x18000db4b  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x18000db50  nop
0x18000db51  lea     rcx, [rsp+0B8h+var_88]
0x18000db56  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x18000db5b  mov     eax, dword ptr [rsp+0B8h+arg_0]
0x18000db62  mov     rbx, [rsp+0B8h+arg_8]
0x18000db6a  add     rsp, 0B0h
0x18000db71  pop     rdi
0x18000db72  retn
```
