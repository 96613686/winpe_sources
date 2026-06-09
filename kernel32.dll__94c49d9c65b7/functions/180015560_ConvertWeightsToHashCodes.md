# ConvertWeightsToHashCodes

- ea: `0x180015560`
- end: `0x1800156db`
- name: `ConvertWeightsToHashCodes`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180013960`

## callees

- `0x180015560`
- `0x1800156e4`

## import_xrefs

- `ntdll!memmove_s` at `0x180015611`
- `ntdll!memmove_s` at `0x180015639`
- `ntdll!memmove_s` at `0x180015665`
- `ntdll!memmove_s` at `0x180015691`
- `ntdll!memmove_s` at `0x1800156bd`
- `ntdll!memmove_s` at `0x180015611`
- `ntdll!memmove_s` at `0x180015639`
- `ntdll!memmove_s` at `0x180015665`
- `ntdll!memmove_s` at `0x180015691`
- `ntdll!memmove_s` at `0x1800156bd`

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
0x180015560  push    rbx
0x180015562  push    rbp
0x180015563  push    rsi
0x180015564  push    rdi
0x180015565  push    r14
0x180015567  push    r15
0x180015569  sub     rsp, 28h
0x18001556d  mov     r15, [rcx+38h]
0x180015571  mov     rsi, rdx
0x180015574  mov     rbp, rcx
0x180015577  mov     r9d, r8d
0x18001557a  mov     r8, [rdx+8]
0x18001557e  mov     rdx, r15
0x180015581  mov     ecx, [rsi+30h]
0x180015584  call    AddBytesToHash
0x180015589  mov     r10d, r9d
0x18001558c  mov     [rsi+30h], eax
0x18001558f  lea     r14, [rsi+10h]
0x180015593  and     r10d, 2
0x180015597  jnz     short loc_1800155AB
0x180015599  mov     r8, [r14]
0x18001559c  mov     rdx, [rbp+40h]
0x1800155a0  mov     ecx, [rsi+34h]
0x1800155a3  call    AddBytesToHash
0x1800155a8  mov     [rsi+34h], eax
0x1800155ab  mov     eax, 20001h
0x1800155b0  and     r9d, eax
0x1800155b3  cmp     r9d, eax
0x1800155b6  jz      short loc_1800155CB
0x1800155b8  mov     r8, [rsi+18h]
0x1800155bc  mov     rdx, [rbp+48h]
0x1800155c0  mov     ecx, [rsi+38h]
0x1800155c3  call    AddBytesToHash
0x1800155c8  mov     [rsi+38h], eax
0x1800155cb  cmp     dword ptr [rbp+20h], 0
0x1800155cf  jnz     short loc_1800155E4
0x1800155d1  mov     r8, [rsi+28h]
0x1800155d5  mov     rdx, [rbp+58h]
0x1800155d9  mov     ecx, [rsi+40h]
0x1800155dc  call    AddBytesToHash
0x1800155e1  mov     [rsi+40h], eax
0x1800155e4  test    r10d, r10d
0x1800155e7  jnz     short loc_1800155FC
0x1800155e9  mov     r8, [rsi+20h]
0x1800155ed  mov     rdx, [rbp+50h]
0x1800155f1  mov     ecx, [rsi+3Ch]
0x1800155f4  call    AddBytesToHash
0x1800155f9  mov     [rsi+3Ch], eax
0x1800155fc  mov     rbx, [rbp+78h]
0x180015600  mov     rcx, r15; Destination
0x180015603  sub     rbx, [rsi+8]
0x180015607  mov     r8, [rsi+8]; Source
0x18001560b  mov     r9, rbx; SourceSize
0x18001560e  mov     rdx, rbx; DestinationSize
0x180015611  call    cs:__imp_memmove_s
0x180015617  mov     r8, [r14]; Source
0x18001561a  lea     rax, [rbx+r15]
0x18001561e  mov     [rbp+78h], rax
0x180015622  mov     rbx, [rbp+80h]
0x180015629  sub     rbx, [r14]
0x18001562c  mov     rdi, [rbp+40h]
0x180015630  mov     r9, rbx; SourceSize
0x180015633  mov     rdx, rbx; DestinationSize
0x180015636  mov     rcx, rdi; Destination
0x180015639  call    cs:__imp_memmove_s
0x18001563f  mov     r8, [rsi+18h]; Source
0x180015643  lea     rax, [rbx+rdi]
0x180015647  mov     [rbp+80h], rax
0x18001564e  mov     rbx, [rbp+88h]
0x180015655  mov     rdi, [rbp+48h]
0x180015659  sub     rbx, r8
0x18001565c  mov     r9, rbx; SourceSize
0x18001565f  mov     rdx, rbx; DestinationSize
0x180015662  mov     rcx, rdi; Destination
0x180015665  call    cs:__imp_memmove_s
0x18001566b  mov     r8, [rsi+20h]; Source
0x18001566f  lea     rax, [rbx+rdi]
0x180015673  mov     [rbp+88h], rax
0x18001567a  mov     rbx, [rbp+90h]
0x180015681  mov     rdi, [rbp+50h]
0x180015685  sub     rbx, r8
0x180015688  mov     r9, rbx; SourceSize
0x18001568b  mov     rdx, rbx; DestinationSize
0x18001568e  mov     rcx, rdi; Destination
0x180015691  call    cs:__imp_memmove_s
0x180015697  mov     r8, [rsi+28h]; Source
0x18001569b  lea     rax, [rbx+rdi]
0x18001569f  mov     [rbp+90h], rax
0x1800156a6  mov     rbx, [rbp+98h]
0x1800156ad  mov     rdi, [rbp+58h]
0x1800156b1  sub     rbx, r8
0x1800156b4  mov     r9, rbx; SourceSize
0x1800156b7  mov     rdx, rbx; DestinationSize
0x1800156ba  mov     rcx, rdi; Destination
0x1800156bd  call    cs:__imp_memmove_s
0x1800156c3  lea     rax, [rbx+rdi]
0x1800156c7  mov     [rbp+98h], rax
0x1800156ce  add     rsp, 28h
0x1800156d2  pop     r15
0x1800156d4  pop     r14
0x1800156d6  pop     rdi
0x1800156d7  pop     rsi
0x1800156d8  pop     rbp
0x1800156d9  pop     rbx
0x1800156da  retn
```
