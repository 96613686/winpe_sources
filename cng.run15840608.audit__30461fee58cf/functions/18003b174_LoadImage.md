# _LoadImage

- ea: `0x18003b174`
- end: `0x18003b344`
- name: `_LoadImage`
- size: `464`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x18003a46c`

## callees

- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x18003b174`
- `0x18003b34c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18003b1c5`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003b1c5`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x18003b2e3`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x18003b2e3`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18003b21d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18003b21d`
- `ntoskrnl!ZwLoadDriver` at `0x18003b2ab`
- `ntoskrnl!ZwLoadDriver` at `0x18003b2ab`

## string_xrefs

- `0x18003b281`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18003b2fb`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall LoadImage(__int64 a1, __int64 a2)
{
  PCWSTR *v3; // rdx
  int v4; // ebx
  int v5; // edx
  NTSTATUS DeviceObjectPointer; // eax
  __int64 v7; // r9
  struct _UNICODE_STRING DriverServiceName; // [rsp+40h] [rbp+7h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+50h] [rbp+17h] BYREF
  UNICODE_STRING String2; // [rsp+60h] [rbp+27h] BYREF
  UNICODE_STRING String1; // [rsp+70h] [rbp+37h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp+47h] BYREF

  *(_QWORD *)&String2.Length = 1048590;
  String2.Buffer = L"cng.sys";
  v3 = *(PCWSTR **)(a1 + 48);
  *(_QWORD *)&DriverServiceName.Length = 0;
  DriverServiceName.Buffer = 0;
  *(_QWORD *)&ObjectName.Length = 0;
  ObjectName.Buffer = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, *v3);
  *(_DWORD *)(&String1.MaximumLength + 1) = 0;
  if ( DestinationString.Length >= 0xEu )
  {
    String1.Length = String2.Length;
    String1.MaximumLength = String2.Length;
    String1.Buffer = &DestinationString.Buffer[(DestinationString.Length - (unsigned __int64)String2.Length) >> 1];
    if ( (DestinationString.Length <= String2.Length
       || DestinationString.Buffer[((DestinationString.Length - (unsigned __int64)String2.Length) >> 1) - 1] == 92)
      && !RtlCompareUnicodeString(&String1, &String2, 1u) )
    {
      *(_QWORD *)a2 = 0;
      v4 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      goto LABEL_17;
    }
  }
  v4 = ResolveDriverNamesFromImage(&DestinationString, &DriverServiceName, &ObjectName);
  if ( v4 >= 0 )
  {
    DeviceObjectPointer = ZwLoadDriver(&DriverServiceName);
    v4 = DeviceObjectPointer;
    if ( DeviceObjectPointer == -1073741554 || DeviceObjectPointer == -1073741771 || DeviceObjectPointer >= 0 )
    {
      DeviceObjectPointer = IoGetDeviceObjectPointer(&ObjectName, 1u, (PFILE_OBJECT *)a2, (PDEVICE_OBJECT *)(a2 + 8));
      v4 = DeviceObjectPointer;
      if ( DeviceObjectPointer >= 0 )
        goto LABEL_17;
      v7 = 1184;
    }
    else
    {
      v7 = 1167;
    }
    DebugTraceError(
      (unsigned int)DeviceObjectPointer,
      "sResult",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
      v7);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v5 = *((_DWORD *)WPP_GLOBAL_Control + 11);
    if ( (v5 & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v5,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        (unsigned int)"sResult",
        v4,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        125);
  }
LABEL_17:
  if ( DriverServiceName.Buffer )
    MSCryptFree(DriverServiceName.Buffer);
  if ( ObjectName.Buffer )
    MSCryptFree(ObjectName.Buffer);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003b174  mov     [rsp-8+arg_0], rbx
0x18003b179  mov     [rsp-8+arg_8], rdi
0x18003b17e  push    rbp
0x18003b17f  lea     rbp, [rsp-57h]
0x18003b184  sub     rsp, 90h
0x18003b18b  lea     rax, aCngSys; "cng.sys"
0x18003b192  mov     qword ptr [rbp+57h+String2.Length], 10000Eh
0x18003b19a  mov     rdi, rdx
0x18003b19d  mov     [rbp+57h+String2.Buffer], rax
0x18003b1a1  mov     rdx, [rcx+30h]
0x18003b1a5  xor     eax, eax
0x18003b1a7  xorps   xmm0, xmm0
0x18003b1aa  mov     qword ptr [rbp+57h+DriverServiceName.Length], rax
0x18003b1ae  mov     [rbp+57h+DriverServiceName.Buffer], rax
0x18003b1b2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003b1b6  mov     qword ptr [rbp+57h+ObjectName.Length], rax
0x18003b1ba  mov     [rbp+57h+ObjectName.Buffer], rax
0x18003b1be  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003b1c2  mov     rdx, [rdx]; SourceString
0x18003b1c5  call    cs:__imp_RtlInitUnicodeString
0x18003b1cc  nop     dword ptr [rax+rax+00h]
0x18003b1d1  movzx   r9d, [rbp+57h+DestinationString.Length]
0x18003b1d6  movzx   edx, [rbp+57h+String2.Length]
0x18003b1da  mov     dword ptr [rbp+57h+String1+4], 0
0x18003b1e1  cmp     r9w, dx
0x18003b1e5  jb      short loc_18003B243
0x18003b1e7  mov     rax, [rbp+57h+DestinationString.Buffer]
0x18003b1eb  mov     ecx, r9d
0x18003b1ee  sub     rcx, rdx
0x18003b1f1  mov     [rbp+57h+String1.Length], dx
0x18003b1f5  shr     rcx, 1
0x18003b1f8  mov     [rbp+57h+String1.MaximumLength], dx
0x18003b1fc  lea     r8, [rax+rcx*2]
0x18003b200  mov     [rbp+57h+String1.Buffer], r8
0x18003b204  cmp     r9w, dx
0x18003b208  jbe     short loc_18003B212
0x18003b20a  cmp     word ptr [r8-2], 5Ch ; '\'
0x18003b210  jnz     short loc_18003B243
0x18003b212  mov     r8b, 1; CaseInSensitive
0x18003b215  lea     rdx, [rbp+57h+String2]; String2
0x18003b219  lea     rcx, [rbp+57h+String1]; String1
0x18003b21d  call    cs:__imp_RtlCompareUnicodeString
0x18003b224  nop     dword ptr [rax+rax+00h]
0x18003b229  test    eax, eax
0x18003b22b  jnz     short loc_18003B243
0x18003b22d  mov     qword ptr [rdi], 0
0x18003b234  xor     ebx, ebx
0x18003b236  mov     qword ptr [rdi+8], 0
0x18003b23e  jmp     loc_18003B310
0x18003b243  lea     r8, [rbp+57h+ObjectName]
0x18003b247  lea     rdx, [rbp+57h+DriverServiceName]
0x18003b24b  lea     rcx, [rbp+57h+DestinationString]
0x18003b24f  call    _ResolveDriverNamesFromImage
0x18003b254  mov     ebx, eax
0x18003b256  test    eax, eax
0x18003b258  jns     short loc_18003B2A7
0x18003b25a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b261  lea     rax, WPP_GLOBAL_Control
0x18003b268  cmp     rcx, rax
0x18003b26b  jz      loc_18003B310
0x18003b271  mov     edx, [rcx+2Ch]
0x18003b274  test    dl, 1
0x18003b277  jz      loc_18003B310
0x18003b27d  mov     rcx, [rcx+18h]
0x18003b281  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b288  mov     [rsp+90h+var_60], 47Dh
0x18003b290  lea     r9, aSresult; "sResult"
0x18003b297  mov     [rsp+90h+var_68], r8
0x18003b29c  mov     [rsp+90h+var_70], ebx
0x18003b2a0  call    WPP_SF_sDsd
0x18003b2a5  jmp     short loc_18003B310
0x18003b2a7  lea     rcx, [rbp+57h+DriverServiceName]; DriverServiceName
0x18003b2ab  call    cs:__imp_ZwLoadDriver
0x18003b2b2  nop     dword ptr [rax+rax+00h]
0x18003b2b7  mov     ebx, eax
0x18003b2b9  cmp     eax, 0C000010Eh
0x18003b2be  jz      short loc_18003B2D3
0x18003b2c0  cmp     eax, 0C0000035h
0x18003b2c5  jz      short loc_18003B2D3
0x18003b2c7  test    eax, eax
0x18003b2c9  jns     short loc_18003B2D3
0x18003b2cb  mov     r9d, 48Fh
0x18003b2d1  jmp     short loc_18003B2FB
0x18003b2d3  lea     r9, [rdi+8]; DeviceObject
0x18003b2d7  mov     r8, rdi; FileObject
0x18003b2da  mov     edx, 1; DesiredAccess
0x18003b2df  lea     rcx, [rbp+57h+ObjectName]; ObjectName
0x18003b2e3  call    cs:__imp_IoGetDeviceObjectPointer
0x18003b2ea  nop     dword ptr [rax+rax+00h]
0x18003b2ef  mov     ebx, eax
0x18003b2f1  test    eax, eax
0x18003b2f3  jns     short loc_18003B310
0x18003b2f5  mov     r9d, 4A0h
0x18003b2fb  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003b302  mov     ecx, eax
0x18003b304  lea     rdx, aSresult; "sResult"
0x18003b30b  call    DebugTraceError
0x18003b310  mov     rcx, [rbp+57h+DriverServiceName.Buffer]; P
0x18003b314  test    rcx, rcx
0x18003b317  jz      short loc_18003B31E
0x18003b319  call    MSCryptFree
0x18003b31e  mov     rcx, [rbp+57h+ObjectName.Buffer]; P
0x18003b322  test    rcx, rcx
0x18003b325  jz      short loc_18003B32C
0x18003b327  call    MSCryptFree
0x18003b32c  lea     r11, [rsp+90h+var_s0]
0x18003b334  mov     eax, ebx
0x18003b336  mov     rbx, [r11+10h]
0x18003b33a  mov     rdi, [r11+18h]
0x18003b33e  mov     rsp, r11
0x18003b341  pop     rbp
0x18003b342  retn
```
