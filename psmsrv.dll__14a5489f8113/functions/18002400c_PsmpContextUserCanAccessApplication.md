# PsmpContextUserCanAccessApplication

- ea: `0x18002400c`
- end: `0x180024067`
- name: `PsmpContextUserCanAccessApplication`
- size: `91`
- prototype: `bool __fastcall(__int64, void *, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000dbd0`

## callees

- `0x18002400c`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18002402f`
- `ntdll!RtlEqualSid` at `0x180024049`
- `ntdll!RtlEqualSid` at `0x18002402f`
- `ntdll!RtlEqualSid` at `0x180024049`

## pseudocode

```c
bool __fastcall PsmpContextUserCanAccessApplication(__int64 a1, void *a2, __int64 a3)
{
  __int64 v3; // rbx

  v3 = *(_QWORD *)(a3 + 312);
  if ( v3 )
  {
    if ( RtlEqualSid(a2, *(PSID *)(v3 + 40)) )
      return 1;
    if ( *(_DWORD *)(a1 + 116) == *(_DWORD *)(v3 + 4) )
      return RtlEqualSid((PSID)(a1 + 48), *(PSID *)(v3 + 40)) != 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18002400c  mov     [rsp+arg_0], rbx
0x180024011  push    rdi
0x180024012  sub     rsp, 20h
0x180024016  mov     rbx, [r8+138h]
0x18002401d  mov     rax, rdx
0x180024020  mov     rdi, rcx
0x180024023  test    rbx, rbx
0x180024026  jz      short loc_18002405A
0x180024028  mov     rdx, [rbx+28h]; Sid2
0x18002402c  mov     rcx, rax; Sid1
0x18002402f  call    cs:__imp_RtlEqualSid
0x180024035  test    al, al
0x180024037  jnz     short loc_180024056
0x180024039  mov     eax, [rbx+4]
0x18002403c  cmp     [rdi+74h], eax
0x18002403f  jnz     short loc_18002405A
0x180024041  mov     rdx, [rbx+28h]; Sid2
0x180024045  lea     rcx, [rdi+30h]; Sid1
0x180024049  call    cs:__imp_RtlEqualSid
0x18002404f  test    al, al
0x180024051  setnz   al
0x180024054  jmp     short loc_18002405C
0x180024056  mov     al, 1
0x180024058  jmp     short loc_18002405C
0x18002405a  xor     al, al
0x18002405c  mov     rbx, [rsp+28h+arg_0]
0x180024061  add     rsp, 20h
0x180024065  pop     rdi
0x180024066  retn
```
