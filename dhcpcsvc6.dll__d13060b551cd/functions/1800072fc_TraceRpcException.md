# TraceRpcException

- ea: `0x1800072fc`
- end: `0x18000732f`
- name: `TraceRpcException`
- size: `51`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x1800016f0`
- `0x180004870`
- `0x180004a10`
- `0x180004ad0`
- `0x180004cc0`
- `0x180004e10`
- `0x180005040`
- `0x180005270`
- `0x180005640`
- `0x180005b30`
- `0x180005ec0`
- `0x1800062f0`
- `0x180006820`
- `0x180006cb0`

## callees

- `0x1800072fc`
- `0x180008220`

## pseudocode

```c
__int64 __fastcall TraceRpcException(int a1, __int64 a2)
{
  __int64 result; // rax

  result = a2;
  if ( (xmmword_18000F160 & 2) != 0 )
    return WPP_SF_DS(1025, 13, (unsigned int)WPP_6b7e826f17c73f2d83587599b1f63da9_Traceguids, a1, a2);
  return result;
}

```

## disassembly

```asm
0x1800072fc  sub     rsp, 38h
0x180007300  mov     rax, rdx
0x180007303  mov     r9d, ecx
0x180007306  test    byte ptr cs:xmmword_18000F160, 2
0x18000730d  jz      short loc_18000732A
0x18000730f  mov     edx, 0Dh
0x180007314  mov     [rsp+38h+var_18], rax
0x180007319  mov     ecx, 401h
0x18000731e  lea     r8, WPP_6b7e826f17c73f2d83587599b1f63da9_Traceguids
0x180007325  call    WPP_SF_DS
0x18000732a  add     rsp, 38h
0x18000732e  retn
```
