# DXVAConfiguration::assign(DXVAConfiguration const &)

- ea: `0x18004e380`
- end: `0x18004e49c`
- name: `?assign@DXVAConfiguration@@QEAA_NAEBU1@@Z`
- size: `284`
- prototype: `bool __fastcall(DXVAConfiguration *__hidden this, const struct DXVAConfiguration *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18004dc20`

## callees

- `0x18004e20c`
- `0x18004e380`

## pseudocode

```c
char __fastcall DXVAConfiguration::assign(DXVAConfiguration *this, const struct DXVAConfiguration *a2)
{
  __int64 v2; // r9
  _OWORD *v4; // rax
  _OWORD *v5; // rcx
  __int128 v6; // xmm1

  v2 = 3;
  *((_OWORD *)this + 1) = *((_OWORD *)a2 + 1);
  *((_OWORD *)this + 2) = *((_OWORD *)a2 + 2);
  *((_OWORD *)this + 3) = *((_OWORD *)a2 + 3);
  *((_OWORD *)this + 4) = *((_OWORD *)a2 + 4);
  *((_OWORD *)this + 5) = *((_OWORD *)a2 + 5);
  *((_OWORD *)this + 6) = *((_OWORD *)a2 + 6);
  *((_DWORD *)this + 28) = *((_DWORD *)a2 + 28);
  v4 = (_OWORD *)((char *)a2 + 116);
  *(_OWORD *)((char *)this + 616) = *(_OWORD *)((char *)a2 + 616);
  *(_OWORD *)((char *)this + 632) = *(_OWORD *)((char *)a2 + 632);
  *(_OWORD *)((char *)this + 648) = *(_OWORD *)((char *)a2 + 648);
  *(_OWORD *)((char *)this + 664) = *(_OWORD *)((char *)a2 + 664);
  v5 = (_OWORD *)((char *)this + 116);
  do
  {
    *v5 = *v4;
    v5[1] = v4[1];
    v5[2] = v4[2];
    v5[3] = v4[3];
    v5[4] = v4[4];
    v5[5] = v4[5];
    v5[6] = v4[6];
    v6 = v4[7];
    v4 += 8;
    v5[7] = v6;
    v5 += 8;
    --v2;
  }
  while ( v2 );
  *v5 = *v4;
  v5[1] = v4[1];
  v5[2] = v4[2];
  v5[3] = v4[3];
  v5[4] = v4[4];
  v5[5] = v4[5];
  v5[6] = v4[6];
  *((_DWORD *)v5 + 28) = *((_DWORD *)v4 + 28);
  return utl::_Tree<enum DXGI_FORMAT,enum DXGI_FORMAT,utl::less<enum DXGI_FORMAT>,utl::allocator<enum DXGI_FORMAT>,0>::_CopyAssignFrom(
           (__int64 *)this + 85,
           (__int64 *)a2 + 85);
}

```

## disassembly

