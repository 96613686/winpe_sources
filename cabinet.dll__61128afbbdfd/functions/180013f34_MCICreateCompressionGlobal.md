# MCICreateCompressionGlobal

- ea: `0x180013f34`
- end: `0x180014081`
- name: `MCICreateCompressionGlobal`
- size: `333`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800146f0`

## callees

- `0x180013f34`
- `0x180014088`
- `0x1800142a8`
- `0x180016cc0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall MCICreateCompressionGlobal(__int64 a1)
{
  __int16 v1; // dx
  unsigned int *v2; // rsi
  __int64 v4; // rax
  __int64 v5; // r9
  unsigned int *v6; // rdi
  __int64 v7; // r8
  int v8; // eax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // [rsp+70h] [rbp+8h] BYREF
  int v14; // [rsp+74h] [rbp+Ch]

  v1 = *(_WORD *)(a1 + 676);
  v2 = (unsigned int *)(a1 + 664);
  *(_QWORD *)(a1 + 688) = 0;
  *(_QWORD *)(a1 + 680) = 0;
  *(_DWORD *)(a1 + 664) = 0x8000;
  switch ( v1 & 0xF )
  {
    case 0:
      v6 = (unsigned int *)(a1 + 660);
      *(_DWORD *)(a1 + 660) = 0x8000;
LABEL_13:
      v10 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 16))(*v6);
      *(_QWORD *)(a1 + 688) = v10;
      if ( !v10 || (v11 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 16))(*v2), (*(_QWORD *)(a1 + 680) = v11) == 0) )
      {
        v12 = *(_QWORD *)(a1 + 88);
        *(_DWORD *)(v12 + 8) = 1;
        *(_QWORD *)v12 = 3;
        MCIDestroyCompressionGlobal(a1);
        return 0;
      }
      return 1;
    case 1:
      v6 = (unsigned int *)(a1 + 660);
      v8 = MCICreateCompression((_DWORD)v2, *(_QWORD *)(a1 + 16), *(_QWORD *)(a1 + 24), (int)a1 + 660, a1 + 8);
LABEL_8:
      if ( v8 )
      {
        v4 = *(_QWORD *)(a1 + 88);
        *(_QWORD *)v4 = 8;
        goto LABEL_10;
      }
      goto LABEL_13;
    case 3:
      v5 = *(_QWORD *)(a1 + 24);
      v6 = (unsigned int *)(a1 + 660);
      v7 = *(_QWORD *)(a1 + 16);
      v14 = 0x10000;
      v13 = 1 << (HIBYTE(v1) & 0x1F);
      v8 = LCICreateCompression((_DWORD)v2, (unsigned int)&v13, v7, v5, a1 + 660, a1 + 8);
      goto LABEL_8;
  }
  if ( (v1 & 0xF) != 0xF )
  {
    v4 = *(_QWORD *)(a1 + 88);
    *(_QWORD *)v4 = 5;
LABEL_10:
    *(_DWORD *)(v4 + 8) = 1;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180013f34  push    rbx
0x180013f36  push    rsi
0x180013f37  push    rdi
0x180013f38  push    r14
0x180013f3a  sub     rsp, 48h
0x180013f3e  movzx   edx, word ptr [rcx+2A4h]
0x180013f45  lea     rsi, [rcx+298h]
0x180013f4c  mov     rbx, rcx
0x180013f4f  mov     qword ptr [rcx+2B0h], 0
0x180013f5a  mov     qword ptr [rcx+2A8h], 0
0x180013f65  mov     r8d, 8000h
0x180013f6b  mov     ecx, edx
0x180013f6d  mov     [rsi], r8d
0x180013f70  mov     r14d, 1
0x180013f76  and     ecx, 0Fh
0x180013f79  jz      loc_180014023
0x180013f7f  sub     ecx, r14d
0x180013f82  jz      short loc_180013FE9
0x180013f84  sub     ecx, 2
0x180013f87  jz      short loc_180013F9F
0x180013f89  cmp     ecx, 0Ch
0x180013f8c  jz      loc_180014074
0x180013f92  mov     rax, [rbx+58h]
0x180013f96  mov     qword ptr [rax], 5
0x180013f9d  jmp     short loc_18001401B
0x180013f9f  mov     r9, [rbx+18h]
0x180013fa3  lea     rdi, [rbx+294h]
0x180013faa  mov     r8, [rbx+10h]
0x180013fae  mov     eax, r14d
0x180013fb1  shr     edx, 8
0x180013fb4  and     edx, 1Fh
0x180013fb7  mov     [rsp+68h+var_30], rbx
0x180013fbc  mov     cl, dl
0x180013fbe  mov     [rsp+68h+arg_4], 10000h
0x180013fc6  shl     eax, cl
0x180013fc8  lea     rdx, [rsp+68h+arg_0]
0x180013fcd  mov     [rsp+68h+arg_0], eax
0x180013fd1  mov     rcx, rsi
0x180013fd4  lea     rax, [rbx+8]
0x180013fd8  mov     [rsp+68h+var_40], rax
0x180013fdd  mov     [rsp+68h+var_48], rdi
0x180013fe2  call    LCICreateCompression
0x180013fe7  jmp     short loc_18001400C
0x180013fe9  mov     r8, [rbx+18h]
0x180013fed  lea     rax, [rbx+8]
0x180013ff1  mov     rdx, [rbx+10h]
0x180013ff5  lea     rdi, [rbx+294h]
0x180013ffc  mov     r9, rdi
0x180013fff  mov     [rsp+68h+var_48], rax
0x180014004  mov     rcx, rsi
0x180014007  call    MCICreateCompression
0x18001400c  test    eax, eax
0x18001400e  jz      short loc_18001402D
0x180014010  mov     rax, [rbx+58h]
0x180014014  mov     qword ptr [rax], 8
0x18001401b  mov     [rax+8], r14d
0x18001401f  xor     eax, eax
0x180014021  jmp     short loc_180014077
0x180014023  lea     rdi, [rbx+294h]
0x18001402a  mov     [rdi], r8d
0x18001402d  mov     ecx, [rdi]
0x18001402f  mov     rax, [rbx+10h]
0x180014033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014038  mov     [rbx+2B0h], rax
0x18001403f  test    rax, rax
0x180014042  jz      short loc_18001405B
0x180014044  mov     ecx, [rsi]
0x180014046  mov     rax, [rbx+10h]
0x18001404a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001404f  mov     [rbx+2A8h], rax
0x180014056  test    rax, rax
0x180014059  jnz     short loc_180014074
0x18001405b  mov     rax, [rbx+58h]
0x18001405f  mov     [rax+8], r14d
0x180014063  mov     qword ptr [rax], 3
0x18001406a  mov     rcx, rbx
0x18001406d  call    MCIDestroyCompressionGlobal
0x180014072  jmp     short loc_18001401F
0x180014074  mov     eax, r14d
0x180014077  add     rsp, 48h
0x18001407b  pop     r14
0x18001407d  pop     rdi
0x18001407e  pop     rsi
0x18001407f  pop     rbx
0x180014080  retn
```
