# RtlpMuiRegCreateAndLoadRegistryInfo

- ea: `0x180071960`
- end: `0x180071d34`
- name: `RtlpMuiRegCreateAndLoadRegistryInfo`
- size: `980`
- prototype: ``
- caller_count: `6`
- callee_count: `20`
- tags: `registry_config, installer_update`

## callers

- `0x18000be70`
- `0x18000d3e0`
- `0x180071890`
- `0x180071d40`
- `0x1800da890`
- `0x1800ec4f0`

## callees

- `0x180007060`
- `0x18000e650`
- `0x180010770`
- `0x180010870`
- `0x180010b80`
- `0x180011d10`
- `0x18001228c`
- `0x18001861c`
- `0x18001b984`
- `0x180071960`
- `0x1800bc9e4`
- `0x1800dab10`
- `0x1800dad74`
- `0x1800dc6c0`
- `0x1801119d0`
- `0x1801210e0`
- `0x18012d320`
- `0x18015ecc0`
- `0x18015ed20`
- `0x180160a90`

## string_xrefs

- `0x180071b7f`: `Control Panel\Desktop\MuiCached\MachineLanguageConfiguration`

## pseudocode

```c
__int64 __fastcall RtlpMuiRegCreateAndLoadRegistryInfo(__int64 *a1)
{
  __int64 v2; // rbx
  __int64 Heap_0; // rax
  __int64 v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // rcx
  int Installed; // edi
  int v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  int v11; // eax
  __int64 RegistryInfo; // rax
  int LicInformation; // eax
  __int64 v14; // rax
  size_t v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int128 v20; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v21[4]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v22; // [rsp+50h] [rbp-10h]
  unsigned int v23; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v24; // [rsp+A8h] [rbp+48h] BYREF
  HANDLE v25; // [rsp+B0h] [rbp+50h] BYREF
  HANDLE Handle; // [rsp+B8h] [rbp+58h] BYREF

  v2 = 0;
  v24 = 0;
  if ( !a1 || *a1 )
  {
    Installed = -1073741811;
    goto LABEL_25;
  }
  v23 = 0;
  if ( (int)ZwGetMUIRegistryInfo(0, &v23, 0) >= 0 )
  {
    if ( !v23 )
      goto LABEL_41;
    Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, v23);
    v4 = Heap_0;
    if ( !Heap_0 )
      goto LABEL_41;
    if ( (int)ZwGetMUIRegistryInfo(0, &v23, Heap_0) >= 0 && (int)RtlpMuiRegDeserializeRegistryInfo(v4, v23, &v24) >= 0 )
    {
      v2 = v24;
      Installed = RtlpMuiRegAddNeutralToInstalled(v24);
      if ( Installed >= 0 )
      {
        if ( !*(_QWORD *)(v2 + 40) )
          goto LABEL_35;
        v25 = 0;
        v20 = 0;
        Handle = 0;
        v8 = GetGlobalizationUserModelType(v6, v5) - 1;
        if ( v8 )
        {
          v10 = v8 - 1;
          if ( v10 )
          {
            if ( v10 == 1 )
            {
              LODWORD(v24) = 0;
              v11 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, v9, (__int64)&v25, &v24);
              goto LABEL_28;
            }
LABEL_35:
            v24 = 0;
            if ( v2 )
            {
              RtlpMuiRegFreeRegistryInfo(v2, 8);
              if ( (int)RtlpLoadLanguageConfigList(8u, &v24, v2) >= 0 )
              {
                v14 = v24;
                if ( v24 )
                {
                  *(_DWORD *)v2 |= 8u;
                  *(_QWORD *)(v2 + 48) = v14;
                }
                RtlpMuiRegFreeRegistryInfo(v2, 32);
                if ( (int)RtlpSetProcUserMachineLangList(v2, 1) >= 0 )
                {
                  RtlpMuiRegFreeRegistryInfo(v2, 16);
                  RtlpSetProcUserMachineLangList(v2, 0);
                }
              }
            }
            goto LABEL_25;
          }
          v11 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000, &v25);
        }
        else
        {
          v11 = RtlOpenCurrentUser(0x2000000, &v25);
        }
LABEL_28:
        if ( v11 >= 0 )
        {
          *(_QWORD *)&v20 = 0;
          *((_QWORD *)&v20 + 1) = L"Control Panel\\Desktop\\MuiCached\\MachineLanguageConfiguration";
          v16 = 2 * wcslen(L"Control Panel\\Desktop\\MuiCached\\MachineLanguageConfiguration");
          v21[0] = 48;
          v21[3] = 64;
          Handle = 0;
          if ( v16 >= 0xFFFE )
            LOWORD(v16) = -4;
          LOWORD(v20) = v16;
          WORD1(v20) = v16 + 2;
          v21[1] = v25;
          v21[2] = &v20;
          v22 = 0;
          if ( (int)NtOpenKey(&Handle, 131097, v21) >= 0 )
          {
            v24 = 0;
            if ( v2 )
            {
              RtlpMuiRegFreeRegistryInfo(v2, 4);
              if ( (int)RtlpLoadLanguageConfigList(4u, &v24, v2) >= 0 )
              {
                v17 = v24;
                if ( v24 )
                {
                  *(_DWORD *)v2 |= 4u;
                  *(_QWORD *)(v2 + 40) = v17;
                }
              }
            }
            NtClose(Handle);
          }
          NtClose(v25);
        }
        goto LABEL_35;
      }
    }
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v4);
  }
  RegistryInfo = RtlpMuiRegCreateRegistryInfo();
  v2 = RegistryInfo;
  if ( !RegistryInfo )
  {
LABEL_41:
    Installed = -1073741801;
    goto LABEL_25;
  }
  v24 = 0;
  LicInformation = RtlpMuiRegLoadLicInformation(RegistryInfo);
  if ( LicInformation < 0 )
    DbgPrint("*** RtlpMuiRegLoadLicInformation failed with status %x", LicInformation);
  Installed = RtlpMuiRegLoadInstalled(v2);
  if ( Installed < 0 )
    goto LABEL_19;
  RtlpMuiRegFreeRegistryInfo(v2, 4);
  Installed = RtlpLoadLanguageConfigList(4u, &v24, v2);
  if ( Installed < 0 )
    goto LABEL_19;
  v18 = v24;
  if ( v24 )
  {
    *(_DWORD *)v2 |= 4u;
    *(_QWORD *)(v2 + 40) = v18;
    v24 = 0;
  }
  RtlpMuiRegFreeRegistryInfo(v2, 8);
  Installed = RtlpLoadLanguageConfigList(8u, &v24, v2);
  if ( Installed < 0 )
    goto LABEL_19;
  v19 = v24;
  if ( v24 )
  {
    *(_DWORD *)v2 |= 8u;
    *(_QWORD *)(v2 + 48) = v19;
  }
  RtlpMuiRegFreeRegistryInfo(v2, 32);
  Installed = RtlpSetProcUserMachineLangList(v2, 1);
  if ( Installed < 0
    || (RtlpMuiRegFreeRegistryInfo(v2, 16), Installed = RtlpSetProcUserMachineLangList(v2, 0), Installed < 0) )
  {
LABEL_19:
    RtlpMuiRegFreeRegistryInfo(v2, 4095);
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v2);
    v2 = 0;
  }
  else
  {
    Installed = 0;
    *(_DWORD *)(v2 + 12) = MEMORY[0x7FFE03A4];
  }
LABEL_25:
  *a1 = v2;
  return (unsigned int)Installed;
}

```

