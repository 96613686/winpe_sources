# ConvertIpv6AddressToFilterDescriptor_V6

- ea: `0x1800189d8`
- end: `0x180018c74`
- name: `ConvertIpv6AddressToFilterDescriptor_V6`
- size: `668`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001a7c0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x1800189d8`
- `0x18002a138`
- `0x18002c328`
- `0x18002c594`
- `0x18002c604`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018c29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018c32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018c29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018c32`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018a33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018a33`

## string_xrefs

- `0x180018b5d`: `MprInfoCreate failed  in ConvertIpv6AddressToFilterDescriptor_v6 and returned %d`
- `0x180018be4`: `MprInfoCreate failed  in ConvertIpv6AddressToFilterDescriptor_v6 and returned %d`

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
    if ( gIsProtocolCommonTracingEnabled && *((_QWORD *)&xmmword_18004C8E0 + 1) )
    {
      LOWORD(v26) = 0;
      FormatRRASErrorString(
        &v26,
        L"MprInfoCreate failed  in ConvertIpv6AddressToFilterDescriptor_v6 and returned %d",
        v18);
      ((void (__fastcall *)(__int64, _QWORD, int *))gProtocolCommonTemplateFunc)(
        gProtocolCommonEtwContext,
        *((_QWORD *)&xmmword_18004C8E0 + 1),
        &v26);
    }
  }
  else
  {
    v20 = lpNewHeader;
    v19 = MprInfoBlockAdd(lpNewHeader, 0xFFFF0011, 52 * v2 + 64, 1u, lpItemData, &lplpNewHeader);
    if ( v19 )
    {
      if ( gIsProtocolCommonTracingEnabled && *((_QWORD *)&xmmword_18004C8E0 + 1) )
      {
        LOWORD(v26) = 0;
        FormatRRASErrorString(
          &v26,
          L"MprInfoCreate failed  in ConvertIpv6AddressToFilterDescriptor_v6 and returned %d",
          v19);
        ((void (__fastcall *)(__int64, _QWORD, int *))gProtocolCommonTemplateFunc)(
          gProtocolCommonEtwContext,
          *((_QWORD *)&xmmword_18004C8E0 + 1),
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
0x1800189d8  mov     [rsp-8+arg_10], rbx
0x1800189dd  push    rbp
0x1800189de  push    rsi
0x1800189df  push    rdi
0x1800189e0  push    r12
0x1800189e2  push    r13
0x1800189e4  push    r14
0x1800189e6  push    r15
0x1800189e8  lea     rbp, [rsp-770h]
0x1800189f0  sub     rsp, 870h
0x1800189f7  mov     rax, cs:__security_cookie
0x1800189fe  xor     rax, rsp
0x180018a01  mov     [rbp+7A0h+var_40], rax
0x180018a08  lea     r15d, [rdx-1]
0x180018a0c  mov     [rsp+8A0h+lpNewHeader], 0
0x180018a15  mov     esi, edx
0x180018a17  mov     eax, r15d
0x180018a1a  imul    rdx, rax, 34h ; '4'
0x180018a1e  mov     r14, rcx
0x180018a21  mov     [rsp+8A0h+var_868], 0
0x180018a2a  add     rdx, 40h ; '@'; uBytes
0x180018a2e  mov     ecx, 40h ; '@'; uFlags
0x180018a33  call    cs:__imp_LocalAlloc
0x180018a39  mov     [rsp+8A0h+var_848], rax
0x180018a3e  xor     edx, edx; Val
0x180018a40  mov     rbx, rax
0x180018a43  lea     rcx, [rsp+8A0h+var_83C]; void *
0x180018a48  xor     eax, eax
0x180018a4a  mov     r8d, 7FCh; Size
0x180018a50  mov     [rsp+8A0h+var_840], eax
0x180018a54  call    memset_0
0x180018a59  xor     eax, eax
0x180018a5b  xor     edi, edi
0x180018a5d  mov     [rsp+8A0h+var_850], eax
0x180018a61  xorps   xmm0, xmm0
0x180018a64  movups  [rsp+8A0h+var_860], xmm0
0x180018a69  test    esi, esi
0x180018a6b  jz      loc_180018B20
0x180018a71  mov     r12, [r14]
0x180018a74  mov     eax, edi
0x180018a76  xor     r13d, r13d
0x180018a79  shl     eax, 4
0x180018a7c  mov     r15d, eax
0x180018a7f  lea     rbx, [r12+rax]
0x180018a83  lea     r11d, ds:0[r13*4]
0x180018a8b  inc     r13d
0x180018a8e  movzx   r8d, byte ptr [r11+rbx]
0x180018a93  lea     rdx, [r11+r12]
0x180018a97  movzx   eax, byte ptr [rdx+r15+2]
0x180018a9d  movzx   r9d, byte ptr [rdx+r15+1]
0x180018aa3  shl     eax, 8
0x180018aa6  shl     r9d, 10h
0x180018aaa  add     r9d, eax
0x180018aad  mov     byte ptr [rsp+r11+8A0h+var_860], r8b
0x180018ab2  mov     eax, r8d
0x180018ab5  shl     eax, 18h
0x180018ab8  add     r9d, eax
0x180018abb  movzx   eax, byte ptr [rdx+r15+3]
0x180018ac1  add     r9d, eax
0x180018ac4  lea     eax, [r11+1]
0x180018ac8  mov     edx, r9d
0x180018acb  shr     edx, 10h
0x180018ace  mov     byte ptr [rsp+rax+8A0h+var_860], dl
0x180018ad2  lea     eax, [r11+2]
0x180018ad6  mov     edx, r9d
0x180018ad9  shr     edx, 8
0x180018adc  mov     byte ptr [rsp+rax+8A0h+var_860], dl
0x180018ae0  lea     eax, [r11+3]
0x180018ae4  mov     byte ptr [rsp+rax+8A0h+var_860], r9b
0x180018ae9  cmp     r13d, 5
0x180018aed  jb      short loc_180018A83
0x180018aef  mov     rbx, [rsp+8A0h+var_848]
0x180018af4  movups  xmm0, [rsp+8A0h+var_860+1]
0x180018af9  mov     eax, edi
0x180018afb  inc     edi
0x180018afd  imul    rcx, rax, 34h ; '4'; dwVersion
0x180018b01  or      dword ptr [rcx+rbx+38h], 11h
0x180018b06  mov     dword ptr [rcx+rbx+30h], 80h
0x180018b0e  movdqu  xmmword ptr [rcx+rbx+20h], xmm0
0x180018b14  cmp     edi, esi
0x180018b16  jb      loc_180018A71
0x180018b1c  lea     r15d, [rsi-1]
0x180018b20  lea     rdx, [rsp+8A0h+lpNewHeader]; lplpNewHeader
0x180018b25  mov     dword ptr [rbx+8], 1
0x180018b2c  mov     dword ptr [rbx], 1
0x180018b32  mov     [rbx+4], esi
0x180018b35  call    MprInfoCreate
0x180018b3a  mov     edi, eax
0x180018b3c  test    eax, eax
0x180018b3e  jz      short loc_180018B9A
0x180018b40  cmp     cs:gIsProtocolCommonTracingEnabled, 0
0x180018b47  jz      loc_180018C48
0x180018b4d  cmp     qword ptr cs:xmmword_18004C8E0+8, 0
0x180018b55  jz      loc_180018C48
0x180018b5b  xor     ecx, ecx
0x180018b5d  lea     rdx, aMprinfocreateF_0; "MprInfoCreate failed  in ConvertIpv6Add"...
0x180018b64  mov     word ptr [rsp+8A0h+var_840], cx
0x180018b69  mov     r8d, eax
0x180018b6c  lea     rcx, [rsp+8A0h+var_840]
0x180018b71  call    FormatRRASErrorString
0x180018b76  mov     rdx, qword ptr cs:xmmword_18004C8E0+8
0x180018b7d  lea     r8, [rsp+8A0h+var_840]
0x180018b82  mov     rcx, cs:gProtocolCommonEtwContext
0x180018b89  mov     rax, cs:gProtocolCommonTemplateFunc
0x180018b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b95  jmp     loc_180018C48
0x180018b9a  mov     rsi, [rsp+8A0h+lpNewHeader]
0x180018b9f  lea     rax, [rsp+8A0h+var_868]
0x180018ba4  imul    r8d, r15d, 34h ; '4'
0x180018ba8  mov     edx, 0FFFF0011h; dwInfoType
0x180018bad  mov     [rsp+8A0h+lplpNewHeader], rax; lplpNewHeader
0x180018bb2  mov     r9d, 1; dwItemCount
0x180018bb8  mov     rcx, rsi; lpHeader
0x180018bbb  mov     [rsp+8A0h+lpItemData], rbx; lpItemData
0x180018bc0  add     r8d, 40h ; '@'; dwItemSize
0x180018bc4  call    MprInfoBlockAdd
0x180018bc9  mov     edi, eax
0x180018bcb  test    eax, eax
0x180018bcd  jz      short loc_180018C26
0x180018bcf  cmp     cs:gIsProtocolCommonTracingEnabled, 0
0x180018bd6  jz      short loc_180018C1C
0x180018bd8  cmp     qword ptr cs:xmmword_18004C8E0+8, 0
0x180018be0  jz      short loc_180018C1C
0x180018be2  xor     eax, eax
0x180018be4  lea     rdx, aMprinfocreateF_0; "MprInfoCreate failed  in ConvertIpv6Add"...
0x180018beb  mov     r8d, edi
0x180018bee  mov     word ptr [rsp+8A0h+var_840], ax
0x180018bf3  lea     rcx, [rsp+8A0h+var_840]
0x180018bf8  call    FormatRRASErrorString
0x180018bfd  mov     rdx, qword ptr cs:xmmword_18004C8E0+8
0x180018c04  lea     r8, [rsp+8A0h+var_840]
0x180018c09  mov     rcx, cs:gProtocolCommonEtwContext
0x180018c10  mov     rax, cs:gProtocolCommonTemplateFunc
0x180018c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c1c  mov     rcx, rsi; lpHeader
0x180018c1f  call    MprInfoDelete
0x180018c24  jmp     short loc_180018C48
0x180018c26  mov     rcx, [r14]; hMem
0x180018c29  call    cs:__imp_LocalFree
0x180018c2f  mov     rcx, rbx; hMem
0x180018c32  call    cs:__imp_LocalFree
0x180018c38  mov     rcx, rsi; lpHeader
0x180018c3b  call    MprInfoDelete
0x180018c40  mov     rax, [rsp+8A0h+var_868]
0x180018c45  mov     [r14], rax
0x180018c48  mov     eax, edi
0x180018c4a  mov     rcx, [rbp+7A0h+var_40]
0x180018c51  xor     rcx, rsp; StackCookie
0x180018c54  call    __security_check_cookie
0x180018c59  mov     rbx, [rsp+8A0h+arg_10]
0x180018c61  add     rsp, 870h
0x180018c68  pop     r15
0x180018c6a  pop     r14
0x180018c6c  pop     r13
0x180018c6e  pop     r12
0x180018c70  pop     rdi
0x180018c71  pop     rsi
0x180018c72  pop     rbp
0x180018c73  retn
```
