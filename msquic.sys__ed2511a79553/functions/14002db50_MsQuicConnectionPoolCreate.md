# MsQuicConnectionPoolCreate

- ea: `0x14002db50`
- end: `0x14002de1b`
- name: `MsQuicConnectionPoolCreate`
- size: `715`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14002db50`
- `0x14002de24`
- `0x14002df00`
- `0x140039e18`
- `0x14003c8e0`
- `0x14003ce00`
- `0x14003e928`
- `0x14003eca4`
- `0x140040c2c`

## import_xrefs

- `ntoskrnl!strnlen` at `0x14002dc40`
- `ntoskrnl!strnlen` at `0x14002dc40`

## string_xrefs

- `0x14002ddb5`: `Connection Pool Config`
- `0x14002dc20`: `Connection Pool SecurityConfig`
- `0x14002dc8d`: `Connection Pool CIBIR config`

## pseudocode

```c
__int64 __fastcall MsQuicConnectionPoolCreate(__int64 a1, __int64 a2)
{
  void *v2; // rbx
  __int64 v3; // rdi
  unsigned int v4; // eax
  int StartingLocalAddress; // ebx
  const char *v6; // r9
  size_t v7; // r8
  __int16 v8; // ax
  __int128 *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // ecx
  __int64 v13; // r8
  int v15; // [rsp+20h] [rbp-50h] BYREF
  __int128 v16; // [rsp+28h] [rbp-48h] BYREF
  __int64 v17; // [rsp+38h] [rbp-38h]
  int v18; // [rsp+40h] [rbp-30h]
  __int128 v19; // [rsp+48h] [rbp-28h] BYREF
  __int64 v20; // [rsp+58h] [rbp-18h]
  int v21; // [rsp+60h] [rbp-10h]

  v2 = (void *)a2;
  v3 = a1;
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, a2, 29, 0);
  if ( !v3 || !v2 )
  {
    StartingLocalAddress = -1073741811;
    if ( (Microsoft_QuicEnableBits & 4) == 0 )
      goto LABEL_45;
    v6 = "Connection Pool Parameter";
    goto LABEL_43;
  }
  if ( !*(_QWORD *)v3
    || (a1 = *(_QWORD *)(v3 + 8)) == 0
    || !*(_WORD *)(v3 + 52)
    || !*(_QWORD *)(v3 + 16)
    || !*(_QWORD *)(v3 + 32)
    || !*(_WORD *)(v3 + 50)
    || (v4 = *(unsigned __int16 *)(v3 + 48), v4 > 0x17)
    || (a2 = 8388613, !_bittest((const int *)&a2, v4)) )
  {
    StartingLocalAddress = -1073741811;
    if ( (Microsoft_QuicEnableBits & 4) == 0 )
      goto LABEL_45;
    v6 = "Connection Pool Config";
    goto LABEL_43;
  }
  if ( !*(_QWORD *)(a1 + 48) )
  {
    StartingLocalAddress = -1073741811;
    if ( (Microsoft_QuicEnableBits & 4) == 0 )
      goto LABEL_45;
    v6 = "Connection Pool SecurityConfig";
LABEL_43:
    v7 = 3221225485LL;
LABEL_44:
    McTemplateU0qs_EtwWriteTransfer(a1, a2, v7, v6);
    goto LABEL_45;
  }
  if ( *(_QWORD *)(v3 + 56) )
  {
    if ( *(_BYTE *)(v3 + 64) )
      goto LABEL_18;
LABEL_22:
    StartingLocalAddress = -1073741811;
    if ( (Microsoft_QuicEnableBits & 4) == 0 )
      goto LABEL_45;
    v6 = "Connection Pool CIBIR config";
    goto LABEL_43;
  }
  if ( *(_BYTE *)(v3 + 64) )
    goto LABEL_22;
