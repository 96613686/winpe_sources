# std::_Tree_std::_Tmap_traits__anonymous_namespace_::OwnedSid_std::shared_ptr_SrumKeyData__std::less__anonymous_namespace_::OwnedSid__std::allocator_std::pair__anonymous_namespace_::OwnedSid_const__std::shared_ptr_SrumKeyData______0___::_Find_lower_bound__anonymous_namespace_::OwnedSid_

- ea: `0x1800248f0`
- end: `0x180024995`
- name: `std::_Tree_std::_Tmap_traits__anonymous_namespace_::OwnedSid_std::shared_ptr_SrumKeyData__std::less__anonymous_namespace_::OwnedSid__std::allocator_std::pair__anonymous_namespace_::OwnedSid_const__std::shared_ptr_SrumKeyData______0___::_Find_lower_bound__anonymous_namespace_::OwnedSid_`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800247c0`

## callees

- `0x1800248f0`
- `0x18004d8d8`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180024935`
- `ntdll!RtlLengthSid` at `0x180024940`
- `ntdll!RtlLengthSid` at `0x180024935`
- `ntdll!RtlLengthSid` at `0x180024940`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_std::_Tmap_traits__anonymous_namespace_::OwnedSid_std::shared_ptr_SrumKeyData__std::less__anonymous_namespace_::OwnedSid__std::allocator_std::pair__anonymous_namespace_::OwnedSid_const__std::shared_ptr_SrumKeyData______0___::_Find_lower_bound__anonymous_namespace_::OwnedSid_(
        __int64 a1,
        _QWORD *a2,
        PSID *a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rbx
  ULONG v7; // edi
  ULONG v8; // eax
  int v9; // eax

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    v7 = RtlLengthSid((PSID)v6[4]);
    v8 = RtlLengthSid(*a3);
    if ( v7 < v8 || v7 <= v8 && memcmp_0((const void *)v6[4], *a3, v7) < 0 )
    {
      v6 += 2;
      v9 = 0;
    }
    else
    {
      a2[2] = v6;
      v9 = 1;
    }
    *((_DWORD *)a2 + 2) = v9;
  }
  return a2;
}

```

## disassembly

```asm
0x1800248f0  mov     [rsp+arg_8], rbx
0x1800248f5  mov     [rsp+arg_10], rsi
0x1800248fa  push    r14
0x1800248fc  sub     rsp, 20h
0x180024900  mov     rax, [rcx]
0x180024903  mov     r14, r8
0x180024906  mov     rsi, rdx
0x180024909  mov     r9, [rax+8]
0x18002490d  mov     [rdx], r9
0x180024910  mov     rbx, r9
0x180024913  mov     qword ptr [rdx+8], 0
0x18002491b  mov     rax, [rcx]
0x18002491e  mov     [rdx+10h], rax
0x180024922  cmp     byte ptr [r9+19h], 0
0x180024927  jnz     short loc_180024979
0x180024929  mov     [rsp+28h+arg_0], rdi
0x18002492e  mov     [rsi], rbx
0x180024931  mov     rcx, [rbx+20h]; Sid
0x180024935  call    cs:__imp_RtlLengthSid
0x18002493b  mov     rcx, [r14]; Sid
0x18002493e  mov     edi, eax
0x180024940  call    cs:__imp_RtlLengthSid
0x180024946  cmp     edi, eax
0x180024948  jb      short loc_18002498D
0x18002494a  ja      short loc_18002495F
0x18002494c  mov     rdx, [r14]; Buf2
0x18002494f  mov     r8d, edi; Size
0x180024952  mov     rcx, [rbx+20h]; Buf1
0x180024956  call    memcmp_0
0x18002495b  test    eax, eax
0x18002495d  js      short loc_18002498D
0x18002495f  mov     [rsi+10h], rbx
0x180024963  mov     eax, 1
0x180024968  mov     [rsi+8], eax
0x18002496b  mov     rbx, [rbx]
0x18002496e  cmp     byte ptr [rbx+19h], 0
0x180024972  jz      short loc_18002492E
0x180024974  mov     rdi, [rsp+28h+arg_0]
0x180024979  mov     rbx, [rsp+28h+arg_8]
0x18002497e  mov     rax, rsi
0x180024981  mov     rsi, [rsp+28h+arg_10]
0x180024986  add     rsp, 20h
0x18002498a  pop     r14
0x18002498c  retn
0x18002498d  add     rbx, 10h
0x180024991  xor     eax, eax
0x180024993  jmp     short loc_180024968
```
