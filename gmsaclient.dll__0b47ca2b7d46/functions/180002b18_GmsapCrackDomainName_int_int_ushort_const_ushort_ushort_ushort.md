# GmsapCrackDomainName(int,int,ushort const *,ushort * *,ushort * *,ushort * *)

- ea: `0x180002b18`
- end: `0x180002e11`
- name: `?GmsapCrackDomainName@@YAJHHPEBGPEAPEAG11@Z`
- size: `761`
- prototype: `__int64 __fastcall(int, int, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800025b0`
- `0x180002e18`
- `0x180003200`
- `0x180003e84`
- `0x1800056d0`

## callees

- `0x180002b18`
- `0x180003160`
- `0x180006280`
- `0x1800062b0`
- `0x180008010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002bd2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180002bd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002d98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002dac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002dc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002d98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002dac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002dc0`
- `DNSAPI!DnsNameCompare_W` at `0x180002c00`
- `DNSAPI!DnsNameCompare_W` at `0x180002c00`
- `netutils!NetApiBufferFree` at `0x180002cc8`
- `netutils!NetApiBufferFree` at `0x180002d84`
- `netutils!NetApiBufferFree` at `0x180002cc8`
- `netutils!NetApiBufferFree` at `0x180002d84`

## pseudocode

```c
__int64 __fastcall GmsapCrackDomainName(
        int a1,
        int a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6)
{
  unsigned __int16 *v6; // r15
  unsigned __int16 *v7; // rsi
  unsigned __int16 *v8; // r14
  const unsigned __int16 *v11; // rbx
  int v12; // eax
  unsigned int v13; // edi
  BOOL v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  LPVOID Buffer; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v22; // [rsp+28h] [rbp-18h]
  unsigned __int16 *v23; // [rsp+30h] [rbp-10h]
  unsigned __int16 *v24; // [rsp+38h] [rbp-8h]
  int v25; // [rsp+88h] [rbp+48h]

  v25 = a2;
  v6 = 0;
  Buffer = 0;
  v7 = 0;
  v22 = 0;
  v8 = 0;
  v24 = 0;
  v23 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
    a2 = v25;
  }
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  v11 = a3;
  v12 = (a1 != 0) + 0x40000000;
  v13 = v12 | 0x200000;
  if ( !a2 )
    v13 = v12;
  if ( (unsigned int)_o__wcsicmp(SourceString.Buffer, a3) )
  {
    if ( stru_18000B5F8.Buffer )
    {
      if ( !a3 )
      {
LABEL_18:
        v13 |= 0x1000u;
        goto LABEL_19;
      }
      v14 = DnsNameCompare_W(stru_18000B5F8.Buffer, a3);
    }
    else
    {
      v14 = a3 == 0;
    }
    if ( v14 )
      goto LABEL_19;
    goto LABEL_18;
  }
LABEL_19:
  while ( 1 )
  {
    v15 = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, LPVOID *))qword_18000B5D0)(v11, v13, &Buffer);
    if ( (v15 & 0x80000000) == 0 )
      break;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v15);
    if ( (v13 & 1) != 0 )
      goto LABEL_42;
    v11 = a3;
    v13 |= 1u;
  }
  if ( !a4 || (v16 = GmsapDuplicateStringStrict(*(PCWSTR *)Buffer), v6 = v22, v15 = v16, v16 >= 0) )
  {
    if ( !a6 || (v17 = GmsapDuplicateStringStrict(*((PCWSTR *)Buffer + 5)), v8 = v23, v15 = v17, v17 >= 0) )
    {
      if ( a5 )
      {
        NetApiBufferFree(Buffer);
        Buffer = 0;
        v18 = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, LPVOID *))qword_18000B5D0)(
                a3,
                v13 & 0x3FFFFFFE | 0x80000000,
                &Buffer);
        v15 = v18;
        if ( v18 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              54,
              &WPP_70b8577d707437755865c965214ce19a_Traceguids,
              (unsigned int)v18);
          goto LABEL_42;
        }
        v19 = GmsapDuplicateStringStrict(*((PCWSTR *)Buffer + 5));
        v7 = v24;
        v15 = v19;
        if ( v19 < 0 )
          goto LABEL_42;
      }
      if ( a4 )
      {
        *a4 = v6;
        v6 = 0;
      }
      if ( a6 )
      {
        *a6 = v8;
        v8 = 0;
      }
      if ( a5 )
      {
        *a5 = v7;
        v7 = 0;
      }
      v15 = 0;
    }
  }
LABEL_42:
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( v6 )
    LocalFree(v6);
  if ( v7 )
    LocalFree(v7);
  if ( v8 )
    LocalFree(v8);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x180002b18  mov     rax, rsp
0x180002b1b  mov     [rax+8], rbx
0x180002b1f  mov     [rax+20h], r9
0x180002b23  mov     [rax+18h], r8
0x180002b27  mov     [rax+10h], edx
0x180002b2a  push    rbp
0x180002b2b  push    rsi
0x180002b2c  push    rdi
0x180002b2d  push    r12
0x180002b2f  push    r13
0x180002b31  push    r14
0x180002b33  push    r15
0x180002b35  mov     rbp, rsp
0x180002b38  sub     rsp, 40h
0x180002b3c  xor     r15d, r15d
0x180002b3f  mov     [rbp+Buffer], 0
0x180002b47  xor     esi, esi
0x180002b49  mov     [rbp+var_18], r15
0x180002b4d  xor     r14d, r14d
0x180002b50  mov     [rbp+var_8], rsi
0x180002b54  mov     [rbp+var_10], r14
0x180002b58  mov     rbx, r9
0x180002b5b  mov     edi, ecx
0x180002b5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b64  lea     rax, WPP_GLOBAL_Control
0x180002b6b  cmp     rcx, rax
0x180002b6e  jz      short loc_180002B8C
0x180002b70  test    byte ptr [rcx+1Ch], 8
0x180002b74  jz      short loc_180002B8C
0x180002b76  mov     rcx, [rcx+10h]
0x180002b7a  lea     edx, [rsi+34h]
0x180002b7d  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180002b84  call    WPP_SF_
0x180002b89  mov     edx, [rbp+arg_8]
0x180002b8c  test    rbx, rbx
0x180002b8f  jz      short loc_180002B94
0x180002b91  mov     [rbx], rsi
0x180002b94  mov     r13, [rbp+arg_20]
0x180002b98  test    r13, r13
0x180002b9b  jz      short loc_180002BA1
0x180002b9d  mov     [r13+0], rsi
0x180002ba1  mov     r12, [rbp+arg_28]
0x180002ba5  test    r12, r12
0x180002ba8  jz      short loc_180002BAE
0x180002baa  mov     [r12], rsi
0x180002bae  mov     rbx, [rbp+pName2]
0x180002bb2  neg     edi
0x180002bb4  mov     rcx, cs:SourceString.Buffer
0x180002bbb  sbb     eax, eax
0x180002bbd  neg     eax
0x180002bbf  add     eax, 40000000h
0x180002bc4  mov     edi, eax
0x180002bc6  bts     edi, 15h
0x180002bca  test    edx, edx
0x180002bcc  mov     rdx, rbx
0x180002bcf  cmovz   edi, eax
0x180002bd2  call    cs:__imp__o__wcsicmp
0x180002bd9  nop     dword ptr [rax+rax+00h]
0x180002bde  test    eax, eax
0x180002be0  jz      short loc_180002C14
0x180002be2  mov     rcx, cs:stru_18000B5F8.Buffer; pName1
0x180002be9  test    rcx, rcx
0x180002bec  jnz     short loc_180002BF8
0x180002bee  xor     eax, eax
0x180002bf0  test    rbx, rbx
0x180002bf3  setz    al
0x180002bf6  jmp     short loc_180002C0C
0x180002bf8  test    rbx, rbx
0x180002bfb  jz      short loc_180002C10
0x180002bfd  mov     rdx, rbx; pName2
0x180002c00  call    cs:__imp_DnsNameCompare_W
0x180002c07  nop     dword ptr [rax+rax+00h]
0x180002c0c  test    eax, eax
0x180002c0e  jnz     short loc_180002C14
0x180002c10  bts     edi, 0Ch
0x180002c14  mov     rax, cs:qword_18000B5D0
0x180002c1b  lea     r8, [rbp+Buffer]
0x180002c1f  mov     edx, edi
0x180002c21  mov     rcx, rbx
0x180002c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c29  mov     ebx, eax
0x180002c2b  test    eax, eax
0x180002c2d  jns     short loc_180002C73
0x180002c2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c36  lea     rax, WPP_GLOBAL_Control
0x180002c3d  cmp     rcx, rax
0x180002c40  jz      short loc_180002C60
0x180002c42  test    byte ptr [rcx+1Ch], 4
0x180002c46  jz      short loc_180002C60
0x180002c48  mov     rcx, [rcx+10h]
0x180002c4c  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180002c53  mov     edx, 35h ; '5'
0x180002c58  mov     r9d, ebx
0x180002c5b  call    WPP_SF_D
0x180002c60  test    dil, 1
0x180002c64  jnz     loc_180002D74
0x180002c6a  mov     rbx, [rbp+pName2]
0x180002c6e  or      edi, 1
0x180002c71  jmp     short loc_180002C14
0x180002c73  cmp     [rbp+arg_18], rsi
0x180002c77  jz      short loc_180002C97
0x180002c79  mov     rcx, [rbp+Buffer]
0x180002c7d  lea     rdx, [rbp+var_18]
0x180002c81  mov     rcx, [rcx]; SourceString
0x180002c84  call    GmsapDuplicateStringStrict
0x180002c89  mov     r15, [rbp+var_18]
0x180002c8d  mov     ebx, eax
0x180002c8f  test    eax, eax
0x180002c91  js      loc_180002D74
0x180002c97  test    r12, r12
0x180002c9a  jz      short loc_180002CBB
0x180002c9c  mov     rcx, [rbp+Buffer]
0x180002ca0  lea     rdx, [rbp+var_10]
0x180002ca4  mov     rcx, [rcx+28h]; SourceString
0x180002ca8  call    GmsapDuplicateStringStrict
0x180002cad  mov     r14, [rbp+var_10]
0x180002cb1  mov     ebx, eax
0x180002cb3  test    eax, eax
0x180002cb5  js      loc_180002D74
0x180002cbb  test    r13, r13
0x180002cbe  jz      loc_180002D4C
0x180002cc4  mov     rcx, [rbp+Buffer]; Buffer
0x180002cc8  call    cs:__imp_NetApiBufferFree
0x180002ccf  nop     dword ptr [rax+rax+00h]
0x180002cd4  mov     rcx, [rbp+pName2]
0x180002cd8  lea     r8, [rbp+Buffer]
0x180002cdc  mov     rax, cs:qword_18000B5D0
0x180002ce3  and     edi, 3FFFFFFEh
0x180002ce9  bts     edi, 1Fh
0x180002ced  mov     [rbp+Buffer], rsi
0x180002cf1  mov     edx, edi
0x180002cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cf8  mov     ebx, eax
0x180002cfa  test    eax, eax
0x180002cfc  jns     short loc_180002D31
0x180002cfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d05  lea     rdi, WPP_GLOBAL_Control
0x180002d0c  cmp     rcx, rdi
0x180002d0f  jz      short loc_180002D7B
0x180002d11  test    byte ptr [rcx+1Ch], 4
0x180002d15  jz      short loc_180002D7B
0x180002d17  mov     rcx, [rcx+10h]
0x180002d1b  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180002d22  mov     edx, 36h ; '6'
0x180002d27  mov     r9d, eax
0x180002d2a  call    WPP_SF_D
0x180002d2f  jmp     short loc_180002D7B
0x180002d31  mov     rcx, [rbp+Buffer]
0x180002d35  lea     rdx, [rbp+var_8]
0x180002d39  mov     rcx, [rcx+28h]; SourceString
0x180002d3d  call    GmsapDuplicateStringStrict
0x180002d42  mov     rsi, [rbp+var_8]
0x180002d46  mov     ebx, eax
0x180002d48  test    eax, eax
0x180002d4a  js      short loc_180002D74
0x180002d4c  mov     rax, [rbp+arg_18]
0x180002d50  test    rax, rax
0x180002d53  jz      short loc_180002D5B
0x180002d55  mov     [rax], r15
0x180002d58  xor     r15d, r15d
0x180002d5b  test    r12, r12
0x180002d5e  jz      short loc_180002D67
0x180002d60  mov     [r12], r14
0x180002d64  xor     r14d, r14d
0x180002d67  test    r13, r13
0x180002d6a  jz      short loc_180002D72
0x180002d6c  mov     [r13+0], rsi
0x180002d70  xor     esi, esi
0x180002d72  xor     ebx, ebx
0x180002d74  lea     rdi, WPP_GLOBAL_Control
0x180002d7b  mov     rcx, [rbp+Buffer]; Buffer
0x180002d7f  test    rcx, rcx
0x180002d82  jz      short loc_180002D90
0x180002d84  call    cs:__imp_NetApiBufferFree
0x180002d8b  nop     dword ptr [rax+rax+00h]
0x180002d90  test    r15, r15
0x180002d93  jz      short loc_180002DA4
0x180002d95  mov     rcx, r15; hMem
0x180002d98  call    cs:__imp_LocalFree
0x180002d9f  nop     dword ptr [rax+rax+00h]
0x180002da4  test    rsi, rsi
0x180002da7  jz      short loc_180002DB8
0x180002da9  mov     rcx, rsi; hMem
0x180002dac  call    cs:__imp_LocalFree
0x180002db3  nop     dword ptr [rax+rax+00h]
0x180002db8  test    r14, r14
0x180002dbb  jz      short loc_180002DCC
0x180002dbd  mov     rcx, r14; hMem
0x180002dc0  call    cs:__imp_LocalFree
0x180002dc7  nop     dword ptr [rax+rax+00h]
0x180002dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180002dd3  cmp     rcx, rdi
0x180002dd6  jz      short loc_180002DF6
0x180002dd8  test    byte ptr [rcx+1Ch], 8
0x180002ddc  jz      short loc_180002DF6
0x180002dde  mov     rcx, [rcx+10h]
0x180002de2  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180002de9  mov     edx, 37h ; '7'
0x180002dee  mov     r9d, ebx
0x180002df1  call    WPP_SF_D
0x180002df6  mov     eax, ebx
0x180002df8  mov     rbx, [rsp+40h+arg_0]
0x180002e00  add     rsp, 40h
0x180002e04  pop     r15
0x180002e06  pop     r14
0x180002e08  pop     r13
0x180002e0a  pop     r12
0x180002e0c  pop     rdi
0x180002e0d  pop     rsi
0x180002e0e  pop     rbp
0x180002e0f  retn
```
