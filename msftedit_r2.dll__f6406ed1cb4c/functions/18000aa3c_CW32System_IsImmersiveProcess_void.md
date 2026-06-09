# CW32System::IsImmersiveProcess(void *)

- ea: `0x18000aa3c`
- end: `0x18000aae5`
- name: `?IsImmersiveProcess@CW32System@@SAHPEAX@Z`
- size: `169`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000ac94`

## callees

- `0x18000aa3c`
- `0x18000f358`
- `0x18005921c`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aaa8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aaa8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000aa86`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000aa86`

## string_xrefs

- `0x18000aa79`: `user32.dll`

## pseudocode

```c
__int64 (__fastcall *__fastcall CW32System::IsImmersiveProcess(void *a1))(void *)
{
  __int64 (__fastcall *result)(void *); // rax
  HMODULE Library; // rax
  unsigned int v4; // [rsp+38h] [rbp+10h] BYREF

  result = (__int64 (__fastcall *)(void *))qword_1802E41D8;
  if ( qword_1802E41D8 )
    return (__int64 (__fastcall *)(void *))result(a1);
  CWriteLock::CWriteLock(&v4, 0);
  if ( !qword_1802E41D8 )
  {
    Library = hModule;
    if ( hModule || (Library = LoadLibraryExW(L"user32.dll", 0, 0x800u), (hModule = Library) != 0) )
      qword_1802E41D8 = (__int64)GetProcAddress(Library, "IsImmersiveProcess");
  }
  CWriteLock::~CWriteLock((CWriteLock *)&v4);
  result = (__int64 (__fastcall *)(void *))qword_1802E41D8;
  if ( qword_1802E41D8 )
    return (__int64 (__fastcall *)(void *))result(a1);
  return result;
}

```

## disassembly

```asm
0x18000aa3c  push    rbx
0x18000aa3e  sub     rsp, 20h
0x18000aa42  mov     rax, cs:qword_1802E41D8
0x18000aa49  mov     rbx, rcx
0x18000aa4c  test    rax, rax
0x18000aa4f  jnz     loc_18000AAD8
0x18000aa55  xor     edx, edx
0x18000aa57  lea     rcx, [rsp+28h+arg_8]
0x18000aa5c  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x18000aa61  cmp     cs:qword_1802E41D8, 0
0x18000aa69  jnz     short loc_18000AABB
0x18000aa6b  mov     rax, cs:hModule
0x18000aa72  test    rax, rax
0x18000aa75  jnz     short loc_18000AA9E
0x18000aa77  xor     edx, edx; hFile
0x18000aa79  lea     rcx, LibFileName; "user32.dll"
0x18000aa80  mov     r8d, 800h; dwFlags
0x18000aa86  call    cs:__imp_LoadLibraryExW
0x18000aa8d  nop     dword ptr [rax+rax+00h]
0x18000aa92  mov     cs:hModule, rax
0x18000aa99  test    rax, rax
0x18000aa9c  jz      short loc_18000AABB
0x18000aa9e  lea     rdx, ProcName; "IsImmersiveProcess"
0x18000aaa5  mov     rcx, rax; hModule
0x18000aaa8  call    cs:__imp_GetProcAddress
0x18000aaaf  nop     dword ptr [rax+rax+00h]
0x18000aab4  mov     cs:qword_1802E41D8, rax
0x18000aabb  lea     rcx, [rsp+28h+arg_8]; this
0x18000aac0  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x18000aac5  mov     rax, cs:qword_1802E41D8
0x18000aacc  test    rax, rax
0x18000aacf  jnz     short loc_18000AAD8
0x18000aad1  add     rsp, 20h
0x18000aad5  pop     rbx
0x18000aad6  retn
0x18000aad8  mov     rcx, rbx
0x18000aadb  add     rsp, 20h
0x18000aadf  pop     rbx
0x18000aae0  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
