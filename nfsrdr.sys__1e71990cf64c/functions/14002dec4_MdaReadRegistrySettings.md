# MdaReadRegistrySettings

- ea: `0x14002dec4`
- end: `0x14002e2cf`
- name: `MdaReadRegistrySettings`
- size: `1035`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140022c5c`
- `0x14002d428`

## callees

- `0x1400159cc`
- `0x1400159fc`
- `0x14002dec4`
- `0x14002e2d8`
- `0x140038550`

## string_xrefs

- `0x14002df30`: `SOFTWARE\Microsoft\ClientForNFS\CurrentVersion\Users\Default\Mount`
- `0x14002e074`: `MountType`
- `0x14002e0f3`: `SoftMountTimeout`
- `0x14002e13c`: `Protocols`
- `0x14002e23e`: `CompatibilityFlags`

## pseudocode

```c
__int64 __fastcall MdaReadRegistrySettings(__int64 a1)
{
  __int64 v2; // r9
  __int64 v3; // r9
  unsigned int v4; // ecx
  unsigned int v5; // eax
  unsigned int v6; // edx
  unsigned int v7; // eax
  int Registry; // eax
  int v9; // ecx
  int v10; // eax
  int v11; // eax
  __int64 v13; // [rsp+60h] [rbp+30h] BYREF

  LODWORD(v13) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids);
  *(_DWORD *)(a1 + 1376) = 800;
  *(_DWORD *)(a1 + 1380) = 936;
  *(_DWORD *)(a1 + 1384) = 1120;
  *(_DWORD *)(a1 + 1388) = 5;
  *(_BYTE *)(a1 + 1392) = 1;
  LODWORD(v13) = 0;
  if ( (int)NfsReadRegistry(
              &stru_140041080,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Mount",
              (__int64)&v13,
              4) >= 0 )
  {
    v2 = (unsigned __int16)v13;
    *(_DWORD *)(a1 + 1388) = (unsigned __int16)v13;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids, v2);
  }
  LODWORD(v13) = 0;
  if ( (int)NfsReadRegistry(
              &stru_140041080,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Mount",
              (__int64)&v13,
              4) >= 0 )
  {
    v3 = (unsigned __int16)(100 * v13);
    *(_DWORD *)(a1 + 1376) = v3;
    v4 = 17 * (int)v3 / 0x64u + v3;
    if ( v4 >= 0xEA60 )
      v4 = 60000;
    *(_DWORD *)(a1 + 1380) = v4;
    v5 = 40 * (int)v3 / 0x64u + v3;
    if ( v5 >= 0xEA60 )
      v5 = 60000;
    *(_DWORD *)(a1 + 1384) = v5;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids, v3);
  }
  LODWORD(v13) = 0;
  if ( (int)NfsReadRegistry(
              &stru_140041080,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Mount",
              (__int64)&v13,
              4) >= 0 )
  {
    v6 = (unsigned __int8)v13;
    *(_BYTE *)(a1 + 1392) = v13;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids, v6);
  }
  if ( *(_DWORD *)(a1 + 1388) == 5 )
    *(_DWORD *)(a1 + 1388) = 4;
  LODWORD(v13) = 0;
  if ( (int)NfsReadRegistry(
              &stru_140041080,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
              (__int64)&v13,
              4) < 0 )
  {
    *(_DWORD *)(a1 + 2356) = 10000;
  }
  else
  {
    v7 = v13;
    *(_DWORD *)(a1 + 2356) = v13;
    if ( v7 > 0xEA60 )
      *(_DWORD *)(a1 + 2356) = 60000;
  }
  LODWORD(v13) = 0;
  *(_DWORD *)(a1 + 1416) = 0;
  if ( (int)NfsReadRegistry(
              &stru_140041080,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
              (__int64)&v13,
              4) < 0 )
  {
    *(_BYTE *)(a1 + 1416) |= 0x55u;
    *(_BYTE *)(a1 + 1417) |= 0x45u;
    *(_BYTE *)(a1 + 1418) |= 0x55u;
    *(_BYTE *)(a1 + 1419) |= 1u;
  }
  else
  {
    NfsProtocolFlagsToBitfield((unsigned int)v13, a1 + 1416);
  }
  LODWORD(v13) = 0;
  if ( (int)NfsReadRegistry(
              &stru_140041080,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
              (__int64)&v13,
              4) >= 0 )
    *(_DWORD *)(a1 + 2332) = v13;
  LODWORD(v13) = 0;
  if ( (int)NfsReadRegistry(
              &stru_140041080,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
              (__int64)&v13,
              4) >= 0 )
    *(_DWORD *)(a1 + 2336) = v13;
  *(_DWORD *)(a1 + 1424) = 0;
  LODWORD(v13) = 0;
  Registry = NfsReadRegistry(
               &stru_140041080,
               L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
               (__int64)&v13,
               4);
  v9 = *(_DWORD *)(a1 + 1424);
  if ( Registry < 0 )
    v10 = v9 | 3;
  else
    v10 = v9 & 0xFFFFFFFC | v13 & 3;
  *(_DWORD *)(a1 + 1424) = v10;
  *(_DWORD *)(a1 + 1420) = 0;
  LODWORD(v13) = 0;
  if ( (int)NfsReadRegistry(
              &stru_140041080,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
              (__int64)&v13,
              4) < 0 )
    v11 = *(_DWORD *)(a1 + 1420) & 0xFFFFFFFE;
  else
    v11 = *(_DWORD *)(a1 + 1420) & 0xFFFFFFFE | v13 & 1;
  *(_DWORD *)(a1 + 1420) = v11;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14002dec4  mov     [rsp-28h+arg_8], rbx
