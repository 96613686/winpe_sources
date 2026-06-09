# CreateLocalILinkInfo(ushort const *,_ilinkinfoW * *)

- ea: `0x180002500`
- end: `0x1800028b8`
- name: `?CreateLocalILinkInfo@@YAHPEBGPEAPEAU_ilinkinfoW@@@Z`
- size: `952`
- prototype: `__int64 __fastcall(LPCWSTR lpString, struct _ilinkinfoW **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001f10`

## callees

- `0x1800023d0`
- `0x180002500`
- `0x1800028c0`
- `0x180002b00`
- `0x180004b50`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800025e1`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800025e1`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800025c4`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800025c4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1800026ad`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1800026ad`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800027c0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800027c0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800026f9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000279d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800027e0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800026f9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000279d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800027e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000274f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000278f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800028a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000274f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000278f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800028a4`
- `ext-ms-win-shell-ntshrui-l1-1-0!GetNetResourceFromLocalPathW` at `0x180002688`
- `ext-ms-win-shell-ntshrui-l1-1-0!GetNetResourceFromLocalPathW` at `0x180002688`

## pseudocode

```c
int __fastcall CreateLocalILinkInfo(LPCWSTR lpString, struct _ilinkinfoW **a2)
{
  unsigned int v2; // r13d
  __int64 v3; // rsi
  WCHAR *v4; // rdx
  __int64 v5; // rax
  const WCHAR *v6; // r14
  LPCWSTR v7; // r8
  __int64 v8; // r9
  WCHAR *v9; // rcx
  __int64 v10; // rdi
  int result; // eax
  DWORD v12; // ebx
  UINT DriveTypeW; // eax
  WCHAR *v14; // r8
  __int64 v15; // rcx
  const WCHAR *v16; // rdx
  __int64 v17; // r9
  WCHAR *v18; // rcx
  int NetResourceFromLocalPathW; // eax
  const struct _volumeid *v20; // r12
  unsigned int v21; // r15d
  const WCHAR *v22; // rcx
  WCHAR *v23; // rdx
  WCHAR *v24; // rcx
  const WCHAR *v25; // r14
  HLOCAL v26; // rdi
  int v27; // ebx
  _WORD *v28; // r8
  unsigned __int64 v29; // rax
  WCHAR *v30; // rdx
  WCHAR *v31; // rcx
  LPDWORD lpMaximumComponentLength; // [rsp+20h] [rbp-E0h]
  DWORD VolumeSerialNumber; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int Size; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int Size_4; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR v36; // [rsp+50h] [rbp-B0h]
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  struct _ilinkinfoW **v38; // [rsp+60h] [rbp-A0h]
  WCHAR RootPathName[4]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR VolumeNameBuffer[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR String[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR pszPath[264]; // [rsp+490h] [rbp+390h] BYREF

  v2 = 0;
  v38 = a2;
  v3 = 2147483646;
  hMem = 0;
  Size = 0;
  v4 = RootPathName;
  VolumeSerialNumber = 0;
  v5 = 2147483646;
  v6 = lpString;
  v36 = lpString;
  v7 = lpString;
  v8 = 4;
  do
  {
    if ( !v5 )
      break;
    if ( !*v7 )
      break;
    *v4++ = *v7++;
    --v5;
    --v8;
  }
  while ( v8 );
  v9 = v4 - 1;
  if ( v8 )
    v9 = v4;
  v10 = 260;
  *v9 = 0;
  result = GetVolumeInformationW(RootPathName, VolumeNameBuffer, 0x104u, &VolumeSerialNumber, 0, 0, 0, 0);
  if ( !result )
    return result;
  v12 = VolumeSerialNumber;
  DriveTypeW = GetDriveTypeW(RootPathName);
  result = UnifyIVolumeIDInfo(DriveTypeW, v12, VolumeNameBuffer, (struct _ivolumeidW **)&hMem, &Size);
  if ( !result )
    return result;
  v14 = pszPath;
  v15 = 2147483646;
  *(_QWORD *)RootPathName = 0;
  v16 = v6;
  Size_4 = 0;
  v17 = 260;
  VolumeSerialNumber = 0;
  do
  {
    if ( !v15 )
      break;
    if ( !*v16 )
      break;
    *v14++ = *v16++;
    --v15;
    --v17;
  }
  while ( v17 );
  v18 = v14 - 1;
  if ( v17 )
    v18 = v14;
  *v18 = 0;
  while ( 1 )
  {
    NetResourceFromLocalPathW = GetNetResourceFromLocalPathW(pszPath, String, 260, &VolumeSerialNumber);
    v20 = (const struct _volumeid *)hMem;
    v21 = Size;
    if ( NetResourceFromLocalPathW )
      break;
    if ( !PathRemoveFileSpecW(pszPath) )
      goto LABEL_18;
  }
  v25 = &v6[lstrlenW(pszPath)];
  if ( (unsigned int)CharIsSlash(*v25) )
    v25 = CharNextW(v25);
  if ( !String[0] || VolumeNameBuffer[lstrlenW(String) + 263] == 36 )
  {
    v6 = v36;
LABEL_18:
    v22 = v6;
    v23 = VolumeNameBuffer;
    do
    {
      if ( !v3 )
        break;
      if ( !*v22 )
        break;
      *v23++ = *v22++;
      --v3;
      --v10;
    }
    while ( v10 );
    v24 = v23 - 1;
    if ( v10 )
      v24 = v23;
    *v24 = 0;
    v25 = &v6[lstrlenW(v6)];
    goto LABEL_25;
  }
  v27 = UnifyICNRLinkInfo(String, 2u, 0, VolumeSerialNumber, (struct tagICNRLINKW **)RootPathName, &Size_4);
  if ( !v27 )
    goto LABEL_27;
  v28 = v36;
  v29 = v25 - v36;
  if ( v29 > 0x7FFFFFFE )
  {
    VolumeNameBuffer[0] = 0;
LABEL_48:
    LocalFree(*(HLOCAL *)RootPathName);
    v27 = 0;
    goto LABEL_27;
  }
  v30 = VolumeNameBuffer;
  do
  {
    if ( !v29 )
      break;
    if ( !*v28 )
      break;
    *v30++ = *v28++;
    --v29;
    --v10;
  }
  while ( v10 );
  v31 = v30 - 1;
  if ( v10 )
    v31 = v30;
  *v31 = 0;
  if ( !v10 )
    goto LABEL_48;
  v2 = Size_4;
LABEL_25:
  v26 = *(HLOCAL *)RootPathName;
  LODWORD(lpMaximumComponentLength) = v2;
  v27 = UnifyILinkInfo(
          v20,
          v21,
          VolumeNameBuffer,
          *(const struct _cnrlink **)RootPathName,
          (size_t)lpMaximumComponentLength,
          v25,
          v38);
  if ( v2 )
    LocalFree(v26);
LABEL_27:
  if ( v21 )
    LocalFree(v20);
  return v27;
}

```

