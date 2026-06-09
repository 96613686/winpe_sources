# KappxCheckTrustLabelAce

- ea: `0x18005d3fc`
- end: `0x18005d5a7`
- name: `KappxCheckTrustLabelAce`
- size: `427`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005cee8`

## callees

- `0x18002bef0`
- `0x18005d3fc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18005d497`
- `ntoskrnl!ExAllocatePool2` at `0x18005d497`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d575`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005d575`
- `ntoskrnl!ZwQuerySecurityObject` at `0x18005d474`
- `ntoskrnl!ZwQuerySecurityObject` at `0x18005d4eb`
- `ntoskrnl!ZwQuerySecurityObject` at `0x18005d474`
- `ntoskrnl!ZwQuerySecurityObject` at `0x18005d4eb`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x18005d441`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x18005d4bd`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x18005d441`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x18005d4bd`
- `ntoskrnl!RtlFindAceByType` at `0x18005d53f`
- `ntoskrnl!RtlFindAceByType` at `0x18005d53f`

## pseudocode

```c
__int64 __fastcall KappxCheckTrustLabelAce(HANDLE Handle, _BYTE *a2)
{
  NTSTATUS v4; // edi
  __int16 *v5; // rbx
  __int16 *Pool2; // rax
  __int16 v7; // ax
  _BYTE *v8; // rcx
  __int64 v9; // rax
  __int64 AceByType; // rax
  ULONG Length; // [rsp+30h] [rbp-69h] BYREF
  int v13[3]; // [rsp+34h] [rbp-65h] BYREF
  _BYTE SecurityDescriptor[128]; // [rsp+40h] [rbp-59h] BYREF

  Length = 128;
  *a2 = 0;
  v13[0] = 0;
  v4 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v4 < 0 )
    return (unsigned int)v4;
  v5 = (__int16 *)SecurityDescriptor;
  v4 = ZwQuerySecurityObject(Handle, 0x80u, SecurityDescriptor, Length, &Length);
  if ( v4 == -1073741789 )
  {
    Pool2 = (__int16 *)ExAllocatePool2(256, Length, 1483763777);
    v5 = Pool2;
    if ( !Pool2 )
      return (unsigned int)-1073741801;
    v4 = RtlCreateSecurityDescriptor(Pool2, 1u);
    if ( v4 < 0 )
    {
LABEL_23:
      if ( v5 != (__int16 *)SecurityDescriptor )
        ExFreePoolWithTag(v5, 0x58707041u);
      return (unsigned int)v4;
    }
    v4 = ZwQuerySecurityObject(Handle, 0x80u, v5, Length, &Length);
  }
  if ( v4 >= 0 )
  {
    if ( !v5 )
      return (unsigned int)-1073739509;
    while ( 1 )
    {
      v7 = v5[1];
      if ( (v7 & 0x10) == 0 )
        goto LABEL_13;
      if ( v7 >= 0 )
      {
        v8 = (_BYTE *)*((_QWORD *)v5 + 3);
        goto LABEL_18;
      }
      v9 = *((unsigned int *)v5 + 3);
      if ( (_DWORD)v9 )
        v8 = (char *)v5 + v9;
      else
LABEL_13:
        v8 = 0;
LABEL_18:
      AceByType = RtlFindAceByType(v8, 20, v13);
      if ( AceByType && (*(_BYTE *)(AceByType + 1) & 8) == 0 )
      {
        *a2 = 1;
        goto LABEL_23;
      }
      ++v13[0];
      if ( !AceByType )
        goto LABEL_23;
    }
  }
  v4 = 0;
  if ( v5 )
    goto LABEL_23;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005d3fc  mov     [rsp-8+arg_10], rbx
