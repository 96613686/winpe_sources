# CFwCplLua::AddProgram(ushort *,ushort *,long,long,ushort * *,ushort * *)

- ea: `0x18002a460`
- end: `0x18002aaf6`
- name: `?AddProgram@CFwCplLua@@UEAAJPEAG0JJPEAPEAG1@Z`
- size: `1686`
- prototype: `__int64 __fastcall(CFwCplLua *this, unsigned __int16 *, unsigned __int16 *, int, int, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000994c`
- `0x18002a460`
- `0x18002c2a0`
- `0x180030e6e`
- `0x180030ea0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002a746`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a888`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a746`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a888`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a562`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a570`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a562`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a570`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002a5e6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002a7ae`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002a8e6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002a9d8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002a5e6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002a7ae`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002a8e6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002a9d8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002a637`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002a7f9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002a931`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002aa23`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002a637`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002a7f9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002a931`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002aa23`
- `FirewallAPI!FWAddFirewallRule` at `0x18002a6f8`
- `FirewallAPI!FWAddFirewallRule` at `0x18002a840`
- `FirewallAPI!FWAddFirewallRule` at `0x18002a990`
- `FirewallAPI!FWAddFirewallRule` at `0x18002aa74`
- `FirewallAPI!FWAddFirewallRule` at `0x18002a6f8`
- `FirewallAPI!FWAddFirewallRule` at `0x18002a840`
- `FirewallAPI!FWAddFirewallRule` at `0x18002a990`
- `FirewallAPI!FWAddFirewallRule` at `0x18002aa74`

## pseudocode

```c
__int64 __fastcall CFwCplLua::AddProgram(
        CFwCplLua *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        int a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7)
{
  BSTR *v8; // rdi
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // r9
  int v15; // ebx
  CFwCplLua *v16; // rcx
  __int64 v17; // rdx
  BSTR *v18; // r15
  int v20; // eax
  unsigned __int16 *v21; // rax
  __int64 v22; // r9
  CFwCplLua *v23; // rcx
  __int64 v24; // rdx
  int v25; // eax
  unsigned __int16 *v26; // rax
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  int v30; // eax
  _BYTE v31[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v32; // [rsp+38h] [rbp-C8h]
  OLECHAR *v33; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v34; // [rsp+48h] [rbp-B8h]
  int v35; // [rsp+58h] [rbp-A8h]
  int v36; // [rsp+5Ch] [rbp-A4h]
  __int16 v37; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v38; // [rsp+140h] [rbp+40h]
  int v39; // [rsp+150h] [rbp+50h]
  __int16 v40; // [rsp+154h] [rbp+54h]
  GUID pguid; // [rsp+230h] [rbp+130h] BYREF
  OLECHAR sz[40]; // [rsp+240h] [rbp+140h] BYREF

  v8 = a7;
  memset_0(v31, 0, 0x1F8u);
  pguid = 0;
  if ( !a3 || !a2 || !a6 || !a7 )
  {
    v14 = 2147942487LL;
    v15 = -2147024809;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_12;
      v17 = 38;
      goto LABEL_11;
    }
    goto LABEL_99;
  }
  v12 = -1;
  *a7 = 0;
  v13 = -1;
  *a6 = 0;
  do
    ++v13;
  while ( a3[v13] );
  if ( !(_DWORD)v13 )
  {
    v14 = 2147942487LL;
    v15 = -2147024809;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_12:
        v18 = a6;
LABEL_13:
        v8 = a7;
LABEL_14:
        if ( *v18 )
          SysFreeString(*v18);
        if ( *v8 )
          SysFreeString(*v8);
        return (unsigned int)v15;
      }
      v17 = 39;
LABEL_11:
      WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids, v14);
      goto LABEL_12;
    }
