# RfsServerNameInitialize

- ea: `0x140018bc0`
- end: `0x14001932a`
- name: `RfsServerNameInitialize`
- size: `1898`
- prototype: `__int64 __fastcall(PCUNICODE_STRING StringIn)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140017f00`
- `0x140018520`
- `0x140018960`
- `0x14001a8d0`

## callees

- `0x1400054a0`
- `0x140017c60`
- `0x140018bc0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140018e48`
- `ntoskrnl!ExAllocatePool2` at `0x1400190fc`
- `ntoskrnl!ExAllocatePool2` at `0x140018e48`
- `ntoskrnl!ExAllocatePool2` at `0x1400190fc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140018ffa`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140018ffa`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140018f9c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140018f9c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140018e20`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140018e20`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140018c0f`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140018c0f`
- `ntoskrnl!RtlIpv4StringToAddressExW` at `0x140018c4b`
- `ntoskrnl!RtlIpv4StringToAddressExW` at `0x140018c4b`
- `ntoskrnl!RtlIpv6StringToAddressExW` at `0x140018c80`
- `ntoskrnl!RtlIpv6StringToAddressExW` at `0x140018c80`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140018d53`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140018db3`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140018d53`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140018db3`

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
0x140018bc0  push    rbp
0x140018bc2  push    rbx
0x140018bc3  push    r12
0x140018bc5  push    r15
0x140018bc7  lea     rbp, [rsp-188h]
0x140018bcf  sub     rsp, 288h
0x140018bd6  mov     rax, cs:__security_cookie
0x140018bdd  xor     rax, rsp
0x140018be0  mov     [rbp+1A0h+var_40], rax
0x140018be7  xorps   xmm1, xmm1
0x140018bea  lea     r8, [rsp+2A0h+StringOut]; StringOut
0x140018bef  movups  xmmword ptr [rdx], xmm1
0x140018bf2  xor     eax, eax
0x140018bf4  mov     r15, rdx
0x140018bf7  movups  xmmword ptr [rdx+10h], xmm1
0x140018bfb  mov     [rdx+20h], rax
0x140018bff  mov     rdx, rcx; StringIn
0x140018c02  xorps   xmm0, xmm0
0x140018c05  mov     ecx, 1; Flags
0x140018c0a  movups  xmmword ptr [rsp+2A0h+StringOut.Length], xmm0
0x140018c0f  call    cs:__imp_RtlDuplicateUnicodeString
0x140018c16  nop     dword ptr [rax+rax+00h]
0x140018c1b  mov     r12d, eax
0x140018c1e  test    eax, eax
0x140018c20  js      loc_140018E1B
0x140018c26  cmp     [rsp+2A0h+StringOut.Length], 0
0x140018c2c  jz      loc_1400190BE
0x140018c32  mov     rcx, [rsp+2A0h+StringOut.Buffer]; AddressString
0x140018c37  lea     r9, [rsp+2A0h+Address.S_un+2]; Port
0x140018c3c  xorps   xmm0, xmm0
0x140018c3f  lea     r8, [rsp+2A0h+Address.S_un+4]; Address
0x140018c44  mov     dl, 1; Strict
0x140018c46  movups  xmmword ptr [rsp+30h], xmm0
0x140018c4b  call    cs:__imp_RtlIpv4StringToAddressExW
0x140018c52  nop     dword ptr [rax+rax+00h]
0x140018c57  test    eax, eax
0x140018c59  jns     loc_140018E2E
0x140018c5f  mov     rcx, [rsp+2A0h+StringOut.Buffer]; AddressString
0x140018c64  lea     r9, [rsp+2A0h+var_260.u+2]; Port
0x140018c69  xorps   xmm0, xmm0
0x140018c6c  lea     r8, [rsp+2A0h+ScopeId]; ScopeId
0x140018c71  movups  xmmword ptr [rsp+40h], xmm0
0x140018c76  lea     rdx, [rsp+2A0h+var_260.u+8]; Address
0x140018c7b  movups  xmmword ptr [rsp+4Ch], xmm0
0x140018c80  call    cs:__imp_RtlIpv6StringToAddressExW
0x140018c87  nop     dword ptr [rax+rax+00h]
0x140018c8c  test    eax, eax
0x140018c8e  jns     loc_1400190E2
0x140018c94  movzx   r10d, [rsp+2A0h+StringOut.Length]
0x140018c9a  lea     rax, [rsp+2A0h+var_240]
0x140018c9f  mov     qword ptr [rsp+2A0h+Address.S_un+8], rax
0x140018ca4  xor     r12d, r12d
0x140018ca7  mov     eax, 1FEh
0x140018cac  mov     qword ptr [rsp+30h], 2000000h
0x140018cb5  cmp     r10w, ax
0x140018cb9  jbe     loc_140018F65
0x140018cbf  mov     r9, [rsp+2A0h+StringOut.Buffer]
0x140018cc4  movzx   r8d, r10w
0x140018cc8  mov     [rsp+2A0h+arg_10], rsi
0x140018cd0  movzx   ecx, r12w
0x140018cd4  mov     [rsp+2A0h+var_20], rdi
0x140018cdc  mov     [rsp+2A0h+var_28], r13
0x140018ce4  mov     [rsp+2A0h+var_30], r14
0x140018cec  mov     dword ptr [r15], 1
0x140018cf3  mov     [r15+8], r9
0x140018cf7  mov     [r15+10h], r10w
0x140018cfc  shr     r8w, 1
0x140018d00  cmp     cx, r8w
0x140018d04  jnb     short loc_140018D1E
0x140018d06  movzx   eax, cx
0x140018d09  cmp     word ptr [r9+rax*2], 2Eh ; '.'
0x140018d0f  lea     rdx, [r9+rax*2]
0x140018d13  jz      loc_140018FB7
0x140018d19  inc     cx
0x140018d1c  jmp     short loc_140018D00
0x140018d1e  lea     rax, [r15+12h]
0x140018d22  mov     r13, rax
0x140018d25  mov     [rax], r10w
0x140018d29  movzx   eax, word ptr [r15+10h]
0x140018d2e  mov     edi, 4CB2Fh
0x140018d33  shr     rax, 1
0x140018d36  mov     rbx, r9
0x140018d39  mov     esi, edi
0x140018d3b  lea     r14, [r9+rax*2]
0x140018d3f  cmp     r9, r14
0x140018d42  jnb     short loc_140018D80
0x140018d44  nop     dword ptr [rax+00h]
0x140018d48  nop     dword ptr [rax+rax+00000000h]
0x140018d50  movzx   ecx, word ptr [rbx]; SourceCharacter
0x140018d53  call    cs:__imp_RtlUpcaseUnicodeChar
0x140018d5a  nop     dword ptr [rax+rax+00h]
0x140018d5f  imul    rcx, rsi, 25h ; '%'
0x140018d63  movzx   edx, ax
0x140018d66  add     rbx, 2
0x140018d6a  movzx   eax, dl
0x140018d6d  add     rcx, rax
0x140018d70  shr     rdx, 8
0x140018d74  imul    rsi, rcx, 25h ; '%'
0x140018d78  add     rsi, rdx
0x140018d7b  cmp     rbx, r14
0x140018d7e  jb      short loc_140018D50
0x140018d80  movzx   eax, word ptr [r13+0]
0x140018d85  mov     rbx, [r15+8]
0x140018d89  mov     r14, [rsp+2A0h+var_30]
0x140018d91  mov     r13, [rsp+2A0h+var_28]
0x140018d99  shr     rax, 1
0x140018d9c  mov     [r15+18h], rsi
0x140018da0  lea     rsi, [rbx+rax*2]
0x140018da4  cmp     rbx, rsi
0x140018da7  jnb     short loc_140018DE0
0x140018da9  nop     dword ptr [rax+00000000h]
0x140018db0  movzx   ecx, word ptr [rbx]; SourceCharacter
0x140018db3  call    cs:__imp_RtlUpcaseUnicodeChar
0x140018dba  nop     dword ptr [rax+rax+00h]
0x140018dbf  imul    rcx, rdi, 25h ; '%'
0x140018dc3  movzx   edx, ax
0x140018dc6  add     rbx, 2
0x140018dca  movzx   eax, dl
0x140018dcd  add     rcx, rax
0x140018dd0  shr     rdx, 8
0x140018dd4  imul    rdi, rcx, 25h ; '%'
0x140018dd8  add     rdi, rdx
0x140018ddb  cmp     rbx, rsi
0x140018dde  jb      short loc_140018DB0
0x140018de0  mov     rsi, [rsp+2A0h+arg_10]
0x140018de8  mov     [r15+20h], rdi
0x140018dec  mov     rdi, [rsp+2A0h+var_20]
0x140018df4  cmp     dword ptr [r15], 1
0x140018df8  jnz     short loc_140018E1B
0x140018dfa  mov     eax, r12d
0x140018dfd  mov     rcx, [rbp+1A0h+var_40]
0x140018e04  xor     rcx, rsp; StackCookie
0x140018e07  call    __security_check_cookie
0x140018e0c  add     rsp, 288h
0x140018e13  pop     r15
0x140018e15  pop     r12
0x140018e17  pop     rbx
0x140018e18  pop     rbp
0x140018e19  retn
0x140018e1b  lea     rcx, [rsp+2A0h+StringOut]; UnicodeString
0x140018e20  call    cs:__imp_RtlFreeUnicodeString
0x140018e27  nop     dword ptr [rax+rax+00h]
0x140018e2c  jmp     short loc_140018DFA
0x140018e2e  mov     ebx, 2
0x140018e33  mov     edx, 10h
0x140018e38  mov     ecx, 102h
0x140018e3d  mov     word ptr [rsp+2A0h+Address.S_un], bx
0x140018e42  mov     r8d, 5266534Ch
0x140018e48  call    cs:__imp_ExAllocatePool2
0x140018e4f  nop     dword ptr [rax+rax+00h]
0x140018e54  mov     [r15+8], rax
0x140018e58  test    rax, rax
0x140018e5b  jz      loc_14001931F
0x140018e61  movups  xmm0, xmmword ptr [rsp+2A0h+Address.S_un]
0x140018e66  mov     [r15], ebx
0x140018e69  movups  xmmword ptr [rax], xmm0
0x140018e6c  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+3]
0x140018e71  imul    rcx, rax, 25h ; '%'
0x140018e75  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+4]
0x140018e7a  add     rcx, rax
0x140018e7d  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+5]
0x140018e82  imul    rdx, rcx, 25h ; '%'
0x140018e86  add     rdx, rax
0x140018e89  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+6]
0x140018e8e  imul    rcx, rdx, 25h ; '%'
0x140018e92  add     rcx, rax
0x140018e95  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+7]
0x140018e9a  imul    rdx, rcx, 25h ; '%'
0x140018e9e  add     rdx, rax
0x140018ea1  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+8]
0x140018ea6  imul    rcx, rdx, 25h ; '%'
0x140018eaa  add     rcx, rax
0x140018ead  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+9]
0x140018eb2  imul    rdx, rcx, 25h ; '%'
0x140018eb6  add     rdx, rax
0x140018eb9  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+0Ah]
0x140018ebe  imul    rcx, rdx, 25h ; '%'
0x140018ec2  add     rcx, rax
0x140018ec5  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+0Bh]
0x140018eca  imul    rdx, rcx, 25h ; '%'
0x140018ece  add     rdx, rax
0x140018ed1  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+0Ch]
0x140018ed6  imul    rcx, rdx, 25h ; '%'
0x140018eda  add     rcx, rax
0x140018edd  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+0Dh]
0x140018ee2  imul    rdx, rcx, 25h ; '%'
0x140018ee6  add     rdx, rax
0x140018ee9  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+0Eh]
0x140018eee  imul    rcx, rdx, 25h ; '%'
0x140018ef2  add     rcx, rax
0x140018ef5  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+2]
0x140018efa  imul    rdx, rcx, 25h ; '%'
0x140018efe  mov     rcx, 3433B6F080FF8F35h
0x140018f08  imul    rax, rcx
0x140018f0c  mov     rcx, 8B7970C2A4EFB2A9h
0x140018f16  add     rdx, rax
0x140018f19  movzx   eax, byte ptr [rsp+2A0h+Address.S_un+1]
0x140018f1e  imul    rax, rcx
0x140018f22  mov     rcx, 288D4C21D6A4D26Dh
0x140018f2c  add     rdx, rax
0x140018f2f  movzx   eax, byte ptr [rsp+2A0h+Address.S_un]
0x140018f34  imul    rax, rcx
0x140018f38  movzx   ecx, byte ptr [rsp+2A0h+Address.S_un+0Fh]
0x140018f3d  add     rdx, rax
0x140018f40  mov     rax, 201911C49281756Fh
0x140018f4a  add     rax, rdx
0x140018f4d  add     rcx, rax
0x140018f50  xor     r12d, r12d
0x140018f53  mov     [r15+10h], rcx
0x140018f57  test    r12d, r12d
0x140018f5a  jns     loc_140018DF4
0x140018f60  jmp     loc_140018E1B
0x140018f65  mov     dword ptr [rsp+2A0h+var_260.u+4], r12d
0x140018f6a  cmp     r10d, 22h ; '"'
0x140018f6e  jb      loc_140018CBF
0x140018f74  mov     rcx, [rsp+2A0h+StringOut.Buffer]
0x140018f79  lea     rdx, RfspIpv6LiteralDomainName; String2
0x140018f80  add     r10, 0FFFFFFFFFFFFFFDEh
0x140018f84  mov     dword ptr [rsp+40h], 220022h
0x140018f8c  add     rcx, r10
0x140018f8f  mov     r8b, 1; CaseInSensitive
0x140018f92  mov     qword ptr [rsp+2A0h+var_260.u+8], rcx
0x140018f97  lea     rcx, [rsp+2A0h+var_260]; String1
0x140018f9c  call    cs:__imp_RtlEqualUnicodeString
0x140018fa3  nop     dword ptr [rax+rax+00h]
0x140018fa8  test    al, al
0x140018faa  jnz     short loc_140018FD8
0x140018fac  movzx   r10d, [rsp+2A0h+StringOut.Length]
0x140018fb2  jmp     loc_140018CBF
0x140018fb7  lea     rax, [r15+12h]
0x140018fbb  mov     r13, rax
0x140018fbe  test    rdx, rdx
0x140018fc1  jz      loc_140018D25
0x140018fc7  sub     rdx, r9
0x140018fca  sar     rdx, 1
0x140018fcd  add     dx, dx
0x140018fd0  mov     [rax], dx
0x140018fd3  jmp     loc_140018D29
0x140018fd8  movaps  xmm0, xmmword ptr [rsp+2A0h+StringOut.Length]
0x140018fdd  lea     rdx, [rsp+2A0h+var_260]; SourceString
0x140018fe2  movd    eax, xmm0
0x140018fe6  lea     rcx, [rsp+2A0h+Address]; DestinationString
0x140018feb  movdqa  xmmword ptr [rsp+2A0h+var_260.u], xmm0
0x140018ff1  sub     ax, 22h ; '"'
0x140018ff5  mov     word ptr [rsp+2A0h+var_260.u], ax
0x140018ffa  call    cs:__imp_RtlCopyUnicodeString
0x140019001  nop     dword ptr [rax+rax+00h]
0x140019006  movzx   edx, word ptr [rsp+2A0h+Address.S_un]
0x14001900b  movzx   r8d, r12w
0x14001900f  movzx   r9d, dx
0x140019013  shr     r9w, 1
0x140019017  cmp     r12w, r9w
0x14001901b  jnb     short loc_140019040
0x14001901d  mov     rax, qword ptr [rsp+2A0h+Address.S_un+8]
0x140019022  movzx   ecx, r8w
0x140019026  cmp     word ptr [rax+rcx*2], 2Dh ; '-'
0x14001902b  jz      loc_1400190C9
0x140019031  inc     r8w
0x140019035  cmp     r8w, r9w
0x140019039  jb      short loc_14001901D
0x14001903b  movzx   edx, word ptr [rsp+2A0h+Address.S_un]
0x140019040  movzx   r9d, dx
0x140019044  movzx   r8d, r12w
0x140019048  shr     r9w, 1
0x14001904c  mov     r10d, 25h ; '%'
0x140019052  cmp     r12w, r9w
0x140019056  jnb     short loc_140019077
0x140019058  mov     rax, qword ptr [rsp+2A0h+Address.S_un+8]
0x14001905d  movzx   ecx, r8w
0x140019061  cmp     word ptr [rax+rcx*2], 73h ; 's'
0x140019066  jz      short loc_1400190D4
0x140019068  inc     r8w
0x14001906c  cmp     r8w, r9w
0x140019070  jb      short loc_140019058
0x140019072  movzx   edx, word ptr [rsp+2A0h+Address.S_un]
0x140019077  shr     dx, 1
0x14001907a  movzx   r8d, r12w
0x14001907e  cmp     r12w, dx
0x140019082  jnb     short loc_14001909E
0x140019084  mov     rax, qword ptr [rsp+2A0h+Address.S_un+8]
0x140019089  movzx   ecx, r8w
0x14001908d  cmp     word ptr [rax+rcx*2], 53h ; 'S'
0x140019092  jz      short loc_1400190DB
0x140019094  inc     r8w
0x140019098  cmp     r8w, dx
0x14001909c  jb      short loc_140019084
0x14001909e  mov     rdx, r15
0x1400190a1  lea     rcx, [rsp+2A0h+Address]
0x1400190a6  call    RfspServerNameInitializeAsIpv6
0x1400190ab  cmp     eax, 0C0000016h
0x1400190b0  jz      loc_140018FAC
0x1400190b6  mov     r12d, eax
0x1400190b9  jmp     loc_140018F57
0x1400190be  xor     r12d, r12d
0x1400190c1  mov     [r15], r12d
0x1400190c4  jmp     loc_140018E1B
0x1400190c9  mov     word ptr [rax+rcx*2], 3Ah ; ':'
0x1400190cf  jmp     loc_140019031
0x1400190d4  mov     [rax+rcx*2], r10w
0x1400190d9  jmp     short loc_140019068
  ... truncated ...
```
