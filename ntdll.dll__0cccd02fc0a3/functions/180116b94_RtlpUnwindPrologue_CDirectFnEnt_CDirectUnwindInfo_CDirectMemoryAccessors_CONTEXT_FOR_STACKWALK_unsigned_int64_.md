# RtlpUnwindPrologue<CDirectFnEnt,CDirectUnwindInfo,CDirectMemoryAccessors,_CONTEXT_FOR_STACKWALK *>(unsigned __int64,unsigned __int64,unsigned __int64,CDirectFnEnt,_CONTEXT_FOR_STACKWALK *,uchar *,CDirectFnEnt *,_AMD64_UNWIND_PARAMS *)

- ea: `0x180116b94`
- end: `0x18011721e`
- name: `??$RtlpUnwindPrologue@VCDirectFnEnt@@VCDirectUnwindInfo@@VCDirectMemoryAccessors@@PEAU_CONTEXT_FOR_STACKWALK@@@@YAJ_K00VCDirectFnEnt@@PEAU_CONTEXT_FOR_STACKWALK@@PEAEPEAV0@PEAU_AMD64_UNWIND_PARAMS@@@Z`
- size: `1674`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800881ec`

## callees

- `0x180053990`
- `0x1800e1fc8`
- `0x1800f80c4`
- `0x180116b94`
- `0x1801497fc`
- `0x180149874`

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
0x180116b94  mov     rax, rsp
0x180116b97  mov     [rax+20h], r9
0x180116b9b  mov     [rax+18h], r8
0x180116b9f  mov     [rax+10h], rdx
0x180116ba3  mov     [rax+8], rcx
0x180116ba7  push    rbx
0x180116ba8  push    rsi
0x180116ba9  push    rdi
0x180116baa  push    r14
0x180116bac  push    r15
0x180116bae  sub     rsp, 70h
0x180116bb2  mov     rsi, [rsp+98h+arg_20]
0x180116bba  mov     [rsp+98h+var_38], rsi
0x180116bbf  mov     r14, [rsp+98h+arg_38]
0x180116bc7  mov     r15, r14
0x180116bca  mov     [rsp+98h+var_48], 0
0x180116bd2  xor     edi, edi
0x180116bd4  mov     [rsp+98h+var_78], dil
0x180116bd9  mov     ecx, [rsp+98h+arg_8]
0x180116be0  sub     ecx, dword ptr [rsp+98h+arg_0]
0x180116be7  mov     rax, [rsp+98h+arg_18]
0x180116bef  sub     ecx, [rax]
0x180116bf1  mov     [rsp+98h+var_44], ecx
0x180116bf5  mov     ebx, [rax+8]
0x180116bf8  add     rbx, [rsp+98h+arg_0]
0x180116c00  mov     [rsp+98h+var_58], rbx
0x180116c05  mov     [rsp+98h+var_74], edi
0x180116c09  movzx   ecx, byte ptr [rbx+2]
0x180116c0d  cmp     edi, ecx
0x180116c0f  jnb     loc_18011714B
0x180116c15  movzx   ecx, word ptr [rbx+rdi*2+4]
0x180116c1a  movzx   eax, cl
0x180116c1d  cmp     [rsp+98h+var_44], eax
0x180116c21  jb      loc_18011713F
0x180116c27  mov     r9d, ecx
0x180116c2a  shr     r9d, 8
0x180116c2e  mov     eax, r9d
0x180116c31  and     eax, 0Fh
0x180116c34  shr     r9d, 4
0x180116c38  mov     dword ptr [rsp+98h+var_70], r9d
0x180116c3d  cmp     eax, 5
0x180116c40  ja      loc_180116EB1
0x180116c46  jz      loc_180116E19
0x180116c4c  test    eax, eax
0x180116c4e  jz      loc_180116D81
0x180116c54  sub     eax, 1
0x180116c57  jz      loc_180116D55
0x180116c5d  sub     eax, 1
0x180116c60  jz      loc_180116D44
0x180116c66  sub     eax, 1
0x180116c69  jz      loc_180116D19
0x180116c6f  cmp     eax, 1
0x180116c72  jnz     loc_180117213
0x180116c78  inc     edi
0x180116c7a  mov     dword ptr [rsp+98h+var_40], edi
0x180116c7e  movzx   ecx, word ptr [rbx+rdi*2+4]
0x180116c83  mov     rax, [rsp+98h+arg_10]
0x180116c8b  lea     r10, [rax+rcx*8]
0x180116c8f  mov     [rsp+98h+var_60], r10
0x180116c94  mov     rax, [r15]
0x180116c97  test    rax, rax
0x180116c9a  jz      short loc_180116CBB
0x180116c9c  cmp     r10, [rax]
0x180116c9f  jb      short loc_180116CB1
0x180116ca1  mov     rax, [r14+8]
0x180116ca5  mov     rcx, [rax]
0x180116ca8  sub     rcx, 8
0x180116cac  cmp     r10, rcx
0x180116caf  jbe     short loc_180116CBB
0x180116cb1  mov     eax, 0C0000028h
0x180116cb6  jmp     loc_180117206
0x180116cbb  xor     eax, eax
0x180116cbd  jmp     short loc_180116CE6
0x180116cbf  mov     r14, [rsp+98h+arg_38]
0x180116cc7  mov     rsi, [rsp+98h+arg_20]
0x180116ccf  mov     rbx, [rsp+98h+var_58]
0x180116cd4  mov     r15, r14
0x180116cd7  mov     r9d, dword ptr [rsp+98h+var_70]
0x180116cdc  mov     r10, [rsp+98h+var_60]
0x180116ce1  mov     rdi, [rsp+98h+var_40]
0x180116ce6  test    eax, eax
0x180116ce8  js      loc_180117206
0x180116cee  mov     r8, [r10]
0x180116cf1  mov     edx, r9d
0x180116cf4  mov     rcx, rsi
0x180116cf7  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT_FOR_STACKWALK@@@@YAXPEAU_CONTEXT_FOR_STACKWALK@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x180116cfc  mov     rcx, [r14+10h]
0x180116d00  test    rcx, rcx
0x180116d03  jz      loc_180117138
0x180116d09  mov     eax, r9d
0x180116d0c  mov     [rcx+rax*8+80h], r10
0x180116d14  jmp     loc_180117138
0x180116d19  movzx   edx, byte ptr [rbx+3]
0x180116d1d  and     edx, 0Fh
0x180116d20  mov     rcx, rsi
0x180116d23  call    ??$RtlpAmd64GetContextGp@PEAU_CONTEXT_FOR_STACKWALK@@@@YA_KPEAU_CONTEXT_FOR_STACKWALK@@KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64GetContextGp<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,_AMD64_UNWIND_PARAMS const *)
0x180116d28  mov     [rsi+8], rax
0x180116d2c  movzx   ecx, byte ptr [rbx+3]
0x180116d30  mov     edx, 0FFFFFFF0h
0x180116d35  and     rcx, rdx
0x180116d38  sub     rax, rcx
0x180116d3b  mov     [rsi+8], rax
0x180116d3f  jmp     loc_180117138
0x180116d44  lea     ecx, ds:8[r9*8]
0x180116d4c  add     [rsi+8], rcx
0x180116d50  jmp     loc_180117138
0x180116d55  inc     edi
0x180116d57  movzx   edx, word ptr [rbx+rdi*2+4]
0x180116d5c  test    r9d, r9d
0x180116d5f  jz      short loc_180116D6F
0x180116d61  inc     edi
0x180116d63  movzx   ecx, word ptr [rbx+rdi*2+4]
0x180116d68  shl     ecx, 10h
0x180116d6b  add     ecx, edx
0x180116d6d  jmp     short loc_180116D76
0x180116d6f  lea     ecx, ds:0[rdx*8]
0x180116d76  mov     eax, ecx
0x180116d78  add     [rsi+8], rax
0x180116d7c  jmp     loc_180117138
0x180116d81  lea     r11, [rsi+8]
0x180116d85  mov     [rsp+98h+var_68], r11
0x180116d8a  mov     r10, [r11]
0x180116d8d  mov     [rsp+98h+var_60], r10
0x180116d92  mov     rax, [r15]
0x180116d95  test    rax, rax
0x180116d98  jz      short loc_180116DB7
0x180116d9a  cmp     r10, [rax]
0x180116d9d  jb      loc_180116CB1
0x180116da3  mov     rax, [r14+8]
0x180116da7  mov     rcx, [rax]
0x180116daa  sub     rcx, 8
0x180116dae  cmp     r10, rcx
0x180116db1  ja      loc_180116CB1
0x180116db7  xor     eax, eax
0x180116db9  jmp     short loc_180116DE6
0x180116dbb  mov     r14, [rsp+98h+arg_38]
0x180116dc3  mov     rsi, [rsp+98h+arg_20]
0x180116dcb  mov     edi, [rsp+98h+var_74]
0x180116dcf  mov     rbx, [rsp+98h+var_58]
0x180116dd4  mov     r15, r14
0x180116dd7  mov     r9d, dword ptr [rsp+98h+var_70]
0x180116ddc  mov     r11, [rsp+98h+var_68]
0x180116de1  mov     r10, [rsp+98h+var_60]
0x180116de6  test    eax, eax
0x180116de8  js      loc_180117206
0x180116dee  mov     r8, [r10]
0x180116df1  mov     edx, r9d
0x180116df4  mov     rcx, rsi
0x180116df7  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT_FOR_STACKWALK@@@@YAXPEAU_CONTEXT_FOR_STACKWALK@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x180116dfc  mov     rcx, [r14+10h]
0x180116e00  test    rcx, rcx
0x180116e03  jz      short loc_180116E10
0x180116e05  mov     eax, r9d
0x180116e08  mov     [rcx+rax*8+80h], r10
0x180116e10  add     qword ptr [r11], 8
0x180116e14  jmp     loc_180117138
0x180116e19  add     edi, 2
0x180116e1c  mov     [rsp+98h+var_74], edi
0x180116e20  movzx   r8d, word ptr [rbx+rdi*2+4]
0x180116e26  shl     r8, 10h
0x180116e2a  lea     eax, [rdi-1]
0x180116e2d  movzx   edx, word ptr [rbx+rax*2+4]
0x180116e32  mov     rax, [rsp+98h+arg_10]
0x180116e3a  lea     r8, [rax+r8]
0x180116e3e  lea     r8, [rdx+r8]
0x180116e42  mov     [rsp+98h+var_68], r8
0x180116e47  mov     rax, [r15]
0x180116e4a  test    rax, rax
0x180116e4d  jz      short loc_180116E6C
0x180116e4f  cmp     r8, [rax]
0x180116e52  jb      loc_180116CB1
0x180116e58  mov     rax, [r14+8]
0x180116e5c  mov     rcx, [rax]
0x180116e5f  sub     rcx, 8
0x180116e63  cmp     r8, rcx
0x180116e66  ja      loc_180116CB1
0x180116e6c  xor     eax, eax
0x180116e6e  jmp     short loc_180116E96
0x180116e70  mov     r14, [rsp+98h+arg_38]
0x180116e78  mov     rsi, [rsp+98h+arg_20]
0x180116e80  mov     rbx, [rsp+98h+var_58]
0x180116e85  mov     r15, r14
0x180116e88  mov     r9d, dword ptr [rsp+98h+var_70]
0x180116e8d  mov     edi, [rsp+98h+var_74]
0x180116e91  mov     r8, [rsp+98h+var_68]
0x180116e96  test    eax, eax
0x180116e98  js      loc_180117206
0x180116e9e  mov     r8, [r8]
0x180116ea1  mov     edx, r9d
0x180116ea4  mov     rcx, rsi
0x180116ea7  call    ??$RtlpAmd64SetContextGp@PEAU_CONTEXT_FOR_STACKWALK@@@@YAXPEAU_CONTEXT_FOR_STACKWALK@@K_KPEBU_AMD64_UNWIND_PARAMS@@@Z; RtlpAmd64SetContextGp<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,unsigned __int64,_AMD64_UNWIND_PARAMS const *)
0x180116eac  jmp     loc_180117138
0x180116eb1  mov     dword ptr [rsp+98h+var_70], r9d
0x180116eb6  sub     eax, 6
0x180116eb9  jz      loc_180117136
0x180116ebf  sub     eax, 1
0x180116ec2  jz      loc_180117131
0x180116ec8  sub     eax, 1
0x180116ecb  jz      loc_1801170A8
0x180116ed1  sub     eax, 1
0x180116ed4  jz      loc_18011700A
0x180116eda  cmp     eax, 1
0x180116edd  jnz     loc_180117213
0x180116ee3  lea     r10, [rsi+8]
0x180116ee7  mov     [rsp+98h+var_68], r10
0x180116eec  mov     rax, [r10]
0x180116eef  lea     r8, [rax+8]
0x180116ef3  test    r9d, r9d
0x180116ef6  cmovz   r8, rax
0x180116efa  mov     [rsp+98h+var_70], r8
0x180116eff  neg     r9d
0x180116f02  sbb     rdx, rdx
0x180116f05  and     edx, 8
0x180116f08  add     rdx, 18h
0x180116f0c  add     rdx, rax
0x180116f0f  mov     [rsp+98h+var_60], rdx
0x180116f14  mov     rax, [r15]
0x180116f17  test    rax, rax
0x180116f1a  jz      short loc_180116F39
0x180116f1c  cmp     r8, [rax]
0x180116f1f  jb      loc_180116CB1
0x180116f25  mov     rax, [r14+8]
0x180116f29  mov     rcx, [rax]
0x180116f2c  sub     rcx, 8
0x180116f30  cmp     r8, rcx
0x180116f33  ja      loc_180116CB1
0x180116f39  xor     eax, eax
0x180116f3b  jmp     short loc_180116F68
0x180116f3d  mov     r14, [rsp+98h+arg_38]
0x180116f45  mov     rsi, [rsp+98h+arg_20]
0x180116f4d  mov     edi, [rsp+98h+var_74]
0x180116f51  mov     rbx, [rsp+98h+var_58]
0x180116f56  mov     r15, r14
0x180116f59  mov     r8, [rsp+98h+var_70]
0x180116f5e  mov     rdx, [rsp+98h+var_60]
0x180116f63  mov     r10, [rsp+98h+var_68]
0x180116f68  test    eax, eax
0x180116f6a  js      loc_180117206
0x180116f70  mov     rax, [r15]
0x180116f73  test    rax, rax
0x180116f76  jz      short loc_180116F95
0x180116f78  cmp     rdx, [rax]
0x180116f7b  jb      loc_180116CB1
0x180116f81  mov     rax, [r14+8]
0x180116f85  mov     rcx, [rax]
0x180116f88  sub     rcx, 8
0x180116f8c  cmp     rdx, rcx
0x180116f8f  ja      loc_180116CB1
0x180116f95  xor     eax, eax
0x180116f97  jmp     short loc_180116FC4
0x180116f99  mov     r14, [rsp+98h+arg_38]
0x180116fa1  mov     rsi, [rsp+98h+arg_20]
0x180116fa9  mov     edi, [rsp+98h+var_74]
0x180116fad  mov     rbx, [rsp+98h+var_58]
0x180116fb2  mov     r15, r14
0x180116fb5  mov     r8, [rsp+98h+var_70]
0x180116fba  mov     rdx, [rsp+98h+var_60]
0x180116fbf  mov     r10, [rsp+98h+var_68]
0x180116fc4  test    eax, eax
0x180116fc6  js      loc_180117206
0x180116fcc  mov     [rsp+98h+var_78], 1
0x180116fd1  mov     rcx, [r8]
0x180116fd4  mov     rax, [rsp+98h+var_38]
0x180116fd9  mov     [rax], rcx
0x180116fdc  mov     rax, [rdx]
0x180116fdf  mov     [r10], rax
0x180116fe2  xor     ecx, ecx
0x180116fe4  lea     rdx, RtlpContinuationContextMachineFrameEntries
0x180116feb  cmp     rbx, [rdx+rcx*8]
0x180116fef  jz      short loc_180116FFD
0x180116ff1  inc     ecx
0x180116ff3  cmp     ecx, 2
0x180116ff6  jb      short loc_180116FE4
0x180116ff8  jmp     loc_180117138
0x180116ffd  mov     rcx, rsi
0x180117000  call    ??$RtlpVirtualPopShadowStack@PEAU_CONTEXT_FOR_STACKWALK@@@@YAXPEAU_CONTEXT_FOR_STACKWALK@@KK@Z; RtlpVirtualPopShadowStack<_CONTEXT_FOR_STACKWALK *>(_CONTEXT_FOR_STACKWALK *,ulong,ulong)
0x180117005  jmp     loc_180117138
0x18011700a  add     edi, 2
0x18011700d  mov     [rsp+98h+var_74], edi
0x180117011  movzx   r8d, word ptr [rbx+rdi*2+4]
0x180117017  shl     r8, 10h
0x18011701b  lea     eax, [rdi-1]
0x18011701e  movzx   edx, word ptr [rbx+rax*2+4]
0x180117023  mov     rax, [rsp+98h+arg_10]
0x18011702b  lea     r8, [rax+r8]
0x18011702f  lea     r8, [rdx+r8]
0x180117033  mov     [rsp+98h+var_68], r8
0x180117038  mov     rax, [r15]
0x18011703b  test    rax, rax
0x18011703e  jz      short loc_18011705D
0x180117040  cmp     r8, [rax]
0x180117043  jb      loc_180116CB1
0x180117049  mov     rax, [r14+8]
0x18011704d  mov     rcx, [rax]
0x180117050  sub     rcx, 10h
0x180117054  cmp     r8, rcx
0x180117057  ja      loc_180116CB1
0x18011705d  xor     eax, eax
0x18011705f  jmp     short loc_180117087
0x180117061  mov     r14, [rsp+98h+arg_38]
  ... truncated ...
```
