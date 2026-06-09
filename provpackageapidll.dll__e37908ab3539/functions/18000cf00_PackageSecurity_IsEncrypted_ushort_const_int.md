# PackageSecurity::IsEncrypted(ushort const *,int *)

- ea: `0x18000cf00`
- end: `0x18000cf4f`
- name: `?IsEncrypted@PackageSecurity@@EEAAJPEBGPEAH@Z`
- size: `79`
- prototype: `__int64 __fastcall(PackageSecurity *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000cf00`

## import_xrefs

- `WIMGAPI!WIMCreateFile` at `0x18000cf29`
- `WIMGAPI!WIMCreateFile` at `0x18000cf29`
- `WIMGAPI!WIMCloseHandle` at `0x18000cf41`
- `WIMGAPI!WIMCloseHandle` at `0x18000cf41`

## pseudocode

```c
__int64 __fastcall PackageSecurity::IsEncrypted(PackageSecurity *this, const unsigned __int16 *a2, int *a3)
{
  __int64 v4; // rax

  v4 = WIMCreateFile(a2, 0x80000000LL, 3, 0);
  *a3 = v4 == 0;
  if ( v4 )
    WIMCloseHandle(v4);
  return 0;
}

```

## disassembly

```asm
0x18000cf00  push    rbx
0x18000cf02  sub     rsp, 30h
0x18000cf06  xor     r9d, r9d
0x18000cf09  mov     [rsp+38h+var_10], 0
0x18000cf12  mov     rbx, r8
0x18000cf15  mov     [rsp+38h+var_18], 0
0x18000cf1d  mov     rcx, rdx
0x18000cf20  mov     edx, 80000000h
0x18000cf25  lea     r8d, [r9+3]
0x18000cf29  call    cs:__imp_WIMCreateFile
0x18000cf2f  xor     ecx, ecx
0x18000cf31  test    rax, rax
0x18000cf34  setz    cl
0x18000cf37  mov     [rbx], ecx
0x18000cf39  test    rax, rax
0x18000cf3c  jz      short loc_18000CF47
0x18000cf3e  mov     rcx, rax
0x18000cf41  call    cs:__imp_WIMCloseHandle
0x18000cf47  xor     eax, eax
0x18000cf49  add     rsp, 30h
0x18000cf4d  pop     rbx
0x18000cf4e  retn
```
