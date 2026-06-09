# PcwpCreateAllowedDacl(utl::unique_ptr<_ACL,utl::default_delete<_ACL>> *,ulong,...)

- ea: `0x14000df74`
- end: `0x14000e07f`
- name: `?PcwpCreateAllowedDacl@@YAJPEAV?$unique_ptr@U_ACL@@U?$default_delete@U_ACL@@@utl@@@utl@@KZZ`
- size: `267`
- prototype: `NTSTATUS(PACL *, unsigned int, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000e088`

## callees

- `0x14000df74`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000dff0`
- `ntoskrnl!ExAllocatePool2` at `0x14000dff0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e009`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e009`
- `ntoskrnl!RtlLengthSid` at `0x14000dfb0`
- `ntoskrnl!RtlLengthSid` at `0x14000dfb0`
- `ntoskrnl!RtlCreateAcl` at `0x14000e022`
- `ntoskrnl!RtlCreateAcl` at `0x14000e022`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000e054`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000e054`

## pseudocode

```c
NTSTATUS PcwpCreateAllowedDacl(PACL *a1, unsigned int a2, ...)
{
  int v2; // edi
  va_list v3; // rbp
  ULONG v5; // ebx
  va_list v6; // rcx
  ULONG v7; // eax
  ULONG v8; // ebx
  __int64 Pool2; // rax
  PACL v10; // rcx
  NTSTATUS result; // eax
  int v12; // ebx
  va_list v13; // rdi
  va_list v14; // r9
  va_list va; // [rsp+70h] [rbp+18h] BYREF

  va_start(va, a2);
  v2 = 0;
  va_copy(v3, va);
  v5 = 8;
  if ( a2 )
  {
    while ( 1 )
    {
      v6 = v3 + 8;
      v3 += 16;
      v7 = RtlLengthSid(*((PSID *)v6 - 1));
      v8 = v7 + v5;
      if ( v8 < v7 )
        return -1073741675;
      v5 = v8 + 12;
      if ( v5 < 0xC )
        return -1073741675;
      if ( ++v2 >= a2 )
        goto LABEL_5;
    }
  }
  else
  {
LABEL_5:
    Pool2 = ExAllocatePool2(256, v5, 1417110352);
    v10 = *a1;
    *a1 = (PACL)Pool2;
    if ( v10 )
      ExFreePoolWithTag(v10, 0);
    result = RtlCreateAcl(*a1, v5, 2u);
    if ( result >= 0 )
    {
      v12 = 0;
      va_copy(v13, va);
      if ( a2 )
      {
        while ( 1 )
        {
          v14 = v13 + 8;
          v13 += 16;
          result = RtlAddAccessAllowedAce(*a1, 2u, *((_DWORD *)v13 - 2), *((PSID *)v14 - 1));
          if ( result < 0 )
            break;
          if ( ++v12 >= a2 )
            return 0;
        }
      }
      else
      {
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000df74  mov     rax, rsp
0x14000df77  mov     [rax+10h], edx
0x14000df7a  mov     [rax+18h], r8
0x14000df7e  mov     [rax+20h], r9
0x14000df82  push    rbx
0x14000df83  push    rbp
0x14000df84  push    rsi
0x14000df85  push    rdi
0x14000df86  sub     rsp, 38h
0x14000df8a  xor     edi, edi
0x14000df8c  mov     qword ptr [rax-38h], 0
0x14000df94  lea     rbp, [rax+18h]
0x14000df98  mov     rsi, rcx
0x14000df9b  mov     ebx, 8
0x14000dfa0  test    edx, edx
0x14000dfa2  jz      short loc_14000DFDA
0x14000dfa4  lea     rcx, [rbp+8]
0x14000dfa8  lea     rbp, [rcx+8]
0x14000dfac  mov     rcx, [rcx-8]; Sid
0x14000dfb0  call    cs:__imp_RtlLengthSid
0x14000dfb7  nop     dword ptr [rax+rax+00h]
0x14000dfbc  add     ebx, eax
0x14000dfbe  cmp     ebx, eax
0x14000dfc0  jb      loc_14000E078
0x14000dfc6  add     ebx, 0Ch
0x14000dfc9  cmp     ebx, 0Ch
0x14000dfcc  jb      loc_14000E078
0x14000dfd2  inc     edi
0x14000dfd4  cmp     edi, [rsp+58h+arg_8]
0x14000dfd8  jb      short loc_14000DFA4
0x14000dfda  mov     edx, ebx
0x14000dfdc  mov     ecx, 100h
0x14000dfe1  mov     r8d, 54776350h
0x14000dfe7  mov     [rsp+58h+var_38], 0
0x14000dff0  call    cs:__imp_ExAllocatePool2
0x14000dff7  nop     dword ptr [rax+rax+00h]
0x14000dffc  mov     rcx, [rsi]; P
0x14000dfff  mov     [rsi], rax
0x14000e002  test    rcx, rcx
0x14000e005  jz      short loc_14000E015
0x14000e007  xor     edx, edx; Tag
0x14000e009  call    cs:__imp_ExFreePoolWithTag
0x14000e010  nop     dword ptr [rax+rax+00h]
0x14000e015  mov     rcx, [rsi]; Acl
0x14000e018  mov     ebp, 2
0x14000e01d  mov     r8d, ebp; AclRevision
0x14000e020  mov     edx, ebx; AclLength
0x14000e022  call    cs:__imp_RtlCreateAcl
0x14000e029  nop     dword ptr [rax+rax+00h]
0x14000e02e  test    eax, eax
0x14000e030  js      short loc_14000E06E
0x14000e032  xor     ebx, ebx
0x14000e034  lea     rdi, [rsp+58h+arg_10]
0x14000e039  cmp     [rsp+58h+arg_8], ebx
0x14000e03d  jbe     short loc_14000E06C
0x14000e03f  mov     rcx, [rsi]; Acl
0x14000e042  lea     r9, [rdi+8]
0x14000e046  lea     rdi, [r9+8]
0x14000e04a  mov     edx, ebp; AceRevision
0x14000e04c  mov     r8d, [rdi-8]; AccessMask
0x14000e050  mov     r9, [r9-8]; Sid
0x14000e054  call    cs:__imp_RtlAddAccessAllowedAce
0x14000e05b  nop     dword ptr [rax+rax+00h]
0x14000e060  test    eax, eax
0x14000e062  js      short loc_14000E06E
0x14000e064  inc     ebx
0x14000e066  cmp     ebx, [rsp+58h+arg_8]
0x14000e06a  jb      short loc_14000E03F
0x14000e06c  xor     eax, eax
0x14000e06e  add     rsp, 38h
0x14000e072  pop     rdi
0x14000e073  pop     rsi
0x14000e074  pop     rbp
0x14000e075  pop     rbx
0x14000e076  retn
0x14000e078  mov     eax, 0C0000095h
0x14000e07d  jmp     short loc_14000E06E
```
