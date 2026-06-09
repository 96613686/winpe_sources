# NdisOpenProtocolConfiguration

- ea: `0x1400663c0`
- end: `0x14006660c`
- name: `NdisOpenProtocolConfiguration`
- size: `588`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14004d6a0`
- `0x14004d9b0`
- `0x1401941b4`
- `0x140194424`

## callees

- `0x14002ab60`
- `0x140059c80`
- `0x1400663c0`
- `0x1400eb4c0`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400664eb`
- `ntoskrnl!ZwOpenKey` at `0x140066566`
- `ntoskrnl!ZwOpenKey` at `0x1400664eb`
- `ntoskrnl!ZwOpenKey` at `0x140066566`
- `ntoskrnl!ZwClose` at `0x140066510`
- `ntoskrnl!ZwClose` at `0x140066510`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400665fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400665fb`
- `ntoskrnl!ExAllocatePool2` at `0x140066437`
- `ntoskrnl!ExAllocatePool2` at `0x140066437`

## string_xrefs

- `0x1400663e2`: `\Registry\Machine\System\CurrentControlSet\Services`

## pseudocode

```c
void __fastcall NdisOpenProtocolConfiguration(NTSTATUS *a1, _QWORD *a2, struct _UNICODE_STRING *a3)
{
  _QWORD *v4; // r15
  __int64 MaximumLength; // rdi
  char *Pool2; // rax
  int v8; // edx
  char *v9; // rbx
  NTSTATUS v10; // eax
  _QWORD v11[2]; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *KeyHandle; // [rsp+C0h] [rbp+48h] BYREF

  v11[0] = 6815846;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  KeyHandle = 0;
  v11[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services";
  v4 = a2;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_Z(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)a2,
      13,
      44,
      (struct _GUID *)&WPP_e3923b1e1d063659b60938af674e4994_Traceguids,
      (__int64)a3);
  }
  MaximumLength = a3->MaximumLength;
  Pool2 = (char *)ExAllocatePool2(64, MaximumLength + 178, 1668301902);
  v9 = Pool2;
  if ( !Pool2 )
  {
    *a1 = -1073741670;
    *v4 = 0;
    goto LABEL_5;
  }
  *a1 = 0;
  memset(Pool2, 0, MaximumLength + 178);
  memmove(v9 + 176, a3->Buffer, a3->Length);
  *((_QWORD *)v9 + 2) = v9 + 40;
  *((_QWORD *)v9 + 3) = 0;
  *((_WORD *)v9 + 20) = 266;
  *(_WORD *)(*((_QWORD *)v9 + 2) + 2LL) = 40;
  *(_DWORD *)(*((_QWORD *)v9 + 2) + 16LL) |= 2u;
  *((_QWORD *)v9 + 8) = ndisSaveParameters;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v11;
  *((_DWORD *)v9 + 18) = 20;
  *((_DWORD *)v9 + 24) = 0;
  *((_QWORD *)v9 + 15) = 0;
  *((_DWORD *)v9 + 32) = 0;
  *((_QWORD *)v9 + 17) = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = ZwOpenKey(&KeyHandle, 8u, &ObjectAttributes);
  *a1 = v10;
  if ( v10 < 0 )
  {
LABEL_5:
    if ( *a1 < 0 && v9 )
      ExFreePoolWithTag(v9, 0);
    goto LABEL_6;
  }
  ObjectAttributes.RootDirectory = KeyHandle;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.ObjectName = a3;
  if ( ZwOpenKey((PHANDLE)v9 + 4, 0xBu, &ObjectAttributes) < 0 )
    *((_QWORD *)v9 + 4) = 0;
  *v4 = v9;
  *a1 = 0;
LABEL_6:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = 4;
    WPP_RECORDER_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v8,
      13,
      45,
      (struct _GUID *)&WPP_e3923b1e1d063659b60938af674e4994_Traceguids);
  }
}

