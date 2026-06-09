# DeleteQueueFiles(ushort const *)

- ea: `0x140037cd4`
- end: `0x140037f7a`
- name: `?DeleteQueueFiles@@YAHPEBG@Z`
- size: `678`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x14003bf04`

## callees

- `0x140002c43`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140004d44`
- `0x140004df0`
- `0x140037cd4`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140037ecb`
- `KERNEL32!GetLastError` at `0x140037f35`
- `KERNEL32!GetLastError` at `0x140037ecb`
- `KERNEL32!GetLastError` at `0x140037f35`
- `KERNEL32!FindFirstFileW` at `0x140037dac`
- `KERNEL32!FindFirstFileW` at `0x140037dac`
- `KERNEL32!FindClose` at `0x140037f13`
- `KERNEL32!FindClose` at `0x140037f13`
- `KERNEL32!DeleteFileW` at `0x140037ea9`
- `KERNEL32!DeleteFileW` at `0x140037ea9`
- `KERNEL32!FindNextFileW` at `0x140037f02`
- `KERNEL32!FindNextFileW` at `0x140037f02`

## pseudocode

```c
_BOOL8 __fastcall DeleteQueueFiles(const unsigned __int16 *a1)
{
  int v2; // eax
  HANDLE FirstFileW; // rdi
  int v5; // ebx
  int v6; // eax
  char LastError; // al
  DWORD v8; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-498h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp-248h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  v2 = StringCchPrintfW(FileName, 0x104u, L"%s\\*.%s", *((_QWORD *)g_pFaxConfig + 12), a1);
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        (unsigned int)v2);
    }
    return 0;
  }
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        (_DWORD)a1,
        *((_QWORD *)g_pFaxConfig + 12));
    }
    return 1;
  }
  v5 = 0;
  do
  {
    v6 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", *((_QWORD *)g_pFaxConfig + 12), FindFileData.cFileName);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
          (unsigned int)v6);
      }
