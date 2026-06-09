# ATL::IConnectionPointImpl<ConnectionManager,&_GUID const IID_INetConnectionNotifySink,ATL::CComDynamicUnkArray>::EnumConnections(IEnumConnections * *)

- ea: `0x18000fbe0`
- end: `0x18000fe22`
- name: `?EnumConnections@?$IConnectionPointImpl@VConnectionManager@@$1?IID_INetConnectionNotifySink@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAPEAUIEnumConnections@@@Z`
- size: `578`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002320`
- `0x1800064a0`
- `0x18000a9c0`
- `0x18000fbe0`
- `0x180011804`
- `0x180019c68`
- `0x180036010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000fd26`
- `KERNEL32!LeaveCriticalSection` at `0x18000fdd7`
- `KERNEL32!LeaveCriticalSection` at `0x18000fd26`
- `KERNEL32!LeaveCriticalSection` at `0x18000fdd7`
- `KERNEL32!EnterCriticalSection` at `0x18000fca4`
- `KERNEL32!EnterCriticalSection` at `0x18000fca4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall ATL::IConnectionPointImpl<ConnectionManager,&_GUID const IID_INetConnectionNotifySink,ATL::CComDynamicUnkArray>::EnumConnections(
        __int64 a1,
        void **a2)
{
  void *v5; // rax
  __int64 v6; // rbx
  void *v7; // rbx
  __int64 v8; // r14
  int *v9; // r13
  void *v10; // r12
  void *v11; // r8
  _QWORD *v12; // r15
  unsigned __int64 i; // rcx
  int v14; // edx
  _QWORD *v15; // rcx
  _QWORD *v16; // r9
  int Interface; // edi
  _DWORD *v18; // [rsp+88h] [rbp+10h]

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = MemAlloc(0x90u);
  v6 = (__int64)v5;
  if ( v5 )
  {
    memset_0(v5, 0, 0x90u);
    v7 = (void *)ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>(v6);
  }
  else
  {
    v7 = 0;
  }
  if ( !v7 )
    return 2147942414LL;
  v8 = a1 + 72;
  if ( !a1 )
    v8 = 80;
  EnterCriticalSection((LPCRITICAL_SECTION)v8);
  v9 = (int *)(a1 + 16);
  v10 = MemAlloc(saturated_mul(*(int *)(a1 + 16), 0x10u));
  if ( !v10 )
  {
    (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v7 + 56LL))(v7, 1);
    LeaveCriticalSection((LPCRITICAL_SECTION)v8);
    return 2147942414LL;
  }
  v11 = v10;
  v18 = v10;
  v12 = *(_QWORD **)(a1 + 8);
  for ( i = (unsigned __int64)&v12[*v9]; (unsigned __int64)v12 < i; i = *(_QWORD *)(a1 + 8) + 8LL * *v9 )
  {
    if ( *v12 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 8LL))(*v12);
      *(_QWORD *)v18 = *v12;
      if ( *v12 )
      {
        v14 = 1;
        v15 = *(_QWORD **)(a1 + 8);
        v16 = &v15[*(int *)(a1 + 16)];
        while ( v15 < v16 )
        {
          if ( *v15 == *v12 )
            goto LABEL_20;
          ++v14;
          ++v15;
        }
      }
      v14 = 0;
LABEL_20:
      v18[2] = v14;
      v11 = v18 + 4;
      v18 += 4;
    }
    ++v12;
  }
  ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(
    v7,
    v10,
    v11,
    0,
    2);
  LeaveCriticalSection((LPCRITICAL_SECTION)v8);
  Interface = ATL::AtlInternalQueryInterface(
                v7,
                (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>::_GetEntries'::`2'::_entries,
                &GUID_b196b287_bab4_101a_b69c_00aa00341d07,
                a2);
  if ( Interface < 0 )
    (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v7 + 56LL))(v7, 1);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x18000fbe0  mov     [rsp+arg_8], rdx
