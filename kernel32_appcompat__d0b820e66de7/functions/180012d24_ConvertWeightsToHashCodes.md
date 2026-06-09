# ConvertWeightsToHashCodes

- ea: `0x180012d24`
- end: `0x180012ebe`
- name: `ConvertWeightsToHashCodes`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180011110`

## callees

- `0x180012d24`
- `0x180012ec4`

## import_xrefs

- `ntdll!memmove_s` at `0x180012dd5`
- `ntdll!memmove_s` at `0x180012e03`
- `ntdll!memmove_s` at `0x180012e35`
- `ntdll!memmove_s` at `0x180012e67`
- `ntdll!memmove_s` at `0x180012e99`
- `ntdll!memmove_s` at `0x180012dd5`
- `ntdll!memmove_s` at `0x180012e03`
- `ntdll!memmove_s` at `0x180012e35`
- `ntdll!memmove_s` at `0x180012e67`
- `ntdll!memmove_s` at `0x180012e99`

## pseudocode

```c
char *__fastcall ConvertWeightsToHashCodes(__int64 a1, __int64 a2, unsigned int a3)
{
  char *v3; // r15
  __int64 v6; // r9
  _QWORD *v7; // r14
  int v8; // r10d
  __int64 v9; // r9
  rsize_t v10; // rbx
  const void *v11; // r8
  rsize_t v12; // rbx
  char *v13; // rdi
  const void *v14; // r8
  char *v15; // rdi
  rsize_t v16; // rbx
  const void *v17; // r8
  char *v18; // rdi
  rsize_t v19; // rbx
  const void *v20; // r8
  char *v21; // rdi
  rsize_t v22; // rbx
  char *result; // rax

  v3 = *(char **)(a1 + 56);
  *(_DWORD *)(a2 + 48) = AddBytesToHash(*(unsigned int *)(a2 + 48), v3, *(_QWORD *)(a2 + 8), a3);
  v7 = (_QWORD *)(a2 + 16);
  v8 = v6 & 2;
  if ( (v6 & 2) == 0 )
    *(_DWORD *)(a2 + 52) = AddBytesToHash(*(unsigned int *)(a2 + 52), *(_QWORD *)(a1 + 64), *v7, v6);
  v9 = v6 & 0x20001;
  if ( (_DWORD)v9 != 131073 )
    *(_DWORD *)(a2 + 56) = AddBytesToHash(*(unsigned int *)(a2 + 56), *(_QWORD *)(a1 + 72), *(_QWORD *)(a2 + 24), v9);
  if ( !*(_DWORD *)(a1 + 32) )
    *(_DWORD *)(a2 + 64) = AddBytesToHash(*(unsigned int *)(a2 + 64), *(_QWORD *)(a1 + 88), *(_QWORD *)(a2 + 40), v9);
  if ( !v8 )
    *(_DWORD *)(a2 + 60) = AddBytesToHash(*(unsigned int *)(a2 + 60), *(_QWORD *)(a1 + 80), *(_QWORD *)(a2 + 32), v9);
  v10 = *(_QWORD *)(a1 + 120) - *(_QWORD *)(a2 + 8);
  memmove_s(v3, v10, *(const void *const *)(a2 + 8), v10);
  v11 = (const void *)*v7;
  *(_QWORD *)(a1 + 120) = &v3[v10];
  v12 = *(_QWORD *)(a1 + 128) - *v7;
  v13 = *(char **)(a1 + 64);
  memmove_s(v13, v12, v11, v12);
  v14 = *(const void **)(a2 + 24);
  *(_QWORD *)(a1 + 128) = &v13[v12];
  v15 = *(char **)(a1 + 72);
  v16 = *(_QWORD *)(a1 + 136) - (_QWORD)v14;
  memmove_s(v15, v16, v14, v16);
  v17 = *(const void **)(a2 + 32);
  *(_QWORD *)(a1 + 136) = &v15[v16];
  v18 = *(char **)(a1 + 80);
  v19 = *(_QWORD *)(a1 + 144) - (_QWORD)v17;
  memmove_s(v18, v19, v17, v19);
  v20 = *(const void **)(a2 + 40);
  *(_QWORD *)(a1 + 144) = &v18[v19];
  v21 = *(char **)(a1 + 88);
  v22 = *(_QWORD *)(a1 + 152) - (_QWORD)v20;
  memmove_s(v21, v22, v20, v22);
  result = &v21[v22];
  *(_QWORD *)(a1 + 152) = &v21[v22];
  return result;
}

