# CAsyncFile::CalcAlignment(ushort const *,long &,ulong &)

- ea: `0x1800283c0`
- end: `0x18002855e`
- name: `?CalcAlignment@CAsyncFile@@AEAAXPEBGAEAJAEAK@Z`
- size: `414`
- prototype: `void(CAsyncFile *__hidden this, const unsigned __int16 *, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800fd28c`

## callees

- `0x1800283c0`
- `0x1800388a0`
- `0x18015bb20`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x180028408`
- `KERNEL32!GetFullPathNameW` at `0x18002844f`
- `KERNEL32!GetFullPathNameW` at `0x180028408`
- `KERNEL32!GetFullPathNameW` at `0x18002844f`
- `KERNEL32!GetDiskFreeSpaceW` at `0x180028520`
- `KERNEL32!GetDiskFreeSpaceW` at `0x180028520`
- `KERNEL32!GetDriveTypeW` at `0x1800284e4`
- `KERNEL32!GetDriveTypeW` at `0x1800284e4`
- `USER32!CharNextW` at `0x180028488`
- `USER32!CharNextW` at `0x1800284b3`
- `USER32!CharNextW` at `0x1800284cd`
- `USER32!CharNextW` at `0x180028488`
- `USER32!CharNextW` at `0x1800284b3`
- `USER32!CharNextW` at `0x1800284cd`

## pseudocode

```c
void __fastcall CAsyncFile::CalcAlignment(CAsyncFile *this, const unsigned __int16 *a2, DWORD *a3, unsigned int *a4)
{
  DWORD v7; // edi
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  DWORD FullPathNameW; // eax
  WCHAR *i; // rax
  const WCHAR *v15; // rcx
  UINT DriveTypeW; // eax
  bool v17; // zf
  DWORD v18; // eax
  LPWSTR FilePart; // [rsp+30h] [rbp+0h] BYREF
  DWORD BytesPerSector; // [rsp+38h] [rbp+8h] BYREF
  DWORD TotalNumberOfClusters; // [rsp+3Ch] [rbp+Ch] BYREF
  DWORD NumberOfFreeClusters; // [rsp+40h] [rbp+10h] BYREF
  DWORD SectorsPerCluster; // [rsp+44h] [rbp+14h] BYREF

  *a3 = 1;
  *a4 = 0;
  FilePart = 0;
  v7 = GetFullPathNameW(a2, 0, 0, &FilePart) + 1;
  v8 = 2LL * v7;
  v9 = v8 + 15;
  if ( v8 + 15 < v8 )
    v9 = 0xFFFFFFFFFFFFFF0LL;
  v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
  v11 = alloca(v10);
  v12 = alloca(v10);
  FullPathNameW = GetFullPathNameW(a2, v7, (LPWSTR)&FilePart, &FilePart);
  if ( FullPathNameW && FullPathNameW < v7 )
  {
    if ( (_DWORD)FilePart == 6029404 )
    {
      for ( i = (WCHAR *)&FilePart + 2; ; i = CharNextW(i) )
      {
        FilePart = i;
        if ( !*i )
          break;
        v15 = i;
        if ( *i == 92 )
          goto LABEL_13;
      }
    }
    else
    {
      i = (WCHAR *)&FilePart;
      FilePart = (LPWSTR)&FilePart;
    }
    while ( *i )
    {
      v15 = i;
      if ( *i == 92 )
      {
        FilePart = CharNextW(i);
        *FilePart = 0;
        break;
      }
LABEL_13:
      i = CharNextW(v15);
      FilePart = i;
    }
    DriveTypeW = GetDriveTypeW((LPCWSTR)&FilePart);
    *a4 = DriveTypeW;
    if ( DriveTypeW == 4 )
    {
      *a3 = 1;
    }
    else
    {
      SectorsPerCluster = 0;
      NumberOfFreeClusters = 0;
      TotalNumberOfClusters = 0;
      BytesPerSector = 0;
      v17 = !GetDiskFreeSpaceW(
               (LPCWSTR)&FilePart,
               &SectorsPerCluster,
               &BytesPerSector,
               &NumberOfFreeClusters,
               &TotalNumberOfClusters);
      v18 = 4096;
      if ( !v17 )
        v18 = BytesPerSector;
      *a3 = v18;
    }
  }
}

