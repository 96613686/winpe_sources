# LoadKeyboardUsageMappingList

- ea: `0x140004f80`
- end: `0x140005168`
- name: `LoadKeyboardUsageMappingList`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000ff70`

## callees

- `0x140004f80`
- `0x140006f4c`
- `0x140007130`
- `0x140010de0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400050ef`
- `ntoskrnl!ZwClose` at `0x140005107`
- `ntoskrnl!ZwClose` at `0x1400050ef`
- `ntoskrnl!ZwClose` at `0x140005107`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000511a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000511a`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140004fc8`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140004fc8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005137`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005137`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14000504b`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14000504b`
- `ntoskrnl!ExAllocatePool2` at `0x14000509f`
- `ntoskrnl!ExAllocatePool2` at `0x14000509f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004ff2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004ff2`

## pseudocode

```c
void __fastcall LoadKeyboardUsageMappingList(_QWORD *a1)
{
  struct _DEVICE_OBJECT *v2; // rcx
  __int64 v3; // rsi
  __int64 v4; // rdi
  ULONG v5; // r14d
  __int16 v6; // ax
  _WORD *v7; // r10
  __int16 v8; // ax
  __int64 v9; // r10
  KIRQL v10; // al
  ULONG ResultLength; // [rsp+30h] [rbp-39h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-31h] BYREF
  void *DeviceRegKey; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-21h] BYREF
  __int64 v15; // [rsp+58h] [rbp-11h] BYREF
  __int16 v16; // [rsp+60h] [rbp-9h]
  __int64 v17; // [rsp+68h] [rbp-1h] BYREF
  __int16 v18; // [rsp+70h] [rbp+7h]
  __int64 KeyValueInformation; // [rsp+78h] [rbp+Fh] BYREF
  unsigned int v20; // [rsp+80h] [rbp+17h]
  int v21; // [rsp+84h] [rbp+1Bh]
  unsigned int v22; // [rsp+88h] [rbp+1Fh]
  __int64 v23; // [rsp+8Ch] [rbp+23h]

  v2 = (struct _DEVICE_OBJECT *)a1[2];
  DeviceRegKey = 0;
  v3 = 0;
  if ( IoOpenDeviceRegistryKey(v2, 2u, 0x20019u, &DeviceRegKey) >= 0 )
  {
    KeyHandle = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"UsageMappings");
    if ( OpenSubkey(&KeyHandle, DeviceRegKey, &DestinationString) >= 0 )
    {
      v4 = 0;
      v5 = 0;
      ResultLength = 0;
      while ( ZwEnumerateValueKey(KeyHandle, v5, KeyValueFullInformation, &KeyValueInformation, 0x2Au, &ResultLength) >= 0 )
      {
        if ( HIDWORD(KeyValueInformation) == 1 && v21 == 10 && v22 <= 0xA )
        {
          v15 = v23;
          v16 = 0;
          v18 = 0;
          v17 = *(__int64 *)((char *)&KeyValueInformation + v20);
          if ( !ExAllocatePool2(64, 16, 1214538315) )
            break;
          v6 = LAtoX(&v15);
          *v7 = v6;
          v8 = LAtoX(&v17);
          *(_WORD *)(v9 + 2) = v8;
          *(_QWORD *)(v9 + 8) = 0;
          if ( v4 )
            *(_QWORD *)(v4 + 8) = v9;
          else
            v3 = v9;
          v4 = v9;
        }
        ++v5;
      }
      ZwClose(KeyHandle);
    }
    ZwClose(DeviceRegKey);
  }
  v10 = KeAcquireSpinLockRaiseToDpc(a1 + 93);
  a1[92] = v3;
  KeReleaseSpinLock(a1 + 93, v10);
}

