# RtlpQueryRegistryValues

- ea: `0x1800c9be0`
- end: `0x1800ca382`
- name: `RtlpQueryRegistryValues`
- size: `1954`
- prototype: ``
- caller_count: `6`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c9100`
- `0x1800c9208`
- `0x1800c93e0`
- `0x1800c9760`
- `0x1800c99e0`
- `0x180147a94`

## callees

- `0x180007060`
- `0x1800c9be0`
- `0x1800ca388`
- `0x1800ca7e4`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e530`
- `0x18015e5b0`
- `0x18015e5d0`
- `0x18015e690`
- `0x18015fea0`
- `0x18016f020`

## string_xrefs

- `0x1800c9ece`: `RtlpQueryRegistryValues: Miscomputed buffer size at line %d\n`
- `0x1800ca2e1`: `RtlpQueryRegistryValues: Miscomputed buffer size at line %d\n`

## pseudocode

```c
__int64 __fastcall RtlpQueryRegistryValues(__int64 a1, const wchar_t *a2, __int64 a3, __int64 a4, __int64 a5, char a6)
{
  __int64 v6; // r15
  int v9; // r13d
  __int64 result; // rax
  int v11; // r13d
  size_t v12; // rax
  int v13; // esi
  __int64 v14; // r14
  HANDLE v15; // rdx
  HANDLE v16; // r10
  unsigned int v17; // r12d
  int v18; // eax
  int v19; // eax
  const wchar_t *v20; // rcx
  int v21; // eax
  int v22; // r12d
  unsigned int v23; // r15d
  int v24; // eax
  size_t v25; // rax
  int v26; // r15d
  int v27; // eax
  int v28; // eax
  size_t v29; // rax
  int v30; // eax
  int v31; // eax
  bool v32; // sf
  unsigned int v33; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v34; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+58h] [rbp-A8h]
  HANDLE Handle; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v38; // [rsp+68h] [rbp-98h] BYREF
  __int128 v39; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+88h] [rbp-78h] BYREF
  __int64 v41; // [rsp+90h] [rbp-70h] BYREF
  __int64 v42; // [rsp+98h] [rbp-68h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v45; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v46; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v47; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v48; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v49; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v50[48]; // [rsp+D8h] [rbp-28h] BYREF

  v6 = a4;
  Handle = 0;
  v34 = 0;
  v35 = 0;
  v33 = 0;
  v9 = a1;
  memset(v50, 0, 44);
  v38 = 0;
  v39 = 0;
  result = RtlpGetRegistryHandle(a1, a2, 0, &Handle);
  if ( (int)result < 0 )
    return result;
  *(_QWORD *)&v38 = 0;
  v11 = v9 & 0x40000000;
  if ( v11 )
  {
    *((_QWORD *)&v38 + 1) = 0;
  }
  else
  {
    *((_QWORD *)&v38 + 1) = a2;
    if ( a2 )
    {
      v12 = 2 * wcslen(a2);
      if ( v12 >= 0xFFFE )
        LOWORD(v12) = -4;
      LOWORD(v38) = v12;
      WORD1(v38) = v12 + 2;
    }
  }
  v35 = 4096;
  v40 = 0;
  v13 = ZwAllocateVirtualMemory(-1, &v40, 0, &v35, 4096, 4);
  if ( v13 >= 0 )
  {
    v14 = v40;
  }
  else
  {
    v14 = 0;
    v40 = 0;
  }
  if ( !v14 )
  {
    if ( !v11 )
      NtClose(Handle);
    return (unsigned int)v13;
  }
  *(_DWORD *)(v14 + 8) = 0;
  v15 = Handle;
  v16 = Handle;
  v17 = v35 - 2;
  v34 = Handle;
  v36 = v35 - 2;
  while ( 1 )
  {
    if ( !*(_QWORD *)a3 && (*(_BYTE *)(a3 + 8) & 0x21) == 0 )
      goto LABEL_42;
    v18 = *(_DWORD *)(a3 + 8);
    if ( (v18 & 0x20) != 0 && (!*(_QWORD *)(a3 + 16) || (v18 & 1) != 0 || *(_QWORD *)a3) )
    {
LABEL_68:
      v13 = -1073741811;
      goto LABEL_42;
    }
    if ( (v18 & 3) != 0 && v16 != v15 )
    {
      NtClose(v16);
      v15 = Handle;
      v16 = Handle;
      v34 = Handle;
    }
    v19 = *(_DWORD *)(a3 + 8);
    v20 = *(const wchar_t **)(a3 + 16);
    if ( (v19 & 1) == 0 )
      break;
    if ( !v20 )
      goto LABEL_68;
    *(_QWORD *)&v38 = 0;
    *((_QWORD *)&v38 + 1) = v20;
    v29 = 2 * wcslen(v20);
    *(_DWORD *)v50 = 48;
    *(_DWORD *)&v50[24] = 576;
    if ( v29 >= 0xFFFE )
      LOWORD(v29) = -4;
    LOWORD(v38) = v29;
    WORD1(v38) = v29 + 2;
    *(_QWORD *)&v50[8] = Handle;
    *(_QWORD *)&v50[16] = &v38;
    *(_OWORD *)&v50[32] = 0;
    v13 = NtOpenKey(&v34, 0x2000000, v50);
    if ( v13 < 0 )
      goto LABEL_38;
    if ( *(_QWORD *)a3 )
    {
      v16 = v34;
      goto LABEL_18;
    }
LABEL_39:
    v15 = Handle;
    a3 += 56;
    v16 = v34;
    v6 = a4;
  }
  if ( v20 )
  {
    *(_QWORD *)&v39 = 0;
    *((_QWORD *)&v39 + 1) = v20;
    v25 = 2 * wcslen(v20);
    if ( v25 >= 0xFFFE )
      LOWORD(v25) = -4;
    LOWORD(v39) = v25;
    WORD1(v39) = v25 + 2;
    v26 = 0;
    while ( 1 )
    {
      if ( v26 > 4 )
      {
        DbgPrint("RtlpQueryRegistryValues: Miscomputed buffer size at line %d\n", 1459);
        goto LABEL_41;
      }
      ++v26;
      v27 = NtQueryValueKey(v34, &v39, 1, v14, v17, &v33);
      v13 = v27;
      if ( v27 == -2147483643 )
        break;
      if ( v27 < 0 )
      {
        if ( v27 == -1073741772 )
        {
          *(_DWORD *)(v14 + 4) = 0;
          *(_DWORD *)(v14 + 12) = 0;
          v33 = v17;
          v30 = RtlpCallQueryRegistryRoutine((_DWORD)v34, a3, v14, (unsigned int)&v33, a4, a5, a6);
          v13 = v30;
LABEL_73:
          if ( v30 != -1073741789 )
            goto LABEL_38;
          v47 = v14;
          v35 = v33 + 10LL;
          v46 = v35;
          v41 = 0;
          if ( v14 )
            ZwFreeVirtualMemory(-1, &v47, &v46, 0x8000);
          v13 = ZwAllocateVirtualMemory(-1, &v41, 0, &v35, 4096, 4);
          if ( v13 >= 0 )
          {
            v14 = v41;
          }
          else
          {
            v14 = 0;
            v41 = 0;
          }
          goto LABEL_78;
        }
LABEL_102:
        v30 = v13;
        goto LABEL_73;
      }
      if ( *(_DWORD *)(v14 + 4) == 7 )
      {
        *(_WORD *)(v33 + v14) = 0;
        *(_DWORD *)(v14 + 12) += 2;
      }
      v33 = v17;
      v28 = RtlpCallQueryRegistryRoutine((_DWORD)v34, a3, v14, (unsigned int)&v33, a4, a5, a6);
      v13 = v28;
      if ( v28 != -1073741789 )
      {
        if ( v28 >= 0 )
        {
          if ( (*(_BYTE *)(a3 + 8) & 0x40) != 0 )
            ZwDeleteValueKey(v34, &v39);
          goto LABEL_39;
        }
        goto LABEL_41;
      }
      v49 = v14;
      v35 = v33 + 10LL;
      v48 = v35;
      v42 = 0;
      ZwFreeVirtualMemory(-1, &v49, &v48, 0x8000);
      v13 = ZwAllocateVirtualMemory(-1, &v42, 0, &v35, 4096, 4);
      if ( v13 >= 0 )
      {
        v14 = v42;
      }
      else
      {
        v14 = 0;
        v42 = 0;
      }
LABEL_78:
      if ( !v14 )
        goto LABEL_41;
      *(_DWORD *)(v14 + 8) = 0;
      v17 = v35 - 2;
      v36 = v35 - 2;
    }
    v13 = -1073741789;
    goto LABEL_102;
  }
  if ( (v19 & 8) != 0 )
  {
    v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, __int64, _QWORD))a3)(
            0,
            0,
            0,
            0,
            v6,
            *(_QWORD *)(a3 + 24));
    goto LABEL_38;
  }
LABEL_18:
  v21 = v36;
  v22 = 0;
  v23 = 0;
  while ( 1 )
  {
    v24 = ZwEnumerateValueKey(v16, v23, 1, v14, v21, &v33);
    v13 = v24;
    if ( v24 == -2147483643 )
    {
      v13 = -1073741789;
LABEL_104:
      v31 = v13;
      goto LABEL_85;
    }
    if ( v24 == -2147483622 )
      break;
    if ( v24 < 0 )
      goto LABEL_104;
    v33 = v36;
    v31 = RtlpCallQueryRegistryRoutine((_DWORD)v34, a3, v14, (unsigned int)&v33, a4, a5, a6);
    v13 = v31;
LABEL_85:
    if ( v31 == -1073741789 )
    {
      v45 = v14;
      v35 = v33 + 10LL;
      v44 = v35;
      v43 = 0;
      if ( v14 )
        ZwFreeVirtualMemory(-1, &v45, &v44, 0x8000);
      v13 = ZwAllocateVirtualMemory(-1, &v43, 0, &v35, 4096, 4);
      if ( v13 >= 0 )
      {
        v14 = v43;
      }
      else
      {
        v14 = 0;
        v43 = 0;
      }
      if ( !v14 )
        goto LABEL_37;
      *(_DWORD *)(v14 + 8) = 0;
      v21 = v35 - 2;
      v36 = v35 - 2;
      if ( v22 > 4 )
      {
        DbgPrint("RtlpQueryRegistryValues: Miscomputed buffer size at line %d\n", 1646);
        goto LABEL_37;
      }
      v16 = v34;
      ++v22;
    }
    else
    {
      if ( v31 < 0 )
        goto LABEL_37;
      v22 = 0;
      if ( (*(_BYTE *)(a3 + 8) & 0x40) != 0 )
      {
        *((_QWORD *)&v39 + 1) = v14 + 20;
        LOWORD(v39) = *(_WORD *)(v14 + 16);
        WORD1(v39) = *(_WORD *)(v14 + 16);
        v32 = (int)ZwDeleteValueKey(v34, &v39) < 0;
        v21 = v36;
        if ( !v32 )
          --v23;
      }
      else
      {
        v21 = v36;
      }
      v16 = v34;
      ++v23;
    }
  }
  if ( v23 || (*(_BYTE *)(a3 + 8) & 4) == 0 )
    v13 = 0;
  else
    v13 = -1073741772;
LABEL_37:
  v17 = v36;
LABEL_38:
  if ( v13 >= 0 )
    goto LABEL_39;
LABEL_41:
  v16 = v34;
  v15 = Handle;
LABEL_42:
  if ( v15 && !v11 )
  {
    NtClose(v15);
    v15 = Handle;
    v16 = v34;
  }
  if ( v16 && v16 != v15 )
    NtClose(v16);
  v45 = v35;
  v44 = v14;
  if ( v14 )
    ZwFreeVirtualMemory(-1, &v44, &v45, 0x8000);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800c9be0  mov     [rsp-8+arg_10], rbx
0x1800c9be5  mov     [rsp-8+arg_18], r9
0x1800c9bea  push    rbp
0x1800c9beb  push    rdi
0x1800c9bec  push    r12
0x1800c9bee  push    r13
0x1800c9bf0  push    r15
0x1800c9bf2  lea     rbp, [rsp-10h]
0x1800c9bf7  sub     rsp, 110h
0x1800c9bfe  xorps   xmm0, xmm0
0x1800c9c01  xor     r12d, r12d
0x1800c9c04  mov     r15, r9
0x1800c9c07  mov     [rsp+130h+Handle], r12
0x1800c9c0c  mov     rdi, r8
0x1800c9c0f  mov     [rsp+130h+var_E8], r12
0x1800c9c14  xorps   xmm1, xmm1
0x1800c9c17  mov     [rsp+130h+var_E0], r12
0x1800c9c1c  movups  [rbp+30h+var_48], xmm0
0x1800c9c20  xor     eax, eax
0x1800c9c22  mov     [rsp+130h+var_F0], r12d
0x1800c9c27  lea     r9, [rsp+130h+Handle]
0x1800c9c2c  xor     r8d, r8d
0x1800c9c2f  movups  [rbp+30h+var_48+0Ch], xmm0
0x1800c9c33  mov     rbx, rdx
0x1800c9c36  mov     r13d, ecx
0x1800c9c39  movups  [rbp+30h+var_58], xmm0
0x1800c9c3d  movups  [rsp+130h+var_C8], xmm0
0x1800c9c42  movups  [rsp+130h+var_B8], xmm1
0x1800c9c47  call    RtlpGetRegistryHandle
0x1800c9c4c  test    eax, eax
0x1800c9c4e  js      loc_1800C9F50
0x1800c9c54  mov     [rsp+130h+arg_0], rsi
0x1800c9c5c  mov     esi, 0FFFCh
0x1800c9c61  mov     [rsp+130h+arg_8], r14
0x1800c9c69  mov     qword ptr [rsp+130h+var_C8], r12
0x1800c9c6e  and     r13d, 40000000h
0x1800c9c75  jnz     short loc_1800C9CA6
0x1800c9c77  mov     qword ptr [rsp+130h+var_C8+8], rbx
0x1800c9c7c  test    rbx, rbx
0x1800c9c7f  jz      short loc_1800C9CAB
0x1800c9c81  mov     rcx, rbx; String
0x1800c9c84  call    wcslen
0x1800c9c89  add     rax, rax
0x1800c9c8c  cmp     rax, 0FFFEh
0x1800c9c92  cmovnb  rax, rsi
0x1800c9c96  mov     word ptr [rsp+130h+var_C8], ax
0x1800c9c9b  add     ax, 2
0x1800c9c9f  mov     word ptr [rsp+130h+var_C8+2], ax
0x1800c9ca4  jmp     short loc_1800C9CAB
0x1800c9ca6  mov     qword ptr [rsp+130h+var_C8+8], r12
0x1800c9cab  mov     dword ptr [rsp+130h+var_108], 4
0x1800c9cb3  lea     r9, [rsp+130h+var_E0]
0x1800c9cb8  xor     r8d, r8d
0x1800c9cbb  mov     dword ptr [rsp+130h+var_110], 1000h
0x1800c9cc3  lea     rdx, [rbp+30h+var_A8]
0x1800c9cc7  mov     [rsp+130h+var_E0], 1000h
0x1800c9cd0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c9cd7  mov     [rbp+30h+var_A8], r12
0x1800c9cdb  call    ZwAllocateVirtualMemory
0x1800c9ce0  mov     esi, eax
0x1800c9ce2  test    eax, eax
0x1800c9ce4  jns     loc_1800CA1E0
0x1800c9cea  mov     r14, r12
0x1800c9ced  mov     [rbp+30h+var_A8], r12
0x1800c9cf1  test    r14, r14
0x1800c9cf4  jz      loc_1800C9F69
0x1800c9cfa  mov     [r14+8], r12d
0x1800c9cfe  mov     rdx, [rsp+130h+Handle]
0x1800c9d03  mov     r12, [rsp+130h+var_E0]
0x1800c9d08  mov     r10, rdx
0x1800c9d0b  add     r12, 0FFFFFFFFFFFFFFFEh
0x1800c9d0f  mov     [rsp+130h+var_E8], rdx
0x1800c9d14  mov     [rsp+130h+var_D8], r12
0x1800c9d19  mov     rcx, [rdi]
0x1800c9d1c  test    rcx, rcx
0x1800c9d1f  jz      loc_1800CA059
0x1800c9d25  mov     eax, [rdi+8]
0x1800c9d28  test    al, 20h
0x1800c9d2a  jnz     loc_1800CA068
0x1800c9d30  test    al, 3
0x1800c9d32  jnz     loc_1800CA00F
0x1800c9d38  mov     eax, [rdi+8]
0x1800c9d3b  mov     rcx, [rdi+10h]; String
0x1800c9d3f  test    al, 1
0x1800c9d41  jnz     loc_1800C9F7A
0x1800c9d47  test    rcx, rcx
0x1800c9d4a  jnz     short loc_1800C9DB6
0x1800c9d4c  test    al, 8
0x1800c9d4e  jnz     loc_1800CA032
0x1800c9d54  mov     rax, [rsp+130h+var_D8]
0x1800c9d59  xor     r12d, r12d
0x1800c9d5c  xor     r15d, r15d
0x1800c9d5f  lea     rcx, [rsp+130h+var_F0]
0x1800c9d64  mov     r9, r14
0x1800c9d67  mov     [rsp+130h+var_108], rcx
0x1800c9d6c  mov     r8d, 1
0x1800c9d72  mov     rcx, r10
0x1800c9d75  mov     dword ptr [rsp+130h+var_110], eax
0x1800c9d79  mov     edx, r15d
0x1800c9d7c  call    ZwEnumerateValueKey
0x1800c9d81  mov     esi, eax
0x1800c9d83  cmp     eax, 80000005h
0x1800c9d88  jz      loc_1800CA376
0x1800c9d8e  cmp     eax, 8000001Ah
0x1800c9d93  jnz     loc_1800CA1F5
0x1800c9d99  test    r15d, r15d
0x1800c9d9c  jnz     loc_1800C9EA7
0x1800c9da2  test    byte ptr [rdi+8], 4
0x1800c9da6  jz      loc_1800C9EA7
0x1800c9dac  mov     esi, 0C0000034h
0x1800c9db1  jmp     loc_1800C9EA9
0x1800c9db6  mov     qword ptr [rsp+130h+var_B8], 0
0x1800c9dbf  mov     qword ptr [rbp+30h+var_B8+8], rcx
0x1800c9dc3  call    wcslen
0x1800c9dc8  add     rax, rax
0x1800c9dcb  mov     ecx, 0FFFCh
0x1800c9dd0  cmp     rax, 0FFFEh
0x1800c9dd6  cmovnb  rax, rcx
0x1800c9dda  mov     word ptr [rsp+130h+var_B8], ax
0x1800c9ddf  add     ax, 2
0x1800c9de3  mov     word ptr [rsp+130h+var_B8+2], ax
0x1800c9de8  xor     r15d, r15d
0x1800c9deb  cmp     r15d, 4
0x1800c9def  jg      loc_1800C9EC9
0x1800c9df5  mov     rcx, [rsp+130h+var_E8]
0x1800c9dfa  lea     rax, [rsp+130h+var_F0]
0x1800c9dff  mov     [rsp+130h+var_108], rax
0x1800c9e04  lea     rdx, [rsp+130h+var_B8]
0x1800c9e09  mov     r9, r14
0x1800c9e0c  mov     dword ptr [rsp+130h+var_110], r12d
0x1800c9e11  mov     r8d, 1
0x1800c9e17  inc     r15d
0x1800c9e1a  call    NtQueryValueKey
0x1800c9e1f  mov     esi, eax
0x1800c9e21  cmp     eax, 80000005h
0x1800c9e26  jz      loc_1800CA36A
0x1800c9e2c  test    eax, eax
0x1800c9e2e  js      loc_1800CA0FA
0x1800c9e34  cmp     dword ptr [r14+4], 7
0x1800c9e39  jnz     short loc_1800C9E4B
0x1800c9e3b  mov     ecx, [rsp+130h+var_F0]
0x1800c9e3f  xor     eax, eax
0x1800c9e41  mov     [rcx+r14], ax
0x1800c9e46  add     dword ptr [r14+0Ch], 2
0x1800c9e4b  movzx   eax, [rbp+30h+arg_28]
0x1800c9e4f  lea     r9, [rsp+130h+var_F0]
0x1800c9e54  mov     rcx, [rsp+130h+var_E8]
0x1800c9e59  mov     r8, r14
0x1800c9e5c  mov     [rsp+130h+var_100], al
0x1800c9e60  mov     rdx, rdi
0x1800c9e63  mov     rax, [rbp+30h+arg_20]
0x1800c9e67  mov     [rsp+130h+var_108], rax
0x1800c9e6c  mov     rax, [rbp+30h+arg_18]
0x1800c9e70  mov     [rsp+130h+var_110], rax
0x1800c9e75  mov     [rsp+130h+var_F0], r12d
0x1800c9e7a  call    RtlpCallQueryRegistryRoutine
0x1800c9e7f  mov     esi, eax
0x1800c9e81  cmp     eax, 0C0000023h
0x1800c9e86  jz      loc_1800CA086
0x1800c9e8c  test    eax, eax
0x1800c9e8e  js      short loc_1800C9EDA
0x1800c9e90  test    byte ptr [rdi+8], 40h
0x1800c9e94  jz      short loc_1800C9EB2
0x1800c9e96  mov     rcx, [rsp+130h+var_E8]
0x1800c9e9b  lea     rdx, [rsp+130h+var_B8]
0x1800c9ea0  call    ZwDeleteValueKey
0x1800c9ea5  jmp     short loc_1800C9EB2
0x1800c9ea7  xor     esi, esi
0x1800c9ea9  mov     r12, [rsp+130h+var_D8]
0x1800c9eae  test    esi, esi
0x1800c9eb0  js      short loc_1800C9EDA
0x1800c9eb2  mov     rdx, [rsp+130h+Handle]
0x1800c9eb7  add     rdi, 38h ; '8'
0x1800c9ebb  mov     r10, [rsp+130h+var_E8]
0x1800c9ec0  mov     r15, [rbp+30h+arg_18]
0x1800c9ec4  jmp     loc_1800C9D19
0x1800c9ec9  mov     edx, 5B3h
0x1800c9ece  lea     rcx, aRtlpqueryregis; "RtlpQueryRegistryValues: Miscomputed bu"...
0x1800c9ed5  call    DbgPrint
0x1800c9eda  mov     r10, [rsp+130h+var_E8]
0x1800c9edf  mov     rdx, [rsp+130h+Handle]
0x1800c9ee4  test    rdx, rdx
0x1800c9ee7  jz      short loc_1800C9F00
0x1800c9ee9  test    r13d, r13d
0x1800c9eec  jnz     short loc_1800C9F00
0x1800c9eee  mov     rcx, rdx; Handle
0x1800c9ef1  call    NtClose
0x1800c9ef6  mov     rdx, [rsp+130h+Handle]
0x1800c9efb  mov     r10, [rsp+130h+var_E8]
0x1800c9f00  test    r10, r10
0x1800c9f03  jz      short loc_1800C9F12
0x1800c9f05  cmp     r10, rdx
0x1800c9f08  jz      short loc_1800C9F12
0x1800c9f0a  mov     rcx, r10; Handle
0x1800c9f0d  call    NtClose
0x1800c9f12  mov     rax, [rsp+130h+var_E0]
0x1800c9f17  mov     [rbp+30h+var_80], rax
0x1800c9f1b  mov     [rbp+30h+var_88], r14
0x1800c9f1f  test    r14, r14
0x1800c9f22  jz      short loc_1800C9F3E
0x1800c9f24  mov     r9d, 8000h
0x1800c9f2a  lea     r8, [rbp+30h+var_80]
0x1800c9f2e  lea     rdx, [rbp+30h+var_88]
0x1800c9f32  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c9f39  call    ZwFreeVirtualMemory
0x1800c9f3e  mov     r14, [rsp+130h+arg_8]
0x1800c9f46  mov     eax, esi
0x1800c9f48  mov     rsi, [rsp+130h+arg_0]
0x1800c9f50  mov     rbx, [rsp+130h+arg_10]
0x1800c9f58  add     rsp, 110h
0x1800c9f5f  pop     r15
0x1800c9f61  pop     r13
0x1800c9f63  pop     r12
0x1800c9f65  pop     rdi
0x1800c9f66  pop     rbp
0x1800c9f67  retn
0x1800c9f69  test    r13d, r13d
0x1800c9f6c  jnz     short loc_1800C9F3E
0x1800c9f6e  mov     rcx, [rsp+130h+Handle]; Handle
0x1800c9f73  call    NtClose
0x1800c9f78  jmp     short loc_1800C9F3E
0x1800c9f7a  test    rcx, rcx
0x1800c9f7d  jz      loc_1800CA07C
0x1800c9f83  mov     qword ptr [rsp+130h+var_C8], 0
0x1800c9f8c  mov     qword ptr [rsp+130h+var_C8+8], rcx
0x1800c9f91  call    wcslen
0x1800c9f96  add     rax, rax
0x1800c9f99  mov     dword ptr [rbp+30h+var_58], 30h ; '0'
0x1800c9fa0  cmp     rax, 0FFFEh
0x1800c9fa6  mov     dword ptr [rbp+30h+var_48+8], 240h
0x1800c9fad  mov     ecx, 0FFFCh
0x1800c9fb2  lea     r8, [rbp+30h+var_58]
0x1800c9fb6  cmovnb  rax, rcx
0x1800c9fba  xorps   xmm0, xmm0
0x1800c9fbd  mov     word ptr [rsp+130h+var_C8], ax
0x1800c9fc2  lea     rcx, [rsp+130h+var_E8]
0x1800c9fc7  add     ax, 2
0x1800c9fcb  mov     edx, 2000000h
0x1800c9fd0  mov     word ptr [rsp+130h+var_C8+2], ax
0x1800c9fd5  mov     rax, [rsp+130h+Handle]
0x1800c9fda  mov     qword ptr [rbp+30h+var_58+8], rax
0x1800c9fde  lea     rax, [rsp+130h+var_C8]
0x1800c9fe3  mov     qword ptr [rbp+30h+var_48], rax
0x1800c9fe7  movdqu  [rbp+30h+var_38], xmm0
0x1800c9fec  call    NtOpenKey
0x1800c9ff1  mov     esi, eax
0x1800c9ff3  test    eax, eax
0x1800c9ff5  js      loc_1800C9EAE
0x1800c9ffb  cmp     qword ptr [rdi], 0
0x1800c9fff  jz      loc_1800C9EB2
0x1800ca005  mov     r10, [rsp+130h+var_E8]
0x1800ca00a  jmp     loc_1800C9D54
0x1800ca00f  cmp     r10, rdx
0x1800ca012  jz      loc_1800C9D38
0x1800ca018  mov     rcx, r10; Handle
0x1800ca01b  call    NtClose
0x1800ca020  mov     rdx, [rsp+130h+Handle]
0x1800ca025  mov     r10, rdx
0x1800ca028  mov     [rsp+130h+var_E8], rdx
0x1800ca02d  jmp     loc_1800C9D38
0x1800ca032  mov     rcx, [rdi+18h]
0x1800ca036  xor     r9d, r9d
0x1800ca039  mov     rax, [rdi]
0x1800ca03c  xor     r8d, r8d
0x1800ca03f  mov     [rsp+130h+var_108], rcx
0x1800ca044  xor     edx, edx
0x1800ca046  xor     ecx, ecx
0x1800ca048  mov     [rsp+130h+var_110], r15
0x1800ca04d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca052  mov     esi, eax
0x1800ca054  jmp     loc_1800C9EAE
0x1800ca059  test    byte ptr [rdi+8], 21h
0x1800ca05d  jnz     loc_1800C9D25
0x1800ca063  jmp     loc_1800C9EE4
0x1800ca068  cmp     qword ptr [rdi+10h], 0
0x1800ca06d  jz      short loc_1800CA07C
0x1800ca06f  test    al, 1
0x1800ca071  jnz     short loc_1800CA07C
0x1800ca073  test    rcx, rcx
0x1800ca076  jz      loc_1800C9D30
0x1800ca07c  mov     esi, 0C000000Dh
0x1800ca081  jmp     loc_1800C9EE4
0x1800ca086  mov     eax, [rsp+130h+var_F0]
0x1800ca08a  lea     r8, [rbp+30h+var_68]
0x1800ca08e  add     rax, 0Ah
0x1800ca092  mov     [rbp+30h+var_60], r14
0x1800ca096  xor     r12d, r12d
0x1800ca099  mov     [rsp+130h+var_E0], rax
0x1800ca09e  mov     r9d, 8000h
0x1800ca0a4  mov     [rbp+30h+var_68], rax
0x1800ca0a8  lea     rdx, [rbp+30h+var_60]
0x1800ca0ac  mov     [rbp+30h+var_98], r12
0x1800ca0b0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ca0b7  call    ZwFreeVirtualMemory
0x1800ca0bc  lea     r9, [rsp+130h+var_E0]
0x1800ca0c1  mov     dword ptr [rsp+130h+var_108], 4
0x1800ca0c9  xor     r8d, r8d
0x1800ca0cc  mov     dword ptr [rsp+130h+var_110], 1000h
0x1800ca0d4  lea     rdx, [rbp+30h+var_98]
0x1800ca0d8  mov     rcx, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