LABEL_99:
    v18 = a6;
    goto LABEL_14;
  }
  do
    ++v12;
  while ( a2[v12] );
  if ( !(_DWORD)v12 )
  {
    v14 = 2147942487LL;
    v15 = -2147024809;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_12;
      v17 = 40;
      goto LABEL_11;
    }
    goto LABEL_99;
  }
  v15 = CoCreateGuid(&pguid);
  if ( v15 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control )
      goto LABEL_99;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_12;
    v17 = 41;
LABEL_28:
    v14 = (unsigned int)v15;
    goto LABEL_11;
  }
  if ( !StringFromGUID2(&pguid, sz, 40) )
  {
    v14 = 2147942522LL;
    v15 = -2147024774;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_12;
      v17 = 42;
      goto LABEL_11;
    }
    goto LABEL_99;
  }
  v35 = a4;
  v40 |= 1u;
  v32 = 545;
  v36 = 1;
  v39 = 3;
  v37 = 6;
  v33 = sz;
  v34 = a2;
  v38 = a3;
  v15 = CFwCplLua::EnsurePolicyHandle(this);
  if ( v15 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_12;
    v17 = 43;
    goto LABEL_28;
  }
  v20 = FWAddFirewallRule(*((_QWORD *)this + 8), v31);
  v15 = v20;
  if ( v20 > 0 )
    v15 = (unsigned __int16)v20 | 0x80070000;
  if ( v15 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_12;
    v17 = 44;
    goto LABEL_28;
  }
  v21 = SysAllocString(sz);
  v18 = a6;
  *a6 = v21;
  if ( !v21 )
  {
    v22 = 2147942414LL;
    v15 = -2147024882;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v24 = 45;
    goto LABEL_47;
  }
  v37 = 17;
  v15 = CoCreateGuid(&pguid);
  if ( v15 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v24 = 46;
    goto LABEL_52;
  }
  if ( !StringFromGUID2(&pguid, sz, 40) )
  {
    v22 = 2147942522LL;
    v15 = -2147024774;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v24 = 47;
    goto LABEL_47;
  }
  v25 = FWAddFirewallRule(*((_QWORD *)this + 8), v31);
  v15 = v25;
  if ( v25 > 0 )
    v15 = (unsigned __int16)v25 | 0x80070000;
  if ( v15 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v24 = 48;
    goto LABEL_52;
  }
  v26 = SysAllocString(sz);
  *a7 = v26;
  if ( !v26 )
  {
    v22 = 2147942414LL;
    v15 = -2147024882;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v24 = 49;
    goto LABEL_47;
  }
  if ( !a5 )
    return (unsigned int)v15;
  v15 = CoCreateGuid(&pguid);
  if ( v15 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v24 = 50;
    goto LABEL_52;
  }
  if ( !StringFromGUID2(&pguid, sz, 40) )
  {
    v22 = 2147942522LL;
    v15 = -2147024774;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v24 = 51;
    goto LABEL_47;
  }
  v27 = *((_QWORD *)this + 8);
  v35 = a5;
  v37 = 6;
  v40 &= ~1u;
  v28 = FWAddFirewallRule(v27, v31);
  v15 = v28;
  if ( v28 > 0 )
    v15 = (unsigned __int16)v28 | 0x80070000;
  if ( v15 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v24 = 52;
    goto LABEL_52;
  }
  v15 = CoCreateGuid(&pguid);
  if ( v15 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v24 = 53;
    goto LABEL_52;
  }
  if ( !StringFromGUID2(&pguid, sz, 40) )
  {
    v22 = 2147942522LL;
    v15 = -2147024774;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v24 = 54;
    goto LABEL_47;
  }
  v29 = *((_QWORD *)this + 8);
  v37 = 17;
  v30 = FWAddFirewallRule(v29, v31);
  v15 = v30;
  if ( v30 > 0 )
    v15 = (unsigned __int16)v30 | 0x80070000;
  if ( v15 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v24 = 55;
LABEL_52:
    v22 = (unsigned int)v15;
LABEL_47:
    WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids, v22);
    goto LABEL_13;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18002a460  push    rbp
