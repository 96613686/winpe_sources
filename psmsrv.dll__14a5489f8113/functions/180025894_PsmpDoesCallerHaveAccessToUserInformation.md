# PsmpDoesCallerHaveAccessToUserInformation

- ea: `0x180025894`
- end: `0x1800258d4`
- name: `PsmpDoesCallerHaveAccessToUserInformation`
- size: `64`
- prototype: `BOOLEAN __fastcall(PSID Sid2, PSID Sid1, PSID)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002a630`
- `0x18002a7d0`
- `0x18002b200`

## callees

- `0x180025894`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x1800258af`
- `ntdll!RtlEqualSid` at `0x1800258c3`
- `ntdll!RtlEqualSid` at `0x1800258af`
- `ntdll!RtlEqualSid` at `0x1800258c3`

## pseudocode

```c
BOOLEAN __fastcall PsmpDoesCallerHaveAccessToUserInformation(PSID Sid2, PSID Sid1, PSID a3)
{
  if ( a3 && RtlEqualSid(Sid1, a3) )
    return 1;
  else
    return RtlEqualSid(Sid1, Sid2);
}

```

## disassembly

```asm
0x180025894  mov     [rsp+arg_0], rbx
0x180025899  push    rdi
0x18002589a  sub     rsp, 20h
0x18002589e  mov     rbx, rdx
0x1800258a1  mov     rdi, rcx
0x1800258a4  test    r8, r8
0x1800258a7  jz      short loc_1800258BD
0x1800258a9  mov     rdx, r8; Sid2
0x1800258ac  mov     rcx, rbx; Sid1
0x1800258af  call    cs:__imp_RtlEqualSid
0x1800258b5  test    al, al
0x1800258b7  jz      short loc_1800258BD
0x1800258b9  mov     al, 1
0x1800258bb  jmp     short loc_1800258C9
0x1800258bd  mov     rdx, rdi; Sid2
0x1800258c0  mov     rcx, rbx; Sid1
0x1800258c3  call    cs:__imp_RtlEqualSid
0x1800258c9  mov     rbx, [rsp+28h+arg_0]
0x1800258ce  add     rsp, 20h
0x1800258d2  pop     rdi
0x1800258d3  retn
```
