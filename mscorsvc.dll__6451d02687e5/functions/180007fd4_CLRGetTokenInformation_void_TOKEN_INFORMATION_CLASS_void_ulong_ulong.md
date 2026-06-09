# CLRGetTokenInformation(void *,_TOKEN_INFORMATION_CLASS,void *,ulong,ulong *)

- ea: `0x180007fd4`
- end: `0x18000807c`
- name: `?CLRGetTokenInformation@@YAHPEAXW4_TOKEN_INFORMATION_CLASS@@0KPEAK@Z`
- size: `168`
- prototype: `__int64 __fastcall(void *, enum _TOKEN_INFORMATION_CLASS, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800280bc`

## callees

- `0x180007fd4`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000800d`
- `KERNEL32!LoadLibraryExW` at `0x18000800d`
- `KERNEL32!GetProcAddress` at `0x180008022`
- `KERNEL32!GetProcAddress` at `0x180008022`

## string_xrefs

- `0x180008004`: `advapi32.dll`
- `0x180008018`: `GetTokenInformation`

## pseudocode

```c
__int64 __fastcall CLRGetTokenInformation(
        void *a1,
        enum _TOKEN_INFORMATION_CLASS a2,
        void *a3,
        unsigned int a4,
        unsigned int *a5)
{
  FARPROC ProcAddress; // r10
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18006FF98;
  if ( qword_18006FF98 )
    return ((__int64 (__fastcall *)(void *, __int64, void *, _QWORD, unsigned int *))ProcAddress)(a1, 3, a3, a4, a5);
  if ( !bGetTokenInformationProbed
    && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
      ? (ProcAddress = (FARPROC)qword_18006FF98)
      : (FARPROC)(ProcAddress = GetProcAddress(Library, "GetTokenInformation"), qword_18006FF98 = (__int64)ProcAddress),
        bGetTokenInformationProbed = 1,
        ProcAddress) )
  {
    return ((__int64 (__fastcall *)(void *, __int64, void *, _QWORD, unsigned int *))ProcAddress)(a1, 3, a3, a4, a5);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180007fd4  mov     [rsp+arg_0], rbx
0x180007fd9  mov     [rsp+arg_8], rsi
0x180007fde  push    rdi
0x180007fdf  sub     rsp, 30h
0x180007fe3  mov     r10, cs:qword_18006FF98
0x180007fea  mov     ebx, r9d
0x180007fed  mov     rdi, r8
0x180007ff0  mov     rsi, rcx
0x180007ff3  test    r10, r10
0x180007ff6  jnz     short loc_18000804B
0x180007ff8  cmp     cs:?bGetTokenInformationProbed@@3_NA, r10b; bool bGetTokenInformationProbed
0x180007fff  jnz     short loc_180008047
0x180008001  xor     r8d, r8d; dwFlags
0x180008004  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x18000800b  xor     edx, edx; hFile
0x18000800d  call    cs:__imp_LoadLibraryExW
0x180008013  test    rax, rax
0x180008016  jz      short loc_180008034
0x180008018  lea     rdx, aGettokeninform; "GetTokenInformation"
0x18000801f  mov     rcx, rax; hModule
0x180008022  call    cs:__imp_GetProcAddress
0x180008028  mov     r10, rax
0x18000802b  mov     cs:qword_18006FF98, rax
0x180008032  jmp     short loc_18000803B
0x180008034  mov     r10, cs:qword_18006FF98
0x18000803b  mov     cs:?bGetTokenInformationProbed@@3_NA, 1; bool bGetTokenInformationProbed
0x180008042  test    r10, r10
0x180008045  jnz     short loc_18000804B
0x180008047  xor     eax, eax
0x180008049  jmp     short loc_18000806C
0x18000804b  mov     rax, [rsp+38h+arg_20]
0x180008050  mov     r9d, ebx
0x180008053  mov     [rsp+38h+var_18], rax
0x180008058  mov     r8, rdi
0x18000805b  mov     rax, r10
0x18000805e  mov     edx, 3
0x180008063  mov     rcx, rsi
0x180008066  call    cs:__guard_dispatch_icall_fptr
0x18000806c  mov     rbx, [rsp+38h+arg_0]
0x180008071  mov     rsi, [rsp+38h+arg_8]
0x180008076  add     rsp, 30h
0x18000807a  pop     rdi
0x18000807b  retn
```
