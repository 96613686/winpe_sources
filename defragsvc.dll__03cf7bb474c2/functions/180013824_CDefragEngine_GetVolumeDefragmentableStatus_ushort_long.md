# CDefragEngine::_GetVolumeDefragmentableStatus(ushort *,long *)

- ea: `0x180013824`
- end: `0x180013adf`
- name: `?_GetVolumeDefragmentableStatus@CDefragEngine@@AEAAJPEAGPEAJ@Z`
- size: `699`
- prototype: `__int64 __fastcall(CDefragEngine *this, unsigned __int16 *, int *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180012cc8`
- `0x18001727c`
- `0x18004275c`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180013824`
- `0x1800157fc`
- `0x180017e34`
- `0x18001913c`
- `0x18003b0e8`
- `0x18004006c`
- `0x180042470`
- `0x180067b30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180013a0a`
- `msvcrt!_wcsicmp` at `0x180013a1f`
- `msvcrt!_wcsicmp` at `0x180013a34`
- `msvcrt!_wcsicmp` at `0x180013a49`
- `msvcrt!_wcsicmp` at `0x180013a5e`
- `msvcrt!_wcsicmp` at `0x180013a0a`
- `msvcrt!_wcsicmp` at `0x180013a1f`
- `msvcrt!_wcsicmp` at `0x180013a34`
- `msvcrt!_wcsicmp` at `0x180013a49`
- `msvcrt!_wcsicmp` at `0x180013a5e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001393e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001393e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013956`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013aa9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013aa9`

## pseudocode

```c
__int64 __fastcall CDefragEngine::_GetVolumeDefragmentableStatus(CDefragEngine *this, unsigned __int16 *a2, int *a3)
{
  __int64 FileW; // rbx
  WCHAR *v6; // r14
  __int16 v7; // ax
  int VolumeDriveType; // edi
  unsigned __int16 v9; // dx
  __int64 v10; // rcx
  CDefragEngine *v11; // rcx
  __int16 v12; // ax
  CDefragEngine *v13; // rcx
  unsigned int v14; // r9d
  unsigned int v15; // edi
  unsigned int v17; // [rsp+40h] [rbp-39h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-31h] BYREF
  __int64 v19; // [rsp+50h] [rbp-29h]
  int v20; // [rsp+58h] [rbp-21h] BYREF
  __int16 v21; // [rsp+5Ch] [rbp-1Dh]
  __int16 v22; // [rsp+5Eh] [rbp-1Bh]
  __int64 v23; // [rsp+90h] [rbp+17h]
  wchar_t String1[12]; // [rsp+98h] [rbp+1Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v20,
    "CDefragEngine::_GetVolumeDefragmentableStatus",
    2679,
    1);
  v17 = 0;
  FileW = -1;
  v6 = (WCHAR *)&qword_18006F470;
  lpFileName = &qword_18006F470;
  v19 = 0;
  v7 = 2686;
  if ( !a2 )
  {
    VolumeDriveType = -2147024809;
LABEL_3:
    v20 = VolumeDriveType;
LABEL_4:
    v22 = v7;
    goto LABEL_34;
  }
  v20 = 0;
  v21 = 2686;
  *a3 = 0;
  VolumeDriveType = CBsString::Set((CBsString *)&lpFileName, a2);
  v20 = VolumeDriveType;
  if ( VolumeDriveType < 0 )
  {
    v22 = 2698;
    v6 = (WCHAR *)lpFileName;
    goto LABEL_34;
  }
  v21 = 2698;
  VolumeDriveType = CBsString::Trailing((CBsString *)&lpFileName, v9);
  v20 = VolumeDriveType;
  v6 = (WCHAR *)lpFileName;
  v7 = 2699;
  if ( VolumeDriveType < 0 )
    goto LABEL_4;
  v21 = 2699;
  v10 = (unsigned int)(v19 - 1);
  if ( (unsigned int)v10 < (unsigned int)v19 )
  {
    LODWORD(v19) = v19 - 1;
    lpFileName[v10] = 0;
  }
  FileW = (__int64)CreateFileW(v6, 0x80000000, 3u, 0, 3u, 0x2000000u, 0);
  v23 = FileW;
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( GetLastError() != 5 )
    {
      VolumeDriveType = -1996488703;
      v7 = 2720;
      goto LABEL_3;
    }
    v12 = 2716;
    goto LABEL_13;
  }
  if ( CDefragEngine::_CheckVolumeDirty(v11, (void *)FileW) == -1996488683 )
    *a3 = -1996488683;
  VolumeDriveType = CDefragEngine::_GetVolumeDriveType((CDefragEngine *)0x89000015LL, (void *)FileW, &v17);
  v20 = VolumeDriveType;
  v7 = 2732;
  if ( VolumeDriveType < 0 )
    goto LABEL_4;
  v21 = 2732;
  v15 = v17;
  if ( v17 == 4 )
  {
    *a3 = -1996488690;
    v12 = 2737;
    goto LABEL_14;
  }
  if ( v17 == 5 )
  {
    *a3 = -1996488689;
    v12 = 2743;
    goto LABEL_14;
  }
  if ( CDefragEngine::_GetVolumeFileSystemName(v13, (void *)FileW, String1, v14) < 0 )
  {
    v12 = 2755;
LABEL_13:
    *a3 = -1996488691;
LABEL_14:
    VolumeDriveType = 0;
    v20 = 0;
    v21 = v12;
    goto LABEL_34;
  }
  if ( _wcsicmp(String1, L"NTFS") && _wcsicmp(String1, L"REFS") && _wcsicmp(String1, L"CSVFS") )
  {
    if ( _wcsicmp(String1, L"FAT32") && _wcsicmp(String1, L"FAT") )
    {
      *a3 = -1996488657;
      v12 = 2772;
      goto LABEL_14;
    }
    if ( v15 - 2 > 1 )
    {
      *a3 = -1996488657;
      v12 = 2779;
      goto LABEL_14;
    }
  }
  VolumeDriveType = v20;
LABEL_34:
  CBsString::_FreeData(v6);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v20);
  return (unsigned int)VolumeDriveType;
}

```

