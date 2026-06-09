# Win32LiveSystemProvider::ReadAllVirtual(void *,unsigned __int64,void *,ulong)

- ea: `0x1800156a0`
- end: `0x180015768`
- name: `?ReadAllVirtual@Win32LiveSystemProvider@@UEAAJPEAX_K0K@Z`
- size: `200`
- prototype: `int(Win32LiveSystemProvider *__hidden this, void *, unsigned __int64, void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800156a0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015702`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800156ee`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800156ee`

## pseudocode

```c
int __fastcall Win32LiveSystemProvider::ReadAllVirtual(
        Win32LiveSystemProvider *this,
        void *a2,
        const void *a3,
        void *a4,
        unsigned int nSize)
{
  bool v5; // zf
  unsigned int v6; // ebx
  int result; // eax
  int v8; // eax
  SIZE_T lpNumberOfBytesRead[3]; // [rsp+40h] [rbp-18h] BYREF

  v5 = *((_QWORD *)this + 3) == 0;
  lpNumberOfBytesRead[0] = 0;
  if ( !v5 || *((_QWORD *)this + 4) )
  {
    v6 = nSize;
    result = (*(__int64 (__fastcall **)(Win32LiveSystemProvider *, void *))(*(_QWORD *)this + 232LL))(this, a2);
    if ( result )
      return result;
    v8 = 0;
    return v8 != v6 ? 0x8007001E : 0;
  }
  v6 = nSize;
  if ( ReadProcessMemory(a2, a3, a4, nSize, lpNumberOfBytesRead) )
  {
    v8 = lpNumberOfBytesRead[0];
    return v8 != v6 ? 0x8007001E : 0;
  }
  if ( !GetLastError() )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800156a0  mov     rax, rsp
0x1800156a3  mov     [rax+10h], rbx
0x1800156a7  push    rdi
0x1800156a8  sub     rsp, 50h
0x1800156ac  cmp     qword ptr [rcx+18h], 0
0x1800156b1  mov     r10, r9
0x1800156b4  mov     r11, r8
0x1800156b7  mov     dword ptr [rax+8], 0
0x1800156be  mov     rdi, rdx
0x1800156c1  mov     qword ptr [rax-18h], 0
0x1800156c9  jnz     short loc_180015723
0x1800156cb  cmp     qword ptr [rcx+20h], 0
0x1800156d0  jnz     short loc_180015723
0x1800156d2  mov     ebx, dword ptr [rsp+58h+nSize]
0x1800156d9  lea     rax, [rax-18h]
0x1800156dd  mov     r9d, ebx; nSize
0x1800156e0  mov     [rsp+58h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x1800156e5  mov     r8, r10; lpBuffer
0x1800156e8  mov     rdx, r11; lpBaseAddress
0x1800156eb  mov     rcx, rdi; hProcess
0x1800156ee  call    cs:__imp_ReadProcessMemory
0x1800156f4  test    eax, eax
0x1800156f6  jnz     short loc_18001571D
0x1800156f8  call    cs:__imp_GetLastError
0x1800156fe  test    eax, eax
0x180015700  jz      short loc_180015716
0x180015702  call    cs:__imp_GetLastError
0x180015708  test    eax, eax
0x18001570a  jle     short loc_18001575D
0x18001570c  movzx   eax, ax
0x18001570f  or      eax, 80070000h
0x180015714  jmp     short loc_18001575D
0x180015716  mov     eax, 80004005h
0x18001571b  jmp     short loc_18001575D
0x18001571d  mov     eax, dword ptr [rsp+58h+var_18]
0x180015721  jmp     short loc_180015752
0x180015723  mov     rax, [rcx]
0x180015726  lea     rdx, [rsp+58h+arg_0]
0x18001572b  mov     ebx, dword ptr [rsp+58h+nSize]
0x180015732  mov     [rsp+58h+var_30], rdx
0x180015737  mov     rdx, rdi
0x18001573a  mov     dword ptr [rsp+58h+lpNumberOfBytesRead], ebx
0x18001573e  mov     rax, [rax+0E8h]
0x180015745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001574a  test    eax, eax
0x18001574c  jnz     short loc_18001575D
0x18001574e  mov     eax, [rsp+58h+arg_0]
0x180015752  sub     ebx, eax
0x180015754  neg     ebx
0x180015756  sbb     eax, eax
0x180015758  and     eax, 8007001Eh
0x18001575d  mov     rbx, [rsp+58h+arg_8]
0x180015762  add     rsp, 50h
0x180015766  pop     rdi
0x180015767  retn
```
