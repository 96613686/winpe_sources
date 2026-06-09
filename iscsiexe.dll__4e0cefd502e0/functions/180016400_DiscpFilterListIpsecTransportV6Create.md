# DiscpFilterListIpsecTransportV6Create

- ea: `0x180016400`
- end: `0x1800165bc`
- name: `DiscpFilterListIpsecTransportV6Create`
- size: `444`
- prototype: `__int64 __fastcall(__int64, int, int, int, int, int, __int16, int, _OWORD *, _OWORD *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180015384`

## callees

- `0x1800161c8`
- `0x180016400`
- `0x180016780`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x180016571`
- `ISCSIUM!DiscpAllocMemory` at `0x180016571`

## pseudocode

```c
__int64 __fastcall DiscpFilterListIpsecTransportV6Create(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        __int16 a7,
        int a8,
        _OWORD *a9,
        _OWORD *a10,
        _QWORD *a11,
        _DWORD *a12)
{
  unsigned int v14; // ebx
  int v15; // r8d
  __int64 v16; // rax
  int v17; // r8d
  __int64 v18; // rax
  int v19; // r8d
  _OWORD *v20; // rax
  __int128 v22; // xmm1
  int v23; // [rsp+50h] [rbp-30h] BYREF
  _OWORD *v24; // [rsp+58h] [rbp-28h] BYREF
  __int128 v25; // [rsp+60h] [rbp-20h]
  __int128 v26; // [rsp+70h] [rbp-10h]

  *a11 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  *a12 = 0;
  v26 = 0;
  v14 = DiscpFilterV6Create(68, a4, a3, a2);
  if ( !v14 )
  {
    if ( a9 )
    {
      v16 = v25;
      *(_OWORD *)(v25 + 152) = *a9;
      *(_DWORD *)(v16 + 32) |= 4u;
    }
    v23 = 1;
    v14 = DiscpFilterV6Create(72, a4, v15, a2);
    if ( !v14 )
    {
      if ( a10 )
      {
        v18 = *((_QWORD *)&v25 + 1);
        *(_OWORD *)(*((_QWORD *)&v25 + 1) + 152LL) = *a10;
        *(_DWORD *)(v18 + 32) |= 4u;
      }
      v23 = 2;
      v14 = DiscpFilterV6Create(34, a2, v17, a4);
      if ( !v14 )
      {
        v23 = 3;
        v14 = DiscpFilterV6Create(33, a4, v19, a2);
        if ( !v14 )
        {
          v23 = 4;
          v20 = (_OWORD *)DiscpAllocMemory(32);
          v24 = v20;
          if ( v20 )
          {
            v22 = v26;
            *v20 = v25;
            v20[1] = v22;
            *a11 = v20;
            *a12 = 4;
            return v14;
          }
          v14 = 8;
        }
      }
    }
  }
  DiscpFilterListDestroy(&v24, &v23);
  return v14;
}

