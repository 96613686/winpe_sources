# BuildConfiguredLanList

- ea: `0x18000a020`
- end: `0x18000a616`
- name: `BuildConfiguredLanList`
- size: `1526`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180008570`

## callees

- `0x180002538`
- `0x1800045ac`
- `0x18000937c`
- `0x1800093e0`
- `0x1800094f4`
- `0x180009b60`
- `0x18000a020`
- `0x18000c15c`
- `0x18000c220`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000a42e`
- `msvcrt!wcscpy_s` at `0x18000a42e`
- `KERNEL32!GlobalFree` at `0x18000a205`
- `KERNEL32!GlobalFree` at `0x18000a4e1`
- `KERNEL32!GlobalFree` at `0x18000a591`
- `KERNEL32!GlobalFree` at `0x18000a205`
- `KERNEL32!GlobalFree` at `0x18000a4e1`
- `KERNEL32!GlobalFree` at `0x18000a591`
- `KERNEL32!GlobalAlloc` at `0x18000a128`
- `KERNEL32!GlobalAlloc` at `0x18000a226`
- `KERNEL32!GlobalAlloc` at `0x18000a39a`
- `KERNEL32!GlobalAlloc` at `0x18000a128`
- `KERNEL32!GlobalAlloc` at `0x18000a226`
- `KERNEL32!GlobalAlloc` at `0x18000a39a`
- `RPCRT4!RpcBindingFree` at `0x18000a4f3`
- `RPCRT4!RpcBindingFree` at `0x18000a5b7`
- `RPCRT4!RpcBindingFree` at `0x18000a4f3`
- `RPCRT4!RpcBindingFree` at `0x18000a5b7`
- `RPCRT4!NdrClientCall3` at `0x18000a1de`
- `RPCRT4!NdrClientCall3` at `0x18000a2ac`
- `RPCRT4!NdrClientCall3` at `0x18000a1de`
- `RPCRT4!NdrClientCall3` at `0x18000a2ac`

## string_xrefs

- `0x18000a055`: `BuildConfiguredLanList`

## pseudocode

