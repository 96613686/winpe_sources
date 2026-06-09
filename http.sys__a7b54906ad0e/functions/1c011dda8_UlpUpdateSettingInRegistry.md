# UlpUpdateSettingInRegistry

- ea: `0x1c011dda8`
- end: `0x1c011defd`
- name: `UlpUpdateSettingInRegistry`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1c011c81c`

## callees

- `0x1c008f374`
- `0x1c0097c28`
- `0x1c011dda8`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1c011de3f`
- `ntoskrnl!ZwOpenKey` at `0x1c011de3f`
- `ntoskrnl!ZwDeleteValueKey` at `0x1c011de7d`
- `ntoskrnl!ZwDeleteValueKey` at `0x1c011de7d`
- `ntoskrnl!ZwSetValueKey` at `0x1c011dea2`
- `ntoskrnl!ZwSetValueKey` at `0x1c011dea2`
- `ntoskrnl!ZwClose` at `0x1c011deb9`
- `ntoskrnl!ZwClose` at `0x1c011deb9`

## string_xrefs

- `0x1c011ddf4`: `\Registry\Machine\System\CurrentControlSet\Services\Http\Parameters`

## pseudocode

```c
__int64 __fastcall UlpUpdateSettingInRegistry(__int64 a1, __int64 a2)
{
  char v2; // di
  NTSTATUS v3; // ebx
  NTSTATUS v4; // eax
  __int128 v6; // [rsp+38h] [rbp-9h]
  struct _UNICODE_STRING v7; // [rsp+38h] [rbp-9h]
  struct _UNICODE_STRING ValueName; // [rsp+48h] [rbp+7h] BYREF
  __int128 v9; // [rsp+58h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp+27h] BYREF
  int Data; // [rsp+A8h] [rbp+67h] BYREF
  void *KeyHandle; // [rsp+B8h] [rbp+77h] BYREF

  Data = a1;
  KeyHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  ValueName = 0;
  v2 = a2;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_Ll(a1, a2, (unsigned int)a1, (unsigned __int8)a2);
  ObjectAttributes.RootDirectory = 0;
  *((_QWORD *)&v6 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Http\\Parameters";
  *(_QWORD *)&v6 = 8781958;
  v9 = v6;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v9;
  v3 = ZwOpenKey(&KeyHandle, 0x2001Fu, &ObjectAttributes);
  if ( v3 >= 0 )
  {
    v7.Buffer = L"AscThrottleLimit";
    *(_QWORD *)&v7.Length = 2097184;
    ValueName = v7;
    if ( v2 )
      v4 = ZwDeleteValueKey(KeyHandle, &ValueName);
    else
      v4 = ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
    v3 = v4;
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_D(116, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1c011dda8  mov     rax, rsp
0x1c011ddab  mov     [rax+10h], rbx
0x1c011ddaf  mov     [rax+20h], rdi
0x1c011ddb3  mov     [rax+8], ecx
0x1c011ddb6  push    rbp
0x1c011ddb7  lea     rbp, [rax-5Fh]
0x1c011ddbb  sub     rsp, 90h
0x1c011ddc2  and     [rbp+57h+KeyHandle], 0
0x1c011ddc7  xorps   xmm0, xmm0
0x1c011ddca  and     dword ptr [rbp+57h+ObjectAttributes+4], 0
0x1c011ddce  and     dword ptr [rbp+57h+ObjectAttributes+1Ch], 0
0x1c011ddd2  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x1c011ddd6  movzx   edi, dl
0x1c011ddd9  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c011dde3  jz      short loc_1C011DDF0
0x1c011dde5  mov     r9d, edi
0x1c011dde8  mov     r8d, ecx
0x1c011ddeb  call    WPP_SF_Ll
0x1c011ddf0  and     dword ptr [rbp+57h+var_60+4], 0
0x1c011ddf4  lea     rax, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x1c011ddfb  and     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1c011de00  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1c011de04  mov     qword ptr [rbp+57h+var_60+8], rax
0x1c011de08  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1c011de0c  lea     rax, [rbp+57h+var_40]
0x1c011de10  mov     dword ptr [rbp+57h+var_60], 860086h
0x1c011de17  movaps  xmm0, [rbp+57h+var_60]
0x1c011de1b  mov     edx, 2001Fh; DesiredAccess
0x1c011de20  movdqa  [rbp+57h+var_40], xmm0
0x1c011de25  xorps   xmm0, xmm0
0x1c011de28  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1c011de2d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1c011de34  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1c011de3b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1c011de3f  call    cs:__imp_ZwOpenKey
0x1c011de46  nop     dword ptr [rax+rax+00h]
0x1c011de4b  mov     ebx, eax
0x1c011de4d  test    eax, eax
0x1c011de4f  js      short loc_1C011DEB0
0x1c011de51  and     dword ptr [rbp+57h+var_60+4], 0
0x1c011de55  lea     rax, aAscthrottlelim; "AscThrottleLimit"
0x1c011de5c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1c011de60  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1c011de64  mov     qword ptr [rbp+57h+var_60+8], rax
0x1c011de68  mov     dword ptr [rbp+57h+var_60], 200020h
0x1c011de6f  movaps  xmm0, [rbp+57h+var_60]
0x1c011de73  movdqa  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x1c011de78  test    dil, dil
0x1c011de7b  jz      short loc_1C011DE8B
0x1c011de7d  call    cs:__imp_ZwDeleteValueKey
0x1c011de84  nop     dword ptr [rax+rax+00h]
0x1c011de89  jmp     short loc_1C011DEAE
0x1c011de8b  mov     r9d, 4; Type
0x1c011de91  lea     rax, [rbp+57h+arg_0]
0x1c011de95  mov     [rsp+90h+DataSize], r9d; DataSize
0x1c011de9a  xor     r8d, r8d; TitleIndex
0x1c011de9d  mov     [rsp+90h+Data], rax; Data
0x1c011dea2  call    cs:__imp_ZwSetValueKey
0x1c011dea9  nop     dword ptr [rax+rax+00h]
0x1c011deae  mov     ebx, eax
0x1c011deb0  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1c011deb4  test    rcx, rcx
0x1c011deb7  jz      short loc_1C011DEC5
0x1c011deb9  call    cs:__imp_ZwClose
0x1c011dec0  nop     dword ptr [rax+rax+00h]
0x1c011dec5  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c011decf  jz      short loc_1C011DEE5
0x1c011ded1  mov     ecx, 74h ; 't'
0x1c011ded6  lea     rdx, WPP_18ca8755388c316524f95a91261e2540_Traceguids
0x1c011dedd  mov     r8d, ebx
0x1c011dee0  call    WPP_SF_D
0x1c011dee5  lea     r11, [rsp+90h+var_s0]
0x1c011deed  mov     eax, ebx
0x1c011deef  mov     rbx, [r11+18h]
0x1c011def3  mov     rdi, [r11+28h]
0x1c011def7  mov     rsp, r11
0x1c011defa  pop     rbp
0x1c011defb  retn
```
