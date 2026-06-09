# UnMarshallRegistryNFAObject

- ea: `0x18003ab84`
- end: `0x18003b067`
- name: `UnMarshallRegistryNFAObject`
- size: `1251`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180039788`

## callees

- `0x180006f00`
- `0x180006f60`
- `0x18000c828`
- `0x18000e510`
- `0x180039f64`
- `0x18003ab84`
- `0x180042c6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003adc7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003af15`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003adc7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003af15`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ac41`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ac41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b04e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b04e`

## pseudocode

```c
__int64 __fastcall UnMarshallRegistryNFAObject(
        HKEY hKey,
        __int64 a2,
        unsigned __int16 *a3,
        _QWORD *a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6)
{
  unsigned __int64 v7; // r10
  __int64 v8; // r8
  __int64 v10; // r9
  unsigned int Value; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  _QWORD *v14; // rdi
  unsigned __int16 *v15; // r14
  unsigned __int16 *v16; // rax
  __int64 v17; // r9
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  unsigned __int16 *v20; // rcx
  unsigned __int16 *v21; // rcx
  unsigned __int16 **v22; // rax
  DWORD Type; // [rsp+30h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-24h] BYREF
  BYTE v26[8]; // [rsp+38h] [rbp-20h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+58h] BYREF

  v7 = -1;
  hKeya = 0;
  v8 = -1;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v26 = 0;
  do
    ++v8;
  while ( *(_WORD *)(a2 + 2 * v8) );
  if ( !a3 || !*a3 )
  {
    v10 = 13;
    Value = 13;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_60;
    v13 = 45;
    goto LABEL_59;
  }
  do
    ++v7;
  while ( a3[v7] );
  if ( v7 > (unsigned int)(v8 + 1) )
  {
    Value = RegOpenKeyExW(hKey, &a3[(unsigned int)v8 + 1], 0, 0x20019u, &hKeya);
    if ( Value )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_60;
      v13 = 47;
      v10 = Value;
      goto LABEL_59;
    }
    v14 = IpsecAllocMem(0x58u);
    if ( !v14 )
    {
      v10 = 14;
      Value = 14;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_60;
      v13 = 48;
      goto LABEL_59;
    }
    v15 = 0;
    v16 = IpsecAllocStr(a3);
    *v14 = v16;
    if ( !v16 )
    {
      v17 = 14;
      Value = 14;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v19 = 49;
LABEL_53:
        WPP_SF_d(v18[2], v19, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, v17);
      }
LABEL_54:
      FreeIpsecNFAObject(v14);
      if ( v15 )
        IpsecFreeMem(v15);
      goto LABEL_60;
    }
    RegstoreQueryValue(hKeya, L"ipsecName", (__int64)&cbData);
    RegstoreQueryValue(hKeya, L"description", (__int64)&cbData);
    Value = RegstoreQueryValue(hKeya, L"ipsecID", (__int64)&cbData);
    if ( Value )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_54;
      v19 = 50;
    }
    else
    {
      Type = 4;
      cbData = 4;
      Value = RegQueryValueExW(hKeya, L"ipsecDataType", 0, &Type, Data, &cbData);
      if ( Value )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_54;
        v19 = 51;
      }
      else
      {
        *((_DWORD *)v14 + 6) = *(_DWORD *)Data;
        Value = RegstoreQueryValue(hKeya, L"ipsecData", (__int64)(v14 + 5));
        if ( Value )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            goto LABEL_54;
          }
          v19 = 52;
        }
        else
        {
          RegstoreQueryValue(hKeya, L"ipsecOwnersReference", (__int64)&cbData);
          Value = RegstoreQueryValue(hKeya, L"ipsecNegotiationPolicyReference", (__int64)&cbData);
          if ( Value )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
            {
              goto LABEL_54;
            }
            v19 = 53;
          }
          else
          {
            RegstoreQueryValue(hKeya, L"ipsecFilterReference", (__int64)&cbData);
            Type = 4;
            cbData = 4;
            Value = RegQueryValueExW(hKeya, L"whenChanged", 0, &Type, v26, &cbData);
            if ( !Value )
            {
              v20 = (unsigned __int16 *)v14[7];
              *((_DWORD *)v14 + 18) = *(_DWORD *)v26;
              if ( !v20 || !*v20 || (v15 = IpsecAllocStr(v20)) != 0 )
              {
                v21 = IpsecAllocStr((unsigned __int16 *)v14[8]);
                if ( v21 )
                  goto LABEL_61;
                v17 = 14;
                Value = 14;
                v18 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
                {
                  goto LABEL_54;
                }
                v19 = 56;
                goto LABEL_53;
              }
              v17 = 14;
              Value = 14;
              v18 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                v19 = 55;
                goto LABEL_53;
              }
              goto LABEL_54;
            }
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
            {
              goto LABEL_54;
            }
            v19 = 54;
          }
        }
      }
    }
    v17 = Value;
    goto LABEL_53;
  }
  v10 = 13;
  Value = 13;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
    goto LABEL_60;
  v13 = 46;
LABEL_59:
  WPP_SF_d(v12[2], v13, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, v10);
LABEL_60:
  v21 = 0;
  v15 = 0;
  v14 = 0;
LABEL_61:
  v22 = a5;
  *a4 = v14;
  *v22 = v15;
  *a6 = v21;
  if ( hKeya )
    RegCloseKey(hKeya);
  return Value;
}

```

