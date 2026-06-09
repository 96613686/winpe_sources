# Pku2uUnloadCredTable(void)

- ea: `0x18002e59c`
- end: `0x18002e612`
- name: `?Pku2uUnloadCredTable@@YAXXZ`
- size: `118`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002e1d4`

## callees

- `0x18000afc0`
- `0x18002e59c`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18002e60b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002e5ab`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002e5ab`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18002e5e4`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18002e5e4`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002e5d1`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002e5d1`
- `ntdll!RtlReleaseResource` at `0x18002e5f9`
- `ntdll!RtlReleaseResource` at `0x18002e5f9`

## pseudocode

```c
void Pku2uUnloadCredTable(void)
{
  BOOLEAN i; // dl
  struct _PKU2U_SECONDARY_CREDENTIAL **v1; // rax
  struct _PKU2U_SECONDARY_CREDENTIAL **v2; // rbx

  RtlAcquireResourceExclusive(&Pku2uGlobalCredTableLock, 1u);
  for ( i = 1; ; i = 0 )
  {
    v1 = (struct _PKU2U_SECONDARY_CREDENTIAL **)RtlEnumerateGenericTableAvl(&Pku2uGlobalCredTable, i);
    v2 = v1;
    if ( !v1 )
      break;
    *((_DWORD *)*v1 + 3) = 0;
    Pku2uDereferenceSecondaryCredential(*v1);
    if ( !RtlDeleteElementGenericTableAvl(&Pku2uGlobalCredTable, v2) )
      break;
  }
  RtlReleaseResource(&Pku2uGlobalCredTableLock);
  RtlDeleteResource(&Pku2uGlobalCredTableLock);
}

```

## disassembly

```asm
0x18002e59c  push    rbx
0x18002e59e  sub     rsp, 20h
0x18002e5a2  mov     dl, 1; Wait
0x18002e5a4  lea     rcx, ?Pku2uGlobalCredTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18002e5ab  call    cs:__imp_RtlAcquireResourceExclusive
0x18002e5b1  mov     dl, 1
0x18002e5b3  jmp     short loc_18002E5DD
0x18002e5b5  mov     rcx, [rbx]
0x18002e5b8  mov     dword ptr [rcx+0Ch], 0
0x18002e5bf  mov     rcx, [rbx]; struct _PKU2U_SECONDARY_CREDENTIAL *
0x18002e5c2  call    ?Pku2uDereferenceSecondaryCredential@@YAXPEAU_PKU2U_SECONDARY_CREDENTIAL@@@Z; Pku2uDereferenceSecondaryCredential(_PKU2U_SECONDARY_CREDENTIAL *)
0x18002e5c7  mov     rdx, rbx; Buffer
0x18002e5ca  lea     rcx, ?Pku2uGlobalCredTable@@3U_RTL_AVL_TABLE@@A; Table
0x18002e5d1  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18002e5d7  test    al, al
0x18002e5d9  jz      short loc_18002E5F2
0x18002e5db  xor     edx, edx; Restart
0x18002e5dd  lea     rcx, ?Pku2uGlobalCredTable@@3U_RTL_AVL_TABLE@@A; Table
0x18002e5e4  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18002e5ea  mov     rbx, rax
0x18002e5ed  test    rax, rax
0x18002e5f0  jnz     short loc_18002E5B5
0x18002e5f2  lea     rcx, ?Pku2uGlobalCredTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18002e5f9  call    cs:__imp_RtlReleaseResource
0x18002e5ff  lea     rcx, ?Pku2uGlobalCredTableLock@@3U_RTL_RESOURCE@@A; _RTL_RESOURCE Pku2uGlobalCredTableLock
0x18002e606  add     rsp, 20h
0x18002e60a  pop     rbx
0x18002e60b  jmp     cs:__imp_RtlDeleteResource
```
