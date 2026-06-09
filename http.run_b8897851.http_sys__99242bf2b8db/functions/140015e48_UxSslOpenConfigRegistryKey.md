# UxSslOpenConfigRegistryKey

- ea: `0x140015e48`
- end: `0x14001600a`
- name: `UxSslOpenConfigRegistryKey`
- size: `450`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140016174`
- `0x140017d68`
- `0x1401327d4`

## callees

- `0x140015e48`
- `0x1401677e0`
- `0x1401c3f58`
- `0x1401c4a18`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140015f3e`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140015f3e`
- `ntoskrnl!ZwOpenKey` at `0x140015f8b`
- `ntoskrnl!ZwOpenKey` at `0x140015f8b`
- `ntoskrnl!ZwCreateKey` at `0x140171fc7`
- `ntoskrnl!ZwCreateKey` at `0x140171fc7`
- `ntoskrnl!ZwClose` at `0x140015fd7`
- `ntoskrnl!ZwClose` at `0x140015fd7`
- `ntoskrnl!ExAllocatePool3` at `0x140015eb7`
- `ntoskrnl!ExAllocatePool3` at `0x140015eb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015ef6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015ef6`

## pseudocode

```c
__int64 __fastcall UxSslOpenConfigRegistryKey(__int64 a1, int a2, void **a3)
{
  __int64 Pool3; // rax
  WCHAR *v7; // r14
  NTSTATUS inited; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG Disposition; // [rsp+B0h] [rbp+30h] BYREF
  void *KeyHandle; // [rsp+B8h] [rbp+38h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes.ObjectName, 0, 28);
  Disposition = 0;
  DestinationString = 0;
  *a3 = 0;
  *(_OWORD *)&ObjectAttributes.Length = 0;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qdP(1041, 154, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids, a1, a2, a3);
  Pool3 = ExAllocatePool3(258, 520, 1398107221, UxLowPriorityPool, 1);
  v7 = (WCHAR *)Pool3;
  if ( Pool3 )
  {
    inited = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)(a1 + 416) + 80LL))(a1, Pool3, 520);
    if ( inited < 0 )
      goto LABEL_5;
    inited = RtlInitUnicodeStringEx(&DestinationString, v7);
    if ( inited < 0 )
      goto LABEL_5;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( a2 )
    {
      inited = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
      if ( inited >= 0 )
      {
        if ( a2 == 1 && Disposition != 1 )
        {
          if ( (BYTE2(xmmword_1401A2C90) & 2) != 0 )
            WPP_SF_(529, 155, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids);
          inited = -1073741771;
          goto LABEL_5;
        }
        goto LABEL_22;
      }
    }
    else
    {
      inited = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
      if ( inited >= 0 )
      {
LABEL_22:
        *a3 = KeyHandle;
        KeyHandle = 0;
      }
    }
LABEL_5:
    ExFreePoolWithTag(v7, 0);
    goto LABEL_6;
  }
  inited = -1073741670;
