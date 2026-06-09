# CTxtRange::Update_iFormat(long)

- ea: `0x180016d90`
- end: `0x180017224`
- name: `?Update_iFormat@CTxtRange@@QEAAXJ@Z`
- size: `1172`
- prototype: `void __fastcall(CTxtRange *__hidden this, int)`
- caller_count: `21`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800020c4`
- `0x180005510`
- `0x18000e1e0`
- `0x1800159d8`
- `0x180016470`
- `0x180016700`
- `0x180017ad0`
- `0x180017cdc`
- `0x1800238dc`
- `0x180027b20`
- `0x18002d048`
- `0x18002dce0`
- `0x180035230`
- `0x18003ec60`
- `0x180040500`
- `0x180045164`
- `0x18005fa14`
- `0x180060014`
- `0x180073c24`
- `0x180073ca0`
- `0x180073d88`

## callees

- `0x180005510`
- `0x180015448`
- `0x180016d90`
- `0x180095010`

## pseudocode

```c
void __fastcall CTxtRange::Update_iFormat(CTxtRange *this, int a2)
{
  int v2; // esi
  __int64 v4; // rcx
  __int64 *v5; // r12
  int v6; // r8d
  int v7; // edx
  _DWORD *v8; // r9
  int v9; // edx
  int v10; // eax
  __int64 v11; // rax
  unsigned int v12; // eax
  int v13; // r15d
  __int64 v14; // rdx
  char *v15; // rdi
  __int64 *v16; // r14
  int v17; // ebp
  __int64 v18; // rcx
  int v19; // eax
  int v20; // eax
  int v21; // edx
  _DWORD *v22; // rax
  __int64 v23; // rcx
  int v24; // edx
  int v25; // eax
  __int64 v26; // rax
  unsigned int v27; // eax
  __int64 v28; // rdx
  __int64 *v29; // rcx
  __int64 v30; // rdx
  __int128 v31; // xmm0
  __int64 v32; // xmm1_8
  int v33; // eax
  struct IFormatCache *v34; // rdi
  _OWORD v35[2]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v36; // [rsp+50h] [rbp-48h]
  __int64 *v37; // [rsp+A0h] [rbp+8h] BYREF
  __int64 *v38; // [rsp+B0h] [rbp+18h] BYREF

  v2 = a2;
  if ( !*((_DWORD *)this + 22) )
  {
    *((_WORD *)this + 49) &= 0xFE7Fu;
    if ( (*((_BYTE *)this + 98) & 8) == 0 )
    {
      v4 = *((_QWORD *)this + 7);
      v5 = g_defaultCF;
      if ( !v4 || (v6 = *(_DWORD *)(v4 + 8)) == 0 )
      {
        v15 = (char *)this + 48;
        goto LABEL_51;
      }
      if ( a2 != -1 )
      {
        v15 = (char *)this + 48;
        goto LABEL_60;
      }
      v7 = *((_DWORD *)this + 16);
      if ( v6 > 0 && v7 < v6 && *(_QWORD *)v4 && v7 >= 0 )
        v8 = (_DWORD *)(*(_QWORD *)v4 + *(_DWORD *)(v4 + 16) * v7);
      else
        v8 = 0;
      if ( *v8 == *((_DWORD *)this + 17) && v7 < v6 - 1 )
        *((_QWORD *)this + 8) = (unsigned int)(v7 + 1);
      v9 = *(_DWORD *)(v4 + 8);
      if ( v9 )
      {
        if ( v9 > 0 && (v10 = *((_DWORD *)this + 16), v10 < v9) && *(_QWORD *)v4 && v10 >= 0 )
          v11 = *(_QWORD *)v4 + *(_DWORD *)(v4 + 16) * v10;
        else
          v11 = 0;
        v12 = *(__int16 *)(v11 + 4);
        v37 = 0;
        v13 = v12;
        v14 = v12;
        if ( (v12 & 0x8000u) == 0 )
        {
          v15 = (char *)this + 48;
LABEL_23:
          if ( (*(int (__fastcall **)(struct IFormatCache *, __int64, __int64 **))(*(_QWORD *)qword_1800A72D0 + 32LL))(
                 qword_1800A72D0,
                 v14,
                 &v37) >= 0 )
          {
            v16 = v37;
          }
          else
          {
            v16 = g_defaultCF;
            v37 = g_defaultCF;
          }
          v17 = *(_DWORD *)v16;
          if ( (unsigned int)CTxtPtr::IsAfterEOP((CTxtRange *)((char *)this + 24)) )
          {
            v2 = v13;
            v29 = v16;
            goto LABEL_47;
          }
          if ( !*((_DWORD *)this + 17) )
          {
            v18 = *((_QWORD *)this + 7);
            if ( v18 )
            {
              v19 = *((_DWORD *)this + 16);
              *((_DWORD *)this + 17) = 0;
              if ( v19 > 0 )
              {
                v20 = v19 - 1;
                *((_DWORD *)this + 16) = v20;
                v21 = *(_DWORD *)(v18 + 8);
                if ( v21 > 0 && v20 < v21 && *(_QWORD *)v18 && v20 >= 0 )
                  v22 = (_DWORD *)(*(_QWORD *)v18 + *(_DWORD *)(v18 + 16) * v20);
                else
                  v22 = 0;
                *((_DWORD *)this + 17) = *v22;
              }
            }
          }
          v23 = *((_QWORD *)this + 7);
          if ( v23 && (v24 = *(_DWORD *)(v23 + 8)) != 0 )
          {
            if ( v24 > 0 && (v25 = *((_DWORD *)this + 16), v25 < v24) && *(_QWORD *)v23 && v25 >= 0 )
              v26 = *(_QWORD *)v23 + *(_DWORD *)(v23 + 16) * v25;
            else
              v26 = 0;
            v27 = *(__int16 *)(v26 + 4);
            v38 = 0;
            v2 = v27;
            v28 = v27;
            if ( (v27 & 0x8000u) == 0 )
            {
              v15 = (char *)this + 48;
              goto LABEL_44;
            }
          }
          else
          {
            v38 = 0;
            v2 = -1;
          }
          v15 = (char *)this + 48;
          v28 = (unsigned int)*(__int16 *)(*((_QWORD *)this + 6) + 276LL);
LABEL_44:
          if ( (*(int (__fastcall **)(struct IFormatCache *, __int64, __int64 **))(*(_QWORD *)qword_1800A72D0 + 32LL))(
                 qword_1800A72D0,
                 v28,
                 &v38) >= 0 )
          {
            v29 = v38;
          }
          else
          {
            v29 = g_defaultCF;
            v38 = g_defaultCF;
          }
          v17 = *(_DWORD *)v29;
LABEL_47:
          if ( (*(_WORD *)(*(_QWORD *)v15 + 184LL) & 0x4000) == 0 )
          {
            if ( *((_DWORD *)this + 10) || (*(_DWORD *)v29 & 0x40000) == 0 )
            {
              if ( (v17 & 0x40130) != 0 )
              {
                v2 = v13;
              }
              else if ( v2 != v13
                     && (*((_BYTE *)this + 98) & 0x40) != 0
                     && (unsigned int)*((unsigned __int8 *)v29 + 4) - 177 <= 1 != (unsigned int)*((unsigned __int8 *)v16
                                                                                                + 4)
                                                                                - 177 <= 1 )
              {
                v2 = v13;
              }
            }
            else
            {
              v2 = -1;
            }
          }
LABEL_51:
          if ( v2 == -1 )
          {
LABEL_52:
            if ( v2 != *((__int16 *)this + 48) )
            {
              v34 = qword_1800A72D0;
              (**(void (__fastcall ***)(struct IFormatCache *, _QWORD))qword_1800A72D0)(
                qword_1800A72D0,
                (unsigned int)v2);
              (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)v34 + 8LL))(
                v34,
                (unsigned int)*((__int16 *)this + 48));
              *((_WORD *)this + 48) = v2;
            }
            return;
          }
LABEL_60:
          v37 = 0;
          if ( v2 >= 0 )
            v30 = (unsigned int)v2;
          else
            v30 = (unsigned int)*(__int16 *)(*(_QWORD *)v15 + 276LL);
          if ( (*(int (__fastcall **)(struct IFormatCache *, __int64, __int64 **))(*(_QWORD *)qword_1800A72D0 + 32LL))(
                 qword_1800A72D0,
                 v30,
                 &v37) >= 0 )
            v5 = v37;
          else
            v37 = g_defaultCF;
          if ( (*(_DWORD *)v5 & 0x120) != 0 )
          {
            v31 = *((_OWORD *)v5 + 1);
            v32 = v5[4];
            v33 = _mm_cvtsi128_si32(*(__m128i *)v5);
            v35[0] = *(_OWORD *)v5;
            v36 = v32;
            LODWORD(v35[0]) = v33 & 0xFFFFFEDF;
            v35[1] = v31;
            CTxtRange::SetCharFormat(this, (const struct CCharFormat *)v35, 0, 0, 0xFEFFFFFF, 0);
            return;
          }
          goto LABEL_52;
        }
      }
      else
      {
        v37 = 0;
        v13 = -1;
      }
      v15 = (char *)this + 48;
      v14 = (unsigned int)*(__int16 *)(*((_QWORD *)this + 6) + 276LL);
      goto LABEL_23;
    }
  }
}

