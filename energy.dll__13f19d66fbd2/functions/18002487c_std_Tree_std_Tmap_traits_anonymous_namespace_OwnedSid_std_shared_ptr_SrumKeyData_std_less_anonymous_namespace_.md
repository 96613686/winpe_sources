# std::_Tree_std::_Tmap_traits__anonymous_namespace_::OwnedSid_std::shared_ptr_SrumKeyData__std::less__anonymous_namespace_::OwnedSid__std::allocator_std::pair__anonymous_namespace_::OwnedSid_const__std::shared_ptr_SrumKeyData______0___::_Lower_bound_duplicate__anonymous_namespace_::OwnedSid_

- ea: `0x18002487c`
- end: `0x1800248db`
- name: `std::_Tree_std::_Tmap_traits__anonymous_namespace_::OwnedSid_std::shared_ptr_SrumKeyData__std::less__anonymous_namespace_::OwnedSid__std::allocator_std::pair__anonymous_namespace_::OwnedSid_const__std::shared_ptr_SrumKeyData______0___::_Lower_bound_duplicate__anonymous_namespace_::OwnedSid_`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800247c0`

## callees

- `0x18002487c`
- `0x18004d8d8`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002489a`
- `ntdll!RtlLengthSid` at `0x1800248a6`
- `ntdll!RtlLengthSid` at `0x18002489a`
- `ntdll!RtlLengthSid` at `0x1800248a6`

## pseudocode

```c
bool __fastcall std::_Tree_std::_Tmap_traits__anonymous_namespace_::OwnedSid_std::shared_ptr_SrumKeyData__std::less__anonymous_namespace_::OwnedSid__std::allocator_std::pair__anonymous_namespace_::OwnedSid_const__std::shared_ptr_SrumKeyData______0___::_Lower_bound_duplicate__anonymous_namespace_::OwnedSid_(
        __int64 a1,
        __int64 a2,
        PSID *a3)
{
  ULONG v5; // edi
  ULONG v6; // eax
  bool result; // al

  result = 0;
  if ( !*(_BYTE *)(a2 + 25) )
  {
    v5 = RtlLengthSid(*a3);
    v6 = RtlLengthSid(*(PSID *)(a2 + 32));
    if ( v5 >= v6 && (v5 > v6 || memcmp_0(*a3, *(const void **)(a2 + 32), v5) >= 0) )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18002487c  mov     [rsp+arg_0], rbx
0x180024881  mov     [rsp+arg_8], rsi
0x180024886  push    rdi
0x180024887  sub     rsp, 20h
0x18002488b  cmp     byte ptr [rdx+19h], 0
0x18002488f  mov     rsi, r8
0x180024892  mov     rbx, rdx
0x180024895  jnz     short loc_1800248D7
0x180024897  mov     rcx, [r8]; Sid
0x18002489a  call    cs:__imp_RtlLengthSid
0x1800248a0  mov     rcx, [rbx+20h]; Sid
0x1800248a4  mov     edi, eax
0x1800248a6  call    cs:__imp_RtlLengthSid
0x1800248ac  cmp     edi, eax
0x1800248ae  jb      short loc_1800248D7
0x1800248b0  ja      short loc_1800248C5
0x1800248b2  mov     rdx, [rbx+20h]; Buf2
0x1800248b6  mov     r8d, edi; Size
0x1800248b9  mov     rcx, [rsi]; Buf1
0x1800248bc  call    memcmp_0
0x1800248c1  test    eax, eax
0x1800248c3  js      short loc_1800248D7
0x1800248c5  mov     al, 1
0x1800248c7  mov     rbx, [rsp+28h+arg_0]
0x1800248cc  mov     rsi, [rsp+28h+arg_8]
0x1800248d1  add     rsp, 20h
0x1800248d5  pop     rdi
0x1800248d6  retn
0x1800248d7  xor     al, al
0x1800248d9  jmp     short loc_1800248C7
```
