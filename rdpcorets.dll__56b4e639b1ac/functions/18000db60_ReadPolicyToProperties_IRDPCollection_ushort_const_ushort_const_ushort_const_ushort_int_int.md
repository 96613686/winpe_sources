# ReadPolicyToProperties(IRDPCollection *,ushort const *,ushort const *,ushort const *,ushort,int,int *)

- ea: `0x18000db60`
- end: `0x18000df9f`
- name: `?ReadPolicyToProperties@@YAJPEAUIRDPCollection@@PEBG11GHPEAH@Z`
- size: `1087`
- prototype: `int(struct IRDPCollection *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16, int, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18006233c`

## callees

- `0x1800091a8`
- `0x18000db60`
- `0x18002e600`
- `0x180033da0`
- `0x180059838`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dc71`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dcf8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dc71`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dcf8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dbfe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dcb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dbfe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dcb8`
- `OLEAUT32!__imp_SysAllocString` at `0x18000de25`
- `OLEAUT32!__imp_SysAllocString` at `0x18000de25`
- `OLEAUT32!__imp_VariantInit` at `0x18000dbdb`
- `OLEAUT32!__imp_VariantInit` at `0x18000dbdb`
- `OLEAUT32!__imp_VariantClear` at `0x18000dd20`
- `OLEAUT32!__imp_VariantClear` at `0x18000dd20`

## pseudocode

```c
__int64 __fastcall ReadPolicyToProperties(
        struct IRDPCollection *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 a5,
        int a6,
        int *a7)
{
  int v8; // r14d
  int v9; // esi
  int v10; // r13d
  LSTATUS v12; // edi
  LSTATUS Value; // eax
  int v14; // eax
  LSTATUS v15; // eax
  LSTATUS v16; // edi
  __int64 result; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v19; // edx
  const char *v20; // rcx
  LPDWORD lpcbData; // [rsp+30h] [rbp-D8h]
  __int64 cbData; // [rsp+38h] [rbp-D0h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B8h] BYREF
  struct IRDPCollection *v26; // [rsp+58h] [rbp-B0h]
  VARIANTARG pvarg; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+78h] [rbp-90h]
  OLECHAR psz[264]; // [rsp+88h] [rbp-80h] BYREF

  v8 = 0;
  v26 = a1;
  v9 = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  v10 = 0;
  hKey = 0;
  *(_QWORD *)&pvarg.vt = a4;
  *(_OWORD *)&pvarg.decVal.Lo32 = 0;
  v28 = 0;
  VariantInit((VARIANTARG *)&pvarg.decVal.8);
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey);
  if ( v12 )
    goto LABEL_12;
  if ( a5 == 8 )
  {
    LODWORD(cbData) = 520;
    psz[0] = 0;
    v8 = 1;
    Value = RegQueryValueExW(hKey, a3, 0, (LPDWORD)&cbData + 1, (LPBYTE)psz, (LPDWORD)&cbData);
    goto LABEL_5;
  }
  if ( ((a5 - 11) & 0xFFF7) == 0 )
  {
    v8 = 4;
    LODWORD(cbData) = 4;
    Value = RegQueryValueExW(hKey, a3, 0, (LPDWORD)&cbData + 1, Data, (LPDWORD)&cbData);
LABEL_5:
    v12 = Value;
    goto LABEL_6;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5a582c1ff5bf36125383cd1c3d5e99aa_Traceguids, a5);
  }
