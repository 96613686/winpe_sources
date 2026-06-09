# NetioNcmInitializeState

- ea: `0x14005c9a0`
- end: `0x14005cc69`
- name: `NetioNcmInitializeState`
- size: `713`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14003ebf0`
- `0x140042460`
- `0x140042d60`
- `0x140050b00`
- `0x140050ea4`
- `0x1400512d8`
- `0x14005c36c`
- `0x14005c45c`
- `0x14005c9a0`
- `0x140078400`

## import_xrefs

- `ntoskrnl!RtlCreateHashTableEx` at `0x14005c9f5`
- `ntoskrnl!RtlCreateHashTableEx` at `0x14005ca1f`
- `ntoskrnl!RtlCreateHashTableEx` at `0x14005c9f5`
- `ntoskrnl!RtlCreateHashTableEx` at `0x14005ca1f`
- `ntoskrnl!ZwPowerInformation` at `0x14005ca8e`
- `ntoskrnl!ZwPowerInformation` at `0x14005ca8e`
- `ntoskrnl!RtlDeleteHashTable` at `0x14005ca32`
- `ntoskrnl!RtlDeleteHashTable` at `0x14005ca32`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cba8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005cba8`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005ca5c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005ca5c`
- `ext-ms-win-kmpdc-l1-1-0!Pdcv2ActivationClientRegister` at `0x14005cc10`
- `ext-ms-win-kmpdc-l1-1-0!Pdcv2ActivationClientRegister` at `0x14005cc10`

## string_xrefs

- `0x14005cb0b`: `\Registry\Machine\System\CurrentControlSet\Services\NcbService\NCB`

## pseudocode

```c
__int64 __fastcall NetioNcmInitializeState(void *a1)
{
  NTSTATUS v3; // eax
  __int64 v4; // rdx
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  int *v8; // rbx
  HANDLE KeyHandle; // [rsp+40h] [rbp-30h] BYREF
  PVOID P; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v11[4]; // [rsp+50h] [rbp-20h] BYREF
  char OutputBuffer; // [rsp+98h] [rbp+28h] BYREF
  __int64 v13; // [rsp+A0h] [rbp+30h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE *v14; // [rsp+A8h] [rbp+38h] BYREF

  KeyHandle = 0;
  P = 0;
  memset(&NcmGlobal, 0, 0xB8u);
  OutputBuffer = 0;
  v14 = &stru_14009B008;
  if ( !(unsigned __int8)RtlCreateHashTableEx(&v14, 128, 0, 0) )
    return 3221225626LL;
  v14 = &stru_14009B030;
  if ( !(unsigned __int8)RtlCreateHashTableEx(&v14, 128, 0, 0) )
  {
    RtlDeleteHashTable(&stru_14009B008);
    return 3221225626LL;
  }
  KeInitializeSpinLock(&SpinLock);
  dword_14009B060 = 0;
  Context = a1;
  v3 = ZwPowerInformation((POWER_INFORMATION_LEVEL)66, 0, 0, &OutputBuffer, 1u);
  v7 = (unsigned int)v3;
  if ( v3 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        54,
        WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids,
        (unsigned int)v3);
    }
  }
  else
  {
    byte_14009B06C = OutputBuffer;
  }
  dword_14009B074 = NcmGetSystemReservedSlotCount(v5, v4, v6, v7);
  if ( byte_14009B06C )
  {
    dword_14009B090 = 16;
    if ( (int)NetioOpenKey(L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\NcbService\\NCB", 1u, &KeyHandle) >= 0 )
    {
      if ( (int)NetioQueryValueKey(KeyHandle, 0x6D636E4Eu, (__int64)&P, (__int64)&v13) >= 0 )
      {
        v8 = (int *)P;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            55,
            WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids,
            (unsigned int)dword_14009B090,
            *(_DWORD *)P);
        }
        dword_14009B090 = *v8;
        ExFreePoolWithTag(v8, 0x6D636E4Eu);
      }
      NetioCloseKey(&KeyHandle);
    }
  }
  qword_14009B0A0 = (__int64)&qword_14009B098;
  qword_14009B098 = &qword_14009B098;
  if ( !qword_14009B0A8 && !(unsigned __int8)NetioCheckIfPdcActivationDisabled() )
  {
    v11[0] = 1;
    v11[1] = WfpStreamEndpointCleanupBegin;
    v11[2] = 0;
    if ( (int)Pdcv2ActivationClientRegister(9, v11, &qword_14009B0A8) < 0 )
    {
      qword_14009B0A8 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids);
      }
      byte_14009B0B0 = 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14005c9a0  mov     [rsp-18h+arg_0], rbx
