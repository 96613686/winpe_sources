# NetpGetDomainNameExExEx

- ea: `0x1800847f4`
- end: `0x180084a7e`
- name: `NetpGetDomainNameExExEx`
- size: `650`
- prototype: `__int64 __fastcall(LPVOID *Buffer, LPVOID *, LPVOID *, LPVOID *, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800160d0`
- `0x180039204`
- `0x1800393f4`

## callees

- `0x1800847f4`
- `0x180089ab4`

## import_xrefs

- `ntdll!RtlCompareMemoryUlong` at `0x180084a36`
- `ntdll!RtlCompareMemoryUlong` at `0x180084a36`
- `netutils!NetApiBufferFree` at `0x18008489a`
- `netutils!NetApiBufferFree` at `0x1800848b0`
- `netutils!NetApiBufferFree` at `0x1800848c6`
- `netutils!NetApiBufferFree` at `0x1800848dc`
- `netutils!NetApiBufferFree` at `0x18008489a`
- `netutils!NetApiBufferFree` at `0x1800848b0`
- `netutils!NetApiBufferFree` at `0x1800848c6`
- `netutils!NetApiBufferFree` at `0x1800848dc`
- `netutils!NetApiBufferAllocate` at `0x180084946`
- `netutils!NetApiBufferAllocate` at `0x180084996`
- `netutils!NetApiBufferAllocate` at `0x1800849e8`
- `netutils!NetApiBufferAllocate` at `0x180084a46`
- `netutils!NetApiBufferAllocate` at `0x180084946`
- `netutils!NetApiBufferAllocate` at `0x180084996`
- `netutils!NetApiBufferAllocate` at `0x1800849e8`
- `netutils!NetApiBufferAllocate` at `0x180084a46`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18008487f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18008487f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18008492b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18008492b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800848ee`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800848ee`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800848fd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800848fd`

## pseudocode

```c
__int64 __fastcall NetpGetDomainNameExExEx(LPVOID *Buffer, LPVOID *a2, LPVOID *a3, LPVOID *a4, bool *a5)
{
  DWORD v10; // ebx
  PVOID PolicyHandle; // [rsp+20h] [rbp-40h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+28h] [rbp-38h] BYREF
  PVOID Buffera; // [rsp+90h] [rbp+30h] BYREF

  PolicyHandle = 0;
  Buffera = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  if ( !Buffer )
    return 87;
  *Buffer = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle) < 0
    || LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffera) < 0 )
  {
    v10 = 2146;
    goto LABEL_11;
  }
  v10 = NetApiBufferAllocate(*(unsigned __int16 *)Buffera + 2, Buffer);
  if ( v10 )
    goto LABEL_11;
  memcpy_0(*Buffer, *((const void **)Buffera + 1), *(unsigned __int16 *)Buffera);
  *((_WORD *)*Buffer + ((unsigned __int64)*(unsigned __int16 *)Buffera >> 1)) = 0;
  if ( a2 && *((_WORD *)Buffera + 8) )
  {
    v10 = NetApiBufferAllocate(*((unsigned __int16 *)Buffera + 8) + 2, a2);
    if ( v10 )
      goto LABEL_11;
    memcpy_0(*a2, *((const void **)Buffera + 3), *((unsigned __int16 *)Buffera + 8));
    *((_WORD *)*a2 + ((unsigned __int64)*((unsigned __int16 *)Buffera + 8) >> 1)) = 0;
  }
  if ( a3 && *((_WORD *)Buffera + 16) )
  {
    v10 = NetApiBufferAllocate(*((unsigned __int16 *)Buffera + 16) + 2, a3);
    if ( v10 )
      goto LABEL_11;
    memcpy_0(*a3, *((const void **)Buffera + 5), *((unsigned __int16 *)Buffera + 16));
    *((_WORD *)*a3 + ((unsigned __int64)*((unsigned __int16 *)Buffera + 16) >> 1)) = 0;
  }
  if ( !a4 || RtlCompareMemoryUlong((char *)Buffera + 48, 0x10u, 0) == 16 )
    goto LABEL_41;
  v10 = NetApiBufferAllocate(0x10u, a4);
  if ( v10 )
  {
LABEL_11:
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
    if ( a3 && *a3 )
    {
      NetApiBufferFree(*a3);
      *a3 = 0;
    }
    if ( a4 && *a4 )
    {
      NetApiBufferFree(*a4);
      *a4 = 0;
    }
    goto LABEL_22;
  }
  *(_OWORD *)*a4 = *((_OWORD *)Buffera + 3);
LABEL_41:
  v10 = 0;
  *a5 = *((_QWORD *)Buffera + 8) == 0;
LABEL_22:
  if ( Buffera )
    LsaFreeMemory(Buffera);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v10;
}

