# myDsRoleFreeMemory(void *)

- ea: `0x180010168`
- end: `0x18001027b`
- name: `?myDsRoleFreeMemory@@YAXPEAX@Z`
- size: `275`
- prototype: `void __fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000ac20`

## callees

- `0x180008400`
- `0x180008610`
- `0x18000d9f0`
- `0x180010168`
- `0x180012450`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800101f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800101f8`

## string_xrefs

- `0x1800101be`: `netapi32.dll`
- `0x180010184`: `dsrole.dll`
- `0x1800101a7`: `dsrole.dll`
- `0x180010224`: `dsrole.dll`

## pseudocode

```c
void __fastcall myDsRoleFreeMemory(void *a1, void *a2)
{
  HMODULE v3; // rcx
  int v4; // eax
  void *v5; // rdx
  int v6; // eax
  unsigned int v7; // ecx
  FARPROC ProcAddress; // rax
  int v9; // ebx

  v3 = hModule;
  if ( hModule
    || (hModule = myLoadSystem32LibraryEx(L"dsrole.dll", a2, 0), (v3 = hModule) != 0)
    || (v4 = myHLastError(),
        CSPrintErrorLineFileData2(L"dsrole.dll", 0x2A01CBu, v4, 0),
        hModule = myLoadSystem32LibraryEx(L"netapi32.dll", v5, 0),
        (v3 = hModule) != 0) )
  {
    ProcAddress = (FARPROC)qword_1800C4EB0;
    if ( qword_1800C4EB0 )
      goto LABEL_11;
    ProcAddress = GetProcAddress(v3, "DsRoleFreeMemory");
    qword_1800C4EB0 = (__int64)ProcAddress;
    if ( ProcAddress )
      goto LABEL_11;
    v6 = myHLastError();
    v7 = 4129227;
  }
  else
  {
    v6 = myHLastError();
    v7 = 3146187;
  }
  v9 = v6;
  CSPrintErrorLineFile(v7, v6);
  if ( v9 )
  {
    CSPrintErrorLineFileData2(L"dsrole.dll", 0x4801CBu, 1, 0);
    CSPrintErrorLineFileData2(L"DsRoleFreeMemory", 0x4901CBu, 1, 0);
    CSPrintErrorLineFile(0xC701CBu, v9);
    return;
  }
  ProcAddress = (FARPROC)qword_1800C4EB0;
LABEL_11:
  ((void (__fastcall *)(void *))ProcAddress)(a1);
}

```

## disassembly

```asm
0x180010168  mov     [rsp+arg_0], rbx
0x18001016d  push    rdi
0x18001016e  sub     rsp, 20h
0x180010172  mov     rdi, rcx
0x180010175  mov     rcx, cs:hModule; hModule
0x18001017c  test    rcx, rcx
0x18001017f  jnz     short loc_1800101E5
0x180010181  xor     r8d, r8d; unsigned int
0x180010184  lea     rcx, aDsroleDll; "dsrole.dll"
0x18001018b  call    ?myLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; myLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x180010190  mov     cs:hModule, rax
0x180010197  mov     rcx, rax
0x18001019a  test    rax, rax
0x18001019d  jnz     short loc_1800101E5
0x18001019f  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800101a4  xor     r9d, r9d; int
0x1800101a7  lea     rcx, aDsroleDll; "dsrole.dll"
0x1800101ae  mov     r8d, eax; int
0x1800101b1  mov     edx, 2A01CBh; unsigned int
0x1800101b6  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800101bb  xor     r8d, r8d; unsigned int
0x1800101be  lea     rcx, aNetapi32Dll; "netapi32.dll"
0x1800101c5  call    ?myLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; myLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x1800101ca  mov     cs:hModule, rax
0x1800101d1  mov     rcx, rax
0x1800101d4  test    rax, rax
0x1800101d7  jnz     short loc_1800101E5
0x1800101d9  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800101de  mov     ecx, 3001CBh
0x1800101e3  jmp     short loc_180010214
0x1800101e5  mov     rax, cs:qword_1800C4EB0
0x1800101ec  test    rax, rax
0x1800101ef  jnz     short loc_180010268
0x1800101f1  lea     rdx, ProcName; "DsRoleFreeMemory"
0x1800101f8  call    cs:__imp_GetProcAddress
0x1800101fe  mov     cs:qword_1800C4EB0, rax
0x180010205  test    rax, rax
0x180010208  jnz     short loc_180010268
0x18001020a  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001020f  mov     ecx, 3F01CBh; unsigned int
0x180010214  mov     edx, eax; int
0x180010216  mov     ebx, eax
0x180010218  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001021d  test    ebx, ebx
0x18001021f  jz      short loc_180010261
0x180010221  xor     r9d, r9d; int
0x180010224  lea     rcx, aDsroleDll; "dsrole.dll"
0x18001022b  mov     edx, 4801CBh; unsigned int
0x180010230  lea     edi, [r9+1]
0x180010234  mov     r8d, edi; int
0x180010237  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18001023c  xor     r9d, r9d; int
0x18001023f  lea     rcx, aDsrolefreememo_0; "DsRoleFreeMemory"
0x180010246  mov     r8d, edi; int
0x180010249  mov     edx, 4901CBh; unsigned int
0x18001024e  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180010253  mov     edx, ebx; int
0x180010255  mov     ecx, 0C701CBh; unsigned int
0x18001025a  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001025f  jmp     short loc_180010270
0x180010261  mov     rax, cs:qword_1800C4EB0
0x180010268  mov     rcx, rdi
0x18001026b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010270  mov     rbx, [rsp+28h+arg_0]
0x180010275  add     rsp, 20h
0x180010279  pop     rdi
0x18001027a  retn
```
