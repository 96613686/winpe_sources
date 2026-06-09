# FindAndReadIconData

- ea: `0x180007258`
- end: `0x1800072ee`
- name: `FindAndReadIconData`
- size: `150`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800074d4`

## callees

- `0x180006f04`
- `0x180007258`
- `0x1800072f4`

## pseudocode

```c
__int64 __fastcall FindAndReadIconData(__int64 *a1, __int64 a2, __int64 *a3, __int64 a4, __int64 a5)
{
  unsigned int v7; // ebx
  __int64 result; // rax
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF
  __int64 v10; // [rsp+40h] [rbp+18h] BYREF

  v9 = *a3;
  v10 = *a1;
  v7 = a2;
  if ( !(unsigned __int8)FindStringInData(&v10, a2, &v9) || !(unsigned __int8)FindStringInData(&v10, v7, &v9) )
    return 2147500037LL;
  result = DecodeBase64Fragment(&v10, v7, &v9, a5);
  if ( (int)result >= 0 )
  {
    *a3 = v9;
    *a1 = v10;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180007258  mov     r11, rsp
0x18000725b  mov     [r11+10h], rbx
0x18000725f  mov     [r11+20h], rsi
0x180007263  push    rdi
0x180007264  sub     rsp, 20h
0x180007268  mov     rax, [r8]
0x18000726b  mov     rdi, r8
0x18000726e  mov     [r11+8], rax
0x180007272  lea     r8, [r11+8]
0x180007276  mov     rax, [rcx]
0x180007279  mov     rsi, rcx
0x18000727c  lea     rcx, [r11+18h]
0x180007280  mov     [r11+18h], rax
0x180007284  mov     ebx, edx
0x180007286  call    FindStringInData
0x18000728b  test    al, al
0x18000728d  jz      short loc_1800072D9
0x18000728f  lea     r9, asc_18000E628; ">"
0x180007296  mov     edx, ebx
0x180007298  lea     r8, [rsp+28h+arg_0]
0x18000729d  lea     rcx, [rsp+28h+arg_10]
0x1800072a2  call    FindStringInData
0x1800072a7  test    al, al
0x1800072a9  jz      short loc_1800072D9
0x1800072ab  mov     r9, [rsp+28h+arg_20]
0x1800072b0  lea     r8, [rsp+28h+arg_0]
0x1800072b5  mov     edx, ebx
0x1800072b7  lea     rcx, [rsp+28h+arg_10]
0x1800072bc  call    DecodeBase64Fragment
0x1800072c1  test    eax, eax
0x1800072c3  js      short loc_1800072DE
0x1800072c5  mov     rax, [rsp+28h+arg_0]
0x1800072ca  mov     [rdi], rax
0x1800072cd  mov     rax, [rsp+28h+arg_10]
0x1800072d2  mov     [rsi], rax
0x1800072d5  xor     eax, eax
0x1800072d7  jmp     short loc_1800072DE
0x1800072d9  mov     eax, 80004005h
0x1800072de  mov     rbx, [rsp+28h+arg_8]
0x1800072e3  mov     rsi, [rsp+28h+arg_18]
0x1800072e8  add     rsp, 20h
0x1800072ec  pop     rdi
0x1800072ed  retn
```
