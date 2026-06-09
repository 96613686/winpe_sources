# CMenu::get_accState(tagVARIANT,tagVARIANT *)

- ea: `0x18000ceb0`
- end: `0x18000d072`
- name: `?get_accState@CMenu@@UEAAJUtagVARIANT@@PEAU2@@Z`
- size: `450`
- prototype: `__int64 __fastcall(CMenu *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000c6a0`
- `0x18000ceb0`
- `0x18000d18c`
- `0x18001e4c0`
- `0x18001efc4`
- `0x180049010`

## import_xrefs

- `USER32!IsRectEmpty` at `0x18000cfa6`
- `USER32!IsRectEmpty` at `0x18000cfa6`
- `USER32!GetMenuItemInfoW` at `0x18000cffd`
- `USER32!GetMenuItemInfoW` at `0x18000cffd`

## pseudocode

```c
__int64 __fastcall CMenu::get_accState(CMenu *this, struct tagVARIANT *a2, struct tagVARIANT *a3)
{
  __int128 v3; // xmm0
  IRecordInfo *pRecInfo; // xmm1_8
  __int64 v7; // rax
  unsigned int (__fastcall *v8)(CMenu *, int *); // rax
  int v10; // r14d
  HMENU v11; // rcx
  __int16 fState; // ax
  int v13[4]; // [rsp+30h] [rbp-79h] BYREF
  IRecordInfo *v14; // [rsp+40h] [rbp-69h]
  struct tagMENUITEMINFOW mii; // [rsp+50h] [rbp-59h] BYREF
  struct tagMENUBARINFO rc; // [rsp+A0h] [rbp-9h] BYREF

  v3 = *(_OWORD *)&a2->vt;
  pRecInfo = a2->pRecInfo;
  a3->vt = 0;
  v7 = *(_QWORD *)this;
  *(_OWORD *)v13 = v3;
  v14 = pRecInfo;
  v8 = *(unsigned int (__fastcall **)(CMenu *, int *))(v7 + 240);
  memset(&rc, 0, sizeof(rc));
  if ( v8(this, v13) )
  {
    a3->lVal = 0;
    a3->vt = 3;
    if ( *((_QWORD *)this + 16)
      && MyGetMenuBarInfo(
           *((_DWORD *)this + 25),
           *((_DWORD *)this + 17),
           *((HWND *)this + 10),
           *((_DWORD *)this + 30) != 0 ? -1 : -3,
           v13[2],
           &rc) )
    {
      if ( !v13[2] || !GetMDIButtonIndex(*((HMENU *)this + 16), v13[2] - 1) )
      {
        if ( IsRectEmpty(&rc.rcBar) )
          a3->lVal |= 0x8000u;
        a3->lVal |= 0x100000u;
        if ( (*((_BYTE *)&rc + 40) & 2) != 0 )
          a3->lVal |= 4u;
        v10 = v13[2];
        if ( v13[2] )
        {
          memset_0(&mii, 0, sizeof(mii));
          v11 = (HMENU)*((_QWORD *)this + 16);
          mii.cbSize = 80;
          mii.fMask = 5;
          if ( !GetMenuItemInfoW(v11, v10 - 1, 1, &mii) )
          {
            a3->lVal |= 0x8000u;
            return 1;
          }
          fState = mii.fState;
          if ( (mii.fState & 3) != 0 )
            a3->lVal |= 1u;
          if ( (fState & 8) != 0 )
            a3->lVal |= 0x10u;
          if ( (fState & 0x1000) != 0 )
            a3->lVal |= 0x100u;
          if ( (*((_BYTE *)&rc + 40) & 2) != 0 )
          {
            a3->lVal |= 0x80u;
            if ( (fState & 0x80u) != 0 )
              a3->lVal |= 4u;
          }
          if ( mii.hSubMenu )
            a3->lVal |= 0x40000000u;
        }
      }
    }
    else
    {
      a3->lVal |= 0x8000u;
    }
    return 0;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000ceb0  push    rbp
0x18000ceb2  push    rbx
0x18000ceb3  push    rsi
0x18000ceb4  push    r13
0x18000ceb6  push    r14
0x18000ceb8  lea     rbp, [rsp-37h]
0x18000cebd  sub     rsp, 0E0h
0x18000cec4  mov     rax, cs:__security_cookie
0x18000cecb  xor     rax, rsp
0x18000cece  mov     [rbp+57h+var_30], rax
0x18000ced2  movups  xmm0, xmmword ptr [rdx]
0x18000ced5  xor     eax, eax
0x18000ced7  mov     rbx, r8
0x18000ceda  movsd   xmm1, qword ptr [rdx+10h]
0x18000cedf  mov     rsi, rcx
0x18000cee2  mov     [r8], ax
0x18000cee6  lea     rdx, [rbp+57h+var_D0]
0x18000ceea  mov     rax, [rcx]
0x18000ceed  movups  xmmword ptr [rbp+57h+var_D0], xmm0
0x18000cef1  xorps   xmm0, xmm0
0x18000cef4  movsd   [rbp+57h+var_C0], xmm1
0x18000cef9  mov     rax, [rax+0F0h]
0x18000cf00  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x18000cf04  movups  [rbp+57h+var_50], xmm0
0x18000cf08  movups  [rbp+57h+var_40], xmm0
0x18000cf0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf11  test    eax, eax
0x18000cf13  jz      loc_18000D014
0x18000cf19  mov     r13d, 3
0x18000cf1f  mov     dword ptr [rbx+8], 0
0x18000cf26  mov     [rbx], r13w
0x18000cf2a  cmp     qword ptr [rsi+80h], 0
0x18000cf32  jnz     short loc_18000CF56
0x18000cf34  bts     dword ptr [rbx+8], 0Fh
0x18000cf39  xor     eax, eax
0x18000cf3b  mov     rcx, [rbp+57h+var_30]
0x18000cf3f  xor     rcx, rsp; StackCookie
0x18000cf42  call    __security_check_cookie
0x18000cf47  add     rsp, 0E0h
0x18000cf4e  pop     r14
0x18000cf50  pop     r13
0x18000cf52  pop     rsi
0x18000cf53  pop     rbx
0x18000cf54  pop     rbp
0x18000cf55  retn
0x18000cf56  mov     eax, [rsi+78h]
0x18000cf59  mov     ecx, [rbp+57h+var_D0+8]
0x18000cf5c  neg     eax
0x18000cf5e  mov     r8, [rsi+50h]; HWND
0x18000cf62  lea     rax, [rbp+57h+rc]
0x18000cf66  mov     edx, [rsi+44h]; unsigned int
0x18000cf69  sbb     r9d, r9d
0x18000cf6c  and     r9d, 2
0x18000cf70  mov     [rsp+100h+var_D8], rax; struct tagMENUBARINFO *
0x18000cf75  mov     [rsp+100h+var_E0], ecx; int
0x18000cf79  add     r9d, 0FFFFFFFDh; int
0x18000cf7d  mov     ecx, [rsi+64h]; unsigned int
0x18000cf80  call    ?MyGetMenuBarInfo@@YAHKKPEAUHWND__@@JJPEAUtagMENUBARINFO@@@Z; MyGetMenuBarInfo(ulong,ulong,HWND__ *,long,long,tagMENUBARINFO *)
0x18000cf85  test    eax, eax
0x18000cf87  jz      short loc_18000CF34
0x18000cf89  mov     edx, [rbp+57h+var_D0+8]
0x18000cf8c  test    edx, edx
0x18000cf8e  jz      short loc_18000CFA2
0x18000cf90  mov     rcx, [rsi+80h]; HMENU
0x18000cf97  dec     edx; unsigned int
0x18000cf99  call    ?GetMDIButtonIndex@@YAIPEAUHMENU__@@K@Z; GetMDIButtonIndex(HMENU__ *,ulong)
0x18000cf9e  test    eax, eax
0x18000cfa0  jnz     short loc_18000CF39
0x18000cfa2  lea     rcx, [rbp+57h+rc.top]; lprc
0x18000cfa6  call    cs:__imp_IsRectEmpty
0x18000cfac  test    eax, eax
0x18000cfae  jnz     short loc_18000D01E
0x18000cfb0  bts     dword ptr [rbx+8], 14h
0x18000cfb5  test    byte ptr [rbp+57h+var_40+8], 2
0x18000cfb9  jnz     short loc_18000D025
0x18000cfbb  mov     r14d, [rbp+57h+var_D0+8]
0x18000cfbf  test    r14d, r14d
0x18000cfc2  jz      loc_18000CF39
0x18000cfc8  xor     edx, edx; Val
0x18000cfca  lea     rcx, [rbp+57h+mii]; void *
0x18000cfce  lea     r8d, [rdx+50h]; Size
0x18000cfd2  call    memset_0
0x18000cfd7  mov     rcx, [rsi+80h]; hmenu
0x18000cfde  lea     edx, [r14-1]; item
0x18000cfe2  mov     r14d, 1
0x18000cfe8  mov     [rbp+57h+mii.cbSize], 50h ; 'P'
0x18000cfef  mov     r8d, r14d; fByPosition
0x18000cff2  mov     [rbp+57h+mii.fMask], 5
0x18000cff9  lea     r9, [rbp+57h+mii]; lpmii
0x18000cffd  call    cs:__imp_GetMenuItemInfoW
0x18000d003  test    eax, eax
0x18000d005  jnz     short loc_18000D02B
0x18000d007  bts     dword ptr [rbx+8], 0Fh
0x18000d00c  mov     eax, r14d
0x18000d00f  jmp     loc_18000CF3B
0x18000d014  mov     eax, 80070057h
0x18000d019  jmp     loc_18000CF3B
0x18000d01e  bts     dword ptr [rbx+8], 0Fh
0x18000d023  jmp     short loc_18000CFB0
0x18000d025  or      dword ptr [rbx+8], 4
0x18000d029  jmp     short loc_18000CFBB
0x18000d02b  mov     eax, [rbp+57h+mii.fState]
0x18000d02e  test    r13b, al
0x18000d031  jz      short loc_18000D037
0x18000d033  or      [rbx+8], r14d
0x18000d037  test    al, 8
0x18000d039  jz      short loc_18000D03F
0x18000d03b  or      dword ptr [rbx+8], 10h
0x18000d03f  bt      eax, 0Ch
0x18000d043  jnb     short loc_18000D04A
0x18000d045  bts     dword ptr [rbx+8], 8
0x18000d04a  test    byte ptr [rbp+57h+var_40+8], 2
0x18000d04e  jz      short loc_18000D05D
0x18000d050  bts     dword ptr [rbx+8], 7
0x18000d055  test    al, al
0x18000d057  jns     short loc_18000D05D
0x18000d059  or      dword ptr [rbx+8], 4
0x18000d05d  cmp     [rbp+57h+mii.hSubMenu], 0
0x18000d062  jz      loc_18000CF39
0x18000d068  bts     dword ptr [rbx+8], 1Eh
0x18000d06d  jmp     loc_18000CF39
```
