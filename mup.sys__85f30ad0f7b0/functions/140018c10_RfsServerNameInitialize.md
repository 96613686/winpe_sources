# RfsServerNameInitialize

- ea: `0x140018c10`
- end: `0x14001937a`
- name: `RfsServerNameInitialize`
- size: `1898`
- prototype: `__int64 __fastcall(PCUNICODE_STRING StringIn, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140017f50`
- `0x140018570`
- `0x1400189b0`
- `0x14001a920`

## callees

- `0x1400054a0`
- `0x140017cb0`
- `0x140018c10`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140018e98`
- `ntoskrnl!ExAllocatePool2` at `0x14001914c`
- `ntoskrnl!ExAllocatePool2` at `0x140018e98`
- `ntoskrnl!ExAllocatePool2` at `0x14001914c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001904a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001904a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140018fec`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140018fec`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140018e70`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140018e70`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140018c5f`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140018c5f`
- `ntoskrnl!RtlIpv4StringToAddressExW` at `0x140018c9b`
- `ntoskrnl!RtlIpv4StringToAddressExW` at `0x140018c9b`
- `ntoskrnl!RtlIpv6StringToAddressExW` at `0x140018cd0`
- `ntoskrnl!RtlIpv6StringToAddressExW` at `0x140018cd0`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140018da3`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140018e03`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140018da3`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140018e03`

## pseudocode

