# CUserModeSynth::KsEvent(KSIDENTIFIER *,ulong,void *,ulong,ulong *)

- ea: `0x18000fcf0`
- end: `0x18000fd14`
- name: `?KsEvent@CUserModeSynth@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z`
- size: `36`
- prototype: `__int64 __fastcall(CUserModeSynth *__hidden this, struct KSIDENTIFIER *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18000fcf0`

## pseudocode

```c
__int64 __fastcall CUserModeSynth::KsEvent(
        CUserModeSynth *this,
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
0x18000fcf0  test    r8d, r8d
0x18000fcf3  jz      short loc_18000FD00
0x18000fcf5  test    rdx, rdx
0x18000fcf8  jnz     short loc_18000FD00
0x18000fcfa  mov     eax, 80004003h
0x18000fcff  retn
0x18000fd00  cmp     [rsp+arg_28], 0
0x18000fd06  mov     eax, 88781122h
0x18000fd0b  mov     ecx, 80004003h
0x18000fd10  cmovz   eax, ecx
0x18000fd13  retn
```
