# WfpRegOpenKey

- ea: `0x14006bf4c`
- end: `0x14006c025`
- name: `WfpRegOpenKey`
- size: `217`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `7`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140064270`
- `0x14006aa50`
- `0x14006ad28`
- `0x14006bccc`
- `0x14006c02c`
- `0x1400aa16c`
- `0x1400aa388`

## callees

- `0x140009520`
- `0x140009e00`
- `0x14006bf4c`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14006bfc0`
- `ntoskrnl!ZwOpenKey` at `0x14006bfc0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006bf80`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006bf80`

## string_xrefs

- `0x14006bff8`: `WfpRegOpenKey`
- `0x14006bfe1`: `ZwOpenKey`

## pseudocode

```c
__int64 __fastcall WfpRegOpenKey(PHANDLE KeyHandle, const WCHAR *a2, _DWORD *a3)
{
  NTSTATUS v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rbx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  *(_OWORD *)&ObjectAttributes.ObjectName = 0;
  *a3 = 0;
  *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
  *(_OWORD *)&ObjectAttributes.Length = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenKey(KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v5 >= 0 )
  {
    if ( !v5 )
    {
      *a3 = 1;
      return 0;
    }
  }
  else if ( v5 == -1073741772 )
  {
    return 0;
  }
  v7 = WfpReportSysErrorAsNtStatus(v6, "ZwOpenKey", (unsigned int)v5, 1);
  v8 = v7;
  if ( v7 )
    WfpReportError(v7, "WfpRegOpenKey");
  return v8;
}

```

## disassembly

```asm
0x14006bf4c  mov     [rsp-8+arg_0], rbx
0x14006bf51  mov     [rsp-8+arg_8], rdi
0x14006bf56  push    rbp
0x14006bf57  mov     rbp, rsp
0x14006bf5a  sub     rsp, 60h
0x14006bf5e  xorps   xmm0, xmm0
0x14006bf61  mov     rbx, rcx
0x14006bf64  xor     eax, eax
0x14006bf66  lea     rcx, [rbp+DestinationString]; DestinationString
0x14006bf6a  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14006bf6e  mov     rdi, r8
0x14006bf71  mov     [r8], eax
0x14006bf74  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14006bf78  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14006bf7c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14006bf80  call    cs:__imp_RtlInitUnicodeString
0x14006bf87  nop     dword ptr [rax+rax+00h]
0x14006bf8c  lea     rax, [rbp+DestinationString]
0x14006bf90  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14006bf98  xorps   xmm0, xmm0
0x14006bf9b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14006bf9f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14006bfa3  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14006bfab  mov     edx, 20019h; DesiredAccess
0x14006bfb0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14006bfb8  mov     rcx, rbx; KeyHandle
0x14006bfbb  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14006bfc0  call    cs:__imp_ZwOpenKey
0x14006bfc7  nop     dword ptr [rax+rax+00h]
0x14006bfcc  test    eax, eax
0x14006bfce  jns     short loc_14006BFD9
0x14006bfd0  cmp     eax, 0C0000034h
0x14006bfd5  jnz     short loc_14006BFDB
0x14006bfd7  jmp     short loc_14006C00F
0x14006bfd9  jz      short loc_14006C009
0x14006bfdb  mov     r9d, 1
0x14006bfe1  lea     rdx, aZwopenkey; "ZwOpenKey"
0x14006bfe8  mov     r8d, eax
0x14006bfeb  call    WfpReportSysErrorAsNtStatus
0x14006bff0  mov     rbx, rax
0x14006bff3  test    rax, rax
0x14006bff6  jz      short loc_14006C011
0x14006bff8  lea     rdx, aWfpregopenkey; "WfpRegOpenKey"
0x14006bfff  mov     rcx, rax
0x14006c002  call    WfpReportError
0x14006c007  jmp     short loc_14006C011
0x14006c009  mov     dword ptr [rdi], 1
0x14006c00f  xor     ebx, ebx
0x14006c011  mov     rdi, [rsp+60h+arg_8]
0x14006c016  mov     rax, rbx
0x14006c019  mov     rbx, [rsp+60h+arg_0]
0x14006c01e  add     rsp, 60h
0x14006c022  pop     rbp
0x14006c023  retn
```