LABEL_18:
  v7 = strnlen(*(const char **)(v3 + 32), 0x10000u);
  if ( v7 == 0x10000 )
  {
    StartingLocalAddress = -1073741811;
    if ( (Microsoft_QuicEnableBits & 4) == 0 )
      goto LABEL_45;
    v6 = "Connection Pool ServerName too long";
    goto LABEL_44;
  }
  memset(v2, 0, 8LL * *(unsigned __int16 *)(v3 + 52));
  v17 = 0;
  v18 = 0;
  v8 = *(_WORD *)(v3 + 48);
  v16 = 0;
  LOWORD(v16) = v8;
  v9 = *(__int128 **)(v3 + 40);
  if ( v9 )
  {
    v16 = *v9;
    v17 = *((_QWORD *)v9 + 2);
    v18 = *((_DWORD *)v9 + 6);
  }
  else
  {
    StartingLocalAddress = CxPlatDataPathResolveAddress(qword_14005C590, *(_QWORD *)(v3 + 32), &v16);
    if ( StartingLocalAddress < 0 )
      goto LABEL_45;
  }
  v10 = *(_QWORD *)(v3 + 8);
  WORD1(v16) = __ROR2__(*(_WORD *)(v3 + 50), 8);
  v11 = *(_QWORD *)(v10 + 96);
  v12 = 8 * ((unsigned __int8)byte_14005C53C >> 7);
  if ( (v11 & 0x1000000000000LL) != 0 )
  {
    v12 = 0;
    if ( *(char *)(v10 + 236) < 0 )
      v12 = 8;
  }
  v13 = v12 | 0x10;
  if ( (byte_14005C53D & 1) == 0 )
    v13 = v12;
  if ( (v11 & 0x2000000000000LL) != 0 )
  {
    if ( (*(_BYTE *)(v10 + 237) & 1) != 0 )
      v13 = (unsigned int)v13 | 0x10;
    else
      v13 = (unsigned int)v13 & 0xFFFFFFEF;
  }
  v20 = 0;
  v21 = 0;
  v19 = 0;
  StartingLocalAddress = QuicConnPoolGetStartingLocalAddress(&v16, &v19, v13);
  if ( StartingLocalAddress >= 0 )
  {
    v15 = 0;
    StartingLocalAddress = QuicConnPoolGetInterfaceIndexForLocalAddress(&v19, &v15);
    if ( StartingLocalAddress >= 0 )
      StartingLocalAddress = -1073741637;
  }
LABEL_45:
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer(a1, QuicApiExitStatus, (unsigned int)StartingLocalAddress);
  return (unsigned int)StartingLocalAddress;
}

