# LuafvSetFileCreateEvent

- ea: `0x140024058`
- end: `0x140024096`
- name: `LuafvSetFileCreateEvent`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400161c0`
- `0x140016238`

## callees

- `0x140024058`

## pseudocode

```c
__int64 __fastcall LuafvSetFileCreateEvent(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rcx
  __int64 v4; // rdx
  __int64 result; // rax

  if ( a2 )
  {
    v3 = a2 + 40;
    v4 = a2 + 44;
  }
  else
  {
    result = *(_QWORD *)(a1 + 16);
    v3 = result + 32;
    v4 = *(_QWORD *)(result + 24) + 16LL;
  }
  a3[14] = v3;
  a3[15] = 4;
  a3[16] = v4;
  a3[17] = 4;
  return result;
}

```

## disassembly

```asm
0x140024058  test    rdx, rdx
0x14002405b  jz      short loc_140024067
0x14002405d  lea     rcx, [rdx+28h]
0x140024061  add     rdx, 2Ch ; ','
0x140024065  jmp     short loc_140024077
0x140024067  mov     rax, [rcx+10h]
0x14002406b  mov     rdx, [rax+18h]
0x14002406f  lea     rcx, [rax+20h]
0x140024073  add     rdx, 10h
0x140024077  mov     [r8+70h], rcx
0x14002407b  mov     qword ptr [r8+78h], 4
0x140024083  mov     [r8+80h], rdx
0x14002408a  mov     qword ptr [r8+88h], 4
0x140024095  retn
```
