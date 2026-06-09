# VsmOpenAlgorithmProvider

- ea: `0x18005aca8`
- end: `0x18005b069`
- name: `VsmOpenAlgorithmProvider`
- size: `961`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800449b0`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x18005a8fc`
- `0x18005aca8`
- `0x18006948c`
- `0x18009d860`
- `0x18009d920`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!wcsncpy_s` at `0x18005ade2`
- `ntoskrnl!wcsncpy_s` at `0x18005ade2`

## string_xrefs

- `0x18005afcd`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005b038`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall VsmOpenAlgorithmProvider(_QWORD *a1, const wchar_t *a2, const void *a3, unsigned int a4)
{
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rcx
  unsigned int i; // ecx
  __int64 v10; // r15
  wchar_t *v11; // rax
  signed __int64 v12; // r9
  int v13; // r8d
  __int64 v14; // rdx
  int v15; // esi
  char *v16; // rax
  char *v17; // rdi
  _OWORD *v18; // r14
  int Interface; // eax
  __int64 v20; // r9
  __int64 v21; // rax
  _OWORD *v22; // rcx
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  _QWORD *v30; // r14
  __int64 v31; // rcx
  wchar_t *v32; // rdx
  __int64 (__fastcall *v34)(char *, const wchar_t *, _QWORD); // [rsp+40h] [rbp-C0h] BYREF
  int v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall *v36)(_QWORD, const wchar_t *, char *, __int64, int *, _DWORD); // [rsp+50h] [rbp-B0h] BYREF
  void (__fastcall *v37)(_QWORD, wchar_t *, __int64 *, _QWORD, _DWORD); // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v39[448]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v41; // [rsp+250h] [rbp+150h] BYREF

  v41 = 4;
  v34 = 0;
  v38 = 0;
  v37 = 0;
  v36 = 0;
  v35 = 0;
  if ( !a3 || !memcmp(a3, L"Microsoft Primitive Provider", 0x3Au) )
  {
    for ( i = 0; i < 0x35; ++i )
    {
      v10 = 4LL * i;
      v11 = (&AlgorithmClassPropertyTable)[v10];
      v12 = (char *)a2 - (char *)v11;
      do
      {
        v13 = *(wchar_t *)((char *)v11 + v12);
        v14 = (unsigned int)*v11 - v13;
        if ( (_DWORD)v14 )
          break;
        ++v11;
      }
      while ( v13 );
      if ( !(_DWORD)v14 )
      {
        v15 = *((_DWORD *)&AlgorithmClassPropertyTable + 2 * v10 + 2);
        if ( (unsigned int)(v15 - 1) > 7 )
        {
          v7 = 1677;
          goto LABEL_41;
        }
        v16 = (char *)MSCryptAlloc(968, v14);
        v17 = v16;
        if ( !v16 )
        {
          v6 = -1073741801;
          v7 = 1691;
          v8 = 3221225495LL;
          goto LABEL_42;
        }
        memset(v16, 0, 0x3C8u);
        *(_DWORD *)v17 = 968;
        *((_DWORD *)v17 + 1) = 1431655761;
        *((_DWORD *)v17 + 4) = 1;
        *((_DWORD *)v17 + 9) = v15;
        wcsncpy_s((wchar_t *)v17 + 222, 0x104u, a2, 0xFFFFFFFFFFFFFFFFuLL);
        v18 = v17 + 48;
        *((_DWORD *)v17 + 8) = a4 & 1;
        Interface = VsmLoadInterface(*((unsigned int *)v17 + 9), a2, a4, v17 + 48);
        v6 = Interface;
        if ( Interface < 0 )
        {
          v20 = 1722;
          goto LABEL_35;
        }
        v21 = 3;
        v22 = v39;
        do
        {
          v23 = v18[1];
          *v22 = *v18;
          v24 = v18[2];
          v22[1] = v23;
          v25 = v18[3];
          v22[2] = v24;
          v26 = v18[4];
          v22[3] = v25;
          v27 = v18[5];
          v22[4] = v26;
          v28 = v18[6];
          v22[5] = v27;
          v29 = v18[7];
          v18 += 8;
          v22[6] = v28;
          v22[7] = v29;
          v22 += 8;
          --v21;
        }
        while ( v21 );
        *(_QWORD *)v22 = *(_QWORD *)v18;
        Interface = ValidateFunctionTable(
                      v15,
                      (unsigned int)v39,
                      (unsigned int)&v34,
                      (unsigned int)&v38,
                      (__int64)&v37,
                      (__int64)&v36);
        v6 = Interface;
        if ( Interface < 0 )
        {
          v20 = 1731;
          goto LABEL_35;
        }
        v30 = v17 + 24;
        v6 = v34(v17 + 24, a2, a4);
        if ( v6 == -1073700863 )
        {
          if ( v15 == 2 )
          {
            if ( (a4 & 0x28) == 8 )
            {
              v34(v17 + 24, a2, a4 & 0xFFFFFFF7);
              *((_DWORD *)v17 + 2) |= 8u;
            }
LABEL_26:
            if ( !v36 )
            {
              v6 = -1073741595;
              v31 = 3221225701LL;
              v20 = 1769;
LABEL_36:
              DebugTraceError(v31, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v20);
              MSCryptFree(v17);
              return v6;
            }
            Interface = v36(*v30, L"HashBlockLength", v17 + 12, 4, &v35, 0);
            v6 = Interface;
            if ( Interface < 0 )
            {
              v20 = 1781;
LABEL_35:
              v31 = (unsigned int)Interface;
              goto LABEL_36;
            }
LABEL_37:
            v32 = (&AlgorithmClassPropertyTable)[v10 + 1];
            if ( v32 )
              v37(*v30, v32, &qword_1800A79C8[v10], *((unsigned int *)&AlgorithmClassPropertyTable + 2 * v10 + 7), 0);
            *a1 = v17;
            return v6;
          }
        }
        else if ( v15 == 2 )
        {
          goto LABEL_26;
        }
        if ( v15 == 3 )
        {
          if ( !v36 )
          {
            v6 = -1073741595;
            v31 = 3221225701LL;
            v20 = 1790;
            goto LABEL_36;
          }
          Interface = v36(*v30, L"PaddingSchemes", v17 + 440, v41, (int *)&v41, 0);
          v6 = Interface;
          if ( Interface < 0 )
          {
            v20 = 1802;
            goto LABEL_35;
          }
        }
        goto LABEL_37;
      }
    }
    v7 = 1668;
LABEL_41:
    v8 = 3221225480LL;
    v6 = -1073741816;
  }
  else
  {
    v6 = -1073741811;
    v7 = 1660;
    v8 = 3221225485LL;
  }
