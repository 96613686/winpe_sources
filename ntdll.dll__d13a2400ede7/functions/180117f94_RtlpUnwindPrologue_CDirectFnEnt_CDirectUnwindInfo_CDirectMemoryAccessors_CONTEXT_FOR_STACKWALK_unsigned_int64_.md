# RtlpUnwindPrologue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(unsigned __int64,unsigned __int64,unsigned __int64,CDirectFnEnt,_CONTEXT_FOR_STACKWALK *,uchar *,CDirectFnEnt *,_AMD64_UNWIND_PARAMS *)

- ea: `0x180117f94`
- end: `0x18011861e`
- name: `??$RtlpUnwindPrologue@VCDirectFnEnt@@VCDirectUnwindInfo@@VCDirectMemoryAccessors@@PEAU_CONTEXT_FOR_STACKWALK@@@@YAJ_K00VCDirectFnEnt@@PEAU_CONTEXT_FOR_STACKWALK@@PEAEPEAV0@PEAU_AMD64_UNWIND_PARAMS@@@Z`
- size: `1674`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18009464c`

## callees

- `0x180070370`
- `0x1800e25d8`
- `0x1800f8ba4`
- `0x180117f94`
- `0x18014a15c`
- `0x18014a1d4`

## pseudocode

```c
__int64 __fastcall RtlpUnwindPrologue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(
        __int64 a1,
        int a2,
        __int64 a3,
        _DWORD *a4,
        _QWORD *a5,
        char *a6,
        _QWORD *a7,
        __int64 a8)
{
  __int64 v8; // rdi
  __int64 v9; // rbx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // eax
  unsigned int v13; // r9d
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  _QWORD *v17; // r10
  unsigned int v19; // r9d
  __int64 v20; // r10
  __int64 v21; // rcx
  __int64 Context; // rax
  int v23; // edx
  unsigned int v24; // ecx
  _QWORD *v25; // r10
  unsigned int v26; // r9d
  __int64 v27; // r10
  _QWORD *v28; // r11
  __int64 v29; // rcx
  _QWORD *v30; // r8
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  __int64 v35; // rax
  _QWORD *v36; // r8
  _QWORD *v37; // rdx
  __int64 v38; // rcx
  unsigned __int64 v39; // r8
  __int64 v40; // rcx
  unsigned __int64 v41; // rdx
  __int64 v42; // rcx
  unsigned __int64 v43; // rdx
  _QWORD *v44; // r8
  char v45; // [rsp+20h] [rbp-78h]
  int v46; // [rsp+50h] [rbp-48h]
  unsigned int v47; // [rsp+54h] [rbp-44h]

  v46 = 0;
  while ( 1 )
  {
    v8 = 0;
    v45 = 0;
    v47 = a2 - a1 - *a4;
    v9 = a1 + (unsigned int)a4[2];
    while ( 1 )
    {
      v10 = *(unsigned __int8 *)(v9 + 2);
      if ( (unsigned int)v8 >= v10 )
        break;
      v11 = *(unsigned __int16 *)(v9 + 2 * v8 + 4);
      if ( v47 < (unsigned __int8)v11 )
      {
        v8 = (unsigned int)RtlpUnwindOpSlots() + (unsigned int)v8;
      }
      else
      {
        v12 = BYTE1(v11) & 0xF;
        v13 = v11 >> 12;
        if ( v12 > 5 )
        {
          v31 = v12 - 6;
          if ( v31 )
          {
            v32 = v31 - 1;
            if ( v32 )
            {
              v33 = v32 - 1;
              if ( v33 )
              {
                v34 = v33 - 1;
                if ( v34 )
                {
                  if ( v34 != 1 )
                    goto LABEL_77;
                  v35 = a5[1];
                  v36 = (_QWORD *)(v35 + 8);
                  if ( !v13 )
                    v36 = (_QWORD *)a5[1];
                  v37 = (_QWORD *)(v35 + (v13 != 0 ? 32LL : 24LL));
                  if ( *(_QWORD *)a8
                    && ((unsigned __int64)v36 < **(_QWORD **)a8 || (unsigned __int64)v36 > **(_QWORD **)(a8 + 8) - 8LL)
                    || *(_QWORD *)a8
                    && ((unsigned __int64)v37 < **(_QWORD **)a8 || (unsigned __int64)v37 > **(_QWORD **)(a8 + 8) - 8LL) )
                  {
                    return 3221225512LL;
                  }
                  v45 = 1;
                  *a5 = *v36;
                  a5[1] = *v37;
                  v38 = 0;
                  while ( (void (__fastcall __noreturn *)())v9 != RtlpContinuationContextMachineFrameEntries[v38] )
                  {
                    v38 = (unsigned int)(v38 + 1);
                    if ( (unsigned int)v38 >= 2 )
                      goto LABEL_64;
                  }
                  RtlpVirtualPopShadowStack<_CONTEXT_FOR_STACKWALK *>(a5);
                }
                else
                {
                  v8 = (unsigned int)(v8 + 2);
                  v39 = *(unsigned __int16 *)(v9 + 2LL * (unsigned int)(v8 - 1) + 4)
                      + a3
                      + ((unsigned __int64)*(unsigned __int16 *)(v9 + 2 * v8 + 4) << 16);
                  if ( *(_QWORD *)a8 && (v39 < **(_QWORD **)a8 || v39 > **(_QWORD **)(a8 + 8) - 16LL) )
                    return 3221225512LL;
                  v40 = *(_QWORD *)(a8 + 16);
                  if ( v40 )
                    *(_QWORD *)(v40 + 8LL * v13) = v39;
                }
              }
              else
              {
                v8 = (unsigned int)(v8 + 1);
                v41 = a3 + 16LL * *(unsigned __int16 *)(v9 + 2 * v8 + 4);
                if ( *(_QWORD *)a8 && (v41 < **(_QWORD **)a8 || v41 > **(_QWORD **)(a8 + 8) - 16LL) )
                  return 3221225512LL;
                v42 = *(_QWORD *)(a8 + 16);
                if ( v42 )
                  *(_QWORD *)(v42 + 8LL * v13) = v41;
              }
            }
            else
            {
              LODWORD(v8) = v8 + 2;
            }
          }
          else
          {
            LODWORD(v8) = v8 + 1;
          }
        }
        else if ( v12 == 5 )
        {
          v8 = (unsigned int)(v8 + 2);
          v30 = (_QWORD *)(*(unsigned __int16 *)(v9 + 2LL * (unsigned int)(v8 - 1) + 4)
                         + a3
                         + ((unsigned __int64)*(unsigned __int16 *)(v9 + 2 * v8 + 4) << 16));
          if ( *(_QWORD *)a8
            && ((unsigned __int64)v30 < **(_QWORD **)a8 || (unsigned __int64)v30 > **(_QWORD **)(a8 + 8) - 8LL) )
          {
            return 3221225512LL;
          }
          RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(a5, v13, *v30);
        }
        else if ( (v11 & 0xF00) != 0 )
        {
          v14 = v12 - 1;
          if ( v14 )
          {
            v15 = v14 - 1;
            if ( v15 )
            {
              v16 = v15 - 1;
              if ( v16 )
              {
                if ( v16 != 1 )
                  goto LABEL_77;
                v8 = (unsigned int)(v8 + 1);
                v17 = (_QWORD *)(a3 + 8LL * *(unsigned __int16 *)(v9 + 2 * v8 + 4));
                if ( *(_QWORD *)a8
                  && ((unsigned __int64)v17 < **(_QWORD **)a8 || (unsigned __int64)v17 > **(_QWORD **)(a8 + 8) - 8LL) )
                {
                  return 3221225512LL;
                }
                RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(a5, v13, *v17);
                v21 = *(_QWORD *)(a8 + 16);
                if ( v21 )
                  *(_QWORD *)(v21 + 8LL * v19 + 128) = v20;
              }
              else
              {
                Context = RtlpAmd64GetContextGp<_CONTEXT_FOR_STACKWALK *>(a5, *(_BYTE *)(v9 + 3) & 0xF);
                a5[1] = Context;
                a5[1] = Context - (*(_BYTE *)(v9 + 3) & 0xF0);
              }
            }
            else
            {
              a5[1] += 8 * v13 + 8;
            }
          }
          else
          {
            v8 = (unsigned int)(v8 + 1);
            v23 = *(unsigned __int16 *)(v9 + 2 * v8 + 4);
            if ( v13 )
            {
              v8 = (unsigned int)(v8 + 1);
              v24 = v23 + (*(unsigned __int16 *)(v9 + 2 * v8 + 4) << 16);
            }
            else
            {
              v24 = 8 * v23;
            }
            a5[1] += v24;
          }
        }
        else
        {
          v25 = (_QWORD *)a5[1];
          if ( *(_QWORD *)a8
            && ((unsigned __int64)v25 < **(_QWORD **)a8 || (unsigned __int64)v25 > **(_QWORD **)(a8 + 8) - 8LL) )
          {
            return 3221225512LL;
          }
          RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(a5, v13, *v25);
          v29 = *(_QWORD *)(a8 + 16);
          if ( v29 )
            *(_QWORD *)(v29 + 8LL * v26 + 128) = v27;
          *v28 += 8LL;
        }
LABEL_64:
        v8 = (unsigned int)(v8 + 1);
      }
    }
    if ( (*(_BYTE *)v9 & 0x20) == 0 )
      break;
    if ( (unsigned int)++v46 > 0x20 )
LABEL_77:
      RtlRaiseStatus(3221225727LL);
    a4 = (_DWORD *)(v9 + 2 * ((v10 & 1) + v10 + 2LL));
  }
  if ( !v45 )
  {
    if ( *(_QWORD *)a8 )
    {
      v43 = a5[1];
      if ( v43 < **(_QWORD **)a8 || v43 > **(_QWORD **)(a8 + 8) - 8LL )
        return 3221225512LL;
    }
    v44 = (_QWORD *)a5[1];
    *a5 = *v44;
    a5[1] = v44 + 1;
    RtlpVirtualPopShadowStack<_CONTEXT_FOR_STACKWALK *>(a5);
  }
  if ( a6 )
    *a6 = v45;
  *a7 = a4;
  return 0;
}

