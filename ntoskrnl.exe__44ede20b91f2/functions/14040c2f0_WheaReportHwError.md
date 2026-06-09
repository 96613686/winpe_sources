# WheaReportHwError

- ea: `0x14040c2f0`
- end: `0x14040c74c`
- name: `WheaReportHwError`
- size: `1116`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: ``

## callers

- `0x14040b5ec`
- `0x1404a696c`
- `0x140584e70`
- `0x140689900`

## callees

- `0x14040c2f0`
- `0x14040c754`
- `0x14040c7a4`
- `0x14040c84c`
- `0x14040c8e8`
- `0x14040c93c`
- `0x14040cb78`
- `0x14040cbb0`
- `0x14040cc00`
- `0x14040cc28`
- `0x14040cdf0`
- `0x14053a530`
- `0x140689230`
- `0x140689320`
- `0x140689408`
- `0x1406894b0`
- `0x1406d9d70`

## import_xrefs

- `PSHED!PshedWriteErrorRecord` at `0x14040c6b2`
- `PSHED!PshedWriteErrorRecord` at `0x140711c47`
- `PSHED!PshedWriteErrorRecord` at `0x14040c6b2`
- `PSHED!PshedWriteErrorRecord` at `0x140711c47`
- `PSHED!PshedBugCheckSystem` at `0x140711c8a`
- `PSHED!PshedBugCheckSystem` at `0x140711c8a`
- `PSHED!PshedFinalizeErrorRecord` at `0x14040c47b`
- `PSHED!PshedFinalizeErrorRecord` at `0x14040c6e4`
- `PSHED!PshedFinalizeErrorRecord` at `0x140711c1e`
- `PSHED!PshedFinalizeErrorRecord` at `0x14040c47b`
- `PSHED!PshedFinalizeErrorRecord` at `0x14040c6e4`
- `PSHED!PshedFinalizeErrorRecord` at `0x140711c1e`

## pseudocode

