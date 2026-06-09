# FveConfigSubscriberBaseInit

- ea: `0x140082700`
- end: `0x1400827db`
- name: `FveConfigSubscriberBaseInit`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140021d00`
- `0x140082700`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400827b0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400827b0`
- `ntoskrnl!ObfReferenceObject` at `0x140082740`
- `ntoskrnl!ObfReferenceObject` at `0x140082740`
- `ntoskrnl!ExInitializeResourceLite` at `0x14008277c`
- `ntoskrnl!ExInitializeResourceLite` at `0x14008277c`
- `ntoskrnl!ExDeleteResourceLite` at `0x14008279c`
- `ntoskrnl!ExDeleteResourceLite` at `0x14008279c`

## pseudocode

```c
__int64 __fastcall FveConfigSubscriberBaseInit(__int64 a1, int a2, __int64 a3, void *a4, __int64 a5, _QWORD *a6)
{
  __int64 v8; // rbp
  NTSTATUS v9; // esi

  v8 = a1 + 8 + 264LL * a2;
  memset(a6, 0, *(unsigned int *)(v8 + 132));
  if ( a4 )
    ObfReferenceObject(a4);
  *((_DWORD *)a6 + 10) = *(_DWORD *)(v8 + 132);
  a6[4] = a5;
  *((_DWORD *)a6 + 11) = 1;
  a6[2] = v8;
  a6[7] = a3;
  a6[3] = a4;
  a6[1] = a6;
  *a6 = a6;
  v9 = ExInitializeResourceLite((PERESOURCE)(a6 + 8));
  if ( v9 < 0 )
  {
    if ( a4 )
      ObfDereferenceObject(a4);
    memset(a6, 0, *(unsigned int *)(v8 + 132));
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140082700  push    rbx
0x140082702  push    rbp
0x140082703  push    rsi
0x140082704  push    rdi
0x140082705  push    r14
0x140082707  sub     rsp, 20h
0x14008270b  mov     rbx, [rsp+48h+arg_28]
0x140082710  add     rcx, 8
0x140082714  movsxd  rax, edx
0x140082717  mov     rsi, r8
0x14008271a  imul    rbp, rax, 108h
0x140082721  xor     edx, edx; Val
0x140082723  mov     rdi, r9
0x140082726  add     rbp, rcx
0x140082729  mov     rcx, rbx; void *
0x14008272c  mov     r8d, [rbp+84h]; Size
0x140082733  call    memset
0x140082738  test    rdi, rdi
0x14008273b  jz      short loc_14008274C
0x14008273d  mov     rcx, rdi; Object
0x140082740  call    cs:__imp_ObfReferenceObject
0x140082747  nop     dword ptr [rax+rax+00h]
0x14008274c  mov     eax, [rbp+84h]
0x140082752  lea     rcx, [rbx+40h]; Resource
0x140082756  mov     [rbx+28h], eax
0x140082759  mov     rax, [rsp+48h+arg_20]
0x14008275e  mov     [rbx+20h], rax
0x140082762  mov     dword ptr [rbx+2Ch], 1
0x140082769  mov     [rbx+10h], rbp
0x14008276d  mov     [rbx+38h], rsi
0x140082771  mov     [rbx+18h], rdi
0x140082775  mov     [rbx+8], rbx
0x140082779  mov     [rbx], rbx
0x14008277c  call    cs:__imp_ExInitializeResourceLite
0x140082783  nop     dword ptr [rax+rax+00h]
0x140082788  mov     esi, eax
0x14008278a  test    eax, eax
0x14008278c  jns     short loc_1400827CD
0x14008278e  mov     edx, eax
0x140082790  shr     edx, 1Fh
0x140082793  xor     dl, 1
0x140082796  jz      short loc_1400827A8
0x140082798  lea     rcx, [rbx+40h]; Resource
0x14008279c  call    cs:__imp_ExDeleteResourceLite
0x1400827a3  nop     dword ptr [rax+rax+00h]
0x1400827a8  test    rdi, rdi
0x1400827ab  jz      short loc_1400827BC
0x1400827ad  mov     rcx, rdi; Object
0x1400827b0  call    cs:__imp_ObfDereferenceObject
0x1400827b7  nop     dword ptr [rax+rax+00h]
0x1400827bc  mov     r8d, [rbp+84h]; Size
0x1400827c3  xor     edx, edx; Val
0x1400827c5  mov     rcx, rbx; void *
0x1400827c8  call    memset
0x1400827cd  mov     eax, esi
0x1400827cf  add     rsp, 20h
0x1400827d3  pop     r14
0x1400827d5  pop     rdi
0x1400827d6  pop     rsi
0x1400827d7  pop     rbp
0x1400827d8  pop     rbx
0x1400827d9  retn
```
