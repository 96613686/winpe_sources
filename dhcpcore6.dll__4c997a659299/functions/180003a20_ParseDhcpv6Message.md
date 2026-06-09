# ParseDhcpv6Message

- ea: `0x180003a20`
- end: `0x180003cb7`
- name: `ParseDhcpv6Message`
- size: `663`
- prototype: `__int64 __fastcall(__int64, u_short *, unsigned int, int, unsigned __int16 *, __int64, __int64, int, __int64 *, __int64, int, _OWORD *)`
- caller_count: `8`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800034c8`
- `0x18002211c`
- `0x1800225c8`
- `0x180022b80`
- `0x180023344`
- `0x180023dc0`
- `0x18002458c`
- `0x180025094`

## callees

- `0x180001d8c`
- `0x180003a20`
- `0x180003cc0`
- `0x180004b30`
- `0x1800337d0`
- `0x180033900`
- `0x180033970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003ba2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003ba2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003c37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003c37`

## pseudocode

```c
__int64 __fastcall ParseDhcpv6Message(
        __int64 a1,
        u_short *a2,
        unsigned int a3,
        int a4,
        unsigned __int16 *a5,
        __int64 a6,
        __int64 a7,
        int a8,
        __int64 *a9,
        __int64 a10,
        int a11,
        _OWORD *a12)
{
  __int64 v15; // rdi
  unsigned int v16; // ebx
  unsigned int v17; // esi
  int v18; // r14d
  __int64 v20; // rdx
  _OWORD v21[5]; // [rsp+60h] [rbp-58h] BYREF

  v15 = a1;
  if ( !a6 || !a2 || !a3 || !a5 )
    goto LABEL_2;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 35, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *(_QWORD *)(a1 + 56));
  if ( a3 < 4 )
    goto LABEL_2;
  a1 = *(u_short *)((char *)a2 + 1) - (unsigned int)*a5;
  if ( !(_DWORD)a1 )
    a1 = *((unsigned __int8 *)a2 + 3) - (unsigned int)*((unsigned __int8 *)a5 + 2);
  if ( (_DWORD)a1 )
  {
    if ( (xmmword_1800423E0 & 2) == 0 )
      goto LABEL_2;
    v20 = 36;
    goto LABEL_28;
  }
  v17 = *(unsigned __int8 *)a2;
  v18 = 1;
  if ( v17 == 7 )
    goto LABEL_17;
  if ( v17 != 2 )
  {
    if ( (xmmword_1800423E0 & 2) == 0 )
      goto LABEL_2;
    v20 = 38;
    goto LABEL_28;
  }
  if ( a4 != 1 )
  {
    if ( (xmmword_1800423E0 & 2) == 0 )
    {
LABEL_2:
      v16 = 87;
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_SD(1025, 41, (unsigned int)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *(_QWORD *)(v15 + 56), 87);
      if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 4) != 0 )
        McTemplateU0qq_EtwEventWriteTransfer(a1, ErrorInParsing, *(unsigned int *)(v15 + 48), 87);
      TraceLogErrorv6(v15, 87, 41);
      return v16;
    }
    v20 = 37;
LABEL_28:
    WPP_SF_(1025, v20, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
    goto LABEL_2;
  }
LABEL_17:
  if ( a7 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)(v15 + 608));
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_S(1028, 39, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *(_QWORD *)(v15 + 56));
  }
  else
  {
    v18 = 0;
  }
  v21[0] = *a12;
  v16 = ParseDhcpv6Options(v15, a2 + 2, a3 - 4, v17, a8, a7, a9, a10, a11, v21, a6);
  if ( v18 )
  {
    ReleaseSRWLockExclusive((PSRWLOCK)(v15 + 608));
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_S(1028, 40, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *(_QWORD *)(v15 + 56));
  }
  if ( v16 )
    goto LABEL_2;
  return v16;
}

