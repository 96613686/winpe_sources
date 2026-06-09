# BiGetFilePathFromEfiPath

- ea: `0x18003755c`
- end: `0x1800376b9`
- name: `BiGetFilePathFromEfiPath`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180036540`

## callees

- `0x180003bb5`
- `0x180034254`
- `0x18003755c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180037607`
- `ntdll!RtlAllocateHeap` at `0x180037607`

## string_xrefs

- `0x180037623`: `BiGetFilePathFromEfiPath failed %x`

## pseudocode

```c
__int64 __fastcall BiGetFilePathFromEfiPath(__int64 a1, _QWORD *a2, unsigned int *a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // r8d
  __int64 i; // rdx
  unsigned int v9; // ecx
  unsigned int v10; // r14d
  _WORD *Heap; // rax
  _WORD *v12; // rbp
  _WORD *v13; // rsi
  __int64 j; // rdi
  size_t v15; // rbx

  if ( (*(_BYTE *)a1 & 0x7F) == 0x7F )
  {
    v6 = -1073741766;
LABEL_15:
    BiLogMessage(4, L"BiGetFilePathFromEfiPath failed %x", v6);
    return v6;
  }
  v7 = 0;
  for ( i = a1 + *(unsigned __int16 *)(a1 + 2); (*(_BYTE *)i & 0x7F) != 0x7F; i += *(unsigned __int16 *)(i + 2) )
  {
    if ( *(_BYTE *)i == 4 && *(_BYTE *)(i + 1) == 4 )
    {
      v9 = *(unsigned __int16 *)(i + 2);
      if ( v9 < 4 )
      {
        v6 = -1073741675;
        goto LABEL_15;
      }
      v7 = v9 + v7 - 4;
    }
  }
  if ( v7 )
  {
    v10 = v7 + 2;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v7 + 2);
    v12 = Heap;
    if ( !Heap )
    {
      v6 = -1073741670;
      goto LABEL_15;
    }
    v13 = Heap;
    for ( j = a1 + *(unsigned __int16 *)(a1 + 2); (*(_BYTE *)j & 0x7F) != 0x7F; j += *(unsigned __int16 *)(j + 2) )
    {
      if ( *(_BYTE *)j == 4 && *(_BYTE *)(j + 1) == 4 )
      {
        v15 = (unsigned int)*(unsigned __int16 *)(j + 2) - 4;
        memcpy_0(v13, (const void *)(j + 4), v15);
        v13 = (_WORD *)((char *)v13 + v15);
      }
    }
    *a2 = v12;
    *v13 = 0;
    v6 = 0;
    *a3 = v10;
  }
  else
  {
    return (unsigned int)-1073741275;
  }
  return v6;
}

