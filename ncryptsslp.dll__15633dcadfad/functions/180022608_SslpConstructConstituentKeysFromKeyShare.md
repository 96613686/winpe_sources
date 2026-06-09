# SslpConstructConstituentKeysFromKeyShare

- ea: `0x180022608`
- end: `0x18002299c`
- name: `SslpConstructConstituentKeysFromKeyShare`
- size: `916`
- prototype: `__int64 __fastcall(__int64, __int64, int, const wchar_t *, _QWORD *, _DWORD *, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800234b0`

## callees

- `0x180003ef0`
- `0x180007940`
- `0x18000b654`
- `0x1800185e0`
- `0x180022608`
- `0x180023314`
- `0x1800233a8`
- `0x180024fb0`
- `0x180025660`

## string_xrefs

- `0x1800226a2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x1800226db`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`
- `0x180022963`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlshybrid.c`

## pseudocode

```c
__int64 __fastcall SslpConstructConstituentKeysFromKeyShare(
        __int64 a1,
        __int64 a2,
        int a3,
        const wchar_t *a4,
        _QWORD *a5,
        _DWORD *a6,
        _QWORD *a7,
        unsigned int *a8)
{
  unsigned __int16 v11; // bp
  int HybridKeyConstituentKeyIndices; // eax
  unsigned int v13; // edi
  __int64 v14; // r9
  __int64 v15; // rcx
  int v16; // r15d
  __int64 HybridKeyGroup; // rax
  __int64 v18; // rcx
  unsigned int v20; // edx
  unsigned int v21; // eax
  unsigned int v22; // ebp
  int v23; // ebx
  int v24; // edx
  _DWORD *v25; // rax
  _DWORD *v26; // r14
  __int64 v27; // rcx
  __int64 v28; // r9
  unsigned int v29; // r15d
  _DWORD *v30; // rax
  _DWORD *v31; // rsi
  unsigned int v32; // ecx
  void *v33; // rdx
  unsigned int v34; // eax
  __int64 v35; // rbx
  char *v36; // rcx
  _DWORD *v37; // rax
  int v38; // edx
  unsigned __int16 v39; // [rsp+20h] [rbp-88h]
  __int16 v40; // [rsp+22h] [rbp-86h]
  int v41; // [rsp+24h] [rbp-84h] BYREF
  int v42; // [rsp+28h] [rbp-80h] BYREF
  unsigned int v43; // [rsp+2Ch] [rbp-7Ch]
  int v44; // [rsp+30h] [rbp-78h]
  int v45; // [rsp+34h] [rbp-74h]
  unsigned int v46; // [rsp+38h] [rbp-70h]
  int v47; // [rsp+3Ch] [rbp-6Ch]
  unsigned int v48; // [rsp+40h] [rbp-68h]
  size_t Size; // [rsp+48h] [rbp-60h]
  void *Src; // [rsp+50h] [rbp-58h]
  char v51; // [rsp+B8h] [rbp+10h]
  unsigned int v52; // [rsp+B8h] [rbp+10h]

  v41 = 0;
  v42 = 0;
  v11 = a1;
  if ( !a2 || !a4 || !a5 || !a6 || !a7 || !a8 )
  {
    v26 = 0;
    v13 = -2146893785;
    v27 = 2148073511LL;
    v28 = 955;
    goto LABEL_32;
  }
  HybridKeyConstituentKeyIndices = SslpGetHybridKeyConstituentKeyIndices(a1, &v41, &v42);
  v13 = HybridKeyConstituentKeyIndices;
  if ( HybridKeyConstituentKeyIndices >= 0 )
  {
    v16 = wcscmp(a4, L"TLS_KEM_CIPHERTEXT");
    HybridKeyGroup = SslpGetHybridKeyGroup(v11);
    v18 = HybridKeyGroup;
    if ( !HybridKeyGroup )
    {
      DebugTraceError(2148073513LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", 975);
      return 2148073513LL;
    }
    v20 = *(_DWORD *)(HybridKeyGroup + 44);
    v21 = *(_DWORD *)(HybridKeyGroup + 56);
    v22 = v20;
    if ( !v16 )
      v22 = v21;
    v46 = v20;
    v48 = v21;
    if ( !v22 || (v23 = *(_DWORD *)(v18 + 12)) == 0 || a3 != v23 + v22 )
    {
      v13 = -2146893819;
      v14 = 992;
      v15 = 2148073477LL;
      goto LABEL_9;
    }
    v24 = *(_DWORD *)(v18 + 8);
    v39 = *(_WORD *)(v18 + 4);
    v51 = *(_BYTE *)(v18 + 16);
    v45 = *(_DWORD *)(v18 + 28);
    Src = *(void **)(v18 + 32);
    v43 = *(_DWORD *)(v18 + 40);
    v40 = *(_WORD *)(v18 + 48);
    v47 = *(_DWORD *)(v18 + 52);
    v44 = v24;
    Size = (unsigned int)(2 * v24 + 8);
    v25 = (_DWORD *)SafeAllocaAllocateFromHeap(Size);
    v26 = v25;
    if ( !v25 )
    {
      v13 = -2146893810;
      v27 = 2148073486LL;
      v28 = 1016;
      goto LABEL_32;
    }
    memset(v25, 0, Size);
    *v26 = v39;
    v26[1] = v44;
    if ( v51 && *(_BYTE *)((v41 != 0 ? v22 : 0) + a2) != 4 )
    {
      v13 = -2146893819;
      v27 = 2148073477LL;
      v28 = 1033;
      goto LABEL_32;
    }
    memmove(
      v26 + 2,
      (const void *)(a2 + (v41 != 0 ? v22 : 0) + (unsigned __int64)(v51 != 0)),
      v23 - (unsigned int)(v51 != 0));
    v52 = v42 != 0 ? v23 : 0;
    if ( v16 )
    {
      v29 = v22 + v43 + 12;
      v30 = (_DWORD *)SafeAllocaAllocateFromHeap(v29);
      v31 = v30;
      if ( !v30 )
      {
        v13 = -2146893810;
        v27 = 2148073486LL;
        v28 = 1054;
        goto LABEL_32;
      }
      memset(v30, 0, v29);
      v32 = v46;
      v33 = Src;
      *v31 = v45;
      v34 = v43;
      v31[2] = v32;
      v31[1] = v34;
      v35 = v34;
      memmove(v31 + 3, v33, v34);
      v36 = (char *)v31 + v35 + 12;
LABEL_29:
      memmove(v36, (const void *)(a2 + v52), v22);
      v38 = v44;
      *a5 = v26;
      *a7 = v31;
      *a6 = 2 * v38 + 8;
      *a8 = v29;
      return v13;
    }
    v29 = v22 + 12;
    v37 = (_DWORD *)SafeAllocaAllocateFromHeap(v22 + 12);
    v31 = v37;
    if ( v37 )
    {
      memset(v37, 0, v22 + 12);
      v36 = (char *)(v31 + 3);
      *v31 = v47;
      *((_WORD *)v31 + 2) = v40;
      v31[2] = v48;
      goto LABEL_29;
    }
    v13 = -2146893810;
    v27 = 2148073486LL;
    v28 = 1080;
LABEL_32:
    DebugTraceError(v27, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", v28);
    if ( v26 )
      MSCryptFree(v26);
    return v13;
  }
  v14 = 962;
  v15 = (unsigned int)HybridKeyConstituentKeyIndices;
LABEL_9:
  DebugTraceError(v15, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlshybrid.c", v14);
  return v13;
}

```