```c
__int64 __fastcall WheaReportHwError(__int64 a1)
{
  int v1; // r11d
  int v2; // eax
  char v4; // r15
  unsigned __int64 v5; // r13
  char v6; // r12
  _QWORD *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  ULONG_PTR v10; // rdx
  unsigned int v11; // r11d
  __int64 v12; // r14
  __int64 v13; // rax
  char *v14; // rsi
  __int64 v15; // r8
  int v16; // ecx
  unsigned int v17; // r12d
  int v18; // edx
  __int128 *p_Src; // rcx
  __int64 v21; // r13
  char v22; // [rsp+30h] [rbp-49h]
  int v23; // [rsp+34h] [rbp-45h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-41h]
  __int128 Src; // [rsp+40h] [rbp-39h] BYREF
  __int128 v26; // [rsp+50h] [rbp-29h]
  __int64 v27; // [rsp+60h] [rbp-19h]
  __int128 v28; // [rsp+68h] [rbp-11h] BYREF
  __int128 v29; // [rsp+78h] [rbp-1h]

  v1 = *(_DWORD *)(a1 + 20);
  v27 = 0;
  v2 = v1 & 0x40000000;
  v23 = 0;
  Src = 0;
  v26 = 0;
  v28 = 0;
  v29 = 0;
  if ( v1 >= 0 )
  {
    v4 = 0;
    if ( v2 )
    {
      v1 &= ~0x40000000u;
      v21 = *(unsigned int *)(a1 + 8) + 7LL;
      *(_DWORD *)(a1 + 20) = v1;
      v22 = 1;
      v5 = (a1 + v21) & 0xFFFFFFFFFFFFFFF8uLL;
      v6 = 1;
      goto LABEL_5;
    }
  }
  else
  {
    if ( v2 )
      return 3221225485LL;
    v1 &= ~0x80000000;
    v4 = 1;
    *(_DWORD *)(a1 + 20) = v1;
  }
  v5 = 0;
  v22 = 0;
  v6 = 0;
LABEL_5:
  if ( v1 == 3 && !v4 )
    return 0;
  v7 = KeGetPcr()[66].Unused1[1];
  v24 = v7;
  if ( !v7 || (v8 = v7[1]) == 0 || !*(_DWORD *)(v8 + 4) )
  {
    if ( (unsigned int)v1 <= 1 && (*(_BYTE *)(a1 + 12) & 1) == 0 && !v4 )
      KeBugCheckEx(0x124u, *(int *)(a1 + 28), 0, 0, 0);
    *(_QWORD *)&v28 = 0x1674C6857LL;
    p_Src = &v28;
    *((_QWORD *)&v28 + 1) = 0x100000020LL;
    *(_QWORD *)&v29 = 0x800000364C4E524BuLL;
    *((_QWORD *)&v29 + 1) = 2;
    goto LABEL_24;
  }
  v9 = sub_14040C754(v8, *(unsigned int *)(a1 + 24));
  v12 = v9;
  if ( v9 )
  {
    _InterlockedAdd((volatile signed __int32 *)(v9 + 24), 1u);
    if ( *(_DWORD *)(a1 + 20) == 2 && (unsigned __int8)sub_14040C93C(v9) )
    {
      p_Src = &Src;
      LODWORD(v27) = *(_DWORD *)(a1 + 28);
      HIDWORD(v27) = *(_DWORD *)(a1 + 24);
      *(_QWORD *)&Src = 0x1674C6857LL;
      *((_QWORD *)&Src + 1) = 0x100000028LL;
      *(_QWORD *)&v26 = 0x800000044C4E524BuLL;
      *((_QWORD *)&v26 + 1) = 0x800000002LL;
LABEL_24:
      WheaLogInternalEvent(p_Src);
      return 0;
    }
    v13 = sub_14040C7A4(v12, &v23);
    v14 = (char *)v13;
    if ( v13 )
    {
      v15 = (unsigned int)(v23 - 40);
      v16 = *(_DWORD *)(v13 + 24)
          ^ ((unsigned __int8)*(_DWORD *)(v13 + 24)
           ^ (unsigned __int8)(*(_DWORD *)(a1 + 12) >> 2))
          & 4;
      *(_DWORD *)(v13 + 24) = v16;
      *(_DWORD *)(v13 + 24) = v16 ^ ((unsigned __int8)v16 ^ (unsigned __int8)(*(_DWORD *)(a1 + 12) >> 2)) & 8;
      v23 = sub_14040C84C(v12, a1, v15, v13 + 40);
      if ( v23 >= 0 )
      {
        if ( v4 || v6 )
          *((_DWORD *)v14 + 36) |= 8u;
        v17 = 0;
        if ( (v14[144] & 2) != 0 )
        {
          if ( (*((_DWORD *)v14 + 6) & 1) == 0 || (unsigned __int8)WheaIsCriticalState() )
            goto LABEL_20;
          if ( dword_140EE3D90 != 1 )
          {
LABEL_64:
            sub_14040CB78(v14);
            return v17;
          }
        }
        else
        {
          if ( !*(_BYTE *)off_140E0CBE8 && !v4 )
          {
            sub_14040CC28(0, v14 + 40);
            if ( (int)PshedWriteErrorRecord(1, *((unsigned int *)v14 + 15), v14 + 40) < 0 )
              *(_BYTE *)off_140E0CBE8 = 1;
          }
          v18 = *(_DWORD *)(a1 + 20);
          if ( v18 == 1 )
          {
            if ( !v4 )
            {
              PshedFinalizeErrorRecord(v14 + 40, v12 + 96);
              sub_1406894B0(v14 + 40);
              sub_14040CC28(3, v14 + 40);
              PshedWriteErrorRecord(0, *((unsigned int *)v14 + 15), v14 + 40);
              sub_140689320(v14 + 40, *((unsigned int *)v14 + 15));
              if ( v22 )
                KeBugCheckEx(
                  0x124u,
                  *(int *)(v12 + 104),
                  (ULONG_PTR)(v14 + 40),
                  *(_QWORD *)(v5 + 72),
                  *(_QWORD *)(v5 + 80));
              PshedBugCheckSystem(v12 + 96, v14 + 40);
              return v17;
            }
            goto LABEL_19;
          }
          if ( (unsigned int)(v18 - 2) <= 1 )
          {
LABEL_19:
            PshedFinalizeErrorRecord(v14 + 40, v12 + 96);
            goto LABEL_20;
          }
          if ( v18 )
          {
            sub_14040CB78(v14);
            return (unsigned int)-1073741811;
          }
          PshedFinalizeErrorRecord(v14 + 40, v12 + 96);
          sub_140689408(v14 + 40);
          if ( *((_DWORD *)v14 + 13) == 2 )
          {
            *((_DWORD *)v14 + 36) |= 1u;
          }
          else if ( !v4 )
          {
            WheaRecoveryBugCheck(v14 + 40, v12 + 96, a1);
            return v17;
          }
          if ( (*((_DWORD *)v14 + 6) & 1) == 0
            || dword_140EE3D90 != 1
            || (unsigned __int8)WheaIsCriticalState()
            || v14[144] < 0 )
          {
LABEL_20:
            sub_14040C8E8(v24[2], v14);
            return v17;
          }
        }
        sub_14040CBB0(v14 + 40);
        goto LABEL_64;
      }
      if ( *(_DWORD *)(a1 + 20) <= 1u && (*(_BYTE *)(a1 + 12) & 1) == 0 && !v4 )
        KeBugCheckEx(0x122u, 0xBu, *(int *)(a1 + 28), *(unsigned int *)(a1 + 24), 0);
      sub_14040CB78(v14);
      return (unsigned int)v23;
    }
    else
    {
      ++*(_DWORD *)(v12 + 16);
      if ( *(_DWORD *)(a1 + 20) <= 1u && (*(_BYTE *)(a1 + 12) & 1) == 0 && !v4 )
        KeBugCheckEx(0x122u, 0xAu, *(int *)(a1 + 28), *(unsigned int *)(a1 + 24), 0);
      return 3221225626LL;
    }
  }
  else
  {
    if ( v11 <= 1 && (*(_BYTE *)(a1 + 12) & 1) == 0 && !v4 )
      KeBugCheckEx(0x122u, 9u, *(int *)(a1 + 28), v10, 0);
    return 3221225664LL;
  }
}

```

