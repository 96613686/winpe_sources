# NetpGetDomainNameExExEx

- ea: `0x180090994`
- end: `0x180090b71`
- name: `NetpGetDomainNameExExEx`
- size: `477`
- prototype: `__int64 __usercall@<rax>(LPVOID *Buffer@<rcx>, LPVOID *@<rdx>, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180034970`
- `0x18004d9d0`

## callees

- `0x180090994`
- `0x1800cda62`

## import_xrefs

- `ADVAPI32!LsaOpenPolicy` at `0x180090a0e`
- `ADVAPI32!LsaOpenPolicy` at `0x180090a0e`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x180090aa3`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x180090aa3`
- `ADVAPI32!LsaFreeMemory` at `0x180090a5f`
- `ADVAPI32!LsaFreeMemory` at `0x180090a5f`
- `ADVAPI32!LsaClose` at `0x180090a74`
- `ADVAPI32!LsaClose` at `0x180090a74`
- `netutils!NetApiBufferAllocate` at `0x180090ac4`
- `netutils!NetApiBufferAllocate` at `0x180090b1a`
- `netutils!NetApiBufferAllocate` at `0x180090ac4`
- `netutils!NetApiBufferAllocate` at `0x180090b1a`
- `netutils!NetApiBufferFree` at `0x180090a2b`
- `netutils!NetApiBufferFree` at `0x180090a47`
- `netutils!NetApiBufferFree` at `0x180090a2b`
- `netutils!NetApiBufferFree` at `0x180090a47`

## pseudocode

```c
__int64 __fastcall NetpGetDomainNameExExEx(LPVOID *Buffer, LPVOID *a2, __int64 a3, __int64 a4, bool *a5)
{
  DWORD v8; // ebx
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+80h] [rbp+30h] BYREF
  PVOID Buffera; // [rsp+88h] [rbp+38h] BYREF

  PolicyHandle = 0;
  Buffera = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  if ( !Buffer )
    return 87;
  *Buffer = 0;
  if ( a2 )
    *a2 = 0;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle) < 0
    || LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffera) < 0 )
  {
    v8 = 2146;
    goto LABEL_7;
  }
  v8 = NetApiBufferAllocate(*(unsigned __int16 *)Buffera + 2, Buffer);
  if ( v8 )
    goto LABEL_7;
  memcpy_0(*Buffer, *((const void **)Buffera + 1), *(unsigned __int16 *)Buffera);
  *((_WORD *)*Buffer + ((unsigned __int64)*(unsigned __int16 *)Buffera >> 1)) = 0;
  if ( !a2 || !*((_WORD *)Buffera + 8) )
    goto LABEL_23;
  v8 = NetApiBufferAllocate(*((unsigned __int16 *)Buffera + 8) + 2, a2);
  if ( v8 )
  {
LABEL_7:
    if ( *Buffer )
    {
      NetApiBufferFree(*Buffer);
      *Buffer = 0;
    }
    if ( a2 && *a2 )
    {
      NetApiBufferFree(*a2);
      *a2 = 0;
    }
    goto LABEL_12;
  }
  memcpy_0(*a2, *((const void **)Buffera + 3), *((unsigned __int16 *)Buffera + 8));
  *((_WORD *)*a2 + ((unsigned __int64)*((unsigned __int16 *)Buffera + 8) >> 1)) = 0;
LABEL_23:
  v8 = 0;
  *a5 = *((_QWORD *)Buffera + 8) == 0;
LABEL_12:
  if ( Buffera )
    LsaFreeMemory(Buffera);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v8;
}

```

## disassembly

