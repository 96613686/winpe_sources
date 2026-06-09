# FwSplitRule(void *,_tag_FW_RULE *,ulong)

- ea: `0x180032840`
- end: `0x180032b0d`
- name: `?FwSplitRule@@YAJPEAXPEAU_tag_FW_RULE@@K@Z`
- size: `717`
- prototype: `__int64 __fastcall(void *, struct _tag_FW_RULE *, unsigned int)`
- caller_count: `9`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800022c0`
- `0x18000283c`
- `0x180015fb0`
- `0x180032fe0`
- `0x18003308c`
- `0x18003bd9c`
- `0x180047618`
- `0x1800479f0`
- `0x1800484dc`

## callees

- `0x180005e0c`
- `0x180014110`
- `0x180014720`
- `0x1800294b0`
- `0x18002a1f4`
- `0x180032840`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800329f2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800329f2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800329a4`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800329a4`
- `fwbase!FwBaseFree` at `0x180032a91`
- `fwbase!FwBaseFree` at `0x180032a91`
- `fwbase!FwStringCopy` at `0x180032aac`
- `fwbase!FwStringCopy` at `0x180032aac`

## pseudocode

```c
__int64 __fastcall FwSplitRule(__int64 a1, struct _tag_FW_RULE *a2, int a3)
{
  int v6; // edi
  _OWORD *v7; // rcx
  __int64 v8; // rdx
  struct _tag_FW_RULE *v9; // rax
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int64 v23; // rax
  int v24; // eax
  int v25; // ebx
  FwPolicy2 *v26; // rcx
  __int64 v27; // rdx
  int v28; // edi
  int v29; // eax
  OLECHAR *v30; // rcx
  _BYTE Src[16]; // [rsp+20h] [rbp-E0h] BYREF
  OLECHAR *v33; // [rsp+30h] [rbp-D0h]
  int v34; // [rsp+48h] [rbp-B8h]
  GUID pguid; // [rsp+220h] [rbp+120h] BYREF
  OLECHAR sz[256]; // [rsp+230h] [rbp+130h] BYREF

  pguid = 0;
  memset_0(sz, 0, sizeof(sz));
  v6 = *((_DWORD *)a2 + 10);
  v7 = Src;
  v8 = 3;
  v9 = a2;
  do
  {
    v10 = *((_OWORD *)v9 + 1);
    *v7 = *(_OWORD *)v9;
    v11 = *((_OWORD *)v9 + 2);
    v7[1] = v10;
    v12 = *((_OWORD *)v9 + 3);
    v7[2] = v11;
    v13 = *((_OWORD *)v9 + 4);
    v7[3] = v12;
    v14 = *((_OWORD *)v9 + 5);
    v7[4] = v13;
    v15 = *((_OWORD *)v9 + 6);
    v7[5] = v14;
    v16 = *((_OWORD *)v9 + 7);
    v9 = (struct _tag_FW_RULE *)((char *)v9 + 128);
    v7[6] = v15;
    v7[7] = v16;
    v7 += 8;
    --v8;
  }
  while ( v8 );
  v17 = *((_OWORD *)v9 + 1);
  *v7 = *(_OWORD *)v9;
  v18 = *((_OWORD *)v9 + 2);
  v7[1] = v17;
  v19 = *((_OWORD *)v9 + 3);
  v7[2] = v18;
  v20 = *((_OWORD *)v9 + 4);
  v7[3] = v19;
  v21 = *((_OWORD *)v9 + 5);
  v7[4] = v20;
  v22 = *((_OWORD *)v9 + 6);
  v23 = *((_QWORD *)v9 + 14);
  v7[5] = v21;
  v7[6] = v22;
  *((_QWORD *)v7 + 14) = v23;
  v34 = (unsigned __int8)v6 & (unsigned __int8)~(_BYTE)a3 & 7;
  v24 = FWSetFirewallRule(a1, Src);
  v25 = v24;
  if ( !v24 )
    goto LABEL_11;
  if ( v24 > 0 )
    v25 = (unsigned __int16)v24 | 0x80070000;
  if ( v25 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v27 = 78;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v26 + 2), v27, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, (unsigned int)v25);
    }
  }
  else
  {
LABEL_11:
    v25 = CoCreateGuid(&pguid);
    if ( v25 >= 0 )
    {
      if ( StringFromGUID2(&pguid, sz, 256) )
      {
        v28 = a3 & v6;
        v33 = sz;
        v34 = v28;
        v29 = FWAddFirewallRule(a1, Src);
        v25 = v29;
        if ( !v29 )
          goto LABEL_26;
        if ( v29 > 0 )
          v25 = (unsigned __int16)v29 | 0x80070000;
        if ( v25 < 0 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v27 = 81;
            goto LABEL_10;
          }
        }
        else
        {
LABEL_26:
          FwBaseFree(*((_QWORD *)a2 + 2));
          v30 = v33;
          *((_QWORD *)a2 + 2) = 0;
          v25 = FwStringCopy(v30, (char *)a2 + 16);
          if ( v25 >= 0 )
          {
            *((_DWORD *)a2 + 10) = v28;
            return (unsigned int)v25;
          }
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v27 = 82;
            goto LABEL_10;
          }
        }
      }
      else
      {
        v25 = -2147024774;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v27 = 80;
          goto LABEL_10;
        }
      }
    }
    else
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v27 = 79;
        goto LABEL_10;
      }
    }
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x180032840  mov     [rsp-8+arg_18], rbx
0x180032845  push    rbp
0x180032846  push    rsi
0x180032847  push    rdi
0x180032848  push    r14
0x18003284a  push    r15
0x18003284c  lea     rbp, [rsp-340h]
0x180032854  sub     rsp, 440h
0x18003285b  mov     rax, cs:__security_cookie
0x180032862  xor     rax, rsp
0x180032865  mov     [rbp+360h+var_30], rax
0x18003286c  mov     r15d, r8d
0x18003286f  mov     rsi, rdx
0x180032872  mov     r14, rcx
0x180032875  xorps   xmm0, xmm0
0x180032878  xor     edx, edx; Val
0x18003287a  lea     rcx, [rbp+360h+sz]; void *
0x180032881  mov     r8d, 200h; Size
0x180032887  movups  xmmword ptr [rbp+360h+pguid.Data1], xmm0
0x18003288e  call    memset_0
0x180032893  mov     edi, [rsi+28h]
0x180032896  lea     rcx, [rsp+460h+Src]
0x18003289b  mov     edx, 3
0x1800328a0  mov     rax, rsi
0x1800328a3  lea     r8d, [rdx+7Dh]
0x1800328a7  movups  xmm0, xmmword ptr [rax]
0x1800328aa  movups  xmm1, xmmword ptr [rax+10h]
0x1800328ae  movups  xmmword ptr [rcx], xmm0
0x1800328b1  movups  xmm0, xmmword ptr [rax+20h]
0x1800328b5  movups  xmmword ptr [rcx+10h], xmm1
0x1800328b9  movups  xmm1, xmmword ptr [rax+30h]
0x1800328bd  movups  xmmword ptr [rcx+20h], xmm0
0x1800328c1  movups  xmm0, xmmword ptr [rax+40h]
0x1800328c5  movups  xmmword ptr [rcx+30h], xmm1
0x1800328c9  movups  xmm1, xmmword ptr [rax+50h]
0x1800328cd  movups  xmmword ptr [rcx+40h], xmm0
0x1800328d1  movups  xmm0, xmmword ptr [rax+60h]
0x1800328d5  movups  xmmword ptr [rcx+50h], xmm1
0x1800328d9  movups  xmm1, xmmword ptr [rax+70h]
0x1800328dd  add     rax, r8
0x1800328e0  movups  xmmword ptr [rcx+60h], xmm0
0x1800328e4  movups  xmmword ptr [rcx+70h], xmm1
0x1800328e8  add     rcx, r8
0x1800328eb  sub     rdx, 1
0x1800328ef  jnz     short loc_1800328A7
0x1800328f1  movups  xmm0, xmmword ptr [rax]
0x1800328f4  lea     rdx, [rsp+460h+Src]; Src
0x1800328f9  movups  xmm1, xmmword ptr [rax+10h]
0x1800328fd  movups  xmmword ptr [rcx], xmm0
0x180032900  movups  xmm0, xmmword ptr [rax+20h]
0x180032904  movups  xmmword ptr [rcx+10h], xmm1
0x180032908  movups  xmm1, xmmword ptr [rax+30h]
0x18003290c  movups  xmmword ptr [rcx+20h], xmm0
0x180032910  movups  xmm0, xmmword ptr [rax+40h]
0x180032914  movups  xmmword ptr [rcx+30h], xmm1
0x180032918  movups  xmm1, xmmword ptr [rax+50h]
0x18003291c  movups  xmmword ptr [rcx+40h], xmm0
0x180032920  movups  xmm0, xmmword ptr [rax+60h]
0x180032924  mov     rax, [rax+70h]
0x180032928  movups  xmmword ptr [rcx+50h], xmm1
0x18003292c  movups  xmmword ptr [rcx+60h], xmm0
0x180032930  mov     [rcx+70h], rax
0x180032934  mov     eax, r15d
0x180032937  not     eax
0x180032939  mov     rcx, r14; __int64
0x18003293c  and     eax, edi
0x18003293e  and     eax, 7
0x180032941  mov     [rsp+460h+var_418], eax
0x180032945  call    FWSetFirewallRule
0x18003294a  mov     ebx, eax
0x18003294c  test    eax, eax
0x18003294e  jz      short loc_18003299D
0x180032950  jle     short loc_18003295B
0x180032952  movzx   ebx, ax
0x180032955  or      ebx, 80070000h
0x18003295b  test    ebx, ebx
0x18003295d  jns     short loc_18003299D
0x18003295f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032966  lea     rax, WPP_GLOBAL_Control
0x18003296d  cmp     rcx, rax
0x180032970  jz      loc_180032AE4
0x180032976  test    byte ptr [rcx+1Ch], 1
0x18003297a  jz      loc_180032AE4
0x180032980  mov     edx, 4Eh ; 'N'
0x180032985  mov     rcx, [rcx+10h]
0x180032989  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x180032990  mov     r9d, ebx
0x180032993  call    WPP_SF_d
0x180032998  jmp     loc_180032AE4
0x18003299d  lea     rcx, [rbp+360h+pguid]; pguid
0x1800329a4  call    cs:__imp_CoCreateGuid
0x1800329ab  nop     dword ptr [rax+rax+00h]
0x1800329b0  mov     ebx, eax
0x1800329b2  test    eax, eax
0x1800329b4  jns     short loc_1800329DE
0x1800329b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800329bd  lea     rax, WPP_GLOBAL_Control
0x1800329c4  cmp     rcx, rax
0x1800329c7  jz      loc_180032AE4
0x1800329cd  test    byte ptr [rcx+1Ch], 1
0x1800329d1  jz      loc_180032AE4
0x1800329d7  mov     edx, 4Fh ; 'O'
0x1800329dc  jmp     short loc_180032985
0x1800329de  mov     r8d, 100h; cchMax
0x1800329e4  lea     rdx, [rbp+360h+sz]; lpsz
0x1800329eb  lea     rcx, [rbp+360h+pguid]; rguid
0x1800329f2  call    cs:__imp_StringFromGUID2
0x1800329f9  nop     dword ptr [rax+rax+00h]
0x1800329fe  test    eax, eax
0x180032a00  jnz     short loc_180032A32
0x180032a02  mov     ebx, 8007007Ah
0x180032a07  mov     rcx, cs:WPP_GLOBAL_Control
0x180032a0e  lea     rax, WPP_GLOBAL_Control
0x180032a15  cmp     rcx, rax
0x180032a18  jz      loc_180032AE4
0x180032a1e  test    byte ptr [rcx+1Ch], 1
0x180032a22  jz      loc_180032AE4
0x180032a28  mov     edx, 50h ; 'P'
0x180032a2d  jmp     loc_180032985
0x180032a32  lea     rax, [rbp+360h+sz]
0x180032a39  and     edi, r15d
0x180032a3c  lea     rdx, [rsp+460h+Src]; Src
0x180032a41  mov     [rsp+460h+var_430], rax
0x180032a46  mov     rcx, r14; __int64
0x180032a49  mov     [rsp+460h+var_418], edi
0x180032a4d  call    FWAddFirewallRule
0x180032a52  mov     ebx, eax
0x180032a54  test    eax, eax
0x180032a56  jz      short loc_180032A8A
0x180032a58  jle     short loc_180032A63
0x180032a5a  movzx   ebx, ax
0x180032a5d  or      ebx, 80070000h
0x180032a63  test    ebx, ebx
0x180032a65  jns     short loc_180032A8A
0x180032a67  mov     rcx, cs:WPP_GLOBAL_Control
0x180032a6e  lea     rax, WPP_GLOBAL_Control
0x180032a75  cmp     rcx, rax
0x180032a78  jz      short loc_180032AE4
0x180032a7a  test    byte ptr [rcx+1Ch], 1
0x180032a7e  jz      short loc_180032AE4
0x180032a80  mov     edx, 51h ; 'Q'
0x180032a85  jmp     loc_180032985
0x180032a8a  lea     rbx, [rsi+10h]
0x180032a8e  mov     rcx, [rbx]
0x180032a91  call    cs:__imp_FwBaseFree
0x180032a98  nop     dword ptr [rax+rax+00h]
0x180032a9d  mov     rcx, [rsp+460h+var_430]
0x180032aa2  mov     rdx, rbx
0x180032aa5  mov     qword ptr [rbx], 0
0x180032aac  call    cs:__imp_FwStringCopy
0x180032ab3  nop     dword ptr [rax+rax+00h]
0x180032ab8  mov     ebx, eax
0x180032aba  test    eax, eax
0x180032abc  jns     short loc_180032AE1
0x180032abe  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ac5  lea     rax, WPP_GLOBAL_Control
0x180032acc  cmp     rcx, rax
0x180032acf  jz      short loc_180032AE4
0x180032ad1  test    byte ptr [rcx+1Ch], 1
0x180032ad5  jz      short loc_180032AE4
0x180032ad7  mov     edx, 52h ; 'R'
0x180032adc  jmp     loc_180032985
0x180032ae1  mov     [rsi+28h], edi
0x180032ae4  mov     eax, ebx
0x180032ae6  mov     rcx, [rbp+360h+var_30]
0x180032aed  xor     rcx, rsp; StackCookie
0x180032af0  call    __security_check_cookie
0x180032af5  mov     rbx, [rsp+460h+arg_18]
0x180032afd  add     rsp, 440h
0x180032b04  pop     r15
0x180032b06  pop     r14
0x180032b08  pop     rdi
0x180032b09  pop     rsi
0x180032b0a  pop     rbp
0x180032b0b  retn
```
