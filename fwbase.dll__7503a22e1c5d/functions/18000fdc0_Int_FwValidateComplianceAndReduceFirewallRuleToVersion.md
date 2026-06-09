# Int_FwValidateComplianceAndReduceFirewallRuleToVersion

- ea: `0x18000fdc0`
- end: `0x180010d6a`
- name: `Int_FwValidateComplianceAndReduceFirewallRuleToVersion`
- size: `4010`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d490`

## callees

- `0x18000ccd4`
- `0x18000fdc0`
- `0x180010d70`
- `0x180017d1c`

## pseudocode

```c
__int64 __fastcall Int_FwValidateComplianceAndReduceFirewallRuleToVersion(
        __int64 a1,
        enum _tag_FW_RULE_STATUS *a2,
        unsigned __int16 a3)
{
  unsigned int v6; // edi
  unsigned __int16 v8; // ax
  unsigned int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int v13; // edx
  bool v14; // zf
  unsigned __int16 v15; // dx
  unsigned __int16 v16; // dx
  unsigned int v17; // edx
  unsigned int v18; // edx
  unsigned __int16 v19; // dx
  unsigned __int16 v20; // cx
  unsigned int v21; // ecx
  __int16 v22; // cx
  unsigned __int16 v23; // dx
  __int16 v24; // dx
  __int16 v25; // r8
  unsigned int v26; // r8d
  __int16 v27; // r8
  unsigned int v28; // edx
  unsigned __int16 v29; // ax
  unsigned __int16 v30; // ax
  _DWORD *v31; // r8
  unsigned __int16 v32; // r9
  unsigned __int16 v33; // dx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 303, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
  if ( a3 < 0x209u )
  {
    v29 = *(_WORD *)(a1 + 292);
    if ( v29 >= 0x20u )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1048759;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 304;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      *(_WORD *)(a1 + 292) = v29 & 0x1F;
    }
    goto LABEL_19;
  }
  if ( a3 < 0x20Au )
  {
LABEL_19:
    v8 = *(_WORD *)(a1 + 292);
    if ( v8 >= 0x40u )
    {
      if ( a2 )
      {
        if ( (v8 & 0x40) != 0 )
        {
          *(_DWORD *)a2 = 1048757;
          v6 = 87;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 305;
            goto LABEL_34;
          }
          return v6;
        }
        if ( (v8 & 0x180) != 0 )
        {
          *(_DWORD *)a2 = 1048765;
          v6 = 87;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 306;
            goto LABEL_34;
          }
          return v6;
        }
        if ( (v8 & 0x200) != 0 )
        {
          *(_DWORD *)a2 = 1048767;
          v6 = 87;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 307;
            goto LABEL_34;
          }
          return v6;
        }
      }
      else
      {
        *(_DWORD *)(a1 + 336) = 0x20000;
        *(_WORD *)(a1 + 292) = v8 & 0x3F;
      }
    }
    v9 = FwValidateComplianceAndReduceRuleOnPortList(
           (struct _tag_FW_PORTS *)(a1 + 56),
           (struct _tag_FW_PORTS *)(a1 + 80),
           a2,
           (enum _tag_FW_RULE_STATUS *)(a1 + 336));
    v6 = v9;
    if ( v9 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 308;
        v12 = v9;
LABEL_24:
        WPP_SF_d(v10[2], v11, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, v12);
        return v6;
      }
      return v6;
    }
    v30 = *(_WORD *)(a1 + 56);
    if ( v30 >= 8u || *(_WORD *)(a1 + 80) >= 8u )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1048609;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 309;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      if ( v30 >= 8u )
        *(_WORD *)(a1 + 56) = v30 & 7;
      if ( *(_WORD *)(a1 + 80) >= 8u )
        *(_WORD *)(a1 + 80) &= 7u;
    }
