# CMemPropStore::_SetPropertyStorageMaybeStealBuffer(tagSERIALIZEDPROPSTORAGE * *,ulong,int)

- ea: `0x1800170b0`
- end: `0x18001739f`
- name: `?_SetPropertyStorageMaybeStealBuffer@CMemPropStore@@AEAAJPEAPEFAUtagSERIALIZEDPROPSTORAGE@@KH@Z`
- size: `751`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, struct tagSERIALIZEDPROPSTORAGE **, unsigned int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180016950`

## callees

- `0x180007f40`
- `0x1800170b0`
- `0x180017770`
- `0x180049b90`
- `0x180049ca0`
- `0x18006fb80`
- `0x18006fb98`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800172f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800172f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800172b0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800172b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800172c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800172f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017368`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800172c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800172f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017368`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017265`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017265`

## pseudocode

```c
__int64 __fastcall CMemPropStore::_SetPropertyStorageMaybeStealBuffer(
        RTL_SRWLOCK *this,
        struct tagSERIALIZEDPROPSTORAGE **a2,
        unsigned int a3,
        int a4)
{
  int v4; // r12d
  unsigned int *v7; // rsi
  unsigned int v8; // ebp
  unsigned int *v9; // rdx
  unsigned int v10; // ebx
  __int64 v11; // rax
  __int64 v12; // r14
  unsigned int *v13; // r10
  unsigned int v14; // r11d
  int v15; // eax
  __int64 v16; // rax
  unsigned __int64 v18; // rcx
  __int64 v19; // rax
  unsigned int *v20; // rcx
  unsigned int *v21; // rax
  size_t v22; // rax
  PVOID Ptr; // rcx
  PVOID v24; // rcx
  int v25; // ebx

  v4 = 0;
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
  v7 = (unsigned int *)*a2;
  if ( !*a2 )
    return (unsigned int)-2147467261;
  v8 = 4;
  if ( a3 < 4 )
    goto LABEL_61;
  v9 = (unsigned int *)*a2;
  if ( *v7 )
  {
    if ( *v7 >= 0x1C && *v7 <= a3 )
    {
      v10 = -2147024883;
      while ( 1 )
      {
        if ( v9[1] != 1397773105 )
          return (unsigned int)-2147286780;
        v11 = *((_QWORD *)v9 + 1) - *(_QWORD *)&FMTID_UserDefinedProperties.Data1;
        if ( !v11 )
          v11 = *((_QWORD *)v9 + 2) - *(_QWORD *)FMTID_UserDefinedProperties.Data4;
        v12 = *v9;
        v13 = v9 + 6;
        v14 = v12 - 24;
        LOBYTE(v4) = v11 == 0;
        if ( (unsigned int)(v12 - 24) < 4 )
          goto LABEL_57;
        if ( !*v13 )
          goto LABEL_35;
        if ( *v13 < 9 || (v15 = 0, *v13 > v14) )
LABEL_57:
          v15 = -2147024883;
        while ( !v15 )
        {
          if ( v4 )
          {
            if ( v13[1] < 2 )
              return v10;
            v18 = v13[1];
            if ( v18 > (unsigned __int64)*v13 - 9 || (v13[1] & 1) != 0 || *(_WORD *)((char *)v13 + 2 * (v18 >> 1) + 7) )
              return v10;
          }
          v16 = *v13;
          v14 -= v16;
          v13 = (unsigned int *)((char *)v13 + v16);
          if ( v14 < 4 )
            goto LABEL_57;
          if ( *v13 )
          {
            if ( *v13 < 9 || *v13 > v14 )
              goto LABEL_57;
            v15 = 0;
          }
          else
          {
LABEL_35:
            v15 = 1;
          }
        }
        v4 = 0;
        if ( v15 < 0 )
          return (unsigned int)v15;
        a3 -= v12;
        if ( a3 < 4 )
          return (unsigned int)-2147024883;
        v9 = (unsigned int *)((char *)v9 + v12);
        if ( !*v9 )
        {
          v15 = 1;
          goto LABEL_37;
        }
        if ( *v9 < 0x1C || *v9 > a3 )
          return (unsigned int)-2147024883;
      }
    }
LABEL_61:
    v25 = -2147024883;
    goto LABEL_62;
  }
  v25 = 1;
LABEL_62:
  v15 = v25;
LABEL_37:
  if ( v15 >= 0 )
  {
    v19 = *v7;
    v20 = v7;
    while ( (_DWORD)v19 )
    {
      v8 += v19;
      v20 = (unsigned int *)((char *)v20 + v19);
      v19 = *v20;
    }
    if ( a4 )
    {
      *a2 = 0;
      v10 = 0;
      goto LABEL_46;
    }
    v7 = 0;
    if ( v8 > 0x8000000 )
    {
      v10 = -2147023604;
    }
    else
    {
      v10 = 0;
      if ( !v8 )
      {
LABEL_46:
        Ptr = this[28].Ptr;
        if ( Ptr )
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 24LL))(Ptr);
        else
          AcquireSRWLockExclusive(this + 31);
        CMemPropStore::_DeleteAllPropsFromDPAs((CMemPropStore *)this);
        CoTaskMemFree(this[25].Ptr);
        v24 = this[28].Ptr;
        this[25].Ptr = v7;
        HIDWORD(this[26].Ptr) = v8;
        LODWORD(this[26].Ptr) = v8;
        if ( v24 )
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)v24 + 32LL))(v24);
        else
          ReleaseSRWLockExclusive(this + 31);
        goto LABEL_50;
      }
      v21 = (unsigned int *)CoTaskMemAlloc(v8);
      v7 = v21;
      if ( v21 )
      {
        v22 = CTCoAllocPolicy::_CoTaskMemSize(v21);
        memset_0(v7, 0, v22);
        memcpy_0(v7, *a2, v8);
        goto LABEL_46;
      }
      v10 = -2147024882;
    }
