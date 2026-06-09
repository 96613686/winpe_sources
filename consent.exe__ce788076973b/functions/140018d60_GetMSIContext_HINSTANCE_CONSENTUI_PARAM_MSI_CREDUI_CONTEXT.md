# GetMSIContext(HINSTANCE__ *,_CONSENTUI_PARAM_MSI *,_CREDUI_CONTEXT *)

- ea: `0x140018d60`
- end: `0x140019030`
- name: `?GetMSIContext@@YAXPEAUHINSTANCE__@@PEAU_CONSENTUI_PARAM_MSI@@PEAU_CREDUI_CONTEXT@@@Z`
- size: `720`
- prototype: `void __fastcall(HINSTANCE, struct _CONSENTUI_PARAM_MSI *, struct _CREDUI_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140003040`

## callees

- `0x14000e558`
- `0x14000eaa0`
- `0x14000f200`
- `0x140018d60`
- `0x14001cb38`

## import_xrefs

- `msvcrt!_wtoi` at `0x140018dfb`
- `msvcrt!_wtoi` at `0x140018dfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018e56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018fd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018ff9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140019002`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018e56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018fd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018ff9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140019002`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140018e2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140018f19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140018e2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140018f19`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x140018e1c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x140018e49`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x140018e1c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x140018e49`
- `SHLWAPI!SHStrDupW` at `0x140018ff0`
- `SHLWAPI!SHStrDupW` at `0x140018ff0`

## pseudocode

```c
void __fastcall GetMSIContext(HINSTANCE a1, struct _CONSENTUI_PARAM_MSI *a2, struct _CREDUI_CONTEXT *a3)
{
  int v3; // r9d
  int v6; // edx
  WCHAR *v7; // rdi
  unsigned int v8; // eax
  LCID v9; // r14d
  int LocaleInfoW; // eax
  int v11; // ebp
  WCHAR *v12; // rax
  void *v13; // r15
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  unsigned __int64 v19; // r14
  unsigned int v20; // edx
  unsigned int i; // ecx
  __int64 v22; // rax
  unsigned __int16 *v23; // rax
  int v24; // eax
  unsigned int v25; // ebp
  int v26; // [rsp+20h] [rbp-48h]
  LPVOID pv; // [rsp+78h] [rbp+10h] BYREF

  v3 = *((_DWORD *)a2 + 50);
  pv = 0;
  if ( v3 )
  {
    if ( --v3 )
    {
      if ( --v3 && (--v3, v3) && (--v3, v3) )
      {
        if ( v3 == 1 )
          v6 = 3003;
        else
          v6 = 3004;
      }
      else
      {
        v6 = 3002;
      }
    }
    else
    {
      v6 = 3001;
    }
  }
  else
  {
    v6 = 3000;
  }
  TResourceStringAllocCopyEx<unsigned short *>((int)a1, v6, (int)a3, v3, v26, &pv);
  v7 = 0;
  *((_WORD *)a3 + 29) = *((_WORD *)a2 + 100);
  v8 = _wtoi(*((const wchar_t **)a2 + 28));
  if ( v8 <= 0xFFFF )
  {
    v9 = (unsigned __int16)v8;
    LocaleInfoW = GetLocaleInfoW((unsigned __int16)v8, 2u, 0, 0);
    v11 = LocaleInfoW;
    if ( LocaleInfoW )
    {
      v12 = (WCHAR *)CoTaskMemAlloc(2LL * LocaleInfoW);
      v7 = v12;
      if ( v12 )
      {
        if ( !GetLocaleInfoW(v9, 2u, v12, v11) )
        {
          CoTaskMemFree(v7);
          v7 = 0;
        }
      }
    }
  }
  v13 = pv;
  if ( pv )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)pv + v14) );
  }
  else
  {
    v14 = 0;
  }
  if ( v7 )
  {
    v15 = -1;
    do
      ++v15;
    while ( v7[v15] );
  }
  else
  {
    v15 = 0;
  }
  v16 = -1;
  do
    ++v16;
  while ( *(_WORD *)(*((_QWORD *)a2 + 27) + 2 * v16) );
  v17 = -1;
  do
    ++v17;
  while ( *(_WORD *)(*((_QWORD *)a2 + 29) + 2 * v17) );
  v18 = -1;
  do
    ++v18;
  while ( *(_WORD *)(*((_QWORD *)a2 + 31) + 2 * v18) );
  v19 = v14 + v15 + v18 + v17 + v16 + 5;
  v20 = *((_DWORD *)a2 + 64);
  if ( v20 )
  {
    for ( i = 0; i < v20; ++i )
    {
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)a2 + 34) + 8LL * i) + 2 * v22) );
      v19 += v22 + 1;
    }
  }
  v23 = (unsigned __int16 *)CoTaskMemAlloc(2 * v19);
  *((_QWORD *)a3 + 4) = v23;
  if ( v23 )
  {
    v24 = StringCchPrintfW(v23, v19, L"%s\n%s\n%s\n%s\n%s");
    v25 = 0;
    if ( *((_DWORD *)a2 + 64) )
    {
      while ( StringCchCatW(*((unsigned __int16 **)a3 + 4), v19, L"\n") >= 0
           && StringCchCatW(
                *((unsigned __int16 **)a3 + 4),
                v19,
                *(const unsigned __int16 **)(*((_QWORD *)a2 + 34) + 8LL * v25)) >= 0 )
      {
        if ( ++v25 >= *((_DWORD *)a2 + 64) )
          goto LABEL_46;
      }
    }
    else if ( v24 >= 0 )
    {
      goto LABEL_46;
    }
    CoTaskMemFree(*((LPVOID *)a3 + 4));
    *((_QWORD *)a3 + 4) = 0;
  }
LABEL_46:
  if ( !*((_QWORD *)a3 + 2) )
    SHStrDupW(*((LPCWSTR *)a2 + 31), (LPWSTR *)a3 + 2);
  CoTaskMemFree(v7);
  CoTaskMemFree(v13);
  *((_DWORD *)a3 + 15) = CuiGetBinaryLocation(*((_QWORD *)a2 + 31));
}

```