```c
__int64 __fastcall BuildConfiguredLanList(CLIENT_CALL_RETURN a1)
{
  CLIENT_CALL_RETURN v1; // rbx
  int v2; // eax
  _QWORD *v3; // rcx
  unsigned int v4; // r13d
  char *v5; // rax
  char *v6; // r15
  char *v7; // rax
  CLIENT_CALL_RETURN v8; // r13
  unsigned __int64 Simple; // rcx
  __int64 *v10; // rbx
  int v11; // eax
  __int64 v12; // rax
  char *v13; // rcx
  __int64 v14; // rax
  __int64 *v15; // rax
  int v16; // edx
  int v17; // r8d
  __int64 *v18; // r13
  __int64 **v19; // rcx
  CLIENT_CALL_RETURN v21; // [rsp+28h] [rbp-D0h]
  __int64 v22; // [rsp+40h] [rbp-B8h] BYREF
  _DWORD v23[3]; // [rsp+4Ch] [rbp-ACh] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-A0h] BYREF
  CLIENT_CALL_RETURN v25; // [rsp+60h] [rbp-98h]
  char *v26; // [rsp+68h] [rbp-90h]
  CLIENT_CALL_RETURN v27; // [rsp+70h] [rbp-88h]
  rsize_t SizeInWords; // [rsp+78h] [rbp-80h]
  __int64 **v29; // [rsp+80h] [rbp-78h]
  __int64 *v30; // [rsp+88h] [rbp-70h]
  CLIENT_CALL_RETURN v31; // [rsp+90h] [rbp-68h]
  char v32[24]; // [rsp+98h] [rbp-60h] BYREF

  v1.Pointer = a1.Pointer;
  v25.Pointer = a1.Pointer;
  v31.Pointer = a1.Pointer;
  strcpy(v32, "BuildConfiguredLanList");
  HIDWORD(v22) = 0;
  v23[0] = 0;
  v26 = 0;
  Binding = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      (unsigned int)&WPP_7b522c97afb2341f13613538df880a66_Traceguids,
      (unsigned int)v32,
      a1.Simple);
  v29 = (__int64 **)(v1.Simple + 40);
  *(_QWORD *)(v1.Simple + 40) = 0;
  v2 = RpcBindForNfsClient(&Binding);
  LODWORD(v1.Pointer) = v2;
  if ( v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return LODWORD(v1.Pointer);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_62:
      if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 )
        WPP_SF_sd(
          v3[2],
          48,
          (unsigned int)&WPP_7b522c97afb2341f13613538df880a66_Traceguids,
          (unsigned int)v32,
          v1.Simple);
      return LODWORD(v1.Pointer);
    }
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      (unsigned int)&WPP_7b522c97afb2341f13613538df880a66_Traceguids,
      (unsigned int)v32,
      v2);
LABEL_61:
    v3 = WPP_GLOBAL_Control;
    goto LABEL_62;
  }
  LODWORD(v22) = 0;
  v4 = 8190;
  v5 = (char *)GlobalAlloc(0x40u, 0x2000u);
  v6 = v5;
  v26 = v5;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, v32);
    LODWORD(v1.Pointer) = 8;
LABEL_60:
    RpcBindingFree(&Binding);
    goto LABEL_61;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_sq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      (unsigned int)&WPP_7b522c97afb2341f13613538df880a66_Traceguids,
      (unsigned int)v32,
      (char)v5);
  v27.Simple = 0;
  v1.Pointer = NdrClientCall3(
                 (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                 8u,
                 0,
                 Binding,
                 (char *)&v22 + 4,
                 8190,
                 v6,
                 v23,
                 v22).Pointer;
  v27.Pointer = v1.Pointer;
  LODWORD(v22) = v1.Pointer;
  while ( LODWORD(v1.Pointer) == 234 )
  {
    GlobalFree(v6);
    v4 = v23[0] + 64;
    v7 = (char *)GlobalAlloc(0x40u, (unsigned int)(v23[0] + 64) + 2LL);
    v6 = v7;
    v26 = v7;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, v32);
      LODWORD(v1.Pointer) = 8;
      goto LABEL_60;
    }
    SizeInWords = 0;
    LODWORD(v21.Pointer) = v4;
    SizeInWords = (rsize_t)NdrClientCall3(
                             (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                             8u,
                             0,
                             Binding,
                             (char *)&v22 + 4,
                             v21.Simple,
                             v7,
                             v23,
                             v22).Pointer;
    LODWORD(v1.Pointer) = SizeInWords;
    LODWORD(v22) = SizeInWords;
  }
  if ( LODWORD(v1.Pointer) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        &WPP_7b522c97afb2341f13613538df880a66_Traceguids,
        LODWORD(v1.Pointer));
    v8.Pointer = v25.Pointer;
LABEL_58:
    GlobalFree(v6);
    if ( *v29 )
      ((void (__fastcall *)(_QWORD))FreeLanList)((CLIENT_CALL_RETURN)v8.Simple);
    goto LABEL_60;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      (unsigned int)&WPP_7b522c97afb2341f13613538df880a66_Traceguids,
      (unsigned int)v32,
      SBYTE4(v22));
  Simple = v4;
  v27.Simple = v4;
  *(_WORD *)&v6[2 * ((unsigned __int64)v4 >> 1)] = 0;
  v10 = (__int64 *)v6;
  v30 = (__int64 *)v6;
  v11 = HIDWORD(v22);
  while ( v11 )
  {
    if ( v10 >= (__int64 *)&v6[Simple] || (v12 = *v10, *v10 >= Simple) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, v32);
      LODWORD(v1.Pointer) = 13;
      v8.Pointer = v25.Pointer;
      goto LABEL_58;
    }
    v13 = &v6[v12];
    *v10 = (__int64)&v6[v12];
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)&v13[2 * v14] );
    SizeInWords = (unsigned int)(v14 + 1);
    v15 = (__int64 *)GlobalAlloc(0x40u, 2LL * (unsigned int)SizeInWords + 16);
    v18 = v15;
    if ( !v15 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, v32);
      LODWORD(v1.Pointer) = 8;
      v8.Pointer = v25.Pointer;
      goto LABEL_58;
    }
    *v15 = (__int64)(v15 + 2);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_sqS(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v17, (unsigned int)v32, (char)v10, *v10);
    wcscpy_s((wchar_t *)*v18, SizeInWords, (const wchar_t *)*v10);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        (unsigned int)&WPP_7b522c97afb2341f13613538df880a66_Traceguids,
        (unsigned int)v32,
        *v18);
    v19 = v29;
    v18[1] = (__int64)*v29;
    *v19 = v18;
    v10 += 2;
    v30 = v10;
    v11 = --HIDWORD(v22);
    Simple = v27.Simple;
  }
  GlobalFree(v6);
  RpcBindingFree(&Binding);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, v32);
  return 0;
}

```

