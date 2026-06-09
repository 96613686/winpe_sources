# SspDuplicateToken

- ea: `0x180014434`
- end: `0x1800144ce`
- name: `SspDuplicateToken`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800268dc`

## callees

- `0x180014434`
- `0x18002fb50`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x18001449e`
- `ntdll!NtDuplicateToken` at `0x18001449e`
- `LSASRV!LsaIAdjustTokenObjectIntegrity` at `0x1800144ab`
- `LSASRV!LsaIAdjustTokenObjectIntegrity` at `0x1800144ab`

## pseudocode

```c
NTSTATUS __fastcall SspDuplicateToken(void *a1, int a2, void **NewTokenHandle)
{
  NTSTATUS result; // eax
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-50h] BYREF
  _DWORD v6[4]; // [rsp+60h] [rbp-20h] BYREF

  v6[1] = a2;
  v6[2] = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 32);
  ObjectAttributes.SecurityQualityOfService = v6;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v6[0] = 12;
  result = NtDuplicateToken(a1, 0, &ObjectAttributes, 0, TokenImpersonation, NewTokenHandle);
  if ( result >= 0 )
    return LsaIAdjustTokenObjectIntegrity(*NewTokenHandle);
  return result;
}

```

## disassembly

```asm
0x180014434  mov     [rsp-8+arg_18], rbx
0x180014439  push    rbp
0x18001443a  mov     rbp, rsp
0x18001443d  sub     rsp, 80h
0x180014444  mov     rax, cs:__security_cookie
0x18001444b  xor     rax, rsp
0x18001444e  mov     [rbp+var_10], rax
0x180014452  xor     eax, eax
0x180014454  mov     [rbp+var_1C], edx
0x180014457  mov     rbx, r8
0x18001445a  mov     [rbp+var_18], eax
0x18001445d  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180014461  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180014465  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180014469  xor     r9d, r9d; EffectiveOnly
0x18001446c  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x180014470  xor     edx, edx; DesiredAccess
0x180014472  lea     rax, [rbp+var_20]
0x180014476  mov     [rsp+80h+NewTokenHandle], rbx; NewTokenHandle
0x18001447b  mov     [rbp+ObjectAttributes.SecurityQualityOfService], rax
0x18001447f  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180014487  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x18001448f  mov     [rbp+var_20], 0Ch
0x180014496  mov     [rsp+80h+TokenType], 2; TokenType
0x18001449e  call    cs:__imp_NtDuplicateToken
0x1800144a4  test    eax, eax
0x1800144a6  js      short loc_1800144B1
0x1800144a8  mov     rcx, [rbx]
0x1800144ab  call    cs:__imp_LsaIAdjustTokenObjectIntegrity
0x1800144b1  mov     rcx, [rbp+var_10]
0x1800144b5  xor     rcx, rsp; StackCookie
0x1800144b8  call    __security_check_cookie
0x1800144bd  mov     rbx, [rsp+80h+arg_18]
0x1800144c5  add     rsp, 80h
0x1800144cc  pop     rbp
0x1800144cd  retn
```