LABEL_41:
    v16 = *(_WORD *)(a1 + 292);
    if ( v16 >= 0x400u )
    {
      if ( a2 )
      {
        if ( (v16 & 0x400) != 0 )
        {
          *(_DWORD *)a2 = 1048784;
          v6 = 87;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 310;
            goto LABEL_34;
          }
          return v6;
        }
      }
      else
      {
        *(_DWORD *)(a1 + 336) = 0x20000;
        *(_WORD *)(a1 + 292) = v16 & 0x3FF;
      }
    }
LABEL_42:
    v17 = *(_DWORD *)(a1 + 176);
    if ( v17 >= 0x20 )
    {
      if ( a2 )
      {
        if ( (v17 & 0x60) != 0 )
        {
          *(_DWORD *)a2 = 1048819;
          v6 = 87;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 311;
            goto LABEL_34;
          }
          return v6;
        }
      }
      else
      {
        *(_DWORD *)(a1 + 336) = 0x20000;
        *(_DWORD *)(a1 + 176) = v17 & 0x1F;
      }
    }
    v18 = *(_DWORD *)(a1 + 180);
    if ( v18 >= 0x20 )
    {
      if ( a2 )
      {
        if ( (v18 & 0x60) != 0 )
        {
          *(_DWORD *)a2 = 1048819;
          v6 = 87;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 312;
            goto LABEL_34;
          }
          return v6;
        }
      }
      else
      {
        *(_DWORD *)(a1 + 336) = 0x20000;
        *(_DWORD *)(a1 + 180) = v18 & 0x1F;
      }
    }
    if ( *(_QWORD *)(a1 + 368) )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1048771;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 313;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      *(_QWORD *)(a1 + 368) = 0;
    }
    if ( *(_QWORD *)(a1 + 384) )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1048773;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 314;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      *(_QWORD *)(a1 + 384) = 0;
    }
    if ( *(_QWORD *)(a1 + 376) )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1048833;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 315;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      *(_QWORD *)(a1 + 376) = 0;
    }
    if ( *(_DWORD *)(a1 + 392) )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1049090;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 316;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      *(_DWORD *)(a1 + 392) = 0;
    }
    v19 = *(_WORD *)(a1 + 292);
    if ( v19 >= 0x400u )
    {
      if ( a2 )
      {
        if ( (v19 & 0x800) != 0 )
        {
          *(_DWORD *)a2 = 1048785;
          v6 = 87;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 317;
            goto LABEL_34;
          }
          return v6;
        }
      }
      else
      {
        *(_DWORD *)(a1 + 336) = 0x20000;
        *(_WORD *)(a1 + 292) = v19 & 0x3FF;
      }
    }
    v20 = *(_WORD *)(a1 + 56);
    if ( v20 >= 0x20u || *(_WORD *)(a1 + 80) >= 0x20u )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1048609;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 318;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      if ( v20 >= 0x20u )
        *(_WORD *)(a1 + 56) = v20 & 0x1F;
      if ( *(_WORD *)(a1 + 80) >= 0x20u )
        *(_WORD *)(a1 + 80) &= 0x1Fu;
    }
    goto LABEL_56;
  }
  v6 = 0;
  if ( a3 < 0x210u )
    goto LABEL_41;
  if ( a3 < 0x214u )
    goto LABEL_42;
  if ( a3 < 0x216u )
  {
LABEL_56:
    v21 = *(_DWORD *)(a1 + 392);
    if ( v21 >= 4 )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1049090;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 319;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      *(_DWORD *)(a1 + 392) = v21 & 3;
    }
