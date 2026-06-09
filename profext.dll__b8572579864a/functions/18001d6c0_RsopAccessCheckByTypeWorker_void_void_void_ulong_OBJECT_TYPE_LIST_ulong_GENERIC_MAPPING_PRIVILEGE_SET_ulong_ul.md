# RsopAccessCheckByTypeWorker(void *,void *,void *,ulong,_OBJECT_TYPE_LIST *,ulong,_GENERIC_MAPPING *,_PRIVILEGE_SET *,ulong *,ulong *,int *)

- ea: `0x18001d6c0`
- end: `0x18001d760`
- name: `?RsopAccessCheckByTypeWorker@@YAJPEAX00KPEAU_OBJECT_TYPE_LIST@@KPEAU_GENERIC_MAPPING@@PEAU_PRIVILEGE_SET@@PEAK4PEAH@Z`
- size: `160`
- prototype: `__int64 __fastcall(void *, void *, void *, unsigned int, struct _OBJECT_TYPE_LIST *, unsigned int, struct _GENERIC_MAPPING *, struct _PRIVILEGE_SET *, unsigned int *, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callees

- `0x1800122d8`
- `0x18001d6c0`

## import_xrefs

- `ext-ms-win-gpsvc-grouppolicy-l1-1-0!RsopAccessCheckByTypeInternal` at `0x18001d74a`
- `ext-ms-win-gpsvc-grouppolicy-l1-1-0!RsopAccessCheckByTypeInternal` at `0x18001d74a`

## pseudocode

```c
__int64 __fastcall RsopAccessCheckByTypeWorker(
        void *a1,
        void *a2,
        void *a3,
        unsigned int a4,
        struct _OBJECT_TYPE_LIST *a5,
        unsigned int a6,
        struct _GENERIC_MAPPING *a7,
        struct _PRIVILEGE_SET *a8,
        unsigned int *a9,
        unsigned int *a10,
        int *a11)
{
  if ( (unsigned __int8)IsRsopAccessCheckByTypeInternalPresent() )
    return RsopAccessCheckByTypeInternal(a1, a2, a3, a4, a5, a6, a7, a8, a9, a10, a11);
  else
    return 2147942527LL;
}

```

## disassembly

```asm
0x18001d6c0  push    rbx
0x18001d6c2  push    rbp
0x18001d6c3  push    rsi
0x18001d6c4  push    rdi
0x18001d6c5  sub     rsp, 68h
0x18001d6c9  mov     ebx, r9d
0x18001d6cc  mov     rdi, r8
0x18001d6cf  mov     rsi, rdx
0x18001d6d2  mov     rbp, rcx
0x18001d6d5  call    IsRsopAccessCheckByTypeInternalPresent
0x18001d6da  test    al, al
0x18001d6dc  jnz     short loc_18001D6E5
0x18001d6de  mov     eax, 8007007Fh
0x18001d6e3  jmp     short loc_18001D756
0x18001d6e5  mov     rax, [rsp+88h+arg_50]
0x18001d6ed  mov     r9d, ebx
0x18001d6f0  mov     [rsp+88h+var_38], rax
0x18001d6f5  mov     r8, rdi
0x18001d6f8  mov     rax, [rsp+88h+arg_48]
0x18001d700  mov     rdx, rsi
0x18001d703  mov     [rsp+88h+var_40], rax
0x18001d708  mov     rcx, rbp
0x18001d70b  mov     rax, [rsp+88h+arg_40]
0x18001d713  mov     [rsp+88h+var_48], rax
0x18001d718  mov     rax, [rsp+88h+arg_38]
0x18001d720  mov     [rsp+88h+var_50], rax
0x18001d725  mov     rax, [rsp+88h+arg_30]
0x18001d72d  mov     [rsp+88h+var_58], rax
0x18001d732  mov     eax, [rsp+88h+arg_28]
0x18001d739  mov     [rsp+88h+var_60], eax
0x18001d73d  mov     rax, [rsp+88h+arg_20]
0x18001d745  mov     [rsp+88h+var_68], rax
0x18001d74a  call    cs:__imp_RsopAccessCheckByTypeInternal
0x18001d751  nop     dword ptr [rax+rax+00h]
0x18001d756  add     rsp, 68h
0x18001d75a  pop     rdi
0x18001d75b  pop     rsi
0x18001d75c  pop     rbp
0x18001d75d  pop     rbx
0x18001d75e  retn
```
