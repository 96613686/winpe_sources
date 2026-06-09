# TextLogEnumerateOpenSections

- ea: `0x180004e0c`
- end: `0x180004e6e`
- name: `TextLogEnumerateOpenSections`
- size: `98`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800045ec`
- `0x180004e74`
- `0x1800052c4`
- `0x1800054d4`
- `0x1800057a8`
- `0x180005a5c`

## callees

- `0x180004e0c`

## pseudocode

```c
__int64 __fastcall TextLogEnumerateOpenSections(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v3; // r9d
  unsigned __int64 v4; // r10
  unsigned __int64 v5; // rax

  if ( a2 > 0x2710 )
    return 0;
  v3 = 0;
  v4 = 20LL * (a2 + 1);
  if ( v4 > (unsigned int)(*(_DWORD *)(a1 + 24) - *(_DWORD *)(a1 + 16)) )
    return 0;
  v5 = *(_QWORD *)(a1 + 24) - v4;
  if ( *(_DWORD *)v5 == -522186479 )
  {
    *(_OWORD *)a3 = *(_OWORD *)v5;
    *(_DWORD *)(a3 + 16) = *(_DWORD *)(v5 + 16);
    return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x180004e0c  sub     rsp, 18h
0x180004e10  cmp     edx, 2710h
0x180004e16  ja      short loc_180004E67
0x180004e18  xor     r9d, r9d
0x180004e1b  mov     [rsp+18h+var_18], r9d
0x180004e1f  lea     eax, [rdx+1]
0x180004e22  lea     r10, [rax+rax*4]
0x180004e26  shl     r10, 2
0x180004e2a  mov     eax, [rcx+18h]
0x180004e2d  sub     eax, [rcx+10h]
0x180004e30  cmp     r10, rax
0x180004e33  ja      short loc_180004E67
0x180004e35  mov     rax, [rcx+18h]
0x180004e39  sub     rax, r10
0x180004e3c  cmp     dword ptr [rax], 0E0E01111h
0x180004e42  jnz     short loc_180004E5C
0x180004e44  movups  xmm0, xmmword ptr [rax]
0x180004e47  movups  xmmword ptr [r8], xmm0
0x180004e4b  mov     eax, [rax+10h]
0x180004e4e  mov     [r8+10h], eax
0x180004e52  mov     r9d, 1
0x180004e58  mov     [rsp+18h+var_18], r9d
0x180004e5c  jmp     short loc_180004E62
0x180004e5e  mov     r9d, [rsp+18h+var_18]
0x180004e62  mov     eax, r9d
0x180004e65  jmp     short loc_180004E69
0x180004e67  xor     eax, eax
0x180004e69  add     rsp, 18h
0x180004e6d  retn
```
