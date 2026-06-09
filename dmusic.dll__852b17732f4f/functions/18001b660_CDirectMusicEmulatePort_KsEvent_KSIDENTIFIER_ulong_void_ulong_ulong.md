# CDirectMusicEmulatePort::KsEvent(KSIDENTIFIER *,ulong,void *,ulong,ulong *)

- ea: `0x18001b660`
- end: `0x18001b684`
- name: `?KsEvent@CDirectMusicEmulatePort@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z`
- size: `36`
- prototype: `__int64 __fastcall(CDirectMusicEmulatePort *__hidden this, struct KSIDENTIFIER *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18001b660`

## pseudocode

```c
__int64 __fastcall CDirectMusicEmulatePort::KsEvent(
        CDirectMusicEmulatePort *this,
        struct KSIDENTIFIER *a2,
        int a3,
        void *a4,
        unsigned int a5,
        unsigned int *a6)
{
  __int64 result; // rax

  if ( a3 && !a2 )
    return 2147500035LL;
  result = 2289570082LL;
  if ( !a6 )
    return 2147500035LL;
  return result;
}

```

## disassembly

```asm
0x18001b660  test    r8d, r8d
0x18001b663  jz      short loc_18001B670
0x18001b665  test    rdx, rdx
0x18001b668  jnz     short loc_18001B670
0x18001b66a  mov     eax, 80004003h
0x18001b66f  retn
0x18001b670  cmp     [rsp+arg_28], 0
0x18001b676  mov     eax, 88781122h
0x18001b67b  mov     ecx, 80004003h
0x18001b680  cmovz   eax, ecx
0x18001b683  retn
```