## disassembly

```asm
0x180013824  mov     [rsp-8+arg_0], rbx
0x180013829  mov     [rsp-8+arg_18], rsi
0x18001382e  push    rbp
0x18001382f  push    rdi
0x180013830  push    r14
0x180013832  lea     rbp, [rsp-47h]
0x180013837  sub     rsp, 0C0h
0x18001383e  mov     rax, cs:__security_cookie
0x180013845  xor     rax, rsp
0x180013848  mov     [rbp+57h+var_20], rax
0x18001384c  mov     rsi, r8
0x18001384f  mov     rdi, rdx
0x180013852  mov     r9d, 1; unsigned __int16
0x180013858  mov     r8d, 0A77h; unsigned __int16
0x18001385e  lea     rdx, aCdefragengineG_8; "CDefragEngine::_GetVolumeDefragmentable"...
0x180013865  lea     rcx, [rbp+57h+var_78]; this
0x180013869  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001386e  nop
0x18001386f  mov     [rbp+57h+var_90], 0
0x180013876  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001387a  lea     r14, qword_18006F470
0x180013881  mov     [rbp+57h+lpFileName], r14
0x180013885  mov     [rbp+57h+var_80], 0
0x18001388d  mov     eax, 0A7Eh
0x180013892  test    rdi, rdi
0x180013895  jnz     short loc_1800138A8
0x180013897  mov     edi, 80070057h
0x18001389c  mov     [rbp+57h+var_78], edi
0x18001389f  mov     [rbp+57h+var_72], ax
0x1800138a3  jmp     loc_180013A93
0x1800138a8  mov     [rbp+57h+var_78], 0
0x1800138af  mov     [rbp+57h+var_74], ax
0x1800138b3  mov     dword ptr [rsi], 0
0x1800138b9  mov     rdx, rdi; unsigned __int16 *
0x1800138bc  lea     rcx, [rbp+57h+lpFileName]; this
0x1800138c0  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800138c5  mov     edi, eax
0x1800138c7  mov     [rbp+57h+var_78], eax
0x1800138ca  test    eax, eax
0x1800138cc  mov     eax, 0A8Ah
0x1800138d1  jns     short loc_1800138E0
0x1800138d3  mov     [rbp+57h+var_72], ax
0x1800138d7  mov     r14, [rbp+57h+lpFileName]
0x1800138db  jmp     loc_180013A93
0x1800138e0  mov     [rbp+57h+var_74], ax
0x1800138e4  lea     rcx, [rbp+57h+lpFileName]; this
0x1800138e8  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x1800138ed  mov     edi, eax
0x1800138ef  mov     [rbp+57h+var_78], eax
0x1800138f2  mov     r14, [rbp+57h+lpFileName]
0x1800138f6  test    eax, eax
0x1800138f8  mov     eax, 0A8Bh
0x1800138fd  js      short loc_18001389F
0x1800138ff  mov     [rbp+57h+var_74], ax
0x180013903  mov     eax, dword ptr [rbp+57h+var_80]
0x180013906  lea     ecx, [rax-1]
0x180013909  cmp     ecx, eax
0x18001390b  jnb     short loc_180013917
0x18001390d  mov     dword ptr [rbp+57h+var_80], ecx
0x180013910  xor     eax, eax
0x180013912  mov     [r14+rcx*2], ax
0x180013917  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x180013920  mov     [rsp+0D0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180013928  mov     r8d, 3; dwShareMode
0x18001392e  mov     [rsp+0D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180013933  xor     r9d, r9d; lpSecurityAttributes
0x180013936  mov     edx, 80000000h; dwDesiredAccess
0x18001393b  mov     rcx, r14; lpFileName
0x18001393e  call    cs:__imp_CreateFileW
0x180013944  mov     rbx, rax
0x180013947  mov     [rbp+57h+var_40], rax
0x18001394b  inc     rax
0x18001394e  test    rax, 0FFFFFFFFFFFFFFFEh
0x180013954  jnz     short loc_180013989
0x180013956  call    cs:__imp_GetLastError
0x18001395c  cmp     eax, 5
0x18001395f  jnz     short loc_18001397A
0x180013961  mov     eax, 0A9Ch
0x180013966  mov     dword ptr [rsi], 8900000Dh
0x18001396c  xor     edi, edi
0x18001396e  mov     [rbp+57h+var_78], edi
0x180013971  mov     [rbp+57h+var_74], ax
0x180013975  jmp     loc_180013A93
0x18001397a  mov     edi, 89000001h
0x18001397f  mov     eax, 0AA0h
0x180013984  jmp     loc_18001389C
0x180013989  mov     rdx, rbx; void *
0x18001398c  call    ?_CheckVolumeDirty@CDefragEngine@@AEAAJPEAX@Z; CDefragEngine::_CheckVolumeDirty(void *)
0x180013991  mov     ecx, 89000015h; this
0x180013996  cmp     eax, ecx
0x180013998  jnz     short loc_18001399C
0x18001399a  mov     [rsi], ecx
0x18001399c  lea     r8, [rbp+57h+var_90]; unsigned int *
0x1800139a0  mov     rdx, rbx; void *
0x1800139a3  call    ?_GetVolumeDriveType@CDefragEngine@@AEAAJPEAXPEAI@Z; CDefragEngine::_GetVolumeDriveType(void *,uint *)
0x1800139a8  mov     edi, eax
0x1800139aa  mov     [rbp+57h+var_78], eax
0x1800139ad  test    eax, eax
0x1800139af  mov     eax, 0AACh
0x1800139b4  js      loc_18001389F
0x1800139ba  mov     [rbp+57h+var_74], ax
0x1800139be  mov     edi, [rbp+57h+var_90]
0x1800139c1  cmp     edi, 4
0x1800139c4  jnz     short loc_1800139D3
0x1800139c6  mov     dword ptr [rsi], 8900000Eh
0x1800139cc  mov     eax, 0AB1h
0x1800139d1  jmp     short loc_18001396C
0x1800139d3  cmp     edi, 5
0x1800139d6  jnz     short loc_1800139E5
0x1800139d8  mov     dword ptr [rsi], 8900000Fh
0x1800139de  mov     eax, 0AB7h
0x1800139e3  jmp     short loc_18001396C
0x1800139e5  lea     r8, [rbp+57h+String1]; unsigned __int16 *
0x1800139e9  mov     rdx, rbx; void *
0x1800139ec  call    ?_GetVolumeFileSystemName@CDefragEngine@@AEAAJPEAXPEAGK@Z; CDefragEngine::_GetVolumeFileSystemName(void *,ushort *,ulong)
0x1800139f1  test    eax, eax
0x1800139f3  jns     short loc_1800139FF
0x1800139f5  mov     eax, 0AC3h
0x1800139fa  jmp     loc_180013966
0x1800139ff  lea     rdx, aNtfs; "NTFS"
0x180013a06  lea     rcx, [rbp+57h+String1]; String1
0x180013a0a  call    cs:__imp__wcsicmp
0x180013a10  test    eax, eax
0x180013a12  jz      short loc_180013A90
0x180013a14  lea     rdx, aRefs; "REFS"
0x180013a1b  lea     rcx, [rbp+57h+String1]; String1
0x180013a1f  call    cs:__imp__wcsicmp
0x180013a25  test    eax, eax
0x180013a27  jz      short loc_180013A90
0x180013a29  lea     rdx, aCsvfs; "CSVFS"
0x180013a30  lea     rcx, [rbp+57h+String1]; String1
0x180013a34  call    cs:__imp__wcsicmp
0x180013a3a  test    eax, eax
0x180013a3c  jz      short loc_180013A90
0x180013a3e  lea     rdx, aFat32; "FAT32"
0x180013a45  lea     rcx, [rbp+57h+String1]; String1
0x180013a49  call    cs:__imp__wcsicmp
0x180013a4f  test    eax, eax
0x180013a51  jz      short loc_180013A78
0x180013a53  lea     rdx, aFat; "FAT"
0x180013a5a  lea     rcx, [rbp+57h+String1]; String1
0x180013a5e  call    cs:__imp__wcsicmp
0x180013a64  test    eax, eax
0x180013a66  jz      short loc_180013A78
0x180013a68  mov     dword ptr [rsi], 8900002Fh
0x180013a6e  mov     eax, 0AD4h
0x180013a73  jmp     loc_18001396C
0x180013a78  lea     eax, [rdi-2]
0x180013a7b  cmp     eax, 1
0x180013a7e  jbe     short loc_180013A90
0x180013a80  mov     dword ptr [rsi], 8900002Fh
0x180013a86  mov     eax, 0ADBh
0x180013a8b  jmp     loc_18001396C
0x180013a90  mov     edi, [rbp+57h+var_78]
0x180013a93  mov     rcx, r14; unsigned __int16 *
0x180013a96  call    ?_FreeData@CBsString@@CAXPEAGK@Z; CBsString::_FreeData(ushort *,ulong)
0x180013a9b  nop
0x180013a9c  lea     rdx, [rbx-1]
0x180013aa0  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180013aa4  ja      short loc_180013AB0
0x180013aa6  mov     rcx, rbx; hObject
0x180013aa9  call    cs:__imp_CloseHandle
0x180013aaf  nop
0x180013ab0  lea     rcx, [rbp+57h+var_78]; this
0x180013ab4  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180013ab9  mov     eax, edi
0x180013abb  mov     rcx, [rbp+57h+var_20]
0x180013abf  xor     rcx, rsp; StackCookie
0x180013ac2  call    __security_check_cookie
0x180013ac7  lea     r11, [rsp+0D0h+var_10]
0x180013acf  mov     rbx, [r11+20h]
0x180013ad3  mov     rsi, [r11+38h]
0x180013ad7  mov     rsp, r11
0x180013ada  pop     r14
0x180013adc  pop     rdi
0x180013add  pop     rbp
0x180013ade  retn
```
