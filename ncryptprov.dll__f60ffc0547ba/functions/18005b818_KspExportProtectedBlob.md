# KspExportProtectedBlob

- ea: `0x18005b818`
- end: `0x18005bbc3`
- name: `KspExportProtectedBlob`
- size: `939`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180029600`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x1800398b0`
- `0x18005b818`
- `0x180063010`

## import_xrefs

- `ncrypt!NCryptProtectSecret` at `0x18005bab7`
- `ncrypt!NCryptProtectSecret` at `0x18005bab7`
- `ncrypt!NCryptCreateProtectionDescriptor` at `0x18005b988`
- `ncrypt!NCryptCreateProtectionDescriptor` at `0x18005b988`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x18005bba3`
- `ncrypt!NCryptCloseProtectionDescriptor` at `0x18005bba3`

## string_xrefs

- `0x18005bb68`: `onecore\ds\security\cryptoapi\ncrypt\storage\exportkey.c`

## pseudocode

```c
__int64 __fastcall KspExportProtectedBlob(
        __int64 a1,
        __int64 a2,
        _DWORD *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6)
{
  __int64 v9; // r14
  __int64 v10; // r9
  unsigned int *v11; // r12
  unsigned int v12; // ebx
  __int64 v13; // rcx
  int v14; // esi
  _WORD *v15; // r9
  unsigned int i; // r11d
  __int64 v17; // rax
  _DWORD *v18; // rbx
  unsigned __int64 v19; // r8
  unsigned int v20; // eax
  const wchar_t *v21; // rsi
  __int64 v22; // rax
  size_t v23; // rsi
  unsigned int v24; // eax
  size_t Size; // [rsp+40h] [rbp-38h] BYREF
  void *Src; // [rsp+48h] [rbp-30h] BYREF
  __int64 v28; // [rsp+50h] [rbp-28h] BYREF
  _QWORD v29[2]; // [rsp+58h] [rbp-20h] BYREF
  void (*v30)(void); // [rsp+68h] [rbp-10h]
  unsigned int v31; // [rsp+C0h] [rbp+48h] BYREF

  v29[0] = 24;
  v29[1] = SafeAllocaAllocateFromHeap;
  v30 = (void (*)(void))MSCryptFree;
  v28 = 0;
  v31 = 0;
  Src = 0;
  v9 = 0;
  LODWORD(Size) = 0;
  if ( !a1 )
  {
    v10 = 58;
LABEL_52:
    v12 = -2146893785;
    v13 = 2148073511LL;
    goto LABEL_53;
  }
  if ( !*(_QWORD *)(a1 + 64) )
  {
    v10 = 65;
    goto LABEL_52;
  }
  v11 = a5;
  if ( !a5 )
  {
    v10 = 72;
    goto LABEL_52;
  }
  if ( (*(_DWORD *)(a1 + 36) & 3) != 0 )
  {
    if ( (a6 & 0xFFFFFFBF) != 0 )
    {
      v12 = -2146893815;
      v10 = 91;
      v13 = 2148073481LL;
    }
    else
    {
      if ( !a2 || *(_DWORD *)a2 )
      {
        v10 = 167;
        goto LABEL_52;
      }
      v14 = 0;
      v15 = 0;
      for ( i = 0; i < *(_DWORD *)(a2 + 4); ++i )
      {
        v17 = *(_QWORD *)(a2 + 8);
        v18 = *(_DWORD **)(v17 + 16LL * i + 8);
        v19 = *(unsigned int *)(v17 + 16LL * i);
        if ( *(_DWORD *)(v17 + 16LL * i + 4) == 4 )
        {
          if ( (_DWORD)v19 != 4 )
          {
            v10 = 181;
LABEL_25:
            v12 = -1073741811;
            v13 = 3221225485LL;
            goto LABEL_53;
          }
          v14 = *v18;
        }
        else if ( *(_DWORD *)(v17 + 16LL * i + 4) == 3 )
        {
          if ( (v19 & 1) != 0 || (v19 & 0xFFFFFFFE) < 2 || *((_WORD *)v18 + (v19 >> 1) - 1) )
          {
            v10 = 198;
            goto LABEL_25;
          }
          v15 = *(_WORD **)(v17 + 16LL * i + 8);
        }
      }
      if ( !v15 || !*v15 )
      {
        v10 = 209;
        goto LABEL_25;
      }
      v20 = NCryptCreateProtectionDescriptor(v15, v14 | a6 & 0x40u, &v28);
      v12 = v20;
      if ( v20 )
      {
        v10 = 220;
      }
      else
      {
        if ( *(_DWORD *)(a1 + 144) )
        {
          v21 = L"ISOPROTECTEDBLOB";
        }
        else
        {
          v22 = *(_QWORD *)(a1 + 64);
          if ( *(_DWORD *)(v22 + 8) == 1 || (v21 = L"PRIVATEBLOB", *(_DWORD *)(v22 + 8) == 7) )
            v21 = L"KeyDataBlob";
        }
        v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD, unsigned int, unsigned int *, _DWORD))(*(_QWORD *)(a1 + 168) + 120LL))(
                *(_QWORD *)(a1 + 112),
                0,
                v21,
                0,
                v31,
                &v31,
                0);
        v12 = v20;
        if ( v20 )
        {
          v10 = 247;
        }
        else
        {
          v9 = SafeAllocaAllocateFromHeap(v31);
          if ( !v9 )
          {
            v12 = -2146893810;
            v10 = 255;
            v13 = 2148073486LL;
            goto LABEL_53;
          }
          v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, __int64, unsigned int, unsigned int *, _DWORD))(*(_QWORD *)(a1 + 168) + 120LL))(
                  *(_QWORD *)(a1 + 112),
                  0,
                  v21,
                  v9,
                  v31,
                  &v31,
                  0);
          v12 = v20;
          if ( v20 )
          {
            v10 = 270;
          }
          else
          {
            v20 = NCryptProtectSecret(v28, 64, v9, v31, v29, 0, &Src, &Size);
            v12 = v20;
            if ( !v20 )
            {
              v23 = (unsigned int)Size;
              v24 = *(_DWORD *)(*(_QWORD *)(a1 + 64) + 24LL) + Size + 16;
              *v11 = v24;
              if ( a3 )
              {
                if ( a4 < v24 )
                {
                  v12 = -2146893784;
                  goto LABEL_54;
                }
                *a3 = 16;
                a3[1] = 1263817296;
                a3[2] = *(_DWORD *)(*(_QWORD *)(a1 + 64) + 24LL);
                a3[3] = v23;
                memcpy_0(a3 + 4, **(const void ***)(a1 + 64), *(_QWORD *)(*(_QWORD *)(a1 + 64) + 24LL));
                memcpy_0((char *)a3 + *(_QWORD *)(*(_QWORD *)(a1 + 64) + 24LL) + 16, Src, v23);
              }
              v12 = 0;
              goto LABEL_54;
            }
            v10 = 315;
          }
        }
      }
      v13 = v20;
    }
  }
  else
  {
    v12 = -2146893783;
    v10 = 84;
    v13 = 2148073513LL;
  }
