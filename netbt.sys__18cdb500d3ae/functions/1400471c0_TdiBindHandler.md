# TdiBindHandler

- ea: `0x1400471c0`
- end: `0x140047627`
- name: `TdiBindHandler`
- size: `1127`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400061ac`
- `0x140006900`
- `0x1400141bc`
- `0x140017954`
- `0x14001a2b8`
- `0x14001c5d4`
- `0x140030f40`
- `0x140031440`
- `0x1400400a4`
- `0x140040294`
- `0x14004031c`
- `0x140041c38`
- `0x1400424b4`
- `0x1400426a0`
- `0x1400471c0`
- `0x140047630`
- `0x1400493c4`
- `0x140050ce4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140047494`
- `ntoskrnl!RtlInitUnicodeString` at `0x140047494`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400474c0`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400474c0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047202`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047202`
- `ntoskrnl!KeSetEvent` at `0x140047233`
- `ntoskrnl!KeSetEvent` at `0x140047233`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400473dc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400473dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400473d0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400473d0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004733f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004733f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004732a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004732a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004736a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004737b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047395`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400473a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400473bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004736a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004737b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047395`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400473a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400473bd`

## pseudocode

```c
LONG __fastcall TdiBindHandler(unsigned int a1, const UNICODE_STRING *a2)
{
  const UNICODE_STRING *v4; // rcx
  __int64 v6; // rax
  struct _DEVICE_OBJECT *v7; // rsi
  int v8; // eax
  int v9; // ecx
  int v10; // r8d
  unsigned int v11; // esi
  int v12; // edx
  unsigned int v13; // r9d
  PVOID v14; // rdi
  PVOID v15; // rdi
  __int64 v16; // rdx
  unsigned int v17; // eax
  int v18; // ecx
  int v19; // r8d
  int v20; // ecx
  int v21; // r8d
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-69h]
  PVOID v23[2]; // [rsp+30h] [rbp-59h] BYREF
  PVOID P; // [rsp+40h] [rbp-49h] BYREF
  PVOID v25; // [rsp+48h] [rbp-41h] BYREF
  WCHAR SourceString[64]; // [rsp+50h] [rbp-39h] BYREF

  KeWaitForSingleObject(&stru_140038590, Executive, 0, 0, 0);
  if ( a1 == 1 )
  {
    if ( !(unsigned __int8)IsIPv6Interface(a2) )
    {
      v8 = NbtDeviceAdd(v4);
      v11 = v8;
      if ( v8 < 0 )
      {
        if ( (BYTE3(xmmword_140038420) & 1) != 0 )
        {
          LODWORD(Timeout) = (unsigned __int16)word_1400395BA;
          WPP_SF_dd(1048, 35, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids, (unsigned int)v8, Timeout);
        }
        NbtLogDeviceCreationFailure(v11, 273, a2->Buffer);
      }
      if ( (BYTE3(xmmword_140038420) & 1) != 0 )
      {
        v12 = 36;
        v13 = v11;
LABEL_12:
        WPP_SF_dZ(v9, v12, v10, v13, (__int64)a2);
      }
    }
  }
  else
  {
    if ( a1 != 2 )
    {
      switch ( a1 )
      {
        case 3u:
          P = 0;
          v25 = 0;
          v23[0] = 0;
          if ( (BYTE3(xmmword_140038420) & 1) != 0 )
            WPP_SF_(1048, 41, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids);
          KeEnterCriticalRegion();
          ExAcquireResourceExclusiveLite(&Resource, 1u);
          NbtReadRegistry((__int64 *)&P, (__int64 *)&v25, v23);
          v14 = P;
          if ( P )
          {
            ExFreePoolWithTag(*(PVOID *)P, 0);
            ExFreePoolWithTag(v14, 0);
          }
          v15 = v25;
          if ( v25 )
          {
            ExFreePoolWithTag(*(PVOID *)v25, 0);
            ExFreePoolWithTag(v15, 0);
          }
          if ( v23[0] )
            ExFreePoolWithTag(v23[0], 0);
          ExReleaseResourceLite(&Resource);
          KeLeaveCriticalRegion();
          SetNodeType();
          if ( (BYTE3(xmmword_140038420) & 1) == 0 )
            return KeSetEvent(&stru_140038590, 2, 0);
          v16 = 42;
          break;
        case 4u:
          wcscpy(SourceString, L"\\Device\\Tdx");
          memset(&SourceString[12], 0, 0x60u);
          *(_OWORD *)v23 = 0;
          RtlInitUnicodeString((PUNICODE_STRING)v23, SourceString);
          WORD1(v23[0]) = 120;
          if ( (BYTE3(xmmword_140038420) & 1) != 0 )
          {
            WPP_SF_ZZ(v18, 43, v19, (_DWORD)a2, (__int64)v23);
            if ( (BYTE3(xmmword_140038420) & 1) != 0 )
              WPP_SF_ZZ(v20, 44, v21, (_DWORD)a2, (__int64)v23);
          }
          if ( !RtlCompareUnicodeString(a2, (PCUNICODE_STRING)v23, 1u) )
          {
            if ( (BYTE3(xmmword_140038420) & 1) != 0 )
              WPP_SF_(1048, 45, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids);
            NbtDownBootCounter();
          }
          return KeSetEvent(&stru_140038590, 2, 0);
        case 5u:
          if ( (BYTE3(xmmword_140038420) & 1) == 0 )
            return KeSetEvent(&stru_140038590, 2, 0);
          v16 = 46;
          break;
        default:
          if ( (BYTE3(xmmword_140038420) & 1) != 0 )
          {
            WPP_SF_d(1048, 47, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids, a1);
            if ( (BYTE3(xmmword_140038420) & 1) != 0 )
              WPP_SF_d(1048, 48, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids, a1);
          }
          return KeSetEvent(&stru_140038590, 2, 0);
      }
      WPP_SF_(1048, v16, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids);
      return KeSetEvent(&stru_140038590, 2, 0);
    }
    v6 = NbtFindAndReferenceDevice(a2);
    v7 = (struct _DEVICE_OBJECT *)v6;
    if ( v6 )
    {
      if ( (BYTE3(xmmword_140038420) & 1) != 0 )
        WPP_SF_Z(1048, 37, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids, v6 + 456);
      NBT_DEREFERENCE_DEVICE(v7, 6);
      v17 = NbtDestroyDevice(v7);
      if ( (BYTE3(xmmword_140038420) & 1) != 0 )
      {
        v12 = 38;
        v13 = v17;
        goto LABEL_12;
      }
    }
    else if ( (BYTE3(xmmword_140038420) & 1) != 0 )
    {
      WPP_SF_Z(1048, 39, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids, a2);
      if ( (BYTE3(xmmword_140038420) & 1) != 0 )
        WPP_SF_Z(1048, 40, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids, a2);
    }
  }
  return KeSetEvent(&stru_140038590, 2, 0);
}

