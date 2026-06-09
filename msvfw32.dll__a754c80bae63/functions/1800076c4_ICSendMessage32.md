# ICSendMessage32

- ea: `0x1800076c4`
- end: `0x1800080bc`
- name: `ICSendMessage32`
- size: `2552`
- prototype: `__int64 __fastcall(HIC hic, UINT msg)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800074a0`

## callees

- `0x1800014b0`
- `0x180001d62`
- `0x180002df0`
- `0x180003a60`
- `0x180006f44`
- `0x180007084`
- `0x1800070c4`
- `0x1800070f0`
- `0x180007260`
- `0x1800072a8`
- `0x1800072f4`
- `0x180007464`
- `0x1800076c4`
- `0x1800162fd`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007b38`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007b38`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007b4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007b4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007895`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800078a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007977`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007982`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007afd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007e2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007895`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800078a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007977`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007982`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007afd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007e2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f55`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800079d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008022`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800079d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008022`

## string_xrefs

- `0x180007b31`: `wow32.dll`

## pseudocode

```c
LONG_PTR __fastcall ICSendMessage32(HIC hic, UINT msg, HLOCAL *a3, SIZE_T a4)
{
  HLOCAL v4; // r13
  HIC v5; // r15
  DWORD_PTR v6; // rsi
  HLOCAL *v7; // r14
  UINT v8; // edi
  bool v9; // zf
  UINT v10; // eax
  HLOCAL v11; // r12
  void *v12; // rcx
  __int64 v13; // rbx
  HLOCAL v14; // r14
  unsigned int *v15; // rax
  int *v16; // rdi
  DWORD_PTR *v17; // rsi
  HLOCAL v18; // rcx
  HLOCAL v19; // rax
  DWORD_PTR v20; // r12
  signed __int64 v21; // rax
  HLOCAL v22; // rax
  void *v23; // r14
  unsigned int v24; // r13d
  __int64 v25; // r9
  LONG_PTR v27; // rax
  bool v28; // sf
  unsigned int BMI16Size; // eax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  int i; // r8d
  __int64 v34; // rcx
  int v35; // eax
  HLOCAL v36; // rax
  HLOCAL v37; // r14
  HLOCAL v38; // rcx
  unsigned int *v39; // rsi
  __int64 v40; // rax
  void *v41; // rax
  __int64 v42; // rbx
  LONG_PTR v43; // rax
  HLOCAL v44; // rax
  LONG_PTR v45; // rax
  __int64 v46; // r8
  DWORD_PTR dw1; // [rsp+20h] [rbp-E0h] BYREF
  int v48; // [rsp+28h] [rbp-D8h] BYREF
  HLOCAL hMem[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v50; // [rsp+50h] [rbp-B0h]
  DWORD_PTR *p_dw1; // [rsp+58h] [rbp-A8h]
  int *v52; // [rsp+60h] [rbp-A0h]
  HLOCAL v53; // [rsp+78h] [rbp-88h]
  __int64 v54; // [rsp+80h] [rbp-80h]
  __int64 v55; // [rsp+88h] [rbp-78h]
  __int128 v56; // [rsp+90h] [rbp-70h] BYREF
  __int128 v57; // [rsp+A0h] [rbp-60h]
  __int64 v58; // [rsp+B0h] [rbp-50h]
  ICINFO picinfo; // [rsp+C0h] [rbp-40h] BYREF

  v4 = 0;
  v5 = (HIC)(unsigned int)hic;
  v6 = a4;
  v7 = a3;
  v8 = msg;
  if ( msg > 0x5000 )
  {
    v13 = 0;
    if ( msg > 0x5014 )
    {
      if ( msg == 20501 )
        return v13;
      if ( msg != 20510 && msg != 20511 )
      {
        if ( msg != 20512 )
          return -1;
        goto LABEL_156;
      }
      goto LABEL_101;
    }
    if ( msg == 20500 )
      return v13;
    if ( msg != 20481 )
    {
      if ( msg == 20482 )
      {
        memset_0(&picinfo, 0, sizeof(picinfo));
        v43 = ICGetInfo(v5, &picinfo, 0x238u);
        v13 = v43;
        if ( !v43 )
          return v13;
        return (unsigned int)CopyICINFOTo16bit((unsigned int)v7, &picinfo, (unsigned int)v43);
      }
      if ( msg != 20490 && msg != 20491 )
      {
        if ( msg == 20492 )
          return v13;
        return -1;
      }
      v42 = -1;
      if ( a3 != (HLOCAL *)-1LL )
        v42 = ((__int64 (__fastcall *)(_QWORD, _QWORD))lpWOWHandle32)((unsigned __int16)a3, 0);
      a4 = v6;
      a3 = (HLOCAL *)v42;
      goto LABEL_156;
    }
    goto LABEL_159;
  }
  if ( msg == 20480 )
  {
LABEL_159:
    if ( a3 )
    {
      v44 = LocalAlloc(0x40u, a4);
      v20 = (DWORD_PTR)v44;
      if ( !v44 )
        return 0;
      if ( v8 == 20481 )
        CopyTo32Bit(v44);
      v45 = ICSendMessage(v5, v8, v20, v6);
      v13 = v45;
      if ( v45 > 0 && v8 == 20480 )
      {
        v46 = (unsigned int)v45;
        if ( (unsigned int)v45 >= (unsigned int)v6 )
          v46 = (unsigned int)v6;
        CopyTo16Bit(v7, v20, v46);
      }
LABEL_57:
      v18 = (HLOCAL)v20;
LABEL_144:
      LocalFree(v18);
      return v13;
    }
    a3 = 0;
    return ICSendMessage(v5, msg, (DWORD_PTR)a3, a4);
  }
  if ( msg > 0x401F )
  {
    if ( msg > 0x402A )
    {
      switch ( msg )
      {
        case 0x4032u:
          v50 = 0;
          memset(hMem, 0, sizeof(hMem));
          if ( a4 == 40 )
          {
            CopyTo32Bit(hMem);
            v38 = hMem[1];
            v39 = 0;
            if ( hMem[1] )
            {
              v40 = ((__int64 (__fastcall *)(HLOCAL, _QWORD, __int64))GetVDMPointer)(hMem[1], 0, 1);
              v38 = hMem[1];
              v39 = (unsigned int *)v40;
            }
            if ( hMem[0] )
            {
              v41 = (void *)CopyBitmapInfoHeader(LODWORD(hMem[0]));
              v38 = hMem[1];
              hMem[0] = v41;
            }
            if ( v38 )
              hMem[1] = (HLOCAL)CopyBitmapInfoHeader(v38);
            v13 = ICSendMessage(v5, 0x4032u, (DWORD_PTR)hMem, 0x28u);
            if ( hMem[0] )
              LocalFree(hMem[0]);
            v18 = hMem[1];
            if ( hMem[1] )
            {
              if ( !v13 )
              {
                memcpy_0(v39, hMem[1], *v39);
                v18 = hMem[1];
              }
              goto LABEL_144;
            }
            return v13;
          }
          break;
        case 0x4033u:
LABEL_129:
          v36 = CopyBitmapInfo((unsigned int)a3);
          v37 = v36;
          if ( v36 )
          {
            v13 = ICSendMessage(v5, v8, (DWORD_PTR)v36, v6);
            v18 = v37;
            goto LABEL_144;
          }
          return -3;
        case 0x403Cu:
        case 0x403Du:
        case 0x403Eu:
          v25 = 56;
          goto LABEL_59;
        case 0x403Fu:
          goto LABEL_156;
        case 0x4046u:
          memset_0(hMem, 0, 0x60u);
          if ( v6 == 96 )
          {
            CopyTo32Bit(hMem);
            v54 = 0;
            v55 = 0;
            if ( hMem[1] )
              hMem[1] = (HLOCAL)CopyBitmapInfoHeader(hMem[1]);
            if ( hMem[3] )
              hMem[3] = (HLOCAL)CopyBitmapInfoHeader(hMem[3]);
            v13 = ICSendMessage(v5, v8, (DWORD_PTR)hMem, 0x60u);
            if ( hMem[1] )
              LocalFree(hMem[1]);
            v18 = hMem[3];
            if ( hMem[3] )
              goto LABEL_144;
            return v13;
          }
          break;
        default:
          return -1;
      }
      return -6;
    }
    if ( msg == 16426 || msg == 16416 )
    {
LABEL_101:
      LODWORD(dw1) = 0;
      v13 = ICSendMessage((HIC)(unsigned int)hic, msg, (DWORD_PTR)&dw1, a4);
      if ( !v13 )
        CopyTo16Bit(v7, &dw1, 4);
      return v13;
    }
    if ( msg != 16417 )
    {
      switch ( msg )
      {
        case 0x4022u:
          dw1 = 0;
          *(_OWORD *)hMem = 0;
          CopyTo32Bit(&dw1);
          for ( i = 0; i < 4; ++i )
          {
            v34 = 2 * i;
            v35 = 4 * i;
            *(_DWORD *)((char *)hMem + v35) = *(__int16 *)((char *)&dw1 + v34);
          }
          a3 = hMem;
          msg = 16418;
          break;
        case 0x4023u:
          goto LABEL_156;
        case 0x4024u:
          a3 = (HLOCAL *)((__int64 (__fastcall *)(_QWORD, __int64))lpWOWHandle32)((unsigned __int16)a3, 4);
          msg = 16420;
          break;
        case 0x4025u:
        case 0x4026u:
          goto LABEL_156;
        case 0x4029u:
          goto LABEL_101;
        default:
          return -1;
      }
LABEL_108:
      a4 = v6;
      return ICSendMessage(v5, msg, (DWORD_PTR)a3, a4);
    }
    if ( a4 != 32 )
      return -7;
    memset(hMem, 0, 28);
    v58 = 0;
    v56 = 0;
    v57 = 0;
    CopyTo32Bit(hMem);
    CopyTo32Bit(&v56);
    hMem[1] = &v56;
    hMem[2] = (HLOCAL)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))GetVDMPointer)(
                        LODWORD(hMem[2]),
                        LODWORD(hMem[3]),
                        1);
    a3 = hMem;
    a4 = 32;
    msg = 16417;
    return ICSendMessage(v5, msg, (DWORD_PTR)a3, a4);
  }
  if ( msg == 16415 )
    goto LABEL_129;
  msg = 16397;
  if ( v8 > 0x400D )
  {
    if ( v8 != 16398 )
    {
      if ( v8 != 16399 )
      {
        if ( v8 == 16400 )
        {
          v13 = ICSendMessage((HIC)(unsigned int)hic, 0x4010u, (DWORD_PTR)a3, a4);
          if ( v13 != -1 && v13 != 0 )
          {
            ModuleHandleW = GetModuleHandleW(L"wow32.dll");
            if ( ModuleHandleW && (ProcAddress = GetProcAddress(ModuleHandleW, "WOWHandle16")) != 0 )
              return ((unsigned __int16 (__fastcall *)(__int64, __int64))ProcAddress)(v13, 10);
            else
              return -100;
          }
          return v13;
        }
        if ( v8 != 16402 && v8 != 16403 && v8 != 16405 )
        {
          v10 = v8 - 16413;
          v9 = v8 == 16413;
          goto LABEL_15;
        }
        goto LABEL_156;
      }
      HIDWORD(hMem[0]) = 0;
      memset_0(hMem, 0, 0x4Cu);
      v58 = 0;
      v56 = 0;
      v57 = 0;
      ConvertICDRAWBEGIN(hMem, &v56, (unsigned int)v7);
      a3 = hMem;
      msg = 16399;
      goto LABEL_108;
    }
LABEL_156:
    msg = v8;
    return ICSendMessage(v5, msg, (DWORD_PTR)a3, a4);
  }
  if ( v8 == 16397 )
  {
    v25 = 48;
LABEL_59:
    if ( v6 != v25 )
      return -7;
    return (unsigned int)DoICM_DecompressX((HIC)(unsigned int)hic, msg);
  }
  if ( v8 == 16388 )
    goto LABEL_47;
  if ( v8 != 16389 && v8 != 16390 && v8 != 16391 )
  {
    if ( v8 != 16392 )
    {
      if ( v8 != 16393 )
      {
        if ( v8 != 16394 )
        {
          v10 = v8 - 16395;
          v9 = v8 == 16395;
LABEL_15:
          if ( v9 || v10 == 1 )
            goto LABEL_17;
          return -1;
        }
LABEL_47:
        if ( !a3 )
          return 0;
        v19 = CopyBitmapInfo((unsigned int)a3);
        v20 = (DWORD_PTR)v19;
        if ( v19 )
        {
          v21 = ICSendMessage(v5, v8, (DWORD_PTR)v19, 0);
          v13 = v21;
          if ( v21 > 0 && v6 )
          {
            v22 = LocalAlloc(0, v21);
            v23 = v22;
            if ( v22 )
            {
              v24 = v13;
              v13 = ICSendMessage(v5, v8, v20, (DWORD_PTR)v22);
              if ( v13 >= 0 )
                CopyTo16Bit(v6, v23, v24);
              LocalFree(v23);
            }
            else
            {
              v13 = -3;
            }
          }
          goto LABEL_57;
        }
        return -3;
      }
      goto LABEL_156;
    }
    if ( a4 != 88 )
      return -7;
    v48 = 0;
    LODWORD(dw1) = 0;
    HIDWORD(hMem[0]) = 0;
    memset_0(hMem, 0, 0x54u);
    CopyTo32Bit(hMem);
    hMem[3] = CopyBitmapInfo(LODWORD(hMem[3]));
    if ( !hMem[3] )
      return -3;
    v14 = hMem[1];
    hMem[1] = CopyBitmapInfo(LODWORD(hMem[1]));
    if ( hMem[1] )
    {
      v50 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))GetVDMPointer)(
              (unsigned int)v50,
              *((unsigned int *)hMem[3] + 5),
              1);
      hMem[2] = (HLOCAL)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))GetVDMPointer)(
                          LODWORD(hMem[2]),
                          *((unsigned int *)hMem[1] + 5),
                          1);
      if ( v53 )
      {
        v15 = (unsigned int *)CopyBitmapInfo((unsigned int)v53);
        v53 = v15;
        if ( !v15 )
        {
          LocalFree(hMem[1]);
          goto LABEL_32;
        }
        v54 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))GetVDMPointer)((unsigned int)v54, v15[5], 1);
      }
      v16 = v52;
      v17 = 0;
      if ( v52 )
      {
        CopyTo32Bit(&v48);
        v52 = &v48;
      }
      if ( p_dw1 )
      {
        v17 = p_dw1;
        p_dw1 = &dw1;
      }
      v13 = ICSendMessage(v5, 0x4008u, (DWORD_PTR)hMem, 0x58u);
      if ( !v13 )
      {
        CopyTo16Bit(v14, hMem[1], 40);
        if ( v16 )
          CopyTo16Bit(v16, &v48, 4);
        if ( p_dw1 )
          CopyTo16Bit(v17, &dw1, 4);
      }
      if ( v53 )
        LocalFree(v53);
      LocalFree(hMem[1]);
      v18 = hMem[3];
      goto LABEL_144;
    }
