# KerbUnloadLogonSessionTable(void)

- ea: `0x1800908ec`
- end: `0x180090956`
- name: `?KerbUnloadLogonSessionTable@@YAXXZ`
- size: `106`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007e540`
- `0x18008ffe0`

## callees

- `0x18000a630`
- `0x1800908ec`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18009094f`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18009092b`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18009092b`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180090910`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180090910`
- `ntdll!RtlReleaseResource` at `0x18009093d`
- `ntdll!RtlReleaseResource` at `0x18009093d`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800908fb`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800908fb`

## pseudocode

```c
void KerbUnloadLogonSessionTable(void)
{
  struct _KERB_LOGON_SESSION *v0; // rbx
  struct _KERB_LOGON_SESSION **v1; // rax

  RtlAcquireResourceExclusive(&KerbGlobalLogonSessionTableLock, 1u);
  while ( 1 )
  {
    v1 = (struct _KERB_LOGON_SESSION **)RtlEnumerateGenericTableAvl(&KerbGlobalLogonSessionTable, 1u);
    if ( !v1 )
      break;
    v0 = *v1;
    if ( !RtlDeleteElementGenericTableAvl(&KerbGlobalLogonSessionTable, v1) )
      break;
    KerbDereferenceLogonSession(v0);
  }
  RtlReleaseResource(&KerbGlobalLogonSessionTableLock);
  RtlDeleteResource(&KerbGlobalLogonSessionTableLock);
}

```

## disassembly

```asm
0x1800908ec  push    rbx
0x1800908ee  sub     rsp, 20h
0x1800908f2  mov     dl, 1; Wait
0x1800908f4  lea     rcx, ?KerbGlobalLogonSessionTableLock@@3U_RTL_RESOURCE@@A; Resource
0x1800908fb  call    cs:__imp_RtlAcquireResourceExclusive
0x180090901  jmp     short loc_180090922
0x180090903  mov     rbx, [rax]
0x180090906  lea     rcx, ?KerbGlobalLogonSessionTable@@3U_RTL_AVL_TABLE@@A; Table
0x18009090d  mov     rdx, rax; Buffer
0x180090910  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180090916  test    al, al
0x180090918  jz      short loc_180090936
0x18009091a  mov     rcx, rbx; struct _KERB_LOGON_SESSION *
0x18009091d  call    ?KerbDereferenceLogonSession@@YAXPEAU_KERB_LOGON_SESSION@@@Z; KerbDereferenceLogonSession(_KERB_LOGON_SESSION *)
0x180090922  mov     dl, 1; Restart
0x180090924  lea     rcx, ?KerbGlobalLogonSessionTable@@3U_RTL_AVL_TABLE@@A; Table
0x18009092b  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180090931  test    rax, rax
0x180090934  jnz     short loc_180090903
0x180090936  lea     rcx, ?KerbGlobalLogonSessionTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18009093d  call    cs:__imp_RtlReleaseResource
0x180090943  lea     rcx, ?KerbGlobalLogonSessionTableLock@@3U_RTL_RESOURCE@@A; _RTL_RESOURCE KerbGlobalLogonSessionTableLock
0x18009094a  add     rsp, 20h
0x18009094e  pop     rbx
0x18009094f  jmp     cs:__imp_RtlDeleteResource
```
