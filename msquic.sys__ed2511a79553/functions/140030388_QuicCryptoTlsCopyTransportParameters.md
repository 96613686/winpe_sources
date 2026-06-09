# QuicCryptoTlsCopyTransportParameters

- ea: `0x140030388`
- end: `0x140030476`
- name: `QuicCryptoTlsCopyTransportParameters`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000524c`

## callees

- `0x140030388`
- `0x14003cb00`
- `0x14003ed00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140030407`
- `ntoskrnl!ExAllocatePool2` at `0x140030407`

## pseudocode

```c
__int64 __fastcall QuicCryptoTlsCopyTransportParameters(const void **a1, __int64 a2)
{
  _OWORD *v3; // rax
  __int64 v4; // rdx
  const void **v5; // rbx
  __int128 v6; // xmm1
  void *Pool2; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx

  v3 = (_OWORD *)a2;
  v4 = 2;
  v5 = a1;
  do
  {
    *v3 = *(_OWORD *)a1;
    v3[1] = *((_OWORD *)a1 + 1);
    v3[2] = *((_OWORD *)a1 + 2);
    v3[3] = *((_OWORD *)a1 + 3);
    v3[4] = *((_OWORD *)a1 + 4);
    v3[5] = *((_OWORD *)a1 + 5);
    v3[6] = *((_OWORD *)a1 + 6);
    v3 += 8;
    v6 = *((_OWORD *)a1 + 7);
    a1 += 16;
    *(v3 - 1) = v6;
    --v4;
  }
  while ( v4 );
  if ( (*(_DWORD *)v5 & 0x80000) == 0 )
    return 0;
  Pool2 = (void *)ExAllocatePool2(66, *((unsigned int *)v5 + 60), 842294097);
  *(_QWORD *)(a2 + 248) = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)a2 |= 0x80000u;
    memmove(Pool2, v5[31], *((unsigned int *)v5 + 60));
    *(_DWORD *)(a2 + 240) = *((_DWORD *)v5 + 60);
    return 0;
  }
  if ( (Microsoft_QuicEnableBits & 2) != 0 )
    McTemplateU0sx_EtwWriteTransfer(v9, v8, "Version Negotiation Info", *((unsigned int *)v5 + 60));
  return 3221225495LL;
}

```

## disassembly

```asm
0x140030388  mov     [rsp+arg_0], rbx
0x14003038d  push    rdi
0x14003038e  sub     rsp, 20h
0x140030392  mov     rdi, rdx
0x140030395  mov     rax, rdx
0x140030398  mov     edx, 2
0x14003039d  mov     rbx, rcx
0x1400303a0  lea     r8d, [rdx+7Eh]
0x1400303a4  movups  xmm0, xmmword ptr [rcx]
0x1400303a7  movups  xmmword ptr [rax], xmm0
0x1400303aa  movups  xmm1, xmmword ptr [rcx+10h]
0x1400303ae  movups  xmmword ptr [rax+10h], xmm1
0x1400303b2  movups  xmm0, xmmword ptr [rcx+20h]
0x1400303b6  movups  xmmword ptr [rax+20h], xmm0
0x1400303ba  movups  xmm1, xmmword ptr [rcx+30h]
0x1400303be  movups  xmmword ptr [rax+30h], xmm1
0x1400303c2  movups  xmm0, xmmword ptr [rcx+40h]
0x1400303c6  movups  xmmword ptr [rax+40h], xmm0
0x1400303ca  movups  xmm1, xmmword ptr [rcx+50h]
0x1400303ce  movups  xmmword ptr [rax+50h], xmm1
0x1400303d2  movups  xmm0, xmmword ptr [rcx+60h]
0x1400303d6  movups  xmmword ptr [rax+60h], xmm0
0x1400303da  add     rax, r8
0x1400303dd  movups  xmm1, xmmword ptr [rcx+70h]
0x1400303e1  add     rcx, r8
0x1400303e4  movups  xmmword ptr [rax-10h], xmm1
0x1400303e8  sub     rdx, 1
0x1400303ec  jnz     short loc_1400303A4
0x1400303ee  test    dword ptr [rbx], 80000h
0x1400303f4  jz      short loc_140030468
0x1400303f6  mov     edx, [rbx+0F0h]
0x1400303fc  mov     ecx, 42h ; 'B'
0x140030401  mov     r8d, 32346351h
0x140030407  call    cs:__imp_ExAllocatePool2
0x14003040e  nop     dword ptr [rax+rax+00h]
0x140030413  mov     [rdi+0F8h], rax
0x14003041a  test    rax, rax
0x14003041d  jnz     short loc_140030442
0x14003041f  test    cs:Microsoft_QuicEnableBits, 2
0x140030426  jz      short loc_14003043B
0x140030428  mov     r9d, [rbx+0F0h]
0x14003042f  lea     r8, aVersionNegotia_0; "Version Negotiation Info"
0x140030436  call    McTemplateU0sx_EtwWriteTransfer
0x14003043b  mov     eax, 0C0000017h
0x140030440  jmp     short loc_14003046A
0x140030442  bts     dword ptr [rdi], 13h
0x140030446  mov     rcx, rax; void *
0x140030449  mov     r8d, [rbx+0F0h]; Size
0x140030450  mov     rdx, [rbx+0F8h]; Src
0x140030457  call    memmove
0x14003045c  mov     eax, [rbx+0F0h]
0x140030462  mov     [rdi+0F0h], eax
0x140030468  xor     eax, eax
0x14003046a  mov     rbx, [rsp+28h+arg_0]
0x14003046f  add     rsp, 20h
0x140030473  pop     rdi
0x140030474  retn
```