## disassembly

```asm
0x180002500  push    rbp
0x180002502  push    rsi
0x180002503  push    rdi
0x180002504  push    r13
0x180002506  push    r14
0x180002508  lea     rbp, [rsp-5C0h]
0x180002510  sub     rsp, 6C0h
0x180002517  mov     rax, cs:__security_cookie
0x18000251e  xor     rax, rsp
0x180002521  mov     [rbp+5E0h+var_40], rax
0x180002528  xor     r13d, r13d
0x18000252b  mov     [rsp+6E0h+var_680], rdx
0x180002530  mov     esi, 7FFFFFFEh
0x180002535  mov     [rsp+6E0h+hMem], r13
0x18000253a  mov     dword ptr [rsp+6E0h+Size], r13d
0x18000253f  lea     rdx, [rsp+6E0h+RootPathName]
0x180002544  mov     [rsp+6E0h+VolumeSerialNumber], r13d
0x180002549  mov     eax, esi
0x18000254b  mov     r14, rcx
0x18000254e  mov     [rsp+6E0h+var_690], rcx
0x180002553  mov     r8, rcx
0x180002556  mov     r9d, 4
0x18000255c  nop     dword ptr [rax+00h]
0x180002560  test    rax, rax
0x180002563  jz      short loc_180002582
0x180002565  movzx   ecx, word ptr [r8]
0x180002569  test    cx, cx
0x18000256c  jz      short loc_180002582
0x18000256e  mov     [rdx], cx
0x180002571  add     r8, 2
0x180002575  add     rdx, 2
0x180002579  dec     rax
0x18000257c  sub     r9, 1
0x180002580  jnz     short loc_180002560
0x180002582  test    r9, r9
0x180002585  mov     [rsp+6E0h+nFileSystemNameSize], r13d; nFileSystemNameSize
0x18000258a  lea     rcx, [rdx-2]
0x18000258e  mov     [rsp+6E0h+lpFileSystemNameBuffer], r13; lpFileSystemNameBuffer
0x180002593  cmovnz  rcx, rdx
0x180002597  mov     [rsp+6E0h+lpFileSystemFlags], r13; lpFileSystemFlags
0x18000259c  mov     edi, 104h
0x1800025a1  mov     [rsp+6E0h+arg_10], rbx
0x1800025a9  lea     r9, [rsp+6E0h+VolumeSerialNumber]; lpVolumeSerialNumber
0x1800025ae  mov     [rsp+6E0h+lpMaximumComponentLength], r13; lpMaximumComponentLength
0x1800025b3  mov     r8d, edi; nVolumeNameSize
0x1800025b6  lea     rdx, [rsp+6E0h+VolumeNameBuffer]; lpVolumeNameBuffer
0x1800025bb  mov     [rcx], r13w
0x1800025bf  lea     rcx, [rsp+6E0h+RootPathName]; lpRootPathName
0x1800025c4  call    cs:__imp_GetVolumeInformationW
0x1800025cb  nop     dword ptr [rax+rax+00h]
0x1800025d0  test    eax, eax
0x1800025d2  jz      loc_180002765
0x1800025d8  mov     ebx, [rsp+6E0h+VolumeSerialNumber]
0x1800025dc  lea     rcx, [rsp+6E0h+RootPathName]; lpRootPathName
0x1800025e1  call    cs:__imp_GetDriveTypeW
0x1800025e8  nop     dword ptr [rax+rax+00h]
0x1800025ed  lea     rcx, [rsp+6E0h+Size]
0x1800025f2  mov     edx, ebx; unsigned int
0x1800025f4  mov     [rsp+6E0h+lpMaximumComponentLength], rcx; unsigned int *
0x1800025f9  lea     r9, [rsp+6E0h+hMem]; struct _ivolumeidW **
0x1800025fe  mov     ecx, eax; unsigned int
0x180002600  lea     r8, [rsp+6E0h+VolumeNameBuffer]; unsigned __int16 *
0x180002605  call    ?UnifyIVolumeIDInfo@@YAHIKPEBGPEAPEAU_ivolumeidW@@PEAI@Z; UnifyIVolumeIDInfo(uint,ulong,ushort const *,_ivolumeidW * *,uint *)
0x18000260a  test    eax, eax
0x18000260c  jz      loc_180002765
0x180002612  mov     [rsp+6E0h+var_28], r12
0x18000261a  lea     r8, [rbp+5E0h+pszPath]
0x180002621  mov     [rsp+6E0h+var_30], r15
0x180002629  mov     rcx, rsi
0x18000262c  mov     qword ptr [rsp+6E0h+RootPathName], r13
0x180002631  mov     rdx, r14
0x180002634  mov     dword ptr [rsp+6E0h+Size+4], r13d
0x180002639  mov     r9d, edi
0x18000263c  mov     [rsp+6E0h+VolumeSerialNumber], r13d
0x180002641  test    rcx, rcx
0x180002644  jz      short loc_180002663
0x180002646  movzx   eax, word ptr [rdx]
0x180002649  test    ax, ax
0x18000264c  jz      short loc_180002663
0x18000264e  mov     [r8], ax
0x180002652  add     rdx, 2
0x180002656  add     r8, 2
0x18000265a  dec     rcx
0x18000265d  sub     r9, 1
0x180002661  jnz     short loc_180002641
0x180002663  test    r9, r9
0x180002666  lea     rcx, [r8-2]
0x18000266a  cmovnz  rcx, r8
0x18000266e  mov     [rcx], r13w
0x180002672  lea     r9, [rsp+6E0h+VolumeSerialNumber]
0x180002677  mov     r8d, edi
0x18000267a  lea     rdx, [rbp+5E0h+String]
0x180002681  lea     rcx, [rbp+5E0h+pszPath]
0x180002688  call    cs:__imp_GetNetResourceFromLocalPathW
0x18000268f  nop     dword ptr [rax+rax+00h]
0x180002694  mov     r12, [rsp+6E0h+hMem]
0x180002699  lea     rcx, [rbp+5E0h+pszPath]; lpString
0x1800026a0  mov     r15d, dword ptr [rsp+6E0h+Size]
0x1800026a5  test    eax, eax
0x1800026a7  jnz     loc_18000279D
0x1800026ad  call    cs:__imp_PathRemoveFileSpecW
0x1800026b4  nop     dword ptr [rax+rax+00h]
0x1800026b9  test    eax, eax
0x1800026bb  jnz     short loc_180002672
0x1800026bd  mov     rcx, r14
0x1800026c0  lea     rdx, [rsp+6E0h+VolumeNameBuffer]
0x1800026c5  test    rsi, rsi
0x1800026c8  jz      short loc_1800026E6
0x1800026ca  movzx   eax, word ptr [rcx]
0x1800026cd  test    ax, ax
0x1800026d0  jz      short loc_1800026E6
0x1800026d2  mov     [rdx], ax
0x1800026d5  add     rcx, 2
0x1800026d9  add     rdx, 2
0x1800026dd  dec     rsi
0x1800026e0  sub     rdi, 1
0x1800026e4  jnz     short loc_1800026C5
0x1800026e6  test    rdi, rdi
0x1800026e9  lea     rcx, [rdx-2]
0x1800026ed  cmovnz  rcx, rdx
0x1800026f1  xor     eax, eax
0x1800026f3  mov     [rcx], ax
0x1800026f6  mov     rcx, r14; lpString
0x1800026f9  call    cs:__imp_lstrlenW
0x180002700  nop     dword ptr [rax+rax+00h]
0x180002705  movsxd  rcx, eax
0x180002708  lea     r14, [r14+rcx*2]
0x18000270c  mov     rax, [rsp+6E0h+var_680]
0x180002711  lea     r8, [rsp+6E0h+VolumeNameBuffer]; lpString1
0x180002716  mov     rdi, qword ptr [rsp+6E0h+RootPathName]
0x18000271b  mov     edx, r15d; Size
0x18000271e  mov     [rsp+6E0h+lpFileSystemNameBuffer], rax; struct _ilinkinfoW **
0x180002723  mov     r9, rdi; struct _cnrlink *
0x180002726  mov     [rsp+6E0h+lpFileSystemFlags], r14; lpWideCharStr
0x18000272b  mov     rcx, r12; Src
0x18000272e  mov     dword ptr [rsp+6E0h+lpMaximumComponentLength], r13d; size_t
0x180002733  call    ?UnifyILinkInfo@@YAHPEBU_volumeid@@IPEBGPEBU_cnrlink@@I1PEAPEAU_ilinkinfoW@@@Z; UnifyILinkInfo(_volumeid const *,uint,ushort const *,_cnrlink const *,uint,ushort const *,_ilinkinfoW * *)
0x180002738  mov     ebx, eax
0x18000273a  test    r13d, r13d
0x18000273d  jnz     short loc_18000278C
0x18000273f  test    r15d, r15d
0x180002742  mov     r15, [rsp+6E0h+var_30]
0x18000274a  jz      short loc_18000275B
0x18000274c  mov     rcx, r12; hMem
0x18000274f  call    cs:__imp_LocalFree
0x180002756  nop     dword ptr [rax+rax+00h]
0x18000275b  mov     r12, [rsp+6E0h+var_28]
0x180002763  mov     eax, ebx
0x180002765  mov     rbx, [rsp+6E0h+arg_10]
0x18000276d  mov     rcx, [rbp+5E0h+var_40]
0x180002774  xor     rcx, rsp; StackCookie
0x180002777  call    __security_check_cookie
0x18000277c  add     rsp, 6C0h
0x180002783  pop     r14
0x180002785  pop     r13
0x180002787  pop     rdi
0x180002788  pop     rsi
0x180002789  pop     rbp
0x18000278a  retn
0x18000278c  mov     rcx, rdi; hMem
0x18000278f  call    cs:__imp_LocalFree
0x180002796  nop     dword ptr [rax+rax+00h]
0x18000279b  jmp     short loc_18000273F
0x18000279d  call    cs:__imp_lstrlenW
0x1800027a4  nop     dword ptr [rax+rax+00h]
0x1800027a9  movsxd  rcx, eax
0x1800027ac  lea     r14, [r14+rcx*2]
0x1800027b0  movzx   ecx, word ptr [r14]; unsigned __int16
0x1800027b4  call    ?CharIsSlash@@YAHG@Z; CharIsSlash(ushort)
0x1800027b9  test    eax, eax
0x1800027bb  jz      short loc_1800027CF
0x1800027bd  mov     rcx, r14; lpsz
0x1800027c0  call    cs:__imp_CharNextW
0x1800027c7  nop     dword ptr [rax+rax+00h]
0x1800027cc  mov     r14, rax
0x1800027cf  cmp     [rbp+5E0h+String], r13w
0x1800027d7  jz      short loc_1800027FA
0x1800027d9  lea     rcx, [rbp+5E0h+String]; lpString
0x1800027e0  call    cs:__imp_lstrlenW
0x1800027e7  nop     dword ptr [rax+rax+00h]
0x1800027ec  movsxd  rcx, eax
0x1800027ef  cmp     [rbp+rcx*2+5E0h+var_462], 24h ; '$'
0x1800027f8  jnz     short loc_18000285D
0x1800027fa  mov     r14, [rsp+6E0h+var_690]
0x1800027ff  jmp     loc_1800026BD
0x180002804  mov     r8, [rsp+6E0h+var_690]
0x180002809  mov     rax, r14
0x18000280c  sub     rax, r8
0x18000280f  sar     rax, 1
0x180002812  cmp     rax, rsi
0x180002815  ja      loc_180002899
0x18000281b  lea     rdx, [rsp+6E0h+VolumeNameBuffer]
0x180002820  test    rax, rax
0x180002823  jz      short loc_180002842
0x180002825  movzx   ecx, word ptr [r8]
0x180002829  test    cx, cx
0x18000282c  jz      short loc_180002842
0x18000282e  mov     [rdx], cx
0x180002831  add     r8, 2
0x180002835  add     rdx, 2
0x180002839  dec     rax
0x18000283c  sub     rdi, 1
0x180002840  jnz     short loc_180002820
0x180002842  test    rdi, rdi
0x180002845  lea     rcx, [rdx-2]
0x180002849  cmovnz  rcx, rdx
0x18000284d  mov     [rcx], r13w
0x180002851  jz      short loc_18000289F
0x180002853  mov     r13d, dword ptr [rsp+6E0h+Size+4]
0x180002858  jmp     loc_18000270C
0x18000285d  mov     r9d, [rsp+6E0h+VolumeSerialNumber]; unsigned int
0x180002862  lea     rax, [rsp+6E0h+Size+4]
0x180002867  mov     [rsp+6E0h+lpFileSystemFlags], rax; unsigned int *
0x18000286c  lea     rcx, [rbp+5E0h+String]; lpString
0x180002873  lea     rax, [rsp+6E0h+RootPathName]
0x180002878  xor     r8d, r8d; unsigned __int16 *
0x18000287b  mov     edx, 2; unsigned int
0x180002880  mov     [rsp+6E0h+lpMaximumComponentLength], rax; struct tagICNRLINKW **
0x180002885  call    ?UnifyICNRLinkInfo@@YAHPEBGK0KPEAPEAUtagICNRLINKW@@PEAI@Z; UnifyICNRLinkInfo(ushort const *,ulong,ushort const *,ulong,tagICNRLINKW * *,uint *)
0x18000288a  mov     ebx, eax
0x18000288c  test    eax, eax
0x18000288e  jz      loc_18000273F
0x180002894  jmp     loc_180002804
0x180002899  mov     [rsp+6E0h+VolumeNameBuffer], r13w
0x18000289f  mov     rcx, qword ptr [rsp+6E0h+RootPathName]; hMem
0x1800028a4  call    cs:__imp_LocalFree
0x1800028ab  nop     dword ptr [rax+rax+00h]
0x1800028b0  mov     ebx, r13d
0x1800028b3  jmp     loc_18000273F
```
