# CheckShimImplCallback(ushort *,void *)

- ea: `0x180005300`
- end: `0x180005389`
- name: `?CheckShimImplCallback@@YAHPEAGPEAX@Z`
- size: `137`
- prototype: `__int64 __fastcall(wchar_t *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002f30`

## callees

- `0x180004660`
- `0x180005300`
- `0x180041ac0`
- `0x180045030`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x180005353`
- `KERNEL32!FindFirstFileW` at `0x180005353`
- `KERNEL32!FindClose` at `0x180005362`
- `KERNEL32!FindClose` at `0x180005362`

## string_xrefs

- `0x180005324`: `mscoreei.dll`

## pseudocode

```c
__int64 __fastcall CheckShimImplCallback(wchar_t *a1, void *a2)
{
  HANDLE FirstFileW; // rax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-478h] BYREF
  WCHAR FileName[264]; // [rsp+270h] [rbp-228h] BYREF

  if ( (int)GetShimDllPathName((wchar_t *)L"mscoreei.dll", a1, FileName) < 0 )
    return 0;
  memset_thunk_772440563353939046(&FindFileData, 0, 0x250u);
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    return 0;
  FindClose(FirstFileW);
  return 1;
}

```

## disassembly

```asm
0x180005300  sub     rsp, 498h
0x180005307  mov     rax, cs:__security_cookie
0x18000530e  xor     rax, rsp
0x180005311  mov     [rsp+498h+var_18], rax
0x180005319  mov     rdx, rcx; wchar_t *
0x18000531c  lea     r8, [rsp+498h+FileName]; void *
0x180005324  lea     rcx, aMscoreeiDll; "mscoreei.dll"
0x18000532b  call    GetShimDllPathName
0x180005330  test    eax, eax
0x180005332  js      short loc_180005385
0x180005334  xor     edx, edx; Val
0x180005336  lea     rcx, [rsp+498h+FindFileData]; void *
0x18000533b  mov     r8d, 250h; Size
0x180005341  call    memset$thunk$772440563353939046
0x180005346  lea     rdx, [rsp+498h+FindFileData]; lpFindFileData
0x18000534b  lea     rcx, [rsp+498h+FileName]; lpFileName
0x180005353  call    cs:__imp_FindFirstFileW
0x180005359  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000535d  jz      short loc_180005385
0x18000535f  mov     rcx, rax; hFindFile
0x180005362  call    cs:__imp_FindClose
0x180005368  mov     eax, 1
0x18000536d  mov     rcx, [rsp+498h+var_18]
0x180005375  xor     rcx, rsp; StackCookie
0x180005378  call    __security_check_cookie
0x18000537d  add     rsp, 498h
0x180005384  retn
0x180005385  xor     eax, eax
0x180005387  jmp     short loc_18000536D
```
