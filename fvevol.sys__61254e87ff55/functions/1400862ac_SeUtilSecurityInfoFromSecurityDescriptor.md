# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x1400862ac`
- end: `0x1400863a5`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400851d4`
- `0x140085ddc`

## callees

- `0x1400862ac`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140086346`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140086346`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1400862f2`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1400862f2`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14008631d`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14008631d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14008636e`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14008636e`

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
0x1400862ac  mov     [rsp-18h+arg_0], rbx
0x1400862b1  mov     [rsp-18h+arg_10], rsi
0x1400862b6  push    rbp
0x1400862b7  push    rdi
0x1400862b8  push    r14
0x1400862ba  mov     rbp, rsp
0x1400862bd  sub     rsp, 30h
0x1400862c1  xor     eax, eax
0x1400862c3  mov     byte ptr [rdx], 0
0x1400862c6  mov     [r8], eax
0x1400862c9  mov     rsi, r8
0x1400862cc  mov     r14, rdx
0x1400862cf  mov     [rbp+OwnerDefaulted], 0
0x1400862d3  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x1400862d7  mov     [rbp+SaclPresent], 0
0x1400862db  lea     rdx, [rbp+Owner]; Owner
0x1400862df  mov     [rbp+Owner], 0
0x1400862e7  mov     rdi, rcx
0x1400862ea  mov     [rbp+Sacl], 0
0x1400862f2  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1400862f9  nop     dword ptr [rax+rax+00h]
0x1400862fe  test    eax, eax
0x140086300  js      loc_140086391
0x140086306  xor     ebx, ebx
0x140086308  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x14008630c  cmp     [rbp+Owner], rbx
0x140086310  lea     rdx, [rbp+Owner]; Group
0x140086314  mov     rcx, rdi; SecurityDescriptor
0x140086317  lea     eax, [rbx+1]
0x14008631a  cmovnz  ebx, eax
0x14008631d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x140086324  nop     dword ptr [rax+rax+00h]
0x140086329  test    eax, eax
0x14008632b  js      short loc_140086391
0x14008632d  cmp     [rbp+Owner], 0
0x140086332  jz      short loc_140086337
0x140086334  or      ebx, 2
0x140086337  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x14008633b  mov     rcx, rdi; SecurityDescriptor
0x14008633e  lea     r8, [rbp+Sacl]; Sacl
0x140086342  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x140086346  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x14008634d  nop     dword ptr [rax+rax+00h]
0x140086352  test    eax, eax
0x140086354  js      short loc_140086391
0x140086356  cmp     [rbp+SaclPresent], 0
0x14008635a  jz      short loc_14008635F
0x14008635c  or      ebx, 8
0x14008635f  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x140086363  mov     rcx, rdi; SecurityDescriptor
0x140086366  lea     r8, [rbp+Sacl]; Dacl
0x14008636a  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x14008636e  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140086375  nop     dword ptr [rax+rax+00h]
0x14008637a  test    eax, eax
0x14008637c  js      short loc_140086391
0x14008637e  cmp     [rbp+SaclPresent], 0
0x140086382  jz      short loc_140086387
0x140086384  or      ebx, 4
0x140086387  mov     al, [rbp+OwnerDefaulted]
0x14008638a  mov     [r14], al
0x14008638d  xor     eax, eax
0x14008638f  mov     [rsi], ebx
0x140086391  mov     rbx, [rsp+30h+arg_0]
0x140086396  mov     rsi, [rsp+30h+arg_10]
0x14008639b  add     rsp, 30h
0x14008639f  pop     r14
0x1400863a1  pop     rdi
0x1400863a2  pop     rbp
0x1400863a3  retn
```
