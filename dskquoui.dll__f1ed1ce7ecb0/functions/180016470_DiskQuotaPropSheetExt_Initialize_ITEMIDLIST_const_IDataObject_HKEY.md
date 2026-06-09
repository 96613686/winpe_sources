# DiskQuotaPropSheetExt::Initialize(_ITEMIDLIST const *,IDataObject *,HKEY__ *)

- ea: `0x180016470`
- end: `0x18001684c`
- name: `?Initialize@DiskQuotaPropSheetExt@@UEAAJPEFBU_ITEMIDLIST@@PEAUIDataObject@@PEAUHKEY__@@@Z`
- size: `988`
- prototype: `__int64 __fastcall(DiskQuotaPropSheetExt *__hidden this, const struct _ITEMIDLIST *, struct IDataObject *, HKEY)`
- caller_count: `0`
- callee_count: `14`
- tags: `reparse_path, loader_planting`

## callees

- `0x180001510`
- `0x1800022b4`
- `0x180016470`
- `0x180019dd0`
- `0x180019ee0`
- `0x180019f38`
- `0x180019fb0`
- `0x18001a468`
- `0x18001a5f0`
- `0x18001a6c8`
- `0x18001a708`
- `0x18001a73c`
- `0x18001a888`
- `0x18001f010`

## import_xrefs

