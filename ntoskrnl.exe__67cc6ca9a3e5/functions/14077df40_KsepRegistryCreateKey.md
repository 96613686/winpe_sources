# KsepRegistryCreateKey

- ea: `0x14077df40`
- end: `0x14077e19d`
- name: `KsepRegistryCreateKey`
- size: `605`
- prototype: `__int64 __fastcall(__int64, __int64, HANDLE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14077bb00`

## callees

- `0x140613770`
- `0x1406daa70`
- `0x1406dac30`
- `0x14077df40`
- `0x14097a118`
- `0x14097a928`

## string_xrefs

- `0x14077dfd6`: `EnginePath != NULL`
- `0x14077dfcf`: `minkernel\ntos\kshim\kseregistry.c`
- `0x14077e01e`: `minkernel\ntos\kshim\kseregistry.c`
- `0x14077e06d`: `minkernel\ntos\kshim\kseregistry.c`

## pseudocode

```c
__int64 __fastcall KsepRegistryCreateKey(__int64 a1, __int64 a2, HANDLE *a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  NTSTATUS v9; // ebx
  _QWORD v11[2]; // [rsp+40h] [rbp-9h] BYREF
  _QWORD v12[2]; // [rsp+50h] [rbp+7h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+17h] BYREF
  HANDLE KeyHandle; // [rsp+B0h] [rbp+67h] BYREF
  HANDLE v15; // [rsp+B8h] [rbp+6Fh] BYREF

  v11[0] = 0;
  v11[1] = 0;
  v12[0] = 0;
  v12[1] = 0;
  KeyHandle = 0;
  v15 = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !a1 )
  {
    v6 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&AlpcpMessageLogLock.Timer.DueTime, 1u) + 1)
       & 0x3F;
    *(&AlpcpMessageLogLock.Timer.Period + 2 * v6) = -1073740768;
    *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * v6) = 262645;
    if ( ((__int64)stru_140E4CF30.StackBase & 4) != 0 )
      RtlAssert("EnginePath != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x1F5u, 0);
  }
  if ( !a2 )
  {
    v7 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&AlpcpMessageLogLock.Timer.DueTime, 1u) + 1)
       & 0x3F;
    *(&AlpcpMessageLogLock.Timer.Period + 2 * v7) = -1073740768;
    *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * v7) = 262646;
    if ( ((__int64)stru_140E4CF30.StackBase & 4) != 0 )
      RtlAssert("SearchKey != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x1F6u, 0);
  }
  if ( !a3 )
  {
    v8 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&AlpcpMessageLogLock.Timer.DueTime, 1u) + 1)
       & 0x3F;
    *(&AlpcpMessageLogLock.Timer.Period + 2 * v8) = -1073740768;
    *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * v8) = 262647;
    if ( ((__int64)stru_140E4CF30.StackBase & 4) != 0 )
      RtlAssert("Handle != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x1F7u, 0);
  }
  KsepStringDuplicate(v11, a1);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v11;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( v9 >= 0 )
  {
    v9 = KsepStringDuplicate(v12, a2);
    if ( v9 >= 0 )
    {
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)v12;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v9 = ZwCreateKey(&v15, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
      if ( v9 >= 0 )
      {
        *a3 = v15;
        _InterlockedIncrement((volatile signed __int32 *)&AlpcpMessageLogLock.WaitBlockList);
      }
    }
  }
  KsepStringFree(v11);
  KsepStringFree(v12);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14077df40  mov     [rsp-8+arg_10], rbx
0x14077df45  mov     [rsp-8+arg_18], rsi
0x14077df4a  push    rbp
0x14077df4b  push    rdi
0x14077df4c  push    r12
0x14077df4e  lea     rbp, [rsp-47h]
0x14077df53  sub     rsp, 90h
0x14077df5a  xor     eax, eax
0x14077df5c  lea     r12, AlpcpMessageLogLock.Timer.Processor
0x14077df63  mov     [rbp+57h+var_60], rax
0x14077df67  xorps   xmm0, xmm0
0x14077df6a  mov     [rbp+57h+var_58], rax
0x14077df6e  mov     rsi, rdx
0x14077df71  mov     [rbp+57h+var_50], rax
0x14077df75  mov     rdi, r8
0x14077df78  mov     [rbp+57h+var_48], rax
0x14077df7c  lea     edx, [rax+4]
0x14077df7f  mov     [rbp+57h+KeyHandle], rax
0x14077df83  mov     rbx, rcx
0x14077df86  mov     [rbp+57h+arg_8], rax
0x14077df8a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14077df8e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14077df92  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14077df96  test    rcx, rcx
0x14077df99  jnz     short loc_14077DFE5
0x14077df9b  lea     eax, [rcx+1]
0x14077df9e  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, eax
0x14077dfa6  inc     eax
0x14077dfa8  mov     r8d, 1F5h; LineNumber
0x14077dfae  and     eax, 3Fh
0x14077dfb1  mov     dword ptr [r12+rax*8+4], 0C0000420h
0x14077dfba  mov     dword ptr [r12+rax*8], 401F5h
0x14077dfc2  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x14077dfc8  test    dl, al
0x14077dfca  jz      short loc_14077DFE5
0x14077dfcc  xor     r9d, r9d; MutableMessage
0x14077dfcf  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x14077dfd6  lea     rcx, aEnginepathNull; "EnginePath != NULL"
0x14077dfdd  call    RtlAssert
0x14077dfe2  lea     edx, [rbx+4]
0x14077dfe5  test    rsi, rsi
0x14077dfe8  jnz     short loc_14077E031
0x14077dfea  lea     eax, [rsi+1]
0x14077dfed  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, eax
0x14077dff5  inc     eax
0x14077dff7  mov     r8d, 1F6h; LineNumber
0x14077dffd  and     eax, 3Fh
0x14077e000  mov     dword ptr [r12+rax*8+4], 0C0000420h
0x14077e009  mov     dword ptr [r12+rax*8], 401F6h
0x14077e011  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x14077e017  test    dl, al
0x14077e019  jz      short loc_14077E031
0x14077e01b  xor     r9d, r9d; MutableMessage
0x14077e01e  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x14077e025  lea     rcx, aSearchkeyNull; "SearchKey != NULL"
0x14077e02c  call    RtlAssert
0x14077e031  test    rdi, rdi
0x14077e034  jnz     short loc_14077E080
0x14077e036  lea     eax, [rdi+1]
0x14077e039  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, eax
0x14077e041  inc     eax
0x14077e043  lea     edx, [rdi+4]
0x14077e046  and     eax, 3Fh
0x14077e049  mov     r8d, 1F7h; LineNumber
0x14077e04f  mov     dword ptr [r12+rax*8+4], 0C0000420h
0x14077e058  mov     dword ptr [r12+rax*8], 401F7h
0x14077e060  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x14077e066  test    dl, al
0x14077e068  jz      short loc_14077E080
0x14077e06a  xor     r9d, r9d; MutableMessage
0x14077e06d  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x14077e074  lea     rcx, aHandleNull; "Handle != NULL"
0x14077e07b  call    RtlAssert
0x14077e080  mov     rdx, rbx
0x14077e083  lea     rcx, [rbp+57h+var_60]
0x14077e087  call    KsepStringDuplicate
0x14077e08c  lea     rax, [rbp+57h+var_60]
0x14077e090  mov     [rsp+0A0h+Disposition], 0; Disposition
0x14077e099  xorps   xmm0, xmm0
0x14077e09c  mov     [rsp+0A0h+CreateOptions], 0; CreateOptions
0x14077e0a4  mov     r12d, 30h ; '0'
0x14077e0aa  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14077e0ae  xor     r9d, r9d; TitleIndex
0x14077e0b1  mov     [rbp+57h+ObjectAttributes.Length], r12d
0x14077e0b5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14077e0b9  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14077e0c1  mov     edx, 2001Fh; DesiredAccess
0x14077e0c6  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14077e0cd  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14077e0d1  mov     [rsp+0A0h+Class], 0; Class
0x14077e0da  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14077e0df  call    ZwCreateKey
0x14077e0e4  mov     ebx, eax
0x14077e0e6  test    eax, eax
0x14077e0e8  js      short loc_14077E162
0x14077e0ea  mov     rdx, rsi
0x14077e0ed  lea     rcx, [rbp+57h+var_50]
0x14077e0f1  call    KsepStringDuplicate
0x14077e0f6  mov     ebx, eax
0x14077e0f8  test    eax, eax
0x14077e0fa  js      short loc_14077E162
0x14077e0fc  mov     rax, [rbp+57h+KeyHandle]
0x14077e100  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14077e104  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14077e108  lea     rcx, [rbp+57h+arg_8]; KeyHandle
0x14077e10c  lea     rax, [rbp+57h+var_50]
0x14077e110  mov     [rsp+0A0h+Disposition], 0; Disposition
0x14077e119  xorps   xmm0, xmm0
0x14077e11c  mov     [rsp+0A0h+CreateOptions], 0; CreateOptions
0x14077e124  xor     r9d, r9d; TitleIndex
0x14077e127  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14077e12b  mov     edx, 2001Fh; DesiredAccess
0x14077e130  mov     [rbp+57h+ObjectAttributes.Length], r12d
0x14077e134  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14077e13b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14077e140  mov     [rsp+0A0h+Class], 0; Class
0x14077e149  call    ZwCreateKey
0x14077e14e  mov     ebx, eax
0x14077e150  test    eax, eax
0x14077e152  js      short loc_14077E162
0x14077e154  mov     rax, [rbp+57h+arg_8]
0x14077e158  mov     [rdi], rax
0x14077e15b  lock inc dword ptr cs:AlpcpMessageLogLock.WaitBlockList
0x14077e162  lea     rcx, [rbp+57h+var_60]
0x14077e166  call    KsepStringFree
0x14077e16b  lea     rcx, [rbp+57h+var_50]
0x14077e16f  call    KsepStringFree
0x14077e174  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14077e178  test    rcx, rcx
0x14077e17b  jz      short loc_14077E182
0x14077e17d  call    ZwClose
0x14077e182  lea     r11, [rsp+0A0h+var_10]
0x14077e18a  mov     eax, ebx
0x14077e18c  mov     rbx, [r11+30h]
0x14077e190  mov     rsi, [r11+38h]
0x14077e194  mov     rsp, r11
0x14077e197  pop     r12
0x14077e199  pop     rdi
0x14077e19a  pop     rbp
0x14077e19b  retn
```