LABEL_32:
      v5 = 1;
      continue;
    }
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, FileName);
    }
    if ( !DeleteFileW(FileName) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          53,
          (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
          (unsigned int)FileName,
          LastError);
      }
      goto LABEL_32;
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  if ( !FindClose(FirstFileW)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v8);
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x140037cd4  push    rbx
0x140037cd6  push    rbp
0x140037cd7  push    rdi
0x140037cd8  push    r14
0x140037cda  sub     rsp, 4A8h
0x140037ce1  mov     rax, cs:__security_cookie
0x140037ce8  xor     rax, rsp
0x140037ceb  mov     [rsp+4C8h+var_38], rax
0x140037cf3  mov     rbx, rcx
0x140037cf6  xor     edx, edx; Val
0x140037cf8  lea     rcx, [rsp+4C8h+FindFileData]; void *
0x140037cfd  mov     r8d, 250h; Size
0x140037d03  call    memset_0
0x140037d08  mov     rcx, cs:WPP_GLOBAL_Control
0x140037d0f  lea     rbp, WPP_GLOBAL_Control
0x140037d16  lea     r14, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140037d1d  cmp     rcx, rbp
0x140037d20  jz      short loc_140037D3F
0x140037d22  test    byte ptr [rcx+1Ch], 4
0x140037d26  jz      short loc_140037D3F
0x140037d28  cmp     byte ptr [rcx+19h], 5
0x140037d2c  jb      short loc_140037D3F
0x140037d2e  mov     rcx, [rcx+10h]
0x140037d32  mov     edx, 30h ; '0'
0x140037d37  mov     r8, r14
0x140037d3a  call    WPP_SF_
0x140037d3f  mov     r9, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140037d46  lea     r8, aSS; "%s\\*.%s"
0x140037d4d  mov     edx, 104h; unsigned __int64
0x140037d52  mov     [rsp+4C8h+var_4A8], rbx
0x140037d57  lea     rcx, [rsp+4C8h+FileName]; unsigned __int16 *
0x140037d5f  mov     r9, [r9+60h]
0x140037d63  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140037d68  test    eax, eax
0x140037d6a  jns     short loc_140037D9F
0x140037d6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140037d73  cmp     rcx, rbp
0x140037d76  jz      short loc_140037D98
0x140037d78  test    byte ptr [rcx+1Ch], 4
0x140037d7c  jz      short loc_140037D98
0x140037d7e  cmp     byte ptr [rcx+19h], 2
0x140037d82  jb      short loc_140037D98
0x140037d84  mov     rcx, [rcx+10h]
0x140037d88  mov     edx, 31h ; '1'
0x140037d8d  mov     r9d, eax
0x140037d90  mov     r8, r14
0x140037d93  call    WPP_SF_d
0x140037d98  xor     eax, eax
0x140037d9a  jmp     loc_140037F5D
0x140037d9f  lea     rdx, [rsp+4C8h+FindFileData]; lpFindFileData
0x140037da4  lea     rcx, [rsp+4C8h+FileName]; lpFileName
0x140037dac  call    cs:__imp_FindFirstFileW
0x140037db2  mov     rdi, rax
0x140037db5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140037db9  jnz     short loc_140037DFF
0x140037dbb  mov     rcx, cs:WPP_GLOBAL_Control
0x140037dc2  cmp     rcx, rbp
0x140037dc5  jz      short loc_140037DF5
0x140037dc7  test    byte ptr [rcx+1Ch], 4
0x140037dcb  jz      short loc_140037DF5
0x140037dcd  cmp     byte ptr [rcx+19h], 3
0x140037dd1  jb      short loc_140037DF5
0x140037dd3  mov     rcx, [rcx+10h]
0x140037dd7  lea     edx, [rax+33h]
0x140037dda  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140037de1  mov     r9, rbx
0x140037de4  mov     r8, [rax+60h]
0x140037de8  mov     [rsp+4C8h+var_4A8], r8
0x140037ded  mov     r8, r14
0x140037df0  call    WPP_SF_SS
0x140037df5  mov     eax, 1
0x140037dfa  jmp     loc_140037F5D
0x140037dff  xor     ebx, ebx
0x140037e01  mov     r9, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140037e08  lea     rax, [rsp+4C8h+FindFileData.cFileName]
0x140037e0d  lea     r8, aSS_0; "%s\\%s"
0x140037e14  mov     [rsp+4C8h+var_4A8], rax
0x140037e19  mov     edx, 104h; unsigned __int64
0x140037e1e  lea     rcx, [rsp+4C8h+FileName]; unsigned __int16 *
0x140037e26  mov     r9, [r9+60h]
0x140037e2a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140037e2f  test    eax, eax
0x140037e31  jns     short loc_140037E70
0x140037e33  mov     rcx, cs:WPP_GLOBAL_Control
0x140037e3a  cmp     rcx, rbp
0x140037e3d  jz      loc_140037EF5
0x140037e43  test    byte ptr [rcx+1Ch], 4
0x140037e47  jz      loc_140037EF5
0x140037e4d  cmp     byte ptr [rcx+19h], 2
0x140037e51  jb      loc_140037EF5
0x140037e57  mov     rcx, [rcx+10h]
0x140037e5b  mov     edx, 33h ; '3'
0x140037e60  mov     r9d, eax
0x140037e63  mov     r8, r14
0x140037e66  call    WPP_SF_d
0x140037e6b  jmp     loc_140037EF5
0x140037e70  mov     rcx, cs:WPP_GLOBAL_Control
0x140037e77  cmp     rcx, rbp
0x140037e7a  jz      short loc_140037EA1
0x140037e7c  test    byte ptr [rcx+1Ch], 4
0x140037e80  jz      short loc_140037EA1
0x140037e82  cmp     byte ptr [rcx+19h], 5
0x140037e86  jb      short loc_140037EA1
0x140037e88  mov     rcx, [rcx+10h]
0x140037e8c  lea     r9, [rsp+4C8h+FileName]
0x140037e94  mov     edx, 34h ; '4'
0x140037e99  mov     r8, r14
0x140037e9c  call    WPP_SF_S
0x140037ea1  lea     rcx, [rsp+4C8h+FileName]; lpFileName
0x140037ea9  call    cs:__imp_DeleteFileW
0x140037eaf  test    eax, eax
0x140037eb1  jnz     short loc_140037EFA
0x140037eb3  mov     rax, cs:WPP_GLOBAL_Control
0x140037eba  cmp     rax, rbp
0x140037ebd  jz      short loc_140037EF5
0x140037ebf  test    byte ptr [rax+1Ch], 4
0x140037ec3  jz      short loc_140037EF5
0x140037ec5  cmp     byte ptr [rax+19h], 2
0x140037ec9  jb      short loc_140037EF5
0x140037ecb  call    cs:__imp_GetLastError
0x140037ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x140037ed8  lea     r9, [rsp+4C8h+FileName]
0x140037ee0  mov     edx, 35h ; '5'
0x140037ee5  mov     dword ptr [rsp+4C8h+var_4A8], eax
0x140037ee9  mov     r8, r14
0x140037eec  mov     rcx, [rcx+10h]
0x140037ef0  call    WPP_SF_Sd
0x140037ef5  mov     ebx, 1
0x140037efa  lea     rdx, [rsp+4C8h+FindFileData]; lpFindFileData
0x140037eff  mov     rcx, rdi; hFindFile
0x140037f02  call    cs:__imp_FindNextFileW
0x140037f08  test    eax, eax
0x140037f0a  jnz     loc_140037E01
0x140037f10  mov     rcx, rdi; hFindFile
0x140037f13  call    cs:__imp_FindClose
0x140037f19  test    eax, eax
0x140037f1b  jnz     short loc_140037F56
0x140037f1d  mov     rax, cs:WPP_GLOBAL_Control
0x140037f24  cmp     rax, rbp
0x140037f27  jz      short loc_140037F56
0x140037f29  test    byte ptr [rax+1Ch], 4
0x140037f2d  jz      short loc_140037F56
0x140037f2f  cmp     byte ptr [rax+19h], 2
0x140037f33  jb      short loc_140037F56
0x140037f35  call    cs:__imp_GetLastError
0x140037f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140037f42  mov     edx, 36h ; '6'
0x140037f47  mov     r9d, eax
0x140037f4a  mov     r8, r14
0x140037f4d  mov     rcx, [rcx+10h]
0x140037f51  call    WPP_SF_d
0x140037f56  xor     eax, eax
0x140037f58  test    ebx, ebx
0x140037f5a  setz    al
0x140037f5d  mov     rcx, [rsp+4C8h+var_38]
0x140037f65  xor     rcx, rsp; StackCookie
0x140037f68  call    __security_check_cookie
0x140037f6d  add     rsp, 4A8h
0x140037f74  pop     r14
0x140037f76  pop     rdi
0x140037f77  pop     rbp
0x140037f78  pop     rbx
0x140037f79  retn
```