LABEL_6:
  v14 = HIDWORD(cbData);
  if ( HIDWORD(cbData) == v8 && !v12 )
  {
LABEL_26:
    if ( v14 != v8 )
      goto LABEL_12;
    switch ( a5 )
    {
      case 8u:
        pvarg.iVal = 8;
        pvarg.pRecInfo = (IRecordInfo *)SysAllocString(psz);
        v9 = (*(__int64 (__fastcall **)(struct IRDPCollection *, _QWORD, CY *))(*(_QWORD *)v26 + 56LL))(
               v26,
               *(_QWORD *)&pvarg.vt,
               &pvarg.cyVal);
        if ( v9 < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_12;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v19 = 11;
          v20 = "Failed to set the string propery";
          break;
        }
LABEL_46:
        v10 = 1;
        goto LABEL_12;
      case 0x13u:
        v9 = (*(__int64 (__fastcall **)(struct IRDPCollection *, _QWORD, _QWORD))(*(_QWORD *)v26 + 72LL))(
               v26,
               *(_QWORD *)&pvarg.vt,
               *(unsigned int *)Data);
        if ( v9 >= 0 )
          goto LABEL_46;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_12;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 12;
        v20 = "Failed to set a ulong policy property";
        break;
      case 0xBu:
        v9 = (*(__int64 (__fastcall **)(struct IRDPCollection *, _QWORD, bool))(*(_QWORD *)v26 + 64LL))(
               v26,
               *(_QWORD *)&pvarg.vt,
               *(_DWORD *)Data != 0);
        if ( v9 >= 0 )
          goto LABEL_46;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_12;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 13;
        v20 = "Failed to set a bool property";
        break;
      default:
        goto LABEL_12;
    }
    LODWORD(lpcbData) = v9;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      (unsigned int)WPP_5a582c1ff5bf36125383cd1c3d5e99aa_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v20,
      lpcbData,
      cbData);
    goto LABEL_12;
  }
  if ( a6 )
  {
    phkResult = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
            0,
            0x20019u,
            &phkResult) )
    {
      if ( v8 == 1 )
      {
        LODWORD(cbData) = 520;
        psz[0] = 0;
        v15 = RegQueryValueExW(phkResult, a3, 0, (LPDWORD)&cbData + 1, (LPBYTE)psz, (LPDWORD)&cbData);
      }
      else
      {
        LODWORD(cbData) = 4;
        v15 = RegQueryValueExW(phkResult, a3, 0, (LPDWORD)&cbData + 1, Data, (LPDWORD)&cbData);
      }
      v16 = v15;
      RegCloseKey(phkResult);
      if ( !v16 )
      {
        v14 = HIDWORD(cbData);
        goto LABEL_26;
      }
    }
  }
LABEL_12:
  VariantClear((VARIANTARG *)&pvarg.decVal.8);
  if ( hKey )
    RegCloseKey(hKey);
  result = (unsigned int)v9;
  if ( a7 )
    *a7 = v10;
  return result;
}

