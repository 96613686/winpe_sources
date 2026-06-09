# DiagCabFdiNotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)

- ea: `0x140060900`
- end: `0x140060bdc`
- name: `?DiagCabFdiNotify@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z`
- size: `732`
- prototype: `INT_PTR __fastcall(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x140060900`
- `0x14006162c`
- `0x140061b50`
- `0x140061c62`
- `0x140061c90`
- `0x140063010`

## import_xrefs

- `KERNEL32!LocalFileTimeToFileTime` at `0x1400609b7`
- `KERNEL32!LocalFileTimeToFileTime` at `0x1400609b7`
- `KERNEL32!SetFileTime` at `0x1400609e8`
- `KERNEL32!SetFileTime` at `0x1400609e8`
- `KERNEL32!MultiByteToWideChar` at `0x140060a19`
- `KERNEL32!MultiByteToWideChar` at `0x140060aaa`
- `KERNEL32!MultiByteToWideChar` at `0x140060a19`
- `KERNEL32!MultiByteToWideChar` at `0x140060aaa`
- `KERNEL32!DosDateTimeToFileTime` at `0x140060999`
- `KERNEL32!DosDateTimeToFileTime` at `0x140060999`
- `KERNEL32!GetFullPathNameW` at `0x140060aff`
- `KERNEL32!GetFullPathNameW` at `0x140060b2d`
- `KERNEL32!GetFullPathNameW` at `0x140060aff`
- `KERNEL32!GetFullPathNameW` at `0x140060b2d`
- `KERNEL32!SetFileAttributesW` at `0x140060a5f`
- `KERNEL32!SetFileAttributesW` at `0x140060a5f`
- `msvcrt!_close` at `0x140060a6e`
- `msvcrt!_close` at `0x140060a6e`
- `msvcrt!_get_osfhandle` at `0x1400609ca`
- `msvcrt!_get_osfhandle` at `0x1400609ca`
- `msvcrt!_wopen` at `0x140060ba8`
- `msvcrt!_wopen` at `0x140060ba8`

## pseudocode

```c
INT_PTR __fastcall DiagCabFdiNotify(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)
{
  void *pv; // r14
  int v4; // ebx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  void *osfhandle; // rax
  signed int FullPathNameW; // eax
  signed int v11; // eax
  size_t v12; // r8
  unsigned __int64 v13; // rax
  struct _FILETIME FileTime; // [rsp+30h] [rbp-D0h] BYREF
  FILETIME LastWriteTime; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR FilePart[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+260h] [rbp+160h] BYREF
  wchar_t Buffer[264]; // [rsp+470h] [rbp+370h] BYREF
  wchar_t String1[264]; // [rsp+680h] [rbp+580h] BYREF

  pv = pfdin->pv;
  LastWriteTime = 0;
  FileTime = 0;
  FilePart[0] = 0;
  if ( fdint == fdintCABINET_INFO )
    return 0;
  v4 = -1;
  v5 = fdint - 1;
  if ( !v5 )
    return -1;
  v6 = v5 - 1;
  if ( !v6 )
  {
    if ( MultiByteToWideChar(0xFDE9u, 8u, pfdin->psz1, -1, WideCharStr, 260) )
    {
      if ( (int)StringCbPrintfW(FileName, 0x208u, L"%s\\%s", *((_QWORD *)pv + 2), WideCharStr) < 0 )
      {
LABEL_29:
        if ( *(_QWORD *)pv )
          (*(void (__fastcall **)(WCHAR *, _QWORD))pv)(FileName, *((_QWORD *)pv + 1));
        return v4;
      }
      FullPathNameW = GetFullPathNameW(FileName, 0x104u, Buffer, FilePart);
      if ( FullPathNameW )
      {
        if ( FullPathNameW <= 260 )
        {
          v11 = GetFullPathNameW(*((LPCWSTR *)pv + 2), 0x104u, String1, FilePart);
          if ( v11 )
          {
            if ( v11 <= 260 )
            {
              v12 = -1;
              do
                ++v12;
              while ( String1[v12] );
              v13 = -1;
              do
                ++v13;
              while ( Buffer[v13] );
              if ( v12 <= v13 && !wcsncmp_0(String1, Buffer, v12) )
              {
                if ( (int)DiagCreatePath(FileName) >= 0 )
                  v4 = _wopen(FileName, 33025, 0);
                goto LABEL_29;
              }
            }
          }
        }
      }
    }
    return -1;
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    if ( v7 != 1 )
      return 0;
    return -1;
  }
  if ( DosDateTimeToFileTime(pfdin->date, pfdin->time, &FileTime) )
  {
    if ( LocalFileTimeToFileTime(&FileTime, &LastWriteTime) )
    {
      osfhandle = (void *)_get_osfhandle(pfdin->hf);
      if ( osfhandle != (void *)-1LL )
        SetFileTime(osfhandle, 0, 0, &LastWriteTime);
    }
  }
  if ( MultiByteToWideChar(0xFDE9u, 8u, pfdin->psz1, -1, WideCharStr, 260) )
  {
    if ( (int)StringCbPrintfW(FileName, 0x208u, L"%s\\%s", *((_QWORD *)pv + 2), WideCharStr) >= 0 )
      SetFileAttributesW(FileName, pfdin->attribs & 0x27);
  }
  _close(pfdin->hf);
  return 1;
}

```

