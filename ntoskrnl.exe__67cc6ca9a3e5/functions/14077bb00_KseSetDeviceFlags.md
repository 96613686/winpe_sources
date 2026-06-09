# KseSetDeviceFlags

- ea: `0x14077bb00`
- end: `0x14077bc47`
- name: `KseSetDeviceFlags`
- size: `327`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1403f2d50`
- `0x1406db490`
- `0x14077bb00`
- `0x14077df40`
- `0x1409791e8`
- `0x14097a118`
- `0x14097a800`

## string_xrefs

- `0x14077bb9c`: `\Registry\Machine\System\CurrentControlSet\Control\Compatibility`
- `0x14077bb7c`: `\Registry\Machine\System\CurrentControlSet\Control\Compatibility\Device`
- `0x14077bbbf`: `\Registry\Machine\System\CurrentControlSet\Control\Compatibility\Device`

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
  if ( dword_140E4CF04 != 2 || (KseEngine & 2) != 0 )
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
0x14077bb00  mov     [rsp-18h+arg_0], rbx
0x14077bb05  mov     [rsp-18h+arg_10], r8
0x14077bb0a  push    rbp
0x14077bb0b  push    rsi
0x14077bb0c  push    rdi
0x14077bb0d  mov     rbp, rsp
0x14077bb10  sub     rsp, 50h
0x14077bb14  xor     eax, eax
0x14077bb16  xor     edi, edi
0x14077bb18  mov     [rbp+var_20], rax
0x14077bb1c  mov     rsi, rdx
0x14077bb1f  mov     [rbp+var_18], rax
0x14077bb23  mov     qword ptr [rbp+DestinationString.Length], rax
0x14077bb27  mov     [rbp+DestinationString.Buffer], rax
0x14077bb2b  mov     eax, cs:dword_140E4CF04
0x14077bb31  mov     [rbp+KeyHandle], rdi
0x14077bb35  cmp     eax, 2
0x14077bb38  jnz     loc_14077BC1C
0x14077bb3e  mov     eax, cs:KseEngine
0x14077bb44  test    al, 2
0x14077bb46  jnz     loc_14077BC1C
0x14077bb4c  test    rcx, rcx
0x14077bb4f  jz      loc_14077BC15
0x14077bb55  test    rdx, rdx
0x14077bb58  jz      loc_14077BC15
0x14077bb5e  mov     rdx, rcx
0x14077bb61  lea     rcx, [rbp+var_20]
0x14077bb65  call    KsepStringTransform
0x14077bb6a  mov     ebx, eax
0x14077bb6c  test    eax, eax
0x14077bb6e  js      loc_14077BC21
0x14077bb74  mov     rdx, [rbp+var_18]
0x14077bb78  lea     r8, [rbp+KeyHandle]
0x14077bb7c  lea     rcx, aRegistryMachin_149; "\\Registry\\Machine\\System\\CurrentCon"...
0x14077bb83  call    KsepRegistryCreateKey
0x14077bb88  mov     ebx, eax
0x14077bb8a  cmp     eax, 0C0000034h
0x14077bb8f  jnz     short loc_14077BBD1
0x14077bb91  lea     r8, [rbp+KeyHandle]
0x14077bb95  lea     rdx, aDevice; "Device"
0x14077bb9c  lea     rcx, aRegistryMachin_210; "\\Registry\\Machine\\System\\CurrentCon"...
0x14077bba3  call    KsepRegistryCreateKey
0x14077bba8  mov     ebx, eax
0x14077bbaa  test    eax, eax
0x14077bbac  js      short loc_14077BC0F
0x14077bbae  mov     rcx, [rbp+KeyHandle]
0x14077bbb2  call    KsepRegistryCloseKey
0x14077bbb7  mov     rdx, [rbp+var_18]
0x14077bbbb  lea     r8, [rbp+KeyHandle]
0x14077bbbf  lea     rcx, aRegistryMachin_149; "\\Registry\\Machine\\System\\CurrentCon"...
0x14077bbc6  mov     [rbp+KeyHandle], rdi
0x14077bbca  call    KsepRegistryCreateKey
0x14077bbcf  mov     ebx, eax
0x14077bbd1  test    ebx, ebx
0x14077bbd3  js      short loc_14077BC0F
0x14077bbd5  mov     rdx, rsi; SourceString
0x14077bbd8  lea     rcx, [rbp+DestinationString]; DestinationString
0x14077bbdc  call    RtlInitUnicodeString
0x14077bbe1  mov     rdi, [rbp+KeyHandle]
0x14077bbe5  lea     rax, [rbp+arg_10]
0x14077bbe9  mov     rcx, rdi; KeyHandle
0x14077bbec  mov     [rsp+50h+DataSize], 8; DataSize
0x14077bbf4  mov     r9d, 0Bh; Type
0x14077bbfa  mov     [rsp+50h+Data], rax; Data
0x14077bbff  xor     r8d, r8d; TitleIndex
0x14077bc02  lea     rdx, [rbp+DestinationString]; ValueName
0x14077bc06  call    ZwSetValueKey
0x14077bc0b  mov     ebx, eax
0x14077bc0d  jmp     short loc_14077BC21
0x14077bc0f  mov     rdi, [rbp+KeyHandle]
0x14077bc13  jmp     short loc_14077BC21
0x14077bc15  mov     ebx, 0C000000Dh
0x14077bc1a  jmp     short loc_14077BC21
0x14077bc1c  mov     ebx, 0C0000001h
0x14077bc21  lea     rcx, [rbp+var_20]
0x14077bc25  call    KsepStringFree
0x14077bc2a  test    rdi, rdi
0x14077bc2d  jz      short loc_14077BC37
0x14077bc2f  mov     rcx, rdi
0x14077bc32  call    KsepRegistryCloseKey
0x14077bc37  mov     eax, ebx
0x14077bc39  mov     rbx, [rsp+50h+arg_0]
0x14077bc3e  add     rsp, 50h
0x14077bc42  pop     rdi
0x14077bc43  pop     rsi
0x14077bc44  pop     rbp
0x14077bc45  retn
```
