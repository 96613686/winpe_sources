# FindCompatibleInterface(IKsPin *,IKsPin *,KSIDENTIFIER *)

- ea: `0x1001fe62`
- end: `0x1001fea6`
- name: `?FindCompatibleInterface@@YGJPAUIKsPin@@0PAUKSIDENTIFIER@@@Z`
- size: `68`
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
- `0x1001fe62`
- `0x1002d510`

## pseudocode

```c
int __userpurge FindCompatibleInterface@<eax>(
        int *a1@<edx>,
        int *a2@<ecx>,
        struct IKsPin *a3,
        struct IKsPin *a4,
        struct KSIDENTIFIER *a5)
{
  unsigned int v8; // [esp+0h] [ebp-Ch]
  struct KSIDENTIFIER *v9; // [esp+4h] [ebp-8h]

  if ( a1
    && (*(int (__thiscall **)(_DWORD, int *, _DWORD, struct IKsPin *, _DWORD))(*a1 + 24))(
         *(_DWORD *)(*a1 + 24),
         a1,
         0,
         a3,
         0) >= 0 )
  {
    return 0;
  }
  else
  {
    return FindCompatiblePinFactoryIdentifier(a1, a2, (struct IKsPin *)5, a3, v8, v9);
  }
}

```

## disassembly

```asm
0x1001fe62  mov     edi, edi
0x1001fe64  push    ebp
0x1001fe65  mov     ebp, esp
0x1001fe67  push    ebx
0x1001fe68  push    esi; struct KSIDENTIFIER *
0x1001fe69  push    edi; unsigned int
0x1001fe6a  mov     edi, edx
0x1001fe6c  mov     ebx, ecx
0x1001fe6e  test    edi, edi
0x1001fe70  jz      short loc_1001FE91
0x1001fe72  mov     eax, [edi]
0x1001fe74  push    0
0x1001fe76  push    [ebp+arg_0]
0x1001fe79  mov     esi, [eax+18h]
0x1001fe7c  mov     ecx, esi; this
0x1001fe7e  push    0
0x1001fe80  push    edi
0x1001fe81  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001fe87  call    esi
0x1001fe89  test    eax, eax
0x1001fe8b  js      short loc_1001FE91
0x1001fe8d  xor     eax, eax
0x1001fe8f  jmp     short loc_1001FE9F
0x1001fe91  push    [ebp+arg_0]; struct IKsPin *
0x1001fe94  mov     edx, edi
0x1001fe96  mov     ecx, ebx
0x1001fe98  push    5; struct IKsPin *
0x1001fe9a  call    ?FindCompatiblePinFactoryIdentifier@@YGJPAUIKsPin@@0KPAUKSIDENTIFIER@@@Z; FindCompatiblePinFactoryIdentifier(IKsPin *,IKsPin *,ulong,KSIDENTIFIER *)
0x1001fe9f  pop     edi
0x1001fea0  pop     esi
0x1001fea1  pop     ebx
0x1001fea2  pop     ebp
0x1001fea3  retn    4
```
