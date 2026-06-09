# Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(Container::Manager::Image::RegistryAdjustment &&)

- ea: `0x1400153c4`
- end: `0x1400154f8`
- name: `??0RegistryAdjustment@Image@Manager@Container@@QEAA@$$QEAU0123@@Z`
- size: `308`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400113ec`
- `0x1400133e4`
- `0x140013ee8`
- `0x140014bbc`
- `0x1400150dc`
- `0x14001feac`

## callees

- `0x1400153c4`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(__int64 a1, __int64 a2)
{
  _OWORD *v2; // r9
  _OWORD *v3; // r10
  __int64 v4; // rax
  _OWORD *v5; // r10
  __int64 v6; // rax
  _OWORD *v7; // r9
  _OWORD *v8; // r10
  __int64 v9; // rax
  _OWORD *v10; // r8

  *(_DWORD *)a1 = *(_DWORD *)a2;
  v2 = (_OWORD *)(a2 + 24);
  v3 = (_OWORD *)(a1 + 24);
  *(_DWORD *)(a1 + 4) = *(_DWORD *)(a2 + 4);
  v4 = *(_QWORD *)(a2 + 8);
  if ( v4 == a2 + 24 )
  {
    *(_QWORD *)(a1 + 8) = v3;
    *(_QWORD *)(a1 + 16) = a1 + 2 * (((*(_QWORD *)(a2 + 16) - (a2 + 8) - 16) >> 1) + 12);
    *v3 = *v2;
  }
  else
  {
    *(_QWORD *)(a1 + 8) = v4;
    *(_QWORD *)(a1 + 16) = *(_QWORD *)(a2 + 16);
    *(_QWORD *)v3 = *(_QWORD *)v2;
  }
  *(_QWORD *)(a2 + 8) = v2;
  v5 = (_OWORD *)(a1 + 56);
  *(_QWORD *)(a2 + 16) = v2;
  *(_WORD *)v2 = 0;
  v6 = *(_QWORD *)(a2 + 40);
  v7 = (_OWORD *)(a2 + 56);
  if ( v6 == a2 + 56 )
  {
    *(_QWORD *)(a1 + 40) = v5;
    *(_QWORD *)(a1 + 48) = a1 + 2 * (((*(_QWORD *)(a2 + 48) - (a2 + 40) - 16) >> 1) + 28);
    *v5 = *v7;
  }
  else
  {
    *(_QWORD *)(a1 + 40) = v6;
    *(_QWORD *)(a1 + 48) = *(_QWORD *)(a2 + 48);
    *(_QWORD *)v5 = *(_QWORD *)v7;
  }
  *(_QWORD *)(a2 + 40) = v7;
  *(_QWORD *)(a2 + 48) = v7;
  v8 = (_OWORD *)(a1 + 88);
  *(_WORD *)v7 = 0;
  v9 = *(_QWORD *)(a2 + 72);
  v10 = (_OWORD *)(a2 + 88);
  if ( v9 == a2 + 88 )
  {
    *(_QWORD *)(a1 + 72) = v8;
    *(_QWORD *)(a1 + 80) = a1 + 2 * (((*(_QWORD *)(a2 + 80) - (a2 + 72) - 16) >> 1) + 44);
    *v8 = *v10;
  }
  else
  {
    *(_QWORD *)(a1 + 72) = v9;
    *(_QWORD *)(a1 + 80) = *(_QWORD *)(a2 + 80);
    *(_QWORD *)v8 = *(_QWORD *)v10;
  }
  *(_QWORD *)(a2 + 72) = v10;
  *(_WORD *)v10 = 0;
  *(_QWORD *)(a2 + 80) = v10;
  *(_DWORD *)(a1 + 104) = *(_DWORD *)(a2 + 104);
  *(_DWORD *)(a1 + 108) = *(_DWORD *)(a2 + 108);
  *(_DWORD *)(a1 + 112) = *(_DWORD *)(a2 + 112);
  return a1;
}

```

## disassembly

