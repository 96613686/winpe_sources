# I_UpdateReaderStateArray

- ea: `0x180005830`
- end: `0x180005dfc`
- name: `I_UpdateReaderStateArray`
- size: `1484`
- prototype: `__int64 __fastcall(__int64, LPVOID *, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180003510`
- `0x180004900`

## callees

- `0x180004600`
- `0x180005830`
- `0x18000db90`
- `0x18000fe14`
- `0x180014a04`
- `0x180016a66`
- `0x180018b58`
- `0x18001f9a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800058b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005b6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bb7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800058b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005b6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bb7`
- `WinSCard!SCardGetDeviceTypeIdW` at `0x180005bfc`
- `WinSCard!SCardGetDeviceTypeIdW` at `0x180005bfc`
- `WinSCard!SCardListReadersW` at `0x18000587e`
- `WinSCard!SCardListReadersW` at `0x18000587e`
- `WinSCard!SCardFreeMemory` at `0x180005db7`
- `WinSCard!SCardFreeMemory` at `0x180005db7`

## string_xrefs

- `0x18000586b`: `SCard$AllReaders`

## pseudocode

```c
__int64 __fastcall I_UpdateReaderStateArray(__int64 a1, LPVOID *a2, unsigned int *a3)
{
  _OWORD *v3; // rsi
  unsigned int *v4; // r13
  unsigned int v7; // r12d
  wchar_t **m; // rdi
  wchar_t **v9; // r14
  LONG v10; // eax
  unsigned int DeviceTypeIdW; // ebx
  __int64 v12; // rcx
  DWORD i; // edx
  __int64 v14; // rax
  _OWORD *v15; // rax
  unsigned int v16; // r13d
  __int64 j; // rdx
  unsigned int k; // r8d
  unsigned __int64 v19; // r10
  unsigned __int16 *v20; // rax
  int v21; // ecx
  int v22; // r9d
  unsigned __int64 v23; // rcx
  __int64 v24; // r8
  char *v25; // rdx
  bool v26; // zf
  wchar_t *v27; // rax
  __int64 v28; // rcx
  _OWORD *v29; // rbx
  const wchar_t *v30; // r8
  __int64 v31; // rdx
  wchar_t **v32; // r9
  char *v33; // rdx
  signed __int64 v34; // r8
  int v35; // eax
  int v36; // ecx
  wchar_t *v37; // rax
  HANDLE v38; // rcx
  wchar_t **v39; // rax
  __int64 v40; // rcx
  __int64 v41; // r8
  wchar_t *v42; // rax
  __int64 v43; // rcx
  const wchar_t *v44; // r8
  __int64 v45; // rdx
  int v46; // eax
  __int64 v47; // rax
  STRSAFE_LPSTR v48; // rcx
  __int64 v49; // rdx
  DWORD v51; // [rsp+70h] [rbp+8h] BYREF
  int v52; // [rsp+78h] [rbp+10h] BYREF
  unsigned int *v53; // [rsp+80h] [rbp+18h]
  LPCVOID pvMem; // [rsp+88h] [rbp+20h] BYREF

  v53 = a3;
  v3 = 0;
  v51 = -1;
  v4 = a3;
  pvMem = 0;
  v52 = 0;
  v7 = 0;
  m = 0;
  v9 = 0;
  v10 = SCardListReadersW(*(_QWORD *)(a1 + 232), L"SCard$AllReaders", (LPWSTR)&pvMem, &v51);
  DeviceTypeIdW = v10;
  if ( v10 )
  {
    if ( v10 != -2146435026 )
      goto LABEL_78;
    DeviceTypeIdW = 0;
  }
  else
  {
    v51 = 0;
    if ( pvMem )
    {
      for ( i = 0; *((_WORD *)pvMem + i); v51 = i )
      {
        ++v7;
        v14 = -1;
        do
          ++v14;
        while ( *((_WORD *)pvMem + i + v14) );
        i += v14 + 1;
      }
    }
  }
  v3 = HeapAlloc(hHeap, 8u, (unsigned __int64)(v7 + 1) << 6);
  if ( !v3 )
  {
    WppTraceIndent(v12, 2);
    DeviceTypeIdW = 8;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        194,
        &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent);
    }
    goto LABEL_78;
  }
  v15 = *a2;
  if ( *a2 && *(_QWORD *)v15 )
  {
    *v3 = *v15;
    v3[1] = v15[1];
    v3[2] = v15[2];
    v3[3] = v15[3];
  }
  else
  {
    *((_DWORD *)v3 + 4) = v7 << 16;
    *(_QWORD *)v3 = L"\\\\?PnP?\\Notification";
  }
  v16 = 0;
  for ( j = 0; ; j = (unsigned int)v47 + v51 + 1 )
  {
    m = 0;
    v51 = j;
    if ( v16 >= v7 )
      goto LABEL_77;
    for ( k = 1; k < *v53 && *a2; ++k )
    {
      v19 = (unsigned __int64)*a2 + 64 * (unsigned __int64)k;
      v20 = *(unsigned __int16 **)v19;
      do
      {
        v21 = *(unsigned __int16 *)((char *)pvMem + 2 * j - *(_QWORD *)v19 + (_QWORD)v20);
        v22 = *v20 - v21;
        if ( v22 )
          break;
        ++v20;
      }
      while ( v21 );
      if ( !v22 )
      {
        LODWORD(m) = 1;
        v23 = (unsigned __int64)(v16 + 1) << 6;
        *(_OWORD *)((char *)v3 + v23) = *(_OWORD *)v19;
        *(_OWORD *)((char *)v3 + v23 + 16) = *(_OWORD *)(v19 + 16);
        *(_OWORD *)((char *)v3 + v23 + 32) = *(_OWORD *)(v19 + 32);
        *(_OWORD *)((char *)v3 + v23 + 48) = *(_OWORD *)(v19 + 48);
        LODWORD(j) = v51;
        break;
      }
    }
    v24 = -1;
    v25 = (char *)pvMem + 2 * (unsigned int)j;
    do
      v26 = *(_WORD *)&v25[2 * v24++ + 2] == 0;
    while ( !v26 );
    ++v16;
    v27 = (wchar_t *)HeapAlloc(hHeap, 8u, 2 * v24 + 2);
    v29 = &v3[4 * (unsigned __int64)v16];
    *(_QWORD *)v29 = v27;
    if ( !v27 )
    {
      WppTraceIndent(v28, 2);
      DeviceTypeIdW = 8;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          195,
          &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent);
      }
LABEL_76:
      m = 0;
      goto LABEL_77;
    }
    v30 = (const wchar_t *)((char *)pvMem + 2 * v51);
    v31 = -1;
    do
      ++v31;
    while ( v30[v31] );
    if ( StringCchCopyW(v27, v31 + 1, v30) < 0 )
    {
      DeviceTypeIdW = 122;
      goto LABEL_76;
    }
    if ( (_DWORD)m )
    {
      v32 = *(wchar_t ***)(a1 + 112);
      for ( m = v32; ; m = (wchar_t **)m[30] )
      {
        if ( !m )
        {
          DeviceTypeIdW = 1168;
          goto LABEL_77;
        }
        v33 = (char *)pvMem + 2 * v51;
        v34 = (char *)*m - v33;
        do
        {
          v35 = *(unsigned __int16 *)&v33[v34];
          v36 = *(unsigned __int16 *)v33 - v35;
          if ( v36 )
            break;
          v33 += 2;
        }
        while ( v35 );
        v37 = m[30];
        if ( !v36 )
          break;
        v32 = m;
      }
      if ( m == *(wchar_t ***)(a1 + 112) )
        *(_QWORD *)(a1 + 112) = v37;
      else
        v32[30] = v37;
      goto LABEL_54;
    }
    v38 = hHeap;
    *((_DWORD *)v29 + 4) = 16;
    v39 = (wchar_t **)HeapAlloc(v38, 8u, 0xF8u);
    m = v39;
    if ( !v39 )
      break;
    memset_0(v39, 0, 0xF8u);
    v41 = -1;
    do
      v26 = *(_WORD *)(*(_QWORD *)v29 + 2 * v41++ + 2) == 0;
    while ( !v26 );
    v42 = (wchar_t *)HeapAlloc(hHeap, 8u, 2 * v41 + 2);
    *m = v42;
    if ( !v42 )
    {
      WppTraceIndent(v43, 2);
      DeviceTypeIdW = 8;
      v48 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        v49 = 197;
LABEL_66:
        WPP_SF_s(*((_QWORD *)v48 + 2), v49, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
        goto LABEL_77;
      }
      goto LABEL_77;
    }
    v44 = *(const wchar_t **)v29;
    v45 = -1;
    do
      ++v45;
    while ( v44[v45] );
    if ( StringCchCopyW(v42, v45 + 1, v44) < 0 )
    {
      DeviceTypeIdW = 122;
      goto LABEL_77;
    }
LABEL_54:
    DeviceTypeIdW = SCardGetDeviceTypeIdW(*(_QWORD *)(a1 + 232), *m, &v52, v32);
    if ( DeviceTypeIdW )
    {
      v46 = 32;
      DeviceTypeIdW = 0;
      v52 = 32;
    }
    else
    {
      v46 = v52;
    }
    *((_DWORD *)m + 3) = v46;
    m[30] = (wchar_t *)v9;
    v9 = m;
    v47 = -1;
    do
      ++v47;
    while ( *((_WORD *)pvMem + v51 + v47) );
  }
  WppTraceIndent(v40, 2);
  DeviceTypeIdW = 8;
  v48 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
  {
    v49 = 196;
    goto LABEL_66;
  }
LABEL_77:
  v4 = v53;
LABEL_78:
  if ( *a2 )
  {
    I_FreeReaderStates(*a2);
    *a2 = 0;
    *v4 = 0;
  }
  if ( *(_QWORD *)(a1 + 112) )
  {
    ((void (*)(void))I_ReaderListFree)();
    *(_QWORD *)(a1 + 112) = 0;
  }
  if ( !DeviceTypeIdW )
  {
    *a2 = v3;
    v3 = 0;
    *(_QWORD *)(a1 + 112) = v9;
    v9 = 0;
    *v4 = v7 + 1;
  }
  if ( pvMem )
    SCardFreeMemory(*(_QWORD *)(a1 + 232), pvMem);
  if ( m )
    I_ReaderListFreeItem(m);
  if ( v3 )
    I_FreeReaderStates(v3);
  if ( v9 )
    I_ReaderListFree(v9);
  return DeviceTypeIdW;
}

```

