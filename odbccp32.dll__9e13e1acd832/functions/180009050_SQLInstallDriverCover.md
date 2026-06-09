# SQLInstallDriverCover

- ea: `0x180009050`
- end: `0x180009150`
- name: `SQLInstallDriverCover`
- size: `256`
- prototype: `_BOOL8 __fastcall(wchar_t *String1, wchar_t *, wchar_t *, unsigned __int16, __int16 *, __int16, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180009160`
- `0x180009280`

## callees

- `0x180004bac`
- `0x180007628`
- `0x180009050`

## pseudocode

```c
_BOOL8 __fastcall SQLInstallDriverCover(
        wchar_t *String1,
        wchar_t *a2,
        wchar_t *a3,
        unsigned __int16 a4,
        __int16 *a5,
        __int16 a6,
        int *a7)
{
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rax
  int v11; // ecx
  __int16 *v12; // rcx
  __int16 v14; // [rsp+50h] [rbp+8h] BYREF

  v14 = 0;
  if ( !String1 )
    goto LABEL_20;
  if ( !*String1 )
    goto LABEL_20;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( String1[v10] );
  if ( v10 >= 0x104 )
  {
LABEL_20:
    v11 = 7;
    goto LABEL_21;
  }
  v11 = 2;
  if ( a6 == 2 && (!a3 || !a4) )
    goto LABEL_21;
  if ( !String1[v10 + 1] )
  {
    v11 = 8;
LABEL_21:
    PostInstError(v11);
    return 0;
  }
  if ( (unsigned __int16)(a6 - 1) > 1u )
  {
    v11 = 5;
    goto LABEL_21;
  }
  if ( a2 )
  {
    do
      ++v9;
    while ( a2[v9] );
    if ( v9 >= 0x104 )
    {
      v11 = 12;
      goto LABEL_21;
    }
  }
  v12 = &v14;
  if ( a5 )
    v12 = a5;
  return (unsigned int)AddDriverW(String1, a2, a3, a4, v12, a6, a7) != 0;
}

```

## disassembly

```asm
0x180009050  mov     [rsp+arg_8], rbx
0x180009055  push    rdi
0x180009056  sub     rsp, 40h
0x18000905a  xor     edi, edi
0x18000905c  mov     rbx, r8
0x18000905f  mov     [rsp+48h+arg_0], di
0x180009064  mov     r11, rdx
0x180009067  mov     r10, rcx
0x18000906a  test    rcx, rcx
0x18000906d  jz      loc_180009139
0x180009073  cmp     [rcx], di
0x180009076  jz      loc_180009139
0x18000907c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009080  mov     rax, r8
0x180009083  inc     rax
0x180009086  cmp     [rcx+rax*2], di
0x18000908a  jnz     short loc_180009083
0x18000908c  cmp     rax, 104h
0x180009092  jnb     loc_180009139
0x180009098  movzx   edx, [rsp+48h+arg_28]
0x18000909d  mov     ecx, 2
0x1800090a2  cmp     dx, cx
0x1800090a5  jnz     short loc_1800090BA
0x1800090a7  test    rbx, rbx
0x1800090aa  jz      loc_18000913E
0x1800090b0  test    r9w, r9w
0x1800090b4  jz      loc_18000913E
0x1800090ba  cmp     [r10+rax*2+2], di
0x1800090c0  jnz     short loc_1800090C9
0x1800090c2  mov     ecx, 8
0x1800090c7  jmp     short loc_18000913E
0x1800090c9  lea     eax, [rdx-1]
0x1800090cc  cmp     ax, 1
0x1800090d0  ja      short loc_180009132
0x1800090d2  test    r11, r11
0x1800090d5  jz      short loc_1800090F1
0x1800090d7  inc     r8
0x1800090da  cmp     [r11+r8*2], di
0x1800090df  jnz     short loc_1800090D7
0x1800090e1  cmp     r8, 104h
0x1800090e8  jb      short loc_1800090F1
0x1800090ea  mov     ecx, 0Ch
0x1800090ef  jmp     short loc_18000913E
0x1800090f1  mov     rax, [rsp+48h+arg_20]
0x1800090f6  lea     rcx, [rsp+48h+arg_0]
0x1800090fb  test    rax, rax
0x1800090fe  mov     r8, rbx
0x180009101  cmovnz  rcx, rax
0x180009105  mov     rax, [rsp+48h+arg_30]
0x18000910d  mov     [rsp+48h+var_18], rax; __int64
0x180009112  mov     [rsp+48h+var_20], dx; __int16
0x180009117  mov     rdx, r11; wchar_t *
0x18000911a  mov     [rsp+48h+var_28], rcx; __int64
0x18000911f  mov     rcx, r10; String1
0x180009122  call    AddDriverW
0x180009127  test    eax, eax
0x180009129  mov     ecx, edi
0x18000912b  setnz   cl
0x18000912e  mov     eax, ecx
0x180009130  jmp     short loc_180009145
0x180009132  mov     ecx, 5
0x180009137  jmp     short loc_18000913E
0x180009139  mov     ecx, 7
0x18000913e  call    PostInstError
0x180009143  xor     eax, eax
0x180009145  mov     rbx, [rsp+48h+arg_8]
0x18000914a  add     rsp, 40h
0x18000914e  pop     rdi
0x18000914f  retn
```