0x18005d401  push    rbp
0x18005d402  push    rsi
0x18005d403  push    rdi
0x18005d404  push    r14
0x18005d406  push    r15
0x18005d408  lea     rbp, [rsp-37h]
0x18005d40d  sub     rsp, 0D0h
0x18005d414  mov     rax, cs:__security_cookie
0x18005d41b  xor     rax, rsp
0x18005d41e  mov     [rbp+57h+var_30], rax
0x18005d422  xor     r15d, r15d
0x18005d425  mov     [rbp+57h+Length], 80h
0x18005d42c  mov     r14, rdx
0x18005d42f  mov     [rdx], r15b
0x18005d432  mov     rsi, rcx
0x18005d435  mov     [rbp+57h+var_BC], r15d
0x18005d439  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18005d43d  lea     edx, [r15+1]; Revision
0x18005d441  call    cs:__imp_RtlCreateSecurityDescriptor
0x18005d448  nop     dword ptr [rax+rax+00h]
0x18005d44d  mov     edi, eax
0x18005d44f  test    eax, eax
0x18005d451  js      loc_18005D581
0x18005d457  mov     r9d, [rbp+57h+Length]; Length
0x18005d45b  lea     rax, [rbp+57h+Length]
0x18005d45f  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18005d463  mov     [rsp+0F0h+LengthNeeded], rax; LengthNeeded
0x18005d468  mov     edx, 80h; SecurityInformation
0x18005d46d  lea     rbx, [rbp+57h+SecurityDescriptor]
0x18005d471  mov     rcx, rsi; Handle
0x18005d474  call    cs:__imp_ZwQuerySecurityObject
0x18005d47b  nop     dword ptr [rax+rax+00h]
0x18005d480  mov     edi, eax
0x18005d482  cmp     eax, 0C0000023h
0x18005d487  jnz     short loc_18005D4F9
0x18005d489  mov     edx, [rbp+57h+Length]
0x18005d48c  mov     ecx, 100h
0x18005d491  mov     r8d, 58707041h
0x18005d497  call    cs:__imp_ExAllocatePool2
0x18005d49e  nop     dword ptr [rax+rax+00h]
0x18005d4a3  mov     rbx, rax
0x18005d4a6  test    rax, rax
0x18005d4a9  jnz     short loc_18005D4B5
0x18005d4ab  mov     edi, 0C0000017h
0x18005d4b0  jmp     loc_18005D581
0x18005d4b5  mov     edx, 1; Revision
0x18005d4ba  mov     rcx, rbx; SecurityDescriptor
0x18005d4bd  call    cs:__imp_RtlCreateSecurityDescriptor
0x18005d4c4  nop     dword ptr [rax+rax+00h]
0x18005d4c9  mov     edi, eax
0x18005d4cb  test    eax, eax
0x18005d4cd  js      loc_18005D564
0x18005d4d3  mov     r9d, [rbp+57h+Length]; Length
0x18005d4d7  lea     rax, [rbp+57h+Length]
0x18005d4db  mov     r8, rbx; SecurityDescriptor
0x18005d4de  mov     [rsp+0F0h+LengthNeeded], rax; LengthNeeded
0x18005d4e3  mov     edx, 80h; SecurityInformation
0x18005d4e8  mov     rcx, rsi; Handle
0x18005d4eb  call    cs:__imp_ZwQuerySecurityObject
0x18005d4f2  nop     dword ptr [rax+rax+00h]
0x18005d4f7  mov     edi, eax
0x18005d4f9  test    edi, edi
0x18005d4fb  jns     short loc_18005D507
0x18005d4fd  mov     edi, r15d
0x18005d500  test    rbx, rbx
0x18005d503  jz      short loc_18005D581
0x18005d505  jmp     short loc_18005D564
0x18005d507  test    rbx, rbx
0x18005d50a  jnz     short loc_18005D513
0x18005d50c  mov     edi, 0C000090Bh
0x18005d511  jmp     short loc_18005D581
0x18005d513  movzx   eax, word ptr [rbx+2]
0x18005d517  test    al, 10h
0x18005d519  jnz     short loc_18005D520
0x18005d51b  mov     rcx, r15
0x18005d51e  jmp     short loc_18005D536
0x18005d520  test    ax, ax
0x18005d523  jns     short loc_18005D532
0x18005d525  mov     eax, [rbx+0Ch]
0x18005d528  test    eax, eax
0x18005d52a  jz      short loc_18005D51B
0x18005d52c  lea     rcx, [rbx+rax]
0x18005d530  jmp     short loc_18005D536
0x18005d532  mov     rcx, [rbx+18h]
0x18005d536  lea     r8, [rbp+57h+var_BC]
0x18005d53a  mov     edx, 14h
0x18005d53f  call    cs:__imp_RtlFindAceByType
0x18005d546  nop     dword ptr [rax+rax+00h]
0x18005d54b  test    rax, rax
0x18005d54e  jz      short loc_18005D556
0x18005d550  test    byte ptr [rax+1], 8
0x18005d554  jz      short loc_18005D560
0x18005d556  inc     [rbp+57h+var_BC]
0x18005d559  test    rax, rax
0x18005d55c  jnz     short loc_18005D513
0x18005d55e  jmp     short loc_18005D564
0x18005d560  mov     byte ptr [r14], 1
0x18005d564  lea     rax, [rbp+57h+SecurityDescriptor]
0x18005d568  cmp     rbx, rax
0x18005d56b  jz      short loc_18005D581
0x18005d56d  mov     edx, 58707041h; Tag
0x18005d572  mov     rcx, rbx; P
0x18005d575  call    cs:__imp_ExFreePoolWithTag
0x18005d57c  nop     dword ptr [rax+rax+00h]
0x18005d581  mov     eax, edi
0x18005d583  mov     rcx, [rbp+57h+var_30]
0x18005d587  xor     rcx, rsp; StackCookie
0x18005d58a  call    __security_check_cookie
0x18005d58f  mov     rbx, [rsp+0F0h+arg_10]
0x18005d597  add     rsp, 0D0h
0x18005d59e  pop     r15
0x18005d5a0  pop     r14
0x18005d5a2  pop     rdi
0x18005d5a3  pop     rsi
0x18005d5a4  pop     rbp
0x18005d5a5  retn
```
