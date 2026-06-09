# RemoveDirectoryAndChildren(char const *)

- ea: `0x14000abd4`
- end: `0x14000ae65`
- name: `?RemoveDirectoryAndChildren@@YAJPEBD@Z`
- size: `657`
- prototype: `__int64 __fastcall(const char *)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14000447c`
- `0x140005924`
- `0x14000747c`
- `0x140008c74`
- `0x14000abd4`

## callees

- `0x140001af3`
- `0x14000abd4`
- `0x14000b654`
- `0x14000ba00`
- `0x1400109c0`

## import_xrefs

- `KERNEL32!SetFileAttributesA` at `0x14000ad6f`
- `KERNEL32!SetFileAttributesA` at `0x14000ad91`
- `KERNEL32!SetFileAttributesA` at `0x14000ad6f`
- `KERNEL32!SetFileAttributesA` at `0x14000ad91`
- `KERNEL32!FindFirstFileA` at `0x14000acde`
- `KERNEL32!FindFirstFileA` at `0x14000acde`
- `KERNEL32!FindNextFileA` at `0x14000adb9`
- `KERNEL32!FindNextFileA` at `0x14000adb9`
- `KERNEL32!FindClose` at `0x14000adfc`
- `KERNEL32!FindClose` at `0x14000ae0d`
- `KERNEL32!FindClose` at `0x14000adfc`
- `KERNEL32!FindClose` at `0x14000ae0d`
- `KERNEL32!lstrcmpA` at `0x14000ad03`
- `KERNEL32!lstrcmpA` at `0x14000ad23`
- `KERNEL32!lstrcmpA` at `0x14000ad03`
- `KERNEL32!lstrcmpA` at `0x14000ad23`
- `KERNEL32!RemoveDirectoryA` at `0x14000ac38`
- `KERNEL32!RemoveDirectoryA` at `0x14000ae1c`
- `KERNEL32!RemoveDirectoryA` at `0x14000ac38`
- `KERNEL32!RemoveDirectoryA` at `0x14000ae1c`
- `KERNEL32!DeleteFileA` at `0x14000ada1`
- `KERNEL32!DeleteFileA` at `0x14000ada1`
- `KERNEL32!GetLastError` at `0x14000adcd`
- `KERNEL32!GetLastError` at `0x14000adde`
- `KERNEL32!GetLastError` at `0x14000ae2c`
- `KERNEL32!GetLastError` at `0x14000adcd`
- `KERNEL32!GetLastError` at `0x14000adde`
- `KERNEL32!GetLastError` at `0x14000ae2c`

## pseudocode