LABEL_32:
    LocalFree(hMem[3]);
    return -3;
  }
LABEL_17:
  v11 = 0;
  if ( a3 )
    v4 = CopyBitmapInfo((unsigned int)a3);
  if ( v6 )
    v11 = CopyBitmapInfo((unsigned int)v6);
  if ( !v4 && v7 )
  {
    if ( v11 )
    {
      v12 = v11;
LABEL_73:
      LocalFree(v12);
      goto LABEL_74;
    }
    goto LABEL_74;
  }
  if ( !v11 && v6 )
  {
    if ( v4 )
    {
      v12 = v4;
      goto LABEL_73;
    }
LABEL_74:
    v13 = -(__int64)(v8 != 16389) & 0xFFFFFFFFFFFFFFFDuLL;
    goto LABEL_83;
  }
  v27 = ICSendMessage(v5, v8, (DWORD_PTR)v4, (DWORD_PTR)v11);
  v13 = v27;
  if ( v11 )
  {
    v28 = v27 < 0;
    if ( !v27 )
    {
      if ( v8 == 16395 )
      {
LABEL_81:
        BMI16Size = GetBMI16Size((__int64)v11);
        CopyTo16Bit(v6, v11, BMI16Size);
LABEL_82:
        LocalFree(v11);
        goto LABEL_83;
      }
      v28 = 0;
    }
    if ( v28 || v8 != 16414 )
      goto LABEL_82;
    goto LABEL_81;
  }
