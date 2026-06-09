# Pku2uUnloadLogonSessionTable(void)

- ea: `0x18002cedc`
- end: `0x18002cf48`
- name: `?Pku2uUnloadLogonSessionTable@@YAXXZ`
- size: `108`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002cd5c`

## callees

- `0x18000af80`
- `0x18002cedc`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18002cf41`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002ceeb`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002ceeb`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18002cf1a`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18002cf1a`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002cf07`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002cf07`
- `ntdll!RtlReleaseResource` at `0x18002cf2f`
- `ntdll!RtlReleaseResource` at `0x18002cf2f`

## pseudocode

```c
void Pku2uUnloadLogonSessionTable(void)
{
  BOOLEAN i; // dl
  struct _PKU2U_LOGON_SESSION **v1; // rax
  struct _PKU2U_LOGON_SESSION **v2; // rbx

  RtlAcquireResourceExclusive(&Pku2uGlobalLogonSessionTableLock, 1u);
  for ( i = 1; ; i = 0 )
  {
    v1 = (struct _PKU2U_LOGON_SESSION **)RtlEnumerateGenericTableAvl(&Pku2uGlobalLogonSessionTable, i);
    v2 = v1;
    if ( !v1 )
      break;
    Pku2uDereferenceLogonSession(*v1);
    if ( !RtlDeleteElementGenericTableAvl(&Pku2uGlobalLogonSessionTable, v2) )
      break;
  }
  RtlReleaseResource(&Pku2uGlobalLogonSessionTableLock);
  RtlDeleteResource(&Pku2uGlobalLogonSessionTableLock);
}

```

## disassembly

```asm
0x18002cedc  push    rbx
0x18002cede  sub     rsp, 20h
0x18002cee2  mov     dl, 1; Wait
0x18002cee4  lea     rcx, ?Pku2uGlobalLogonSessionTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18002ceeb  call    cs:__imp_RtlAcquireResourceExclusive
0x18002cef1  mov     dl, 1
0x18002cef3  jmp     short loc_18002CF13
0x18002cef5  mov     rcx, [rbx]; struct _PKU2U_LOGON_SESSION *
0x18002cef8  call    ?Pku2uDereferenceLogonSession@@YAXPEAU_PKU2U_LOGON_SESSION@@@Z; Pku2uDereferenceLogonSession(_PKU2U_LOGON_SESSION *)
0x18002cefd  mov     rdx, rbx; Buffer
0x18002cf00  lea     rcx, ?Pku2uGlobalLogonSessionTable@@3U_RTL_AVL_TABLE@@A; Table
0x18002cf07  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18002cf0d  test    al, al
0x18002cf0f  jz      short loc_18002CF28
0x18002cf11  xor     edx, edx; Restart
0x18002cf13  lea     rcx, ?Pku2uGlobalLogonSessionTable@@3U_RTL_AVL_TABLE@@A; Table
0x18002cf1a  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18002cf20  mov     rbx, rax
0x18002cf23  test    rax, rax
0x18002cf26  jnz     short loc_18002CEF5
0x18002cf28  lea     rcx, ?Pku2uGlobalLogonSessionTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18002cf2f  call    cs:__imp_RtlReleaseResource
0x18002cf35  lea     rcx, ?Pku2uGlobalLogonSessionTableLock@@3U_RTL_RESOURCE@@A; _RTL_RESOURCE Pku2uGlobalLogonSessionTableLock
0x18002cf3c  add     rsp, 20h
0x18002cf40  pop     rbx
0x18002cf41  jmp     cs:__imp_RtlDeleteResource
```
