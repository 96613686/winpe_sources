# SetProcAddr(void * &,DLL_ENUM,char const *)

- ea: `0x1800dce48`
- end: `0x1800dcfdb`
- name: `?SetProcAddr@@YAXAEAPEAXW4DLL_ENUM@@PEBD@Z`
- size: `403`
- prototype: `void __high(void **, enum DLL_ENUM, const char *)`
- caller_count: `77`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800441ac`
- `0x1800d9c80`
- `0x1800dc570`
- `0x1800dc5d0`
- `0x1800dc734`
- `0x1800dc790`
- `0x1800dc8c8`
- `0x1800dcba8`
- `0x1800dcd90`
- `0x1800dd958`
- `0x1800dd9a0`
- `0x1800ddc24`
- `0x1800fed70`
- `0x180109cd0`
- `0x18010e098`
- `0x18010f820`
- `0x180113280`
- `0x180114fd0`
- `0x180127d34`
- `0x1801281e0`
- `0x180128cc8`
- `0x180135018`
- `0x1801358c0`
- `0x180138ae4`
- `0x1801393f0`
- `0x180139470`
- `0x180139908`
- `0x18014720c`
- `0x1801474a4`
- `0x1801474f4`
- `0x180147654`
- `0x1801478c8`
- `0x180147eb8`
- `0x180148cb0`
- `0x180148d48`
- `0x180148de4`
- `0x180148e54`
- `0x180148ec0`
- `0x180148f24`
- `0x180149110`
- `0x180149168`
- `0x1801491c0`
- `0x180149228`
- `0x180149290`
- `0x1801493a0`
- `0x180149414`
- `0x18014948c`
- `0x180149808`
- `0x180149874`
- `0x180151988`

## callees

- `0x18000f358`
- `0x18005921c`
- `0x1800dce48`
- `0x1801401f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dcec9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dcec9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dceab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dcf0e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dcf43`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dcf8c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dcfc3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dceab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dcf0e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dcf43`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dcf8c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dcfc3`

## string_xrefs

- `0x1800dcf01`: `oleaut32.dll`
- `0x1800dce9e`: `user32.dll`
- `0x1800dcf36`: `uiautomationcore.dll`
- `0x1800dcf72`: `combase.dll`
- `0x1800dcf79`: `ole32.dll`
- `0x1800dcfb6`: `oleacc.dll`

## pseudocode

```c
void __fastcall SetProcAddr(FARPROC *a1, int a2, const CHAR *a3)
{
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  HMODULE Library; // rax
  char v10; // al
  const WCHAR *v11; // rcx
  char v12; // [rsp+30h] [rbp+8h] BYREF

  CWriteLock::CWriteLock(&v12, 0);
  if ( !*a1 )
  {
    if ( a2 )
    {
      v6 = a2 - 1;
      if ( v6 )
      {
        v7 = v6 - 1;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            if ( v8 != 1 )
              goto LABEL_10;
            Library = qword_1802E4220;
            if ( qword_1802E4220 )
              goto LABEL_9;
            Library = LoadLibraryExW(L"uiautomationcore.dll", 0, 0x800u);
            qword_1802E4220 = Library;
          }
          else
          {
            Library = hModule;
            if ( hModule )
            {
LABEL_9:
              *a1 = GetProcAddress(Library, a3);
              goto LABEL_10;
            }
            Library = LoadLibraryExW(L"user32.dll", 0, 0x800u);
            hModule = Library;
          }
        }
        else
        {
          Library = (HMODULE)qword_1802E4230;
          if ( qword_1802E4230 )
            goto LABEL_9;
          Library = LoadLibraryExW(L"oleacc.dll", 0, 0x800u);
          qword_1802E4230 = (__int64)Library;
        }
      }
      else
      {
        Library = qword_1802E4268;
        if ( qword_1802E4268 )
          goto LABEL_9;
        v10 = IsRegisterClassWPresent();
        v11 = L"ole32.dll";
        if ( !v10 )
          v11 = L"combase.dll";
        Library = LoadLibraryExW(v11, 0, 0x800u);
        qword_1802E4268 = Library;
      }
    }
    else
    {
      Library = qword_1802E4270;
      if ( qword_1802E4270 )
        goto LABEL_9;
      Library = LoadLibraryExW(L"oleaut32.dll", 0, 0x800u);
      qword_1802E4270 = Library;
    }
    if ( Library )
      goto LABEL_9;
  }
LABEL_10:
  CWriteLock::~CWriteLock((CWriteLock *)&v12);
}

