# SendUIAction

- ea: `0x180004884`
- end: `0x180004919`
- name: `SendUIAction`
- size: `149`
- prototype: `_UNKNOWN **__fastcall(unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003594`

## callees

- `0x180004884`
- `0x180005238`
- `0x180009010`

## pseudocode

```c
_UNKNOWN **__fastcall SendUIAction(unsigned int a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  _UNKNOWN **result; // rax
  int v6; // [rsp+68h] [rbp+10h] BYREF

  if ( InputThreadEnabled && !IsSessionLocked )
  {
    v4 = (unsigned int)SessionId;
    if ( SessionId && WinStaProc )
    {
      v6 = 0;
      WinStaProc(0, (unsigned int)SessionId, 5, (unsigned int)hWndHidServ, 815, (int)a1, 0, &v6);
    }
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      return (_UNKNOWN **)WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, a3, a1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004884  mov     r11, rsp
0x180004887  push    rbx
0x180004888  sub     rsp, 50h
0x18000488c  xor     r10d, r10d
0x18000488f  movsxd  rbx, ecx
0x180004892  cmp     cs:InputThreadEnabled, r10d
0x180004899  jz      short loc_180004913
0x18000489b  cmp     cs:IsSessionLocked, r10d
0x1800048a2  jnz     short loc_180004913
0x1800048a4  mov     edx, cs:SessionId
0x1800048aa  test    edx, edx
0x1800048ac  jz      short loc_1800048E8
0x1800048ae  mov     rax, cs:WinStaProc
0x1800048b5  test    rax, rax
0x1800048b8  jz      short loc_1800048E8
0x1800048ba  mov     r9d, dword ptr cs:hWndHidServ
0x1800048c1  lea     r8, [r11+10h]
0x1800048c5  mov     [r11-20h], r8
0x1800048c9  xor     ecx, ecx
0x1800048cb  mov     [r11-28h], r10
0x1800048cf  lea     r8d, [r10+5]
0x1800048d3  mov     [r11-30h], rbx
0x1800048d7  mov     [rsp+58h+var_38], 32Fh
0x1800048df  mov     [r11+10h], r10d
0x1800048e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048ef  lea     rax, WPP_GLOBAL_Control
0x1800048f6  cmp     rcx, rax
0x1800048f9  jz      short loc_180004913
0x1800048fb  test    byte ptr [rcx+1Ch], 10h
0x1800048ff  jz      short loc_180004913
0x180004901  cmp     byte ptr [rcx+19h], 4
0x180004905  jb      short loc_180004913
0x180004907  mov     rcx, [rcx+10h]
0x18000490b  mov     r9d, ebx
0x18000490e  call    WPP_SF_L
0x180004913  add     rsp, 50h
0x180004917  pop     rbx
0x180004918  retn
```
