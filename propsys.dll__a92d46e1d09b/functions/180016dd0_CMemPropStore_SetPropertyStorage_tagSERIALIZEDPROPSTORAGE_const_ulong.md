# CMemPropStore::SetPropertyStorage(tagSERIALIZEDPROPSTORAGE const *,ulong)

- ea: `0x180016dd0`
- end: `0x1800170a7`
- name: `?SetPropertyStorage@CMemPropStore@@UEAAJPEFBUtagSERIALIZEDPROPSTORAGE@@K@Z`
- size: `727`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, const struct tagSERIALIZEDPROPSTORAGE *Src, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180007f40`
- `0x180016dd0`
- `0x180017770`
- `0x180049b90`
- `0x180049ca0`
- `0x18006fb80`
- `0x18006fb98`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017001`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017001`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016fc4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016fc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016fd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001700c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017070`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016fd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001700c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017070`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016f79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016f79`

## pseudocode

```c
__int64 __fastcall CMemPropStore::SetPropertyStorage(
        RTL_SRWLOCK *this,
        const struct tagSERIALIZEDPROPSTORAGE *Src,
        unsigned int a3)
{
  unsigned int v5; // esi
  const struct tagSERIALIZEDPROPSTORAGE *v6; // r9
  unsigned int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rbp
  unsigned int *v10; // r10
  BOOL v11; // r15d
  unsigned int v12; // r11d
  int v13; // eax
  __int64 v14; // rax
  unsigned __int64 v16; // rcx
  __int64 v17; // rax
  const struct tagSERIALIZEDPROPSTORAGE *v18; // rcx
  void *v19; // rbx
  void *v20; // rax
  size_t v21; // rax
  PVOID Ptr; // rcx
  PVOID v23; // rcx
  int v24; // ebx

  if ( !a3 )
  {
    CMemPropStore::_AcquireWriteLock((CMemPropStore *)this);
    CMemPropStore::_DeleteAllPropsFromDPAs((CMemPropStore *)this);
    CoTaskMemFree(this[25].Ptr);
    this[25].Ptr = 0;
    this[26].Ptr = 0;
    CMemPropStore::_ReleaseWriteLock((CMemPropStore *)this);
    return 0;
  }
  if ( !Src )
    return (unsigned int)-2147467261;
  v5 = 4;
  if ( a3 < 4 )
    goto LABEL_60;
  if ( *(_DWORD *)Src )
  {
    if ( *(_DWORD *)Src >= 0x1Cu && *(_DWORD *)Src <= a3 )
    {
      v6 = Src;
      v7 = -2147024883;
      while ( 1 )
      {
        if ( *((_DWORD *)v6 + 1) != 1397773105 )
          return (unsigned int)-2147286780;
        v8 = *((_QWORD *)v6 + 1) - *(_QWORD *)&FMTID_UserDefinedProperties.Data1;
        if ( !v8 )
          v8 = *((_QWORD *)v6 + 2) - *(_QWORD *)FMTID_UserDefinedProperties.Data4;
        v9 = *(unsigned int *)v6;
        v10 = (unsigned int *)((char *)v6 + 24);
        v11 = v8 == 0;
        v12 = v9 - 24;
        if ( (unsigned int)(v9 - 24) < 4 )
          goto LABEL_56;
        if ( !*v10 )
          goto LABEL_35;
        if ( *v10 < 9 || (v13 = 0, *v10 > v12) )
LABEL_56:
          v13 = -2147024883;
        while ( !v13 )
        {
          if ( v11 )
          {
            if ( v10[1] < 2 )
              return v7;
            v16 = v10[1];
            if ( v16 > (unsigned __int64)*v10 - 9 || (v10[1] & 1) != 0 || *(_WORD *)((char *)v10 + 2 * (v16 >> 1) + 7) )
              return v7;
          }
          v14 = *v10;
          v12 -= v14;
          v10 = (unsigned int *)((char *)v10 + v14);
          if ( v12 < 4 )
            goto LABEL_56;
          if ( *v10 )
          {
            if ( *v10 < 9 || *v10 > v12 )
              goto LABEL_56;
            v13 = 0;
          }
          else
          {
LABEL_35:
            v13 = 1;
          }
        }
        if ( v13 < 0 )
          return (unsigned int)v13;
        a3 -= v9;
        if ( a3 < 4 )
          return (unsigned int)-2147024883;
        v6 = (const struct tagSERIALIZEDPROPSTORAGE *)((char *)v6 + v9);
        if ( !*(_DWORD *)v6 )
        {
          v13 = 1;
          goto LABEL_37;
        }
        if ( *(_DWORD *)v6 < 0x1Cu || *(_DWORD *)v6 > a3 )
          return (unsigned int)-2147024883;
      }
    }
LABEL_60:
    v24 = -2147024883;
    goto LABEL_61;
  }
  v24 = 1;
LABEL_61:
  v13 = v24;
LABEL_37:
  if ( v13 >= 0 )
  {
    v17 = *(unsigned int *)Src;
    if ( (_DWORD)v17 )
    {
      v18 = Src;
      do
      {
        v18 = (const struct tagSERIALIZEDPROPSTORAGE *)((char *)v18 + v17);
        v5 += v17;
        v17 = *(unsigned int *)v18;
      }
      while ( (_DWORD)v17 );
    }
    if ( v5 > 0x8000000 )
    {
      v7 = -2147023604;
    }
    else
    {
      v19 = 0;
      if ( !v5 )
      {
LABEL_45:
        Ptr = this[28].Ptr;
        if ( Ptr )
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 24LL))(Ptr);
        else
          AcquireSRWLockExclusive(this + 31);
        CMemPropStore::_DeleteAllPropsFromDPAs((CMemPropStore *)this);
        CoTaskMemFree(this[25].Ptr);
        v23 = this[28].Ptr;
        this[25].Ptr = v19;
        HIDWORD(this[26].Ptr) = v5;
        LODWORD(this[26].Ptr) = v5;
        if ( v23 )
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)v23 + 32LL))(v23);
        else
          ReleaseSRWLockExclusive(this + 31);
        v7 = 0;
        goto LABEL_50;
      }
      v20 = CoTaskMemAlloc(v5);
      v19 = v20;
      if ( v20 )
      {
        v21 = CTCoAllocPolicy::_CoTaskMemSize(v20);
        memset_0(v19, 0, v21);
        memcpy_0(v19, Src, v5);
        goto LABEL_45;
      }
      v7 = -2147024882;
    }
LABEL_50:
    CoTaskMemFree(0);
    return v7;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180016dd0  mov     [rsp+arg_10], rbx
0x180016dd5  mov     [rsp+arg_18], rbp
0x180016dda  push    rsi
0x180016ddb  push    rdi
0x180016ddc  push    r12
0x180016dde  push    r14
0x180016de0  push    r15
0x180016de2  sub     rsp, 20h
0x180016de6  xor     r12d, r12d
0x180016de9  mov     r14, rdx
0x180016dec  mov     rdi, rcx
0x180016def  test    r8d, r8d
0x180016df2  jz      loc_18001705C
0x180016df8  test    rdx, rdx
0x180016dfb  jz      loc_180017041
0x180016e01  lea     esi, [r12+4]
0x180016e06  cmp     r8d, esi
0x180016e09  jb      loc_18001709B
0x180016e0f  cmp     [rdx], r12d
0x180016e12  jz      loc_180017094
0x180016e18  cmp     dword ptr [rdx], 1Ch
0x180016e1b  jb      loc_18001709B
0x180016e21  cmp     [rdx], r8d
0x180016e24  ja      loc_18001709B
0x180016e2a  mov     r9, rdx
0x180016e2d  mov     ebx, 8007000Dh
0x180016e32  lea     edx, [rsi-3]
0x180016e35  cmp     dword ptr [r9+4], 53505331h
0x180016e3d  jnz     loc_180017052
0x180016e43  mov     rax, [r9+8]
0x180016e47  sub     rax, qword ptr cs:FMTID_UserDefinedProperties.Data1
0x180016e4e  jnz     short loc_180016E5B
0x180016e50  mov     rax, [r9+10h]
0x180016e54  sub     rax, qword ptr cs:FMTID_UserDefinedProperties.Data4
0x180016e5b  mov     ebp, [r9]
0x180016e5e  lea     r10, [r9+18h]
0x180016e62  test    rax, rax
0x180016e65  mov     r15d, r12d
0x180016e68  setz    r15b
0x180016e6c  lea     r11d, [rbp-18h]
0x180016e70  cmp     r11d, esi
0x180016e73  jb      loc_18001704B
0x180016e79  cmp     [r10], r12d
0x180016e7c  jz      loc_180016F40
0x180016e82  cmp     dword ptr [r10], 9
0x180016e86  jb      loc_18001704B
0x180016e8c  mov     eax, r12d
0x180016e8f  cmp     [r10], r11d
0x180016e92  ja      loc_18001704B
0x180016e98  test    eax, eax
0x180016e9a  jnz     short loc_180016ED4
0x180016e9c  test    r15d, r15d
0x180016e9f  jnz     short loc_180016F12
0x180016ea1  mov     eax, [r10]
0x180016ea4  sub     r11d, eax
0x180016ea7  add     r10, rax
0x180016eaa  cmp     r11d, esi
0x180016ead  jb      loc_18001704B
0x180016eb3  cmp     [r10], r12d
0x180016eb6  jz      loc_180016F40
0x180016ebc  cmp     dword ptr [r10], 9
0x180016ec0  jb      loc_18001704B
0x180016ec6  cmp     [r10], r11d
0x180016ec9  ja      loc_18001704B
0x180016ecf  mov     eax, r12d
0x180016ed2  jmp     short loc_180016E98
0x180016ed4  js      short loc_180016EF7
0x180016ed6  sub     r8d, ebp
0x180016ed9  cmp     r8d, esi
0x180016edc  jb      short loc_180016EF5
0x180016ede  add     r9, rbp
0x180016ee1  cmp     [r9], r12d
0x180016ee4  jz      short loc_180016F47
0x180016ee6  cmp     dword ptr [r9], 1Ch
0x180016eea  jb      short loc_180016EF5
0x180016eec  cmp     [r9], r8d
0x180016eef  jbe     loc_180016E35
0x180016ef5  mov     eax, ebx
0x180016ef7  mov     ebx, eax
0x180016ef9  mov     rbp, [rsp+48h+arg_18]
0x180016efe  mov     eax, ebx
0x180016f00  mov     rbx, [rsp+48h+arg_10]
0x180016f05  add     rsp, 20h
0x180016f09  pop     r15
0x180016f0b  pop     r14
0x180016f0d  pop     r12
0x180016f0f  pop     rdi
0x180016f10  pop     rsi
0x180016f11  retn
0x180016f12  cmp     dword ptr [r10+4], 2
0x180016f17  jb      short loc_180016EF9
0x180016f19  mov     eax, [r10]
0x180016f1c  mov     ecx, [r10+4]
0x180016f20  sub     rax, 9
0x180016f24  cmp     rcx, rax
0x180016f27  ja      short loc_180016EF9
0x180016f29  test    [r10+4], dl
0x180016f2d  jnz     short loc_180016EF9
0x180016f2f  shr     rcx, 1
0x180016f32  cmp     [r10+rcx*2+7], r12w
0x180016f38  jz      loc_180016EA1
0x180016f3e  jmp     short loc_180016EF9
0x180016f40  mov     eax, edx
0x180016f42  jmp     loc_180016E98
0x180016f47  mov     eax, edx
0x180016f49  test    eax, eax
0x180016f4b  js      short loc_180016EF7
0x180016f4d  mov     eax, [r14]
0x180016f50  test    eax, eax
0x180016f52  jz      short loc_180016F62
0x180016f54  mov     rcx, r14
0x180016f57  add     rcx, rax
0x180016f5a  add     esi, eax
0x180016f5c  mov     eax, [rcx]
0x180016f5e  test    eax, eax
0x180016f60  jnz     short loc_180016F57
0x180016f62  cmp     esi, 8000000h
0x180016f68  ja      loc_18001703A
0x180016f6e  mov     rbx, r12
0x180016f71  test    esi, esi
0x180016f73  jz      short loc_180016FAE
0x180016f75  mov     ecx, esi; cb
0x180016f77  mov     ebp, esi
0x180016f79  call    cs:__imp_CoTaskMemAlloc
0x180016f7f  mov     rbx, rax
0x180016f82  test    rax, rax
0x180016f85  jz      loc_180017017
0x180016f8b  mov     rcx, rax; void *
0x180016f8e  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180016f93  mov     r8, rax; Size
0x180016f96  xor     edx, edx; Val
0x180016f98  mov     rcx, rbx; void *
0x180016f9b  call    memset_0
0x180016fa0  mov     r8d, ebp; Size
0x180016fa3  mov     rdx, r14; Src
0x180016fa6  mov     rcx, rbx; void *
0x180016fa9  call    memcpy_0
0x180016fae  mov     rcx, [rdi+0E0h]
0x180016fb5  lea     rbp, [rdi+0F8h]
0x180016fbc  test    rcx, rcx
0x180016fbf  jnz     short loc_18001702C
0x180016fc1  mov     rcx, rbp; SRWLock
0x180016fc4  call    cs:__imp_AcquireSRWLockExclusive
0x180016fca  mov     rcx, rdi; this
0x180016fcd  call    ?_DeleteAllPropsFromDPAs@CMemPropStore@@AEAAXXZ; CMemPropStore::_DeleteAllPropsFromDPAs(void)
0x180016fd2  mov     rcx, [rdi+0C8h]; pv
0x180016fd9  call    cs:__imp_CoTaskMemFree
0x180016fdf  mov     rcx, [rdi+0E0h]
0x180016fe6  mov     [rdi+0C8h], rbx
0x180016fed  mov     [rdi+0D4h], esi
0x180016ff3  mov     [rdi+0D0h], esi
0x180016ff9  test    rcx, rcx
0x180016ffc  jnz     short loc_18001701E
0x180016ffe  mov     rcx, rbp; SRWLock
0x180017001  call    cs:__imp_ReleaseSRWLockExclusive
0x180017007  mov     ebx, r12d
0x18001700a  xor     ecx, ecx; pv
0x18001700c  call    cs:__imp_CoTaskMemFree
0x180017012  jmp     loc_180016EF9
0x180017017  mov     ebx, 8007000Eh
0x18001701c  jmp     short loc_18001700A
0x18001701e  mov     rax, [rcx]
0x180017021  mov     rax, [rax+20h]
0x180017025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001702a  jmp     short loc_180017007
0x18001702c  mov     rax, [rcx]
0x18001702f  mov     rax, [rax+18h]
0x180017033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017038  jmp     short loc_180016FCA
0x18001703a  mov     ebx, 8007050Ch
0x18001703f  jmp     short loc_18001700A
0x180017041  mov     ebx, 80004003h
0x180017046  jmp     loc_180016EF9
0x18001704b  mov     eax, ebx
0x18001704d  jmp     loc_180016E98
0x180017052  mov     ebx, 80030104h
0x180017057  jmp     loc_180016EF9
0x18001705c  call    ?_AcquireWriteLock@CMemPropStore@@AEAAXXZ; CMemPropStore::_AcquireWriteLock(void)
0x180017061  mov     rcx, rdi; this
0x180017064  call    ?_DeleteAllPropsFromDPAs@CMemPropStore@@AEAAXXZ; CMemPropStore::_DeleteAllPropsFromDPAs(void)
0x180017069  mov     rcx, [rdi+0C8h]; pv
0x180017070  call    cs:__imp_CoTaskMemFree
0x180017076  mov     rcx, rdi; this
0x180017079  mov     [rdi+0C8h], r12
0x180017080  mov     [rdi+0D0h], r12
0x180017087  call    ?_ReleaseWriteLock@CMemPropStore@@AEAAXXZ; CMemPropStore::_ReleaseWriteLock(void)
0x18001708c  mov     ebx, r12d
0x18001708f  jmp     loc_180016EF9
0x180017094  mov     ebx, 1
0x180017099  jmp     short loc_1800170A0
0x18001709b  mov     ebx, 8007000Dh
0x1800170a0  mov     eax, ebx
0x1800170a2  jmp     loc_180016F49
```
