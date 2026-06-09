# sub_180B3CCE

- ea: `0x180b3cce`
- end: `0x180b3d88`
- name: `sub_180B3CCE`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1812b965`

## callees

- `0x180b3cce`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void __usercall __noreturn sub_180B3CCE(
        int a1@<eax>,
        int a2@<ecx>,
        char a3@<bh>,
        int a4@<edi>,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int a13,
        int a14,
        int a15,
        int a16,
        int a17,
        int a18,
        int a19,
        int a20,
        int a21,
        int a22,
        int a23,
        int a24,
        int a25,
        int a26,
        int a27,
        int a28,
        int a29,
        int a30,
        char a31,
        int a32,
        int a33,
        int a34,
        int a35,
        int a36,
        int a37,
        char a38,
        int a39,
        int a40,
        int a41,
        int a42)
{
  int v42; // ecx
  int v43; // ecx
  int v44; // ecx
  _UNKNOWN *retaddr; // [esp+0h] [ebp+0h] BYREF

  *(_BYTE *)(a4 - 17) += BYTE1(a2);
  ((void (__thiscall *)(int, int))L"8A007-E189-409D-A2C8-9AF4EF3C72AA}")(a2 - 1, a1);
  (*(void (__thiscall **)(int))(a4 + 40))(a6);
  MEMORY[0x382FB1B7](v42 - 16);
  MEMORY[0x3C2FB9C3](&a36);
  MEMORY[0x402F89D2](&a29, a27);
  MEMORY[0x782F89D5]();
  MEMORY[0x742FB9D3](v43 - 16);
  if ( a3 )
  {
    MEMORY[0x8D0AC2BA]();
    ((void (*)(void))((char *)&byte_1816A001 + 135))();
    MEMORY[0xFB8C02](a23 - 16);
    v44 = a40;
  }
  MEMORY[0xDB692313]((unsigned int)&retaddr ^ v44);
  JUMPOUT(0x180B3D88);
}

```

## disassembly

```asm
0x180b3cce  add     [edi-11h], ch
0x180b3cd1  dec     ecx
0x180b3cd2  push    eax
0x180b3cd3  call    dword ptr ds:a8a007E189409dA; "8A007-E189-409D-A2C8-9AF4EF3C72AA}"
0x180b3cd9  mov     ecx, [esp+4+arg_C]
0x180b3cdd  call    dword ptr [edi+28h]
0x180b3ce0  jmp     short loc_180B3D24
0x180b3d24  lea     ecx, [ecx-10h]
0x180b3d27  call    near ptr 382FB1B7h
0x180b3d2c  lea     ecx, [esp+4+arg_84]
0x180b3d33  call    near ptr 3C2FB9C3h
0x180b3d38  push    [esp+4+arg_60]
0x180b3d3c  lea     ecx, [esp+8+arg_68]
0x180b3d40  call    near ptr 402F89D2h
0x180b3d45  call    near ptr 782F89D5h
0x180b3d4a  lea     ecx, [ecx-10h]
0x180b3d4d  call    near ptr 742FB9D3h
0x180b3d52  add     eax, 74800040h
0x180b3d57  or      bh, bh
0x180b3d59  jz      short loc_180B3D7F
0x180b3d5b  pop     esp
0x180b3d5c  call    near ptr 8D0AC2BAh
0x180b3d61  pop     es
0x180b3d62  push    edi
0x180b3d63  call    dword ptr ds:byte_1816A001+87h
0x180b3d69  mov     ecx, [esp+4+arg_50]
0x180b3d6d  add     ecx, 0FFFFFFF0h
0x180b3d70  call    near ptr 0FB8C02h
0x180b3d75  mov     eax, ebx
0x180b3d77  mov     ecx, [esp+4+arg_94]
0x180b3d7e  pop     edi
0x180b3d7f  pop     esi
0x180b3d80  pop     ebx
0x180b3d81  xor     ecx, esp
0x180b3d83  call    near ptr 0DB692313h
```