```asm
0x18004e380  movups  xmm0, xmmword ptr [rdx+10h]
0x18004e384  mov     r9d, 3
0x18004e38a  mov     r8, rcx
0x18004e38d  movups  xmmword ptr [rcx+10h], xmm0
0x18004e391  movups  xmm1, xmmword ptr [rdx+20h]
0x18004e395  lea     r10d, [r9+7Dh]
0x18004e399  movups  xmmword ptr [rcx+20h], xmm1
0x18004e39d  movups  xmm0, xmmword ptr [rdx+30h]
0x18004e3a1  movups  xmmword ptr [rcx+30h], xmm0
0x18004e3a5  movups  xmm1, xmmword ptr [rdx+40h]
0x18004e3a9  movups  xmmword ptr [rcx+40h], xmm1
0x18004e3ad  movups  xmm0, xmmword ptr [rdx+50h]
0x18004e3b1  movups  xmmword ptr [rcx+50h], xmm0
0x18004e3b5  movups  xmm1, xmmword ptr [rdx+60h]
0x18004e3b9  movups  xmmword ptr [rcx+60h], xmm1
0x18004e3bd  mov     eax, [rdx+70h]
0x18004e3c0  mov     [rcx+70h], eax
0x18004e3c3  lea     rax, [rdx+74h]
0x18004e3c7  movups  xmm0, xmmword ptr [rdx+268h]
0x18004e3ce  movups  xmmword ptr [rcx+268h], xmm0
0x18004e3d5  movups  xmm1, xmmword ptr [rdx+278h]
0x18004e3dc  movups  xmmword ptr [rcx+278h], xmm1
0x18004e3e3  movups  xmm0, xmmword ptr [rdx+288h]
0x18004e3ea  movups  xmmword ptr [rcx+288h], xmm0
0x18004e3f1  movups  xmm1, xmmword ptr [rdx+298h]
0x18004e3f8  movups  xmmword ptr [rcx+298h], xmm1
0x18004e3ff  add     rcx, 74h ; 't'
0x18004e403  movups  xmm0, xmmword ptr [rax]
0x18004e406  movups  xmmword ptr [rcx], xmm0
0x18004e409  movups  xmm1, xmmword ptr [rax+10h]
0x18004e40d  movups  xmmword ptr [rcx+10h], xmm1
0x18004e411  movups  xmm0, xmmword ptr [rax+20h]
0x18004e415  movups  xmmword ptr [rcx+20h], xmm0
0x18004e419  movups  xmm1, xmmword ptr [rax+30h]
0x18004e41d  movups  xmmword ptr [rcx+30h], xmm1
0x18004e421  movups  xmm0, xmmword ptr [rax+40h]
0x18004e425  movups  xmmword ptr [rcx+40h], xmm0
0x18004e429  movups  xmm1, xmmword ptr [rax+50h]
0x18004e42d  movups  xmmword ptr [rcx+50h], xmm1
0x18004e431  movups  xmm0, xmmword ptr [rax+60h]
0x18004e435  movups  xmmword ptr [rcx+60h], xmm0
0x18004e439  movups  xmm1, xmmword ptr [rax+70h]
0x18004e43d  add     rax, r10
0x18004e440  movups  xmmword ptr [rcx+70h], xmm1
0x18004e444  add     rcx, r10
0x18004e447  sub     r9, 1
0x18004e44b  jnz     short loc_18004E403
0x18004e44d  movups  xmm0, xmmword ptr [rax]
0x18004e450  add     rdx, 2A8h
0x18004e457  movups  xmmword ptr [rcx], xmm0
0x18004e45a  movups  xmm1, xmmword ptr [rax+10h]
0x18004e45e  movups  xmmword ptr [rcx+10h], xmm1
0x18004e462  movups  xmm0, xmmword ptr [rax+20h]
0x18004e466  movups  xmmword ptr [rcx+20h], xmm0
0x18004e46a  movups  xmm1, xmmword ptr [rax+30h]
0x18004e46e  movups  xmmword ptr [rcx+30h], xmm1
0x18004e472  movups  xmm0, xmmword ptr [rax+40h]
0x18004e476  movups  xmmword ptr [rcx+40h], xmm0
0x18004e47a  movups  xmm1, xmmword ptr [rax+50h]
0x18004e47e  movups  xmmword ptr [rcx+50h], xmm1
0x18004e482  movups  xmm0, xmmword ptr [rax+60h]
0x18004e486  movups  xmmword ptr [rcx+60h], xmm0
0x18004e48a  mov     eax, [rax+70h]
0x18004e48d  mov     [rcx+70h], eax
0x18004e490  lea     rcx, [r8+2A8h]
0x18004e497  jmp     ?_CopyAssignFrom@?$_Tree@W4DXGI_FORMAT@@W41@U?$less@W4DXGI_FORMAT@@@utl@@V?$allocator@W4DXGI_FORMAT@@@3@$0A@@utl@@IEAA_NAEBV12@@Z; utl::_Tree<DXGI_FORMAT,DXGI_FORMAT,utl::less<DXGI_FORMAT>,utl::allocator<DXGI_FORMAT>,0>::_CopyAssignFrom(utl::_Tree<DXGI_FORMAT,DXGI_FORMAT,utl::less<DXGI_FORMAT>,utl::allocator<DXGI_FORMAT>,0> const &)
```
