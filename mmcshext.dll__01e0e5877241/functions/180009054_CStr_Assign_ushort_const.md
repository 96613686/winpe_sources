# CStr::Assign(ushort const *)

- ea: `0x180009054`
- end: `0x180009141`
- name: `?Assign@CStr@@QEAAJPEBG@Z`
- size: `237`
- prototype: `__int64 __fastcall(CStr *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002460`
- `0x180004240`
- `0x180005dbc`

## callees

- `0x180002c40`
- `0x180007dec`
- `0x180008c54`
- `0x180009054`
- `0x18000931c`

## pseudocode

```c
__int64 __fastcall CStr::Assign(CStr *this, const unsigned __int16 *a2)
{
  unsigned __int16 near **v2; // r8
  int v5; // ebx
  _QWORD *v6; // rcx
  unsigned __int16 v7; // dx

  v2 = (unsigned __int16 near **)*((_QWORD *)this + 1);
  if ( a2 == (const unsigned __int16 *)v2 )
  {
    v5 = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v7 = 15;
LABEL_5:
      WPP_SF_(v6[2], v7, (__int64)WPP_46616a5bce583dfc538f214383f522c0_Traceguids);
    }
  }
  else if ( v2 == &CStr::s_rgwchEmptyStringBuffer
         || a2 < (const unsigned __int16 *)v2
         || a2 > (const unsigned __int16 *)v2 + *((unsigned int *)this + 5) )
  {
    CStr::Empty(this);
    v5 = CStr::Append(this, a2);
    if ( v5 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x11u, (__int64)WPP_46616a5bce583dfc538f214383f522c0_Traceguids, v5);
  }
  else
  {
    v5 = -2147024809;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 16;
      goto LABEL_5;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180009054  mov     [rsp+arg_0], rbx
0x180009059  push    rdi
0x18000905a  sub     rsp, 20h
0x18000905e  mov     r8, [rcx+8]
0x180009062  mov     rbx, rdx
0x180009065  mov     rdi, rcx
0x180009068  cmp     rdx, r8
0x18000906b  jnz     short loc_1800090A8
0x18000906d  xor     ebx, ebx
0x18000906f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009076  lea     rax, WPP_GLOBAL_Control
0x18000907d  cmp     rcx, rax
0x180009080  jz      loc_180009134
0x180009086  cmp     byte ptr [rcx+19h], 4
0x18000908a  jb      loc_180009134
0x180009090  lea     edx, [rbx+0Fh]
0x180009093  mov     rcx, [rcx+10h]
0x180009097  lea     r8, WPP_46616a5bce583dfc538f214383f522c0_Traceguids
0x18000909e  call    WPP_SF_
0x1800090a3  jmp     loc_180009134
0x1800090a8  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x1800090af  cmp     r8, rax
0x1800090b2  jz      short loc_1800090EA
0x1800090b4  cmp     rbx, r8
0x1800090b7  jb      short loc_1800090EA
0x1800090b9  mov     eax, [rcx+14h]
0x1800090bc  lea     rcx, [r8+rax*2]
0x1800090c0  cmp     rbx, rcx
0x1800090c3  ja      short loc_1800090EA
0x1800090c5  mov     ebx, 80070057h
0x1800090ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090d1  lea     rax, WPP_GLOBAL_Control
0x1800090d8  cmp     rcx, rax
0x1800090db  jz      short loc_180009134
0x1800090dd  cmp     byte ptr [rcx+19h], 2
0x1800090e1  jb      short loc_180009134
0x1800090e3  mov     edx, 10h
0x1800090e8  jmp     short loc_180009093
0x1800090ea  mov     rcx, rdi; this
0x1800090ed  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x1800090f2  mov     rdx, rbx; unsigned __int16 *
0x1800090f5  mov     rcx, rdi; this
0x1800090f8  call    ?Append@CStr@@QEAAJPEBG@Z; CStr::Append(ushort const *)
0x1800090fd  mov     ebx, eax
0x1800090ff  test    eax, eax
0x180009101  jns     short loc_180009134
0x180009103  mov     rcx, cs:WPP_GLOBAL_Control
0x18000910a  lea     rax, WPP_GLOBAL_Control
0x180009111  cmp     rcx, rax
0x180009114  jz      short loc_180009134
0x180009116  cmp     byte ptr [rcx+19h], 2
0x18000911a  jb      short loc_180009134
0x18000911c  mov     rcx, [rcx+10h]
0x180009120  lea     r8, WPP_46616a5bce583dfc538f214383f522c0_Traceguids
0x180009127  mov     edx, 11h
0x18000912c  mov     r9d, ebx
0x18000912f  call    WPP_SF_d
0x180009134  mov     eax, ebx
0x180009136  mov     rbx, [rsp+28h+arg_0]
0x18000913b  add     rsp, 20h
0x18000913f  pop     rdi
0x180009140  retn
```
