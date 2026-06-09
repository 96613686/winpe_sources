# NfsCreateShareCore

- ea: `0x18002d45c`
- end: `0x18002d6a1`
- name: `NfsCreateShareCore`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callers

- `0x18001d798`

## callees

- `0x180001d4a`
- `0x180027510`
- `0x18002bfe0`
- `0x18002c288`
- `0x18002c97c`
- `0x18002d2b4`
- `0x18002d45c`
- `0x18002db34`
- `0x180035b40`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002d664`
- `KERNEL32!HeapFree` at `0x18002d664`
- `KERNEL32!GetLastError` at `0x18002d577`
- `KERNEL32!GetLastError` at `0x18002d577`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002d5f3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002d5f3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002d58e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002d58e`
- `KERNEL32!GetProcessHeap` at `0x18002d656`
- `KERNEL32!GetProcessHeap` at `0x18002d656`
- `KERNEL32!GetFileAttributesW` at `0x18002d4a3`
- `KERNEL32!GetFileAttributesW` at `0x18002d4a3`
- `KERNEL32!InitOnceExecuteOnce` at `0x18002d56d`
- `KERNEL32!InitOnceExecuteOnce` at `0x18002d56d`
- `KERNEL32!GetDriveTypeW` at `0x18002d4f5`
- `KERNEL32!GetDriveTypeW` at `0x18002d4f5`

## pseudocode

```c
__int64 __fastcall NfsCreateShareCore(__int64 a1, __int64 a2, int *a3)
{
  const wchar_t *v3; // r14
  DWORD LastError; // ebx
  int v7; // esi
  wchar_t *v8; // rax
  int v9; // eax
  bool v10; // zf
  __int16 v11; // ax
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  __int64 v15; // r12
  DWORD PFsPersistentPath; // eax
  void *v17; // r14
  DWORD v18; // eax
  HANDLE ProcessHeap; // rax
  int v21; // [rsp+30h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-38h] BYREF
  __int128 v23; // [rsp+40h] [rbp-30h]
  int *v24; // [rsp+50h] [rbp-20h]
  WCHAR RootPathName; // [rsp+58h] [rbp-18h] BYREF

  v24 = a3;
  v3 = (const wchar_t *)(a1 + 32);
  lpMem = 0;
  v21 = 0;
  LastError = 0;
  v7 = 0;
  if ( GetFileAttributesW((LPCWSTR)(a1 + 32)) == -1 )
  {
    v7 = -2147483639;
LABEL_28:
    *v24 = v7;
    return LastError;
  }
  v8 = wcschr_0(v3, 0x5Cu);
  if ( !v8 || (int)StringCchCopyNW(&RootPathName, 4u, v3, v8 - v3 + 1) < 0 )
    return 87;
  if ( GetDriveTypeW(&RootPathName) == 4 )
  {
    v7 = -2147483641;
    goto LABEL_28;
  }
  if ( (int)NormalizeSharePath(v3) < 0 )
    return 87;
  DWORD1(v23) = *(_DWORD *)(a1 + 4);
  v9 = *(_DWORD *)a1 & 0x3C1F200;
  HIWORD(v23) = 0;
  v10 = (*(_DWORD *)a1 & 0x1000000) == 0;
  LODWORD(v23) = v9 | 0xC00;
  DWORD2(v23) = *(_DWORD *)(a1 + 8);
  if ( v10 )
    v11 = 90;
  else
    v11 = *(_WORD *)(a1 + 12);
  WORD6(v23) = v11;
  *(_OWORD *)a1 = v23;
  if ( !InitOnceExecuteOnce(&g_InitOnce, InitShareCreateMutexCallbackFn, 0, 0) )
    LastError = GetLastError();
  if ( !LastError )
  {
    AcquireSRWLockExclusive(&g_shareCreateMutex);
    v10 = (*(_DWORD *)a1 & 0x800000) == 0;
    v13 = a1 + 1656;
    *(_DWORD *)(a1 + 1656) = 0;
    *(_QWORD *)(a1 + 1664) = 0;
    v14 = a1 + 556;
    if ( v10 )
    {
      PFsPersistentPath = NfsCreatePFsPersistentPath(v14, 0, v12, v13, (__int64)&lpMem);
      v15 = a1 + 1620;
    }
    else
    {
      v15 = a1 + 1620;
      PFsPersistentPath = NfsCreatePFsPersistentPath(v14, (int)a1 + 1620, v12, v13, (__int64)&lpMem);
    }
    v17 = lpMem;
    *(_QWORD *)(a1 + 1664) = lpMem;
    LastError = PFsPersistentPath;
    ReleaseSRWLockExclusive(&g_shareCreateMutex);
    if ( !LastError )
    {
      v18 = (*(_DWORD *)a1 & 0x1000000) != 0
          ? ExportDeviceIoControlDb(268469696, a2, a1, &v21)
          : ExportDeviceIoControl(268469376, a2, a1, &v21);
      v7 = v21;
      LastError = v18;
      if ( v18 || v21 && v21 != -2147483645 )
        NfsRemovePFsPersistentPath(a1 + 556, v15 & -(__int64)((*(_DWORD *)a1 & 0x800000) != 0));
    }
    if ( v17 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v17);
    }
    if ( !LastError )
      goto LABEL_28;
  }
  return LastError;
}

```