```

## disassembly

```asm
0x1400471c0  mov     [rsp-8+arg_10], rsi
0x1400471c5  mov     [rsp-8+arg_18], rdi
0x1400471ca  push    rbp
0x1400471cb  lea     rbp, [rsp-57h]
0x1400471d0  sub     rsp, 0E0h
0x1400471d7  mov     rax, cs:__security_cookie
0x1400471de  xor     rax, rsp
0x1400471e1  mov     [rbp+57h+var_10], rax
0x1400471e5  mov     rdi, rdx
0x1400471e8  mov     [rsp+0E0h+Timeout], 0; Timeout
0x1400471f1  mov     esi, ecx
0x1400471f3  xor     edx, edx; WaitReason
0x1400471f5  lea     rcx, stru_140038590; Object
0x1400471fc  xor     r9d, r9d; Alertable
0x1400471ff  xor     r8d, r8d; WaitMode
0x140047202  call    cs:__imp_KeWaitForSingleObject
0x140047209  nop     dword ptr [rax+rax+00h]
0x14004720e  mov     ecx, esi
0x140047210  sub     ecx, 1
0x140047213  jnz     short loc_140047261
0x140047215  mov     rcx, rdi
0x140047218  call    IsIPv6Interface
0x14004721d  test    al, al
0x14004721f  jz      loc_1400472C9
0x140047225  xor     r8d, r8d; Wait
0x140047228  lea     rcx, stru_140038590; Event
0x14004722f  lea     edx, [r8+2]; Increment
0x140047233  call    cs:__imp_KeSetEvent
0x14004723a  nop     dword ptr [rax+rax+00h]
0x14004723f  mov     rcx, [rbp+57h+var_10]
0x140047243  xor     rcx, rsp; StackCookie
0x140047246  call    __security_check_cookie
0x14004724b  lea     r11, [rsp+0E0h+var_s0]
0x140047253  mov     rsi, [r11+20h]
0x140047257  mov     rdi, [r11+28h]
0x14004725b  mov     rsp, r11
0x14004725e  pop     rbp
0x14004725f  retn
0x140047261  sub     ecx, 1
0x140047264  jnz     loc_1400472FC
0x14004726a  mov     dl, 1
0x14004726c  mov     rcx, rdi; String1
0x14004726f  call    NbtFindAndReferenceDevice
0x140047274  mov     rsi, rax
0x140047277  test    rax, rax
0x14004727a  jnz     loc_140047415
0x140047280  test    byte ptr cs:xmmword_140038420+3, 1
0x140047287  jz      short loc_140047225
0x140047289  lea     edx, [rax+27h]
0x14004728c  mov     ecx, 418h
0x140047291  mov     r9, rdi
0x140047294  lea     r8, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids
0x14004729b  call    WPP_SF_Z
0x1400472a0  test    byte ptr cs:xmmword_140038420+3, 1
0x1400472a7  jz      loc_140047225
0x1400472ad  lea     edx, [rsi+28h]
0x1400472b0  mov     ecx, 418h
0x1400472b5  mov     r9, rdi
0x1400472b8  lea     r8, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids
0x1400472bf  call    WPP_SF_Z
0x1400472c4  jmp     loc_140047225
0x1400472c9  call    NbtDeviceAdd
0x1400472ce  mov     esi, eax
0x1400472d0  test    eax, eax
0x1400472d2  js      loc_1400475E3
0x1400472d8  test    byte ptr cs:xmmword_140038420+3, 1
0x1400472df  jz      loc_140047225
0x1400472e5  mov     edx, 24h ; '$'
0x1400472ea  mov     r9d, esi
0x1400472ed  mov     [rsp+0E0h+Timeout], rdi
0x1400472f2  call    WPP_SF_dZ
0x1400472f7  jmp     loc_140047225
0x1400472fc  sub     ecx, 1
0x1400472ff  jnz     loc_140047455
0x140047305  mov     [rbp+57h+P], 0
0x14004730d  mov     [rbp+57h+var_98], 0
0x140047315  mov     [rbp+57h+var_B0], 0
0x14004731d  test    byte ptr cs:xmmword_140038420+3, 1
0x140047324  jnz     loc_1400475A6
0x14004732a  call    cs:__imp_KeEnterCriticalRegion
0x140047331  nop     dword ptr [rax+rax+00h]
0x140047336  mov     dl, 1; Wait
0x140047338  lea     rcx, Resource; Resource
0x14004733f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140047346  nop     dword ptr [rax+rax+00h]
0x14004734b  lea     r8, [rbp+57h+var_B0]
0x14004734f  lea     rdx, [rbp+57h+var_98]
0x140047353  lea     rcx, [rbp+57h+P]
0x140047357  call    NbtReadRegistry
0x14004735c  mov     rdi, [rbp+57h+P]
0x140047360  test    rdi, rdi
0x140047363  jz      short loc_140047387
0x140047365  mov     rcx, [rdi]; P
0x140047368  xor     edx, edx; Tag
0x14004736a  call    cs:__imp_ExFreePoolWithTag
0x140047371  nop     dword ptr [rax+rax+00h]
0x140047376  xor     edx, edx; Tag
0x140047378  mov     rcx, rdi; P
0x14004737b  call    cs:__imp_ExFreePoolWithTag
0x140047382  nop     dword ptr [rax+rax+00h]
0x140047387  mov     rdi, [rbp+57h+var_98]
0x14004738b  test    rdi, rdi
0x14004738e  jz      short loc_1400473B2
0x140047390  mov     rcx, [rdi]; P
0x140047393  xor     edx, edx; Tag
0x140047395  call    cs:__imp_ExFreePoolWithTag
0x14004739c  nop     dword ptr [rax+rax+00h]
0x1400473a1  xor     edx, edx; Tag
0x1400473a3  mov     rcx, rdi; P
0x1400473a6  call    cs:__imp_ExFreePoolWithTag
0x1400473ad  nop     dword ptr [rax+rax+00h]
0x1400473b2  mov     rcx, [rbp+57h+var_B0]; P
0x1400473b6  test    rcx, rcx
0x1400473b9  jz      short loc_1400473C9
0x1400473bb  xor     edx, edx; Tag
0x1400473bd  call    cs:__imp_ExFreePoolWithTag
0x1400473c4  nop     dword ptr [rax+rax+00h]
0x1400473c9  lea     rcx, Resource; Resource
0x1400473d0  call    cs:__imp_ExReleaseResourceLite
0x1400473d7  nop     dword ptr [rax+rax+00h]
0x1400473dc  call    cs:__imp_KeLeaveCriticalRegion
0x1400473e3  nop     dword ptr [rax+rax+00h]
0x1400473e8  call    SetNodeType
0x1400473ed  test    byte ptr cs:xmmword_140038420+3, 1
0x1400473f4  jz      loc_140047225
0x1400473fa  mov     edx, 2Ah ; '*'
0x1400473ff  mov     ecx, 418h
0x140047404  lea     r8, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids
0x14004740b  call    WPP_SF_
0x140047410  jmp     loc_140047225
0x140047415  test    byte ptr cs:xmmword_140038420+3, 1
0x14004741c  jnz     loc_1400475C1
0x140047422  xor     r8d, r8d
0x140047425  mov     rcx, rsi
0x140047428  lea     edx, [r8+6]
0x14004742c  call    NBT_DEREFERENCE_DEVICE
0x140047431  mov     dl, 1
0x140047433  mov     rcx, rsi; DeviceObject
0x140047436  call    NbtDestroyDevice
0x14004743b  test    byte ptr cs:xmmword_140038420+3, 1
0x140047442  jz      loc_140047225
0x140047448  mov     edx, 26h ; '&'
0x14004744d  mov     r9d, eax
0x140047450  jmp     loc_1400472ED
0x140047455  sub     ecx, 1
0x140047458  jnz     loc_1400474FB
0x14004745e  movups  xmm0, xmmword ptr cs:aDeviceTdx; "\\Device\\Tdx"
0x140047465  lea     r8d, [rcx+60h]; Size
0x140047469  xor     edx, edx; Val
0x14004746b  movsd   xmm1, qword ptr cs:aDeviceTdx+10h; "Tdx"
0x140047473  lea     rcx, [rbp+57h+var_78]; void *
0x140047477  movaps  xmmword ptr [rbp+57h+SourceString], xmm0
0x14004747b  movsd   [rbp+57h+var_80], xmm1
0x140047480  call    memset
0x140047485  xorps   xmm0, xmm0
0x140047488  lea     rdx, [rbp+57h+SourceString]; SourceString
0x14004748c  lea     rcx, [rbp+57h+var_B0]; DestinationString
0x140047490  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x140047494  call    cs:__imp_RtlInitUnicodeString
0x14004749b  nop     dword ptr [rax+rax+00h]
0x1400474a0  mov     eax, 78h ; 'x'
0x1400474a5  mov     word ptr [rbp+57h+var_B0+2], ax
0x1400474a9  test    byte ptr cs:xmmword_140038420+3, 1
0x1400474b0  jnz     loc_140047568
0x1400474b6  mov     r8b, 1; CaseInSensitive
0x1400474b9  lea     rdx, [rbp+57h+var_B0]; String2
0x1400474bd  mov     rcx, rdi; String1
0x1400474c0  call    cs:__imp_RtlCompareUnicodeString
0x1400474c7  nop     dword ptr [rax+rax+00h]
0x1400474cc  test    eax, eax
0x1400474ce  jnz     loc_140047225
0x1400474d4  test    byte ptr cs:xmmword_140038420+3, 1
0x1400474db  jz      short loc_1400474F1
0x1400474dd  lea     edx, [rax+2Dh]
0x1400474e0  mov     ecx, 418h
0x1400474e5  lea     r8, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids
0x1400474ec  call    WPP_SF_
0x1400474f1  call    NbtDownBootCounter
0x1400474f6  jmp     loc_140047225
0x1400474fb  cmp     ecx, 1
0x1400474fe  jz      short loc_140047551
0x140047500  test    byte ptr cs:xmmword_140038420+3, 1
0x140047507  jz      loc_140047225
0x14004750d  mov     edx, 2Fh ; '/'
0x140047512  lea     r8, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids
0x140047519  mov     ecx, 418h
0x14004751e  mov     r9d, esi
0x140047521  call    WPP_SF_d
0x140047526  test    byte ptr cs:xmmword_140038420+3, 1
0x14004752d  jz      loc_140047225
0x140047533  mov     edx, 30h ; '0'
0x140047538  lea     r8, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids
0x14004753f  mov     ecx, 418h
0x140047544  mov     r9d, esi
0x140047547  call    WPP_SF_d
0x14004754c  jmp     loc_140047225
0x140047551  test    byte ptr cs:xmmword_140038420+3, 1
0x140047558  jz      loc_140047225
0x14004755e  mov     edx, 2Eh ; '.'
0x140047563  jmp     loc_1400473FF
0x140047568  lea     rax, [rbp+57h+var_B0]
0x14004756c  mov     edx, 2Bh ; '+'
0x140047571  mov     r9, rdi
0x140047574  mov     [rsp+0E0h+Timeout], rax
0x140047579  call    WPP_SF_ZZ
0x14004757e  test    byte ptr cs:xmmword_140038420+3, 1
0x140047585  jz      loc_1400474B6
0x14004758b  lea     rax, [rbp+57h+var_B0]
0x14004758f  mov     edx, 2Ch ; ','
0x140047594  mov     r9, rdi
0x140047597  mov     [rsp+0E0h+Timeout], rax
0x14004759c  call    WPP_SF_ZZ
0x1400475a1  jmp     loc_1400474B6
0x1400475a6  mov     edx, 29h ; ')'
0x1400475ab  lea     r8, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids
0x1400475b2  mov     ecx, 418h
0x1400475b7  call    WPP_SF_
0x1400475bc  jmp     loc_14004732A
0x1400475c1  lea     r9, [rax+1C8h]
0x1400475c8  mov     edx, 25h ; '%'
0x1400475cd  mov     ecx, 418h
0x1400475d2  lea     r8, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids
0x1400475d9  call    WPP_SF_Z
0x1400475de  jmp     loc_140047422
0x1400475e3  test    byte ptr cs:xmmword_140038420+3, 1
0x1400475ea  jz      short loc_140047612
0x1400475ec  movzx   r8d, cs:word_1400395BA
0x1400475f4  mov     edx, 23h ; '#'
0x1400475f9  mov     dword ptr [rsp+0E0h+Timeout], r8d
0x1400475fe  mov     ecx, 418h
0x140047603  lea     r8, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids
0x14004760a  mov     r9d, esi
0x14004760d  call    WPP_SF_dd
0x140047612  mov     r8, [rdi+8]
0x140047616  mov     edx, 111h
0x14004761b  mov     ecx, esi
0x14004761d  call    NbtLogDeviceCreationFailure
0x140047622  jmp     loc_1400472D8
```