LABEL_42:
  DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v7);
  return v6;
}

```

## disassembly

```asm
0x18005aca8  mov     [rsp-8+arg_8], rbx
0x18005acad  mov     [rsp-8+arg_0], rcx
0x18005acb2  push    rbp
0x18005acb3  push    rsi
0x18005acb4  push    rdi
0x18005acb5  push    r12
0x18005acb7  push    r13
0x18005acb9  push    r14
0x18005acbb  push    r15
0x18005acbd  lea     rbp, [rsp-100h]
0x18005acc5  sub     rsp, 200h
0x18005accc  xor     ebx, ebx
0x18005acce  mov     [rbp+130h+arg_10], 4
0x18005acd8  mov     [rsp+230h+var_1F0], rbx
0x18005acdd  mov     r12d, r9d
0x18005ace0  mov     [rsp+230h+var_1D0], rbx
0x18005ace5  mov     rax, r8
0x18005ace8  mov     [rsp+230h+var_1D8], rbx
0x18005aced  mov     r13, rdx
0x18005acf0  mov     [rsp+230h+var_1E0], rbx
0x18005acf5  mov     [rsp+230h+var_1E8], ebx
0x18005acf9  test    r8, r8
0x18005acfc  jz      short loc_18005AD2A
0x18005acfe  lea     r8d, [rbx+3Ah]; Size
0x18005ad02  mov     rcx, rax; Buf1
0x18005ad05  lea     rdx, pszProvider; "Microsoft Primitive Provider"
0x18005ad0c  call    memcmp
0x18005ad11  test    eax, eax
0x18005ad13  jz      short loc_18005AD2A
0x18005ad15  mov     ebx, 0C000000Dh
0x18005ad1a  mov     r9d, 67Ch
0x18005ad20  mov     ecx, 0C000000Dh
0x18005ad25  jmp     loc_18005B038
0x18005ad2a  mov     ecx, ebx
0x18005ad2c  lea     r10, AlgorithmClassPropertyTable
0x18005ad33  cmp     ecx, 35h ; '5'
0x18005ad36  jnb     loc_18005B028
0x18005ad3c  mov     r15d, ecx
0x18005ad3f  mov     r9, r13
0x18005ad42  shl     r15, 5
0x18005ad46  mov     rax, [r15+r10]
0x18005ad4a  sub     r9, rax
0x18005ad4d  movzx   edx, word ptr [rax]
0x18005ad50  movzx   r8d, word ptr [rax+r9]
0x18005ad55  sub     edx, r8d
0x18005ad58  jnz     short loc_18005AD63
0x18005ad5a  add     rax, 2
0x18005ad5e  test    r8d, r8d
0x18005ad61  jnz     short loc_18005AD4D
0x18005ad63  test    edx, edx
0x18005ad65  jz      short loc_18005AD6B
0x18005ad67  inc     ecx
0x18005ad69  jmp     short loc_18005AD33
0x18005ad6b  mov     esi, [r15+r10+8]
0x18005ad70  lea     eax, [rsi-1]
0x18005ad73  cmp     eax, 7
0x18005ad76  jbe     short loc_18005AD83
0x18005ad78  mov     r9d, 68Dh
0x18005ad7e  jmp     loc_18005B02E
0x18005ad83  mov     r14d, 3C8h
0x18005ad89  mov     ecx, r14d
0x18005ad8c  call    MSCryptAlloc
0x18005ad91  mov     rdi, rax
0x18005ad94  test    rax, rax
0x18005ad97  jnz     short loc_18005ADAE
0x18005ad99  mov     ebx, 0C0000017h
0x18005ad9e  mov     r9d, 69Bh
0x18005ada4  mov     ecx, 0C0000017h
0x18005ada9  jmp     loc_18005B038
0x18005adae  mov     r8, r14; Size
0x18005adb1  xor     edx, edx; Val
0x18005adb3  mov     rcx, rdi; void *
0x18005adb6  call    memset
0x18005adbb  lea     rcx, [rdi+1BCh]; Dst
0x18005adc2  mov     [rdi], r14d
0x18005adc5  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18005adc9  mov     dword ptr [rdi+4], 55555551h
0x18005add0  mov     r8, r13; Src
0x18005add3  mov     dword ptr [rdi+10h], 1
0x18005adda  mov     edx, 104h; SizeInWords
0x18005addf  mov     [rdi+24h], esi
0x18005ade2  call    cs:__imp_wcsncpy_s
0x18005ade9  nop     dword ptr [rax+rax+00h]
0x18005adee  mov     eax, r12d
0x18005adf1  lea     r14, [rdi+30h]
0x18005adf5  and     eax, 1
0x18005adf8  mov     r9, r14
0x18005adfb  mov     [rdi+20h], eax
0x18005adfe  mov     r8d, r12d
0x18005ae01  mov     ecx, [rdi+24h]
0x18005ae04  mov     rdx, r13
0x18005ae07  call    VsmLoadInterface
0x18005ae0c  mov     ebx, eax
0x18005ae0e  test    eax, eax
0x18005ae10  jns     short loc_18005AE1D
0x18005ae12  mov     r9d, 6BAh
0x18005ae18  jmp     loc_18005AFCB
0x18005ae1d  mov     eax, 3
0x18005ae22  lea     rcx, [rsp+230h+var_1C0]
0x18005ae27  lea     edx, [rax+7Dh]
0x18005ae2a  movups  xmm0, xmmword ptr [r14]
0x18005ae2e  movups  xmm1, xmmword ptr [r14+10h]
0x18005ae33  movups  xmmword ptr [rcx], xmm0
0x18005ae36  movups  xmm0, xmmword ptr [r14+20h]
0x18005ae3b  movups  xmmword ptr [rcx+10h], xmm1
0x18005ae3f  movups  xmm1, xmmword ptr [r14+30h]
0x18005ae44  movups  xmmword ptr [rcx+20h], xmm0
0x18005ae48  movups  xmm0, xmmword ptr [r14+40h]
0x18005ae4d  movups  xmmword ptr [rcx+30h], xmm1
0x18005ae51  movups  xmm1, xmmword ptr [r14+50h]
0x18005ae56  movups  xmmword ptr [rcx+40h], xmm0
0x18005ae5a  movups  xmm0, xmmword ptr [r14+60h]
0x18005ae5f  movups  xmmword ptr [rcx+50h], xmm1
0x18005ae63  movups  xmm1, xmmword ptr [r14+70h]
0x18005ae68  add     r14, rdx
0x18005ae6b  movups  xmmword ptr [rcx+60h], xmm0
0x18005ae6f  movups  xmmword ptr [rcx+70h], xmm1
0x18005ae73  add     rcx, rdx
0x18005ae76  sub     rax, 1
0x18005ae7a  jnz     short loc_18005AE2A
0x18005ae7c  mov     rax, [r14]
0x18005ae7f  lea     r9, [rsp+230h+var_1D0]
0x18005ae84  mov     [rcx], rax
0x18005ae87  lea     r8, [rsp+230h+var_1F0]
0x18005ae8c  lea     rax, [rsp+230h+var_1E0]
0x18005ae91  mov     ecx, esi
0x18005ae93  mov     [rsp+230h+var_208], rax
0x18005ae98  lea     rdx, [rsp+230h+var_1C0]
0x18005ae9d  lea     rax, [rsp+230h+var_1D8]
0x18005aea2  mov     [rsp+230h+var_210], rax
0x18005aea7  call    ValidateFunctionTable
0x18005aeac  mov     ebx, eax
0x18005aeae  test    eax, eax
0x18005aeb0  jns     short loc_18005AEBD
0x18005aeb2  mov     r9d, 6C3h
0x18005aeb8  jmp     loc_18005AFCB
0x18005aebd  mov     rax, [rsp+230h+var_1F0]
0x18005aec2  lea     r14, [rdi+18h]
0x18005aec6  mov     rcx, r14
0x18005aec9  mov     r8d, r12d
0x18005aecc  mov     rdx, r13
0x18005aecf  call    _guard_dispatch_icall
0x18005aed4  mov     ebx, eax
0x18005aed6  cmp     eax, 0C000A001h
0x18005aedb  jnz     short loc_18005AF0C
0x18005aedd  cmp     esi, 2
0x18005aee0  jnz     loc_18005AF6D
0x18005aee6  mov     eax, r12d
0x18005aee9  and     al, 28h
0x18005aeeb  cmp     al, 8
0x18005aeed  jnz     short loc_18005AF11
0x18005aeef  mov     rax, [rsp+230h+var_1F0]
0x18005aef4  and     r12d, 0FFFFFFF7h
0x18005aef8  mov     r8d, r12d
0x18005aefb  mov     rdx, r13
0x18005aefe  mov     rcx, r14
0x18005af01  call    _guard_dispatch_icall
0x18005af06  or      dword ptr [rdi+8], 8
0x18005af0a  jmp     short loc_18005AF11
0x18005af0c  cmp     esi, 2
0x18005af0f  jnz     short loc_18005AF6D
0x18005af11  mov     rax, [rsp+230h+var_1E0]
0x18005af16  test    rax, rax
0x18005af19  jnz     short loc_18005AF30
0x18005af1b  mov     ebx, 0C00000E5h
0x18005af20  mov     ecx, 0C00000E5h
0x18005af25  mov     r9d, 6E9h
0x18005af2b  jmp     loc_18005AFCD
0x18005af30  lea     rcx, [rsp+230h+var_1E8]
0x18005af35  mov     dword ptr [rsp+230h+var_208], 0
0x18005af3d  mov     [rsp+230h+var_210], rcx
0x18005af42  lea     r8, [rdi+0Ch]
0x18005af46  mov     rcx, [r14]
0x18005af49  lea     rdx, aHashblocklengt; "HashBlockLength"
0x18005af50  mov     r9d, 4
0x18005af56  call    _guard_dispatch_icall
0x18005af5b  mov     ebx, eax
0x18005af5d  test    eax, eax
0x18005af5f  jns     loc_18005AFEA
0x18005af65  mov     r9d, 6F5h
0x18005af6b  jmp     short loc_18005AFCB
0x18005af6d  cmp     esi, 3
0x18005af70  jnz     short loc_18005AFEA
0x18005af72  mov     rax, [rsp+230h+var_1E0]
0x18005af77  test    rax, rax
0x18005af7a  jnz     short loc_18005AF8E
0x18005af7c  mov     ebx, 0C00000E5h
0x18005af81  mov     ecx, 0C00000E5h
0x18005af86  mov     r9d, 6FEh
0x18005af8c  jmp     short loc_18005AFCD
0x18005af8e  mov     r9d, [rbp+130h+arg_10]
0x18005af95  lea     rcx, [rbp+130h+arg_10]
0x18005af9c  mov     dword ptr [rsp+230h+var_208], 0
0x18005afa4  lea     r8, [rdi+1B8h]
0x18005afab  mov     [rsp+230h+var_210], rcx
0x18005afb0  lea     rdx, aPaddingschemes; "PaddingSchemes"
0x18005afb7  mov     rcx, [r14]
0x18005afba  call    _guard_dispatch_icall
0x18005afbf  mov     ebx, eax
0x18005afc1  test    eax, eax
0x18005afc3  jns     short loc_18005AFEA
0x18005afc5  mov     r9d, 70Ah
0x18005afcb  mov     ecx, eax
0x18005afcd  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005afd4  lea     rdx, aStatus; "Status"
0x18005afdb  call    DebugTraceError
0x18005afe0  mov     rcx, rdi; P
0x18005afe3  call    MSCryptFree
0x18005afe8  jmp     short loc_18005B04B
0x18005afea  lea     r9, AlgorithmClassPropertyTable
0x18005aff1  mov     rdx, [r15+r9+10h]
0x18005aff6  test    rdx, rdx
0x18005aff9  jz      short loc_18005B01C
0x18005affb  mov     rcx, [r14]
0x18005affe  lea     r8, [r9+18h]
0x18005b002  mov     r9d, [r15+r9+1Ch]
0x18005b007  add     r8, r15
0x18005b00a  mov     rax, [rsp+230h+var_1D8]
0x18005b00f  mov     dword ptr [rsp+230h+var_210], 0
0x18005b017  call    _guard_dispatch_icall
0x18005b01c  mov     rax, [rbp+130h+arg_0]
0x18005b023  mov     [rax], rdi
0x18005b026  jmp     short loc_18005B04B
0x18005b028  mov     r9d, 684h
0x18005b02e  mov     ecx, 0C0000008h
0x18005b033  mov     ebx, 0C0000008h
0x18005b038  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005b03f  lea     rdx, aStatus; "Status"
0x18005b046  call    DebugTraceError
0x18005b04b  mov     eax, ebx
0x18005b04d  mov     rbx, [rsp+230h+arg_8]
0x18005b055  add     rsp, 200h
0x18005b05c  pop     r15
0x18005b05e  pop     r14
0x18005b060  pop     r13
0x18005b062  pop     r12
0x18005b064  pop     rdi
0x18005b065  pop     rsi
0x18005b066  pop     rbp
0x18005b067  retn
```
