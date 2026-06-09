# DavDisplayNetResource

- ea: `0x1800070c0`
- end: `0x1800071b3`
- name: `DavDisplayNetResource`
- size: `243`
- prototype: `__int64 __fastcall(unsigned int *, __int64, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180001600`
- `0x180004340`
- `0x18000f7f0`

## callees

- `0x1800070c0`
- `0x180010a80`
- `0x180010c28`
- `0x180010e68`
- `0x1800112fc`

## pseudocode

```c
__int64 __fastcall DavDisplayNetResource(unsigned int *a1, __int64 a2, __int64 a3)
{
  _QWORD *v4; // rcx
  __int64 result; // rax

  if ( !a2 )
    goto LABEL_10;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    result = WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, a2);
LABEL_10:
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
  {
    result = WPP_SF_q(v4[2], 235, a3, a1);
    v4 = WPP_GLOBAL_Control;
  }
LABEL_7:
  if ( a1 && v4 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v4 + 28) & 2) != 0 )
    {
      result = WPP_SF_DDDD(v4[2], a2, a3, *a1, a1[1], a1[3], a1[2]);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
      return WPP_SF_SSSS(
               v4[2],
               237,
               a3,
               *((_QWORD *)a1 + 2),
               *((_QWORD *)a1 + 3),
               *((_QWORD *)a1 + 4),
               *((_QWORD *)a1 + 5));
  }
  return result;
}

```

## disassembly

```asm
0x1800070c0  mov     [rsp+arg_0], rbx
0x1800070c5  push    rdi
0x1800070c6  sub     rsp, 40h
0x1800070ca  lea     rdi, WPP_GLOBAL_Control
0x1800070d1  mov     r9, rdx
0x1800070d4  mov     rbx, rcx
0x1800070d7  test    rdx, rdx
0x1800070da  jz      short loc_18000710E
0x1800070dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070e3  cmp     rcx, rdi
0x1800070e6  jz      short loc_1800070F9
0x1800070e8  test    byte ptr [rcx+1Ch], 20h
0x1800070ec  jnz     short loc_180007117
0x1800070ee  cmp     rcx, rdi
0x1800070f1  jz      short loc_1800070F9
0x1800070f3  test    byte ptr [rcx+1Ch], 2
0x1800070f7  jnz     short loc_18000712E
0x1800070f9  test    rbx, rbx
0x1800070fc  jz      short loc_180007103
0x1800070fe  cmp     rcx, rdi
0x180007101  jnz     short loc_180007148
0x180007103  mov     rbx, [rsp+48h+arg_0]
0x180007108  add     rsp, 40h
0x18000710c  pop     rdi
0x18000710d  retn
0x18000710e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007115  jmp     short loc_1800070EE
0x180007117  mov     rcx, [rcx+10h]
0x18000711b  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180007122  mov     edx, 0EAh
0x180007127  call    WPP_SF_S
0x18000712c  jmp     short loc_18000710E
0x18000712e  mov     rcx, [rcx+10h]
0x180007132  mov     edx, 0EBh
0x180007137  mov     r9, rbx
0x18000713a  call    WPP_SF_q
0x18000713f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007146  jmp     short loc_1800070F9
0x180007148  test    byte ptr [rcx+1Ch], 2
0x18000714c  jz      short loc_180007176
0x18000714e  mov     eax, [rbx+8]
0x180007151  mov     r9d, [rbx]
0x180007154  mov     rcx, [rcx+10h]
0x180007158  mov     dword ptr [rsp+48h+var_18], eax
0x18000715c  mov     eax, [rbx+0Ch]
0x18000715f  mov     dword ptr [rsp+48h+var_20], eax
0x180007163  mov     eax, [rbx+4]
0x180007166  mov     dword ptr [rsp+48h+var_28], eax
0x18000716a  call    WPP_SF_DDDD
0x18000716f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007176  cmp     rcx, rdi
0x180007179  jz      short loc_180007103
0x18000717b  test    byte ptr [rcx+1Ch], 2
0x18000717f  jz      short loc_180007103
0x180007181  mov     rax, [rbx+28h]
0x180007185  mov     edx, 0EDh
0x18000718a  mov     r9, [rbx+10h]
0x18000718e  mov     rcx, [rcx+10h]
0x180007192  mov     [rsp+48h+var_18], rax
0x180007197  mov     rax, [rbx+20h]
0x18000719b  mov     [rsp+48h+var_20], rax
0x1800071a0  mov     rax, [rbx+18h]
0x1800071a4  mov     [rsp+48h+var_28], rax
0x1800071a9  call    WPP_SF_SSSS
0x1800071ae  jmp     loc_180007103
```
