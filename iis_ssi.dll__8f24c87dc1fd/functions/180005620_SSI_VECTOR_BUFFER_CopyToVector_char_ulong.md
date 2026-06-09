# SSI_VECTOR_BUFFER::CopyToVector(char *,ulong)

- ea: `0x180005620`
- end: `0x18000568b`
- name: `?CopyToVector@SSI_VECTOR_BUFFER@@QEAAJPEADK@Z`
- size: `107`
- prototype: `int __fastcall(SSI_VECTOR_BUFFER *this, char *Src, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000395c`
- `0x180003e9c`
- `0x18000559c`

## callees

- `0x180005548`
- `0x180005620`
- `0x18000573e`

## import_xrefs

- `iisutil!?AllocateSpace@CHUNK_BUFFER@@QEAAJKPEAPEAD@Z` at `0x180005651`
- `iisutil!?AllocateSpace@CHUNK_BUFFER@@QEAAJKPEAPEAD@Z` at `0x180005651`

## pseudocode

```c
int __fastcall SSI_VECTOR_BUFFER::CopyToVector(SSI_VECTOR_BUFFER *this, char *Src, unsigned int a3)
{
  size_t v3; // rbx
  int result; // eax
  char *v7; // [rsp+48h] [rbp+20h] BYREF

  v3 = a3;
  v7 = 0;
  if ( !a3 )
    return 0;
  result = CHUNK_BUFFER::AllocateSpace(this, a3, &v7);
  if ( result >= 0 )
  {
    memcpy_0(v7, Src, v3);
    return SSI_VECTOR_BUFFER::AddToVector(this, v7, v3);
  }
  return result;
}

```

## disassembly

```asm
0x180005620  mov     [rsp+arg_0], rbx
0x180005625  mov     [rsp+arg_8], rsi
0x18000562a  push    rdi
0x18000562b  sub     rsp, 20h
0x18000562f  mov     ebx, r8d
0x180005632  mov     rsi, rdx
0x180005635  mov     [rsp+28h+arg_18], 0
0x18000563e  mov     rdi, rcx
0x180005641  test    r8d, r8d
0x180005644  jnz     short loc_18000564A
0x180005646  xor     eax, eax
0x180005648  jmp     short loc_18000567B
0x18000564a  lea     r8, [rsp+28h+arg_18]
0x18000564f  mov     edx, ebx
0x180005651  call    cs:__imp_?AllocateSpace@CHUNK_BUFFER@@QEAAJKPEAPEAD@Z; CHUNK_BUFFER::AllocateSpace(ulong,char * *)
0x180005657  test    eax, eax
0x180005659  js      short loc_18000567B
0x18000565b  mov     rcx, [rsp+28h+arg_18]; void *
0x180005660  mov     r8, rbx; Size
0x180005663  mov     rdx, rsi; Src
0x180005666  call    memcpy_0
0x18000566b  mov     rdx, [rsp+28h+arg_18]; char *
0x180005670  mov     r8d, ebx; unsigned int
0x180005673  mov     rcx, rdi; this
0x180005676  call    ?AddToVector@SSI_VECTOR_BUFFER@@QEAAJPEADK@Z; SSI_VECTOR_BUFFER::AddToVector(char *,ulong)
0x18000567b  mov     rbx, [rsp+28h+arg_0]
0x180005680  mov     rsi, [rsp+28h+arg_8]
0x180005685  add     rsp, 20h
0x180005689  pop     rdi
0x18000568a  retn
```
