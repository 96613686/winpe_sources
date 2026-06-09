# TokenBindingVerifyMessage

- ea: `0x1800237b0`
- end: `0x180023a6f`
- name: `TokenBindingVerifyMessage`
- size: `703`
- prototype: `__int64 __usercall@<rax>(unsigned __int8 *@<rcx>, int, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180007bd8`
- `0x18000fedc`
- `0x18000ffa4`
- `0x180010114`
- `0x180010198`
- `0x18001f008`
- `0x18001f058`
- `0x1800237b0`
- `0x180023a78`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x18002384c`
- `HAL!KeQueryPerformanceCounter` at `0x180023875`
- `HAL!KeQueryPerformanceCounter` at `0x18002384c`
- `HAL!KeQueryPerformanceCounter` at `0x180023875`

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
0x1800237b0  mov     [rsp-38h+arg_8], rbx
0x1800237b5  mov     [rsp-38h+arg_10], r8d
0x1800237ba  push    rbp
0x1800237bb  push    rsi
0x1800237bc  push    rdi
0x1800237bd  push    r12
0x1800237bf  push    r13
0x1800237c1  push    r14
0x1800237c3  push    r15
0x1800237c5  mov     rbp, rsp
0x1800237c8  sub     rsp, 60h
0x1800237cc  xor     r14d, r14d
0x1800237cf  mov     r15d, edx
0x1800237d2  mov     [rbp+var_10], r14
0x1800237d6  mov     r13, r9
0x1800237d9  mov     [rbp+arg_0], r14b
0x1800237dd  mov     edi, r8d
0x1800237e0  mov     r12, rcx
0x1800237e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800237ea  lea     rax, WPP_GLOBAL_Control
0x1800237f1  mov     ebx, [rbp+arg_20]
0x1800237f4  cmp     rcx, rax
0x1800237f7  jz      short loc_180023819
0x1800237f9  mov     eax, [rcx+2Ch]
0x1800237fc  test    al, 4
0x1800237fe  jz      short loc_180023819
0x180023800  mov     rcx, [rcx+18h]
0x180023804  lea     edx, [r14+14h]
0x180023808  mov     dword ptr [rsp+60h+var_38], ebx
0x18002380c  mov     r9d, r15d
0x18002380f  mov     dword ptr [rsp+60h+var_40], r8d
0x180023814  call    WPP_SF_ddd
0x180023819  test    r12, r12
0x18002381c  jz      loc_180023A51
0x180023822  test    r15d, r15d
0x180023825  jz      loc_180023A51
0x18002382b  test    r13, r13
0x18002382e  jz      loc_180023A51
0x180023834  cmp     ebx, 20h ; ' '
0x180023837  jnz     loc_180023A51
0x18002383d  cmp     [rbp+arg_28], r14
0x180023841  jz      loc_180023A51
0x180023847  xor     ecx, ecx; PerformanceFrequency
0x180023849  mov     esi, r14d
0x18002384c  call    cs:__imp_KeQueryPerformanceCounter
0x180023853  nop     dword ptr [rax+rax+00h]
0x180023858  mov     ecx, edi
0x18002385a  mov     rbx, rax
0x18002385d  call    TBValidateKeyType
0x180023862  mov     edi, eax
0x180023864  test    eax, eax
0x180023866  jnz     short loc_180023873
0x180023868  cmp     r15, 2
0x18002386c  jnb     short loc_1800238DD
0x18002386e  mov     edi, 80090005h
0x180023873  xor     ecx, ecx; PerformanceFrequency
0x180023875  call    cs:__imp_KeQueryPerformanceCounter
0x18002387c  nop     dword ptr [rax+rax+00h]
0x180023881  mov     r8b, byte ptr [rbp+arg_10]; unsigned __int8
0x180023885  mov     r9d, esi; unsigned int
0x180023888  mov     dword ptr [rsp+60h+var_30], edi; int
0x18002388c  mov     qword ptr [rsp+60h+var_38], rax; union _LARGE_INTEGER
0x180023891  mov     qword ptr [rsp+60h+var_40], rbx; union _LARGE_INTEGER
0x180023896  call    ?LogKsecTokenBindingVerifyMessage@@YAXEEEKT_LARGE_INTEGER@@0J@Z; LogKsecTokenBindingVerifyMessage(uchar,uchar,uchar,ulong,_LARGE_INTEGER,_LARGE_INTEGER,long)
0x18002389b  lea     rcx, [rbp+var_10]
0x18002389f  call    TBFreeBuffer
0x1800238a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238ab  lea     rax, WPP_GLOBAL_Control
0x1800238b2  cmp     rcx, rax
0x1800238b5  jz      short loc_1800238D6
0x1800238b7  mov     eax, [rcx+2Ch]
0x1800238ba  test    al, 4
0x1800238bc  jz      short loc_1800238D6
0x1800238be  mov     rcx, [rcx+18h]
0x1800238c2  lea     r8, WPP_0c97cf3ebcf83aea482108bb01090baf_Traceguids
0x1800238c9  mov     edx, 15h
0x1800238ce  mov     r9d, edi
0x1800238d1  call    WPP_SF_D
0x1800238d6  mov     eax, edi
0x1800238d8  jmp     loc_180023A56
0x1800238dd  movzx   eax, word ptr [r12]
0x1800238e2  shl     ax, 8
0x1800238e6  movzx   ecx, ax
0x1800238e9  movzx   eax, byte ptr [r12+1]
0x1800238ef  or      ecx, eax
0x1800238f1  mov     [rbp+var_20], 2
0x1800238f8  mov     [rbp+var_1C], ecx
0x1800238fb  jz      loc_180023A4A
0x180023901  mov     eax, ecx
0x180023903  add     rax, 2
0x180023907  cmp     r15, rax
0x18002390a  jnz     loc_180023A4A
0x180023910  cmp     [rbp+var_20], r15d
0x180023914  jnb     short loc_18002395F
0x180023916  mov     r9d, [rbp+arg_10]
0x18002391a  lea     rax, [rbp+arg_0]
0x18002391e  mov     [rsp+60h+var_28], rax
0x180023923  lea     rdx, [rbp+var_20]
0x180023927  lea     rax, [rbp+var_1C]
0x18002392b  mov     r8d, r15d
0x18002392e  mov     [rsp+60h+var_30], rax
0x180023933  mov     rcx, r12
0x180023936  mov     dword ptr [rsp+60h+var_38], 20h ; ' '
0x18002393e  mov     qword ptr [rsp+60h+var_40], r13
0x180023943  call    _VerifyTokenBinding
0x180023948  mov     edi, eax
0x18002394a  test    eax, eax
0x18002394c  jnz     loc_180023873
0x180023952  cmp     [rbp+arg_0], al
0x180023955  jnz     short loc_180023910
0x180023957  add     r14d, [rbp+var_1C]
0x18002395b  inc     esi
0x18002395d  jmp     short loc_180023910
0x18002395f  mov     r13d, esi
0x180023962  lea     rcx, [rbp+var_10]
0x180023966  shl     r13d, 5
0x18002396a  lea     edx, [r13+10h]
0x18002396e  add     edx, r14d
0x180023971  call    TBAllocateBuffer
0x180023976  xor     r8d, r8d; unsigned int
0x180023979  test    eax, eax
0x18002397b  jnz     short loc_180023987
0x18002397d  mov     edi, 80090300h
0x180023982  jmp     loc_180023873
0x180023987  mov     r14, [rbp+var_10]
0x18002398b  lea     edx, [r13+10h]
0x18002398f  mov     [rbp+var_20], 2
0x180023996  mov     [r14], esi
0x180023999  lea     rax, [r14+10h]
0x18002399d  mov     [r14+8], rax
0x1800239a1  mov     esi, r8d
0x1800239a4  mov     [rbp+var_18], edx
0x1800239a7  cmp     [rbp+var_20], r15d
0x1800239ab  jnb     loc_180023A3A
0x1800239b1  mov     rax, [r14+8]
0x1800239b5  mov     ecx, edx
0x1800239b7  lea     rdx, [rbp+var_20]; unsigned int *
0x1800239bb  add     rcx, r14
0x1800239be  mov     r13d, esi
0x1800239c1  shl     r13, 5
0x1800239c5  mov     [rax+r13+8], rcx
0x1800239ca  mov     rcx, r12; unsigned __int8 *
0x1800239cd  mov     rax, [r14+8]
0x1800239d1  mov     [rax+r13+18h], r8
0x1800239d6  mov     rax, [r14+8]
0x1800239da  mov     [rax+r13+10h], r8d
0x1800239df  mov     rax, [r14+8]
0x1800239e3  mov     [rax+r13+14h], r8d
0x1800239e8  lea     rax, [rbp+arg_0]
0x1800239ec  mov     r9, [r14+8]
0x1800239f0  mov     [rsp+60h+var_30], rax; unsigned __int8 *
0x1800239f5  add     r9, r13
0x1800239f8  mov     qword ptr [rsp+60h+var_38], r9; enum TOKENBINDING_TYPE *
0x1800239fd  lea     rax, [rbp+var_1C]
0x180023a01  mov     qword ptr [rsp+60h+var_40], rax; unsigned int *
0x180023a06  mov     r9, [r9+8]; struct TOKENBINDING_IDENTIFIER *
0x180023a0a  call    ?_CopyTokenBinding@@YAJPEAEPEAKKPEAUTOKENBINDING_IDENTIFIER@@1PEAW4TOKENBINDING_TYPE@@0@Z; _CopyTokenBinding(uchar *,ulong *,ulong,TOKENBINDING_IDENTIFIER *,ulong *,TOKENBINDING_TYPE *,uchar *)
0x180023a0f  xor     r8d, r8d
0x180023a12  mov     edi, eax
0x180023a14  test    eax, eax
0x180023a16  jnz     loc_180023873
0x180023a1c  mov     edx, [rbp+var_18]
0x180023a1f  cmp     [rbp+arg_0], r8b
0x180023a23  jnz     short loc_1800239A7
0x180023a25  mov     ecx, [rbp+var_1C]
0x180023a28  add     edx, ecx
0x180023a2a  mov     rax, [r14+8]
0x180023a2e  inc     esi
0x180023a30  mov     [rax+r13+4], ecx
0x180023a35  jmp     loc_1800239A4
0x180023a3a  mov     rax, [rbp+arg_28]
0x180023a3e  mov     [rbp+var_10], r8
0x180023a42  mov     [rax], r14
0x180023a45  jmp     loc_180023873
0x180023a4a  mov     eax, 80090004h
0x180023a4f  jmp     short loc_180023A56
0x180023a51  mov     eax, 80090027h
0x180023a56  mov     rbx, [rsp+60h+arg_8]
0x180023a5e  add     rsp, 60h
0x180023a62  pop     r15
0x180023a64  pop     r14
0x180023a66  pop     r13
0x180023a68  pop     r12
0x180023a6a  pop     rdi
0x180023a6b  pop     rsi
0x180023a6c  pop     rbp
0x180023a6d  retn
```
