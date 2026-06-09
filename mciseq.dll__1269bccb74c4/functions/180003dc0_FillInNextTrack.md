# FillInNextTrack

- ea: `0x180003dc0`
- end: `0x180003e92`
- name: `FillInNextTrack`
- size: `210`
- prototype: `char __fastcall(__int64)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1800048fc`
- `0x180005990`
- `0x180005a1c`
- `0x180005cd0`
- `0x180005d4c`

## callees

- `0x180003dc0`
- `0x180003f18`
- `0x180003f68`
- `0x180004430`
- `0x1800058bc`

## pseudocode

```c
char __fastcall FillInNextTrack(__int64 a1)
{
  int v2; // esi
  int VarLen; // eax
  bool v4; // zf
  char Status; // al
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rax
  char v10; // r8
  int v11; // edi

  v2 = *(_DWORD *)(a1 + 4);
  *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 24);
  VarLen = GetVarLen(a1);
  v4 = *(_DWORD *)a1 == 0;
  *(_DWORD *)(a1 + 4) = v2 + VarLen;
  if ( !v4 )
    goto LABEL_17;
  Status = GetStatus(a1);
  LOBYTE(v8) = Status;
  if ( *(_DWORD *)a1 )
    goto LABEL_17;
  LOBYTE(v7) = Status;
  LODWORD(v9) = MIDILength(v7, v6, v8);
  v11 = v9;
  if ( (int)v9 > 3 )
  {
    if ( v10 == -16 || v10 == -9 )
    {
      *(_BYTE *)(a1 + 16) = v10;
      LODWORD(v9) = GetVarLen(a1);
      *(_DWORD *)(a1 + 20) = v9;
    }
    else if ( v10 == -1 )
    {
      *(_BYTE *)(a1 + 16) = -1;
    }
  }
  else
  {
    *(_BYTE *)(a1 + 16) = v10;
    if ( (int)v9 >= 2 )
    {
      LOBYTE(v9) = LookByte(a1);
      if ( !*(_DWORD *)a1 )
        ++*(_QWORD *)(a1 + 24);
      *(_BYTE *)(a1 + 17) = v9;
      if ( v11 == 3 )
      {
        LOBYTE(v9) = LookByte(a1);
        if ( !*(_DWORD *)a1 )
          ++*(_QWORD *)(a1 + 24);
        *(_BYTE *)(a1 + 18) = v9;
      }
    }
  }
  if ( *(_DWORD *)a1 )
  {
LABEL_17:
    v9 = *(_QWORD *)(a1 + 40);
    if ( v9 )
      *(_QWORD *)(a1 + 24) = v9;
    *(_DWORD *)(a1 + 4) = v2;
  }
  return v9;
}

```

## disassembly

```asm
0x180003dc0  mov     [rsp+arg_0], rbx
0x180003dc5  mov     [rsp+arg_8], rsi
0x180003dca  push    rdi
0x180003dcb  sub     rsp, 20h
0x180003dcf  mov     rax, [rcx+18h]
0x180003dd3  mov     rbx, rcx
0x180003dd6  mov     esi, [rcx+4]
0x180003dd9  mov     [rcx+28h], rax
0x180003ddd  call    GetVarLen
0x180003de2  add     eax, esi
0x180003de4  cmp     dword ptr [rbx], 0
0x180003de7  mov     [rbx+4], eax
0x180003dea  jnz     loc_180003E72
0x180003df0  mov     rcx, rbx
0x180003df3  call    GetStatus
0x180003df8  cmp     dword ptr [rbx], 0
0x180003dfb  mov     r8b, al
0x180003dfe  jnz     short loc_180003E72
0x180003e00  mov     cl, al
0x180003e02  call    MIDILength
0x180003e07  mov     edi, eax
0x180003e09  cmp     eax, 3
0x180003e0c  jg      short loc_180003E46
0x180003e0e  mov     [rbx+10h], r8b
0x180003e12  cmp     eax, 2
0x180003e15  jl      short loc_180003E6D
0x180003e17  mov     rcx, rbx
0x180003e1a  call    LookByte
0x180003e1f  cmp     dword ptr [rbx], 0
0x180003e22  jnz     short loc_180003E28
0x180003e24  inc     qword ptr [rbx+18h]
0x180003e28  mov     [rbx+11h], al
0x180003e2b  cmp     edi, 3
0x180003e2e  jnz     short loc_180003E6D
0x180003e30  mov     rcx, rbx
0x180003e33  call    LookByte
0x180003e38  cmp     dword ptr [rbx], 0
0x180003e3b  jnz     short loc_180003E41
0x180003e3d  inc     qword ptr [rbx+18h]
0x180003e41  mov     [rbx+12h], al
0x180003e44  jmp     short loc_180003E6D
0x180003e46  cmp     r8b, 0F0h
0x180003e4a  jz      short loc_180003E5E
0x180003e4c  cmp     r8b, 0F7h
0x180003e50  jz      short loc_180003E5E
0x180003e52  cmp     r8b, 0FFh
0x180003e56  jnz     short loc_180003E6D
0x180003e58  mov     [rbx+10h], r8b
0x180003e5c  jmp     short loc_180003E6D
0x180003e5e  mov     rcx, rbx
0x180003e61  mov     [rbx+10h], r8b
0x180003e65  call    GetVarLen
0x180003e6a  mov     [rbx+14h], eax
0x180003e6d  cmp     dword ptr [rbx], 0
0x180003e70  jz      short loc_180003E82
0x180003e72  mov     rax, [rbx+28h]
0x180003e76  test    rax, rax
0x180003e79  jz      short loc_180003E7F
0x180003e7b  mov     [rbx+18h], rax
0x180003e7f  mov     [rbx+4], esi
0x180003e82  mov     rbx, [rsp+28h+arg_0]
0x180003e87  mov     rsi, [rsp+28h+arg_8]
0x180003e8c  add     rsp, 20h
0x180003e90  pop     rdi
0x180003e91  retn
```
