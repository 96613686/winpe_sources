# AslPathIsOnRemovableMedia

- ea: `0x180020554`
- end: `0x18002075c`
- name: `AslPathIsOnRemovableMedia`
- size: `520`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001fabc`
- `0x180020374`

## callees

- `0x180020554`
- `0x1800212e4`
- `0x18005c414`
- `0x18007a840`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180020717`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180020717`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800206d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800206d1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800206e7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800206e7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800206b9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800206b9`

## string_xrefs

- `0x180020686`: `%ws not a full path we can operate on [%x]`
- `0x180020697`: `AslPathIsOnRemovableMedia`
- `0x180020749`: `AslPathIsOnRemovableMedia`
- `0x1800206a7`: `ntdll.dll`
- `0x180020738`: `RtlStringCchCopyW failed for c:\ [%x]`

## pseudocode

```c
__int64 __fastcall AslPathIsOnRemovableMedia(int *a1, wchar_t *a2)
{
  size_t v3; // r14
  int v4; // ebp
  unsigned __int64 v5; // rax
  __int64 v6; // r8
  const wchar_t *v7; // rcx
  __int64 v8; // rax
  wchar_t *v9; // r9
  wchar_t *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rbx
  int v14; // r8d
  HMODULE Library; // rax
  HMODULE v16; // rsi
  __int64 (*ProcAddress)(void); // rax
  UINT DriveTypeW; // ecx
  wchar_t String1[8]; // [rsp+30h] [rbp-48h] BYREF

  v3 = -1;
  v4 = 0;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( v5 < 8 )
  {
    v11 = 0;
    v14 = 263;
LABEL_18:
    AslLogCallPrintf(
      1,
      (unsigned int)"AslPathIsOnRemovableMedia",
      v14,
      (unsigned int)"%ws not a full path we can operate on [%x]");
    goto LABEL_16;
  }
  if ( a2[1] != 58 )
  {
    v11 = 0;
    if ( a2[1] == 92 )
      goto LABEL_16;
    v14 = 274;
    goto LABEL_18;
  }
  v6 = 5;
  v7 = L"c:\\";
  v8 = 2147483646;
  v9 = String1;
  do
  {
    if ( !v8 )
      break;
    if ( !*v7 )
      break;
    *v9++ = *v7++;
    --v8;
    --v6;
  }
  while ( v6 );
  v10 = v9 - 1;
  v11 = v6 == 0 ? 0x80000005 : 0;
  if ( v6 )
    v10 = v9;
  *v10 = 0;
  if ( v6 )
  {
    v12 = (__int64)Src;
    String1[0] = *a2;
    if ( !Src )
    {
      v12 = 2147352624;
      Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
      v16 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
        if ( ProcAddress )
          v12 = ProcAddress();
        FreeLibrary(v16);
      }
      Src = (wchar_t *)v12;
    }
    do
      ++v3;
    while ( String1[v3] );
    if ( wcsnicmp_0(String1, (const wchar_t *)v12, v3) )
    {
      DriveTypeW = GetDriveTypeW(String1);
      if ( ((DriveTypeW - 2) & 0xFFFFFFFC) == 0 && DriveTypeW != 3 )
        v4 = 1;
    }
    v11 = 0;
  }
  else
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"AslPathIsOnRemovableMedia",
      291,
      (unsigned int)"RtlStringCchCopyW failed for c:\\ [%x]");
  }
LABEL_16:
  *a1 = v4;
  return v11;
}

```

## disassembly

