# CFwCplLua::AddGlobalPort(ushort *,long,long,long,long,ushort * *)

- ea: `0x18002a0f0`
- end: `0x18002a457`
- name: `?AddGlobalPort@CFwCplLua@@UEAAJPEAGJJJJPEAPEAG@Z`
- size: `871`
- prototype: `__int64 __fastcall(CFwCplLua *this, unsigned __int16 *, __int16, __int16, int, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000994c`
- `0x18002a0f0`
- `0x18002c2a0`
- `0x180030e6e`
- `0x180030ea0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002a2e4`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a2e4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a425`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a425`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002a170`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002a345`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002a170`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002a345`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002a1be`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002a390`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002a1be`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002a390`
- `FirewallAPI!FWAddFirewallRule` at `0x18002a298`
- `FirewallAPI!FWAddFirewallRule` at `0x18002a3cc`
- `FirewallAPI!FWAddFirewallRule` at `0x18002a298`
- `FirewallAPI!FWAddFirewallRule` at `0x18002a3cc`

## pseudocode

```c
__int64 __fastcall CFwCplLua::AddGlobalPort(
        CFwCplLua *this,
        unsigned __int16 *a2,
        __int16 a3,
        __int16 a4,
        int a5,
        int a6,
        unsigned __int16 **a7)
{
  int v11; // ebx
  CFwCplLua *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // eax
  unsigned __int16 *v16; // rax
  int v17; // eax
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v20[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v21; // [rsp+38h] [rbp-C8h]
  OLECHAR *v22; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v23; // [rsp+48h] [rbp-B8h]
  int v24; // [rsp+58h] [rbp-A8h]
  int v25; // [rsp+5Ch] [rbp-A4h]
  __int16 v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+70h] [rbp-90h]
  int *v28; // [rsp+78h] [rbp-88h]
  int v29; // [rsp+150h] [rbp+50h]
  __int16 v30; // [rsp+154h] [rbp+54h]
  GUID pguid; // [rsp+230h] [rbp+130h] BYREF
  OLECHAR sz[40]; // [rsp+240h] [rbp+140h] BYREF

  v19 = 0;
  memset_0(v20, 0, 0x1F8u);
  pguid = 0;
  if ( !a7 || !a2 )
  {
    v11 = -2147024809;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 56;
      goto LABEL_41;
    }
    goto LABEL_43;
  }
  v11 = CoCreateGuid(&pguid);
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 57;
LABEL_41:
      v14 = (unsigned int)v11;
      goto LABEL_42;
    }
    goto LABEL_43;
  }
  if ( !StringFromGUID2(&pguid, sz, 40) )
  {
    v14 = 2147942522LL;
    v11 = -2147024774;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_43;
    v13 = 58;
    goto LABEL_42;
  }
  v26 = a4;
  v30 |= 1u;
  v21 = 545;
  v25 = 1;
  v28 = &v19;
  v24 = a5;
  v22 = sz;
  v27 = 1;
  HIWORD(v19) = a3;
  LOWORD(v19) = a3;
  v29 = 3;
  v23 = a2;
  v11 = CFwCplLua::EnsurePolicyHandle(this);
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 59;
      goto LABEL_41;
    }
LABEL_43:
    if ( *a7 )
      SysFreeString(*a7);
    return (unsigned int)v11;
  }
  v15 = FWAddFirewallRule(*((_QWORD *)this + 8), v20);
  v11 = v15;
  if ( v15 > 0 )
    v11 = (unsigned __int16)v15 | 0x80070000;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 60;
      goto LABEL_41;
    }
    goto LABEL_43;
  }
  v16 = SysAllocString(sz);
  *a7 = v16;
  if ( !v16 )
  {
    v11 = -2147024882;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 61;
      goto LABEL_41;
    }
    goto LABEL_43;
  }
  if ( !a6 )
    return (unsigned int)v11;
  v24 = a6;
  v30 &= ~1u;
  v11 = CoCreateGuid(&pguid);
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 62;
      goto LABEL_41;
    }
    goto LABEL_43;
  }
  if ( !StringFromGUID2(&pguid, sz, 40) )
  {
    v14 = 2147942522LL;
    v11 = -2147024774;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_43;
    v13 = 63;
LABEL_42:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids, v14);
    goto LABEL_43;
  }
  v17 = FWAddFirewallRule(*((_QWORD *)this + 8), v20);
  v11 = v17;
  if ( v17 > 0 )
    v11 = (unsigned __int16)v17 | 0x80070000;
  if ( v11 < 0 )
    goto LABEL_43;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002a0f0  mov     [rsp-8+arg_10], rbx
0x18002a0f5  push    rbp
0x18002a0f6  push    rsi
0x18002a0f7  push    rdi
0x18002a0f8  push    r12
0x18002a0fa  push    r13
0x18002a0fc  push    r14
0x18002a0fe  push    r15
0x18002a100  lea     rbp, [rsp-1A0h]
0x18002a108  sub     rsp, 2A0h
0x18002a10f  mov     rax, cs:__security_cookie
0x18002a116  xor     rax, rsp
0x18002a119  mov     [rbp+1D0h+var_40], rax
0x18002a120  mov     r13, [rbp+1D0h+arg_30]
0x18002a127  mov     r15d, r8d
0x18002a12a  mov     rsi, rdx
0x18002a12d  mov     [rsp+2D0h+var_2B0], 0
0x18002a135  mov     r14, rcx
0x18002a138  xor     edx, edx; Val
0x18002a13a  mov     r8d, 1F8h; Size
0x18002a140  lea     rcx, [rsp+2D0h+var_2A0]; void *
0x18002a145  mov     r12d, r9d
0x18002a148  call    memset_0
0x18002a14d  xorps   xmm0, xmm0
0x18002a150  movups  xmmword ptr [rbp+1D0h+pguid.Data1], xmm0
0x18002a157  test    r13, r13
0x18002a15a  jz      loc_18002A3E3
0x18002a160  test    rsi, rsi
0x18002a163  jz      loc_18002A3E3
0x18002a169  lea     rcx, [rbp+1D0h+pguid]; pguid
0x18002a170  call    cs:__imp_CoCreateGuid
0x18002a176  mov     ebx, eax
0x18002a178  test    eax, eax
0x18002a17a  jns     short loc_18002A1AA
0x18002a17c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a183  lea     rax, WPP_GLOBAL_Control
0x18002a18a  cmp     rcx, rax
0x18002a18d  jz      loc_18002A41C
0x18002a193  mov     edi, 1
0x18002a198  test    [rcx+1Ch], dil
0x18002a19c  jz      loc_18002A41C
0x18002a1a2  lea     edx, [rdi+38h]
0x18002a1a5  jmp     loc_18002A409
0x18002a1aa  mov     r8d, 28h ; '('; cchMax
0x18002a1b0  lea     rdx, [rbp+1D0h+sz]; lpsz
0x18002a1b7  lea     rcx, [rbp+1D0h+pguid]; rguid
0x18002a1be  call    cs:__imp_StringFromGUID2
0x18002a1c4  test    eax, eax
0x18002a1c6  jnz     short loc_18002A1FF
0x18002a1c8  mov     r9d, 8007007Ah
0x18002a1ce  mov     ebx, r9d
0x18002a1d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a1d8  lea     rax, WPP_GLOBAL_Control
0x18002a1df  cmp     rcx, rax
0x18002a1e2  jz      loc_18002A41C
0x18002a1e8  mov     edi, 1
0x18002a1ed  test    [rcx+1Ch], dil
0x18002a1f1  jz      loc_18002A41C
0x18002a1f7  lea     edx, [rdi+39h]
0x18002a1fa  jmp     loc_18002A40C
0x18002a1ff  mov     edi, 1
0x18002a204  mov     [rsp+2D0h+var_270], r12w
0x18002a20a  or      [rbp+1D0h+var_17C], di
0x18002a20e  mov     eax, 221h
0x18002a213  mov     [rsp+2D0h+var_298], ax
0x18002a218  mov     rcx, r14; this
0x18002a21b  lea     rax, [rsp+2D0h+var_2B0]
0x18002a220  mov     [rsp+2D0h+var_274], edi
0x18002a224  mov     [rsp+2D0h+var_258], rax
0x18002a229  mov     eax, [rbp+1D0h+arg_20]
0x18002a22f  mov     [rsp+2D0h+var_278], eax
0x18002a233  lea     rax, [rbp+1D0h+sz]
0x18002a23a  mov     [rsp+2D0h+var_290], rax
0x18002a23f  mov     [rsp+2D0h+var_260], edi
0x18002a243  mov     word ptr [rsp+2D0h+var_2B0+2], r15w
0x18002a249  mov     word ptr [rsp+2D0h+var_2B0], r15w
0x18002a24f  mov     [rbp+1D0h+var_180], 3
0x18002a256  mov     [rsp+2D0h+var_288], rsi
0x18002a25b  call    ?EnsurePolicyHandle@CFwCplLua@@AEAAJXZ; CFwCplLua::EnsurePolicyHandle(void)
0x18002a260  mov     ebx, eax
0x18002a262  test    eax, eax
0x18002a264  jns     short loc_18002A28F
0x18002a266  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a26d  lea     rax, WPP_GLOBAL_Control
0x18002a274  cmp     rcx, rax
0x18002a277  jz      loc_18002A41C
0x18002a27d  test    [rcx+1Ch], dil
0x18002a281  jz      loc_18002A41C
0x18002a287  lea     edx, [rdi+3Ah]
0x18002a28a  jmp     loc_18002A409
0x18002a28f  mov     rcx, [r14+40h]
0x18002a293  lea     rdx, [rsp+2D0h+var_2A0]
0x18002a298  call    cs:__imp_FWAddFirewallRule
0x18002a29e  mov     ebx, eax
0x18002a2a0  mov     esi, 80070000h
0x18002a2a5  test    eax, eax
0x18002a2a7  jle     short loc_18002A2AE
0x18002a2a9  movzx   ebx, ax
0x18002a2ac  or      ebx, esi
0x18002a2ae  test    ebx, ebx
0x18002a2b0  jns     short loc_18002A2DD
0x18002a2b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a2b9  lea     rax, WPP_GLOBAL_Control
0x18002a2c0  cmp     rcx, rax
0x18002a2c3  jz      loc_18002A41C
0x18002a2c9  test    [rcx+1Ch], dil
0x18002a2cd  jz      loc_18002A41C
0x18002a2d3  mov     edx, 3Ch ; '<'
0x18002a2d8  jmp     loc_18002A409
0x18002a2dd  lea     rcx, [rbp+1D0h+sz]; psz
0x18002a2e4  call    cs:__imp_SysAllocString
0x18002a2ea  mov     [r13+0], rax
0x18002a2ee  test    rax, rax
0x18002a2f1  jnz     short loc_18002A323
0x18002a2f3  mov     ebx, 8007000Eh
0x18002a2f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a2ff  lea     rax, WPP_GLOBAL_Control
0x18002a306  cmp     rcx, rax
0x18002a309  jz      loc_18002A41C
0x18002a30f  test    [rcx+1Ch], dil
0x18002a313  jz      loc_18002A41C
0x18002a319  mov     edx, 3Dh ; '='
0x18002a31e  jmp     loc_18002A409
0x18002a323  mov     eax, [rbp+1D0h+arg_28]
0x18002a329  test    eax, eax
0x18002a32b  jz      loc_18002A42B
0x18002a331  mov     ecx, 0FFFEh
0x18002a336  mov     [rsp+2D0h+var_278], eax
0x18002a33a  and     [rbp+1D0h+var_17C], cx
0x18002a33e  lea     rcx, [rbp+1D0h+pguid]; pguid
0x18002a345  call    cs:__imp_CoCreateGuid
0x18002a34b  mov     ebx, eax
0x18002a34d  test    eax, eax
0x18002a34f  jns     short loc_18002A37C
0x18002a351  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a358  lea     rax, WPP_GLOBAL_Control
0x18002a35f  cmp     rcx, rax
0x18002a362  jz      loc_18002A41C
0x18002a368  test    [rcx+1Ch], dil
0x18002a36c  jz      loc_18002A41C
0x18002a372  mov     edx, 3Eh ; '>'
0x18002a377  jmp     loc_18002A409
0x18002a37c  mov     r8d, 28h ; '('; cchMax
0x18002a382  lea     rdx, [rbp+1D0h+sz]; lpsz
0x18002a389  lea     rcx, [rbp+1D0h+pguid]; rguid
0x18002a390  call    cs:__imp_StringFromGUID2
0x18002a396  test    eax, eax
0x18002a398  jnz     short loc_18002A3C3
0x18002a39a  mov     r9d, 8007007Ah
0x18002a3a0  mov     ebx, r9d
0x18002a3a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a3aa  lea     rax, WPP_GLOBAL_Control
0x18002a3b1  cmp     rcx, rax
0x18002a3b4  jz      short loc_18002A41C
0x18002a3b6  test    [rcx+1Ch], dil
0x18002a3ba  jz      short loc_18002A41C
0x18002a3bc  mov     edx, 3Fh ; '?'
0x18002a3c1  jmp     short loc_18002A40C
0x18002a3c3  mov     rcx, [r14+40h]
0x18002a3c7  lea     rdx, [rsp+2D0h+var_2A0]
0x18002a3cc  call    cs:__imp_FWAddFirewallRule
0x18002a3d2  mov     ebx, eax
0x18002a3d4  test    eax, eax
0x18002a3d6  jle     short loc_18002A3DD
0x18002a3d8  movzx   ebx, ax
0x18002a3db  or      ebx, esi
0x18002a3dd  test    ebx, ebx
0x18002a3df  jns     short loc_18002A42B
0x18002a3e1  jmp     short loc_18002A41C
0x18002a3e3  mov     ebx, 80070057h
0x18002a3e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a3ef  lea     rax, WPP_GLOBAL_Control
0x18002a3f6  cmp     rcx, rax
0x18002a3f9  jz      short loc_18002A41C
0x18002a3fb  mov     edi, 1
0x18002a400  test    [rcx+1Ch], dil
0x18002a404  jz      short loc_18002A41C
0x18002a406  lea     edx, [rdi+37h]
0x18002a409  mov     r9d, ebx
0x18002a40c  mov     rcx, [rcx+10h]
0x18002a410  lea     r8, WPP_f27af61f95773e14f7ebc838a76e1066_Traceguids
0x18002a417  call    WPP_SF_d
0x18002a41c  mov     rcx, [r13+0]; bstrString
0x18002a420  test    rcx, rcx
0x18002a423  jz      short loc_18002A42B
0x18002a425  call    cs:__imp_SysFreeString
0x18002a42b  mov     eax, ebx
0x18002a42d  mov     rcx, [rbp+1D0h+var_40]
0x18002a434  xor     rcx, rsp; StackCookie
0x18002a437  call    __security_check_cookie
0x18002a43c  mov     rbx, [rsp+2D0h+arg_10]
0x18002a444  add     rsp, 2A0h
0x18002a44b  pop     r15
0x18002a44d  pop     r14
0x18002a44f  pop     r13
0x18002a451  pop     r12
0x18002a453  pop     rdi
0x18002a454  pop     rsi
0x18002a455  pop     rbp
0x18002a456  retn
```
