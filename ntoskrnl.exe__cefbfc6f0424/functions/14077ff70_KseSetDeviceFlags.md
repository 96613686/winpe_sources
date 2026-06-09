# KseSetDeviceFlags

- ea: `0x14077ff70`
- end: `0x1407800b7`
- name: `KseSetDeviceFlags`
- size: `327`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140403380`
- `0x1406ddfe0`
- `0x14077ff70`
- `0x1407823b0`
- `0x1408befb0`
- `0x1408bff4c`
- `0x1408c0630`

## string_xrefs

- `0x14078000c`: `\Registry\Machine\System\CurrentControlSet\Control\Compatibility`
- `0x14077ffec`: `\Registry\Machine\System\CurrentControlSet\Control\Compatibility\Device`
- `0x14078002f`: `\Registry\Machine\System\CurrentControlSet\Control\Compatibility\Device`

## pseudocode

```c
__int64 __fastcall KseSetDeviceFlags(__int64 a1, const WCHAR *a2, __int64 a3)
{
  HANDLE v3; // rdi
  NTSTATUS v5; // ebx
  __int64 v7; // [rsp+30h] [rbp-20h] BYREF
  __int64 v8; // [rsp+38h] [rbp-18h]
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  __int64 Data; // [rsp+80h] [rbp+30h] BYREF
  HANDLE KeyHandle; // [rsp+88h] [rbp+38h] BYREF

  Data = a3;
  v3 = 0;
  v7 = 0;
  v8 = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  KeyHandle = 0;
  if ( dword_140E4CE94 != 2 || (KseEngine & 2) != 0 )
  {
    v5 = -1073741823;
  }
  else
  {
    if ( a1 && a2 )
    {
      v5 = KsepStringTransform(&v7, a1);
      if ( v5 < 0 )
        goto LABEL_14;
      v5 = KsepRegistryCreateKey(
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Compatibility\\Device",
             v8,
             &KeyHandle);
      if ( v5 == -1073741772 )
      {
        v5 = KsepRegistryCreateKey(
               L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Compatibility",
               L"Device",
               &KeyHandle);
        if ( v5 < 0 )
        {
LABEL_11:
          v3 = KeyHandle;
          goto LABEL_14;
        }
        KsepRegistryCloseKey(KeyHandle);
        KeyHandle = 0;
        v5 = KsepRegistryCreateKey(
               L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Compatibility\\Device",
               v8,
               &KeyHandle);
      }
      if ( v5 >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, a2);
        v3 = KeyHandle;
        v5 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 0xBu, &Data, 8u);
        goto LABEL_14;
      }
      goto LABEL_11;
    }
    v5 = -1073741811;
  }
LABEL_14:
  KsepStringFree(&v7);
  if ( v3 )
    KsepRegistryCloseKey(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14077ff70  mov     [rsp-18h+arg_0], rbx
0x14077ff75  mov     [rsp-18h+arg_10], r8
0x14077ff7a  push    rbp
0x14077ff7b  push    rsi
0x14077ff7c  push    rdi
0x14077ff7d  mov     rbp, rsp
0x14077ff80  sub     rsp, 50h
0x14077ff84  xor     eax, eax
0x14077ff86  xor     edi, edi
0x14077ff88  mov     [rbp+var_20], rax
0x14077ff8c  mov     rsi, rdx
0x14077ff8f  mov     [rbp+var_18], rax
0x14077ff93  mov     qword ptr [rbp+DestinationString.Length], rax
0x14077ff97  mov     [rbp+DestinationString.Buffer], rax
0x14077ff9b  mov     eax, cs:dword_140E4CE94
0x14077ffa1  mov     [rbp+KeyHandle], rdi
0x14077ffa5  cmp     eax, 2
0x14077ffa8  jnz     loc_14078008C
0x14077ffae  mov     eax, cs:KseEngine
0x14077ffb4  test    al, 2
0x14077ffb6  jnz     loc_14078008C
0x14077ffbc  test    rcx, rcx
0x14077ffbf  jz      loc_140780085
0x14077ffc5  test    rdx, rdx
0x14077ffc8  jz      loc_140780085
0x14077ffce  mov     rdx, rcx
0x14077ffd1  lea     rcx, [rbp+var_20]
0x14077ffd5  call    KsepStringTransform
0x14077ffda  mov     ebx, eax
0x14077ffdc  test    eax, eax
0x14077ffde  js      loc_140780091
0x14077ffe4  mov     rdx, [rbp+var_18]
0x14077ffe8  lea     r8, [rbp+KeyHandle]
0x14077ffec  lea     rcx, aRegistryMachin_149; "\\Registry\\Machine\\System\\CurrentCon"...
0x14077fff3  call    KsepRegistryCreateKey
0x14077fff8  mov     ebx, eax
0x14077fffa  cmp     eax, 0C0000034h
0x14077ffff  jnz     short loc_140780041
0x140780001  lea     r8, [rbp+KeyHandle]
0x140780005  lea     rdx, aDevice; "Device"
0x14078000c  lea     rcx, aRegistryMachin_210; "\\Registry\\Machine\\System\\CurrentCon"...
0x140780013  call    KsepRegistryCreateKey
0x140780018  mov     ebx, eax
0x14078001a  test    eax, eax
0x14078001c  js      short loc_14078007F
0x14078001e  mov     rcx, [rbp+KeyHandle]
0x140780022  call    KsepRegistryCloseKey
0x140780027  mov     rdx, [rbp+var_18]
0x14078002b  lea     r8, [rbp+KeyHandle]
0x14078002f  lea     rcx, aRegistryMachin_149; "\\Registry\\Machine\\System\\CurrentCon"...
0x140780036  mov     [rbp+KeyHandle], rdi
0x14078003a  call    KsepRegistryCreateKey
0x14078003f  mov     ebx, eax
0x140780041  test    ebx, ebx
0x140780043  js      short loc_14078007F
0x140780045  mov     rdx, rsi; SourceString
0x140780048  lea     rcx, [rbp+DestinationString]; DestinationString
0x14078004c  call    RtlInitUnicodeString
0x140780051  mov     rdi, [rbp+KeyHandle]
0x140780055  lea     rax, [rbp+arg_10]
0x140780059  mov     rcx, rdi; KeyHandle
0x14078005c  mov     [rsp+50h+DataSize], 8; DataSize
0x140780064  mov     r9d, 0Bh; Type
0x14078006a  mov     [rsp+50h+Data], rax; Data
0x14078006f  xor     r8d, r8d; TitleIndex
0x140780072  lea     rdx, [rbp+DestinationString]; ValueName
0x140780076  call    ZwSetValueKey
0x14078007b  mov     ebx, eax
0x14078007d  jmp     short loc_140780091
0x14078007f  mov     rdi, [rbp+KeyHandle]
0x140780083  jmp     short loc_140780091
0x140780085  mov     ebx, 0C000000Dh
0x14078008a  jmp     short loc_140780091
0x14078008c  mov     ebx, 0C0000001h
0x140780091  lea     rcx, [rbp+var_20]
0x140780095  call    KsepStringFree
0x14078009a  test    rdi, rdi
0x14078009d  jz      short loc_1407800A7
0x14078009f  mov     rcx, rdi
0x1407800a2  call    KsepRegistryCloseKey
0x1407800a7  mov     eax, ebx
0x1407800a9  mov     rbx, [rsp+50h+arg_0]
0x1407800ae  add     rsp, 50h
0x1407800b2  pop     rdi
0x1407800b3  pop     rsi
0x1407800b4  pop     rbp
0x1407800b5  retn
```
