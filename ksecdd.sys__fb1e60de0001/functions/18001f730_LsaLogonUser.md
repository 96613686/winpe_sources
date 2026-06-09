# LsaLogonUser

- ea: `0x18001f730`
- end: `0x18001f7b9`
- name: `LsaLogonUser`
- size: `137`
- prototype: `NTSTATUS __stdcall(HANDLE LsaHandle, PLSA_STRING OriginName, SECURITY_LOGON_TYPE LogonType, ULONG AuthenticationPackage, PVOID AuthenticationInformation, ULONG AuthenticationInformationLength, PTOKEN_GROUPS LocalGroups, PTOKEN_SOURCE SourceContext, PVOID *ProfileBuffer, PULONG ProfileBufferLength, PLUID LogonId, PHANDLE Token, PQUOTA_LIMITS Quotas, PNTSTATUS SubStatus)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800076a0`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
NTSTATUS __stdcall LsaLogonUser(
        HANDLE LsaHandle,
        PLSA_STRING OriginName,
        SECURITY_LOGON_TYPE LogonType,
        ULONG AuthenticationPackage,
        PVOID AuthenticationInformation,
        ULONG AuthenticationInformationLength,
        PTOKEN_GROUPS LocalGroups,
        PTOKEN_SOURCE SourceContext,
        PVOID *ProfileBuffer,
        PULONG ProfileBufferLength,
        PLUID LogonId,
        PHANDLE Token,
        PQUOTA_LIMITS Quotas,
        PNTSTATUS SubStatus)
{
  return SspipLogonUser(
           (__int64)LsaHandle,
           (__int64)OriginName,
           *(__int64 *)&LogonType,
           *(__int64 *)&AuthenticationPackage,
           (__int64)AuthenticationInformation,
           AuthenticationInformationLength,
           (__int64)LocalGroups,
           (__int64)SourceContext,
           ProfileBuffer,
           (__int64)ProfileBufferLength,
           (__int64)LogonId,
           Token,
           Quotas,
           (__int64)SubStatus);
}

```

## disassembly

```asm
0x18001f730  mov     r11, rsp
0x18001f733  sub     rsp, 78h
0x18001f737  mov     rax, [rsp+78h+SubStatus]
0x18001f73f  mov     [r11-10h], rax
0x18001f743  mov     rax, [rsp+78h+Quotas]
0x18001f74b  mov     [r11-18h], rax
0x18001f74f  mov     rax, [rsp+78h+Token]
0x18001f757  mov     [r11-20h], rax
0x18001f75b  mov     rax, [rsp+78h+LogonId]
0x18001f763  mov     [r11-28h], rax
0x18001f767  mov     rax, [rsp+78h+ProfileBufferLength]
0x18001f76f  mov     [r11-30h], rax
0x18001f773  mov     rax, [rsp+78h+ProfileBuffer]
0x18001f77b  mov     [r11-38h], rax
0x18001f77f  mov     rax, [rsp+78h+SourceContext]
0x18001f787  mov     [r11-40h], rax
0x18001f78b  mov     rax, [rsp+78h+LocalGroups]
0x18001f793  mov     [r11-48h], rax
0x18001f797  mov     eax, [rsp+78h+AuthenticationInformationLength]
0x18001f79e  mov     [rsp+78h+var_50], eax
0x18001f7a2  mov     rax, [rsp+78h+AuthenticationInformation]
0x18001f7aa  mov     [r11-58h], rax
0x18001f7ae  call    SspipLogonUser
0x18001f7b3  add     rsp, 78h
0x18001f7b7  retn
```
