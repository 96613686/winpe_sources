# _SerialChainGetTimeValidDisallowedAutoUpdateCtl

- ea: `0x18001768c`
- end: `0x1800178d6`
- name: `_SerialChainGetTimeValidDisallowedAutoUpdateCtl`
- size: `586`
- prototype: `__int64 __fastcall(int, int, int, int, int, FILETIME *lpFileTime2)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180015e4c`

## callees

- `0x18001768c`
- `0x180034270`
- `0x18003523c`
- `0x1800352b8`
- `0x180054894`
- `0x1800567b0`
- `0x180056de0`
- `0x18008e370`
- `0x18008e3f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017716`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800177b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017802`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017716`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800177b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017802`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800176bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017743`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001781e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800176bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017743`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001781e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017705`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017796`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800177cc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017876`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017705`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017796`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800177cc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017876`

## pseudocode

```c
__int64 __fastcall SerialChainGetTimeValidDisallowedAutoUpdateCtl(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        FILETIME *lpFileTime2)
{
  unsigned int v6; // edi
  bool v8; // zf
  RTL_SRWLOCK *v11; // r14
  FILETIME *v12; // rsi
  LONG v13; // ebx
  FILETIME v15; // rax
  int v16; // ebx
  __int64 DisallowedAutoUpdateCab; // rax
  void *v18; // r13
  struct _FILETIME *v19; // rdx
  FILETIME FileTime1; // [rsp+40h] [rbp-18h] BYREF
  FILETIME FileTime2; // [rsp+A8h] [rbp+50h] BYREF

  v6 = 0;
  v8 = (*(_BYTE *)(a2 + 68) & 8) == 0;
  FileTime2 = 0;
  if ( !v8 )
    return 0;
  v11 = (RTL_SRWLOCK *)(a1 + 32);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
  v12 = (FILETIME *)(a1 + 52);
  FileTime1 = 0;
  if ( !*(_DWORD *)(a1 + 52) && !*(_DWORD *)(a1 + 56)
    || (unsigned int)I_CryptIsResetBackCurrentFileTime(lpFileTime2, 300, a1 + 52) )
  {
    I_CertGetAutoUpdateLastSyncTime(6, a1 + 52);
  }
  FileTime1 = (FILETIME)(*(_QWORD *)v12 + 10000000LL * *(unsigned int *)(a1 + 96));
  v13 = CompareFileTime(&FileTime1, lpFileTime2);
  LOBYTE(v6) = v13 > 0;
  ReleaseSRWLockExclusive(v11);
  if ( v13 > 0 )
    return 1;
  if ( a5 < 0 )
    return 0;
  AcquireSRWLockExclusive(v11);
  if ( (int)GetOfflineUrlTimeStatus((struct _OFFLINE_URL_TIME_INFO *)(a1 + 60)) >= 0 )
  {
    if ( (unsigned int)GetAutoUpdateLastSyncTime(-2147483646, 6, &FileTime2) )
    {
      FileTime1 = 0;
      if ( (unsigned int)GetAutoUpdateLastSyncTime(-2147483647, 6, &FileTime1) )
      {
        if ( CompareFileTime(&FileTime1, &FileTime2) > 0 )
          FileTime2 = FileTime1;
      }
    }
    if ( CompareFileTime(&FileTime2, (const FILETIME *)(a1 + 52)) > 0 )
      goto LABEL_12;
    v16 = 0;
    ReleaseSRWLockExclusive(v11);
    DisallowedAutoUpdateCab = SerialChainWireRetrieveDisallowedAutoUpdateCab(a3, a4);
    v18 = (void *)DisallowedAutoUpdateCab;
    if ( DisallowedAutoUpdateCab )
    {
      v16 = I_CertCltProtectFunction(
              13,
              6,
              0,
              *(_QWORD *)(*(_QWORD *)(DisallowedAutoUpdateCab + 8) + 8LL),
              **(_DWORD **)(DisallowedAutoUpdateCab + 8),
              0,
              0);
      ICM_Free(v18);
    }
    AcquireSRWLockExclusive(v11);
    if ( !v16 )
    {
      SetOfflineUrlTime((struct _OFFLINE_URL_TIME_INFO *)(a1 + 60), v19);
      goto LABEL_14;
    }
    if ( (unsigned int)GetAutoUpdateLastSyncTime(-2147483646, 6, &FileTime2)
      && (FileTime1 = 0, (unsigned int)GetAutoUpdateLastSyncTime(-2147483647, 6, &FileTime1))
      && CompareFileTime(&FileTime1, &FileTime2) > 0 )
    {
      v15 = FileTime1;
      FileTime2 = FileTime1;
    }
    else
    {
LABEL_12:
      v15 = FileTime2;
    }
    *v12 = v15;
    v6 = 1;
    *(_DWORD *)(a1 + 60) = 0;
  }
LABEL_14:
  ReleaseSRWLockExclusive(v11);
  return v6;
}