```

## disassembly

```asm
0x14002db50  mov     [rsp-18h+arg_10], rbx
0x14002db55  mov     [rsp-18h+arg_18], rdi
0x14002db5a  push    rbp
0x14002db5b  push    r14
0x14002db5d  push    r15
0x14002db5f  mov     rbp, rsp
0x14002db62  sub     rsp, 70h
0x14002db66  mov     rax, cs:__security_cookie
0x14002db6d  xor     rax, rsp
0x14002db70  mov     [rbp+var_8], rax
0x14002db74  mov     r15d, 8
0x14002db7a  mov     rbx, rdx
0x14002db7d  test    cs:Microsoft_QuicEnableBits, r15b
0x14002db84  mov     rdi, rcx
0x14002db87  jz      short loc_14002DB95
0x14002db89  xor     r9d, r9d
0x14002db8c  lea     r8d, [r15+15h]
0x14002db90  call    McTemplateU0qp_EtwWriteTransfer
0x14002db95  xor     r14d, r14d
0x14002db98  test    rdi, rdi
0x14002db9b  jz      loc_14002DDBE
0x14002dba1  test    rbx, rbx
0x14002dba4  jz      loc_14002DDBE
0x14002dbaa  cmp     [rdi], r14
0x14002dbad  jz      loc_14002DDA7
0x14002dbb3  mov     rcx, [rdi+8]
0x14002dbb7  test    rcx, rcx
0x14002dbba  jz      loc_14002DDA7
0x14002dbc0  cmp     [rdi+34h], r14w
0x14002dbc5  jz      loc_14002DDA7
0x14002dbcb  cmp     [rdi+10h], r14
0x14002dbcf  jz      loc_14002DDA7
0x14002dbd5  mov     r8, [rdi+20h]
0x14002dbd9  test    r8, r8
0x14002dbdc  jz      loc_14002DDA7
0x14002dbe2  cmp     [rdi+32h], r14w
0x14002dbe7  jz      loc_14002DDA7
0x14002dbed  movzx   eax, word ptr [rdi+30h]
0x14002dbf1  cmp     eax, 17h
0x14002dbf4  ja      loc_14002DDA7
0x14002dbfa  mov     edx, 800005h
0x14002dbff  bt      edx, eax
0x14002dc02  jnb     loc_14002DDA7
0x14002dc08  cmp     [rcx+30h], r14
0x14002dc0c  jnz     short loc_14002DC2C
0x14002dc0e  test    cs:Microsoft_QuicEnableBits, 4
0x14002dc15  mov     ebx, 0C000000Dh
0x14002dc1a  jz      loc_14002DDDE
0x14002dc20  lea     r9, aConnectionPool_2; "Connection Pool SecurityConfig"
0x14002dc27  jmp     loc_14002DDD3
0x14002dc2c  cmp     [rdi+38h], r14
0x14002dc30  jz      short loc_14002DC75
0x14002dc32  cmp     [rdi+40h], r14b
0x14002dc36  jz      short loc_14002DC7B
0x14002dc38  mov     edx, 10000h; MaxCount
0x14002dc3d  mov     rcx, r8; Str
0x14002dc40  call    cs:__imp_strnlen
0x14002dc47  nop     dword ptr [rax+rax+00h]
0x14002dc4c  mov     r8, rax
0x14002dc4f  cmp     rax, 10000h
0x14002dc55  jnz     short loc_14002DC99
0x14002dc57  test    cs:Microsoft_QuicEnableBits, 4
0x14002dc5e  mov     ebx, 0C000000Dh
0x14002dc63  jz      loc_14002DDDE
0x14002dc69  lea     r9, aConnectionPool_3; "Connection Pool ServerName too long"
0x14002dc70  jmp     loc_14002DDD9
0x14002dc75  cmp     [rdi+40h], r14b
0x14002dc79  jz      short loc_14002DC38
0x14002dc7b  test    cs:Microsoft_QuicEnableBits, 4
0x14002dc82  mov     ebx, 0C000000Dh
0x14002dc87  jz      loc_14002DDDE
0x14002dc8d  lea     r9, aConnectionPool_4; "Connection Pool CIBIR config"
0x14002dc94  jmp     loc_14002DDD3
0x14002dc99  movzx   r8d, word ptr [rdi+34h]
0x14002dc9e  xor     edx, edx; Val
0x14002dca0  shl     r8, 3; Size
0x14002dca4  mov     rcx, rbx; void *
0x14002dca7  call    memset
0x14002dcac  xor     eax, eax
0x14002dcae  xorps   xmm0, xmm0
0x14002dcb1  mov     [rbp+var_38], rax
0x14002dcb5  mov     [rbp+var_30], eax
0x14002dcb8  movzx   eax, word ptr [rdi+30h]
0x14002dcbc  movups  [rbp+var_48], xmm0
0x14002dcc0  mov     word ptr [rbp+var_48], ax
0x14002dcc4  mov     rax, [rdi+28h]
0x14002dcc8  test    rax, rax
0x14002dccb  jz      short loc_14002DCE6
0x14002dccd  movups  xmm0, xmmword ptr [rax]
0x14002dcd0  movups  [rbp+var_48], xmm0
0x14002dcd4  movsd   xmm1, qword ptr [rax+10h]
0x14002dcd9  movsd   [rbp+var_38], xmm1
0x14002dcde  mov     eax, [rax+18h]
0x14002dce1  mov     [rbp+var_30], eax
0x14002dce4  jmp     short loc_14002DD04
0x14002dce6  mov     rdx, [rdi+20h]
0x14002dcea  lea     r8, [rbp+var_48]
0x14002dcee  mov     rcx, cs:qword_14005C590
0x14002dcf5  call    CxPlatDataPathResolveAddress
0x14002dcfa  mov     ebx, eax
0x14002dcfc  test    eax, eax
0x14002dcfe  js      loc_14002DDDE
0x14002dd04  movzx   eax, word ptr [rdi+32h]
0x14002dd08  mov     rdx, [rdi+8]
0x14002dd0c  movzx   ecx, cs:byte_14005C53C
0x14002dd13  ror     ax, 8
0x14002dd17  shr     ecx, 7
0x14002dd1a  mov     word ptr [rbp+var_48+2], ax
0x14002dd1e  mov     r9, [rdx+60h]
0x14002dd22  shl     ecx, 3
0x14002dd25  bt      r9, 30h ; '0'
0x14002dd2a  jnb     short loc_14002DD3A
0x14002dd2c  cmp     [rdx+0ECh], r14b
0x14002dd33  mov     ecx, r14d
0x14002dd36  cmovl   ecx, r15d
0x14002dd3a  mov     r8d, ecx
0x14002dd3d  or      r8d, 10h
0x14002dd41  test    cs:byte_14005C53D, 1
0x14002dd48  cmovz   r8d, ecx
0x14002dd4c  bt      r9, 31h ; '1'
0x14002dd51  jnb     short loc_14002DD66
0x14002dd53  test    byte ptr [rdx+0EDh], 1
0x14002dd5a  jz      short loc_14002DD62
0x14002dd5c  or      r8d, 10h
0x14002dd60  jmp     short loc_14002DD66
0x14002dd62  and     r8d, 0FFFFFFEFh
0x14002dd66  xor     eax, eax
0x14002dd68  lea     rdx, [rbp+var_28]
0x14002dd6c  xorps   xmm0, xmm0
0x14002dd6f  mov     [rbp+var_18], rax
0x14002dd73  lea     rcx, [rbp+var_48]
0x14002dd77  mov     [rbp+var_10], eax
0x14002dd7a  movups  [rbp+var_28], xmm0
0x14002dd7e  call    QuicConnPoolGetStartingLocalAddress
0x14002dd83  mov     ebx, eax
0x14002dd85  test    eax, eax
0x14002dd87  js      short loc_14002DDDE
0x14002dd89  lea     rdx, [rbp+var_50]
0x14002dd8d  mov     [rbp+var_50], r14d
0x14002dd91  lea     rcx, [rbp+var_28]
0x14002dd95  call    QuicConnPoolGetInterfaceIndexForLocalAddress
0x14002dd9a  mov     ebx, eax
0x14002dd9c  test    eax, eax
0x14002dd9e  js      short loc_14002DDDE
0x14002dda0  mov     ebx, 0C00000BBh
0x14002dda5  jmp     short loc_14002DDDE
0x14002dda7  test    cs:Microsoft_QuicEnableBits, 4
0x14002ddae  mov     ebx, 0C000000Dh
0x14002ddb3  jz      short loc_14002DDDE
0x14002ddb5  lea     r9, aConnectionPool; "Connection Pool Config"
0x14002ddbc  jmp     short loc_14002DDD3
0x14002ddbe  test    cs:Microsoft_QuicEnableBits, 4
0x14002ddc5  mov     ebx, 0C000000Dh
0x14002ddca  jz      short loc_14002DDDE
0x14002ddcc  lea     r9, aConnectionPool_0; "Connection Pool Parameter"
0x14002ddd3  mov     r8d, 0C000000Dh
0x14002ddd9  call    McTemplateU0qs_EtwWriteTransfer
0x14002ddde  test    cs:Microsoft_QuicEnableBits, r15b
0x14002dde5  jz      short loc_14002DDF6
0x14002dde7  mov     r8d, ebx
0x14002ddea  lea     rdx, QuicApiExitStatus
0x14002ddf1  call    McTemplateU0q_EtwWriteTransfer
0x14002ddf6  mov     eax, ebx
0x14002ddf8  mov     rcx, [rbp+var_8]
0x14002ddfc  xor     rcx, rsp; StackCookie
0x14002ddff  call    __security_check_cookie
0x14002de04  lea     r11, [rsp+70h+var_s0]
0x14002de09  mov     rbx, [r11+30h]
0x14002de0d  mov     rdi, [r11+38h]
0x14002de11  mov     rsp, r11
0x14002de14  pop     r15
0x14002de16  pop     r14
0x14002de18  pop     rbp
0x14002de19  retn
```
