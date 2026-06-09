# CW32System::SysAllocStringLen(ushort const *,uint)

- ea: `0x1800440f0`
- end: `0x1800441a6`
- name: `?SysAllocStringLen@CW32System@@SAPEAGPEBGI@Z`
- size: `182`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `28`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180034640`
- `0x180044334`
- `0x180062054`
- `0x1800996c0`
- `0x18009c9d0`
- `0x1800c9394`
- `0x1800eb604`
- `0x1800ed930`
- `0x18010d6a8`
- `0x1801389c8`
- `0x1801789c8`
- `0x1801795e4`
- `0x1801899c0`
- `0x1801977e4`
- `0x180198330`
- `0x1801991b0`
- `0x1801a3440`
- `0x1801b1734`
- `0x1801b18ac`
- `0x1801b25a8`
- `0x1801c19ac`
- `0x1801d5f8c`
- `0x1801daf90`
- `0x1801e0110`
- `0x1801eb1b0`
- `0x1801ec324`
- `0x1801f2100`
- `0x1801f48b0`

## callees

- `0x18000f358`
- `0x1800440f0`
- `0x18005921c`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044174`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044174`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180044152`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180044152`

## string_xrefs

- `0x180044145`: `oleaut32.dll`

## pseudocode

```c
unsigned __int16 *__fastcall CW32System::SysAllocStringLen(const unsigned __int16 *a1, unsigned int a2)
{
  unsigned __int16 *result; // rax
  HMODULE Library; // rax
  unsigned int v6; // [rsp+40h] [rbp+18h] BYREF

  result = (unsigned __int16 *)qword_1802E26E8;
  if ( qword_1802E26E8 )
    return (unsigned __int16 *)((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD))result)(a1, a2);
  CWriteLock::CWriteLock(&v6, 0);
  if ( !qword_1802E26E8 )
  {
    Library = qword_1802E4270;
    if ( qword_1802E4270 || (Library = LoadLibraryExW(L"oleaut32.dll", 0, 0x800u), (qword_1802E4270 = Library) != 0) )
      qword_1802E26E8 = (__int64)GetProcAddress(Library, "SysAllocStringLen");
  }
  CWriteLock::~CWriteLock((CWriteLock *)&v6);
  result = (unsigned __int16 *)qword_1802E26E8;
  if ( qword_1802E26E8 )
    return (unsigned __int16 *)((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD))result)(a1, a2);
  return result;
}

```

## disassembly

```asm
0x1800440f0  mov     [rsp+arg_0], rbx
0x1800440f5  push    rdi
0x1800440f6  sub     rsp, 20h
0x1800440fa  mov     rax, cs:qword_1802E26E8
0x180044101  mov     ebx, edx
0x180044103  mov     rdi, rcx
0x180044106  test    rax, rax
0x180044109  jz      short loc_180044121
0x18004410b  mov     edx, ebx
0x18004410d  mov     rcx, rdi
0x180044110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044115  mov     rbx, [rsp+28h+arg_0]
0x18004411a  add     rsp, 20h
0x18004411e  pop     rdi
0x18004411f  retn
0x180044121  xor     edx, edx
0x180044123  lea     rcx, [rsp+28h+arg_10]
0x180044128  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x18004412d  cmp     cs:qword_1802E26E8, 0
0x180044135  jnz     short loc_180044187
0x180044137  mov     rax, cs:qword_1802E4270
0x18004413e  test    rax, rax
0x180044141  jnz     short loc_18004416A
0x180044143  xor     edx, edx; hFile
0x180044145  lea     rcx, aOleaut32Dll_0; "oleaut32.dll"
0x18004414c  mov     r8d, 800h; dwFlags
0x180044152  call    cs:__imp_LoadLibraryExW
0x180044159  nop     dword ptr [rax+rax+00h]
0x18004415e  mov     cs:qword_1802E4270, rax
0x180044165  test    rax, rax
0x180044168  jz      short loc_180044187
0x18004416a  lea     rdx, aSysallocstring_0; "SysAllocStringLen"
0x180044171  mov     rcx, rax; hModule
0x180044174  call    cs:__imp_GetProcAddress
0x18004417b  nop     dword ptr [rax+rax+00h]
0x180044180  mov     cs:qword_1802E26E8, rax
0x180044187  lea     rcx, [rsp+28h+arg_10]; this
0x18004418c  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x180044191  mov     rax, cs:qword_1802E26E8
0x180044198  test    rax, rax
0x18004419b  jnz     loc_18004410B
0x1800441a1  jmp     loc_180044115
```
