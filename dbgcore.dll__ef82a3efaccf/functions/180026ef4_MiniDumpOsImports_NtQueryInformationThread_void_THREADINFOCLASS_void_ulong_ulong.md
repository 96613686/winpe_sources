# MiniDumpOsImports::NtQueryInformationThread(void *,_THREADINFOCLASS,void *,ulong,ulong *)

- ea: `0x180026ef4`
- end: `0x180026f4f`
- name: `?NtQueryInformationThread@MiniDumpOsImports@@QEAAJPEAXW4_THREADINFOCLASS@@0KPEAK@Z`
- size: `91`
- prototype: `__int64 __fastcall(MiniDumpOsImports *__hidden this, void *, enum _THREADINFOCLASS, void *, unsigned int, unsigned int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180023920`
- `0x180024b90`
- `0x180024e20`
- `0x180024f60`

## callees

- `0x180026ef4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026f16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026f16`

## pseudocode

```c
__int64 __fastcall MiniDumpOsImports::NtQueryInformationThread(
        MiniDumpOsImports *this,
        void *a2,
        unsigned int a3,
        void *a4,
        unsigned int a5,
        unsigned int *a6)
{
  if ( g_NtDllCallsMdwd )
    return g_NtDllCallsMdwd(a2, a3, a4, a5, a6);
  SetLastError(0x32u);
  return 3221225659LL;
}

```

## disassembly

```asm
0x180026ef4  mov     [rsp+arg_0], rbx
0x180026ef9  push    rdi
0x180026efa  sub     rsp, 30h
0x180026efe  mov     rax, qword ptr cs:?g_NtDllCallsMdwd@@3UNTDLL_CALLS_MDWD@@C; NTDLL_CALLS_MDWD volatile g_NtDllCallsMdwd
0x180026f05  mov     r11, r9
0x180026f08  mov     ebx, r8d
0x180026f0b  mov     rdi, rdx
0x180026f0e  test    rax, rax
0x180026f11  jnz     short loc_180026F23
0x180026f13  lea     ecx, [rax+32h]; dwErrCode
0x180026f16  call    cs:__imp_SetLastError
0x180026f1c  mov     eax, 0C00000BBh
0x180026f21  jmp     short loc_180026F44
0x180026f23  mov     rax, [rsp+38h+arg_28]
0x180026f28  mov     r8, r11
0x180026f2b  mov     r10, qword ptr cs:?g_NtDllCallsMdwd@@3UNTDLL_CALLS_MDWD@@C; NTDLL_CALLS_MDWD volatile g_NtDllCallsMdwd
0x180026f32  mov     edx, ebx
0x180026f34  mov     r9d, [rsp+38h+arg_20]
0x180026f39  mov     rcx, rdi
0x180026f3c  mov     [rsp+38h+var_18], rax
0x180026f41  call    r10 ; NTDLL_CALLS_MDWD volatile g_NtDllCallsMdwd
0x180026f44  mov     rbx, [rsp+38h+arg_0]
0x180026f49  add     rsp, 30h
0x180026f4d  pop     rdi
0x180026f4e  retn
```
