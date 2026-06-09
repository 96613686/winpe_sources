# CmCheckRegistry

- ea: `0x14002a338`
- end: `0x14002a57a`
- name: `CmCheckRegistry`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002785c`

## callees

- `0x140002b2c`
- `0x14002a338`
- `0x14002b75c`
- `0x14002d7d4`
- `0x14002e228`
- `0x140031f38`
- `0x140034010`

## pseudocode

```c
__int64 __fastcall CmCheckRegistry(__int64 a1, int a2, __int64 a3)
{
  unsigned int v5; // ebx
  int v6; // ebx
  unsigned int v7; // r15d
  void *v8; // rax
  void *v9; // r12
  char i; // si
  int v11; // edx
  int v12; // r8d
  int v13; // eax
  unsigned int v14; // edx
  __int64 v15; // rdx
  int v16; // r9d
  int v18; // [rsp+28h] [rbp-39h]
  __int64 v19; // [rsp+48h] [rbp-19h] BYREF
  void *v20; // [rsp+50h] [rbp-11h]
  __int128 v21; // [rsp+58h] [rbp-9h] BYREF
  __int128 v22; // [rsp+68h] [rbp+7h]
  __int128 v23; // [rsp+78h] [rbp+17h]
  __int64 v24; // [rsp+88h] [rbp+27h]
  int v25; // [rsp+C8h] [rbp+67h] BYREF
  int v26; // [rsp+D0h] [rbp+6Fh] BYREF

  v26 = a2;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v24 = 0;
  v22 = 0;
  v25 = 0;
  v23 = 0;
  LOBYTE(v26) = 0;
  if ( a1 == CmpMasterHive )
    return 0;
  v6 = *(_DWORD *)(a1 + 288) >> 3;
  v7 = (((unsigned int)(v6 + 7) >> 3) + 7) & 0xFFFFFFF8;
  v8 = (void *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 24))(v7, 0, 1649167683);
  v9 = v8;
  if ( !v8 )
  {
    v5 = -1073741670;
    SetFailureLocation(a3, 0, 11, -1073741670, 0);
    return v5;
  }
  LODWORD(v19) = v6;
  v20 = v8;
  memset_0(v8, 0, 4 * ((unsigned int)(v6 + 31) >> 5));
  for ( i = 0; ; i = 1 )
  {
    memset_0(v20, 0, 4 * ((unsigned int)(v19 + 31) >> 5));
    v13 = HvCheckHive(a1, v11, v12, (unsigned int)&v19, (__int64)&v21, a3);
    v5 = v13;
    if ( v13 < 0 )
      break;
    v14 = v21 + v22 + v23;
    if ( v14 > 0x100000 )
      *(_DWORD *)(a1 + 4128) |= 0x400u;
    *(_QWORD *)(a1 + 4768) = v24;
    if ( *(int *)(*(_QWORD *)(a1 + 64) + 36LL) < 0 )
    {
      v5 = -1073741492;
      SetFailureLocation(a3, 0, 11, -1073741492, 32);
      goto LABEL_25;
    }
    v13 = CmpValidateHiveSecurityDescriptors(a1, v14, &v26, (__int64)&v19, a3);
    v5 = v13;
    if ( v13 >= 0 )
      goto LABEL_13;
    if ( v13 == -2147483606 )
    {
      i = 1;
LABEL_13:
      v13 = CmpCheckRegistry2(a1, v15, *(_DWORD *)(*(_QWORD *)(a1 + 64) + 36LL), v16, v26, (__int64)&v19, a3, &v25);
      v5 = v13;
      if ( v13 >= 0 )
        goto LABEL_21;
      if ( v13 == -2147483606 )
      {
        i = 1;
LABEL_21:
        *(_DWORD *)(a1 + 4780) = v25;
        v5 = i != 0 ? 0x8000002A : 0;
        goto LABEL_25;
      }
      if ( v13 != -1073741267 )
      {
        v18 = 64;
        goto LABEL_24;
      }
      continue;
    }
    if ( v13 != -1073741267 )
    {
      v18 = 48;
      goto LABEL_24;
    }
  }
  v18 = 16;
LABEL_24:
  SetFailureLocation(a3, 0, 11, v13, v18);
LABEL_25:
  (*(void (__fastcall **)(void *, _QWORD))(a1 + 32))(v9, v7);
  return v5;
}

