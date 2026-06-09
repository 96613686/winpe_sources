# InitializeRegTermsrvFpns

- ea: `0x1800315f8`
- end: `0x18003178f`
- name: `InitializeRegTermsrvFpns`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800389dc`

## callees

- `0x1800315f8`
- `0x1800318b8`
- `0x1800318f8`
- `0x180031ba8`
- `0x180031d8c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031689`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800316a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800316c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800316e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800316fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003171a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031737`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031754`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031771`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031689`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800316a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800316c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800316e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800316fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003171a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031737`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031754`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031771`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180031667`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180031667`

## string_xrefs

- `0x180031657`: `tsappcmp.dll`
- `0x18003167f`: `TermsrvCreateRegEntry`
- `0x180031695`: `TermsrvOpenRegEntry`
- `0x1800316ec`: `TermsrvDeleteValue`
- `0x1800316cf`: `TermsrvDeleteKey`
- `0x180031726`: `TermsrvSetKeySecurity`
- `0x180031743`: `TermsrvOpenUserClasses`

## pseudocode

```c
char __fastcall InitializeRegTermsrvFpns(__int64 a1, _DWORD *a2)
{
  int CompatFlags; // eax
  __int16 v6; // bx
  char v7; // di
  HMODULE Library; // rax
  HMODULE v9; // rbx

  if ( (unsigned int)IsTerminalServerCompatible() || !(unsigned int)IsRegTSAppCompatEnabled(a1) )
    return 0;
  CompatFlags = GetCompatFlags();
  v6 = CompatFlags;
  *a2 = CompatFlags;
  if ( (unsigned int)IsSystemLUID() )
  {
    if ( (v6 & 0x2008) == 0x2008 )
      goto LABEL_8;
    return 0;
  }
  if ( (v6 & 0x108) == 0x108 )
    return 0;
LABEL_8:
  v7 = 0;
  Library = LoadLibraryExW(L"tsappcmp.dll", 0, 0x800u);
  v9 = Library;
  if ( Library )
  {
    qword_1800BDD10 = (__int64)GetProcAddress(Library, "TermsrvCreateRegEntry");
    qword_1800BDD18 = (__int64)GetProcAddress(v9, "TermsrvOpenRegEntry");
    qword_1800BDD20 = (__int64)GetProcAddress(v9, "TermsrvSetValueKey");
    qword_1800BDD28 = (__int64)GetProcAddress(v9, "TermsrvDeleteKey");
    qword_1800BDD30 = (__int64)GetProcAddress(v9, "TermsrvDeleteValue");
    qword_1800BDD38 = (__int64)GetProcAddress(v9, "TermsrvRestoreKey");
    qword_1800BDD40 = (__int64)GetProcAddress(v9, "TermsrvSetKeySecurity");
    qword_1800BDD48 = (__int64)GetProcAddress(v9, "TermsrvOpenUserClasses");
    qword_1800BDD50 = (__int64)GetProcAddress(v9, "TermsrvGetPreSetValue");
    return 1;
  }
  return v7;
}

```

## disassembly