LABEL_53:
  DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\exportkey.c", v10);
LABEL_54:
  if ( Src )
    v30();
  if ( v9 )
    MSCryptFree(v9);
  if ( v28 )
    NCryptCloseProtectionDescriptor();
  return v12;
}

```

## disassembly

```asm
0x18005b818  push    rbp
0x18005b81a  push    rbx
0x18005b81b  push    rsi
0x18005b81c  push    rdi
0x18005b81d  push    r12
0x18005b81f  push    r13
0x18005b821  push    r14
0x18005b823  push    r15
0x18005b825  mov     rbp, rsp
0x18005b828  sub     rsp, 78h
0x18005b82c  lea     rax, SafeAllocaAllocateFromHeap
0x18005b833  mov     [rbp+var_20], 18h
0x18005b83b  mov     rdi, rcx
0x18005b83e  mov     [rbp+var_18], rax
0x18005b842  xor     ecx, ecx
0x18005b844  lea     rax, MSCryptFree
0x18005b84b  mov     [rbp+var_10], rax
0x18005b84f  mov     r13d, r9d
0x18005b852  mov     [rbp+var_28], rcx
0x18005b856  mov     r15, r8
0x18005b859  mov     [rbp+arg_0], ecx
0x18005b85c  mov     r10, rdx
0x18005b85f  mov     [rbp+Src], rcx
0x18005b863  mov     r14d, ecx
0x18005b866  mov     dword ptr [rbp+Size], ecx
0x18005b869  test    rdi, rdi
0x18005b86c  jnz     short loc_18005B877
0x18005b86e  lea     r9d, [rcx+3Ah]
0x18005b872  jmp     loc_18005BB5E
0x18005b877  cmp     [rdi+40h], rcx
0x18005b87b  jnz     short loc_18005B888
0x18005b87d  mov     r9d, 41h ; 'A'
0x18005b883  jmp     loc_18005BB5E
0x18005b888  mov     r12, [rbp+arg_20]
0x18005b88c  test    r12, r12
0x18005b88f  jnz     short loc_18005B89B
0x18005b891  lea     r9d, [r12+48h]
0x18005b896  jmp     loc_18005BB5E
0x18005b89b  mov     eax, [rdi+24h]
0x18005b89e  test    al, 3
0x18005b8a0  jnz     short loc_18005B8B7
0x18005b8a2  mov     ebx, 80090029h
0x18005b8a7  mov     r9d, 54h ; 'T'
0x18005b8ad  mov     ecx, 80090029h
0x18005b8b2  jmp     loc_18005BB68
0x18005b8b7  mov     edx, [rbp+arg_28]
0x18005b8ba  test    edx, 0FFFFFFBFh
0x18005b8c0  jz      short loc_18005B8D7
0x18005b8c2  mov     ebx, 80090009h
0x18005b8c7  mov     r9d, 5Bh ; '['
0x18005b8cd  mov     ecx, 80090009h
0x18005b8d2  jmp     loc_18005BB68
0x18005b8d7  test    r10, r10
0x18005b8da  jz      loc_18005BB58
0x18005b8e0  cmp     [r10], ecx
0x18005b8e3  jnz     loc_18005BB58
0x18005b8e9  mov     esi, ecx
0x18005b8eb  mov     r9, rcx
0x18005b8ee  mov     r11d, ecx
0x18005b8f1  cmp     r11d, [r10+4]
0x18005b8f5  jnb     short loc_18005B967
0x18005b8f7  mov     rax, [r10+8]
0x18005b8fb  mov     ecx, r11d
0x18005b8fe  add     rcx, rcx
0x18005b901  cmp     dword ptr [rax+rcx*8+4], 4
0x18005b906  mov     rbx, [rax+rcx*8+8]
0x18005b90b  mov     r8d, [rax+rcx*8]
0x18005b90f  jnz     short loc_18005B91B
0x18005b911  cmp     r8d, 4
0x18005b915  jnz     short loc_18005B94A
0x18005b917  mov     esi, [rbx]
0x18005b919  jmp     short loc_18005B945
0x18005b91b  cmp     dword ptr [rax+rcx*8+4], 3
0x18005b920  jnz     short loc_18005B945
0x18005b922  test    r8b, 1
0x18005b926  jnz     short loc_18005B95F
0x18005b928  mov     eax, r8d
0x18005b92b  and     eax, 0FFFFFFFEh
0x18005b92e  cmp     eax, 2
0x18005b931  jb      short loc_18005B95F
0x18005b933  mov     rcx, r8
0x18005b936  xor     eax, eax
0x18005b938  shr     rcx, 1
0x18005b93b  cmp     ax, [rbx+rcx*2-2]
0x18005b940  jnz     short loc_18005B95F
0x18005b942  mov     r9, rbx
0x18005b945  inc     r11d
0x18005b948  jmp     short loc_18005B8F1
0x18005b94a  mov     r9d, 0B5h
0x18005b950  mov     ebx, 0C000000Dh
0x18005b955  mov     ecx, 0C000000Dh
0x18005b95a  jmp     loc_18005BB68
0x18005b95f  mov     r9d, 0C6h
0x18005b965  jmp     short loc_18005B950
0x18005b967  xor     ecx, ecx
0x18005b969  test    r9, r9
0x18005b96c  jz      loc_18005BB4D
0x18005b972  cmp     cx, [r9]
0x18005b976  jz      loc_18005BB4D
0x18005b97c  and     edx, 40h
0x18005b97f  lea     r8, [rbp+var_28]
0x18005b983  or      edx, esi
0x18005b985  mov     rcx, r9
0x18005b988  call    cs:__imp_NCryptCreateProtectionDescriptor
0x18005b98f  nop     dword ptr [rax+rax+00h]
0x18005b994  mov     ebx, eax
0x18005b996  test    eax, eax
0x18005b998  jz      short loc_18005B9A7
0x18005b99a  mov     r9d, 0DCh
0x18005b9a0  mov     ecx, eax
0x18005b9a2  jmp     loc_18005BB68
0x18005b9a7  cmp     [rdi+90h], r14d
0x18005b9ae  jz      short loc_18005B9B9
0x18005b9b0  lea     rsi, aIsoprotectedbl; "ISOPROTECTEDBLOB"
0x18005b9b7  jmp     short loc_18005B9D7
0x18005b9b9  mov     rax, [rdi+40h]
0x18005b9bd  cmp     dword ptr [rax+8], 1
0x18005b9c1  jz      short loc_18005B9D0
0x18005b9c3  cmp     dword ptr [rax+8], 7
0x18005b9c7  lea     rsi, aPrivateblob; "PRIVATEBLOB"
0x18005b9ce  jnz     short loc_18005B9D7
0x18005b9d0  lea     rsi, aKeydatablob; "KeyDataBlob"
0x18005b9d7  mov     rax, [rdi+0A8h]
0x18005b9de  xor     r9d, r9d
0x18005b9e1  mov     rcx, [rdi+70h]
0x18005b9e5  mov     r8, rsi
0x18005b9e8  mov     dword ptr [rsp+78h+var_48], r14d
0x18005b9ed  xor     edx, edx
0x18005b9ef  mov     r10, [rax+78h]
0x18005b9f3  lea     rax, [rbp+arg_0]
0x18005b9f7  mov     [rsp+78h+var_50], rax
0x18005b9fc  mov     eax, [rbp+arg_0]
0x18005b9ff  mov     dword ptr [rsp+78h+var_58], eax
0x18005ba03  mov     rax, r10
0x18005ba06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ba0b  mov     ebx, eax
0x18005ba0d  test    eax, eax
0x18005ba0f  jz      short loc_18005BA19
0x18005ba11  mov     r9d, 0F7h
0x18005ba17  jmp     short loc_18005B9A0
0x18005ba19  mov     ecx, [rbp+arg_0]
0x18005ba1c  call    SafeAllocaAllocateFromHeap
0x18005ba21  mov     r14, rax
0x18005ba24  test    rax, rax
0x18005ba27  jnz     short loc_18005BA3E
0x18005ba29  mov     ebx, 8009000Eh
0x18005ba2e  mov     r9d, 0FFh
0x18005ba34  mov     ecx, 8009000Eh
0x18005ba39  jmp     loc_18005BB68
0x18005ba3e  mov     rax, [rdi+0A8h]
0x18005ba45  lea     rcx, [rbp+arg_0]
0x18005ba49  mov     dword ptr [rsp+78h+var_48], 0
0x18005ba51  mov     r9, r14
0x18005ba54  mov     [rsp+78h+var_50], rcx
0x18005ba59  mov     r8, rsi
0x18005ba5c  mov     ecx, [rbp+arg_0]
0x18005ba5f  xor     edx, edx
0x18005ba61  mov     rax, [rax+78h]
0x18005ba65  mov     dword ptr [rsp+78h+var_58], ecx
0x18005ba69  mov     rcx, [rdi+70h]
0x18005ba6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ba72  mov     ebx, eax
0x18005ba74  test    eax, eax
0x18005ba76  jz      short loc_18005BA83
0x18005ba78  mov     r9d, 10Eh
0x18005ba7e  jmp     loc_18005B9A0
0x18005ba83  mov     r9d, [rbp+arg_0]
0x18005ba87  lea     rax, [rbp+Size]
0x18005ba8b  mov     rcx, [rbp+var_28]
0x18005ba8f  mov     r8, r14
0x18005ba92  mov     [rsp+78h+var_40], rax
0x18005ba97  mov     edx, 40h ; '@'
0x18005ba9c  lea     rax, [rbp+Src]
0x18005baa0  mov     [rsp+78h+var_48], rax
0x18005baa5  lea     rax, [rbp+var_20]
0x18005baa9  mov     [rsp+78h+var_50], 0
0x18005bab2  mov     [rsp+78h+var_58], rax
0x18005bab7  call    cs:__imp_NCryptProtectSecret
0x18005babe  nop     dword ptr [rax+rax+00h]
0x18005bac3  mov     ebx, eax
0x18005bac5  test    eax, eax
0x18005bac7  jz      short loc_18005BAD4
0x18005bac9  mov     r9d, 13Bh
0x18005bacf  jmp     loc_18005B9A0
0x18005bad4  mov     rax, [rdi+40h]
0x18005bad8  mov     esi, dword ptr [rbp+Size]
0x18005badb  mov     ecx, [rax+18h]
0x18005bade  lea     eax, [rsi+10h]
0x18005bae1  add     eax, ecx
0x18005bae3  mov     [r12], eax
0x18005bae7  test    r15, r15
0x18005baea  jnz     short loc_18005BAF3
0x18005baec  xor     ebx, ebx
0x18005baee  jmp     loc_18005BB7B
0x18005baf3  cmp     r13d, eax
0x18005baf6  jnb     short loc_18005BAFF
0x18005baf8  mov     ebx, 80090028h
0x18005bafd  jmp     short loc_18005BB7B
0x18005baff  mov     dword ptr [r15], 10h
0x18005bb06  lea     rbx, [r15+10h]
0x18005bb0a  mov     dword ptr [r15+4], 4B545250h
0x18005bb12  mov     rax, [rdi+40h]
0x18005bb16  mov     ecx, [rax+18h]
0x18005bb19  mov     [r15+8], ecx
0x18005bb1d  mov     rcx, rbx; void *
0x18005bb20  mov     [r15+0Ch], esi
0x18005bb24  mov     rdx, [rdi+40h]
0x18005bb28  mov     r8, [rdx+18h]; Size
0x18005bb2c  mov     rdx, [rdx]; Src
0x18005bb2f  call    memcpy_0
0x18005bb34  mov     rax, [rdi+40h]
0x18005bb38  mov     r8, rsi; Size
0x18005bb3b  mov     rdx, [rbp+Src]; Src
0x18005bb3f  mov     rcx, [rax+18h]
0x18005bb43  add     rcx, rbx; void *
0x18005bb46  call    memcpy_0
0x18005bb4b  jmp     short loc_18005BAEC
0x18005bb4d  mov     r9d, 0D1h
0x18005bb53  jmp     loc_18005B950
0x18005bb58  mov     r9d, 0A7h
0x18005bb5e  mov     ebx, 80090027h
0x18005bb63  mov     ecx, 80090027h
0x18005bb68  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005bb6f  lea     rdx, aStatus; "Status"
0x18005bb76  call    DebugTraceError
0x18005bb7b  mov     rcx, [rbp+Src]
0x18005bb7f  test    rcx, rcx
0x18005bb82  jz      short loc_18005BB8D
0x18005bb84  mov     rax, [rbp+var_10]
0x18005bb88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb8d  test    r14, r14
0x18005bb90  jz      short loc_18005BB9A
0x18005bb92  mov     rcx, r14
0x18005bb95  call    MSCryptFree
0x18005bb9a  mov     rcx, [rbp+var_28]
0x18005bb9e  test    rcx, rcx
0x18005bba1  jz      short loc_18005BBAF
0x18005bba3  call    cs:__imp_NCryptCloseProtectionDescriptor
0x18005bbaa  nop     dword ptr [rax+rax+00h]
0x18005bbaf  mov     eax, ebx
0x18005bbb1  add     rsp, 78h
0x18005bbb5  pop     r15
0x18005bbb7  pop     r14
0x18005bbb9  pop     r13
0x18005bbbb  pop     r12
0x18005bbbd  pop     rdi
0x18005bbbe  pop     rsi
0x18005bbbf  pop     rbx
0x18005bbc0  pop     rbp
0x18005bbc1  retn
```
