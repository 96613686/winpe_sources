# Int_FWVerifyMainModeRule

- ea: `0x18002e7c0`
- end: `0x18002ed1c`
- name: `Int_FWVerifyMainModeRule`
- size: `1372`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002cc00`

## callees

- `0x18000ccd4`
- `0x18000d3fc`
- `0x18000f520`
- `0x180010f20`
- `0x180017d1c`
- `0x18002df50`
- `0x18002e7c0`
- `0x18002eee0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e95b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e95b`

## pseudocode

```c
__int64 __fastcall Int_FWVerifyMainModeRule(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v5; // r9
  unsigned int v6; // esi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // eax
  const WCHAR *v10; // r8
  wchar_t *v11; // rcx
  char IsEnabled; // al
  unsigned __int16 v13; // cx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
  *a3 = 0x10000;
  if ( *(_WORD *)(a2 + 8) >= 0x208u )
  {
    if ( *(_WORD *)(a2 + 8) >= 0x300u )
      *a3 = 0x40000;
    v9 = Int_FwValidateComplianceAndReduceMainModeRuleToVersion(a2, a3, *(unsigned __int16 *)(a2 + 8));
    v6 = v9;
    if ( v9 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 140;
        v5 = v9;
        goto LABEL_84;
      }
    }
    else if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 16), 0, 1u, 0x200u) )
    {
      v5 = 87;
      *a3 = 524296;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 141;
        goto LABEL_84;
      }
    }
    else if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 24), 0, 1u, 0x2710u) )
    {
      v5 = 87;
      *a3 = 524289;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 142;
        goto LABEL_84;
      }
    }
    else
    {
      v10 = *(const WCHAR **)(a2 + 24);
      if ( v10 && CompareStringW(0x7Fu, 1u, v10, -1, L"ALL", -1) == 2 )
      {
        v5 = 87;
        *a3 = 524289;
        v6 = 87;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 143;
          goto LABEL_84;
        }
      }
      else if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 32), 1, 0, 0x2710u) )
      {
        v5 = 87;
        *a3 = 524290;
        v6 = 87;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 144;
          goto LABEL_84;
        }
      }
      else if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 216), 1, 0, 0x2710u) )
      {
        v5 = 87;
        *a3 = 524295;
        v6 = 87;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 145;
          goto LABEL_84;
        }
      }
      else if ( (unsigned int)Int_FwValidateProfiles(*(_DWORD *)(a2 + 40)) )
      {
        v5 = 87;
        *a3 = 1048656;
        v6 = 87;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 146;
          goto LABEL_84;
        }
      }
      else if ( (unsigned int)Int_FwValidateAddresses(a2 + 48, 1, 0, a3) )
      {
        v5 = 87;
        v6 = 87;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 147;
          goto LABEL_84;
        }
      }
      else if ( (unsigned int)Int_FwValidateAddresses(a2 + 120, 1, 0, a3) )
      {
        v5 = 87;
        v6 = 87;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 148;
          goto LABEL_84;
        }
      }
      else
      {
        v11 = *(wchar_t **)(a2 + 192);
        if ( v11 )
        {
          if ( *(_QWORD *)(a2 + 200) )
          {
            if ( (unsigned int)Int_FwValidateString(v11, 0, 1u, 0xFFu) )
            {
              v5 = 87;
              *a3 = 524297;
              v6 = 87;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v8 = 151;
                goto LABEL_84;
              }
            }
            else if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 200), 0, 1u, 0xFFu) )
            {
              v5 = 87;
              *a3 = 524302;
              v6 = 87;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v8 = 152;
                goto LABEL_84;
              }
            }
            else
            {
              IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::GetImpl'::`2'::impl);
              v13 = *(_WORD *)(a2 + 208);
              if ( IsEnabled )
              {
                if ( v13 >= 0x400u )
                {
                  v5 = 87;
                  *a3 = 1048752;
                  v6 = 87;
                  v7 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    v8 = 153;
                    goto LABEL_84;
                  }
                  return v6;
                }
              }
              else if ( v13 >= 0x200u )
              {
                v5 = 87;
                *a3 = 1048752;
                v6 = 87;
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v8 = 154;
                  goto LABEL_84;
                }
                return v6;
              }
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::GetImpl'::`2'::impl)
                && (*(_WORD *)(a2 + 208) & 0x200) != 0 )
              {
                v5 = 87;
                *a3 = 1048752;
                v6 = 87;
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v8 = 155;
                  goto LABEL_84;
                }
              }
              else
              {
                if ( *(_QWORD *)(a2 + 232) )
                {
                  if ( *(_DWORD *)(a2 + 224) )
                    return v6;
                }
                else if ( !*(_DWORD *)(a2 + 224) )
                {
                  return v6;
                }
                v5 = 87;
                *a3 = 1048800;
                v6 = 87;
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v8 = 156;
                  goto LABEL_84;
                }
              }
            }
          }
          else
          {
            v5 = 87;
            *a3 = 1049873;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 150;
              goto LABEL_84;
            }
          }
        }
        else
        {
          v5 = 87;
          *a3 = 1049856;
          v6 = 87;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 149;
            goto LABEL_84;
          }
        }
      }
    }
  }
  else
  {
    v5 = 87;
    *a3 = 1069136;
    v6 = 87;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 139;
LABEL_84:
      WPP_SF_d(v7[2], v8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, v5);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18002e7c0  push    rbx
0x18002e7c2  push    rbp
0x18002e7c3  push    rsi
0x18002e7c4  push    rdi
0x18002e7c5  push    r13
0x18002e7c7  push    r14
0x18002e7c9  push    r15
0x18002e7cb  sub     rsp, 30h
0x18002e7cf  mov     rdi, r8
0x18002e7d2  mov     rbp, rdx
0x18002e7d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e7dc  lea     r14, WPP_GLOBAL_Control
0x18002e7e3  lea     r15, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18002e7ea  cmp     rcx, r14
0x18002e7ed  jz      short loc_18002E806
0x18002e7ef  test    byte ptr [rcx+1Ch], 8
0x18002e7f3  jz      short loc_18002E806
0x18002e7f5  mov     rcx, [rcx+10h]
0x18002e7f9  mov     edx, 8Ah
0x18002e7fe  mov     r8, r15
0x18002e801  call    WPP_SF_
0x18002e806  mov     eax, 208h
0x18002e80b  mov     dword ptr [rdi], 10000h
0x18002e811  cmp     [rbp+8], ax
0x18002e815  jnb     short loc_18002E84C
0x18002e817  mov     r9d, 57h ; 'W'
0x18002e81d  mov     dword ptr [rdi], 105050h
0x18002e823  mov     esi, r9d
0x18002e826  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e82d  cmp     rcx, r14
0x18002e830  jz      loc_18002ED0B
0x18002e836  lea     ebx, [r9-56h]
0x18002e83a  test    [rcx+1Ch], bl
0x18002e83d  jz      loc_18002ED0B
0x18002e843  lea     edx, [r9+34h]
0x18002e847  jmp     loc_18002ECFF
0x18002e84c  mov     eax, 300h
0x18002e851  cmp     [rbp+8], ax
0x18002e855  jb      short loc_18002E85D
0x18002e857  mov     dword ptr [rdi], 40000h
0x18002e85d  movzx   r8d, word ptr [rbp+8]
0x18002e862  mov     rdx, rdi
0x18002e865  mov     rcx, rbp
0x18002e868  call    Int_FwValidateComplianceAndReduceMainModeRuleToVersion
0x18002e86d  mov     esi, eax
0x18002e86f  test    eax, eax
0x18002e871  jz      short loc_18002E89E
0x18002e873  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e87a  cmp     rcx, r14
0x18002e87d  jz      loc_18002ED0B
0x18002e883  mov     ebx, 1
0x18002e888  test    [rcx+1Ch], bl
0x18002e88b  jz      loc_18002ED0B
0x18002e891  mov     edx, 8Ch
0x18002e896  mov     r9d, eax
0x18002e899  jmp     loc_18002ECFF
0x18002e89e  mov     rcx, [rbp+10h]; Str
0x18002e8a2  mov     ebx, 1
0x18002e8a7  mov     r8d, ebx
0x18002e8aa  mov     r9d, 200h
0x18002e8b0  xor     edx, edx
0x18002e8b2  call    Int_FwValidateString
0x18002e8b7  test    eax, eax
0x18002e8b9  jz      short loc_18002E8EA
0x18002e8bb  lea     r9d, [rbx+56h]
0x18002e8bf  mov     dword ptr [rdi], 80008h
0x18002e8c5  mov     esi, r9d
0x18002e8c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e8cf  cmp     rcx, r14
0x18002e8d2  jz      loc_18002ED0B
0x18002e8d8  test    [rcx+1Ch], bl
0x18002e8db  jz      loc_18002ED0B
0x18002e8e1  lea     edx, [r9+36h]
0x18002e8e5  jmp     loc_18002ECFF
0x18002e8ea  mov     rcx, [rbp+18h]; Str
0x18002e8ee  mov     r13d, 2710h
0x18002e8f4  mov     r9d, r13d
0x18002e8f7  mov     r8d, ebx
0x18002e8fa  xor     edx, edx
0x18002e8fc  call    Int_FwValidateString
0x18002e901  test    eax, eax
0x18002e903  jz      short loc_18002E936
0x18002e905  mov     r9d, 57h ; 'W'
0x18002e90b  mov     dword ptr [rdi], 80001h
0x18002e911  mov     esi, r9d
0x18002e914  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e91b  cmp     rcx, r14
0x18002e91e  jz      loc_18002ED0B
0x18002e924  test    [rcx+1Ch], bl
0x18002e927  jz      loc_18002ED0B
0x18002e92d  lea     edx, [r9+37h]
0x18002e931  jmp     loc_18002ECFF
0x18002e936  mov     r8, [rbp+18h]; lpString1
0x18002e93a  test    r8, r8
0x18002e93d  jz      short loc_18002E995
0x18002e93f  or      r9d, 0FFFFFFFFh; cchCount1
0x18002e943  lea     rax, String2; "ALL"
0x18002e94a  mov     [rsp+68h+cchCount2], r9d; cchCount2
0x18002e94f  mov     edx, ebx; dwCmpFlags
0x18002e951  mov     ecx, 7Fh; Locale
0x18002e956  mov     [rsp+68h+lpString2], rax; lpString2
0x18002e95b  call    cs:__imp_CompareStringW
0x18002e961  cmp     eax, 2
0x18002e964  jnz     short loc_18002E995
0x18002e966  lea     r9d, [rax+55h]
0x18002e96a  mov     dword ptr [rdi], 80001h
0x18002e970  mov     esi, r9d
0x18002e973  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e97a  cmp     rcx, r14
0x18002e97d  jz      loc_18002ED0B
0x18002e983  test    [rcx+1Ch], bl
0x18002e986  jz      loc_18002ED0B
0x18002e98c  lea     edx, [r9+38h]
0x18002e990  jmp     loc_18002ECFF
0x18002e995  mov     rcx, [rbp+20h]; Str
0x18002e999  mov     r9d, r13d
0x18002e99c  xor     r8d, r8d
0x18002e99f  mov     edx, ebx
0x18002e9a1  call    Int_FwValidateString
0x18002e9a6  test    eax, eax
0x18002e9a8  jz      short loc_18002E9DB
0x18002e9aa  mov     r9d, 57h ; 'W'
0x18002e9b0  mov     dword ptr [rdi], 80002h
0x18002e9b6  mov     esi, r9d
0x18002e9b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e9c0  cmp     rcx, r14
0x18002e9c3  jz      loc_18002ED0B
0x18002e9c9  test    [rcx+1Ch], bl
0x18002e9cc  jz      loc_18002ED0B
0x18002e9d2  lea     edx, [r9+39h]
0x18002e9d6  jmp     loc_18002ECFF
0x18002e9db  mov     rcx, [rbp+0D8h]; Str
0x18002e9e2  mov     r9d, r13d
0x18002e9e5  xor     r8d, r8d
0x18002e9e8  mov     edx, ebx
0x18002e9ea  call    Int_FwValidateString
0x18002e9ef  test    eax, eax
0x18002e9f1  jz      short loc_18002EA24
0x18002e9f3  mov     r9d, 57h ; 'W'
0x18002e9f9  mov     dword ptr [rdi], 80007h
0x18002e9ff  mov     esi, r9d
0x18002ea02  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea09  cmp     rcx, r14
0x18002ea0c  jz      loc_18002ED0B
0x18002ea12  test    [rcx+1Ch], bl
0x18002ea15  jz      loc_18002ED0B
0x18002ea1b  lea     edx, [r9+3Ah]
0x18002ea1f  jmp     loc_18002ECFF
0x18002ea24  mov     ecx, [rbp+28h]
0x18002ea27  call    Int_FwValidateProfiles
0x18002ea2c  test    eax, eax
0x18002ea2e  jz      short loc_18002EA61
0x18002ea30  mov     r9d, 57h ; 'W'
0x18002ea36  mov     dword ptr [rdi], 100050h
0x18002ea3c  mov     esi, r9d
0x18002ea3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea46  cmp     rcx, r14
0x18002ea49  jz      loc_18002ED0B
0x18002ea4f  test    [rcx+1Ch], bl
0x18002ea52  jz      loc_18002ED0B
0x18002ea58  lea     edx, [r9+3Bh]
0x18002ea5c  jmp     loc_18002ECFF
0x18002ea61  lea     rcx, [rbp+30h]
0x18002ea65  mov     r9, rdi
0x18002ea68  xor     r8d, r8d
0x18002ea6b  mov     edx, ebx
0x18002ea6d  call    Int_FwValidateAddresses
0x18002ea72  test    eax, eax
0x18002ea74  jz      short loc_18002EAA1
0x18002ea76  mov     r9d, 57h ; 'W'
0x18002ea7c  mov     esi, r9d
0x18002ea7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea86  cmp     rcx, r14
0x18002ea89  jz      loc_18002ED0B
0x18002ea8f  test    [rcx+1Ch], bl
0x18002ea92  jz      loc_18002ED0B
0x18002ea98  lea     edx, [r9+3Ch]
0x18002ea9c  jmp     loc_18002ECFF
0x18002eaa1  lea     rcx, [rbp+78h]
0x18002eaa5  mov     r9, rdi
0x18002eaa8  xor     r8d, r8d
0x18002eaab  mov     edx, ebx
0x18002eaad  call    Int_FwValidateAddresses
0x18002eab2  test    eax, eax
0x18002eab4  jz      short loc_18002EAE1
0x18002eab6  mov     r9d, 57h ; 'W'
0x18002eabc  mov     esi, r9d
0x18002eabf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eac6  cmp     rcx, r14
0x18002eac9  jz      loc_18002ED0B
0x18002eacf  test    [rcx+1Ch], bl
0x18002ead2  jz      loc_18002ED0B
0x18002ead8  lea     edx, [r9+3Dh]
0x18002eadc  jmp     loc_18002ECFF
0x18002eae1  mov     rcx, [rbp+0C0h]; Str
0x18002eae8  test    rcx, rcx
0x18002eaeb  jnz     short loc_18002EB1C
0x18002eaed  lea     r9d, [rcx+57h]
0x18002eaf1  mov     dword ptr [rdi], 100500h
0x18002eaf7  mov     esi, r9d
0x18002eafa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb01  cmp     rcx, r14
0x18002eb04  jz      loc_18002ED0B
0x18002eb0a  test    [rcx+1Ch], bl
0x18002eb0d  jz      loc_18002ED0B
0x18002eb13  lea     edx, [r9+3Eh]
0x18002eb17  jmp     loc_18002ECFF
0x18002eb1c  cmp     qword ptr [rbp+0C8h], 0
0x18002eb24  jnz     short loc_18002EB57
0x18002eb26  mov     r9d, 57h ; 'W'
0x18002eb2c  mov     dword ptr [rdi], 100511h
0x18002eb32  mov     esi, r9d
0x18002eb35  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb3c  cmp     rcx, r14
0x18002eb3f  jz      loc_18002ED0B
0x18002eb45  test    [rcx+1Ch], bl
0x18002eb48  jz      loc_18002ED0B
0x18002eb4e  lea     edx, [r9+3Fh]
0x18002eb52  jmp     loc_18002ECFF
0x18002eb57  mov     r13d, 0FFh
0x18002eb5d  mov     r8d, ebx
0x18002eb60  mov     r9d, r13d
0x18002eb63  xor     edx, edx
0x18002eb65  call    Int_FwValidateString
0x18002eb6a  test    eax, eax
0x18002eb6c  jz      short loc_18002EB9F
0x18002eb6e  mov     r9d, 57h ; 'W'
0x18002eb74  mov     dword ptr [rdi], 80009h
0x18002eb7a  mov     esi, r9d
0x18002eb7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb84  cmp     rcx, r14
0x18002eb87  jz      loc_18002ED0B
0x18002eb8d  test    [rcx+1Ch], bl
0x18002eb90  jz      loc_18002ED0B
0x18002eb96  lea     edx, [r13-68h]
0x18002eb9a  jmp     loc_18002ECFF
0x18002eb9f  mov     rcx, [rbp+0C8h]; Str
0x18002eba6  mov     r9d, r13d
0x18002eba9  mov     r8d, ebx
0x18002ebac  xor     edx, edx
0x18002ebae  call    Int_FwValidateString
0x18002ebb3  test    eax, eax
0x18002ebb5  jz      short loc_18002EBE8
0x18002ebb7  mov     r9d, 57h ; 'W'
0x18002ebbd  mov     dword ptr [rdi], 8000Eh
0x18002ebc3  mov     esi, r9d
0x18002ebc6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ebcd  cmp     rcx, r14
0x18002ebd0  jz      loc_18002ED0B
0x18002ebd6  test    [rcx+1Ch], bl
0x18002ebd9  jz      loc_18002ED0B
0x18002ebdf  lea     edx, [r9+41h]
0x18002ebe3  jmp     loc_18002ECFF
0x18002ebe8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IPSec_Point_To_Site@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site> `wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::GetImpl(void)'::`2'::impl
0x18002ebef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::__private_IsEnabled(void)
0x18002ebf4  movzx   ecx, word ptr [rbp+0D0h]
0x18002ebfb  test    al, al
0x18002ebfd  jz      short loc_18002EC3A
0x18002ebff  mov     eax, 400h
0x18002ec04  cmp     cx, ax
0x18002ec07  jb      short loc_18002EC77
0x18002ec09  mov     r9d, 57h ; 'W'
0x18002ec0f  mov     dword ptr [rdi], 1000B0h
0x18002ec15  mov     esi, r9d
0x18002ec18  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec1f  cmp     rcx, r14
0x18002ec22  jz      loc_18002ED0B
0x18002ec28  test    [rcx+1Ch], bl
0x18002ec2b  jz      loc_18002ED0B
0x18002ec31  lea     edx, [r9+42h]
0x18002ec35  jmp     loc_18002ECFF
0x18002ec3a  mov     r13d, 200h
0x18002ec40  cmp     cx, r13w
0x18002ec44  jb      short loc_18002EC7D
0x18002ec46  mov     r9d, 57h ; 'W'
0x18002ec4c  mov     dword ptr [rdi], 1000B0h
0x18002ec52  mov     esi, r9d
0x18002ec55  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec5c  cmp     rcx, r14
0x18002ec5f  jz      loc_18002ED0B
0x18002ec65  test    [rcx+1Ch], bl
0x18002ec68  jz      loc_18002ED0B
0x18002ec6e  lea     edx, [r9+43h]
0x18002ec72  jmp     loc_18002ECFF
0x18002ec77  mov     r13d, 200h
0x18002ec7d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IPSec_Point_To_Site@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site> `wil::Feature<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::GetImpl(void)'::`2'::impl
0x18002ec84  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_IPSec_Point_To_Site@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IPSec_Point_To_Site>::__private_IsEnabled(void)
0x18002ec89  test    al, al
0x18002ec8b  jz      short loc_18002ECBD
0x18002ec8d  test    [rbp+0D0h], r13w
0x18002ec95  jz      short loc_18002ECBD
0x18002ec97  mov     r9d, 57h ; 'W'
0x18002ec9d  mov     dword ptr [rdi], 1000B0h
0x18002eca3  mov     esi, r9d
0x18002eca6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ecad  cmp     rcx, r14
0x18002ecb0  jz      short loc_18002ED0B
0x18002ecb2  test    [rcx+1Ch], bl
0x18002ecb5  jz      short loc_18002ED0B
0x18002ecb7  lea     edx, [r9+44h]
  ... truncated ...
```