```c
__int64 __fastcall RemoveDirectoryAndChildren(const char *a1)
{
  signed int v2; // ebx
  CHAR *p_PathName; // rdx
  __int64 v4; // rcx
  __int64 v5; // rax
  const char *v6; // r8
  CHAR *v7; // rax
  __int64 v8; // rax
  HANDLE FirstFileA; // rsi
  signed int LastError; // eax
  signed int v11; // eax
  struct _WIN32_FIND_DATAA FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  CHAR PathName; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v15[271]; // [rsp+171h] [rbp+71h] BYREF

  v2 = 0;
  PathName = 0;
  memset_0(v15, 0, 0x103u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( a1 && *a1 && !RemoveDirectoryA(a1) )
  {
    p_PathName = &PathName;
    v4 = 260;
    v5 = 2147483646;
    v6 = a1;
    do
    {
      if ( !v5 )
        break;
      if ( !*v6 )
        break;
      *p_PathName++ = *v6++;
      --v5;
      --v4;
    }
    while ( v4 );
    v7 = p_PathName - 1;
    v2 = v4 == 0 ? 0x8007007A : 0;
    if ( v4 )
      v7 = p_PathName;
    *v7 = 0;
    if ( v4 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v15[v8 - 1] );
      v2 = StringCchCatA(&PathName, 260 - v8, "\\*");
      if ( v2 >= 0 )
      {
        FirstFileA = FindFirstFileA(&PathName, &FindFileData);
        if ( FirstFileA == (HANDLE)-1LL )
          goto LABEL_28;
        do
        {
          if ( lstrcmpA(FindFileData.cFileName, ".") && lstrcmpA(FindFileData.cFileName, "..") )
          {
            v2 = StringCchPrintfA(&PathName, 0x103u, "%s\\%s", a1, FindFileData.cFileName);
            if ( v2 < 0 )
              goto LABEL_26;
            if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
            {
              SetFileAttributesA(&PathName, 0x90u);
              v2 = RemoveDirectoryAndChildren(&PathName);
              if ( v2 < 0 )
                goto LABEL_26;
            }
            else
            {
              SetFileAttributesA(&PathName, 0x80u);
              if ( !DeleteFileA(&PathName) )
                goto LABEL_24;
            }
          }
        }
        while ( FindNextFileA(FirstFileA, &FindFileData) );
        if ( GetLastError() != 18 )
        {
LABEL_24:
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError > 0 )
            v2 = (unsigned __int16)LastError | 0x80070000;
LABEL_26:
          FindClose(FirstFileA);
          return (unsigned int)v2;
        }
        FindClose(FirstFileA);
        if ( !RemoveDirectoryA(a1) )
        {
LABEL_28:
          v11 = GetLastError();
          v2 = v11;
          if ( v11 > 0 )
            return (unsigned __int16)v11 | 0x80070000;
        }
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000abd4  push    rbp
0x14000abd6  push    rbx
0x14000abd7  push    rsi
0x14000abd8  push    rdi
0x14000abd9  lea     rbp, [rsp-198h]
0x14000abe1  sub     rsp, 298h
0x14000abe8  mov     rax, cs:__security_cookie
0x14000abef  xor     rax, rsp
0x14000abf2  mov     [rbp+1B0h+var_30], rax
0x14000abf9  mov     rdi, rcx
0x14000abfc  xor     ebx, ebx
0x14000abfe  lea     rcx, [rbp+1B0h+var_13F]; void *
0x14000ac02  mov     [rbp+1B0h+PathName], bl
0x14000ac05  xor     edx, edx; Val
0x14000ac07  mov     r8d, 103h; Size
0x14000ac0d  call    memset_0
0x14000ac12  xor     edx, edx; Val
0x14000ac14  lea     rcx, [rsp+2B0h+FindFileData]; void *
0x14000ac19  mov     r8d, 140h; Size
0x14000ac1f  call    memset_0
0x14000ac24  test    rdi, rdi
0x14000ac27  jz      loc_14000AE47
0x14000ac2d  cmp     [rdi], bl
0x14000ac2f  jz      loc_14000AE47
0x14000ac35  mov     rcx, rdi; lpPathName
0x14000ac38  call    cs:__imp_RemoveDirectoryA
0x14000ac3f  nop     dword ptr [rax+rax+00h]
0x14000ac44  test    eax, eax
0x14000ac46  jnz     loc_14000AE47
0x14000ac4c  mov     r10d, 104h
0x14000ac52  lea     rdx, [rbp+1B0h+PathName]
0x14000ac56  mov     ecx, r10d
0x14000ac59  mov     eax, 7FFFFFFEh
0x14000ac5e  mov     r8, rdi
0x14000ac61  test    rax, rax
0x14000ac64  jz      short loc_14000AC80
0x14000ac66  mov     r9b, [r8]
0x14000ac69  test    r9b, r9b
0x14000ac6c  jz      short loc_14000AC80
0x14000ac6e  mov     [rdx], r9b
0x14000ac71  inc     r8
0x14000ac74  inc     rdx
0x14000ac77  dec     rax
0x14000ac7a  sub     rcx, 1
0x14000ac7e  jnz     short loc_14000AC61
0x14000ac80  mov     rax, rcx
0x14000ac83  neg     rax
0x14000ac86  lea     rax, [rdx-1]
0x14000ac8a  sbb     ebx, ebx
0x14000ac8c  not     ebx
0x14000ac8e  and     ebx, 8007007Ah
0x14000ac94  test    rcx, rcx
0x14000ac97  cmovnz  rax, rdx
0x14000ac9b  mov     byte ptr [rax], 0
0x14000ac9e  jz      loc_14000AE47
0x14000aca4  lea     rcx, [rbp+1B0h+PathName]
0x14000aca8  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000acac  inc     rax
0x14000acaf  cmp     byte ptr [rcx+rax], 0
0x14000acb3  jnz     short loc_14000ACAC
0x14000acb5  sub     r10, rax
0x14000acb8  lea     r8, asc_140013304; "\\*"
0x14000acbf  mov     rdx, r10; unsigned __int64
0x14000acc2  lea     rcx, [rbp+1B0h+PathName]; char *
0x14000acc6  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x14000accb  mov     ebx, eax
0x14000accd  test    eax, eax
0x14000accf  js      loc_14000AE47
0x14000acd5  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x14000acda  lea     rcx, [rbp+1B0h+PathName]; lpFileName
0x14000acde  call    cs:__imp_FindFirstFileA
0x14000ace5  nop     dword ptr [rax+rax+00h]
0x14000acea  mov     rsi, rax
0x14000aced  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000acf1  jz      loc_14000AE2C
0x14000acf7  lea     rdx, String2; "."
0x14000acfe  lea     rcx, [rsp+2B0h+FindFileData.cFileName]; lpString1
0x14000ad03  call    cs:__imp_lstrcmpA
0x14000ad0a  nop     dword ptr [rax+rax+00h]
0x14000ad0f  test    eax, eax
0x14000ad11  jz      loc_14000ADB1
0x14000ad17  lea     rdx, asc_14001330C; ".."
0x14000ad1e  lea     rcx, [rsp+2B0h+FindFileData.cFileName]; lpString1
0x14000ad23  call    cs:__imp_lstrcmpA
0x14000ad2a  nop     dword ptr [rax+rax+00h]
0x14000ad2f  test    eax, eax
0x14000ad31  jz      short loc_14000ADB1
0x14000ad33  lea     rax, [rsp+2B0h+FindFileData.cFileName]
0x14000ad38  mov     r9, rdi
0x14000ad3b  lea     r8, aSS_1; "%s\\%s"
0x14000ad42  mov     [rsp+2B0h+var_290], rax
0x14000ad47  mov     edx, 103h; unsigned __int64
0x14000ad4c  lea     rcx, [rbp+1B0h+PathName]; char *
0x14000ad50  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14000ad55  mov     ebx, eax
0x14000ad57  test    eax, eax
0x14000ad59  js      loc_14000ADF9
0x14000ad5f  test    byte ptr [rsp+2B0h+FindFileData.dwFileAttributes], 10h
0x14000ad64  lea     rcx, [rbp+1B0h+PathName]; lpFileName
0x14000ad68  jz      short loc_14000AD8C
0x14000ad6a  mov     edx, 90h; dwFileAttributes
0x14000ad6f  call    cs:__imp_SetFileAttributesA
0x14000ad76  nop     dword ptr [rax+rax+00h]
0x14000ad7b  lea     rcx, [rbp+1B0h+PathName]; char *
0x14000ad7f  call    ?RemoveDirectoryAndChildren@@YAJPEBD@Z; RemoveDirectoryAndChildren(char const *)
0x14000ad84  mov     ebx, eax
0x14000ad86  test    eax, eax
0x14000ad88  js      short loc_14000ADF9
0x14000ad8a  jmp     short loc_14000ADB1
0x14000ad8c  mov     edx, 80h; dwFileAttributes
0x14000ad91  call    cs:__imp_SetFileAttributesA
0x14000ad98  nop     dword ptr [rax+rax+00h]
0x14000ad9d  lea     rcx, [rbp+1B0h+PathName]; lpFileName
0x14000ada1  call    cs:__imp_DeleteFileA
0x14000ada8  nop     dword ptr [rax+rax+00h]
0x14000adad  test    eax, eax
0x14000adaf  jz      short loc_14000ADDE
0x14000adb1  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x14000adb6  mov     rcx, rsi; hFindFile
0x14000adb9  call    cs:__imp_FindNextFileA
0x14000adc0  nop     dword ptr [rax+rax+00h]
0x14000adc5  test    eax, eax
0x14000adc7  jnz     loc_14000ACF7
0x14000adcd  call    cs:__imp_GetLastError
0x14000add4  nop     dword ptr [rax+rax+00h]
0x14000add9  cmp     eax, 12h
0x14000addc  jz      short loc_14000AE0A
0x14000adde  call    cs:__imp_GetLastError
0x14000ade5  nop     dword ptr [rax+rax+00h]
0x14000adea  mov     ebx, eax
0x14000adec  test    eax, eax
0x14000adee  jle     short loc_14000ADF9
0x14000adf0  movzx   ebx, ax
0x14000adf3  or      ebx, 80070000h
0x14000adf9  mov     rcx, rsi; hFindFile
0x14000adfc  call    cs:__imp_FindClose
0x14000ae03  nop     dword ptr [rax+rax+00h]
0x14000ae08  jmp     short loc_14000AE47
0x14000ae0a  mov     rcx, rsi; hFindFile
0x14000ae0d  call    cs:__imp_FindClose
0x14000ae14  nop     dword ptr [rax+rax+00h]
0x14000ae19  mov     rcx, rdi; lpPathName
0x14000ae1c  call    cs:__imp_RemoveDirectoryA
0x14000ae23  nop     dword ptr [rax+rax+00h]
0x14000ae28  test    eax, eax
0x14000ae2a  jnz     short loc_14000AE47
0x14000ae2c  call    cs:__imp_GetLastError
0x14000ae33  nop     dword ptr [rax+rax+00h]
0x14000ae38  mov     ebx, eax
0x14000ae3a  test    eax, eax
0x14000ae3c  jle     short loc_14000AE47
0x14000ae3e  movzx   ebx, ax
0x14000ae41  or      ebx, 80070000h
0x14000ae47  mov     eax, ebx
0x14000ae49  mov     rcx, [rbp+1B0h+var_30]
0x14000ae50  xor     rcx, rsp; StackCookie
0x14000ae53  call    __security_check_cookie
0x14000ae58  add     rsp, 298h
0x14000ae5f  pop     rdi
0x14000ae60  pop     rsi
0x14000ae61  pop     rbx
0x14000ae62  pop     rbp
0x14000ae63  retn
```
