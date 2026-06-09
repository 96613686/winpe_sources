# fIsPortAlreadyPresent

- ea: `0x18000f5ec`
- end: `0x18000f65f`
- name: `fIsPortAlreadyPresent`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000de88`

## callees

- `0x18000f5ec`

## pseudocode

```c
__int64 __fastcall fIsPortAlreadyPresent(int a1, int a2, int a3, int a4, _QWORD *a5)
{
  _QWORD *v5; // r10
  unsigned int v6; // r11d
  __int64 v7; // rax
  bool v8; // zf

  v5 = RasPortsList;
  v6 = 0;
  if ( RasPortsList )
  {
    while ( 1 )
    {
      v7 = v5[27];
      if ( a1 == *(_DWORD *)(v7 + 8) && a4 == *(_DWORD *)(v7 + 60) )
      {
        v8 = *((_DWORD *)v5 + 14) == 6;
        *a5 = v7;
        if ( !v8
          && a3 == *((_DWORD *)v5 + 57)
          && a2 == *((_DWORD *)v5 + 56)
          && *((_DWORD *)v5 + 14) != 7
          && (v5[138] & 1) == 0 )
        {
          break;
        }
      }
      v5 = (_QWORD *)v5[1];
      if ( !v5 )
        return v6;
    }
    return 1;
  }
  return v6;
}

```

## disassembly

```asm
0x18000f5ec  mov     [rsp+arg_0], rbx
0x18000f5f1  mov     r10, cs:RasPortsList
0x18000f5f8  xor     r11d, r11d
0x18000f5fb  test    r10, r10
0x18000f5fe  jz      short loc_18000F656
0x18000f600  mov     rbx, [rsp+arg_20]
0x18000f605  mov     rax, [r10+0D8h]
0x18000f60c  cmp     ecx, [rax+8]
0x18000f60f  jnz     short loc_18000F645
0x18000f611  cmp     r9d, [rax+3Ch]
0x18000f615  jnz     short loc_18000F645
0x18000f617  cmp     dword ptr [r10+38h], 6
0x18000f61c  mov     [rbx], rax
0x18000f61f  jz      short loc_18000F645
0x18000f621  cmp     r8d, [r10+0E4h]
0x18000f628  jnz     short loc_18000F645
0x18000f62a  cmp     edx, [r10+0E0h]
0x18000f631  jnz     short loc_18000F645
0x18000f633  cmp     dword ptr [r10+38h], 7
0x18000f638  jz      short loc_18000F645
0x18000f63a  mov     eax, [r10+450h]
0x18000f641  test    al, 1
0x18000f643  jz      short loc_18000F650
0x18000f645  mov     r10, [r10+8]
0x18000f649  test    r10, r10
0x18000f64c  jnz     short loc_18000F605
0x18000f64e  jmp     short loc_18000F656
0x18000f650  mov     r11d, 1
0x18000f656  mov     rbx, [rsp+arg_0]
0x18000f65b  mov     eax, r11d
0x18000f65e  retn
```