```asm
0x180090994  mov     rax, rsp
0x180090997  mov     [rax+8], rbx
0x18009099b  mov     [rax+10h], rsi
0x18009099f  mov     [rax+20h], r9
0x1800909a3  mov     [rax+18h], r8
0x1800909a7  push    rbp
0x1800909a8  push    rdi
0x1800909a9  push    r14
0x1800909ab  mov     rbp, rsp
0x1800909ae  sub     rsp, 50h
0x1800909b2  xor     r14d, r14d
0x1800909b5  mov     rdi, rdx
0x1800909b8  mov     [rbp+PolicyHandle], r14
0x1800909bc  mov     rsi, rcx
0x1800909bf  mov     [rbp+Buffer], r14
0x1800909c3  mov     dword ptr [rbp+ObjectAttributes+4], r14d
0x1800909c7  mov     dword ptr [rbp+ObjectAttributes+1Ch], r14d
0x1800909cb  test    rcx, rcx
0x1800909ce  jnz     short loc_1800909D8
0x1800909d0  lea     eax, [rcx+57h]
0x1800909d3  jmp     loc_180090A82
0x1800909d8  mov     [rcx], r14
0x1800909db  test    rdi, rdi
0x1800909de  jz      short loc_1800909E3
0x1800909e0  mov     [rdx], r14
0x1800909e3  xorps   xmm0, xmm0
0x1800909e6  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800909ed  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800909f1  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x1800909f5  mov     r8d, 1; DesiredAccess
0x1800909fb  mov     [rbp+ObjectAttributes.Attributes], r14d
0x1800909ff  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180090a03  mov     [rbp+ObjectAttributes.ObjectName], r14
0x180090a07  xor     ecx, ecx; SystemName
0x180090a09  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180090a0e  call    cs:__imp_LsaOpenPolicy
0x180090a15  nop     dword ptr [rax+rax+00h]
0x180090a1a  test    eax, eax
0x180090a1c  jns     short loc_180090A96
0x180090a1e  mov     ebx, 862h
0x180090a23  mov     rcx, [rsi]; Buffer
0x180090a26  test    rcx, rcx
0x180090a29  jz      short loc_180090A3A
0x180090a2b  call    cs:__imp_NetApiBufferFree
0x180090a32  nop     dword ptr [rax+rax+00h]
0x180090a37  mov     [rsi], r14
0x180090a3a  test    rdi, rdi
0x180090a3d  jz      short loc_180090A56
0x180090a3f  mov     rcx, [rdi]; Buffer
0x180090a42  test    rcx, rcx
0x180090a45  jz      short loc_180090A56
0x180090a47  call    cs:__imp_NetApiBufferFree
0x180090a4e  nop     dword ptr [rax+rax+00h]
0x180090a53  mov     [rdi], r14
0x180090a56  mov     rcx, [rbp+Buffer]; Buffer
0x180090a5a  test    rcx, rcx
0x180090a5d  jz      short loc_180090A6B
0x180090a5f  call    cs:__imp_LsaFreeMemory
0x180090a66  nop     dword ptr [rax+rax+00h]
0x180090a6b  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180090a6f  test    rcx, rcx
0x180090a72  jz      short loc_180090A80
0x180090a74  call    cs:__imp_LsaClose
0x180090a7b  nop     dword ptr [rax+rax+00h]
0x180090a80  mov     eax, ebx
0x180090a82  mov     rbx, [rsp+50h+arg_0]
0x180090a87  mov     rsi, [rsp+50h+arg_8]
0x180090a8c  add     rsp, 50h
0x180090a90  pop     r14
0x180090a92  pop     rdi
0x180090a93  pop     rbp
0x180090a94  retn
0x180090a96  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180090a9a  lea     r8, [rbp+Buffer]; Buffer
0x180090a9e  mov     edx, 0Ch; InformationClass
0x180090aa3  call    cs:__imp_LsaQueryInformationPolicy
0x180090aaa  nop     dword ptr [rax+rax+00h]
0x180090aaf  test    eax, eax
0x180090ab1  js      loc_180090A1E
0x180090ab7  mov     rax, [rbp+Buffer]
0x180090abb  mov     rdx, rsi; Buffer
0x180090abe  movzx   ecx, word ptr [rax]
0x180090ac1  add     ecx, 2; ByteCount
0x180090ac4  call    cs:__imp_NetApiBufferAllocate
0x180090acb  nop     dword ptr [rax+rax+00h]
0x180090ad0  mov     ebx, eax
0x180090ad2  test    eax, eax
0x180090ad4  jnz     loc_180090A23
0x180090ada  mov     rdx, [rbp+Buffer]
0x180090ade  mov     rcx, [rsi]; void *
0x180090ae1  movzx   r8d, word ptr [rdx]; Size
0x180090ae5  mov     rdx, [rdx+8]; Src
0x180090ae9  call    memcpy_0
0x180090aee  mov     rax, [rbp+Buffer]
0x180090af2  movzx   ecx, word ptr [rax]
0x180090af5  mov     rax, [rsi]
0x180090af8  shr     rcx, 1
0x180090afb  mov     [rax+rcx*2], r14w
0x180090b00  test    rdi, rdi
0x180090b03  jz      short loc_180090B58
0x180090b05  mov     rax, [rbp+Buffer]
0x180090b09  cmp     [rax+10h], r14w
0x180090b0e  jz      short loc_180090B58
0x180090b10  movzx   ecx, word ptr [rax+10h]
0x180090b14  mov     rdx, rdi; Buffer
0x180090b17  add     ecx, 2; ByteCount
0x180090b1a  call    cs:__imp_NetApiBufferAllocate
0x180090b21  nop     dword ptr [rax+rax+00h]
0x180090b26  mov     ebx, eax
0x180090b28  test    eax, eax
0x180090b2a  jnz     loc_180090A23
0x180090b30  mov     rdx, [rbp+Buffer]
0x180090b34  mov     rcx, [rdi]; void *
0x180090b37  movzx   r8d, word ptr [rdx+10h]; Size
0x180090b3c  mov     rdx, [rdx+18h]; Src
0x180090b40  call    memcpy_0
0x180090b45  mov     rax, [rbp+Buffer]
0x180090b49  movzx   ecx, word ptr [rax+10h]
0x180090b4d  mov     rax, [rdi]
0x180090b50  shr     rcx, 1
0x180090b53  mov     [rax+rcx*2], r14w
0x180090b58  mov     rax, [rbp+Buffer]
0x180090b5c  mov     ebx, r14d
0x180090b5f  cmp     [rax+40h], r14
0x180090b63  mov     rax, [rbp+arg_20]
0x180090b67  setz    cl
0x180090b6a  mov     [rax], cl
0x180090b6c  jmp     loc_180090A56
```