- `SHELL32!DragQueryFileW` at `0x180016582`
- `SHELL32!DragQueryFileW` at `0x1800165ae`
- `SHELL32!DragQueryFileW` at `0x180016582`
- `SHELL32!DragQueryFileW` at `0x1800165ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001662f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001662f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167e6`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800166ae`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800166ae`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001670c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001670c`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180016611`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180016611`
- `KERNEL32!lstrcmpW` at `0x1800167cb`
- `KERNEL32!lstrcmpW` at `0x1800167cb`
- `ole32!ReleaseStgMedium` at `0x1800165d4`
- `ole32!ReleaseStgMedium` at `0x1800165d4`
- `USER32!RegisterClipboardFormatW` at `0x180016538`
- `USER32!RegisterClipboardFormatW` at `0x180016538`

## string_xrefs

- `0x180016531`: `MountedVolume`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DiskQuotaPropSheetExt::Initialize(
        DiskQuotaPropSheetExt *this,
        const struct _ITEMIDLIST *a2,
        struct IDataObject *a3,
        HKEY a4)
{
  signed int v6; // edi
  unsigned int v7; // r14d
  char v8; // bl
  WCHAR *Buffer; // rax
  signed int LastError; // eax
  unsigned int v11; // esi
  const WCHAR *i; // rcx
  const WCHAR *v13; // rbx
  unsigned int v14; // eax
  __int64 v15; // r8
  __int64 v16; // rax
  signed int v17; // eax
  DWORD FileSystemFlags; // [rsp+40h] [rbp-2F8h] BYREF
  char v20[8]; // [rsp+48h] [rbp-2F0h] BYREF
  LPCWSTR *v21; // [rsp+50h] [rbp-2E8h]
  __int16 v22; // [rsp+58h] [rbp-2E0h] BYREF
  int v23; // [rsp+5Ah] [rbp-2DEh]
  __int16 v24; // [rsp+5Eh] [rbp-2DAh]
  LPCWSTR *v25; // [rsp+60h] [rbp-2D8h]
  int v26; // [rsp+68h] [rbp-2D0h]
  int v27; // [rsp+6Ch] [rbp-2CCh]
  __int64 v28; // [rsp+70h] [rbp-2C8h]
  char v29[8]; // [rsp+78h] [rbp-2C0h] BYREF
  LPCWSTR *v30; // [rsp+80h] [rbp-2B8h]
  STGMEDIUM hDrop; // [rsp+88h] [rbp-2B0h] BYREF
  WCHAR VolumeNameBuffer[40]; // [rsp+A0h] [rbp-298h] BYREF
  WCHAR szVolumeName[264]; // [rsp+F0h] [rbp-248h] BYREF

  try
  {
    v6 = -2147467259;
    CString::CString((CString *)v29);
    CString::CString((CString *)v20);
    if ( a3 )
    {
      v22 = 15;
      v23 = 0;
      v24 = 0;
      v25 = 0;
      v26 = 1;
      v7 = -1;
      v27 = -1;
      v28 = 1;
      memset(&hDrop, 0, sizeof(hDrop));
      v6 = ((__int64 (__fastcall *)(struct IDataObject *, __int16 *, STGMEDIUM *))a3->lpVtbl->GetData)(a3, &v22, &hDrop);
      if ( v6 >= 0 )
      {
        v8 = 0;
LABEL_7:
        if ( DragQueryFileW((HDROP)hDrop.hBitmap, 0xFFFFFFFF, 0, 0) == 1 )
        {
          Buffer = CString::GetBuffer((CString *)v20, 260);
          DragQueryFileW((HDROP)hDrop.hBitmap, 0, Buffer, 0x104u);
          CString::ReleaseBuffer((CString *)v20);
        }
        else
        {
          v6 = -2147024846;
        }
        ReleaseStgMedium(&hDrop);
        if ( v6 >= 0 )
        {
          if ( v8 )
          {
            memset_0(szVolumeName, 0, 0x208u);
            if ( GetVolumeNameForVolumeMountPointW(*v21, szVolumeName, 0x104u) )
            {
              CString::operator=(v29, szVolumeName);
            }
            else
            {
              LastError = GetLastError();
              v6 = LastError;
              if ( LastError > 0 )
                v6 = (unsigned __int16)LastError | 0x80070000;
              if ( v6 >= 0 )
                v6 = -2147467259;
            }
          }
          else
          {
            CString::operator=(v29, v20);
          }
          if ( v6 >= 0 )
          {
            memset_0(VolumeNameBuffer, 0, 0x42u);
            FileSystemFlags = 0;
            if ( GetVolumeInformationW(*v30, VolumeNameBuffer, 0x21u, 0, 0, &FileSystemFlags, 0, 0) )
            {
              if ( (FileSystemFlags & 0x20) == 0 )
                v6 = -2147024846;
              if ( v6 >= 0 )
              {
                CString::CString((CString *)&v22);
                if ( !(unsigned int)CString::IsEmpty((CString *)v20) )
                {
                  v11 = 0;
                  for ( i = *v21; i && *i; v11 += i - v13 )
                  {
                    v13 = i;
                    v14 = v11;
                    if ( *i != 92 )
                      v14 = v7;
                    v7 = v14;
                    i = CharNextW(i);
                  }
                  if ( v7 == (unsigned int)CString::Length((CString *)v20) - 1 )
                  {
                    v16 = CString::SubString(v20, &hDrop, v15, v7);
                    CString::operator=(v20, v16);
                    CString::~CString((CString *)&hDrop);
                  }
                }
                CString::Format((CString *)&v22, g_hInstDll, 0x9EBCu, VolumeNameBuffer, *v21);
                CString::operator=((char *)this + 16, v29);
                CString::operator=((char *)this + 48, v20);
                CString::operator=((char *)this + 32, &v22);
                *((_BYTE *)this + 64) = lstrcmpW(*v30, *v25) != 0;
                CString::~CString((CString *)&v22);
              }
            }
            else
            {
              v17 = GetLastError();
              v6 = v17;
              if ( v17 > 0 )
                v6 = (unsigned __int16)v17 | 0x80070000;
              if ( v6 >= 0 )
                v6 = -2147467259;
            }
          }
        }
        goto LABEL_39;
      }
      v22 = RegisterClipboardFormatW(L"MountedVolume");
      v6 = ((__int64 (__fastcall *)(struct IDataObject *, __int16 *, STGMEDIUM *))a3->lpVtbl->GetData)(a3, &v22, &hDrop);
      if ( v6 >= 0 )
      {
        v8 = 1;
        goto LABEL_7;
      }
    }
LABEL_39:
    CString::~CString((CString *)v20);
    CString::~CString((CString *)v29);
  }
  catch ( CAllocException )
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016470  mov     [rsp+arg_8], rbx
0x180016475  mov     [rsp+arg_18], rsi
0x18001647a  push    rdi
0x18001647b  push    r12
0x18001647d  push    r13
0x18001647f  push    r14
0x180016481  push    r15
0x180016483  sub     rsp, 310h
0x18001648a  mov     rax, cs:__security_cookie
0x180016491  xor     rax, rsp
0x180016494  mov     [rsp+338h+var_38], rax
0x18001649c  mov     rbx, r8
0x18001649f  mov     r15, rcx
0x1800164a2  mov     r13d, 80004005h
0x1800164a8  mov     edi, r13d
0x1800164ab  lea     rcx, [rsp+338h+var_2C0]; this
0x1800164b0  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x1800164b5  nop
0x1800164b6  lea     rcx, [rsp+338h+var_2F0]; this
0x1800164bb  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x1800164c0  nop
0x1800164c1  xor     r12d, r12d
0x1800164c4  test    rbx, rbx
0x1800164c7  jz      loc_180016801
0x1800164cd  lea     eax, [r12+0Fh]
0x1800164d2  mov     [rsp+338h+var_2E0], ax
0x1800164d7  xor     eax, eax
0x1800164d9  mov     [rsp+338h+var_2DE], eax
0x1800164dd  mov     [rsp+338h+var_2DA], ax
0x1800164e2  mov     [rsp+338h+var_2D8], r12
0x1800164e7  lea     esi, [rax+1]
0x1800164ea  mov     [rsp+338h+var_2D0], esi
0x1800164ee  or      r14d, 0FFFFFFFFh
0x1800164f2  mov     [rsp+338h+var_2CC], r14d
0x1800164f7  mov     [rsp+338h+var_2C8], rsi
0x1800164fc  xorps   xmm0, xmm0
0x1800164ff  movups  xmmword ptr [rsp+338h+hDrop], xmm0
0x180016507  mov     [rsp+338h+var_2A0], rax
0x18001650f  mov     rax, [rbx]
0x180016512  lea     r8, [rsp+338h+hDrop]
0x18001651a  lea     rdx, [rsp+338h+var_2E0]
0x18001651f  mov     rcx, rbx
0x180016522  mov     rax, [rax+18h]
0x180016526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001652b  mov     edi, eax
0x18001652d  test    eax, eax
0x18001652f  jns     short loc_18001656E
0x180016531  lea     rcx, aMountedvolume; "MountedVolume"
0x180016538  call    cs:__imp_RegisterClipboardFormatW
0x18001653e  mov     [rsp+338h+var_2E0], ax
0x180016543  mov     rax, [rbx]
0x180016546  lea     r8, [rsp+338h+hDrop]
0x18001654e  lea     rdx, [rsp+338h+var_2E0]
0x180016553  mov     rcx, rbx
0x180016556  mov     rax, [rax+18h]
0x18001655a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001655f  mov     edi, eax
0x180016561  test    eax, eax
0x180016563  js      loc_180016801
0x180016569  mov     bl, sil
0x18001656c  jmp     short loc_180016571
0x18001656e  mov     bl, r12b
0x180016571  xor     r9d, r9d; cch
0x180016574  xor     r8d, r8d; lpszFile
0x180016577  or      edx, 0FFFFFFFFh; iFile
0x18001657a  mov     rcx, [rsp+338h+hDrop+8]; hDrop
0x180016582  call    cs:__imp_DragQueryFileW
0x180016588  cmp     eax, esi
0x18001658a  jnz     short loc_1800165C5
0x18001658c  mov     edx, 104h; int
0x180016591  lea     rcx, [rsp+338h+var_2F0]; this
0x180016596  call    ?GetBuffer@CString@@QEAAPEAGH@Z; CString::GetBuffer(int)
0x18001659b  mov     r9d, 104h; cch
0x1800165a1  mov     r8, rax; lpszFile
0x1800165a4  xor     edx, edx; iFile
0x1800165a6  mov     rcx, [rsp+338h+hDrop+8]; hDrop
0x1800165ae  call    cs:__imp_DragQueryFileW
0x1800165b4  lea     rcx, [rsp+338h+var_2F0]; this
0x1800165b9  call    ?ReleaseBuffer@CString@@QEAAXXZ; CString::ReleaseBuffer(void)
0x1800165be  mov     esi, 80070032h
0x1800165c3  jmp     short loc_1800165CC
0x1800165c5  mov     esi, 80070032h
0x1800165ca  mov     edi, esi
0x1800165cc  lea     rcx, [rsp+338h+hDrop]; LPSTGMEDIUM
0x1800165d4  call    cs:__imp_ReleaseStgMedium
0x1800165da  test    edi, edi
0x1800165dc  js      loc_180016801
0x1800165e2  test    bl, bl
0x1800165e4  jz      short loc_18001664C
0x1800165e6  xor     edx, edx; Val
0x1800165e8  mov     r8d, 208h; Size
0x1800165ee  lea     rcx, [rsp+338h+szVolumeName]; void *
0x1800165f6  call    memset_0
0x1800165fb  mov     r8d, 104h; cchBufferLength
0x180016601  lea     rdx, [rsp+338h+szVolumeName]; lpszVolumeName
0x180016609  mov     rcx, [rsp+338h+var_2E8]
0x18001660e  mov     rcx, [rcx]; lpszVolumeMountPoint
0x180016611  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180016617  test    eax, eax
0x180016619  jz      short loc_18001662F
0x18001661b  lea     rdx, [rsp+338h+szVolumeName]
0x180016623  lea     rcx, [rsp+338h+var_2C0]
0x180016628  call    ??4CString@@QEAAAEAV0@PEBG@Z; CString::operator=(ushort const *)
0x18001662d  jmp     short loc_18001665B
0x18001662f  call    cs:__imp_GetLastError
0x180016635  mov     edi, eax
0x180016637  test    eax, eax
0x180016639  jle     short loc_180016644
0x18001663b  movzx   edi, ax
0x18001663e  or      edi, 80070000h
0x180016644  test    edi, edi
0x180016646  cmovns  edi, r13d
0x18001664a  jmp     short loc_18001665B
0x18001664c  lea     rdx, [rsp+338h+var_2F0]
0x180016651  lea     rcx, [rsp+338h+var_2C0]
0x180016656  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x18001665b  test    edi, edi
0x18001665d  js      loc_180016801
0x180016663  xor     edx, edx; Val
0x180016665  lea     r8d, [rdx+42h]; Size
0x180016669  lea     rcx, [rsp+338h+VolumeNameBuffer]; void *
0x180016671  call    memset_0
0x180016676  mov     [rsp+338h+FileSystemFlags], r12d
0x18001667b  mov     [rsp+338h+nFileSystemNameSize], r12d; nFileSystemNameSize
0x180016680  mov     [rsp+338h+lpFileSystemNameBuffer], r12; lpFileSystemNameBuffer
0x180016685  lea     rax, [rsp+338h+FileSystemFlags]
0x18001668a  mov     [rsp+338h+lpFileSystemFlags], rax; lpFileSystemFlags
0x18001668f  mov     [rsp+338h+lpMaximumComponentLength], r12; lpMaximumComponentLength
0x180016694  xor     r9d, r9d; lpVolumeSerialNumber
0x180016697  lea     r8d, [r9+21h]; nVolumeNameSize
0x18001669b  lea     rdx, [rsp+338h+VolumeNameBuffer]; lpVolumeNameBuffer
0x1800166a3  mov     rcx, [rsp+338h+var_2B8]
0x1800166ab  mov     rcx, [rcx]; lpRootPathName
0x1800166ae  call    cs:__imp_GetVolumeInformationW
0x1800166b4  test    eax, eax
0x1800166b6  jz      loc_1800167E6
0x1800166bc  test    byte ptr [rsp+338h+FileSystemFlags], 20h
0x1800166c1  cmovz   edi, esi
0x1800166c4  test    edi, edi
0x1800166c6  js      loc_180016801
0x1800166cc  lea     rcx, [rsp+338h+var_2E0]; this
0x1800166d1  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x1800166d6  nop
0x1800166d7  lea     rcx, [rsp+338h+var_2F0]; this
0x1800166dc  call    ?IsEmpty@CString@@QEBAHXZ; CString::IsEmpty(void)
0x1800166e1  test    eax, eax
0x1800166e3  jnz     short loc_180016762
0x1800166e5  mov     esi, r12d
0x1800166e8  mov     rax, [rsp+338h+var_2E8]
0x1800166ed  mov     rcx, [rax]
0x1800166f0  jmp     short loc_18001671D
0x1800166f2  cmp     [rcx], r12w
0x1800166f6  jz      short loc_180016722
0x1800166f8  mov     rbx, rcx
0x1800166fb  mov     edx, 5Ch ; '\'
0x180016700  mov     eax, esi
0x180016702  cmp     dx, [rcx]
0x180016705  cmovnz  eax, r14d
0x180016709  mov     r14d, eax
0x18001670c  call    cs:__imp_CharNextW
0x180016712  mov     rcx, rax; lpsz
0x180016715  sub     rax, rbx
0x180016718  sar     rax, 1
0x18001671b  add     esi, eax
0x18001671d  test    rcx, rcx
0x180016720  jnz     short loc_1800166F2
0x180016722  lea     rcx, [rsp+338h+var_2F0]; this
0x180016727  call    ?Length@CString@@QEBAHXZ; CString::Length(void)
0x18001672c  dec     eax
0x18001672e  cmp     r14d, eax
0x180016731  jnz     short loc_180016762
0x180016733  mov     r9d, r14d
0x180016736  lea     rdx, [rsp+338h+hDrop]
0x18001673e  lea     rcx, [rsp+338h+var_2F0]
0x180016743  call    ?SubString@CString@@QEAA?AV1@HH@Z; CString::SubString(int,int)
0x180016748  mov     rdx, rax
0x18001674b  lea     rcx, [rsp+338h+var_2F0]
0x180016750  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x180016755  lea     rcx, [rsp+338h+hDrop]; this
0x18001675d  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180016762  mov     rax, [rsp+338h+var_2E8]
0x180016767  mov     rcx, [rax]
0x18001676a  mov     [rsp+338h+lpMaximumComponentLength], rcx
0x18001676f  lea     r9, [rsp+338h+VolumeNameBuffer]
0x180016777  mov     r8d, 9EBCh; unsigned int
0x18001677d  mov     rdx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180016784  lea     rcx, [rsp+338h+var_2E0]; this
0x180016789  call    ?Format@CString@@QEAAHPEAUHINSTANCE__@@IZZ; CString::Format(HINSTANCE__ *,uint,...)
0x18001678e  lea     rdx, [rsp+338h+var_2C0]
0x180016793  lea     rcx, [r15+10h]
0x180016797  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x18001679c  lea     rcx, [r15+30h]
0x1800167a0  lea     rdx, [rsp+338h+var_2F0]
0x1800167a5  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x1800167aa  lea     rcx, [r15+20h]
0x1800167ae  lea     rdx, [rsp+338h+var_2E0]
0x1800167b3  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x1800167b8  mov     rdx, [rsp+338h+var_2D8]
0x1800167bd  mov     rdx, [rdx]; lpString2
0x1800167c0  mov     rcx, [rsp+338h+var_2B8]
0x1800167c8  mov     rcx, [rcx]; lpString1
0x1800167cb  call    cs:__imp_lstrcmpW
0x1800167d1  test    eax, eax
0x1800167d3  setnz   al
0x1800167d6  mov     [r15+40h], al
0x1800167da  lea     rcx, [rsp+338h+var_2E0]; this
0x1800167df  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x1800167e4  jmp     short loc_180016801
0x1800167e6  call    cs:__imp_GetLastError
0x1800167ec  mov     edi, eax
0x1800167ee  test    eax, eax
0x1800167f0  jle     short loc_1800167FB
0x1800167f2  movzx   edi, ax
0x1800167f5  or      edi, 80070000h
0x1800167fb  test    edi, edi
0x1800167fd  cmovns  edi, r13d
0x180016801  lea     rcx, [rsp+338h+var_2F0]; this
0x180016806  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18001680b  nop
0x18001680c  lea     rcx, [rsp+338h+var_2C0]; this
0x180016811  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180016816  nop
0x180016817  jmp     short loc_18001681D
0x180016819  mov     edi, [rsp+338h+FileSystemFlags]
0x18001681d  mov     eax, edi
0x18001681f  mov     rcx, [rsp+338h+var_38]
0x180016827  xor     rcx, rsp; StackCookie
0x18001682a  call    __security_check_cookie
0x18001682f  lea     r11, [rsp+338h+var_28]
0x180016837  mov     rbx, [r11+38h]
0x18001683b  mov     rsi, [r11+48h]
0x18001683f  mov     rsp, r11
0x180016842  pop     r15
0x180016844  pop     r14
0x180016846  pop     r13
0x180016848  pop     r12
0x18001684a  pop     rdi
0x18001684b  retn
```
