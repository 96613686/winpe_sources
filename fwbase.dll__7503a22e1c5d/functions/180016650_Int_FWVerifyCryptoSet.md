# Int_FWVerifyCryptoSet

- ea: `0x180016650`
- end: `0x1800169e9`
- name: `Int_FWVerifyCryptoSet`
- size: `921`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c980`

## callees

- `0x18000bfd0`
- `0x18000ccd4`
- `0x180010f20`
- `0x180014340`
- `0x180016650`
- `0x180017718`
- `0x180017d1c`
- `0x18002f16c`
- `0x18002f38c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001695c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001695c`

## string_xrefs

- `0x1800168b0`: `MPSSVC.dll`

## pseudocode

```c
__int64 __fastcall Int_FWVerifyCryptoSet(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v5; // r9
  unsigned int v6; // esi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rdx
  _WORD *v12; // [rsp+58h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
  *a3 = 0x10000;
  v12 = 0;
  if ( *(_WORD *)(a2 + 8) >= 0x200u )
  {
    if ( *(_WORD *)(a2 + 8) >= 0x300u )
      *a3 = 0x40000;
    v9 = Int_FwValidateComplianceAndReduceCryptoSetToVersion(a2, a3, *(unsigned __int16 *)(a2 + 8));
    v6 = v9;
    if ( v9 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 173;
        v5 = v9;
        goto LABEL_55;
      }
    }
    else if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 16), 0, 1u, 0xFFu) )
    {
      v5 = 87;
      *a3 = 524296;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 174;
        goto LABEL_55;
      }
    }
    else if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 24), 1, 0, 0x2710u) )
    {
      v5 = 87;
      *a3 = 524289;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 175;
        goto LABEL_55;
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
        v8 = 176;
        goto LABEL_55;
      }
    }
    else if ( (unsigned int)Int_FwValidateString(*(wchar_t **)(a2 + 40), 1, 0, 0x2710u) )
    {
      v5 = 87;
      *a3 = 524295;
      v6 = 87;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 177;
        goto LABEL_55;
      }
    }
    else
    {
      v10 = *(unsigned int *)(a2 + 12);
      if ( (unsigned int)(v10 - 1) <= 1 )
      {
        if ( (_DWORD)v10 == 1 )
        {
          if ( (unsigned int)_o__wcsicmp(*(_QWORD *)(a2 + 16), L"{E5A5D32A-4BCE-4e4d-B07F-4AB1BA7E5FE1}")
            && *(_WORD *)(a2 + 8) < 0x208u )
          {
            v5 = 87;
            *a3 = 1069056;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 179;
              goto LABEL_55;
            }
          }
          else if ( (unsigned int)Int_FwValidatePhase1CryptoSuite(a2, a3) )
          {
            v5 = 87;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 180;
              goto LABEL_55;
            }
          }
        }
        else if ( (_DWORD)v10 == 2 )
        {
          if ( (unsigned int)FwFieldNameMatchStringBegining(
                               L"{E5A5D32A-4BCE-4e4d-B07F-4AB1BA7E5FE2}",
                               *(_QWORD *)(a2 + 16),
                               &v12) == 1
            && *v12 )
          {
            v5 = 87;
            *a3 = 524296;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 181;
              goto LABEL_55;
            }
          }
          else if ( (unsigned int)Int_FwValidatePhase2CryptoSuite(a2, a3) )
          {
            v5 = 87;
            v6 = 87;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 182;
              goto LABEL_55;
            }
          }
        }
        else
        {
          MicrosoftTelemetryAssertTriggeredArgs("MPSSVC.dll", v10, 0);
        }
      }
      else
      {
        v5 = 87;
        *a3 = 1052688;
        v6 = 87;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 178;
          goto LABEL_55;
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
      v8 = 172;
LABEL_55:
      WPP_SF_d(v7[2], v8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, v5);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180016650  mov     [rsp+arg_0], rbx
0x180016655  mov     [rsp+arg_10], rbp
0x18001665a  push    rsi
0x18001665b  push    rdi
0x18001665c  push    r12
0x18001665e  push    r14
0x180016660  push    r15
0x180016662  sub     rsp, 20h
0x180016666  mov     rdi, r8
0x180016669  mov     rbp, rdx
0x18001666c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016673  lea     r14, WPP_GLOBAL_Control
0x18001667a  lea     r15, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x180016681  cmp     rcx, r14
0x180016684  jz      short loc_18001669D
0x180016686  test    byte ptr [rcx+1Ch], 8
0x18001668a  jz      short loc_18001669D
0x18001668c  mov     rcx, [rcx+10h]
0x180016690  mov     edx, 0ABh
0x180016695  mov     r8, r15
0x180016698  call    WPP_SF_
0x18001669d  xor     r12d, r12d
0x1800166a0  mov     dword ptr [rdi], 10000h
0x1800166a6  mov     eax, 200h
0x1800166ab  mov     [rsp+48h+arg_8], r12
0x1800166b0  cmp     [rbp+8], ax
0x1800166b4  jnb     short loc_1800166EB
0x1800166b6  lea     r9d, [r12+57h]
0x1800166bb  mov     dword ptr [rdi], 105050h
0x1800166c1  mov     esi, r9d
0x1800166c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166cb  cmp     rcx, r14
0x1800166ce  jz      loc_1800169D0
0x1800166d4  lea     ebx, [r12+1]
0x1800166d9  test    [rcx+1Ch], bl
0x1800166dc  jz      loc_1800169D0
0x1800166e2  lea     edx, [r9+55h]
0x1800166e6  jmp     loc_1800169C4
0x1800166eb  mov     eax, 300h
0x1800166f0  cmp     [rbp+8], ax
0x1800166f4  jb      short loc_1800166FC
0x1800166f6  mov     dword ptr [rdi], 40000h
0x1800166fc  movzx   r8d, word ptr [rbp+8]
0x180016701  mov     rdx, rdi
0x180016704  mov     rcx, rbp
0x180016707  call    Int_FwValidateComplianceAndReduceCryptoSetToVersion
0x18001670c  mov     esi, eax
0x18001670e  test    eax, eax
0x180016710  jz      short loc_18001673D
0x180016712  mov     rcx, cs:WPP_GLOBAL_Control
0x180016719  cmp     rcx, r14
0x18001671c  jz      loc_1800169D0
0x180016722  mov     ebx, 1
0x180016727  test    [rcx+1Ch], bl
0x18001672a  jz      loc_1800169D0
0x180016730  mov     edx, 0ADh
0x180016735  mov     r9d, eax
0x180016738  jmp     loc_1800169C4
0x18001673d  mov     rcx, [rbp+10h]; Str
0x180016741  mov     ebx, 1
0x180016746  mov     r8d, ebx
0x180016749  mov     r9d, 0FFh
0x18001674f  xor     edx, edx
0x180016751  call    Int_FwValidateString
0x180016756  test    eax, eax
0x180016758  jz      short loc_180016789
0x18001675a  lea     r9d, [rbx+56h]
0x18001675e  mov     dword ptr [rdi], 80008h
0x180016764  mov     esi, r9d
0x180016767  mov     rcx, cs:WPP_GLOBAL_Control
0x18001676e  cmp     rcx, r14
0x180016771  jz      loc_1800169D0
0x180016777  test    [rcx+1Ch], bl
0x18001677a  jz      loc_1800169D0
0x180016780  lea     edx, [r9+57h]
0x180016784  jmp     loc_1800169C4
0x180016789  mov     rcx, [rbp+18h]; Str
0x18001678d  mov     r9d, 2710h
0x180016793  xor     r8d, r8d
0x180016796  mov     edx, ebx
0x180016798  call    Int_FwValidateString
0x18001679d  test    eax, eax
0x18001679f  jz      short loc_1800167D2
0x1800167a1  mov     r9d, 57h ; 'W'
0x1800167a7  mov     dword ptr [rdi], 80001h
0x1800167ad  mov     esi, r9d
0x1800167b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167b7  cmp     rcx, r14
0x1800167ba  jz      loc_1800169D0
0x1800167c0  test    [rcx+1Ch], bl
0x1800167c3  jz      loc_1800169D0
0x1800167c9  lea     edx, [r9+58h]
0x1800167cd  jmp     loc_1800169C4
0x1800167d2  mov     rcx, [rbp+20h]; Str
0x1800167d6  mov     r9d, 2710h
0x1800167dc  xor     r8d, r8d
0x1800167df  mov     edx, ebx
0x1800167e1  call    Int_FwValidateString
0x1800167e6  test    eax, eax
0x1800167e8  jz      short loc_18001681B
0x1800167ea  mov     r9d, 57h ; 'W'
0x1800167f0  mov     dword ptr [rdi], 80002h
0x1800167f6  mov     esi, r9d
0x1800167f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180016800  cmp     rcx, r14
0x180016803  jz      loc_1800169D0
0x180016809  test    [rcx+1Ch], bl
0x18001680c  jz      loc_1800169D0
0x180016812  lea     edx, [r9+59h]
0x180016816  jmp     loc_1800169C4
0x18001681b  mov     rcx, [rbp+28h]; Str
0x18001681f  mov     r9d, 2710h
0x180016825  xor     r8d, r8d
0x180016828  mov     edx, ebx
0x18001682a  call    Int_FwValidateString
0x18001682f  test    eax, eax
0x180016831  jz      short loc_180016864
0x180016833  mov     r9d, 57h ; 'W'
0x180016839  mov     dword ptr [rdi], 80007h
0x18001683f  mov     esi, r9d
0x180016842  mov     rcx, cs:WPP_GLOBAL_Control
0x180016849  cmp     rcx, r14
0x18001684c  jz      loc_1800169D0
0x180016852  test    [rcx+1Ch], bl
0x180016855  jz      loc_1800169D0
0x18001685b  lea     edx, [r9+5Ah]
0x18001685f  jmp     loc_1800169C4
0x180016864  mov     edx, [rbp+0Ch]
0x180016867  lea     eax, [rdx-1]
0x18001686a  cmp     eax, ebx
0x18001686c  jbe     short loc_18001689F
0x18001686e  mov     r9d, 57h ; 'W'
0x180016874  mov     dword ptr [rdi], 101010h
0x18001687a  mov     esi, r9d
0x18001687d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016884  cmp     rcx, r14
0x180016887  jz      loc_1800169D0
0x18001688d  test    [rcx+1Ch], bl
0x180016890  jz      loc_1800169D0
0x180016896  lea     edx, [r9+5Bh]
0x18001689a  jmp     loc_1800169C4
0x18001689f  mov     ecx, edx
0x1800168a1  sub     ecx, ebx
0x1800168a3  jz      loc_180016951
0x1800168a9  cmp     ecx, ebx
0x1800168ab  jz      short loc_1800168C1
0x1800168ad  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "FALSE", "pCrypto->IpSecPhase")
0x1800168b0  lea     rcx, aMpssvcDll; "MPSSVC.dll"
0x1800168b7  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800168bc  jmp     loc_1800169D0
0x1800168c1  mov     rdx, [rbp+10h]
0x1800168c5  lea     r8, [rsp+48h+arg_8]
0x1800168ca  lea     rcx, aE5a5d32a4bce4e_2; "{E5A5D32A-4BCE-4e4d-B07F-4AB1BA7E5FE2}"
0x1800168d1  call    FwFieldNameMatchStringBegining
0x1800168d6  cmp     eax, ebx
0x1800168d8  jnz     short loc_180016916
0x1800168da  mov     rax, [rsp+48h+arg_8]
0x1800168df  cmp     [rax], r12w
0x1800168e3  jz      short loc_180016916
0x1800168e5  mov     r9d, 57h ; 'W'
0x1800168eb  mov     dword ptr [rdi], 80008h
0x1800168f1  mov     esi, r9d
0x1800168f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168fb  cmp     rcx, r14
0x1800168fe  jz      loc_1800169D0
0x180016904  test    [rcx+1Ch], bl
0x180016907  jz      loc_1800169D0
0x18001690d  lea     edx, [r9+5Eh]
0x180016911  jmp     loc_1800169C4
0x180016916  mov     rdx, rdi
0x180016919  mov     rcx, rbp
0x18001691c  call    Int_FwValidatePhase2CryptoSuite
0x180016921  test    eax, eax
0x180016923  jz      loc_1800169D0
0x180016929  mov     r9d, 57h ; 'W'
0x18001692f  mov     esi, r9d
0x180016932  mov     rcx, cs:WPP_GLOBAL_Control
0x180016939  cmp     rcx, r14
0x18001693c  jz      loc_1800169D0
0x180016942  test    [rcx+1Ch], bl
0x180016945  jz      loc_1800169D0
0x18001694b  lea     edx, [r9+5Fh]
0x18001694f  jmp     short loc_1800169C4
0x180016951  mov     rcx, [rbp+10h]
0x180016955  lea     rdx, aE5a5d32a4bce4e_0; "{E5A5D32A-4BCE-4e4d-B07F-4AB1BA7E5FE1}"
0x18001695c  call    cs:__imp__o__wcsicmp
0x180016962  test    eax, eax
0x180016964  jz      short loc_180016997
0x180016966  mov     eax, 208h
0x18001696b  cmp     [rbp+8], ax
0x18001696f  jnb     short loc_180016997
0x180016971  mov     r9d, 57h ; 'W'
0x180016977  mov     dword ptr [rdi], 105000h
0x18001697d  mov     esi, r9d
0x180016980  mov     rcx, cs:WPP_GLOBAL_Control
0x180016987  cmp     rcx, r14
0x18001698a  jz      short loc_1800169D0
0x18001698c  test    [rcx+1Ch], bl
0x18001698f  jz      short loc_1800169D0
0x180016991  lea     edx, [r9+5Ch]
0x180016995  jmp     short loc_1800169C4
0x180016997  mov     rdx, rdi
0x18001699a  mov     rcx, rbp
0x18001699d  call    Int_FwValidatePhase1CryptoSuite
0x1800169a2  test    eax, eax
0x1800169a4  jz      short loc_1800169D0
0x1800169a6  mov     r9d, 57h ; 'W'
0x1800169ac  mov     esi, r9d
0x1800169af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169b6  cmp     rcx, r14
0x1800169b9  jz      short loc_1800169D0
0x1800169bb  test    [rcx+1Ch], bl
0x1800169be  jz      short loc_1800169D0
0x1800169c0  lea     edx, [r9+5Dh]
0x1800169c4  mov     rcx, [rcx+10h]
0x1800169c8  mov     r8, r15
0x1800169cb  call    WPP_SF_d
0x1800169d0  mov     rbx, [rsp+48h+arg_0]
0x1800169d5  mov     eax, esi
0x1800169d7  mov     rbp, [rsp+48h+arg_10]
0x1800169dc  add     rsp, 20h
0x1800169e0  pop     r15
0x1800169e2  pop     r14
0x1800169e4  pop     r12
0x1800169e6  pop     rdi
0x1800169e7  pop     rsi
0x1800169e8  retn
```