```

## disassembly

```asm
0x1800847f4  mov     [rsp-28h+arg_8], rbx
0x1800847f9  mov     [rsp-28h+arg_10], rsi
0x1800847fe  push    rbp
0x1800847ff  push    rdi
0x180084800  push    r12
0x180084802  push    r14
0x180084804  push    r15
0x180084806  mov     rbp, rsp
0x180084809  sub     rsp, 60h
0x18008480d  xor     r12d, r12d
0x180084810  mov     rdi, r9
0x180084813  mov     [rbp+PolicyHandle], r12
0x180084817  mov     rsi, r8
0x18008481a  mov     [rbp+Buffer], r12
0x18008481e  mov     r14, rdx
0x180084821  mov     dword ptr [rbp+ObjectAttributes+4], r12d
0x180084825  mov     r15, rcx
0x180084828  mov     dword ptr [rbp+ObjectAttributes+1Ch], r12d
0x18008482c  test    rcx, rcx
0x18008482f  jnz     short loc_180084839
0x180084831  lea     eax, [rcx+57h]
0x180084834  jmp     loc_180084905
0x180084839  mov     [rcx], r12
0x18008483c  test    r14, r14
0x18008483f  jz      short loc_180084844
0x180084841  mov     [rdx], r12
0x180084844  test    rsi, rsi
0x180084847  jz      short loc_18008484C
0x180084849  mov     [r8], r12
0x18008484c  test    rdi, rdi
0x18008484f  jz      short loc_180084854
0x180084851  mov     [r9], r12
0x180084854  xorps   xmm0, xmm0
0x180084857  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18008485e  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180084862  mov     [rbp+ObjectAttributes.RootDirectory], r12
0x180084866  mov     r8d, 1; DesiredAccess
0x18008486c  mov     [rbp+ObjectAttributes.Attributes], r12d
0x180084870  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180084874  mov     [rbp+ObjectAttributes.ObjectName], r12
0x180084878  xor     ecx, ecx; SystemName
0x18008487a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18008487f  call    cs:__imp_LsaOpenPolicy
0x180084885  test    eax, eax
0x180084887  jns     loc_18008491E
0x18008488d  mov     ebx, 862h
0x180084892  mov     rcx, [r15]; Buffer
0x180084895  test    rcx, rcx
0x180084898  jz      short loc_1800848A3
0x18008489a  call    cs:__imp_NetApiBufferFree
0x1800848a0  mov     [r15], r12
0x1800848a3  test    r14, r14
0x1800848a6  jz      short loc_1800848B9
0x1800848a8  mov     rcx, [r14]; Buffer
0x1800848ab  test    rcx, rcx
0x1800848ae  jz      short loc_1800848B9
0x1800848b0  call    cs:__imp_NetApiBufferFree
0x1800848b6  mov     [r14], r12
0x1800848b9  test    rsi, rsi
0x1800848bc  jz      short loc_1800848CF
0x1800848be  mov     rcx, [rsi]; Buffer
0x1800848c1  test    rcx, rcx
0x1800848c4  jz      short loc_1800848CF
0x1800848c6  call    cs:__imp_NetApiBufferFree
0x1800848cc  mov     [rsi], r12
0x1800848cf  test    rdi, rdi
0x1800848d2  jz      short loc_1800848E5
0x1800848d4  mov     rcx, [rdi]; Buffer
0x1800848d7  test    rcx, rcx
0x1800848da  jz      short loc_1800848E5
0x1800848dc  call    cs:__imp_NetApiBufferFree
0x1800848e2  mov     [rdi], r12
0x1800848e5  mov     rcx, [rbp+Buffer]; Buffer
0x1800848e9  test    rcx, rcx
0x1800848ec  jz      short loc_1800848F4
0x1800848ee  call    cs:__imp_LsaFreeMemory
0x1800848f4  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800848f8  test    rcx, rcx
0x1800848fb  jz      short loc_180084903
0x1800848fd  call    cs:__imp_LsaClose
0x180084903  mov     eax, ebx
0x180084905  lea     r11, [rsp+60h+var_s0]
0x18008490a  mov     rbx, [r11+38h]
0x18008490e  mov     rsi, [r11+40h]
0x180084912  mov     rsp, r11
0x180084915  pop     r15
0x180084917  pop     r14
0x180084919  pop     r12
0x18008491b  pop     rdi
0x18008491c  pop     rbp
0x18008491d  retn
0x18008491e  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180084922  lea     r8, [rbp+Buffer]; Buffer
0x180084926  mov     edx, 0Ch; InformationClass
0x18008492b  call    cs:__imp_LsaQueryInformationPolicy
0x180084931  test    eax, eax
0x180084933  js      loc_18008488D
0x180084939  mov     rax, [rbp+Buffer]
0x18008493d  mov     rdx, r15; Buffer
0x180084940  movzx   ecx, word ptr [rax]
0x180084943  add     ecx, 2; ByteCount
0x180084946  call    cs:__imp_NetApiBufferAllocate
0x18008494c  mov     ebx, eax
0x18008494e  test    eax, eax
0x180084950  jnz     loc_180084892
0x180084956  mov     rdx, [rbp+Buffer]
0x18008495a  mov     rcx, [r15]; void *
0x18008495d  movzx   r8d, word ptr [rdx]; Size
0x180084961  mov     rdx, [rdx+8]; Src
0x180084965  call    memcpy_0
0x18008496a  mov     rax, [rbp+Buffer]
0x18008496e  mov     rcx, [r15]
0x180084971  movzx   edx, word ptr [rax]
0x180084974  shr     rdx, 1
0x180084977  mov     [rcx+rdx*2], r12w
0x18008497c  test    r14, r14
0x18008497f  jz      short loc_1800849CE
0x180084981  mov     rax, [rbp+Buffer]
0x180084985  cmp     [rax+10h], r12w
0x18008498a  jz      short loc_1800849CE
0x18008498c  movzx   ecx, word ptr [rax+10h]
0x180084990  mov     rdx, r14; Buffer
0x180084993  add     ecx, 2; ByteCount
0x180084996  call    cs:__imp_NetApiBufferAllocate
0x18008499c  mov     ebx, eax
0x18008499e  test    eax, eax
0x1800849a0  jnz     loc_180084892
0x1800849a6  mov     rdx, [rbp+Buffer]
0x1800849aa  mov     rcx, [r14]; void *
0x1800849ad  movzx   r8d, word ptr [rdx+10h]; Size
0x1800849b2  mov     rdx, [rdx+18h]; Src
0x1800849b6  call    memcpy_0
0x1800849bb  mov     rax, [rbp+Buffer]
0x1800849bf  mov     rcx, [r14]
0x1800849c2  movzx   edx, word ptr [rax+10h]
0x1800849c6  shr     rdx, 1
0x1800849c9  mov     [rcx+rdx*2], r12w
0x1800849ce  test    rsi, rsi
0x1800849d1  jz      short loc_180084A20
0x1800849d3  mov     rax, [rbp+Buffer]
0x1800849d7  cmp     [rax+20h], r12w
0x1800849dc  jz      short loc_180084A20
0x1800849de  movzx   ecx, word ptr [rax+20h]
0x1800849e2  mov     rdx, rsi; Buffer
0x1800849e5  add     ecx, 2; ByteCount
0x1800849e8  call    cs:__imp_NetApiBufferAllocate
0x1800849ee  mov     ebx, eax
0x1800849f0  test    eax, eax
0x1800849f2  jnz     loc_180084892
0x1800849f8  mov     rdx, [rbp+Buffer]
0x1800849fc  mov     rcx, [rsi]; void *
0x1800849ff  movzx   r8d, word ptr [rdx+20h]; Size
0x180084a04  mov     rdx, [rdx+28h]; Src
0x180084a08  call    memcpy_0
0x180084a0d  mov     rax, [rbp+Buffer]
0x180084a11  mov     rcx, [rsi]
0x180084a14  movzx   edx, word ptr [rax+20h]
0x180084a18  shr     rdx, 1
0x180084a1b  mov     [rcx+rdx*2], r12w
0x180084a20  test    rdi, rdi
0x180084a23  jz      short loc_180084A65
0x180084a25  mov     rcx, [rbp+Buffer]
0x180084a29  xor     r8d, r8d; Pattern
0x180084a2c  add     rcx, 30h ; '0'; Source
0x180084a30  lea     ebx, [r8+10h]
0x180084a34  mov     edx, ebx; Length
0x180084a36  call    cs:__imp_RtlCompareMemoryUlong
0x180084a3c  cmp     rax, rbx
0x180084a3f  jz      short loc_180084A65
0x180084a41  mov     rdx, rdi; Buffer
0x180084a44  mov     ecx, ebx; ByteCount
0x180084a46  call    cs:__imp_NetApiBufferAllocate
0x180084a4c  mov     ebx, eax
0x180084a4e  test    eax, eax
0x180084a50  jnz     loc_180084892
0x180084a56  mov     rax, [rbp+Buffer]
0x180084a5a  mov     rcx, [rdi]
0x180084a5d  movups  xmm0, xmmword ptr [rax+30h]
0x180084a61  movdqu  xmmword ptr [rcx], xmm0
0x180084a65  mov     rax, [rbp+Buffer]
0x180084a69  mov     ebx, r12d
0x180084a6c  cmp     [rax+40h], r12
0x180084a70  mov     rax, [rbp+arg_20]
0x180084a74  setz    cl
0x180084a77  mov     [rax], cl
0x180084a79  jmp     loc_1800848E5
```
