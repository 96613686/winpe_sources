# GenerateStaticEncodingTables

- ea: `0x180003ff0`
- end: `0x1800040bd`
- name: `GenerateStaticEncodingTables`
- size: `205`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003df0`

## callees

- `0x1800040d0`

## pseudocode

```c
__int64 GenerateStaticEncodingTables()
{
  _DWORD v1[8]; // [rsp+20h] [rbp-19h] BYREF
  __int128 v2; // [rsp+40h] [rbp+7h] BYREF
  __int128 v3; // [rsp+50h] [rbp+17h]
  __int128 v4; // [rsp+60h] [rbp+27h]
  __int128 v5; // [rsp+70h] [rbp+37h]
  int v6; // [rsp+80h] [rbp+47h]

  v3 = 0;
  HIDWORD(v3) = 24;
  v4 = 0x7000000098uLL;
  v6 = 0;
  v2 = 0;
  v5 = 0;
  makeCode(288, &v2, (__int64)&g_StaticLiteralTreeLength, (__int64)g_StaticLiteralTreeCode);
  memset(v1, 5, sizeof(v1));
  v3 = 0;
  v6 = 0;
  DWORD1(v3) = 32;
  v2 = 0;
  v4 = 0;
  v5 = 0;
  return makeCode(32, &v2, (__int64)v1, (__int64)g_StaticDistanceTreeCode);
}

```

## disassembly

```asm
0x180003ff0  push    rbp
0x180003ff2  lea     rbp, [rsp-57h]
0x180003ff7  sub     rsp, 90h
0x180003ffe  xorps   xmm0, xmm0
0x180004001  lea     r9, g_StaticLiteralTreeCode
0x180004008  movups  [rbp+57h+var_30], xmm0
0x18000400c  xor     eax, eax
0x18000400e  mov     dword ptr [rbp+57h+var_30+4], 70h ; 'p'
0x180004015  movups  [rbp+57h+var_40], xmm0
0x180004019  lea     r8, g_StaticLiteralTreeLength
0x180004020  mov     dword ptr [rbp+57h+var_40+0Ch], 18h
0x180004027  lea     rdx, [rbp+57h+var_50]
0x18000402b  mov     dword ptr [rbp+57h+var_30], 98h
0x180004032  mov     ecx, 120h
0x180004037  mov     [rbp+57h+var_10], eax
0x18000403a  movups  [rbp+57h+var_50], xmm0
0x18000403e  movups  [rbp+57h+var_20], xmm0
0x180004042  call    makeCode
0x180004047  xor     eax, eax
0x180004049  mov     [rbp+57h+var_70], 5050505h
0x180004050  movups  [rbp+57h+var_40], xmm0
0x180004054  lea     r9, g_StaticDistanceTreeCode
0x18000405b  mov     [rbp+57h+var_10], eax
0x18000405e  lea     r8, [rbp+57h+var_70]
0x180004062  mov     dword ptr [rbp+57h+var_40+4], 20h ; ' '
0x180004069  lea     rdx, [rbp+57h+var_50]
0x18000406d  mov     [rbp+57h+var_6C], 5050505h
0x180004074  mov     ecx, 20h ; ' '
0x180004079  mov     [rbp+57h+var_68], 5050505h
0x180004080  movups  [rbp+57h+var_50], xmm0
0x180004084  mov     [rbp+57h+var_64], 5050505h
0x18000408b  movups  [rbp+57h+var_30], xmm0
0x18000408f  mov     [rbp+57h+var_60], 5050505h
0x180004096  movups  [rbp+57h+var_20], xmm0
0x18000409a  mov     [rbp+57h+var_5C], 5050505h
0x1800040a1  mov     [rbp+57h+var_58], 5050505h
0x1800040a8  mov     [rbp+57h+var_54], 5050505h
0x1800040af  call    makeCode
0x1800040b4  add     rsp, 90h
0x1800040bb  pop     rbp
0x1800040bc  retn
```