```asm
0x1400153c4  mov     eax, [rdx]
0x1400153c6  lea     r8, [rdx+8]
0x1400153ca  mov     [rcx], eax
0x1400153cc  lea     r9, [r8+10h]
0x1400153d0  mov     eax, [rdx+4]
0x1400153d3  lea     r10, [rcx+18h]
0x1400153d7  mov     [rcx+4], eax
0x1400153da  mov     rax, [r8]
0x1400153dd  cmp     rax, r9
0x1400153e0  jnz     short loc_14001540B
0x1400153e2  mov     [rcx+8], r10
0x1400153e6  mov     rax, [r8+8]
0x1400153ea  sub     rax, r8
0x1400153ed  sub     rax, 10h
0x1400153f1  sar     rax, 1
0x1400153f4  add     rax, 0Ch
0x1400153f8  lea     rax, [rcx+rax*2]
0x1400153fc  mov     [rcx+10h], rax
0x140015400  movups  xmm0, xmmword ptr [r9]
0x140015404  movdqu  xmmword ptr [r10], xmm0
0x140015409  jmp     short loc_14001541D
0x14001540b  mov     [rcx+8], rax
0x14001540f  mov     rax, [r8+8]
0x140015413  mov     [rcx+10h], rax
0x140015417  mov     rax, [r9]
0x14001541a  mov     [r10], rax
0x14001541d  mov     [r8], r9
0x140015420  lea     r10, [rcx+38h]
0x140015424  mov     [r8+8], r9
0x140015428  xor     eax, eax
0x14001542a  lea     r8, [rdx+28h]
0x14001542e  mov     [r9], ax
0x140015432  mov     rax, [r8]
0x140015435  lea     r9, [r8+10h]
0x140015439  cmp     rax, r9
0x14001543c  jnz     short loc_140015467
0x14001543e  mov     [rcx+28h], r10
0x140015442  mov     rax, [r8+8]
0x140015446  sub     rax, r8
0x140015449  sub     rax, 10h
0x14001544d  sar     rax, 1
0x140015450  add     rax, 1Ch
0x140015454  lea     rax, [rcx+rax*2]
0x140015458  mov     [rcx+30h], rax
0x14001545c  movups  xmm0, xmmword ptr [r9]
0x140015460  movdqu  xmmword ptr [r10], xmm0
0x140015465  jmp     short loc_140015479
0x140015467  mov     [rcx+28h], rax
0x14001546b  mov     rax, [r8+8]
0x14001546f  mov     [rcx+30h], rax
0x140015473  mov     rax, [r9]
0x140015476  mov     [r10], rax
0x140015479  xor     eax, eax
0x14001547b  mov     [r8], r9
0x14001547e  mov     [r8+8], r9
0x140015482  lea     r10, [rcx+58h]
0x140015486  mov     [r9], ax
0x14001548a  lea     r9, [rdx+48h]
0x14001548e  mov     rax, [r9]
0x140015491  lea     r8, [r9+10h]
0x140015495  cmp     rax, r8
0x140015498  jnz     short loc_1400154C3
0x14001549a  mov     [rcx+48h], r10
0x14001549e  mov     rax, [r9+8]
0x1400154a2  sub     rax, r9
0x1400154a5  sub     rax, 10h
0x1400154a9  sar     rax, 1
0x1400154ac  add     rax, 2Ch ; ','
0x1400154b0  lea     rax, [rcx+rax*2]
0x1400154b4  mov     [rcx+50h], rax
0x1400154b8  movups  xmm0, xmmword ptr [r8]
0x1400154bc  movdqu  xmmword ptr [r10], xmm0
0x1400154c1  jmp     short loc_1400154D5
0x1400154c3  mov     [rcx+48h], rax
0x1400154c7  mov     rax, [r9+8]
0x1400154cb  mov     [rcx+50h], rax
0x1400154cf  mov     rax, [r8]
0x1400154d2  mov     [r10], rax
0x1400154d5  mov     [r9], r8
0x1400154d8  xor     eax, eax
0x1400154da  mov     [r8], ax
0x1400154de  mov     [r9+8], r8
0x1400154e2  mov     eax, [rdx+68h]
0x1400154e5  mov     [rcx+68h], eax
0x1400154e8  mov     eax, [rdx+6Ch]
0x1400154eb  mov     [rcx+6Ch], eax
0x1400154ee  mov     eax, [rdx+70h]
0x1400154f1  mov     [rcx+70h], eax
0x1400154f4  mov     rax, rcx
0x1400154f7  retn
```