```asm
0x1800315f8  mov     [rsp+arg_0], rbx
0x1800315fd  push    rdi
0x1800315fe  sub     rsp, 20h
0x180031602  mov     rdi, rdx
0x180031605  mov     rbx, rcx
0x180031608  call    IsTerminalServerCompatible
0x18003160d  test    eax, eax
0x18003160f  jz      short loc_18003161F
0x180031611  xor     al, al
0x180031613  mov     rbx, [rsp+28h+arg_0]
0x180031618  add     rsp, 20h
0x18003161c  pop     rdi
0x18003161d  retn
0x18003161f  mov     rcx, rbx
0x180031622  call    IsRegTSAppCompatEnabled
0x180031627  test    eax, eax
0x180031629  jz      short loc_180031611
0x18003162b  call    GetCompatFlags
0x180031630  mov     ebx, eax
0x180031632  mov     [rdi], eax
0x180031634  call    IsSystemLUID
0x180031639  test    eax, eax
0x18003163b  jz      short loc_18003164A
0x18003163d  mov     eax, 2008h
0x180031642  and     ebx, eax
0x180031644  cmp     ebx, eax
0x180031646  jnz     short loc_180031611
0x180031648  jmp     short loc_180031655
0x18003164a  mov     eax, 108h
0x18003164f  and     ebx, eax
0x180031651  cmp     ebx, eax
0x180031653  jz      short loc_180031611
0x180031655  xor     edx, edx; hFile
0x180031657  lea     rcx, aTsappcmpDll; "tsappcmp.dll"
0x18003165e  mov     r8d, 800h; dwFlags
0x180031664  xor     dil, dil
0x180031667  call    cs:__imp_LoadLibraryExW
0x18003166e  nop     dword ptr [rax+rax+00h]
0x180031673  mov     rbx, rax
0x180031676  test    rax, rax
0x180031679  jz      loc_180031787
0x18003167f  lea     rdx, aTermsrvcreater_0; "TermsrvCreateRegEntry"
0x180031686  mov     rcx, rax; hModule
0x180031689  call    cs:__imp_GetProcAddress
0x180031690  nop     dword ptr [rax+rax+00h]
0x180031695  lea     rdx, aTermsrvopenreg_0; "TermsrvOpenRegEntry"
0x18003169c  mov     rcx, rbx; hModule
0x18003169f  mov     cs:qword_1800BDD10, rax
0x1800316a6  call    cs:__imp_GetProcAddress
0x1800316ad  nop     dword ptr [rax+rax+00h]
0x1800316b2  lea     rdx, aTermsrvsetvalu_0; "TermsrvSetValueKey"
0x1800316b9  mov     rcx, rbx; hModule
0x1800316bc  mov     cs:qword_1800BDD18, rax
0x1800316c3  call    cs:__imp_GetProcAddress
0x1800316ca  nop     dword ptr [rax+rax+00h]
0x1800316cf  lea     rdx, aTermsrvdeletek_0; "TermsrvDeleteKey"
0x1800316d6  mov     rcx, rbx; hModule
0x1800316d9  mov     cs:qword_1800BDD20, rax
0x1800316e0  call    cs:__imp_GetProcAddress
0x1800316e7  nop     dword ptr [rax+rax+00h]
0x1800316ec  lea     rdx, aTermsrvdeletev_0; "TermsrvDeleteValue"
0x1800316f3  mov     rcx, rbx; hModule
0x1800316f6  mov     cs:qword_1800BDD28, rax
0x1800316fd  call    cs:__imp_GetProcAddress
0x180031704  nop     dword ptr [rax+rax+00h]
0x180031709  lea     rdx, aTermsrvrestore_0; "TermsrvRestoreKey"
0x180031710  mov     rcx, rbx; hModule
0x180031713  mov     cs:qword_1800BDD30, rax
0x18003171a  call    cs:__imp_GetProcAddress
0x180031721  nop     dword ptr [rax+rax+00h]
0x180031726  lea     rdx, aTermsrvsetkeys_0; "TermsrvSetKeySecurity"
0x18003172d  mov     rcx, rbx; hModule
0x180031730  mov     cs:qword_1800BDD38, rax
0x180031737  call    cs:__imp_GetProcAddress
0x18003173e  nop     dword ptr [rax+rax+00h]
0x180031743  lea     rdx, aTermsrvopenuse_0; "TermsrvOpenUserClasses"
0x18003174a  mov     rcx, rbx; hModule
0x18003174d  mov     cs:qword_1800BDD40, rax
0x180031754  call    cs:__imp_GetProcAddress
0x18003175b  nop     dword ptr [rax+rax+00h]
0x180031760  lea     rdx, aTermsrvgetpres_0; "TermsrvGetPreSetValue"
0x180031767  mov     rcx, rbx; hModule
0x18003176a  mov     cs:qword_1800BDD48, rax
0x180031771  call    cs:__imp_GetProcAddress
0x180031778  nop     dword ptr [rax+rax+00h]
0x18003177d  mov     cs:qword_1800BDD50, rax
0x180031784  mov     dil, 1
0x180031787  mov     al, dil
0x18003178a  jmp     loc_180031613
```
