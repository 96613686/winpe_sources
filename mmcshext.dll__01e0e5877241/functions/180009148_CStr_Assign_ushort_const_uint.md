# CStr::Assign(ushort const *,uint)

- ea: `0x180009148`
- end: `0x180009212`
- name: `?Assign@CStr@@QEAAJPEBGI@Z`
- size: `202`
- prototype: `__int64 __fastcall(CStr *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180009218`
- `0x180009294`

## callees

- `0x180002c40`
- `0x180007dec`
- `0x180008cf8`
- `0x180009148`
- `0x18000931c`

## pseudocode

```c
__int64 __fastcall CStr::Assign(CStr *this, const unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int16 near **v3; // r9
  int v7; // ebx

  v3 = (unsigned __int16 near **)*((_QWORD *)this + 1);
  if ( v3 == &CStr::s_rgwchEmptyStringBuffer
    || a2 < (const unsigned __int16 *)v3
    || a2 > (const unsigned __int16 *)v3 + *((unsigned int *)this + 5) )
  {
    CStr::Empty(this);
    v7 = CStr::Append(this, a2, a3);
    if ( v7 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x13u, (__int64)WPP_46616a5bce583dfc538f214383f522c0_Traceguids, v7);
  }
  else
  {
    v7 = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x12u, (__int64)WPP_46616a5bce583dfc538f214383f522c0_Traceguids);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009148  mov     [rsp+arg_0], rbx
0x18000914d  mov     [rsp+arg_8], rsi
0x180009152  push    rdi
0x180009153  sub     rsp, 20h
0x180009157  mov     r9, [rcx+8]
0x18000915b  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x180009162  mov     esi, r8d
0x180009165  mov     rbx, rdx
0x180009168  mov     rdi, rcx
0x18000916b  cmp     r9, rax
0x18000916e  jz      short loc_1800091B6
0x180009170  cmp     rdx, r9
0x180009173  jb      short loc_1800091B6
0x180009175  mov     eax, [rcx+14h]
0x180009178  lea     r9, [r9+rax*2]
0x18000917c  cmp     rdx, r9
0x18000917f  ja      short loc_1800091B6
0x180009181  mov     ebx, 80070057h
0x180009186  mov     rcx, cs:WPP_GLOBAL_Control
0x18000918d  lea     rax, WPP_GLOBAL_Control
0x180009194  cmp     rcx, rax
0x180009197  jz      short loc_180009200
0x180009199  cmp     byte ptr [rcx+19h], 2
0x18000919d  jb      short loc_180009200
0x18000919f  mov     rcx, [rcx+10h]
0x1800091a3  lea     r8, WPP_46616a5bce583dfc538f214383f522c0_Traceguids
0x1800091aa  mov     edx, 12h
0x1800091af  call    WPP_SF_
0x1800091b4  jmp     short loc_180009200
0x1800091b6  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x1800091bb  mov     r8d, esi; unsigned int
0x1800091be  mov     rdx, rbx; unsigned __int16 *
0x1800091c1  mov     rcx, rdi; this
0x1800091c4  call    ?Append@CStr@@QEAAJPEBGI@Z; CStr::Append(ushort const *,uint)
0x1800091c9  mov     ebx, eax
0x1800091cb  test    eax, eax
0x1800091cd  jns     short loc_180009200
0x1800091cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091d6  lea     rax, WPP_GLOBAL_Control
0x1800091dd  cmp     rcx, rax
0x1800091e0  jz      short loc_180009200
0x1800091e2  cmp     byte ptr [rcx+19h], 2
0x1800091e6  jb      short loc_180009200
0x1800091e8  mov     rcx, [rcx+10h]
0x1800091ec  lea     r8, WPP_46616a5bce583dfc538f214383f522c0_Traceguids
0x1800091f3  mov     edx, 13h
0x1800091f8  mov     r9d, ebx
0x1800091fb  call    WPP_SF_d
0x180009200  mov     rsi, [rsp+28h+arg_8]
0x180009205  mov     eax, ebx
0x180009207  mov     rbx, [rsp+28h+arg_0]
0x18000920c  add     rsp, 20h
0x180009210  pop     rdi
0x180009211  retn
```