```

## disassembly

```asm
0x180003a20  push    rbx
0x180003a22  push    rbp
0x180003a23  push    rsi
0x180003a24  push    rdi
0x180003a25  push    r12
0x180003a27  push    r13
0x180003a29  push    r14
0x180003a2b  push    r15
0x180003a2d  sub     rsp, 78h
0x180003a31  mov     r13, [rsp+0B8h+arg_28]
0x180003a39  mov     r15d, r9d
0x180003a3c  mov     ebp, r8d
0x180003a3f  mov     rbx, rdx
0x180003a42  mov     rdi, rcx
0x180003a45  mov     r12d, 401h
0x180003a4b  test    r13, r13
0x180003a4e  jnz     short loc_180003A87
0x180003a50  mov     ebx, 57h ; 'W'
0x180003a55  test    byte ptr cs:xmmword_1800423E0, 2
0x180003a5c  lea     esi, [rbx-2Eh]
0x180003a5f  jnz     loc_180003C7A
0x180003a65  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 4
0x180003a6c  jnz     loc_180003C9C
0x180003a72  mov     r8d, esi
0x180003a75  mov     edx, 57h ; 'W'
0x180003a7a  mov     rcx, rdi
0x180003a7d  call    TraceLogErrorv6
0x180003a82  jmp     loc_180003B8B
0x180003a87  test    rbx, rbx
0x180003a8a  jz      short loc_180003A50
0x180003a8c  test    ebp, ebp
0x180003a8e  jz      short loc_180003A50
0x180003a90  mov     rsi, [rsp+0B8h+arg_20]
0x180003a98  test    rsi, rsi
0x180003a9b  jz      short loc_180003A50
0x180003a9d  test    byte ptr cs:xmmword_1800423E0, 10h
0x180003aa4  jz      short loc_180003AC0
0x180003aa6  mov     r9, [rdi+38h]
0x180003aaa  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180003ab1  mov     edx, 23h ; '#'
0x180003ab6  mov     ecx, 404h
0x180003abb  call    WPP_SF_S
0x180003ac0  cmp     ebp, 4
0x180003ac3  jb      short loc_180003A50
0x180003ac5  movzx   ecx, word ptr [rbx+1]
0x180003ac9  movzx   eax, word ptr [rsi]
0x180003acc  sub     ecx, eax
0x180003ace  jnz     short loc_180003ADA
0x180003ad0  movzx   ecx, byte ptr [rbx+3]
0x180003ad4  movzx   eax, byte ptr [rsi+2]
0x180003ad8  sub     ecx, eax
0x180003ada  test    ecx, ecx
0x180003adc  jnz     loc_180003C0C
0x180003ae2  movzx   esi, byte ptr [rbx]
0x180003ae5  lea     r14d, [rcx+1]
0x180003ae9  cmp     esi, 7
0x180003aec  jnz     loc_180003BDA
0x180003af2  mov     r15, [rsp+0B8h+arg_30]
0x180003afa  lea     r12d, [rbp-4]
0x180003afe  lea     rbp, [rdi+260h]
0x180003b05  test    r15, r15
0x180003b08  jnz     loc_180003B9F
0x180003b0e  xor     r14d, r14d
0x180003b11  mov     rax, [rsp+0B8h+arg_58]
0x180003b19  lea     rdx, [rbx+4]
0x180003b1d  mov     [rsp+0B8h+var_68], r13
0x180003b22  mov     r9d, esi
0x180003b25  mov     r8d, r12d
0x180003b28  mov     rcx, rdi
0x180003b2b  movaps  xmm0, xmmword ptr [rax]
0x180003b2e  lea     rax, [rsp+0B8h+var_58]
0x180003b33  mov     [rsp+0B8h+var_70], rax
0x180003b38  mov     eax, [rsp+0B8h+arg_50]
0x180003b3f  mov     [rsp+0B8h+var_78], eax
0x180003b43  mov     rax, [rsp+0B8h+arg_48]
0x180003b4b  mov     [rsp+0B8h+var_80], rax
0x180003b50  mov     rax, [rsp+0B8h+arg_40]
0x180003b58  mov     [rsp+0B8h+var_88], rax
0x180003b5d  mov     eax, [rsp+0B8h+arg_38]
0x180003b64  mov     [rsp+0B8h+var_90], r15
0x180003b69  mov     [rsp+0B8h+var_98], eax
0x180003b6d  movdqa  [rsp+0B8h+var_58], xmm0
0x180003b73  call    ParseDhcpv6Options
0x180003b78  mov     ebx, eax
0x180003b7a  test    r14d, r14d
0x180003b7d  jnz     loc_180003C34
0x180003b83  test    ebx, ebx
0x180003b85  jnz     loc_180003C6F
0x180003b8b  mov     eax, ebx
0x180003b8d  add     rsp, 78h
0x180003b91  pop     r15
0x180003b93  pop     r14
0x180003b95  pop     r13
0x180003b97  pop     r12
0x180003b99  pop     rdi
0x180003b9a  pop     rsi
0x180003b9b  pop     rbp
0x180003b9c  pop     rbx
0x180003b9d  retn
0x180003b9f  mov     rcx, rbp; SRWLock
0x180003ba2  call    cs:__imp_AcquireSRWLockExclusive
0x180003ba9  nop     dword ptr [rax+rax+00h]
0x180003bae  test    byte ptr cs:xmmword_1800423E0, 10h
0x180003bb5  jz      loc_180003B11
0x180003bbb  mov     r9, [rdi+38h]
0x180003bbf  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180003bc6  mov     edx, 27h ; '''
0x180003bcb  mov     ecx, 404h
0x180003bd0  call    WPP_SF_S
0x180003bd5  jmp     loc_180003B11
0x180003bda  cmp     esi, 2
0x180003bdd  jnz     short loc_180003C20
0x180003bdf  cmp     r15d, r14d
0x180003be2  jz      loc_180003AF2
0x180003be8  test    byte ptr cs:xmmword_1800423E0, sil
0x180003bef  jz      loc_180003A50
0x180003bf5  lea     edx, [rsi+23h]
0x180003bf8  mov     ecx, r12d
0x180003bfb  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180003c02  call    WPP_SF_
0x180003c07  jmp     loc_180003A50
0x180003c0c  test    byte ptr cs:xmmword_1800423E0, 2
0x180003c13  jz      loc_180003A50
0x180003c19  mov     edx, 24h ; '$'
0x180003c1e  jmp     short loc_180003BF8
0x180003c20  test    byte ptr cs:xmmword_1800423E0, 2
0x180003c27  jz      loc_180003A50
0x180003c2d  mov     edx, 26h ; '&'
0x180003c32  jmp     short loc_180003BF8
0x180003c34  mov     rcx, rbp; SRWLock
0x180003c37  call    cs:__imp_ReleaseSRWLockExclusive
0x180003c3e  nop     dword ptr [rax+rax+00h]
0x180003c43  test    byte ptr cs:xmmword_1800423E0, 10h
0x180003c4a  jz      loc_180003B83
0x180003c50  mov     r9, [rdi+38h]
0x180003c54  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180003c5b  mov     edx, 28h ; '('
0x180003c60  mov     ecx, 404h
0x180003c65  call    WPP_SF_S
0x180003c6a  jmp     loc_180003B83
0x180003c6f  mov     r12d, 401h
0x180003c75  jmp     loc_180003A50
0x180003c7a  mov     r9, [rdi+38h]
0x180003c7e  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180003c85  mov     edx, esi
0x180003c87  mov     [rsp+0B8h+var_98], 57h ; 'W'
0x180003c8f  mov     ecx, r12d
0x180003c92  call    WPP_SF_SD
0x180003c97  jmp     loc_180003A65
0x180003c9c  mov     r8d, [rdi+30h]
0x180003ca0  lea     rdx, ErrorInParsing
0x180003ca7  mov     r9d, 57h ; 'W'
0x180003cad  call    McTemplateU0qq_EtwEventWriteTransfer
0x180003cb2  jmp     loc_180003A72
```