```

## disassembly

```asm
0x1400663c0  push    rbp
0x1400663c2  push    rbx
0x1400663c3  push    rsi
0x1400663c4  push    rdi
0x1400663c5  push    r12
0x1400663c7  push    r13
0x1400663c9  push    r14
0x1400663cb  push    r15
0x1400663cd  mov     rbp, rsp
0x1400663d0  sub     rsp, 78h
0x1400663d4  xorps   xmm0, xmm0
0x1400663d7  mov     [rbp+var_48], 680066h
0x1400663df  xor     r12d, r12d
0x1400663e2  lea     rax, aRegistryMachin_17; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400663e9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400663ed  mov     [rbp+KeyHandle], r12
0x1400663f1  mov     rsi, r8
0x1400663f4  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400663f8  mov     [rbp+var_40], rax
0x1400663fc  mov     r15, rdx
0x1400663ff  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140066403  mov     r14, rcx
0x140066406  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14006640d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140066414  lea     rax, WPP_e3923b1e1d063659b60938af674e4994_Traceguids
0x14006641b  jnz     loc_1400665C0
0x140066421  movzx   edi, word ptr [rsi+2]
0x140066425  mov     r8d, 6370444Eh
0x14006642b  mov     ecx, 40h ; '@'
0x140066430  lea     rdx, [rdi+0B2h]
0x140066437  call    cs:__imp_ExAllocatePool2
0x14006643e  nop     dword ptr [rax+rax+00h]
0x140066443  mov     rbx, rax
0x140066446  test    rax, rax
0x140066449  jz      loc_1400665B1
0x14006644f  lea     r8, [rdi+0B2h]; Size
0x140066456  mov     [r14], r12d
0x140066459  xor     edx, edx; Val
0x14006645b  mov     rcx, rax; void *
0x14006645e  call    memset
0x140066463  movzx   r8d, word ptr [rsi]; Size
0x140066467  lea     rcx, [rbx+0B0h]; void *
0x14006646e  mov     rdx, [rsi+8]; Src
0x140066472  lea     rdi, [rbx+28h]
0x140066476  call    memmove
0x14006647b  mov     [rbx+10h], rdi
0x14006647f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140066483  mov     [rbx+18h], r12
0x140066487  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14006648b  mov     word ptr [rdi], 10Ah
0x140066490  xorps   xmm0, xmm0
0x140066493  mov     rax, [rbx+10h]
0x140066497  mov     edx, 8; DesiredAccess
0x14006649c  mov     word ptr [rax+2], 28h ; '('
0x1400664a2  mov     rax, [rbx+10h]
0x1400664a6  or      dword ptr [rax+10h], 2
0x1400664aa  lea     rax, ?ndisSaveParameters@@YAJPEA_WKPEAXK11@Z; ndisSaveParameters(wchar_t *,ulong,void *,ulong,void *,void *)
0x1400664b1  mov     [rdi+18h], rax
0x1400664b5  lea     rax, [rbp+var_48]
0x1400664b9  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400664bd  mov     dword ptr [rdi+20h], 14h
0x1400664c4  mov     [rdi+38h], r12d
0x1400664c8  mov     [rdi+50h], r12
0x1400664cc  mov     [rdi+58h], r12d
0x1400664d0  mov     [rdi+60h], r12
0x1400664d4  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400664db  mov     [rbp+ObjectAttributes.RootDirectory], r12
0x1400664df  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400664e6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400664eb  call    cs:__imp_ZwOpenKey
0x1400664f2  nop     dword ptr [rax+rax+00h]
0x1400664f7  mov     [r14], eax
0x1400664fa  test    eax, eax
0x1400664fc  jns     short loc_140066537
0x1400664fe  cmp     [r14], r12d
0x140066501  jl      loc_1400665ED
0x140066507  mov     rcx, [rbp+KeyHandle]; Handle
0x14006650b  test    rcx, rcx
0x14006650e  jz      short loc_14006651C
0x140066510  call    cs:__imp_ZwClose
0x140066517  nop     dword ptr [rax+rax+00h]
0x14006651c  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140066523  jnz     short loc_140066582
0x140066525  add     rsp, 78h
0x140066529  pop     r15
0x14006652b  pop     r14
0x14006652d  pop     r13
0x14006652f  pop     r12
0x140066531  pop     rdi
0x140066532  pop     rsi
0x140066533  pop     rbx
0x140066534  pop     rbp
0x140066535  retn
0x140066537  mov     rax, [rbp+KeyHandle]
0x14006653b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14006653f  xorps   xmm0, xmm0
0x140066542  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x140066546  mov     edx, 0Bh; DesiredAccess
0x14006654b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140066552  lea     rcx, [rbx+20h]; KeyHandle
0x140066556  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14006655d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140066562  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x140066566  call    cs:__imp_ZwOpenKey
0x14006656d  nop     dword ptr [rax+rax+00h]
0x140066572  test    eax, eax
0x140066574  jns     short loc_14006657A
0x140066576  mov     [rbx+20h], r12
0x14006657a  mov     [r15], rbx
0x14006657d  mov     [r14], r12d
0x140066580  jmp     short loc_140066507
0x140066582  mov     rcx, cs:WPP_GLOBAL_Control
0x140066589  lea     rax, WPP_e3923b1e1d063659b60938af674e4994_Traceguids
0x140066590  mov     r9d, 2Dh ; '-'; int
0x140066596  mov     [rsp+78h+var_58], rax; struct _GUID *
0x14006659b  mov     r8d, 0Dh; int
0x1400665a1  mov     dl, 4; int
0x1400665a3  mov     rcx, [rcx+40h]; int
0x1400665a7  call    WPP_RECORDER_SF_
0x1400665ac  jmp     loc_140066525
0x1400665b1  mov     dword ptr [r14], 0C000009Ah
0x1400665b8  mov     [r15], r12
0x1400665bb  jmp     loc_1400664FE
0x1400665c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400665c7  mov     r9d, 2Ch ; ','; int
0x1400665cd  mov     [rsp+78h+var_50], rsi; __int64
0x1400665d2  mov     r8d, 0Dh; int
0x1400665d8  mov     dl, 4; int
0x1400665da  mov     [rsp+78h+var_58], rax; struct _GUID *
0x1400665df  mov     rcx, [rcx+40h]; int
0x1400665e3  call    WPP_RECORDER_SF_Z
0x1400665e8  jmp     loc_140066421
0x1400665ed  test    rbx, rbx
0x1400665f0  jz      loc_140066507
0x1400665f6  xor     edx, edx; Tag
0x1400665f8  mov     rcx, rbx; P
0x1400665fb  call    cs:__imp_ExFreePoolWithTag
0x140066602  nop     dword ptr [rax+rax+00h]
0x140066607  jmp     loc_140066507
```
