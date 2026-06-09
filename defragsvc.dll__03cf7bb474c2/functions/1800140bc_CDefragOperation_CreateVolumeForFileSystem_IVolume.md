# CDefragOperation::_CreateVolumeForFileSystem(IVolume * *)

- ea: `0x1800140bc`
- end: `0x180014576`
- name: `?_CreateVolumeForFileSystem@CDefragOperation@@IEAAJPEAPEAUIVolume@@@Z`
- size: `1210`
- prototype: `__int64 __fastcall(CDefragOperation *__hidden this, struct IVolume **)`
- caller_count: `11`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e4e0`
- `0x18002b840`
- `0x18002f280`
- `0x1800309c0`
- `0x180053410`
- `0x1800548f0`
- `0x1800568c0`
- `0x180058a20`
- `0x18005a150`
- `0x18005a820`
- `0x18005c2a0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180013f80`
- `0x1800140bc`
- `0x1800157fc`
- `0x180017e34`
- `0x1800192b4`
- `0x18001a630`
- `0x180037b70`
- `0x180037c90`
- `0x180037db8`
- `0x180037ed8`
- `0x180065bdc`
- `0x180065e90`
- `0x180065f00`
- `0x180067af2`
- `0x180067b0a`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180014257`
- `msvcrt!_wcsicmp` at `0x1800143e3`
- `msvcrt!_wcsicmp` at `0x180014438`
- `msvcrt!_wcsicmp` at `0x180014450`
- `msvcrt!_wcsicmp` at `0x180014468`
- `msvcrt!_wcsicmp` at `0x180014257`
- `msvcrt!_wcsicmp` at `0x1800143e3`
- `msvcrt!_wcsicmp` at `0x180014438`
- `msvcrt!_wcsicmp` at `0x180014450`
- `msvcrt!_wcsicmp` at `0x180014468`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800142b9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800142b9`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180014219`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180014219`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800142f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800143bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800142f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800143bb`

## string_xrefs

