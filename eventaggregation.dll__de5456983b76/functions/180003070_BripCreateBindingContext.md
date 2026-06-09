# BripCreateBindingContext

- ea: `0x180003070`
- end: `0x18000323e`
- name: `BripCreateBindingContext`
- size: `462`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001c80`
- `0x1800026f0`
- `0x1800089c0`
- `0x180008af0`

## callees

- `0x180002e30`
- `0x180003070`
- `0x180003250`
- `0x180003600`
- `0x180006e20`
- `0x180008ed0`

## import_xrefs

- `ntdll!ZwClose` at `0x1800031de`
- `ntdll!ZwClose` at `0x1800031ed`
- `ntdll!ZwClose` at `0x1800031de`
- `ntdll!ZwClose` at `0x1800031ed`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800030dd`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800030dd`
- `ntdll!RtlInsertEntryHashTable` at `0x1800031c2`
- `ntdll!RtlInsertEntryHashTable` at `0x1800031c2`
- `ntdll!RtlStringFromGUID` at `0x1800030c2`
- `ntdll!RtlStringFromGUID` at `0x1800030c2`
- `ntdll!ZwOpenKey` at `0x18000311c`
- `ntdll!ZwOpenKey` at `0x18000315f`
- `ntdll!ZwOpenKey` at `0x18000311c`
- `ntdll!ZwOpenKey` at `0x18000315f`

## string_xrefs

- `0x1800030d2`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\BackgroundModel\Brokers`

## pseudocode

```c
__int64 __fastcall BripCreateBindingContext(const GUID *a1)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  int inited; // ebx
  __int64 BindingContext; // rax
  unsigned int v6; // eax
  void *KeyHandle; // [rsp+20h] [rbp-60h] BYREF
  _UNICODE_STRING GuidString; // [rsp+28h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-48h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-38h] BYREF
  int v12; // [rsp+B8h] [rbp+38h] BYREF
  __int64 v13; // [rsp+C0h] [rbp+40h] BYREF
  HANDLE Handle; // [rsp+C8h] [rbp+48h] BYREF

  Handle = 0;
  KeyHandle = 0;
  v13 = 0;
  v12 = 0;
  memset(&ObjectAttributes, 0, 44);
  v2 = 0;
  v3 = 0;
  GuidString = 0;
  DestinationString = 0;
  inited = RtlStringFromGUID(a1, &GuidString);
  if ( inited >= 0 )
  {
    inited = RtlInitUnicodeStringEx(
               &DestinationString,
               L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\BackgroundModel\\Brokers");
    if ( inited >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      inited = ZwOpenKey(&KeyHandle, 0x101u, &ObjectAttributes);
      if ( inited >= 0 )
      {
        ObjectAttributes.RootDirectory = KeyHandle;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &GuidString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        inited = ZwOpenKey(&Handle, 0x101u, &ObjectAttributes);
        if ( inited >= 0 )
        {
          BindingContext = BripAllocateBindingContext(a1);
          v2 = BindingContext;
          if ( BindingContext )
          {
            *(GUID *)(BindingContext + 24) = *a1;
            inited = BripQueryBindingContextProperties(Handle, (_QWORD *)BindingContext, (__int64)&v13, (__int64)&v12);
            if ( inited >= 0 )
            {
              v6 = BripComputeHash((PUCHAR)(v2 + 24), 0x10u);
              if ( !(unsigned __int8)RtlInsertEntryHashTable(BrokerBindingTable, v2, v6, 0) )
                inited = -1073741670;
            }
            v3 = v13;
          }
          else
          {
            inited = -1073741801;
          }
        }
      }
    }
  }
  if ( Handle )
    ZwClose(Handle);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( GuidString.Buffer )
    EaLibFree(GuidString.Buffer);
  if ( v3 )
    EaLibFree(v3);
  if ( inited >= 0 || !v2 )
    return v2;
  BripFreeBindingContext(v2);
  return 0;
}

```

## disassembly

