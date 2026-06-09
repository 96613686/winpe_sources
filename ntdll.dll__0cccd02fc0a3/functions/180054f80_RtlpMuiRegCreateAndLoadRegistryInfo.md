# RtlpMuiRegCreateAndLoadRegistryInfo

- ea: `0x180054f80`
- end: `0x180055354`
- name: `RtlpMuiRegCreateAndLoadRegistryInfo`
- size: `980`
- prototype: ``
- caller_count: `6`
- callee_count: `20`
- tags: `registry_config, installer_update`

## callers

- `0x18000be70`
- `0x18000d3e0`
- `0x180054eb0`
- `0x180055360`
- `0x1800d9e10`
- `0x1800eba10`

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
- `0x180054f80`
- `0x1800b8c44`
- `0x1800da090`
- `0x1800da2f4`
- `0x1800dbc40`
- `0x180110670`
- `0x1801205f0`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e510`
- `0x180160280`

## string_xrefs

- `0x18005519f`: `Control Panel\Desktop\MuiCached\MachineLanguageConfiguration`

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
0x180054f80  push    rbp
0x180054f82  push    rbx
0x180054f83  push    rsi
0x180054f84  push    rdi
0x180054f85  push    r12
0x180054f87  push    r14
0x180054f89  push    r15
0x180054f8b  mov     rbp, rsp
0x180054f8e  sub     rsp, 60h
0x180054f92  xor     r15d, r15d
0x180054f95  mov     r14, rcx
0x180054f98  mov     ebx, r15d
0x180054f9b  mov     [rbp+arg_8], rbx
0x180054f9f  test    rcx, rcx
0x180054fa2  jz      loc_180055182
0x180054fa8  cmp     [rcx], r15
0x180054fab  jnz     loc_180055182
0x180054fb1  xor     r8d, r8d
0x180054fb4  mov     [rbp+arg_0], r15d
0x180054fb8  lea     rdx, [rbp+arg_0]
0x180054fbc  xor     ecx, ecx
0x180054fbe  call    ZwGetMUIRegistryInfo
0x180054fc3  lea     r12d, [r15+8]
0x180054fc7  test    eax, eax
0x180054fc9  js      loc_1800550A0
0x180054fcf  mov     eax, [rbp+arg_0]
0x180054fd2  test    eax, eax
0x180054fd4  jz      loc_180055285
0x180054fda  mov     rcx, gs:60h
0x180054fe3  mov     r8d, eax
0x180054fe6  mov     edx, r12d
0x180054fe9  mov     rcx, [rcx+30h]
0x180054fed  call    RtlAllocateHeap_0
0x180054ff2  mov     rsi, rax
0x180054ff5  test    rax, rax
0x180054ff8  jz      loc_180055285
0x180054ffe  mov     r8, rax
0x180055001  lea     rdx, [rbp+arg_0]
0x180055005  xor     ecx, ecx
0x180055007  call    ZwGetMUIRegistryInfo
0x18005500c  test    eax, eax
0x18005500e  js      short loc_180055089
0x180055010  mov     edx, [rbp+arg_0]
0x180055013  lea     r8, [rbp+arg_8]
0x180055017  mov     rcx, rsi
0x18005501a  call    _RtlpMuiRegDeserializeRegistryInfo
0x18005501f  test    eax, eax
0x180055021  js      short loc_180055089
0x180055023  mov     rbx, [rbp+arg_8]
0x180055027  mov     rcx, rbx
0x18005502a  call    _RtlpMuiRegAddNeutralToInstalled
0x18005502f  mov     edi, eax
0x180055031  test    eax, eax
0x180055033  js      short loc_180055089
0x180055035  cmp     [rbx+28h], r15
0x180055039  jz      loc_18005522E
0x18005503f  xorps   xmm0, xmm0
0x180055042  mov     [rbp+arg_10], r15
0x180055046  movups  [rbp+var_40], xmm0
0x18005504a  mov     [rbp+Handle], r15
0x18005504e  call    GetGlobalizationUserModelType
0x180055053  sub     eax, 1
0x180055056  jz      loc_180055272
0x18005505c  sub     eax, 1
0x18005505f  jz      loc_180055189
0x180055065  cmp     eax, 1
0x180055068  jnz     loc_18005522E
0x18005506e  lea     r9, [rbp+arg_8]
0x180055072  mov     dword ptr [rbp+arg_8], r15d
0x180055076  lea     r8, [rbp+arg_10]
0x18005507a  mov     ecx, 2000000h
0x18005507f  call    OpenGlobalizationUserSettingsKey_ForMua
0x180055084  jmp     loc_180055197
0x180055089  mov     rcx, gs:60h
0x180055092  mov     r8, rsi
0x180055095  xor     edx, edx
0x180055097  mov     rcx, [rcx+30h]
0x18005509b  call    RtlFreeHeap_0
0x1800550a0  call    RtlpMuiRegCreateRegistryInfo
0x1800550a5  mov     rbx, rax
0x1800550a8  test    rax, rax
0x1800550ab  jz      loc_180055285
0x1800550b1  mov     rcx, rax
0x1800550b4  mov     [rbp+arg_8], r15
0x1800550b8  call    RtlpMuiRegLoadLicInformation
0x1800550bd  test    eax, eax
0x1800550bf  jns     short loc_1800550CF
0x1800550c1  mov     edx, eax
0x1800550c3  lea     rcx, aRtlpmuiregload_0; "*** RtlpMuiRegLoadLicInformation failed"...
0x1800550ca  call    DbgPrint
0x1800550cf  mov     rcx, rbx
0x1800550d2  call    _RtlpMuiRegLoadInstalled
0x1800550d7  mov     edi, eax
0x1800550d9  test    eax, eax
0x1800550db  jns     loc_18005528F
0x1800550e1  mov     edx, 0FFFh
0x1800550e6  mov     rcx, rbx
0x1800550e9  call    RtlpMuiRegFreeRegistryInfo
0x1800550ee  mov     rcx, gs:60h
0x1800550f7  mov     r8, rbx
0x1800550fa  xor     edx, edx
0x1800550fc  mov     rcx, [rcx+30h]
0x180055100  call    RtlFreeHeap_0
0x180055105  mov     rbx, r15
0x180055108  jmp     short loc_18005516D
0x18005510a  mov     edx, r12d
0x18005510d  mov     rcx, rbx
0x180055110  call    RtlpMuiRegFreeRegistryInfo
0x180055115  mov     r8, rbx
0x180055118  lea     rdx, [rbp+arg_8]
0x18005511c  mov     ecx, r12d
0x18005511f  call    RtlpLoadLanguageConfigList
0x180055124  test    eax, eax
0x180055126  js      short loc_18005516D
0x180055128  mov     rax, [rbp+arg_8]
0x18005512c  test    rax, rax
0x18005512f  jz      short loc_180055138
0x180055131  or      [rbx], r12d
0x180055134  mov     [rbx+30h], rax
0x180055138  mov     edx, 20h ; ' '
0x18005513d  mov     rcx, rbx
0x180055140  call    RtlpMuiRegFreeRegistryInfo
0x180055145  mov     edx, 1
0x18005514a  mov     rcx, rbx
0x18005514d  call    RtlpSetProcUserMachineLangList
0x180055152  test    eax, eax
0x180055154  js      short loc_18005516D
0x180055156  mov     edx, 10h
0x18005515b  mov     rcx, rbx
0x18005515e  call    RtlpMuiRegFreeRegistryInfo
0x180055163  xor     edx, edx
0x180055165  mov     rcx, rbx
0x180055168  call    RtlpSetProcUserMachineLangList
0x18005516d  mov     [r14], rbx
0x180055170  mov     eax, edi
0x180055172  add     rsp, 60h
0x180055176  pop     r15
0x180055178  pop     r14
0x18005517a  pop     r12
0x18005517c  pop     rdi
0x18005517d  pop     rsi
0x18005517e  pop     rbx
0x18005517f  pop     rbp
0x180055180  retn
0x180055182  mov     edi, 0C000000Dh
0x180055187  jmp     short loc_18005516D
0x180055189  lea     rdx, [rbp+arg_10]
0x18005518d  mov     ecx, 2000000h
0x180055192  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x180055197  test    eax, eax
0x180055199  js      loc_18005522E
0x18005519f  lea     rcx, aControlPanelDe_1; "Control Panel\\Desktop\\MuiCached\\Mach"...
0x1800551a6  mov     qword ptr [rbp+var_40], r15
0x1800551aa  mov     qword ptr [rbp+var_40+8], rcx
0x1800551ae  call    wcslen
0x1800551b3  add     rax, rax
0x1800551b6  mov     [rbp+var_30], 30h ; '0'
0x1800551be  cmp     rax, 0FFFEh
0x1800551c4  mov     [rbp+var_18], 40h ; '@'
0x1800551cc  mov     ecx, 0FFFCh
0x1800551d1  mov     [rbp+Handle], r15
0x1800551d5  cmovnb  rax, rcx
0x1800551d9  lea     r8, [rbp+var_30]
0x1800551dd  mov     word ptr [rbp+var_40], ax
0x1800551e1  lea     rcx, [rbp+Handle]
0x1800551e5  add     ax, 2
0x1800551e9  xorps   xmm0, xmm0
0x1800551ec  mov     word ptr [rbp+var_40+2], ax
0x1800551f0  mov     edx, 20019h
0x1800551f5  mov     rax, [rbp+arg_10]
0x1800551f9  mov     [rbp+var_28], rax
0x1800551fd  lea     rax, [rbp+var_40]
0x180055201  mov     [rbp+var_20], rax
0x180055205  movdqu  [rbp+var_10], xmm0
0x18005520a  call    NtOpenKey
0x18005520f  test    eax, eax
0x180055211  js      short loc_180055225
0x180055213  mov     [rbp+arg_8], r15
0x180055217  test    rbx, rbx
0x18005521a  jnz     short loc_180055240
0x18005521c  mov     rcx, [rbp+Handle]; Handle
0x180055220  call    NtClose
0x180055225  mov     rcx, [rbp+arg_10]; Handle
0x180055229  call    NtClose
0x18005522e  mov     [rbp+arg_8], r15
0x180055232  test    rbx, rbx
0x180055235  jz      loc_18005516D
0x18005523b  jmp     loc_18005510A
0x180055240  mov     esi, 4
0x180055245  mov     rcx, rbx
0x180055248  mov     edx, esi
0x18005524a  call    RtlpMuiRegFreeRegistryInfo
0x18005524f  mov     r8, rbx
0x180055252  lea     rdx, [rbp+arg_8]
0x180055256  mov     ecx, esi
0x180055258  call    RtlpLoadLanguageConfigList
0x18005525d  test    eax, eax
0x18005525f  js      short loc_18005521C
0x180055261  mov     rax, [rbp+arg_8]
0x180055265  test    rax, rax
0x180055268  jz      short loc_18005521C
0x18005526a  or      [rbx], esi
0x18005526c  mov     [rbx+28h], rax
0x180055270  jmp     short loc_18005521C
0x180055272  lea     rdx, [rbp+arg_10]
0x180055276  mov     ecx, 2000000h
0x18005527b  call    RtlOpenCurrentUser
0x180055280  jmp     loc_180055197
0x180055285  mov     edi, 0C0000017h
0x18005528a  jmp     loc_18005516D
0x18005528f  mov     esi, 4
0x180055294  mov     rcx, rbx
0x180055297  mov     edx, esi
0x180055299  call    RtlpMuiRegFreeRegistryInfo
0x18005529e  mov     r8, rbx
0x1800552a1  lea     rdx, [rbp+arg_8]
0x1800552a5  mov     ecx, esi
0x1800552a7  call    RtlpLoadLanguageConfigList
0x1800552ac  mov     edi, eax
0x1800552ae  test    eax, eax
0x1800552b0  js      loc_1800550E1
0x1800552b6  mov     rax, [rbp+arg_8]
0x1800552ba  test    rax, rax
0x1800552bd  jz      short loc_1800552C9
0x1800552bf  or      [rbx], esi
0x1800552c1  mov     [rbx+28h], rax
0x1800552c5  mov     [rbp+arg_8], r15
0x1800552c9  mov     edx, r12d
0x1800552cc  mov     rcx, rbx
0x1800552cf  call    RtlpMuiRegFreeRegistryInfo
0x1800552d4  mov     r8, rbx
0x1800552d7  lea     rdx, [rbp+arg_8]
0x1800552db  mov     ecx, r12d
0x1800552de  call    RtlpLoadLanguageConfigList
0x1800552e3  mov     edi, eax
0x1800552e5  test    eax, eax
0x1800552e7  js      loc_1800550E1
0x1800552ed  mov     rax, [rbp+arg_8]
0x1800552f1  test    rax, rax
0x1800552f4  jz      short loc_1800552FD
0x1800552f6  or      [rbx], r12d
0x1800552f9  mov     [rbx+30h], rax
0x1800552fd  mov     edx, 20h ; ' '
0x180055302  mov     rcx, rbx
0x180055305  call    RtlpMuiRegFreeRegistryInfo
0x18005530a  mov     edx, 1
0x18005530f  mov     rcx, rbx
0x180055312  call    RtlpSetProcUserMachineLangList
0x180055317  mov     edi, eax
0x180055319  test    eax, eax
0x18005531b  js      loc_1800550E1
0x180055321  mov     edx, 10h
0x180055326  mov     rcx, rbx
0x180055329  call    RtlpMuiRegFreeRegistryInfo
0x18005532e  xor     edx, edx
0x180055330  mov     rcx, rbx
0x180055333  call    RtlpSetProcUserMachineLangList
0x180055338  mov     edi, eax
0x18005533a  test    eax, eax
0x18005533c  js      loc_1800550E1
0x180055342  mov     eax, ds:7FFE03A4h
0x180055349  mov     edi, r15d
0x18005534c  mov     [rbx+0Ch], eax
0x18005534f  jmp     loc_18005516D
```