## disassembly

```asm
0x180022608  push    rbx
0x18002260a  push    rbp
0x18002260b  push    rsi
0x18002260c  push    rdi
0x18002260d  push    r12
0x18002260f  push    r13
0x180022611  push    r14
0x180022613  push    r15
0x180022615  sub     rsp, 68h
0x180022619  xor     eax, eax
0x18002261b  mov     rbx, r9
0x18002261e  mov     [rsp+0A8h+var_84], eax
0x180022622  mov     r14d, r8d
0x180022625  mov     [rsp+0A8h+var_80], eax
0x180022629  mov     r12, rdx
0x18002262c  movzx   ebp, cx
0x18002262f  mov     esi, eax
0x180022631  test    rdx, rdx
0x180022634  jz      loc_180022949
0x18002263a  test    rbx, rbx
0x18002263d  jz      loc_180022949
0x180022643  mov     r13, [rsp+0A8h+arg_20]
0x18002264b  test    r13, r13
0x18002264e  jz      loc_180022949
0x180022654  cmp     [rsp+0A8h+arg_28], rax
0x18002265c  jz      loc_180022949
0x180022662  cmp     [rsp+0A8h+arg_30], rax
0x18002266a  jz      loc_180022949
0x180022670  cmp     [rsp+0A8h+arg_38], rax
0x180022678  jz      loc_180022949
0x18002267e  lea     r8, [rsp+0A8h+var_80]
0x180022683  lea     rdx, [rsp+0A8h+var_84]
0x180022688  call    SslpGetHybridKeyConstituentKeyIndices
0x18002268d  mov     edi, eax
0x18002268f  test    eax, eax
0x180022691  jns     short loc_1800226B3
0x180022693  mov     r9d, 3C2h
0x180022699  mov     ecx, eax
0x18002269b  lea     rdx, aStatus_0; "status"
0x1800226a2  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800226a9  call    DebugTraceError
0x1800226ae  jmp     loc_180022989
0x1800226b3  lea     rdx, aTlsKemCipherte; "TLS_KEM_CIPHERTEXT"
0x1800226ba  mov     rcx, rbx; String1
0x1800226bd  call    wcscmp
0x1800226c2  movzx   ecx, bp
0x1800226c5  mov     r15d, eax
0x1800226c8  call    SslpGetHybridKeyGroup
0x1800226cd  mov     rcx, rax
0x1800226d0  test    rax, rax
0x1800226d3  jnz     short loc_1800226FD
0x1800226d5  mov     r9d, 3CFh
0x1800226db  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800226e2  lea     rdx, aStatus_0; "status"
0x1800226e9  mov     ecx, 80090029h
0x1800226ee  call    DebugTraceError
0x1800226f3  mov     eax, 80090029h
0x1800226f8  jmp     loc_18002298B
0x1800226fd  mov     edx, [rax+2Ch]
0x180022700  test    r15d, r15d
0x180022703  mov     eax, [rax+38h]
0x180022706  mov     ebp, edx
0x180022708  cmovz   ebp, eax
0x18002270b  mov     [rsp+0A8h+var_70], edx
0x18002270f  mov     [rsp+0A8h+var_68], eax
0x180022713  test    ebp, ebp
0x180022715  jz      loc_180022934
0x18002271b  mov     ebx, [rcx+0Ch]
0x18002271e  test    ebx, ebx
0x180022720  jz      loc_180022934
0x180022726  lea     eax, [rbx+rbp]
0x180022729  cmp     r14d, eax
0x18002272c  jnz     loc_180022934
0x180022732  movzx   eax, word ptr [rcx+4]
0x180022736  mov     edx, [rcx+8]
0x180022739  mov     [rsp+0A8h+var_88], ax
0x18002273e  mov     al, [rcx+10h]
0x180022741  mov     byte ptr [rsp+0A8h+arg_8], al
0x180022748  mov     eax, [rcx+1Ch]
0x18002274b  mov     [rsp+0A8h+var_74], eax
0x18002274f  mov     rax, [rcx+20h]
0x180022753  mov     [rsp+0A8h+Src], rax
0x180022758  mov     eax, [rcx+28h]
0x18002275b  mov     dword ptr [rsp+0A8h+var_7C], eax
0x18002275f  movzx   eax, word ptr [rcx+30h]
0x180022763  mov     [rsp+0A8h+var_86], ax
0x180022768  mov     eax, [rcx+34h]
0x18002276b  mov     [rsp+0A8h+var_6C], eax
0x18002276f  lea     eax, ds:8[rdx*2]
0x180022776  mov     ecx, eax
0x180022778  mov     dword ptr [rsp+0A8h+var_7C+4], edx
0x18002277c  mov     [rsp+0A8h+Size], rax
0x180022781  call    SafeAllocaAllocateFromHeap
0x180022786  mov     r14, rax
0x180022789  test    rax, rax
0x18002278c  jnz     short loc_1800227A3
0x18002278e  mov     edi, 8009000Eh
0x180022793  mov     ecx, 8009000Eh
0x180022798  mov     r9d, 3F8h
0x18002279e  jmp     loc_18002295C
0x1800227a3  mov     r8, [rsp+0A8h+Size]; Size
0x1800227a8  xor     edx, edx; Val
0x1800227aa  mov     rcx, r14; void *
0x1800227ad  call    memset
0x1800227b2  movzx   eax, [rsp+0A8h+var_88]
0x1800227b7  xor     edx, edx
0x1800227b9  mov     r8b, byte ptr [rsp+0A8h+arg_8]
0x1800227c1  mov     [r14], eax
0x1800227c4  test    r8b, r8b
0x1800227c7  mov     eax, dword ptr [rsp+0A8h+var_7C+4]
0x1800227cb  setnz   dl
0x1800227ce  mov     [r14+4], eax
0x1800227d2  mov     eax, [rsp+0A8h+var_84]
0x1800227d6  neg     eax
0x1800227d8  sbb     ecx, ecx
0x1800227da  and     ecx, ebp
0x1800227dc  mov     r9d, ecx
0x1800227df  test    r8b, r8b
0x1800227e2  jz      short loc_180022800
0x1800227e4  cmp     byte ptr [rcx+r12], 4
0x1800227e9  jz      short loc_180022800
0x1800227eb  mov     edi, 80090005h
0x1800227f0  mov     ecx, 80090005h
0x1800227f5  mov     r9d, 409h
0x1800227fb  jmp     loc_18002295C
0x180022800  mov     r8d, ebx
0x180022803  lea     rcx, [r14+8]; void *
0x180022807  sub     r8d, edx; Size
0x18002280a  mov     edx, edx
0x18002280c  add     rdx, r9
0x18002280f  add     rdx, r12; Src
0x180022812  call    memmove
0x180022817  mov     eax, [rsp+0A8h+var_80]
0x18002281b  neg     eax
0x18002281d  sbb     eax, eax
0x18002281f  and     eax, ebx
0x180022821  mov     [rsp+0A8h+arg_8], eax
0x180022828  test    r15d, r15d
0x18002282b  jz      short loc_18002289E
0x18002282d  mov     r15d, dword ptr [rsp+0A8h+var_7C]
0x180022832  add     r15d, 0Ch
0x180022836  add     r15d, ebp
0x180022839  mov     ecx, r15d
0x18002283c  mov     ebx, r15d
0x18002283f  call    SafeAllocaAllocateFromHeap
0x180022844  mov     rsi, rax
0x180022847  test    rax, rax
0x18002284a  jnz     short loc_180022861
0x18002284c  mov     edi, 8009000Eh
0x180022851  mov     ecx, 8009000Eh
0x180022856  mov     r9d, 41Eh
0x18002285c  jmp     loc_18002295C
0x180022861  mov     r8, rbx; Size
0x180022864  xor     edx, edx; Val
0x180022866  mov     rcx, rsi; void *
0x180022869  call    memset
0x18002286e  mov     eax, [rsp+0A8h+var_74]
0x180022872  mov     ecx, [rsp+0A8h+var_70]
0x180022876  mov     rdx, [rsp+0A8h+Src]; Src
0x18002287b  mov     [rsi], eax
0x18002287d  mov     eax, dword ptr [rsp+0A8h+var_7C]
0x180022881  mov     [rsi+8], ecx
0x180022884  mov     r8d, eax; Size
0x180022887  lea     rcx, [rsi+0Ch]; void *
0x18002288b  mov     [rsi+4], eax
0x18002288e  mov     ebx, eax
0x180022890  call    memmove
0x180022895  lea     rcx, [rbx+0Ch]
0x180022899  add     rcx, rsi
0x18002289c  jmp     short loc_1800228F1
0x18002289e  lea     r15d, [rbp+0Ch]
0x1800228a2  mov     ecx, r15d
0x1800228a5  mov     ebx, r15d
0x1800228a8  call    SafeAllocaAllocateFromHeap
0x1800228ad  mov     rsi, rax
0x1800228b0  test    rax, rax
0x1800228b3  jnz     short loc_1800228CA
0x1800228b5  mov     edi, 8009000Eh
0x1800228ba  mov     ecx, 8009000Eh
0x1800228bf  mov     r9d, 438h
0x1800228c5  jmp     loc_18002295C
0x1800228ca  mov     r8, rbx; Size
0x1800228cd  xor     edx, edx; Val
0x1800228cf  mov     rcx, rsi; void *
0x1800228d2  call    memset
0x1800228d7  mov     eax, [rsp+0A8h+var_6C]
0x1800228db  lea     rcx, [rsi+0Ch]; void *
0x1800228df  mov     [rsi], eax
0x1800228e1  movzx   eax, [rsp+0A8h+var_86]
0x1800228e6  mov     [rsi+4], ax
0x1800228ea  mov     eax, [rsp+0A8h+var_68]
0x1800228ee  mov     [rsi+8], eax
0x1800228f1  mov     edx, [rsp+0A8h+arg_8]
0x1800228f8  add     rdx, r12; Src
0x1800228fb  mov     r8d, ebp; Size
0x1800228fe  call    memmove
0x180022903  mov     rax, [rsp+0A8h+arg_30]
0x18002290b  mov     edx, dword ptr [rsp+0A8h+var_7C+4]
0x18002290f  mov     [r13+0], r14
0x180022913  mov     [rax], rsi
0x180022916  mov     rax, [rsp+0A8h+arg_28]
0x18002291e  lea     ecx, ds:8[rdx*2]
0x180022925  mov     [rax], ecx
0x180022927  mov     rax, [rsp+0A8h+arg_38]
0x18002292f  mov     [rax], r15d
0x180022932  jmp     short loc_180022989
0x180022934  mov     edi, 80090005h
0x180022939  mov     r9d, 3E0h
0x18002293f  mov     ecx, 80090005h
0x180022944  jmp     loc_18002269B
0x180022949  mov     r14, rax
0x18002294c  mov     edi, 80090027h
0x180022951  mov     ecx, 80090027h
0x180022956  mov     r9d, 3BBh
0x18002295c  lea     rdx, aStatus_0; "status"
0x180022963  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002296a  call    DebugTraceError
0x18002296f  test    r14, r14
0x180022972  jz      short loc_18002297C
0x180022974  mov     rcx, r14
0x180022977  call    MSCryptFree
0x18002297c  test    rsi, rsi
0x18002297f  jz      short loc_180022989
0x180022981  mov     rcx, rsi
0x180022984  call    MSCryptFree
0x180022989  mov     eax, edi
0x18002298b  add     rsp, 68h
0x18002298f  pop     r15
0x180022991  pop     r14
0x180022993  pop     r13
0x180022995  pop     r12
0x180022997  pop     rdi
0x180022998  pop     rsi
0x180022999  pop     rbp
0x18002299a  pop     rbx
0x18002299b  retn
```