## disassembly

```asm
0x18003ab84  push    rbp
0x18003ab86  push    rbx
0x18003ab87  push    rsi
0x18003ab88  push    rdi
0x18003ab89  push    r12
0x18003ab8b  push    r13
0x18003ab8d  push    r14
0x18003ab8f  push    r15
0x18003ab91  mov     rbp, rsp
0x18003ab94  sub     rsp, 58h
0x18003ab98  xor     r13d, r13d
0x18003ab9b  mov     rsi, r8
0x18003ab9e  or      r10, 0FFFFFFFFFFFFFFFFh
0x18003aba2  mov     [rbp+hKey], r13
0x18003aba6  mov     r8, r10
0x18003aba9  mov     [rbp+Type], r13d
0x18003abad  mov     r12, r9
0x18003abb0  mov     [rbp+cbData], r13d
0x18003abb4  mov     r11, rcx
0x18003abb7  mov     dword ptr [rbp+Data], r13d
0x18003abbb  mov     dword ptr [rbp+var_20], r13d
0x18003abbf  inc     r8
0x18003abc2  cmp     [rdx+r8*2], r13w
0x18003abc7  jnz     short loc_18003ABBF
0x18003abc9  test    rsi, rsi
0x18003abcc  jz      loc_18003AFF4
0x18003abd2  cmp     [rsi], r13w
0x18003abd6  jz      loc_18003AFF4
0x18003abdc  inc     r10
0x18003abdf  cmp     [rsi+r10*2], r13w
0x18003abe4  jnz     short loc_18003ABDC
0x18003abe6  lea     ecx, [r8+1]
0x18003abea  cmp     r10, rcx
0x18003abed  ja      short loc_18003AC22
0x18003abef  mov     r9d, 0Dh
0x18003abf5  mov     ebx, r9d
0x18003abf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003abff  lea     rax, WPP_GLOBAL_Control
0x18003ac06  cmp     rcx, rax
0x18003ac09  jz      loc_18003B02A
0x18003ac0f  test    byte ptr [rcx+1Ch], 10h
0x18003ac13  jz      loc_18003B02A
0x18003ac19  lea     edx, [r9+21h]
0x18003ac1d  jmp     loc_18003B01A
0x18003ac22  mov     eax, r8d
0x18003ac25  mov     r9d, 20019h; samDesired
0x18003ac2b  inc     rax
0x18003ac2e  xor     r8d, r8d; ulOptions
0x18003ac31  mov     rcx, r11; hKey
0x18003ac34  lea     rdx, [rsi+rax*2]; lpSubKey
0x18003ac38  lea     rax, [rbp+hKey]
0x18003ac3c  mov     [rsp+58h+phkResult], rax; phkResult
0x18003ac41  call    cs:__imp_RegOpenKeyExW
0x18003ac47  mov     ebx, eax
0x18003ac49  test    eax, eax
0x18003ac4b  jz      short loc_18003AC7B
0x18003ac4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac54  lea     rax, WPP_GLOBAL_Control
0x18003ac5b  cmp     rcx, rax
0x18003ac5e  jz      loc_18003B02A
0x18003ac64  test    byte ptr [rcx+1Ch], 10h
0x18003ac68  jz      loc_18003B02A
0x18003ac6e  mov     edx, 2Fh ; '/'
0x18003ac73  mov     r9d, ebx
0x18003ac76  jmp     loc_18003B01A
0x18003ac7b  mov     ecx, 58h ; 'X'
0x18003ac80  call    IpsecAllocMem
0x18003ac85  mov     rdi, rax
0x18003ac88  test    rax, rax
0x18003ac8b  jnz     short loc_18003ACBD
0x18003ac8d  lea     r9d, [rax+0Eh]
0x18003ac91  mov     ebx, r9d
0x18003ac94  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac9b  lea     rax, WPP_GLOBAL_Control
0x18003aca2  cmp     rcx, rax
0x18003aca5  jz      loc_18003B02A
0x18003acab  test    byte ptr [rcx+1Ch], 10h
0x18003acaf  jz      loc_18003B02A
0x18003acb5  lea     edx, [rdi+30h]
0x18003acb8  jmp     loc_18003B01A
0x18003acbd  mov     rcx, rsi; unsigned __int16 *
0x18003acc0  mov     r14, r13
0x18003acc3  call    IpsecAllocStr
0x18003acc8  mov     [rdi], rax
0x18003accb  test    rax, rax
0x18003acce  jnz     short loc_18003AD01
0x18003acd0  lea     r9d, [rax+0Eh]
0x18003acd4  mov     ebx, r9d
0x18003acd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003acde  lea     rax, WPP_GLOBAL_Control
0x18003ace5  cmp     rcx, rax
0x18003ace8  jz      loc_18003AFDD
0x18003acee  test    byte ptr [rcx+1Ch], 10h
0x18003acf2  jz      loc_18003AFDD
0x18003acf8  lea     edx, [r9+23h]
0x18003acfc  jmp     loc_18003AFCD
0x18003ad01  mov     rcx, [rbp+hKey]; hKey
0x18003ad05  lea     rax, [rbp+cbData]
0x18003ad09  mov     esi, 1
0x18003ad0e  mov     [rsp+58h+phkResult], rax; __int64
0x18003ad13  mov     r8d, esi
0x18003ad16  lea     r9, [rdi+8]
0x18003ad1a  lea     rdx, aIpsecname; "ipsecName"
0x18003ad21  call    RegstoreQueryValue
0x18003ad26  mov     rcx, [rbp+hKey]; hKey
0x18003ad2a  lea     rax, [rbp+cbData]
0x18003ad2e  lea     r9, [rdi+50h]
0x18003ad32  mov     [rsp+58h+phkResult], rax; __int64
0x18003ad37  mov     r8d, esi
0x18003ad3a  lea     rdx, aDescription; "description"
0x18003ad41  call    RegstoreQueryValue
0x18003ad46  mov     rcx, [rbp+hKey]; hKey
0x18003ad4a  lea     rax, [rbp+cbData]
0x18003ad4e  lea     r9, [rdi+10h]
0x18003ad52  mov     [rsp+58h+phkResult], rax; __int64
0x18003ad57  mov     r8d, esi
0x18003ad5a  lea     rdx, aIpsecid; "ipsecID"
0x18003ad61  call    RegstoreQueryValue
0x18003ad66  mov     ebx, eax
0x18003ad68  test    eax, eax
0x18003ad6a  jz      short loc_18003AD98
0x18003ad6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ad73  lea     rax, WPP_GLOBAL_Control
0x18003ad7a  cmp     rcx, rax
0x18003ad7d  jz      loc_18003AFDD
0x18003ad83  test    byte ptr [rcx+1Ch], 10h
0x18003ad87  jz      loc_18003AFDD
0x18003ad8d  lea     edx, [rsi+31h]
0x18003ad90  mov     r9d, ebx
0x18003ad93  jmp     loc_18003AFCD
0x18003ad98  mov     rcx, [rbp+hKey]; hKey
0x18003ad9c  lea     r9, [rbp+Type]; lpType
0x18003ada0  mov     eax, 4
0x18003ada5  lea     rdx, aIpsecdatatype; "ipsecDataType"
0x18003adac  mov     [rbp+Type], eax
0x18003adaf  xor     r8d, r8d; lpReserved
0x18003adb2  mov     [rbp+cbData], eax
0x18003adb5  lea     rax, [rbp+cbData]
0x18003adb9  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18003adbe  lea     rax, [rbp+Data]
0x18003adc2  mov     [rsp+58h+phkResult], rax; lpData
0x18003adc7  call    cs:__imp_RegQueryValueExW
0x18003adcd  mov     ebx, eax
0x18003adcf  test    eax, eax
0x18003add1  jz      short loc_18003ADFB
0x18003add3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003adda  lea     rax, WPP_GLOBAL_Control
0x18003ade1  cmp     rcx, rax
0x18003ade4  jz      loc_18003AFDD
0x18003adea  test    byte ptr [rcx+1Ch], 10h
0x18003adee  jz      loc_18003AFDD
0x18003adf4  mov     edx, 33h ; '3'
0x18003adf9  jmp     short loc_18003AD90
0x18003adfb  mov     eax, dword ptr [rbp+Data]
0x18003adfe  lea     r9, [rdi+20h]
0x18003ae02  mov     [rdi+18h], eax
0x18003ae05  lea     rdx, attr; "ipsecData"
0x18003ae0c  mov     rcx, [rbp+hKey]; hKey
0x18003ae10  lea     rax, [rdi+28h]
0x18003ae14  mov     r8d, 3
0x18003ae1a  mov     [rsp+58h+phkResult], rax; __int64
0x18003ae1f  call    RegstoreQueryValue
0x18003ae24  mov     ebx, eax
0x18003ae26  test    eax, eax
0x18003ae28  jz      short loc_18003AE55
0x18003ae2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ae31  lea     rax, WPP_GLOBAL_Control
0x18003ae38  cmp     rcx, rax
0x18003ae3b  jz      loc_18003AFDD
0x18003ae41  test    byte ptr [rcx+1Ch], 10h
0x18003ae45  jz      loc_18003AFDD
0x18003ae4b  mov     edx, 34h ; '4'
0x18003ae50  jmp     loc_18003AD90
0x18003ae55  mov     rcx, [rbp+hKey]; hKey
0x18003ae59  lea     rax, [rbp+cbData]
0x18003ae5d  lea     r9, [rdi+30h]
0x18003ae61  mov     [rsp+58h+phkResult], rax; __int64
0x18003ae66  mov     r8d, esi
0x18003ae69  lea     rdx, aIpsecownersref; "ipsecOwnersReference"
0x18003ae70  call    RegstoreQueryValue
0x18003ae75  mov     rcx, [rbp+hKey]; hKey
0x18003ae79  lea     rax, [rbp+cbData]
0x18003ae7d  lea     r9, [rdi+40h]
0x18003ae81  mov     [rsp+58h+phkResult], rax; __int64
0x18003ae86  mov     r8d, esi
0x18003ae89  lea     rdx, aIpsecnegotiati_0; "ipsecNegotiationPolicyReference"
0x18003ae90  call    RegstoreQueryValue
0x18003ae95  mov     ebx, eax
0x18003ae97  test    eax, eax
0x18003ae99  jz      short loc_18003AEC6
0x18003ae9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aea2  lea     rax, WPP_GLOBAL_Control
0x18003aea9  cmp     rcx, rax
0x18003aeac  jz      loc_18003AFDD
0x18003aeb2  test    byte ptr [rcx+1Ch], 10h
0x18003aeb6  jz      loc_18003AFDD
0x18003aebc  mov     edx, 35h ; '5'
0x18003aec1  jmp     loc_18003AD90
0x18003aec6  mov     rcx, [rbp+hKey]; hKey
0x18003aeca  lea     rax, [rbp+cbData]
0x18003aece  lea     r9, [rdi+38h]
0x18003aed2  mov     [rsp+58h+phkResult], rax; __int64
0x18003aed7  mov     r8d, esi
0x18003aeda  lea     rdx, aIpsecfilterref; "ipsecFilterReference"
0x18003aee1  call    RegstoreQueryValue
0x18003aee6  mov     rcx, [rbp+hKey]; hKey
0x18003aeea  lea     r9, [rbp+Type]; lpType
0x18003aeee  mov     eax, 4
0x18003aef3  lea     rdx, aWhenchanged; "whenChanged"
0x18003aefa  mov     [rbp+Type], eax
0x18003aefd  xor     r8d, r8d; lpReserved
0x18003af00  mov     [rbp+cbData], eax
0x18003af03  lea     rax, [rbp+cbData]
0x18003af07  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18003af0c  lea     rax, [rbp+var_20]
0x18003af10  mov     [rsp+58h+phkResult], rax; lpData
0x18003af15  call    cs:__imp_RegQueryValueExW
0x18003af1b  mov     ebx, eax
0x18003af1d  test    eax, eax
0x18003af1f  jz      short loc_18003AF4C
0x18003af21  mov     rcx, cs:WPP_GLOBAL_Control
0x18003af28  lea     rax, WPP_GLOBAL_Control
0x18003af2f  cmp     rcx, rax
0x18003af32  jz      loc_18003AFDD
0x18003af38  test    byte ptr [rcx+1Ch], 10h
0x18003af3c  jz      loc_18003AFDD
0x18003af42  mov     edx, 36h ; '6'
0x18003af47  jmp     loc_18003AD90
0x18003af4c  mov     rcx, [rdi+38h]; unsigned __int16 *
0x18003af50  mov     eax, dword ptr [rbp+var_20]
0x18003af53  mov     [rdi+48h], eax
0x18003af56  test    rcx, rcx
0x18003af59  jz      short loc_18003AF94
0x18003af5b  cmp     [rcx], r13w
0x18003af5f  jz      short loc_18003AF94
0x18003af61  call    IpsecAllocStr
0x18003af66  mov     r14, rax
0x18003af69  test    rax, rax
0x18003af6c  jnz     short loc_18003AF94
0x18003af6e  lea     r9d, [rax+0Eh]
0x18003af72  mov     ebx, r9d
0x18003af75  mov     rcx, cs:WPP_GLOBAL_Control
0x18003af7c  lea     rax, WPP_GLOBAL_Control
0x18003af83  cmp     rcx, rax
0x18003af86  jz      short loc_18003AFDD
0x18003af88  test    byte ptr [rcx+1Ch], 10h
0x18003af8c  jz      short loc_18003AFDD
0x18003af8e  lea     edx, [r14+37h]
0x18003af92  jmp     short loc_18003AFCD
0x18003af94  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18003af98  call    IpsecAllocStr
0x18003af9d  mov     rcx, rax
0x18003afa0  test    rax, rax
0x18003afa3  jnz     loc_18003B033
0x18003afa9  lea     r9d, [rax+0Eh]
0x18003afad  mov     ebx, r9d
0x18003afb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003afb7  lea     rax, WPP_GLOBAL_Control
0x18003afbe  cmp     rcx, rax
0x18003afc1  jz      short loc_18003AFDD
0x18003afc3  test    byte ptr [rcx+1Ch], 10h
0x18003afc7  jz      short loc_18003AFDD
0x18003afc9  lea     edx, [r9+2Ah]
0x18003afcd  mov     rcx, [rcx+10h]
0x18003afd1  lea     r8, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids
0x18003afd8  call    WPP_SF_d
0x18003afdd  mov     rcx, rdi; lpMem
0x18003afe0  call    FreeIpsecNFAObject
0x18003afe5  test    r14, r14
0x18003afe8  jz      short loc_18003B02A
0x18003afea  mov     rcx, r14; lpMem
0x18003afed  call    IpsecFreeMem
0x18003aff2  jmp     short loc_18003B02A
0x18003aff4  mov     r9d, 0Dh
0x18003affa  mov     ebx, r9d
0x18003affd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b004  lea     rax, WPP_GLOBAL_Control
0x18003b00b  cmp     rcx, rax
0x18003b00e  jz      short loc_18003B02A
0x18003b010  test    byte ptr [rcx+1Ch], 10h
0x18003b014  jz      short loc_18003B02A
0x18003b016  lea     edx, [r9+20h]
0x18003b01a  mov     rcx, [rcx+10h]
0x18003b01e  lea     r8, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids
0x18003b025  call    WPP_SF_d
0x18003b02a  mov     rcx, r13
0x18003b02d  mov     r14, r13
0x18003b030  mov     rdi, r13
0x18003b033  mov     rax, [rbp+arg_20]
0x18003b037  mov     [r12], rdi
0x18003b03b  mov     [rax], r14
0x18003b03e  mov     rax, [rbp+arg_28]
0x18003b042  mov     [rax], rcx
0x18003b045  mov     rcx, [rbp+hKey]; hKey
0x18003b049  test    rcx, rcx
0x18003b04c  jz      short loc_18003B054
0x18003b04e  call    cs:__imp_RegCloseKey
0x18003b054  mov     eax, ebx
0x18003b056  add     rsp, 58h
0x18003b05a  pop     r15
  ... truncated ...
```
