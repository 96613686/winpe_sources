# outputBits

- ea: `0x180004be0`
- end: `0x180004c22`
- name: `outputBits`
- size: `66`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004220`
- `0x180004760`
- `0x1800059dc`
- `0x180006038`

## callees

- `0x180004be0`

## pseudocode

```c
__int64 __fastcall outputBits(__int64 a1, int a2, int a3)
{
  __int64 result; // rax
  int v4; // ecx
  int v5; // r8d
  int v6; // ecx
  int v7; // r8d
  int v8; // ecx

  result = a1;
  v4 = *(_DWORD *)(a1 + 68);
  v5 = a3 << v4;
  v6 = a2 + v4;
  *(_DWORD *)(result + 64) |= v5;
  v7 = *(_DWORD *)(result + 64);
  *(_DWORD *)(result + 68) = v6;
  if ( v6 >= 16 )
  {
    *(_BYTE *)(*(_QWORD *)(result + 40))++ = v7;
    *(_BYTE *)(*(_QWORD *)(result + 40))++ = BYTE1(*(_DWORD *)(result + 64));
    v8 = *(unsigned __int16 *)(result + 66);
    *(_DWORD *)(result + 68) -= 16;
    *(_DWORD *)(result + 64) = v8;
  }
  return result;
}

```

## disassembly

```asm
0x180004be0  mov     rax, rcx
0x180004be3  mov     ecx, [rcx+44h]
0x180004be6  shl     r8d, cl
0x180004be9  add     ecx, edx
0x180004beb  or      [rax+40h], r8d
0x180004bef  mov     r8d, [rax+40h]
0x180004bf3  mov     [rax+44h], ecx
0x180004bf6  cmp     ecx, 10h
0x180004bf9  jl      short locret_180004C21
0x180004bfb  mov     rcx, [rax+28h]
0x180004bff  mov     [rcx], r8b
0x180004c02  inc     qword ptr [rax+28h]
0x180004c06  mov     ecx, [rax+40h]
0x180004c09  mov     rdx, [rax+28h]
0x180004c0d  shr     ecx, 8
0x180004c10  mov     [rdx], cl
0x180004c12  inc     qword ptr [rax+28h]
0x180004c16  movzx   ecx, word ptr [rax+42h]
0x180004c1a  add     dword ptr [rax+44h], 0FFFFFFF0h
0x180004c1e  mov     [rax+40h], ecx
0x180004c21  retn
```
