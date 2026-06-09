# NfsRdrpReadStartupRegistrySettings

- ea: `0x14002eb18`
- end: `0x14002edcb`
- name: `NfsRdrpReadStartupRegistrySettings`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x14002d428`

## callees

- `0x1400159fc`
- `0x14002eb18`
- `0x140038550`

## string_xrefs

- `0x14002eb5c`: `MaxCacheSize`
- `0x14002ebba`: `MaxDirCacheSize`
- `0x14002eccc`: `DisableCache`
- `0x14002ecff`: `DeleteSymlinks`
- `0x14002ed32`: `DisplayAllLinks`

## pseudocode

```c
__int64 __fastcall NfsRdrpReadStartupRegistrySettings(_DWORD *a1)
{
  int Registry; // eax
  __int64 v3; // r9
  int v4; // eax
  int v5; // ecx
  int v6; // eax
  __int64 v7; // r9
  __int64 result; // rax
  __int64 v9; // [rsp+70h] [rbp+38h] BYREF

  LODWORD(v9) = 0;
  Registry = NfsReadRegistry(
               &stru_140041080,
               L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
               (__int64)&v9,
               4);
  v3 = 0x200000;
  if ( Registry >= 0 )
    v3 = (unsigned int)v9;
  a1[582] = v3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids, v3);
  v4 = NfsReadRegistry(&stru_140041080, L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default", (__int64)&v9, 4);
  v5 = 0x400000;
  if ( v4 >= 0 )
    v5 = v9;
  a1[585] = v5;
  v6 = NfsReadRegistry(&stru_140041080, L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default", (__int64)&v9, 4);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        35,
        WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids,
        (unsigned int)v6);
    a1[580] = 3000;
  }
  else
  {
    v7 = (unsigned int)(100 * v9);
    a1[580] = v7;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids, v7);
      LODWORD(v7) = a1[580];
    }
    if ( (_DWORD)v7 == 300 )
      a1[580] = 1600;
  }
  if ( (int)NfsReadRegistry(
              &stru_140041080,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
              (__int64)&v9,
              4) >= 0
    && (_DWORD)v9 )
  {
    a1[579] |= 1u;
  }
  if ( (int)NfsReadRegistry(
              &stru_140041080,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
              (__int64)&v9,
              4) >= 0
    && (_DWORD)v9 )
  {
    a1[579] |= 0x40u;
  }
  if ( (int)NfsReadRegistry(
              &stru_140041080,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
              (__int64)&v9,
              4) >= 0
    && (_DWORD)v9 )
  {
    a1[579] |= 2u;
  }
  if ( (int)NfsReadRegistry(
              &stru_140041080,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
              (__int64)&v9,
              4) >= 0
    && (_DWORD)v9 )
  {
    a1[579] |= 4u;
  }
  if ( (int)NfsReadRegistry(
              &stru_140041080,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
              (__int64)&v9,
              4) >= 0
    && (_DWORD)v9 )
  {
    a1[579] |= 0x400u;
  }
  result = NfsReadRegistry(
             &stru_140041080,
             L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
             (__int64)&v9,
             4);
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)v9 )
      a1[579] |= 0x100u;
  }
  return result;
}

