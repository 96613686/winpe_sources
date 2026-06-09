# __delayLoadHelper2

- ea: `0x1800056d0`
- end: `0x180005cf9`
- name: `__delayLoadHelper2`
- size: `1577`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b8e7`
- `0x18000b972`
- `0x18000ba21`
- `0x18000bb06`
- `0x18000bbd9`
- `0x18000bcd0`

## callees

- `0x180005590`
- `0x1800056d0`
- `0x180005d00`
- `0x180005dd0`
- `0x180041980`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180005a01`
- `KERNEL32!GetProcAddress` at `0x180005a01`
- `KERNEL32!FreeLibrary` at `0x180005beb`
- `KERNEL32!FreeLibrary` at `0x180005beb`
- `KERNEL32!GetLastError` at `0x180005acf`
- `KERNEL32!GetLastError` at `0x180005c5b`
- `KERNEL32!GetLastError` at `0x180005acf`
- `KERNEL32!GetLastError` at `0x180005c5b`
- `KERNEL32!VirtualProtect` at `0x1800057d7`
- `KERNEL32!VirtualProtect` at `0x1800059a7`
- `KERNEL32!VirtualProtect` at `0x1800057d7`
- `KERNEL32!VirtualProtect` at `0x1800059a7`
- `KERNEL32!RaiseException` at `0x180005b06`
- `KERNEL32!RaiseException` at `0x180005b33`
- `KERNEL32!RaiseException` at `0x180005ca8`
- `KERNEL32!RaiseException` at `0x180005b06`
- `KERNEL32!RaiseException` at `0x180005b33`
- `KERNEL32!RaiseException` at `0x180005ca8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800057ec`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800059bc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800057ec`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800059bc`
- `KERNEL32!LoadLibraryExA` at `0x180005a49`
- `KERNEL32!LoadLibraryExA` at `0x180005a49`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000571e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800058f5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000571e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800058f5`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(int *a1, CHAR *a2)
{
  __int64 v4; // r8
  unsigned int v5; // r10d
  int *v6; // rcx
  unsigned int i; // r8d
  __int64 v8; // rdx
  SIZE_T v9; // r9
  char *v10; // rdi
  SIZE_T v11; // r14
  __int64 v12; // rcx
  FARPROC ProcAddress; // rdi
  volatile signed __int64 *v14; // r14
  __int64 v15; // r9
  char *v16; // r12
  int v17; // eax
  HMODULE Library; // r15
  __int64 v19; // r13
  __int64 v20; // rax
  __int64 v21; // rdx
  PfnDliHook v22; // r8
  __int64 v23; // r8
  unsigned int v24; // r8d
  int *v25; // rdx
  unsigned int j; // r10d
  __int64 v27; // rax
  SIZE_T v28; // r9
  char *v29; // rbx
  DWORD v30; // r14d
  SIZE_T v31; // rsi
  signed __int64 v33; // r14
  bool v34; // sf
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int128 v45; // [rsp+20h] [rbp-58h] BYREF
  LPCSTR lpLibFileName[2]; // [rsp+30h] [rbp-48h]
  LPCSTR lpProcName[2]; // [rsp+40h] [rbp-38h]
  __int128 v48; // [rsp+50h] [rbp-28h]
  DWORD LastError; // [rsp+60h] [rbp-18h]
  __int128 *flOldProtect; // [rsp+B0h] [rbp+38h] BYREF

  LastError = 0;
  v45 = 0;
  *(_OWORD *)lpLibFileName = 0;
  *(_OWORD *)lpProcName = 0;
  v48 = 0;
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( ++DloadSectionLockCount == 1 )
  {
    if ( *(_DWORD *)&byte_180000040[(int)off_18000003C + 68] > 0xDu )
    {
      v4 = *(unsigned int *)&byte_180000040[(int)off_18000003C + 176];
      if ( (_DWORD)v4 )
      {
        v5 = *(_DWORD *)((char *)&word_18000000C + v4);
        v6 = (int *)((char *)&_ImageBase
                   + (int)off_18000003C
                   + *(unsigned __int16 *)((char *)&word_180000014 + (int)off_18000003C)
                   + 24);
        for ( i = 0; i < *(unsigned __int16 *)((char *)&word_180000006 + (int)off_18000003C); ++i )
        {
          v8 = (unsigned int)v6[3];
          if ( v5 >= (unsigned int)v8 )
          {
            v9 = (unsigned int)v6[2];
            if ( v5 < (int)v9 + (int)v8 )
            {
              v10 = (char *)&_ImageBase + v8;
              if ( !(__int16 *)((char *)&_ImageBase + v8) )
                break;
              if ( DloadSectionCommitPermanent )
              {
                v11 = (unsigned int)v6[2];
              }
              else
              {
                v34 = v6[9] < 0;
                DloadSectionCommitPermanent = 1;
                if ( !v34 )
                  __fastfail(0x19u);
                v11 = v9;
                DloadMakePermanentImageCommit(v10, v9);
              }
              if ( !VirtualProtect(v10, v11, 4u, &DloadSectionOldProtection) )
                __fastfail(0x19u);
              goto LABEL_13;
            }
          }
          v6 += 10;
        }
      }
    }
    DloadSectionOldProtection = 4;
  }
LABEL_13:
  ReleaseSRWLockExclusive(&DloadSrwLock);
  ProcAddress = 0;
  v14 = (volatile signed __int64 *)((char *)&_ImageBase + (unsigned int)a1[2]);
  v15 = (unsigned int)a1[7];
  v16 = (char *)&_ImageBase + (unsigned int)a1[5];
  lpLibFileName[1] = (char *)&_ImageBase + (unsigned int)a1[1];
  v17 = *a1;
  LODWORD(flOldProtect) = v15;
  LODWORD(v45) = 72;
  *((_QWORD *)&v45 + 1) = a1;
  lpLibFileName[0] = a2;
  LODWORD(lpProcName[0]) = 0;
  lpProcName[1] = 0;
  v48 = 0u;
  LastError = 0;
  if ( (v17 & 1) == 0 )
  {
    flOldProtect = &v45;
    DloadReleaseSectionWriteAccess(v12, &_ImageBase);
    RaiseException(0xC06D0057, 0, 1u, (const ULONG_PTR *)&flOldProtect);
    return 0;
  }
  Library = (HMODULE)*v14;
  v19 = 8LL * (unsigned int)((&a2[-a1[3]] - (CHAR *)&_ImageBase) >> 3);
  v20 = v19 + (unsigned int)a1[4];
  LODWORD(lpProcName[0]) = *(_QWORD *)((char *)&_ImageBase + v20) >= 0LL;
  v21 = *(unsigned int *)((char *)&_ImageBase + v20);
  if ( LODWORD(lpProcName[0]) )
    lpProcName[1] = (char *)&word_180000002 + v21;
  else
    LODWORD(lpProcName[1]) = (unsigned __int16)v21;
  v22 = _pfnDliNotifyHook2;
  if ( !_pfnDliNotifyHook2 )
    goto LABEL_17;
  v37 = ((__int64 (__fastcall *)(_QWORD, __int128 *))_pfnDliNotifyHook2)(0, &v45);
  v22 = _pfnDliNotifyHook2;
  ProcAddress = (FARPROC)v37;
  if ( !v37 )
  {
    v15 = (unsigned int)flOldProtect;
LABEL_17:
    if ( !Library )
    {
      if ( !v22
        || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, __int128 *, PfnDliHook, __int64))v22)(
                                 1,
                                 &v45,
                                 v22,
                                 v15)) == 0 )
      {
        Library = LoadLibraryExA(lpLibFileName[1], 0, 0);
        if ( !Library )
        {
          LastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, &v45)) == 0 )
          {
            flOldProtect = &v45;
            DloadReleaseSectionWriteAccess(v36, v35);
            RaiseException(0xC06D007E, 0, 1u, (const ULONG_PTR *)&flOldProtect);
            return (FARPROC)*((_QWORD *)&v48 + 1);
          }
        }
      }
      v33 = _InterlockedCompareExchange64(v14, (signed __int64)Library, 0);
      if ( v33 )
      {
        if ( Library != (HMODULE)-1LL )
          FreeLibrary(Library);
        if ( Library != (HMODULE)v33 )
          Library = (HMODULE)v33;
      }
      else if ( Library != (HMODULE)-1LL && a1[6] )
      {
        NewUnloadInfo(a1);
      }
      v22 = _pfnDliNotifyHook2;
      v15 = (unsigned int)flOldProtect;
    }
    *(_QWORD *)&v48 = Library;
    if ( v22 )
    {
      v38 = ((__int64 (__fastcall *)(__int64, __int128 *, PfnDliHook, __int64))v22)(2, &v45, v22, v15);
      v22 = _pfnDliNotifyHook2;
      ProcAddress = (FARPROC)v38;
      v15 = (unsigned int)flOldProtect;
    }
    if ( !ProcAddress )
    {
      if ( !a1[5]
        || !a1[7]
        || (v39 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v39) != 17744)
        || *(_DWORD *)((char *)Library + v39 + 8) != (_DWORD)v15
        || Library != *(HMODULE *)((char *)Library + v39 + 48)
        || (ProcAddress = *(FARPROC *)&v16[v19]) == 0 )
      {
        ProcAddress = GetProcAddress(Library, lpProcName[1]);
        if ( !ProcAddress )
        {
          LastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (ProcAddress = (FARPROC)_pfnDefaultDliFailureHook2(4, &v45)) == 0 )
          {
            flOldProtect = &v45;
            DloadReleaseSectionWriteAccess(v41, v40);
            RaiseException(0xC06D007F, 0, 1u, (const ULONG_PTR *)&flOldProtect);
            DloadAcquireSectionWriteAccess(v43, v42, v44);
            ProcAddress = (FARPROC)*((_QWORD *)&v48 + 1);
          }
        }
        v22 = _pfnDliNotifyHook2;
      }
    }
    *(_QWORD *)a2 = ProcAddress;
  }
  if ( v22 )
  {
    LastError = 0;
    *(_QWORD *)&v48 = Library;
    *((_QWORD *)&v48 + 1) = ProcAddress;
    ((void (__fastcall *)(__int64, __int128 *, PfnDliHook, __int64))v22)(5, &v45, v22, v15);
  }
  LODWORD(flOldProtect) = 0;
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( !--DloadSectionLockCount )
  {
    if ( *(_DWORD *)&byte_180000040[(int)off_18000003C + 68] > 0xDu )
    {
      v23 = *(unsigned int *)&byte_180000040[(int)off_18000003C + 176];
      if ( (_DWORD)v23 )
      {
        v24 = *(_DWORD *)((char *)&word_18000000C + v23);
        v25 = (int *)((char *)&_ImageBase
                    + (int)off_18000003C
                    + *(unsigned __int16 *)((char *)&word_180000014 + (int)off_18000003C)
                    + 24);
        for ( j = 0; j < *(unsigned __int16 *)((char *)&word_180000006 + (int)off_18000003C); ++j )
        {
          v27 = (unsigned int)v25[3];
          if ( v24 >= (unsigned int)v27 )
          {
            v28 = (unsigned int)v25[2];
            if ( v24 < (int)v28 + (int)v27 )
            {
              v29 = (char *)&_ImageBase + v27;
              if ( !(__int16 *)((char *)&_ImageBase + v27) )
                break;
              v30 = DloadSectionOldProtection;
              if ( DloadSectionCommitPermanent )
              {
                v31 = (unsigned int)v25[2];
              }
              else
              {
                v34 = v25[9] < 0;
                DloadSectionCommitPermanent = 1;
                if ( !v34 )
                  __fastfail(0x19u);
                v31 = v28;
                DloadMakePermanentImageCommit((char *)&_ImageBase + v27, v28);
              }
              if ( !VirtualProtect(v29, v31, v30, (PDWORD)&flOldProtect) )
                __fastfail(0x19u);
              goto LABEL_36;
            }
          }
          v25 += 10;
        }
      }
    }
    LODWORD(flOldProtect) = 4;
  }
LABEL_36:
  ReleaseSRWLockExclusive(&DloadSrwLock);
  return ProcAddress;
}

```

