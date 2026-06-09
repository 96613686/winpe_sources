# TextLogUpdateSectionTag

- ea: `0x180005b18`
- end: `0x180005b82`
- name: `TextLogUpdateSectionTag`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180005a5c`

## callees

- `0x180005b18`

## pseudocode

```c
__int64 __fastcall TextLogUpdateSectionTag(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // r9d
  unsigned __int64 v4; // r10
  unsigned __int64 v5; // rcx

  if ( a3 > 0x2710 )
    return 0;
  v3 = 0;
  v4 = 20LL * (a3 + 1);
  if ( v4 > (unsigned int)(*(_DWORD *)(a1 + 24) - *(_DWORD *)(a1 + 16)) )
    return 0;
  v5 = *(_QWORD *)(a1 + 24) - v4;
  if ( *(_DWORD *)v5 == -522186479 && *(_DWORD *)(v5 + 4) == *(_DWORD *)(a2 + 4) )
  {
    *(_OWORD *)v5 = *(_OWORD *)a2;
    *(_DWORD *)(v5 + 16) = *(_DWORD *)(a2 + 16);
    return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x180005b18  sub     rsp, 18h
0x180005b1c  cmp     r8d, 2710h
0x180005b23  ja      short loc_180005B7B
0x180005b25  xor     r9d, r9d
0x180005b28  mov     [rsp+18h+var_18], r9d
0x180005b2c  lea     eax, [r8+1]
0x180005b30  lea     r10, [rax+rax*4]
0x180005b34  shl     r10, 2
0x180005b38  mov     eax, [rcx+18h]
0x180005b3b  sub     eax, [rcx+10h]
0x180005b3e  cmp     r10, rax
0x180005b41  ja      short loc_180005B7B
0x180005b43  mov     rcx, [rcx+18h]
0x180005b47  sub     rcx, r10
0x180005b4a  cmp     dword ptr [rcx], 0E0E01111h
0x180005b50  jnz     short loc_180005B70
0x180005b52  mov     eax, [rdx+4]
0x180005b55  cmp     [rcx+4], eax
0x180005b58  jnz     short loc_180005B70
0x180005b5a  movups  xmm0, xmmword ptr [rdx]
0x180005b5d  movups  xmmword ptr [rcx], xmm0
0x180005b60  mov     eax, [rdx+10h]
0x180005b63  mov     [rcx+10h], eax
0x180005b66  mov     r9d, 1
0x180005b6c  mov     [rsp+18h+var_18], r9d
0x180005b70  jmp     short loc_180005B76
0x180005b72  mov     r9d, [rsp+18h+var_18]
0x180005b76  mov     eax, r9d
0x180005b79  jmp     short loc_180005B7D
0x180005b7b  xor     eax, eax
0x180005b7d  add     rsp, 18h
0x180005b81  retn
```
