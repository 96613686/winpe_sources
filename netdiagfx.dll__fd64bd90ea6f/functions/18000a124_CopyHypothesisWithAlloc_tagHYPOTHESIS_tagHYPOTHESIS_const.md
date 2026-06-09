# CopyHypothesisWithAlloc(tagHYPOTHESIS *,tagHYPOTHESIS const *)

- ea: `0x18000a124`
- end: `0x18000a2eb`
- name: `?CopyHypothesisWithAlloc@@YAJPEAUtagHYPOTHESIS@@PEBU1@@Z`
- size: `455`
- prototype: `__int64 __fastcall(struct tagHYPOTHESIS *, const struct tagHYPOTHESIS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bfcc`

## callees

- `0x180006fa0`
- `0x180007014`
- `0x180008ccc`
- `0x180009f54`
- `0x18000a124`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a195`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a1f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a235`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a195`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a1f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a235`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CopyHypothesisWithAlloc(struct tagHYPOTHESIS *a1, const struct tagHYPOTHESIS *a2)
{
  const unsigned __int16 *pwszClassName; // rsi
  int v5; // ebx
  unsigned __int64 v6; // rbx
  unsigned __int16 *v7; // rax
  const unsigned __int16 *pwszDescription; // rsi
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  _BYTE *v11; // rdx
  __int64 i; // rcx
  ULONG celt; // eax
  __int64 v14; // rsi
  __int128 v15; // xmm1
  __int128 *v17; // [rsp+20h] [rbp-30h] BYREF
  __int64 v18; // [rsp+28h] [rbp-28h]
  __int128 v19; // [rsp+30h] [rbp-20h] BYREF
  __int128 v20; // [rsp+40h] [rbp-10h]
  unsigned __int64 v21; // [rsp+78h] [rbp+28h] BYREF

  pwszClassName = a2->pwszClassName;
  v17 = &v19;
  v18 = 1;
  v19 = 0;
  v20 = 0;
  if ( !pwszClassName )
  {
    v5 = -2147024809;
    goto LABEL_23;
  }
  v21 = 0;
  v5 = StringCchLengthW(pwszClassName, 0xFFFEu, &v21);
  if ( v5 >= 0 )
  {
    v6 = v21;
    v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v21 + 2);
    *(_QWORD *)&v19 = v7;
    if ( v7 )
    {
      v5 = StringCchCopyW(v7, v6 + 1, pwszClassName);
      if ( v5 < 0 )
        goto LABEL_23;
      pwszDescription = a2->pwszDescription;
      if ( pwszDescription )
      {
        v21 = 0;
        v5 = StringCchLengthW(pwszDescription, 0xFFFEu, &v21);
        if ( v5 >= 0 )
        {
          v9 = v21;
          v10 = (unsigned __int16 *)CoTaskMemAlloc(2 * v21 + 2);
          *((_QWORD *)&v19 + 1) = v10;
          if ( v10 )
            v5 = StringCchCopyW(v10, v9 + 1, pwszDescription);
          else
            v5 = -2147024882;
        }
        if ( v5 < 0 )
          goto LABEL_23;
      }
      if ( !a2->celt )
        goto LABEL_20;
      *((_QWORD *)&v20 + 1) = CoTaskMemAlloc(144LL * a2->celt);
      v11 = (_BYTE *)*((_QWORD *)&v20 + 1);
      if ( *((_QWORD *)&v20 + 1) )
      {
        for ( i = 144LL * a2->celt; i; --i )
          *v11++ = 0;
        celt = a2->celt;
        v14 = 0;
        if ( celt )
        {
          while ( v5 >= 0 )
          {
            v5 = CopyHelperAttribute(
                   (struct tagHELPER_ATTRIBUTE *)(*((_QWORD *)&v20 + 1) + 144 * v14),
                   &a2->rgAttributes[v14]);
            celt = a2->celt;
            v14 = (unsigned int)(v14 + 1);
            if ( (unsigned int)v14 >= celt )
            {
              if ( v5 < 0 )
                goto LABEL_23;
              goto LABEL_19;
            }
          }
          goto LABEL_23;
        }
LABEL_19:
        LODWORD(v20) = celt;
LABEL_20:
        v17 = 0;
        v15 = v20;
        v18 = 0;
        *(_OWORD *)&a1->pwszClassName = v19;
        *(_OWORD *)&a1->celt = v15;
        goto LABEL_23;
      }
    }
    v5 = -2147024882;
  }