LABEL_50:
    CoTaskMemFree(0);
    return v10;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800170b0  push    rbx
0x1800170b2  push    rbp
0x1800170b3  push    rsi
0x1800170b4  push    rdi
0x1800170b5  push    r12
0x1800170b7  push    r13
0x1800170b9  push    r14
0x1800170bb  push    r15
0x1800170bd  sub     rsp, 28h
0x1800170c1  xor     r12d, r12d
0x1800170c4  mov     r13d, r9d
0x1800170c7  mov     r15, rdx
0x1800170ca  mov     rdi, rcx
0x1800170cd  test    r8d, r8d
0x1800170d0  jz      loc_180017354
0x1800170d6  mov     rsi, [rdx]
0x1800170d9  test    rsi, rsi
0x1800170dc  jz      loc_180017339
0x1800170e2  lea     ebp, [r12+4]
0x1800170e7  cmp     r8d, ebp
0x1800170ea  jb      loc_180017393
0x1800170f0  mov     rdx, rsi
0x1800170f3  cmp     [rsi], r12d
0x1800170f6  jz      loc_18001738C
0x1800170fc  cmp     dword ptr [rsi], 1Ch
0x1800170ff  jb      loc_180017393
0x180017105  cmp     [rsi], r8d
0x180017108  ja      loc_180017393
0x18001710e  mov     ebx, 8007000Dh
0x180017113  lea     r9d, [r12+1]
0x180017118  cmp     dword ptr [rdx+4], 53505331h
0x18001711f  jnz     loc_18001734A
0x180017125  mov     rax, [rdx+8]
0x180017129  sub     rax, qword ptr cs:FMTID_UserDefinedProperties.Data1
0x180017130  jnz     short loc_18001713D
0x180017132  mov     rax, [rdx+10h]
0x180017136  sub     rax, qword ptr cs:FMTID_UserDefinedProperties.Data4
0x18001713d  mov     r14d, [rdx]
0x180017140  lea     r10, [rdx+18h]
0x180017144  xor     ecx, ecx
0x180017146  test    rax, rax
0x180017149  lea     r11d, [r14-18h]
0x18001714d  setz    r12b
0x180017151  cmp     r11d, ebp
0x180017154  jb      loc_180017343
0x18001715a  cmp     [r10], ecx
0x18001715d  jz      loc_180017220
0x180017163  cmp     dword ptr [r10], 9
0x180017167  jb      loc_180017343
0x18001716d  mov     eax, ecx
0x18001716f  cmp     [r10], r11d
0x180017172  ja      loc_180017343
0x180017178  test    eax, eax
0x18001717a  jnz     short loc_1800171B3
0x18001717c  test    r12d, r12d
0x18001717f  jnz     short loc_1800171EF
0x180017181  mov     eax, [r10]
0x180017184  sub     r11d, eax
0x180017187  add     r10, rax
0x18001718a  cmp     r11d, ebp
0x18001718d  jb      loc_180017343
0x180017193  cmp     [r10], ecx
0x180017196  jz      loc_180017220
0x18001719c  cmp     dword ptr [r10], 9
0x1800171a0  jb      loc_180017343
0x1800171a6  cmp     [r10], r11d
0x1800171a9  ja      loc_180017343
0x1800171af  mov     eax, ecx
0x1800171b1  jmp     short loc_180017178
0x1800171b3  xor     r12d, r12d
0x1800171b6  test    eax, eax
0x1800171b8  js      short loc_1800171DA
0x1800171ba  sub     r8d, r14d
0x1800171bd  cmp     r8d, ebp
0x1800171c0  jb      short loc_1800171D8
0x1800171c2  add     rdx, r14
0x1800171c5  cmp     [rdx], r12d
0x1800171c8  jz      short loc_180017228
0x1800171ca  cmp     dword ptr [rdx], 1Ch
0x1800171cd  jb      short loc_1800171D8
0x1800171cf  cmp     [rdx], r8d
0x1800171d2  jbe     loc_180017118
0x1800171d8  mov     eax, ebx
0x1800171da  mov     ebx, eax
0x1800171dc  mov     eax, ebx
0x1800171de  add     rsp, 28h
0x1800171e2  pop     r15
0x1800171e4  pop     r14
0x1800171e6  pop     r13
0x1800171e8  pop     r12
0x1800171ea  pop     rdi
0x1800171eb  pop     rsi
0x1800171ec  pop     rbp
0x1800171ed  pop     rbx
0x1800171ee  retn
0x1800171ef  cmp     dword ptr [r10+4], 2
0x1800171f4  jb      short loc_1800171DC
0x1800171f6  mov     eax, [r10]
0x1800171f9  mov     ecx, [r10+4]
0x1800171fd  sub     rax, 9
0x180017201  cmp     rcx, rax
0x180017204  ja      short loc_1800171DC
0x180017206  test    [r10+4], r9b
0x18001720a  jnz     short loc_1800171DC
0x18001720c  shr     rcx, 1
0x18001720f  xor     eax, eax
0x180017211  cmp     [r10+rcx*2+7], ax
0x180017217  jnz     short loc_1800171DC
0x180017219  xor     ecx, ecx
0x18001721b  jmp     loc_180017181
0x180017220  mov     eax, r9d
0x180017223  jmp     loc_180017178
0x180017228  mov     eax, r9d
0x18001722b  test    eax, eax
0x18001722d  js      short loc_1800171DA
0x18001722f  mov     eax, [rsi]
0x180017231  mov     rcx, rsi
0x180017234  jmp     short loc_18001723D
0x180017236  add     ebp, eax
0x180017238  add     rcx, rax
0x18001723b  mov     eax, [rcx]
0x18001723d  test    eax, eax
0x18001723f  jnz     short loc_180017236
0x180017241  test    r13d, r13d
0x180017244  jnz     loc_180017319
0x18001724a  mov     rsi, r12
0x18001724d  cmp     ebp, 8000000h
0x180017253  ja      loc_180017332
0x180017259  mov     ebx, r12d
0x18001725c  test    ebp, ebp
0x18001725e  jz      short loc_18001729A
0x180017260  mov     ecx, ebp; cb
0x180017262  mov     r14d, ebp
0x180017265  call    cs:__imp_CoTaskMemAlloc
0x18001726b  mov     rsi, rax
0x18001726e  test    rax, rax
0x180017271  jz      loc_180017304
0x180017277  mov     rcx, rax; void *
0x18001727a  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18001727f  mov     r8, rax; Size
0x180017282  xor     edx, edx; Val
0x180017284  mov     rcx, rsi; void *
0x180017287  call    memset_0
0x18001728c  mov     rdx, [r15]; Src
0x18001728f  mov     r8d, r14d; Size
0x180017292  mov     rcx, rsi; void *
0x180017295  call    memcpy_0
0x18001729a  mov     rcx, [rdi+0E0h]
0x1800172a1  lea     r14, [rdi+0F8h]
0x1800172a8  test    rcx, rcx
0x1800172ab  jnz     short loc_180017324
0x1800172ad  mov     rcx, r14; SRWLock
0x1800172b0  call    cs:__imp_AcquireSRWLockExclusive
0x1800172b6  mov     rcx, rdi; this
0x1800172b9  call    ?_DeleteAllPropsFromDPAs@CMemPropStore@@AEAAXXZ; CMemPropStore::_DeleteAllPropsFromDPAs(void)
0x1800172be  mov     rcx, [rdi+0C8h]; pv
0x1800172c5  call    cs:__imp_CoTaskMemFree
0x1800172cb  mov     rcx, [rdi+0E0h]
0x1800172d2  mov     [rdi+0C8h], rsi
0x1800172d9  mov     rsi, r12
0x1800172dc  mov     [rdi+0D4h], ebp
0x1800172e2  mov     [rdi+0D0h], ebp
0x1800172e8  test    rcx, rcx
0x1800172eb  jnz     short loc_18001730B
0x1800172ed  mov     rcx, r14; SRWLock
0x1800172f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800172f6  mov     rcx, rsi; pv
0x1800172f9  call    cs:__imp_CoTaskMemFree
0x1800172ff  jmp     loc_1800171DC
0x180017304  mov     ebx, 8007000Eh
0x180017309  jmp     short loc_1800172F6
0x18001730b  mov     rax, [rcx]
0x18001730e  mov     rax, [rax+20h]
0x180017312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017317  jmp     short loc_1800172F6
0x180017319  mov     [r15], r12
0x18001731c  mov     ebx, r12d
0x18001731f  jmp     loc_18001729A
0x180017324  mov     rax, [rcx]
0x180017327  mov     rax, [rax+18h]
0x18001732b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017330  jmp     short loc_1800172B6
0x180017332  mov     ebx, 8007050Ch
0x180017337  jmp     short loc_1800172F6
0x180017339  mov     ebx, 80004003h
0x18001733e  jmp     loc_1800171DC
0x180017343  mov     eax, ebx
0x180017345  jmp     loc_180017178
0x18001734a  mov     ebx, 80030104h
0x18001734f  jmp     loc_1800171DC
0x180017354  call    ?_AcquireWriteLock@CMemPropStore@@AEAAXXZ; CMemPropStore::_AcquireWriteLock(void)
0x180017359  mov     rcx, rdi; this
0x18001735c  call    ?_DeleteAllPropsFromDPAs@CMemPropStore@@AEAAXXZ; CMemPropStore::_DeleteAllPropsFromDPAs(void)
0x180017361  mov     rcx, [rdi+0C8h]; pv
0x180017368  call    cs:__imp_CoTaskMemFree
0x18001736e  mov     rcx, rdi; this
0x180017371  mov     [rdi+0C8h], r12
0x180017378  mov     [rdi+0D0h], r12
0x18001737f  call    ?_ReleaseWriteLock@CMemPropStore@@AEAAXXZ; CMemPropStore::_ReleaseWriteLock(void)
0x180017384  mov     ebx, r12d
0x180017387  jmp     loc_1800171DC
0x18001738c  mov     ebx, 1
0x180017391  jmp     short loc_180017398
0x180017393  mov     ebx, 8007000Dh
0x180017398  mov     eax, ebx
0x18001739a  jmp     loc_18001722B
```
