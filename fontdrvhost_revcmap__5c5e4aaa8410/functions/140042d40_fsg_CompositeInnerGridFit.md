# fsg_CompositeInnerGridFit

- ea: `0x140042d40`
- end: `0x140043188`
- name: `fsg_CompositeInnerGridFit`
- size: `1096`
- prototype: `__int64 __usercall@<rax>(struct fnt_GlobalGraphicStateType *@<rcx>, __int64, __int16, __int64, __int64, __int16, __int16, __int16, char, struct TransMatrix *, struct BBOX *, __int16, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400197e0`

## callees

- `0x14001bf54`
- `0x14001c2ec`
- `0x14001c570`
- `0x140042d40`
- `0x140043190`
- `0x14004336c`
- `0x140043510`
- `0x14004357c`
- `0x14005e604`
- `0x1400622d4`
- `0x14007680c`
- `0x140076eea`
- `0x140095e2c`
- `0x140095ed4`

## pseudocode

```c
__int64 __fastcall fsg_CompositeInnerGridFit(
        struct fnt_GlobalGraphicStateType *a1,
        int a2,
        __int64 a3,
        char a4,
        __int64 a5,
        unsigned __int16 a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        __int16 a9,
        __int16 a10,
        __int16 a11,
        char a12,
        struct TransMatrix *a13,
        struct BBOX *a14,
        unsigned __int16 a15,
        __int64 a16,
        _WORD *a17,
        _WORD *a18,
        bool *a19,
        _DWORD *a20)
{
  __int128 v21; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int64 v26; // r8
  __int64 v27; // r8
  __int64 v28; // r8
  __int64 v29; // r8
  __int64 v30; // r8
  __int64 v31; // r8
  __int64 v32; // r8
  __int64 v33; // r8
  __int16 v34; // dx
  __int64 result; // rax
  bool v36; // zf

  v21 = *(_OWORD *)((char *)a1 + 72);
  *(_OWORD *)((char *)a1 + 120) = *(_OWORD *)((char *)a1 + 56);
  *((_BYTE *)a1 + 369) = 1;
  v24 = *(_OWORD *)((char *)a1 + 88);
  *((_BYTE *)a1 + 406) = 1;
  *(_OWORD *)((char *)a1 + 136) = v21;
  v25 = *(_OWORD *)((char *)a1 + 104);
  *(_OWORD *)((char *)a1 + 152) = v24;
  *(_OWORD *)((char *)a1 + 168) = v25;
  *a17 = *((_WORD *)a1 + 67);
  *a18 = *((_WORD *)a1 + 66);
  *a19 = 0;
  scl_CalcOrigPhantomPoints((struct fnt_ElementType *)a3, a14, a9, a10, *a7, *a8, a11);
  v26 = (unsigned __int16)(*(_WORD *)(*(_QWORD *)(a3 + 64) + 2LL * *(__int16 *)(a3 + 80) - 2) + 1);
  *(_DWORD *)(*(_QWORD *)(a3 + 32) + 4 * v26) += *a20;
  v27 = (unsigned __int16)(*(_WORD *)(*(_QWORD *)(a3 + 64) + 2LL * *(__int16 *)(a3 + 80) - 2) + 2);
  *(_DWORD *)(*(_QWORD *)(a3 + 32) + 4 * v27) += a20[2];
  v28 = (unsigned __int16)(*(_WORD *)(*(_QWORD *)(a3 + 64) + 2LL * *(__int16 *)(a3 + 80) - 2) + 3);
  *(_DWORD *)(*(_QWORD *)(a3 + 32) + 4 * v28) += a20[4];
  v29 = (unsigned __int16)(*(_WORD *)(*(_QWORD *)(a3 + 64) + 2LL * *(__int16 *)(a3 + 80) - 2) + 4);
  *(_DWORD *)(*(_QWORD *)(a3 + 32) + 4 * v29) += a20[6];
  v30 = (unsigned __int16)(*(_WORD *)(*(_QWORD *)(a3 + 64) + 2LL * *(__int16 *)(a3 + 80) - 2) + 1);
  *(_DWORD *)(*(_QWORD *)(a3 + 40) + 4 * v30) += a20[1];
  v31 = (unsigned __int16)(*(_WORD *)(*(_QWORD *)(a3 + 64) + 2LL * *(__int16 *)(a3 + 80) - 2) + 2);
  *(_DWORD *)(*(_QWORD *)(a3 + 40) + 4 * v31) += a20[3];
  v32 = (unsigned __int16)(*(_WORD *)(*(_QWORD *)(a3 + 64) + 2LL * *(__int16 *)(a3 + 80) - 2) + 3);
  *(_DWORD *)(*(_QWORD *)(a3 + 40) + 4 * v32) += a20[5];
  v33 = (unsigned __int16)(*(_WORD *)(*(_QWORD *)(a3 + 64) + 2LL * *(__int16 *)(a3 + 80) - 2) + 4);
  *(_DWORD *)(*(_QWORD *)(a3 + 40) + 4 * v33) += a20[7];
  v34 = *(_WORD *)(*(_QWORD *)(a3 + 64) + 2LL * *(__int16 *)(a3 + 80) - 2);
  *a7 = *(_WORD *)(*(_QWORD *)(a3 + 32) + 4LL * (unsigned __int16)(v34 + 2))
      - *(_WORD *)(*(_QWORD *)(a3 + 32) + 4LL * (unsigned __int16)(v34 + 1));
  LOWORD(v33) = *(_WORD *)(*(_QWORD *)(a3 + 64) + 2LL * *(__int16 *)(a3 + 80) - 2);
  *a8 = *(_WORD *)(*(_QWORD *)(a3 + 40) + 4LL * (unsigned __int16)(v33 + 3))
      - *(_WORD *)(*(_QWORD *)(a3 + 40) + 4LL * (unsigned __int16)(v33 + 4));
  memcpy_0(
    *(void **)(a3 + 16),
    *(const void **)a3,
    4LL * (unsigned __int16)(*(_WORD *)(*(_QWORD *)(a3 + 64) + 2LL * *(__int16 *)(a3 + 80) - 2) + 1));
  memcpy_0(
    *(void **)(a3 + 24),
    *(const void **)(a3 + 8),
    4LL * (unsigned __int16)(*(_WORD *)(*(_QWORD *)(a3 + 64) + 2LL * *(__int16 *)(a3 + 80) - 2) + 1));
  if ( (*((_BYTE *)a1 + 136) & 1) != 0 || !a4 )
  {
    if ( a12 )
    {
      scl_ScaleOldPhantomPoints((struct fnt_ElementType *)a3, a1);
      scl_CopyCurrentPhantomPoints((struct fnt_ElementType *)a3);
    }
    else
    {
      scl_OriginalPhantomPointsToCurrentFixedFUnits((struct fnt_ElementType *)a3);
    }
    return 0;
  }
  *((_BYTE *)a1 + 405) = a12;
  if ( *((_BYTE *)a1 + 369) || !a12 )
  {
    *((_BYTE *)a1 + 406) = 1;
    if ( !a12 )
    {
      scl_InitializeChildScaling(a1, a13, a6);
      scl_ScaleFixedCurrentCharPoints((struct fnt_ElementType *)a3, a1);
    }
  }
  else
  {
    *((_BYTE *)a1 + 406) = 0;
  }
  scl_ScaleOldPhantomPoints((struct fnt_ElementType *)a3, a1);
  scl_AdjustOldSideBearingPoints((struct fnt_ElementType *)a3, a1);
  scl_CopyCurrentPhantomPoints((struct fnt_ElementType *)a3);
  scl_RoundCurrentSideBearingPnt((struct fnt_ElementType *)a3, a1, a6);
  if ( !a15 )
    goto LABEL_9;
  memset_0(
    *(void **)(a3 + 72),
    0,
    (unsigned __int16)(*(_WORD *)(*(_QWORD *)(a3 + 64) + 2LL * *(__int16 *)(a3 + 80) - 2) + 9));
  v36 = (*((_BYTE *)a1 + 136) & 1) == 0;
  result = 0;
  *((_WORD *)a1 + 181) = 512;
  if ( v36 )
    result = itrp_Execute(a2, a3, a16, (unsigned int)a16 + a15, (__int64)a1, a5);
  *a19 = *((_DWORD *)a1 + 33) != *((_DWORD *)a1 + 17);
  *a18 = *((_WORD *)a1 + 66);
  *a17 = *((_WORD *)a1 + 67);
  if ( !(_DWORD)result )
  {
LABEL_9:
    if ( !a12 )
    {
      scl_ScaleBackCurrentCharPoints((struct fnt_ElementType *)a3, a1);
      scl_ScaleBackCurrentPhantomPoints((struct fnt_ElementType *)a3, a1);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140042d40  mov     [rsp+arg_8], rdx
0x140042d45  push    rbx
0x140042d46  push    rbp
0x140042d47  push    rsi
0x140042d48  push    rdi
0x140042d49  push    r12
0x140042d4b  push    r13
0x140042d4d  push    r14
0x140042d4f  push    r15
0x140042d51  sub     rsp, 48h
0x140042d55  movups  xmm0, xmmword ptr [rcx+38h]
0x140042d59  mov     r15, [rsp+88h+arg_80]
0x140042d61  mov     r14, r8
0x140042d64  movups  xmm1, xmmword ptr [rcx+48h]
0x140042d68  mov     r12, [rsp+88h+arg_88]
0x140042d70  mov     bpl, r9b
0x140042d73  mov     r13, [rsp+88h+arg_90]
0x140042d7b  mov     rsi, rcx
0x140042d7e  mov     rdi, [rsp+88h+arg_38]
0x140042d86  mov     rbx, [rsp+88h+arg_30]
0x140042d8e  movzx   r9d, [rsp+88h+arg_48]; __int16
0x140042d97  movzx   r8d, [rsp+88h+arg_40]; __int16
0x140042da0  mov     rdx, [rsp+88h+arg_68]; struct BBOX *
0x140042da8  movups  xmmword ptr [rcx+78h], xmm0
0x140042dac  mov     byte ptr [rcx+171h], 1
0x140042db3  movups  xmm0, xmmword ptr [rcx+58h]
0x140042db7  mov     byte ptr [rcx+196h], 1
0x140042dbe  movups  xmmword ptr [rcx+88h], xmm1
0x140042dc5  movups  xmm1, xmmword ptr [rcx+68h]
0x140042dc9  movups  xmmword ptr [rcx+98h], xmm0
0x140042dd0  movups  xmmword ptr [rcx+0A8h], xmm1
0x140042dd7  movzx   eax, word ptr [rcx+86h]
0x140042dde  mov     [r15], ax
0x140042de2  movzx   eax, word ptr [rcx+84h]
0x140042de9  mov     rcx, r14; struct fnt_ElementType *
0x140042dec  mov     [r12], ax
0x140042df1  movzx   eax, [rsp+88h+arg_50]
0x140042df9  mov     [rsp+88h+var_58], ax; __int16
0x140042dfe  mov     byte ptr [r13+0], 0
0x140042e03  movzx   eax, word ptr [rdi]
0x140042e06  mov     [rsp+88h+var_60], ax; unsigned __int16
0x140042e0b  movzx   eax, word ptr [rbx]
0x140042e0e  mov     [rsp+88h+var_68], ax; unsigned __int16
0x140042e13  call    ?scl_CalcOrigPhantomPoints@@YAXPEAUfnt_ElementType@@PEBUBBOX@@FFGGF@Z; scl_CalcOrigPhantomPoints(fnt_ElementType *,BBOX const *,short,short,ushort,ushort,short)
0x140042e18  mov     rax, [r14+40h]
0x140042e1c  mov     r10w, 1
0x140042e21  movsx   rcx, word ptr [r14+50h]
0x140042e26  mov     r9, [rsp+88h+arg_98]
0x140042e2e  movzx   edx, word ptr [rax+rcx*2-2]
0x140042e33  mov     rcx, [r14+20h]
0x140042e37  add     dx, r10w
0x140042e3b  mov     eax, [r9]
0x140042e3e  movzx   r8d, dx
0x140042e42  add     [rcx+r8*4], eax
0x140042e46  mov     rax, [r14+40h]
0x140042e4a  movsx   rcx, word ptr [r14+50h]
0x140042e4f  movzx   edx, word ptr [rax+rcx*2-2]
0x140042e54  mov     rcx, [r14+20h]
0x140042e58  add     dx, 2
0x140042e5c  mov     eax, [r9+8]
0x140042e60  movzx   r8d, dx
0x140042e64  add     [rcx+r8*4], eax
0x140042e68  mov     rax, [r14+40h]
0x140042e6c  movsx   rcx, word ptr [r14+50h]
0x140042e71  movzx   edx, word ptr [rax+rcx*2-2]
0x140042e76  mov     rcx, [r14+20h]
0x140042e7a  add     dx, 3
0x140042e7e  mov     eax, [r9+10h]
0x140042e82  movzx   r8d, dx
0x140042e86  add     [rcx+r8*4], eax
0x140042e8a  mov     rax, [r14+40h]
0x140042e8e  movsx   rcx, word ptr [r14+50h]
0x140042e93  movzx   edx, word ptr [rax+rcx*2-2]
0x140042e98  mov     rcx, [r14+20h]
0x140042e9c  add     dx, 4
0x140042ea0  mov     eax, [r9+18h]
0x140042ea4  movzx   r8d, dx
0x140042ea8  add     [rcx+r8*4], eax
0x140042eac  mov     rax, [r14+40h]
0x140042eb0  movsx   rcx, word ptr [r14+50h]
0x140042eb5  movzx   edx, word ptr [rax+rcx*2-2]
0x140042eba  mov     rcx, [r14+28h]
0x140042ebe  add     dx, r10w
0x140042ec2  mov     eax, [r9+4]
0x140042ec6  movzx   r8d, dx
0x140042eca  add     [rcx+r8*4], eax
0x140042ece  movsx   rcx, word ptr [r14+50h]
0x140042ed3  mov     rax, [r14+40h]
0x140042ed7  movzx   edx, word ptr [rax+rcx*2-2]
0x140042edc  add     dx, 2
0x140042ee0  movzx   r8d, dx
0x140042ee4  mov     eax, [r9+0Ch]
0x140042ee8  mov     rcx, [r14+28h]
0x140042eec  add     [rcx+r8*4], eax
0x140042ef0  mov     rax, [r14+40h]
0x140042ef4  movsx   rcx, word ptr [r14+50h]
0x140042ef9  movzx   edx, word ptr [rax+rcx*2-2]
0x140042efe  mov     eax, [r9+14h]
0x140042f02  add     dx, 3
0x140042f06  mov     rcx, [r14+28h]
0x140042f0a  movzx   r8d, dx
0x140042f0e  add     [rcx+r8*4], eax
0x140042f12  mov     rax, [r14+40h]
0x140042f16  movsx   rcx, word ptr [r14+50h]
0x140042f1b  movzx   edx, word ptr [rax+rcx*2-2]
0x140042f20  mov     eax, [r9+1Ch]
0x140042f24  add     dx, 4
0x140042f28  mov     rcx, [r14+28h]
0x140042f2c  movzx   r8d, dx
0x140042f30  add     [rcx+r8*4], eax
0x140042f34  mov     r8, [r14+20h]
0x140042f38  mov     rax, [r14+40h]
0x140042f3c  movsx   rcx, word ptr [r14+50h]
0x140042f41  movzx   edx, word ptr [rax+rcx*2-2]
0x140042f46  lea     eax, [rdx+2]
0x140042f49  add     dx, r10w
0x140042f4d  movzx   ecx, ax
0x140042f50  movzx   eax, dx
0x140042f53  movzx   ecx, word ptr [r8+rcx*4]
0x140042f58  sub     cx, [r8+rax*4]
0x140042f5d  mov     [rbx], cx
0x140042f60  movsx   rcx, word ptr [r14+50h]
0x140042f65  mov     rax, [r14+40h]
0x140042f69  mov     r9, [r14+28h]
0x140042f6d  movzx   r8d, word ptr [rax+rcx*2-2]
0x140042f73  lea     eax, [r8+4]
0x140042f77  add     r8w, 3
0x140042f7c  movzx   edx, ax
0x140042f7f  movzx   eax, r8w
0x140042f83  movzx   ecx, word ptr [r9+rax*4]
0x140042f88  sub     cx, [r9+rdx*4]
0x140042f8d  mov     [rdi], cx
0x140042f90  movsx   rcx, word ptr [r14+50h]
0x140042f95  mov     rax, [r14+40h]
0x140042f99  movzx   edx, word ptr [rax+rcx*2-2]
0x140042f9e  mov     rcx, [r14+10h]; void *
0x140042fa2  add     dx, r10w
0x140042fa6  movzx   r8d, dx
0x140042faa  mov     rdx, [r14]; Src
0x140042fad  shl     r8, 2; Size
0x140042fb1  call    memcpy_0
0x140042fb6  movsx   rcx, word ptr [r14+50h]
0x140042fbb  mov     rax, [r14+40h]
0x140042fbf  movzx   edx, word ptr [rax+rcx*2-2]
0x140042fc4  mov     rcx, [r14+18h]; void *
0x140042fc8  inc     dx
0x140042fcb  movzx   r8d, dx
0x140042fcf  mov     rdx, [r14+8]; Src
0x140042fd3  shl     r8, 2; Size
0x140042fd7  call    memcpy_0
0x140042fdc  test    byte ptr [rsi+88h], 1
0x140042fe3  jnz     loc_140043080
0x140042fe9  test    bpl, bpl
0x140042fec  jz      loc_140043080
0x140042ff2  mov     bl, [rsp+88h+arg_58]
0x140042ff9  xor     ebp, ebp
0x140042ffb  mov     [rsi+195h], bl
0x140043001  cmp     [rsi+171h], bpl
0x140043008  jnz     short loc_140043017
0x14004300a  test    bl, bl
0x14004300c  jz      short loc_140043017
0x14004300e  mov     [rsi+196h], bpl
0x140043015  jmp     short loc_140043026
0x140043017  mov     byte ptr [rsi+196h], 1
0x14004301e  test    bl, bl
0x140043020  jz      loc_140043144
0x140043026  mov     rdx, rsi; struct fnt_GlobalGraphicStateType *
0x140043029  mov     rcx, r14; struct fnt_ElementType *
0x14004302c  call    ?scl_ScaleOldPhantomPoints@@YAXPEAUfnt_ElementType@@PEBUfnt_GlobalGraphicStateType@@@Z; scl_ScaleOldPhantomPoints(fnt_ElementType *,fnt_GlobalGraphicStateType const *)
0x140043031  mov     rdx, rsi; struct fnt_GlobalGraphicStateType *
0x140043034  mov     rcx, r14; struct fnt_ElementType *
0x140043037  call    ?scl_AdjustOldSideBearingPoints@@YAXPEAUfnt_ElementType@@PEBUfnt_GlobalGraphicStateType@@@Z; scl_AdjustOldSideBearingPoints(fnt_ElementType *,fnt_GlobalGraphicStateType const *)
0x14004303c  mov     rcx, r14; struct fnt_ElementType *
0x14004303f  call    ?scl_CopyCurrentPhantomPoints@@YAXPEAUfnt_ElementType@@@Z; scl_CopyCurrentPhantomPoints(fnt_ElementType *)
0x140043044  movzx   r8d, [rsp+88h+arg_28]; unsigned __int16
0x14004304d  mov     rdx, rsi; struct fnt_GlobalGraphicStateType *
0x140043050  mov     rcx, r14; struct fnt_ElementType *
0x140043053  call    ?scl_RoundCurrentSideBearingPnt@@YAXPEAUfnt_ElementType@@PEBUfnt_GlobalGraphicStateType@@G@Z; scl_RoundCurrentSideBearingPnt(fnt_ElementType *,fnt_GlobalGraphicStateType const *,ushort)
0x140043058  movzx   edi, [rsp+88h+arg_70]
0x140043060  test    di, di
0x140043063  jnz     short loc_1400430A3
0x140043065  test    bl, bl
0x140043067  jz      loc_14004316D
0x14004306d  xor     eax, eax
0x14004306f  add     rsp, 48h
0x140043073  pop     r15
0x140043075  pop     r14
0x140043077  pop     r13
0x140043079  pop     r12
0x14004307b  pop     rdi
0x14004307c  pop     rsi
0x14004307d  pop     rbp
0x14004307e  pop     rbx
0x14004307f  retn
0x140043080  cmp     [rsp+88h+arg_58], 0
0x140043088  mov     rcx, r14; struct fnt_ElementType *
0x14004308b  jz      loc_14004313A
0x140043091  mov     rdx, rsi; struct fnt_GlobalGraphicStateType *
0x140043094  call    ?scl_ScaleOldPhantomPoints@@YAXPEAUfnt_ElementType@@PEBUfnt_GlobalGraphicStateType@@@Z; scl_ScaleOldPhantomPoints(fnt_ElementType *,fnt_GlobalGraphicStateType const *)
0x140043099  mov     rcx, r14; struct fnt_ElementType *
0x14004309c  call    ?scl_CopyCurrentPhantomPoints@@YAXPEAUfnt_ElementType@@@Z; scl_CopyCurrentPhantomPoints(fnt_ElementType *)
0x1400430a1  jmp     short loc_14004306D
0x1400430a3  movsx   rcx, word ptr [r14+50h]
0x1400430a8  mov     rax, [r14+40h]
0x1400430ac  movzx   edx, word ptr [rax+rcx*2-2]
0x1400430b1  mov     rcx, [r14+48h]; void *
0x1400430b5  add     dx, 9
0x1400430b9  movzx   r8d, dx; Size
0x1400430bd  xor     edx, edx; Val
0x1400430bf  call    memset_0
0x1400430c4  test    byte ptr [rsi+88h], 1
0x1400430cb  mov     eax, ebp
0x1400430cd  mov     word ptr [rsi+16Ah], 200h
0x1400430d6  jnz     short loc_140043106
0x1400430d8  mov     r8, [rsp+88h+arg_78]
0x1400430e0  mov     rdx, r14
0x1400430e3  mov     rax, [rsp+88h+arg_20]
0x1400430eb  mov     rcx, [rsp+88h+arg_8]
0x1400430f3  mov     qword ptr [rsp+88h+var_60], rax
0x1400430f8  lea     r9, [r8+rdi]
0x1400430fc  mov     qword ptr [rsp+88h+var_68], rsi
0x140043101  call    itrp_Execute
0x140043106  mov     ecx, [rsi+44h]
0x140043109  cmp     [rsi+84h], ecx
0x14004310f  setnz   cl
0x140043112  mov     [r13+0], cl
0x140043116  movzx   ecx, word ptr [rsi+84h]
0x14004311d  mov     [r12], cx
0x140043122  movzx   ecx, word ptr [rsi+86h]
0x140043129  mov     [r15], cx
0x14004312d  test    eax, eax
0x14004312f  jz      loc_140043065
0x140043135  jmp     loc_14004306F
0x14004313a  call    ?scl_OriginalPhantomPointsToCurrentFixedFUnits@@YAXPEAUfnt_ElementType@@@Z; scl_OriginalPhantomPointsToCurrentFixedFUnits(fnt_ElementType *)
0x14004313f  jmp     loc_14004306D
0x140043144  movzx   r8d, [rsp+88h+arg_28]; unsigned __int16
0x14004314d  mov     rcx, rsi; struct fnt_GlobalGraphicStateType *
0x140043150  mov     rdx, [rsp+88h+arg_60]; struct TransMatrix *
0x140043158  call    ?scl_InitializeChildScaling@@YAXPEAUfnt_GlobalGraphicStateType@@PEBUTransMatrix@@G@Z; scl_InitializeChildScaling(fnt_GlobalGraphicStateType *,TransMatrix const *,ushort)
0x14004315d  mov     rdx, rsi; struct fnt_GlobalGraphicStateType *
0x140043160  mov     rcx, r14; struct fnt_ElementType *
0x140043163  call    ?scl_ScaleFixedCurrentCharPoints@@YAXPEAUfnt_ElementType@@PEBUfnt_GlobalGraphicStateType@@@Z; scl_ScaleFixedCurrentCharPoints(fnt_ElementType *,fnt_GlobalGraphicStateType const *)
0x140043168  jmp     loc_140043026
0x14004316d  mov     rdx, rsi; struct fnt_GlobalGraphicStateType *
0x140043170  mov     rcx, r14; struct fnt_ElementType *
0x140043173  call    ?scl_ScaleBackCurrentCharPoints@@YAXPEAUfnt_ElementType@@PEBUfnt_GlobalGraphicStateType@@@Z; scl_ScaleBackCurrentCharPoints(fnt_ElementType *,fnt_GlobalGraphicStateType const *)
0x140043178  mov     rdx, rsi; struct fnt_GlobalGraphicStateType *
0x14004317b  mov     rcx, r14; struct fnt_ElementType *
0x14004317e  call    ?scl_ScaleBackCurrentPhantomPoints@@YAXPEAUfnt_ElementType@@PEBUfnt_GlobalGraphicStateType@@@Z; scl_ScaleBackCurrentPhantomPoints(fnt_ElementType *,fnt_GlobalGraphicStateType const *)
0x140043183  jmp     loc_14004306D
```
