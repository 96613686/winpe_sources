# CILogRead::GetCurrentLogRecord(char *,ulong)

- ea: `0x180002b20`
- end: `0x180002bc3`
- name: `?GetCurrentLogRecord@CILogRead@@UEAAJPEADK@Z`
- size: `163`
- prototype: `__int64 __fastcall(CILogRead *this, char *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002b20`
- `0x1800127f2`

## pseudocode

```c
__int64 __fastcall CILogRead::GetCurrentLogRecord(CILogRead *this, char *a2, unsigned int a3)
{
  char *v4; // rsi
  __int64 v7; // rbx
  unsigned int v8; // edx
  unsigned int i; // r15d
  unsigned int v10; // edi

  v4 = a2;
  if ( !a2 )
    return 2147942487LL;
  v7 = *(_QWORD *)(*((_QWORD *)this + 1) + 584LL);
  if ( !v7 )
    return 2147549183LL;
  v8 = 0;
  for ( i = 0; i < *(_DWORD *)(*((_QWORD *)this + 1) + 576LL); ++i )
  {
    v10 = *(_DWORD *)(v7 + 8) + v8;
    if ( v10 < v8 )
      return 2147942934LL;
    if ( a3 < v10 )
      return 2147942487LL;
    memcpy_0(v4, *(const void **)v7, *(unsigned int *)(v7 + 8));
    v4 += *(unsigned int *)(v7 + 8);
    v7 += 16;
    v8 = v10;
  }
  return 0;
}

```

## disassembly

```asm
0x180002b20  push    rbx
0x180002b22  push    rsi
0x180002b23  push    rdi
0x180002b24  push    r12
0x180002b26  push    r14
0x180002b28  push    r15
0x180002b2a  sub     rsp, 38h
0x180002b2e  mov     r12d, r8d
0x180002b31  mov     rsi, rdx
0x180002b34  mov     r14, rcx
0x180002b37  test    rdx, rdx
0x180002b3a  jnz     short loc_180002B43
0x180002b3c  mov     eax, 80070057h
0x180002b41  jmp     short loc_180002BB4
0x180002b43  mov     rax, [rcx+8]
0x180002b47  mov     rbx, [rax+248h]
0x180002b4e  test    rbx, rbx
0x180002b51  jnz     short loc_180002B5A
0x180002b53  mov     eax, 8000FFFFh
0x180002b58  jmp     short loc_180002BB4
0x180002b5a  xor     ecx, ecx
0x180002b5c  xor     edx, edx
0x180002b5e  xor     r15d, r15d
0x180002b61  mov     rax, [r14+8]
0x180002b65  cmp     r15d, [rax+240h]
0x180002b6c  jnb     short loc_180002BAC
0x180002b6e  mov     eax, [rbx+8]
0x180002b71  lea     edi, [rax+rdx]
0x180002b74  cmp     edi, edx
0x180002b76  jb      short loc_180002BA5
0x180002b78  cmp     r12d, edi
0x180002b7b  jnb     short loc_180002B84
0x180002b7d  mov     eax, 80070057h
0x180002b82  jmp     short loc_180002BB4
0x180002b84  mov     r8, rax; Size
0x180002b87  mov     rdx, [rbx]; Src
0x180002b8a  mov     rcx, rsi; void *
0x180002b8d  call    memcpy_0
0x180002b92  mov     eax, [rbx+8]
0x180002b95  add     rsi, rax
0x180002b98  add     rbx, 10h
0x180002b9c  inc     r15d
0x180002b9f  mov     edx, edi
0x180002ba1  xor     ecx, ecx
0x180002ba3  jmp     short loc_180002B61
0x180002ba5  mov     eax, 80070216h
0x180002baa  jmp     short loc_180002BB4
0x180002bac  jmp     short loc_180002BB2
0x180002bae  mov     ecx, [rsp+68h+arg_8]
0x180002bb2  mov     eax, ecx
0x180002bb4  add     rsp, 38h
0x180002bb8  pop     r15
0x180002bba  pop     r14
0x180002bbc  pop     r12
0x180002bbe  pop     rdi
0x180002bbf  pop     rsi
0x180002bc0  pop     rbx
0x180002bc1  retn
```
