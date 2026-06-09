# CuipDuplicateToken(void *,void * *)

- ea: `0x14000ab5c`
- end: `0x14000abaa`
- name: `?CuipDuplicateToken@@YAKPEAXPEAPEAX@Z`
- size: `78`
- prototype: `ULONG __fastcall(void *, void **)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000cfdc`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x14000ab97`
- `ntdll!NtDuplicateToken` at `0x14000ab97`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14000ab9f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14000ab9f`

## pseudocode

```c
ULONG __fastcall CuipDuplicateToken(void *a1, void **a2)
{
  NTSTATUS v2; // eax
  struct _OBJECT_ATTRIBUTES v4; // [rsp+30h] [rbp-38h] BYREF

  memset(&v4.RootDirectory, 0, 40);
  *(_QWORD *)&v4.Length = 48;
  v2 = NtDuplicateToken(a1, 0, &v4, 0, TokenPrimary, a2);
  return RtlNtStatusToDosErrorNoTeb(v2);
}

```

## disassembly

```asm
0x14000ab5c  mov     r11, rsp
0x14000ab5f  sub     rsp, 68h
0x14000ab63  xor     eax, eax
0x14000ab65  mov     [r11-40h], rdx
0x14000ab69  xorps   xmm0, xmm0
0x14000ab6c  mov     [r11-20h], rax
0x14000ab70  mov     [r11-30h], rax
0x14000ab74  lea     r8, [r11-38h]; ObjectAttributes
0x14000ab78  mov     [r11-28h], rax
0x14000ab7c  xor     r9d, r9d; EffectiveOnly
0x14000ab7f  mov     qword ptr [r11-38h], 30h ; '0'
0x14000ab87  xor     edx, edx; DesiredAccess
0x14000ab89  movdqu  [rsp+68h+var_18], xmm0
0x14000ab8f  mov     [rsp+68h+TokenType], 1; TokenType
0x14000ab97  call    cs:__imp_NtDuplicateToken
0x14000ab9d  mov     ecx, eax; Status
0x14000ab9f  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x14000aba5  add     rsp, 68h
0x14000aba9  retn
```
