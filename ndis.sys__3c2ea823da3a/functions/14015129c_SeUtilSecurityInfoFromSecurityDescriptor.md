# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x14015129c`
- end: `0x140151395`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401501c4`
- `0x140150dcc`

## callees

- `0x14015129c`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14015135e`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14015135e`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1401512e2`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1401512e2`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14015130d`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14015130d`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140151336`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140151336`

## pseudocode

```c
NTSTATUS __fastcall SeUtilSecurityInfoFromSecurityDescriptor(
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        unsigned __int8 *a2,
        _DWORD *a3)
{
  NTSTATUS result; // eax
  int v7; // ebx
  PSID Owner; // [rsp+20h] [rbp-10h] BYREF
  PACL Sacl; // [rsp+28h] [rbp-8h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+58h] [rbp+28h] BYREF
  unsigned __int8 SaclPresent; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  *a3 = 0;
  OwnerDefaulted = 0;
  SaclPresent = 0;
  Owner = 0;
  Sacl = 0;
  result = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, &OwnerDefaulted);
  if ( result >= 0 )
  {
    v7 = Owner != 0;
    result = RtlGetGroupSecurityDescriptor(SecurityDescriptor, &Owner, &OwnerDefaulted);
    if ( result >= 0 )
    {
      if ( Owner )
        v7 |= 2u;
      result = RtlGetSaclSecurityDescriptor(SecurityDescriptor, &SaclPresent, &Sacl, &OwnerDefaulted);
      if ( result >= 0 )
      {
        if ( SaclPresent )
          v7 |= 8u;
        result = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &SaclPresent, &Sacl, &OwnerDefaulted);
        if ( result >= 0 )
        {
          if ( SaclPresent )
            v7 |= 4u;
          *a2 = OwnerDefaulted;
          result = 0;
          *a3 = v7;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14015129c  mov     [rsp-18h+arg_0], rbx
0x1401512a1  mov     [rsp-18h+arg_10], rsi
0x1401512a6  push    rbp
0x1401512a7  push    rdi
0x1401512a8  push    r14
0x1401512aa  mov     rbp, rsp
0x1401512ad  sub     rsp, 30h
0x1401512b1  xor     eax, eax
0x1401512b3  mov     byte ptr [rdx], 0
0x1401512b6  mov     [r8], eax
0x1401512b9  mov     rsi, r8
0x1401512bc  mov     r14, rdx
0x1401512bf  mov     [rbp+OwnerDefaulted], 0
0x1401512c3  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x1401512c7  mov     [rbp+SaclPresent], 0
0x1401512cb  lea     rdx, [rbp+Owner]; Owner
0x1401512cf  mov     [rbp+Owner], 0
0x1401512d7  mov     rdi, rcx
0x1401512da  mov     [rbp+Sacl], 0
0x1401512e2  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1401512e9  nop     dword ptr [rax+rax+00h]
0x1401512ee  test    eax, eax
0x1401512f0  js      loc_140151381
0x1401512f6  xor     ebx, ebx
0x1401512f8  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x1401512fc  cmp     [rbp+Owner], rbx
0x140151300  lea     rdx, [rbp+Owner]; Group
0x140151304  mov     rcx, rdi; SecurityDescriptor
0x140151307  lea     eax, [rbx+1]
0x14015130a  cmovnz  ebx, eax
0x14015130d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x140151314  nop     dword ptr [rax+rax+00h]
0x140151319  test    eax, eax
0x14015131b  js      short loc_140151381
0x14015131d  cmp     [rbp+Owner], 0
0x140151322  jz      short loc_140151327
0x140151324  or      ebx, 2
0x140151327  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x14015132b  mov     rcx, rdi; SecurityDescriptor
0x14015132e  lea     r8, [rbp+Sacl]; Sacl
0x140151332  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x140151336  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x14015133d  nop     dword ptr [rax+rax+00h]
0x140151342  test    eax, eax
0x140151344  js      short loc_140151381
0x140151346  cmp     [rbp+SaclPresent], 0
0x14015134a  jz      short loc_14015134F
0x14015134c  or      ebx, 8
0x14015134f  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x140151353  mov     rcx, rdi; SecurityDescriptor
0x140151356  lea     r8, [rbp+Sacl]; Dacl
0x14015135a  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x14015135e  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140151365  nop     dword ptr [rax+rax+00h]
0x14015136a  test    eax, eax
0x14015136c  js      short loc_140151381
0x14015136e  cmp     [rbp+SaclPresent], 0
0x140151372  jz      short loc_140151377
0x140151374  or      ebx, 4
0x140151377  mov     al, [rbp+OwnerDefaulted]
0x14015137a  mov     [r14], al
0x14015137d  xor     eax, eax
0x14015137f  mov     [rsi], ebx
0x140151381  mov     rbx, [rsp+30h+arg_0]
0x140151386  mov     rsi, [rsp+30h+arg_10]
0x14015138b  add     rsp, 30h
0x14015138f  pop     r14
0x140151391  pop     rdi
0x140151392  pop     rbp
0x140151393  retn
```