- `0x180014102`: `CDefragOperation::_CreateVolumeForFileSystem`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDefragOperation::_CreateVolumeForFileSystem(CDefragOperation *this, struct IVolume **a2)
{
  struct IVolume **v2; // rdi
  unsigned int v4; // edx
  __int16 v5; // ax
  _WORD *v6; // r12
  __int64 v7; // r14
  int v8; // r15d
  int v9; // esi
  WCHAR *v10; // rdi
  __int64 v11; // rdx
  struct IVolume **FileW; // rbx
  __int64 v13; // r8
  __int64 v14; // r9
  struct IVolume *v15; // rcx
  bool v16; // sf
  __int16 v17; // ax
  struct IVolume *v18; // rcx
  struct IVolume *v19; // rcx
  bool v20; // sf
  struct IVolume *v21; // rcx
  struct IVolume *v22; // rcx
  unsigned int v23; // ebx
  struct IVolume *v24; // rcx
  LPDWORD lpMaximumComponentLength; // [rsp+20h] [rbp-E0h]
  struct IVolume *v27; // [rsp+40h] [rbp-C0h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v29; // [rsp+4Ch] [rbp-B4h]
  __int16 v30; // [rsp+4Eh] [rbp-B2h]
  LPCWSTR lpRootPathName; // [rsp+80h] [rbp-80h] BYREF
  __int64 v32; // [rsp+88h] [rbp-78h]
  struct IVolume **v33; // [rsp+90h] [rbp-70h]
  _BYTE v34[40]; // [rsp+98h] [rbp-68h] BYREF
  NTFS_VOLUME_DATA_BUFFER v35; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v36[160]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR FileSystemNameBuffer[12]; // [rsp+1C0h] [rbp+C0h] BYREF

  v2 = a2;
  v33 = a2;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CDefragOperation::_CreateVolumeForFileSystem",
    0x406u,
    1u);
  v27 = 0;
  lpRootPathName = &qword_18006F470;
  v32 = 0;
  v5 = 1036;
  if ( !v2 )
  {
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_48;
  }
  *v2 = 0;
  LastFailureAsHRESULT = 0;
  v29 = 1036;
  v6 = (_WORD *)*((_QWORD *)this + 87);
  if ( !v6 )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_13:
    v5 = 1038;
    goto LABEL_48;
  }
  v7 = -1;
  do
    ++v7;
  while ( v6[v7] );
  v8 = 0;
  if ( (_DWORD)v7 && (v8 = CBsString::ExtendBuffer((CBsString *)&lpRootPathName, (int)v7 + 1), v8 >= 0) )
  {
    v9 = v32;
    v10 = (WCHAR *)&lpRootPathName[(unsigned int)v32];
    memcpy_0(v10, v6, 2LL * (unsigned int)v7);
    v10[(unsigned int)v7] = 0;
    LODWORD(v32) = v7 + v9;
    LastFailureAsHRESULT = v8;
    v2 = v33;
  }
  else
  {
    LastFailureAsHRESULT = v8;
    if ( v8 < 0 )
      goto LABEL_13;
  }
  v29 = 1038;
  LastFailureAsHRESULT = CBsString::Trailing((CBsString *)&lpRootPathName, v4);
  v5 = 1039;
  if ( LastFailureAsHRESULT >= 0 )
  {
    v29 = 1039;
    if ( !GetVolumeInformationW(lpRootPathName, 0, 0, 0, 0, 0, FileSystemNameBuffer, 0xAu) )
    {
      LastFailureAsHRESULT = -1996488691;
      v5 = 1054;
      goto LABEL_48;
    }
    if ( _wcsicmp(FileSystemNameBuffer, L"CSVFS") )
    {
      if ( _wcsicmp(FileSystemNameBuffer, L"NTFS") )
      {
        if ( _wcsicmp(FileSystemNameBuffer, L"FAT32") && _wcsicmp(FileSystemNameBuffer, L"FAT") )
        {
          if ( _wcsicmp(FileSystemNameBuffer, L"REFS") )
          {
            LastFailureAsHRESULT = -1996488691;
            v5 = 1110;
            goto LABEL_48;
          }
          v21 = v27;
          if ( v27 )
          {
            v27 = 0;
            (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v21 + 16LL))(v21);
          }
          LastFailureAsHRESULT = CReFsVolume::CreateInstance(*((unsigned __int16 **)this + 87), &v27);
          v20 = LastFailureAsHRESULT < 0;
          v5 = 1104;
        }
        else
        {
          v22 = v27;
          if ( v27 )
          {
            v27 = 0;
            (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v22 + 16LL))(v22);
          }
          LastFailureAsHRESULT = CFatVolume::CreateInstance(*((unsigned __int16 **)this + 87), &v27);
          v20 = LastFailureAsHRESULT < 0;
          v5 = 1100;
        }
      }
      else
      {
        v19 = v27;
        if ( v27 )
        {
          v27 = 0;
          (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v19 + 16LL))(v19);
        }
        LastFailureAsHRESULT = CNtfsVolume::CreateInstance(*((unsigned __int16 **)this + 87), &v27);
        v20 = LastFailureAsHRESULT < 0;
        v5 = 1095;
      }
      if ( v20 )
        goto LABEL_48;
      v29 = v5;
    }
    else
    {
      CFileSystemControl::CFileSystemControl((CFileSystemControl *)v34);
      v35.VolumeSerialNumber.LowPart = 0;
      memset_0((char *)&v35.VolumeSerialNumber.QuadPart + 4, 0, 0x5Cu);
      memset_0(v36, 0, 0x98u);
      FileW = (struct IVolume **)CreateFileW(*((LPCWSTR *)this + 87), 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
      v33 = FileW;
      if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT((char *)FileW + 1, v11, v13, v14, lpMaximumComponentLength);
        v30 = 1083;
        if ( (unsigned __int64)FileW - 1 > 0xFFFFFFFFFFFFFFFDuLL )
          goto LABEL_49;
        goto LABEL_17;
      }
      LastFailureAsHRESULT = 0;
      v29 = 1083;
      if ( CFileSystemControl::GetNtfsVolumeData((CFileSystemControl *)v34, FileW, &v35) < 0 )
      {
        if ( CFileSystemControl::GetRefsVolumeData(
               (CFileSystemControl *)v34,
               FileW,
               (struct REFS_VOLUME_DATA_BUFFER *)v36) < 0 )
        {
          LastFailureAsHRESULT = -1996488672;
          v17 = 1090;
          goto LABEL_23;
        }
        v18 = v27;
        if ( v27 )
        {
          v27 = 0;
          (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v18 + 16LL))(v18);
        }
        LastFailureAsHRESULT = CCsvfsRefsVolume::CreateInstance(*((unsigned __int16 **)this + 87), &v27);
        v16 = LastFailureAsHRESULT < 0;
        v17 = 1088;
      }
      else
      {
        v15 = v27;
        if ( v27 )
        {
          v27 = 0;
          (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v15 + 16LL))(v15);
        }
        LastFailureAsHRESULT = CCsvfsNtfsVolume::CreateInstance(*((unsigned __int16 **)this + 87), &v27);
        v16 = LastFailureAsHRESULT < 0;
        v17 = 1086;
      }
      if ( v16 )
      {
LABEL_23:
        v30 = v17;
LABEL_17:
        CloseHandle(FileW);
        goto LABEL_49;
      }
      v29 = v17;
      CloseHandle(FileW);
    }
    *v2 = v27;
    v27 = 0;
    goto LABEL_49;
  }
