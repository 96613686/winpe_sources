# PCW_COUNTERSET::PCW_COUNTERSET(utl::unique_ptr<PCW_SILO_NEUTRAL_COUNTERSET,ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>> &&,PCW_SILO_CONTEXT *)

- ea: `0x14000cb24`
- end: `0x14000cbf1`
- name: `??0PCW_COUNTERSET@@AEAA@$$QEAV?$unique_ptr@VPCW_SILO_NEUTRAL_COUNTERSET@@U?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@@utl@@PEAVPCW_SILO_CONTEXT@@@Z`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d460`

## callees

- `0x14000cb24`

## import_xrefs

- `ntoskrnl!PsReferenceSiloContext` at `0x14000cbb0`
- `ntoskrnl!PsReferenceSiloContext` at `0x14000cbb0`

## pseudocode

```c
__int64 __fastcall PCW_COUNTERSET::PCW_COUNTERSET(__int64 a1, __int64 *a2, __int64 a3)
{
  __int16 v5; // r9
  __int64 v6; // rdi
  __int64 v7; // r10
  __int64 v8; // rsi
  __int64 v9; // r14
  _QWORD *v10; // rcx
  __int64 v11; // rax
  __int64 result; // rax

  v5 = *(_WORD *)(*a2 + 24);
  v6 = a1 + 88;
  v7 = *(_QWORD *)(*a2 + 32);
  v8 = a1 + 112;
  *(_OWORD *)a1 = 0;
  v9 = a1 + 128;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)(a1 + 24) = v5;
  *(_WORD *)(a1 + 26) = v5;
  *(_DWORD *)(a1 + 28) = 0;
  *(_QWORD *)(a1 + 32) = v7;
  v10 = (_QWORD *)(a1 + 40);
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 72) = a1 + 64;
  *(_QWORD *)(a1 + 64) = a1 + 64;
  v10[1] = v10;
  *v10 = v10;
  v11 = *a2;
  *a2 = 0;
  *(_QWORD *)(a1 + 80) = v11;
  *(_OWORD *)v6 = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_OWORD *)v8 = 0;
  *(_OWORD *)v9 = 0;
  if ( a3 )
    PsReferenceSiloContext(a3);
  *(_QWORD *)(a1 + 144) = a3;
  result = a1;
  *(_DWORD *)(a1 + 152) = 1;
  *(_QWORD *)(v6 + 8) = v6;
  *(_QWORD *)v6 = v6;
  *(_QWORD *)(v8 + 8) = v8;
  *(_QWORD *)v8 = v8;
  *(_QWORD *)(v9 + 8) = v9;
  *(_QWORD *)v9 = v9;
  return result;
}

```

## disassembly

```asm
0x14000cb24  push    rbx
0x14000cb26  push    rbp
0x14000cb27  push    rsi
0x14000cb28  push    rdi
0x14000cb29  push    r14
0x14000cb2b  sub     rsp, 20h
0x14000cb2f  mov     rax, [rdx]
0x14000cb32  mov     rbx, rcx
0x14000cb35  xorps   xmm0, xmm0
0x14000cb38  xorps   xmm1, xmm1
0x14000cb3b  mov     rbp, r8
0x14000cb3e  movzx   r9d, word ptr [rax+18h]
0x14000cb43  lea     rdi, [rbx+58h]
0x14000cb47  mov     r10, [rax+20h]
0x14000cb4b  lea     rsi, [rbx+70h]
0x14000cb4f  movups  xmmword ptr [rcx], xmm0
0x14000cb52  xor     eax, eax
0x14000cb54  lea     r14, [rbx+80h]
0x14000cb5b  mov     [rcx+10h], rax
0x14000cb5f  mov     [rcx+18h], r9w
0x14000cb64  mov     [rcx+1Ah], r9w
0x14000cb69  mov     [rcx+1Ch], eax
0x14000cb6c  mov     [rcx+20h], r10
0x14000cb70  add     rcx, 28h ; '('
0x14000cb74  mov     [rbx+38h], rax
0x14000cb78  lea     rax, [rbx+40h]
0x14000cb7c  mov     [rax+8], rax
0x14000cb80  mov     [rax], rax
0x14000cb83  mov     [rcx+8], rcx
0x14000cb87  mov     [rcx], rcx
0x14000cb8a  mov     rax, [rdx]
0x14000cb8d  mov     qword ptr [rdx], 0
0x14000cb94  mov     [rbx+50h], rax
0x14000cb98  xor     eax, eax
0x14000cb9a  movups  xmmword ptr [rdi], xmm0
0x14000cb9d  mov     [rbx+68h], rax
0x14000cba1  movups  xmmword ptr [rsi], xmm0
0x14000cba4  movups  xmmword ptr [r14], xmm1
0x14000cba8  test    r8, r8
0x14000cbab  jz      short loc_14000CBBC
0x14000cbad  mov     rcx, r8
0x14000cbb0  call    cs:__imp_PsReferenceSiloContext
0x14000cbb7  nop     dword ptr [rax+rax+00h]
0x14000cbbc  mov     [rbx+90h], rbp
0x14000cbc3  mov     rax, rbx
0x14000cbc6  mov     dword ptr [rbx+98h], 1
0x14000cbd0  mov     [rdi+8], rdi
0x14000cbd4  mov     [rdi], rdi
0x14000cbd7  mov     [rsi+8], rsi
0x14000cbdb  mov     [rsi], rsi
0x14000cbde  mov     [r14+8], r14
0x14000cbe2  mov     [r14], r14
0x14000cbe5  add     rsp, 20h
0x14000cbe9  pop     r14
0x14000cbeb  pop     rdi
0x14000cbec  pop     rsi
0x14000cbed  pop     rbp
0x14000cbee  pop     rbx
0x14000cbef  retn
```