```

## disassembly

```asm
0x140004f80  mov     [rsp-8+arg_10], rbx
0x140004f85  mov     [rsp-8+arg_18], rsi
0x140004f8a  push    rbp
0x140004f8b  push    rdi
0x140004f8c  push    r15
0x140004f8e  lea     rbp, [rsp-47h]
0x140004f93  sub     rsp, 0B0h
0x140004f9a  mov     rax, cs:__security_cookie
0x140004fa1  xor     rax, rsp
0x140004fa4  mov     [rbp+57h+var_18], rax
0x140004fa8  mov     rbx, rcx
0x140004fab  lea     r9, [rbp+57h+DeviceRegKey]; DeviceRegKey
0x140004faf  mov     rcx, [rcx+10h]; DeviceObject
0x140004fb3  xor     r15d, r15d
0x140004fb6  mov     edx, 2; DevInstKeyType
0x140004fbb  mov     [rbp+57h+DeviceRegKey], r15
0x140004fbf  mov     r8d, 20019h; DesiredAccess
0x140004fc5  mov     esi, r15d
0x140004fc8  call    cs:__imp_IoOpenDeviceRegistryKey
0x140004fcf  nop     dword ptr [rax+rax+00h]
0x140004fd4  test    eax, eax
0x140004fd6  js      loc_140005113
0x140004fdc  xorps   xmm0, xmm0
0x140004fdf  mov     [rbp+57h+KeyHandle], r15
0x140004fe3  lea     rdx, SourceString; "UsageMappings"
0x140004fea  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140004fee  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140004ff2  call    cs:__imp_RtlInitUnicodeString
0x140004ff9  nop     dword ptr [rax+rax+00h]
0x140004ffe  mov     rdx, [rbp+57h+DeviceRegKey]
0x140005002  lea     r8, [rbp+57h+DestinationString]
0x140005006  lea     rcx, [rbp+57h+KeyHandle]
0x14000500a  call    OpenSubkey
0x14000500f  test    eax, eax
0x140005011  js      loc_140005103
0x140005017  mov     [rsp+0C0h+arg_8], r14
0x14000501f  mov     edi, r15d
0x140005022  mov     r14d, r15d
0x140005025  mov     [rbp+57h+var_90], r15d
0x140005029  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000502d  lea     rax, [rbp+57h+var_90]
0x140005031  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x140005036  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000503a  mov     r8d, 1; KeyValueInformationClass
0x140005040  mov     [rsp+0C0h+Length], 2Ah ; '*'; Length
0x140005048  mov     edx, r14d; Index
0x14000504b  call    cs:__imp_ZwEnumerateValueKey
0x140005052  nop     dword ptr [rax+rax+00h]
0x140005057  test    eax, eax
0x140005059  js      loc_1400050EB
0x14000505f  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 1
0x140005063  jnz     short loc_1400050E3
0x140005065  cmp     [rbp+57h+var_3C], 0Ah
0x140005069  jnz     short loc_1400050E3
0x14000506b  cmp     [rbp+57h+var_38], 0Ah
0x14000506f  ja      short loc_1400050E3
0x140005071  mov     rax, [rbp+57h+var_34]
0x140005075  mov     edx, 10h
0x14000507a  mov     [rbp+57h+var_68], rax
0x14000507e  mov     r8d, 4864624Bh
0x140005084  mov     eax, [rbp+57h+var_40]
0x140005087  mov     [rbp+57h+var_60], r15w
0x14000508c  mov     [rbp+57h+var_50], r15w
0x140005091  mov     rcx, [rbp+rax+57h+KeyValueInformation]
0x140005096  mov     [rbp+57h+var_58], rcx
0x14000509a  mov     ecx, 40h ; '@'
0x14000509f  call    cs:__imp_ExAllocatePool2
0x1400050a6  nop     dword ptr [rax+rax+00h]
0x1400050ab  mov     r10, rax
0x1400050ae  test    rax, rax
0x1400050b1  jz      short loc_1400050EB
0x1400050b3  lea     rcx, [rbp+57h+var_68]
0x1400050b7  call    LAtoX
0x1400050bc  lea     rcx, [rbp+57h+var_58]
0x1400050c0  mov     [r10], ax
0x1400050c4  call    LAtoX
0x1400050c9  mov     [r10+2], ax
0x1400050ce  mov     [r10+8], r15
0x1400050d2  test    rdi, rdi
0x1400050d5  jz      short loc_1400050DD
0x1400050d7  mov     [rdi+8], r10
0x1400050db  jmp     short loc_1400050E0
0x1400050dd  mov     rsi, r10
0x1400050e0  mov     rdi, r10
0x1400050e3  inc     r14d
0x1400050e6  jmp     loc_140005029
0x1400050eb  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400050ef  call    cs:__imp_ZwClose
0x1400050f6  nop     dword ptr [rax+rax+00h]
0x1400050fb  mov     r14, [rsp+0C0h+arg_8]
0x140005103  mov     rcx, [rbp+57h+DeviceRegKey]; Handle
0x140005107  call    cs:__imp_ZwClose
0x14000510e  nop     dword ptr [rax+rax+00h]
0x140005113  lea     rcx, [rbx+2E8h]; SpinLock
0x14000511a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005121  nop     dword ptr [rax+rax+00h]
0x140005126  lea     rcx, [rbx+2E8h]; SpinLock
0x14000512d  mov     [rbx+2E0h], rsi
0x140005134  movzx   edx, al; NewIrql
0x140005137  call    cs:__imp_KeReleaseSpinLock
0x14000513e  nop     dword ptr [rax+rax+00h]
0x140005143  mov     rcx, [rbp+57h+var_18]
0x140005147  xor     rcx, rsp; StackCookie
0x14000514a  call    __security_check_cookie
0x14000514f  lea     r11, [rsp+0C0h+var_10]
0x140005157  mov     rbx, [r11+30h]
0x14000515b  mov     rsi, [r11+38h]
0x14000515f  mov     rsp, r11
0x140005162  pop     r15
0x140005164  pop     rdi
0x140005165  pop     rbp
0x140005166  retn
```
