# ReadOTFHeadTable

- ea: `0x14008fb68`
- end: `0x14008fc0b`
- name: `ReadOTFHeadTable`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140059d9c`

## callees

- `0x14005a3c4`
- `0x140075de0`
- `0x14008fb68`
- `0x140098010`

## pseudocode

```c
__int64 __fastcall ReadOTFHeadTable(__int64 a1, __int64 a2, _DWORD *a3)
{
  unsigned int v5; // r9d
  unsigned int v6; // r9d
  _BYTE v7[4]; // [rsp+30h] [rbp-118h] BYREF
  _BYTE v8[16]; // [rsp+34h] [rbp-114h] BYREF
  _BYTE v9[4]; // [rsp+44h] [rbp-104h] BYREF
  _BYTE v10[232]; // [rsp+48h] [rbp-100h] BYREF

  if ( (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))(a1 + 8))(*(_QWORD *)a1, v7, 48) != 1 )
    return 0xFFFFFFFFLL;
  a3[44] = getnum(v8, 4);
  a3[45] = getnum(v9, v5);
  a3[46] = getnum(v10, v6);
  return 0;
}

```

## disassembly

```asm
0x14008fb68  push    rbx
0x14008fb6a  sub     rsp, 140h
0x14008fb71  mov     rax, cs:__security_cookie
0x14008fb78  xor     rax, rsp
0x14008fb7b  mov     [rsp+148h+var_18], rax
0x14008fb83  mov     rax, [rcx+8]
0x14008fb87  mov     r9d, 1
0x14008fb8d  mov     rcx, [rcx]
0x14008fb90  mov     rbx, r8
0x14008fb93  mov     [rsp+148h+var_128], rdx
0x14008fb98  lea     rdx, [rsp+148h+var_118]
0x14008fb9d  lea     r8d, [r9+2Fh]
0x14008fba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008fba6  cmp     rax, 1
0x14008fbaa  jz      short loc_14008FBB1
0x14008fbac  or      eax, 0FFFFFFFFh
0x14008fbaf  jmp     short loc_14008FBF2
0x14008fbb1  mov     r9d, 4
0x14008fbb7  lea     rcx, [rsp+148h+var_114]
0x14008fbbc  mov     edx, r9d
0x14008fbbf  call    getnum
0x14008fbc4  mov     edx, r9d
0x14008fbc7  mov     [rbx+0B0h], eax
0x14008fbcd  lea     rcx, [rsp+148h+var_104]
0x14008fbd2  call    getnum
0x14008fbd7  mov     edx, r9d
0x14008fbda  mov     [rbx+0B4h], eax
0x14008fbe0  lea     rcx, [rsp+148h+var_100]
0x14008fbe5  call    getnum
0x14008fbea  mov     [rbx+0B8h], eax
0x14008fbf0  xor     eax, eax
0x14008fbf2  mov     rcx, [rsp+148h+var_18]
0x14008fbfa  xor     rcx, rsp; StackCookie
0x14008fbfd  call    __security_check_cookie
0x14008fc02  add     rsp, 140h
0x14008fc09  pop     rbx
0x14008fc0a  retn
```
