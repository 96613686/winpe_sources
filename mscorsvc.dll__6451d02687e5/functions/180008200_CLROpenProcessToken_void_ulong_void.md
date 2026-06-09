# CLROpenProcessToken(void *,ulong,void * *)

- ea: `0x180008200`
- end: `0x180008287`
- name: `?CLROpenProcessToken@@YAHPEAXKPEAPEAX@Z`
- size: `135`
- prototype: `__int64 __fastcall(void *, __int64, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800280bc`

## callees

- `0x180008200`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180008230`
- `KERNEL32!LoadLibraryExW` at `0x180008230`
- `KERNEL32!GetProcAddress` at `0x180008245`
- `KERNEL32!GetProcAddress` at `0x180008245`

## string_xrefs

- `0x180008227`: `advapi32.dll`
- `0x18000823b`: `OpenProcessToken`

## pseudocode

```c
__int64 __fastcall CLROpenProcessToken(void *a1, __int64 a2, void **a3)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FFB0;
  if ( qword_18006FFB0 )
    return ((__int64 (__fastcall *)(void *, __int64, void **))ProcAddress)(a1, 983551, a3);
  if ( !bOpenProcessTokenProbed
    && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FFB0)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "OpenProcessToken"), qword_18006FFB0 = (__int64)ProcAddress),
        bOpenProcessTokenProbed = 1,
        ProcAddress) )
  {
    return ((__int64 (__fastcall *)(void *, __int64, void **))ProcAddress)(a1, 983551, a3);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180008200  mov     [rsp+arg_0], rbx
0x180008205  push    rdi
0x180008206  sub     rsp, 20h
0x18000820a  mov     rax, cs:qword_18006FFB0
0x180008211  mov     rbx, r8
0x180008214  mov     rdi, rcx
0x180008217  test    rax, rax
0x18000821a  jnz     short loc_18000826B
0x18000821c  cmp     cs:?bOpenProcessTokenProbed@@3_NA, al; bool bOpenProcessTokenProbed
0x180008222  jnz     short loc_180008267
0x180008224  xor     r8d, r8d; dwFlags
0x180008227  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x18000822e  xor     edx, edx; hFile
0x180008230  call    cs:__imp_LoadLibraryExW
0x180008236  test    rax, rax
0x180008239  jz      short loc_180008254
0x18000823b  lea     rdx, aOpenprocesstok; "OpenProcessToken"
0x180008242  mov     rcx, rax; hModule
0x180008245  call    cs:__imp_GetProcAddress
0x18000824b  mov     cs:qword_18006FFB0, rax
0x180008252  jmp     short loc_18000825B
0x180008254  mov     rax, cs:qword_18006FFB0
0x18000825b  mov     cs:?bOpenProcessTokenProbed@@3_NA, 1; bool bOpenProcessTokenProbed
0x180008262  test    rax, rax
0x180008265  jnz     short loc_18000826B
0x180008267  xor     eax, eax
0x180008269  jmp     short loc_18000827C
0x18000826b  mov     r8, rbx
0x18000826e  mov     edx, 0F01FFh
0x180008273  mov     rcx, rdi
0x180008276  call    cs:__guard_dispatch_icall_fptr
0x18000827c  mov     rbx, [rsp+28h+arg_0]
0x180008281  add     rsp, 20h
0x180008285  pop     rdi
0x180008286  retn
```
