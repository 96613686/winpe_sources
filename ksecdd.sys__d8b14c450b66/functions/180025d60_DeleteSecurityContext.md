# DeleteSecurityContext

- ea: `0x180025d60`
- end: `0x180025d74`
- name: `DeleteSecurityContext`
- size: `20`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025db0`

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
0x180025d60  sub     rsp, 28h
0x180025d64  mov     r8, rcx
0x180025d67  xor     ecx, ecx
0x180025d69  call    DeleteSecurityContextInternal
0x180025d6e  add     rsp, 28h
0x180025d72  retn
```
