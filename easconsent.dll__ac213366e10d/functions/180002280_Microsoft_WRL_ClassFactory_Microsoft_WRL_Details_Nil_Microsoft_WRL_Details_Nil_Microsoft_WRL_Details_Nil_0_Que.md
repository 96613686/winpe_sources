# Microsoft::WRL::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(_GUID const &,void * *)

- ea: `0x180002280`
- end: `0x1800022f1`
- name: `?QueryInterface@?$ClassFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `113`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002280`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  int v4; // eax

  v3 = 0;
  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 != 1
      || a2[1] != *(_DWORD *)&GUID_00000001_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000001_0000_0000_c000_000000000046.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_00000001_0000_0000_c000_000000000046.Data4[4];
  }
  else
  {
    if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      return (unsigned int)-2147467262;
    }
    v4 = *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
  }
  if ( a2[3] != v4 )
    return (unsigned int)-2147467262;
  *a3 = a1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return v3;
}

```

## disassembly

```asm
0x180002280  push    rbx
0x180002282  sub     rsp, 20h
0x180002286  xor     ebx, ebx
0x180002288  mov     [r8], rbx
0x18000228b  cmp     [rdx], ebx
0x18000228d  jnz     short loc_1800022C1
0x18000228f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180002295  cmp     [rdx+4], eax
0x180002298  jnz     short loc_1800022E4
0x18000229a  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1800022a0  cmp     [rdx+8], eax
0x1800022a3  jnz     short loc_1800022E4
0x1800022a5  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x1800022ab  cmp     [rdx+0Ch], eax
0x1800022ae  jnz     short loc_1800022E4
0x1800022b0  mov     [r8], rcx
0x1800022b3  mov     rax, [rcx]
0x1800022b6  mov     rax, [rax+8]
0x1800022ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022bf  jmp     short loc_1800022E9
0x1800022c1  cmp     dword ptr [rdx], 1
0x1800022c4  jnz     short loc_1800022E4
0x1800022c6  mov     eax, dword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data2
0x1800022cc  cmp     [rdx+4], eax
0x1800022cf  jnz     short loc_1800022E4
0x1800022d1  mov     eax, dword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data4
0x1800022d7  cmp     [rdx+8], eax
0x1800022da  jnz     short loc_1800022E4
0x1800022dc  mov     eax, dword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data4+4
0x1800022e2  jmp     short loc_1800022AB
0x1800022e4  mov     ebx, 80004002h
0x1800022e9  mov     eax, ebx
0x1800022eb  add     rsp, 20h
0x1800022ef  pop     rbx
0x1800022f0  retn
```
