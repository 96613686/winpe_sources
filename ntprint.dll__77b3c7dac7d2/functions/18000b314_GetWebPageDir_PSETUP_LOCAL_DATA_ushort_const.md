# GetWebPageDir(_PSETUP_LOCAL_DATA *,ushort * const)

- ea: `0x18000b314`
- end: `0x18000b3f3`
- name: `?GetWebPageDir@@YAHPEAU_PSETUP_LOCAL_DATA@@QEAG@Z`
- size: `223`
- prototype: `int(struct _PSETUP_LOCAL_DATA *, unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180012424`

## callees

- `0x1800078f0`
- `0x18000b314`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b397`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b397`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18000b349`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18000b349`

## pseudocode

```c
__int64 __fastcall GetWebPageDir(struct _PSETUP_LOCAL_DATA *a1, unsigned __int16 *const a2)
{
  unsigned int v4; // esi
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rdx

  v4 = 0;
  if ( *((_QWORD *)a1 + 5) && *((_QWORD *)a1 + 1) && GetSystemWindowsDirectoryW(a2, 0x104u) )
  {
    v5 = -1;
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * v7) );
    do
      ++v5;
    while ( *(_WORD *)(*((_QWORD *)a1 + 5) + 2 * v5) );
    if ( (unsigned int)(v7 + v6 + v5 + 16) < 0x104 )
    {
      StringCchCatW(a2, 0x104u, L"\\web\\printers\\");
      StringCchCatW(a2, 0x104u, *((const unsigned __int16 **)a1 + 5));
      StringCchCatW(a2, 0x104u, L"\\");
      StringCchCatW(a2, 0x104u, *((const unsigned __int16 **)a1 + 1));
      return 1;
    }
    else
    {
      SetLastError(8u);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000b314  push    rbx
0x18000b316  push    rbp
0x18000b317  push    rsi
0x18000b318  push    rdi
0x18000b319  push    r14
0x18000b31b  sub     rsp, 20h
0x18000b31f  xor     ebp, ebp
0x18000b321  mov     rdi, rdx
0x18000b324  mov     rbx, rcx
0x18000b327  mov     esi, ebp
0x18000b329  cmp     [rcx+28h], rbp
0x18000b32d  jz      loc_18000B3E6
0x18000b333  cmp     [rcx+8], rbp
0x18000b337  jz      loc_18000B3E6
0x18000b33d  mov     r14d, 104h
0x18000b343  mov     rcx, rdi; lpBuffer
0x18000b346  mov     edx, r14d; uSize
0x18000b349  call    cs:__imp_GetSystemWindowsDirectoryW
0x18000b34f  test    eax, eax
0x18000b351  jz      loc_18000B3E6
0x18000b357  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000b35b  mov     rax, rcx
0x18000b35e  inc     rax
0x18000b361  cmp     [rdi+rax*2], bp
0x18000b365  jnz     short loc_18000B35E
0x18000b367  mov     r8, [rbx+8]
0x18000b36b  mov     rdx, rcx
0x18000b36e  inc     rdx
0x18000b371  cmp     [r8+rdx*2], bp
0x18000b376  jnz     short loc_18000B36E
0x18000b378  mov     r8, [rbx+28h]
0x18000b37c  inc     rcx
0x18000b37f  cmp     [r8+rcx*2], bp
0x18000b384  jnz     short loc_18000B37C
0x18000b386  add     eax, edx
0x18000b388  add     ecx, 10h
0x18000b38b  add     ecx, eax
0x18000b38d  cmp     ecx, r14d
0x18000b390  jb      short loc_18000B39F
0x18000b392  mov     ecx, 8; dwErrCode
0x18000b397  call    cs:__imp_SetLastError
0x18000b39d  jmp     short loc_18000B3E6
0x18000b39f  lea     r8, aWebPrinters; "\\web\\printers\\"
0x18000b3a6  mov     rdx, r14; unsigned __int64
0x18000b3a9  mov     rcx, rdi; unsigned __int16 *
0x18000b3ac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b3b1  mov     r8, [rbx+28h]; unsigned __int16 *
0x18000b3b5  mov     rdx, r14; unsigned __int64
0x18000b3b8  mov     rcx, rdi; unsigned __int16 *
0x18000b3bb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b3c0  lea     r8, SubBlock; "\\"
0x18000b3c7  mov     rdx, r14; unsigned __int64
0x18000b3ca  mov     rcx, rdi; unsigned __int16 *
0x18000b3cd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b3d2  mov     r8, [rbx+8]; unsigned __int16 *
0x18000b3d6  mov     rdx, r14; unsigned __int64
0x18000b3d9  mov     rcx, rdi; unsigned __int16 *
0x18000b3dc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b3e1  mov     esi, 1
0x18000b3e6  mov     eax, esi
0x18000b3e8  add     rsp, 20h
0x18000b3ec  pop     r14
0x18000b3ee  pop     rdi
0x18000b3ef  pop     rsi
0x18000b3f0  pop     rbp
0x18000b3f1  pop     rbx
0x18000b3f2  retn
```
