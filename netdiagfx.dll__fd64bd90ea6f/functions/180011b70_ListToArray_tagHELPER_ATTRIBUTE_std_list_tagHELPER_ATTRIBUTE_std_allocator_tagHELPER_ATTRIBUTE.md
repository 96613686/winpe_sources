# ListToArray<tagHELPER_ATTRIBUTE>(std::list<tagHELPER_ATTRIBUTE,std::allocator<tagHELPER_ATTRIBUTE>> *)

- ea: `0x180011b70`
- end: `0x180011c17`
- name: `??$ListToArray@UtagHELPER_ATTRIBUTE@@@@YAPEAUtagHELPER_ATTRIBUTE@@PEAV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@@Z`
- size: `167`
- prototype: `_OWORD *__fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800121d0`
- `0x18001dfa4`
- `0x180022810`

## callees

- `0x180011b70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011b8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011b8e`

## pseudocode

```c
_OWORD *__fastcall ListToArray<tagHELPER_ATTRIBUTE>(__int64 a1)
{
  __int64 v1; // rax
  _OWORD *result; // rax
  _OWORD *v4; // r8
  _QWORD *v5; // rdx
  _OWORD *v6; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( !v1 )
    return 0;
  result = CoTaskMemAlloc(144 * v1);
  if ( !result )
    return 0;
  v4 = result;
  v5 = **(_QWORD ***)a1;
  while ( v5 != *(_QWORD **)a1 )
  {
    v6 = v5;
    v5 = (_QWORD *)*v5;
    *v4 = v6[1];
    v4[1] = v6[2];
    v4[2] = v6[3];
    v4[3] = v6[4];
    v4[4] = v6[5];
    v4[5] = v6[6];
    v4[6] = v6[7];
    v4[7] = v6[8];
    v4[8] = v6[9];
    v4 += 9;
  }
  return result;
}

```

## disassembly

```asm
0x180011b70  push    rbx
0x180011b72  sub     rsp, 20h
0x180011b76  mov     rax, [rcx+8]
0x180011b7a  mov     rbx, rcx
0x180011b7d  test    rax, rax
0x180011b80  jz      loc_180011C0F
0x180011b86  lea     rcx, [rax+rax*8]
0x180011b8a  shl     rcx, 4; cb
0x180011b8e  call    cs:__imp_CoTaskMemAlloc
0x180011b94  test    rax, rax
0x180011b97  jz      short loc_180011C0F
0x180011b99  mov     rdx, [rbx]
0x180011b9c  mov     r8, rax
0x180011b9f  mov     rdx, [rdx]
0x180011ba2  cmp     rdx, [rbx]
0x180011ba5  jz      short loc_180011C11
0x180011ba7  mov     rcx, rdx
0x180011baa  mov     rdx, [rdx]
0x180011bad  movups  xmm0, xmmword ptr [rcx+10h]
0x180011bb1  movups  xmmword ptr [r8], xmm0
0x180011bb5  movups  xmm1, xmmword ptr [rcx+20h]
0x180011bb9  movups  xmmword ptr [r8+10h], xmm1
0x180011bbe  movups  xmm0, xmmword ptr [rcx+30h]
0x180011bc2  movups  xmmword ptr [r8+20h], xmm0
0x180011bc7  movups  xmm1, xmmword ptr [rcx+40h]
0x180011bcb  movups  xmmword ptr [r8+30h], xmm1
0x180011bd0  movups  xmm0, xmmword ptr [rcx+50h]
0x180011bd4  movups  xmmword ptr [r8+40h], xmm0
0x180011bd9  movups  xmm1, xmmword ptr [rcx+60h]
0x180011bdd  movups  xmmword ptr [r8+50h], xmm1
0x180011be2  movups  xmm0, xmmword ptr [rcx+70h]
0x180011be6  movups  xmmword ptr [r8+60h], xmm0
0x180011beb  movups  xmm1, xmmword ptr [rcx+80h]
0x180011bf2  movups  xmmword ptr [r8+70h], xmm1
0x180011bf7  movups  xmm0, xmmword ptr [rcx+90h]
0x180011bfe  movups  xmmword ptr [r8+80h], xmm0
0x180011c06  add     r8, 90h
0x180011c0d  jmp     short loc_180011BA2
0x180011c0f  xor     eax, eax
0x180011c11  add     rsp, 20h
0x180011c15  pop     rbx
0x180011c16  retn
```
