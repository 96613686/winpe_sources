# TokenBindingVerifyMessage

- ea: `0x180023760`
- end: `0x180023a1f`
- name: `TokenBindingVerifyMessage`
- size: `703`
- prototype: `__int64 __usercall@<rax>(unsigned __int8 *@<rcx>, int, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180007bd8`
- `0x18000fe7c`
- `0x18000ff44`
- `0x1800100b4`
- `0x180010138`
- `0x18001f008`
- `0x18001f058`
- `0x180023760`
- `0x180023a28`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x1800237fc`
- `HAL!KeQueryPerformanceCounter` at `0x180023825`
- `HAL!KeQueryPerformanceCounter` at `0x1800237fc`
- `HAL!KeQueryPerformanceCounter` at `0x180023825`

## pseudocode

```c
__int64 __fastcall TokenBindingVerifyMessage(
        unsigned __int8 *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        _QWORD *a6)
{
  int v6; // r14d
  unsigned __int64 v7; // r15
  unsigned int v9; // edi
  int v11; // ebx
  unsigned int v12; // esi
  LARGE_INTEGER PerformanceCounter; // rbx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int v17; // edi
  LARGE_INTEGER v18; // rax
  unsigned __int8 v19; // dl
  unsigned __int8 v20; // cl
  int v22; // eax
  bool v23; // zf
  unsigned int v24; // ecx
  __int64 v25; // r14
  unsigned int v26; // edx
  __int64 v27; // r13
  unsigned int v28; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-1Ch] BYREF
  unsigned int v30; // [rsp+48h] [rbp-18h]
  _QWORD v31[2]; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int8 v32; // [rsp+A0h] [rbp+40h] BYREF
  int v33; // [rsp+B0h] [rbp+50h]

  v33 = a3;
  v6 = 0;
  v7 = a2;
  v31[0] = 0;
  v32 = 0;
  v9 = a3;
  v11 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 3), 20, a3, a2, a3, a5);
  if ( !a1 || !(_DWORD)v7 || !a4 || v11 != 32 || !a6 )
    return 2148073511LL;
  v12 = 0;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v17 = TBValidateKeyType(v9, v14, v15, v16);
  if ( !v17 )
  {
    if ( v7 >= 2 )
    {
      v22 = a1[1];
      v23 = (v22 | (unsigned __int16)(*(_WORD *)a1 << 8)) == 0;
      v24 = v22 | (unsigned __int16)(*(_WORD *)a1 << 8);
      v28 = 2;
      v29 = v24;
      if ( v23 || v7 != v24 + 2LL )
        return 2148073476LL;
      while ( v28 < (unsigned int)v7 )
      {
        v17 = VerifyTokenBinding((__int64)a1, &v28, (unsigned int)v7, v33, a4, 0x20u, &v29, &v32);
        if ( v17 )
          goto LABEL_12;
        if ( !v32 )
        {
          v6 += v29;
          ++v12;
        }
      }
      if ( (unsigned int)TBAllocateBuffer(v31, v6 + 32 * v12 + 16) )
      {
        v25 = v31[0];
        v26 = 32 * v12 + 16;
        v28 = 2;
        *(_DWORD *)v31[0] = v12;
        *(_QWORD *)(v25 + 8) = v25 + 16;
        v12 = 0;
LABEL_25:
        v30 = v26;
        while ( v28 < (unsigned int)v7 )
        {
          v27 = 32LL * v12;
          *(_QWORD *)(*(_QWORD *)(v25 + 8) + v27 + 8) = v25 + v26;
          *(_QWORD *)(*(_QWORD *)(v25 + 8) + v27 + 24) = 0;
          *(_DWORD *)(*(_QWORD *)(v25 + 8) + v27 + 16) = 0;
          *(_DWORD *)(*(_QWORD *)(v25 + 8) + v27 + 20) = 0;
          v17 = _CopyTokenBinding(
                  a1,
                  &v28,
                  0,
                  *(struct TOKENBINDING_IDENTIFIER **)(v27 + *(_QWORD *)(v25 + 8) + 8),
                  &v29,
                  (enum TOKENBINDING_TYPE *)(v27 + *(_QWORD *)(v25 + 8)),
                  &v32);
          if ( v17 )
            goto LABEL_12;
          v26 = v30;
          if ( !v32 )
          {
            v26 = v29 + v30;
            ++v12;
            *(_DWORD *)(*(_QWORD *)(v25 + 8) + v27 + 4) = v29;
            goto LABEL_25;
          }
        }
        v31[0] = 0;
        *a6 = v25;
      }
      else
      {
        v17 = -2146893056;
      }
    }
    else
    {
      v17 = -2146893819;
    }
  }
