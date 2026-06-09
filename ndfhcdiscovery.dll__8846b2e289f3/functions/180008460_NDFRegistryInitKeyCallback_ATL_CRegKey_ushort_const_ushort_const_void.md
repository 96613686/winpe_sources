# NDFRegistryInitKeyCallback(ATL::CRegKey &,ushort const *,ushort const *,void *)

- ea: `0x180008460`
- end: `0x18000850e`
- name: `?NDFRegistryInitKeyCallback@@YAJAEAVCRegKey@ATL@@PEBG1PEAX@Z`
- size: `174`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *, const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180007d5c`
- `0x180008460`
- `0x180011a10`

## pseudocode

```c
LSTATUS __fastcall NDFRegistryInitKeyCallback(HKEY *a1, unsigned __int16 *a2, unsigned __int16 *a3, _QWORD *a4)
{
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  bool v6; // cf
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int64 v9; // rax
  __int128 v11; // [rsp+30h] [rbp-40h] BYREF
  __int128 v12; // [rsp+40h] [rbp-30h]
  __int128 v13; // [rsp+50h] [rbp-20h]
  __int64 v14; // [rsp+60h] [rbp-10h]

  if ( !*((_WORD *)a4 + 24) )
  {
    a4[4] = a2;
    v4 = *((_OWORD *)a4 + 1);
    v11 = *(_OWORD *)a4;
    v5 = *((_OWORD *)a4 + 2);
    v12 = v4;
    *(_QWORD *)&v4 = a4[6];
    v13 = v5;
    v14 = v4;
LABEL_4:
    v9 = (unsigned __int16)v14;
    LOWORD(v14) = v14 + 1;
    return RegUtilIterateThroughKeys(
             a1,
             off_180016DF8[v9],
             a3,
             (int (*)(struct ATL::CRegKey *, const unsigned __int16 *, const unsigned __int16 *, void *))NDFRegistryInitKeyCallback,
             &v11);
  }
  v6 = *((_WORD *)a4 + 24) < 2u;
  v7 = *((_OWORD *)a4 + 1);
  v11 = *(_OWORD *)a4;
  v8 = *((_OWORD *)a4 + 2);
  v12 = v7;
  *(_QWORD *)&v7 = a4[6];
  v13 = v8;
  v14 = v7;
  if ( v6 )
    goto LABEL_4;
  return LoadHelperClass((struct ATL::CRegKey *)a1, a2, a3, (const unsigned __int16 **)&v11);
}

```

## disassembly

```asm
0x180008460  push    rbp
0x180008462  mov     rbp, rsp
0x180008465  sub     rsp, 70h
0x180008469  cmp     word ptr [r9+30h], 0
0x18000846f  mov     r10, rcx
0x180008472  jnz     short loc_18000849F
0x180008474  mov     [r9+20h], rdx
0x180008478  movups  xmm0, xmmword ptr [r9]
0x18000847c  movups  xmm1, xmmword ptr [r9+10h]
0x180008481  movups  [rbp+var_40], xmm0
0x180008485  movups  xmm0, xmmword ptr [r9+20h]
0x18000848a  movups  [rbp+var_30], xmm1
0x18000848e  movsd   xmm1, qword ptr [r9+30h]
0x180008494  movups  [rbp+var_20], xmm0
0x180008498  movsd   [rbp+var_10], xmm1
0x18000849d  jmp     short loc_1800084CC
0x18000849f  cmp     word ptr [r9+30h], 2
0x1800084a5  movups  xmm0, xmmword ptr [r9]
0x1800084a9  movups  xmm1, xmmword ptr [r9+10h]
0x1800084ae  movups  [rbp+var_40], xmm0
0x1800084b2  movups  xmm0, xmmword ptr [r9+20h]
0x1800084b7  movups  [rbp+var_30], xmm1
0x1800084bb  movsd   xmm1, qword ptr [r9+30h]
0x1800084c1  movups  [rbp+var_20], xmm0
0x1800084c5  movsd   [rbp+var_10], xmm1
0x1800084ca  jnb     short loc_1800084FE
0x1800084cc  movzx   ecx, word ptr [rbp+var_10]
0x1800084d0  lea     rdx, off_180016DF8; "HostDLLs"
0x1800084d7  mov     eax, ecx
0x1800084d9  lea     r9, ?NDFRegistryInitKeyCallback@@YAJAEAVCRegKey@ATL@@PEBG1PEAX@Z; int (*)(struct ATL::CRegKey *, const unsigned __int16 *, const unsigned __int16 *, void *)
0x1800084e0  inc     cx
0x1800084e3  mov     word ptr [rbp+var_10], cx
0x1800084e7  lea     rcx, [rbp+var_40]
0x1800084eb  mov     [rsp+70h+var_50], rcx; void *
0x1800084f0  mov     rcx, r10; struct ATL::CRegKey *
0x1800084f3  mov     rdx, [rdx+rax*8]; unsigned __int16 *
0x1800084f7  call    ?RegUtilIterateThroughKeys@@YAJAEAVCRegKey@ATL@@PEBG1P6AJ011PEAX@Z2@Z; RegUtilIterateThroughKeys(ATL::CRegKey &,ushort const *,ushort const *,long (*)(ATL::CRegKey &,ushort const *,ushort const *,void *),void *)
0x1800084fc  jmp     short loc_180008507
0x1800084fe  lea     r9, [rbp+var_40]; void *
0x180008502  call    ?LoadHelperClass@@YAJAEAVCRegKey@ATL@@PEBG1PEAX@Z; LoadHelperClass(ATL::CRegKey &,ushort const *,ushort const *,void *)
0x180008507  add     rsp, 70h
0x18000850b  pop     rbp
0x18000850c  retn
```
