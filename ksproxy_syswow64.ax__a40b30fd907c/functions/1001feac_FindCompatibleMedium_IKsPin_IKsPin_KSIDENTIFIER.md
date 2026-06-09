# FindCompatibleMedium(IKsPin *,IKsPin *,KSIDENTIFIER *)

- ea: `0x1001feac`
- end: `0x1001feec`
- name: `?FindCompatibleMedium@@YGJPAUIKsPin@@0PAUKSIDENTIFIER@@@Z`
- size: `64`
- prototype: `int __userpurge@<eax>(int *@<edx>, int *@<ecx>, struct IKsPin *, struct IKsPin *, struct KSIDENTIFIER *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100115a5`
- `0x100150a0`
- `0x1001a8f0`

## callees

- `0x1001fd03`
- `0x1001feac`
- `0x1002d510`

## pseudocode

```c
int __userpurge FindCompatibleMedium@<eax>(
        int *a1@<edx>,
        int *a2@<ecx>,
        struct IKsPin *a3,
        struct IKsPin *a4,
        struct KSIDENTIFIER *a5)
{
  int result; // eax
  unsigned int v8; // [esp+0h] [ebp-Ch]
  struct KSIDENTIFIER *v9; // [esp+4h] [ebp-8h]

  if ( !a1 )
    return FindCompatiblePinFactoryIdentifier(a1, a2, (struct IKsPin *)6, a3, v8, v9);
  result = (*(int (__thiscall **)(_DWORD, int *, _DWORD, _DWORD, struct IKsPin *))(*a1 + 24))(
             *(_DWORD *)(*a1 + 24),
             a1,
             0,
             0,
             a3);
  if ( result < 0 )
    return FindCompatiblePinFactoryIdentifier(a1, a2, (struct IKsPin *)6, a3, v8, v9);
  return result;
}

```

## disassembly

```asm
0x1001feac  mov     edi, edi
0x1001feae  push    ebp
0x1001feaf  mov     ebp, esp
0x1001feb1  push    ebx
0x1001feb2  push    esi; struct KSIDENTIFIER *
0x1001feb3  push    edi; unsigned int
0x1001feb4  mov     edi, edx
0x1001feb6  mov     ebx, ecx
0x1001feb8  test    edi, edi
0x1001feba  jz      short loc_1001FED7
0x1001febc  push    [ebp+arg_0]
0x1001febf  mov     eax, [edi]
0x1001fec1  push    0
0x1001fec3  push    0
0x1001fec5  push    edi
0x1001fec6  mov     esi, [eax+18h]
0x1001fec9  mov     ecx, esi; this
0x1001fecb  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001fed1  call    esi
0x1001fed3  test    eax, eax
0x1001fed5  jns     short loc_1001FEE5
0x1001fed7  push    [ebp+arg_0]; struct IKsPin *
0x1001feda  mov     edx, edi
0x1001fedc  mov     ecx, ebx
0x1001fede  push    6; struct IKsPin *
0x1001fee0  call    ?FindCompatiblePinFactoryIdentifier@@YGJPAUIKsPin@@0KPAUKSIDENTIFIER@@@Z; FindCompatiblePinFactoryIdentifier(IKsPin *,IKsPin *,ulong,KSIDENTIFIER *)
0x1001fee5  pop     edi
0x1001fee6  pop     esi
0x1001fee7  pop     ebx
0x1001fee8  pop     ebp
0x1001fee9  retn    4
```