LABEL_12:
  v18 = KeQueryPerformanceCounter(0);
  LogKsecTokenBindingVerifyMessage(v20, v19, v33, v12, PerformanceCounter, v18, v17);
  TBFreeBuffer(v31);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 21, WPP_0c97cf3ebcf83aea482108bb01090baf_Traceguids, v17);
  return v17;
}

```

## disassembly

```asm
0x180023760  mov     [rsp-38h+arg_8], rbx
0x180023765  mov     [rsp-38h+arg_10], r8d
0x18002376a  push    rbp
0x18002376b  push    rsi
0x18002376c  push    rdi
0x18002376d  push    r12
0x18002376f  push    r13
0x180023771  push    r14
0x180023773  push    r15
0x180023775  mov     rbp, rsp
0x180023778  sub     rsp, 60h
0x18002377c  xor     r14d, r14d
0x18002377f  mov     r15d, edx
0x180023782  mov     [rbp+var_10], r14
0x180023786  mov     r13, r9
0x180023789  mov     [rbp+arg_0], r14b
0x18002378d  mov     edi, r8d
0x180023790  mov     r12, rcx
0x180023793  mov     rcx, cs:WPP_GLOBAL_Control
0x18002379a  lea     rax, WPP_GLOBAL_Control
0x1800237a1  mov     ebx, [rbp+arg_20]
0x1800237a4  cmp     rcx, rax
0x1800237a7  jz      short loc_1800237C9
0x1800237a9  mov     eax, [rcx+2Ch]
0x1800237ac  test    al, 4
0x1800237ae  jz      short loc_1800237C9
0x1800237b0  mov     rcx, [rcx+18h]
0x1800237b4  lea     edx, [r14+14h]
0x1800237b8  mov     dword ptr [rsp+60h+var_38], ebx
0x1800237bc  mov     r9d, r15d
0x1800237bf  mov     dword ptr [rsp+60h+var_40], r8d
0x1800237c4  call    WPP_SF_ddd
0x1800237c9  test    r12, r12
0x1800237cc  jz      loc_180023A01
0x1800237d2  test    r15d, r15d
0x1800237d5  jz      loc_180023A01
0x1800237db  test    r13, r13
0x1800237de  jz      loc_180023A01
0x1800237e4  cmp     ebx, 20h ; ' '
0x1800237e7  jnz     loc_180023A01
0x1800237ed  cmp     [rbp+arg_28], r14
0x1800237f1  jz      loc_180023A01
0x1800237f7  xor     ecx, ecx; PerformanceFrequency
0x1800237f9  mov     esi, r14d
0x1800237fc  call    cs:__imp_KeQueryPerformanceCounter
0x180023803  nop     dword ptr [rax+rax+00h]
0x180023808  mov     ecx, edi
0x18002380a  mov     rbx, rax
0x18002380d  call    TBValidateKeyType
0x180023812  mov     edi, eax
0x180023814  test    eax, eax
0x180023816  jnz     short loc_180023823
0x180023818  cmp     r15, 2
0x18002381c  jnb     short loc_18002388D
0x18002381e  mov     edi, 80090005h
0x180023823  xor     ecx, ecx; PerformanceFrequency
0x180023825  call    cs:__imp_KeQueryPerformanceCounter
0x18002382c  nop     dword ptr [rax+rax+00h]
0x180023831  mov     r8b, byte ptr [rbp+arg_10]; unsigned __int8
0x180023835  mov     r9d, esi; unsigned int
0x180023838  mov     dword ptr [rsp+60h+var_30], edi; int
0x18002383c  mov     qword ptr [rsp+60h+var_38], rax; union _LARGE_INTEGER
0x180023841  mov     qword ptr [rsp+60h+var_40], rbx; union _LARGE_INTEGER
0x180023846  call    ?LogKsecTokenBindingVerifyMessage@@YAXEEEKT_LARGE_INTEGER@@0J@Z; LogKsecTokenBindingVerifyMessage(uchar,uchar,uchar,ulong,_LARGE_INTEGER,_LARGE_INTEGER,long)
0x18002384b  lea     rcx, [rbp+var_10]
0x18002384f  call    TBFreeBuffer
0x180023854  mov     rcx, cs:WPP_GLOBAL_Control
0x18002385b  lea     rax, WPP_GLOBAL_Control
0x180023862  cmp     rcx, rax
0x180023865  jz      short loc_180023886
0x180023867  mov     eax, [rcx+2Ch]
0x18002386a  test    al, 4
0x18002386c  jz      short loc_180023886
0x18002386e  mov     rcx, [rcx+18h]
0x180023872  lea     r8, WPP_0c97cf3ebcf83aea482108bb01090baf_Traceguids
0x180023879  mov     edx, 15h
0x18002387e  mov     r9d, edi
0x180023881  call    WPP_SF_D
0x180023886  mov     eax, edi
0x180023888  jmp     loc_180023A06
0x18002388d  movzx   eax, word ptr [r12]
0x180023892  shl     ax, 8
0x180023896  movzx   ecx, ax
0x180023899  movzx   eax, byte ptr [r12+1]
0x18002389f  or      ecx, eax
0x1800238a1  mov     [rbp+var_20], 2
0x1800238a8  mov     [rbp+var_1C], ecx
0x1800238ab  jz      loc_1800239FA
0x1800238b1  mov     eax, ecx
0x1800238b3  add     rax, 2
0x1800238b7  cmp     r15, rax
0x1800238ba  jnz     loc_1800239FA
0x1800238c0  cmp     [rbp+var_20], r15d
0x1800238c4  jnb     short loc_18002390F
0x1800238c6  mov     r9d, [rbp+arg_10]
0x1800238ca  lea     rax, [rbp+arg_0]
0x1800238ce  mov     [rsp+60h+var_28], rax
0x1800238d3  lea     rdx, [rbp+var_20]
0x1800238d7  lea     rax, [rbp+var_1C]
0x1800238db  mov     r8d, r15d
0x1800238de  mov     [rsp+60h+var_30], rax
0x1800238e3  mov     rcx, r12
0x1800238e6  mov     dword ptr [rsp+60h+var_38], 20h ; ' '
0x1800238ee  mov     qword ptr [rsp+60h+var_40], r13
0x1800238f3  call    _VerifyTokenBinding
0x1800238f8  mov     edi, eax
0x1800238fa  test    eax, eax
0x1800238fc  jnz     loc_180023823
0x180023902  cmp     [rbp+arg_0], al
0x180023905  jnz     short loc_1800238C0
0x180023907  add     r14d, [rbp+var_1C]
0x18002390b  inc     esi
0x18002390d  jmp     short loc_1800238C0
0x18002390f  mov     r13d, esi
0x180023912  lea     rcx, [rbp+var_10]
0x180023916  shl     r13d, 5
0x18002391a  lea     edx, [r13+10h]
0x18002391e  add     edx, r14d
0x180023921  call    TBAllocateBuffer
0x180023926  xor     r8d, r8d; unsigned int
0x180023929  test    eax, eax
0x18002392b  jnz     short loc_180023937
0x18002392d  mov     edi, 80090300h
0x180023932  jmp     loc_180023823
0x180023937  mov     r14, [rbp+var_10]
0x18002393b  lea     edx, [r13+10h]
0x18002393f  mov     [rbp+var_20], 2
0x180023946  mov     [r14], esi
0x180023949  lea     rax, [r14+10h]
0x18002394d  mov     [r14+8], rax
0x180023951  mov     esi, r8d
0x180023954  mov     [rbp+var_18], edx
0x180023957  cmp     [rbp+var_20], r15d
0x18002395b  jnb     loc_1800239EA
0x180023961  mov     rax, [r14+8]
0x180023965  mov     ecx, edx
0x180023967  lea     rdx, [rbp+var_20]; unsigned int *
0x18002396b  add     rcx, r14
0x18002396e  mov     r13d, esi
0x180023971  shl     r13, 5
0x180023975  mov     [rax+r13+8], rcx
0x18002397a  mov     rcx, r12; unsigned __int8 *
0x18002397d  mov     rax, [r14+8]
0x180023981  mov     [rax+r13+18h], r8
0x180023986  mov     rax, [r14+8]
0x18002398a  mov     [rax+r13+10h], r8d
0x18002398f  mov     rax, [r14+8]
0x180023993  mov     [rax+r13+14h], r8d
0x180023998  lea     rax, [rbp+arg_0]
0x18002399c  mov     r9, [r14+8]
0x1800239a0  mov     [rsp+60h+var_30], rax; unsigned __int8 *
0x1800239a5  add     r9, r13
0x1800239a8  mov     qword ptr [rsp+60h+var_38], r9; enum TOKENBINDING_TYPE *
0x1800239ad  lea     rax, [rbp+var_1C]
0x1800239b1  mov     qword ptr [rsp+60h+var_40], rax; unsigned int *
0x1800239b6  mov     r9, [r9+8]; struct TOKENBINDING_IDENTIFIER *
0x1800239ba  call    ?_CopyTokenBinding@@YAJPEAEPEAKKPEAUTOKENBINDING_IDENTIFIER@@1PEAW4TOKENBINDING_TYPE@@0@Z; _CopyTokenBinding(uchar *,ulong *,ulong,TOKENBINDING_IDENTIFIER *,ulong *,TOKENBINDING_TYPE *,uchar *)
0x1800239bf  xor     r8d, r8d
0x1800239c2  mov     edi, eax
0x1800239c4  test    eax, eax
0x1800239c6  jnz     loc_180023823
0x1800239cc  mov     edx, [rbp+var_18]
0x1800239cf  cmp     [rbp+arg_0], r8b
0x1800239d3  jnz     short loc_180023957
0x1800239d5  mov     ecx, [rbp+var_1C]
0x1800239d8  add     edx, ecx
0x1800239da  mov     rax, [r14+8]
0x1800239de  inc     esi
0x1800239e0  mov     [rax+r13+4], ecx
0x1800239e5  jmp     loc_180023954
0x1800239ea  mov     rax, [rbp+arg_28]
0x1800239ee  mov     [rbp+var_10], r8
0x1800239f2  mov     [rax], r14
0x1800239f5  jmp     loc_180023823
0x1800239fa  mov     eax, 80090004h
0x1800239ff  jmp     short loc_180023A06
0x180023a01  mov     eax, 80090027h
0x180023a06  mov     rbx, [rsp+60h+arg_8]
0x180023a0e  add     rsp, 60h
0x180023a12  pop     r15
0x180023a14  pop     r14
0x180023a16  pop     r13
0x180023a18  pop     r12
0x180023a1a  pop     rdi
0x180023a1b  pop     rsi
0x180023a1c  pop     rbp
0x180023a1d  retn
```
