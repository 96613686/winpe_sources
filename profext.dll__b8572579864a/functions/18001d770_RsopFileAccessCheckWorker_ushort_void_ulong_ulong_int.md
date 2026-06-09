# RsopFileAccessCheckWorker(ushort *,void *,ulong,ulong *,int *)

- ea: `0x18001d770`
- end: `0x18001d7c4`
- name: `?RsopFileAccessCheckWorker@@YAJPEAGPEAXKPEAKPEAH@Z`
- size: `84`
- prototype: `__int64 __fastcall(unsigned __int16 *, void *, unsigned int, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callees

- `0x1800122d8`
- `0x18001d770`

## import_xrefs

- `ext-ms-win-gpsvc-grouppolicy-l1-1-0!RsopFileAccessCheckInternal` at `0x18001d7ae`
- `ext-ms-win-gpsvc-grouppolicy-l1-1-0!RsopFileAccessCheckInternal` at `0x18001d7ae`

## pseudocode

```c
__int64 __fastcall RsopFileAccessCheckWorker(
        unsigned __int16 *a1,
        void *a2,
        unsigned int a3,
        unsigned int *a4,
        int *a5)
{
  if ( (unsigned __int8)IsRsopAccessCheckByTypeInternalPresent() )
    return RsopFileAccessCheckInternal(a1, a2, a3, a4, a5);
  else
    return 2147942527LL;
}

```

## disassembly

```asm
0x18001d770  push    rbx
0x18001d772  push    rbp
0x18001d773  push    rsi
0x18001d774  push    rdi
0x18001d775  sub     rsp, 38h
0x18001d779  mov     rbx, r9
0x18001d77c  mov     edi, r8d
0x18001d77f  mov     rsi, rdx
0x18001d782  mov     rbp, rcx
0x18001d785  call    IsRsopAccessCheckByTypeInternalPresent
0x18001d78a  test    al, al
0x18001d78c  jnz     short loc_18001D795
0x18001d78e  mov     eax, 8007007Fh
0x18001d793  jmp     short loc_18001D7BA
0x18001d795  mov     rax, [rsp+58h+arg_20]
0x18001d79d  mov     r9, rbx
0x18001d7a0  mov     r8d, edi
0x18001d7a3  mov     [rsp+58h+var_38], rax
0x18001d7a8  mov     rdx, rsi
0x18001d7ab  mov     rcx, rbp
0x18001d7ae  call    cs:__imp_RsopFileAccessCheckInternal
0x18001d7b5  nop     dword ptr [rax+rax+00h]
0x18001d7ba  add     rsp, 38h
0x18001d7be  pop     rdi
0x18001d7bf  pop     rsi
0x18001d7c0  pop     rbp
0x18001d7c1  pop     rbx
0x18001d7c2  retn
```
