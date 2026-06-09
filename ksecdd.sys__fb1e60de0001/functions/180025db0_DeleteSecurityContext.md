# DeleteSecurityContext

- ea: `0x180025db0`
- end: `0x180025dc4`
- name: `DeleteSecurityContext`
- size: `20`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025e00`

## pseudocode

```c
SECURITY_STATUS __stdcall DeleteSecurityContext(PCtxtHandle phContext)
{
  __int64 v1; // rdx

  return DeleteSecurityContextInternal(0, v1, phContext);
}

```

## disassembly

```asm
0x180025db0  sub     rsp, 28h
0x180025db4  mov     r8, rcx
0x180025db7  xor     ecx, ecx
0x180025db9  call    DeleteSecurityContextInternal
0x180025dbe  add     rsp, 28h
0x180025dc2  retn
```
