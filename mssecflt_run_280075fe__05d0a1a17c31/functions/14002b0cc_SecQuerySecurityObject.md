# SecQuerySecurityObject

- ea: `0x14002b0cc`
- end: `0x14002b1c2`
- name: `SecQuerySecurityObject`
- size: `246`
- prototype: `__int64 __fastcall(HANDLE Handle, SECURITY_INFORMATION SecurityInformation)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140008524`

## callees

- `0x140009b80`
- `0x140011610`
- `0x140011650`
- `0x14002b0cc`

## import_xrefs

- `ntoskrnl!ZwQuerySecurityObject` at `0x14002b107`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14002b183`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14002b107`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14002b183`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b148`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b148`

## pseudocode

```c
__int64 __fastcall SecQuerySecurityObject(HANDLE Handle, SECURITY_INFORMATION SecurityInformation, _QWORD *a3)
{
  NTSTATUS v6; // edi
  PVOID PoolWithTag; // rax
  void *v8; // rbx
  ULONG v9; // r9d
  ULONG Length; // [rsp+30h] [rbp-38h] BYREF

  Length = 0;
  v6 = ZwQuerySecurityObject(Handle, SecurityInformation, 0, 0, &Length);
  if ( v6 == -1073741789 )
  {
    if ( qword_140020008 )
      PoolWithTag = (PVOID)qword_140020008(256, Length, 1146315603);
    else
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, Length, 0x44536353u);
    v8 = PoolWithTag;
    if ( PoolWithTag )
    {
      v9 = Length;
      Length = 0;
      v6 = ZwQuerySecurityObject(Handle, SecurityInformation, PoolWithTag, v9, &Length);
      if ( v6 < 0 )
        SecFreePool(v8, 0x44536353u);
      else
        *a3 = v8;
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14002b0cc  push    rbx
0x14002b0ce  push    rbp
0x14002b0cf  push    rsi
0x14002b0d0  push    rdi
0x14002b0d1  push    r14
0x14002b0d3  sub     rsp, 40h
0x14002b0d7  mov     rax, cs:__security_cookie
0x14002b0de  xor     rax, rsp
0x14002b0e1  mov     [rsp+68h+var_30], rax
0x14002b0e6  mov     rsi, r8
0x14002b0e9  mov     [rsp+68h+Length], 0
0x14002b0f1  lea     rax, [rsp+68h+Length]
0x14002b0f6  xor     r8d, r8d; SecurityDescriptor
0x14002b0f9  xor     r9d, r9d; Length
0x14002b0fc  mov     [rsp+68h+LengthNeeded], rax; LengthNeeded
0x14002b101  mov     r14d, edx
0x14002b104  mov     rbp, rcx
0x14002b107  call    cs:__imp_ZwQuerySecurityObject
0x14002b10e  nop     dword ptr [rax+rax+00h]
0x14002b113  mov     edi, eax
0x14002b115  cmp     eax, 0C0000023h
0x14002b11a  jnz     loc_14002B1A7
0x14002b120  mov     rax, cs:qword_140020008
0x14002b127  mov     r8d, 44536353h; Tag
0x14002b12d  mov     edx, [rsp+68h+Length]; NumberOfBytes
0x14002b131  test    rax, rax
0x14002b134  jz      short loc_14002B143
0x14002b136  mov     ecx, 100h
0x14002b13b  call    cs:__guard_dispatch_icall_fptr
0x14002b141  jmp     short loc_14002B154
0x14002b143  mov     ecx, 1; PoolType
0x14002b148  call    cs:__imp_ExAllocatePoolWithTag
0x14002b14f  nop     dword ptr [rax+rax+00h]
0x14002b154  mov     rbx, rax
0x14002b157  test    rax, rax
0x14002b15a  jnz     short loc_14002B163
0x14002b15c  mov     edi, 0C0000017h
0x14002b161  jmp     short loc_14002B1A7
0x14002b163  mov     r9d, [rsp+68h+Length]; Length
0x14002b168  lea     rax, [rsp+68h+Length]
0x14002b16d  mov     r8, rbx; SecurityDescriptor
0x14002b170  mov     [rsp+68h+LengthNeeded], rax; LengthNeeded
0x14002b175  mov     edx, r14d; SecurityInformation
0x14002b178  mov     [rsp+68h+Length], 0
0x14002b180  mov     rcx, rbp; Handle
0x14002b183  call    cs:__imp_ZwQuerySecurityObject
0x14002b18a  nop     dword ptr [rax+rax+00h]
0x14002b18f  mov     edi, eax
0x14002b191  test    eax, eax
0x14002b193  js      short loc_14002B19A
0x14002b195  mov     [rsi], rbx
0x14002b198  jmp     short loc_14002B1A7
0x14002b19a  mov     edx, 44536353h; Tag
0x14002b19f  mov     rcx, rbx; P
0x14002b1a2  call    SecFreePool
0x14002b1a7  mov     eax, edi
0x14002b1a9  mov     rcx, [rsp+68h+var_30]
0x14002b1ae  xor     rcx, rsp; StackCookie
0x14002b1b1  call    __security_check_cookie
0x14002b1b6  add     rsp, 40h
0x14002b1ba  pop     r14
0x14002b1bc  pop     rdi
0x14002b1bd  pop     rsi
0x14002b1be  pop     rbp
0x14002b1bf  pop     rbx
0x14002b1c0  retn
```