```

## disassembly

```asm
0x18001768c  push    rbp
0x18001768e  push    rbx
0x18001768f  push    rsi
0x180017690  push    rdi
0x180017691  push    r12
0x180017693  push    r13
0x180017695  push    r14
0x180017697  push    r15
0x180017699  mov     rbp, rsp
0x18001769c  sub     rsp, 58h
0x1800176a0  xor     edi, edi
0x1800176a2  mov     r12, r9
0x1800176a5  test    byte ptr [rdx+44h], 8
0x1800176a9  mov     r13, r8
0x1800176ac  mov     r15, rcx
0x1800176af  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rdi
0x1800176b3  jnz     short loc_18001772D
0x1800176b5  lea     r14, [rcx+20h]
0x1800176b9  mov     rcx, r14; SRWLock
0x1800176bc  call    cs:__imp_AcquireSRWLockExclusive
0x1800176c2  lea     rsi, [r15+34h]
0x1800176c6  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rdi
0x1800176ca  cmp     [rsi], edi
0x1800176cc  jz      loc_1800177E0
0x1800176d2  mov     rcx, [rbp+lpFileTime2]
0x1800176d6  mov     r8, rsi
0x1800176d9  mov     edx, 12Ch
0x1800176de  call    I_CryptIsResetBackCurrentFileTime
0x1800176e3  test    eax, eax
0x1800176e5  jnz     loc_1800177E9
0x1800176eb  mov     eax, [r15+60h]
0x1800176ef  mov     rdx, [rbp+lpFileTime2]; lpFileTime2
0x1800176f3  imul    rcx, rax, 989680h
0x1800176fa  add     rcx, [rsi]
0x1800176fd  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rcx
0x180017701  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180017705  call    cs:__imp_CompareFileTime
0x18001770b  test    eax, eax
0x18001770d  mov     rcx, r14; SRWLock
0x180017710  mov     ebx, eax
0x180017712  setnle  dil
0x180017716  call    cs:__imp_ReleaseSRWLockExclusive
0x18001771c  test    ebx, ebx
0x18001771e  jle     short loc_180017727
0x180017720  mov     eax, 1
0x180017725  jmp     short loc_18001772F
0x180017727  cmp     [rbp+arg_20], 0
0x18001772b  jge     short loc_180017740
0x18001772d  xor     eax, eax
0x18001772f  add     rsp, 58h
0x180017733  pop     r15
0x180017735  pop     r14
0x180017737  pop     r13
0x180017739  pop     r12
0x18001773b  pop     rdi
0x18001773c  pop     rsi
0x18001773d  pop     rbx
0x18001773e  pop     rbp
0x18001773f  retn
0x180017740  mov     rcx, r14; SRWLock
0x180017743  call    cs:__imp_AcquireSRWLockExclusive
0x180017749  lea     rcx, [r15+3Ch]; struct _OFFLINE_URL_TIME_INFO *
0x18001774d  call    ?GetOfflineUrlTimeStatus@@YAJPEAU_OFFLINE_URL_TIME_INFO@@@Z; GetOfflineUrlTimeStatus(_OFFLINE_URL_TIME_INFO *)
0x180017752  test    eax, eax
0x180017754  js      short loc_1800177B4
0x180017756  mov     ebx, 6
0x18001775b  lea     r8, [rbp+FileTime2]
0x18001775f  mov     edx, ebx
0x180017761  mov     rcx, 0FFFFFFFF80000002h
0x180017768  call    _GetAutoUpdateLastSyncTime
0x18001776d  test    eax, eax
0x18001776f  jz      short loc_18001778F
0x180017771  lea     r8, [rbp+FileTime1]
0x180017775  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x18001777d  mov     edx, ebx
0x18001777f  mov     rcx, 0FFFFFFFF80000001h
0x180017786  call    _GetAutoUpdateLastSyncTime
0x18001778b  test    eax, eax
0x18001778d  jnz     short loc_1800177C4
0x18001778f  mov     rdx, rsi; lpFileTime2
0x180017792  lea     rcx, [rbp+FileTime2]; lpFileTime1
0x180017796  call    cs:__imp_CompareFileTime
0x18001779c  test    eax, eax
0x18001779e  jle     short loc_1800177FD
0x1800177a0  mov     rax, qword ptr [rbp+FileTime2.dwLowDateTime]
0x1800177a4  mov     [rsi], rax
0x1800177a7  mov     edi, 1
0x1800177ac  mov     dword ptr [r15+3Ch], 0
0x1800177b4  mov     rcx, r14; SRWLock
0x1800177b7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800177bd  mov     eax, edi
0x1800177bf  jmp     loc_18001772F
0x1800177c4  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x1800177c8  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800177cc  call    cs:__imp_CompareFileTime
0x1800177d2  test    eax, eax
0x1800177d4  jle     short loc_18001778F
0x1800177d6  mov     rax, qword ptr [rbp+FileTime1.dwLowDateTime]
0x1800177da  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x1800177de  jmp     short loc_18001778F
0x1800177e0  cmp     [rsi+4], edi
0x1800177e3  jnz     loc_1800176D2
0x1800177e9  xor     r8d, r8d
0x1800177ec  mov     rdx, rsi
0x1800177ef  lea     ecx, [r8+6]
0x1800177f3  call    I_CertGetAutoUpdateLastSyncTime
0x1800177f8  jmp     loc_1800176EB
0x1800177fd  mov     rcx, r14; SRWLock
0x180017800  xor     ebx, ebx
0x180017802  call    cs:__imp_ReleaseSRWLockExclusive
0x180017808  mov     rdx, r12
0x18001780b  mov     rcx, r13
0x18001780e  call    _SerialChainWireRetrieveDisallowedAutoUpdateCab
0x180017813  mov     r13, rax
0x180017816  test    rax, rax
0x180017819  jnz     short loc_180017891
0x18001781b  mov     rcx, r14; SRWLock
0x18001781e  call    cs:__imp_AcquireSRWLockExclusive
0x180017824  test    ebx, ebx
0x180017826  jz      loc_1800178C8
0x18001782c  lea     r8, [rbp+FileTime2]
0x180017830  mov     edx, 6
0x180017835  mov     rcx, 0FFFFFFFF80000002h
0x18001783c  call    _GetAutoUpdateLastSyncTime
0x180017841  test    eax, eax
0x180017843  jz      loc_1800177A0
0x180017849  lea     r8, [rbp+FileTime1]
0x18001784d  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x180017855  mov     edx, 6
0x18001785a  mov     rcx, 0FFFFFFFF80000001h
0x180017861  call    _GetAutoUpdateLastSyncTime
0x180017866  test    eax, eax
0x180017868  jz      loc_1800177A0
0x18001786e  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180017872  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180017876  call    cs:__imp_CompareFileTime
0x18001787c  test    eax, eax
0x18001787e  jle     loc_1800177A0
0x180017884  mov     rax, qword ptr [rbp+FileTime1.dwLowDateTime]
0x180017888  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x18001788c  jmp     loc_1800177A4
0x180017891  mov     r9, [rax+8]
0x180017895  xor     r8d, r8d
0x180017898  mov     [rsp+58h+var_28], rbx
0x18001789d  mov     [rsp+58h+var_30], rbx
0x1800178a2  mov     ecx, [r9]
0x1800178a5  lea     edx, [r8+6]
0x1800178a9  mov     r9, [r9+8]
0x1800178ad  mov     [rsp+58h+var_38], ecx
0x1800178b1  lea     ecx, [rdx+7]
0x1800178b4  call    I_CertCltProtectFunction
0x1800178b9  mov     rcx, r13; pv
0x1800178bc  mov     ebx, eax
0x1800178be  call    ?ICM_Free@@YAXPEAX@Z; ICM_Free(void *)
0x1800178c3  jmp     loc_18001781B
0x1800178c8  lea     rcx, [r15+3Ch]; struct _OFFLINE_URL_TIME_INFO *
0x1800178cc  call    ?SetOfflineUrlTime@@YAXPEAU_OFFLINE_URL_TIME_INFO@@PEAU_FILETIME@@@Z; SetOfflineUrlTime(_OFFLINE_URL_TIME_INFO *,_FILETIME *)
0x1800178d1  jmp     loc_1800177B4
```
