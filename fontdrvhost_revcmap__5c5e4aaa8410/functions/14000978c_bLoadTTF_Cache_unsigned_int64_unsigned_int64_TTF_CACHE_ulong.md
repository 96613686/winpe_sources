# bLoadTTF_Cache(unsigned __int64,unsigned __int64 *,_TTF_CACHE *,ulong)

- ea: `0x14000978c`
- end: `0x140009995`
- name: `?bLoadTTF_Cache@@YAH_KPEA_KPEAU_TTF_CACHE@@K@Z`
- size: `521`
- prototype: `int(unsigned __int64, unsigned __int64 *, struct _TTF_CACHE *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140007f98`

## callees

- `0x14000978c`
- `0x14005af90`
- `0x14007680c`
- `0x140076eea`
- `0x1400928c0`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x140009978`
- `KERNEL32!GlobalFree` at `0x14000998d`
- `KERNEL32!GlobalFree` at `0x140009978`
- `KERNEL32!GlobalFree` at `0x14000998d`
- `KERNEL32!GlobalAlloc` at `0x1400097d9`
- `KERNEL32!GlobalAlloc` at `0x14000993a`
- `KERNEL32!GlobalAlloc` at `0x1400097d9`
- `KERNEL32!GlobalAlloc` at `0x14000993a`

## pseudocode

```c
__int64 __fastcall bLoadTTF_Cache(__int64 a1, HGLOBAL *a2, struct _TTF_CACHE *a3)
{
  _DWORD *v5; // r13
  char *v6; // rax
  char *v7; // rbx
  struct _IFIMETRICS *v8; // rdi
  unsigned int v9; // esi
  __int64 v10; // rdx
  _OWORD *v11; // rcx
  _OWORD *v12; // rax
  unsigned int (__fastcall *v13)(struct _TT_FONTFILE *, unsigned int); // rax

  *a2 = 0;
  v5 = (_DWORD *)((char *)a3 + 328);
  if ( *((_DWORD *)a3 + 82) < 0xFFFFFE48 )
  {
    v6 = (char *)GlobalAlloc(0, (unsigned int)(*((_DWORD *)a3 + 82) + 440));
    v7 = v6;
    if ( v6 )
    {
      v8 = 0;
      v9 = 1;
      *a2 = v6;
      memset_0(v6, 0, 0x1B8u);
      *((_QWORD *)v7 + 7) = a1;
      v10 = 2;
      if ( *((_DWORD *)a3 + 66) == 2 )
      {
        v8 = (struct _IFIMETRICS *)GlobalAlloc(0, (*v5 + 7) & 0xFFFFFFF8);
        if ( !v8 )
        {
          v9 = 0;
          if ( *a2 )
          {
            GlobalFree(*a2);
            *a2 = 0;
          }
          return v9;
        }
        v10 = 2;
      }
      v11 = v7 + 112;
      v12 = (_OWORD *)((char *)a3 + 4);
      do
      {
        *v11 = *v12;
        v11[1] = v12[1];
        v11[2] = v12[2];
        v11[3] = v12[3];
        v11[4] = v12[4];
        v11[5] = v12[5];
        v11[6] = v12[6];
        v11[7] = v12[7];
        v11 += 8;
        v12 += 8;
        --v10;
      }
      while ( v10 );
      *v11 = *v12;
      v11[1] = v12[1];
      v11[2] = v12[2];
      v11[3] = v12[3];
      *((_DWORD *)v11 + 16) = *((_DWORD *)v12 + 16);
      memcpy_0(v7 + 440, v5, (unsigned int)*v5);
      if ( !v8 )
      {
LABEL_14:
        *((_QWORD *)v7 + 13) = 0;
        return v9;
      }
      vCopy_IFIV((struct _IFIMETRICS *)(v7 + 440), v8);
      *((_QWORD *)v7 + 2) = v8;
      if ( *(_DWORD *)a3 )
      {
        if ( *(_DWORD *)a3 == 1 )
        {
          v13 = SearchGsubTable;
LABEL_10:
          *((_QWORD *)v7 + 1) = v13;
          goto LABEL_14;
        }
        if ( *(_DWORD *)a3 == 2 )
        {
          v13 = SearchMortTable;
          goto LABEL_10;
        }
      }
      v13 = SearchDummyTable;
      goto LABEL_10;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000978c  mov     [rsp+arg_18], r9d
0x140009791  mov     [rsp+arg_8], rdx
0x140009796  mov     [rsp+arg_0], rcx
0x14000979b  push    rbx
0x14000979c  push    rsi
0x14000979d  push    rdi
0x14000979e  push    r12
0x1400097a0  push    r13
0x1400097a2  push    r14
0x1400097a4  push    r15
0x1400097a6  sub     rsp, 20h
0x1400097aa  mov     r12d, r9d
0x1400097ad  mov     r15, r8
0x1400097b0  mov     r14, rdx
0x1400097b3  mov     qword ptr [rdx], 0
0x1400097ba  lea     r13, [r8+148h]
0x1400097c1  mov     eax, [r13+0]
0x1400097c5  add     eax, 1B8h
0x1400097ca  cmp     eax, 1B8h
0x1400097cf  jb      loc_140009957
0x1400097d5  mov     edx, eax; dwBytes
0x1400097d7  xor     ecx, ecx; uFlags
0x1400097d9  call    cs:__imp_GlobalAlloc
0x1400097df  mov     rbx, rax
0x1400097e2  test    rax, rax
0x1400097e5  jz      loc_140009957
0x1400097eb  xor     edi, edi
0x1400097ed  mov     [rsp+58h+arg_10], rdi
0x1400097f2  lea     esi, [rdi+1]
0x1400097f5  mov     [r14], rax
0x1400097f8  xor     edx, edx; Val
0x1400097fa  mov     r8d, 1B8h; Size
0x140009800  mov     rcx, rax; void *
0x140009803  call    memset_0
0x140009808  mov     rax, [rsp+58h+arg_0]
0x14000980d  mov     [rbx+38h], rax
0x140009811  lea     edx, [rdi+2]
0x140009814  cmp     [r15+108h], edx
0x14000981b  jz      loc_140009929
0x140009821  lea     rcx, [rbx+70h]
0x140009825  lea     rax, [r15+4]
0x140009829  mov     r8d, 80h
0x14000982f  movups  xmm0, xmmword ptr [rax]
0x140009832  movups  xmmword ptr [rcx], xmm0
0x140009835  movups  xmm1, xmmword ptr [rax+10h]
0x140009839  movups  xmmword ptr [rcx+10h], xmm1
0x14000983d  movups  xmm0, xmmword ptr [rax+20h]
0x140009841  movups  xmmword ptr [rcx+20h], xmm0
0x140009845  movups  xmm1, xmmword ptr [rax+30h]
0x140009849  movups  xmmword ptr [rcx+30h], xmm1
0x14000984d  movups  xmm0, xmmword ptr [rax+40h]
0x140009851  movups  xmmword ptr [rcx+40h], xmm0
0x140009855  movups  xmm1, xmmword ptr [rax+50h]
0x140009859  movups  xmmword ptr [rcx+50h], xmm1
0x14000985d  movups  xmm0, xmmword ptr [rax+60h]
0x140009861  movups  xmmword ptr [rcx+60h], xmm0
0x140009865  movups  xmm1, xmmword ptr [rax+70h]
0x140009869  movups  xmmword ptr [rcx+70h], xmm1
0x14000986d  add     rcx, r8
0x140009870  add     rax, r8
0x140009873  sub     rdx, 1
0x140009877  jnz     short loc_14000982F
0x140009879  movups  xmm0, xmmword ptr [rax]
0x14000987c  movups  xmmword ptr [rcx], xmm0
0x14000987f  movups  xmm1, xmmword ptr [rax+10h]
0x140009883  movups  xmmword ptr [rcx+10h], xmm1
0x140009887  movups  xmm0, xmmword ptr [rax+20h]
0x14000988b  movups  xmmword ptr [rcx+20h], xmm0
0x14000988f  movups  xmm1, xmmword ptr [rax+30h]
0x140009893  movups  xmmword ptr [rcx+30h], xmm1
0x140009897  mov     eax, [rax+40h]
0x14000989a  mov     [rcx+40h], eax
0x14000989d  lea     rcx, [rbx+1B8h]; void *
0x1400098a4  mov     r8d, [r13+0]; Size
0x1400098a8  mov     rdx, r13; Src
0x1400098ab  call    memcpy_0
0x1400098b0  test    rdi, rdi
0x1400098b3  jz      short loc_1400098F8
0x1400098b5  mov     rdx, rdi; struct _IFIMETRICS *
0x1400098b8  lea     rcx, [rbx+1B8h]; Src
0x1400098bf  call    ?vCopy_IFIV@@YAXPEAU_IFIMETRICS@@0@Z; vCopy_IFIV(_IFIMETRICS *,_IFIMETRICS *)
0x1400098c4  mov     [rbx+10h], rdi
0x1400098c8  mov     ecx, [r15]
0x1400098cb  test    ecx, ecx
0x1400098cd  jz      short loc_1400098EF
0x1400098cf  sub     ecx, 1
0x1400098d2  jnz     short loc_1400098E1
0x1400098d4  lea     rax, ?SearchGsubTable@@YAKPEAU_TT_FONTFILE@@K@Z; SearchGsubTable(_TT_FONTFILE *,ulong)
0x1400098db  mov     [rbx+8], rax
0x1400098df  jmp     short loc_1400098F8
0x1400098e1  cmp     ecx, 1
0x1400098e4  jnz     short loc_1400098EF
0x1400098e6  lea     rax, ?SearchMortTable@@YAKPEAU_TT_FONTFILE@@K@Z; SearchMortTable(_TT_FONTFILE *,ulong)
0x1400098ed  jmp     short loc_1400098DB
0x1400098ef  lea     rax, ?SearchDummyTable@@YAKPEAU_TT_FONTFILE@@K@Z; SearchDummyTable(_TT_FONTFILE *,ulong)
0x1400098f6  jmp     short loc_1400098DB
0x1400098f8  mov     qword ptr [rbx+68h], 0
0x140009900  jmp     short loc_140009913
0x140009902  xor     esi, esi
0x140009904  mov     r12d, [rsp+58h+arg_18]
0x140009909  mov     r14, [rsp+58h+arg_8]
0x14000990e  mov     rdi, [rsp+58h+arg_10]
0x140009913  test    esi, esi
0x140009915  jz      short loc_14000995F
0x140009917  mov     eax, esi
0x140009919  add     rsp, 20h
0x14000991d  pop     r15
0x14000991f  pop     r14
0x140009921  pop     r13
0x140009923  pop     r12
0x140009925  pop     rdi
0x140009926  pop     rsi
0x140009927  pop     rbx
0x140009928  retn
0x140009929  mov     edx, [r13+0]
0x14000992d  add     edx, 7
0x140009930  mov     eax, 0FFFFFFF8h
0x140009935  and     rdx, rax; dwBytes
0x140009938  xor     ecx, ecx; uFlags
0x14000993a  call    cs:__imp_GlobalAlloc
0x140009940  mov     rdi, rax
0x140009943  mov     [rsp+58h+arg_10], rax
0x140009948  test    rax, rax
0x14000994b  jz      short loc_14000995B
0x14000994d  mov     edx, 2
0x140009952  jmp     loc_140009821
0x140009957  xor     eax, eax
0x140009959  jmp     short loc_140009919
0x14000995b  xor     esi, esi
0x14000995d  jmp     short loc_140009970
0x14000995f  mov     edx, 1; iFaultMode
0x140009964  mov     ecx, r12d; ulFastCheckSum
0x140009967  call    EngFntCacheFault
0x14000996c  test    esi, esi
0x14000996e  jnz     short loc_140009917
0x140009970  mov     rcx, [r14]; hMem
0x140009973  test    rcx, rcx
0x140009976  jz      short loc_140009985
0x140009978  call    cs:__imp_GlobalFree
0x14000997e  mov     qword ptr [r14], 0
0x140009985  test    rdi, rdi
0x140009988  jz      short loc_140009917
0x14000998a  mov     rcx, rdi; hMem
0x14000998d  call    cs:__imp_GlobalFree
0x140009993  jmp     short loc_140009917
```
