# MibLeafFunction

- ea: `0x180001c00`
- end: `0x180001cbc`
- name: `MibLeafFunction`
- size: `188`
- prototype: `__int64 __usercall@<rax>(AsnObjectIdentifier *pOidDst@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001cd0`

## callees

- `0x180001b5c`
- `0x180001c00`

## pseudocode

```c
__int64 __fastcall MibLeafFunction(AsnObjectIdentifier *pOidDst, int a2, unsigned __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v5; // r10d
  int v6; // edx
  int v7; // edx
  unsigned __int64 v8; // rdx

  v5 = 2;
  v6 = a2 - 160;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( !v7 )
    {
      v8 = *(_QWORD *)(a4 + 16);
      if ( a3 >= v8 && a3 < v8 + 40LL * *(int *)(a4 + 8) )
        return (unsigned int)MibGetNextVar(pOidDst, a3, a4, a5);
      return v5;
    }
    if ( v7 != 63 )
      return 5;
  }
  if ( (*(_DWORD *)(a3 + 16) & 0xFFFFFFFD) == 0 )
  {
    v5 = 0;
    LOBYTE(pOidDst[1].idLength) = *(_BYTE *)(a3 + 32);
    if ( *(_BYTE *)(a3 + 32) == 2
      || *(_BYTE *)(a3 + 32) != 4 && *(_BYTE *)(a3 + 32) != 64 && (unsigned int)*(unsigned __int8 *)(a3 + 32) - 65 < 2 )
    {
      LODWORD(pOidDst[1].ids) = *(_DWORD *)(*(int *)(a3 + 12) + a5);
      return v5;
    }
    return 5;
  }
  return v5;
}

```

## disassembly

```asm
0x180001c00  mov     [rsp+arg_0], rbx
0x180001c05  push    rdi
0x180001c06  sub     rsp, 20h
0x180001c0a  mov     r11, r8
0x180001c0d  mov     r8d, 2
0x180001c13  mov     r10d, r8d
0x180001c16  mov     rdi, r9
0x180001c19  mov     rbx, rcx
0x180001c1c  sub     edx, 0A0h
0x180001c22  jz      short loc_180001C33
0x180001c24  sub     edx, 1
0x180001c27  jz      short loc_180001C79
0x180001c29  sub     edx, r8d
0x180001c2c  jz      short loc_180001C71
0x180001c2e  cmp     edx, 3Dh ; '='
0x180001c31  jnz     short loc_180001C71
0x180001c33  test    dword ptr [r11+10h], 0FFFFFFFDh
0x180001c3b  jnz     short loc_180001CAE
0x180001c3d  mov     al, [r11+20h]
0x180001c41  xor     r10d, r10d
0x180001c44  mov     [rcx+0Ch], al
0x180001c47  movsxd  rcx, dword ptr [r11+0Ch]
0x180001c4b  mov     rax, [rsp+28h+arg_20]
0x180001c50  mov     edx, [rcx+rax]
0x180001c53  movzx   ecx, byte ptr [r11+20h]
0x180001c58  sub     ecx, r8d
0x180001c5b  jz      short loc_180001CAB
0x180001c5d  sub     ecx, r8d
0x180001c60  jz      short loc_180001C71
0x180001c62  sub     ecx, 3Ch ; '<'
0x180001c65  jz      short loc_180001C71
0x180001c67  sub     ecx, 1
0x180001c6a  jz      short loc_180001CAB
0x180001c6c  cmp     ecx, 1
0x180001c6f  jz      short loc_180001CAB
0x180001c71  mov     r10d, 5
0x180001c77  jmp     short loc_180001CAE
0x180001c79  mov     rdx, [r9+10h]
0x180001c7d  cmp     r11, rdx
0x180001c80  jb      short loc_180001CAE
0x180001c82  movsxd  rax, dword ptr [r9+8]
0x180001c86  lea     rcx, [rax+rax*4]
0x180001c8a  lea     rax, [rdx+rcx*8]
0x180001c8e  cmp     r11, rax
0x180001c91  jnb     short loc_180001CAE
0x180001c93  mov     r9, [rsp+28h+arg_20]
0x180001c98  mov     r8, rdi
0x180001c9b  mov     rdx, r11
0x180001c9e  mov     rcx, rbx; pOidDst
0x180001ca1  call    MibGetNextVar
0x180001ca6  mov     r10d, eax
0x180001ca9  jmp     short loc_180001CAE
0x180001cab  mov     [rbx+10h], edx
0x180001cae  mov     rbx, [rsp+28h+arg_0]
0x180001cb3  mov     eax, r10d
0x180001cb6  add     rsp, 20h
0x180001cba  pop     rdi
0x180001cbb  retn
```