## disassembly

```asm
0x18000a020  mov     r11, rsp
0x18000a023  push    rbx
0x18000a024  push    rsi
0x18000a025  push    rdi
0x18000a026  push    r13
0x18000a028  push    r14
0x18000a02a  push    r15
0x18000a02c  sub     rsp, 0C8h
0x18000a033  mov     rax, cs:__security_cookie
0x18000a03a  xor     rax, rsp
0x18000a03d  mov     [rsp+0F8h+var_48], rax
0x18000a045  mov     rbx, rcx
0x18000a048  mov     [rsp+0F8h+var_98], rcx
0x18000a04d  mov     [rsp+0F8h+var_68], rcx
0x18000a055  movups  xmm0, xmmword ptr cs:aBuildconfigure; "BuildConfiguredLanList"
0x18000a05c  movups  xmmword ptr [r11-60h], xmm0
0x18000a061  movsd   xmm1, qword ptr cs:aBuildconfigure+0Fh; "LanList"
0x18000a069  movsd   qword ptr [r11-51h], xmm1
0x18000a06f  xor     edi, edi
0x18000a071  mov     [rsp+0F8h+var_B4], edi
0x18000a075  mov     [rsp+0F8h+var_AC], edi
0x18000a079  mov     [rsp+0F8h+var_90], rdi
0x18000a07e  mov     [rsp+0F8h+Binding], rdi
0x18000a083  lea     r14, WPP_GLOBAL_Control
0x18000a08a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a091  lea     rsi, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000a098  cmp     rcx, r14
0x18000a09b  jz      short loc_18000A0BB
0x18000a09d  test    byte ptr [rcx+1Ch], 1
0x18000a0a1  jz      short loc_18000A0BB
0x18000a0a3  lea     edx, [rdi+23h]
0x18000a0a6  mov     [rsp+0F8h+var_D8], rbx
0x18000a0ab  lea     r9, [r11-60h]
0x18000a0af  mov     r8, rsi
0x18000a0b2  mov     rcx, [rcx+10h]
0x18000a0b6  call    WPP_SF_sq
0x18000a0bb  lea     rax, [rbx+28h]
0x18000a0bf  mov     [rsp+0F8h+var_78], rax
0x18000a0c7  mov     [rax], rdi
0x18000a0ca  lea     rcx, [rsp+0F8h+Binding]
0x18000a0cf  call    RpcBindForNfsClient
0x18000a0d4  mov     ebx, eax
0x18000a0d6  test    eax, eax
0x18000a0d8  jz      short loc_18000A116
0x18000a0da  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0e1  cmp     rcx, r14
0x18000a0e4  jz      loc_18000A5F2
0x18000a0ea  test    byte ptr [rcx+1Ch], 2
0x18000a0ee  jz      loc_18000A5CA
0x18000a0f4  mov     edx, 24h ; '$'
0x18000a0f9  mov     dword ptr [rsp+0F8h+var_D8], eax
0x18000a0fd  lea     r9, [rsp+0F8h+var_60]
0x18000a105  mov     r8, rsi
0x18000a108  mov     rcx, [rcx+10h]
0x18000a10c  call    WPP_SF_sd
0x18000a111  jmp     loc_18000A5C3
0x18000a116  mov     [rsp+0F8h+var_B8], edi
0x18000a11a  mov     edx, 2000h; dwBytes
0x18000a11f  mov     ecx, 40h ; '@'; uFlags
0x18000a124  lea     r13d, [rdx-2]
0x18000a128  call    cs:__imp_GlobalAlloc
0x18000a12f  nop     dword ptr [rax+rax+00h]
0x18000a134  mov     r15, rax
0x18000a137  mov     [rsp+0F8h+var_90], rax
0x18000a13c  test    rax, rax
0x18000a13f  jnz     short loc_18000A178
0x18000a141  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a148  cmp     rcx, r14
0x18000a14b  jz      short loc_18000A16A
0x18000a14d  test    byte ptr [rcx+1Ch], 2
0x18000a151  jz      short loc_18000A16A
0x18000a153  lea     edx, [rax+25h]
0x18000a156  lea     r9, [rsp+0F8h+var_60]
0x18000a15e  mov     r8, rsi
0x18000a161  mov     rcx, [rcx+10h]
0x18000a165  call    WPP_SF_s
0x18000a16a  mov     ebx, 8
0x18000a16f  mov     [rsp+0F8h+var_B8], ebx
0x18000a173  jmp     loc_18000A5B2
0x18000a178  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a17f  cmp     rcx, r14
0x18000a182  jz      short loc_18000A1A8
0x18000a184  test    byte ptr [rcx+1Ch], 8
0x18000a188  jz      short loc_18000A1A8
0x18000a18a  mov     edx, 26h ; '&'
0x18000a18f  mov     [rsp+0F8h+var_D8], r15
0x18000a194  lea     r9, [rsp+0F8h+var_60]
0x18000a19c  mov     r8, rsi
0x18000a19f  mov     rcx, [rcx+10h]
0x18000a1a3  call    WPP_SF_sq
0x18000a1a8  mov     [rsp+0F8h+var_88], rdi
0x18000a1ad  lea     rax, [rsp+0F8h+var_AC]
0x18000a1b2  mov     [rsp+0F8h+var_C0], rax
0x18000a1b7  mov     [rsp+0F8h+var_C8], r15
0x18000a1bc  mov     dword ptr [rsp+0F8h+var_D0], r13d
0x18000a1c1  lea     rax, [rsp+0F8h+var_B4]
0x18000a1c6  mov     [rsp+0F8h+var_D8], rax
0x18000a1cb  mov     r9, [rsp+0F8h+Binding]
0x18000a1d0  xor     r8d, r8d; pReturnValue
0x18000a1d3  lea     edx, [r8+8]; nProcNum
0x18000a1d7  lea     rcx, pProxyInfo; pProxyInfo
0x18000a1de  call    cs:__imp_NdrClientCall3
0x18000a1e5  nop     dword ptr [rax+rax+00h]
0x18000a1ea  mov     rbx, rax
0x18000a1ed  mov     [rsp+0F8h+var_88], rax
0x18000a1f2  mov     [rsp+0F8h+var_B8], eax
0x18000a1f6  cmp     ebx, 0EAh
0x18000a1fc  jnz     loc_18000A2C8
0x18000a202  mov     rcx, r15; hMem
0x18000a205  call    cs:__imp_GlobalFree
0x18000a20c  nop     dword ptr [rax+rax+00h]
0x18000a211  mov     r13d, [rsp+0F8h+var_AC]
0x18000a216  add     r13d, 40h ; '@'
0x18000a21a  mov     edx, r13d
0x18000a21d  add     rdx, 2; dwBytes
0x18000a221  mov     ecx, 40h ; '@'; uFlags
0x18000a226  call    cs:__imp_GlobalAlloc
0x18000a22d  nop     dword ptr [rax+rax+00h]
0x18000a232  mov     r15, rax
0x18000a235  mov     [rsp+0F8h+var_90], rax
0x18000a23a  test    rax, rax
0x18000a23d  jnz     short loc_18000A276
0x18000a23f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a246  cmp     rcx, r14
0x18000a249  jz      short loc_18000A268
0x18000a24b  test    byte ptr [rcx+1Ch], 2
0x18000a24f  jz      short loc_18000A268
0x18000a251  lea     edx, [rax+27h]
0x18000a254  lea     r9, [rsp+0F8h+var_60]
0x18000a25c  mov     r8, rsi
0x18000a25f  mov     rcx, [rcx+10h]
0x18000a263  call    WPP_SF_s
0x18000a268  mov     ebx, 8
0x18000a26d  mov     [rsp+0F8h+var_B8], ebx
0x18000a271  jmp     loc_18000A5B2
0x18000a276  mov     [rsp+0F8h+SizeInWords], rdi
0x18000a27b  lea     rax, [rsp+0F8h+var_AC]
0x18000a280  mov     [rsp+0F8h+var_C0], rax
0x18000a285  mov     [rsp+0F8h+var_C8], r15
0x18000a28a  mov     dword ptr [rsp+0F8h+var_D0], r13d
0x18000a28f  lea     rax, [rsp+0F8h+var_B4]
0x18000a294  mov     [rsp+0F8h+var_D8], rax
0x18000a299  mov     r9, [rsp+0F8h+Binding]
0x18000a29e  xor     r8d, r8d; pReturnValue
0x18000a2a1  lea     edx, [r8+8]; nProcNum
0x18000a2a5  lea     rcx, pProxyInfo; pProxyInfo
0x18000a2ac  call    cs:__imp_NdrClientCall3
0x18000a2b3  nop     dword ptr [rax+rax+00h]
0x18000a2b8  mov     [rsp+0F8h+SizeInWords], rax
0x18000a2bd  mov     ebx, eax
0x18000a2bf  mov     [rsp+0F8h+var_B8], eax
0x18000a2c3  jmp     loc_18000A1F6
0x18000a2c8  test    ebx, ebx
0x18000a2ca  jz      short loc_18000A2FC
0x18000a2cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2d3  cmp     rcx, r14
0x18000a2d6  jz      short loc_18000A2F2
0x18000a2d8  test    byte ptr [rcx+1Ch], 2
0x18000a2dc  jz      short loc_18000A2F2
0x18000a2de  mov     edx, 28h ; '('
0x18000a2e3  mov     r9d, ebx
0x18000a2e6  mov     r8, rsi
0x18000a2e9  mov     rcx, [rcx+10h]
0x18000a2ed  call    WPP_SF_d
0x18000a2f2  mov     r13, [rsp+0F8h+var_98]
0x18000a2f7  jmp     loc_18000A58E
0x18000a2fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a303  cmp     rcx, r14
0x18000a306  jz      short loc_18000A32F
0x18000a308  test    byte ptr [rcx+1Ch], 8
0x18000a30c  jz      short loc_18000A32F
0x18000a30e  mov     edx, 29h ; ')'
0x18000a313  mov     eax, [rsp+0F8h+var_B4]
0x18000a317  mov     dword ptr [rsp+0F8h+var_D8], eax
0x18000a31b  lea     r9, [rsp+0F8h+var_60]
0x18000a323  mov     r8, rsi
0x18000a326  mov     rcx, [rcx+10h]
0x18000a32a  call    WPP_SF_sd
0x18000a32f  mov     ecx, r13d
0x18000a332  mov     [rsp+0F8h+var_88], rcx
0x18000a337  mov     eax, r13d
0x18000a33a  shr     rax, 1
0x18000a33d  mov     [r15+rax*2], di
0x18000a342  mov     rbx, r15
0x18000a345  mov     [rsp+0F8h+var_70], rbx
0x18000a34d  mov     eax, [rsp+0F8h+var_B4]
0x18000a351  test    eax, eax
0x18000a353  jz      loc_18000A4DE
0x18000a359  lea     rax, [rcx+r15]
0x18000a35d  cmp     rbx, rax
0x18000a360  jnb     loc_18000A4A0
0x18000a366  mov     rax, [rbx]
0x18000a369  cmp     rax, rcx
0x18000a36c  jnb     loc_18000A4A0
0x18000a372  lea     rcx, [rax+r15]
0x18000a376  mov     [rbx], rcx
0x18000a379  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a37d  inc     rax
0x18000a380  cmp     [rcx+rax*2], di
0x18000a384  jnz     short loc_18000A37D
0x18000a386  inc     eax
0x18000a388  mov     [rsp+0F8h+SizeInWords], rax
0x18000a38d  lea     rdx, ds:10h[rax*2]; dwBytes
0x18000a395  mov     ecx, 40h ; '@'; uFlags
0x18000a39a  call    cs:__imp_GlobalAlloc
0x18000a3a1  nop     dword ptr [rax+rax+00h]
0x18000a3a6  mov     r13, rax
0x18000a3a9  test    rax, rax
0x18000a3ac  jnz     short loc_18000A3EA
0x18000a3ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3b5  cmp     rcx, r14
0x18000a3b8  jz      short loc_18000A3D7
0x18000a3ba  test    byte ptr [rcx+1Ch], 2
0x18000a3be  jz      short loc_18000A3D7
0x18000a3c0  lea     edx, [rax+2Bh]
0x18000a3c3  lea     r9, [rsp+0F8h+var_60]
0x18000a3cb  mov     r8, rsi
0x18000a3ce  mov     rcx, [rcx+10h]
0x18000a3d2  call    WPP_SF_s
0x18000a3d7  mov     ebx, 8
0x18000a3dc  mov     [rsp+0F8h+var_B8], ebx
0x18000a3e0  mov     r13, [rsp+0F8h+var_98]
0x18000a3e5  jmp     loc_18000A58E
0x18000a3ea  add     rax, 10h
0x18000a3ee  mov     [r13+0], rax
0x18000a3f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3f9  cmp     rcx, r14
0x18000a3fc  jz      short loc_18000A422
0x18000a3fe  test    byte ptr [rcx+1Ch], 8
0x18000a402  jz      short loc_18000A422
0x18000a404  mov     rax, [rbx]
0x18000a407  mov     [rsp+0F8h+var_D0], rax
0x18000a40c  mov     [rsp+0F8h+var_D8], rbx
0x18000a411  lea     r9, [rsp+0F8h+var_60]
0x18000a419  mov     rcx, [rcx+10h]
0x18000a41d  call    WPP_SF_sqS
0x18000a422  mov     r8, [rbx]; Source
0x18000a425  mov     rdx, [rsp+0F8h+SizeInWords]; SizeInWords
0x18000a42a  mov     rcx, [r13+0]; Destination
0x18000a42e  call    cs:__imp_wcscpy_s
0x18000a435  nop     dword ptr [rax+rax+00h]
0x18000a43a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a441  cmp     rcx, r14
0x18000a444  jz      short loc_18000A46E
0x18000a446  test    byte ptr [rcx+1Ch], 8
0x18000a44a  jz      short loc_18000A46E
0x18000a44c  mov     edx, 2Dh ; '-'
0x18000a451  mov     rax, [r13+0]
0x18000a455  mov     [rsp+0F8h+var_D8], rax
0x18000a45a  lea     r9, [rsp+0F8h+var_60]
0x18000a462  mov     r8, rsi
0x18000a465  mov     rcx, [rcx+10h]
0x18000a469  call    WPP_SF_sS
0x18000a46e  mov     rcx, [rsp+0F8h+var_78]
0x18000a476  mov     rax, [rcx]
0x18000a479  mov     [r13+8], rax
0x18000a47d  mov     [rcx], r13
0x18000a480  add     rbx, 10h
0x18000a484  mov     [rsp+0F8h+var_70], rbx
0x18000a48c  mov     eax, [rsp+0F8h+var_B4]
0x18000a490  dec     eax
0x18000a492  mov     [rsp+0F8h+var_B4], eax
0x18000a496  mov     rcx, [rsp+0F8h+var_88]
0x18000a49b  jmp     loc_18000A351
0x18000a4a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4a7  cmp     rcx, r14
0x18000a4aa  jz      short loc_18000A4CB
0x18000a4ac  test    byte ptr [rcx+1Ch], 2
0x18000a4b0  jz      short loc_18000A4CB
0x18000a4b2  mov     edx, 2Ah ; '*'
0x18000a4b7  lea     r9, [rsp+0F8h+var_60]
0x18000a4bf  mov     r8, rsi
0x18000a4c2  mov     rcx, [rcx+10h]
0x18000a4c6  call    WPP_SF_s
0x18000a4cb  mov     ebx, 0Dh
0x18000a4d0  mov     [rsp+0F8h+var_B8], ebx
0x18000a4d4  mov     r13, [rsp+0F8h+var_98]
0x18000a4d9  jmp     loc_18000A58E
0x18000a4de  mov     rcx, r15; hMem
0x18000a4e1  call    cs:__imp_GlobalFree
0x18000a4e8  nop     dword ptr [rax+rax+00h]
0x18000a4ed  nop
0x18000a4ee  lea     rcx, [rsp+0F8h+Binding]; Binding
0x18000a4f3  call    cs:__imp_RpcBindingFree
0x18000a4fa  nop     dword ptr [rax+rax+00h]
0x18000a4ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a506  cmp     rcx, r14
0x18000a509  jz      short loc_18000A52A
0x18000a50b  test    byte ptr [rcx+1Ch], 1
0x18000a50f  jz      short loc_18000A52A
0x18000a511  mov     edx, 2Fh ; '/'
0x18000a516  lea     r9, [rsp+0F8h+var_60]
0x18000a51e  mov     r8, rsi
0x18000a521  mov     rcx, [rcx+10h]
0x18000a525  call    WPP_SF_s
0x18000a52a  xor     eax, eax
0x18000a52c  jmp     loc_18000A5F4
0x18000a531  mov     ebx, eax
0x18000a533  mov     [rsp+0F8h+var_B8], eax
0x18000a537  lea     rdx, WPP_GLOBAL_Control
  ... truncated ...
```