LABEL_57:
    if ( *(_DWORD *)(a1 + 264) >= 8u )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1049345;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 320;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 392) &= 7u;
      *(_DWORD *)(a1 + 336) = 0x20000;
    }
    goto LABEL_62;
  }
  if ( a3 < 0x217u )
    goto LABEL_57;
  if ( a3 < 0x218u )
  {
LABEL_62:
    v22 = *(_WORD *)(a1 + 292);
    if ( (v22 & 0x1000) != 0 )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1048774;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 321;
          goto LABEL_34;
        }
        return v6;
      }
      v22 &= 0xFFFu;
      *(_DWORD *)(a1 + 336) = 0x20000;
      *(_WORD *)(a1 + 292) = v22;
      *(_QWORD *)(a1 + 368) = 0;
    }
    if ( (v22 & 0x2000) != 0 )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1048752;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 322;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      *(_WORD *)(a1 + 292) = v22 & 0xFFF;
    }
    if ( *(_DWORD *)(a1 + 400) )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1049601;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 323;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      *(_DWORD *)(a1 + 400) = 0;
      *(_QWORD *)(a1 + 408) = 0;
    }
    if ( *(_QWORD *)(a1 + 416) )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1049602;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 324;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      *(_QWORD *)(a1 + 416) = 0;
    }
    v23 = *(_WORD *)(a1 + 56);
    if ( v23 >= 0x80u || *(_WORD *)(a1 + 80) >= 0x80u )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1048609;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 325;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      if ( v23 >= 0x80u )
        *(_WORD *)(a1 + 56) = v23 & 0x7F;
      if ( *(_WORD *)(a1 + 80) >= 0x80u )
        *(_WORD *)(a1 + 80) &= 0x7Fu;
    }
LABEL_72:
    v24 = *(_WORD *)(a1 + 424);
    if ( (v24 & 3) != 0 )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1049603;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 326;
          goto LABEL_34;
        }
        return v6;
      }
      v31 = (_DWORD *)(a1 + 336);
    }
    else
    {
      v31 = (_DWORD *)(a1 + 336);
      if ( (v24 & 4) == 0 )
      {
LABEL_119:
        v32 = *(_WORD *)(a1 + 56);
        if ( v32 >= 0x100u || *(_WORD *)(a1 + 80) >= 0x100u )
        {
          if ( a2 )
          {
            *(_DWORD *)a2 = 1048609;
            v6 = 87;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v11 = 328;
              goto LABEL_34;
            }
            return v6;
          }
          *v31 = 0x20000;
          if ( v32 >= 0x100u )
            *(_WORD *)(a1 + 56) = (unsigned __int8)v32;
          if ( *(_WORD *)(a1 + 80) >= 0x100u )
            *(_WORD *)(a1 + 80) = (unsigned __int8)*(_WORD *)(a1 + 80);
        }
        goto LABEL_77;
      }
      if ( a2 )
      {
        *(_DWORD *)a2 = 1049604;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 327;
          goto LABEL_34;
        }
        return v6;
      }
    }
    *(_WORD *)(a1 + 424) = 0;
    *v31 = 0x20000;
    goto LABEL_119;
  }
  if ( a3 < 0x219u )
    goto LABEL_72;
  if ( a3 < 0x21Au )
  {
LABEL_77:
    if ( *(_DWORD *)(a1 + 432) )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1049605;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 329;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      *(_DWORD *)(a1 + 432) = 0;
      *(_QWORD *)(a1 + 440) = 0;
    }
    v25 = *(_WORD *)(a1 + 424);
    if ( (v25 & 0x30) != 0 )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1049605;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 330;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      *(_WORD *)(a1 + 424) = v25 & 7;
    }
    goto LABEL_82;
  }
  if ( a3 < 0x21Bu )
  {
LABEL_82:
    if ( *(_QWORD *)(a1 + 448) )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1049606;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 331;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      *(_QWORD *)(a1 + 448) = 0;
    }
    if ( *(_DWORD *)(a1 + 456) )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1049607;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 332;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      *(_DWORD *)(a1 + 456) = 0;
    }
    v26 = *(_DWORD *)(a1 + 392);
    if ( v26 >= 0x20 )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1049090;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 333;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      *(_DWORD *)(a1 + 392) = v26 & 0x1F;
    }
    v27 = *(_WORD *)(a1 + 424);
    if ( (v27 & 0x80u) != 0 )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1049608;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 334;
          goto LABEL_34;
        }
        return v6;
      }
    }
    else
    {
      if ( (v27 & 0x100) == 0 )
        goto LABEL_87;
      if ( a2 )
      {
        *(_DWORD *)a2 = 1049609;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 335;
          goto LABEL_34;
        }
        return v6;
      }
    }
    *(_DWORD *)(a1 + 336) = 0x20000;
    *(_WORD *)(a1 + 424) = 0;
