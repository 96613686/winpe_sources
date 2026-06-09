# NdisOpenProtocolConfiguration

- ea: `0x140061340`
- end: `0x14006158c`
- name: `NdisOpenProtocolConfiguration`
- size: `588`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140048d20`
- `0x140049030`
- `0x14018e1a4`
- `0x14018e414`

## callees

- `0x140029620`
- `0x140054b80`
- `0x140061340`
- `0x1400e62c0`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14006146b`
- `ntoskrnl!ZwOpenKey` at `0x1400614e6`
- `ntoskrnl!ZwOpenKey` at `0x14006146b`
- `ntoskrnl!ZwOpenKey` at `0x1400614e6`
- `ntoskrnl!ZwClose` at `0x140061490`
- `ntoskrnl!ZwClose` at `0x140061490`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006157b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006157b`
- `ntoskrnl!ExAllocatePool2` at `0x1400613b7`
- `ntoskrnl!ExAllocatePool2` at `0x1400613b7`

## string_xrefs

- `0x140061362`: `\Registry\Machine\System\CurrentControlSet\Services`

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
0x140061340  push    rbp
0x140061342  push    rbx
0x140061343  push    rsi
0x140061344  push    rdi
0x140061345  push    r12
0x140061347  push    r13
0x140061349  push    r14
0x14006134b  push    r15
0x14006134d  mov     rbp, rsp
0x140061350  sub     rsp, 78h
0x140061354  xorps   xmm0, xmm0
0x140061357  mov     [rbp+var_48], 680066h
0x14006135f  xor     r12d, r12d
0x140061362  lea     rax, aRegistryMachin_17; "\\Registry\\Machine\\System\\CurrentCon"...
0x140061369  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14006136d  mov     [rbp+KeyHandle], r12
0x140061371  mov     rsi, r8
0x140061374  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140061378  mov     [rbp+var_40], rax
0x14006137c  mov     r15, rdx
0x14006137f  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140061383  mov     r14, rcx
0x140061386  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14006138d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140061394  lea     rax, WPP_e3923b1e1d063659b60938af674e4994_Traceguids
0x14006139b  jnz     loc_140061540
0x1400613a1  movzx   edi, word ptr [rsi+2]
0x1400613a5  mov     r8d, 6370444Eh
0x1400613ab  mov     ecx, 40h ; '@'
0x1400613b0  lea     rdx, [rdi+0B2h]
0x1400613b7  call    cs:__imp_ExAllocatePool2
0x1400613be  nop     dword ptr [rax+rax+00h]
0x1400613c3  mov     rbx, rax
0x1400613c6  test    rax, rax
0x1400613c9  jz      loc_140061531
0x1400613cf  lea     r8, [rdi+0B2h]; Size
0x1400613d6  mov     [r14], r12d
0x1400613d9  xor     edx, edx; Val
0x1400613db  mov     rcx, rax; void *
0x1400613de  call    memset
0x1400613e3  movzx   r8d, word ptr [rsi]; Size
0x1400613e7  lea     rcx, [rbx+0B0h]; void *
0x1400613ee  mov     rdx, [rsi+8]; Src
0x1400613f2  lea     rdi, [rbx+28h]
0x1400613f6  call    memmove
0x1400613fb  mov     [rbx+10h], rdi
0x1400613ff  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140061403  mov     [rbx+18h], r12
0x140061407  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14006140b  mov     word ptr [rdi], 10Ah
0x140061410  xorps   xmm0, xmm0
0x140061413  mov     rax, [rbx+10h]
0x140061417  mov     edx, 8; DesiredAccess
0x14006141c  mov     word ptr [rax+2], 28h ; '('
0x140061422  mov     rax, [rbx+10h]
0x140061426  or      dword ptr [rax+10h], 2
0x14006142a  lea     rax, ?ndisSaveParameters@@YAJPEA_WKPEAXK11@Z; ndisSaveParameters(wchar_t *,ulong,void *,ulong,void *,void *)
0x140061431  mov     [rdi+18h], rax
0x140061435  lea     rax, [rbp+var_48]
0x140061439  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14006143d  mov     dword ptr [rdi+20h], 14h
0x140061444  mov     [rdi+38h], r12d
0x140061448  mov     [rdi+50h], r12
0x14006144c  mov     [rdi+58h], r12d
0x140061450  mov     [rdi+60h], r12
0x140061454  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14006145b  mov     [rbp+ObjectAttributes.RootDirectory], r12
0x14006145f  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140061466  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14006146b  call    cs:__imp_ZwOpenKey
0x140061472  nop     dword ptr [rax+rax+00h]
0x140061477  mov     [r14], eax
0x14006147a  test    eax, eax
0x14006147c  jns     short loc_1400614B7
0x14006147e  cmp     [r14], r12d
0x140061481  jl      loc_14006156D
0x140061487  mov     rcx, [rbp+KeyHandle]; Handle
0x14006148b  test    rcx, rcx
0x14006148e  jz      short loc_14006149C
0x140061490  call    cs:__imp_ZwClose
0x140061497  nop     dword ptr [rax+rax+00h]
0x14006149c  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400614a3  jnz     short loc_140061502
0x1400614a5  add     rsp, 78h
0x1400614a9  pop     r15
0x1400614ab  pop     r14
0x1400614ad  pop     r13
0x1400614af  pop     r12
0x1400614b1  pop     rdi
0x1400614b2  pop     rsi
0x1400614b3  pop     rbx
0x1400614b4  pop     rbp
0x1400614b5  retn
0x1400614b7  mov     rax, [rbp+KeyHandle]
0x1400614bb  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400614bf  xorps   xmm0, xmm0
0x1400614c2  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1400614c6  mov     edx, 0Bh; DesiredAccess
0x1400614cb  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400614d2  lea     rcx, [rbx+20h]; KeyHandle
0x1400614d6  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400614dd  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400614e2  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x1400614e6  call    cs:__imp_ZwOpenKey
0x1400614ed  nop     dword ptr [rax+rax+00h]
0x1400614f2  test    eax, eax
0x1400614f4  jns     short loc_1400614FA
0x1400614f6  mov     [rbx+20h], r12
0x1400614fa  mov     [r15], rbx
0x1400614fd  mov     [r14], r12d
0x140061500  jmp     short loc_140061487
0x140061502  mov     rcx, cs:WPP_GLOBAL_Control
0x140061509  lea     rax, WPP_e3923b1e1d063659b60938af674e4994_Traceguids
0x140061510  mov     r9d, 2Dh ; '-'; int
0x140061516  mov     [rsp+78h+var_58], rax; struct _GUID *
0x14006151b  mov     r8d, 0Dh; int
0x140061521  mov     dl, 4; int
0x140061523  mov     rcx, [rcx+40h]; int
0x140061527  call    WPP_RECORDER_SF_
0x14006152c  jmp     loc_1400614A5
0x140061531  mov     dword ptr [r14], 0C000009Ah
0x140061538  mov     [r15], r12
0x14006153b  jmp     loc_14006147E
0x140061540  mov     rcx, cs:WPP_GLOBAL_Control
0x140061547  mov     r9d, 2Ch ; ','; int
0x14006154d  mov     [rsp+78h+var_50], rsi; __int64
0x140061552  mov     r8d, 0Dh; int
0x140061558  mov     dl, 4; int
0x14006155a  mov     [rsp+78h+var_58], rax; struct _GUID *
0x14006155f  mov     rcx, [rcx+40h]; int
0x140061563  call    WPP_RECORDER_SF_Z
0x140061568  jmp     loc_1400613A1
0x14006156d  test    rbx, rbx
0x140061570  jz      loc_140061487
0x140061576  xor     edx, edx; Tag
0x140061578  mov     rcx, rbx; P
0x14006157b  call    cs:__imp_ExFreePoolWithTag
0x140061582  nop     dword ptr [rax+rax+00h]
0x140061587  jmp     loc_140061487
```
