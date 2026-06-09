# EapStoreAggregatedEventTrigger

- ea: `0x18000aec4`
- end: `0x18000afc7`
- name: `EapStoreAggregatedEventTrigger`
- size: `259`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, GUID *Guid)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800095e0`

## callees

- `0x1800072e0`
- `0x18000982c`
- `0x180009848`
- `0x18000ab18`
- `0x18000aec4`
- `0x18000afd0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18000af96`
- `ntdll!RtlFreeUnicodeString` at `0x18000af96`
- `ntdll!RtlInitUnicodeString` at `0x18000af01`
- `ntdll!RtlInitUnicodeString` at `0x18000af01`
- `ntdll!RtlStringFromGUID` at `0x18000af55`
- `ntdll!RtlStringFromGUID` at `0x18000af55`
- `RPCRT4!UuidCreate` at `0x18000af11`
- `RPCRT4!UuidCreate` at `0x18000af11`

## pseudocode

```c
__int64 __fastcall EapStoreAggregatedEventTrigger(HANDLE KeyHandle, GUID *Guid)
{
  HANDLE v4; // rdi
  NTSTATUS v5; // ebx
  int v6; // eax
  HANDLE KeyHandlea; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+48h] [rbp-18h] BYREF

  DestinationString = 0;
  Uuid = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v4 = 0;
  KeyHandlea = 0;
  if ( UuidCreate(&Uuid) )
  {
    v5 = -1073741595;
  }
  else
  {
    v6 = EapCreateAggregatedEventNode(KeyHandle, &Uuid, &KeyHandlea);
    v4 = KeyHandlea;
    v5 = v6;
    if ( v6 >= 0 )
    {
      v5 = EapStoreSimpleEventParameters(KeyHandlea, Guid);
      if ( v5 >= 0 )
      {
        v5 = RtlStringFromGUID(&Uuid, &DestinationString);
        if ( v5 >= 0 )
        {
          v5 = EapSetValue(KeyHandle, DestinationString.Length);
          if ( v5 >= 0 )
            v5 = 0;
        }
      }
    }
  }
  if ( DestinationString.Buffer )
    RtlFreeUnicodeString(&DestinationString);
  EapCloseAggregatedEventNode(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000aec4  mov     [rsp-18h+arg_10], rbx
0x18000aec9  mov     [rsp-18h+arg_18], rsi
0x18000aece  push    rbp
0x18000aecf  push    rdi
0x18000aed0  push    r14
0x18000aed2  mov     rbp, rsp
0x18000aed5  sub     rsp, 60h
0x18000aed9  mov     rax, cs:__security_cookie
0x18000aee0  xor     rax, rsp
0x18000aee3  mov     [rbp+var_8], rax
0x18000aee7  mov     r14, rdx
0x18000aeea  mov     rsi, rcx
0x18000aeed  xorps   xmm0, xmm0
0x18000aef0  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000aef4  xorps   xmm1, xmm1
0x18000aef7  xor     edx, edx; SourceString
0x18000aef9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000aefd  movups  xmmword ptr [rbp+Uuid.Data1], xmm1
0x18000af01  call    cs:__imp_RtlInitUnicodeString
0x18000af07  xor     edi, edi
0x18000af09  lea     rcx, [rbp+Uuid]; Uuid
0x18000af0d  mov     [rbp+KeyHandle], rdi
0x18000af11  call    cs:__imp_UuidCreate
0x18000af17  test    eax, eax
0x18000af19  jz      short loc_18000AF22
0x18000af1b  mov     ebx, 0C00000E5h
0x18000af20  jmp     short loc_18000AF8B
0x18000af22  lea     r8, [rbp+KeyHandle]
0x18000af26  mov     rcx, rsi
0x18000af29  lea     rdx, [rbp+Uuid]
0x18000af2d  call    EapCreateAggregatedEventNode
0x18000af32  mov     rdi, [rbp+KeyHandle]
0x18000af36  mov     ebx, eax
0x18000af38  test    eax, eax
0x18000af3a  js      short loc_18000AF8B
0x18000af3c  mov     rdx, r14; Guid
0x18000af3f  mov     rcx, rdi; KeyHandle
0x18000af42  call    EapStoreSimpleEventParameters
0x18000af47  mov     ebx, eax
0x18000af49  test    eax, eax
0x18000af4b  js      short loc_18000AF8B
0x18000af4d  lea     rdx, [rbp+DestinationString]; GuidString
0x18000af51  lea     rcx, [rbp+Uuid]; Guid
0x18000af55  call    cs:__imp_RtlStringFromGUID
0x18000af5b  mov     ebx, eax
0x18000af5d  test    eax, eax
0x18000af5f  js      short loc_18000AF8B
0x18000af61  movzx   eax, [rbp+DestinationString.Length]
0x18000af65  lea     rdx, EA_STORE_AGGRERATED_EVENT_FIELD_TRIGGER; "Trigger"
0x18000af6c  mov     r9, [rbp+DestinationString.Buffer]
0x18000af70  mov     r8d, 1
0x18000af76  mov     rcx, rsi; KeyHandle
0x18000af79  mov     [rsp+60h+var_40], eax; ULONG
0x18000af7d  call    EapSetValue
0x18000af82  mov     ebx, eax
0x18000af84  xor     eax, eax
0x18000af86  test    ebx, ebx
0x18000af88  cmovns  ebx, eax
0x18000af8b  cmp     [rbp+DestinationString.Buffer], 0
0x18000af90  jz      short loc_18000AF9C
0x18000af92  lea     rcx, [rbp+DestinationString]; UnicodeString
0x18000af96  call    cs:__imp_RtlFreeUnicodeString
0x18000af9c  mov     rcx, rdi
0x18000af9f  call    EapCloseAggregatedEventNode
0x18000afa4  mov     eax, ebx
0x18000afa6  mov     rcx, [rbp+var_8]
0x18000afaa  xor     rcx, rsp; StackCookie
0x18000afad  call    __security_check_cookie
0x18000afb2  lea     r11, [rsp+60h+var_s0]
0x18000afb7  mov     rbx, [r11+30h]
0x18000afbb  mov     rsi, [r11+38h]
0x18000afbf  mov     rsp, r11
0x18000afc2  pop     r14
0x18000afc4  pop     rdi
0x18000afc5  pop     rbp
0x18000afc6  retn
```