## disassembly

```asm
0x14040c2f0  push    rbp
0x14040c2f2  push    rbx
0x14040c2f3  push    rsi
0x14040c2f4  push    rdi
0x14040c2f5  push    r12
0x14040c2f7  push    r13
0x14040c2f9  push    r14
0x14040c2fb  push    r15
0x14040c2fd  lea     rbp, [rsp-1Fh]
0x14040c302  sub     rsp, 98h
0x14040c309  mov     rax, cs:__security_cookie
0x14040c310  xor     rax, rsp
0x14040c313  mov     [rbp+57h+var_48], rax
0x14040c317  mov     r11d, [rcx+14h]
0x14040c31b  xor     eax, eax
0x14040c31d  xorps   xmm0, xmm0
0x14040c320  mov     [rbp+57h+var_70], rax
0x14040c324  xor     edi, edi
0x14040c326  mov     eax, r11d
0x14040c329  and     eax, 40000000h
0x14040c32e  mov     [rbp+57h+var_9C], edi
0x14040c331  mov     rbx, rcx
0x14040c334  movups  [rbp+57h+Src], xmm0
0x14040c338  lea     esi, [rdi+1]
0x14040c33b  movups  [rbp+57h+var_80], xmm0
0x14040c33f  movups  [rbp+57h+var_68], xmm0
0x14040c343  movups  [rbp+57h+var_58], xmm0
0x14040c347  test    r11d, r11d
0x14040c34a  jns     loc_14040C5B2
0x14040c350  test    eax, eax
0x14040c352  jnz     loc_14040C558
0x14040c358  btr     r11d, 1Fh
0x14040c35d  mov     r15b, sil
0x14040c360  mov     [rcx+14h], r11d
0x14040c364  mov     r13, rdi
0x14040c367  mov     [rbp+57h+var_A0], dil
0x14040c36b  mov     r12b, dil
0x14040c36e  cmp     r11d, 3
0x14040c372  jz      loc_14040C5E1
0x14040c378  mov     rax, gs:18h
0x14040c381  mov     rax, [rax+6160h]
0x14040c388  mov     [rbp+57h+var_98], rax
0x14040c38c  test    rax, rax
0x14040c38f  jz      loc_14040C562
0x14040c395  mov     rcx, [rax+8]
0x14040c399  test    rcx, rcx
0x14040c39c  jz      loc_14040C562
0x14040c3a2  cmp     [rcx+4], edi
0x14040c3a5  jz      loc_14040C562
0x14040c3ab  mov     edx, [rbx+18h]
0x14040c3ae  call    sub_14040C754
0x14040c3b3  mov     r14, rax
0x14040c3b6  test    rax, rax
0x14040c3b9  jz      loc_14040C5EF
0x14040c3bf  lock add [rax+18h], esi
0x14040c3c3  cmp     dword ptr [rbx+14h], 2
0x14040c3c7  jz      loc_14040C4BB
0x14040c3cd  lea     rdx, [rbp+57h+var_9C]
0x14040c3d1  mov     rcx, r14
0x14040c3d4  call    sub_14040C7A4
0x14040c3d9  mov     rsi, rax
0x14040c3dc  test    rax, rax
0x14040c3df  jz      loc_14040C59E
0x14040c3e5  mov     eax, [rax+18h]
0x14040c3e8  lea     rdi, [rsi+28h]
0x14040c3ec  mov     ecx, [rbx+0Ch]
0x14040c3ef  mov     r9, rdi
0x14040c3f2  mov     r8d, [rbp+57h+var_9C]
0x14040c3f6  mov     rdx, rbx
0x14040c3f9  shr     ecx, 2
0x14040c3fc  add     r8d, 0FFFFFFD8h
0x14040c400  xor     ecx, eax
0x14040c402  and     ecx, 4
0x14040c405  xor     ecx, eax
0x14040c407  mov     [rsi+18h], ecx
0x14040c40a  mov     eax, [rbx+0Ch]
0x14040c40d  shr     eax, 2
0x14040c410  xor     eax, ecx
0x14040c412  and     eax, 8
0x14040c415  xor     eax, ecx
0x14040c417  mov     rcx, r14
0x14040c41a  mov     [rsi+18h], eax
0x14040c41d  call    sub_14040C84C
0x14040c422  mov     [rbp+57h+var_9C], eax
0x14040c425  test    eax, eax
0x14040c427  js      loc_14040C53E
0x14040c42d  test    r15b, r15b
0x14040c430  jnz     loc_14040C68B
0x14040c436  test    r12b, r12b
0x14040c439  jnz     loc_14040C68B
0x14040c43f  xor     r12d, r12d
0x14040c442  test    byte ptr [rdi+68h], 2
0x14040c446  jnz     loc_14040C514
0x14040c44c  mov     rax, cs:off_140E0CBE8
0x14040c453  cmp     [rax], r12b
0x14040c456  jz      loc_14040C694
0x14040c45c  mov     edx, [rbx+14h]
0x14040c45f  cmp     edx, 1
0x14040c462  jz      loc_140711C0E
0x14040c468  lea     eax, [rdx-2]
0x14040c46b  cmp     eax, 1
0x14040c46e  ja      loc_14040C6D5
0x14040c474  lea     rdx, [r14+60h]
0x14040c478  mov     rcx, rdi
0x14040c47b  call    cs:PshedFinalizeErrorRecord
0x14040c482  nop     dword ptr [rax+rax+00h]
0x14040c487  mov     rcx, [rbp+57h+var_98]
0x14040c48b  mov     rdx, rsi
0x14040c48e  mov     rcx, [rcx+10h]
0x14040c492  call    sub_14040C8E8
0x14040c497  mov     eax, r12d
0x14040c49a  mov     rcx, [rbp+57h+var_48]
0x14040c49e  xor     rcx, rsp; StackCookie
0x14040c4a1  call    __security_check_cookie
0x14040c4a6  add     rsp, 98h
0x14040c4ad  pop     r15
0x14040c4af  pop     r14
0x14040c4b1  pop     r13
0x14040c4b3  pop     r12
0x14040c4b5  pop     rdi
0x14040c4b6  pop     rsi
0x14040c4b7  pop     rbx
0x14040c4b8  pop     rbp
0x14040c4b9  retn
0x14040c4bb  mov     rcx, r14
0x14040c4be  call    sub_14040C93C
0x14040c4c3  test    al, al
0x14040c4c5  jz      loc_14040C3CD
0x14040c4cb  mov     eax, [rbx+1Ch]
0x14040c4ce  lea     rcx, [rbp+57h+Src]; Src
0x14040c4d2  mov     dword ptr [rbp+57h+var_70], eax
0x14040c4d5  mov     eax, [rbx+18h]
0x14040c4d8  mov     dword ptr [rbp+57h+var_70+4], eax
0x14040c4db  mov     dword ptr [rbp+57h+Src], 674C6857h
0x14040c4e2  mov     dword ptr [rbp+57h+Src+4], esi
0x14040c4e5  mov     dword ptr [rbp+57h+Src+8], 28h ; '('
0x14040c4ec  mov     dword ptr [rbp+57h+Src+0Ch], esi
0x14040c4ef  mov     dword ptr [rbp+57h+var_80+4], 80000004h
0x14040c4f6  mov     dword ptr [rbp+57h+var_80], 4C4E524Bh
0x14040c4fd  mov     dword ptr [rbp+57h+var_80+8], 2
0x14040c504  mov     dword ptr [rbp+57h+var_80+0Ch], 8
0x14040c50b  call    WheaLogInternalEvent
0x14040c510  xor     eax, eax
0x14040c512  jmp     short loc_14040C49A
0x14040c514  mov     eax, [rsi+18h]
0x14040c517  test    al, 1
0x14040c519  jz      loc_14040C487
0x14040c51f  call    WheaIsCriticalState
0x14040c524  test    al, al
0x14040c526  jnz     loc_14040C487
0x14040c52c  cmp     cs:dword_140EE3D90, 1
0x14040c533  jz      loc_140711BF8
0x14040c539  jmp     loc_140711C00
0x14040c53e  cmp     dword ptr [rbx+14h], 1
0x14040c542  jbe     loc_14040C657
0x14040c548  mov     rcx, rsi
0x14040c54b  call    sub_14040CB78
0x14040c550  mov     eax, [rbp+57h+var_9C]
0x14040c553  jmp     loc_14040C49A
0x14040c558  mov     eax, 0C000000Dh
0x14040c55d  jmp     loc_14040C49A
0x14040c562  cmp     r11d, esi
0x14040c565  jbe     loc_14040C71F
0x14040c56b  mov     dword ptr [rbp+57h+var_68], 674C6857h
0x14040c572  lea     rcx, [rbp+57h+var_68]
0x14040c576  mov     dword ptr [rbp+57h+var_68+4], esi
0x14040c579  mov     dword ptr [rbp+57h+var_68+8], 20h ; ' '
0x14040c580  mov     dword ptr [rbp+57h+var_68+0Ch], esi
0x14040c583  mov     dword ptr [rbp+57h+var_58+4], 80000036h
0x14040c58a  mov     dword ptr [rbp+57h+var_58], 4C4E524Bh
0x14040c591  mov     qword ptr [rbp+57h+var_58+8], 2
0x14040c599  jmp     loc_14040C50B
0x14040c59e  inc     dword ptr [r14+10h]
0x14040c5a2  cmp     dword ptr [rbx+14h], 1
0x14040c5a6  jbe     short loc_14040C627
0x14040c5a8  mov     eax, 0C000009Ah
0x14040c5ad  jmp     loc_14040C49A
0x14040c5b2  mov     r15b, dil
0x14040c5b5  test    eax, eax
0x14040c5b7  jz      loc_14040C364
0x14040c5bd  mov     r13d, [rcx+8]
0x14040c5c1  btr     r11d, 1Eh
0x14040c5c6  add     r13, 7
0x14040c5ca  mov     [rcx+14h], r11d
0x14040c5ce  add     r13, rbx
0x14040c5d1  mov     [rbp+57h+var_A0], sil
0x14040c5d5  and     r13, 0FFFFFFFFFFFFFFF8h
0x14040c5d9  mov     r12b, sil
0x14040c5dc  jmp     loc_14040C36E
0x14040c5e1  test    r15b, r15b
0x14040c5e4  jz      loc_14040C510
0x14040c5ea  jmp     loc_14040C378
0x14040c5ef  cmp     r11d, esi
0x14040c5f2  ja      loc_140711BEE
0x14040c5f8  test    [rbx+0Ch], sil
0x14040c5fc  jnz     loc_140711BEE
0x14040c602  test    r15b, r15b
0x14040c605  jnz     loc_140711BEE
0x14040c60b  movsxd  r8, dword ptr [rbx+1Ch]; BugCheckParameter2
0x14040c60f  mov     r9, rdx; BugCheckParameter3
0x14040c612  mov     edx, 9; BugCheckParameter1
0x14040c617  mov     [rsp+0D0h+BugCheckParameter4], rdi; BugCheckParameter4
0x14040c61c  mov     ecx, 122h; BugCheckCode
0x14040c621  call    KeBugCheckEx
0x14040c627  test    byte ptr [rbx+0Ch], 1
0x14040c62b  jnz     loc_14040C5A8
0x14040c631  test    r15b, r15b
0x14040c634  jnz     loc_14040C5A8
0x14040c63a  mov     r9d, [rbx+18h]; BugCheckParameter3
0x14040c63e  mov     edx, 0Ah; BugCheckParameter1
0x14040c643  movsxd  r8, dword ptr [rbx+1Ch]; BugCheckParameter2
0x14040c647  mov     ecx, 122h; BugCheckCode
0x14040c64c  mov     [rsp+0D0h+BugCheckParameter4], rdi; BugCheckParameter4
0x14040c651  call    KeBugCheckEx
0x14040c657  test    byte ptr [rbx+0Ch], 1
0x14040c65b  jnz     loc_14040C548
0x14040c661  test    r15b, r15b
0x14040c664  jnz     loc_14040C548
0x14040c66a  mov     r9d, [rbx+18h]; BugCheckParameter3
0x14040c66e  mov     edx, 0Bh; BugCheckParameter1
0x14040c673  movsxd  r8, dword ptr [rbx+1Ch]; BugCheckParameter2
0x14040c677  mov     ecx, 122h; BugCheckCode
0x14040c67c  mov     [rsp+0D0h+BugCheckParameter4], 0; BugCheckParameter4
0x14040c685  call    KeBugCheckEx
0x14040c68b  or      dword ptr [rdi+68h], 8
0x14040c68f  jmp     loc_14040C43F
0x14040c694  test    r15b, r15b
0x14040c697  jnz     loc_14040C45C
0x14040c69d  mov     rdx, rdi
0x14040c6a0  xor     ecx, ecx
0x14040c6a2  call    sub_14040CC28
0x14040c6a7  mov     edx, [rdi+14h]
0x14040c6aa  mov     r8, rdi
0x14040c6ad  mov     ecx, 1
0x14040c6b2  call    cs:PshedWriteErrorRecord
0x14040c6b9  nop     dword ptr [rax+rax+00h]
0x14040c6be  test    eax, eax
0x14040c6c0  jns     loc_14040C45C
0x14040c6c6  mov     rax, cs:off_140E0CBE8
0x14040c6cd  mov     byte ptr [rax], 1
0x14040c6d0  jmp     loc_14040C45C
0x14040c6d5  test    edx, edx
0x14040c6d7  jnz     loc_140711CD5
0x14040c6dd  lea     rdx, [r14+60h]
0x14040c6e1  mov     rcx, rdi
0x14040c6e4  call    cs:PshedFinalizeErrorRecord
0x14040c6eb  nop     dword ptr [rax+rax+00h]
0x14040c6f0  mov     rcx, rdi
0x14040c6f3  call    sub_140689408
0x14040c6f8  cmp     dword ptr [rdi+0Ch], 2
0x14040c6fc  jz      loc_140711C9C
0x14040c702  test    r15b, r15b
0x14040c705  jnz     loc_140711CA0
0x14040c70b  mov     r8, rbx
0x14040c70e  lea     rdx, [r14+60h]
0x14040c712  mov     rcx, rdi
0x14040c715  call    WheaRecoveryBugCheck
0x14040c71a  jmp     loc_14040C497
0x14040c71f  test    [rbx+0Ch], sil
0x14040c723  jnz     loc_14040C56B
0x14040c729  test    r15b, r15b
0x14040c72c  jnz     loc_14040C56B
0x14040c732  movsxd  rdx, dword ptr [rbx+1Ch]; BugCheckParameter1
0x14040c736  xor     r9d, r9d; BugCheckParameter3
0x14040c739  xor     r8d, r8d; BugCheckParameter2
0x14040c73c  mov     [rsp+0D0h+BugCheckParameter4], rdi; BugCheckParameter4
0x14040c741  mov     ecx, 124h; BugCheckCode
0x14040c746  call    KeBugCheckEx
0x140711bee  mov     eax, 0C00000C0h
0x140711bf3  jmp     loc_14040C49A
0x140711bf8  mov     rcx, rdi
0x140711bfb  call    sub_14040CBB0
0x140711c00  mov     rcx, rsi
0x140711c03  call    sub_14040CB78
0x140711c08  nop
0x140711c09  jmp     loc_14040C497
0x140711c0e  test    r15b, r15b
0x140711c11  jnz     loc_14040C474
0x140711c17  lea     rdx, [r14+60h]
0x140711c1b  mov     rcx, rdi
0x140711c1e  call    cs:PshedFinalizeErrorRecord
0x140711c25  nop     dword ptr [rax+rax+00h]
0x140711c2a  mov     rcx, rdi
0x140711c2d  call    sub_1406894B0
0x140711c32  mov     rdx, rdi
0x140711c35  mov     ecx, 3
0x140711c3a  call    sub_14040CC28
0x140711c3f  mov     edx, [rdi+14h]
0x140711c42  mov     r8, rdi
0x140711c45  xor     ecx, ecx
0x140711c47  call    cs:PshedWriteErrorRecord
0x140711c4e  nop     dword ptr [rax+rax+00h]
0x140711c53  mov     edx, [rdi+14h]
0x140711c56  mov     rcx, rdi
0x140711c59  call    sub_140689320
0x140711c5e  cmp     [rbp+57h+var_A0], r12b
0x140711c62  jz      short loc_140711C83
0x140711c64  mov     rax, [r13+50h]
0x140711c68  mov     r8, rdi; BugCheckParameter2
0x140711c6b  movsxd  rdx, dword ptr [r14+68h]; BugCheckParameter1
  ... truncated ...
```