```

## disassembly

```asm
0x14002a338  mov     rax, rsp
0x14002a33b  mov     [rax+18h], rbx
0x14002a33f  mov     [rax+20h], rsi
0x14002a343  mov     [rax+10h], edx
0x14002a346  push    rbp
0x14002a347  push    rdi
0x14002a348  push    r12
0x14002a34a  push    r14
0x14002a34c  push    r15
0x14002a34e  lea     rbp, [rax-5Fh]
0x14002a352  sub     rsp, 90h
0x14002a359  xor     eax, eax
0x14002a35b  xorps   xmm0, xmm0
0x14002a35e  cmp     rcx, cs:CmpMasterHive
0x14002a365  mov     r14, r8
0x14002a368  mov     rdi, rcx
0x14002a36b  mov     [rbp+57h+var_70], rax
0x14002a36f  mov     [rbp+57h+var_68], rax
0x14002a373  movups  [rbp+57h+var_60], xmm0
0x14002a377  mov     [rbp+57h+var_30], rax
0x14002a37b  movups  [rbp+57h+var_50], xmm0
0x14002a37f  mov     [rbp+57h+arg_0], eax
0x14002a382  movups  [rbp+57h+var_40], xmm0
0x14002a386  mov     byte ptr [rbp+57h+arg_8], al
0x14002a389  jnz     short loc_14002A392
0x14002a38b  xor     ebx, ebx
0x14002a38d  jmp     loc_14002A55B
0x14002a392  mov     ebx, [rcx+120h]
0x14002a398  xor     edx, edx
0x14002a39a  mov     rax, [rdi+18h]
0x14002a39e  mov     r8d, 624C4D43h
0x14002a3a4  shr     ebx, 3
0x14002a3a7  lea     r15d, [rbx+7]
0x14002a3ab  shr     r15d, 3
0x14002a3af  add     r15d, 7
0x14002a3b3  and     r15d, 0FFFFFFF8h
0x14002a3b7  mov     ecx, r15d
0x14002a3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a3bf  xor     edx, edx; Val
0x14002a3c1  mov     r12, rax
0x14002a3c4  test    rax, rax
0x14002a3c7  jnz     short loc_14002A3E6
0x14002a3c9  mov     ebx, 0C000009Ah
0x14002a3ce  mov     dword ptr [rsp+0B0h+var_90], edx
0x14002a3d2  mov     r9d, ebx
0x14002a3d5  lea     r8d, [rax+0Bh]
0x14002a3d9  mov     rcx, r14
0x14002a3dc  call    SetFailureLocation
0x14002a3e1  jmp     loc_14002A55B
0x14002a3e6  lea     r8d, [rbx+1Fh]
0x14002a3ea  mov     dword ptr [rbp+57h+var_70], ebx
0x14002a3ed  shr     r8d, 5
0x14002a3f1  mov     rcx, r12; void *
0x14002a3f4  shl     r8d, 2; Size
0x14002a3f8  mov     [rbp+57h+var_68], r12
0x14002a3fc  call    memset_0
0x14002a401  xor     sil, sil
0x14002a404  mov     r8d, dword ptr [rbp+57h+var_70]
0x14002a408  xor     edx, edx; Val
0x14002a40a  mov     rcx, [rbp+57h+var_68]; void *
0x14002a40e  add     r8d, 1Fh
0x14002a412  shr     r8d, 5
0x14002a416  shl     r8d, 2; Size
0x14002a41a  call    memset_0
0x14002a41f  lea     rax, [rbp+57h+var_60]
0x14002a423  mov     [rsp+0B0h+var_88], r14
0x14002a428  lea     r9, [rbp+57h+var_70]
0x14002a42c  mov     [rsp+0B0h+var_90], rax
0x14002a431  mov     rcx, rdi
0x14002a434  call    HvCheckHive
0x14002a439  mov     ebx, eax
0x14002a43b  test    eax, eax
0x14002a43d  js      loc_14002A531
0x14002a443  mov     edx, dword ptr [rbp+57h+var_40]
0x14002a446  add     edx, dword ptr [rbp+57h+var_50]
0x14002a449  add     edx, dword ptr [rbp+57h+var_60]
0x14002a44c  cmp     edx, 100000h
0x14002a452  jbe     short loc_14002A45C
0x14002a454  bts     dword ptr [rdi+1020h], 0Ah
0x14002a45c  mov     eax, dword ptr [rbp+57h+var_30]
0x14002a45f  mov     [rdi+12A0h], eax
0x14002a465  mov     eax, dword ptr [rbp+57h+var_30+4]
0x14002a468  mov     [rdi+12A4h], eax
0x14002a46e  mov     rax, [rdi+40h]
0x14002a472  cmp     dword ptr [rax+24h], 0
0x14002a476  jl      loc_14002A51F
0x14002a47c  lea     r9, [rbp+57h+var_70]
0x14002a480  mov     [rsp+0B0h+var_90], r14
0x14002a485  lea     r8, [rbp+57h+arg_8]
0x14002a489  mov     rcx, rdi
0x14002a48c  call    CmpValidateHiveSecurityDescriptors
0x14002a491  mov     ebx, eax
0x14002a493  test    eax, eax
0x14002a495  jns     short loc_14002A4A1
0x14002a497  cmp     eax, 8000002Ah
0x14002a49c  jnz     short loc_14002A4ED
0x14002a49e  mov     sil, 1
0x14002a4a1  mov     r8, [rdi+40h]
0x14002a4a5  lea     rax, [rbp+57h+arg_0]
0x14002a4a9  mov     [rsp+0B0h+var_78], rax
0x14002a4ae  mov     rcx, rdi
0x14002a4b1  lea     rax, [rbp+57h+var_70]
0x14002a4b5  mov     [rsp+0B0h+var_80], r14
0x14002a4ba  mov     [rsp+0B0h+var_88], rax
0x14002a4bf  mov     al, byte ptr [rbp+57h+arg_8]
0x14002a4c2  mov     r8d, [r8+24h]
0x14002a4c6  mov     byte ptr [rsp+0B0h+var_90], al
0x14002a4ca  call    CmpCheckRegistry2
0x14002a4cf  mov     ebx, eax
0x14002a4d1  test    eax, eax
0x14002a4d3  jns     short loc_14002A509
0x14002a4d5  cmp     eax, 8000002Ah
0x14002a4da  jz      short loc_14002A506
0x14002a4dc  cmp     eax, 0C000022Dh
0x14002a4e1  jz      short loc_14002A4F4
0x14002a4e3  mov     dword ptr [rsp+0B0h+var_90], 40h ; '@'
0x14002a4eb  jmp     short loc_14002A539
0x14002a4ed  cmp     eax, 0C000022Dh
0x14002a4f2  jnz     short loc_14002A4FC
0x14002a4f4  mov     sil, 1
0x14002a4f7  jmp     loc_14002A404
0x14002a4fc  mov     dword ptr [rsp+0B0h+var_90], 30h ; '0'
0x14002a504  jmp     short loc_14002A539
0x14002a506  mov     sil, 1
0x14002a509  mov     eax, [rbp+57h+arg_0]
0x14002a50c  neg     sil
0x14002a50f  mov     [rdi+12ACh], eax
0x14002a515  sbb     ebx, ebx
0x14002a517  and     ebx, 8000002Ah
0x14002a51d  jmp     short loc_14002A54C
0x14002a51f  mov     ebx, 0C000014Ch
0x14002a524  mov     dword ptr [rsp+0B0h+var_90], 20h ; ' '
0x14002a52c  mov     r9d, ebx
0x14002a52f  jmp     short loc_14002A53C
0x14002a531  mov     dword ptr [rsp+0B0h+var_90], 10h
0x14002a539  mov     r9d, eax
0x14002a53c  mov     r8d, 0Bh
0x14002a542  xor     edx, edx
0x14002a544  mov     rcx, r14
0x14002a547  call    SetFailureLocation
0x14002a54c  mov     rax, [rdi+20h]
0x14002a550  mov     edx, r15d
0x14002a553  mov     rcx, r12
0x14002a556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a55b  lea     r11, [rsp+0B0h+var_20]
0x14002a563  mov     eax, ebx
0x14002a565  mov     rbx, [r11+40h]
0x14002a569  mov     rsi, [r11+48h]
0x14002a56d  mov     rsp, r11
0x14002a570  pop     r15
0x14002a572  pop     r14
0x14002a574  pop     r12
0x14002a576  pop     rdi
0x14002a577  pop     rbp
0x14002a578  retn
```
