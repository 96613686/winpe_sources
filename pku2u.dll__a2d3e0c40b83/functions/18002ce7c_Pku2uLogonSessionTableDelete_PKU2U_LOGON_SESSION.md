# Pku2uLogonSessionTableDelete(_PKU2U_LOGON_SESSION *)

- ea: `0x18002ce7c`
- end: `0x18002ced4`
- name: `?Pku2uLogonSessionTableDelete@@YAJPEAU_PKU2U_LOGON_SESSION@@@Z`
- size: `88`
- prototype: `__int64 __fastcall(struct _PKU2U_LOGON_SESSION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180011c30`

## callees

- `0x18000af80`
- `0x18002ce7c`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18002ce90`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002ce90`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002cea2`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002cea2`
- `ntdll!RtlReleaseResource` at `0x18002cec6`
- `ntdll!RtlReleaseResource` at `0x18002cec6`

## pseudocode

```c
__int64 __fastcall Pku2uLogonSessionTableDelete(struct _PKU2U_LOGON_SESSION *a1)
{
  unsigned int v1; // ebx
  struct _PKU2U_LOGON_SESSION *Buffer; // [rsp+30h] [rbp+8h] BYREF

  Buffer = a1;
  RtlAcquireResourceExclusive(&Pku2uGlobalLogonSessionTableLock, 1u);
  if ( RtlDeleteElementGenericTableAvl(&Pku2uGlobalLogonSessionTable, &Buffer) )
  {
    v1 = 0;
    Pku2uDereferenceLogonSession(Buffer);
  }
  else
  {
    v1 = -1073741816;
  }
  RtlReleaseResource(&Pku2uGlobalLogonSessionTableLock);
  return v1;
}

```

## disassembly

```asm
0x18002ce7c  push    rbx
0x18002ce7e  sub     rsp, 20h
0x18002ce82  mov     [rsp+28h+Buffer], rcx
0x18002ce87  mov     dl, 1; Wait
0x18002ce89  lea     rcx, ?Pku2uGlobalLogonSessionTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18002ce90  call    cs:__imp_RtlAcquireResourceExclusive
0x18002ce96  lea     rdx, [rsp+28h+Buffer]; Buffer
0x18002ce9b  lea     rcx, ?Pku2uGlobalLogonSessionTable@@3U_RTL_AVL_TABLE@@A; Table
0x18002cea2  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18002cea8  test    al, al
0x18002ceaa  jz      short loc_18002CEBA
0x18002ceac  mov     rcx, [rsp+28h+Buffer]; struct _PKU2U_LOGON_SESSION *
0x18002ceb1  xor     ebx, ebx
0x18002ceb3  call    ?Pku2uDereferenceLogonSession@@YAXPEAU_PKU2U_LOGON_SESSION@@@Z; Pku2uDereferenceLogonSession(_PKU2U_LOGON_SESSION *)
0x18002ceb8  jmp     short loc_18002CEBF
0x18002ceba  mov     ebx, 0C0000008h
0x18002cebf  lea     rcx, ?Pku2uGlobalLogonSessionTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18002cec6  call    cs:__imp_RtlReleaseResource
0x18002cecc  mov     eax, ebx
0x18002cece  add     rsp, 20h
0x18002ced2  pop     rbx
0x18002ced3  retn
```