```

## disassembly

```asm
0x1800dce48  mov     [rsp+arg_8], rbx
0x1800dce4d  mov     [rsp+arg_10], rsi
0x1800dce52  push    rdi
0x1800dce53  sub     rsp, 20h
0x1800dce57  mov     ebx, edx
0x1800dce59  mov     rdi, rcx
0x1800dce5c  xor     edx, edx
0x1800dce5e  lea     rcx, [rsp+28h+arg_0]
0x1800dce63  mov     rsi, r8
0x1800dce66  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x1800dce6b  cmp     qword ptr [rdi], 0
0x1800dce6f  jnz     short loc_1800DCED8
0x1800dce71  test    ebx, ebx
0x1800dce73  jz      short loc_1800DCEF3
0x1800dce75  sub     ebx, 1
0x1800dce78  jz      loc_1800DCF5B
0x1800dce7e  sub     ebx, 1
0x1800dce81  jz      loc_1800DCFA4
0x1800dce87  sub     ebx, 1
0x1800dce8a  jnz     loc_1800DCF23
0x1800dce90  mov     rax, cs:hModule
0x1800dce97  test    rax, rax
0x1800dce9a  jnz     short loc_1800DCEC3
0x1800dce9c  xor     edx, edx; hFile
0x1800dce9e  lea     rcx, LibFileName; "user32.dll"
0x1800dcea5  mov     r8d, 800h; dwFlags
0x1800dceab  call    cs:__imp_LoadLibraryExW
0x1800dceb2  nop     dword ptr [rax+rax+00h]
0x1800dceb7  mov     cs:hModule, rax
0x1800dcebe  test    rax, rax
0x1800dcec1  jz      short loc_1800DCED8
0x1800dcec3  mov     rdx, rsi; lpProcName
0x1800dcec6  mov     rcx, rax; hModule
0x1800dcec9  call    cs:__imp_GetProcAddress
0x1800dced0  nop     dword ptr [rax+rax+00h]
0x1800dced5  mov     [rdi], rax
0x1800dced8  lea     rcx, [rsp+28h+arg_0]; this
0x1800dcedd  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x1800dcee2  mov     rbx, [rsp+28h+arg_8]
0x1800dcee7  mov     rsi, [rsp+28h+arg_10]
0x1800dceec  add     rsp, 20h
0x1800dcef0  pop     rdi
0x1800dcef1  retn
0x1800dcef3  mov     rax, cs:qword_1802E4270
0x1800dcefa  test    rax, rax
0x1800dcefd  jnz     short loc_1800DCEC3
0x1800dceff  xor     edx, edx; hFile
0x1800dcf01  lea     rcx, aOleaut32Dll_0; "oleaut32.dll"
0x1800dcf08  mov     r8d, 800h; dwFlags
0x1800dcf0e  call    cs:__imp_LoadLibraryExW
0x1800dcf15  nop     dword ptr [rax+rax+00h]
0x1800dcf1a  mov     cs:qword_1802E4270, rax
0x1800dcf21  jmp     short loc_1800DCEBE
0x1800dcf23  cmp     ebx, 1
0x1800dcf26  jnz     short loc_1800DCED8
0x1800dcf28  mov     rax, cs:qword_1802E4220
0x1800dcf2f  test    rax, rax
0x1800dcf32  jnz     short loc_1800DCEC3
0x1800dcf34  xor     edx, edx; hFile
0x1800dcf36  lea     rcx, aUiautomationco; "uiautomationcore.dll"
0x1800dcf3d  mov     r8d, 800h; dwFlags
0x1800dcf43  call    cs:__imp_LoadLibraryExW
0x1800dcf4a  nop     dword ptr [rax+rax+00h]
0x1800dcf4f  mov     cs:qword_1802E4220, rax
0x1800dcf56  jmp     loc_1800DCEBE
0x1800dcf5b  mov     rax, cs:qword_1802E4268
0x1800dcf62  test    rax, rax
0x1800dcf65  jnz     loc_1800DCEC3
0x1800dcf6b  call    IsRegisterClassWPresent
0x1800dcf70  test    al, al
0x1800dcf72  lea     rdx, aCombaseDll; "combase.dll"
0x1800dcf79  lea     rcx, aOle32Dll; "ole32.dll"
0x1800dcf80  mov     r8d, 800h; dwFlags
0x1800dcf86  cmovz   rcx, rdx; lpLibFileName
0x1800dcf8a  xor     edx, edx; hFile
0x1800dcf8c  call    cs:__imp_LoadLibraryExW
0x1800dcf93  nop     dword ptr [rax+rax+00h]
0x1800dcf98  mov     cs:qword_1802E4268, rax
0x1800dcf9f  jmp     loc_1800DCEBE
0x1800dcfa4  mov     rax, cs:qword_1802E4230
0x1800dcfab  test    rax, rax
0x1800dcfae  jnz     loc_1800DCEC3
0x1800dcfb4  xor     edx, edx; hFile
0x1800dcfb6  lea     rcx, aOleaccDll; "oleacc.dll"
0x1800dcfbd  mov     r8d, 800h; dwFlags
0x1800dcfc3  call    cs:__imp_LoadLibraryExW
0x1800dcfca  nop     dword ptr [rax+rax+00h]
0x1800dcfcf  mov     cs:qword_1802E4230, rax
0x1800dcfd6  jmp     loc_1800DCEBE
```
