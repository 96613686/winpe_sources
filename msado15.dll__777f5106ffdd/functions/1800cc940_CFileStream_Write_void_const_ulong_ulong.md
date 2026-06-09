# CFileStream::Write(void const *,ulong,ulong *)

- ea: `0x1800cc940`
- end: `0x1800cc9a1`
- name: `?Write@CFileStream@@UEAAJPEBXKPEAK@Z`
- size: `97`
- prototype: `int(CFileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800cc940`

## import_xrefs

- `msvcrt!fwrite` at `0x1800cc962`
- `msvcrt!fwrite` at `0x1800cc962`
- `KERNEL32!GetLastError` at `0x1800cc97d`
- `KERNEL32!GetLastError` at `0x1800cc97d`

## pseudocode

```c
int __fastcall CFileStream::Write(FILE **this, const void *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v6; // eax
  int result; // eax

  v6 = fwrite(a2, 1u, a3, this[5]);
  if ( a4 )
    *a4 = v6;
  if ( v6 == a3 )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800cc940  mov     [rsp+arg_0], rbx
0x1800cc945  push    rdi
0x1800cc946  sub     rsp, 20h
0x1800cc94a  mov     rax, rdx
0x1800cc94d  mov     ebx, r8d
0x1800cc950  mov     rdi, r9
0x1800cc953  mov     r8d, r8d; ElementCount
0x1800cc956  mov     r9, [rcx+28h]; Stream
0x1800cc95a  mov     edx, 1; ElementSize
0x1800cc95f  mov     rcx, rax; Buffer
0x1800cc962  call    cs:__imp_fwrite
0x1800cc969  nop     dword ptr [rax+rax+00h]
0x1800cc96e  test    rdi, rdi
0x1800cc971  jz      short loc_1800CC975
0x1800cc973  mov     [rdi], eax
0x1800cc975  cmp     eax, ebx
0x1800cc977  jnz     short loc_1800CC97D
0x1800cc979  xor     eax, eax
0x1800cc97b  jmp     short loc_1800CC995
0x1800cc97d  call    cs:__imp_GetLastError
0x1800cc984  nop     dword ptr [rax+rax+00h]
0x1800cc989  test    eax, eax
0x1800cc98b  jle     short loc_1800CC995
0x1800cc98d  movzx   eax, ax
0x1800cc990  or      eax, 80070000h
0x1800cc995  mov     rbx, [rsp+28h+arg_0]
0x1800cc99a  add     rsp, 20h
0x1800cc99e  pop     rdi
0x1800cc99f  retn
```
