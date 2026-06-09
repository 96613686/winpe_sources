# CPersistableIcon::GetIcon(int,CSmartIcon &)

- ea: `0x1800081ec`
- end: `0x1800083b1`
- name: `?GetIcon@CPersistableIcon@@QEBAJHAEAVCSmartIcon@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(CPersistableIcon *this, int, struct CSmartIcon *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180002160`

## callees

- `0x180002c40`
- `0x180007c7c`
- `0x180007cb8`
- `0x180007da0`
- `0x180007dec`
- `0x1800081ec`

## import_xrefs

- `USER32!CopyImage` at `0x1800082b2`
- `USER32!CopyImage` at `0x1800082b2`
- `KERNEL32!GetLastError` at `0x1800082d1`
- `KERNEL32!GetLastError` at `0x1800082d1`

## pseudocode

```c
__int64 __fastcall CPersistableIcon::GetIcon(CPersistableIcon *this, int a2, struct CSmartIcon *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rax
  void *v7; // rcx
  HICON v8; // rax
  signed int LastError; // eax
  _QWORD *v10; // rcx
  __int64 v12; // [rsp+68h] [rbp+20h] BYREF

  v5 = 0;
  if ( a2 == 16 || a2 == 32 )
  {
LABEL_34:
    CSmartIcon::operator=(a3);
    return v5;
  }
  v6 = *((_QWORD *)this + 7);
  if ( a2 == 48 )
  {
    if ( (!v6 || !*(_QWORD *)v6)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b863bf09446f3c1eaaaf5f26bf80057e_Traceguids);
    }
    goto LABEL_34;
  }
  v12 = *((_QWORD *)this + 7);
  if ( v6 )
    ++*(_DWORD *)(v6 + 8);
  if ( a2 <= 40 )
    goto LABEL_12;
  if ( !v6 || !*(_QWORD *)v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b863bf09446f3c1eaaaf5f26bf80057e_Traceguids);
LABEL_12:
    CSmartIcon::operator=(&v12);
    v6 = v12;
  }
  if ( v6 )
    v7 = *(void **)v6;
  else
    v7 = 0;
  v8 = (HICON)CopyImage(v7, 1u, a2, a2, 0);
  CSmartIcon::Attach(a3, v8);
  if ( !*(_QWORD *)a3 || !**(_QWORD **)a3 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b863bf09446f3c1eaaaf5f26bf80057e_Traceguids, v5);
      v10 = WPP_GLOBAL_Control;
    }
    if ( (v5 & 0x80000000) == 0 )
    {
      if ( v10 != &WPP_GLOBAL_Control && *((_BYTE *)v10 + 25) >= 4u )
        WPP_SF_(v10[2], 13, WPP_b863bf09446f3c1eaaaf5f26bf80057e_Traceguids);
      v5 = -2147467259;
    }
  }
  CSmartIcon::Empty((CSmartIcon *)&v12);
  return v5;
}

```

## disassembly