LABEL_6:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qD(1041, 156, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids, a3, inited);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140015e48  mov     [rsp-18h+arg_0], rbx
0x140015e4d  mov     [rsp-18h+arg_8], rsi
0x140015e52  push    rbp
0x140015e53  push    rdi
0x140015e54  push    r14
0x140015e56  mov     rbp, rsp
0x140015e59  sub     rsp, 80h
0x140015e60  xorps   xmm0, xmm0
0x140015e63  mov     [rbp+KeyHandle], 0
0x140015e6b  xor     eax, eax
0x140015e6d  mov     rsi, r8
0x140015e70  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140015e74  mov     edi, edx
0x140015e76  mov     rbx, rcx
0x140015e79  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140015e7d  mov     [rbp+arg_10], eax
0x140015e80  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140015e84  mov     [r8], rax
0x140015e87  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140015e8b  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140015e92  jnz     loc_140015FB0
0x140015e98  lea     r9, UxLowPriorityPool
0x140015e9f  mov     dword ptr [rsp+80h+Class], 1
0x140015ea7  mov     edx, 208h
0x140015eac  mov     ecx, 102h
0x140015eb1  mov     r8d, 53556C55h
0x140015eb7  call    cs:__imp_ExAllocatePool3
0x140015ebe  nop     dword ptr [rax+rax+00h]
0x140015ec3  mov     r14, rax
0x140015ec6  test    rax, rax
0x140015ec9  jz      loc_140015FA6
0x140015ecf  mov     rax, [rbx+1A0h]
0x140015ed6  mov     r8d, 208h
0x140015edc  mov     rdx, r14
0x140015edf  mov     rcx, rbx
0x140015ee2  mov     rax, [rax+50h]
0x140015ee6  call    _guard_dispatch_icall
0x140015eeb  mov     ebx, eax
0x140015eed  test    eax, eax
0x140015eef  jns     short loc_140015F37
0x140015ef1  xor     edx, edx; Tag
0x140015ef3  mov     rcx, r14; P
0x140015ef6  call    cs:__imp_ExFreePoolWithTag
0x140015efd  nop     dword ptr [rax+rax+00h]
0x140015f02  mov     rcx, [rbp+KeyHandle]; Handle
0x140015f06  test    rcx, rcx
0x140015f09  jnz     loc_140015FD7
0x140015f0f  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x140015f16  jnz     loc_140015FE8
0x140015f1c  lea     r11, [rsp+80h+var_s0]
0x140015f24  mov     eax, ebx
0x140015f26  mov     rbx, [r11+20h]
0x140015f2a  mov     rsi, [r11+28h]
0x140015f2e  mov     rsp, r11
0x140015f31  pop     r14
0x140015f33  pop     rdi
0x140015f34  pop     rbp
0x140015f35  retn
0x140015f37  mov     rdx, r14; SourceString
0x140015f3a  lea     rcx, [rbp+DestinationString]; DestinationString
0x140015f3e  call    cs:__imp_RtlInitUnicodeStringEx
0x140015f45  nop     dword ptr [rax+rax+00h]
0x140015f4a  mov     ebx, eax
0x140015f4c  test    eax, eax
0x140015f4e  js      short loc_140015EF1
0x140015f50  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140015f57  lea     rax, [rbp+DestinationString]
0x140015f5b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140015f5f  xorps   xmm0, xmm0
0x140015f62  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140015f6a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140015f6e  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140015f75  mov     edx, 0F003Fh; DesiredAccess
0x140015f7a  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140015f7e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140015f83  test    edi, edi
0x140015f85  jnz     loc_140171FAA
0x140015f8b  call    cs:__imp_ZwOpenKey
0x140015f92  nop     dword ptr [rax+rax+00h]
0x140015f97  mov     ebx, eax
0x140015f99  test    eax, eax
0x140015f9b  js      loc_140015EF1
0x140015fa1  jmp     loc_140172010
0x140015fa6  mov     ebx, 0C000009Ah
0x140015fab  jmp     loc_140015F02
0x140015fb0  mov     edx, 9Ah
0x140015fb5  mov     qword ptr [rsp+80h+CreateOptions], rsi
0x140015fba  mov     ecx, 411h
0x140015fbf  mov     dword ptr [rsp+80h+Class], edi
0x140015fc3  mov     r9, rbx
0x140015fc6  lea     r8, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids
0x140015fcd  call    WPP_SF_qdP
0x140015fd2  jmp     loc_140015E98
0x140015fd7  call    cs:__imp_ZwClose
0x140015fde  nop     dword ptr [rax+rax+00h]
0x140015fe3  jmp     loc_140015F0F
0x140015fe8  mov     edx, 9Ch
0x140015fed  mov     dword ptr [rsp+80h+Class], ebx
0x140015ff1  mov     ecx, 411h
0x140015ff6  lea     r8, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids
0x140015ffd  mov     r9, rsi
0x140016000  call    WPP_SF_qD
0x140016005  jmp     loc_140015F1C
0x140171faa  lea     rax, [rbp+arg_10]
0x140171fae  xor     r9d, r9d; TitleIndex
0x140171fb1  mov     [rsp+80h+Disposition], rax; Disposition
0x140171fb6  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x140171fbe  mov     [rsp+80h+Class], 0; Class
0x140171fc7  call    cs:__imp_ZwCreateKey
0x140171fce  nop     dword ptr [rax+rax+00h]
0x140171fd3  mov     ebx, eax
0x140171fd5  test    eax, eax
0x140171fd7  js      loc_140015EF1
0x140171fdd  cmp     edi, 1
0x140171fe0  jnz     short loc_140172010
0x140171fe2  cmp     [rbp+arg_10], edi
0x140171fe5  jz      short loc_140172010
0x140171fe7  test    byte ptr cs:xmmword_1401A2C90+2, 2
0x140171fee  jz      short loc_140172006
0x140171ff0  mov     edx, 9Bh
0x140171ff5  lea     r8, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids
0x140171ffc  mov     ecx, 211h
0x140172001  call    WPP_SF_
0x140172006  mov     ebx, 0C0000035h
0x14017200b  jmp     loc_140015EF1
0x140172010  mov     rax, [rbp+KeyHandle]
0x140172014  mov     [rsi], rax
0x140172017  mov     [rbp+KeyHandle], 0
0x14017201f  jmp     loc_140015EF1
```