## disassembly

```asm
0x140018d60  mov     r11, rsp
0x140018d63  mov     [r11+8], rbx
0x140018d67  mov     [r11+18h], rbp
0x140018d6b  push    rsi
0x140018d6c  push    rdi
0x140018d6d  push    r12
0x140018d6f  push    r14
0x140018d71  push    r15
0x140018d73  sub     rsp, 40h
0x140018d77  mov     r9d, [rdx+0C8h]; int
0x140018d7e  xor     r12d, r12d
0x140018d81  mov     [r11+10h], r12
0x140018d85  mov     rsi, r8
0x140018d88  mov     rbx, rdx
0x140018d8b  test    r9d, r9d
0x140018d8e  jz      short loc_140018DD2
0x140018d90  sub     r9d, 1
0x140018d94  jz      short loc_140018DCB
0x140018d96  sub     r9d, 1
0x140018d9a  jz      short loc_140018DC4
0x140018d9c  sub     r9d, 1
0x140018da0  jz      short loc_140018DC4
0x140018da2  sub     r9d, 1
0x140018da6  jz      short loc_140018DC4
0x140018da8  lea     rax, [r11+10h]
0x140018dac  mov     [r11-40h], rax
0x140018db0  cmp     r9d, 1
0x140018db4  jz      short loc_140018DBD
0x140018db6  mov     edx, 0BBCh
0x140018dbb  jmp     short loc_140018DE1
0x140018dbd  mov     edx, 0BBBh
0x140018dc2  jmp     short loc_140018DE1
0x140018dc4  mov     edx, 0BBAh
0x140018dc9  jmp     short loc_140018DD7
0x140018dcb  mov     edx, 0BB9h
0x140018dd0  jmp     short loc_140018DD7
0x140018dd2  mov     edx, 0BB8h; int
0x140018dd7  lea     rax, [rsp+68h+pv]
0x140018ddc  mov     [rsp+68h+Src], rax; Src
0x140018de1  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x140018de6  movzx   eax, word ptr [rbx+0C8h]
0x140018ded  mov     rdi, r12
0x140018df0  mov     [rsi+3Ah], ax
0x140018df4  mov     rcx, [rbx+0E0h]; String
0x140018dfb  call    cs:__imp__wtoi
0x140018e01  cmp     eax, 0FFFFh
0x140018e06  ja      short loc_140018E5F
0x140018e08  xor     r9d, r9d; cchData
0x140018e0b  movzx   r14d, ax
0x140018e0f  xor     r8d, r8d; lpLCData
0x140018e12  mov     ecx, r14d; Locale
0x140018e15  lea     r15d, [r9+2]
0x140018e19  mov     edx, r15d; LCType
0x140018e1c  call    cs:__imp_GetLocaleInfoW
0x140018e22  movsxd  rbp, eax
0x140018e25  test    eax, eax
0x140018e27  jz      short loc_140018E5F
0x140018e29  mov     rcx, rbp
0x140018e2c  add     rcx, rcx; cb
0x140018e2f  call    cs:__imp_CoTaskMemAlloc
0x140018e35  mov     rdi, rax
0x140018e38  test    rax, rax
0x140018e3b  jz      short loc_140018E5F
0x140018e3d  mov     r9d, ebp; cchData
0x140018e40  mov     r8, rax; lpLCData
0x140018e43  mov     edx, r15d; LCType
0x140018e46  mov     ecx, r14d; Locale
0x140018e49  call    cs:__imp_GetLocaleInfoW
0x140018e4f  test    eax, eax
0x140018e51  jnz     short loc_140018E5F
0x140018e53  mov     rcx, rdi; pv
0x140018e56  call    cs:__imp_CoTaskMemFree
0x140018e5c  mov     rdi, r12
0x140018e5f  mov     r15, [rsp+68h+pv]
0x140018e64  or      r11, 0FFFFFFFFFFFFFFFFh
0x140018e68  test    r15, r15
0x140018e6b  jz      short loc_140018E7C
0x140018e6d  mov     rdx, r11
0x140018e70  inc     rdx
0x140018e73  cmp     [r15+rdx*2], r12w
0x140018e78  jnz     short loc_140018E70
0x140018e7a  jmp     short loc_140018E7F
0x140018e7c  mov     rdx, r12
0x140018e7f  test    rdi, rdi
0x140018e82  jz      short loc_140018E93
0x140018e84  mov     rcx, r11
0x140018e87  inc     rcx
0x140018e8a  cmp     [rdi+rcx*2], r12w
0x140018e8f  jnz     short loc_140018E87
0x140018e91  jmp     short loc_140018E96
0x140018e93  mov     rcx, r12
0x140018e96  mov     r8, [rbx+0D8h]
0x140018e9d  mov     rax, r11
0x140018ea0  inc     rax
0x140018ea3  cmp     [r8+rax*2], r12w
0x140018ea8  jnz     short loc_140018EA0
0x140018eaa  mov     r9, [rbx+0E8h]
0x140018eb1  mov     r8, r11
0x140018eb4  inc     r8
0x140018eb7  cmp     [r9+r8*2], r12w
0x140018ebc  jnz     short loc_140018EB4
0x140018ebe  mov     r10, [rbx+0F8h]
0x140018ec5  mov     r9, r11
0x140018ec8  inc     r9
0x140018ecb  cmp     [r10+r9*2], r12w
0x140018ed0  jnz     short loc_140018EC8
0x140018ed2  lea     r14, [rax+5]
0x140018ed6  add     r14, r8
0x140018ed9  add     r14, r9
0x140018edc  add     r14, rcx
0x140018edf  add     r14, rdx
0x140018ee2  mov     edx, [rbx+100h]
0x140018ee8  test    edx, edx
0x140018eea  jz      short loc_140018F15
0x140018eec  mov     r9, [rbx+110h]
0x140018ef3  mov     ecx, r12d
0x140018ef6  mov     eax, ecx
0x140018ef8  mov     r8, [r9+rax*8]
0x140018efc  mov     rax, r11
0x140018eff  inc     rax
0x140018f02  cmp     [r8+rax*2], r12w
0x140018f07  jnz     short loc_140018EFF
0x140018f09  inc     r14
0x140018f0c  inc     ecx
0x140018f0e  add     r14, rax
0x140018f11  cmp     ecx, edx
0x140018f13  jb      short loc_140018EF6
0x140018f15  lea     rcx, [r14+r14]; cb
0x140018f19  call    cs:__imp_CoTaskMemAlloc
0x140018f1f  mov     [rsi+20h], rax
0x140018f23  mov     r10, rax
0x140018f26  test    rax, rax
0x140018f29  jz      loc_140018FE0
0x140018f2f  mov     r8, [rbx+0F8h]
0x140018f36  lea     r9, qword_1400210F8
0x140018f3d  mov     rcx, [rbx+0D8h]
0x140018f44  mov     rdx, r9
0x140018f47  mov     rax, [rbx+0E8h]
0x140018f4e  test    rdi, rdi
0x140018f51  mov     [rsp+68h+var_30], r8
0x140018f56  lea     r8, aSSSSS; "%s\n%s\n%s\n%s\n%s"
0x140018f5d  cmovnz  rdx, rdi
0x140018f61  test    r15, r15
0x140018f64  mov     [rsp+68h+var_38], rdx
0x140018f69  mov     rdx, r14; unsigned __int64
0x140018f6c  mov     [rsp+68h+Src], rax
0x140018f71  cmovnz  r9, r15
0x140018f75  mov     [rsp+68h+var_48], rcx
0x140018f7a  mov     rcx, r10; unsigned __int16 *
0x140018f7d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140018f82  mov     ebp, r12d
0x140018f85  cmp     [rbx+100h], r12d
0x140018f8c  jbe     short loc_140018FCE
0x140018f8e  mov     rcx, [rsi+20h]; unsigned __int16 *
0x140018f92  lea     r8, asc_140021A90; "\n"
0x140018f99  mov     rdx, r14; unsigned __int64
0x140018f9c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140018fa1  test    eax, eax
0x140018fa3  js      short loc_140018FD2
0x140018fa5  mov     r8, [rbx+110h]
0x140018fac  mov     rdx, r14; unsigned __int64
0x140018faf  mov     rcx, [rsi+20h]; unsigned __int16 *
0x140018fb3  mov     eax, ebp
0x140018fb5  mov     r8, [r8+rax*8]; unsigned __int16 *
0x140018fb9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140018fbe  test    eax, eax
0x140018fc0  js      short loc_140018FD2
0x140018fc2  inc     ebp
0x140018fc4  cmp     ebp, [rbx+100h]
0x140018fca  jb      short loc_140018F8E
0x140018fcc  jmp     short loc_140018FE0
0x140018fce  test    eax, eax
0x140018fd0  jns     short loc_140018FE0
0x140018fd2  mov     rcx, [rsi+20h]; pv
0x140018fd6  call    cs:__imp_CoTaskMemFree
0x140018fdc  mov     [rsi+20h], r12
0x140018fe0  lea     rdx, [rsi+10h]; ppwsz
0x140018fe4  cmp     [rdx], r12
0x140018fe7  jnz     short loc_140018FF6
0x140018fe9  mov     rcx, [rbx+0F8h]; psz
0x140018ff0  call    cs:__imp_SHStrDupW
0x140018ff6  mov     rcx, rdi; pv
0x140018ff9  call    cs:__imp_CoTaskMemFree
0x140018fff  mov     rcx, r15; pv
0x140019002  call    cs:__imp_CoTaskMemFree
0x140019008  mov     rcx, [rbx+0F8h]
0x14001900f  call    ?CuiGetBinaryLocation@@YA?AW4_CONTEXT_FILE_LOCATION@@PEBG@Z; CuiGetBinaryLocation(ushort const *)
0x140019014  lea     r11, [rsp+68h+var_28]
0x140019019  mov     [rsi+3Ch], eax
0x14001901c  mov     rbx, [r11+30h]
0x140019020  mov     rbp, [r11+40h]
0x140019024  mov     rsp, r11
0x140019027  pop     r15
0x140019029  pop     r14
0x14001902b  pop     r12
0x14001902d  pop     rdi
0x14001902e  pop     rsi
0x14001902f  retn
```
