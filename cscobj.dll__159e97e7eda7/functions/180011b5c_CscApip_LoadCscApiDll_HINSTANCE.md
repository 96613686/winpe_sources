# CscApip_LoadCscApiDll(HINSTANCE__ * *)

- ea: `0x180011b5c`
- end: `0x180011bf2`
- name: `?CscApip_LoadCscApiDll@@YAJPEAPEAUHINSTANCE__@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(HINSTANCE *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180011998`
- `0x180011a78`

## callees

- `0x1800084e0`
- `0x180009864`
- `0x18000f5cc`
- `0x180011b5c`
- `0x18002a270`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180011b95`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180011b95`

## string_xrefs

- `0x180011b70`: `%systemroot%\system32\cscapi.dll`

## pseudocode

```c
__int64 __fastcall CscApip_LoadCscApiDll(HINSTANCE *a1)
{
  int Error; // ebx
  HMODULE LibraryW; // rax
  void *v4; // rdx
  UstVarLib *v5; // rcx
  LPCWSTR lpLibFileName; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  lpLibFileName = 0;
  Error = CscUtil_ExpandEnvironmentStringsAlloc(
            L"%systemroot%\\system32\\cscapi.dll",
            (unsigned __int16 **)&lpLibFileName);
  if ( Error >= 0 )
  {
    LibraryW = LoadLibraryW(lpLibFileName);
    *a1 = LibraryW;
    if ( !LibraryW )
    {
      Error = UstVarLib::ResultFromLastError(v5);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          10,
          WPP_40a70a3e45b638f5dc509d2906e6a248_Traceguids,
          (unsigned int)Error);
    }
    CscUtil_HeapFree((void *)lpLibFileName, v4);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180011b5c  mov     [rsp+arg_8], rbx
0x180011b61  push    rdi
0x180011b62  sub     rsp, 20h
0x180011b66  mov     rdi, rcx
0x180011b69  mov     qword ptr [rcx], 0
0x180011b70  lea     rcx, Src; "%systemroot%\\system32\\cscapi.dll"
0x180011b77  mov     [rsp+28h+lpLibFileName], 0
0x180011b80  lea     rdx, [rsp+28h+lpLibFileName]; unsigned __int16 **
0x180011b85  call    ?CscUtil_ExpandEnvironmentStringsAlloc@@YAJPEBGPEAPEAG@Z; CscUtil_ExpandEnvironmentStringsAlloc(ushort const *,ushort * *)
0x180011b8a  mov     ebx, eax
0x180011b8c  test    eax, eax
0x180011b8e  js      short loc_180011BE5
0x180011b90  mov     rcx, [rsp+28h+lpLibFileName]; lpLibFileName
0x180011b95  call    cs:__imp_LoadLibraryW
0x180011b9b  mov     [rdi], rax
0x180011b9e  test    rax, rax
0x180011ba1  jnz     short loc_180011BDB
0x180011ba3  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x180011ba8  mov     ebx, eax
0x180011baa  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bb1  lea     rax, WPP_GLOBAL_Control
0x180011bb8  cmp     rcx, rax
0x180011bbb  jz      short loc_180011BDB
0x180011bbd  test    byte ptr [rcx+1Ch], 2
0x180011bc1  jz      short loc_180011BDB
0x180011bc3  mov     rcx, [rcx+10h]
0x180011bc7  lea     r8, WPP_40a70a3e45b638f5dc509d2906e6a248_Traceguids
0x180011bce  mov     edx, 0Ah
0x180011bd3  mov     r9d, ebx
0x180011bd6  call    WPP_SF_d
0x180011bdb  mov     rcx, [rsp+28h+lpLibFileName]; lpMem
0x180011be0  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180011be5  mov     eax, ebx
0x180011be7  mov     rbx, [rsp+28h+arg_8]
0x180011bec  add     rsp, 20h
0x180011bf0  pop     rdi
0x180011bf1  retn
```
