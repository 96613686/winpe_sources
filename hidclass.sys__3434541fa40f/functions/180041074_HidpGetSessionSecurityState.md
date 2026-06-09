# HidpGetSessionSecurityState

- ea: `0x180041074`
- end: `0x180041240`
- name: `HidpGetSessionSecurityState`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180042f24`

## callees

- `0x18000ddc8`
- `0x180041074`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x180041165`
- `ntoskrnl!ZwQueryValueKey` at `0x180041165`
- `ntoskrnl!ZwClose` at `0x1800411a0`
- `ntoskrnl!ZwClose` at `0x1800411a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180041190`
- `ntoskrnl!ExFreePoolWithTag` at `0x180041190`
- `ntoskrnl!ExAllocatePool2` at `0x180041133`
- `ntoskrnl!ExAllocatePool2` at `0x180041133`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1800410e1`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1800410e1`
- `ntoskrnl!RtlInitUnicodeString` at `0x180041110`
- `ntoskrnl!RtlInitUnicodeString` at `0x180041110`

## string_xrefs

- `0x180041101`: `SessionSecurityEnabled`

## pseudocode

```c
int __fastcall HidpGetSessionSecurityState(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rbx
  __int64 v4; // rax
  char v5; // di
  __int64 v6; // rcx
  __int64 v7; // rax
  bool v8; // al
  struct _DEVICE_OBJECT *v9; // rcx
  NTSTATUS v10; // edx
  int v11; // r8d
  unsigned int *Pool2; // rbx
  _UNKNOWN **v13; // rax
  char v15; // [rsp+48h] [rbp-18h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF
  ULONG Length; // [rsp+80h] [rbp+20h] BYREF
  void *DeviceRegKey; // [rsp+88h] [rbp+28h] BYREF

  v2 = *(_QWORD **)(a1 + 64);
  v4 = *(unsigned int *)(a2 + 4);
  v5 = 1;
  DeviceRegKey = 0;
  v6 = v2[24];
  v7 = 5 * v4;
  v8 = *(_WORD *)(v6 + 8 * v7) == 13 && (unsigned __int16)(*(_WORD *)(v6 + 8 * v7 + 2) - 1) <= 3u;
  v9 = *(struct _DEVICE_OBJECT **)(a1 + 48);
  *(_BYTE *)(a1 + 257) = v8;
  v10 = IoOpenDeviceRegistryKey(v9, 1u, 0x1F0000u, &DeviceRegKey);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v5 = 0;
    }
    v13 = &WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = v10;
      LOBYTE(v10) = v5;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LODWORD(v13) = WPP_RECORDER_AND_TRACE_SF_qL(
                       WPP_GLOBAL_Control->AttachedDevice,
                       v10,
                       v11,
                       v2[88],
                       2,
                       3,
                       12,
                       (__int64)WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids,
                       v2[4],
                       v15);
    }
  }
  else
  {
    Length = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"SessionSecurityEnabled");
    Length = DestinationString.MaximumLength + 28;
    Pool2 = (unsigned int *)ExAllocatePool2(256, Length, 1130654024);
    if ( Pool2 )
    {
      if ( ZwQueryValueKey(DeviceRegKey, &DestinationString, KeyValueFullInformation, Pool2, Length, &Length) >= 0
        && Pool2[3] == 4 )
      {
        *(_BYTE *)(a1 + 257) = *(unsigned int *)((char *)Pool2 + Pool2[2]) != 0;
      }
      ExFreePoolWithTag(Pool2, 0);
    }
    LODWORD(v13) = ZwClose(DeviceRegKey);
  }
  return (int)v13;
}

```

## disassembly