LABEL_83:
  if ( v4 )
  {
    v18 = v4;
    goto LABEL_144;
  }
  return v13;
}

```

## disassembly

```asm
0x1800076c4  push    rbp
0x1800076c6  push    rbx
0x1800076c7  push    rsi
0x1800076c8  push    rdi
0x1800076c9  push    r12
0x1800076cb  push    r13
0x1800076cd  push    r14
0x1800076cf  push    r15
0x1800076d1  lea     rbp, [rsp-218h]
0x1800076d9  sub     rsp, 318h
0x1800076e0  mov     rax, cs:__security_cookie
0x1800076e7  xor     rax, rsp
0x1800076ea  mov     [rbp+250h+var_50], rax
0x1800076f1  xor     r13d, r13d
0x1800076f4  mov     r15d, ecx
0x1800076f7  mov     eax, 5000h
0x1800076fc  mov     rsi, r9
0x1800076ff  mov     r14, r8
0x180007702  mov     edi, edx
0x180007704  cmp     edx, eax
0x180007706  ja      loc_180007F60
0x18000770c  jz      loc_18000800D
0x180007712  mov     eax, 401Fh
0x180007717  cmp     edx, eax
0x180007719  ja      loc_180007BC0
0x18000771f  jz      loc_180007E4E
0x180007725  lea     edx, [rax-12h]; msg
0x180007728  cmp     edi, edx
0x18000772a  ja      loc_180007A41
0x180007730  jz      loc_180007A23
0x180007736  mov     eax, edi
0x180007738  sub     eax, 4004h
0x18000773d  jz      loc_180007992
0x180007743  sub     eax, 1
0x180007746  jz      short loc_180007777
0x180007748  sub     eax, 1
0x18000774b  jz      short loc_180007777
0x18000774d  sub     eax, 1
0x180007750  jz      short loc_180007777
0x180007752  sub     eax, 1
0x180007755  jz      short loc_1800077BC
0x180007757  sub     eax, 1
0x18000775a  jz      loc_180007FC4
0x180007760  sub     eax, 1
0x180007763  jz      loc_180007992
0x180007769  sub     eax, 1
0x18000776c  jz      short loc_180007777
0x18000776e  cmp     eax, 1
0x180007771  jnz     loc_1800080B3
0x180007777  mov     r12, r13
0x18000777a  test    r14, r14
0x18000777d  jz      short loc_18000778A
0x18000777f  mov     ecx, r14d
0x180007782  call    CopyBitmapInfo
0x180007787  mov     r13, rax
0x18000778a  test    rsi, rsi
0x18000778d  jz      short loc_180007799
0x18000778f  mov     ecx, esi
0x180007791  call    CopyBitmapInfo
0x180007796  mov     r12, rax
0x180007799  test    r13, r13
0x18000779c  jnz     loc_180007A83
0x1800077a2  test    r14, r14
0x1800077a5  jz      loc_180007A83
0x1800077ab  test    r12, r12
0x1800077ae  jz      loc_180007A9B
0x1800077b4  mov     rcx, r12
0x1800077b7  jmp     loc_180007A95
0x1800077bc  mov     ebx, 58h ; 'X'
0x1800077c1  cmp     rsi, rbx
0x1800077c4  jz      short loc_1800077D2
0x1800077c6  mov     rbx, 0FFFFFFFFFFFFFFF9h
0x1800077cd  jmp     loc_180007C3E
0x1800077d2  xor     eax, eax
0x1800077d4  mov     [rsp+350h+var_328], r13d
0x1800077d9  xor     edx, edx; Val
0x1800077db  mov     dword ptr [rsp+350h+dw1], r13d
0x1800077e0  lea     rcx, [rsp+350h+hMem]; void *
0x1800077e5  mov     dword ptr [rsp+350h+hMem+4], eax
0x1800077e9  lea     r8d, [rax+54h]; Size
0x1800077ed  call    memset_0
0x1800077f2  mov     r8d, ebx
0x1800077f5  lea     rcx, [rsp+350h+hMem]; void *
0x1800077fa  mov     rdx, r14
0x1800077fd  call    CopyTo32Bit
0x180007802  mov     ecx, dword ptr [rsp+350h+var_310+8]
0x180007806  call    CopyBitmapInfo
0x18000780b  mov     [rsp+350h+var_310+8], rax
0x180007810  test    rax, rax
0x180007813  jz      loc_1800078A6
0x180007819  mov     r14, [rsp+350h+hMem+8]
0x18000781e  mov     ecx, r14d
0x180007821  call    CopyBitmapInfo
0x180007826  mov     [rsp+350h+hMem+8], rax
0x18000782b  test    rax, rax
0x18000782e  jz      short loc_18000789B
0x180007830  mov     rdx, [rsp+350h+var_310+8]
0x180007835  mov     r8d, 1
0x18000783b  mov     ecx, dword ptr [rsp+350h+var_300]
0x18000783f  mov     rax, cs:GetVDMPointer
0x180007846  mov     edx, [rdx+14h]
0x180007849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000784e  mov     rdx, [rsp+350h+hMem+8]
0x180007853  mov     r8d, 1
0x180007859  mov     ecx, dword ptr [rsp+350h+var_310]
0x18000785d  mov     [rsp+350h+var_300], rax
0x180007862  mov     rax, cs:GetVDMPointer
0x180007869  mov     edx, [rdx+14h]
0x18000786c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007871  mov     [rsp+350h+var_310], rax
0x180007876  cmp     [rsp+350h+var_2D8], r13
0x18000787b  jz      short loc_1800078CE
0x18000787d  mov     ecx, dword ptr [rsp+350h+var_2D8]
0x180007881  call    CopyBitmapInfo
0x180007886  mov     [rsp+350h+var_2D8], rax
0x18000788b  test    rax, rax
0x18000788e  jnz     short loc_1800078B2
0x180007890  mov     rcx, [rsp+350h+hMem+8]; hMem
0x180007895  call    cs:__imp_LocalFree
0x18000789b  mov     rcx, [rsp+350h+var_310+8]; hMem
0x1800078a0  call    cs:__imp_LocalFree
0x1800078a6  mov     rbx, 0FFFFFFFFFFFFFFFDh
0x1800078ad  jmp     loc_180007C3E
0x1800078b2  mov     edx, [rax+14h]
0x1800078b5  mov     r8d, 1
0x1800078bb  mov     rax, cs:GetVDMPointer
0x1800078c2  mov     ecx, dword ptr [rbp+250h+var_2D0]
0x1800078c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078ca  mov     [rbp+250h+var_2D0], rax
0x1800078ce  mov     rdi, [rsp+350h+var_2F0]
0x1800078d3  mov     rsi, r13
0x1800078d6  test    rdi, rdi
0x1800078d9  jz      short loc_1800078F8
0x1800078db  mov     r8d, 4
0x1800078e1  lea     rcx, [rsp+350h+var_328]; void *
0x1800078e6  mov     rdx, rdi
0x1800078e9  call    CopyTo32Bit
0x1800078ee  lea     rax, [rsp+350h+var_328]
0x1800078f3  mov     [rsp+350h+var_2F0], rax
0x1800078f8  mov     rax, [rsp+350h+var_2F8]
0x1800078fd  test    rax, rax
0x180007900  jz      short loc_18000790F
0x180007902  mov     rsi, rax
0x180007905  lea     rax, [rsp+350h+dw1]
0x18000790a  mov     [rsp+350h+var_2F8], rax
0x18000790f  mov     rcx, r15; hic
0x180007912  lea     r8, [rsp+350h+hMem]; dw1
0x180007917  mov     r9, rbx; dw2
0x18000791a  mov     edx, 4008h; msg
0x18000791f  call    ICSendMessage
0x180007924  mov     rbx, rax
0x180007927  test    rax, rax
0x18000792a  jnz     short loc_18000796D
0x18000792c  mov     rdx, [rsp+350h+hMem+8]
0x180007931  lea     r8d, [rax+28h]
0x180007935  mov     rcx, r14
0x180007938  call    CopyTo16Bit
0x18000793d  test    rdi, rdi
0x180007940  jz      short loc_180007953
0x180007942  lea     r8d, [rbx+4]
0x180007946  mov     rcx, rdi
0x180007949  lea     rdx, [rsp+350h+var_328]
0x18000794e  call    CopyTo16Bit
0x180007953  cmp     [rsp+350h+var_2F8], r13
0x180007958  jz      short loc_18000796D
0x18000795a  mov     r8d, 4
0x180007960  lea     rdx, [rsp+350h+dw1]
0x180007965  mov     rcx, rsi
0x180007968  call    CopyTo16Bit
0x18000796d  mov     rcx, [rsp+350h+var_2D8]; hMem
0x180007972  test    rcx, rcx
0x180007975  jz      short loc_18000797D
0x180007977  call    cs:__imp_LocalFree
0x18000797d  mov     rcx, [rsp+350h+hMem+8]; hMem
0x180007982  call    cs:__imp_LocalFree
0x180007988  mov     rcx, [rsp+350h+var_310+8]
0x18000798d  jmp     loc_180007F55
0x180007992  test    r14, r14
0x180007995  jnz     short loc_18000799F
0x180007997  mov     rbx, r13
0x18000799a  jmp     loc_180007C3E
0x18000799f  mov     ecx, r14d
0x1800079a2  call    CopyBitmapInfo
0x1800079a7  mov     r12, rax
0x1800079aa  test    rax, rax
0x1800079ad  jz      loc_1800078A6
0x1800079b3  xor     r9d, r9d; dw2
0x1800079b6  mov     r8, rax; dw1
0x1800079b9  mov     edx, edi; msg
0x1800079bb  mov     rcx, r15; hic
0x1800079be  call    ICSendMessage
0x1800079c3  mov     rbx, rax
0x1800079c6  test    rax, rax
0x1800079c9  jle     short loc_180007A1B
0x1800079cb  test    rsi, rsi
0x1800079ce  jz      short loc_180007A1B
0x1800079d0  mov     rdx, rax; uBytes
0x1800079d3  xor     ecx, ecx; uFlags
0x1800079d5  call    cs:__imp_LocalAlloc
0x1800079db  mov     r14, rax
0x1800079de  test    rax, rax
0x1800079e1  jnz     short loc_1800079E9
0x1800079e3  lea     rbx, [rax-3]
0x1800079e7  jmp     short loc_180007A1B
0x1800079e9  mov     r9, r14; dw2
0x1800079ec  mov     r8, r12; dw1
0x1800079ef  mov     edx, edi; msg
0x1800079f1  mov     rcx, r15; hic
0x1800079f4  mov     r13d, ebx
0x1800079f7  call    ICSendMessage
0x1800079fc  mov     rbx, rax
0x1800079ff  test    rax, rax
0x180007a02  js      short loc_180007A12
0x180007a04  mov     r8d, r13d
0x180007a07  mov     rdx, r14
0x180007a0a  mov     rcx, rsi
0x180007a0d  call    CopyTo16Bit
0x180007a12  mov     rcx, r14; hMem
0x180007a15  call    cs:__imp_LocalFree
0x180007a1b  mov     rcx, r12
0x180007a1e  jmp     loc_180007F55
0x180007a23  mov     r9d, 30h ; '0'
0x180007a29  cmp     rsi, r9
0x180007a2c  jnz     loc_1800077C6
0x180007a32  mov     ecx, r15d; hic
0x180007a35  call    DoICM_DecompressX
0x180007a3a  mov     ebx, eax
0x180007a3c  jmp     loc_180007C3E
0x180007a41  mov     eax, edi
0x180007a43  sub     eax, 400Eh
0x180007a48  jz      loc_180007FC4
0x180007a4e  sub     eax, 1
0x180007a51  jz      loc_180007B79
0x180007a57  sub     eax, 1
0x180007a5a  jz      loc_180007B14
0x180007a60  sub     eax, 2
0x180007a63  jz      loc_180007FC4
0x180007a69  sub     eax, 1
0x180007a6c  jz      loc_180007FC4
0x180007a72  sub     eax, 2
0x180007a75  jz      loc_180007FC4
0x180007a7b  sub     eax, 8
0x180007a7e  jmp     loc_18000776C
0x180007a83  test    r12, r12
0x180007a86  jnz     short loc_180007AB2
0x180007a88  test    rsi, rsi
0x180007a8b  jz      short loc_180007AB2
0x180007a8d  test    r13, r13
0x180007a90  jz      short loc_180007A9B
0x180007a92  mov     rcx, r13; hMem
0x180007a95  call    cs:__imp_LocalFree
0x180007a9b  sub     edi, 4005h
0x180007aa1  mov     rbx, 0FFFFFFFFFFFFFFFDh
0x180007aa8  neg     edi
0x180007aaa  sbb     rax, rax
0x180007aad  and     rbx, rax
0x180007ab0  jmp     short loc_180007B03
0x180007ab2  mov     rcx, r15; hic
0x180007ab5  mov     r9, r12; dw2
0x180007ab8  mov     r8, r13; dw1
0x180007abb  mov     edx, edi; msg
0x180007abd  call    ICSendMessage
0x180007ac2  mov     rbx, rax
0x180007ac5  test    r12, r12
0x180007ac8  jz      short loc_180007B03
0x180007aca  test    rax, rax
0x180007acd  jnz     short loc_180007ADA
0x180007acf  cmp     edi, 400Bh
0x180007ad5  jz      short loc_180007AE4
0x180007ad7  test    rax, rax
0x180007ada  js      short loc_180007AFA
0x180007adc  cmp     edi, 401Eh
0x180007ae2  jnz     short loc_180007AFA
0x180007ae4  mov     rcx, r12
0x180007ae7  call    GetBMI16Size
0x180007aec  mov     r8d, eax
0x180007aef  mov     rdx, r12
0x180007af2  mov     rcx, rsi
0x180007af5  call    CopyTo16Bit
0x180007afa  mov     rcx, r12; hMem
0x180007afd  call    cs:__imp_LocalFree
0x180007b03  test    r13, r13
0x180007b06  jz      loc_180007C3E
0x180007b0c  mov     rcx, r13
0x180007b0f  jmp     loc_180007F55
0x180007b14  mov     rcx, r15; hic
0x180007b17  mov     edx, 4010h; msg
0x180007b1c  call    ICSendMessage
0x180007b21  mov     rbx, rax
0x180007b24  inc     rax
0x180007b27  cmp     rax, 1
0x180007b2b  jbe     loc_180007C3E
0x180007b31  lea     rcx, aWow32Dll; "wow32.dll"
0x180007b38  call    cs:__imp_GetModuleHandleW
0x180007b3e  test    rax, rax
0x180007b41  jz      short loc_180007B6D
0x180007b43  lea     rdx, aWowhandle16; "WOWHandle16"
0x180007b4a  mov     rcx, rax; hModule
0x180007b4d  call    cs:__imp_GetProcAddress
0x180007b53  test    rax, rax
  ... truncated ...
```
