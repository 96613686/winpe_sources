# CTSSecurityDescriptor::RemoveUserAce(IUserName *)

- ea: `0x180089120`
- end: `0x180089267`
- name: `?RemoveUserAce@CTSSecurityDescriptor@@QEAAJPEAUIUserName@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(CTSSecurityDescriptor *__hidden this, struct IUserName *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006aaa0`

## callees

- `0x18004b460`
- `0x180089120`
- `0x180097010`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180089216`
- `ntdll!RtlEqualSid` at `0x180089216`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1800891b4`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1800891b4`
- `ntdll!RtlDeleteAce` at `0x18008922a`
- `ntdll!RtlDeleteAce` at `0x18008922a`
- `ntdll!RtlQueryInformationAcl` at `0x1800891db`
- `ntdll!RtlQueryInformationAcl` at `0x1800891db`
- `ntdll!RtlGetAce` at `0x1800891f6`
- `ntdll!RtlGetAce` at `0x1800891f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089241`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089241`

## pseudocode

```c
__int64 __fastcall CTSSecurityDescriptor::RemoveUserAce(CTSSecurityDescriptor *this, struct IUserName *a2)
{
  __int64 v3; // rax
  int v4; // ebx
  void *v5; // rcx
  NTSTATUS DaclSecurityDescriptor; // eax
  ULONG i; // edi
  unsigned __int8 DaclPresent; // [rsp+20h] [rbp-40h] BYREF
  unsigned __int8 DaclDefaulted[7]; // [rsp+21h] [rbp-3Fh] BYREF
  PACL Dacl; // [rsp+28h] [rbp-38h] BYREF
  PSID Sid1; // [rsp+30h] [rbp-30h] BYREF
  PVOID Ace; // [rsp+38h] [rbp-28h] BYREF
  __int64 Information; // [rsp+40h] [rbp-20h] BYREF
  int v15; // [rsp+48h] [rbp-18h]

  Dacl = 0;
  Information = 0;
  v15 = 0;
  Ace = 0;
  Sid1 = 0;
  v3 = *(_QWORD *)a2;
  DaclPresent = 0;
  DaclDefaulted[0] = 0;
  v4 = (*(__int64 (__fastcall **)(struct IUserName *, PSID *))(v3 + 72))(a2, &Sid1);
  if ( v4 >= 0 )
  {
    v5 = (void *)*((_QWORD *)this + 1);
    if ( v5 )
    {
      if ( !Sid1 )
        return (unsigned int)-804650987;
      DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(v5, &DaclPresent, &Dacl, DaclDefaulted);
      if ( DaclSecurityDescriptor >= 0
        && DaclPresent
        && Dacl
        && (DaclSecurityDescriptor = RtlQueryInformationAcl(Dacl, &Information, 0xCu, AclSizeInformation),
            DaclSecurityDescriptor >= 0) )
      {
        for ( i = 0; i < (unsigned int)Information; ++i )
        {
          RtlGetAce(Dacl, i, &Ace);
          if ( !*(_BYTE *)Ace && *((_DWORD *)Ace + 1) == 959 && RtlEqualSid(Sid1, (char *)Ace + 8) )
          {
            RtlDeleteAce(Dacl, i);
            break;
          }
        }
      }
      else
      {
        v4 = DaclSecurityDescriptor | 0x10000000;
      }
    }
    else
    {
      v4 = -2147467259;
    }
  }
  if ( Sid1 )
    CoTaskMemFree(Sid1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180089120  mov     [rsp-8+arg_10], rbx
0x180089125  mov     [rsp-8+arg_18], rdi
0x18008912a  push    rbp
0x18008912b  mov     rbp, rsp
0x18008912e  sub     rsp, 60h
0x180089132  mov     rax, cs:__security_cookie
0x180089139  xor     rax, rsp
0x18008913c  mov     [rbp+var_10], rax
0x180089140  xor     eax, eax
0x180089142  mov     [rbp+Dacl], 0
0x18008914a  mov     [rbp+Information], rax
0x18008914e  mov     r8, rdx
0x180089151  mov     [rbp+var_18], eax
0x180089154  mov     rdi, rcx
0x180089157  mov     [rbp+Ace], rax
0x18008915b  mov     rcx, r8
0x18008915e  mov     [rbp+Sid1], rax
0x180089162  mov     rax, [rdx]
0x180089165  lea     rdx, [rbp+Sid1]
0x180089169  mov     [rbp+DaclPresent], 0
0x18008916d  mov     [rbp+DaclDefaulted], 0
0x180089171  mov     rax, [rax+48h]
0x180089175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008917a  mov     ebx, eax
0x18008917c  test    eax, eax
0x18008917e  js      loc_180089238
0x180089184  mov     rcx, [rdi+8]; SecurityDescriptor
0x180089188  test    rcx, rcx
0x18008918b  jnz     short loc_180089197
0x18008918d  mov     ebx, 80004005h
0x180089192  jmp     loc_180089238
0x180089197  cmp     [rbp+Sid1], 0
0x18008919c  jnz     short loc_1800891A8
0x18008919e  mov     ebx, 0D00A0015h
0x1800891a3  jmp     loc_180089247
0x1800891a8  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x1800891ac  lea     r8, [rbp+Dacl]; Dacl
0x1800891b0  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x1800891b4  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1800891ba  test    eax, eax
0x1800891bc  js      short loc_180089232
0x1800891be  cmp     [rbp+DaclPresent], 0
0x1800891c2  jz      short loc_180089232
0x1800891c4  mov     rcx, [rbp+Dacl]; Acl
0x1800891c8  test    rcx, rcx
0x1800891cb  jz      short loc_180089232
0x1800891cd  mov     r9d, 2; InformationClass
0x1800891d3  lea     rdx, [rbp+Information]; Information
0x1800891d7  lea     r8d, [r9+0Ah]; InformationLength
0x1800891db  call    cs:__imp_RtlQueryInformationAcl
0x1800891e1  test    eax, eax
0x1800891e3  js      short loc_180089232
0x1800891e5  xor     edi, edi
0x1800891e7  cmp     edi, dword ptr [rbp+Information]
0x1800891ea  jnb     short loc_180089238
0x1800891ec  mov     rcx, [rbp+Dacl]; Acl
0x1800891f0  lea     r8, [rbp+Ace]; Ace
0x1800891f4  mov     edx, edi; AceIndex
0x1800891f6  call    cs:__imp_RtlGetAce
0x1800891fc  mov     rdx, [rbp+Ace]
0x180089200  cmp     byte ptr [rdx], 0
0x180089203  jnz     short loc_180089220
0x180089205  cmp     dword ptr [rdx+4], 3BFh
0x18008920c  jnz     short loc_180089220
0x18008920e  mov     rcx, [rbp+Sid1]; Sid1
0x180089212  add     rdx, 8; Sid2
0x180089216  call    cs:__imp_RtlEqualSid
0x18008921c  test    al, al
0x18008921e  jnz     short loc_180089224
0x180089220  inc     edi
0x180089222  jmp     short loc_1800891E7
0x180089224  mov     rcx, [rbp+Dacl]; Acl
0x180089228  mov     edx, edi; AceIndex
0x18008922a  call    cs:__imp_RtlDeleteAce
0x180089230  jmp     short loc_180089238
0x180089232  mov     ebx, eax
0x180089234  bts     ebx, 1Ch
0x180089238  mov     rcx, [rbp+Sid1]; pv
0x18008923c  test    rcx, rcx
0x18008923f  jz      short loc_180089247
0x180089241  call    cs:__imp_CoTaskMemFree
0x180089247  mov     eax, ebx
0x180089249  mov     rcx, [rbp+var_10]
0x18008924d  xor     rcx, rsp; StackCookie
0x180089250  call    __security_check_cookie
0x180089255  lea     r11, [rsp+60h+var_s0]
0x18008925a  mov     rbx, [r11+20h]
0x18008925e  mov     rdi, [r11+28h]
0x180089262  mov     rsp, r11
0x180089265  pop     rbp
0x180089266  retn
```