LABEL_87:
    v28 = *(_DWORD *)(a1 + 392);
    if ( v28 >= 0x80 )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1049090;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 336;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      *(_DWORD *)(a1 + 392) = v28 & 0x7F;
    }
    goto LABEL_35;
  }
  if ( a3 < 0x21Cu )
    goto LABEL_87;
  if ( a3 >= 0x21Du )
  {
    if ( a3 >= 0x21Eu )
    {
      if ( a3 >= 0x21Fu )
        return v6;
LABEL_29:
      v14 = *(_DWORD *)(a1 + 480) == 0;
      *(_OWORD *)(a1 + 460) = 0;
      if ( !v14 )
      {
        if ( !a2 )
        {
          *(_DWORD *)(a1 + 336) = 0x20000;
          *(_DWORD *)(a1 + 480) = 0;
          *(_QWORD *)(a1 + 488) = 0;
          return v6;
        }
        *(_DWORD *)a2 = 1077252;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 339;
LABEL_34:
          v12 = 87;
          goto LABEL_24;
        }
      }
      return v6;
    }
LABEL_25:
    v13 = *(_DWORD *)(a1 + 104);
    if ( v13 >= 0x200
      || *(_DWORD *)(a1 + 176) >= 0x200u
      || *(_DWORD *)(a1 + 108) >= 0x200u
      || *(_DWORD *)(a1 + 180) >= 0x200u )
    {
      if ( a2 )
      {
        *(_DWORD *)a2 = 1048647;
        v6 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 338;
          goto LABEL_34;
        }
        return v6;
      }
      *(_DWORD *)(a1 + 336) = 0x20000;
      if ( v13 >= 0x200 )
        *(_DWORD *)(a1 + 104) = v13 & 0x1FF;
      if ( *(_DWORD *)(a1 + 176) >= 0x200u )
        *(_DWORD *)(a1 + 176) &= 0x1FFu;
      if ( *(_DWORD *)(a1 + 108) >= 0x200u )
        *(_DWORD *)(a1 + 108) &= 0x1FFu;
      if ( *(_DWORD *)(a1 + 180) >= 0x200u )
        *(_DWORD *)(a1 + 180) &= 0x1FFu;
    }
    goto LABEL_29;
  }
LABEL_35:
  v15 = *(_WORD *)(a1 + 56);
  if ( v15 < 0x200u && *(_WORD *)(a1 + 80) < 0x200u )
    goto LABEL_25;
  if ( !a2 )
  {
    *(_DWORD *)(a1 + 336) = 0x20000;
    if ( v15 >= 0x200u )
      *(_WORD *)(a1 + 56) = v15 & 0x1FF;
    v33 = *(_WORD *)(a1 + 80);
    if ( v33 >= 0x200u )
      *(_WORD *)(a1 + 80) = v33 & 0x1FF;
    goto LABEL_25;
  }
  *(_DWORD *)a2 = 1048609;
  v6 = 87;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 337;
    goto LABEL_34;
  }
  return v6;
}

