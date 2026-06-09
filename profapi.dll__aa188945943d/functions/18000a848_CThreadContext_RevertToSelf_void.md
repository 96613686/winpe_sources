# CThreadContext::RevertToSelf(void)

- ea: `0x18000a848`
- end: `0x18000a86c`
- name: `?RevertToSelf@CThreadContext@@QEAAXXZ`
- size: `36`
- prototype: `void __fastcall(CThreadContext *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800061a4`
- `0x18000a7c4`

## callees

- `0x18000a848`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a85d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a85d`

## pseudocode

```c
void __fastcall CThreadContext::RevertToSelf(CThreadContext *this)
{
  if ( *((_DWORD *)this + 4) )
  {
    RevertToSelf();
    *((_DWORD *)this + 4) = 0;
  }
}

```

## disassembly

```asm
0x18000a848  push    rbx
0x18000a84a  sub     rsp, 20h
0x18000a84e  cmp     dword ptr [rcx+10h], 0
0x18000a852  mov     rbx, rcx
0x18000a855  jnz     short loc_18000A85D
0x18000a857  add     rsp, 20h
0x18000a85b  pop     rbx
0x18000a85c  retn
0x18000a85d  call    cs:__imp_RevertToSelf
0x18000a863  mov     dword ptr [rbx+10h], 0
0x18000a86a  jmp     short loc_18000A857
```