```

## disassembly

```asm
0x14002eb18  push    rbp
0x14002eb1a  push    rbx
0x14002eb1b  push    rdi
0x14002eb1c  push    r12
0x14002eb1e  push    r14
0x14002eb20  push    r15
0x14002eb22  mov     rbp, rsp
0x14002eb25  sub     rsp, 38h
0x14002eb29  mov     edi, 4
0x14002eb2e  mov     dword ptr [rbp+arg_0], 0
0x14002eb35  mov     rbx, rcx
0x14002eb38  mov     [rsp+38h+var_10], edi; int
0x14002eb3c  lea     rax, [rbp+arg_0]
0x14002eb40  mov     r9d, edi
0x14002eb43  lea     r14, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x14002eb4a  mov     [rsp+38h+var_18], rax; __int64
0x14002eb4f  lea     r15, stru_140041080
0x14002eb56  mov     rdx, r14; PCWSTR
0x14002eb59  mov     rcx, r15; SourceString
0x14002eb5c  lea     r8, aMaxcachesize; "MaxCacheSize"
0x14002eb63  call    NfsReadRegistry
0x14002eb68  test    eax, eax
0x14002eb6a  mov     r9d, 200000h
0x14002eb70  cmovns  r9d, dword ptr [rbp+arg_0]
0x14002eb75  mov     [rbx+918h], r9d
0x14002eb7c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002eb83  lea     r12, WPP_GLOBAL_Control
0x14002eb8a  cmp     rcx, r12
0x14002eb8d  jz      short loc_14002EBAA
0x14002eb8f  mov     eax, [rcx+2Ch]
0x14002eb92  test    dil, al
0x14002eb95  jz      short loc_14002EBAA
0x14002eb97  mov     rcx, [rcx+18h]
0x14002eb9b  lea     edx, [rdi+1Dh]
0x14002eb9e  lea     r8, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002eba5  call    WPP_SF_d
0x14002ebaa  lea     rax, [rbp+arg_0]
0x14002ebae  mov     [rsp+38h+var_10], edi; int
0x14002ebb2  mov     r9d, edi
0x14002ebb5  mov     [rsp+38h+var_18], rax; __int64
0x14002ebba  lea     r8, aMaxdircachesiz; "MaxDirCacheSize"
0x14002ebc1  mov     rdx, r14; PCWSTR
0x14002ebc4  mov     rcx, r15; SourceString
0x14002ebc7  call    NfsReadRegistry
0x14002ebcc  test    eax, eax
0x14002ebce  mov     [rsp+38h+var_10], edi; int
0x14002ebd2  mov     ecx, 400000h
0x14002ebd7  lea     rax, [rbp+arg_0]
0x14002ebdb  cmovns  ecx, dword ptr [rbp+arg_0]
0x14002ebdf  lea     r8, aFirstcontact; "FirstContact"
0x14002ebe6  mov     [rbx+924h], ecx
0x14002ebec  mov     r9d, edi
0x14002ebef  mov     rcx, r15; SourceString
0x14002ebf2  mov     [rsp+38h+var_18], rax; __int64
0x14002ebf7  mov     rdx, r14; PCWSTR
0x14002ebfa  call    NfsReadRegistry
0x14002ebff  mov     r9d, eax
0x14002ec02  test    eax, eax
0x14002ec04  js      short loc_14002EC57
0x14002ec06  imul    r9d, dword ptr [rbp+arg_0], 64h ; 'd'
0x14002ec0b  mov     [rbx+910h], r9d
0x14002ec12  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ec19  cmp     rcx, r12
0x14002ec1c  jz      short loc_14002EC42
0x14002ec1e  mov     eax, [rcx+2Ch]
0x14002ec21  test    dil, al
0x14002ec24  jz      short loc_14002EC42
0x14002ec26  mov     rcx, [rcx+18h]
0x14002ec2a  lea     r8, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002ec31  mov     edx, 22h ; '"'
0x14002ec36  call    WPP_SF_d
0x14002ec3b  mov     r9d, [rbx+910h]
0x14002ec42  cmp     r9d, 12Ch
0x14002ec49  jnz     short loc_14002EC89
0x14002ec4b  mov     dword ptr [rbx+910h], 640h
0x14002ec55  jmp     short loc_14002EC89
0x14002ec57  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ec5e  cmp     rcx, r12
0x14002ec61  jz      short loc_14002EC7F
0x14002ec63  mov     eax, [rcx+2Ch]
0x14002ec66  test    al, 2
0x14002ec68  jz      short loc_14002EC7F
0x14002ec6a  mov     rcx, [rcx+18h]
0x14002ec6e  lea     r8, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002ec75  mov     edx, 23h ; '#'
0x14002ec7a  call    WPP_SF_d
0x14002ec7f  mov     dword ptr [rbx+910h], 0BB8h
0x14002ec89  lea     rax, [rbp+arg_0]
0x14002ec8d  mov     [rsp+38h+var_10], edi; int
0x14002ec91  mov     r9d, edi
0x14002ec94  mov     [rsp+38h+var_18], rax; __int64
0x14002ec99  lea     r8, aDisablev3; "DisableV3"
0x14002eca0  mov     rdx, r14; PCWSTR
0x14002eca3  mov     rcx, r15; SourceString
0x14002eca6  call    NfsReadRegistry
0x14002ecab  test    eax, eax
0x14002ecad  js      short loc_14002ECBC
0x14002ecaf  cmp     dword ptr [rbp+arg_0], 0
0x14002ecb3  jz      short loc_14002ECBC
0x14002ecb5  or      dword ptr [rbx+90Ch], 1
0x14002ecbc  lea     rax, [rbp+arg_0]
0x14002ecc0  mov     [rsp+38h+var_10], edi; int
0x14002ecc4  mov     r9d, edi
0x14002ecc7  mov     [rsp+38h+var_18], rax; __int64
0x14002eccc  lea     r8, aDisablecache; "DisableCache"
0x14002ecd3  mov     rdx, r14; PCWSTR
0x14002ecd6  mov     rcx, r15; SourceString
0x14002ecd9  call    NfsReadRegistry
0x14002ecde  test    eax, eax
0x14002ece0  js      short loc_14002ECEF
0x14002ece2  cmp     dword ptr [rbp+arg_0], 0
0x14002ece6  jz      short loc_14002ECEF
0x14002ece8  or      dword ptr [rbx+90Ch], 40h
0x14002ecef  lea     rax, [rbp+arg_0]
0x14002ecf3  mov     [rsp+38h+var_10], edi; int
0x14002ecf7  mov     r9d, edi
0x14002ecfa  mov     [rsp+38h+var_18], rax; __int64
0x14002ecff  lea     r8, aDeletesymlinks; "DeleteSymlinks"
0x14002ed06  mov     rdx, r14; PCWSTR
0x14002ed09  mov     rcx, r15; SourceString
0x14002ed0c  call    NfsReadRegistry
0x14002ed11  test    eax, eax
0x14002ed13  js      short loc_14002ED22
0x14002ed15  cmp     dword ptr [rbp+arg_0], 0
0x14002ed19  jz      short loc_14002ED22
0x14002ed1b  or      dword ptr [rbx+90Ch], 2
0x14002ed22  lea     rax, [rbp+arg_0]
0x14002ed26  mov     [rsp+38h+var_10], edi; int
0x14002ed2a  mov     r9d, edi
0x14002ed2d  mov     [rsp+38h+var_18], rax; __int64
0x14002ed32  lea     r8, aDisplayalllink; "DisplayAllLinks"
0x14002ed39  mov     rdx, r14; PCWSTR
0x14002ed3c  mov     rcx, r15; SourceString
0x14002ed3f  call    NfsReadRegistry
0x14002ed44  test    eax, eax
0x14002ed46  js      short loc_14002ED54
0x14002ed48  cmp     dword ptr [rbp+arg_0], 0
0x14002ed4c  jz      short loc_14002ED54
0x14002ed4e  or      [rbx+90Ch], edi
0x14002ed54  lea     rax, [rbp+arg_0]
0x14002ed58  mov     [rsp+38h+var_10], edi; int
0x14002ed5c  mov     r9d, edi
0x14002ed5f  mov     [rsp+38h+var_18], rax; __int64
0x14002ed64  lea     r8, aUsereservedpor; "UseReservedPorts"
0x14002ed6b  mov     rdx, r14; PCWSTR
0x14002ed6e  mov     rcx, r15; SourceString
0x14002ed71  call    NfsReadRegistry
0x14002ed76  test    eax, eax
0x14002ed78  js      short loc_14002ED88
0x14002ed7a  cmp     dword ptr [rbp+arg_0], 0
0x14002ed7e  jz      short loc_14002ED88
0x14002ed80  bts     dword ptr [rbx+90Ch], 0Ah
0x14002ed88  lea     rax, [rbp+arg_0]
0x14002ed8c  mov     [rsp+38h+var_10], edi; int
0x14002ed90  mov     r9d, edi
0x14002ed93  mov     [rsp+38h+var_18], rax; __int64
0x14002ed98  lea     r8, aServersupports; "ServerSupportsLongCookies"
0x14002ed9f  mov     rdx, r14; PCWSTR
0x14002eda2  mov     rcx, r15; SourceString
0x14002eda5  call    NfsReadRegistry
0x14002edaa  test    eax, eax
0x14002edac  js      short loc_14002EDBC
0x14002edae  cmp     dword ptr [rbp+arg_0], 0
0x14002edb2  jz      short loc_14002EDBC
0x14002edb4  bts     dword ptr [rbx+90Ch], 8
0x14002edbc  add     rsp, 38h
0x14002edc0  pop     r15
0x14002edc2  pop     r14
0x14002edc4  pop     r12
0x14002edc6  pop     rdi
0x14002edc7  pop     rbx
0x14002edc8  pop     rbp
0x14002edc9  retn
```