```

## disassembly

```asm
0x18003755c  push    rbx
0x18003755e  push    rbp
0x18003755f  push    rsi
0x180037560  push    rdi
0x180037561  push    r12
0x180037563  push    r14
0x180037565  push    r15
0x180037567  sub     rsp, 20h
0x18003756b  mov     al, [rcx]
0x18003756d  mov     r15, r8
0x180037570  and     al, 7Fh
0x180037572  mov     r12, rdx
0x180037575  mov     rbx, rcx
0x180037578  cmp     al, 7Fh
0x18003757a  jnz     short loc_180037586
0x18003757c  mov     ebx, 0C000003Ah
0x180037581  jmp     loc_180037620
0x180037586  movzx   edx, byte ptr [rcx+3]
0x18003758a  xor     r8d, r8d
0x18003758d  movzx   eax, byte ptr [rcx+2]
0x180037591  shl     rdx, 8
0x180037595  or      rdx, rax
0x180037598  add     rdx, rbx
0x18003759b  mov     al, [rdx]
0x18003759d  and     al, 7Fh
0x18003759f  cmp     al, 7Fh
0x1800375a1  jz      short loc_1800375E2
0x1800375a3  cmp     byte ptr [rdx], 4
0x1800375a6  jnz     short loc_1800375C7
0x1800375a8  cmp     byte ptr [rdx+1], 4
0x1800375ac  jnz     short loc_1800375C7
0x1800375ae  movzx   ecx, byte ptr [rdx+3]
0x1800375b2  movzx   eax, byte ptr [rdx+2]
0x1800375b6  shl     ecx, 8
0x1800375b9  or      ecx, eax
0x1800375bb  cmp     ecx, 4
0x1800375be  jb      short loc_1800375DB
0x1800375c0  add     r8d, 0FFFFFFFCh
0x1800375c4  add     r8d, ecx
0x1800375c7  movzx   ecx, byte ptr [rdx+3]
0x1800375cb  movzx   eax, byte ptr [rdx+2]
0x1800375cf  shl     rcx, 8
0x1800375d3  or      rcx, rax
0x1800375d6  add     rdx, rcx
0x1800375d9  jmp     short loc_18003759B
0x1800375db  mov     ebx, 0C0000095h
0x1800375e0  jmp     short loc_180037620
0x1800375e2  test    r8d, r8d
0x1800375e5  jnz     short loc_1800375F1
0x1800375e7  mov     ebx, 0C0000225h
0x1800375ec  jmp     loc_1800376A7
0x1800375f1  mov     rcx, gs:60h
0x1800375fa  lea     r14d, [r8+2]
0x1800375fe  mov     r8d, r14d; Size
0x180037601  xor     edx, edx; Flags
0x180037603  mov     rcx, [rcx+30h]; HeapHandle
0x180037607  call    cs:__imp_RtlAllocateHeap
0x18003760e  nop     dword ptr [rax+rax+00h]
0x180037613  mov     rbp, rax
0x180037616  test    rax, rax
0x180037619  jnz     short loc_180037636
0x18003761b  mov     ebx, 0C000009Ah
0x180037620  mov     r8d, ebx
0x180037623  lea     rdx, aBigetfilepathf; "BiGetFilePathFromEfiPath failed %x"
0x18003762a  mov     ecx, 4
0x18003762f  call    BiLogMessage
0x180037634  jmp     short loc_1800376A7
0x180037636  movzx   edi, byte ptr [rbx+3]
0x18003763a  mov     rsi, rbp
0x18003763d  movzx   eax, byte ptr [rbx+2]
0x180037641  shl     rdi, 8
0x180037645  or      rdi, rax
0x180037648  add     rdi, rbx
0x18003764b  mov     al, [rdi]
0x18003764d  and     al, 7Fh
0x18003764f  cmp     al, 7Fh
0x180037651  jz      short loc_180037699
0x180037653  cmp     byte ptr [rdi], 4
0x180037656  jnz     short loc_180037685
0x180037658  cmp     byte ptr [rdi+1], 4
0x18003765c  jnz     short loc_180037685
0x18003765e  movzx   ecx, byte ptr [rdi+3]
0x180037662  lea     rdx, [rdi+4]; Src
0x180037666  movzx   eax, byte ptr [rdi+2]
0x18003766a  shl     rcx, 8
0x18003766e  or      rcx, rax
0x180037671  sub     rcx, 4
0x180037675  mov     ebx, ecx
0x180037677  mov     r8d, ecx; Size
0x18003767a  mov     rcx, rsi; void *
0x18003767d  call    memcpy_0
0x180037682  add     rsi, rbx
0x180037685  movzx   ecx, byte ptr [rdi+3]
0x180037689  movzx   eax, byte ptr [rdi+2]
0x18003768d  shl     rcx, 8
0x180037691  or      rcx, rax
0x180037694  add     rdi, rcx
0x180037697  jmp     short loc_18003764B
0x180037699  xor     eax, eax
0x18003769b  mov     [r12], rbp
0x18003769f  mov     [rsi], ax
0x1800376a2  xor     ebx, ebx
0x1800376a4  mov     [r15], r14d
0x1800376a7  mov     eax, ebx
0x1800376a9  add     rsp, 20h
0x1800376ad  pop     r15
0x1800376af  pop     r14
0x1800376b1  pop     r12
0x1800376b3  pop     rdi
0x1800376b4  pop     rsi
0x1800376b5  pop     rbp
0x1800376b6  pop     rbx
0x1800376b7  retn
```
