# CSelectMonth::RealDlgProc(uint,unsigned __int64,__int64)

- ea: `0x1800192e0`
- end: `0x180019403`
- name: `?RealDlgProc@CSelectMonth@@EEAA_JI_K_J@Z`
- size: `291`
- prototype: `__int64 __fastcall(CSelectMonth *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180017df4`
- `0x1800192e0`

## import_xrefs

- `USER32!CheckDlgButton` at `0x1800193ba`
- `USER32!CheckDlgButton` at `0x1800193ba`
- `USER32!WinHelpW` at `0x1800193ef`
- `USER32!WinHelpW` at `0x1800193ef`
- `USER32!EndDialog` at `0x180019379`
- `USER32!EndDialog` at `0x180019379`
- `USER32!IsDlgButtonChecked` at `0x180019341`
- `USER32!IsDlgButtonChecked` at `0x180019341`

## string_xrefs

- `0x1800193e8`: `%windir%\help\mstask.hlp`

## pseudocode

```c
__int64 __fastcall CSelectMonth::RealDlgProc(HWND *this, int a2, HWND a3, __int64 a4)
{
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v10; // esi
  unsigned int j; // ebx
  unsigned int i; // ebx
  int v13; // eax
  UINT v14; // r8d
  HWND v15; // rcx

  v6 = a2 - 83;
  if ( !v6 )
  {
    v15 = *(HWND *)(a4 + 16);
    v14 = 12;
    goto LABEL_23;
  }
  v7 = v6 - 40;
  if ( !v7 )
  {
    v14 = 10;
    v15 = a3;
LABEL_23:
    WinHelpW(v15, szMstaskHelp, v14, (ULONG_PTR)L"i");
    return 1;
  }
  v8 = v7 - 149;
  if ( !v8 )
  {
    for ( i = 1742; i <= 0x6D9; ++i )
    {
      v13 = *((unsigned __int16 *)this + 8);
      if ( _bittest(&v13, (unsigned __int8)(i + 50)) )
        CheckDlgButton(this[1], i, 1u);
    }
    return 1;
  }
  if ( v8 != 1 )
    return 0;
  v10 = (unsigned __int16)a3;
  if ( (unsigned __int16)a3 == 1 )
  {
    *((_WORD *)this + 8) = 0;
    for ( j = 1742; j <= 0x6D9; ++j )
    {
      if ( IsDlgButtonChecked(this[1], j) )
        *((_WORD *)this + 8) |= 1 << (j + 50);
    }
    if ( !*((_WORD *)this + 8) )
    {
      SchedUIErrorDialog(this[1], 0x1030u, 0, 0);
      return 1;
    }
  }
  else if ( (unsigned __int16)a3 != 2 )
  {
    return 1;
  }
  EndDialog(this[1], v10 != 2);
  return 1;
}

```

## disassembly

```asm
0x1800192e0  push    rbx
0x1800192e2  push    rbp
0x1800192e3  push    rsi
0x1800192e4  push    rdi
0x1800192e5  sub     rsp, 28h
0x1800192e9  mov     r10, r9
0x1800192ec  mov     rax, r8
0x1800192ef  mov     rdi, rcx
0x1800192f2  sub     edx, 53h ; 'S'
0x1800192f5  jz      loc_1800193D7
0x1800192fb  sub     edx, 28h ; '('
0x1800192fe  jz      loc_1800193CC
0x180019304  sub     edx, 95h
0x18001930a  jz      loc_180019397
0x180019310  cmp     edx, 1
0x180019313  jz      short loc_18001931C
0x180019315  xor     eax, eax
0x180019317  jmp     loc_1800193FA
0x18001931c  movzx   esi, ax
0x18001931f  xor     ebp, ebp
0x180019321  mov     ecx, esi
0x180019323  sub     ecx, 1
0x180019326  jz      short loc_180019332
0x180019328  cmp     ecx, 1
0x18001932b  jz      short loc_18001936C
0x18001932d  jmp     loc_1800193F5
0x180019332  mov     [rdi+10h], bp
0x180019336  mov     ebx, 6CEh
0x18001933b  mov     rcx, [rdi+8]; hDlg
0x18001933f  mov     edx, ebx; nIDButton
0x180019341  call    cs:__imp_IsDlgButtonChecked
0x180019347  test    eax, eax
0x180019349  jz      short loc_18001935C
0x18001934b  movzx   ecx, word ptr [rdi+10h]
0x18001934f  lea     eax, [rbx-6CEh]
0x180019355  bts     ecx, eax
0x180019358  mov     [rdi+10h], cx
0x18001935c  inc     ebx
0x18001935e  cmp     ebx, 6D9h
0x180019364  jbe     short loc_18001933B
0x180019366  cmp     [rdi+10h], bp
0x18001936a  jz      short loc_180019381
0x18001936c  mov     rcx, [rdi+8]; hDlg
0x180019370  cmp     esi, 2
0x180019373  mov     rdx, rbp
0x180019376  setnz   dl; nResult
0x180019379  call    cs:__imp_EndDialog
0x18001937f  jmp     short loc_1800193F5
0x180019381  mov     rcx, [rdi+8]; hWnd
0x180019385  xor     r9d, r9d; UINT
0x180019388  xor     r8d, r8d; int
0x18001938b  mov     edx, 1030h; uID
0x180019390  call    ?SchedUIErrorDialog@@YAXPEAUHWND__@@HJI@Z; SchedUIErrorDialog(HWND__ *,int,long,uint)
0x180019395  jmp     short loc_1800193F5
0x180019397  mov     ebx, 6CEh
0x18001939c  movzx   eax, word ptr [rdi+10h]
0x1800193a0  lea     ecx, [rbx-6CEh]
0x1800193a6  movzx   edx, cl
0x1800193a9  bt      eax, edx
0x1800193ac  jnb     short loc_1800193C0
0x1800193ae  mov     rcx, [rdi+8]; hDlg
0x1800193b2  mov     r8d, 1; uCheck
0x1800193b8  mov     edx, ebx; nIDButton
0x1800193ba  call    cs:__imp_CheckDlgButton
0x1800193c0  inc     ebx
0x1800193c2  cmp     ebx, 6D9h
0x1800193c8  jbe     short loc_18001939C
0x1800193ca  jmp     short loc_1800193F5
0x1800193cc  mov     r8d, 0Ah
0x1800193d2  mov     rcx, rax
0x1800193d5  jmp     short loc_1800193E1
0x1800193d7  mov     rcx, [r10+10h]; hWndMain
0x1800193db  mov     r8d, 0Ch; uCommand
0x1800193e1  lea     r9, aI; "i"
0x1800193e8  lea     rdx, szMstaskHelp; "%windir%\\help\\mstask.hlp"
0x1800193ef  call    cs:__imp_WinHelpW
0x1800193f5  mov     eax, 1
0x1800193fa  add     rsp, 28h
0x1800193fe  pop     rdi
0x1800193ff  pop     rsi
0x180019400  pop     rbp
0x180019401  pop     rbx
0x180019402  retn
```