## disassembly

```asm
0x140060900  push    rbp
0x140060902  push    rbx
0x140060903  push    rsi
0x140060904  push    rdi
0x140060905  push    r14
0x140060907  push    r15
0x140060909  lea     rbp, [rsp-7A8h]
0x140060911  sub     rsp, 8A8h
0x140060918  mov     rax, cs:__security_cookie
0x14006091f  xor     rax, rsp
0x140060922  mov     [rbp+7D0h+var_40], rax
0x140060929  mov     r14, [rdx+20h]
0x14006092d  xor     r15d, r15d
0x140060930  mov     qword ptr [rsp+8D0h+LastWriteTime.dwLowDateTime], r15
0x140060935  mov     rdi, rdx
0x140060938  mov     qword ptr [rsp+8D0h+FileTime.dwLowDateTime], r15
0x14006093d  mov     [rsp+8D0h+FilePart], r15
0x140060942  test    ecx, ecx
0x140060944  jz      short loc_14006096A
0x140060946  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14006094a  sub     ecx, 1
0x14006094d  jz      loc_140060BD4
0x140060953  sub     ecx, 1
0x140060956  jz      loc_140060A84
0x14006095c  sub     ecx, 1
0x14006095f  jz      short loc_14006098C
0x140060961  cmp     ecx, 1
0x140060964  jz      loc_140060BD4
0x14006096a  xor     eax, eax
0x14006096c  mov     rcx, [rbp+7D0h+var_40]
0x140060973  xor     rcx, rsp; StackCookie
0x140060976  call    __security_check_cookie
0x14006097b  add     rsp, 8A8h
0x140060982  pop     r15
0x140060984  pop     r14
0x140060986  pop     rdi
0x140060987  pop     rsi
0x140060988  pop     rbx
0x140060989  pop     rbp
0x14006098a  retn
0x14006098c  movzx   edx, word ptr [rdx+32h]; wFatTime
0x140060990  lea     r8, [rsp+8D0h+FileTime]; lpFileTime
0x140060995  movzx   ecx, word ptr [rdi+30h]; wFatDate
0x140060999  call    cs:__imp_DosDateTimeToFileTime
0x1400609a0  nop     dword ptr [rax+rax+00h]
0x1400609a5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400609a9  test    eax, eax
0x1400609ab  jz      short loc_1400609F4
0x1400609ad  lea     rdx, [rsp+8D0h+LastWriteTime]; lpFileTime
0x1400609b2  lea     rcx, [rsp+8D0h+FileTime]; lpLocalFileTime
0x1400609b7  call    cs:__imp_LocalFileTimeToFileTime
0x1400609be  nop     dword ptr [rax+rax+00h]
0x1400609c3  test    eax, eax
0x1400609c5  jz      short loc_1400609F4
0x1400609c7  mov     ecx, [rdi+28h]; FileHandle
0x1400609ca  call    cs:__imp__get_osfhandle
0x1400609d1  nop     dword ptr [rax+rax+00h]
0x1400609d6  cmp     rax, rbx
0x1400609d9  jz      short loc_1400609F4
0x1400609db  lea     r9, [rsp+8D0h+LastWriteTime]; lpLastWriteTime
0x1400609e0  xor     r8d, r8d; lpLastAccessTime
0x1400609e3  xor     edx, edx; lpCreationTime
0x1400609e5  mov     rcx, rax; hFile
0x1400609e8  call    cs:__imp_SetFileTime
0x1400609ef  nop     dword ptr [rax+rax+00h]
0x1400609f4  mov     r8, [rdi+8]; lpMultiByteStr
0x1400609f8  lea     rax, [rbp+7D0h+WideCharStr]
0x1400609ff  mov     [rsp+8D0h+cchWideChar], 104h; cchWideChar
0x140060a07  mov     r9d, ebx; cbMultiByte
0x140060a0a  mov     edx, 8; dwFlags
0x140060a0f  mov     [rsp+8D0h+lpWideCharStr], rax; lpWideCharStr
0x140060a14  mov     ecx, 0FDE9h; CodePage
0x140060a19  call    cs:__imp_MultiByteToWideChar
0x140060a20  nop     dword ptr [rax+rax+00h]
0x140060a25  test    eax, eax
0x140060a27  jz      short loc_140060A6B
0x140060a29  mov     r9, [r14+10h]
0x140060a2d  lea     rax, [rbp+7D0h+WideCharStr]
0x140060a34  lea     r8, aSS_1; "%s\\%s"
0x140060a3b  mov     [rsp+8D0h+lpWideCharStr], rax
0x140060a40  mov     edx, 208h; unsigned __int64
0x140060a45  lea     rcx, [rsp+8D0h+FileName]; unsigned __int16 *
0x140060a4a  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140060a4f  test    eax, eax
0x140060a51  js      short loc_140060A6B
0x140060a53  movzx   edx, word ptr [rdi+34h]
0x140060a57  lea     rcx, [rsp+8D0h+FileName]; lpFileName
0x140060a5c  and     edx, 27h; dwFileAttributes
0x140060a5f  call    cs:__imp_SetFileAttributesW
0x140060a66  nop     dword ptr [rax+rax+00h]
0x140060a6b  mov     ecx, [rdi+28h]; FileHandle
0x140060a6e  call    cs:__imp__close
0x140060a75  nop     dword ptr [rax+rax+00h]
0x140060a7a  mov     eax, 1
0x140060a7f  jmp     loc_14006096C
0x140060a84  mov     r8, [rdx+8]; lpMultiByteStr
0x140060a88  lea     rax, [rbp+7D0h+WideCharStr]
0x140060a8f  mov     esi, 104h
0x140060a94  mov     r9d, ebx; cbMultiByte
0x140060a97  mov     [rsp+8D0h+cchWideChar], esi; cchWideChar
0x140060a9b  mov     edx, 8; dwFlags
0x140060aa0  mov     ecx, 0FDE9h; CodePage
0x140060aa5  mov     [rsp+8D0h+lpWideCharStr], rax; lpWideCharStr
0x140060aaa  call    cs:__imp_MultiByteToWideChar
0x140060ab1  nop     dword ptr [rax+rax+00h]
0x140060ab6  test    eax, eax
0x140060ab8  jz      loc_140060BD4
0x140060abe  mov     r9, [r14+10h]
0x140060ac2  lea     rax, [rbp+7D0h+WideCharStr]
0x140060ac9  lea     r8, aSS_1; "%s\\%s"
0x140060ad0  mov     [rsp+8D0h+lpWideCharStr], rax
0x140060ad5  mov     edx, 208h; unsigned __int64
0x140060ada  lea     rcx, [rsp+8D0h+FileName]; unsigned __int16 *
0x140060adf  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140060ae4  test    eax, eax
0x140060ae6  js      loc_140060BB6
0x140060aec  lea     r9, [rsp+8D0h+FilePart]; lpFilePart
0x140060af1  mov     edx, esi; nBufferLength
0x140060af3  lea     r8, [rbp+7D0h+Buffer]; lpBuffer
0x140060afa  lea     rcx, [rsp+8D0h+FileName]; lpFileName
0x140060aff  call    cs:__imp_GetFullPathNameW
0x140060b06  nop     dword ptr [rax+rax+00h]
0x140060b0b  test    eax, eax
0x140060b0d  jz      loc_140060BD4
0x140060b13  cmp     eax, esi
0x140060b15  jg      loc_140060BD4
0x140060b1b  mov     rcx, [r14+10h]; lpFileName
0x140060b1f  lea     r9, [rsp+8D0h+FilePart]; lpFilePart
0x140060b24  lea     r8, [rbp+7D0h+String1]; lpBuffer
0x140060b2b  mov     edx, esi; nBufferLength
0x140060b2d  call    cs:__imp_GetFullPathNameW
0x140060b34  nop     dword ptr [rax+rax+00h]
0x140060b39  test    eax, eax
0x140060b3b  jz      loc_140060BD4
0x140060b41  cmp     eax, esi
0x140060b43  jg      loc_140060BD4
0x140060b49  lea     rax, [rbp+7D0h+String1]
0x140060b50  mov     r8, rbx
0x140060b53  inc     r8; MaxCount
0x140060b56  cmp     [rax+r8*2], r15w
0x140060b5b  jnz     short loc_140060B53
0x140060b5d  lea     rcx, [rbp+7D0h+Buffer]
0x140060b64  mov     rax, rbx
0x140060b67  inc     rax
0x140060b6a  cmp     [rcx+rax*2], r15w
0x140060b6f  jnz     short loc_140060B67
0x140060b71  cmp     r8, rax
0x140060b74  ja      short loc_140060BD4
0x140060b76  lea     rdx, [rbp+7D0h+Buffer]; String2
0x140060b7d  lea     rcx, [rbp+7D0h+String1]; String1
0x140060b84  call    wcsncmp_0
0x140060b89  test    eax, eax
0x140060b8b  jnz     short loc_140060BD4
0x140060b8d  lea     rcx, [rsp+8D0h+FileName]; lpPathName
0x140060b92  call    ?DiagCreatePath@@YAJPEAG@Z; DiagCreatePath(ushort *)
0x140060b97  test    eax, eax
0x140060b99  js      short loc_140060BB6
0x140060b9b  xor     r8d, r8d
0x140060b9e  lea     rcx, [rsp+8D0h+FileName]; FileName
0x140060ba3  mov     edx, 8101h; OpenFlag
0x140060ba8  call    cs:__imp__wopen
0x140060baf  nop     dword ptr [rax+rax+00h]
0x140060bb4  mov     ebx, eax
0x140060bb6  mov     rax, [r14]
0x140060bb9  test    rax, rax
0x140060bbc  jz      short loc_140060BCC
0x140060bbe  mov     rdx, [r14+8]
0x140060bc2  lea     rcx, [rsp+8D0h+FileName]
0x140060bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060bcc  movsxd  rax, ebx
0x140060bcf  jmp     loc_14006096C
0x140060bd4  mov     rax, rbx
0x140060bd7  jmp     loc_14006096C
```
