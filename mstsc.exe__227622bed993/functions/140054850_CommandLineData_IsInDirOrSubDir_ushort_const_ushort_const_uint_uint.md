# CommandLineData::IsInDirOrSubDir(ushort const *,ushort const *,uint,uint)

- ea: `0x140054850`
- end: `0x140054ba6`
- name: `?IsInDirOrSubDir@CommandLineData@@AEAAHPEBG0II@Z`
- size: `854`
- prototype: `__int64 __fastcall(CommandLineData *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140054850`
- `0x140055b60`

## callees

- `0x140004703`
- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x140054850`
- `0x140111220`

## import_xrefs

- `SHLWAPI!PathAppendW` at `0x1400548c4`
- `SHLWAPI!PathAppendW` at `0x140054967`
- `SHLWAPI!PathAppendW` at `0x140054a3f`
- `SHLWAPI!PathAppendW` at `0x140054ac4`
- `SHLWAPI!PathAppendW` at `0x1400548c4`
- `SHLWAPI!PathAppendW` at `0x140054967`
- `SHLWAPI!PathAppendW` at `0x140054a3f`
- `SHLWAPI!PathAppendW` at `0x140054ac4`
- `SHLWAPI!PathFindFileNameW` at `0x140054889`
- `SHLWAPI!PathFindFileNameW` at `0x140054889`
- `KERNEL32!FindClose` at `0x140054b38`
- `KERNEL32!FindClose` at `0x140054b38`
- `KERNEL32!FindNextFileW` at `0x140054a8f`
- `KERNEL32!FindNextFileW` at `0x140054a8f`
- `KERNEL32!FindFirstFileW` at `0x1400549b7`
- `KERNEL32!FindFirstFileW` at `0x1400549b7`
- `KERNEL32!GetFileAttributesW` at `0x14005490d`
- `KERNEL32!GetFileAttributesW` at `0x14005490d`

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
0x140054850  push    rbp
0x140054852  push    rbx
0x140054853  push    rsi
0x140054854  push    rdi
0x140054855  push    r12
0x140054857  push    r14
0x140054859  push    r15
0x14005485b  lea     rbp, [rsp-3A0h]
0x140054863  sub     rsp, 4A0h
0x14005486a  mov     rax, cs:__security_cookie
0x140054871  xor     rax, rsp
0x140054874  mov     [rbp+3D0h+var_40], rax
0x14005487b  mov     r12, rcx
0x14005487e  mov     r15, r8
0x140054881  mov     rcx, rdx; pszPath
0x140054884  mov     r14, rdx
0x140054887  xor     edi, edi
0x140054889  call    cs:__imp_PathFindFileNameW
0x14005488f  mov     r11, rax
0x140054892  test    rax, rax
0x140054895  jz      loc_140054B40
0x14005489b  cmp     rax, r14
0x14005489e  jz      loc_140054B40
0x1400548a4  mov     esi, 104h
0x1400548a9  lea     rcx, [rbp+3D0h+pszPath]; unsigned __int16 *
0x1400548b0  mov     edx, esi; unsigned __int64
0x1400548b2  mov     r8, r15; unsigned __int16 *
0x1400548b5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400548ba  mov     rdx, r11; pszMore
0x1400548bd  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x1400548c4  call    cs:__imp_PathAppendW
0x1400548ca  test    eax, eax
0x1400548cc  jnz     short loc_140054906
0x1400548ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400548d5  lea     rax, WPP_GLOBAL_Control
0x1400548dc  cmp     rcx, rax
0x1400548df  jz      loc_140054B83
0x1400548e5  test    byte ptr [rcx+1Ch], 1
0x1400548e9  jz      loc_140054B83
0x1400548ef  cmp     byte ptr [rcx+19h], 2
0x1400548f3  jb      loc_140054B83
0x1400548f9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400548fe  lea     edx, [rdi+24h]
0x140054901  jmp     loc_140054B69
0x140054906  lea     rcx, [rbp+3D0h+pszPath]; lpFileName
0x14005490d  call    cs:__imp_GetFileAttributesW
0x140054913  cmp     eax, 0FFFFFFFFh
0x140054916  jz      short loc_140054926
0x140054918  test    al, 10h
0x14005491a  jnz     short loc_140054926
0x14005491c  mov     edi, 1
0x140054921  jmp     loc_140054B83
0x140054926  mov     ebx, [rbp+3D0h+arg_20]
0x14005492c  cmp     ebx, 3
0x14005492f  jnb     loc_140054B83
0x140054935  xor     edx, edx; Val
0x140054937  lea     rcx, [rsp+4D0h+FindFileData]; void *
0x14005493c  mov     r8d, 250h; Size
0x140054942  call    memset_0
0x140054947  mov     r8, r15; unsigned __int16 *
0x14005494a  lea     rcx, [rbp+3D0h+pszPath]; unsigned __int16 *
0x140054951  mov     rdx, rsi; unsigned __int64
0x140054954  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140054959  lea     rdx, pszMore; "*"
0x140054960  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x140054967  call    cs:__imp_PathAppendW
0x14005496d  test    eax, eax
0x14005496f  jnz     short loc_1400549AB
0x140054971  mov     rcx, cs:WPP_GLOBAL_Control
0x140054978  lea     rax, WPP_GLOBAL_Control
0x14005497f  cmp     rcx, rax
0x140054982  jz      loc_140054B83
0x140054988  test    byte ptr [rcx+1Ch], 1
0x14005498c  jz      loc_140054B83
0x140054992  cmp     byte ptr [rcx+19h], 2
0x140054996  jb      loc_140054B83
0x14005499c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400549a1  mov     edx, 25h ; '%'
0x1400549a6  jmp     loc_140054B69
0x1400549ab  lea     rdx, [rsp+4D0h+FindFileData]; lpFindFileData
0x1400549b0  lea     rcx, [rbp+3D0h+pszPath]; lpFileName
0x1400549b7  call    cs:__imp_FindFirstFileW
0x1400549bd  mov     rsi, rax
0x1400549c0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400549c4  jz      loc_140054B83
0x1400549ca  inc     ebx
0x1400549cc  test    byte ptr [rsp+4D0h+FindFileData.dwFileAttributes], 10h
0x1400549d1  jz      loc_140054A87
0x1400549d7  movzx   edx, [rsp+4D0h+FindFileData.cFileName]
0x1400549dc  mov     r8d, 2Eh ; '.'
0x1400549e2  sub     edx, r8d
0x1400549e5  jnz     short loc_1400549F3
0x1400549e7  movzx   edx, [rsp+4D0h+FindFileData.cFileName+2]
0x1400549ec  xor     eax, eax
0x1400549ee  movzx   ecx, ax
0x1400549f1  sub     edx, ecx
0x1400549f3  test    edx, edx
0x1400549f5  jz      loc_140054A87
0x1400549fb  movzx   edx, [rsp+4D0h+FindFileData.cFileName]
0x140054a00  sub     edx, r8d
0x140054a03  jnz     short loc_140054A1B
0x140054a05  movzx   edx, [rsp+4D0h+FindFileData.cFileName+2]
0x140054a0a  sub     edx, r8d
0x140054a0d  jnz     short loc_140054A1B
0x140054a0f  movzx   edx, [rsp+4D0h+FindFileData.cFileName+4]
0x140054a14  xor     eax, eax
0x140054a16  movzx   ecx, ax
0x140054a19  sub     edx, ecx
0x140054a1b  test    edx, edx
0x140054a1d  jz      short loc_140054A87
0x140054a1f  mov     r8, r15; unsigned __int16 *
0x140054a22  lea     rcx, [rbp+3D0h+pszPath]; unsigned __int16 *
0x140054a29  mov     edx, 104h; unsigned __int64
0x140054a2e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140054a33  lea     rdx, [rsp+4D0h+FindFileData.cFileName]; pszMore
0x140054a38  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x140054a3f  call    cs:__imp_PathAppendW
0x140054a45  test    eax, eax
0x140054a47  jnz     loc_140054ACE
0x140054a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140054a54  lea     rax, WPP_GLOBAL_Control
0x140054a5b  cmp     rcx, rax
0x140054a5e  jz      loc_140054B35
0x140054a64  test    byte ptr [rcx+1Ch], 1
0x140054a68  jz      loc_140054B35
0x140054a6e  cmp     byte ptr [rcx+19h], 2
0x140054a72  jb      loc_140054B35
0x140054a78  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140054a7d  mov     edx, 26h ; '&'
0x140054a82  jmp     loc_140054B1B
0x140054a87  lea     rdx, [rsp+4D0h+FindFileData]; lpFindFileData
0x140054a8c  mov     rcx, rsi; hFindFile
0x140054a8f  call    cs:__imp_FindNextFileW
0x140054a95  test    eax, eax
0x140054a97  jz      loc_140054B35
0x140054a9d  test    byte ptr [rsp+4D0h+FindFileData.dwFileAttributes], 10h
0x140054aa2  jz      short loc_140054A87
0x140054aa4  mov     r8, r15; unsigned __int16 *
0x140054aa7  lea     rcx, [rbp+3D0h+pszPath]; unsigned __int16 *
0x140054aae  mov     edx, 104h; unsigned __int64
0x140054ab3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140054ab8  lea     rdx, [rsp+4D0h+FindFileData.cFileName]; pszMore
0x140054abd  lea     rcx, [rbp+3D0h+pszPath]; pszPath
0x140054ac4  call    cs:__imp_PathAppendW
0x140054aca  test    eax, eax
0x140054acc  jz      short loc_140054AF2
0x140054ace  mov     r9d, 3; unsigned int
0x140054ad4  mov     [rsp+4D0h+var_4B0], ebx; unsigned int
0x140054ad8  lea     r8, [rbp+3D0h+pszPath]; unsigned __int16 *
0x140054adf  mov     rdx, r14; unsigned __int16 *
0x140054ae2  mov     rcx, r12; this
0x140054ae5  call    ?IsInDirOrSubDir@CommandLineData@@AEAAHPEBG0II@Z; CommandLineData::IsInDirOrSubDir(ushort const *,ushort const *,uint,uint)
0x140054aea  mov     edi, eax
0x140054aec  test    eax, eax
0x140054aee  jz      short loc_140054A87
0x140054af0  jmp     short loc_140054B35
0x140054af2  mov     rcx, cs:WPP_GLOBAL_Control
0x140054af9  lea     rax, WPP_GLOBAL_Control
0x140054b00  cmp     rcx, rax
0x140054b03  jz      short loc_140054B35
0x140054b05  test    byte ptr [rcx+1Ch], 1
0x140054b09  jz      short loc_140054B35
0x140054b0b  cmp     byte ptr [rcx+19h], 2
0x140054b0f  jb      short loc_140054B35
0x140054b11  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140054b16  mov     edx, 27h ; '''
0x140054b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140054b22  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140054b29  mov     r9d, eax
0x140054b2c  mov     rcx, [rcx+10h]
0x140054b30  call    WPP_SF_d
0x140054b35  mov     rcx, rsi; hFindFile
0x140054b38  call    cs:__imp_FindClose
0x140054b3e  jmp     short loc_140054B83
0x140054b40  mov     rcx, cs:WPP_GLOBAL_Control
0x140054b47  lea     rax, WPP_GLOBAL_Control
0x140054b4e  cmp     rcx, rax
0x140054b51  jz      short loc_140054B83
0x140054b53  test    byte ptr [rcx+1Ch], 1
0x140054b57  jz      short loc_140054B83
0x140054b59  cmp     byte ptr [rcx+19h], 2
0x140054b5d  jb      short loc_140054B83
0x140054b5f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140054b64  mov     edx, 23h ; '#'
0x140054b69  mov     rcx, cs:WPP_GLOBAL_Control
0x140054b70  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140054b77  mov     r9d, eax
0x140054b7a  mov     rcx, [rcx+10h]
0x140054b7e  call    WPP_SF_d
0x140054b83  mov     eax, edi
0x140054b85  mov     rcx, [rbp+3D0h+var_40]
0x140054b8c  xor     rcx, rsp; StackCookie
0x140054b8f  call    __security_check_cookie
0x140054b94  add     rsp, 4A0h
0x140054b9b  pop     r15
0x140054b9d  pop     r14
0x140054b9f  pop     r12
0x140054ba1  pop     rdi
0x140054ba2  pop     rsi
0x140054ba3  pop     rbx
0x140054ba4  pop     rbp
0x140054ba5  retn
```