```

## disassembly

```asm
0x1800283c0  push    rbp
0x1800283c2  push    rbx
0x1800283c3  push    rsi
0x1800283c4  push    rdi
0x1800283c5  push    r12
0x1800283c7  push    r14
0x1800283c9  push    r15
0x1800283cb  sub     rsp, 50h
0x1800283cf  lea     rbp, [rsp+30h]
0x1800283d4  mov     rax, cs:__security_cookie
0x1800283db  xor     rax, rbp
0x1800283de  mov     [rbp+50h+var_38], rax
0x1800283e2  mov     r14, rdx
0x1800283e5  mov     dword ptr [r8], 1
0x1800283ec  xor     r12d, r12d
0x1800283ef  mov     r15, r9
0x1800283f2  mov     [r9], r12d
0x1800283f5  mov     rsi, r8
0x1800283f8  lea     r9, [rbp+50h+FilePart]; lpFilePart
0x1800283fc  mov     [rbp+50h+FilePart], r12
0x180028400  xor     r8d, r8d; lpBuffer
0x180028403  xor     edx, edx; nBufferLength
0x180028405  mov     rcx, r14; lpFileName
0x180028408  call    cs:__imp_GetFullPathNameW
0x18002840f  nop     dword ptr [rax+rax+00h]
0x180028414  lea     edi, [rax+1]
0x180028417  mov     eax, edi
0x180028419  add     rax, rax
0x18002841c  lea     rcx, [rax+0Fh]
0x180028420  cmp     rcx, rax
0x180028423  ja      short loc_18002842F
0x180028425  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002842f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180028433  mov     rax, rcx
0x180028436  call    _alloca_probe
0x18002843b  sub     rsp, rcx
0x18002843e  lea     r9, [rbp+50h+FilePart]; lpFilePart
0x180028442  mov     edx, edi; nBufferLength
0x180028444  mov     rcx, r14; lpFileName
0x180028447  lea     rbx, [rsp+80h+FilePart]
0x18002844c  mov     r8, rbx; lpBuffer
0x18002844f  call    cs:__imp_GetFullPathNameW
0x180028456  nop     dword ptr [rax+rax+00h]
0x18002845b  test    eax, eax
0x18002845d  jz      loc_180028542
0x180028463  cmp     eax, edi
0x180028465  jnb     loc_180028542
0x18002846b  mov     di, 5Ch ; '\'
0x18002846f  cmp     [rbx], di
0x180028472  jnz     short loc_1800284A2
0x180028474  cmp     [rbx+2], di
0x180028478  jnz     short loc_1800284A2
0x18002847a  lea     rax, [rbx+4]
0x18002847e  jmp     short loc_180028494
0x180028480  cmp     cx, di
0x180028483  mov     rcx, rax; lpsz
0x180028486  jz      short loc_1800284B3
0x180028488  call    cs:__imp_CharNextW
0x18002848f  nop     dword ptr [rax+rax+00h]
0x180028494  mov     [rbp+50h+FilePart], rax
0x180028498  movzx   ecx, word ptr [rax]
0x18002849b  test    cx, cx
0x18002849e  jnz     short loc_180028480
0x1800284a0  jmp     short loc_1800284C3
0x1800284a2  mov     rax, rbx
0x1800284a5  mov     [rbp+50h+FilePart], rbx
0x1800284a9  jmp     short loc_1800284C3
0x1800284ab  cmp     cx, di
0x1800284ae  mov     rcx, rax; lpsz
0x1800284b1  jz      short loc_1800284CD
0x1800284b3  call    cs:__imp_CharNextW
0x1800284ba  nop     dword ptr [rax+rax+00h]
0x1800284bf  mov     [rbp+50h+FilePart], rax
0x1800284c3  movzx   ecx, word ptr [rax]
0x1800284c6  test    cx, cx
0x1800284c9  jnz     short loc_1800284AB
0x1800284cb  jmp     short loc_1800284E1
0x1800284cd  call    cs:__imp_CharNextW
0x1800284d4  nop     dword ptr [rax+rax+00h]
0x1800284d9  mov     [rbp+50h+FilePart], rax
0x1800284dd  mov     [rax], r12w
0x1800284e1  mov     rcx, rbx; lpRootPathName
0x1800284e4  call    cs:__imp_GetDriveTypeW
0x1800284eb  nop     dword ptr [rax+rax+00h]
0x1800284f0  mov     [r15], eax
0x1800284f3  cmp     eax, 4
0x1800284f6  jz      short loc_18002853C
0x1800284f8  lea     rax, [rbp+50h+TotalNumberOfClusters]
0x1800284fc  mov     [rbp+50h+SectorsPerCluster], r12d
0x180028500  lea     r9, [rbp+50h+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x180028504  mov     [rsp+80h+lpTotalNumberOfClusters], rax; lpTotalNumberOfClusters
0x180028509  lea     r8, [rbp+50h+BytesPerSector]; lpBytesPerSector
0x18002850d  mov     [rbp+50h+NumberOfFreeClusters], r12d
0x180028511  lea     rdx, [rbp+50h+SectorsPerCluster]; lpSectorsPerCluster
0x180028515  mov     [rbp+50h+TotalNumberOfClusters], r12d
0x180028519  mov     rcx, rbx; lpRootPathName
0x18002851c  mov     [rbp+50h+BytesPerSector], r12d
0x180028520  call    cs:__imp_GetDiskFreeSpaceW
0x180028527  nop     dword ptr [rax+rax+00h]
0x18002852c  test    eax, eax
0x18002852e  mov     eax, 1000h
0x180028533  jz      short loc_180028538
0x180028535  mov     eax, [rbp+50h+BytesPerSector]
0x180028538  mov     [rsi], eax
0x18002853a  jmp     short loc_180028542
0x18002853c  mov     dword ptr [rsi], 1
0x180028542  mov     rcx, [rbp+50h+var_38]
0x180028546  xor     rcx, rbp; StackCookie
0x180028549  call    __security_check_cookie
0x18002854e  lea     rsp, [rbp+20h]
0x180028552  pop     r15
0x180028554  pop     r14
0x180028556  pop     r12
0x180028558  pop     rdi
0x180028559  pop     rsi
0x18002855a  pop     rbx
0x18002855b  pop     rbp
0x18002855c  retn
```