```asm
0x180003070  mov     [rsp-28h+arg_0], rbx
0x180003075  push    rbp
0x180003076  push    rsi
0x180003077  push    rdi
0x180003078  push    r14
0x18000307a  push    r15
0x18000307c  mov     rbp, rsp
0x18000307f  sub     rsp, 80h
0x180003086  xor     r15d, r15d
0x180003089  lea     rdx, [rbp+GuidString]; GuidString
0x18000308d  xorps   xmm0, xmm0
0x180003090  mov     [rbp+Handle], r15
0x180003094  xorps   xmm1, xmm1
0x180003097  mov     [rbp+KeyHandle], r15
0x18000309b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000309f  xor     eax, eax
0x1800030a1  mov     [rbp+arg_10], r15
0x1800030a5  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800030a9  mov     r14, rcx
0x1800030ac  mov     [rbp+arg_8], r15d
0x1800030b0  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800030b4  mov     edi, r15d
0x1800030b7  mov     esi, r15d
0x1800030ba  movups  xmmword ptr [rbp+GuidString.Length], xmm0
0x1800030be  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x1800030c2  call    cs:__imp_RtlStringFromGUID
0x1800030c8  mov     ebx, eax
0x1800030ca  test    eax, eax
0x1800030cc  js      loc_1800031D5
0x1800030d2  lea     rdx, SourceString; "\\Registry\\Machine\\Software\\Microsof"...
0x1800030d9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800030dd  call    cs:__imp_RtlInitUnicodeStringEx
0x1800030e3  mov     ebx, eax
0x1800030e5  test    eax, eax
0x1800030e7  js      loc_1800031D5
0x1800030ed  lea     rax, [rbp+DestinationString]
0x1800030f1  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800030f8  xorps   xmm0, xmm0
0x1800030fb  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800030ff  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180003103  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x180003107  mov     edx, 101h; DesiredAccess
0x18000310c  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180003113  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180003117  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000311c  call    cs:__imp_ZwOpenKey
0x180003122  mov     ebx, eax
0x180003124  test    eax, eax
0x180003126  js      loc_1800031D5
0x18000312c  mov     rax, [rbp+KeyHandle]
0x180003130  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180003134  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180003138  lea     rcx, [rbp+Handle]; KeyHandle
0x18000313c  lea     rax, [rbp+GuidString]
0x180003140  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180003147  xorps   xmm0, xmm0
0x18000314a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000314e  mov     edx, 101h; DesiredAccess
0x180003153  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18000315a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000315f  call    cs:__imp_ZwOpenKey
0x180003165  mov     ebx, eax
0x180003167  test    eax, eax
0x180003169  js      short loc_1800031D5
0x18000316b  mov     rcx, r14
0x18000316e  call    BripAllocateBindingContext
0x180003173  mov     rdi, rax
0x180003176  test    rax, rax
0x180003179  jnz     short loc_180003182
0x18000317b  mov     ebx, 0C0000017h
0x180003180  jmp     short loc_1800031D5
0x180003182  movups  xmm0, xmmword ptr [r14]
0x180003186  lea     r9, [rbp+arg_8]
0x18000318a  mov     rdx, rdi
0x18000318d  lea     r8, [rbp+arg_10]
0x180003191  movups  xmmword ptr [rax+18h], xmm0
0x180003195  mov     rcx, [rbp+Handle]; KeyHandle
0x180003199  call    BripQueryBindingContextProperties
0x18000319e  mov     ebx, eax
0x1800031a0  test    eax, eax
0x1800031a2  js      short loc_1800031D1
0x1800031a4  mov     edx, 10h; Length
0x1800031a9  lea     rcx, [rdi+18h]; Buffer
0x1800031ad  call    BripComputeHash
0x1800031b2  mov     rcx, cs:BrokerBindingTable
0x1800031b9  xor     r9d, r9d
0x1800031bc  mov     r8d, eax
0x1800031bf  mov     rdx, rdi
0x1800031c2  call    cs:__imp_RtlInsertEntryHashTable
0x1800031c8  test    al, al
0x1800031ca  jnz     short loc_1800031D1
0x1800031cc  mov     ebx, 0C000009Ah
0x1800031d1  mov     rsi, [rbp+arg_10]
0x1800031d5  mov     rcx, [rbp+Handle]; Handle
0x1800031d9  test    rcx, rcx
0x1800031dc  jz      short loc_1800031E4
0x1800031de  call    cs:__imp_ZwClose
0x1800031e4  mov     rcx, [rbp+KeyHandle]; Handle
0x1800031e8  test    rcx, rcx
0x1800031eb  jz      short loc_1800031F3
0x1800031ed  call    cs:__imp_ZwClose
0x1800031f3  mov     rcx, [rbp+GuidString.Buffer]
0x1800031f7  test    rcx, rcx
0x1800031fa  jz      short loc_180003201
0x1800031fc  call    EaLibFree
0x180003201  test    rsi, rsi
0x180003204  jz      short loc_18000320E
0x180003206  mov     rcx, rsi
0x180003209  call    EaLibFree
0x18000320e  test    ebx, ebx
0x180003210  jns     short loc_180003224
0x180003212  test    rdi, rdi
0x180003215  jz      short loc_180003224
0x180003217  mov     rcx, rdi
0x18000321a  call    BripFreeBindingContext
0x18000321f  mov     rax, r15
0x180003222  jmp     short loc_180003227
0x180003224  mov     rax, rdi
0x180003227  mov     rbx, [rsp+80h+arg_0]
0x18000322f  add     rsp, 80h
0x180003236  pop     r15
0x180003238  pop     r14
0x18000323a  pop     rdi
0x18000323b  pop     rsi
0x18000323c  pop     rbp
0x18000323d  retn
```
