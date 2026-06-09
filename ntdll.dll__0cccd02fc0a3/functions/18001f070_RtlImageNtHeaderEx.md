# RtlImageNtHeaderEx

- ea: `0x18001f070`
- end: `0x18001f14b`
- name: `RtlImageNtHeaderEx`
- size: `219`
- prototype: ``
- caller_count: `55`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800034a0`
- `0x18001cd30`
- `0x18001d4b0`
- `0x18001da40`
- `0x18001e820`
- `0x1800267b4`
- `0x180029c3c`
- `0x18002b47c`
- `0x180034d20`
- `0x1800400b0`
- `0x180050260`
- `0x1800558c0`
- `0x1800559c0`
- `0x180056330`
- `0x180056b70`
- `0x1800579d0`
- `0x18005b4b0`
- `0x18006596c`
- `0x180065ab0`
- `0x180065c60`
- `0x180065e70`
- `0x180066020`
- `0x1800661e0`
- `0x1800668e0`
- `0x180066eec`
- `0x180067c40`
- `0x180068f24`
- `0x1800693a8`
- `0x1800a4760`
- `0x1800a5c30`
- `0x1800bbda8`
- `0x1800be058`
- `0x1800c8670`
- `0x1800cd540`
- `0x1800cd5c0`
- `0x1800d094c`
- `0x1800d0a5c`
- `0x1800d2a70`
- `0x1800d2b80`
- `0x1800d6508`
- `0x1800d9620`
- `0x1800ea628`
- `0x1800fa8f8`
- `0x1800fc624`
- `0x1800fe050`
- `0x1801064e0`
- `0x1801097c0`
- `0x18010bf68`
- `0x180111714`
- `0x180112488`

## callees

- `0x18001f070`
- `0x180147454`

## pseudocode

```c
__int64 __fastcall RtlImageNtHeaderEx(int a1, unsigned __int64 a2, unsigned __int64 a3, _QWORD *a4)
{
  __int64 result; // rax
  _DWORD *v7; // rdx
  char v8; // cl
  unsigned __int64 v9; // r8

  result = 0;
  if ( !a4 )
    return 3221225485LL;
  *a4 = 0;
  if ( (a1 & 0xFFFFFFFC) != 0 || a2 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    return 3221225485LL;
  v7 = 0;
  if ( (a1 & 1) != 0 )
  {
    v8 = 0;
  }
  else
  {
    v8 = 1;
    if ( a3 < 0x40 )
      return 3221225595LL;
  }
  if ( *(_WORD *)a2 != 23117
    || (v9 = *(unsigned int *)(a2 + 60), v8) && (v9 >= a3 || (unsigned int)v9 >= 0xFFFFFFE7 || v9 + 24 >= a3)
    || (unsigned int)v9 >= 0x10000000
    || (v7 = (_DWORD *)(v9 + a2), v9 + a2 < a2)
    || *v7 != 17744 )
  {
    result = 3221225595LL;
  }
  if ( (int)result >= 0 )
    *a4 = v7;
  return result;
}

```

## disassembly

```asm
0x18001f070  mov     [rsp+arg_18], r9
0x18001f075  mov     [rsp+arg_0], ecx
0x18001f079  push    rbx
0x18001f07a  sub     rsp, 40h
0x18001f07e  mov     rbx, r8
0x18001f081  mov     r10, rdx
0x18001f084  mov     r11d, ecx
0x18001f087  xor     eax, eax
0x18001f089  test    r9, r9
0x18001f08c  jz      loc_18001F144
0x18001f092  mov     [r9], rax
0x18001f095  test    ecx, 0FFFFFFFCh
0x18001f09b  jnz     loc_18001F144
0x18001f0a1  lea     rcx, [rdx-1]
0x18001f0a5  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001f0a9  ja      loc_18001F144
0x18001f0af  mov     edx, eax
0x18001f0b1  mov     [rsp+48h+var_20], rax
0x18001f0b6  test    r11b, 1
0x18001f0ba  jz      short loc_18001F135
0x18001f0bc  xor     cl, cl
0x18001f0be  mov     r8d, 5A4Dh
0x18001f0c4  cmp     [r10], r8w
0x18001f0c8  jnz     short loc_18001F0F1
0x18001f0ca  mov     r8d, [r10+3Ch]
0x18001f0ce  test    cl, cl
0x18001f0d0  jnz     short loc_18001F0F8
0x18001f0d2  cmp     r8d, 10000000h
0x18001f0d9  jnb     short loc_18001F0F1
0x18001f0db  lea     rdx, [r8+r10]
0x18001f0df  mov     [rsp+48h+var_20], rdx
0x18001f0e4  cmp     rdx, r10
0x18001f0e7  jb      short loc_18001F0F1
0x18001f0e9  cmp     dword ptr [rdx], 4550h
0x18001f0ef  jz      short loc_18001F10E
0x18001f0f1  mov     eax, 0C000007Bh
0x18001f0f6  jmp     short loc_18001F10E
0x18001f0f8  cmp     r8, rbx
0x18001f0fb  jnb     short loc_18001F0F1
0x18001f0fd  cmp     r8d, 0FFFFFFE7h
0x18001f101  jnb     short loc_18001F0F1
0x18001f103  lea     rcx, [r8+18h]
0x18001f107  cmp     rcx, rbx
0x18001f10a  jb      short loc_18001F0D2
0x18001f10c  jmp     short loc_18001F0F1
0x18001f10e  mov     [rsp+48h+var_28], eax
0x18001f112  jmp     short loc_18001F127
0x18001f114  mov     eax, 0C000007Bh
0x18001f119  mov     [rsp+48h+var_28], eax
0x18001f11d  mov     r9, [rsp+48h+arg_18]
0x18001f122  mov     rdx, [rsp+48h+var_20]
0x18001f127  test    eax, eax
0x18001f129  js      short loc_18001F12E
0x18001f12b  mov     [r9], rdx
0x18001f12e  add     rsp, 40h
0x18001f132  pop     rbx
0x18001f133  retn
0x18001f135  mov     cl, 1
0x18001f137  cmp     rbx, 40h ; '@'
0x18001f13b  jnb     short loc_18001F0BE
0x18001f13d  mov     eax, 0C000007Bh
0x18001f142  jmp     short loc_18001F12E
0x18001f144  mov     eax, 0C000000Dh
0x18001f149  jmp     short loc_18001F12E
0x180165610  push    rbp
0x180165612  sub     rsp, 20h
0x180165616  mov     rbp, rdx
0x180165619  mov     ecx, [rbp+50h]
0x18016561c  call    RtlImageNtHeaderEx_ExceptionFilter
0x180165621  nop
0x180165622  add     rsp, 20h
0x180165626  pop     rbp
0x180165627  retn
```
