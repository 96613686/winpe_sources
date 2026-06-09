# BuildConfiguredLanList

- ea: `0x180009948`
- end: `0x180009efb`
- name: `BuildConfiguredLanList`
- size: `1459`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180007fd0`

## callees

- `0x180002418`
- `0x180004418`
- `0x180008d20`
- `0x180008d7c`
- `0x180008e80`
- `0x1800094bc`
- `0x180009948`
- `0x18000b8f8`
- `0x18000b9b8`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180009d32`
- `msvcrt!wcscpy_s` at `0x180009d32`
- `KERNEL32!GlobalFree` at `0x180009b21`
- `KERNEL32!GlobalFree` at `0x180009ddf`
- `KERNEL32!GlobalFree` at `0x180009e83`
- `KERNEL32!GlobalFree` at `0x180009b21`
- `KERNEL32!GlobalFree` at `0x180009ddf`
- `KERNEL32!GlobalFree` at `0x180009e83`
- `KERNEL32!GlobalAlloc` at `0x180009a50`
- `KERNEL32!GlobalAlloc` at `0x180009b3c`
- `KERNEL32!GlobalAlloc` at `0x180009ca4`
- `KERNEL32!GlobalAlloc` at `0x180009a50`
- `KERNEL32!GlobalAlloc` at `0x180009b3c`
- `KERNEL32!GlobalAlloc` at `0x180009ca4`
- `RPCRT4!RpcBindingFree` at `0x180009deb`
- `RPCRT4!RpcBindingFree` at `0x180009ea3`
- `RPCRT4!RpcBindingFree` at `0x180009deb`
- `RPCRT4!RpcBindingFree` at `0x180009ea3`
- `RPCRT4!NdrClientCall3` at `0x180009b00`
- `RPCRT4!NdrClientCall3` at `0x180009bbc`
- `RPCRT4!NdrClientCall3` at `0x180009b00`
- `RPCRT4!NdrClientCall3` at `0x180009bbc`

## string_xrefs

