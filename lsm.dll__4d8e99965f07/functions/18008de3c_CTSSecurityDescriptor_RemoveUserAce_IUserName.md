# CTSSecurityDescriptor::RemoveUserAce(IUserName *)

- ea: `0x18008de3c`
- end: `0x18008dfb0`
- name: `?RemoveUserAce@CTSSecurityDescriptor@@QEAAJPEAUIUserName@@@Z`
- size: `372`
- prototype: `__int64 __fastcall(CTSSecurityDescriptor *__hidden this, struct IUserName *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006e8f0`

## callees

- `0x18004e850`
- `0x18008de3c`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18008df4c`
- `ntdll!RtlEqualSid` at `0x18008df4c`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18008ded0`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18008ded0`
- `ntdll!RtlDeleteAce` at `0x18008df66`
- `ntdll!RtlDeleteAce` at `0x18008df66`
- `ntdll!RtlQueryInformationAcl` at `0x18008df05`
- `ntdll!RtlQueryInformationAcl` at `0x18008df05`
- `ntdll!RtlGetAce` at `0x18008df26`
- `ntdll!RtlGetAce` at `0x18008df26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008df83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008df83`

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
0x18008de3c  mov     [rsp-8+arg_10], rbx
0x18008de41  mov     [rsp-8+arg_18], rdi
0x18008de46  push    rbp
0x18008de47  mov     rbp, rsp
0x18008de4a  sub     rsp, 60h
0x18008de4e  mov     rax, cs:__security_cookie
0x18008de55  xor     rax, rsp
0x18008de58  mov     [rbp+var_10], rax
0x18008de5c  xor     eax, eax
0x18008de5e  mov     [rbp+Dacl], 0
0x18008de66  mov     [rbp+Information], rax
0x18008de6a  mov     r8, rdx
0x18008de6d  mov     [rbp+var_18], eax
0x18008de70  mov     rdi, rcx
0x18008de73  mov     [rbp+Ace], rax
0x18008de77  mov     rcx, r8
0x18008de7a  mov     [rbp+Sid1], rax
0x18008de7e  mov     rax, [rdx]
0x18008de81  lea     rdx, [rbp+Sid1]
0x18008de85  mov     [rbp+DaclPresent], 0
0x18008de89  mov     [rbp+DaclDefaulted], 0
0x18008de8d  mov     rax, [rax+48h]
0x18008de91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008de96  mov     ebx, eax
0x18008de98  test    eax, eax
0x18008de9a  js      loc_18008DF7A
0x18008dea0  mov     rcx, [rdi+8]; SecurityDescriptor
0x18008dea4  test    rcx, rcx
0x18008dea7  jnz     short loc_18008DEB3
0x18008dea9  mov     ebx, 80004005h
0x18008deae  jmp     loc_18008DF7A
0x18008deb3  cmp     [rbp+Sid1], 0
0x18008deb8  jnz     short loc_18008DEC4
0x18008deba  mov     ebx, 0D00A0015h
0x18008debf  jmp     loc_18008DF8F
0x18008dec4  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x18008dec8  lea     r8, [rbp+Dacl]; Dacl
0x18008decc  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x18008ded0  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18008ded7  nop     dword ptr [rax+rax+00h]
0x18008dedc  test    eax, eax
0x18008dede  js      loc_18008DF74
0x18008dee4  cmp     [rbp+DaclPresent], 0
0x18008dee8  jz      loc_18008DF74
0x18008deee  mov     rcx, [rbp+Dacl]; Acl
0x18008def2  test    rcx, rcx
0x18008def5  jz      short loc_18008DF74
0x18008def7  mov     r9d, 2; InformationClass
0x18008defd  lea     rdx, [rbp+Information]; Information
0x18008df01  lea     r8d, [r9+0Ah]; InformationLength
0x18008df05  call    cs:__imp_RtlQueryInformationAcl
0x18008df0c  nop     dword ptr [rax+rax+00h]
0x18008df11  test    eax, eax
0x18008df13  js      short loc_18008DF74
0x18008df15  xor     edi, edi
0x18008df17  cmp     edi, dword ptr [rbp+Information]
0x18008df1a  jnb     short loc_18008DF7A
0x18008df1c  mov     rcx, [rbp+Dacl]; Acl
0x18008df20  lea     r8, [rbp+Ace]; Ace
0x18008df24  mov     edx, edi; AceIndex
0x18008df26  call    cs:__imp_RtlGetAce
0x18008df2d  nop     dword ptr [rax+rax+00h]
0x18008df32  mov     rdx, [rbp+Ace]
0x18008df36  cmp     byte ptr [rdx], 0
0x18008df39  jnz     short loc_18008DF5C
0x18008df3b  cmp     dword ptr [rdx+4], 3BFh
0x18008df42  jnz     short loc_18008DF5C
0x18008df44  mov     rcx, [rbp+Sid1]; Sid1
0x18008df48  add     rdx, 8; Sid2
0x18008df4c  call    cs:__imp_RtlEqualSid
0x18008df53  nop     dword ptr [rax+rax+00h]
0x18008df58  test    al, al
0x18008df5a  jnz     short loc_18008DF60
0x18008df5c  inc     edi
0x18008df5e  jmp     short loc_18008DF17
0x18008df60  mov     rcx, [rbp+Dacl]; Acl
0x18008df64  mov     edx, edi; AceIndex
0x18008df66  call    cs:__imp_RtlDeleteAce
0x18008df6d  nop     dword ptr [rax+rax+00h]
0x18008df72  jmp     short loc_18008DF7A
0x18008df74  mov     ebx, eax
0x18008df76  bts     ebx, 1Ch
0x18008df7a  mov     rcx, [rbp+Sid1]; pv
0x18008df7e  test    rcx, rcx
0x18008df81  jz      short loc_18008DF8F
0x18008df83  call    cs:__imp_CoTaskMemFree
0x18008df8a  nop     dword ptr [rax+rax+00h]
0x18008df8f  mov     eax, ebx
0x18008df91  mov     rcx, [rbp+var_10]
0x18008df95  xor     rcx, rsp; StackCookie
0x18008df98  call    __security_check_cookie
0x18008df9d  lea     r11, [rsp+60h+var_s0]
0x18008dfa2  mov     rbx, [r11+20h]
0x18008dfa6  mov     rdi, [r11+28h]
0x18008dfaa  mov     rsp, r11
0x18008dfad  pop     rbp
0x18008dfae  retn
```