LABEL_23:
  TNDFDeallocator<tagHYPOTHESIS *,&void FreeHypothesesAlt(tagHYPOTHESIS *,unsigned long,int)>::~TNDFDeallocator<tagHYPOTHESIS *,&void FreeHypothesesAlt(tagHYPOTHESIS *,unsigned long,int)>(&v17);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a124  mov     [rsp-18h+arg_0], rbx
0x18000a129  mov     [rsp-18h+arg_10], rsi
0x18000a12e  push    rbp
0x18000a12f  push    rdi
0x18000a130  push    r14
0x18000a132  mov     rbp, rsp
0x18000a135  sub     rsp, 50h
0x18000a139  mov     rsi, [rdx]
0x18000a13c  lea     rax, [rbp+var_20]
0x18000a140  mov     [rbp+var_30], rax
0x18000a144  xorps   xmm0, xmm0
0x18000a147  mov     [rbp+var_28], 1
0x18000a14f  mov     rdi, rdx
0x18000a152  mov     r14, rcx
0x18000a155  movups  [rbp+var_20], xmm0
0x18000a159  movups  [rbp+var_10], xmm0
0x18000a15d  test    rsi, rsi
0x18000a160  jz      loc_18000A2C6
0x18000a166  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x18000a16a  mov     [rbp+arg_8], 0
0x18000a172  mov     edx, 0FFFEh; unsigned __int64
0x18000a177  mov     rcx, rsi; unsigned __int16 *
0x18000a17a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000a17f  mov     ebx, eax
0x18000a181  test    eax, eax
0x18000a183  js      loc_18000A2CB
0x18000a189  mov     rbx, [rbp+arg_8]
0x18000a18d  lea     rcx, ds:2[rbx*2]; cb
0x18000a195  call    cs:__imp_CoTaskMemAlloc
0x18000a19b  mov     qword ptr [rbp+var_20], rax
0x18000a19f  test    rax, rax
0x18000a1a2  jz      loc_18000A2BF
0x18000a1a8  lea     rdx, [rbx+1]; unsigned __int64
0x18000a1ac  mov     r8, rsi; unsigned __int16 *
0x18000a1af  mov     rcx, rax; unsigned __int16 *
0x18000a1b2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a1b7  mov     ebx, eax
0x18000a1b9  test    eax, eax
0x18000a1bb  js      loc_18000A2CB
0x18000a1c1  mov     rsi, [rdi+8]
0x18000a1c5  test    rsi, rsi
0x18000a1c8  jz      short loc_18000A224
0x18000a1ca  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x18000a1ce  mov     [rbp+arg_8], 0
0x18000a1d6  mov     edx, 0FFFEh; unsigned __int64
0x18000a1db  mov     rcx, rsi; unsigned __int16 *
0x18000a1de  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000a1e3  mov     ebx, eax
0x18000a1e5  test    eax, eax
0x18000a1e7  js      short loc_18000A21C
0x18000a1e9  mov     rbx, [rbp+arg_8]
0x18000a1ed  lea     rcx, ds:2[rbx*2]; cb
0x18000a1f5  call    cs:__imp_CoTaskMemAlloc
0x18000a1fb  mov     qword ptr [rbp+var_20+8], rax
0x18000a1ff  test    rax, rax
0x18000a202  jnz     short loc_18000A20B
0x18000a204  mov     ebx, 8007000Eh
0x18000a209  jmp     short loc_18000A21C
0x18000a20b  lea     rdx, [rbx+1]; unsigned __int64
0x18000a20f  mov     r8, rsi; unsigned __int16 *
0x18000a212  mov     rcx, rax; unsigned __int16 *
0x18000a215  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a21a  mov     ebx, eax
0x18000a21c  test    ebx, ebx
0x18000a21e  js      loc_18000A2CB
0x18000a224  cmp     dword ptr [rdi+10h], 0
0x18000a228  jz      short loc_18000A29C
0x18000a22a  mov     eax, [rdi+10h]
0x18000a22d  lea     rcx, [rax+rax*8]
0x18000a231  shl     rcx, 4; cb
0x18000a235  call    cs:__imp_CoTaskMemAlloc
0x18000a23b  mov     qword ptr [rbp+var_10+8], rax
0x18000a23f  mov     rdx, rax
0x18000a242  test    rax, rax
0x18000a245  jz      short loc_18000A2BF
0x18000a247  mov     eax, [rdi+10h]
0x18000a24a  lea     rcx, [rax+rax*8]
0x18000a24e  shl     rcx, 4
0x18000a252  test    rcx, rcx
0x18000a255  jz      short loc_18000A263
0x18000a257  mov     byte ptr [rdx], 0
0x18000a25a  inc     rdx
0x18000a25d  sub     rcx, 1
0x18000a261  jnz     short loc_18000A257
0x18000a263  mov     eax, [rdi+10h]
0x18000a266  xor     esi, esi
0x18000a268  test    eax, eax
0x18000a26a  jz      short loc_18000A299
0x18000a26c  test    ebx, ebx
0x18000a26e  js      short loc_18000A2CB
0x18000a270  mov     rdx, [rdi+18h]
0x18000a274  lea     rcx, [rsi+rsi*8]
0x18000a278  shl     rcx, 4
0x18000a27c  add     rdx, rcx; struct tagHELPER_ATTRIBUTE *
0x18000a27f  add     rcx, qword ptr [rbp+var_10+8]; struct tagHELPER_ATTRIBUTE *
0x18000a283  call    ?CopyHelperAttribute@@YAJPEAUtagHELPER_ATTRIBUTE@@PEBU1@@Z; CopyHelperAttribute(tagHELPER_ATTRIBUTE *,tagHELPER_ATTRIBUTE const *)
0x18000a288  mov     ebx, eax
0x18000a28a  mov     ecx, eax
0x18000a28c  mov     eax, [rdi+10h]
0x18000a28f  inc     esi
0x18000a291  cmp     esi, eax
0x18000a293  jb      short loc_18000A26C
0x18000a295  test    ecx, ecx
0x18000a297  js      short loc_18000A2CB
0x18000a299  mov     dword ptr [rbp+var_10], eax
0x18000a29c  movups  xmm0, [rbp+var_20]
0x18000a2a0  mov     [rbp+var_30], 0
0x18000a2a8  movups  xmm1, [rbp+var_10]
0x18000a2ac  mov     [rbp+var_28], 0
0x18000a2b4  movups  xmmword ptr [r14], xmm0
0x18000a2b8  movups  xmmword ptr [r14+10h], xmm1
0x18000a2bd  jmp     short loc_18000A2CB
0x18000a2bf  mov     ebx, 8007000Eh
0x18000a2c4  jmp     short loc_18000A2CB
0x18000a2c6  mov     ebx, 80070057h
0x18000a2cb  lea     rcx, [rbp+var_30]
0x18000a2cf  call    ??1?$TNDFDeallocator@PEAUtagHYPOTHESIS@@$1?FreeHypothesesAlt@@YAXPEAU1@KH@Z@@QEAA@XZ; TNDFDeallocator<tagHYPOTHESIS *,&FreeHypothesesAlt(tagHYPOTHESIS *,ulong,int)>::~TNDFDeallocator<tagHYPOTHESIS *,&FreeHypothesesAlt(tagHYPOTHESIS *,ulong,int)>(void)
0x18000a2d4  lea     r11, [rsp+50h+var_s0]
0x18000a2d9  mov     eax, ebx
0x18000a2db  mov     rbx, [r11+20h]
0x18000a2df  mov     rsi, [r11+30h]
0x18000a2e3  mov     rsp, r11
0x18000a2e6  pop     r14
0x18000a2e8  pop     rdi
0x18000a2e9  pop     rbp
0x18000a2ea  retn
```