- `0x18000997d`: `BuildConfiguredLanList`

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
0x180009948  mov     r11, rsp
0x18000994b  push    rbx
0x18000994c  push    rsi
0x18000994d  push    rdi
0x18000994e  push    r13
0x180009950  push    r14
0x180009952  push    r15
0x180009954  sub     rsp, 0C8h
0x18000995b  mov     rax, cs:__security_cookie
0x180009962  xor     rax, rsp
0x180009965  mov     [rsp+0F8h+var_48], rax
0x18000996d  mov     rbx, rcx
0x180009970  mov     [rsp+0F8h+var_98], rcx
0x180009975  mov     [rsp+0F8h+var_68], rcx
0x18000997d  movups  xmm0, xmmword ptr cs:aBuildconfigure; "BuildConfiguredLanList"
0x180009984  movups  xmmword ptr [r11-60h], xmm0
0x180009989  movsd   xmm1, qword ptr cs:aBuildconfigure+0Fh; "LanList"
0x180009991  movsd   qword ptr [r11-51h], xmm1
0x180009997  xor     edi, edi
0x180009999  mov     [rsp+0F8h+var_B4], edi
0x18000999d  mov     [rsp+0F8h+var_AC], edi
0x1800099a1  mov     [rsp+0F8h+var_90], rdi
0x1800099a6  mov     [rsp+0F8h+Binding], rdi
0x1800099ab  lea     r14, WPP_GLOBAL_Control
0x1800099b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099b9  lea     rsi, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x1800099c0  cmp     rcx, r14
0x1800099c3  jz      short loc_1800099E3
0x1800099c5  test    byte ptr [rcx+1Ch], 1
0x1800099c9  jz      short loc_1800099E3
0x1800099cb  lea     edx, [rdi+23h]
0x1800099ce  mov     [rsp+0F8h+var_D8], rbx
0x1800099d3  lea     r9, [r11-60h]
0x1800099d7  mov     r8, rsi
0x1800099da  mov     rcx, [rcx+10h]
0x1800099de  call    WPP_SF_sq
0x1800099e3  lea     rax, [rbx+28h]
0x1800099e7  mov     [rsp+0F8h+var_78], rax
0x1800099ef  mov     [rax], rdi
0x1800099f2  lea     rcx, [rsp+0F8h+Binding]
0x1800099f7  call    RpcBindForNfsClient
0x1800099fc  mov     ebx, eax
0x1800099fe  test    eax, eax
0x180009a00  jz      short loc_180009A3E
0x180009a02  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a09  cmp     rcx, r14
0x180009a0c  jz      loc_180009ED8
0x180009a12  test    byte ptr [rcx+1Ch], 2
0x180009a16  jz      loc_180009EB0
0x180009a1c  mov     edx, 24h ; '$'
0x180009a21  mov     dword ptr [rsp+0F8h+var_D8], eax
0x180009a25  lea     r9, [rsp+0F8h+var_60]
0x180009a2d  mov     r8, rsi
0x180009a30  mov     rcx, [rcx+10h]
0x180009a34  call    WPP_SF_sd
0x180009a39  jmp     loc_180009EA9
0x180009a3e  mov     [rsp+0F8h+var_B8], edi
0x180009a42  mov     edx, 2000h; dwBytes
0x180009a47  mov     ecx, 40h ; '@'; uFlags
0x180009a4c  lea     r13d, [rdx-2]
0x180009a50  call    cs:__imp_GlobalAlloc
0x180009a56  mov     r15, rax
0x180009a59  mov     [rsp+0F8h+var_90], rax
0x180009a5e  test    rax, rax
0x180009a61  jnz     short loc_180009A9A
0x180009a63  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a6a  cmp     rcx, r14
0x180009a6d  jz      short loc_180009A8C
0x180009a6f  test    byte ptr [rcx+1Ch], 2
0x180009a73  jz      short loc_180009A8C
0x180009a75  lea     edx, [rax+25h]
0x180009a78  lea     r9, [rsp+0F8h+var_60]
0x180009a80  mov     r8, rsi
0x180009a83  mov     rcx, [rcx+10h]
0x180009a87  call    WPP_SF_s
0x180009a8c  mov     ebx, 8
0x180009a91  mov     [rsp+0F8h+var_B8], ebx
0x180009a95  jmp     loc_180009E9E
0x180009a9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009aa1  cmp     rcx, r14
0x180009aa4  jz      short loc_180009ACA
0x180009aa6  test    byte ptr [rcx+1Ch], 8
0x180009aaa  jz      short loc_180009ACA
0x180009aac  mov     edx, 26h ; '&'
0x180009ab1  mov     [rsp+0F8h+var_D8], r15
0x180009ab6  lea     r9, [rsp+0F8h+var_60]
0x180009abe  mov     r8, rsi
0x180009ac1  mov     rcx, [rcx+10h]
0x180009ac5  call    WPP_SF_sq
0x180009aca  mov     [rsp+0F8h+var_88], rdi
0x180009acf  lea     rax, [rsp+0F8h+var_AC]
0x180009ad4  mov     [rsp+0F8h+var_C0], rax
0x180009ad9  mov     [rsp+0F8h+var_C8], r15
0x180009ade  mov     dword ptr [rsp+0F8h+var_D0], r13d
0x180009ae3  lea     rax, [rsp+0F8h+var_B4]
0x180009ae8  mov     [rsp+0F8h+var_D8], rax
0x180009aed  mov     r9, [rsp+0F8h+Binding]
0x180009af2  xor     r8d, r8d; pReturnValue
0x180009af5  lea     edx, [r8+8]; nProcNum
0x180009af9  lea     rcx, pProxyInfo; pProxyInfo
0x180009b00  call    cs:__imp_NdrClientCall3
0x180009b06  mov     rbx, rax
0x180009b09  mov     [rsp+0F8h+var_88], rax
0x180009b0e  mov     [rsp+0F8h+var_B8], eax
0x180009b12  cmp     ebx, 0EAh
0x180009b18  jnz     loc_180009BD2
0x180009b1e  mov     rcx, r15; hMem
0x180009b21  call    cs:__imp_GlobalFree
0x180009b27  mov     r13d, [rsp+0F8h+var_AC]
0x180009b2c  add     r13d, 40h ; '@'
0x180009b30  mov     edx, r13d
0x180009b33  add     rdx, 2; dwBytes
0x180009b37  mov     ecx, 40h ; '@'; uFlags
0x180009b3c  call    cs:__imp_GlobalAlloc
0x180009b42  mov     r15, rax
0x180009b45  mov     [rsp+0F8h+var_90], rax
0x180009b4a  test    rax, rax
0x180009b4d  jnz     short loc_180009B86
0x180009b4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b56  cmp     rcx, r14
0x180009b59  jz      short loc_180009B78
0x180009b5b  test    byte ptr [rcx+1Ch], 2
0x180009b5f  jz      short loc_180009B78
0x180009b61  lea     edx, [rax+27h]
0x180009b64  lea     r9, [rsp+0F8h+var_60]
0x180009b6c  mov     r8, rsi
0x180009b6f  mov     rcx, [rcx+10h]
0x180009b73  call    WPP_SF_s
0x180009b78  mov     ebx, 8
0x180009b7d  mov     [rsp+0F8h+var_B8], ebx
0x180009b81  jmp     loc_180009E9E
0x180009b86  mov     [rsp+0F8h+SizeInWords], rdi
0x180009b8b  lea     rax, [rsp+0F8h+var_AC]
0x180009b90  mov     [rsp+0F8h+var_C0], rax
0x180009b95  mov     [rsp+0F8h+var_C8], r15
0x180009b9a  mov     dword ptr [rsp+0F8h+var_D0], r13d
0x180009b9f  lea     rax, [rsp+0F8h+var_B4]
0x180009ba4  mov     [rsp+0F8h+var_D8], rax
0x180009ba9  mov     r9, [rsp+0F8h+Binding]
0x180009bae  xor     r8d, r8d; pReturnValue
0x180009bb1  lea     edx, [r8+8]; nProcNum
0x180009bb5  lea     rcx, pProxyInfo; pProxyInfo
0x180009bbc  call    cs:__imp_NdrClientCall3
0x180009bc2  mov     [rsp+0F8h+SizeInWords], rax
0x180009bc7  mov     ebx, eax
0x180009bc9  mov     [rsp+0F8h+var_B8], eax
0x180009bcd  jmp     loc_180009B12
0x180009bd2  test    ebx, ebx
0x180009bd4  jz      short loc_180009C06
0x180009bd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bdd  cmp     rcx, r14
0x180009be0  jz      short loc_180009BFC
0x180009be2  test    byte ptr [rcx+1Ch], 2
0x180009be6  jz      short loc_180009BFC
0x180009be8  mov     edx, 28h ; '('
0x180009bed  mov     r9d, ebx
0x180009bf0  mov     r8, rsi
0x180009bf3  mov     rcx, [rcx+10h]
0x180009bf7  call    WPP_SF_d
0x180009bfc  mov     r13, [rsp+0F8h+var_98]
0x180009c01  jmp     loc_180009E80
0x180009c06  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c0d  cmp     rcx, r14
0x180009c10  jz      short loc_180009C39
0x180009c12  test    byte ptr [rcx+1Ch], 8
0x180009c16  jz      short loc_180009C39
0x180009c18  mov     edx, 29h ; ')'
0x180009c1d  mov     eax, [rsp+0F8h+var_B4]
0x180009c21  mov     dword ptr [rsp+0F8h+var_D8], eax
0x180009c25  lea     r9, [rsp+0F8h+var_60]
0x180009c2d  mov     r8, rsi
0x180009c30  mov     rcx, [rcx+10h]
0x180009c34  call    WPP_SF_sd
0x180009c39  mov     ecx, r13d
0x180009c3c  mov     [rsp+0F8h+var_88], rcx
0x180009c41  mov     eax, r13d
0x180009c44  shr     rax, 1
0x180009c47  mov     [r15+rax*2], di
0x180009c4c  mov     rbx, r15
0x180009c4f  mov     [rsp+0F8h+var_70], rbx
0x180009c57  mov     eax, [rsp+0F8h+var_B4]
0x180009c5b  test    eax, eax
0x180009c5d  jz      loc_180009DDC
0x180009c63  lea     rax, [rcx+r15]
0x180009c67  cmp     rbx, rax
0x180009c6a  jnb     loc_180009D9E
0x180009c70  mov     rax, [rbx]
0x180009c73  cmp     rax, rcx
0x180009c76  jnb     loc_180009D9E
0x180009c7c  lea     rcx, [rax+r15]
0x180009c80  mov     [rbx], rcx
0x180009c83  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009c87  inc     rax
0x180009c8a  cmp     [rcx+rax*2], di
0x180009c8e  jnz     short loc_180009C87
0x180009c90  inc     eax
0x180009c92  mov     [rsp+0F8h+SizeInWords], rax
0x180009c97  lea     rdx, ds:10h[rax*2]; dwBytes
0x180009c9f  mov     ecx, 40h ; '@'; uFlags
0x180009ca4  call    cs:__imp_GlobalAlloc
0x180009caa  mov     r13, rax
0x180009cad  test    rax, rax
0x180009cb0  jnz     short loc_180009CEE
0x180009cb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cb9  cmp     rcx, r14
0x180009cbc  jz      short loc_180009CDB
0x180009cbe  test    byte ptr [rcx+1Ch], 2
0x180009cc2  jz      short loc_180009CDB
0x180009cc4  lea     edx, [rax+2Bh]
0x180009cc7  lea     r9, [rsp+0F8h+var_60]
0x180009ccf  mov     r8, rsi
0x180009cd2  mov     rcx, [rcx+10h]
0x180009cd6  call    WPP_SF_s
0x180009cdb  mov     ebx, 8
0x180009ce0  mov     [rsp+0F8h+var_B8], ebx
0x180009ce4  mov     r13, [rsp+0F8h+var_98]
0x180009ce9  jmp     loc_180009E80
0x180009cee  add     rax, 10h
0x180009cf2  mov     [r13+0], rax
0x180009cf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cfd  cmp     rcx, r14
0x180009d00  jz      short loc_180009D26
0x180009d02  test    byte ptr [rcx+1Ch], 8
0x180009d06  jz      short loc_180009D26
0x180009d08  mov     rax, [rbx]
0x180009d0b  mov     [rsp+0F8h+var_D0], rax
0x180009d10  mov     [rsp+0F8h+var_D8], rbx
0x180009d15  lea     r9, [rsp+0F8h+var_60]
0x180009d1d  mov     rcx, [rcx+10h]
0x180009d21  call    WPP_SF_sqS
0x180009d26  mov     r8, [rbx]; Source
0x180009d29  mov     rdx, [rsp+0F8h+SizeInWords]; SizeInWords
0x180009d2e  mov     rcx, [r13+0]; Destination
0x180009d32  call    cs:__imp_wcscpy_s
0x180009d38  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d3f  cmp     rcx, r14
0x180009d42  jz      short loc_180009D6C
0x180009d44  test    byte ptr [rcx+1Ch], 8
0x180009d48  jz      short loc_180009D6C
0x180009d4a  mov     edx, 2Dh ; '-'
0x180009d4f  mov     rax, [r13+0]
0x180009d53  mov     [rsp+0F8h+var_D8], rax
0x180009d58  lea     r9, [rsp+0F8h+var_60]
0x180009d60  mov     r8, rsi
0x180009d63  mov     rcx, [rcx+10h]
0x180009d67  call    WPP_SF_sS
0x180009d6c  mov     rcx, [rsp+0F8h+var_78]
0x180009d74  mov     rax, [rcx]
0x180009d77  mov     [r13+8], rax
0x180009d7b  mov     [rcx], r13
0x180009d7e  add     rbx, 10h
0x180009d82  mov     [rsp+0F8h+var_70], rbx
0x180009d8a  mov     eax, [rsp+0F8h+var_B4]
0x180009d8e  dec     eax
0x180009d90  mov     [rsp+0F8h+var_B4], eax
0x180009d94  mov     rcx, [rsp+0F8h+var_88]
0x180009d99  jmp     loc_180009C5B
0x180009d9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009da5  cmp     rcx, r14
0x180009da8  jz      short loc_180009DC9
0x180009daa  test    byte ptr [rcx+1Ch], 2
0x180009dae  jz      short loc_180009DC9
0x180009db0  mov     edx, 2Ah ; '*'
0x180009db5  lea     r9, [rsp+0F8h+var_60]
0x180009dbd  mov     r8, rsi
0x180009dc0  mov     rcx, [rcx+10h]
0x180009dc4  call    WPP_SF_s
0x180009dc9  mov     ebx, 0Dh
0x180009dce  mov     [rsp+0F8h+var_B8], ebx
0x180009dd2  mov     r13, [rsp+0F8h+var_98]
0x180009dd7  jmp     loc_180009E80
0x180009ddc  mov     rcx, r15; hMem
0x180009ddf  call    cs:__imp_GlobalFree
0x180009de5  nop
0x180009de6  lea     rcx, [rsp+0F8h+Binding]; Binding
0x180009deb  call    cs:__imp_RpcBindingFree
0x180009df1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009df8  cmp     rcx, r14
0x180009dfb  jz      short loc_180009E1C
0x180009dfd  test    byte ptr [rcx+1Ch], 1
0x180009e01  jz      short loc_180009E1C
0x180009e03  mov     edx, 2Fh ; '/'
0x180009e08  lea     r9, [rsp+0F8h+var_60]
0x180009e10  mov     r8, rsi
0x180009e13  mov     rcx, [rcx+10h]
0x180009e17  call    WPP_SF_s
0x180009e1c  xor     eax, eax
0x180009e1e  jmp     loc_180009EDA
0x180009e23  mov     ebx, eax
0x180009e25  mov     [rsp+0F8h+var_B8], eax
0x180009e29  lea     rdx, WPP_GLOBAL_Control
0x180009e30  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e37  cmp     rcx, rdx
0x180009e3a  jz      short loc_180009E63
0x180009e3c  test    byte ptr [rcx+1Ch], 2
0x180009e40  jz      short loc_180009E63
0x180009e42  mov     edx, 2Eh ; '.'
0x180009e47  mov     dword ptr [rsp+0F8h+var_D8], eax
0x180009e4b  lea     r9, [rsp+0F8h+var_60]
0x180009e53  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
  ... truncated ...
```
