# MsvpDeleteTbalPrimaryCredentialsSecret(void)

- ea: `0x180055a34`
- end: `0x180055ab6`
- name: `?MsvpDeleteTbalPrimaryCredentialsSecret@@YAJXZ`
- size: `130`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180055dc0`

## callees

- `0x180055a34`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180055a57`
- `ntdll!RtlInitUnicodeString` at `0x180055a57`
- `LSASRV!LsarDeleteObject` at `0x180055a93`
- `LSASRV!LsarDeleteObject` at `0x180055a93`
- `LSASRV!LsarClose` at `0x180055aa8`
- `LSASRV!LsarClose` at `0x180055aa8`
- `LSASRV!LsarOpenSecret` at `0x180055a74`
- `LSASRV!LsarOpenSecret` at `0x180055a74`

## pseudocode

```c
__int64 MsvpDeleteTbalPrimaryCredentialsSecret(void)
{
  int v0; // eax
  unsigned int v1; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF
  __int64 v4; // [rsp+40h] [rbp+8h] BYREF

  v4 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"M$_MSV1_0_TBAL_PRIMARY_{22BE8E5B-58B3-4A87-BA71-41B0ECF3A9EA}");
  v0 = LsarOpenSecret(NtLmGlobalPolicyHandle, &DestinationString, 3, &v4);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v1 = LsarDeleteObject(&v4);
  }
  else if ( v0 == -1073741772 )
  {
    v1 = -1073740943;
  }
  if ( v4 )
    LsarClose(&v4);
  return v1;
}

```

## disassembly

```asm
0x180055a34  push    rbx
0x180055a36  sub     rsp, 30h
0x180055a3a  xorps   xmm0, xmm0
0x180055a3d  mov     [rsp+38h+arg_0], 0
0x180055a46  lea     rdx, aMMsv10TbalPrim; "M$_MSV1_0_TBAL_PRIMARY_{22BE8E5B-58B3-4"...
0x180055a4d  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x180055a52  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x180055a57  call    cs:__imp_RtlInitUnicodeString
0x180055a5d  mov     rcx, cs:NtLmGlobalPolicyHandle
0x180055a64  lea     r9, [rsp+38h+arg_0]
0x180055a69  mov     r8d, 3
0x180055a6f  lea     rdx, [rsp+38h+DestinationString]
0x180055a74  call    cs:__imp_LsarOpenSecret
0x180055a7a  mov     ebx, eax
0x180055a7c  test    eax, eax
0x180055a7e  jns     short loc_180055A8E
0x180055a80  cmp     eax, 0C0000034h
0x180055a85  jnz     short loc_180055A9B
0x180055a87  mov     ebx, 0C0000371h
0x180055a8c  jmp     short loc_180055A9B
0x180055a8e  lea     rcx, [rsp+38h+arg_0]
0x180055a93  call    cs:__imp_LsarDeleteObject
0x180055a99  mov     ebx, eax
0x180055a9b  cmp     [rsp+38h+arg_0], 0
0x180055aa1  jz      short loc_180055AAE
0x180055aa3  lea     rcx, [rsp+38h+arg_0]
0x180055aa8  call    cs:__imp_LsarClose
0x180055aae  mov     eax, ebx
0x180055ab0  add     rsp, 30h
0x180055ab4  pop     rbx
0x180055ab5  retn
```
