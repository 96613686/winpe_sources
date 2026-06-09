# UnpackUserSid

- ea: `0x1800182d0`
- end: `0x1800182f6`
- name: `UnpackUserSid`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022f70`

## callees

- `0x1800182d0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800182df`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800182df`

## pseudocode

```c
BOOL __fastcall UnpackUserSid(__int64 a1, void *a2, _QWORD *a3)
{
  BOOL result; // eax

  *a3 = a2;
  result = IsValidSid(a2);
  if ( !result )
    *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x1800182d0  push    rbx
0x1800182d2  sub     rsp, 20h
0x1800182d6  mov     rcx, rdx; pSid
0x1800182d9  mov     [r8], rdx
0x1800182dc  mov     rbx, r8
0x1800182df  call    cs:__imp_IsValidSid
0x1800182e5  test    eax, eax
0x1800182e7  jnz     short loc_1800182F0
0x1800182e9  mov     qword ptr [rbx], 0
0x1800182f0  add     rsp, 20h
0x1800182f4  pop     rbx
0x1800182f5  retn
```
