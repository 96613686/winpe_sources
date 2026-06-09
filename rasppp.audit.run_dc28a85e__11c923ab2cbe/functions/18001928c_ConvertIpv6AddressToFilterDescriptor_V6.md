# ConvertIpv6AddressToFilterDescriptor_V6

- ea: `0x18001928c`
- end: `0x18001953b`
- name: `ConvertIpv6AddressToFilterDescriptor_V6`
- size: `687`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001b198`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18001928c`
- `0x18002b0dc`
- `0x18002d414`
- `0x18002d68c`
- `0x18002d708`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800194e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800194f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800194e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800194f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800192e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800192e7`

## string_xrefs

- `0x180019417`: `MprInfoCreate failed  in ConvertIpv6AddressToFilterDescriptor_v6 and returned %d`
- `0x18001949e`: `MprInfoCreate failed  in ConvertIpv6AddressToFilterDescriptor_v6 and returned %d`

## pseudocode

```c
__int64 __fastcall ConvertIpv6AddressToFilterDescriptor_V6(HLOCAL *a1, unsigned int a2)
{
  unsigned int v2; // r15d
  BYTE *lpItemData; // rbx
  __int64 v6; // rcx
  unsigned int v7; // edi
  unsigned __int8 *v8; // r12
  unsigned int v9; // r13d
  __int64 v10; // r15
  char *v11; // rbx
  __int64 v12; // r11
  int v13; // r8d
  int v14; // r9d
  int v15; // r9d
  __int128 v16; // xmm0
  __int64 v17; // rax
  DWORD v18; // eax
  DWORD v19; // edi
  void *v20; // rsi
  LPVOID lpNewHeader; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lplpNewHeader; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v24[20]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  char v27[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v2 = a2 - 1;
  lpNewHeader = 0;
  lplpNewHeader = 0;
  v25 = (BYTE *)LocalAlloc(0x40u, 52LL * (a2 - 1) + 64);
  lpItemData = v25;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v7 = 0;
  memset(v24, 0, sizeof(v24));
  if ( a2 )
  {
    do
    {
      v8 = (unsigned __int8 *)*a1;
      v9 = 0;
      v10 = 16 * v7;
      v11 = (char *)*a1 + v10;
      do
      {
        v12 = 4 * v9++;
        v13 = (unsigned __int8)v11[v12];
        v14 = (v8[v12 + 2 + v10] << 8) + (v8[v12 + 1 + v10] << 16);
        v24[v12] = v13;
        v15 = v8[v12 + 3 + v10] + (v13 << 24) + v14;
        v24[(unsigned int)(v12 + 1)] = BYTE2(v15);
        v24[(unsigned int)(v12 + 2)] = BYTE1(v15);
        v24[(unsigned int)(v12 + 3)] = v15;
      }
      while ( v9 < 5 );
      lpItemData = v25;
      v16 = *(_OWORD *)&v24[1];
      v17 = v7++;
      v6 = 52 * v17;
      *(_DWORD *)&v25[v6 + 56] |= 0x11u;
      *(_DWORD *)&lpItemData[v6 + 48] = 128;
      *(_OWORD *)&lpItemData[v6 + 32] = v16;
    }
    while ( v7 < a2 );
    v2 = a2 - 1;
  }
  *((_DWORD *)lpItemData + 2) = 1;
  *(_DWORD *)lpItemData = 1;
  *((_DWORD *)lpItemData + 1) = a2;
  v18 = MprInfoCreate(v6, &lpNewHeader);
  v19 = v18;
  if ( v18 )
  {
    if ( gIsProtocolCommonTracingEnabled && *((_QWORD *)&xmmword_18004D8E0 + 1) )
    {
      LOWORD(v26) = 0;
      FormatRRASErrorString(
        &v26,
        L"MprInfoCreate failed  in ConvertIpv6AddressToFilterDescriptor_v6 and returned %d",
        v18);
      ((void (__fastcall *)(__int64, _QWORD, int *))gProtocolCommonTemplateFunc)(
        gProtocolCommonEtwContext,
        *((_QWORD *)&xmmword_18004D8E0 + 1),
        &v26);
    }
  }
  else
  {
    v20 = lpNewHeader;
    v19 = MprInfoBlockAdd(lpNewHeader, 0xFFFF0011, 52 * v2 + 64, 1u, lpItemData, &lplpNewHeader);
    if ( v19 )
    {
      if ( gIsProtocolCommonTracingEnabled && *((_QWORD *)&xmmword_18004D8E0 + 1) )
      {
        LOWORD(v26) = 0;
        FormatRRASErrorString(
          &v26,
          L"MprInfoCreate failed  in ConvertIpv6AddressToFilterDescriptor_v6 and returned %d",
          v19);
        ((void (__fastcall *)(__int64, _QWORD, int *))gProtocolCommonTemplateFunc)(
          gProtocolCommonEtwContext,
          *((_QWORD *)&xmmword_18004D8E0 + 1),
          &v26);
      }
      MprInfoDelete(v20);
    }
    else
    {
      LocalFree(*a1);
      LocalFree(lpItemData);
      MprInfoDelete(v20);
      *a1 = lplpNewHeader;
    }
  }
  return v19;
}

```

## disassembly

```asm
0x18001928c  mov     [rsp-8+arg_10], rbx
0x180019291  push    rbp
0x180019292  push    rsi
0x180019293  push    rdi
0x180019294  push    r12
0x180019296  push    r13
0x180019298  push    r14
0x18001929a  push    r15
0x18001929c  lea     rbp, [rsp-770h]
0x1800192a4  sub     rsp, 870h
0x1800192ab  mov     rax, cs:__security_cookie
0x1800192b2  xor     rax, rsp
0x1800192b5  mov     [rbp+7A0h+var_40], rax
0x1800192bc  lea     r15d, [rdx-1]
0x1800192c0  mov     [rsp+8A0h+lpNewHeader], 0
0x1800192c9  mov     esi, edx
0x1800192cb  mov     eax, r15d
0x1800192ce  imul    rdx, rax, 34h ; '4'
0x1800192d2  mov     r14, rcx
0x1800192d5  mov     [rsp+8A0h+var_868], 0
0x1800192de  add     rdx, 40h ; '@'; uBytes
0x1800192e2  mov     ecx, 40h ; '@'; uFlags
0x1800192e7  call    cs:__imp_LocalAlloc
0x1800192ee  nop     dword ptr [rax+rax+00h]
0x1800192f3  mov     [rsp+8A0h+var_848], rax
0x1800192f8  xor     edx, edx; Val
0x1800192fa  mov     rbx, rax
0x1800192fd  lea     rcx, [rsp+8A0h+var_83C]; void *
0x180019302  xor     eax, eax
0x180019304  mov     r8d, 7FCh; Size
0x18001930a  mov     [rsp+8A0h+var_840], eax
0x18001930e  call    memset_0
0x180019313  xor     eax, eax
0x180019315  xor     edi, edi
0x180019317  mov     [rsp+8A0h+var_850], eax
0x18001931b  xorps   xmm0, xmm0
0x18001931e  movups  [rsp+8A0h+var_860], xmm0
0x180019323  test    esi, esi
0x180019325  jz      loc_1800193DA
0x18001932b  mov     r12, [r14]
0x18001932e  mov     eax, edi
0x180019330  xor     r13d, r13d
0x180019333  shl     eax, 4
0x180019336  mov     r15d, eax
0x180019339  lea     rbx, [r12+rax]
0x18001933d  lea     r11d, ds:0[r13*4]
0x180019345  inc     r13d
0x180019348  movzx   r8d, byte ptr [r11+rbx]
0x18001934d  lea     rdx, [r11+r12]
0x180019351  movzx   eax, byte ptr [rdx+r15+2]
0x180019357  movzx   r9d, byte ptr [rdx+r15+1]
0x18001935d  shl     eax, 8
0x180019360  shl     r9d, 10h
0x180019364  add     r9d, eax
0x180019367  mov     byte ptr [rsp+r11+8A0h+var_860], r8b
0x18001936c  mov     eax, r8d
0x18001936f  shl     eax, 18h
0x180019372  add     r9d, eax
0x180019375  movzx   eax, byte ptr [rdx+r15+3]
0x18001937b  add     r9d, eax
0x18001937e  lea     eax, [r11+1]
0x180019382  mov     edx, r9d
0x180019385  shr     edx, 10h
0x180019388  mov     byte ptr [rsp+rax+8A0h+var_860], dl
0x18001938c  lea     eax, [r11+2]
0x180019390  mov     edx, r9d
0x180019393  shr     edx, 8
0x180019396  mov     byte ptr [rsp+rax+8A0h+var_860], dl
0x18001939a  lea     eax, [r11+3]
0x18001939e  mov     byte ptr [rsp+rax+8A0h+var_860], r9b
0x1800193a3  cmp     r13d, 5
0x1800193a7  jb      short loc_18001933D
0x1800193a9  mov     rbx, [rsp+8A0h+var_848]
0x1800193ae  movups  xmm0, [rsp+8A0h+var_860+1]
0x1800193b3  mov     eax, edi
0x1800193b5  inc     edi
0x1800193b7  imul    rcx, rax, 34h ; '4'; dwVersion
0x1800193bb  or      dword ptr [rcx+rbx+38h], 11h
0x1800193c0  mov     dword ptr [rcx+rbx+30h], 80h
0x1800193c8  movdqu  xmmword ptr [rcx+rbx+20h], xmm0
0x1800193ce  cmp     edi, esi
0x1800193d0  jb      loc_18001932B
0x1800193d6  lea     r15d, [rsi-1]
0x1800193da  lea     rdx, [rsp+8A0h+lpNewHeader]; lplpNewHeader
0x1800193df  mov     dword ptr [rbx+8], 1
0x1800193e6  mov     dword ptr [rbx], 1
0x1800193ec  mov     [rbx+4], esi
0x1800193ef  call    MprInfoCreate
0x1800193f4  mov     edi, eax
0x1800193f6  test    eax, eax
0x1800193f8  jz      short loc_180019454
0x1800193fa  cmp     cs:gIsProtocolCommonTracingEnabled, 0
0x180019401  jz      loc_18001950E
0x180019407  cmp     qword ptr cs:xmmword_18004D8E0+8, 0
0x18001940f  jz      loc_18001950E
0x180019415  xor     ecx, ecx
0x180019417  lea     rdx, aMprinfocreateF_0; "MprInfoCreate failed  in ConvertIpv6Add"...
0x18001941e  mov     word ptr [rsp+8A0h+var_840], cx
0x180019423  mov     r8d, eax
0x180019426  lea     rcx, [rsp+8A0h+var_840]
0x18001942b  call    FormatRRASErrorString
0x180019430  mov     rdx, qword ptr cs:xmmword_18004D8E0+8
0x180019437  lea     r8, [rsp+8A0h+var_840]
0x18001943c  mov     rcx, cs:gProtocolCommonEtwContext
0x180019443  mov     rax, cs:gProtocolCommonTemplateFunc
0x18001944a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001944f  jmp     loc_18001950E
0x180019454  mov     rsi, [rsp+8A0h+lpNewHeader]
0x180019459  lea     rax, [rsp+8A0h+var_868]
0x18001945e  imul    r8d, r15d, 34h ; '4'
0x180019462  mov     edx, 0FFFF0011h; dwInfoType
0x180019467  mov     [rsp+8A0h+lplpNewHeader], rax; lplpNewHeader
0x18001946c  mov     r9d, 1; dwItemCount
0x180019472  mov     rcx, rsi; lpHeader
0x180019475  mov     [rsp+8A0h+lpItemData], rbx; lpItemData
0x18001947a  add     r8d, 40h ; '@'; dwItemSize
0x18001947e  call    MprInfoBlockAdd
0x180019483  mov     edi, eax
0x180019485  test    eax, eax
0x180019487  jz      short loc_1800194E0
0x180019489  cmp     cs:gIsProtocolCommonTracingEnabled, 0
0x180019490  jz      short loc_1800194D6
0x180019492  cmp     qword ptr cs:xmmword_18004D8E0+8, 0
0x18001949a  jz      short loc_1800194D6
0x18001949c  xor     eax, eax
0x18001949e  lea     rdx, aMprinfocreateF_0; "MprInfoCreate failed  in ConvertIpv6Add"...
0x1800194a5  mov     r8d, edi
0x1800194a8  mov     word ptr [rsp+8A0h+var_840], ax
0x1800194ad  lea     rcx, [rsp+8A0h+var_840]
0x1800194b2  call    FormatRRASErrorString
0x1800194b7  mov     rdx, qword ptr cs:xmmword_18004D8E0+8
0x1800194be  lea     r8, [rsp+8A0h+var_840]
0x1800194c3  mov     rcx, cs:gProtocolCommonEtwContext
0x1800194ca  mov     rax, cs:gProtocolCommonTemplateFunc
0x1800194d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194d6  mov     rcx, rsi; lpHeader
0x1800194d9  call    MprInfoDelete
0x1800194de  jmp     short loc_18001950E
0x1800194e0  mov     rcx, [r14]; hMem
0x1800194e3  call    cs:__imp_LocalFree
0x1800194ea  nop     dword ptr [rax+rax+00h]
0x1800194ef  mov     rcx, rbx; hMem
0x1800194f2  call    cs:__imp_LocalFree
0x1800194f9  nop     dword ptr [rax+rax+00h]
0x1800194fe  mov     rcx, rsi; lpHeader
0x180019501  call    MprInfoDelete
0x180019506  mov     rax, [rsp+8A0h+var_868]
0x18001950b  mov     [r14], rax
0x18001950e  mov     eax, edi
0x180019510  mov     rcx, [rbp+7A0h+var_40]
0x180019517  xor     rcx, rsp; StackCookie
0x18001951a  call    __security_check_cookie
0x18001951f  mov     rbx, [rsp+8A0h+arg_10]
0x180019527  add     rsp, 870h
0x18001952e  pop     r15
0x180019530  pop     r14
0x180019532  pop     r13
0x180019534  pop     r12
0x180019536  pop     rdi
0x180019537  pop     rsi
0x180019538  pop     rbp
0x180019539  retn
```
