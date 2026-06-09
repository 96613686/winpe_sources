# CMyUpdateList::SetDataBurnAddProgress(ulong)

- ea: `0x180010a40`
- end: `0x180010aa5`
- name: `?SetDataBurnAddProgress@CMyUpdateList@@QEAAEK@Z`
- size: `101`
- prototype: `unsigned __int8 __fastcall(CMyUpdateList *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000cc10`
- `0x180014d60`

## callees

- `0x180007c14`
- `0x180010a40`

## pseudocode

```c
unsigned __int8 __fastcall CMyUpdateList::SetDataBurnAddProgress(CMyUpdateList *this, int a2)
{
  unsigned int v3; // r8d
  __int64 v4; // r9

  if ( !*((_DWORD *)this + 3) )
    return 0;
  *((_DWORD *)this + 23) += a2;
  v3 = *((_DWORD *)this + 23);
  v4 = *((unsigned int *)this + 22);
  *((_DWORD *)this + 25) |= 0x200u;
  *((_DWORD *)this + 27) = v4;
  *((_DWORD *)this + 26) = v3;
  if ( (unsigned int)v4 < v3
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_51141d96add4351c86cdeea4487a7041_Traceguids, v4, v3);
  }
  return 1;
}

```

## disassembly

```asm
0x180010a40  sub     rsp, 38h
0x180010a44  cmp     dword ptr [rcx+0Ch], 0
0x180010a48  jnz     short loc_180010A4E
0x180010a4a  xor     al, al
0x180010a4c  jmp     short loc_180010AA0
0x180010a4e  add     [rcx+5Ch], edx
0x180010a51  mov     r8d, [rcx+5Ch]
0x180010a55  mov     r9d, [rcx+58h]
0x180010a59  bts     dword ptr [rcx+64h], 9
0x180010a5e  mov     [rcx+6Ch], r9d
0x180010a62  mov     [rcx+68h], r8d
0x180010a66  cmp     r9d, r8d
0x180010a69  jnb     short loc_180010A9E
0x180010a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a72  lea     rax, WPP_GLOBAL_Control
0x180010a79  cmp     rcx, rax
0x180010a7c  jz      short loc_180010A9E
0x180010a7e  test    byte ptr [rcx+44h], 1
0x180010a82  jz      short loc_180010A9E
0x180010a84  mov     rcx, [rcx+38h]
0x180010a88  mov     edx, 0Ch
0x180010a8d  mov     [rsp+38h+var_18], r8d
0x180010a92  lea     r8, WPP_51141d96add4351c86cdeea4487a7041_Traceguids
0x180010a99  call    WPP_SF_DD
0x180010a9e  mov     al, 1
0x180010aa0  add     rsp, 38h
0x180010aa4  retn
```