0x18000fbe5  mov     [rsp+arg_0], rcx
0x18000fbea  push    rbx
0x18000fbeb  push    rsi
0x18000fbec  push    rdi
0x18000fbed  push    r12
0x18000fbef  push    r13
0x18000fbf1  push    r14
0x18000fbf3  push    r15
0x18000fbf5  sub     rsp, 40h
0x18000fbf9  mov     rsi, rdx
0x18000fbfc  mov     rdi, rcx
0x18000fbff  test    rdx, rdx
0x18000fc02  jnz     short loc_18000FC0E
0x18000fc04  mov     eax, 80004003h
0x18000fc09  jmp     loc_18000FE12
0x18000fc0e  mov     qword ptr [rdx], 0
0x18000fc15  mov     [rsp+78h+arg_10], 0
0x18000fc21  mov     r14d, 90h
0x18000fc27  mov     ecx, r14d; unsigned __int64
0x18000fc2a  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18000fc2f  mov     rbx, rax
0x18000fc32  mov     [rsp+78h+arg_18], rax
0x18000fc3a  test    rax, rax
0x18000fc3d  jz      short loc_18000FC59
0x18000fc3f  mov     r8d, r14d; Size
0x18000fc42  xor     edx, edx; Val
0x18000fc44  mov     rcx, rax; void *
0x18000fc47  call    memset_0
0x18000fc4c  mov     rcx, rbx
0x18000fc4f  call    ??0?$CComObject@V?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>>(void *)
0x18000fc54  mov     rbx, rax
0x18000fc57  jmp     short loc_18000FC5B
0x18000fc59  xor     ebx, ebx
0x18000fc5b  mov     [rsp+78h+arg_10], rbx
0x18000fc63  jmp     short loc_18000FC7D
0x18000fc65  mov     rdi, [rsp+78h+arg_0]
0x18000fc6d  mov     rsi, [rsp+78h+arg_8]
0x18000fc75  mov     rbx, [rsp+78h+arg_10]
0x18000fc7d  test    rbx, rbx
0x18000fc80  jnz     short loc_18000FC8C
0x18000fc82  mov     eax, 8007000Eh
0x18000fc87  jmp     loc_18000FE12
0x18000fc8c  lea     r14, [rdi+48h]
0x18000fc90  mov     eax, 50h ; 'P'
0x18000fc95  test    rdi, rdi
0x18000fc98  cmovz   r14, rax
0x18000fc9c  mov     [rsp+78h+var_40], r14
0x18000fca1  mov     rcx, r14; lpCriticalSection
0x18000fca4  call    cs:__imp_EnterCriticalSection
0x18000fcaa  nop
0x18000fcab  lea     r13, [rdi+10h]
0x18000fcaf  mov     [rsp+78h+var_48], r13
0x18000fcb4  movsxd  rcx, dword ptr [r13+0]
0x18000fcb8  mov     eax, 10h
0x18000fcbd  mul     rcx
0x18000fcc0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000fcc7  cmovb   rax, rcx
0x18000fccb  mov     rcx, rax; unsigned __int64
0x18000fcce  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18000fcd3  mov     r12, rax
0x18000fcd6  mov     [rsp+78h+arg_18], rax
0x18000fcde  jmp     short loc_18000FD0A
0x18000fce0  mov     rdi, [rsp+78h+arg_0]
0x18000fce8  mov     rsi, [rsp+78h+arg_8]
0x18000fcf0  mov     rbx, [rsp+78h+arg_10]
0x18000fcf8  mov     r12, [rsp+78h+arg_18]
0x18000fd00  mov     r13, [rsp+78h+var_48]
0x18000fd05  mov     r14, [rsp+78h+var_40]
0x18000fd0a  test    r12, r12
0x18000fd0d  jnz     short loc_18000FD31
0x18000fd0f  mov     rax, [rbx]
0x18000fd12  lea     edx, [r12+1]
0x18000fd17  mov     rcx, rbx
0x18000fd1a  mov     rax, [rax+38h]
0x18000fd1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd23  mov     rcx, r14; lpCriticalSection
0x18000fd26  call    cs:__imp_LeaveCriticalSection
0x18000fd2c  jmp     loc_18000FC82
0x18000fd31  mov     r8, r12
0x18000fd34  mov     [rsp+78h+arg_8], r12
0x18000fd3c  mov     r15, [rdi+8]
0x18000fd40  movsxd  rax, dword ptr [r13+0]
0x18000fd44  lea     rcx, [r15+rax*8]
0x18000fd48  jmp     short loc_18000FDB9
0x18000fd4a  mov     rcx, [r15]
0x18000fd4d  test    rcx, rcx
0x18000fd50  jz      short loc_18000FDA9
0x18000fd52  mov     rax, [rcx]
0x18000fd55  mov     rax, [rax+8]
0x18000fd59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd5e  mov     rax, [r15]
0x18000fd61  mov     r8, [rsp+78h+arg_8]
0x18000fd69  mov     [r8], rax
0x18000fd6c  mov     r10, [r15]
0x18000fd6f  test    r10, r10
0x18000fd72  jz      short loc_18000FD97
0x18000fd74  mov     edx, 1
0x18000fd79  mov     rcx, [rdi+8]
0x18000fd7d  movsxd  rax, dword ptr [rdi+10h]
0x18000fd81  lea     r9, [rcx+rax*8]
0x18000fd85  cmp     rcx, r9
0x18000fd88  jnb     short loc_18000FD97
0x18000fd8a  cmp     [rcx], r10
0x18000fd8d  jz      short loc_18000FD99
0x18000fd8f  inc     edx
0x18000fd91  add     rcx, 8
0x18000fd95  jmp     short loc_18000FD85
0x18000fd97  xor     edx, edx
0x18000fd99  mov     [r8+8], edx
0x18000fd9d  add     r8, 10h
0x18000fda1  mov     [rsp+78h+arg_8], r8
0x18000fda9  add     r15, 8
0x18000fdad  movsxd  rcx, dword ptr [r13+0]
0x18000fdb1  mov     rax, [rdi+8]
0x18000fdb5  lea     rcx, [rax+rcx*8]
0x18000fdb9  cmp     r15, rcx
0x18000fdbc  jb      short loc_18000FD4A
0x18000fdbe  mov     [rsp+78h+var_58], 2
0x18000fdc6  xor     r9d, r9d
0x18000fdc9  mov     rdx, r12
0x18000fdcc  mov     rcx, rbx
0x18000fdcf  call    ?Init@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@QEAAJPEAUtagCONNECTDATA@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(tagCONNECTDATA *,tagCONNECTDATA *,IUnknown *,ATL::CComEnumFlags)
0x18000fdd4  mov     rcx, r14; lpCriticalSection
0x18000fdd7  call    cs:__imp_LeaveCriticalSection
0x18000fddd  mov     r9, rsi; void **
0x18000fde0  lea     r8, _GUID_b196b287_bab4_101a_b69c_00aa00341d07; struct _GUID *
0x18000fde7  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000fdee  mov     rcx, rbx; void *
0x18000fdf1  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000fdf6  mov     edi, eax
0x18000fdf8  test    eax, eax
0x18000fdfa  jns     short loc_18000FE10
0x18000fdfc  mov     rcx, [rbx]
0x18000fdff  mov     rax, [rcx+38h]
0x18000fe03  mov     edx, 1
0x18000fe08  mov     rcx, rbx
0x18000fe0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe10  mov     eax, edi
0x18000fe12  add     rsp, 40h
0x18000fe16  pop     r15
0x18000fe18  pop     r14
0x18000fe1a  pop     r13
0x18000fe1c  pop     r12
0x18000fe1e  pop     rdi
0x18000fe1f  pop     rsi
0x18000fe20  pop     rbx
0x18000fe21  retn
```