```

## disassembly

```asm
0x180012d24  push    rbx
0x180012d26  push    rbp
0x180012d27  push    rsi
0x180012d28  push    rdi
0x180012d29  push    r14
0x180012d2b  push    r15
0x180012d2d  sub     rsp, 28h
0x180012d31  mov     r15, [rcx+38h]
0x180012d35  mov     rsi, rdx
0x180012d38  mov     rbp, rcx
0x180012d3b  mov     r9d, r8d
0x180012d3e  mov     r8, [rdx+8]
0x180012d42  mov     rdx, r15
0x180012d45  mov     ecx, [rsi+30h]
0x180012d48  call    AddBytesToHash
0x180012d4d  mov     r10d, r9d
0x180012d50  mov     [rsi+30h], eax
0x180012d53  lea     r14, [rsi+10h]
0x180012d57  and     r10d, 2
0x180012d5b  jnz     short loc_180012D6F
0x180012d5d  mov     r8, [r14]
0x180012d60  mov     rdx, [rbp+40h]
0x180012d64  mov     ecx, [rsi+34h]
0x180012d67  call    AddBytesToHash
0x180012d6c  mov     [rsi+34h], eax
0x180012d6f  mov     eax, 20001h
0x180012d74  and     r9d, eax
0x180012d77  cmp     r9d, eax
0x180012d7a  jz      short loc_180012D8F
0x180012d7c  mov     r8, [rsi+18h]
0x180012d80  mov     rdx, [rbp+48h]
0x180012d84  mov     ecx, [rsi+38h]
0x180012d87  call    AddBytesToHash
0x180012d8c  mov     [rsi+38h], eax
0x180012d8f  cmp     dword ptr [rbp+20h], 0
0x180012d93  jnz     short loc_180012DA8
0x180012d95  mov     r8, [rsi+28h]
0x180012d99  mov     rdx, [rbp+58h]
0x180012d9d  mov     ecx, [rsi+40h]
0x180012da0  call    AddBytesToHash
0x180012da5  mov     [rsi+40h], eax
0x180012da8  test    r10d, r10d
0x180012dab  jnz     short loc_180012DC0
0x180012dad  mov     r8, [rsi+20h]
0x180012db1  mov     rdx, [rbp+50h]
0x180012db5  mov     ecx, [rsi+3Ch]
0x180012db8  call    AddBytesToHash
0x180012dbd  mov     [rsi+3Ch], eax
0x180012dc0  mov     rbx, [rbp+78h]
0x180012dc4  mov     rcx, r15; Destination
0x180012dc7  sub     rbx, [rsi+8]
0x180012dcb  mov     r8, [rsi+8]; Source
0x180012dcf  mov     r9, rbx; SourceSize
0x180012dd2  mov     rdx, rbx; DestinationSize
0x180012dd5  call    cs:__imp_memmove_s
0x180012ddc  nop     dword ptr [rax+rax+00h]
0x180012de1  mov     r8, [r14]; Source
0x180012de4  lea     rax, [rbx+r15]
0x180012de8  mov     [rbp+78h], rax
0x180012dec  mov     rbx, [rbp+80h]
0x180012df3  sub     rbx, [r14]
0x180012df6  mov     rdi, [rbp+40h]
0x180012dfa  mov     r9, rbx; SourceSize
0x180012dfd  mov     rdx, rbx; DestinationSize
0x180012e00  mov     rcx, rdi; Destination
0x180012e03  call    cs:__imp_memmove_s
0x180012e0a  nop     dword ptr [rax+rax+00h]
0x180012e0f  mov     r8, [rsi+18h]; Source
0x180012e13  lea     rax, [rbx+rdi]
0x180012e17  mov     [rbp+80h], rax
0x180012e1e  mov     rbx, [rbp+88h]
0x180012e25  mov     rdi, [rbp+48h]
0x180012e29  sub     rbx, r8
0x180012e2c  mov     r9, rbx; SourceSize
0x180012e2f  mov     rdx, rbx; DestinationSize
0x180012e32  mov     rcx, rdi; Destination
0x180012e35  call    cs:__imp_memmove_s
0x180012e3c  nop     dword ptr [rax+rax+00h]
0x180012e41  mov     r8, [rsi+20h]; Source
0x180012e45  lea     rax, [rbx+rdi]
0x180012e49  mov     [rbp+88h], rax
0x180012e50  mov     rbx, [rbp+90h]
0x180012e57  mov     rdi, [rbp+50h]
0x180012e5b  sub     rbx, r8
0x180012e5e  mov     r9, rbx; SourceSize
0x180012e61  mov     rdx, rbx; DestinationSize
0x180012e64  mov     rcx, rdi; Destination
0x180012e67  call    cs:__imp_memmove_s
0x180012e6e  nop     dword ptr [rax+rax+00h]
0x180012e73  mov     r8, [rsi+28h]; Source
0x180012e77  lea     rax, [rbx+rdi]
0x180012e7b  mov     [rbp+90h], rax
0x180012e82  mov     rbx, [rbp+98h]
0x180012e89  mov     rdi, [rbp+58h]
0x180012e8d  sub     rbx, r8
0x180012e90  mov     r9, rbx; SourceSize
0x180012e93  mov     rdx, rbx; DestinationSize
0x180012e96  mov     rcx, rdi; Destination
0x180012e99  call    cs:__imp_memmove_s
0x180012ea0  nop     dword ptr [rax+rax+00h]
0x180012ea5  lea     rax, [rbx+rdi]
0x180012ea9  mov     [rbp+98h], rax
0x180012eb0  add     rsp, 28h
0x180012eb4  pop     r15
0x180012eb6  pop     r14
0x180012eb8  pop     rdi
0x180012eb9  pop     rsi
0x180012eba  pop     rbp
0x180012ebb  pop     rbx
0x180012ebc  retn
```
