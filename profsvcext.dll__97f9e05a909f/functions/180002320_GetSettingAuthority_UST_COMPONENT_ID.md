# GetSettingAuthority(UST_COMPONENT_ID)

- ea: `0x180002320`
- end: `0x1800024af`
- name: `?GetSettingAuthority@@YA?AW4SETTING_AUTH@@W4UST_COMPONENT_ID@@@Z`
- size: `399`
- prototype: `_BOOL8 __fastcall(unsigned int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180004130`
- `0x180004660`

## callees

- `0x180002320`
- `0x1800024c0`
- `0x180002940`
- `0x18001afa0`
- `0x18001afc8`
- `0x18001b008`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180002497`
- `OLEAUT32!__imp_VariantClear` at `0x180002497`

## pseudocode

```c
_BOOL8 __fastcall GetSettingAuthority(unsigned int a1, __int64 a2, __int64 a3, __int64 a4)
{
  UstCommon::CImpersonator *v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // r9
  const wchar_t *v9; // r9
  BOOL v10; // ebx
  VARIANTARG pvarg; // [rsp+40h] [rbp-28h] BYREF

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_313c576492293c0704086ae70e07ed75_Traceguids, a1);
    v5 = WPP_GLOBAL_Control;
  }
  if ( a1 == 1 )
  {
    v7 = 0;
  }
  else
  {
    v6 = a1 - 2;
    if ( v6 )
    {
      if ( v6 != 1 )
      {
        if ( v5 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)v5 + 2), 18, WPP_313c576492293c0704086ae70e07ed75_Traceguids, a4);
        return 0;
      }
      v7 = 2;
    }
    else
    {
      v7 = 1;
    }
  }
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 0;
  if ( (int)GetUserStateSetting(0, qword_18002D760, 3, v7, &pvarg, 0, 0) < 0 )
  {
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v8);
    }
    if ( pvarg.vt == 4095 )
      pvarg.vt = 8;
    VariantClear(&pvarg);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v9 = L"SA_WMI";
    if ( pvarg.bVal != 1 )
      v9 = L"SA_GP";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v9);
  }
  v10 = pvarg.bVal == 1;
  ATL::CComVariant::Clear(&pvarg);
  return v10;
}

```

## disassembly

```asm
0x180002320  mov     [rsp+arg_0], rbx
0x180002325  mov     [rsp+arg_8], rsi
0x18000232a  push    rdi
0x18000232b  sub     rsp, 60h
0x18000232f  mov     ebx, ecx
0x180002331  lea     rsi, WPP_GLOBAL_Control
0x180002338  mov     rcx, cs:WPP_GLOBAL_Control
0x18000233f  cmp     rcx, rsi
0x180002342  jz      short loc_180002369
0x180002344  test    byte ptr [rcx+1Ch], 2
0x180002348  jz      short loc_180002369
0x18000234a  mov     edx, 11h
0x18000234f  mov     r9d, ebx
0x180002352  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x180002359  mov     rcx, [rcx+10h]
0x18000235d  call    WPP_SF_d
0x180002362  mov     rcx, cs:WPP_GLOBAL_Control
0x180002369  xor     edi, edi
0x18000236b  cmp     ebx, 1
0x18000236e  jz      short loc_1800023B7
0x180002370  sub     ebx, 2
0x180002373  jz      short loc_1800023AF
0x180002375  cmp     ebx, 1
0x180002378  jz      short loc_1800023A7
0x18000237a  cmp     rcx, rsi
0x18000237d  jz      loc_18000249D
0x180002383  test    byte ptr [rcx+1Ch], 2
0x180002387  jz      loc_18000249D
0x18000238d  mov     edx, 12h
0x180002392  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x180002399  mov     rcx, [rcx+10h]
0x18000239d  call    WPP_SF_
0x1800023a2  jmp     loc_18000249D
0x1800023a7  mov     r9d, 2
0x1800023ad  jmp     short loc_1800023BA
0x1800023af  mov     r9d, 1
0x1800023b5  jmp     short loc_1800023BA
0x1800023b7  mov     r9d, edi
0x1800023ba  xorps   xmm0, xmm0
0x1800023bd  xor     eax, eax
0x1800023bf  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x1800023c4  mov     qword ptr [rsp+68h+pvarg+10h], rax
0x1800023c9  mov     word ptr [rsp+68h+pvarg], di
0x1800023ce  mov     [rsp+68h+var_30], rdi
0x1800023d3  mov     [rsp+68h+var_38], edi
0x1800023d7  mov     [rsp+68h+var_40], rdi
0x1800023dc  lea     rax, [rsp+68h+pvarg]
0x1800023e1  mov     [rsp+68h+var_48], rax
0x1800023e6  mov     r8d, 3
0x1800023ec  lea     rdx, qword_18002D760
0x1800023f3  xor     ecx, ecx
0x1800023f5  call    ?GetUserStateSetting@@YAJW4UST_COMPONENT_ID@@QEBUUSERSTATE_SETTING_DESCRIPTOR@@IIAEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z; GetUserStateSetting(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const * const,uint,uint,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)
0x1800023fa  test    eax, eax
0x1800023fc  js      short loc_180002454
0x1800023fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180002405  cmp     rcx, rsi
0x180002408  jz      short loc_18000243C
0x18000240a  test    byte ptr [rcx+1Ch], 2
0x18000240e  jz      short loc_18000243C
0x180002410  lea     r9, aSaWmi; "SA_WMI"
0x180002417  lea     rax, aSaGp; "SA_GP"
0x18000241e  cmp     byte ptr [rsp+68h+pvarg+8], 1
0x180002423  cmovnz  r9, rax
0x180002427  mov     edx, 13h
0x18000242c  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x180002433  mov     rcx, [rcx+10h]
0x180002437  call    WPP_SF_S
0x18000243c  mov     ebx, edi
0x18000243e  cmp     byte ptr [rsp+68h+pvarg+8], 1
0x180002443  setz    bl
0x180002446  lea     rcx, [rsp+68h+pvarg]; this
0x18000244b  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x180002450  mov     eax, ebx
0x180002452  jmp     short loc_18000249F
0x180002454  mov     rcx, cs:WPP_GLOBAL_Control
0x18000245b  cmp     rcx, rsi
0x18000245e  jz      short loc_18000247C
0x180002460  test    byte ptr [rcx+1Ch], 2
0x180002464  jz      short loc_18000247C
0x180002466  mov     edx, 14h
0x18000246b  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x180002472  mov     rcx, [rcx+10h]
0x180002476  call    WPP_SF_
0x18000247b  nop
0x18000247c  mov     eax, 0FFFh
0x180002481  cmp     word ptr [rsp+68h+pvarg], ax
0x180002486  jnz     short loc_180002492
0x180002488  mov     eax, 8
0x18000248d  mov     word ptr [rsp+68h+pvarg], ax
0x180002492  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180002497  call    cs:__imp_VariantClear
0x18000249d  xor     eax, eax
0x18000249f  mov     rbx, [rsp+68h+arg_0]
0x1800024a4  mov     rsi, [rsp+68h+arg_8]
0x1800024a9  add     rsp, 60h
0x1800024ad  pop     rdi
0x1800024ae  retn
```