0x18002a462  push    rbx
0x18002a463  push    rdi
0x18002a464  push    r12
0x18002a466  push    r13
0x18002a468  push    r14
0x18002a46a  push    r15
0x18002a46c  lea     rbp, [rsp-1A0h]
0x18002a474  sub     rsp, 2A0h
0x18002a47b  mov     rax, cs:__security_cookie
0x18002a482  xor     rax, rsp
0x18002a485  mov     [rbp+1D0h+var_40], rax
0x18002a48c  mov     rbx, [rbp+1D0h+arg_28]
0x18002a493  mov     r15, r8
0x18002a496  mov     rdi, [rbp+1D0h+arg_30]
0x18002a49d  mov     r14, rdx
0x18002a4a0  mov     r13, rcx
0x18002a4a3  mov     [rsp+2D0h+var_2A8], rbx
0x18002a4a8  xor     edx, edx; Val
0x18002a4aa  mov     [rsp+2D0h+var_2B0], rdi
0x18002a4af  mov     r8d, 1F8h; Size
0x18002a4b5  lea     rcx, [rsp+2D0h+var_2A0]; void *
0x18002a4ba  mov     r12d, r9d
0x18002a4bd  call    memset_0
0x18002a4c2  xor     r9d, r9d
0x18002a4c5  xorps   xmm0, xmm0
0x18002a4c8  movups  xmmword ptr [rbp+1D0h+pguid.Data1], xmm0
0x18002a4cf  test    r15, r15
0x18002a4d2  jz      loc_18002AAB9
0x18002a4d8  test    r14, r14
0x18002a4db  jz      loc_18002AAB9
0x18002a4e1  test    rbx, rbx
0x18002a4e4  jz      loc_18002AAB9
0x18002a4ea  test    rdi, rdi
0x18002a4ed  jz      loc_18002AAB9
0x18002a4f3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a4f7  mov     [rdi], r9
0x18002a4fa  mov     rcx, rax
0x18002a4fd  mov     [rbx], r9
0x18002a500  inc     rcx
0x18002a503  cmp     [r15+rcx*2], r9w
0x18002a508  jnz     short loc_18002A500
0x18002a50a  test    ecx, ecx
0x18002a50c  jnz     loc_18002A59A
0x18002a512  mov     r9d, 80070057h
0x18002a518  mov     ebx, r9d
0x18002a51b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a522  lea     rax, WPP_GLOBAL_Control
0x18002a529  cmp     rcx, rax
0x18002a52c  jz      loc_18002AAEC
0x18002a532  mov     edi, 1
0x18002a537  test    [rcx+1Ch], dil
0x18002a53b  jz      short loc_18002A550
0x18002a53d  lea     edx, [rdi+26h]
0x18002a540  mov     rcx, [rcx+10h]
0x18002a544  lea     r8, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids
0x18002a54b  call    WPP_SF_d
0x18002a550  mov     r15, [rsp+2D0h+var_2A8]
0x18002a555  mov     rdi, [rsp+2D0h+var_2B0]
0x18002a55a  mov     rcx, [r15]; bstrString
0x18002a55d  test    rcx, rcx
0x18002a560  jz      short loc_18002A568
0x18002a562  call    cs:__imp_SysFreeString
0x18002a568  mov     rcx, [rdi]; bstrString
0x18002a56b  test    rcx, rcx
0x18002a56e  jz      short loc_18002A576
0x18002a570  call    cs:__imp_SysFreeString
0x18002a576  mov     eax, ebx
0x18002a578  mov     rcx, [rbp+1D0h+var_40]
0x18002a57f  xor     rcx, rsp; StackCookie
0x18002a582  call    __security_check_cookie
0x18002a587  add     rsp, 2A0h
0x18002a58e  pop     r15
0x18002a590  pop     r14
0x18002a592  pop     r13
0x18002a594  pop     r12
0x18002a596  pop     rdi
0x18002a597  pop     rbx
0x18002a598  pop     rbp
0x18002a599  retn
0x18002a59a  inc     rax
0x18002a59d  cmp     [r14+rax*2], r9w
0x18002a5a2  jnz     short loc_18002A59A
0x18002a5a4  test    eax, eax
0x18002a5a6  jnz     short loc_18002A5DF
0x18002a5a8  mov     r9d, 80070057h
0x18002a5ae  mov     ebx, r9d
0x18002a5b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a5b8  lea     rax, WPP_GLOBAL_Control
0x18002a5bf  cmp     rcx, rax
0x18002a5c2  jz      loc_18002AAEC
0x18002a5c8  mov     edi, 1
0x18002a5cd  test    [rcx+1Ch], dil
0x18002a5d1  jz      loc_18002A550
0x18002a5d7  lea     edx, [rdi+27h]
0x18002a5da  jmp     loc_18002A540
0x18002a5df  lea     rcx, [rbp+1D0h+pguid]; pguid
0x18002a5e6  call    cs:__imp_CoCreateGuid
0x18002a5ec  mov     ebx, eax
0x18002a5ee  test    eax, eax
0x18002a5f0  jns     short loc_18002A623
0x18002a5f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a5f9  lea     rax, WPP_GLOBAL_Control
0x18002a600  cmp     rcx, rax
0x18002a603  jz      loc_18002AAEC
0x18002a609  mov     edi, 1
0x18002a60e  test    [rcx+1Ch], dil
0x18002a612  jz      loc_18002A550
0x18002a618  lea     edx, [rdi+28h]
0x18002a61b  mov     r9d, ebx
0x18002a61e  jmp     loc_18002A540
0x18002a623  mov     r8d, 28h ; '('; cchMax
0x18002a629  lea     rdx, [rbp+1D0h+sz]; lpsz
0x18002a630  lea     rcx, [rbp+1D0h+pguid]; rguid
0x18002a637  call    cs:__imp_StringFromGUID2
0x18002a63d  test    eax, eax
0x18002a63f  jnz     short loc_18002A678
0x18002a641  mov     r9d, 8007007Ah
0x18002a647  mov     ebx, r9d
0x18002a64a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a651  lea     rax, WPP_GLOBAL_Control
0x18002a658  cmp     rcx, rax
0x18002a65b  jz      loc_18002AAEC
0x18002a661  mov     edi, 1
0x18002a666  test    [rcx+1Ch], dil
0x18002a66a  jz      loc_18002A550
0x18002a670  lea     edx, [rdi+29h]
0x18002a673  jmp     loc_18002A540
0x18002a678  mov     edi, 1
0x18002a67d  mov     [rsp+2D0h+var_278], r12d
0x18002a682  or      [rbp+1D0h+var_17C], di
0x18002a686  mov     eax, 221h
0x18002a68b  mov     [rsp+2D0h+var_298], ax
0x18002a690  mov     rcx, r13; this
0x18002a693  mov     [rsp+2D0h+var_274], edi
0x18002a697  lea     eax, [rdi+5]
0x18002a69a  mov     [rbp+1D0h+var_180], 3
0x18002a6a1  mov     [rsp+2D0h+var_270], ax
0x18002a6a6  lea     rax, [rbp+1D0h+sz]
0x18002a6ad  mov     [rsp+2D0h+var_290], rax
0x18002a6b2  mov     [rsp+2D0h+var_288], r14
0x18002a6b7  mov     [rbp+1D0h+var_190], r15
0x18002a6bb  call    ?EnsurePolicyHandle@CFwCplLua@@AEAAJXZ; CFwCplLua::EnsurePolicyHandle(void)
0x18002a6c0  mov     ebx, eax
0x18002a6c2  test    eax, eax
0x18002a6c4  jns     short loc_18002A6EF
0x18002a6c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a6cd  lea     rax, WPP_GLOBAL_Control
0x18002a6d4  cmp     rcx, rax
0x18002a6d7  jz      loc_18002A550
0x18002a6dd  test    [rcx+1Ch], dil
0x18002a6e1  jz      loc_18002A550
0x18002a6e7  lea     edx, [rdi+2Ah]
0x18002a6ea  jmp     loc_18002A61B
0x18002a6ef  mov     rcx, [r13+40h]
0x18002a6f3  lea     rdx, [rsp+2D0h+var_2A0]
0x18002a6f8  call    cs:__imp_FWAddFirewallRule
0x18002a6fe  mov     ebx, eax
0x18002a700  mov     r12d, 80070000h
0x18002a706  test    eax, eax
0x18002a708  jle     short loc_18002A710
0x18002a70a  movzx   ebx, ax
0x18002a70d  or      ebx, r12d
0x18002a710  test    ebx, ebx
0x18002a712  jns     short loc_18002A73F
0x18002a714  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a71b  lea     rax, WPP_GLOBAL_Control
0x18002a722  cmp     rcx, rax
0x18002a725  jz      loc_18002A550
0x18002a72b  test    [rcx+1Ch], dil
0x18002a72f  jz      loc_18002A550
0x18002a735  mov     edx, 2Ch ; ','
0x18002a73a  jmp     loc_18002A61B
0x18002a73f  lea     rcx, [rbp+1D0h+sz]; psz
0x18002a746  call    cs:__imp_SysAllocString
0x18002a74c  mov     r15, [rsp+2D0h+var_2A8]
0x18002a751  mov     [r15], rax
0x18002a754  test    rax, rax
0x18002a757  jnz     short loc_18002A79D
0x18002a759  mov     r9d, 8007000Eh
0x18002a75f  mov     ebx, r9d
0x18002a762  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a769  lea     rax, WPP_GLOBAL_Control
0x18002a770  cmp     rcx, rax
0x18002a773  jz      loc_18002A555
0x18002a779  test    [rcx+1Ch], dil
0x18002a77d  jz      loc_18002A555
0x18002a783  mov     edx, 2Dh ; '-'
0x18002a788  mov     rcx, [rcx+10h]
0x18002a78c  lea     r8, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids
0x18002a793  call    WPP_SF_d
0x18002a798  jmp     loc_18002A555
0x18002a79d  mov     eax, 11h
0x18002a7a2  lea     rcx, [rbp+1D0h+pguid]; pguid
0x18002a7a9  mov     [rsp+2D0h+var_270], ax
0x18002a7ae  call    cs:__imp_CoCreateGuid
0x18002a7b4  mov     ebx, eax
0x18002a7b6  test    eax, eax
0x18002a7b8  jns     short loc_18002A7E5
0x18002a7ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7c1  lea     rax, WPP_GLOBAL_Control
0x18002a7c8  cmp     rcx, rax
0x18002a7cb  jz      loc_18002A555
0x18002a7d1  test    [rcx+1Ch], dil
0x18002a7d5  jz      loc_18002A555
0x18002a7db  mov     edx, 2Eh ; '.'
0x18002a7e0  mov     r9d, ebx
0x18002a7e3  jmp     short loc_18002A788
0x18002a7e5  mov     r8d, 28h ; '('; cchMax
0x18002a7eb  lea     rdx, [rbp+1D0h+sz]; lpsz
0x18002a7f2  lea     rcx, [rbp+1D0h+pguid]; rguid
0x18002a7f9  call    cs:__imp_StringFromGUID2
0x18002a7ff  test    eax, eax
0x18002a801  jnz     short loc_18002A837
0x18002a803  mov     r9d, 8007007Ah
0x18002a809  mov     ebx, r9d
0x18002a80c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a813  lea     rax, WPP_GLOBAL_Control
0x18002a81a  cmp     rcx, rax
0x18002a81d  jz      loc_18002A555
0x18002a823  test    [rcx+1Ch], dil
0x18002a827  jz      loc_18002A555
0x18002a82d  mov     edx, 2Fh ; '/'
0x18002a832  jmp     loc_18002A788
0x18002a837  mov     rcx, [r13+40h]
0x18002a83b  lea     rdx, [rsp+2D0h+var_2A0]
0x18002a840  call    cs:__imp_FWAddFirewallRule
0x18002a846  mov     ebx, eax
0x18002a848  test    eax, eax
0x18002a84a  jle     short loc_18002A852
0x18002a84c  movzx   ebx, ax
0x18002a84f  or      ebx, r12d
0x18002a852  test    ebx, ebx
0x18002a854  jns     short loc_18002A881
0x18002a856  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a85d  lea     rax, WPP_GLOBAL_Control
0x18002a864  cmp     rcx, rax
0x18002a867  jz      loc_18002A555
0x18002a86d  test    [rcx+1Ch], dil
0x18002a871  jz      loc_18002A555
0x18002a877  mov     edx, 30h ; '0'
0x18002a87c  jmp     loc_18002A7E0
0x18002a881  lea     rcx, [rbp+1D0h+sz]; psz
0x18002a888  call    cs:__imp_SysAllocString
0x18002a88e  mov     rcx, [rsp+2D0h+var_2B0]
0x18002a893  mov     [rcx], rax
0x18002a896  test    rax, rax
0x18002a899  jnz     short loc_18002A8CF
0x18002a89b  mov     r9d, 8007000Eh
0x18002a8a1  mov     ebx, r9d
0x18002a8a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a8ab  lea     rax, WPP_GLOBAL_Control
0x18002a8b2  cmp     rcx, rax
0x18002a8b5  jz      loc_18002A555
0x18002a8bb  test    [rcx+1Ch], dil
0x18002a8bf  jz      loc_18002A555
0x18002a8c5  mov     edx, 31h ; '1'
0x18002a8ca  jmp     loc_18002A788
0x18002a8cf  mov     r14d, [rbp+1D0h+arg_20]
0x18002a8d6  test    r14d, r14d
0x18002a8d9  jz      loc_18002A576
0x18002a8df  lea     rcx, [rbp+1D0h+pguid]; pguid
0x18002a8e6  call    cs:__imp_CoCreateGuid
0x18002a8ec  mov     ebx, eax
0x18002a8ee  test    eax, eax
0x18002a8f0  jns     short loc_18002A91D
0x18002a8f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a8f9  lea     rax, WPP_GLOBAL_Control
0x18002a900  cmp     rcx, rax
0x18002a903  jz      loc_18002A555
0x18002a909  test    [rcx+1Ch], dil
0x18002a90d  jz      loc_18002A555
0x18002a913  mov     edx, 32h ; '2'
0x18002a918  jmp     loc_18002A7E0
0x18002a91d  mov     r8d, 28h ; '('; cchMax
0x18002a923  lea     rdx, [rbp+1D0h+sz]; lpsz
0x18002a92a  lea     rcx, [rbp+1D0h+pguid]; rguid
0x18002a931  call    cs:__imp_StringFromGUID2
0x18002a937  test    eax, eax
0x18002a939  jnz     short loc_18002A96F
0x18002a93b  mov     r9d, 8007007Ah
0x18002a941  mov     ebx, r9d
0x18002a944  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a94b  lea     rax, WPP_GLOBAL_Control
0x18002a952  cmp     rcx, rax
0x18002a955  jz      loc_18002A555
0x18002a95b  test    [rcx+1Ch], dil
0x18002a95f  jz      loc_18002A555
0x18002a965  mov     edx, 33h ; '3'
0x18002a96a  jmp     loc_18002A788
0x18002a96f  mov     rcx, [r13+40h]
0x18002a973  lea     rdx, [rsp+2D0h+var_2A0]
0x18002a978  mov     eax, 6
0x18002a97d  mov     [rsp+2D0h+var_278], r14d
0x18002a982  mov     [rsp+2D0h+var_270], ax
0x18002a987  mov     eax, 0FFFEh
0x18002a98c  and     [rbp+1D0h+var_17C], ax
0x18002a990  call    cs:__imp_FWAddFirewallRule
0x18002a996  mov     ebx, eax
0x18002a998  test    eax, eax
  ... truncated ...
```
