# TryToBundleWithAnotherLink

- ea: `0x180014bfc`
- end: `0x180014f39`
- name: `TryToBundleWithAnotherLink`
- size: `829`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000ecac`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x1800101bc`
- `0x180010d3c`
- `0x180014bfc`
- `0x18002b0dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180014e12`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180014e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e88`
- `rasman!RasPortBundle` at `0x180014cb4`
- `rasman!RasPortBundle` at `0x180014cb4`

## string_xrefs

- `0x180014cd7`: `Bundling this link with hPort = %d`

## pseudocode

```c
__int64 __fastcall TryToBundleWithAnotherLink(__int64 a1)
{
  __int64 *j; // rdi
  DWORD LastError; // r15d
  __int64 i; // rsi
  __int64 v5; // rax
  char *v6; // r14
  __int64 v7; // rcx
  __int64 k; // rsi
  __int64 v9; // r9
  __int64 v10; // r8
  int v11; // eax
  LPVOID v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v17[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v16 = 0;
  j = 0;
  LastError = 0;
  memset_0(v17, 0, sizeof(v17));
  *(_QWORD *)(a1 + 72) = -1;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v5 = -1;
    if ( (unsigned int)i >= (unsigned int)qword_18004D970 )
      break;
    for ( j = (__int64 *)*((_QWORD *)PcbTable + i); j; j = (__int64 *)*j )
    {
      if ( j[2] != *(_QWORD *)(a1 + 16) && (j[7] & 1) != 0 && (unsigned int)CanPortsBeBundled(j, a1, 1) )
      {
        if ( *(_DWORD *)(j[1] + 16) >= *(_DWORD *)(j[1] + 24) )
        {
          LastError = 931;
          break;
        }
        LastError = RasPortBundle(j[2], *(_QWORD *)(a1 + 16));
        if ( !LastError )
        {
          if ( byte_18004DF33 < 0 )
          {
            LOWORD(v16) = 0;
            FormatRRASErrorString((wchar_t *)&v16, L"Bundling this link with hPort = %d", j[2]);
            if ( byte_18004DF33 < 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v16);
          }
          *(_QWORD *)(a1 + 72) = j[2];
          break;
        }
      }
    }
    v5 = *(_QWORD *)(a1 + 72);
    if ( v5 != -1 )
      break;
  }
  v6 = 0;
  if ( !LastError && v5 != -1 )
  {
    if ( j )
      *((_DWORD *)j + 14) |= 2u;
    *(_DWORD *)(a1 + 56) |= 2u;
    v6 = *(char **)(a1 + 8);
    if ( j )
    {
      *(_QWORD *)(a1 + 8) = j[1];
      j[9] = *(_QWORD *)(a1 + 16);
    }
    ++*(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL);
    ++*(_DWORD *)(*(_QWORD *)(a1 + 8) + 20LL);
    v7 = *(_QWORD *)(a1 + 8);
    for ( k = 0; (unsigned int)k < *(_DWORD *)(v7 + 48); k = (unsigned int)(k + 1) )
    {
      if ( !*(_QWORD *)(*(_QWORD *)(v7 + 8) + 8 * k) )
      {
        if ( (byte_18004DF34 & 1) != 0 )
        {
          v9 = *(_QWORD *)(a1 + 16);
          LOWORD(v16) = 0;
          FormatRRASErrorString(
            (wchar_t *)&v16,
            L"Found slot %d for port %d in BCB back pointer array",
            (unsigned int)k,
            v9);
          if ( (byte_18004DF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v16);
        }
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 8 * k) = a1;
        break;
      }
    }
    v10 = *(_QWORD *)(a1 + 8);
    v11 = *(_DWORD *)(v10 + 48);
    if ( (_DWORD)k == v11 )
    {
      v12 = HeapReAlloc(hHeap, 8u, *(LPVOID *)(v10 + 8), 8LL * (unsigned int)(2 * v11));
      if ( v12 )
      {
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = v12;
        if ( (byte_18004DF34 & 1) != 0 )
        {
          v14 = *(_QWORD *)(a1 + 16);
          LOWORD(v16) = 0;
          FormatRRASErrorString(
            (wchar_t *)&v16,
            L"Found slot %d for port %d in BCB back pointer array after ReAlloc",
            (unsigned int)k,
            v14);
          if ( (byte_18004DF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v16);
        }
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 8 * k) = a1;
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 48LL) *= 2;
      }
      else
      {
        *(_QWORD *)(a1 + 8) = v6;
        --*(_DWORD *)(j[1] + 16);
        --*(_DWORD *)(j[1] + 20);
        *(_DWORD *)(a1 + 56) &= ~2u;
        if ( byte_18004DF33 < 0 )
        {
          v13 = *(_QWORD *)(a1 + 16);
          LOWORD(v16) = 0;
          FormatRRASErrorString((wchar_t *)&v16, L"Couldn't ReAlloc BCB back pointer array for port %d", v13);
          if ( byte_18004DF33 < 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v16);
        }
        v6 = 0;
        LastError = GetLastError();
      }
    }
  }
  DeallocateAndRemoveBcbFromTable(v6);
  return LastError;
}