```asm
0x1800081ec  mov     [rsp+arg_0], rbx
0x1800081f1  mov     [rsp+arg_8], rbp
0x1800081f6  push    rsi
0x1800081f7  push    rdi
0x1800081f8  push    r14
0x1800081fa  sub     rsp, 30h
0x1800081fe  mov     r14, r8
0x180008201  mov     esi, edx
0x180008203  mov     rdi, rcx
0x180008206  xor     ebx, ebx
0x180008208  cmp     edx, 10h
0x18000820b  jz      loc_180008390
0x180008211  cmp     edx, 20h ; ' '
0x180008214  jz      loc_18000838A
0x18000821a  lea     rdx, [rcx+38h]
0x18000821e  mov     rax, [rdx]
0x180008221  cmp     esi, 30h ; '0'
0x180008224  jz      loc_18000834C
0x18000822a  mov     [rsp+48h+arg_18], rax
0x18000822f  test    rax, rax
0x180008232  jz      short loc_180008237
0x180008234  inc     dword ptr [rax+8]
0x180008237  lea     rbp, WPP_GLOBAL_Control
0x18000823e  cmp     esi, 18h
0x180008241  jg      short loc_180008249
0x180008243  lea     rdx, [rcx+28h]
0x180008247  jmp     short loc_180008284
0x180008249  cmp     esi, 28h ; '('
0x18000824c  jle     short loc_180008280
0x18000824e  test    rax, rax
0x180008251  jz      short loc_180008259
0x180008253  cmp     qword ptr [rax], 0
0x180008257  jnz     short loc_180008293
0x180008259  mov     rcx, cs:WPP_GLOBAL_Control
0x180008260  cmp     rcx, rbp
0x180008263  jz      short loc_180008280
0x180008265  cmp     byte ptr [rcx+19h], 4
0x180008269  jb      short loc_180008280
0x18000826b  mov     edx, 0Bh
0x180008270  lea     r8, WPP_b863bf09446f3c1eaaaf5f26bf80057e_Traceguids
0x180008277  mov     rcx, [rcx+10h]
0x18000827b  call    WPP_SF_
0x180008280  lea     rdx, [rdi+30h]
0x180008284  lea     rcx, [rsp+48h+arg_18]
0x180008289  call    ??4CSmartIcon@@QEAAAEAV0@AEBV0@@Z; CSmartIcon::operator=(CSmartIcon const &)
0x18000828e  mov     rax, [rsp+48h+arg_18]
0x180008293  test    rax, rax
0x180008296  jz      short loc_18000829D
0x180008298  mov     rcx, [rax]
0x18000829b  jmp     short loc_18000829F
0x18000829d  xor     ecx, ecx; h
0x18000829f  mov     [rsp+48h+flags], 0; flags
0x1800082a7  mov     r9d, esi; cy
0x1800082aa  mov     r8d, esi; cx
0x1800082ad  mov     edx, 1; type
0x1800082b2  call    cs:__imp_CopyImage
0x1800082b8  mov     rdx, rax; HICON
0x1800082bb  mov     rcx, r14; this
0x1800082be  call    ?Attach@CSmartIcon@@QEAAXPEAUHICON__@@@Z; CSmartIcon::Attach(HICON__ *)
0x1800082c3  mov     rax, [r14]
0x1800082c6  test    rax, rax
0x1800082c9  jz      short loc_1800082D1
0x1800082cb  cmp     qword ptr [rax], 0
0x1800082cf  jnz     short loc_180008340
0x1800082d1  call    cs:__imp_GetLastError
0x1800082d7  mov     ebx, eax
0x1800082d9  test    eax, eax
0x1800082db  jle     short loc_1800082E6
0x1800082dd  movzx   ebx, ax
0x1800082e0  or      ebx, 80070000h
0x1800082e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082ed  cmp     rcx, rbp
0x1800082f0  jz      short loc_180008317
0x1800082f2  cmp     byte ptr [rcx+19h], 2
0x1800082f6  jb      short loc_180008317
0x1800082f8  mov     edx, 0Ch
0x1800082fd  mov     r9d, ebx
0x180008300  lea     r8, WPP_b863bf09446f3c1eaaaf5f26bf80057e_Traceguids
0x180008307  mov     rcx, [rcx+10h]
0x18000830b  call    WPP_SF_d
0x180008310  mov     rcx, cs:WPP_GLOBAL_Control
0x180008317  test    ebx, ebx
0x180008319  js      short loc_180008340
0x18000831b  cmp     rcx, rbp
0x18000831e  jz      short loc_18000833B
0x180008320  cmp     byte ptr [rcx+19h], 4
0x180008324  jb      short loc_18000833B
0x180008326  mov     edx, 0Dh
0x18000832b  lea     r8, WPP_b863bf09446f3c1eaaaf5f26bf80057e_Traceguids
0x180008332  mov     rcx, [rcx+10h]
0x180008336  call    WPP_SF_
0x18000833b  mov     ebx, 80004005h
0x180008340  lea     rcx, [rsp+48h+arg_18]; this
0x180008345  call    ?Empty@CSmartIcon@@QEAAXXZ; CSmartIcon::Empty(void)
0x18000834a  jmp     short loc_18000839C
0x18000834c  test    rax, rax
0x18000834f  jz      short loc_180008356
0x180008351  cmp     [rax], rbx
0x180008354  jnz     short loc_180008394
0x180008356  lea     rbp, WPP_GLOBAL_Control
0x18000835d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008364  cmp     rcx, rbp
0x180008367  jz      short loc_180008384
0x180008369  cmp     byte ptr [rcx+19h], 4
0x18000836d  jb      short loc_180008384
0x18000836f  mov     edx, 0Ah
0x180008374  lea     r8, WPP_b863bf09446f3c1eaaaf5f26bf80057e_Traceguids
0x18000837b  mov     rcx, [rcx+10h]
0x18000837f  call    WPP_SF_
0x180008384  lea     rdx, [rdi+30h]
0x180008388  jmp     short loc_180008394
0x18000838a  lea     rdx, [rcx+30h]
0x18000838e  jmp     short loc_180008394
0x180008390  lea     rdx, [rcx+28h]
0x180008394  mov     rcx, r14
0x180008397  call    ??4CSmartIcon@@QEAAAEAV0@AEBV0@@Z; CSmartIcon::operator=(CSmartIcon const &)
0x18000839c  mov     eax, ebx
0x18000839e  mov     rbx, [rsp+48h+arg_0]
0x1800083a3  mov     rbp, [rsp+48h+arg_8]
0x1800083a8  add     rsp, 30h
0x1800083ac  pop     r14
0x1800083ae  pop     rdi
0x1800083af  pop     rsi
0x1800083b0  retn
```