```c
__int64 __fastcall RfsServerNameInitialize(PCUNICODE_STRING StringIn, __int64 a2)
{
  NTSTATUS v3; // r12d
  USHORT Length; // r10
  PWSTR Buffer; // r9
  unsigned __int16 v6; // cx
  USHORT *v7; // rax
  unsigned __int16 *v8; // r13
  __int64 v9; // rdi
  WCHAR *v10; // rbx
  __int64 v11; // rsi
  WCHAR *v12; // r14
  unsigned __int8 v13; // al
  unsigned __int64 v14; // rax
  WCHAR *v15; // rbx
  WCHAR *j; // rsi
  unsigned __int8 v17; // al
  _OWORD *Pool2; // rax
  __int128 v20; // xmm0
  __int64 s_b4; // rcx
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rax
  USHORT s_w1; // dx
  unsigned __int16 v25; // r8
  unsigned __int16 v26; // r9
  unsigned __int16 v27; // r8
  unsigned __int16 v28; // dx
  __int64 i; // r8
  NTSTATUS v30; // eax
  __int64 v31; // rax
  struct in6_addr v32; // xmm0
  struct _UNICODE_STRING StringOut; // [rsp+20h] [rbp-E0h] BYREF
  in_addr Address[4]; // [rsp+30h] [rbp-D0h] BYREF
  struct in6_addr v35[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v36; // [rsp+60h] [rbp-A0h] BYREF

  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  StringOut = 0;
  v3 = RtlDuplicateUnicodeString(1u, StringIn, &StringOut);
  if ( v3 < 0 )
    goto LABEL_19;
  if ( !StringOut.Length )
  {
    v3 = 0;
    *(_DWORD *)a2 = 0;
LABEL_19:
    RtlFreeUnicodeString(&StringOut);
    return (unsigned int)v3;
  }
  *(_OWORD *)&Address[0].S_un.S_un_b.s_b1 = 0;
  if ( RtlIpv4StringToAddressExW(StringOut.Buffer, 1u, &Address[1], &Address[0].S_un.S_un_w.s_w2) >= 0 )
  {
    Address[0].S_un.S_un_w.s_w1 = 2;
    Pool2 = (_OWORD *)ExAllocatePool2(258, 16, 1382437708);
    *(_QWORD *)(a2 + 8) = Pool2;
    if ( !Pool2 )
    {
      v3 = -1073741670;
LABEL_23:
      if ( v3 >= 0 )
        goto LABEL_17;
      goto LABEL_19;
    }
    v20 = *(_OWORD *)&Address[0].S_un.S_un_b.s_b1;
    *(_DWORD *)a2 = 2;
    *Pool2 = v20;
    s_b4 = Address[3].S_un.S_un_b.s_b4;
    v22 = 0x288D4C21D6A4D26DLL * Address[0].S_un.S_un_b.s_b1
        + 0x8B7970C2A4EFB2A9uLL * Address[0].S_un.S_un_b.s_b2
        + 0x3433B6F080FF8F35LL * Address[0].S_un.S_un_b.s_b3
        + 37
        * (Address[3].S_un.S_un_b.s_b3
         + 37
         * (Address[3].S_un.S_un_b.s_b2
          + 37
          * (Address[3].S_un.S_un_b.s_b1
           + 37
           * (Address[2].S_un.S_un_b.s_b4
            + 37
            * (Address[2].S_un.S_un_b.s_b3
             + 37
             * (Address[2].S_un.S_un_b.s_b2
              + 37
              * (Address[2].S_un.S_un_b.s_b1
               + 37
               * (Address[1].S_un.S_un_b.s_b4
                + 37
                * (Address[1].S_un.S_un_b.s_b3
                 + 37
                 * (Address[1].S_un.S_un_b.s_b2 + 37
                                                * (Address[1].S_un.S_un_b.s_b1 + 37LL * Address[0].S_un.S_un_b.s_b4)))))))))));
    v23 = 0x201911C49281756FLL;
LABEL_22:
    v3 = 0;
    *(_QWORD *)(a2 + 16) = v22 + v23 + s_b4;
    goto LABEL_23;
  }
  memset(v35, 0, 28);
  if ( RtlIpv6StringToAddressExW(
         StringOut.Buffer,
         (struct in6_addr *)&v35[0].u.Word[4],
         (PULONG)&v35[1].u.Word[4],
         &v35[0].u.Word[1]) >= 0 )
  {
    v35[0].u.Word[0] = 23;
    v31 = ExAllocatePool2(258, 28, 1382437708);
    *(_QWORD *)(a2 + 8) = v31;
    if ( !v31 )
    {
      v3 = -1073741670;
      goto LABEL_23;
    }
    v32 = v35[0];
    *(_DWORD *)a2 = 2;
    *(struct in6_addr *)v31 = v32;
    *(struct in6_addr *)(v31 + 12) = *(struct in6_addr *)((char *)v35 + 12);
    s_b4 = v35[1].u.Byte[11];
    v22 = 0xBB24DD21FAFC26B1uLL * v35[0].u.Byte[7]
        + 0xECFE0C79B5739BCDuLL * v35[0].u.Byte[4]
        + 0xBD90C36322378919uLL * v35[0].u.Byte[9]
        + 0x288D4C21D6A4D26DLL * v35[0].u.Byte[12]
        + 0xDB9C20F4D76948E5uLL * v35[0].u.Byte[10]
        + 0x8B7970C2A4EFB2A9uLL * v35[0].u.Byte[13]
        + 0x4FE1DAF580C363FDLL * v35[0].u.Byte[0]
        + 0x65EC3D53F206D09DLL * v35[0].u.Byte[8]
        + 0xC8228AB72E6AE889uLL * v35[0].u.Byte[5]
        + 0x3433B6F080FF8F35LL * v35[0].u.Byte[14]
        + 0x5A90B6DB573C2B45LL * v35[0].u.Byte[2]
        + 0x16EA6DB39BB240F9LL * v35[0].u.Byte[1]
        + 0xC53F5E946719795LL * v35[0].u.Byte[6]
        + 0x40B7CD9739B584A1LL * v35[0].u.Byte[3]
        + 0xDC6C00E405D269C1uLL * v35[0].u.Byte[11]
        + 37
        * (v35[1].u.Byte[10]
         + 37
         * (v35[1].u.Byte[9]
          + 37
          * (v35[1].u.Byte[8]
           + 37
           * (v35[1].u.Byte[7]
            + 37
            * (v35[1].u.Byte[6]
             + 37
             * (v35[1].u.Byte[5]
              + 37
              * (v35[1].u.Byte[4]
               + 37
               * (v35[1].u.Byte[3]
                + 37 * (v35[1].u.Byte[2] + 37 * (v35[1].u.Byte[1] + 37 * (v35[1].u.Byte[0] + 37LL * v35[0].u.Byte[15])))))))))));
    v23 = 0xC861D78C3830329FuLL;
    goto LABEL_22;
  }
  Length = StringOut.Length;
  *(_QWORD *)&Address[2].S_un.S_un_b.s_b1 = &v36;
  v3 = 0;
  *(_QWORD *)&Address[0].S_un.S_un_b.s_b1 = 0x2000000;
  if ( StringOut.Length <= 0x1FEu )
  {
    *(_DWORD *)&v35[0].u.Word[2] = 0;
    if ( StringOut.Length >= 0x22u )
    {
      *(_DWORD *)v35[0].u.Byte = 2228258;
      *(_QWORD *)&v35[0].u.Word[4] = (char *)StringOut.Buffer + StringOut.Length - 34;
      if ( RtlEqualUnicodeString((PCUNICODE_STRING)v35, &RfspIpv6LiteralDomainName, 1u) )
      {
        v35[0] = (struct in6_addr)StringOut;
        v35[0].u.Word[0] = _mm_cvtsi128_si32((__m128i)StringOut) - 34;
        RtlCopyUnicodeString((PUNICODE_STRING)Address, (PCUNICODE_STRING)v35);
        s_w1 = Address[0].S_un.S_un_w.s_w1;
        v25 = 0;
        v26 = Address[0].S_un.S_un_w.s_w1 >> 1;
        if ( Address[0].S_un.S_un_w.s_w1 >> 1 )
        {
          do
          {
            if ( *(_WORD *)(*(_QWORD *)&Address[2].S_un.S_un_b.s_b1 + 2LL * v25) == 45 )
              *(_WORD *)(*(_QWORD *)&Address[2].S_un.S_un_b.s_b1 + 2LL * v25) = 58;
            ++v25;
          }
          while ( v25 < v26 );
          s_w1 = Address[0].S_un.S_un_w.s_w1;
        }
        v27 = 0;
        if ( s_w1 >> 1 )
        {
          do
          {
            if ( *(_WORD *)(*(_QWORD *)&Address[2].S_un.S_un_b.s_b1 + 2LL * v27) == 115 )
              *(_WORD *)(*(_QWORD *)&Address[2].S_un.S_un_b.s_b1 + 2LL * v27) = 37;
            ++v27;
          }
          while ( v27 < (unsigned __int16)(s_w1 >> 1) );
          s_w1 = Address[0].S_un.S_un_w.s_w1;
        }
        v28 = s_w1 >> 1;
        for ( i = 0; (unsigned __int16)i < v28; LOWORD(i) = i + 1 )
        {
          if ( *(_WORD *)(*(_QWORD *)&Address[2].S_un.S_un_b.s_b1 + 2LL * (unsigned __int16)i) == 83 )
            *(_WORD *)(*(_QWORD *)&Address[2].S_un.S_un_b.s_b1 + 2LL * (unsigned __int16)i) = 37;
        }
        v30 = RfspServerNameInitializeAsIpv6(Address, a2, i);
        if ( v30 != -1073741802 )
        {
          v3 = v30;
          goto LABEL_23;
        }
      }
      Length = StringOut.Length;
    }
  }
  Buffer = StringOut.Buffer;
  v6 = 0;
  *(_DWORD *)a2 = 1;
  *(_QWORD *)(a2 + 8) = Buffer;
  *(_WORD *)(a2 + 16) = Length;
  while ( 1 )
  {
    if ( v6 >= (unsigned __int16)(Length >> 1) )
    {
      v7 = (USHORT *)(a2 + 18);
      v8 = (unsigned __int16 *)(a2 + 18);
LABEL_11:
      *v7 = Length;
      goto LABEL_12;
    }
    if ( Buffer[v6] == 46 )
      break;
    ++v6;
  }
  v7 = (USHORT *)(a2 + 18);
  v8 = (unsigned __int16 *)(a2 + 18);
  if ( !&Buffer[v6] )
    goto LABEL_11;
  *v7 = 2 * ((2LL * v6) >> 1);
LABEL_12:
  v9 = 314159;
  v10 = Buffer;
  v11 = 314159;
  v12 = &Buffer[(unsigned __int64)*(unsigned __int16 *)(a2 + 16) >> 1];
  if ( Buffer < v12 )
  {
    do
    {
      v13 = RtlUpcaseUnicodeChar(*v10++);
      v11 = 37 * (v13 + 37 * v11);
    }
    while ( v10 < v12 );
  }
  v14 = *v8;
  v15 = *(WCHAR **)(a2 + 8);
  *(_QWORD *)(a2 + 24) = v11;
  for ( j = &v15[v14 >> 1]; v15 < j; v9 = 37 * (v17 + 37 * v9) )
    v17 = RtlUpcaseUnicodeChar(*v15++);
  *(_QWORD *)(a2 + 32) = v9;
LABEL_17:
  if ( *(_DWORD *)a2 != 1 )
    goto LABEL_19;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140018c10  push    rbp
0x140018c12  push    rbx
0x140018c13  push    r12
0x140018c15  push    r15
0x140018c17  lea     rbp, [rsp-188h]
0x140018c1f  sub     rsp, 288h
0x140018c26  mov     rax, cs:__security_cookie
0x140018c2d  xor     rax, rsp
0x140018c30  mov     [rbp+1A0h+var_40], rax
0x140018c37  xorps   xmm1, xmm1
0x140018c3a  lea     r8, [rsp+2A0h+StringOut]; StringOut
0x140018c3f  movups  xmmword ptr [rdx], xmm1
0x140018c42  xor     eax, eax
0x140018c44  mov     r15, rdx
0x140018c47  movups  xmmword ptr [rdx+10h], xmm1
0x140018c4b  mov     [rdx+20h], rax
0x140018c4f  mov     rdx, rcx; StringIn
0x140018c52  xorps   xmm0, xmm0
0x140018c55  mov     ecx, 1; Flags
0x140018c5a  movups  xmmword ptr [rsp+2A0h+StringOut.Length], xmm0
0x140018c5f  call    cs:__imp_RtlDuplicateUnicodeString
0x140018c66  nop     dword ptr [rax+rax+00h]
0x140018c6b  mov     r12d, eax
0x140018c6e  test    eax, eax
0x140018c70  js      loc_140018E6B
0x140018c76  cmp     [rsp+2A0h+StringOut.Length], 0
0x140018c7c  jz      loc_14001910E
0x140018c82  mov     rcx, [rsp+2A0h+StringOut.Buffer]; AddressString
0x140018c87  lea     r9, [rsp+2A0h+Address.S_un+2]; Port
0x140018c8c  xorps   xmm0, xmm0
0x140018c8f  lea     r8, [rsp+2A0h+Address.S_un+4]; Address
0x140018c94  mov     dl, 1; Strict
0x140018c96  movups  xmmword ptr [rsp+30h], xmm0
0x140018c9b  call    cs:__imp_RtlIpv4StringToAddressExW
0x140018ca2  nop     dword ptr [rax+rax+00h]
0x140018ca7  test    eax, eax
0x140018ca9  jns     loc_140018E7E
0x140018caf  mov     rcx, [rsp+2A0h+StringOut.Buffer]; AddressString
0x140018cb4  lea     r9, [rsp+2A0h+var_260.u+2]; Port
0x140018cb9  xorps   xmm0, xmm0
0x140018cbc  lea     r8, [rsp+2A0h+ScopeId]; ScopeId
0x140018cc1  movups  xmmword ptr [rsp+40h], xmm0
0x140018cc6  lea     rdx, [rsp+2A0h+var_260.u+8]; Address
0x140018ccb  movups  xmmword ptr [rsp+4Ch], xmm0
0x140018cd0  call    cs:__imp_RtlIpv6StringToAddressExW
0x140018cd7  nop     dword ptr [rax+rax+00h]
0x140018cdc  test    eax, eax
0x140018cde  jns     loc_140019132
0x140018ce4  movzx   r10d, [rsp+2A0h+StringOut.Length]
0x140018cea  lea     rax, [rsp+2A0h+var_240]
0x140018cef  mov     qword ptr [rsp+2A0h+Address.S_un+8], rax
0x140018cf4  xor     r12d, r12d
0x140018cf7  mov     eax, 1FEh
0x140018cfc  mov     qword ptr [rsp+30h], 2000000h
0x140018d05  cmp     r10w, ax
0x140018d09  jbe     loc_140018FB5
0x140018d0f  mov     r9, [rsp+2A0h+StringOut.Buffer]
0x140018d14  movzx   r8d, r10w
0x140018d18  mov     [rsp+2A0h+arg_10], rsi
0x140018d20  movzx   ecx, r12w
0x140018d24  mov     [rsp+2A0h+var_20], rdi
0x140018d2c  mov     [rsp+2A0h+var_28], r13
0x140018d34  mov     [rsp+2A0h+var_30], r14
0x140018d3c  mov     dword ptr [r15], 1
0x140018d43  mov     [r15+8], r9
0x140018d47  mov     [r15+10h], r10w
0x140018d4c  shr     r8w, 1
0x140018d50  cmp     cx, r8w
0x140018d54  jnb     short loc_140018D6E
0x140018d56  movzx   eax, cx
0x140018d59  cmp     word ptr [r9+rax*2], 2Eh ; '.'
0x140018d5f  lea     rdx, [r9+rax*2]
0x140018d63  jz      loc_140019007
0x140018d69  inc     cx
0x140018d6c  jmp     short loc_140018D50
0x140018d6e  lea     rax, [r15+12h]
0x140018d72  mov     r13, rax
0x140018d75  mov     [rax], r10w
0x140018d79  movzx   eax, word ptr [r15+10h]
0x140018d7e  mov     edi, 4CB2Fh
0x140018d83  shr     rax, 1
0x140018d86  mov     rbx, r9
0x140018d89  mov     esi, edi
0x140018d8b  lea     r14, [r9+rax*2]
0x140018d8f  cmp     r9, r14
0x140018d92  jnb     short loc_140018DD0
0x140018d94  nop     dword ptr [rax+00h]
0x140018d98  nop     dword ptr [rax+rax+00000000h]
0x140018da0  movzx   ecx, word ptr [rbx]; SourceCharacter
0x140018da3  call    cs:__imp_RtlUpcaseUnicodeChar
0x140018daa  nop     dword ptr [rax+rax+00h]
0x140018daf  imul    rcx, rsi, 25h ; '%'
0x140018db3  movzx   edx, ax
0x140018db6  add     rbx, 2
0x140018dba  movzx   eax, dl
0x140018dbd  add     rcx, rax
0x140018dc0  shr     rdx, 8
0x140018dc4  imul    rsi, rcx, 25h ; '%'
0x140018dc8  add     rsi, rdx
0x140018dcb  cmp     rbx, r14
0x140018dce  jb      short loc_140018DA0
0x140018dd0  movzx   eax, word ptr [r13+0]
0x140018dd5  mov     rbx, [r15+8]
0x140018dd9  mov     r14, [rsp+2A0h+var_30]
0x140018de1  mov     r13, [rsp+2A0h+var_28]
0x140018de9  shr     rax, 1
0x140018dec  mov     [r15+18h], rsi
0x140018df0  lea     rsi, [rbx+rax*2]
0x140018df4  cmp     rbx, rsi
0x140018df7  jnb     short loc_140018E30
0x140018df9  nop     dword ptr [rax+00000000h]
0x140018e00  movzx   ecx, word ptr [rbx]; SourceCharacter
0x140018e03  call    cs:__imp_RtlUpcaseUnicodeChar
0x140018e0a  nop     dword ptr [rax+rax+00h]
0x140018e0f  imul    rcx, rdi, 25h ; '%'
0x140018e13  movzx   edx, ax
0x140018e16  add     rbx, 2
0x140018e1a  movzx   eax, dl
0x140018e1d  add     rcx, rax
0x140018e20  shr     rdx, 8
0x140018e24  imul    rdi, rcx, 25h ; '%'
0x140018e28  add     rdi, rdx
0x140018e2b  cmp     rbx, rsi
0x140018e2e  jb      short loc_140018E00
0x140018e30  mov     rsi, [rsp+2A0h+arg_10]
0x140018e38  mov     [r15+20h], rdi
0x140018e3c  mov     rdi, [rsp+2A0h+var_20]
0x140018e44  cmp     dword ptr [r15], 1
0x140018e48  jnz     short loc_140018E6B
0x140018e4a  mov     eax, r12d
0x140018e4d  mov     rcx, [rbp+1A0h+var_40]
0x140018e54  xor     rcx, rsp; StackCookie
0x140018e57  call    __security_check_cookie
0x140018e5c  add     rsp, 288h
0x140018e63  pop     r15
0x140018e65  pop     r12
0x140018e67  pop     rbx
0x140018e68  pop     rbp
0x140018e69  retn
0x140018e6b  lea     rcx, [rsp+2A0h+StringOut]; UnicodeString
0x140018e70  call    cs:__imp_RtlFreeUnicodeString
0x140018e77  nop     dword ptr [rax+rax+00h]
0x140018e7c  jmp     short loc_140018E4A
0x140018e7e  mov     ebx, 2
0x140018e83  mov     edx, 10h
0x140018e88  mov     ecx, 102h
0x140018e8d  mov     word ptr [rsp+2A0h+Address.S_un], bx
0x140018e92  mov     r8d, 5266534Ch
0x140018e98  call    cs:__imp_ExAllocatePool2
0x140018e9f  nop     dword ptr [rax+rax+00h]
0x140018ea4  mov     [r15+8], rax
0x140018ea8  test    rax, rax
0x140018eab  jz      loc_14001936F
0x140018eb1  movups  xmm0, xmmword ptr [rsp+2A0h+Address.S_un]
0x140018eb6  mov     [r15], ebx
0x140018eb9  movups  xmmword ptr [rax], xmm0
0x140018ebc  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+3]
0x140018ec1  imul    rcx, rax, 25h ; '%'
0x140018ec5  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+4]
0x140018eca  add     rcx, rax
0x140018ecd  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+5]
0x140018ed2  imul    rdx, rcx, 25h ; '%'
0x140018ed6  add     rdx, rax
0x140018ed9  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+6]
0x140018ede  imul    rcx, rdx, 25h ; '%'
0x140018ee2  add     rcx, rax
0x140018ee5  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+7]
0x140018eea  imul    rdx, rcx, 25h ; '%'
0x140018eee  add     rdx, rax
0x140018ef1  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+8]
0x140018ef6  imul    rcx, rdx, 25h ; '%'
0x140018efa  add     rcx, rax
0x140018efd  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+9]
0x140018f02  imul    rdx, rcx, 25h ; '%'
0x140018f06  add     rdx, rax
0x140018f09  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+0Ah]
0x140018f0e  imul    rcx, rdx, 25h ; '%'
0x140018f12  add     rcx, rax
0x140018f15  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+0Bh]
0x140018f1a  imul    rdx, rcx, 25h ; '%'
0x140018f1e  add     rdx, rax
0x140018f21  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+0Ch]
0x140018f26  imul    rcx, rdx, 25h ; '%'
0x140018f2a  add     rcx, rax
0x140018f2d  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+0Dh]
0x140018f32  imul    rdx, rcx, 25h ; '%'
0x140018f36  add     rdx, rax
0x140018f39  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+0Eh]
0x140018f3e  imul    rcx, rdx, 25h ; '%'
0x140018f42  add     rcx, rax
0x140018f45  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+2]
0x140018f4a  imul    rdx, rcx, 25h ; '%'
0x140018f4e  mov     rcx, 3433B6F080FF8F35h
0x140018f58  imul    rax, rcx
0x140018f5c  mov     rcx, 8B7970C2A4EFB2A9h
0x140018f66  add     rdx, rax
0x140018f69  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+1]
0x140018f6e  imul    rax, rcx
0x140018f72  mov     rcx, 288D4C21D6A4D26Dh
0x140018f7c  add     rdx, rax
0x140018f7f  movzx   eax, byte ptr [rsp+2A0h+Address.S_un]
0x140018f84  imul    rax, rcx
0x140018f88  movzx   ecx, byte ptr [rsp+2A0h+Address.S_un+0Fh]
0x140018f8d  add     rdx, rax
0x140018f90  mov     rax, 201911C49281756Fh
0x140018f9a  add     rax, rdx
0x140018f9d  add     rcx, rax
0x140018fa0  xor     r12d, r12d
0x140018fa3  mov     [r15+10h], rcx
0x140018fa7  test    r12d, r12d
0x140018faa  jns     loc_140018E44
0x140018fb0  jmp     loc_140018E6B
0x140018fb5  mov     dword ptr [rsp+2A0h+var_260.u+4], r12d
0x140018fba  cmp     r10d, 22h ; '"'
0x140018fbe  jb      loc_140018D0F
0x140018fc4  mov     rcx, [rsp+2A0h+StringOut.Buffer]
0x140018fc9  lea     rdx, RfspIpv6LiteralDomainName; String2
0x140018fd0  add     r10, 0FFFFFFFFFFFFFFDEh
0x140018fd4  mov     dword ptr [rsp+40h], 220022h
0x140018fdc  add     rcx, r10
0x140018fdf  mov     r8b, 1; CaseInSensitive
0x140018fe2  mov     qword ptr [rsp+2A0h+var_260.u+8], rcx
0x140018fe7  lea     rcx, [rsp+2A0h+var_260]; String1
0x140018fec  call    cs:__imp_RtlEqualUnicodeString
0x140018ff3  nop     dword ptr [rax+rax+00h]
0x140018ff8  test    al, al
0x140018ffa  jnz     short loc_140019028
0x140018ffc  movzx   r10d, [rsp+2A0h+StringOut.Length]
0x140019002  jmp     loc_140018D0F
0x140019007  lea     rax, [r15+12h]
0x14001900b  mov     r13, rax
0x14001900e  test    rdx, rdx
0x140019011  jz      loc_140018D75
0x140019017  sub     rdx, r9
0x14001901a  sar     rdx, 1
0x14001901d  add     dx, dx
0x140019020  mov     [rax], dx
0x140019023  jmp     loc_140018D79
0x140019028  movaps  xmm0, xmmword ptr [rsp+2A0h+StringOut.Length]
0x14001902d  lea     rdx, [rsp+2A0h+var_260]; SourceString
0x140019032  movd    eax, xmm0
0x140019036  lea     rcx, [rsp+2A0h+Address]; DestinationString
0x14001903b  movdqa  xmmword ptr [rsp+2A0h+var_260.u], xmm0
0x140019041  sub     ax, 22h ; '"'
0x140019045  mov     word ptr [rsp+2A0h+var_260.u], ax
0x14001904a  call    cs:__imp_RtlCopyUnicodeString
0x140019051  nop     dword ptr [rax+rax+00h]
0x140019056  movzx   edx, word ptr [rsp+2A0h+Address.S_un]
0x14001905b  movzx   r8d, r12w
0x14001905f  movzx   r9d, dx
0x140019063  shr     r9w, 1
0x140019067  cmp     r12w, r9w
0x14001906b  jnb     short loc_140019090
0x14001906d  mov     rax, qword ptr [rsp+2A0h+Address.S_un+8]
0x140019072  movzx   ecx, r8w
0x140019076  cmp     word ptr [rax+rcx*2], 2Dh ; '-'
0x14001907b  jz      loc_140019119
0x140019081  inc     r8w
0x140019085  cmp     r8w, r9w
0x140019089  jb      short loc_14001906D
0x14001908b  movzx   edx, word ptr [rsp+2A0h+Address.S_un]
0x140019090  movzx   r9d, dx
0x140019094  movzx   r8d, r12w
0x140019098  shr     r9w, 1
0x14001909c  mov     r10d, 25h ; '%'
0x1400190a2  cmp     r12w, r9w
0x1400190a6  jnb     short loc_1400190C7
0x1400190a8  mov     rax, qword ptr [rsp+2A0h+Address.S_un+8]
0x1400190ad  movzx   ecx, r8w
0x1400190b1  cmp     word ptr [rax+rcx*2], 73h ; 's'
0x1400190b6  jz      short loc_140019124
0x1400190b8  inc     r8w
0x1400190bc  cmp     r8w, r9w
0x1400190c0  jb      short loc_1400190A8
0x1400190c2  movzx   edx, word ptr [rsp+2A0h+Address.S_un]
0x1400190c7  shr     dx, 1
0x1400190ca  movzx   r8d, r12w
0x1400190ce  cmp     r12w, dx
0x1400190d2  jnb     short loc_1400190EE
0x1400190d4  mov     rax, qword ptr [rsp+2A0h+Address.S_un+8]
0x1400190d9  movzx   ecx, r8w
0x1400190dd  cmp     word ptr [rax+rcx*2], 53h ; 'S'
0x1400190e2  jz      short loc_14001912B
0x1400190e4  inc     r8w
0x1400190e8  cmp     r8w, dx
0x1400190ec  jb      short loc_1400190D4
0x1400190ee  mov     rdx, r15
0x1400190f1  lea     rcx, [rsp+2A0h+Address]
0x1400190f6  call    RfspServerNameInitializeAsIpv6
0x1400190fb  cmp     eax, 0C0000016h
0x140019100  jz      loc_140018FFC
0x140019106  mov     r12d, eax
0x140019109  jmp     loc_140018FA7
0x14001910e  xor     r12d, r12d
0x140019111  mov     [r15], r12d
0x140019114  jmp     loc_140018E6B
0x140019119  mov     word ptr [rax+rcx*2], 3Ah ; ':'
0x14001911f  jmp     loc_140019081
0x140019124  mov     [rax+rcx*2], r10w
0x140019129  jmp     short loc_1400190B8
  ... truncated ...
```