0x14002dec9  mov     [rsp-28h+arg_10], rsi
0x14002dece  push    rbp
0x14002decf  push    rdi
0x14002ded0  push    r12
0x14002ded2  push    r13
0x14002ded4  push    r15
0x14002ded6  mov     rbp, rsp
0x14002ded9  sub     rsp, 30h
0x14002dedd  mov     rbx, rcx
0x14002dee0  mov     dword ptr [rbp+arg_0], 0
0x14002dee7  mov     rcx, cs:WPP_GLOBAL_Control
0x14002deee  lea     rdi, WPP_GLOBAL_Control
0x14002def5  lea     r13, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002defc  cmp     rcx, rdi
0x14002deff  jz      short loc_14002DF19
0x14002df01  mov     eax, [rcx+2Ch]
0x14002df04  test    al, 8
0x14002df06  jz      short loc_14002DF19
0x14002df08  mov     rcx, [rcx+18h]
0x14002df0c  mov     edx, 1Ch
0x14002df11  mov     r8, r13
0x14002df14  call    WPP_SF_
0x14002df19  mov     esi, 4
0x14002df1e  mov     dword ptr [rbx+560h], 320h
0x14002df28  lea     rax, [rbp+arg_0]
0x14002df2c  mov     [rsp+30h+var_8], esi; int
0x14002df30  lea     r12, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x14002df37  mov     [rsp+30h+var_10], rax; __int64
0x14002df3c  lea     r15, stru_140041080
0x14002df43  mov     dword ptr [rbx+564h], 3A8h
0x14002df4d  mov     r9d, esi
0x14002df50  mov     dword ptr [rbx+568h], 460h
0x14002df5a  mov     rdx, r12; PCWSTR
0x14002df5d  mov     dword ptr [rbx+56Ch], 5
0x14002df67  mov     rcx, r15; SourceString
0x14002df6a  mov     byte ptr [rbx+570h], 1
0x14002df71  lea     r8, aRetransmission; "Retransmissions"
0x14002df78  mov     dword ptr [rbp+arg_0], 0
0x14002df7f  call    NfsReadRegistry
0x14002df84  test    eax, eax
0x14002df86  js      short loc_14002DFB7
0x14002df88  movzx   r9d, word ptr [rbp+arg_0]
0x14002df8d  mov     [rbx+56Ch], r9d
0x14002df94  mov     rcx, cs:WPP_GLOBAL_Control
0x14002df9b  cmp     rcx, rdi
0x14002df9e  jz      short loc_14002DFB7
0x14002dfa0  mov     eax, [rcx+2Ch]
0x14002dfa3  test    sil, al
0x14002dfa6  jz      short loc_14002DFB7
0x14002dfa8  mov     rcx, [rcx+18h]
0x14002dfac  lea     edx, [rsi+19h]
0x14002dfaf  mov     r8, r13
0x14002dfb2  call    WPP_SF_d
0x14002dfb7  lea     rax, [rbp+arg_0]
0x14002dfbb  mov     [rsp+30h+var_8], esi; int
0x14002dfbf  mov     r9d, esi
0x14002dfc2  mov     [rsp+30h+var_10], rax; __int64
0x14002dfc7  lea     r8, aTimeout; "Timeout"
0x14002dfce  mov     dword ptr [rbp+arg_0], 0
0x14002dfd5  mov     rdx, r12; PCWSTR
0x14002dfd8  mov     rcx, r15; SourceString
0x14002dfdb  call    NfsReadRegistry
0x14002dfe0  mov     r10d, 0EA60h
0x14002dfe6  test    eax, eax
0x14002dfe8  js      short loc_14002E064
0x14002dfea  movzx   eax, word ptr [rbp+arg_0]
0x14002dfee  mov     r8d, 51EB851Fh
0x14002dff4  imul    ecx, eax, 64h ; 'd'
0x14002dff7  mov     eax, r8d
0x14002dffa  movzx   r9d, cx
0x14002dffe  imul    ecx, r9d, 11h
0x14002e002  mov     [rbx+560h], r9d
0x14002e009  mul     ecx
0x14002e00b  mov     eax, r8d
0x14002e00e  shr     edx, 5
0x14002e011  lea     ecx, [rdx+r9]
0x14002e015  cmp     ecx, r10d
0x14002e018  cmovnb  ecx, r10d
0x14002e01c  mov     [rbx+564h], ecx
0x14002e022  lea     ecx, [r9+r9*4]
0x14002e026  shl     ecx, 3
0x14002e029  mul     ecx
0x14002e02b  shr     edx, 5
0x14002e02e  lea     eax, [rdx+r9]
0x14002e032  cmp     eax, r10d
0x14002e035  cmovnb  eax, r10d
0x14002e039  mov     [rbx+568h], eax
0x14002e03f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e046  cmp     rcx, rdi
0x14002e049  jz      short loc_14002E064
0x14002e04b  mov     eax, [rcx+2Ch]
0x14002e04e  test    sil, al
0x14002e051  jz      short loc_14002E064
0x14002e053  mov     rcx, [rcx+18h]
0x14002e057  mov     edx, 1Eh
0x14002e05c  mov     r8, r13
0x14002e05f  call    WPP_SF_d
0x14002e064  lea     rax, [rbp+arg_0]
0x14002e068  mov     [rsp+30h+var_8], esi; int
0x14002e06c  mov     r9d, esi
0x14002e06f  mov     [rsp+30h+var_10], rax; __int64
0x14002e074  lea     r8, aMounttype; "MountType"
0x14002e07b  mov     dword ptr [rbp+arg_0], 0
0x14002e082  mov     rdx, r12; PCWSTR
0x14002e085  mov     rcx, r15; SourceString
0x14002e088  call    NfsReadRegistry
0x14002e08d  test    eax, eax
0x14002e08f  js      short loc_14002E0C3
0x14002e091  movzx   edx, byte ptr [rbp+arg_0]
0x14002e095  mov     [rbx+570h], dl
0x14002e09b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e0a2  cmp     rcx, rdi
0x14002e0a5  jz      short loc_14002E0C3
0x14002e0a7  mov     eax, [rcx+2Ch]
0x14002e0aa  test    sil, al
0x14002e0ad  jz      short loc_14002E0C3
0x14002e0af  mov     rcx, [rcx+18h]
0x14002e0b3  mov     r9d, edx
0x14002e0b6  mov     edx, 1Fh
0x14002e0bb  mov     r8, r13
0x14002e0be  call    WPP_SF_d
0x14002e0c3  cmp     dword ptr [rbx+56Ch], 5
0x14002e0ca  jnz     short loc_14002E0D2
0x14002e0cc  mov     [rbx+56Ch], esi
0x14002e0d2  lea     rax, [rbp+arg_0]
0x14002e0d6  mov     [rsp+30h+var_8], esi; int
0x14002e0da  lea     r12, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x14002e0e1  mov     dword ptr [rbp+arg_0], 0
0x14002e0e8  mov     rdx, r12; PCWSTR
0x14002e0eb  mov     [rsp+30h+var_10], rax; __int64
0x14002e0f0  mov     r9d, esi
0x14002e0f3  lea     r8, aSoftmounttimeo; "SoftMountTimeout"
0x14002e0fa  mov     rcx, r15; SourceString
0x14002e0fd  call    NfsReadRegistry
0x14002e102  test    eax, eax
0x14002e104  js      short loc_14002E120
0x14002e106  mov     eax, dword ptr [rbp+arg_0]
0x14002e109  mov     ecx, 0EA60h
0x14002e10e  mov     [rbx+934h], eax
0x14002e114  cmp     eax, ecx
0x14002e116  jbe     short loc_14002E12A
0x14002e118  mov     [rbx+934h], ecx
0x14002e11e  jmp     short loc_14002E12A
0x14002e120  mov     dword ptr [rbx+934h], 2710h
0x14002e12a  xor     eax, eax
0x14002e12c  mov     [rsp+30h+var_8], esi; int
0x14002e130  mov     dword ptr [rbp+arg_0], eax
0x14002e133  lea     rdi, [rbx+588h]
0x14002e13a  mov     [rdi], eax
0x14002e13c  lea     r8, aProtocols; "Protocols"
0x14002e143  lea     rax, [rbp+arg_0]
0x14002e147  mov     r9d, esi
0x14002e14a  mov     rdx, r12; PCWSTR
0x14002e14d  mov     [rsp+30h+var_10], rax; __int64
0x14002e152  mov     rcx, r15; SourceString
0x14002e155  call    NfsReadRegistry
0x14002e15a  test    eax, eax
0x14002e15c  js      short loc_14002E16B
0x14002e15e  mov     ecx, dword ptr [rbp+arg_0]
0x14002e161  mov     rdx, rdi
0x14002e164  call    NfsProtocolFlagsToBitfield
0x14002e169  jmp     short loc_14002E183
0x14002e16b  or      byte ptr [rdi], 55h
0x14002e16e  or      byte ptr [rbx+589h], 45h
0x14002e175  or      byte ptr [rbx+58Ah], 55h
0x14002e17c  or      byte ptr [rbx+58Bh], 1
0x14002e183  lea     rax, [rbp+arg_0]
0x14002e187  mov     [rsp+30h+var_8], esi; int
0x14002e18b  mov     r9d, esi
0x14002e18e  mov     [rsp+30h+var_10], rax; __int64
0x14002e193  lea     r8, aAnonymousuid; "AnonymousUid"
0x14002e19a  mov     dword ptr [rbp+arg_0], 0
0x14002e1a1  mov     rdx, r12; PCWSTR
0x14002e1a4  mov     rcx, r15; SourceString
0x14002e1a7  call    NfsReadRegistry
0x14002e1ac  test    eax, eax
0x14002e1ae  js      short loc_14002E1B9
0x14002e1b0  mov     eax, dword ptr [rbp+arg_0]
0x14002e1b3  mov     [rbx+91Ch], eax
0x14002e1b9  lea     rax, [rbp+arg_0]
0x14002e1bd  mov     [rsp+30h+var_8], esi; int
0x14002e1c1  mov     r9d, esi
0x14002e1c4  mov     [rsp+30h+var_10], rax; __int64
0x14002e1c9  lea     r8, aAnonymousgid; "AnonymousGid"
0x14002e1d0  mov     dword ptr [rbp+arg_0], 0
0x14002e1d7  mov     rdx, r12; PCWSTR
0x14002e1da  mov     rcx, r15; SourceString
0x14002e1dd  call    NfsReadRegistry
0x14002e1e2  test    eax, eax
0x14002e1e4  js      short loc_14002E1EF
0x14002e1e6  mov     eax, dword ptr [rbp+arg_0]
0x14002e1e9  mov     [rbx+920h], eax
0x14002e1ef  xor     eax, eax
0x14002e1f1  mov     [rsp+30h+var_8], esi; int
0x14002e1f5  mov     [rbx+590h], eax
0x14002e1fb  lea     r8, aProgramversion; "ProgramVersions"
0x14002e202  mov     dword ptr [rbp+arg_0], eax
0x14002e205  mov     r9d, esi
0x14002e208  lea     rax, [rbp+arg_0]
0x14002e20c  mov     rdx, r12; PCWSTR
0x14002e20f  mov     rcx, r15; SourceString
0x14002e212  mov     [rsp+30h+var_10], rax; __int64
0x14002e217  call    NfsReadRegistry
0x14002e21c  mov     ecx, [rbx+590h]
0x14002e222  test    eax, eax
0x14002e224  js      short loc_14002E233
0x14002e226  mov     eax, dword ptr [rbp+arg_0]
0x14002e229  and     ecx, 0FFFFFFFCh
0x14002e22c  and     eax, 3
0x14002e22f  or      eax, ecx
0x14002e231  jmp     short loc_14002E238
0x14002e233  mov     eax, ecx
0x14002e235  or      eax, 3
0x14002e238  mov     [rbx+590h], eax
0x14002e23e  lea     r8, aCompatibilityf; "CompatibilityFlags"
0x14002e245  xor     eax, eax
0x14002e247  mov     [rsp+30h+var_8], esi; int
0x14002e24b  mov     [rbx+58Ch], eax
0x14002e251  mov     r9d, esi
0x14002e254  mov     dword ptr [rbp+arg_0], eax
0x14002e257  mov     rdx, r12; PCWSTR
0x14002e25a  lea     rax, [rbp+arg_0]
0x14002e25e  mov     rcx, r15; SourceString
0x14002e261  mov     [rsp+30h+var_10], rax; __int64
0x14002e266  call    NfsReadRegistry
0x14002e26b  mov     ecx, [rbx+58Ch]
0x14002e271  and     ecx, 0FFFFFFFEh
0x14002e274  test    eax, eax
0x14002e276  js      short loc_14002E282
0x14002e278  mov     eax, dword ptr [rbp+arg_0]
0x14002e27b  and     eax, 1
0x14002e27e  or      eax, ecx
0x14002e280  jmp     short loc_14002E284
0x14002e282  mov     eax, ecx
0x14002e284  mov     [rbx+58Ch], eax
0x14002e28a  lea     rax, WPP_GLOBAL_Control
0x14002e291  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e298  cmp     rcx, rax
0x14002e29b  jz      short loc_14002E2B5
0x14002e29d  mov     eax, [rcx+2Ch]
0x14002e2a0  test    al, 8
0x14002e2a2  jz      short loc_14002E2B5
0x14002e2a4  mov     rcx, [rcx+18h]
0x14002e2a8  mov     edx, 20h ; ' '
0x14002e2ad  mov     r8, r13
0x14002e2b0  call    WPP_SF_
0x14002e2b5  mov     rbx, [rsp+30h+arg_8]
0x14002e2ba  xor     eax, eax
0x14002e2bc  mov     rsi, [rsp+30h+arg_10]
0x14002e2c1  add     rsp, 30h
0x14002e2c5  pop     r15
0x14002e2c7  pop     r13
0x14002e2c9  pop     r12
0x14002e2cb  pop     rdi
0x14002e2cc  pop     rbp
0x14002e2cd  retn
```
