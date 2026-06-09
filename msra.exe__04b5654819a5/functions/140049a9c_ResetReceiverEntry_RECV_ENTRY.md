# ResetReceiverEntry(RECV_ENTRY *)

- ea: `0x140049a9c`
- end: `0x140049b2e`
- name: `?ResetReceiverEntry@@YAJPEAURECV_ENTRY@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(struct RECV_ENTRY *)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140048730`
- `0x140048d20`
- `0x1400492ec`

## callees

- `0x140049a9c`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x140049ad9`
- `KERNEL32!DeleteFileW` at `0x140049ad9`
- `KERNEL32!CloseHandle` at `0x140049ac0`
- `KERNEL32!CloseHandle` at `0x140049ac0`
- `msvcrt!free` at `0x140049ae9`
- `msvcrt!free` at `0x140049b02`
- `msvcrt!free` at `0x140049ae9`
- `msvcrt!free` at `0x140049b02`

## pseudocode

```c
__int64 __fastcall ResetReceiverEntry(struct RECV_ENTRY *a1)
{
  unsigned int v2; // edi
  void *v3; // rcx
  const WCHAR *v4; // rcx
  void *v5; // rcx

  if ( a1 )
  {
    v3 = (void *)*((_QWORD *)a1 + 3);
    v2 = 0;
    if ( v3 )
    {
      CloseHandle(v3);
      *((_QWORD *)a1 + 3) = 0;
    }
    v4 = (const WCHAR *)*((_QWORD *)a1 + 2);
    if ( v4 )
    {
      DeleteFileW(v4);
      free(*((void **)a1 + 2));
      *((_QWORD *)a1 + 2) = 0;
    }
    v5 = (void *)*((_QWORD *)a1 + 5);
    if ( v5 )
    {
      free(v5);
      *((_QWORD *)a1 + 5) = 0;
    }
    *((_QWORD *)a1 + 4) = 0;
    *((_QWORD *)a1 + 1) = 0;
    *(_DWORD *)a1 = -1000;
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v2;
}

```

## disassembly

```asm
0x140049a9c  mov     [rsp+arg_0], rbx
0x140049aa1  push    rdi
0x140049aa2  sub     rsp, 20h
0x140049aa6  mov     rbx, rcx
0x140049aa9  test    rcx, rcx
0x140049aac  jnz     short loc_140049AB5
0x140049aae  mov     edi, 80004003h
0x140049ab3  jmp     short loc_140049B20
0x140049ab5  mov     rcx, [rcx+18h]; hObject
0x140049ab9  xor     edi, edi
0x140049abb  test    rcx, rcx
0x140049abe  jz      short loc_140049AD0
0x140049ac0  call    cs:__imp_CloseHandle
0x140049ac7  nop     dword ptr [rax+rax+00h]
0x140049acc  mov     [rbx+18h], rdi
0x140049ad0  mov     rcx, [rbx+10h]; lpFileName
0x140049ad4  test    rcx, rcx
0x140049ad7  jz      short loc_140049AF9
0x140049ad9  call    cs:__imp_DeleteFileW
0x140049ae0  nop     dword ptr [rax+rax+00h]
0x140049ae5  mov     rcx, [rbx+10h]; Block
0x140049ae9  call    cs:__imp_free
0x140049af0  nop     dword ptr [rax+rax+00h]
0x140049af5  mov     [rbx+10h], rdi
0x140049af9  mov     rcx, [rbx+28h]; Block
0x140049afd  test    rcx, rcx
0x140049b00  jz      short loc_140049B12
0x140049b02  call    cs:__imp_free
0x140049b09  nop     dword ptr [rax+rax+00h]
0x140049b0e  mov     [rbx+28h], rdi
0x140049b12  mov     [rbx+20h], rdi
0x140049b16  mov     [rbx+8], rdi
0x140049b1a  mov     dword ptr [rbx], 0FFFFFC18h
0x140049b20  mov     rbx, [rsp+28h+arg_0]
0x140049b25  mov     eax, edi
0x140049b27  add     rsp, 20h
0x140049b2b  pop     rdi
0x140049b2c  retn
```
