# _QueryIsDomainMember

- ea: `0x18001de54`
- end: `0x18001defe`
- name: `_QueryIsDomainMember`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001dbfc`

## callees

- `0x180013b20`
- `0x18001ddb0`
- `0x18001de54`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001ded3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001ded3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001dee1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001dee1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18001deaf`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18001deaf`

## pseudocode

```c
ULONG __fastcall QueryIsDomainMember(BOOL *a1)
{
  BOOL v2; // ebx
  ULONG result; // eax
  PVOID v4; // rcx
  LSA_HANDLE PolicyHandle; // [rsp+20h] [rbp-38h] BYREF
  PVOID Buffer; // [rsp+28h] [rbp-30h] BYREF
  _SECURITY_QUALITY_OF_SERVICE v7; // [rsp+30h] [rbp-28h] BYREF

  *(_DWORD *)&v7.ContextTrackingMode = 1;
  PolicyHandle = 0;
  v7.Length = 12;
  v7.ImpersonationLevel = SecurityImpersonation;
  v2 = 1;
  result = LsaOpenLocalSystemPolicy((__int64)a1, &v7, &PolicyHandle);
  if ( !result )
  {
    Buffer = 0;
    if ( LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer) < 0 )
    {
      *a1 = 0;
    }
    else
    {
      v4 = Buffer;
      if ( !*((_WORD *)Buffer + 8) && !*((_WORD *)Buffer + 16) )
        v2 = *((_QWORD *)Buffer + 8) != 0;
      *a1 = v2;
      LsaFreeMemory(v4);
    }
    LsaClose(PolicyHandle);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001de54  push    rbp
0x18001de56  push    rbx
0x18001de57  push    rsi
0x18001de58  push    rdi
0x18001de59  mov     rbp, rsp
0x18001de5c  sub     rsp, 58h
0x18001de60  mov     rax, cs:__security_cookie
0x18001de67  xor     rax, rsp
0x18001de6a  mov     [rbp+var_18], rax
0x18001de6e  xor     esi, esi
0x18001de70  mov     dword ptr [rbp+var_28.ContextTrackingMode], 1
0x18001de77  lea     r8, [rbp+PolicyHandle]; void **
0x18001de7b  mov     [rbp+PolicyHandle], rsi
0x18001de7f  lea     rdx, [rbp+var_28]; struct _SECURITY_QUALITY_OF_SERVICE *
0x18001de83  mov     [rbp+var_28.Length], 0Ch
0x18001de8a  mov     rdi, rcx
0x18001de8d  mov     [rbp+var_28.ImpersonationLevel], 2
0x18001de94  lea     ebx, [rsi+1]
0x18001de97  call    ?LsaOpenLocalSystemPolicy@@YAKKPEAU_SECURITY_QUALITY_OF_SERVICE@@PEAPEAX@Z; LsaOpenLocalSystemPolicy(ulong,_SECURITY_QUALITY_OF_SERVICE *,void * *)
0x18001de9c  test    eax, eax
0x18001de9e  jnz     short loc_18001DEE9
0x18001dea0  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18001dea4  lea     r8, [rbp+Buffer]; Buffer
0x18001dea8  lea     edx, [rsi+0Ch]; InformationClass
0x18001deab  mov     [rbp+Buffer], rsi
0x18001deaf  call    cs:__imp_LsaQueryInformationPolicy
0x18001deb5  test    eax, eax
0x18001deb7  js      short loc_18001DEDB
0x18001deb9  mov     rcx, [rbp+Buffer]; Buffer
0x18001debd  cmp     [rcx+10h], si
0x18001dec1  jnz     short loc_18001DED1
0x18001dec3  cmp     [rcx+20h], si
0x18001dec7  jnz     short loc_18001DED1
0x18001dec9  cmp     [rcx+40h], rsi
0x18001decd  jnz     short loc_18001DED1
0x18001decf  mov     ebx, esi
0x18001ded1  mov     [rdi], ebx
0x18001ded3  call    cs:__imp_LsaFreeMemory
0x18001ded9  jmp     short loc_18001DEDD
0x18001dedb  mov     [rdi], esi
0x18001dedd  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18001dee1  call    cs:__imp_LsaClose
0x18001dee7  mov     eax, esi
0x18001dee9  mov     rcx, [rbp+var_18]
0x18001deed  xor     rcx, rsp; StackCookie
0x18001def0  call    __security_check_cookie
0x18001def5  add     rsp, 58h
0x18001def9  pop     rdi
0x18001defa  pop     rsi
0x18001defb  pop     rbx
0x18001defc  pop     rbp
0x18001defd  retn
```
