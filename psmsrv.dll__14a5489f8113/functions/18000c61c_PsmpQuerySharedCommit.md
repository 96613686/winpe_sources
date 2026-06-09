# PsmpQuerySharedCommit

- ea: `0x18000c61c`
- end: `0x18000c735`
- name: `PsmpQuerySharedCommit`
- size: `281`
- prototype: `__int64 __fastcall(_QWORD *, int, __int64, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002b760`

## callees

- `0x18000a750`
- `0x18000a8d0`
- `0x18000c61c`
- `0x18001720c`

## import_xrefs

- `ntdll!NtQueryInformationJobObject` at `0x18000c670`
- `ntdll!NtQueryInformationJobObject` at `0x18000c670`

## pseudocode

```c
__int64 __fastcall PsmpQuerySharedCommit(_QWORD *a1, int a2, __int64 a3, void *a4)
{
  __int64 *v4; // rbx
  __int64 v8; // rax
  void *v9; // rcx
  unsigned int InformationJobObject; // edi
  __int64 *HostJobContext; // rax
  __int64 v13; // rax

  v4 = 0;
  if ( a2 == 2 )
  {
    v8 = a1[850];
    v9 = (void *)a1[24];
    if ( v8 != a3 && v8 != -1 )
      goto LABEL_22;
    goto LABEL_3;
  }
  if ( a2 != 4 )
  {
    if ( a2 == 6 )
    {
      v9 = (void *)a1[23];
    }
    else
    {
      if ( a2 != 8 )
        goto LABEL_7;
      v13 = a1[851];
      if ( v13 != -1 && v13 != a3 )
        goto LABEL_22;
      v9 = (void *)a1[25];
    }
LABEL_3:
    if ( v9 )
    {
LABEL_8:
      InformationJobObject = NtQueryInformationJobObject(
                               v9,
                               MaxJobObjectInfoClass|JobObjectBasicAccountingInformation|0x10,
                               a4,
                               8u,
                               0);
      if ( v4 )
        PsmpDereferenceHostContext(v4, 0);
      return InformationJobObject;
    }
    if ( v4 )
      PsmpDereferenceHostContext(v4, 0);
    v4 = 0;
LABEL_7:
    v9 = 0;
    goto LABEL_8;
  }
  HostJobContext = PsmpFindHostJobContext((__int64)a1, a3);
  v4 = HostJobContext;
  if ( HostJobContext )
  {
    v9 = (void *)HostJobContext[6];
    goto LABEL_3;
  }
LABEL_22:
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_ii(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids, a1[12], a3);
  return 3221225485LL;
}

```

## disassembly

```asm
0x18000c61c  push    rbx
0x18000c61e  push    rbp
0x18000c61f  push    rsi
0x18000c620  push    rdi
0x18000c621  sub     rsp, 38h
0x18000c625  xor     ebx, ebx
0x18000c627  mov     rbp, r9
0x18000c62a  mov     rsi, r8
0x18000c62d  mov     rdi, rcx
0x18000c630  cmp     edx, 2
0x18000c633  jnz     short loc_18000C688
0x18000c635  mov     rax, [rdi+1A90h]
0x18000c63c  mov     rcx, [rcx+0C0h]
0x18000c643  cmp     rax, r8
0x18000c646  jnz     short loc_18000C6AF
0x18000c648  test    rcx, rcx
0x18000c64b  jnz     short loc_18000C65A
0x18000c64d  test    rbx, rbx
0x18000c650  jnz     loc_18000C726
0x18000c656  xor     ebx, ebx
0x18000c658  xor     ecx, ecx; JobHandle
0x18000c65a  mov     r9d, 8; JobInformationLength
0x18000c660  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x18000c669  mov     r8, rbp; JobInformation
0x18000c66c  lea     edx, [r9+15h]; JobInformationClass
0x18000c670  call    cs:__imp_NtQueryInformationJobObject
0x18000c676  mov     edi, eax
0x18000c678  test    rbx, rbx
0x18000c67b  jnz     short loc_18000C6A3
0x18000c67d  mov     eax, edi
0x18000c67f  add     rsp, 38h
0x18000c683  pop     rdi
0x18000c684  pop     rsi
0x18000c685  pop     rbp
0x18000c686  pop     rbx
0x18000c687  retn
0x18000c688  cmp     edx, 4
0x18000c68b  jnz     short loc_18000C6B7
0x18000c68d  mov     rdx, rsi
0x18000c690  call    PsmpFindHostJobContext
0x18000c695  mov     rbx, rax
0x18000c698  test    rax, rax
0x18000c69b  jz      short loc_18000C6EB
0x18000c69d  mov     rcx, [rax+30h]
0x18000c6a1  jmp     short loc_18000C648
0x18000c6a3  xor     edx, edx
0x18000c6a5  mov     rcx, rbx
0x18000c6a8  call    PsmpDereferenceHostContext
0x18000c6ad  jmp     short loc_18000C67D
0x18000c6af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c6b3  jz      short loc_18000C648
0x18000c6b5  jmp     short loc_18000C6EB
0x18000c6b7  cmp     edx, 6
0x18000c6ba  jz      short loc_18000C6DA
0x18000c6bc  cmp     edx, 8
0x18000c6bf  jnz     short loc_18000C658
0x18000c6c1  mov     rax, [rcx+1A98h]
0x18000c6c8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c6cc  jnz     short loc_18000C6E6
0x18000c6ce  mov     rcx, [rcx+0C8h]
0x18000c6d5  jmp     loc_18000C648
0x18000c6da  mov     rcx, [rcx+0B8h]
0x18000c6e1  jmp     loc_18000C648
0x18000c6e6  cmp     rax, rsi
0x18000c6e9  jz      short loc_18000C6CE
0x18000c6eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6f2  test    byte ptr [rcx+1Ch], 2
0x18000c6f6  jz      short loc_18000C71C
0x18000c6f8  cmp     byte ptr [rcx+19h], 2
0x18000c6fc  jb      short loc_18000C71C
0x18000c6fe  mov     r9, [rdi+60h]
0x18000c702  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x18000c709  mov     rcx, [rcx+10h]
0x18000c70d  mov     edx, 37h ; '7'
0x18000c712  mov     [rsp+58h+ReturnLength], rsi
0x18000c717  call    WPP_SF_ii
0x18000c71c  mov     eax, 0C000000Dh
0x18000c721  jmp     loc_18000C67F
0x18000c726  xor     edx, edx
0x18000c728  mov     rcx, rbx
0x18000c72b  call    PsmpDereferenceHostContext
0x18000c730  jmp     loc_18000C656
```