LABEL_48:
  v30 = v5;
LABEL_49:
  v23 = LastFailureAsHRESULT;
  CBsString::_FreeData((unsigned __int16 *)lpRootPathName, v4);
  v24 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v24 + 16LL))(v24);
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v23;
}

```

## disassembly

```asm
0x1800140bc  mov     [rsp-8+arg_10], rbx
0x1800140c1  push    rbp
0x1800140c2  push    rsi
0x1800140c3  push    rdi
0x1800140c4  push    r12
0x1800140c6  push    r13
0x1800140c8  push    r14
0x1800140ca  push    r15
0x1800140cc  lea     rbp, [rsp-0E0h]
0x1800140d4  sub     rsp, 1E0h
0x1800140db  mov     rax, cs:__security_cookie
0x1800140e2  xor     rax, rsp
0x1800140e5  mov     [rbp+110h+var_38], rax
0x1800140ec  mov     rdi, rdx
0x1800140ef  mov     [rbp+110h+var_180], rdx
0x1800140f3  mov     r13, rcx
0x1800140f6  mov     r9d, 1; unsigned __int16
0x1800140fc  mov     r8d, 406h; unsigned __int16
0x180014102  lea     rdx, aCdefragoperati_5; "CDefragOperation::_CreateVolumeForFileS"...
0x180014109  lea     rcx, [rsp+210h+var_1C8]; this
0x18001410e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180014113  nop
0x180014114  xor     esi, esi
0x180014116  mov     [rsp+210h+var_1D0], rsi
0x18001411b  lea     rax, qword_18006F470
0x180014122  mov     [rbp+110h+lpRootPathName], rax
0x180014126  mov     [rbp+110h+var_188], rsi
0x18001412a  mov     eax, 40Ch
0x18001412f  test    rdi, rdi
0x180014132  jz      loc_180014509
0x180014138  mov     [rdi], rsi
0x18001413b  mov     [rsp+210h+var_1C8], esi
0x18001413f  mov     [rsp+210h+var_1C4], ax
0x180014144  mov     r12, [r13+2B8h]
0x18001414b  test    r12, r12
0x18001414e  jnz     short loc_18001415D
0x180014150  mov     [rsp+210h+var_1C8], 80070057h
0x180014158  jmp     loc_18001423F
0x18001415d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180014161  inc     r14
0x180014164  cmp     [r12+r14*2], si
0x180014169  jnz     short loc_180014161
0x18001416b  mov     r15d, esi
0x18001416e  test    r14d, r14d
0x180014171  jz      loc_180014235
0x180014177  lea     edx, [r14+1]; unsigned int
0x18001417b  lea     rcx, [rbp+110h+lpRootPathName]; this
0x18001417f  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180014184  mov     r15d, eax
0x180014187  test    eax, eax
0x180014189  js      loc_180014235
0x18001418f  mov     esi, dword ptr [rbp+110h+var_188]
0x180014192  mov     rcx, [rbp+110h+lpRootPathName]
0x180014196  lea     rdi, [rcx+rsi*2]
0x18001419a  mov     ecx, r14d
0x18001419d  lea     rbx, [rcx+rcx]
0x1800141a1  mov     r8, rbx; Size
0x1800141a4  mov     rdx, r12; Src
0x1800141a7  mov     rcx, rdi; void *
0x1800141aa  call    memcpy_0
0x1800141af  xor     ecx, ecx
0x1800141b1  mov     [rbx+rdi], cx
0x1800141b5  add     esi, r14d
0x1800141b8  mov     dword ptr [rbp+110h+var_188], esi
0x1800141bb  mov     [rsp+210h+var_1C8], r15d
0x1800141c0  mov     rdi, [rbp+110h+var_180]
0x1800141c4  xor     esi, esi
0x1800141c6  mov     eax, 40Eh
0x1800141cb  mov     [rsp+210h+var_1C4], ax
0x1800141d0  lea     rcx, [rbp+110h+lpRootPathName]; this
0x1800141d4  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x1800141d9  mov     [rsp+210h+var_1C8], eax
0x1800141dd  test    eax, eax
0x1800141df  mov     eax, 40Fh
0x1800141e4  js      loc_180014511
0x1800141ea  mov     [rsp+210h+var_1C4], ax
0x1800141ef  mov     [rsp+210h+nFileSystemNameSize], 0Ah; nFileSystemNameSize
0x1800141f7  lea     rax, [rbp+110h+FileSystemNameBuffer]
0x1800141fe  mov     [rsp+210h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x180014203  mov     [rsp+210h+lpFileSystemFlags], rsi; lpFileSystemFlags
0x180014208  mov     [rsp+210h+lpMaximumComponentLength], rsi; lpMaximumComponentLength
0x18001420d  xor     r9d, r9d; lpVolumeSerialNumber
0x180014210  xor     r8d, r8d; nVolumeNameSize
0x180014213  xor     edx, edx; lpVolumeNameBuffer
0x180014215  mov     rcx, [rbp+110h+lpRootPathName]; lpRootPathName
0x180014219  call    cs:__imp_GetVolumeInformationW
0x18001421f  test    eax, eax
0x180014221  jnz     short loc_180014249
0x180014223  mov     [rsp+210h+var_1C8], 8900000Dh
0x18001422b  mov     eax, 41Eh
0x180014230  jmp     loc_180014511
0x180014235  mov     [rsp+210h+var_1C8], r15d
0x18001423a  test    r15d, r15d
0x18001423d  jns     short loc_1800141C6
0x18001423f  mov     eax, 40Eh
0x180014244  jmp     loc_180014511
0x180014249  lea     rdx, aCsvfs; "CSVFS"
0x180014250  lea     rcx, [rbp+110h+FileSystemNameBuffer]; String1
0x180014257  call    cs:__imp__wcsicmp
0x18001425d  test    eax, eax
0x18001425f  jnz     loc_1800143D5
0x180014265  lea     rcx, [rbp+110h+var_178]; this
0x180014269  call    ??0CFileSystemControl@@QEAA@XZ; CFileSystemControl::CFileSystemControl(void)
0x18001426e  mov     dword ptr [rbp+110h+var_150.VolumeSerialNumber], esi
0x180014271  xor     edx, edx; Val
0x180014273  lea     r8d, [rdx+5Ch]; Size
0x180014277  lea     rcx, [rbp+110h+var_150.VolumeSerialNumber+4]; void *
0x18001427b  call    memset_0
0x180014280  xor     edx, edx; Val
0x180014282  mov     r8d, 98h; Size
0x180014288  lea     rcx, [rbp+110h+var_F0]; void *
0x18001428c  call    memset_0
0x180014291  nop
0x180014292  mov     [rsp+210h+lpFileSystemNameBuffer], rsi; hTemplateFile
0x180014297  mov     dword ptr [rsp+210h+lpFileSystemFlags], 20000080h; dwFlagsAndAttributes
0x18001429f  mov     r8d, 3; dwShareMode
0x1800142a5  mov     dword ptr [rsp+210h+lpMaximumComponentLength], r8d; dwCreationDisposition
0x1800142aa  xor     r9d, r9d; lpSecurityAttributes
0x1800142ad  mov     edx, 0C0000000h; dwDesiredAccess
0x1800142b2  mov     rcx, [r13+2B8h]; lpFileName
0x1800142b9  call    cs:__imp_CreateFileW
0x1800142bf  mov     rbx, rax
0x1800142c2  mov     [rbp+110h+var_180], rax
0x1800142c6  lea     rcx, [rax+1]
0x1800142ca  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1800142d1  jnz     short loc_180014302
0x1800142d3  call    GetLastFailureAsHRESULT
0x1800142d8  mov     [rsp+210h+var_1C8], eax
0x1800142dc  mov     eax, 43Bh
0x1800142e1  mov     [rsp+210h+var_1C2], ax
0x1800142e6  lea     rcx, [rbx-1]
0x1800142ea  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800142ee  ja      loc_180014516
0x1800142f4  mov     rcx, rbx; hObject
0x1800142f7  call    cs:__imp_CloseHandle
0x1800142fd  jmp     loc_180014516
0x180014302  mov     [rsp+210h+var_1C8], esi
0x180014306  mov     eax, 43Bh
0x18001430b  mov     [rsp+210h+var_1C4], ax
0x180014310  lea     r8, [rbp+110h+var_150]; struct NTFS_VOLUME_DATA_BUFFER *
0x180014314  mov     rdx, rbx; void *
0x180014317  lea     rcx, [rbp+110h+var_178]; this
0x18001431b  call    ?GetNtfsVolumeData@CFileSystemControl@@UEAAJPEAXAEAUNTFS_VOLUME_DATA_BUFFER@@@Z; CFileSystemControl::GetNtfsVolumeData(void *,NTFS_VOLUME_DATA_BUFFER &)
0x180014320  test    eax, eax
0x180014322  js      short loc_180014365
0x180014324  mov     rcx, [rsp+210h+var_1D0]
0x180014329  test    rcx, rcx
0x18001432c  jz      short loc_180014340
0x18001432e  mov     [rsp+210h+var_1D0], rsi
0x180014333  mov     rax, [rcx]
0x180014336  mov     rax, [rax+10h]
0x18001433a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001433f  nop
0x180014340  lea     rdx, [rsp+210h+var_1D0]; struct IVolume **
0x180014345  mov     rcx, [r13+2B8h]; unsigned __int16 *
0x18001434c  call    ?CreateInstance@CCsvfsNtfsVolume@@SAJPEAGPEAPEAUIVolume@@@Z; CCsvfsNtfsVolume::CreateInstance(ushort *,IVolume * *)
0x180014351  mov     [rsp+210h+var_1C8], eax
0x180014355  test    eax, eax
0x180014357  mov     eax, 43Eh
0x18001435c  jns     short loc_1800143B3
0x18001435e  mov     [rsp+210h+var_1C2], ax
0x180014363  jmp     short loc_1800142F4
0x180014365  lea     r8, [rbp+110h+var_F0]; struct REFS_VOLUME_DATA_BUFFER *
0x180014369  mov     rdx, rbx; void *
0x18001436c  lea     rcx, [rbp+110h+var_178]; this
0x180014370  call    ?GetRefsVolumeData@CFileSystemControl@@UEAAJPEAXAEAUREFS_VOLUME_DATA_BUFFER@@@Z; CFileSystemControl::GetRefsVolumeData(void *,REFS_VOLUME_DATA_BUFFER &)
0x180014375  test    eax, eax
0x180014377  js      short loc_1800143C6
0x180014379  mov     rcx, [rsp+210h+var_1D0]
0x18001437e  test    rcx, rcx
0x180014381  jz      short loc_180014395
0x180014383  mov     [rsp+210h+var_1D0], rsi
0x180014388  mov     rax, [rcx]
0x18001438b  mov     rax, [rax+10h]
0x18001438f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014394  nop
0x180014395  lea     rdx, [rsp+210h+var_1D0]; struct IVolume **
0x18001439a  mov     rcx, [r13+2B8h]; unsigned __int16 *
0x1800143a1  call    ?CreateInstance@CCsvfsRefsVolume@@SAJPEAGPEAPEAUIVolume@@@Z; CCsvfsRefsVolume::CreateInstance(ushort *,IVolume * *)
0x1800143a6  mov     [rsp+210h+var_1C8], eax
0x1800143aa  test    eax, eax
0x1800143ac  mov     eax, 440h
0x1800143b1  jmp     short loc_18001435C
0x1800143b3  mov     [rsp+210h+var_1C4], ax
0x1800143b8  mov     rcx, rbx; hObject
0x1800143bb  call    cs:__imp_CloseHandle
0x1800143c1  jmp     loc_1800144FA
0x1800143c6  mov     [rsp+210h+var_1C8], 89000020h
0x1800143ce  mov     eax, 442h
0x1800143d3  jmp     short loc_18001435E
0x1800143d5  lea     rdx, aNtfs; "NTFS"
0x1800143dc  lea     rcx, [rbp+110h+FileSystemNameBuffer]; String1
0x1800143e3  call    cs:__imp__wcsicmp
0x1800143e9  test    eax, eax
0x1800143eb  jnz     short loc_18001442A
0x1800143ed  mov     rcx, [rsp+210h+var_1D0]
0x1800143f2  test    rcx, rcx
0x1800143f5  jz      short loc_180014409
0x1800143f7  mov     [rsp+210h+var_1D0], rsi
0x1800143fc  mov     rax, [rcx]
0x1800143ff  mov     rax, [rax+10h]
0x180014403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014408  nop
0x180014409  lea     rdx, [rsp+210h+var_1D0]; struct IVolume **
0x18001440e  mov     rcx, [r13+2B8h]; unsigned __int16 *
0x180014415  call    ?CreateInstance@CNtfsVolume@@SAJPEAGPEAPEAUIVolume@@@Z; CNtfsVolume::CreateInstance(ushort *,IVolume * *)
0x18001441a  mov     [rsp+210h+var_1C8], eax
0x18001441e  test    eax, eax
0x180014420  mov     eax, 447h
0x180014425  jmp     loc_1800144F3
0x18001442a  lea     rdx, aFat32; "FAT32"
0x180014431  lea     rcx, [rbp+110h+FileSystemNameBuffer]; String1
0x180014438  call    cs:__imp__wcsicmp
0x18001443e  test    eax, eax
0x180014440  jz      short loc_1800144BB
0x180014442  lea     rdx, aFat; "FAT"
0x180014449  lea     rcx, [rbp+110h+FileSystemNameBuffer]; String1
0x180014450  call    cs:__imp__wcsicmp
0x180014456  test    eax, eax
0x180014458  jz      short loc_1800144BB
0x18001445a  lea     rdx, aRefs; "REFS"
0x180014461  lea     rcx, [rbp+110h+FileSystemNameBuffer]; String1
0x180014468  call    cs:__imp__wcsicmp
0x18001446e  test    eax, eax
0x180014470  jnz     short loc_1800144AC
0x180014472  mov     rcx, [rsp+210h+var_1D0]
0x180014477  test    rcx, rcx
0x18001447a  jz      short loc_18001448E
0x18001447c  mov     [rsp+210h+var_1D0], rsi
0x180014481  mov     rax, [rcx]
0x180014484  mov     rax, [rax+10h]
0x180014488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001448d  nop
0x18001448e  lea     rdx, [rsp+210h+var_1D0]; struct IVolume **
0x180014493  mov     rcx, [r13+2B8h]; unsigned __int16 *
0x18001449a  call    ?CreateInstance@CReFsVolume@@SAJPEAGPEAPEAUIVolume@@@Z; CReFsVolume::CreateInstance(ushort *,IVolume * *)
0x18001449f  mov     [rsp+210h+var_1C8], eax
0x1800144a3  test    eax, eax
0x1800144a5  mov     eax, 450h
0x1800144aa  jmp     short loc_1800144F3
0x1800144ac  mov     [rsp+210h+var_1C8], 8900000Dh
0x1800144b4  mov     eax, 456h
0x1800144b9  jmp     short loc_180014511
0x1800144bb  mov     rcx, [rsp+210h+var_1D0]
0x1800144c0  test    rcx, rcx
0x1800144c3  jz      short loc_1800144D7
0x1800144c5  mov     [rsp+210h+var_1D0], rsi
0x1800144ca  mov     rax, [rcx]
0x1800144cd  mov     rax, [rax+10h]
0x1800144d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144d6  nop
0x1800144d7  lea     rdx, [rsp+210h+var_1D0]; struct IVolume **
0x1800144dc  mov     rcx, [r13+2B8h]; unsigned __int16 *
0x1800144e3  call    ?CreateInstance@CFatVolume@@SAJPEAGPEAPEAUIVolume@@@Z; CFatVolume::CreateInstance(ushort *,IVolume * *)
0x1800144e8  mov     [rsp+210h+var_1C8], eax
0x1800144ec  test    eax, eax
0x1800144ee  mov     eax, 44Ch
0x1800144f3  js      short loc_180014511
0x1800144f5  mov     [rsp+210h+var_1C4], ax
0x1800144fa  mov     rax, [rsp+210h+var_1D0]
0x1800144ff  mov     [rdi], rax
0x180014502  mov     [rsp+210h+var_1D0], rsi
0x180014507  jmp     short loc_180014516
0x180014509  mov     [rsp+210h+var_1C8], 80070057h
0x180014511  mov     [rsp+210h+var_1C2], ax
0x180014516  mov     ebx, [rsp+210h+var_1C8]
0x18001451a  mov     rcx, [rbp+110h+lpRootPathName]; unsigned __int16 *
0x18001451e  call    ?_FreeData@CBsString@@CAXPEAGK@Z; CBsString::_FreeData(ushort *,ulong)
0x180014523  nop
0x180014524  mov     rcx, [rsp+210h+var_1D0]
0x180014529  test    rcx, rcx
0x18001452c  jz      short loc_180014540
0x18001452e  mov     [rsp+210h+var_1D0], rsi
0x180014533  mov     rdx, [rcx]
0x180014536  mov     rax, [rdx+10h]
0x18001453a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001453f  nop
0x180014540  lea     rcx, [rsp+210h+var_1C8]; this
0x180014545  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001454a  mov     eax, ebx
0x18001454c  mov     rcx, [rbp+110h+var_38]
0x180014553  xor     rcx, rsp; StackCookie
0x180014556  call    __security_check_cookie
0x18001455b  mov     rbx, [rsp+210h+arg_10]
0x180014563  add     rsp, 1E0h
0x18001456a  pop     r15
0x18001456c  pop     r14
0x18001456e  pop     r13
0x180014570  pop     r12
0x180014572  pop     rdi
0x180014573  pop     rsi
0x180014574  pop     rbp
0x180014575  retn
```