## disassembly

```asm
0x18002d45c  mov     [rsp-38h+arg_18], rbx
0x18002d461  push    rbp
0x18002d462  push    rsi
0x18002d463  push    rdi
0x18002d464  push    r12
0x18002d466  push    r13
0x18002d468  push    r14
0x18002d46a  push    r15
0x18002d46c  mov     rbp, rsp
0x18002d46f  sub     rsp, 70h
0x18002d473  mov     rax, cs:__security_cookie
0x18002d47a  xor     rax, rsp
0x18002d47d  mov     [rbp+var_10], rax
0x18002d481  xor     r15d, r15d
0x18002d484  mov     [rbp+var_20], r8
0x18002d488  lea     r14, [rcx+20h]
0x18002d48c  mov     [rbp+lpMem], r15
0x18002d490  mov     rdi, rcx
0x18002d493  mov     [rbp+var_40], r15d
0x18002d497  mov     rcx, r14; lpFileName
0x18002d49a  mov     r13, rdx
0x18002d49d  mov     ebx, r15d
0x18002d4a0  mov     esi, r15d
0x18002d4a3  call    cs:__imp_GetFileAttributesW
0x18002d4a9  cmp     eax, 0FFFFFFFFh
0x18002d4ac  jnz     short loc_18002D4B8
0x18002d4ae  mov     esi, 80000009h
0x18002d4b3  jmp     loc_18002D66E
0x18002d4b8  mov     edx, 5Ch ; '\'; Ch
0x18002d4bd  mov     rcx, r14; Str
0x18002d4c0  call    wcschr_0
0x18002d4c5  test    rax, rax
0x18002d4c8  jz      loc_18002D676
0x18002d4ce  sub     rax, r14
0x18002d4d1  lea     rcx, [rbp+RootPathName]; unsigned __int16 *
0x18002d4d5  sar     rax, 1
0x18002d4d8  mov     r8, r14; unsigned __int16 *
0x18002d4db  mov     edx, 4; unsigned __int64
0x18002d4e0  lea     r9, [rax+1]; unsigned __int64
0x18002d4e4  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18002d4e9  test    eax, eax
0x18002d4eb  js      loc_18002D676
0x18002d4f1  lea     rcx, [rbp+RootPathName]; lpRootPathName
0x18002d4f5  call    cs:__imp_GetDriveTypeW
0x18002d4fb  cmp     eax, 4
0x18002d4fe  jnz     short loc_18002D50A
0x18002d500  mov     esi, 80000007h
0x18002d505  jmp     loc_18002D66E
0x18002d50a  mov     rcx, r14; SourceString
0x18002d50d  call    NormalizeSharePath
0x18002d512  test    eax, eax
0x18002d514  js      loc_18002D676
0x18002d51a  mov     eax, [rdi+4]
0x18002d51d  mov     dword ptr [rbp+var_30+4], eax
0x18002d520  mov     eax, [rdi]
0x18002d522  and     eax, 3C1F200h
0x18002d527  mov     word ptr [rbp+var_30+0Eh], r15w
0x18002d52c  or      eax, 0C00h
0x18002d531  test    dword ptr [rdi], 1000000h
0x18002d537  mov     dword ptr [rbp+var_30], eax
0x18002d53a  mov     eax, [rdi+8]
0x18002d53d  mov     dword ptr [rbp+var_30+8], eax
0x18002d540  jz      short loc_18002D548
0x18002d542  movzx   eax, word ptr [rdi+0Ch]
0x18002d546  jmp     short loc_18002D54D
0x18002d548  mov     eax, 5Ah ; 'Z'
0x18002d54d  mov     word ptr [rbp+var_30+0Ch], ax
0x18002d551  lea     rdx, ?InitShareCreateMutexCallbackFn@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18002d558  movups  xmm0, [rbp+var_30]
0x18002d55c  xor     r9d, r9d; Context
0x18002d55f  lea     rcx, ?g_InitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18002d566  xor     r8d, r8d; Parameter
0x18002d569  movdqu  xmmword ptr [rdi], xmm0
0x18002d56d  call    cs:__imp_InitOnceExecuteOnce
0x18002d573  test    eax, eax
0x18002d575  jnz     short loc_18002D57F
0x18002d577  call    cs:__imp_GetLastError
0x18002d57d  mov     ebx, eax
0x18002d57f  test    ebx, ebx
0x18002d581  jnz     loc_18002D67B
0x18002d587  lea     rcx, ?g_shareCreateMutex@@3U_RTL_SRWLOCK@@A; SRWLock
0x18002d58e  call    cs:__imp_AcquireSRWLockExclusive
0x18002d594  test    dword ptr [rdi], 800000h
0x18002d59a  lea     r9, [rdi+678h]
0x18002d5a1  mov     [r9], r15d
0x18002d5a4  lea     rax, [rbp+lpMem]
0x18002d5a8  mov     [rdi+680h], r15
0x18002d5af  lea     r15, [rdi+22Ch]
0x18002d5b6  mov     rcx, r15
0x18002d5b9  mov     [rsp+70h+var_50], rax
0x18002d5be  jz      short loc_18002D5D1
0x18002d5c0  lea     r12, [rdi+654h]
0x18002d5c7  mov     rdx, r12
0x18002d5ca  call    NfsCreatePFsPersistentPath
0x18002d5cf  jmp     short loc_18002D5DF
0x18002d5d1  xor     edx, edx
0x18002d5d3  call    NfsCreatePFsPersistentPath
0x18002d5d8  lea     r12, [rdi+654h]
0x18002d5df  mov     r14, [rbp+lpMem]
0x18002d5e3  lea     rcx, ?g_shareCreateMutex@@3U_RTL_SRWLOCK@@A; SRWLock
0x18002d5ea  mov     [rdi+680h], r14
0x18002d5f1  mov     ebx, eax
0x18002d5f3  call    cs:__imp_ReleaseSRWLockExclusive
0x18002d5f9  test    ebx, ebx
0x18002d5fb  jnz     short loc_18002D651
0x18002d5fd  test    dword ptr [rdi], 1000000h
0x18002d603  lea     r9, [rbp+var_40]
0x18002d607  mov     r8, rdi
0x18002d60a  mov     rdx, r13
0x18002d60d  jz      short loc_18002D61B
0x18002d60f  mov     ecx, 100085C0h
0x18002d614  call    ExportDeviceIoControlDb
0x18002d619  jmp     short loc_18002D625
0x18002d61b  mov     ecx, 10008480h
0x18002d620  call    ExportDeviceIoControl
0x18002d625  mov     esi, [rbp+var_40]
0x18002d628  mov     ebx, eax
0x18002d62a  test    eax, eax
0x18002d62c  jnz     short loc_18002D63A
0x18002d62e  test    esi, esi
0x18002d630  jz      short loc_18002D651
0x18002d632  cmp     esi, 80000003h
0x18002d638  jz      short loc_18002D651
0x18002d63a  mov     eax, [rdi]
0x18002d63c  mov     rcx, r15
0x18002d63f  and     eax, 800000h
0x18002d644  neg     eax
0x18002d646  sbb     rdx, rdx
0x18002d649  and     rdx, r12
0x18002d64c  call    NfsRemovePFsPersistentPath
0x18002d651  test    r14, r14
0x18002d654  jz      short loc_18002D66A
0x18002d656  call    cs:__imp_GetProcessHeap
0x18002d65c  mov     r8, r14; lpMem
0x18002d65f  xor     edx, edx; dwFlags
0x18002d661  mov     rcx, rax; hHeap
0x18002d664  call    cs:__imp_HeapFree
0x18002d66a  test    ebx, ebx
0x18002d66c  jnz     short loc_18002D67B
0x18002d66e  mov     rax, [rbp+var_20]
0x18002d672  mov     [rax], esi
0x18002d674  jmp     short loc_18002D67B
0x18002d676  mov     ebx, 57h ; 'W'
0x18002d67b  mov     eax, ebx
0x18002d67d  mov     rcx, [rbp+var_10]
0x18002d681  xor     rcx, rsp; StackCookie
0x18002d684  call    __security_check_cookie
0x18002d689  mov     rbx, [rsp+70h+arg_18]
0x18002d691  add     rsp, 70h
0x18002d695  pop     r15
0x18002d697  pop     r14
0x18002d699  pop     r13
0x18002d69b  pop     r12
0x18002d69d  pop     rdi
0x18002d69e  pop     rsi
0x18002d69f  pop     rbp
0x18002d6a0  retn
```