```

## disassembly

```asm
0x18000db60  mov     r11, rsp
0x18000db63  push    rbp
0x18000db64  push    rbx
0x18000db65  push    rsi
0x18000db66  push    r13
0x18000db68  lea     rbp, [r11-1E8h]
0x18000db6f  sub     rsp, 2C8h
0x18000db76  mov     rax, cs:__security_cookie
0x18000db7d  xor     rax, rsp
0x18000db80  mov     [rbp+1E0h+var_50], rax
0x18000db87  mov     rbx, [rbp+1E0h+arg_30]
0x18000db8e  xorps   xmm0, xmm0
0x18000db91  mov     [r11-28h], rdi
0x18000db95  xor     eax, eax
0x18000db97  mov     [r11-38h], r14
0x18000db9b  mov     rdi, rdx
0x18000db9e  xor     r14d, r14d
0x18000dba1  mov     [rsp+2E0h+var_290], rcx
0x18000dba6  mov     [r11-40h], r15
0x18000dbaa  lea     rcx, [rsp+2E0h+pvarg+8]; pvarg
0x18000dbaf  mov     esi, r14d
0x18000dbb2  mov     dword ptr [rsp+2E0h+Data], r14d
0x18000dbb7  mov     [rsp+2E0h+cbData], r14d
0x18000dbbc  mov     r13d, r14d
0x18000dbbf  mov     [rsp+2E0h+Type], r14d
0x18000dbc4  mov     r15, r8
0x18000dbc7  mov     [rsp+2E0h+hKey], r14
0x18000dbcc  mov     qword ptr [rsp+2E0h+pvarg], r9
0x18000dbd1  movups  xmmword ptr [rsp+2E0h+pvarg+8], xmm0
0x18000dbd6  mov     [rsp+2E0h+var_270], rax
0x18000dbdb  call    cs:__imp_VariantInit
0x18000dbe1  lea     rax, [rsp+2E0h+hKey]
0x18000dbe6  mov     r9d, 20019h; samDesired
0x18000dbec  xor     r8d, r8d; ulOptions
0x18000dbef  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18000dbf4  mov     rdx, rdi; lpSubKey
0x18000dbf7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000dbfe  call    cs:__imp_RegOpenKeyExW
0x18000dc04  mov     edi, eax
0x18000dc06  test    eax, eax
0x18000dc08  jnz     loc_18000DD1B
0x18000dc0e  mov     [rsp+2E0h+var_28], r12
0x18000dc16  lea     rdx, WPP_GLOBAL_Control
0x18000dc1d  movzx   r12d, [rbp+1E0h+arg_20]
0x18000dc25  cmp     r12d, 8
0x18000dc29  jz      loc_18000DD74
0x18000dc2f  lea     eax, [r12-0Bh]
0x18000dc34  mov     ecx, 0FFF7h
0x18000dc39  test    cx, ax
0x18000dc3c  jnz     loc_18000DD9B
0x18000dc42  lea     rax, [rsp+2E0h+cbData]
0x18000dc47  mov     r14d, 4
0x18000dc4d  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18000dc52  lea     rax, [rsp+2E0h+Data]
0x18000dc57  mov     [rsp+2E0h+cbData], r14d
0x18000dc5c  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000dc61  lea     r9, [rsp+2E0h+Type]; lpType
0x18000dc66  xor     r8d, r8d; lpReserved
0x18000dc69  mov     [rsp+2E0h+phkResult], rax; lpData
0x18000dc6e  mov     rdx, r15; lpValueName
0x18000dc71  call    cs:__imp_RegQueryValueExW
0x18000dc77  mov     edi, eax
0x18000dc79  mov     eax, [rsp+2E0h+Type]
0x18000dc7d  cmp     eax, r14d
0x18000dc80  jz      loc_18000DDDC
0x18000dc86  cmp     [rbp+1E0h+arg_28], esi
0x18000dc8c  jz      loc_18000DD13
0x18000dc92  lea     rax, [rsp+2E0h+var_2A0]
0x18000dc97  mov     [rsp+2E0h+var_2A0], rsi
0x18000dc9c  mov     r9d, 20019h; samDesired
0x18000dca2  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18000dca7  xor     r8d, r8d; ulOptions
0x18000dcaa  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Ter"...
0x18000dcb1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000dcb8  call    cs:__imp_RegOpenKeyExW
0x18000dcbe  test    eax, eax
0x18000dcc0  jnz     short loc_18000DD13
0x18000dcc2  mov     rcx, [rsp+2E0h+var_2A0]; hKey
0x18000dcc7  lea     r9, [rsp+2E0h+Type]; lpType
0x18000dccc  xor     r8d, r8d; lpReserved
0x18000dccf  mov     rdx, r15; lpValueName
0x18000dcd2  cmp     r14d, 1
0x18000dcd6  jz      loc_18000DDE5
0x18000dcdc  lea     rax, [rsp+2E0h+cbData]
0x18000dce1  mov     [rsp+2E0h+cbData], 4
0x18000dce9  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18000dcee  lea     rax, [rsp+2E0h+Data]
0x18000dcf3  mov     [rsp+2E0h+phkResult], rax; lpData
0x18000dcf8  call    cs:__imp_RegQueryValueExW
0x18000dcfe  mov     rcx, [rsp+2E0h+var_2A0]; hKey
0x18000dd03  mov     edi, eax
0x18000dd05  call    cs:__imp_RegCloseKey
0x18000dd0b  test    edi, edi
0x18000dd0d  jz      loc_18000DE06
0x18000dd13  mov     r12, [rsp+2E0h+var_28]
0x18000dd1b  lea     rcx, [rsp+2E0h+pvarg+8]; pvarg
0x18000dd20  call    cs:__imp_VariantClear
0x18000dd26  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000dd2b  mov     r15, [rsp+2E0h+var_38]
0x18000dd33  mov     r14, [rsp+2E0h+var_30]
0x18000dd3b  mov     rdi, [rsp+2C0h]
0x18000dd43  test    rcx, rcx
0x18000dd46  jz      short loc_18000DD4E
0x18000dd48  call    cs:__imp_RegCloseKey
0x18000dd4e  mov     eax, esi
0x18000dd50  test    rbx, rbx
0x18000dd53  jz      short loc_18000DD58
0x18000dd55  mov     [rbx], r13d
0x18000dd58  mov     rcx, [rbp+1E0h+var_50]
0x18000dd5f  xor     rcx, rsp; StackCookie
0x18000dd62  call    __security_check_cookie
0x18000dd67  add     rsp, 2C8h
0x18000dd6e  pop     r13
0x18000dd70  pop     rsi
0x18000dd71  pop     rbx
0x18000dd72  pop     rbp
0x18000dd73  retn
0x18000dd74  xor     eax, eax
0x18000dd76  mov     [rsp+2E0h+cbData], 208h
0x18000dd7e  mov     [rbp+1E0h+psz], ax
0x18000dd82  mov     r14d, 1
0x18000dd88  lea     rax, [rsp+2E0h+cbData]
0x18000dd8d  mov     [rsp+2E0h+lpcbData], rax
0x18000dd92  lea     rax, [rbp+1E0h+psz]
0x18000dd96  jmp     loc_18000DC5C
0x18000dd9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dda2  cmp     rcx, rdx
0x18000dda5  jz      loc_18000DC79
0x18000ddab  test    byte ptr [rcx+1Ch], 1
0x18000ddaf  jz      loc_18000DC79
0x18000ddb5  cmp     byte ptr [rcx+19h], 1
0x18000ddb9  jb      loc_18000DC79
0x18000ddbf  mov     rcx, [rcx+10h]
0x18000ddc3  lea     r8, WPP_5a582c1ff5bf36125383cd1c3d5e99aa_Traceguids
0x18000ddca  mov     r9d, r12d
0x18000ddcd  mov     edx, 0Ah
0x18000ddd2  call    WPP_SF_d
0x18000ddd7  jmp     loc_18000DC79
0x18000dddc  test    edi, edi
0x18000ddde  jz      short loc_18000DE0A
0x18000dde0  jmp     loc_18000DC86
0x18000dde5  xor     eax, eax
0x18000dde7  mov     [rsp+2E0h+cbData], 208h
0x18000ddef  mov     [rbp+1E0h+psz], ax
0x18000ddf3  lea     rax, [rsp+2E0h+cbData]
0x18000ddf8  mov     [rsp+2E0h+lpcbData], rax
0x18000ddfd  lea     rax, [rbp+1E0h+psz]
0x18000de01  jmp     loc_18000DCF3
0x18000de06  mov     eax, [rsp+2E0h+Type]
0x18000de0a  cmp     eax, r14d
0x18000de0d  jnz     loc_18000DD13
0x18000de13  cmp     r12d, 8
0x18000de17  jnz     short loc_18000DE96
0x18000de19  mov     eax, r12d
0x18000de1c  lea     rcx, [rbp+1E0h+psz]; psz
0x18000de20  mov     word ptr [rsp+2E0h+pvarg+8], ax
0x18000de25  call    cs:__imp_SysAllocString
0x18000de2b  mov     rcx, [rsp+2E0h+var_290]
0x18000de30  lea     r8, [rsp+2E0h+pvarg+8]
0x18000de35  mov     rdx, qword ptr [rsp+2E0h+pvarg]
0x18000de3a  mov     qword ptr [rsp+2E0h+pvarg+10h], rax
0x18000de3f  mov     rax, [rcx]
0x18000de42  mov     rax, [rax+38h]
0x18000de46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de4b  mov     esi, eax
0x18000de4d  test    eax, eax
0x18000de4f  jns     loc_18000DF94
0x18000de55  mov     rax, cs:WPP_GLOBAL_Control
0x18000de5c  lea     rcx, WPP_GLOBAL_Control
0x18000de63  cmp     rax, rcx
0x18000de66  jz      loc_18000DD13
0x18000de6c  test    [rax+1Ch], r12b
0x18000de70  jz      loc_18000DD13
0x18000de76  cmp     byte ptr [rax+19h], 2
0x18000de7a  jb      loc_18000DD13
0x18000de80  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000de85  mov     edx, 0Bh
0x18000de8a  lea     rcx, aFailedToSetThe_17; "Failed to set the string propery"
0x18000de91  jmp     loc_18000DF6C
0x18000de96  cmp     r12d, 13h
0x18000de9a  jnz     short loc_18000DEFF
0x18000de9c  mov     rcx, [rsp+2E0h+var_290]
0x18000dea1  mov     r8d, dword ptr [rsp+2E0h+Data]
0x18000dea6  mov     rdx, qword ptr [rsp+2E0h+pvarg]
0x18000deab  mov     rax, [rcx]
0x18000deae  mov     rax, [rax+48h]
0x18000deb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deb7  mov     esi, eax
0x18000deb9  test    eax, eax
0x18000debb  jns     loc_18000DF94
0x18000dec1  mov     rax, cs:WPP_GLOBAL_Control
0x18000dec8  lea     rcx, WPP_GLOBAL_Control
0x18000decf  cmp     rax, rcx
0x18000ded2  jz      loc_18000DD13
0x18000ded8  test    byte ptr [rax+1Ch], 8
0x18000dedc  jz      loc_18000DD13
0x18000dee2  cmp     byte ptr [rax+19h], 2
0x18000dee6  jb      loc_18000DD13
0x18000deec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000def1  mov     edx, 0Ch
0x18000def6  lea     rcx, aFailedToSetAUl; "Failed to set a ulong policy property"
0x18000defd  jmp     short loc_18000DF6C
0x18000deff  cmp     r12d, 0Bh
0x18000df03  jnz     loc_18000DD13
0x18000df09  mov     rcx, [rsp+2E0h+var_290]
0x18000df0e  xor     r8d, r8d
0x18000df11  cmp     dword ptr [rsp+2E0h+Data], esi
0x18000df15  mov     rdx, qword ptr [rsp+2E0h+pvarg]
0x18000df1a  setnz   r8b
0x18000df1e  mov     rax, [rcx]
0x18000df21  mov     rax, [rax+40h]
0x18000df25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df2a  mov     esi, eax
0x18000df2c  test    eax, eax
0x18000df2e  jns     short loc_18000DF94
0x18000df30  mov     rax, cs:WPP_GLOBAL_Control
0x18000df37  lea     rcx, WPP_GLOBAL_Control
0x18000df3e  cmp     rax, rcx
0x18000df41  jz      loc_18000DD13
0x18000df47  test    byte ptr [rax+1Ch], 8
0x18000df4b  jz      loc_18000DD13
0x18000df51  cmp     byte ptr [rax+19h], 2
0x18000df55  jb      loc_18000DD13
0x18000df5b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000df60  mov     edx, 0Dh
0x18000df65  lea     rcx, aFailedToSetABo; "Failed to set a bool property"
0x18000df6c  mov     dword ptr [rsp+2E0h+lpcbData], esi
0x18000df70  lea     r8, WPP_5a582c1ff5bf36125383cd1c3d5e99aa_Traceguids
0x18000df77  mov     [rsp+2E0h+phkResult], rcx
0x18000df7c  mov     r9d, eax
0x18000df7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df86  mov     rcx, [rcx+10h]
0x18000df8a  call    WPP_SF_DsD
0x18000df8f  jmp     loc_18000DD13
0x18000df94  mov     r13d, 1
0x18000df9a  jmp     loc_18000DD13
```
