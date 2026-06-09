# NetpGetDomainNameExExEx

- ea: `0x1800907e4`
- end: `0x1800909c1`
- name: `NetpGetDomainNameExExEx`
- size: `477`
- prototype: `__int64 __usercall@<rax>(LPVOID *Buffer@<rcx>, LPVOID *@<rdx>, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180035328`
- `0x18004dd90`

## callees

- `0x1800907e4`
- `0x1800cc982`

## import_xrefs

- `ADVAPI32!LsaOpenPolicy` at `0x18009085e`
- `ADVAPI32!LsaOpenPolicy` at `0x18009085e`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1800908f3`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1800908f3`
- `ADVAPI32!LsaFreeMemory` at `0x1800908af`
- `ADVAPI32!LsaFreeMemory` at `0x1800908af`
- `ADVAPI32!LsaClose` at `0x1800908c4`
- `ADVAPI32!LsaClose` at `0x1800908c4`
- `netutils!NetApiBufferAllocate` at `0x180090914`
- `netutils!NetApiBufferAllocate` at `0x18009096a`
- `netutils!NetApiBufferAllocate` at `0x180090914`
- `netutils!NetApiBufferAllocate` at `0x18009096a`
- `netutils!NetApiBufferFree` at `0x18009087b`
- `netutils!NetApiBufferFree` at `0x180090897`
- `netutils!NetApiBufferFree` at `0x18009087b`
- `netutils!NetApiBufferFree` at `0x180090897`

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
0x1800907e4  mov     rax, rsp
0x1800907e7  mov     [rax+8], rbx
0x1800907eb  mov     [rax+10h], rsi
0x1800907ef  mov     [rax+20h], r9
0x1800907f3  mov     [rax+18h], r8
0x1800907f7  push    rbp
0x1800907f8  push    rdi
0x1800907f9  push    r14
0x1800907fb  mov     rbp, rsp
0x1800907fe  sub     rsp, 50h
0x180090802  xor     r14d, r14d
0x180090805  mov     rdi, rdx
0x180090808  mov     [rbp+PolicyHandle], r14
0x18009080c  mov     rsi, rcx
0x18009080f  mov     [rbp+Buffer], r14
0x180090813  mov     dword ptr [rbp+ObjectAttributes+4], r14d
0x180090817  mov     dword ptr [rbp+ObjectAttributes+1Ch], r14d
0x18009081b  test    rcx, rcx
0x18009081e  jnz     short loc_180090828
0x180090820  lea     eax, [rcx+57h]
0x180090823  jmp     loc_1800908D2
0x180090828  mov     [rcx], r14
0x18009082b  test    rdi, rdi
0x18009082e  jz      short loc_180090833
0x180090830  mov     [rdx], r14
0x180090833  xorps   xmm0, xmm0
0x180090836  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18009083d  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180090841  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x180090845  mov     r8d, 1; DesiredAccess
0x18009084b  mov     [rbp+ObjectAttributes.Attributes], r14d
0x18009084f  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180090853  mov     [rbp+ObjectAttributes.ObjectName], r14
0x180090857  xor     ecx, ecx; SystemName
0x180090859  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18009085e  call    cs:__imp_LsaOpenPolicy
0x180090865  nop     dword ptr [rax+rax+00h]
0x18009086a  test    eax, eax
0x18009086c  jns     short loc_1800908E6
0x18009086e  mov     ebx, 862h
0x180090873  mov     rcx, [rsi]; Buffer
0x180090876  test    rcx, rcx
0x180090879  jz      short loc_18009088A
0x18009087b  call    cs:__imp_NetApiBufferFree
0x180090882  nop     dword ptr [rax+rax+00h]
0x180090887  mov     [rsi], r14
0x18009088a  test    rdi, rdi
0x18009088d  jz      short loc_1800908A6
0x18009088f  mov     rcx, [rdi]; Buffer
0x180090892  test    rcx, rcx
0x180090895  jz      short loc_1800908A6
0x180090897  call    cs:__imp_NetApiBufferFree
0x18009089e  nop     dword ptr [rax+rax+00h]
0x1800908a3  mov     [rdi], r14
0x1800908a6  mov     rcx, [rbp+Buffer]; Buffer
0x1800908aa  test    rcx, rcx
0x1800908ad  jz      short loc_1800908BB
0x1800908af  call    cs:__imp_LsaFreeMemory
0x1800908b6  nop     dword ptr [rax+rax+00h]
0x1800908bb  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800908bf  test    rcx, rcx
0x1800908c2  jz      short loc_1800908D0
0x1800908c4  call    cs:__imp_LsaClose
0x1800908cb  nop     dword ptr [rax+rax+00h]
0x1800908d0  mov     eax, ebx
0x1800908d2  mov     rbx, [rsp+50h+arg_0]
0x1800908d7  mov     rsi, [rsp+50h+arg_8]
0x1800908dc  add     rsp, 50h
0x1800908e0  pop     r14
0x1800908e2  pop     rdi
0x1800908e3  pop     rbp
0x1800908e4  retn
0x1800908e6  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800908ea  lea     r8, [rbp+Buffer]; Buffer
0x1800908ee  mov     edx, 0Ch; InformationClass
0x1800908f3  call    cs:__imp_LsaQueryInformationPolicy
0x1800908fa  nop     dword ptr [rax+rax+00h]
0x1800908ff  test    eax, eax
0x180090901  js      loc_18009086E
0x180090907  mov     rax, [rbp+Buffer]
0x18009090b  mov     rdx, rsi; Buffer
0x18009090e  movzx   ecx, word ptr [rax]
0x180090911  add     ecx, 2; ByteCount
0x180090914  call    cs:__imp_NetApiBufferAllocate
0x18009091b  nop     dword ptr [rax+rax+00h]
0x180090920  mov     ebx, eax
0x180090922  test    eax, eax
0x180090924  jnz     loc_180090873
0x18009092a  mov     rdx, [rbp+Buffer]
0x18009092e  mov     rcx, [rsi]; void *
0x180090931  movzx   r8d, word ptr [rdx]; Size
0x180090935  mov     rdx, [rdx+8]; Src
0x180090939  call    memcpy_0
0x18009093e  mov     rax, [rbp+Buffer]
0x180090942  movzx   ecx, word ptr [rax]
0x180090945  mov     rax, [rsi]
0x180090948  shr     rcx, 1
0x18009094b  mov     [rax+rcx*2], r14w
0x180090950  test    rdi, rdi
0x180090953  jz      short loc_1800909A8
0x180090955  mov     rax, [rbp+Buffer]
0x180090959  cmp     [rax+10h], r14w
0x18009095e  jz      short loc_1800909A8
0x180090960  movzx   ecx, word ptr [rax+10h]
0x180090964  mov     rdx, rdi; Buffer
0x180090967  add     ecx, 2; ByteCount
0x18009096a  call    cs:__imp_NetApiBufferAllocate
0x180090971  nop     dword ptr [rax+rax+00h]
0x180090976  mov     ebx, eax
0x180090978  test    eax, eax
0x18009097a  jnz     loc_180090873
0x180090980  mov     rdx, [rbp+Buffer]
0x180090984  mov     rcx, [rdi]; void *
0x180090987  movzx   r8d, word ptr [rdx+10h]; Size
0x18009098c  mov     rdx, [rdx+18h]; Src
0x180090990  call    memcpy_0
0x180090995  mov     rax, [rbp+Buffer]
0x180090999  movzx   ecx, word ptr [rax+10h]
0x18009099d  mov     rax, [rdi]
0x1800909a0  shr     rcx, 1
0x1800909a3  mov     [rax+rcx*2], r14w
0x1800909a8  mov     rax, [rbp+Buffer]
0x1800909ac  mov     ebx, r14d
0x1800909af  cmp     [rax+40h], r14
0x1800909b3  mov     rax, [rbp+arg_20]
0x1800909b7  setz    cl
0x1800909ba  mov     [rax], cl
0x1800909bc  jmp     loc_1800908A6
```