```

## disassembly

```asm
0x18000fdc0  push    rbx
0x18000fdc2  push    rsi
0x18000fdc3  push    rdi
0x18000fdc4  push    r13
0x18000fdc6  push    r14
0x18000fdc8  sub     rsp, 20h
0x18000fdcc  movzx   ebx, r8w
0x18000fdd0  mov     r14, rdx
0x18000fdd3  mov     rsi, rcx
0x18000fdd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fddd  lea     r13, WPP_GLOBAL_Control
0x18000fde4  cmp     rcx, r13
0x18000fde7  jz      short loc_18000FDF3
0x18000fde9  test    byte ptr [rcx+1Ch], 8
0x18000fded  jnz     loc_1800104F4
0x18000fdf3  mov     [rsp+48h+arg_0], rbp
0x18000fdf8  mov     eax, 209h
0x18000fdfd  mov     [rsp+48h+arg_8], r12
0x18000fe02  mov     [rsp+48h+arg_10], r15
0x18000fe07  cmp     bx, ax
0x18000fe0a  jb      loc_18001032B
0x18000fe10  mov     eax, 20Ah
0x18000fe15  cmp     bx, ax
0x18000fe18  jb      loc_18000FEE7
0x18000fe1e  xor     eax, eax
0x18000fe20  mov     ecx, 210h
0x18000fe25  mov     edi, eax
0x18000fe27  cmp     bx, cx
0x18000fe2a  jb      loc_180010021
0x18000fe30  mov     ecx, 214h
0x18000fe35  cmp     bx, cx
0x18000fe38  jb      loc_1800100F0
0x18000fe3e  mov     ecx, 216h
0x18000fe43  cmp     bx, cx
0x18000fe46  jb      loc_1800100FF
0x18000fe4c  mov     ecx, 217h
0x18000fe51  cmp     bx, cx
0x18000fe54  jb      loc_180010284
0x18000fe5a  mov     ecx, 218h
0x18000fe5f  cmp     bx, cx
0x18000fe62  jb      loc_180010155
0x18000fe68  mov     ecx, 219h
0x18000fe6d  cmp     bx, cx
0x18000fe70  jb      loc_1800101E5
0x18000fe76  mov     ecx, 21Ah
0x18000fe7b  cmp     bx, cx
0x18000fe7e  jb      loc_180010238
0x18000fe84  mov     ecx, 21Bh
0x18000fe89  cmp     bx, cx
0x18000fe8c  jb      loc_18001028E
0x18000fe92  mov     ecx, 21Ch
0x18000fe97  cmp     bx, cx
0x18000fe9a  jb      loc_180010395
0x18000fea0  mov     ecx, 21Dh
0x18000fea5  cmp     bx, cx
0x18000fea8  jb      loc_18000FFD3
0x18000feae  mov     ecx, 21Eh
0x18000feb3  cmp     bx, cx
0x18000feb6  jb      loc_18000FF4A
0x18000febc  mov     ecx, 21Fh
0x18000fec1  cmp     bx, cx
0x18000fec4  jb      loc_18000FF80
0x18000feca  mov     r15, [rsp+48h+arg_10]
0x18000fecf  mov     eax, edi
0x18000fed1  mov     r12, [rsp+48h+arg_8]
0x18000fed6  mov     rbp, [rsp+48h+arg_0]
0x18000fedb  add     rsp, 20h
0x18000fedf  pop     r14
0x18000fee1  pop     r13
0x18000fee3  pop     rdi
0x18000fee4  pop     rsi
0x18000fee5  pop     rbx
0x18000fee6  retn
0x18000fee7  movzx   eax, word ptr [rsi+124h]
0x18000feee  mov     ebx, 200h
0x18000fef3  cmp     ax, 40h ; '@'
0x18000fef7  jnb     loc_180010528
0x18000fefd  lea     r9, [rsi+150h]; enum _tag_FW_RULE_STATUS *
0x18000ff04  mov     r8, r14; enum _tag_FW_RULE_STATUS *
0x18000ff07  lea     rdx, [rsi+50h]; struct _tag_FW_PORTS *
0x18000ff0b  lea     rcx, [rsi+38h]; struct _tag_FW_PORTS *
0x18000ff0f  call    ?FwValidateComplianceAndReduceRuleOnPortList@@YAKPEAU_tag_FW_PORTS@@0PEAW4_tag_FW_RULE_STATUS@@1@Z; FwValidateComplianceAndReduceRuleOnPortList(_tag_FW_PORTS *,_tag_FW_PORTS *,_tag_FW_RULE_STATUS *,_tag_FW_RULE_STATUS *)
0x18000ff14  mov     edi, eax
0x18000ff16  test    eax, eax
0x18000ff18  jz      loc_180010375
0x18000ff1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff25  cmp     rcx, r13
0x18000ff28  jz      short loc_18000FECA
0x18000ff2a  test    byte ptr [rcx+1Ch], 1
0x18000ff2e  jz      short loc_18000FECA
0x18000ff30  mov     edx, 134h
0x18000ff35  mov     r9d, eax
0x18000ff38  mov     rcx, [rcx+10h]
0x18000ff3c  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18000ff43  call    WPP_SF_d
0x18000ff48  jmp     short loc_18000FECA
0x18000ff4a  mov     ebx, 200h
0x18000ff4f  mov     ecx, 1FFh
0x18000ff54  mov     edx, [rsi+68h]
0x18000ff57  cmp     edx, ebx
0x18000ff59  jnb     loc_1800103A4
0x18000ff5f  cmp     [rsi+0B0h], ebx
0x18000ff65  jnb     loc_1800103A4
0x18000ff6b  cmp     [rsi+6Ch], ebx
0x18000ff6e  jnb     loc_1800103A4
0x18000ff74  cmp     [rsi+0B4h], ebx
0x18000ff7a  jnb     loc_1800103A4
0x18000ff80  cmp     dword ptr [rsi+1E0h], 0
0x18000ff87  xorps   xmm0, xmm0
0x18000ff8a  movups  xmmword ptr [rsi+1CCh], xmm0
0x18000ff91  jbe     loc_18000FECA
0x18000ff97  test    r14, r14
0x18000ff9a  jz      loc_180010D4E
0x18000ffa0  mov     dword ptr [r14], 107004h
0x18000ffa7  mov     edi, 57h ; 'W'
0x18000ffac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffb3  cmp     rcx, r13
0x18000ffb6  jz      loc_18000FECA
0x18000ffbc  test    byte ptr [rcx+1Ch], 1
0x18000ffc0  jz      loc_18000FECA
0x18000ffc6  mov     edx, 153h
0x18000ffcb  mov     r9d, edi
0x18000ffce  jmp     loc_18000FF38
0x18000ffd3  mov     ebx, 200h
0x18000ffd8  movzx   edx, word ptr [rsi+38h]
0x18000ffdc  cmp     dx, bx
0x18000ffdf  jnb     short loc_18000FFEB
0x18000ffe1  cmp     [rsi+50h], bx
0x18000ffe5  jb      loc_18000FF4F
0x18000ffeb  test    r14, r14
0x18000ffee  jz      loc_180010CCE
0x18000fff4  mov     dword ptr [r14], 100021h
0x18000fffb  mov     edi, 57h ; 'W'
0x180010000  mov     rcx, cs:WPP_GLOBAL_Control
0x180010007  cmp     rcx, r13
0x18001000a  jz      loc_18000FECA
0x180010010  test    byte ptr [rcx+1Ch], 1
0x180010014  jz      loc_18000FECA
0x18001001a  mov     edx, 151h
0x18001001f  jmp     short loc_18000FFCB
0x180010021  mov     ebx, 200h
0x180010026  movzx   edx, word ptr [rsi+124h]
0x18001002d  mov     ecx, 400h
0x180010032  cmp     dx, cx
0x180010035  jnb     loc_1800103DD
0x18001003b  mov     r8d, 3FFh
0x180010041  mov     edx, [rsi+0B0h]
0x180010047  cmp     edx, 20h ; ' '
0x18001004a  jnb     loc_18001067A
0x180010050  mov     edx, [rsi+0B4h]
0x180010056  cmp     edx, 20h ; ' '
0x180010059  jnb     loc_1800106D0
0x18001005f  cmp     qword ptr [rsi+170h], 0
0x180010067  jnz     loc_180010726
0x18001006d  cmp     qword ptr [rsi+180h], 0
0x180010075  jnz     loc_180010771
0x18001007b  cmp     qword ptr [rsi+178h], 0
0x180010083  jnz     loc_1800107BC
0x180010089  cmp     dword ptr [rsi+188h], 0
0x180010090  jnz     loc_180010807
0x180010096  movzx   edx, word ptr [rsi+124h]
0x18001009d  cmp     dx, cx
0x1800100a0  jnb     loc_180010851
0x1800100a6  movzx   ecx, word ptr [rsi+38h]
0x1800100aa  cmp     cx, 20h ; ' '
0x1800100ae  jnb     short loc_1800100B7
0x1800100b0  cmp     word ptr [rsi+50h], 20h ; ' '
0x1800100b5  jb      short loc_180010104
0x1800100b7  test    r14, r14
0x1800100ba  jz      loc_1800108AB
0x1800100c0  mov     dword ptr [r14], 100021h
0x1800100c7  mov     edi, 57h ; 'W'
0x1800100cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100d3  cmp     rcx, r13
0x1800100d6  jz      loc_18000FECA
0x1800100dc  test    byte ptr [rcx+1Ch], 1
0x1800100e0  jz      loc_18000FECA
0x1800100e6  mov     edx, 13Eh
0x1800100eb  jmp     loc_18000FFCB
0x1800100f0  mov     ebx, 200h
0x1800100f5  mov     ecx, 400h
0x1800100fa  jmp     loc_18001003B
0x1800100ff  mov     ebx, 200h
0x180010104  mov     ecx, [rsi+188h]
0x18001010a  cmp     ecx, 4
0x18001010d  jnb     loc_18001041F
0x180010113  cmp     dword ptr [rsi+108h], 8
0x18001011a  jb      short loc_18001015A
0x18001011c  test    r14, r14
0x18001011f  jz      loc_1800108F6
0x180010125  mov     dword ptr [r14], 100301h
0x18001012c  mov     edi, 57h ; 'W'
0x180010131  mov     rcx, cs:WPP_GLOBAL_Control
0x180010138  cmp     rcx, r13
0x18001013b  jz      loc_18000FECA
0x180010141  test    byte ptr [rcx+1Ch], 1
0x180010145  jz      loc_18000FECA
0x18001014b  mov     edx, 140h
0x180010150  jmp     loc_18000FFCB
0x180010155  mov     ebx, 200h
0x18001015a  movzx   ecx, word ptr [rsi+124h]
0x180010161  mov     r8d, 0FFFh
0x180010167  bt      cx, 0Ch
0x18001016c  jb      loc_18001090C
0x180010172  bt      cx, 0Dh
0x180010177  jb      loc_180010962
0x18001017d  cmp     dword ptr [rsi+190h], 0
0x180010184  ja      loc_1800109B1
0x18001018a  cmp     qword ptr [rsi+1A0h], 0
0x180010192  jnz     loc_180010A02
0x180010198  movzx   edx, word ptr [rsi+38h]
0x18001019c  mov     ecx, 80h
0x1800101a1  cmp     dx, cx
0x1800101a4  jnb     short loc_1800101AC
0x1800101a6  cmp     [rsi+50h], cx
0x1800101aa  jb      short loc_1800101EF
0x1800101ac  test    r14, r14
0x1800101af  jz      loc_180010A4D
0x1800101b5  mov     dword ptr [r14], 100021h
0x1800101bc  mov     edi, 57h ; 'W'
0x1800101c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101c8  cmp     rcx, r13
0x1800101cb  jz      loc_18000FECA
0x1800101d1  test    byte ptr [rcx+1Ch], 1
0x1800101d5  jz      loc_18000FECA
0x1800101db  mov     edx, 145h
0x1800101e0  jmp     loc_18000FFCB
0x1800101e5  mov     ebx, 200h
0x1800101ea  mov     ecx, 80h
0x1800101ef  movzx   edx, word ptr [rsi+1A8h]
0x1800101f6  test    dl, 3
0x1800101f9  jz      loc_180010491
0x1800101ff  test    r14, r14
0x180010202  jz      loc_180010A7E
0x180010208  mov     dword ptr [r14], 100403h
0x18001020f  mov     edi, 57h ; 'W'
0x180010214  mov     rcx, cs:WPP_GLOBAL_Control
0x18001021b  cmp     rcx, r13
0x18001021e  jz      loc_18000FECA
0x180010224  test    byte ptr [rcx+1Ch], 1
0x180010228  jz      loc_18000FECA
0x18001022e  mov     edx, 146h
0x180010233  jmp     loc_18000FFCB
0x180010238  mov     ebx, 200h
0x18001023d  mov     ecx, 80h
0x180010242  mov     edx, 100h
0x180010247  cmp     dword ptr [rsi+1B0h], 0
0x18001024e  ja      loc_180010B06
0x180010254  movzx   r8d, word ptr [rsi+1A8h]
0x18001025c  test    r8b, 30h
0x180010260  jz      short loc_18001029D
0x180010262  test    r14, r14
0x180010265  jnz     loc_180010B57
0x18001026b  and     r8w, 7
0x180010270  mov     dword ptr [rsi+150h], 20000h
0x18001027a  mov     [rsi+1A8h], r8w
0x180010282  jmp     short loc_18001029D
0x180010284  mov     ebx, 200h
0x180010289  jmp     loc_180010113
0x18001028e  mov     ebx, 200h
0x180010293  mov     ecx, 80h
0x180010298  mov     edx, 100h
0x18001029d  cmp     qword ptr [rsi+1C0h], 0
0x1800102a5  jnz     loc_180010458
0x1800102ab  cmp     dword ptr [rsi+1C8h], 0
0x1800102b2  jnz     loc_180010B9D
0x1800102b8  mov     r8d, [rsi+188h]
0x1800102bf  cmp     r8d, 20h ; ' '
0x1800102c3  jnb     loc_180010BE7
0x1800102c9  movzx   r8d, word ptr [rsi+1A8h]
0x1800102d1  test    r8b, r8b
0x1800102d4  js      loc_180010C36
0x1800102da  test    dx, r8w
0x1800102de  jnz     loc_180010C6B
0x1800102e4  mov     edx, [rsi+188h]
0x1800102ea  cmp     edx, ecx
0x1800102ec  jb      loc_18000FFD8
0x1800102f2  test    r14, r14
0x1800102f5  jz      loc_180010CB6
0x1800102fb  mov     dword ptr [r14], 100202h
0x180010302  mov     edi, 57h ; 'W'
0x180010307  mov     rcx, cs:WPP_GLOBAL_Control
0x18001030e  cmp     rcx, r13
0x180010311  jz      loc_18000FECA
0x180010317  test    byte ptr [rcx+1Ch], 1
0x18001031b  jz      loc_18000FECA
0x180010321  mov     edx, 150h
0x180010326  jmp     loc_18000FFCB
0x18001032b  movzx   eax, word ptr [rsi+124h]
0x180010332  cmp     ax, 20h ; ' '
0x180010336  jb      loc_18000FEE7
0x18001033c  test    r14, r14
0x18001033f  jz      loc_18001050E
0x180010345  mov     dword ptr [r14], 1000B7h
0x18001034c  mov     edi, 57h ; 'W'
0x180010351  mov     rcx, cs:WPP_GLOBAL_Control
0x180010358  cmp     rcx, r13
0x18001035b  jz      loc_18000FECA
0x180010361  test    byte ptr [rcx+1Ch], 1
0x180010365  jz      loc_18000FECA
  ... truncated ...
```
