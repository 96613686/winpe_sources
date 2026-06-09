# RtlpQueryRegistryValues

- ea: `0x1800382d0`
- end: `0x180038a72`
- name: `RtlpQueryRegistryValues`
- size: `1954`
- prototype: ``
- caller_count: `6`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037cfc`
- `0x1800380d0`
- `0x180039610`
- `0x180039a30`
- `0x18010ad40`
- `0x1801483f4`

## callees

- `0x180007060`
- `0x1800382d0`
- `0x180038a78`
- `0x180038ed4`
- `0x18012d320`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015ed40`
- `0x18015edc0`
- `0x18015ede0`
- `0x18015eea0`
- `0x1801606b0`
- `0x18016f020`

## string_xrefs

- `0x1800385be`: `RtlpQueryRegistryValues: Miscomputed buffer size at line %d\n`
- `0x1800389d1`: `RtlpQueryRegistryValues: Miscomputed buffer size at line %d\n`

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
0x1800382d0  mov     [rsp-8+arg_10], rbx
0x1800382d5  mov     [rsp-8+arg_18], r9
0x1800382da  push    rbp
0x1800382db  push    rdi
0x1800382dc  push    r12
0x1800382de  push    r13
0x1800382e0  push    r15
0x1800382e2  lea     rbp, [rsp-10h]
0x1800382e7  sub     rsp, 110h
0x1800382ee  xorps   xmm0, xmm0
0x1800382f1  xor     r12d, r12d
0x1800382f4  mov     r15, r9
0x1800382f7  mov     [rsp+130h+Handle], r12
0x1800382fc  mov     rdi, r8
0x1800382ff  mov     [rsp+130h+var_E8], r12
0x180038304  xorps   xmm1, xmm1
0x180038307  mov     [rsp+130h+var_E0], r12
0x18003830c  movups  [rbp+30h+var_48], xmm0
0x180038310  xor     eax, eax
0x180038312  mov     [rsp+130h+var_F0], r12d
0x180038317  lea     r9, [rsp+130h+Handle]
0x18003831c  xor     r8d, r8d
0x18003831f  movups  [rbp+30h+var_48+0Ch], xmm0
0x180038323  mov     rbx, rdx
0x180038326  mov     r13d, ecx
0x180038329  movups  [rbp+30h+var_58], xmm0
0x18003832d  movups  [rsp+130h+var_C8], xmm0
0x180038332  movups  [rsp+130h+var_B8], xmm1
0x180038337  call    RtlpGetRegistryHandle
0x18003833c  test    eax, eax
0x18003833e  js      loc_180038640
0x180038344  mov     [rsp+130h+arg_0], rsi
0x18003834c  mov     esi, 0FFFCh
0x180038351  mov     [rsp+130h+arg_8], r14
0x180038359  mov     qword ptr [rsp+130h+var_C8], r12
0x18003835e  and     r13d, 40000000h
0x180038365  jnz     short loc_180038396
0x180038367  mov     qword ptr [rsp+130h+var_C8+8], rbx
0x18003836c  test    rbx, rbx
0x18003836f  jz      short loc_18003839B
0x180038371  mov     rcx, rbx; String
0x180038374  call    wcslen
0x180038379  add     rax, rax
0x18003837c  cmp     rax, 0FFFEh
0x180038382  cmovnb  rax, rsi
0x180038386  mov     word ptr [rsp+130h+var_C8], ax
0x18003838b  add     ax, 2
0x18003838f  mov     word ptr [rsp+130h+var_C8+2], ax
0x180038394  jmp     short loc_18003839B
0x180038396  mov     qword ptr [rsp+130h+var_C8+8], r12
0x18003839b  mov     dword ptr [rsp+130h+var_108], 4
0x1800383a3  lea     r9, [rsp+130h+var_E0]
0x1800383a8  xor     r8d, r8d
0x1800383ab  mov     dword ptr [rsp+130h+var_110], 1000h
0x1800383b3  lea     rdx, [rbp+30h+var_A8]
0x1800383b7  mov     [rsp+130h+var_E0], 1000h
0x1800383c0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800383c7  mov     [rbp+30h+var_A8], r12
0x1800383cb  call    ZwAllocateVirtualMemory
0x1800383d0  mov     esi, eax
0x1800383d2  test    eax, eax
0x1800383d4  jns     loc_1800388D0
0x1800383da  mov     r14, r12
0x1800383dd  mov     [rbp+30h+var_A8], r12
0x1800383e1  test    r14, r14
0x1800383e4  jz      loc_180038659
0x1800383ea  mov     [r14+8], r12d
0x1800383ee  mov     rdx, [rsp+130h+Handle]
0x1800383f3  mov     r12, [rsp+130h+var_E0]
0x1800383f8  mov     r10, rdx
0x1800383fb  add     r12, 0FFFFFFFFFFFFFFFEh
0x1800383ff  mov     [rsp+130h+var_E8], rdx
0x180038404  mov     [rsp+130h+var_D8], r12
0x180038409  mov     rcx, [rdi]
0x18003840c  test    rcx, rcx
0x18003840f  jz      loc_180038749
0x180038415  mov     eax, [rdi+8]
0x180038418  test    al, 20h
0x18003841a  jnz     loc_180038758
0x180038420  test    al, 3
0x180038422  jnz     loc_1800386FF
0x180038428  mov     eax, [rdi+8]
0x18003842b  mov     rcx, [rdi+10h]; String
0x18003842f  test    al, 1
0x180038431  jnz     loc_18003866A
0x180038437  test    rcx, rcx
0x18003843a  jnz     short loc_1800384A6
0x18003843c  test    al, 8
0x18003843e  jnz     loc_180038722
0x180038444  mov     rax, [rsp+130h+var_D8]
0x180038449  xor     r12d, r12d
0x18003844c  xor     r15d, r15d
0x18003844f  lea     rcx, [rsp+130h+var_F0]
0x180038454  mov     r9, r14
0x180038457  mov     [rsp+130h+var_108], rcx
0x18003845c  mov     r8d, 1
0x180038462  mov     rcx, r10
0x180038465  mov     dword ptr [rsp+130h+var_110], eax
0x180038469  mov     edx, r15d
0x18003846c  call    ZwEnumerateValueKey
0x180038471  mov     esi, eax
0x180038473  cmp     eax, 80000005h
0x180038478  jz      loc_180038A66
0x18003847e  cmp     eax, 8000001Ah
0x180038483  jnz     loc_1800388E5
0x180038489  test    r15d, r15d
0x18003848c  jnz     loc_180038597
0x180038492  test    byte ptr [rdi+8], 4
0x180038496  jz      loc_180038597
0x18003849c  mov     esi, 0C0000034h
0x1800384a1  jmp     loc_180038599
0x1800384a6  mov     qword ptr [rsp+130h+var_B8], 0
0x1800384af  mov     qword ptr [rbp+30h+var_B8+8], rcx
0x1800384b3  call    wcslen
0x1800384b8  add     rax, rax
0x1800384bb  mov     ecx, 0FFFCh
0x1800384c0  cmp     rax, 0FFFEh
0x1800384c6  cmovnb  rax, rcx
0x1800384ca  mov     word ptr [rsp+130h+var_B8], ax
0x1800384cf  add     ax, 2
0x1800384d3  mov     word ptr [rsp+130h+var_B8+2], ax
0x1800384d8  xor     r15d, r15d
0x1800384db  cmp     r15d, 4
0x1800384df  jg      loc_1800385B9
0x1800384e5  mov     rcx, [rsp+130h+var_E8]
0x1800384ea  lea     rax, [rsp+130h+var_F0]
0x1800384ef  mov     [rsp+130h+var_108], rax
0x1800384f4  lea     rdx, [rsp+130h+var_B8]
0x1800384f9  mov     r9, r14
0x1800384fc  mov     dword ptr [rsp+130h+var_110], r12d
0x180038501  mov     r8d, 1
0x180038507  inc     r15d
0x18003850a  call    NtQueryValueKey
0x18003850f  mov     esi, eax
0x180038511  cmp     eax, 80000005h
0x180038516  jz      loc_180038A5A
0x18003851c  test    eax, eax
0x18003851e  js      loc_1800387EA
0x180038524  cmp     dword ptr [r14+4], 7
0x180038529  jnz     short loc_18003853B
0x18003852b  mov     ecx, [rsp+130h+var_F0]
0x18003852f  xor     eax, eax
0x180038531  mov     [rcx+r14], ax
0x180038536  add     dword ptr [r14+0Ch], 2
0x18003853b  movzx   eax, [rbp+30h+arg_28]
0x18003853f  lea     r9, [rsp+130h+var_F0]
0x180038544  mov     rcx, [rsp+130h+var_E8]
0x180038549  mov     r8, r14
0x18003854c  mov     [rsp+130h+var_100], al
0x180038550  mov     rdx, rdi
0x180038553  mov     rax, [rbp+30h+arg_20]
0x180038557  mov     [rsp+130h+var_108], rax
0x18003855c  mov     rax, [rbp+30h+arg_18]
0x180038560  mov     [rsp+130h+var_110], rax
0x180038565  mov     [rsp+130h+var_F0], r12d
0x18003856a  call    RtlpCallQueryRegistryRoutine
0x18003856f  mov     esi, eax
0x180038571  cmp     eax, 0C0000023h
0x180038576  jz      loc_180038776
0x18003857c  test    eax, eax
0x18003857e  js      short loc_1800385CA
0x180038580  test    byte ptr [rdi+8], 40h
0x180038584  jz      short loc_1800385A2
0x180038586  mov     rcx, [rsp+130h+var_E8]
0x18003858b  lea     rdx, [rsp+130h+var_B8]
0x180038590  call    ZwDeleteValueKey
0x180038595  jmp     short loc_1800385A2
0x180038597  xor     esi, esi
0x180038599  mov     r12, [rsp+130h+var_D8]
0x18003859e  test    esi, esi
0x1800385a0  js      short loc_1800385CA
0x1800385a2  mov     rdx, [rsp+130h+Handle]
0x1800385a7  add     rdi, 38h ; '8'
0x1800385ab  mov     r10, [rsp+130h+var_E8]
0x1800385b0  mov     r15, [rbp+30h+arg_18]
0x1800385b4  jmp     loc_180038409
0x1800385b9  mov     edx, 5B3h
0x1800385be  lea     rcx, aRtlpqueryregis; "RtlpQueryRegistryValues: Miscomputed bu"...
0x1800385c5  call    DbgPrint
0x1800385ca  mov     r10, [rsp+130h+var_E8]
0x1800385cf  mov     rdx, [rsp+130h+Handle]
0x1800385d4  test    rdx, rdx
0x1800385d7  jz      short loc_1800385F0
0x1800385d9  test    r13d, r13d
0x1800385dc  jnz     short loc_1800385F0
0x1800385de  mov     rcx, rdx; Handle
0x1800385e1  call    NtClose
0x1800385e6  mov     rdx, [rsp+130h+Handle]
0x1800385eb  mov     r10, [rsp+130h+var_E8]
0x1800385f0  test    r10, r10
0x1800385f3  jz      short loc_180038602
0x1800385f5  cmp     r10, rdx
0x1800385f8  jz      short loc_180038602
0x1800385fa  mov     rcx, r10; Handle
0x1800385fd  call    NtClose
0x180038602  mov     rax, [rsp+130h+var_E0]
0x180038607  mov     [rbp+30h+var_80], rax
0x18003860b  mov     [rbp+30h+var_88], r14
0x18003860f  test    r14, r14
0x180038612  jz      short loc_18003862E
0x180038614  mov     r9d, 8000h
0x18003861a  lea     r8, [rbp+30h+var_80]
0x18003861e  lea     rdx, [rbp+30h+var_88]
0x180038622  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180038629  call    ZwFreeVirtualMemory
0x18003862e  mov     r14, [rsp+130h+arg_8]
0x180038636  mov     eax, esi
0x180038638  mov     rsi, [rsp+130h+arg_0]
0x180038640  mov     rbx, [rsp+130h+arg_10]
0x180038648  add     rsp, 110h
0x18003864f  pop     r15
0x180038651  pop     r13
0x180038653  pop     r12
0x180038655  pop     rdi
0x180038656  pop     rbp
0x180038657  retn
0x180038659  test    r13d, r13d
0x18003865c  jnz     short loc_18003862E
0x18003865e  mov     rcx, [rsp+130h+Handle]; Handle
0x180038663  call    NtClose
0x180038668  jmp     short loc_18003862E
0x18003866a  test    rcx, rcx
0x18003866d  jz      loc_18003876C
0x180038673  mov     qword ptr [rsp+130h+var_C8], 0
0x18003867c  mov     qword ptr [rsp+130h+var_C8+8], rcx
0x180038681  call    wcslen
0x180038686  add     rax, rax
0x180038689  mov     dword ptr [rbp+30h+var_58], 30h ; '0'
0x180038690  cmp     rax, 0FFFEh
0x180038696  mov     dword ptr [rbp+30h+var_48+8], 240h
0x18003869d  mov     ecx, 0FFFCh
0x1800386a2  lea     r8, [rbp+30h+var_58]
0x1800386a6  cmovnb  rax, rcx
0x1800386aa  xorps   xmm0, xmm0
0x1800386ad  mov     word ptr [rsp+130h+var_C8], ax
0x1800386b2  lea     rcx, [rsp+130h+var_E8]
0x1800386b7  add     ax, 2
0x1800386bb  mov     edx, 2000000h
0x1800386c0  mov     word ptr [rsp+130h+var_C8+2], ax
0x1800386c5  mov     rax, [rsp+130h+Handle]
0x1800386ca  mov     qword ptr [rbp+30h+var_58+8], rax
0x1800386ce  lea     rax, [rsp+130h+var_C8]
0x1800386d3  mov     qword ptr [rbp+30h+var_48], rax
0x1800386d7  movdqu  [rbp+30h+var_38], xmm0
0x1800386dc  call    NtOpenKey
0x1800386e1  mov     esi, eax
0x1800386e3  test    eax, eax
0x1800386e5  js      loc_18003859E
0x1800386eb  cmp     qword ptr [rdi], 0
0x1800386ef  jz      loc_1800385A2
0x1800386f5  mov     r10, [rsp+130h+var_E8]
0x1800386fa  jmp     loc_180038444
0x1800386ff  cmp     r10, rdx
0x180038702  jz      loc_180038428
0x180038708  mov     rcx, r10; Handle
0x18003870b  call    NtClose
0x180038710  mov     rdx, [rsp+130h+Handle]
0x180038715  mov     r10, rdx
0x180038718  mov     [rsp+130h+var_E8], rdx
0x18003871d  jmp     loc_180038428
0x180038722  mov     rcx, [rdi+18h]
0x180038726  xor     r9d, r9d
0x180038729  mov     rax, [rdi]
0x18003872c  xor     r8d, r8d
0x18003872f  mov     [rsp+130h+var_108], rcx
0x180038734  xor     edx, edx
0x180038736  xor     ecx, ecx
0x180038738  mov     [rsp+130h+var_110], r15
0x18003873d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038742  mov     esi, eax
0x180038744  jmp     loc_18003859E
0x180038749  test    byte ptr [rdi+8], 21h
0x18003874d  jnz     loc_180038415
0x180038753  jmp     loc_1800385D4
0x180038758  cmp     qword ptr [rdi+10h], 0
0x18003875d  jz      short loc_18003876C
0x18003875f  test    al, 1
0x180038761  jnz     short loc_18003876C
0x180038763  test    rcx, rcx
0x180038766  jz      loc_180038420
0x18003876c  mov     esi, 0C000000Dh
0x180038771  jmp     loc_1800385D4
0x180038776  mov     eax, [rsp+130h+var_F0]
0x18003877a  lea     r8, [rbp+30h+var_68]
0x18003877e  add     rax, 0Ah
0x180038782  mov     [rbp+30h+var_60], r14
0x180038786  xor     r12d, r12d
0x180038789  mov     [rsp+130h+var_E0], rax
0x18003878e  mov     r9d, 8000h
0x180038794  mov     [rbp+30h+var_68], rax
0x180038798  lea     rdx, [rbp+30h+var_60]
0x18003879c  mov     [rbp+30h+var_98], r12
0x1800387a0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800387a7  call    ZwFreeVirtualMemory
0x1800387ac  lea     r9, [rsp+130h+var_E0]
0x1800387b1  mov     dword ptr [rsp+130h+var_108], 4
0x1800387b9  xor     r8d, r8d
0x1800387bc  mov     dword ptr [rsp+130h+var_110], 1000h
0x1800387c4  lea     rdx, [rbp+30h+var_98]
0x1800387c8  mov     rcx, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
