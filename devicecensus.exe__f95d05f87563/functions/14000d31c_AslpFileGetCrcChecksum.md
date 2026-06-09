# AslpFileGetCrcChecksum

- ea: `0x14000d31c`
- end: `0x14000d418`
- name: `AslpFileGetCrcChecksum`
- size: `252`
- prototype: `__int64 __fastcall(_DWORD *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000cdfc`

## callees

- `0x140007074`
- `0x1400070ac`
- `0x14000d31c`

## string_xrefs

- `0x14000d3bd`: `Overflow/underflow encountered computing position for CRC_CHECKSUM [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetCrcChecksum(_DWORD *a1, __int64 a2)
{
  unsigned __int64 v3; // rbx
  int v4; // ecx
  unsigned int v5; // r8d
  __int64 v6; // rdx
  unsigned int v7; // ebx
  int v8; // eax
  unsigned __int64 v9; // r11
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // r8

  v3 = *(_QWORD *)(a2 + 16);
  v4 = 0;
  if ( v3 >= 0x2000 )
  {
    v8 = AslComputeCrc32(0, *(_QWORD *)(a2 + 24), 0x1000u);
    v10 = v9 + v3;
    v11 = -1;
    if ( v9 + v3 >= v9 )
      v11 = v9 + v3;
    v12 = v11;
    v7 = v9 + v3 < v9 ? 0xC0000095 : 0;
    if ( v10 < v9 || (v11 < 0x1000 ? (v6 = -1) : (v6 = v11 - 4096), v7 = v12 < 0x1000 ? 0xC0000095 : 0, v12 < 0x1000) )
    {
      AslLogCallPrintf(
        1,
        "AslpFileGetCrcChecksum",
        5021,
        "Overflow/underflow encountered computing position for CRC_CHECKSUM [%x]",
        v7);
      return v7;
    }
    v5 = 4096;
    v4 = v8;
  }
  else
  {
    v5 = *(_DWORD *)(a2 + 32);
    v6 = *(_QWORD *)(a2 + 24);
  }
  *a1 = AslComputeCrc32(v4, v6, v5);
  return 0;
}

```

## disassembly

```asm
0x14000d31c  mov     [rsp+arg_0], rbx
0x14000d321  mov     [rsp+arg_8], rsi
0x14000d326  push    rdi
0x14000d327  sub     rsp, 40h
0x14000d32b  mov     rdi, rcx
0x14000d32e  mov     rbx, [rdx+10h]
0x14000d332  xor     ecx, ecx
0x14000d334  cmp     rbx, 2000h
0x14000d33b  jnb     short loc_14000D357
0x14000d33d  mov     r8d, [rdx+20h]
0x14000d341  mov     rdx, [rdx+18h]
0x14000d345  call    AslComputeCrc32
0x14000d34a  mov     [rdi], eax
0x14000d34c  xor     ebx, ebx
0x14000d34e  mov     [rsp+48h+var_18], ebx
0x14000d352  jmp     loc_14000D3DB
0x14000d357  mov     r11, [rdx+18h]
0x14000d35b  mov     esi, 1000h
0x14000d360  mov     r8d, esi
0x14000d363  mov     rdx, r11
0x14000d366  call    AslComputeCrc32
0x14000d36b  lea     rcx, [r11+rbx]
0x14000d36f  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000d373  mov     rdx, r9
0x14000d376  cmp     rcx, r11
0x14000d379  cmovnb  rdx, rcx
0x14000d37d  mov     r8, rdx
0x14000d380  sbb     ebx, ebx
0x14000d382  mov     r10d, 0C0000095h
0x14000d388  and     ebx, r10d
0x14000d38b  mov     [rsp+48h+var_18], ebx
0x14000d38f  cmp     rcx, r11
0x14000d392  jb      short loc_14000D3B9
0x14000d394  cmp     rdx, rsi
0x14000d397  jb      short loc_14000D39E
0x14000d399  sub     rdx, rsi
0x14000d39c  jmp     short loc_14000D3A1
0x14000d39e  mov     rdx, r9
0x14000d3a1  cmp     r8, rsi
0x14000d3a4  sbb     ebx, ebx
0x14000d3a6  and     ebx, r10d
0x14000d3a9  mov     [rsp+48h+var_18], ebx
0x14000d3ad  cmp     r8, rsi
0x14000d3b0  jb      short loc_14000D3B9
0x14000d3b2  mov     r8d, esi
0x14000d3b5  mov     ecx, eax
0x14000d3b7  jmp     short loc_14000D345
0x14000d3b9  mov     [rsp+48h+var_28], ebx
0x14000d3bd  lea     r9, aOverflowUnderf; "Overflow/underflow encountered computin"...
0x14000d3c4  mov     r8d, 139Dh
0x14000d3ca  lea     rdx, aAslpfilegetcrc; "AslpFileGetCrcChecksum"
0x14000d3d1  mov     ecx, 1
0x14000d3d6  call    AslLogCallPrintf
0x14000d3db  jmp     short loc_14000D406
0x14000d3dd  mov     ebx, eax
0x14000d3df  mov     [rsp+48h+var_18], eax
0x14000d3e3  mov     [rsp+48h+var_28], eax
0x14000d3e7  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x14000d3ee  mov     r8d, 13AAh
0x14000d3f4  lea     rdx, aAslpfilegetcrc; "AslpFileGetCrcChecksum"
0x14000d3fb  mov     ecx, 1
0x14000d400  call    AslLogCallPrintf
0x14000d405  nop
0x14000d406  mov     eax, ebx
0x14000d408  mov     rbx, [rsp+48h+arg_0]
0x14000d40d  mov     rsi, [rsp+48h+arg_8]
0x14000d412  add     rsp, 40h
0x14000d416  pop     rdi
0x14000d417  retn
0x140011836  push    rbp
0x140011838  sub     rsp, 30h
0x14001183c  mov     rbp, rdx
0x14001183f  mov     rax, [rcx]
0x140011842  xor     ecx, ecx
0x140011844  cmp     dword ptr [rax], 0C00000FDh
0x14001184a  setnz   cl
0x14001184d  mov     [rbp+34h], ecx
0x140011850  mov     eax, [rbp+34h]
0x140011853  add     rsp, 30h
0x140011857  pop     rbp
0x140011858  retn
```