```

## disassembly

```asm
0x180117f94  mov     rax, rsp
0x180117f97  mov     [rax+20h], r9
0x180117f9b  mov     [rax+18h], r8
0x180117f9f  mov     [rax+10h], rdx
0x180117fa3  mov     [rax+8], rcx
0x180117fa7  push    rbx
0x180117fa8  push    rsi
0x180117fa9  push    rdi
0x180117faa  push    r14
0x180117fac  push    r15
0x180117fae  sub     rsp, 70h
0x180117fb2  mov     rsi, [rsp+98h+arg_20]
0x180117fba  mov     [rsp+98h+var_38], rsi
0x180117fbf  mov     r14, [rsp+98h+arg_38]
0x180117fc7  mov     r15, r14
0x180117fca  mov     [rsp+98h+var_48], 0
0x180117fd2  xor     edi, edi
0x180117fd4  mov     [rsp+98h+var_78], dil
0x180117fd9  mov     ecx, [rsp+98h+arg_8]
0x180117fe0  sub     ecx, dword ptr [rsp+98h+arg_0]
0x180117fe7  mov     rax, [rsp+98h+arg_18]
0x180117fef  sub     ecx, [rax]
0x180117ff1  mov     [rsp+98h+var_44], ecx
0x180117ff5  mov     ebx, [rax+8]
0x180117ff8  add     rbx, [rsp+98h+arg_0]
0x180118000  mov     [rsp+98h+var_58], rbx
0x180118005  mov     [rsp+98h+var_74], edi
0x180118009  movzx   ecx, byte ptr [rbx+2]
0x18011800d  cmp     edi, ecx
0x18011800f  jnb     loc_18011854B
0x180118015  movzx   ecx, word ptr [rbx+rdi*2+4]
0x18011801a  movzx   eax, cl
0x18011801d  cmp     [rsp+98h+var_44], eax
0x180118021  jb      loc_18011853F
0x180118027  mov     r9d, ecx
0x18011802a  shr     r9d, 8
0x18011802e  mov     eax, r9d
0x180118031  and     eax, 0Fh
0x180118034  shr     r9d, 4
0x180118038  mov     dword ptr [rsp+98h+var_70], r9d
0x18011803d  cmp     eax, 5
0x180118040  ja      loc_1801182B1
0x180118046  jz      loc_180118219
0x18011804c  test    eax, eax
0x18011804e  jz      loc_180118181
0x180118054  sub     eax, 1
0x180118057  jz      loc_180118155
0x18011805d  sub     eax, 1
0x180118060  jz      loc_180118144
0x180118066  sub     eax, 1
0x180118069  jz      loc_180118119
0x18011806f  cmp     eax, 1
0x180118072  jnz     loc_180118613
0x180118078  inc     edi
0x18011807a  mov     dword ptr [rsp+98h+var_40], edi
0x18011807e  movzx   ecx, word ptr [rbx+rdi*2+4]
0x180118083  mov     rax, [rsp+98h+arg_10]
0x18011808b  lea     r10, [rax+rcx*8]
0x18011808f  mov     [rsp+98h+var_60], r10
0x180118094  mov     rax, [r15]
0x180118097  test    rax, rax
0x18011809a  jz      short loc_1801180BB
0x18011809c  cmp     r10, [rax]
0x18011809f  jb      short loc_1801180B1
0x1801180a1  mov     rax, [r14+8]
0x1801180a5  mov     rcx, [rax]
0x1801180a8  sub     rcx, 8
0x1801180ac  cmp     r10, rcx
0x1801180af  jbe     short loc_1801180BB
0x1801180b1  mov     eax, 0C0000028h
0x1801180b6  jmp     loc_180118606
0x1801180bb  xor     eax, eax
0x1801180bd  jmp     short loc_1801180E6
0x1801180bf  mov     r14, [rsp+98h+arg_38]
0x1801180c7  mov     rsi, [rsp+98h+arg_20]
0x1801180cf  mov     rbx, [rsp+98h+var_58]
0x1801180d4  mov     r15, r14
0x1801180d7  mov     r9d, dword ptr [rsp+98h+var_70]
0x1801180dc  mov     r10, [rsp+98h+var_60]
0x1801180e1  mov     rdi, [rsp+98h+var_40]
0x1801180e6  test    eax, eax
0x1801180e8  js      loc_180118606
0x1801180ee  mov     r8, [r10]
0x1801180f1  mov     edx, r9d
0x1801180f4  mov     rcx, rsi
0x1801180f7  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT_FOR_STACKWALK@@@@YAXPEAU_CONTEXT_FOR_STACKWALK@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x1801180fc  mov     rcx, [r14+10h]
0x180118100  test    rcx, rcx
0x180118103  jz      loc_180118538
0x180118109  mov     eax, r9d
0x18011810c  mov     [rcx+rax*8+80h], r10
0x180118114  jmp     loc_180118538
0x180118119  movzx   edx, byte ptr [rbx+3]
0x18011811d  and     edx, 0Fh
0x180118120  mov     rcx, rsi
0x180118123  call    ??$RtlpAmd64GetContextGp@PEAU_CONTEXT_FOR_STACKWALK@@@@YA_KPEAU_CONTEXT_FOR_STACKWALK@@KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64GetContextGp<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,_AMD64_UNWIND_PARAMS const *)
0x180118128  mov     [rsi+8], rax
0x18011812c  movzx   ecx, byte ptr [rbx+3]
0x180118130  mov     edx, 0FFFFFFF0h
0x180118135  and     rcx, rdx
0x180118138  sub     rax, rcx
0x18011813b  mov     [rsi+8], rax
0x18011813f  jmp     loc_180118538
0x180118144  lea     ecx, ds:8[r9*8]
0x18011814c  add     [rsi+8], rcx
0x180118150  jmp     loc_180118538
0x180118155  inc     edi
0x180118157  movzx   edx, word ptr [rbx+rdi*2+4]
0x18011815c  test    r9d, r9d
0x18011815f  jz      short loc_18011816F
0x180118161  inc     edi
0x180118163  movzx   ecx, word ptr [rbx+rdi*2+4]
0x180118168  shl     ecx, 10h
0x18011816b  add     ecx, edx
0x18011816d  jmp     short loc_180118176
0x18011816f  lea     ecx, ds:0[rdx*8]
0x180118176  mov     eax, ecx
0x180118178  add     [rsi+8], rax
0x18011817c  jmp     loc_180118538
0x180118181  lea     r11, [rsi+8]
0x180118185  mov     [rsp+98h+var_68], r11
0x18011818a  mov     r10, [r11]
0x18011818d  mov     [rsp+98h+var_60], r10
0x180118192  mov     rax, [r15]
0x180118195  test    rax, rax
0x180118198  jz      short loc_1801181B7
0x18011819a  cmp     r10, [rax]
0x18011819d  jb      loc_1801180B1
0x1801181a3  mov     rax, [r14+8]
0x1801181a7  mov     rcx, [rax]
0x1801181aa  sub     rcx, 8
0x1801181ae  cmp     r10, rcx
0x1801181b1  ja      loc_1801180B1
0x1801181b7  xor     eax, eax
0x1801181b9  jmp     short loc_1801181E6
0x1801181bb  mov     r14, [rsp+98h+arg_38]
0x1801181c3  mov     rsi, [rsp+98h+arg_20]
0x1801181cb  mov     edi, [rsp+98h+var_74]
0x1801181cf  mov     rbx, [rsp+98h+var_58]
0x1801181d4  mov     r15, r14
0x1801181d7  mov     r9d, dword ptr [rsp+98h+var_70]
0x1801181dc  mov     r11, [rsp+98h+var_68]
0x1801181e1  mov     r10, [rsp+98h+var_60]
0x1801181e6  test    eax, eax
0x1801181e8  js      loc_180118606
0x1801181ee  mov     r8, [r10]
0x1801181f1  mov     edx, r9d
0x1801181f4  mov     rcx, rsi
0x1801181f7  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT_FOR_STACKWALK@@@@YAXPEAU_CONTEXT_FOR_STACKWALK@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x1801181fc  mov     rcx, [r14+10h]
0x180118200  test    rcx, rcx
0x180118203  jz      short loc_180118210
0x180118205  mov     eax, r9d
0x180118208  mov     [rcx+rax*8+80h], r10
0x180118210  add     qword ptr [r11], 8
0x180118214  jmp     loc_180118538
0x180118219  add     edi, 2
0x18011821c  mov     [rsp+98h+var_74], edi
0x180118220  movzx   r8d, word ptr [rbx+rdi*2+4]
0x180118226  shl     r8, 10h
0x18011822a  lea     eax, [rdi-1]
0x18011822d  movzx   edx, word ptr [rbx+rax*2+4]
0x180118232  mov     rax, [rsp+98h+arg_10]
0x18011823a  lea     r8, [rax+r8]
0x18011823e  lea     r8, [rdx+r8]
0x180118242  mov     [rsp+98h+var_68], r8
0x180118247  mov     rax, [r15]
0x18011824a  test    rax, rax
0x18011824d  jz      short loc_18011826C
0x18011824f  cmp     r8, [rax]
0x180118252  jb      loc_1801180B1
0x180118258  mov     rax, [r14+8]
0x18011825c  mov     rcx, [rax]
0x18011825f  sub     rcx, 8
0x180118263  cmp     r8, rcx
0x180118266  ja      loc_1801180B1
0x18011826c  xor     eax, eax
0x18011826e  jmp     short loc_180118296
0x180118270  mov     r14, [rsp+98h+arg_38]
0x180118278  mov     rsi, [rsp+98h+arg_20]
0x180118280  mov     rbx, [rsp+98h+var_58]
0x180118285  mov     r15, r14
0x180118288  mov     r9d, dword ptr [rsp+98h+var_70]
0x18011828d  mov     edi, [rsp+98h+var_74]
0x180118291  mov     r8, [rsp+98h+var_68]
0x180118296  test    eax, eax
0x180118298  js      loc_180118606
0x18011829e  mov     r8, [r8]
0x1801182a1  mov     edx, r9d
0x1801182a4  mov     rcx, rsi
0x1801182a7  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT_FOR_STACKWALK@@@@YAXPEAU_CONTEXT_FOR_STACKWALK@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x1801182ac  jmp     loc_180118538
0x1801182b1  mov     dword ptr [rsp+98h+var_70], r9d
0x1801182b6  sub     eax, 6
0x1801182b9  jz      loc_180118536
0x1801182bf  sub     eax, 1
0x1801182c2  jz      loc_180118531
0x1801182c8  sub     eax, 1
0x1801182cb  jz      loc_1801184A8
0x1801182d1  sub     eax, 1
0x1801182d4  jz      loc_18011840A
0x1801182da  cmp     eax, 1
0x1801182dd  jnz     loc_180118613
0x1801182e3  lea     r10, [rsi+8]
0x1801182e7  mov     [rsp+98h+var_68], r10
0x1801182ec  mov     rax, [r10]
0x1801182ef  lea     r8, [rax+8]
0x1801182f3  test    r9d, r9d
0x1801182f6  cmovz   r8, rax
0x1801182fa  mov     [rsp+98h+var_70], r8
0x1801182ff  neg     r9d
0x180118302  sbb     rdx, rdx
0x180118305  and     edx, 8
0x180118308  add     rdx, 18h
0x18011830c  add     rdx, rax
0x18011830f  mov     [rsp+98h+var_60], rdx
0x180118314  mov     rax, [r15]
0x180118317  test    rax, rax
0x18011831a  jz      short loc_180118339
0x18011831c  cmp     r8, [rax]
0x18011831f  jb      loc_1801180B1
0x180118325  mov     rax, [r14+8]
0x180118329  mov     rcx, [rax]
0x18011832c  sub     rcx, 8
0x180118330  cmp     r8, rcx
0x180118333  ja      loc_1801180B1
0x180118339  xor     eax, eax
0x18011833b  jmp     short loc_180118368
0x18011833d  mov     r14, [rsp+98h+arg_38]
0x180118345  mov     rsi, [rsp+98h+arg_20]
0x18011834d  mov     edi, [rsp+98h+var_74]
0x180118351  mov     rbx, [rsp+98h+var_58]
0x180118356  mov     r15, r14
0x180118359  mov     r8, [rsp+98h+var_70]
0x18011835e  mov     rdx, [rsp+98h+var_60]
0x180118363  mov     r10, [rsp+98h+var_68]
0x180118368  test    eax, eax
0x18011836a  js      loc_180118606
0x180118370  mov     rax, [r15]
0x180118373  test    rax, rax
0x180118376  jz      short loc_180118395
0x180118378  cmp     rdx, [rax]
0x18011837b  jb      loc_1801180B1
0x180118381  mov     rax, [r14+8]
0x180118385  mov     rcx, [rax]
0x180118388  sub     rcx, 8
0x18011838c  cmp     rdx, rcx
0x18011838f  ja      loc_1801180B1
0x180118395  xor     eax, eax
0x180118397  jmp     short loc_1801183C4
0x180118399  mov     r14, [rsp+98h+arg_38]
0x1801183a1  mov     rsi, [rsp+98h+arg_20]
0x1801183a9  mov     edi, [rsp+98h+var_74]
0x1801183ad  mov     rbx, [rsp+98h+var_58]
0x1801183b2  mov     r15, r14
0x1801183b5  mov     r8, [rsp+98h+var_70]
0x1801183ba  mov     rdx, [rsp+98h+var_60]
0x1801183bf  mov     r10, [rsp+98h+var_68]
0x1801183c4  test    eax, eax
0x1801183c6  js      loc_180118606
0x1801183cc  mov     [rsp+98h+var_78], 1
0x1801183d1  mov     rcx, [r8]
0x1801183d4  mov     rax, [rsp+98h+var_38]
0x1801183d9  mov     [rax], rcx
0x1801183dc  mov     rax, [rdx]
0x1801183df  mov     [r10], rax
0x1801183e2  xor     ecx, ecx
0x1801183e4  lea     rdx, RtlpContinuationContextMachineFrameEntries
0x1801183eb  cmp     rbx, [rdx+rcx*8]
0x1801183ef  jz      short loc_1801183FD
0x1801183f1  inc     ecx
0x1801183f3  cmp     ecx, 2
0x1801183f6  jb      short loc_1801183E4
0x1801183f8  jmp     loc_180118538
0x1801183fd  mov     rcx, rsi
0x180118400  call    ??$RtlpVirtualPopShadowStack@PEAU_CONTEXT_FOR_STACKWALK@@@@YAXPEAU_CONTEXT_FOR_STACKWALK@@KK@Z; RtlpVirtualPopShadowStack<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,ulong)
0x180118405  jmp     loc_180118538
0x18011840a  add     edi, 2
0x18011840d  mov     [rsp+98h+var_74], edi
0x180118411  movzx   r8d, word ptr [rbx+rdi*2+4]
0x180118417  shl     r8, 10h
0x18011841b  lea     eax, [rdi-1]
0x18011841e  movzx   edx, word ptr [rbx+rax*2+4]
0x180118423  mov     rax, [rsp+98h+arg_10]
0x18011842b  lea     r8, [rax+r8]
0x18011842f  lea     r8, [rdx+r8]
0x180118433  mov     [rsp+98h+var_68], r8
0x180118438  mov     rax, [r15]
0x18011843b  test    rax, rax
0x18011843e  jz      short loc_18011845D
0x180118440  cmp     r8, [rax]
0x180118443  jb      loc_1801180B1
0x180118449  mov     rax, [r14+8]
0x18011844d  mov     rcx, [rax]
0x180118450  sub     rcx, 10h
0x180118454  cmp     r8, rcx
0x180118457  ja      loc_1801180B1
0x18011845d  xor     eax, eax
0x18011845f  jmp     short loc_180118487
0x180118461  mov     r14, [rsp+98h+arg_38]
  ... truncated ...
```