```

## disassembly

```asm
0x180014bfc  mov     [rsp-8+arg_8], rbx
0x180014c01  mov     [rsp-8+arg_10], rsi
0x180014c06  push    rbp
0x180014c07  push    rdi
0x180014c08  push    r12
0x180014c0a  push    r14
0x180014c0c  push    r15
0x180014c0e  lea     rbp, [rsp-730h]
0x180014c16  sub     rsp, 830h
0x180014c1d  mov     rax, cs:__security_cookie
0x180014c24  xor     rax, rsp
0x180014c27  mov     [rbp+750h+var_30], rax
0x180014c2e  mov     rbx, rcx
0x180014c31  xor     eax, eax
0x180014c33  lea     rcx, [rsp+850h+var_82C]; void *
0x180014c38  mov     [rsp+850h+var_830], eax
0x180014c3c  xor     edx, edx; Val
0x180014c3e  mov     r8d, 7FCh; Size
0x180014c44  xor     edi, edi
0x180014c46  xor     r15d, r15d
0x180014c49  call    memset_0
0x180014c4e  or      r12, 0FFFFFFFFFFFFFFFFh
0x180014c52  mov     [rbx+48h], r12
0x180014c56  xor     esi, esi
0x180014c58  cmp     esi, dword ptr cs:qword_18004D970
0x180014c5e  mov     rax, r12
0x180014c61  jnb     loc_180014D32
0x180014c67  mov     rax, qword ptr cs:PcbTable
0x180014c6e  mov     rdi, [rax+rsi*8]
0x180014c72  test    rdi, rdi
0x180014c75  jz      loc_180014D22
0x180014c7b  mov     rax, [rbx+10h]
0x180014c7f  cmp     [rdi+10h], rax
0x180014c83  jz      short loc_180014CC7
0x180014c85  test    byte ptr [rdi+38h], 1
0x180014c89  jz      short loc_180014CC7
0x180014c8b  mov     r8d, 1
0x180014c91  mov     rdx, rbx
0x180014c94  mov     rcx, rdi
0x180014c97  call    CanPortsBeBundled
0x180014c9c  test    eax, eax
0x180014c9e  jz      short loc_180014CC7
0x180014ca0  mov     rcx, [rdi+8]
0x180014ca4  mov     eax, [rcx+18h]
0x180014ca7  cmp     [rcx+10h], eax
0x180014caa  jnb     short loc_180014D1C
0x180014cac  mov     rdx, [rbx+10h]
0x180014cb0  mov     rcx, [rdi+10h]
0x180014cb4  call    cs:__imp_RasPortBundle
0x180014cbb  nop     dword ptr [rax+rax+00h]
0x180014cc0  mov     r15d, eax
0x180014cc3  test    eax, eax
0x180014cc5  jz      short loc_180014CCC
0x180014cc7  mov     rdi, [rdi]
0x180014cca  jmp     short loc_180014C72
0x180014ccc  cmp     cs:byte_18004DF33, 0
0x180014cd3  jge     short loc_180014D12
0x180014cd5  xor     eax, eax
0x180014cd7  lea     rdx, aBundlingThisLi; "Bundling this link with hPort = %d"
0x180014cde  mov     word ptr [rsp+850h+var_830], ax
0x180014ce3  lea     rcx, [rsp+850h+var_830]
0x180014ce8  mov     r8, [rdi+10h]
0x180014cec  call    FormatRRASErrorString
0x180014cf1  cmp     cs:byte_18004DF33, 0
0x180014cf8  jge     short loc_180014D12
0x180014cfa  lea     r8, [rsp+850h+var_830]
0x180014cff  lea     rdx, RasPppTraceError
0x180014d06  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014d0d  call    McTemplateU0z_EventWriteTransfer
0x180014d12  mov     rax, [rdi+10h]
0x180014d16  mov     [rbx+48h], rax
0x180014d1a  jmp     short loc_180014D22
0x180014d1c  mov     r15d, 3A3h
0x180014d22  mov     rax, [rbx+48h]
0x180014d26  cmp     rax, r12
0x180014d29  jnz     short loc_180014D32
0x180014d2b  inc     esi
0x180014d2d  jmp     loc_180014C58
0x180014d32  xor     r14d, r14d
0x180014d35  test    r15d, r15d
0x180014d38  jnz     loc_180014F02
0x180014d3e  cmp     rax, r12
0x180014d41  jz      loc_180014F02
0x180014d47  test    rdi, rdi
0x180014d4a  jz      short loc_180014D50
0x180014d4c  or      dword ptr [rdi+38h], 2
0x180014d50  or      dword ptr [rbx+38h], 2
0x180014d54  mov     r14, [rbx+8]
0x180014d58  test    rdi, rdi
0x180014d5b  jz      short loc_180014D6D
0x180014d5d  mov     rax, [rdi+8]
0x180014d61  mov     [rbx+8], rax
0x180014d65  mov     rax, [rbx+10h]
0x180014d69  mov     [rdi+48h], rax
0x180014d6d  mov     rax, [rbx+8]
0x180014d71  inc     dword ptr [rax+10h]
0x180014d74  mov     rax, [rbx+8]
0x180014d78  inc     dword ptr [rax+14h]
0x180014d7b  mov     rcx, [rbx+8]
0x180014d7f  xor     esi, esi
0x180014d81  cmp     esi, [rcx+30h]
0x180014d84  jnb     short loc_180014DEA
0x180014d86  mov     rax, [rcx+8]
0x180014d8a  cmp     qword ptr [rax+rsi*8], 0
0x180014d8f  jz      short loc_180014D95
0x180014d91  inc     esi
0x180014d93  jmp     short loc_180014D81
0x180014d95  test    cs:byte_18004DF34, 1
0x180014d9c  jz      short loc_180014DDE
0x180014d9e  mov     r9, [rbx+10h]
0x180014da2  lea     rdx, aFoundSlotDForP; "Found slot %d for port %d in BCB back p"...
0x180014da9  xor     eax, eax
0x180014dab  lea     rcx, [rsp+850h+var_830]
0x180014db0  mov     r8d, esi
0x180014db3  mov     word ptr [rsp+850h+var_830], ax
0x180014db8  call    FormatRRASErrorString
0x180014dbd  test    cs:byte_18004DF34, 1
0x180014dc4  jz      short loc_180014DDE
0x180014dc6  lea     r8, [rsp+850h+var_830]
0x180014dcb  lea     rdx, RasPppTraceInfo
0x180014dd2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014dd9  call    McTemplateU0z_EventWriteTransfer
0x180014dde  mov     rax, [rbx+8]
0x180014de2  mov     rcx, [rax+8]
0x180014de6  mov     [rcx+rsi*8], rbx
0x180014dea  mov     r8, [rbx+8]
0x180014dee  mov     eax, [r8+30h]
0x180014df2  cmp     esi, eax
0x180014df4  jnz     loc_180014F02
0x180014dfa  mov     r8, [r8+8]; lpMem
0x180014dfe  lea     r9d, [rax+rax]
0x180014e02  mov     rcx, cs:hHeap; hHeap
0x180014e09  mov     edx, 8; dwFlags
0x180014e0e  shl     r9, 3; dwBytes
0x180014e12  call    cs:__imp_HeapReAlloc
0x180014e19  nop     dword ptr [rax+rax+00h]
0x180014e1e  mov     rcx, rax
0x180014e21  test    rax, rax
0x180014e24  jnz     short loc_180014E99
0x180014e26  mov     [rbx+8], r14
0x180014e2a  or      ecx, 0FFFFFFFFh
0x180014e2d  mov     rax, [rdi+8]
0x180014e31  add     [rax+10h], ecx
0x180014e34  mov     rax, [rdi+8]
0x180014e38  add     [rax+14h], ecx
0x180014e3b  and     dword ptr [rbx+38h], 0FFFFFFFDh
0x180014e3f  cmp     cs:byte_18004DF33, 0
0x180014e46  jge     short loc_180014E85
0x180014e48  mov     r8, [rbx+10h]
0x180014e4c  lea     rdx, aCouldnTRealloc; "Couldn't ReAlloc BCB back pointer array"...
0x180014e53  xor     eax, eax
0x180014e55  lea     rcx, [rsp+850h+var_830]
0x180014e5a  mov     word ptr [rsp+850h+var_830], ax
0x180014e5f  call    FormatRRASErrorString
0x180014e64  cmp     cs:byte_18004DF33, 0
0x180014e6b  jge     short loc_180014E85
0x180014e6d  lea     r8, [rsp+850h+var_830]
0x180014e72  lea     rdx, RasPppTraceError
0x180014e79  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014e80  call    McTemplateU0z_EventWriteTransfer
0x180014e85  xor     r14d, r14d
0x180014e88  call    cs:__imp_GetLastError
0x180014e8f  nop     dword ptr [rax+rax+00h]
0x180014e94  mov     r15d, eax
0x180014e97  jmp     short loc_180014F02
0x180014e99  mov     rax, [rbx+8]
0x180014e9d  mov     [rax+8], rcx
0x180014ea1  test    cs:byte_18004DF34, 1
0x180014ea8  jz      short loc_180014EEA
0x180014eaa  mov     r9, [rbx+10h]
0x180014eae  lea     rdx, aFoundSlotDForP_0; "Found slot %d for port %d in BCB back p"...
0x180014eb5  xor     eax, eax
0x180014eb7  lea     rcx, [rsp+850h+var_830]
0x180014ebc  mov     r8d, esi
0x180014ebf  mov     word ptr [rsp+850h+var_830], ax
0x180014ec4  call    FormatRRASErrorString
0x180014ec9  test    cs:byte_18004DF34, 1
0x180014ed0  jz      short loc_180014EEA
0x180014ed2  lea     r8, [rsp+850h+var_830]
0x180014ed7  lea     rdx, RasPppTraceInfo
0x180014ede  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014ee5  call    McTemplateU0z_EventWriteTransfer
0x180014eea  mov     rax, [rbx+8]
0x180014eee  mov     rdx, [rax+8]
0x180014ef2  mov     [rdx+rsi*8], rbx
0x180014ef6  mov     rdx, [rbx+8]
0x180014efa  mov     eax, [rdx+30h]
0x180014efd  add     eax, eax
0x180014eff  mov     [rdx+30h], eax
0x180014f02  mov     rcx, r14; lpMem
0x180014f05  call    DeallocateAndRemoveBcbFromTable
0x180014f0a  mov     eax, r15d
0x180014f0d  mov     rcx, [rbp+750h+var_30]
0x180014f14  xor     rcx, rsp; StackCookie
0x180014f17  call    __security_check_cookie
0x180014f1c  lea     r11, [rsp+850h+var_20]
0x180014f24  mov     rbx, [r11+38h]
0x180014f28  mov     rsi, [r11+40h]
0x180014f2c  mov     rsp, r11
0x180014f2f  pop     r15
0x180014f31  pop     r14
0x180014f33  pop     r12
0x180014f35  pop     rdi
0x180014f36  pop     rbp
0x180014f37  retn
```
