# DBOpenDimensions

- ea: `0x1001a860`
- end: `0x1001a8bd`
- name: `DBOpenDimensions`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1001a860`

## pseudocode

```c
int __stdcall DBOpenDimensions(int a1, int a2, __int16 a3, __int16 a4)
{
  int v4; // edx
  int v5; // ecx
  int result; // eax

  if ( a1 == a2 )
  {
    dword_1003A9C8 = 0;
    dword_1003A9CC = 0;
  }
  else
  {
    LOWORD(dword_1003A9C8) = a1;
    HIWORD(dword_1003A9C8) = a3;
    LOWORD(dword_1003A9CC) = a2 - 1;
    HIWORD(dword_1003A9CC) = a4 - 1;
  }
  v4 = dword_1003A9BC;
  v5 = dword_1003A9CC;
  *(_DWORD *)(dword_1003A9BC + 52) = dword_1003A9C8;
  result = 0;
  *(_DWORD *)(v4 + 56) = v5;
  return result;
}

```

## disassembly

```asm
0x1001a860  mov     edi, edi
0x1001a862  push    ebp
0x1001a863  mov     ebp, esp
0x1001a865  mov     eax, [ebp+arg_0]
0x1001a868  mov     ecx, [ebp+arg_4]
0x1001a86b  cmp     eax, ecx
0x1001a86d  jnz     short loc_1001A87D
0x1001a86f  xor     eax, eax
0x1001a871  mov     dword_1003A9C8, eax
0x1001a876  mov     dword_1003A9CC, eax
0x1001a87b  jmp     short loc_1001A8A0
0x1001a87d  mov     word ptr dword_1003A9C8, ax
0x1001a883  mov     ax, [ebp+arg_8]
0x1001a887  mov     word ptr dword_1003A9C8+2, ax
0x1001a88d  lea     eax, [ecx-1]
0x1001a890  mov     word ptr dword_1003A9CC, ax
0x1001a896  mov     eax, [ebp+arg_C]
0x1001a899  dec     eax
0x1001a89a  mov     word ptr dword_1003A9CC+2, ax
0x1001a8a0  mov     edx, dword_1003A9BC
0x1001a8a6  mov     eax, dword_1003A9C8
0x1001a8ab  mov     ecx, dword_1003A9CC
0x1001a8b1  mov     [edx+34h], eax
0x1001a8b4  xor     eax, eax
0x1001a8b6  mov     [edx+38h], ecx
0x1001a8b9  pop     ebp
0x1001a8ba  retn    10h
```