```

## disassembly

```asm
0x180016400  push    rbp
0x180016402  push    rbx
0x180016403  push    rsi
0x180016404  push    rdi
0x180016405  push    r12
0x180016407  push    r14
0x180016409  push    r15
0x18001640b  mov     rbp, rsp
0x18001640e  sub     rsp, 80h
0x180016415  mov     r15, [rbp+arg_50]
0x18001641c  mov     r14, rdx
0x18001641f  mov     r12, [rbp+arg_58]
0x180016426  lea     rdx, [rbp+var_20]
0x18001642a  mov     [rsp+80h+var_38], rdx
0x18001642f  xor     eax, eax
0x180016431  mov     [rsp+80h+var_48], al
0x180016435  xor     ecx, ecx
0x180016437  mov     rsi, r9
0x18001643a  mov     [rsp+80h+var_50], ax
0x18001643f  xorps   xmm0, xmm0
0x180016442  mov     [rsp+80h+var_58], cx
0x180016447  mov     qword ptr [r15], 0
0x18001644e  lea     ecx, [rax+44h]
0x180016451  mov     r9, r14
0x180016454  mov     [rbp+var_30], 0
0x18001645b  mov     rdx, rsi
0x18001645e  mov     [rbp+var_28], 0
0x180016466  movups  [rbp+var_20], xmm0
0x18001646a  mov     dword ptr [r12], 0
0x180016472  movups  [rbp+var_10], xmm0
0x180016476  call    DiscpFilterV6Create
0x18001647b  mov     ebx, eax
0x18001647d  test    eax, eax
0x18001647f  jnz     loc_180016583
0x180016485  mov     rcx, [rbp+arg_40]
0x18001648c  test    rcx, rcx
0x18001648f  jz      short loc_1800164A4
0x180016491  mov     rax, qword ptr [rbp+var_20]
0x180016495  movups  xmm0, xmmword ptr [rcx]
0x180016498  movdqu  xmmword ptr [rax+98h], xmm0
0x1800164a0  or      dword ptr [rax+20h], 4
0x1800164a4  movzx   edi, [rbp+arg_30]
0x1800164a8  lea     rcx, [rbp+var_20+8]
0x1800164ac  mov     [rsp+80h+var_38], rcx
0x1800164b1  xor     eax, eax
0x1800164b3  mov     [rsp+80h+var_48], 6
0x1800164b8  mov     r9, r14
0x1800164bb  mov     [rsp+80h+var_50], di
0x1800164c0  mov     rdx, rsi
0x1800164c3  mov     [rbp+var_30], 1
0x1800164ca  lea     ecx, [rax+48h]
0x1800164cd  mov     [rsp+80h+var_58], ax
0x1800164d2  call    DiscpFilterV6Create
0x1800164d7  mov     ebx, eax
0x1800164d9  test    eax, eax
0x1800164db  jnz     loc_180016583
0x1800164e1  mov     rcx, [rbp+arg_48]
0x1800164e8  test    rcx, rcx
0x1800164eb  jz      short loc_180016500
0x1800164ed  mov     rax, qword ptr [rbp+var_20+8]
0x1800164f1  movups  xmm0, xmmword ptr [rcx]
0x1800164f4  movdqu  xmmword ptr [rax+98h], xmm0
0x1800164fc  or      dword ptr [rax+20h], 4
0x180016500  xor     eax, eax
0x180016502  mov     [rbp+var_30], 2
0x180016509  lea     rcx, [rbp+var_10]
0x18001650d  mov     r9, rsi
0x180016510  mov     [rsp+80h+var_38], rcx
0x180016515  mov     rdx, r14
0x180016518  mov     [rsp+80h+var_48], 6
0x18001651d  lea     ecx, [rax+22h]
0x180016520  mov     [rsp+80h+var_50], di
0x180016525  mov     [rsp+80h+var_58], ax
0x18001652a  call    DiscpFilterV6Create
0x18001652f  mov     ebx, eax
0x180016531  test    eax, eax
0x180016533  jnz     short loc_180016583
0x180016535  lea     rcx, [rbp+var_10+8]
0x180016539  mov     [rbp+var_30], 3
0x180016540  mov     [rsp+80h+var_38], rcx
0x180016545  mov     r9, r14
0x180016548  mov     [rsp+80h+var_48], 6
0x18001654d  lea     ecx, [rax+21h]
0x180016550  mov     [rsp+80h+var_50], ax
0x180016555  mov     rdx, rsi
0x180016558  mov     [rsp+80h+var_58], di
0x18001655d  call    DiscpFilterV6Create
0x180016562  mov     ebx, eax
0x180016564  test    eax, eax
0x180016566  jnz     short loc_180016583
0x180016568  lea     edi, [rax+4]
0x18001656b  lea     ecx, [rax+20h]
0x18001656e  mov     [rbp+var_30], edi
0x180016571  call    cs:__imp_DiscpAllocMemory
0x180016577  mov     [rbp+var_28], rax
0x18001657b  test    rax, rax
0x18001657e  jnz     short loc_1800165A4
0x180016580  lea     ebx, [rdi+4]
0x180016583  lea     rdx, [rbp+var_30]
0x180016587  lea     rcx, [rbp+var_28]
0x18001658b  call    DiscpFilterListDestroy
0x180016590  mov     eax, ebx
0x180016592  add     rsp, 80h
0x180016599  pop     r15
0x18001659b  pop     r14
0x18001659d  pop     r12
0x18001659f  pop     rdi
0x1800165a0  pop     rsi
0x1800165a1  pop     rbx
0x1800165a2  pop     rbp
0x1800165a3  retn
0x1800165a4  movups  xmm0, [rbp+var_20]
0x1800165a8  movups  xmm1, [rbp+var_10]
0x1800165ac  movups  xmmword ptr [rax], xmm0
0x1800165af  movups  xmmword ptr [rax+10h], xmm1
0x1800165b3  mov     [r15], rax
0x1800165b6  mov     [r12], edi
0x1800165ba  jmp     short loc_180016590
```