0x14005c9a5  push    rbp
0x14005c9a6  push    rsi
0x14005c9a7  push    r15
0x14005c9a9  mov     rbp, rsp
0x14005c9ac  sub     rsp, 70h
0x14005c9b0  mov     rbx, rcx
0x14005c9b3  mov     [rbp+KeyHandle], 0
0x14005c9bb  lea     rcx, NcmGlobal; void *
0x14005c9c2  mov     [rbp+P], 0
0x14005c9ca  xor     edx, edx; Val
0x14005c9cc  mov     r8d, 0B8h; Size
0x14005c9d2  call    memset
0x14005c9d7  lea     rsi, stru_14009B008
0x14005c9de  mov     [rbp+OutputBuffer], 0
0x14005c9e2  xor     r9d, r9d
0x14005c9e5  mov     [rbp+arg_18], rsi
0x14005c9e9  xor     r8d, r8d
0x14005c9ec  lea     rcx, [rbp+arg_18]
0x14005c9f0  mov     edx, 80h
0x14005c9f5  call    cs:__imp_RtlCreateHashTableEx
0x14005c9fc  nop     dword ptr [rax+rax+00h]
0x14005ca01  test    al, al
0x14005ca03  jz      short loc_14005CA3E
0x14005ca05  lea     rax, stru_14009B030
0x14005ca0c  xor     r9d, r9d
0x14005ca0f  xor     r8d, r8d
0x14005ca12  mov     [rbp+arg_18], rax
0x14005ca16  mov     edx, 80h
0x14005ca1b  lea     rcx, [rbp+arg_18]
0x14005ca1f  call    cs:__imp_RtlCreateHashTableEx
0x14005ca26  nop     dword ptr [rax+rax+00h]
0x14005ca2b  test    al, al
0x14005ca2d  jnz     short loc_14005CA55
0x14005ca2f  mov     rcx, rsi; HashTable
0x14005ca32  call    cs:__imp_RtlDeleteHashTable
0x14005ca39  nop     dword ptr [rax+rax+00h]
0x14005ca3e  mov     eax, 0C000009Ah
0x14005ca43  mov     rbx, [rsp+70h+arg_0]
0x14005ca4b  add     rsp, 70h
0x14005ca4f  pop     r15
0x14005ca51  pop     rsi
0x14005ca52  pop     rbp
0x14005ca53  retn
0x14005ca55  lea     rcx, SpinLock; SpinLock
0x14005ca5c  call    cs:__imp_KeInitializeSpinLock
0x14005ca63  nop     dword ptr [rax+rax+00h]
0x14005ca68  mov     esi, 1
0x14005ca6d  mov     cs:dword_14009B060, 0
0x14005ca77  lea     r9, [rbp+OutputBuffer]; OutputBuffer
0x14005ca7b  mov     cs:Context, rbx
0x14005ca82  xor     r8d, r8d; InputBufferLength
0x14005ca85  mov     [rsp+70h+OutputBufferLength], esi; OutputBufferLength
0x14005ca89  xor     edx, edx; InputBuffer
0x14005ca8b  lea     ecx, [rsi+41h]; InformationLevel
0x14005ca8e  call    cs:__imp_ZwPowerInformation
0x14005ca95  nop     dword ptr [rax+rax+00h]
0x14005ca9a  lea     r15, WPP_GLOBAL_Control
0x14005caa1  mov     r9d, eax
0x14005caa4  test    eax, eax
0x14005caa6  js      short loc_14005CAB3
0x14005caa8  mov     al, [rbp+OutputBuffer]
0x14005caab  mov     cs:byte_14009B06C, al
0x14005cab1  jmp     short loc_14005CAE3
0x14005cab3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005caba  cmp     rcx, r15
0x14005cabd  jz      short loc_14005CAE3
0x14005cabf  cmp     byte ptr [rcx+29h], 3
0x14005cac3  jb      short loc_14005CAE3
0x14005cac5  test    dword ptr [rcx+2Ch], 200000h
0x14005cacc  jz      short loc_14005CAE3
0x14005cace  mov     rcx, [rcx+18h]
0x14005cad2  lea     r8, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids
0x14005cad9  mov     edx, 36h ; '6'
0x14005cade  call    WPP_SF_d
0x14005cae3  call    NcmGetSystemReservedSlotCount
0x14005cae8  cmp     cs:byte_14009B06C, 0
0x14005caef  mov     cs:dword_14009B074, eax
0x14005caf5  jz      loc_14005CBBD
0x14005cafb  lea     r8, [rbp+KeyHandle]; KeyHandle
0x14005caff  mov     cs:dword_14009B090, 10h
0x14005cb09  mov     edx, esi; DesiredAccess
0x14005cb0b  lea     rcx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14005cb12  call    NetioOpenKey
0x14005cb17  test    eax, eax
0x14005cb19  js      loc_14005CBBD
0x14005cb1f  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14005cb23  lea     rax, [rbp+arg_10]
0x14005cb27  mov     [rsp+70h+var_40], rax; __int64
0x14005cb2c  lea     rdx, aRtcbasesystems; "RtcBaseSystemSlotNumber"
0x14005cb33  mov     r9d, 40h ; '@'
0x14005cb39  lea     rax, [rbp+P]
0x14005cb3d  mov     [rsp+70h+var_48], rax; __int64
0x14005cb42  mov     [rsp+70h+OutputBufferLength], 6D636E4Eh; Tag
0x14005cb4a  lea     r8d, [r9-3Ch]
0x14005cb4e  call    NetioQueryValueKey
0x14005cb53  test    eax, eax
0x14005cb55  js      short loc_14005CBB4
0x14005cb57  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cb5e  mov     rbx, [rbp+P]
0x14005cb62  cmp     rcx, r15
0x14005cb65  jz      short loc_14005CB98
0x14005cb67  cmp     byte ptr [rcx+29h], 4
0x14005cb6b  jb      short loc_14005CB98
0x14005cb6d  test    dword ptr [rcx+2Ch], 200000h
0x14005cb74  jz      short loc_14005CB98
0x14005cb76  mov     eax, [rbx]
0x14005cb78  lea     r8, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids
0x14005cb7f  mov     r9d, cs:dword_14009B090
0x14005cb86  mov     edx, 37h ; '7'
0x14005cb8b  mov     rcx, [rcx+18h]
0x14005cb8f  mov     [rsp+70h+OutputBufferLength], eax
0x14005cb93  call    WPP_SF_Dd
0x14005cb98  mov     eax, [rbx]
0x14005cb9a  mov     edx, 6D636E4Eh; Tag
0x14005cb9f  mov     rcx, rbx; P
0x14005cba2  mov     cs:dword_14009B090, eax
0x14005cba8  call    cs:__imp_ExFreePoolWithTag
0x14005cbaf  nop     dword ptr [rax+rax+00h]
0x14005cbb4  lea     rcx, [rbp+KeyHandle]
0x14005cbb8  call    NetioCloseKey
0x14005cbbd  cmp     cs:qword_14009B0A8, 0
0x14005cbc5  lea     rax, qword_14009B098
0x14005cbcc  mov     cs:qword_14009B0A0, rax
0x14005cbd3  mov     cs:qword_14009B098, rax
0x14005cbda  jnz     loc_14005CC62
0x14005cbe0  call    NetioCheckIfPdcActivationDisabled
0x14005cbe5  test    al, al
0x14005cbe7  jnz     short loc_14005CC62
0x14005cbe9  lea     rax, WfpStreamEndpointCleanupBegin
0x14005cbf0  mov     [rbp+var_20], rsi
0x14005cbf4  lea     r8, qword_14009B0A8
0x14005cbfb  mov     [rbp+var_18], rax
0x14005cbff  lea     rdx, [rbp+var_20]
0x14005cc03  mov     [rbp+var_10], 0
0x14005cc0b  mov     ecx, 9
0x14005cc10  call    cs:__imp_Pdcv2ActivationClientRegister
0x14005cc17  nop     dword ptr [rax+rax+00h]
0x14005cc1c  test    eax, eax
0x14005cc1e  jns     short loc_14005CC62
0x14005cc20  mov     cs:qword_14009B0A8, 0
0x14005cc2b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cc32  cmp     rcx, r15
0x14005cc35  jz      short loc_14005CC5B
0x14005cc37  cmp     byte ptr [rcx+29h], 4
0x14005cc3b  jb      short loc_14005CC5B
0x14005cc3d  test    dword ptr [rcx+2Ch], 200000h
0x14005cc44  jz      short loc_14005CC5B
0x14005cc46  mov     rcx, [rcx+18h]
0x14005cc4a  lea     r8, WPP_b82db9e625ba361a08c79e9c4a088c0e_Traceguids
0x14005cc51  mov     edx, 38h ; '8'
0x14005cc56  call    WPP_SF_
0x14005cc5b  mov     cs:byte_14009B0B0, sil
0x14005cc62  xor     eax, eax
0x14005cc64  jmp     loc_14005CA43
```
