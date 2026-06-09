# CASFReader::GetClassID(_GUID *)

- ea: `0x180009800`
- end: `0x180009832`
- name: `?GetClassID@CASFReader@@UEAAJPEAU_GUID@@@Z`
- size: `50`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180009800`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::GetClassID(CASFReader *this, struct _GUID *a2)
{
  __int64 v2; // r8
  __int64 result; // rax

  v2 = *((_QWORD *)this + 55);
  if ( v2 )
    return (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(*(_QWORD *)v2 + 24LL))(*((_QWORD *)this + 55), a2);
  if ( !a2 )
    return 2147500035LL;
  result = 0;
  *a2 = *(struct _GUID *)((char *)this + 40);
  return result;
}

```

## disassembly

```asm
0x180009800  mov     r8, [rcx+1B8h]
0x180009807  test    r8, r8
0x18000980a  jz      short loc_18000981B
0x18000980c  mov     rax, [r8]
0x18000980f  mov     rcx, r8
0x180009812  mov     rax, [rax+18h]
0x180009816  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000981b  test    rdx, rdx
0x18000981e  jnz     short loc_180009827
0x180009820  mov     eax, 80004003h
0x180009825  jmp     short locret_180009831
0x180009827  movups  xmm0, xmmword ptr [rcx+28h]
0x18000982b  xor     eax, eax
0x18000982d  movdqu  xmmword ptr [rdx], xmm0
0x180009831  retn
```
