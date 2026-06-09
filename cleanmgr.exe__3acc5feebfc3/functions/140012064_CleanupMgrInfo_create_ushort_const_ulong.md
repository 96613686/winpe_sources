# CleanupMgrInfo::create(ushort const *,ulong)

- ea: `0x140012064`
- end: `0x140012242`
- name: `?create@CleanupMgrInfo@@QEAAHPEBGK@Z`
- size: `478`
- prototype: `__int64 __fastcall(CleanupMgrInfo *this, const unsigned __int16 *, char)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000f314`

## callees

- `0x140005fa0`
- `0x14000b68c`
- `0x14000b6dc`
- `0x14000b780`
- `0x14000b830`
- `0x140012064`
- `0x140012970`

## import_xrefs

- `USER32!LoadIconW` at `0x140012161`
- `USER32!LoadIconW` at `0x140012161`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x140012141`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x140012141`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x1400121a4`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x1400121a4`

## pseudocode

```c
__int64 __fastcall CleanupMgrInfo::create(CleanupMgrInfo *this, const unsigned __int16 *a2, char a3)
{
  WCHAR *v3; // rbx
  const unsigned __int16 *v6; // rcx
  const unsigned __int16 *v7; // rcx
  DWORD nFileSystemNameSize; // r11d
  HICON DriveIcon; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rdi
  int LowDiskState; // eax
  bool v15; // zf
  bool v16; // sf
  bool v17; // of
  __int64 result; // rax
  DWORD NumberOfFreeClusters[4]; // [rsp+40h] [rbp-10h] BYREF
  DWORD BytesPerSector; // [rsp+80h] [rbp+30h] BYREF
  DWORD SectorsPerCluster; // [rsp+88h] [rbp+38h] BYREF
  DWORD TotalNumberOfClusters; // [rsp+98h] [rbp+48h] BYREF

  *((_DWORD *)this + 406) = 4;
  SectorsPerCluster = 0;
  v3 = (WCHAR *)((char *)this + 536);
  BytesPerSector = 0;
  NumberOfFreeClusters[0] = 0;
  TotalNumberOfClusters = 0;
  *(_DWORD *)this = 26;
  *((_WORD *)this + 268) = 0;
  *((_DWORD *)this + 395) = 0;
  *((_DWORD *)this + 408) = 0;
  *((_DWORD *)this + 411) = 1;
  if ( !a2
    || !(unsigned int)fIsValidDriveString(a2)
    || !(unsigned int)GetDriveFromString(v6, this)
    || StringCchCopyW((unsigned __int16 *)this + 8, 0x104u, v7) < 0 )
  {
    return 0;
  }
  if ( GetVolumeInformationW(
         (LPCWSTR)this + 8,
         v3,
         nFileSystemNameSize,
         0,
         0,
         0,
         (LPWSTR)this + 528,
         nFileSystemNameSize)
    && ((a3 & 1) == 0
      ? (DriveIcon = (HICON)GetDriveIcon(*(unsigned int *)this, 0))
      : (DriveIcon = LoadIconW(g_hInstance, (LPCWSTR)0x68)),
        (*((_QWORD *)this + 1) = DriveIcon, (unsigned int)GetHardwareType(*(unsigned int *)this, (char *)this + 1576))
     && GetDiskFreeSpaceW(
          (LPCWSTR)this + 8,
          &SectorsPerCluster,
          &BytesPerSector,
          NumberOfFreeClusters,
          &TotalNumberOfClusters)) )
  {
    v10 = SectorsPerCluster * BytesPerSector;
    if ( TotalNumberOfClusters < NumberOfFreeClusters[0] )
      v11 = 0;
    else
      v11 = TotalNumberOfClusters - NumberOfFreeClusters[0];
    v12 = v10 * NumberOfFreeClusters[0];
    v13 = v10 * (unsigned int)v11;
    LowDiskState = CleanupMgrInfo::getLowDiskState(v11, v12, v13 + v12);
    *((_DWORD *)this + 406) = LowDiskState;
    v17 = __OFSUB__(LowDiskState, 2);
    v15 = LowDiskState == 2;
    v16 = LowDiskState - 2 < 0;
    result = 1;
    *((_DWORD *)this + 410) = v16 ^ v17 | v15;
    *((_QWORD *)this + 198) = v12;
    *((_QWORD *)this + 199) = v13;
    *((_QWORD *)this + 200) = 0;
  }
  else
  {
    result = 0;
    *(_DWORD *)this = 26;
    *v3 = 0;
    *((_DWORD *)this + 395) = 0;
    *((_DWORD *)this + 408) = 0;
    *((_DWORD *)this + 411) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x140012064  push    rbp
0x140012066  push    rbx
0x140012067  push    rsi
0x140012068  push    rdi
0x140012069  push    r14
0x14001206b  mov     rbp, rsp
0x14001206e  sub     rsp, 50h
0x140012072  xor     eax, eax
0x140012074  mov     dword ptr [rcx+658h], 4
0x14001207e  mov     [rbp+SectorsPerCluster], 0
0x140012085  lea     rbx, [rcx+218h]
0x14001208c  mov     [rbp+BytesPerSector], 0
0x140012093  mov     r14d, r8d
0x140012096  mov     [rbp+NumberOfFreeClusters], 0
0x14001209d  mov     r9, rdx
0x1400120a0  mov     [rbp+TotalNumberOfClusters], 0
0x1400120a7  mov     rsi, rcx
0x1400120aa  mov     dword ptr [rcx], 1Ah
0x1400120b0  mov     [rbx], ax
0x1400120b3  mov     [rcx+62Ch], eax
0x1400120b9  mov     [rcx+660h], eax
0x1400120bf  mov     dword ptr [rcx+66Ch], 1
0x1400120c9  test    rdx, rdx
0x1400120cc  jz      loc_140012235
0x1400120d2  mov     rcx, rdx; unsigned __int16 *
0x1400120d5  call    ?fIsValidDriveString@@YAHPEBG@Z; fIsValidDriveString(ushort const *)
0x1400120da  test    eax, eax
0x1400120dc  jz      loc_140012235
0x1400120e2  mov     rdx, rsi; enum drenum *
0x1400120e5  call    ?GetDriveFromString@@YAHPEBGAEAW4drenum@@@Z; GetDriveFromString(ushort const *,drenum &)
0x1400120ea  test    eax, eax
0x1400120ec  jz      loc_140012235
0x1400120f2  mov     r8, rcx; unsigned __int16 *
0x1400120f5  lea     rdi, [rsi+10h]
0x1400120f9  mov     r11d, 104h
0x1400120ff  mov     rcx, rdi; unsigned __int16 *
0x140012102  mov     edx, r11d; unsigned __int64
0x140012105  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001210a  test    eax, eax
0x14001210c  js      loc_140012235
0x140012112  mov     [rsp+50h+nFileSystemNameSize], r11d; nFileSystemNameSize
0x140012117  lea     rax, [rsi+420h]
0x14001211e  mov     [rsp+50h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x140012123  xor     r9d, r9d; lpVolumeSerialNumber
0x140012126  mov     [rsp+50h+lpFileSystemFlags], 0; lpFileSystemFlags
0x14001212f  mov     r8d, r11d; nVolumeNameSize
0x140012132  mov     rdx, rbx; lpVolumeNameBuffer
0x140012135  mov     [rsp+50h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x14001213e  mov     rcx, rdi; lpRootPathName
0x140012141  call    cs:__imp_GetVolumeInformationW
0x140012147  test    eax, eax
0x140012149  jz      loc_140012212
0x14001214f  test    r14b, 1
0x140012153  jz      short loc_140012169
0x140012155  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x14001215c  mov     edx, 68h ; 'h'; lpIconName
0x140012161  call    cs:__imp_LoadIconW
0x140012167  jmp     short loc_140012172
0x140012169  mov     ecx, [rsi]
0x14001216b  xor     edx, edx
0x14001216d  call    ?GetDriveIcon@@YAPEAUHICON__@@W4drenum@@H@Z; GetDriveIcon(drenum,int)
0x140012172  mov     [rsi+8], rax
0x140012176  lea     rdx, [rsi+628h]
0x14001217d  mov     ecx, [rsi]
0x14001217f  call    ?GetHardwareType@@YAHW4drenum@@AEAW4hardware@@@Z; GetHardwareType(drenum,hardware &)
0x140012184  test    eax, eax
0x140012186  jz      loc_140012212
0x14001218c  lea     rax, [rbp+TotalNumberOfClusters]
0x140012190  mov     rcx, rdi; lpRootPathName
0x140012193  lea     r9, [rbp+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x140012197  mov     [rsp+50h+lpMaximumComponentLength], rax; lpTotalNumberOfClusters
0x14001219c  lea     r8, [rbp+BytesPerSector]; lpBytesPerSector
0x1400121a0  lea     rdx, [rbp+SectorsPerCluster]; lpSectorsPerCluster
0x1400121a4  call    cs:__imp_GetDiskFreeSpaceW
0x1400121aa  test    eax, eax
0x1400121ac  jz      short loc_140012212
0x1400121ae  mov     eax, [rbp+BytesPerSector]
0x1400121b1  imul    eax, [rbp+SectorsPerCluster]
0x1400121b5  mov     edx, [rbp+NumberOfFreeClusters]
0x1400121b8  mov     ecx, [rbp+TotalNumberOfClusters]
0x1400121bb  cmp     ecx, edx
0x1400121bd  jb      short loc_1400121C3
0x1400121bf  sub     ecx, edx
0x1400121c1  jmp     short loc_1400121C5
0x1400121c3  xor     ecx, ecx
0x1400121c5  mov     rbx, rdx
0x1400121c8  mov     edi, ecx
0x1400121ca  imul    rbx, rax
0x1400121ce  imul    rdi, rax
0x1400121d2  mov     rdx, rbx
0x1400121d5  lea     r8, [rdi+rbx]
0x1400121d9  call    ?getLowDiskState@CleanupMgrInfo@@IEAA?AW4SYSTEM_LOWDISK_STATE@@T_ULARGE_INTEGER@@0@Z; CleanupMgrInfo::getLowDiskState(_ULARGE_INTEGER,_ULARGE_INTEGER)
0x1400121de  xor     ecx, ecx
0x1400121e0  mov     [rsi+658h], eax
0x1400121e6  cmp     eax, 2
0x1400121e9  mov     eax, 1
0x1400121ee  setle   cl
0x1400121f1  mov     [rsi+668h], ecx
0x1400121f7  mov     [rsi+630h], rbx
0x1400121fe  mov     [rsi+638h], rdi
0x140012205  mov     qword ptr [rsi+640h], 0
0x140012210  jmp     short loc_140012237
0x140012212  xor     eax, eax
0x140012214  mov     dword ptr [rsi], 1Ah
0x14001221a  mov     [rbx], ax
0x14001221d  mov     [rsi+62Ch], eax
0x140012223  mov     [rsi+660h], eax
0x140012229  mov     dword ptr [rsi+66Ch], 1
0x140012233  jmp     short loc_140012237
0x140012235  xor     eax, eax
0x140012237  add     rsp, 50h
0x14001223b  pop     r14
0x14001223d  pop     rdi
0x14001223e  pop     rsi
0x14001223f  pop     rbx
0x140012240  pop     rbp
0x140012241  retn
```
