# CW32System::SysFreeString(ushort *)

- ea: `0x180043e7c`
- end: `0x180043f25`
- name: `?SysFreeString@CW32System@@SAXPEAG@Z`
- size: `169`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `93`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000c7f8`
- `0x180015720`
- `0x18001799c`
- `0x180044334`
- `0x180062054`
- `0x18008a1b4`
- `0x18009b294`
- `0x1800aad30`
- `0x1800b61b0`
- `0x1800cf408`
- `0x1800d134c`
- `0x1800da730`
- `0x1800e2b70`
- `0x1800e5cc8`
- `0x1800ea7d4`
- `0x1800eb604`
- `0x1800ed64c`
- `0x1800f00c4`
- `0x1800f5bc4`
- `0x1800fee8c`
- `0x1800ff7d0`
- `0x1800ff9d0`
- `0x1800ffda0`
- `0x180109a20`
- `0x180110e08`
- `0x18012a13c`
- `0x18012a92c`
- `0x18012cf44`
- `0x18012de04`
- `0x18012fbb0`
- `0x1801367fc`
- `0x180137a6c`
- `0x18013b874`
- `0x180147b4c`
- `0x1801504ac`
- `0x180156640`
- `0x18015b478`
- `0x18015b7ac`
- `0x18015c4cc`
- `0x18015c790`
- `0x18015cbe4`
- `0x18015d5f8`
- `0x18015d9a8`
- `0x18015ed60`
- `0x18015f140`
- `0x180160d9c`
- `0x180164090`
- `0x180166a04`
- `0x180171060`
- `0x180176d7c`

## callees

- `0x18000f358`
- `0x180043e7c`
- `0x18005921c`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043ef1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043ef1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180043ecf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180043ecf`

## string_xrefs

- `0x180043ec2`: `oleaut32.dll`

## pseudocode

```c
void __fastcall CW32System::SysFreeString(unsigned __int16 *a1)
{
  void (__fastcall *v1)(unsigned __int16 *); // rax
  HMODULE Library; // rax
  unsigned int v4; // [rsp+38h] [rbp+10h] BYREF

  v1 = (void (__fastcall *)(unsigned __int16 *))qword_1802E26F8;
  if ( qword_1802E26F8 )
    goto LABEL_2;
  CWriteLock::CWriteLock(&v4, 0);
  if ( !qword_1802E26F8 )
  {
    Library = qword_1802E4270;
    if ( qword_1802E4270 || (Library = LoadLibraryExW(L"oleaut32.dll", 0, 0x800u), (qword_1802E4270 = Library) != 0) )
      qword_1802E26F8 = (__int64)GetProcAddress(Library, "SysFreeString");
  }
  CWriteLock::~CWriteLock((CWriteLock *)&v4);
  v1 = (void (__fastcall *)(unsigned __int16 *))qword_1802E26F8;
  if ( qword_1802E26F8 )
LABEL_2:
    v1(a1);
}

```

## disassembly

```asm
0x180043e7c  push    rbx
0x180043e7e  sub     rsp, 20h
0x180043e82  mov     rax, cs:qword_1802E26F8
0x180043e89  mov     rbx, rcx
0x180043e8c  test    rax, rax
0x180043e8f  jz      short loc_180043E9E
0x180043e91  mov     rcx, rbx
0x180043e94  add     rsp, 20h
0x180043e98  pop     rbx
0x180043e99  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180043e9e  xor     edx, edx
0x180043ea0  lea     rcx, [rsp+28h+arg_8]
0x180043ea5  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x180043eaa  cmp     cs:qword_1802E26F8, 0
0x180043eb2  jnz     short loc_180043F04
0x180043eb4  mov     rax, cs:qword_1802E4270
0x180043ebb  test    rax, rax
0x180043ebe  jnz     short loc_180043EE7
0x180043ec0  xor     edx, edx; hFile
0x180043ec2  lea     rcx, aOleaut32Dll_0; "oleaut32.dll"
0x180043ec9  mov     r8d, 800h; dwFlags
0x180043ecf  call    cs:__imp_LoadLibraryExW
0x180043ed6  nop     dword ptr [rax+rax+00h]
0x180043edb  mov     cs:qword_1802E4270, rax
0x180043ee2  test    rax, rax
0x180043ee5  jz      short loc_180043F04
0x180043ee7  lea     rdx, aSysfreestring; "SysFreeString"
0x180043eee  mov     rcx, rax; hModule
0x180043ef1  call    cs:__imp_GetProcAddress
0x180043ef8  nop     dword ptr [rax+rax+00h]
0x180043efd  mov     cs:qword_1802E26F8, rax
0x180043f04  lea     rcx, [rsp+28h+arg_8]; this
0x180043f09  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x180043f0e  mov     rax, cs:qword_1802E26F8
0x180043f15  test    rax, rax
0x180043f18  jnz     loc_180043E91
0x180043f1e  add     rsp, 20h
0x180043f22  pop     rbx
0x180043f23  retn
```