## disassembly

```asm
0x1800056d0  push    rbp
0x1800056d2  push    rbx
0x1800056d3  push    rsi
0x1800056d4  push    rdi
0x1800056d5  push    r12
0x1800056d7  push    r14
0x1800056d9  mov     rbp, rsp
0x1800056dc  sub     rsp, 78h
0x1800056e0  xorps   xmm0, xmm0
0x1800056e3  xor     eax, eax
0x1800056e5  xor     edi, edi
0x1800056e7  mov     [rbp+var_18], eax
0x1800056ea  test    cs:dword_1800463D0, 1000h
0x1800056f4  mov     rsi, rdx
0x1800056f7  mov     rbx, rcx
0x1800056fa  lea     rdx, __ImageBase
0x180005701  movups  [rbp+var_58], xmm0
0x180005705  movups  xmmword ptr [rbp+lpLibFileName], xmm0
0x180005709  movups  xmmword ptr [rbp+lpProcName], xmm0
0x18000570d  movups  [rbp+var_28], xmm0
0x180005711  jz      loc_1800057FB
0x180005717  lea     rcx, DloadSrwLock; SRWLock
0x18000571e  call    cs:__imp_AcquireSRWLockExclusive
0x180005724  mov     eax, cs:DloadSectionLockCount
0x18000572a  inc     eax
0x18000572c  mov     cs:DloadSectionLockCount, eax
0x180005732  cmp     eax, 1
0x180005735  jnz     loc_1800057E5
0x18000573b  movsxd  rdx, cs:off_18000003C
0x180005742  lea     r14, __ImageBase
0x180005749  add     rdx, r14
0x18000574c  cmp     dword ptr [rdx+84h], 0Dh
0x180005753  jbe     loc_180005A28
0x180005759  mov     r8d, [rdx+0F0h]
0x180005760  test    r8d, r8d
0x180005763  jz      loc_180005A28
0x180005769  movzx   ecx, word ptr [rdx+14h]
0x18000576d  mov     r10d, [r8+r14+0Ch]
0x180005772  add     rcx, 18h
0x180005776  movzx   r11d, word ptr [rdx+6]
0x18000577b  add     rcx, rdx
0x18000577e  mov     r8d, edi
0x180005781  cmp     r8d, r11d
0x180005784  jnb     loc_180005A28
0x18000578a  mov     edx, [rcx+0Ch]
0x18000578d  cmp     r10d, edx
0x180005790  jb      short loc_18000579F
0x180005792  mov     r9d, [rcx+8]
0x180005796  lea     eax, [r9+rdx]
0x18000579a  cmp     r10d, eax
0x18000579d  jb      short loc_1800057A8
0x18000579f  inc     r8d
0x1800057a2  add     rcx, 28h ; '('
0x1800057a6  jmp     short loc_180005781
0x1800057a8  mov     rdi, rdx
0x1800057ab  add     rdi, r14
0x1800057ae  jz      loc_180005A28
0x1800057b4  cmp     cs:DloadSectionCommitPermanent, 0
0x1800057bb  jz      loc_180005AA8
0x1800057c1  mov     r14, r9
0x1800057c4  lea     r9, DloadSectionOldProtection; lpflOldProtect
0x1800057cb  mov     r8d, 4; flNewProtect
0x1800057d1  mov     rdx, r14; dwSize
0x1800057d4  mov     rcx, rdi; lpAddress
0x1800057d7  call    cs:__imp_VirtualProtect
0x1800057dd  test    eax, eax
0x1800057df  jz      loc_180005B95
0x1800057e5  lea     rcx, DloadSrwLock; SRWLock
0x1800057ec  call    cs:__imp_ReleaseSRWLockExclusive
0x1800057f2  xor     edi, edi
0x1800057f4  lea     rdx, __ImageBase
0x1800057fb  mov     eax, [rbx+4]
0x1800057fe  mov     r14d, [rbx+8]
0x180005802  add     rax, rdx
0x180005805  mov     r12d, [rbx+14h]
0x180005809  add     r14, rdx
0x18000580c  mov     r9d, [rbx+1Ch]
0x180005810  add     r12, rdx
0x180005813  mov     [rbp+lpLibFileName+8], rax
0x180005817  mov     eax, [rbx]
0x180005819  mov     dword ptr [rbp+flOldProtect], r9d
0x18000581d  mov     dword ptr [rbp+var_58], 48h ; 'H'
0x180005824  mov     qword ptr [rbp+var_58+8], rbx
0x180005828  mov     [rbp+lpLibFileName], rsi
0x18000582c  mov     dword ptr [rbp+lpProcName], edi
0x18000582f  mov     [rbp+lpProcName+8], rdi
0x180005833  mov     qword ptr [rbp+var_28], rdi
0x180005837  mov     qword ptr [rbp+var_28+8], rdi
0x18000583b  mov     [rbp+var_18], edi
0x18000583e  test    al, 1
0x180005840  jz      loc_180005B15
0x180005846  mov     eax, [rbx+0Ch]
0x180005849  mov     rcx, rsi
0x18000584c  sub     rcx, rax
0x18000584f  mov     [rsp+78h+arg_10], r13
0x180005857  sub     rcx, rdx
0x18000585a  mov     [rsp+78h+var_8], r15
0x18000585f  mov     r15, [r14]
0x180005862  sar     rcx, 3
0x180005866  mov     eax, ecx
0x180005868  mov     ecx, edi
0x18000586a  lea     r13, ds:0[rax*8]
0x180005872  mov     eax, [rbx+10h]
0x180005875  add     rax, r13
0x180005878  cmp     qword ptr [rax+rdx], 0
0x18000587d  setnl   cl
0x180005880  mov     dword ptr [rbp+lpProcName], ecx
0x180005883  mov     edx, [rax+rdx]
0x180005886  test    ecx, ecx
0x180005888  jz      loc_1800059DF
0x18000588e  lea     rax, word_180000002
0x180005895  add     rax, rdx
0x180005898  mov     [rbp+lpProcName+8], rax
0x18000589c  mov     r8, cs:__pfnDliNotifyHook2
0x1800058a3  test    r8, r8
0x1800058a6  jnz     loc_180005B5F
0x1800058ac  test    r15, r15
0x1800058af  jz      loc_180005A37
0x1800058b5  mov     qword ptr [rbp+var_28], r15
0x1800058b9  test    r8, r8
0x1800058bc  jnz     loc_180005BFD
0x1800058c2  test    rdi, rdi
0x1800058c5  jz      loc_1800059EA
0x1800058cb  mov     [rsi], rdi
0x1800058ce  test    r8, r8
0x1800058d1  jnz     loc_180005CBC
0x1800058d7  test    cs:dword_1800463D0, 1000h
0x1800058e1  mov     dword ptr [rbp+flOldProtect], 0
0x1800058e8  jz      loc_1800059C2
0x1800058ee  lea     rcx, DloadSrwLock; SRWLock
0x1800058f5  call    cs:__imp_AcquireSRWLockExclusive
0x1800058fb  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180005902  jnz     loc_1800059B5
0x180005908  movsxd  rcx, cs:off_18000003C
0x18000590f  lea     r14, __ImageBase
0x180005916  add     rcx, r14
0x180005919  cmp     dword ptr [rcx+84h], 0Dh
0x180005920  jbe     loc_180005A1F
0x180005926  mov     r8d, [rcx+0F0h]
0x18000592d  test    r8d, r8d
0x180005930  jz      loc_180005A1F
0x180005936  movzx   edx, word ptr [rcx+14h]
0x18000593a  mov     r8d, [r8+r14+0Ch]
0x18000593f  add     rdx, 18h
0x180005943  movzx   r11d, word ptr [rcx+6]
0x180005948  add     rdx, rcx
0x18000594b  xor     r10d, r10d
0x18000594e  xchg    ax, ax
0x180005950  cmp     r10d, r11d
0x180005953  jnb     loc_180005A1F
0x180005959  mov     eax, [rdx+0Ch]
0x18000595c  cmp     r8d, eax
0x18000595f  jb      short loc_18000596E
0x180005961  mov     r9d, [rdx+8]
0x180005965  lea     ecx, [r9+rax]
0x180005969  cmp     r8d, ecx
0x18000596c  jb      short loc_180005977
0x18000596e  inc     r10d
0x180005971  add     rdx, 28h ; '('
0x180005975  jmp     short loc_180005950
0x180005977  mov     rbx, rax
0x18000597a  add     rbx, r14
0x18000597d  jz      loc_180005A1F
0x180005983  cmp     cs:DloadSectionCommitPermanent, 0
0x18000598a  mov     r14d, cs:DloadSectionOldProtection
0x180005991  jz      loc_180005A81
0x180005997  mov     rsi, r9
0x18000599a  lea     r9, [rbp+flOldProtect]; lpflOldProtect
0x18000599e  mov     r8d, r14d; flNewProtect
0x1800059a1  mov     rdx, rsi; dwSize
0x1800059a4  mov     rcx, rbx; lpAddress
0x1800059a7  call    cs:__imp_VirtualProtect
0x1800059ad  test    eax, eax
0x1800059af  jz      loc_180005CED
0x1800059b5  lea     rcx, DloadSrwLock; SRWLock
0x1800059bc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800059c2  mov     rax, rdi
0x1800059c5  mov     r13, [rsp+78h+arg_10]
0x1800059cd  mov     r15, [rsp+78h+var_8]
0x1800059d2  add     rsp, 78h
0x1800059d6  pop     r14
0x1800059d8  pop     r12
0x1800059da  pop     rdi
0x1800059db  pop     rsi
0x1800059dc  pop     rbx
0x1800059dd  pop     rbp
0x1800059de  retn
0x1800059df  movzx   eax, dx
0x1800059e2  mov     dword ptr [rbp+lpProcName+8], eax
0x1800059e5  jmp     loc_18000589C
0x1800059ea  cmp     dword ptr [rbx+14h], 0
0x1800059ee  jz      short loc_1800059FA
0x1800059f0  cmp     dword ptr [rbx+1Ch], 0
0x1800059f4  jnz     loc_180005C21
0x1800059fa  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x1800059fe  mov     rcx, r15; hModule
0x180005a01  call    cs:__imp_GetProcAddress
0x180005a07  mov     rdi, rax
0x180005a0a  test    rax, rax
0x180005a0d  jz      loc_180005C5B
0x180005a13  mov     r8, cs:__pfnDliNotifyHook2
0x180005a1a  jmp     loc_1800058CB
0x180005a1f  mov     dword ptr [rbp+flOldProtect], 4
0x180005a26  jmp     short loc_1800059B5
0x180005a28  mov     cs:DloadSectionOldProtection, 4
0x180005a32  jmp     loc_1800057E5
0x180005a37  test    r8, r8
0x180005a3a  jnz     loc_180005BA1
0x180005a40  mov     rcx, [rbp+lpLibFileName+8]; lpLibFileName
0x180005a44  xor     r8d, r8d; dwFlags
0x180005a47  xor     edx, edx; hFile
0x180005a49  call    cs:__imp_LoadLibraryExA
0x180005a4f  mov     r15, rax
0x180005a52  test    rax, rax
0x180005a55  jz      short loc_180005ACF
0x180005a57  xor     eax, eax
0x180005a59  lock cmpxchg [r14], r15
0x180005a5e  mov     r14, rax
0x180005a61  jnz     loc_180005BE2
0x180005a67  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180005a6b  jnz     loc_180005B48
0x180005a71  mov     r8, cs:__pfnDliNotifyHook2
0x180005a78  mov     r9d, dword ptr [rbp+flOldProtect]
0x180005a7c  jmp     loc_1800058B5
0x180005a81  cmp     dword ptr [rdx+24h], 0
0x180005a85  mov     cs:DloadSectionCommitPermanent, 1
0x180005a8f  jge     loc_180005CE1
0x180005a95  mov     rdx, r9
0x180005a98  mov     rcx, rbx
0x180005a9b  mov     rsi, r9
0x180005a9e  call    DloadMakePermanentImageCommit
0x180005aa3  jmp     loc_18000599A
0x180005aa8  cmp     dword ptr [rcx+24h], 0
0x180005aac  mov     cs:DloadSectionCommitPermanent, 1
0x180005ab6  jge     loc_180005B89
0x180005abc  mov     rdx, r9
0x180005abf  mov     rcx, rdi
0x180005ac2  mov     r14, r9
0x180005ac5  call    DloadMakePermanentImageCommit
0x180005aca  jmp     loc_1800057C4
0x180005acf  call    cs:__imp_GetLastError
0x180005ad5  mov     [rbp+var_18], eax
0x180005ad8  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180005adf  test    rax, rax
0x180005ae2  jnz     loc_180005BC3
0x180005ae8  lea     rax, [rbp+var_58]
0x180005aec  mov     [rbp+flOldProtect], rax
0x180005af0  call    DloadReleaseSectionWriteAccess
0x180005af5  lea     r9, [rbp+flOldProtect]; lpArguments
0x180005af9  xor     edx, edx; dwExceptionFlags
0x180005afb  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180005b00  mov     r8d, 1; nNumberOfArguments
0x180005b06  call    cs:__imp_RaiseException
0x180005b0c  mov     rax, qword ptr [rbp+var_28+8]
0x180005b10  jmp     loc_1800059C5
0x180005b15  lea     rax, [rbp+var_58]
0x180005b19  mov     [rbp+flOldProtect], rax
0x180005b1d  call    DloadReleaseSectionWriteAccess
0x180005b22  lea     r9, [rbp+flOldProtect]; lpArguments
0x180005b26  xor     edx, edx; dwExceptionFlags
0x180005b28  mov     ecx, 0C06D0057h; dwExceptionCode
0x180005b2d  mov     r8d, 1; nNumberOfArguments
0x180005b33  call    cs:__imp_RaiseException
0x180005b39  xor     eax, eax
0x180005b3b  add     rsp, 78h
0x180005b3f  pop     r14
0x180005b41  pop     r12
0x180005b43  pop     rdi
0x180005b44  pop     rsi
0x180005b45  pop     rbx
0x180005b46  pop     rbp
0x180005b47  retn
0x180005b48  cmp     dword ptr [rbx+18h], 0
0x180005b4c  jz      loc_180005A71
0x180005b52  mov     rcx, rbx
0x180005b55  call    NewUnloadInfo
0x180005b5a  jmp     loc_180005A71
0x180005b5f  lea     rdx, [rbp+var_58]
0x180005b63  xor     ecx, ecx
0x180005b65  mov     rax, r8
0x180005b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b6d  mov     r8, cs:__pfnDliNotifyHook2
0x180005b74  mov     rdi, rax
0x180005b77  test    rax, rax
0x180005b7a  jnz     loc_1800058CE
0x180005b80  mov     r9d, dword ptr [rbp+flOldProtect]
0x180005b84  jmp     loc_1800058AC
0x180005b89  mov     ecx, 19h
0x180005b8e  int     29h; Win8: RtlFailFast(ecx)
0x180005b90  jmp     loc_180005ABC
0x180005b95  mov     ecx, 19h
0x180005b9a  int     29h; Win8: RtlFailFast(ecx)
0x180005b9c  jmp     loc_1800057E5
0x180005ba1  lea     rdx, [rbp+var_58]
0x180005ba5  mov     ecx, 1
0x180005baa  mov     rax, r8
0x180005bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb2  mov     r15, rax
0x180005bb5  test    rax, rax
0x180005bb8  jnz     loc_180005A57
  ... truncated ...
```