## disassembly

```asm
0x180005830  mov     rax, rsp
0x180005833  mov     [rax+18h], r8
0x180005837  push    rbx
0x180005838  push    rbp
0x180005839  push    rsi
0x18000583a  push    rdi
0x18000583b  push    r12
0x18000583d  push    r13
0x18000583f  push    r14
0x180005841  push    r15
0x180005843  sub     rsp, 28h
0x180005847  xor     esi, esi
0x180005849  mov     dword ptr [rax+8], 0FFFFFFFFh
0x180005850  mov     r13, r8
0x180005853  mov     [rax+20h], rsi
0x180005857  mov     r15, rdx
0x18000585a  mov     [rax+10h], esi
0x18000585d  mov     rbp, rcx
0x180005860  lea     r8, [rax+20h]; mszReaders
0x180005864  mov     rcx, [rcx+0E8h]; hContext
0x18000586b  lea     rdx, mszGroups; "SCard$AllReaders"
0x180005872  lea     r9, [rax+8]; pcchReaders
0x180005876  mov     r12d, esi
0x180005879  mov     edi, esi
0x18000587b  mov     r14d, esi
0x18000587e  call    cs:__imp_SCardListReadersW
0x180005884  mov     ebx, eax
0x180005886  test    eax, eax
0x180005888  jz      loc_18000591D
0x18000588e  cmp     eax, 8010002Eh
0x180005893  jnz     loc_180005D54
0x180005899  mov     ebx, esi
0x18000589b  mov     rcx, cs:hHeap; hHeap
0x1800058a2  lea     r8d, [r12+1]
0x1800058a7  shl     r8, 6; dwBytes
0x1800058ab  mov     edx, 8; dwFlags
0x1800058b0  call    cs:__imp_HeapAlloc
0x1800058b6  mov     rsi, rax
0x1800058b9  test    rax, rax
0x1800058bc  jnz     loc_180005963
0x1800058c2  mov     edx, 2
0x1800058c7  call    WppTraceIndent
0x1800058cc  mov     ebx, 8
0x1800058d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058d8  lea     rdx, WPP_GLOBAL_Control
0x1800058df  cmp     rcx, rdx
0x1800058e2  jz      loc_180005D54
0x1800058e8  test    byte ptr [rcx+1Ch], 1
0x1800058ec  jz      loc_180005D54
0x1800058f2  cmp     byte ptr [rcx+19h], 2
0x1800058f6  jb      loc_180005D54
0x1800058fc  mov     r9, cs:WPP_pszIndent
0x180005903  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000590a  mov     rcx, [rcx+10h]
0x18000590e  mov     edx, 0C2h
0x180005913  call    WPP_SF_s
0x180005918  jmp     loc_180005D54
0x18000591d  mov     r8, [rsp+68h+pvMem]
0x180005925  mov     [rsp+68h+arg_0], esi
0x180005929  test    r8, r8
0x18000592c  jz      loc_18000589B
0x180005932  mov     edx, esi
0x180005934  mov     eax, edx
0x180005936  cmp     si, [r8+rax*2]
0x18000593b  lea     rcx, [r8+rax*2]
0x18000593f  jz      loc_18000589B
0x180005945  inc     r12d
0x180005948  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000594f  nop
0x180005950  inc     rax
0x180005953  cmp     [rcx+rax*2], si
0x180005957  jnz     short loc_180005950
0x180005959  inc     edx
0x18000595b  add     edx, eax
0x18000595d  mov     [rsp+68h+arg_0], edx
0x180005961  jmp     short loc_180005934
0x180005963  mov     rax, [r15]
0x180005966  test    rax, rax
0x180005969  jz      short loc_180005990
0x18000596b  cmp     [rax], rdi
0x18000596e  jz      short loc_180005990
0x180005970  movups  xmm0, xmmword ptr [rax]
0x180005973  movups  xmmword ptr [rsi], xmm0
0x180005976  movups  xmm1, xmmword ptr [rax+10h]
0x18000597a  movups  xmmword ptr [rsi+10h], xmm1
0x18000597e  movups  xmm0, xmmword ptr [rax+20h]
0x180005982  movups  xmmword ptr [rsi+20h], xmm0
0x180005986  movups  xmm1, xmmword ptr [rax+30h]
0x18000598a  movups  xmmword ptr [rsi+30h], xmm1
0x18000598e  jmp     short loc_1800059A3
0x180005990  mov     eax, r12d
0x180005993  shl     eax, 10h
0x180005996  mov     [rsi+10h], eax
0x180005999  lea     rax, aPnpNotificatio; "\\\\?PnP?\\Notification"
0x1800059a0  mov     [rsi], rax
0x1800059a3  xor     r13d, r13d
0x1800059a6  xor     edx, edx
0x1800059a8  xor     edi, edi
0x1800059aa  mov     [rsp+68h+arg_0], edx
0x1800059ae  cmp     r13d, r12d
0x1800059b1  jnb     loc_180005D4C
0x1800059b7  mov     r8d, 1
0x1800059bd  mov     rax, [rsp+68h+arg_10]
0x1800059c5  cmp     r8d, [rax]
0x1800059c8  jnb     short loc_180005A45
0x1800059ca  mov     rcx, [r15]
0x1800059cd  test    rcx, rcx
0x1800059d0  jz      short loc_180005A45
0x1800059d2  mov     rax, [rsp+68h+pvMem]
0x1800059da  mov     r10d, r8d
0x1800059dd  shl     r10, 6
0x1800059e1  add     r10, rcx
0x1800059e4  lea     r11, [rax+rdx*2]
0x1800059e8  mov     rax, [r10]
0x1800059eb  sub     r11, rax
0x1800059ee  movzx   r9d, word ptr [rax]
0x1800059f2  movzx   ecx, word ptr [rax+r11]
0x1800059f7  sub     r9d, ecx
0x1800059fa  jnz     short loc_180005A04
0x1800059fc  add     rax, 2
0x180005a00  test    ecx, ecx
0x180005a02  jnz     short loc_1800059EE
0x180005a04  test    r9d, r9d
0x180005a07  jz      short loc_180005A0E
0x180005a09  inc     r8d
0x180005a0c  jmp     short loc_1800059BD
0x180005a0e  movups  xmm0, xmmword ptr [r10]
0x180005a12  lea     ecx, [r13+1]
0x180005a16  mov     edi, 1
0x180005a1b  shl     rcx, 6
0x180005a1f  movups  xmmword ptr [rcx+rsi], xmm0
0x180005a23  movups  xmm1, xmmword ptr [r10+10h]
0x180005a28  movups  xmmword ptr [rcx+rsi+10h], xmm1
0x180005a2d  movups  xmm0, xmmword ptr [r10+20h]
0x180005a32  movups  xmmword ptr [rcx+rsi+20h], xmm0
0x180005a37  movups  xmm1, xmmword ptr [r10+30h]
0x180005a3c  movups  xmmword ptr [rcx+rsi+30h], xmm1
0x180005a41  mov     edx, [rsp+68h+arg_0]
0x180005a45  mov     rax, [rsp+68h+pvMem]
0x180005a4d  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180005a54  mov     ecx, edx
0x180005a56  lea     rdx, [rax+rcx*2]
0x180005a5a  nop     word ptr [rax+rax+00h]
0x180005a60  cmp     word ptr [rdx+r8*2+2], 0
0x180005a67  lea     r8, [r8+1]
0x180005a6b  jnz     short loc_180005A60
0x180005a6d  mov     rcx, cs:hHeap; hHeap
0x180005a74  lea     r8, ds:2[r8*2]; dwBytes
0x180005a7c  mov     edx, 8; dwFlags
0x180005a81  inc     r13d
0x180005a84  call    cs:__imp_HeapAlloc
0x180005a8a  mov     ebx, r13d
0x180005a8d  shl     rbx, 6
0x180005a91  add     rbx, rsi
0x180005a94  mov     [rbx], rax
0x180005a97  test    rax, rax
0x180005a9a  jz      loc_180005D00
0x180005aa0  mov     edx, [rsp+68h+arg_0]
0x180005aa4  mov     rcx, [rsp+68h+pvMem]
0x180005aac  lea     r8, [rcx+rdx*2]; pszSrc
0x180005ab0  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180005ab7  nop     word ptr [rax+rax+00000000h]
0x180005ac0  inc     rdx
0x180005ac3  cmp     word ptr [r8+rdx*2], 0
0x180005ac9  jnz     short loc_180005AC0
0x180005acb  inc     rdx; cchDest
0x180005ace  mov     rcx, rax; pszDest
0x180005ad1  call    StringCchCopyW
0x180005ad6  test    eax, eax
0x180005ad8  js      loc_180005CF9
0x180005ade  test    edi, edi
0x180005ae0  jz      short loc_180005B51
0x180005ae2  mov     r10, [rbp+70h]
0x180005ae6  mov     r9, r10
0x180005ae9  mov     rdi, r10
0x180005aec  test    rdi, rdi
0x180005aef  jz      loc_180005C55
0x180005af5  mov     ecx, [rsp+68h+arg_0]
0x180005af9  mov     rax, [rsp+68h+pvMem]
0x180005b01  mov     r8, [rdi]
0x180005b04  lea     rdx, [rax+rcx*2]
0x180005b08  sub     r8, rdx
0x180005b0b  nop     dword ptr [rax+rax+00h]
0x180005b10  movzx   ecx, word ptr [rdx]
0x180005b13  movzx   eax, word ptr [rdx+r8]
0x180005b18  sub     ecx, eax
0x180005b1a  jnz     short loc_180005B24
0x180005b1c  add     rdx, 2
0x180005b20  test    eax, eax
0x180005b22  jnz     short loc_180005B10
0x180005b24  mov     rax, [rdi+0F0h]
0x180005b2b  test    ecx, ecx
0x180005b2d  jz      short loc_180005B37
0x180005b2f  mov     r9, rdi
0x180005b32  mov     rdi, rax
0x180005b35  jmp     short loc_180005AEC
0x180005b37  cmp     rdi, r10
0x180005b3a  jnz     short loc_180005B45
0x180005b3c  mov     [rbp+70h], rax
0x180005b40  jmp     loc_180005BED
0x180005b45  mov     [r9+0F0h], rax
0x180005b4c  jmp     loc_180005BED
0x180005b51  mov     rcx, cs:hHeap; hHeap
0x180005b58  mov     edx, 8; dwFlags
0x180005b5d  mov     r8d, 0F8h; dwBytes
0x180005b63  mov     dword ptr [rbx+10h], 10h
0x180005b6a  call    cs:__imp_HeapAlloc
0x180005b70  mov     rdi, rax
0x180005b73  test    rax, rax
0x180005b76  jz      loc_180005CC4
0x180005b7c  xor     edx, edx; Val
0x180005b7e  mov     r8d, 0F8h; Size
0x180005b84  mov     rcx, rax; void *
0x180005b87  call    memset_0
0x180005b8c  mov     rax, [rbx]
0x180005b8f  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180005b96  cmp     word ptr [rax+r8*2+2], 0
0x180005b9d  lea     r8, [r8+1]
0x180005ba1  jnz     short loc_180005B96
0x180005ba3  mov     rcx, cs:hHeap; hHeap
0x180005baa  lea     r8, ds:2[r8*2]; dwBytes
0x180005bb2  mov     edx, 8; dwFlags
0x180005bb7  call    cs:__imp_HeapAlloc
0x180005bbd  mov     [rdi], rax
0x180005bc0  test    rax, rax
0x180005bc3  jz      loc_180005C69
0x180005bc9  mov     r8, [rbx]; pszSrc
0x180005bcc  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180005bd3  inc     rdx
0x180005bd6  cmp     word ptr [r8+rdx*2], 0
0x180005bdc  jnz     short loc_180005BD3
0x180005bde  inc     rdx; cchDest
0x180005be1  mov     rcx, rax; pszDest
0x180005be4  call    StringCchCopyW
0x180005be9  test    eax, eax
0x180005beb  js      short loc_180005C5F
0x180005bed  mov     rdx, [rdi]
0x180005bf0  lea     r8, [rsp+68h+arg_8]
0x180005bf5  mov     rcx, [rbp+0E8h]
0x180005bfc  call    cs:__imp_SCardGetDeviceTypeIdW
0x180005c02  mov     ebx, eax
0x180005c04  test    eax, eax
0x180005c06  jz      short loc_180005C15
0x180005c08  mov     eax, 20h ; ' '
0x180005c0d  xor     ebx, ebx
0x180005c0f  mov     [rsp+68h+arg_8], eax
0x180005c13  jmp     short loc_180005C19
0x180005c15  mov     eax, [rsp+68h+arg_8]
0x180005c19  mov     [rdi+0Ch], eax
0x180005c1c  mov     [rdi+0F0h], r14
0x180005c23  mov     r14, rdi
0x180005c26  mov     rax, [rsp+68h+pvMem]
0x180005c2e  mov     r8d, [rsp+68h+arg_0]
0x180005c33  lea     rdx, [rax+r8*2]
0x180005c37  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005c3e  xchg    ax, ax
0x180005c40  inc     rax
0x180005c43  cmp     word ptr [rdx+rax*2], 0
0x180005c48  jnz     short loc_180005C40
0x180005c4a  lea     edx, [r8+1]
0x180005c4e  add     edx, eax
0x180005c50  jmp     loc_1800059A8
0x180005c55  mov     ebx, 490h
0x180005c5a  jmp     loc_180005D4C
0x180005c5f  mov     ebx, 7Ah ; 'z'
0x180005c64  jmp     loc_180005D4C
0x180005c69  mov     edx, 2
0x180005c6e  call    WppTraceIndent
0x180005c73  mov     ebx, 8
0x180005c78  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c7f  lea     rdx, WPP_GLOBAL_Control
0x180005c86  cmp     rcx, rdx
0x180005c89  jz      loc_180005D4C
0x180005c8f  test    byte ptr [rcx+1Ch], 1
0x180005c93  jz      loc_180005D4C
0x180005c99  cmp     byte ptr [rcx+19h], 2
0x180005c9d  jb      loc_180005D4C
0x180005ca3  mov     edx, 0C5h
0x180005ca8  mov     r9, cs:WPP_pszIndent
0x180005caf  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180005cb6  mov     rcx, [rcx+10h]
0x180005cba  call    WPP_SF_s
0x180005cbf  jmp     loc_180005D4C
0x180005cc4  mov     edx, 2
0x180005cc9  call    WppTraceIndent
0x180005cce  mov     ebx, 8
0x180005cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cda  lea     rdx, WPP_GLOBAL_Control
0x180005ce1  cmp     rcx, rdx
0x180005ce4  jz      short loc_180005D4C
0x180005ce6  test    byte ptr [rcx+1Ch], 1
0x180005cea  jz      short loc_180005D4C
0x180005cec  cmp     byte ptr [rcx+19h], 2
0x180005cf0  jb      short loc_180005D4C
0x180005cf2  mov     edx, 0C4h
0x180005cf7  jmp     short loc_180005CA8
0x180005cf9  mov     ebx, 7Ah ; 'z'
0x180005cfe  jmp     short loc_180005D4A
0x180005d00  mov     edx, 2
0x180005d05  call    WppTraceIndent
  ... truncated ...
```