```asm
0x180041074  mov     [rsp-18h+arg_10], rbx
0x180041079  mov     [rsp-18h+arg_18], rsi
0x18004107e  push    rbp
0x18004107f  push    rdi
0x180041080  push    r14
0x180041082  mov     rbp, rsp
0x180041085  sub     rsp, 60h
0x180041089  mov     rbx, [rcx+40h]
0x18004108d  mov     rsi, rcx
0x180041090  mov     eax, [rdx+4]
0x180041093  mov     edi, 1
0x180041098  mov     [rbp+DeviceRegKey], 0
0x1800410a0  mov     rcx, [rbx+0C0h]
0x1800410a7  lea     rax, [rax+rax*4]
0x1800410ab  lea     r14d, [rdi+2]
0x1800410af  cmp     word ptr [rcx+rax*8], 0Dh
0x1800410b4  jnz     short loc_1800410C9
0x1800410b6  movzx   eax, word ptr [rcx+rax*8+2]
0x1800410bb  sub     ax, di
0x1800410be  cmp     ax, r14w
0x1800410c2  ja      short loc_1800410C9
0x1800410c4  mov     al, dil
0x1800410c7  jmp     short loc_1800410CB
0x1800410c9  xor     al, al
0x1800410cb  mov     rcx, [rsi+30h]; DeviceObject
0x1800410cf  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x1800410d3  mov     r8d, 1F0000h; DesiredAccess
0x1800410d9  mov     [rsi+101h], al
0x1800410df  mov     edx, edi; DevInstKeyType
0x1800410e1  call    cs:__imp_IoOpenDeviceRegistryKey
0x1800410e8  nop     dword ptr [rax+rax+00h]
0x1800410ed  mov     edx, eax
0x1800410ef  test    eax, eax
0x1800410f1  js      loc_1800411AE
0x1800410f7  xorps   xmm0, xmm0
0x1800410fa  mov     [rbp+arg_0], 0
0x180041101  lea     rdx, aSessionsecurit; "SessionSecurityEnabled"
0x180041108  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004110c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180041110  call    cs:__imp_RtlInitUnicodeString
0x180041117  nop     dword ptr [rax+rax+00h]
0x18004111c  movzx   eax, [rbp+DestinationString.MaximumLength]
0x180041120  mov     ecx, 100h
0x180041125  add     eax, 1Ch
0x180041128  mov     r8d, 43646948h
0x18004112e  mov     edx, eax
0x180041130  mov     [rbp+arg_0], eax
0x180041133  call    cs:__imp_ExAllocatePool2
0x18004113a  nop     dword ptr [rax+rax+00h]
0x18004113f  mov     rbx, rax
0x180041142  test    rax, rax
0x180041145  jz      short loc_18004119C
0x180041147  mov     ecx, [rbp+arg_0]
0x18004114a  lea     rax, [rbp+arg_0]
0x18004114e  mov     [rsp+60h+ResultLength], rax; ResultLength
0x180041153  lea     rdx, [rbp+DestinationString]; ValueName
0x180041157  mov     [rsp+60h+Length], ecx; Length
0x18004115b  mov     r9, rbx; KeyValueInformation
0x18004115e  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x180041162  mov     r8d, edi; KeyValueInformationClass
0x180041165  call    cs:__imp_ZwQueryValueKey
0x18004116c  nop     dword ptr [rax+rax+00h]
0x180041171  test    eax, eax
0x180041173  js      short loc_18004118B
0x180041175  cmp     dword ptr [rbx+0Ch], 4
0x180041179  jnz     short loc_18004118B
0x18004117b  mov     eax, [rbx+8]
0x18004117e  cmp     dword ptr [rax+rbx], 0
0x180041182  setnz   al
0x180041185  mov     [rsi+101h], al
0x18004118b  xor     edx, edx; Tag
0x18004118d  mov     rcx, rbx; P
0x180041190  call    cs:__imp_ExFreePoolWithTag
0x180041197  nop     dword ptr [rax+rax+00h]
0x18004119c  mov     rcx, [rbp+DeviceRegKey]; Handle
0x1800411a0  call    cs:__imp_ZwClose
0x1800411a7  nop     dword ptr [rax+rax+00h]
0x1800411ac  jmp     short loc_18004122A
0x1800411ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800411b5  lea     rax, WPP_GLOBAL_Control
0x1800411bc  cmp     rcx, rax
0x1800411bf  jz      short loc_1800411CE
0x1800411c1  mov     eax, [rcx+2Ch]
0x1800411c4  test    al, 4
0x1800411c6  jz      short loc_1800411CE
0x1800411c8  cmp     byte ptr [rcx+29h], 2
0x1800411cc  jnb     short loc_1800411D1
0x1800411ce  xor     dil, dil
0x1800411d1  lea     rax, WPP_RECORDER_INITIALIZED
0x1800411d8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800411df  setnz   r8b
0x1800411e3  test    dil, dil
0x1800411e6  jnz     short loc_1800411ED
0x1800411e8  test    r8b, r8b
0x1800411eb  jz      short loc_18004122A
0x1800411ed  mov     rax, [rbx+20h]
0x1800411f1  mov     r9, [rbx+2C0h]
0x1800411f8  mov     rcx, [rcx+18h]
0x1800411fc  mov     dword ptr [rsp+60h+var_18], edx
0x180041200  mov     dl, dil
0x180041203  mov     [rsp+60h+var_20], rax
0x180041208  lea     rax, WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids
0x18004120f  mov     [rsp+60h+var_28], rax
0x180041214  mov     [rsp+60h+var_30], 0Ch
0x18004121b  mov     dword ptr [rsp+60h+ResultLength], r14d
0x180041220  mov     byte ptr [rsp+60h+Length], 2
0x180041225  call    WPP_RECORDER_AND_TRACE_SF_qL
0x18004122a  lea     r11, [rsp+60h+var_s0]
0x18004122f  mov     rbx, [r11+30h]
0x180041233  mov     rsi, [r11+38h]
0x180041237  mov     rsp, r11
0x18004123a  pop     r14
0x18004123c  pop     rdi
0x18004123d  pop     rbp
0x18004123e  retn
```
