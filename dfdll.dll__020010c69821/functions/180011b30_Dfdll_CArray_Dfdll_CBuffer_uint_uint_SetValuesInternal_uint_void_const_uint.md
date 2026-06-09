# Dfdll::CArray<Dfdll::CBuffer<uint>,uint>::SetValuesInternal(uint,void const *,uint)

- ea: `0x180011b30`
- end: `0x180011b92`
- name: `?SetValuesInternal@?$CArray@V?$CBuffer@I@Dfdll@@I@Dfdll@@MEAAJIPEBXI@Z`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180011b30`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CArray<Dfdll::CBuffer<unsigned int>,unsigned int>::SetValuesInternal(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        int a4)
{
  unsigned int v4; // ebx
  int v5; // eax

  v4 = 0;
  if ( a4 )
  {
    if ( !a3 )
      return (unsigned int)-2147024809;
    if ( a2 > ~a4 || !(a2 + a4) )
      return (unsigned int)-2147024362;
    if ( a2 + a4 - 1 < *(_DWORD *)(a1 + 8) )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)(a1 + 24) + 104LL))(a1 + 24, a3, a2);
      if ( v5 >= 0 )
        return 0;
      return (unsigned int)v5;
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180011b30  push    rbx
0x180011b32  sub     rsp, 30h
0x180011b36  xor     ebx, ebx
0x180011b38  mov     r10, r8
0x180011b3b  test    r9d, r9d
0x180011b3e  jz      short loc_180011B8A
0x180011b40  test    r8, r8
0x180011b43  jnz     short loc_180011B4C
0x180011b45  mov     ebx, 80070057h
0x180011b4a  jmp     short loc_180011B8A
0x180011b4c  mov     eax, r9d
0x180011b4f  not     eax
0x180011b51  cmp     edx, eax
0x180011b53  jbe     short loc_180011B5C
0x180011b55  mov     ebx, 80070216h
0x180011b5a  jmp     short loc_180011B8A
0x180011b5c  lea     eax, [rdx+r9]
0x180011b60  cmp     eax, 1
0x180011b63  jb      short loc_180011B55
0x180011b65  dec     eax
0x180011b67  cmp     eax, [rcx+8]
0x180011b6a  jnb     short loc_180011B45
0x180011b6c  add     rcx, 18h
0x180011b70  mov     r8d, edx
0x180011b73  mov     rdx, r10
0x180011b76  mov     rax, [rcx]
0x180011b79  mov     rax, [rax+68h]
0x180011b7d  call    cs:__guard_dispatch_icall_fptr
0x180011b83  test    eax, eax
0x180011b85  cmovns  eax, ebx
0x180011b88  mov     ebx, eax
0x180011b8a  mov     eax, ebx
0x180011b8c  add     rsp, 30h
0x180011b90  pop     rbx
0x180011b91  retn
```
