# CommandLineData::IsInDirOrSubDir(ushort const *,ushort const *,uint,uint)

- ea: `0x1400569c0`
- end: `0x140056d16`
- name: `?IsInDirOrSubDir@CommandLineData@@AEAAHPEBG0II@Z`
- size: `854`
- prototype: `__int64 __fastcall(CommandLineData *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400569c0`
- `0x140057cd0`

## callees

- `0x140004703`
- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x1400569c0`
- `0x140113390`

## import_xrefs

- `SHLWAPI!PathAppendW` at `0x140056a34`
- `SHLWAPI!PathAppendW` at `0x140056ad7`
- `SHLWAPI!PathAppendW` at `0x140056baf`
- `SHLWAPI!PathAppendW` at `0x140056c34`
- `SHLWAPI!PathAppendW` at `0x140056a34`
- `SHLWAPI!PathAppendW` at `0x140056ad7`
- `SHLWAPI!PathAppendW` at `0x140056baf`
- `SHLWAPI!PathAppendW` at `0x140056c34`
- `SHLWAPI!PathFindFileNameW` at `0x1400569f9`
- `SHLWAPI!PathFindFileNameW` at `0x1400569f9`
- `KERNEL32!FindClose` at `0x140056ca8`
- `KERNEL32!FindClose` at `0x140056ca8`
- `KERNEL32!FindNextFileW` at `0x140056bff`
- `KERNEL32!FindNextFileW` at `0x140056bff`
- `KERNEL32!FindFirstFileW` at `0x140056b27`
- `KERNEL32!FindFirstFileW` at `0x140056b27`
- `KERNEL32!GetFileAttributesW` at `0x140056a7d`
- `KERNEL32!GetFileAttributesW` at `0x140056a7d`

## pseudocode

```c
__int64 __fastcall CommandLineData::IsInDirOrSubDir(
        CommandLineData *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5)
{
  unsigned int v8; // edi
  const unsigned __int16 *FileNameW; // rax
  LPCWSTR v10; // r11
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v12; // rdx
  DWORD FileAttributesW; // eax
  HANDLE FirstFileW; // rsi
  int v15; // edx
  int v16; // edx
  unsigned int v17; // eax
  __int64 v18; // rdx
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPath[264]; // [rsp+280h] [rbp+180h] BYREF

  v8 = 0;
  FileNameW = PathFindFileNameW(a2);
  if ( !FileNameW || FileNameW == a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 35;
      goto LABEL_46;
    }
  }
  else
  {
    StringCchCopyW(pszPath, 0x104u, a3);
    if ( PathAppendW(pszPath, v10) )
    {
      FileAttributesW = GetFileAttributesW(pszPath);
      if ( FileAttributesW == -1 || (FileAttributesW & 0x10) != 0 )
      {
        if ( a5 < 3 )
        {
          memset_0(&FindFileData, 0, sizeof(FindFileData));
          StringCchCopyW(pszPath, 0x104u, a3);
          if ( PathAppendW(pszPath, L"*") )
          {
            FirstFileW = FindFirstFileW(pszPath, &FindFileData);
            if ( FirstFileW != (HANDLE)-1LL )
            {
              if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
                goto LABEL_31;
              v15 = FindFileData.cFileName[0] - 46;
              if ( FindFileData.cFileName[0] == 46 )
                v15 = FindFileData.cFileName[1];
              if ( !v15 )
                goto LABEL_31;
              v16 = FindFileData.cFileName[0] - 46;
              if ( FindFileData.cFileName[0] == 46 )
              {
                v16 = FindFileData.cFileName[1] - 46;
                if ( FindFileData.cFileName[1] == 46 )
                  v16 = FindFileData.cFileName[2];
              }
              if ( v16 )
              {
                StringCchCopyW(pszPath, 0x104u, a3);
                if ( PathAppendW(pszPath, FindFileData.cFileName) )
                {
LABEL_34:
                  v8 = CommandLineData::IsInDirOrSubDir(this, a2, pszPath, 3u, a5 + 1);
                  if ( !v8 )
                    goto LABEL_31;
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v17 = RdpWppGetCurrentThreadActivityIdPrefix();
                  v18 = 38;
LABEL_40:
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v18,
                    WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids,
                    v17);
                }
              }
              else
              {
LABEL_31:
                while ( FindNextFileW(FirstFileW, &FindFileData) )
                {
                  if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
                  {
                    StringCchCopyW(pszPath, 0x104u, a3);
                    if ( PathAppendW(pszPath, FindFileData.cFileName) )
                      goto LABEL_34;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
                      v18 = 39;
                      goto LABEL_40;
                    }
                    break;
                  }
                }
              }
              FindClose(FirstFileW);
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v12 = 37;
            goto LABEL_46;
          }
        }
      }
      else
      {
        return 1;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 36;
LABEL_46:
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1400569c0  push    rbp
0x1400569c2  push    rbx
0x1400569c3  push    rsi
0x1400569c4  push    rdi
0x1400569c5  push    r12
0x1400569c7  push    r14
0x1400569c9  push    r15
0x1400569cb  lea     rbp, [rsp-3A0h]
0x1400569d3  sub     rsp, 4A0h
0x1400569da  mov     rax, cs:__security_cookie
0x1400569e1  xor     rax, rsp
0x1400569e4  mov     [rbp+3D0h+var_40], rax
0x1400569eb  mov     r12, rcx
0x1400569ee  mov     r15, r8
0x1400569f1  mov     rcx, rdx; pszPath
0x1400569f4  mov     r14, rdx
0x1400569f7  xor     edi, edi
0x1400569f9  call    cs:__imp_PathFindFileNameW
0x1400569ff  mov     r11, rax
0x140056a02  test    rax, rax
0x140056a05  jz      loc_140056CB0
0x140056a0b  cmp     rax, r14
0x140056a0e  jz      loc_140056CB0
0x140056a14  mov     esi, 104h
0x140056a19  lea     rcx, [rbp+3D0h+pszPath]; unsigned __int16 *
0x140056a20  mov     edx, esi; unsigned __int64
0x140056a22  mov     r8, r15; unsigned __int16 *
0x140056a25  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140056a2a  mov     rdx, r11; pszMore
0x140056a2d  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x140056a34  call    cs:__imp_PathAppendW
0x140056a3a  test    eax, eax
0x140056a3c  jnz     short loc_140056A76
0x140056a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140056a45  lea     rax, WPP_GLOBAL_Control
0x140056a4c  cmp     rcx, rax
0x140056a4f  jz      loc_140056CF3
0x140056a55  test    byte ptr [rcx+1Ch], 1
0x140056a59  jz      loc_140056CF3
0x140056a5f  cmp     byte ptr [rcx+19h], 2
0x140056a63  jb      loc_140056CF3
0x140056a69  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140056a6e  lea     edx, [rdi+24h]
0x140056a71  jmp     loc_140056CD9
0x140056a76  lea     rcx, [rbp+3D0h+pszPath]; lpFileName
0x140056a7d  call    cs:__imp_GetFileAttributesW
0x140056a83  cmp     eax, 0FFFFFFFFh
0x140056a86  jz      short loc_140056A96
0x140056a88  test    al, 10h
0x140056a8a  jnz     short loc_140056A96
0x140056a8c  mov     edi, 1
0x140056a91  jmp     loc_140056CF3
0x140056a96  mov     ebx, [rbp+3D0h+arg_20]
0x140056a9c  cmp     ebx, 3
0x140056a9f  jnb     loc_140056CF3
0x140056aa5  xor     edx, edx; Val
0x140056aa7  lea     rcx, [rsp+4D0h+FindFileData]; void *
0x140056aac  mov     r8d, 250h; Size
0x140056ab2  call    memset_0
0x140056ab7  mov     r8, r15; unsigned __int16 *
0x140056aba  lea     rcx, [rbp+3D0h+pszPath]; unsigned __int16 *
0x140056ac1  mov     rdx, rsi; unsigned __int64
0x140056ac4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140056ac9  lea     rdx, pszMore; "*"
0x140056ad0  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x140056ad7  call    cs:__imp_PathAppendW
0x140056add  test    eax, eax
0x140056adf  jnz     short loc_140056B1B
0x140056ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x140056ae8  lea     rax, WPP_GLOBAL_Control
0x140056aef  cmp     rcx, rax
0x140056af2  jz      loc_140056CF3
0x140056af8  test    byte ptr [rcx+1Ch], 1
0x140056afc  jz      loc_140056CF3
0x140056b02  cmp     byte ptr [rcx+19h], 2
0x140056b06  jb      loc_140056CF3
0x140056b0c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140056b11  mov     edx, 25h ; '%'
0x140056b16  jmp     loc_140056CD9
0x140056b1b  lea     rdx, [rsp+4D0h+FindFileData]; lpFindFileData
0x140056b20  lea     rcx, [rbp+3D0h+pszPath]; lpFileName
0x140056b27  call    cs:__imp_FindFirstFileW
0x140056b2d  mov     rsi, rax
0x140056b30  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140056b34  jz      loc_140056CF3
0x140056b3a  inc     ebx
0x140056b3c  test    byte ptr [rsp+4D0h+FindFileData.dwFileAttributes], 10h
0x140056b41  jz      loc_140056BF7
0x140056b47  movzx   edx, [rsp+4D0h+FindFileData.cFileName]
0x140056b4c  mov     r8d, 2Eh ; '.'
0x140056b52  sub     edx, r8d
0x140056b55  jnz     short loc_140056B63
0x140056b57  movzx   edx, [rsp+4D0h+FindFileData.cFileName+2]
0x140056b5c  xor     eax, eax
0x140056b5e  movzx   ecx, ax
0x140056b61  sub     edx, ecx
0x140056b63  test    edx, edx
0x140056b65  jz      loc_140056BF7
0x140056b6b  movzx   edx, [rsp+4D0h+FindFileData.cFileName]
0x140056b70  sub     edx, r8d
0x140056b73  jnz     short loc_140056B8B
0x140056b75  movzx   edx, [rsp+4D0h+FindFileData.cFileName+2]
0x140056b7a  sub     edx, r8d
0x140056b7d  jnz     short loc_140056B8B
0x140056b7f  movzx   edx, [rsp+4D0h+FindFileData.cFileName+4]
0x140056b84  xor     eax, eax
0x140056b86  movzx   ecx, ax
0x140056b89  sub     edx, ecx
0x140056b8b  test    edx, edx
0x140056b8d  jz      short loc_140056BF7
0x140056b8f  mov     r8, r15; unsigned __int16 *
0x140056b92  lea     rcx, [rbp+3D0h+pszPath]; unsigned __int16 *
0x140056b99  mov     edx, 104h; unsigned __int64
0x140056b9e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140056ba3  lea     rdx, [rsp+4D0h+FindFileData.cFileName]; pszMore
0x140056ba8  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x140056baf  call    cs:__imp_PathAppendW
0x140056bb5  test    eax, eax
0x140056bb7  jnz     loc_140056C3E
0x140056bbd  mov     rcx, cs:WPP_GLOBAL_Control
0x140056bc4  lea     rax, WPP_GLOBAL_Control
0x140056bcb  cmp     rcx, rax
0x140056bce  jz      loc_140056CA5
0x140056bd4  test    byte ptr [rcx+1Ch], 1
0x140056bd8  jz      loc_140056CA5
0x140056bde  cmp     byte ptr [rcx+19h], 2
0x140056be2  jb      loc_140056CA5
0x140056be8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140056bed  mov     edx, 26h ; '&'
0x140056bf2  jmp     loc_140056C8B
0x140056bf7  lea     rdx, [rsp+4D0h+FindFileData]; lpFindFileData
0x140056bfc  mov     rcx, rsi; hFindFile
0x140056bff  call    cs:__imp_FindNextFileW
0x140056c05  test    eax, eax
0x140056c07  jz      loc_140056CA5
0x140056c0d  test    byte ptr [rsp+4D0h+FindFileData.dwFileAttributes], 10h
0x140056c12  jz      short loc_140056BF7
0x140056c14  mov     r8, r15; unsigned __int16 *
0x140056c17  lea     rcx, [rbp+3D0h+pszPath]; unsigned __int16 *
0x140056c1e  mov     edx, 104h; unsigned __int64
0x140056c23  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140056c28  lea     rdx, [rsp+4D0h+FindFileData.cFileName]; pszMore
0x140056c2d  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x140056c34  call    cs:__imp_PathAppendW
0x140056c3a  test    eax, eax
0x140056c3c  jz      short loc_140056C62
0x140056c3e  mov     r9d, 3; unsigned int
0x140056c44  mov     [rsp+4D0h+var_4B0], ebx; unsigned int
0x140056c48  lea     r8, [rbp+3D0h+pszPath]; unsigned __int16 *
0x140056c4f  mov     rdx, r14; unsigned __int16 *
0x140056c52  mov     rcx, r12; this
0x140056c55  call    ?IsInDirOrSubDir@CommandLineData@@AEAAHPEBG0II@Z; CommandLineData::IsInDirOrSubDir(ushort const *,ushort const *,uint,uint)
0x140056c5a  mov     edi, eax
0x140056c5c  test    eax, eax
0x140056c5e  jz      short loc_140056BF7
0x140056c60  jmp     short loc_140056CA5
0x140056c62  mov     rcx, cs:WPP_GLOBAL_Control
0x140056c69  lea     rax, WPP_GLOBAL_Control
0x140056c70  cmp     rcx, rax
0x140056c73  jz      short loc_140056CA5
0x140056c75  test    byte ptr [rcx+1Ch], 1
0x140056c79  jz      short loc_140056CA5
0x140056c7b  cmp     byte ptr [rcx+19h], 2
0x140056c7f  jb      short loc_140056CA5
0x140056c81  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140056c86  mov     edx, 27h ; '''
0x140056c8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140056c92  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140056c99  mov     r9d, eax
0x140056c9c  mov     rcx, [rcx+10h]
0x140056ca0  call    WPP_SF_d
0x140056ca5  mov     rcx, rsi; hFindFile
0x140056ca8  call    cs:__imp_FindClose
0x140056cae  jmp     short loc_140056CF3
0x140056cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x140056cb7  lea     rax, WPP_GLOBAL_Control
0x140056cbe  cmp     rcx, rax
0x140056cc1  jz      short loc_140056CF3
0x140056cc3  test    byte ptr [rcx+1Ch], 1
0x140056cc7  jz      short loc_140056CF3
0x140056cc9  cmp     byte ptr [rcx+19h], 2
0x140056ccd  jb      short loc_140056CF3
0x140056ccf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140056cd4  mov     edx, 23h ; '#'
0x140056cd9  mov     rcx, cs:WPP_GLOBAL_Control
0x140056ce0  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140056ce7  mov     r9d, eax
0x140056cea  mov     rcx, [rcx+10h]
0x140056cee  call    WPP_SF_d
0x140056cf3  mov     eax, edi
0x140056cf5  mov     rcx, [rbp+3D0h+var_40]
0x140056cfc  xor     rcx, rsp; StackCookie
0x140056cff  call    __security_check_cookie
0x140056d04  add     rsp, 4A0h
0x140056d0b  pop     r15
0x140056d0d  pop     r14
0x140056d0f  pop     r12
0x140056d11  pop     rdi
0x140056d12  pop     rsi
0x140056d13  pop     rbx
0x140056d14  pop     rbp
0x140056d15  retn
```