```asm
0x180020554  mov     [rsp+arg_10], rbx
0x180020559  mov     [rsp+arg_18], rbp
0x18002055e  push    rsi
0x18002055f  push    rdi
0x180020560  push    r12
0x180020562  push    r14
0x180020564  push    r15
0x180020566  sub     rsp, 50h
0x18002056a  mov     rax, cs:__security_cookie
0x180020571  xor     rax, rsp
0x180020574  mov     [rsp+78h+var_38], rax
0x180020579  xor     r12d, r12d
0x18002057c  mov     r15, rcx
0x18002057f  or      r14, 0FFFFFFFFFFFFFFFFh
0x180020583  mov     ebp, r12d
0x180020586  mov     rax, r14
0x180020589  inc     rax
0x18002058c  cmp     [rdx+rax*2], r12w
0x180020591  jnz     short loc_180020589
0x180020593  cmp     rax, 8
0x180020597  jb      loc_180020678
0x18002059d  cmp     word ptr [rdx+2], 3Ah ; ':'
0x1800205a2  jnz     loc_1800206F9
0x1800205a8  mov     r8d, 5
0x1800205ae  lea     rcx, aC; "c:\\"
0x1800205b5  mov     eax, 7FFFFFFEh
0x1800205ba  lea     r9, [rsp+78h+String1]
0x1800205bf  lea     edi, [r8-4]
0x1800205c3  test    rax, rax
0x1800205c6  jz      short loc_1800205E6
0x1800205c8  movzx   r10d, word ptr [rcx]
0x1800205cc  test    r10w, r10w
0x1800205d0  jz      short loc_1800205E6
0x1800205d2  mov     [r9], r10w
0x1800205d6  add     rcx, 2
0x1800205da  add     r9, 2
0x1800205de  sub     rax, rdi
0x1800205e1  sub     r8, rdi
0x1800205e4  jnz     short loc_1800205C3
0x1800205e6  mov     rax, r8
0x1800205e9  lea     rcx, [r9-2]
0x1800205ed  neg     rax
0x1800205f0  sbb     ebx, ebx
0x1800205f2  not     ebx
0x1800205f4  and     ebx, 80000005h
0x1800205fa  test    r8, r8
0x1800205fd  cmovnz  rcx, r9
0x180020601  mov     [rcx], r12w
0x180020605  jz      loc_180020738
0x18002060b  mov     rbx, cs:Src
0x180020612  movzx   eax, word ptr [rdx]
0x180020615  mov     [rsp+78h+String1], ax
0x18002061a  test    rbx, rbx
0x18002061d  jz      loc_1800206A5
0x180020623  lea     rax, [rsp+78h+String1]
0x180020628  inc     r14
0x18002062b  cmp     [rax+r14*2], r12w
0x180020630  jnz     short loc_180020628
0x180020632  mov     r8, r14; MaxCount
0x180020635  lea     rcx, [rsp+78h+String1]; String1
0x18002063a  mov     rdx, rbx; String2
0x18002063d  call    _wcsnicmp_0
0x180020642  test    eax, eax
0x180020644  jnz     loc_180020712
0x18002064a  mov     ebx, r12d
0x18002064d  mov     [r15], ebp
0x180020650  mov     eax, ebx
0x180020652  mov     rcx, [rsp+78h+var_38]
0x180020657  xor     rcx, rsp; StackCookie
0x18002065a  call    __security_check_cookie
0x18002065f  lea     r11, [rsp+78h+var_28]
0x180020664  mov     rbx, [r11+40h]
0x180020668  mov     rbp, [r11+48h]
0x18002066c  mov     rsp, r11
0x18002066f  pop     r15
0x180020671  pop     r14
0x180020673  pop     r12
0x180020675  pop     rdi
0x180020676  pop     rsi
0x180020677  retn
0x180020678  mov     ebx, r12d
0x18002067b  mov     r8d, 107h
0x180020681  mov     [rsp+78h+var_50], r12d
0x180020686  lea     r9, aWsNotAFullPath; "%ws not a full path we can operate on ["...
0x18002068d  mov     [rsp+78h+var_58], rdx
0x180020692  mov     ecx, 1
0x180020697  lea     rdx, aAslpathisonrem; "AslPathIsOnRemovableMedia"
0x18002069e  call    AslLogCallPrintf
0x1800206a3  jmp     short loc_18002064D
0x1800206a5  xor     edx, edx; hFile
0x1800206a7  lea     rcx, ModuleName; "ntdll.dll"
0x1800206ae  mov     r8d, 800h; dwFlags
0x1800206b4  mov     ebx, 7FFE0030h
0x1800206b9  call    cs:__imp_LoadLibraryExW
0x1800206bf  mov     rsi, rax
0x1800206c2  test    rax, rax
0x1800206c5  jz      short loc_1800206ED
0x1800206c7  lea     rdx, ProcName; "RtlGetNtSystemRoot"
0x1800206ce  mov     rcx, rax; hModule
0x1800206d1  call    cs:__imp_GetProcAddress
0x1800206d7  test    rax, rax
0x1800206da  jz      short loc_1800206E4
0x1800206dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206e1  mov     rbx, rax
0x1800206e4  mov     rcx, rsi; hLibModule
0x1800206e7  call    cs:__imp_FreeLibrary
0x1800206ed  mov     cs:Src, rbx
0x1800206f4  jmp     loc_180020623
0x1800206f9  cmp     word ptr [rdx+2], 5Ch ; '\'
0x1800206fe  mov     ebx, r12d
0x180020701  jz      loc_18002064D
0x180020707  mov     r8d, 112h
0x18002070d  jmp     loc_180020681
0x180020712  lea     rcx, [rsp+78h+String1]; lpRootPathName
0x180020717  call    cs:__imp_GetDriveTypeW
0x18002071d  mov     ecx, eax
0x18002071f  add     eax, 0FFFFFFFEh
0x180020722  test    eax, 0FFFFFFFCh
0x180020727  jnz     loc_18002064A
0x18002072d  cmp     ecx, 3
0x180020730  cmovnz  ebp, edi
0x180020733  jmp     loc_18002064A
0x180020738  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed for c:\\ [%x]"
0x18002073f  mov     dword ptr [rsp+78h+var_58], ebx
0x180020743  mov     r8d, 123h
0x180020749  lea     rdx, aAslpathisonrem; "AslPathIsOnRemovableMedia"
0x180020750  mov     ecx, edi
0x180020752  call    AslLogCallPrintf
0x180020757  jmp     loc_18002064D
```
