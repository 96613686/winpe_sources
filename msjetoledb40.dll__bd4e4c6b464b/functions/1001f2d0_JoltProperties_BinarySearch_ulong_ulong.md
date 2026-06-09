# JoltProperties::BinarySearch(ulong,ulong &)

- ea: `0x1001f2d0`
- end: `0x1001f320`
- name: `?BinarySearch@JoltProperties@@IBEJKAAK@Z`
- size: `80`
- prototype: `int __thiscall(JoltProperties *__hidden this, unsigned int, unsigned int *)`
- caller_count: `54`
- callee_count: `1`
- tags: ``

## callers

- `0x1000fcf0`
- `0x10010b50`
- `0x10014d90`
- `0x10016690`
- `0x100188a0`
- `0x10018f30`
- `0x10019070`
- `0x100196e0`
- `0x100198d0`
- `0x10019cd0`
- `0x1001a140`
- `0x1001a2a0`
- `0x1001a970`
- `0x1001fae0`
- `0x1001fb20`
- `0x1001fb90`
- `0x1001fbe0`
- `0x1001fc50`
- `0x1001fcb0`
- `0x1001fd10`
- `0x1001fd70`
- `0x100201c0`
- `0x10020200`
- `0x10020250`
- `0x100202a0`
- `0x10020e30`
- `0x10021070`
- `0x10021630`
- `0x10021cf0`
- `0x10022540`
- `0x10022740`
- `0x10022990`
- `0x10022a90`
- `0x10022c40`
- `0x100235b0`
- `0x10023ab0`
- `0x10023d10`
- `0x10028340`
- `0x1002d600`
- `0x1002da40`
- `0x1002e3e0`
- `0x10031240`
- `0x10032ba0`
- `0x10032e50`
- `0x1003eb30`
- `0x100434f0`
- `0x10045d20`
- `0x10046bb0`
- `0x10047070`
- `0x10049160`

## callees

- `0x1001f2d0`

## pseudocode

```c
int __thiscall JoltProperties::BinarySearch(JoltProperties *this, unsigned int a2, unsigned int *a3)
{
  int v3; // ebx
  unsigned int v4; // esi
  unsigned int v5; // edx
  unsigned int v6; // eax

  v3 = *((_DWORD *)this + 4);
  v4 = 0;
  v5 = *((_DWORD *)this + 2) - 1;
  while ( 1 )
  {
    v6 = (v5 + v4) >> 1;
    if ( a2 == *(_DWORD *)(v3 + 48 * v6 + 8) )
      break;
    if ( a2 <= *(_DWORD *)(v3 + 48 * v6 + 8) )
    {
      if ( !v6 )
        return -2147467259;
      v5 = v6 - 1;
    }
    else
    {
      v4 = v6 + 1;
    }
    if ( v4 > v5 )
      return -2147467259;
  }
  *a3 = v6;
  return 0;
}

```

## disassembly

```asm
0x1001f2d0  mov     edi, edi
0x1001f2d2  push    ebp
0x1001f2d3  mov     ebp, esp
0x1001f2d5  mov     edx, [ecx+8]
0x1001f2d8  push    ebx
0x1001f2d9  mov     ebx, [ecx+10h]
0x1001f2dc  push    esi
0x1001f2dd  push    edi
0x1001f2de  mov     edi, [ebp+arg_0]
0x1001f2e1  xor     esi, esi
0x1001f2e3  dec     edx
0x1001f2e4  lea     eax, [edx+esi]
0x1001f2e7  shr     eax, 1
0x1001f2e9  lea     ecx, [eax+eax*2]
0x1001f2ec  add     ecx, ecx
0x1001f2ee  cmp     edi, [ebx+ecx*8+8]
0x1001f2f2  jz      short loc_1001F312
0x1001f2f4  jbe     short loc_1001F2FB
0x1001f2f6  lea     esi, [eax+1]
0x1001f2f9  jmp     short loc_1001F302
0x1001f2fb  test    eax, eax
0x1001f2fd  jz      short loc_1001F306
0x1001f2ff  lea     edx, [eax-1]
0x1001f302  cmp     esi, edx
0x1001f304  jbe     short loc_1001F2E4
0x1001f306  pop     edi
0x1001f307  pop     esi
0x1001f308  mov     eax, 80004005h
0x1001f30d  pop     ebx
0x1001f30e  pop     ebp
0x1001f30f  retn    8
0x1001f312  mov     ecx, [ebp+arg_4]
0x1001f315  mov     [ecx], eax
0x1001f317  xor     eax, eax
0x1001f319  pop     edi
0x1001f31a  pop     esi
0x1001f31b  pop     ebx
0x1001f31c  pop     ebp
0x1001f31d  retn    8
```
