# CStr::Assign(CStr const &)

- ea: `0x180008f5c`
- end: `0x18000904c`
- name: `?Assign@CStr@@QEAAJAEBV1@@Z`
- size: `240`
- prototype: `__int64 __fastcall(CStr *__hidden this, const struct CStr *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180004240`
- `0x180005dbc`

## callees

- `0x180002c40`
- `0x180007dec`
- `0x180008bb0`
- `0x180008f5c`
- `0x18000931c`

## pseudocode

```c
__int64 __fastcall CStr::Assign(CStr *this, const struct CStr *a2)
{
  int v4; // ebx
  _QWORD *v5; // rcx
  unsigned __int16 v6; // dx
  unsigned __int16 near **v7; // rcx

  if ( *((_DWORD *)a2 + 6) )
  {
    v4 = -2147024809;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 12;
LABEL_5:
      WPP_SF_(v5[2], v6, (__int64)WPP_46616a5bce583dfc538f214383f522c0_Traceguids);
    }
  }
  else
  {
    v7 = (unsigned __int16 near **)*((_QWORD *)this + 1);
    if ( v7 == &CStr::s_rgwchEmptyStringBuffer
      || *((_QWORD *)a2 + 1) < (unsigned __int64)v7
      || *((_QWORD *)a2 + 1) > (unsigned __int64)v7 + 2 * *((unsigned int *)this + 5) )
    {
      CStr::Empty(this);
      v4 = CStr::Append(this, a2);
      if ( v4 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0xEu,
          (__int64)WPP_46616a5bce583dfc538f214383f522c0_Traceguids,
          v4);
    }
    else
    {
      v4 = 0;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v6 = 13;
        goto LABEL_5;
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180008f5c  mov     [rsp+arg_0], rbx
0x180008f61  push    rdi
0x180008f62  sub     rsp, 20h
0x180008f66  cmp     dword ptr [rdx+18h], 0
0x180008f6a  mov     rdi, rdx
0x180008f6d  mov     rbx, rcx
0x180008f70  jz      short loc_180008FB2
0x180008f72  mov     ebx, 80070057h
0x180008f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f7e  lea     rax, WPP_GLOBAL_Control
0x180008f85  cmp     rcx, rax
0x180008f88  jz      loc_18000903F
0x180008f8e  cmp     byte ptr [rcx+19h], 2
0x180008f92  jb      loc_18000903F
0x180008f98  mov     edx, 0Ch
0x180008f9d  mov     rcx, [rcx+10h]
0x180008fa1  lea     r8, WPP_46616a5bce583dfc538f214383f522c0_Traceguids
0x180008fa8  call    WPP_SF_
0x180008fad  jmp     loc_18000903F
0x180008fb2  mov     rcx, [rcx+8]
0x180008fb6  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x180008fbd  cmp     rcx, rax
0x180008fc0  jz      short loc_180008FF5
0x180008fc2  cmp     [rdx+8], rcx
0x180008fc6  jb      short loc_180008FF5
0x180008fc8  mov     eax, [rbx+14h]
0x180008fcb  lea     rcx, [rcx+rax*2]
0x180008fcf  cmp     [rdx+8], rcx
0x180008fd3  ja      short loc_180008FF5
0x180008fd5  xor     ebx, ebx
0x180008fd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fde  lea     rax, WPP_GLOBAL_Control
0x180008fe5  cmp     rcx, rax
0x180008fe8  jz      short loc_18000903F
0x180008fea  cmp     byte ptr [rcx+19h], 4
0x180008fee  jb      short loc_18000903F
0x180008ff0  lea     edx, [rbx+0Dh]
0x180008ff3  jmp     short loc_180008F9D
0x180008ff5  mov     rcx, rbx; this
0x180008ff8  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180008ffd  mov     rdx, rdi; struct CStr *
0x180009000  mov     rcx, rbx; this
0x180009003  call    ?Append@CStr@@QEAAJAEBV1@@Z; CStr::Append(CStr const &)
0x180009008  mov     ebx, eax
0x18000900a  test    eax, eax
0x18000900c  jns     short loc_18000903F
0x18000900e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009015  lea     rax, WPP_GLOBAL_Control
0x18000901c  cmp     rcx, rax
0x18000901f  jz      short loc_18000903F
0x180009021  cmp     byte ptr [rcx+19h], 2
0x180009025  jb      short loc_18000903F
0x180009027  mov     rcx, [rcx+10h]
0x18000902b  lea     r8, WPP_46616a5bce583dfc538f214383f522c0_Traceguids
0x180009032  mov     edx, 0Eh
0x180009037  mov     r9d, ebx
0x18000903a  call    WPP_SF_d
0x18000903f  mov     eax, ebx
0x180009041  mov     rbx, [rsp+28h+arg_0]
0x180009046  add     rsp, 20h
0x18000904a  pop     rdi
0x18000904b  retn
```
