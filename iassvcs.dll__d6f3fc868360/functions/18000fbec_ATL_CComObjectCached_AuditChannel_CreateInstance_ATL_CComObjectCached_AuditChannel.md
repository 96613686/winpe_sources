# ATL::CComObjectCached<AuditChannel>::CreateInstance(ATL::CComObjectCached<AuditChannel> * *)

- ea: `0x18000fbec`
- end: `0x18000fd09`
- name: `?CreateInstance@?$CComObjectCached@VAuditChannel@@@ATL@@SAJPEAPEAV12@@Z`
- size: `285`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f3b0`

## callees

- `0x18000d7ac`
- `0x18000d98c`
- `0x18000fbec`
- `0x18001033c`

## import_xrefs

- `msvcrt!free` at `0x18000fce9`
- `msvcrt!free` at `0x18000fce9`
- `KERNEL32!DeleteCriticalSection` at `0x18000fce0`
- `KERNEL32!DeleteCriticalSection` at `0x18000fce0`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<AuditChannel>::CreateInstance(_QWORD *a1)
{
  _QWORD *v1; // r14
  int v3; // esi
  char *v4; // rax
  _BYTE *v5; // rbx
  _BYTE *v7; // [rsp+60h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = (char *)operator new(0x60u);
    v5 = v4;
    if ( v4 )
    {
      *((_DWORD *)v4 + 4) = 0;
      *(_OWORD *)(v4 + 24) = 0;
      *(_OWORD *)(v4 + 40) = 0;
      *((_QWORD *)v4 + 7) = 0;
      v4[64] = 0;
      *((_QWORD *)v4 + 9) = 0;
      *((_QWORD *)v4 + 10) = 0;
      *((_QWORD *)v4 + 11) = 0;
      *(_QWORD *)v4 = &ATL::CComObjectCached<AuditChannel>::`vftable'{for `IAuditSink'};
      *((_QWORD *)v4 + 1) = &ATL::CComObjectCached<AuditChannel>::`vftable'{for `IAuditSource'};
    }
    v7 = v4;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v7;
  }
  if ( v5 )
  {
    v3 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v5 + 24));
    if ( v3 < 0 )
    {
      *(_QWORD *)v5 = &ATL::CComObjectCached<AuditChannel>::`vftable'{for `IAuditSink'};
      *((_QWORD *)v5 + 1) = &ATL::CComObjectCached<AuditChannel>::`vftable'{for `IAuditSource'};
      *((_DWORD *)v5 + 4) = -1073741823;
      std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::~vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>((__int64)(v5 + 72));
      if ( v5[64] )
      {
        v5[64] = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v5 + 24));
      }
      free(v5);
      v5 = 0;
    }
    else
    {
      v5[64] = 1;
      v3 = 0;
    }
  }
  *v1 = v5;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000fbec  mov     [rsp+arg_18], rbx
0x18000fbf1  mov     [rsp+arg_0], rcx
0x18000fbf6  push    rsi
0x18000fbf7  push    r12
0x18000fbf9  push    r13
0x18000fbfb  push    r14
0x18000fbfd  push    r15
0x18000fbff  sub     rsp, 20h
0x18000fc03  mov     r14, rcx
0x18000fc06  test    rcx, rcx
0x18000fc09  jnz     short loc_18000FC15
0x18000fc0b  mov     eax, 80004003h
0x18000fc10  jmp     loc_18000FCF6
0x18000fc15  mov     qword ptr [rcx], 0
0x18000fc1c  mov     esi, 8007000Eh
0x18000fc21  mov     [rsp+48h+arg_8], esi
0x18000fc25  mov     [rsp+48h+arg_10], 0
0x18000fc2e  mov     ecx, 60h ; '`'; Size
0x18000fc33  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fc38  mov     rbx, rax
0x18000fc3b  lea     r12, ??_7?$CComObjectCached@VAuditChannel@@@ATL@@6BIAuditSink@@@; const ATL::CComObjectCached<AuditChannel>::`vftable'{for `IAuditSink'}
0x18000fc42  lea     r13, ??_7?$CComObjectCached@VAuditChannel@@@ATL@@6BIAuditSource@@@; const ATL::CComObjectCached<AuditChannel>::`vftable'{for `IAuditSource'}
0x18000fc49  test    rbx, rbx
0x18000fc4c  jz      short loc_18000FC7C
0x18000fc4e  mov     dword ptr [rax+10h], 0
0x18000fc55  xorps   xmm0, xmm0
0x18000fc58  xor     eax, eax
0x18000fc5a  movups  xmmword ptr [rbx+18h], xmm0
0x18000fc5e  movups  xmmword ptr [rbx+28h], xmm0
0x18000fc62  mov     [rbx+38h], rax
0x18000fc66  mov     [rbx+40h], al
0x18000fc69  mov     [rbx+48h], rax
0x18000fc6d  mov     [rbx+50h], rax
0x18000fc71  mov     [rbx+58h], rax
0x18000fc75  mov     [rbx], r12
0x18000fc78  mov     [rbx+8], r13
0x18000fc7c  mov     [rsp+48h+arg_10], rbx
0x18000fc81  jmp     short loc_18000FC9F
0x18000fc83  lea     r12, ??_7?$CComObjectCached@VAuditChannel@@@ATL@@6BIAuditSink@@@; const ATL::CComObjectCached<AuditChannel>::`vftable'{for `IAuditSink'}
0x18000fc8a  lea     r13, ??_7?$CComObjectCached@VAuditChannel@@@ATL@@6BIAuditSource@@@; const ATL::CComObjectCached<AuditChannel>::`vftable'{for `IAuditSource'}
0x18000fc91  mov     r14, [rsp+48h+arg_0]
0x18000fc96  mov     esi, [rsp+48h+arg_8]
0x18000fc9a  mov     rbx, [rsp+48h+arg_10]
0x18000fc9f  test    rbx, rbx
0x18000fca2  jz      short loc_18000FCF1
0x18000fca4  lea     rcx, [rbx+18h]; this
0x18000fca8  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000fcad  mov     esi, eax
0x18000fcaf  test    eax, eax
0x18000fcb1  js      short loc_18000FCBB
0x18000fcb3  mov     byte ptr [rbx+40h], 1
0x18000fcb7  xor     esi, esi
0x18000fcb9  jmp     short loc_18000FCF1
0x18000fcbb  mov     [rbx], r12
0x18000fcbe  mov     [rbx+8], r13
0x18000fcc2  mov     dword ptr [rbx+10h], 0C0000001h
0x18000fcc9  lea     rcx, [rbx+48h]
0x18000fccd  call    ??1?$vector@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@std@@QEAA@XZ; std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::~vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>(void)
0x18000fcd2  cmp     byte ptr [rbx+40h], 0
0x18000fcd6  jz      short loc_18000FCE6
0x18000fcd8  mov     byte ptr [rbx+40h], 0
0x18000fcdc  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000fce0  call    cs:__imp_DeleteCriticalSection
0x18000fce6  mov     rcx, rbx; Block
0x18000fce9  call    cs:__imp_free
0x18000fcef  xor     ebx, ebx
0x18000fcf1  mov     [r14], rbx
0x18000fcf4  mov     eax, esi
0x18000fcf6  mov     rbx, [rsp+48h+arg_18]
0x18000fcfb  add     rsp, 20h
0x18000fcff  pop     r15
0x18000fd01  pop     r14
0x18000fd03  pop     r13
0x18000fd05  pop     r12
0x18000fd07  pop     rsi
0x18000fd08  retn
```