```

## disassembly

```asm
0x180016d90  push    rbx
0x180016d92  push    rsi
0x180016d93  sub     rsp, 88h
0x180016d9a  cmp     dword ptr [rcx+58h], 0
0x180016d9e  mov     esi, edx
0x180016da0  mov     rbx, rcx
0x180016da3  jnz     short loc_180016DB4
0x180016da5  mov     eax, 0FE7Fh
0x180016daa  and     [rcx+62h], ax
0x180016dae  test    byte ptr [rcx+62h], 8
0x180016db2  jz      short loc_180016DBF
0x180016db4  add     rsp, 88h
0x180016dbb  pop     rsi
0x180016dbc  pop     rbx
0x180016dbd  retn
0x180016dbf  mov     rcx, [rcx+38h]
0x180016dc3  mov     [rsp+98h+var_20], r12
0x180016dc8  lea     r12, ?g_defaultCF@@3VCCharFormat@@A; CCharFormat g_defaultCF
0x180016dcf  mov     [rsp+98h+var_28], r13
0x180016dd4  xor     r13d, r13d
0x180016dd7  mov     [rsp+98h+var_18], rdi
0x180016ddf  test    rcx, rcx
0x180016de2  jz      loc_180017079
0x180016de8  mov     r8d, [rcx+8]
0x180016dec  test    r8d, r8d
0x180016def  jz      loc_180017079
0x180016df5  cmp     edx, 0FFFFFFFFh
0x180016df8  jnz     loc_180017091
0x180016dfe  mov     edx, [rbx+40h]
0x180016e01  mov     [rsp+98h+arg_8], rbp
0x180016e09  mov     [rsp+98h+var_30], r14
0x180016e0e  test    r8d, r8d
0x180016e11  jle     loc_1800171A4
0x180016e17  cmp     edx, r8d
0x180016e1a  jge     loc_1800171A4
0x180016e20  mov     r10, [rcx]
0x180016e23  test    r10, r10
0x180016e26  jz      loc_1800171A4
0x180016e2c  test    edx, edx
0x180016e2e  js      loc_1800171A4
0x180016e34  mov     eax, edx
0x180016e36  imul    eax, [rcx+10h]
0x180016e3a  movsxd  r9, eax
0x180016e3d  add     r9, r10
0x180016e40  mov     eax, [rbx+44h]
0x180016e43  cmp     [r9], eax
0x180016e46  jnz     short loc_180016E5A
0x180016e48  lea     eax, [r8-1]
0x180016e4c  cmp     edx, eax
0x180016e4e  jge     short loc_180016E5A
0x180016e50  lea     eax, [rdx+1]
0x180016e53  mov     [rbx+44h], r13d
0x180016e57  mov     [rbx+40h], eax
0x180016e5a  mov     edx, [rcx+8]
0x180016e5d  mov     [rsp+98h+var_38], r15
0x180016e62  test    edx, edx
0x180016e64  jz      loc_1800171CF
0x180016e6a  jle     loc_1800171AC
0x180016e70  mov     eax, [rbx+40h]
0x180016e73  cmp     eax, edx
0x180016e75  jge     loc_1800171AC
0x180016e7b  mov     rdx, [rcx]
0x180016e7e  test    rdx, rdx
0x180016e81  jz      loc_1800171AC
0x180016e87  test    eax, eax
0x180016e89  js      loc_1800171AC
0x180016e8f  imul    eax, [rcx+10h]
0x180016e93  cdqe
0x180016e95  add     rax, rdx
0x180016e98  movsx   eax, word ptr [rax+4]
0x180016e9c  mov     [rsp+98h+arg_0], r13
0x180016ea4  mov     r15d, eax
0x180016ea7  mov     edx, eax
0x180016ea9  test    ax, ax
0x180016eac  jns     loc_18001718B
0x180016eb2  mov     rax, [rbx+30h]
0x180016eb6  lea     rdi, [rbx+30h]
0x180016eba  movsx   edx, word ptr [rax+114h]
0x180016ec1  mov     rcx, cs:qword_1800A72D0
0x180016ec8  lea     r8, [rsp+98h+arg_0]
0x180016ed0  mov     rax, [rcx]
0x180016ed3  mov     rax, [rax+20h]
0x180016ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016edc  test    eax, eax
0x180016ede  jns     loc_18001705F
0x180016ee4  mov     r14, r12
0x180016ee7  mov     [rsp+98h+arg_0], r12
0x180016eef  mov     ebp, [r14]
0x180016ef2  lea     rcx, [rbx+18h]; this
0x180016ef6  call    ?IsAfterEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAfterEOP(void)
0x180016efb  test    eax, eax
0x180016efd  jnz     loc_1800171C4
0x180016f03  cmp     [rbx+44h], r13d
0x180016f07  jnz     short loc_180016F57
0x180016f09  mov     rcx, [rbx+38h]
0x180016f0d  test    rcx, rcx
0x180016f10  jz      short loc_180016F57
0x180016f12  mov     eax, [rbx+40h]
0x180016f15  mov     [rbx+44h], r13d
0x180016f19  test    eax, eax
0x180016f1b  jle     short loc_180016F57
0x180016f1d  dec     eax
0x180016f1f  mov     [rbx+40h], eax
0x180016f22  mov     edx, [rcx+8]
0x180016f25  test    edx, edx
0x180016f27  jle     loc_1800171BC
0x180016f2d  cmp     eax, edx
0x180016f2f  jge     loc_1800171BC
0x180016f35  mov     rdx, [rcx]
0x180016f38  test    rdx, rdx
0x180016f3b  jz      loc_1800171BC
0x180016f41  test    eax, eax
0x180016f43  js      loc_1800171BC
0x180016f49  imul    eax, [rcx+10h]
0x180016f4d  cdqe
0x180016f4f  add     rax, rdx
0x180016f52  mov     eax, [rax]
0x180016f54  mov     [rbx+44h], eax
0x180016f57  mov     rcx, [rbx+38h]
0x180016f5b  test    rcx, rcx
0x180016f5e  jz      loc_18001707F
0x180016f64  mov     edx, [rcx+8]
0x180016f67  test    edx, edx
0x180016f69  jz      loc_18001707F
0x180016f6f  jle     loc_1800171B4
0x180016f75  mov     eax, [rbx+40h]
0x180016f78  cmp     eax, edx
0x180016f7a  jge     loc_1800171B4
0x180016f80  mov     rdx, [rcx]
0x180016f83  test    rdx, rdx
0x180016f86  jz      loc_1800171B4
0x180016f8c  test    eax, eax
0x180016f8e  js      loc_1800171B4
0x180016f94  imul    eax, [rcx+10h]
0x180016f98  cdqe
0x180016f9a  add     rax, rdx
0x180016f9d  movsx   eax, word ptr [rax+4]
0x180016fa1  mov     [rsp+98h+arg_10], r13
0x180016fa9  mov     esi, eax
0x180016fab  mov     edx, eax
0x180016fad  test    ax, ax
0x180016fb0  jns     loc_180017194
0x180016fb6  mov     rax, [rbx+30h]
0x180016fba  lea     rdi, [rbx+30h]
0x180016fbe  movsx   edx, word ptr [rax+114h]
0x180016fc5  mov     rcx, cs:qword_1800A72D0
0x180016fcc  lea     r8, [rsp+98h+arg_10]
0x180016fd4  mov     rax, [rcx]
0x180016fd7  mov     rax, [rax+20h]
0x180016fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fe0  test    eax, eax
0x180016fe2  jns     loc_18001706C
0x180016fe8  mov     rcx, r12
0x180016feb  mov     [rsp+98h+arg_10], rcx
0x180016ff3  mov     ebp, [rcx]
0x180016ff5  mov     rax, [rdi]
0x180016ff8  mov     edx, 4000h
0x180016ffd  test    [rax+0B8h], dx
0x180017004  jnz     short loc_180017025
0x180017006  cmp     [rbx+28h], r13d
0x18001700a  jz      loc_180017175
0x180017010  test    ebp, 40130h
0x180017016  jnz     loc_1800171E2
0x18001701c  cmp     esi, r15d
0x18001701f  jnz     loc_1800171EA
0x180017025  mov     r15, [rsp+98h+var_38]
0x18001702a  mov     r14, [rsp+98h+var_30]
0x18001702f  mov     rbp, [rsp+98h+arg_8]
0x180017037  cmp     esi, 0FFFFFFFFh
0x18001703a  jnz     short loc_180017095
0x18001703c  movsx   eax, word ptr [rbx+60h]
0x180017040  cmp     esi, eax
0x180017042  jnz     loc_180017142
0x180017048  mov     rdi, [rsp+98h+var_18]
0x180017050  mov     r12, [rsp+98h+var_20]
0x180017055  mov     r13, [rsp+98h+var_28]
0x18001705a  jmp     loc_180016DB4
0x18001705f  mov     r14, [rsp+98h+arg_0]
0x180017067  jmp     loc_180016EEF
0x18001706c  mov     rcx, [rsp+98h+arg_10]
0x180017074  jmp     loc_180016FF3
0x180017079  lea     rdi, [rbx+30h]
0x18001707d  jmp     short loc_180017037
0x18001707f  mov     [rsp+98h+arg_10], r13
0x180017087  mov     esi, 0FFFFFFFFh
0x18001708c  jmp     loc_180016FB6
0x180017091  lea     rdi, [rbx+30h]
0x180017095  mov     [rsp+98h+arg_0], r13
0x18001709d  test    esi, esi
0x18001709f  jns     loc_18001719D
0x1800170a5  mov     rax, [rdi]
0x1800170a8  movsx   edx, word ptr [rax+114h]
0x1800170af  mov     rcx, cs:qword_1800A72D0
0x1800170b6  lea     r8, [rsp+98h+arg_0]
0x1800170be  mov     rax, [rcx]
0x1800170c1  mov     rax, [rax+20h]
0x1800170c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170ca  test    eax, eax
0x1800170cc  jns     short loc_180017138
0x1800170ce  mov     [rsp+98h+arg_0], r12
0x1800170d6  test    dword ptr [r12], 120h
0x1800170de  jz      loc_18001703C
0x1800170e4  movups  xmm2, xmmword ptr [r12]
0x1800170e9  mov     [rsp+98h+var_70], r13d; unsigned int
0x1800170ee  xor     r9d, r9d; struct IUndoBuilder *
0x1800170f1  movups  xmm0, xmmword ptr [r12+10h]
0x1800170f7  lea     rdx, [rsp+98h+var_68]; struct CCharFormat *
0x1800170fc  xor     r8d, r8d; unsigned int
0x1800170ff  movsd   xmm1, qword ptr [r12+20h]
0x180017106  mov     rcx, rbx; this
0x180017109  movd    eax, xmm2
0x18001710d  movups  [rsp+98h+var_68], xmm2
0x180017112  mov     [rsp+98h+var_78], 0FEFFFFFFh; unsigned int
0x18001711a  and     eax, 0FFFFFEDFh
0x18001711f  movsd   [rsp+98h+var_48], xmm1
0x180017125  mov     dword ptr [rsp+98h+var_68], eax
0x180017129  movups  [rsp+98h+var_58], xmm0
0x18001712e  call    ?SetCharFormat@CTxtRange@@QEAAJPEBVCCharFormat@@KPEAVIUndoBuilder@@KK@Z; CTxtRange::SetCharFormat(CCharFormat const *,ulong,IUndoBuilder *,ulong,ulong)
0x180017133  jmp     loc_180017048
0x180017138  mov     r12, [rsp+98h+arg_0]
0x180017140  jmp     short loc_1800170D6
0x180017142  mov     rdi, cs:qword_1800A72D0
0x180017149  mov     edx, esi
0x18001714b  mov     rcx, rdi
0x18001714e  mov     rax, [rdi]
0x180017151  mov     rax, [rax]
0x180017154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017159  mov     rax, [rdi]
0x18001715c  mov     rcx, rdi
0x18001715f  movsx   edx, word ptr [rbx+60h]
0x180017163  mov     rax, [rax+8]
0x180017167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001716c  mov     [rbx+60h], si
0x180017170  jmp     loc_180017048
0x180017175  test    dword ptr [rcx], 40000h
0x18001717b  jz      loc_180017010
0x180017181  mov     esi, 0FFFFFFFFh
0x180017186  jmp     loc_180017025
0x18001718b  lea     rdi, [rbx+30h]
0x18001718f  jmp     loc_180016EC1
0x180017194  lea     rdi, [rbx+30h]
0x180017198  jmp     loc_180016FC5
0x18001719d  mov     edx, esi
0x18001719f  jmp     loc_1800170AF
0x1800171a4  mov     r9, r13
0x1800171a7  jmp     loc_180016E40
0x1800171ac  mov     rax, r13
0x1800171af  jmp     loc_180016E98
0x1800171b4  mov     rax, r13
0x1800171b7  jmp     loc_180016F9D
0x1800171bc  mov     rax, r13
0x1800171bf  jmp     loc_180016F52
0x1800171c4  mov     esi, r15d
0x1800171c7  mov     rcx, r14
0x1800171ca  jmp     loc_180016FF5
0x1800171cf  mov     [rsp+98h+arg_0], r13
0x1800171d7  mov     r15d, 0FFFFFFFFh
0x1800171dd  jmp     loc_180016EB2
0x1800171e2  mov     esi, r15d
0x1800171e5  jmp     loc_180017025
0x1800171ea  test    byte ptr [rbx+62h], 40h
0x1800171ee  jz      loc_180017025
0x1800171f4  movzx   eax, byte ptr [r14+4]
0x1800171f9  mov     edx, r13d
0x1800171fc  sub     eax, 0B1h
0x180017201  cmp     eax, 1
0x180017204  movzx   eax, byte ptr [rcx+4]
0x180017208  mov     ecx, r13d
0x18001720b  setbe   dl
0x18001720e  sub     eax, 0B1h
0x180017213  cmp     eax, 1
0x180017216  setbe   cl
0x180017219  cmp     ecx, edx
0x18001721b  cmovnz  esi, r15d
0x18001721f  jmp     loc_180017025
```