## disassembly

```asm
0x180071960  push    rbp
0x180071962  push    rbx
0x180071963  push    rsi
0x180071964  push    rdi
0x180071965  push    r12
0x180071967  push    r14
0x180071969  push    r15
0x18007196b  mov     rbp, rsp
0x18007196e  sub     rsp, 60h
0x180071972  xor     r15d, r15d
0x180071975  mov     r14, rcx
0x180071978  mov     ebx, r15d
0x18007197b  mov     [rbp+arg_8], rbx
0x18007197f  test    rcx, rcx
0x180071982  jz      loc_180071B62
0x180071988  cmp     [rcx], r15
0x18007198b  jnz     loc_180071B62
0x180071991  xor     r8d, r8d
0x180071994  mov     [rbp+arg_0], r15d
0x180071998  lea     rdx, [rbp+arg_0]
0x18007199c  xor     ecx, ecx
0x18007199e  call    ZwGetMUIRegistryInfo
0x1800719a3  lea     r12d, [r15+8]
0x1800719a7  test    eax, eax
0x1800719a9  js      loc_180071A80
0x1800719af  mov     eax, [rbp+arg_0]
0x1800719b2  test    eax, eax
0x1800719b4  jz      loc_180071C65
0x1800719ba  mov     rcx, gs:60h
0x1800719c3  mov     r8d, eax
0x1800719c6  mov     edx, r12d
0x1800719c9  mov     rcx, [rcx+30h]
0x1800719cd  call    RtlAllocateHeap_0
0x1800719d2  mov     rsi, rax
0x1800719d5  test    rax, rax
0x1800719d8  jz      loc_180071C65
0x1800719de  mov     r8, rax
0x1800719e1  lea     rdx, [rbp+arg_0]
0x1800719e5  xor     ecx, ecx
0x1800719e7  call    ZwGetMUIRegistryInfo
0x1800719ec  test    eax, eax
0x1800719ee  js      short loc_180071A69
0x1800719f0  mov     edx, [rbp+arg_0]
0x1800719f3  lea     r8, [rbp+arg_8]
0x1800719f7  mov     rcx, rsi
0x1800719fa  call    _RtlpMuiRegDeserializeRegistryInfo
0x1800719ff  test    eax, eax
0x180071a01  js      short loc_180071A69
0x180071a03  mov     rbx, [rbp+arg_8]
0x180071a07  mov     rcx, rbx
0x180071a0a  call    _RtlpMuiRegAddNeutralToInstalled
0x180071a0f  mov     edi, eax
0x180071a11  test    eax, eax
0x180071a13  js      short loc_180071A69
0x180071a15  cmp     [rbx+28h], r15
0x180071a19  jz      loc_180071C0E
0x180071a1f  xorps   xmm0, xmm0
0x180071a22  mov     [rbp+arg_10], r15
0x180071a26  movups  [rbp+var_40], xmm0
0x180071a2a  mov     [rbp+Handle], r15
0x180071a2e  call    GetGlobalizationUserModelType
0x180071a33  sub     eax, 1
0x180071a36  jz      loc_180071C52
0x180071a3c  sub     eax, 1
0x180071a3f  jz      loc_180071B69
0x180071a45  cmp     eax, 1
0x180071a48  jnz     loc_180071C0E
0x180071a4e  lea     r9, [rbp+arg_8]
0x180071a52  mov     dword ptr [rbp+arg_8], r15d
0x180071a56  lea     r8, [rbp+arg_10]
0x180071a5a  mov     ecx, 2000000h
0x180071a5f  call    OpenGlobalizationUserSettingsKey_ForMua
0x180071a64  jmp     loc_180071B77
0x180071a69  mov     rcx, gs:60h
0x180071a72  mov     r8, rsi
0x180071a75  xor     edx, edx
0x180071a77  mov     rcx, [rcx+30h]
0x180071a7b  call    RtlFreeHeap_0
0x180071a80  call    RtlpMuiRegCreateRegistryInfo
0x180071a85  mov     rbx, rax
0x180071a88  test    rax, rax
0x180071a8b  jz      loc_180071C65
0x180071a91  mov     rcx, rax
0x180071a94  mov     [rbp+arg_8], r15
0x180071a98  call    RtlpMuiRegLoadLicInformation
0x180071a9d  test    eax, eax
0x180071a9f  jns     short loc_180071AAF
0x180071aa1  mov     edx, eax
0x180071aa3  lea     rcx, aRtlpmuiregload_0; "*** RtlpMuiRegLoadLicInformation failed"...
0x180071aaa  call    DbgPrint
0x180071aaf  mov     rcx, rbx
0x180071ab2  call    _RtlpMuiRegLoadInstalled
0x180071ab7  mov     edi, eax
0x180071ab9  test    eax, eax
0x180071abb  jns     loc_180071C6F
0x180071ac1  mov     edx, 0FFFh
0x180071ac6  mov     rcx, rbx
0x180071ac9  call    RtlpMuiRegFreeRegistryInfo
0x180071ace  mov     rcx, gs:60h
0x180071ad7  mov     r8, rbx
0x180071ada  xor     edx, edx
0x180071adc  mov     rcx, [rcx+30h]
0x180071ae0  call    RtlFreeHeap_0
0x180071ae5  mov     rbx, r15
0x180071ae8  jmp     short loc_180071B4D
0x180071aea  mov     edx, r12d
0x180071aed  mov     rcx, rbx
0x180071af0  call    RtlpMuiRegFreeRegistryInfo
0x180071af5  mov     r8, rbx
0x180071af8  lea     rdx, [rbp+arg_8]
0x180071afc  mov     ecx, r12d
0x180071aff  call    RtlpLoadLanguageConfigList
0x180071b04  test    eax, eax
0x180071b06  js      short loc_180071B4D
0x180071b08  mov     rax, [rbp+arg_8]
0x180071b0c  test    rax, rax
0x180071b0f  jz      short loc_180071B18
0x180071b11  or      [rbx], r12d
0x180071b14  mov     [rbx+30h], rax
0x180071b18  mov     edx, 20h ; ' '
0x180071b1d  mov     rcx, rbx
0x180071b20  call    RtlpMuiRegFreeRegistryInfo
0x180071b25  mov     edx, 1
0x180071b2a  mov     rcx, rbx
0x180071b2d  call    RtlpSetProcUserMachineLangList
0x180071b32  test    eax, eax
0x180071b34  js      short loc_180071B4D
0x180071b36  mov     edx, 10h
0x180071b3b  mov     rcx, rbx
0x180071b3e  call    RtlpMuiRegFreeRegistryInfo
0x180071b43  xor     edx, edx
0x180071b45  mov     rcx, rbx
0x180071b48  call    RtlpSetProcUserMachineLangList
0x180071b4d  mov     [r14], rbx
0x180071b50  mov     eax, edi
0x180071b52  add     rsp, 60h
0x180071b56  pop     r15
0x180071b58  pop     r14
0x180071b5a  pop     r12
0x180071b5c  pop     rdi
0x180071b5d  pop     rsi
0x180071b5e  pop     rbx
0x180071b5f  pop     rbp
0x180071b60  retn
0x180071b62  mov     edi, 0C000000Dh
0x180071b67  jmp     short loc_180071B4D
0x180071b69  lea     rdx, [rbp+arg_10]
0x180071b6d  mov     ecx, 2000000h
0x180071b72  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x180071b77  test    eax, eax
0x180071b79  js      loc_180071C0E
0x180071b7f  lea     rcx, aControlPanelDe_1; "Control Panel\\Desktop\\MuiCached\\Mach"...
0x180071b86  mov     qword ptr [rbp+var_40], r15
0x180071b8a  mov     qword ptr [rbp+var_40+8], rcx
0x180071b8e  call    wcslen
0x180071b93  add     rax, rax
0x180071b96  mov     [rbp+var_30], 30h ; '0'
0x180071b9e  cmp     rax, 0FFFEh
0x180071ba4  mov     [rbp+var_18], 40h ; '@'
0x180071bac  mov     ecx, 0FFFCh
0x180071bb1  mov     [rbp+Handle], r15
0x180071bb5  cmovnb  rax, rcx
0x180071bb9  lea     r8, [rbp+var_30]
0x180071bbd  mov     word ptr [rbp+var_40], ax
0x180071bc1  lea     rcx, [rbp+Handle]
0x180071bc5  add     ax, 2
0x180071bc9  xorps   xmm0, xmm0
0x180071bcc  mov     word ptr [rbp+var_40+2], ax
0x180071bd0  mov     edx, 20019h
0x180071bd5  mov     rax, [rbp+arg_10]
0x180071bd9  mov     [rbp+var_28], rax
0x180071bdd  lea     rax, [rbp+var_40]
0x180071be1  mov     [rbp+var_20], rax
0x180071be5  movdqu  [rbp+var_10], xmm0
0x180071bea  call    NtOpenKey
0x180071bef  test    eax, eax
0x180071bf1  js      short loc_180071C05
0x180071bf3  mov     [rbp+arg_8], r15
0x180071bf7  test    rbx, rbx
0x180071bfa  jnz     short loc_180071C20
0x180071bfc  mov     rcx, [rbp+Handle]; Handle
0x180071c00  call    NtClose
0x180071c05  mov     rcx, [rbp+arg_10]; Handle
0x180071c09  call    NtClose
0x180071c0e  mov     [rbp+arg_8], r15
0x180071c12  test    rbx, rbx
0x180071c15  jz      loc_180071B4D
0x180071c1b  jmp     loc_180071AEA
0x180071c20  mov     esi, 4
0x180071c25  mov     rcx, rbx
0x180071c28  mov     edx, esi
0x180071c2a  call    RtlpMuiRegFreeRegistryInfo
0x180071c2f  mov     r8, rbx
0x180071c32  lea     rdx, [rbp+arg_8]
0x180071c36  mov     ecx, esi
0x180071c38  call    RtlpLoadLanguageConfigList
0x180071c3d  test    eax, eax
0x180071c3f  js      short loc_180071BFC
0x180071c41  mov     rax, [rbp+arg_8]
0x180071c45  test    rax, rax
0x180071c48  jz      short loc_180071BFC
0x180071c4a  or      [rbx], esi
0x180071c4c  mov     [rbx+28h], rax
0x180071c50  jmp     short loc_180071BFC
0x180071c52  lea     rdx, [rbp+arg_10]
0x180071c56  mov     ecx, 2000000h
0x180071c5b  call    RtlOpenCurrentUser
0x180071c60  jmp     loc_180071B77
0x180071c65  mov     edi, 0C0000017h
0x180071c6a  jmp     loc_180071B4D
0x180071c6f  mov     esi, 4
0x180071c74  mov     rcx, rbx
0x180071c77  mov     edx, esi
0x180071c79  call    RtlpMuiRegFreeRegistryInfo
0x180071c7e  mov     r8, rbx
0x180071c81  lea     rdx, [rbp+arg_8]
0x180071c85  mov     ecx, esi
0x180071c87  call    RtlpLoadLanguageConfigList
0x180071c8c  mov     edi, eax
0x180071c8e  test    eax, eax
0x180071c90  js      loc_180071AC1
0x180071c96  mov     rax, [rbp+arg_8]
0x180071c9a  test    rax, rax
0x180071c9d  jz      short loc_180071CA9
0x180071c9f  or      [rbx], esi
0x180071ca1  mov     [rbx+28h], rax
0x180071ca5  mov     [rbp+arg_8], r15
0x180071ca9  mov     edx, r12d
0x180071cac  mov     rcx, rbx
0x180071caf  call    RtlpMuiRegFreeRegistryInfo
0x180071cb4  mov     r8, rbx
0x180071cb7  lea     rdx, [rbp+arg_8]
0x180071cbb  mov     ecx, r12d
0x180071cbe  call    RtlpLoadLanguageConfigList
0x180071cc3  mov     edi, eax
0x180071cc5  test    eax, eax
0x180071cc7  js      loc_180071AC1
0x180071ccd  mov     rax, [rbp+arg_8]
0x180071cd1  test    rax, rax
0x180071cd4  jz      short loc_180071CDD
0x180071cd6  or      [rbx], r12d
0x180071cd9  mov     [rbx+30h], rax
0x180071cdd  mov     edx, 20h ; ' '
0x180071ce2  mov     rcx, rbx
0x180071ce5  call    RtlpMuiRegFreeRegistryInfo
0x180071cea  mov     edx, 1
0x180071cef  mov     rcx, rbx
0x180071cf2  call    RtlpSetProcUserMachineLangList
0x180071cf7  mov     edi, eax
0x180071cf9  test    eax, eax
0x180071cfb  js      loc_180071AC1
0x180071d01  mov     edx, 10h
0x180071d06  mov     rcx, rbx
0x180071d09  call    RtlpMuiRegFreeRegistryInfo
0x180071d0e  xor     edx, edx
0x180071d10  mov     rcx, rbx
0x180071d13  call    RtlpSetProcUserMachineLangList
0x180071d18  mov     edi, eax
0x180071d1a  test    eax, eax
0x180071d1c  js      loc_180071AC1
0x180071d22  mov     eax, ds:7FFE03A4h
0x180071d29  mov     edi, r15d
0x180071d2c  mov     [rbx+0Ch], eax
0x180071d2f  jmp     loc_180071B4D
```
