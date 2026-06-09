# ListView_OnKey

- ea: `0x180056f4c`
- end: `0x1800572d6`
- name: `ListView_OnKey`
- size: `906`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x18005c0a0`

## callees

- `0x180018110`
- `0x1800181a0`
- `0x180035fe0`
- `0x180050854`
- `0x18005112c`
- `0x18005181c`
- `0x180053898`
- `0x180055a14`
- `0x180056f4c`
- `0x18005b220`
- `0x18005b6b4`
- `0x18005bb20`
- `0x180079640`
- `0x18008ea60`

## import_xrefs

- `USER32!PeekMessageW` at `0x180057065`
- `USER32!PeekMessageW` at `0x180057065`
- `USER32!IsWindow` at `0x180056ff2`
- `USER32!IsWindow` at `0x180057257`
- `USER32!IsWindow` at `0x1800572a5`
- `USER32!IsWindow` at `0x180056ff2`
- `USER32!IsWindow` at `0x180057257`
- `USER32!IsWindow` at `0x1800572a5`
- `USER32!SetCursor` at `0x1800570ec`
- `USER32!SetCursor` at `0x18005711d`
- `USER32!SetCursor` at `0x1800570ec`
- `USER32!SetCursor` at `0x18005711d`
- `USER32!LoadCursorW` at `0x1800570e3`
- `USER32!LoadCursorW` at `0x1800570e3`
- `USER32!GetKeyState` at `0x18005708a`
- `USER32!GetKeyState` at `0x180057099`
- `USER32!GetKeyState` at `0x1800570d1`
- `USER32!GetKeyState` at `0x18005712d`
- `USER32!GetKeyState` at `0x18005708a`
- `USER32!GetKeyState` at `0x180057099`
- `USER32!GetKeyState` at `0x1800570d1`
- `USER32!GetKeyState` at `0x18005712d`
- `USER32!UpdateWindow` at `0x1800571ea`
- `USER32!UpdateWindow` at `0x1800571ea`
- `USER32!KillTimer` at `0x180056fd1`
- `USER32!KillTimer` at `0x180056fd1`

## pseudocode

```c
void __fastcall ListView_OnKey(__int64 a1, int a2, int a3, __int64 a4, int a5)
{
  HWND v5; // rsi
  bool v7; // zf
  int v8; // edi
  LRESULT v9; // rax
  int v10; // ecx
  unsigned int KeyState; // r14d
  unsigned __int16 v12; // ax
  unsigned int v13; // esi
  int v14; // r14d
  unsigned int v15; // esi
  HCURSOR CursorW; // rax
  unsigned int v17; // edi
  HCURSOR i; // rsi
  int v19; // eax
  int v20; // edi
  int v21; // r9d
  int v22; // esi
  __int64 v23; // rdx
  __int64 v24; // rdx
  _OWORD v25[2]; // [rsp+30h] [rbp-41h] BYREF
  _BYTE Msg[72]; // [rsp+50h] [rbp-21h] BYREF

  if ( !a3 )
    return;
  v5 = *(HWND *)a1;
  v7 = (*(_DWORD *)(a1 + 32) & 0x400000) == 0;
  memset(v25, 0, 30);
  if ( !v7 )
  {
    v8 = 39;
    if ( a2 == 37 )
      goto LABEL_7;
    if ( a2 == 39 )
      a2 = 37;
  }
  v8 = a2;
LABEL_7:
  if ( (*(_BYTE *)(a1 + 76) & 0x40) == 0
    || (*(_BYTE *)(a1 + 56) & 8) == 0
    || (*(_BYTE *)(a1 + 56) & 4) == 0
    || (unsigned int)(v8 - 16) > 2
    && v8 != 13
    && (KillTimer(v5, 0x2Eu), *(_DWORD *)(a1 + 56) &= ~8u, CCSendNotify(a1, -114, a1 + 352), IsWindow(v5)) )
  {
    *(_DWORD *)((char *)&v25[1] + 10) = a5;
    WORD4(v25[1]) = v8;
    v9 = CCSendNotify(a1, -155, (LPARAM)v25);
    v10 = *(_DWORD *)(a1 + 192);
    if ( v9 )
    {
      *(_DWORD *)(a1 + 192) = v10 + 1;
      return;
    }
    if ( v10 )
    {
      memset(Msg, 0, 48);
      do
      {
        if ( !PeekMessageW((LPMSG)Msg, *(HWND *)a1, 0x102u, 0x102u, 1u) )
          break;
        v7 = (*(_DWORD *)(a1 + 192))-- == 1;
      }
      while ( !v7 );
    }
    if ( *(_DWORD *)(a1 + 512) )
    {
      KeyState = (unsigned __int16)GetKeyState(17);
      v12 = GetKeyState(16);
      if ( v8 != 13 )
      {
        v13 = KeyState;
        v14 = v12 >> 15;
        v15 = v13 >> 15;
        if ( v8 == 32 )
        {
          if ( v15 )
          {
            v23 = *(unsigned int *)(a1 + 144);
            *(_DWORD *)(a1 + 148) = v23;
            ListView_ToggleSelection(a1, v23);
            ++*(_DWORD *)(a1 + 192);
          }
          if ( v14 )
            ListView_SelectRangeTo(a1, *(_DWORD *)(a1 + 144));
          if ( (*(_BYTE *)(a1 + 76) & 4) != 0 )
          {
            v24 = *(unsigned int *)(a1 + 144);
            if ( (_DWORD)v24 != -1 )
              ListView_HandleStateIconClick(a1, v24);
          }
        }
        else if ( v8 == 107 && (*(_DWORD *)(a1 + 16) & 3) == 1 && GetKeyState(17) < 0 )
        {
          CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
          v17 = 0;
          for ( i = SetCursor(CursorW); (signed int)v17 < *(_DWORD *)(a1 + 428); ++v17 )
            ListView_RSetColumnWidth(a1, v17, 0xFFFFFFFFLL);
          SetCursor(i);
        }
        else
        {
          if ( GetKeyState(18) < 0 )
            return;
          if ( (*(_BYTE *)(a1 + 16) & 4) != 0 )
          {
            v15 = 0;
            v14 = 0;
          }
          v19 = ListView_Arrow(a1, *(_DWORD *)(a1 + 144));
          v20 = v19;
          if ( v19 != -1 )
          {
            if ( v14 )
            {
              ListView_SelectRangeTo(a1, v19);
              v21 = 0;
              v22 = 0;
            }
            else
            {
              if ( v15 )
              {
                v21 = 0;
              }
              else
              {
                *(_DWORD *)(a1 + 148) = v19;
                v21 = 1;
              }
              v22 = v15 ^ 1;
            }
            ListView_SetFocusSel(a1, v20, v22, v21, 0);
            *(_DWORD *)(a1 + 652) = 0;
            *(_DWORD *)(a1 + 632) = 0;
            CCPlaySound(L"CCSelect");
          }
          if ( (unsigned int)ListView_CancelPendingTimer(a1, 512, 43) )
          {
            ListView_OnEnsureVisible(a1, *(_DWORD *)(a1 + 144));
            UpdateWindow(*(HWND *)a1);
          }
        }
        goto LABEL_50;
      }
      CCSendNotify(a1, -4, 0);
      if ( IsWindow(v5) )
      {
        memset(Msg, 0, sizeof(Msg));
        *(_QWORD *)&Msg[24] = *(unsigned int *)(a1 + 144);
        *(_DWORD *)&Msg[40] = 0;
        *(_QWORD *)&Msg[44] = -1;
        *(_DWORD *)&Msg[64] = GetLVKeyFlags();
        CCSendNotify(a1, -114, (LPARAM)Msg);
        if ( IsWindow(v5) )
LABEL_50:
          CCNotifyNavigationKeyUsage(a1, 1);
      }
    }
  }
}

```

## disassembly

```asm
0x180056f4c  test    r8d, r8d
0x180056f4f  jz      locret_1800572D5
0x180056f55  mov     [rsp-8+arg_0], rbx
0x180056f5a  mov     [rsp-8+arg_8], rsi
0x180056f5f  push    rbp
0x180056f60  push    rdi
0x180056f61  push    r12
0x180056f63  push    r14
0x180056f65  push    r15
0x180056f67  lea     rbp, [rsp-2Fh]
0x180056f6c  sub     rsp, 0A0h
0x180056f73  mov     rsi, [rcx]
0x180056f76  xorps   xmm0, xmm0
0x180056f79  xor     r15d, r15d
0x180056f7c  mov     rbx, rcx
0x180056f7f  test    dword ptr [rcx+20h], 400000h
0x180056f86  movups  [rbp+4Fh+var_90], xmm0
0x180056f8a  movups  [rbp+4Fh+var_90+0Eh], xmm0
0x180056f8e  jz      short loc_180056FA0
0x180056f90  lea     eax, [r15+25h]
0x180056f94  lea     edi, [rax+2]
0x180056f97  cmp     edx, eax
0x180056f99  jz      short loc_180056FA2
0x180056f9b  cmp     edx, edi
0x180056f9d  cmovz   edx, eax
0x180056fa0  mov     edi, edx
0x180056fa2  test    byte ptr [rcx+4Ch], 40h
0x180056fa6  jz      short loc_180057000
0x180056fa8  test    byte ptr [rcx+38h], 8
0x180056fac  jz      short loc_180057000
0x180056fae  test    byte ptr [rcx+38h], 4
0x180056fb2  jz      short loc_180057000
0x180056fb4  lea     eax, [rdi-10h]
0x180056fb7  cmp     eax, 2
0x180056fba  jbe     loc_1800572BA
0x180056fc0  cmp     edi, 0Dh
0x180056fc3  jz      loc_1800572BA
0x180056fc9  mov     edx, 2Eh ; '.'; uIDEvent
0x180056fce  mov     rcx, rsi; hWnd
0x180056fd1  call    cs:__imp_KillTimer
0x180056fd7  and     dword ptr [rbx+38h], 0FFFFFFF7h
0x180056fdb  lea     r8, [rbx+160h]
0x180056fe2  mov     edx, 0FFFFFF8Eh
0x180056fe7  mov     rcx, rbx
0x180056fea  call    CCSendNotify
0x180056fef  mov     rcx, rsi; hWnd
0x180056ff2  call    cs:__imp_IsWindow
0x180056ff8  test    eax, eax
0x180056ffa  jz      loc_1800572BA
0x180057000  mov     eax, [rbp+4Fh+arg_20]
0x180057003  lea     r8, [rbp+4Fh+var_90]
0x180057007  mov     edx, 0FFFFFF65h
0x18005700c  mov     [rbp+4Fh+var_76], eax
0x18005700f  mov     rcx, rbx
0x180057012  mov     [rbp+4Fh+var_78], di
0x180057016  call    CCSendNotify
0x18005701b  mov     ecx, [rbx+0C0h]
0x180057021  test    rax, rax
0x180057024  jz      short loc_180057034
0x180057026  lea     eax, [rcx+1]
0x180057029  mov     [rbx+0C0h], eax
0x18005702f  jmp     loc_1800572BA
0x180057034  mov     r12d, 1
0x18005703a  test    ecx, ecx
0x18005703c  jz      short loc_180057078
0x18005703e  xorps   xmm0, xmm0
0x180057041  mov     r14d, 102h
0x180057047  movups  xmmword ptr [rbp+4Fh+Msg.hwnd], xmm0
0x18005704b  movups  xmmword ptr [rbp+4Fh+Msg.wParam], xmm0
0x18005704f  movups  xmmword ptr [rbp+4Fh+Msg.time], xmm0
0x180057053  mov     rdx, [rbx]; hWnd
0x180057056  lea     rcx, [rbp+4Fh+Msg]; lpMsg
0x18005705a  mov     r9d, r14d; wMsgFilterMax
0x18005705d  mov     [rsp+0C0h+wRemoveMsg], r12d; wRemoveMsg
0x180057062  mov     r8d, r14d; wMsgFilterMin
0x180057065  call    cs:__imp_PeekMessageW
0x18005706b  test    eax, eax
0x18005706d  jz      short loc_180057078
0x18005706f  sub     [rbx+0C0h], r12d
0x180057076  jnz     short loc_180057053
0x180057078  cmp     [rbx+200h], r15d
0x18005707f  jz      loc_1800572BA
0x180057085  mov     ecx, 11h; nVirtKey
0x18005708a  call    cs:__imp_GetKeyState
0x180057090  mov     ecx, 10h; nVirtKey
0x180057095  movzx   r14d, ax
0x180057099  call    cs:__imp_GetKeyState
0x18005709f  cmp     edi, 0Dh
0x1800570a2  jz      loc_180057245
0x1800570a8  mov     esi, r14d
0x1800570ab  movzx   r14d, ax
0x1800570af  shr     r14d, 0Fh
0x1800570b3  shr     esi, 0Fh
0x1800570b6  cmp     edi, 20h ; ' '
0x1800570b9  jz      loc_1800571F5
0x1800570bf  cmp     edi, 6Bh ; 'k'
0x1800570c2  jnz     short loc_180057128
0x1800570c4  mov     eax, [rbx+10h]
0x1800570c7  and     al, 3
0x1800570c9  cmp     al, r12b
0x1800570cc  jnz     short loc_180057128
0x1800570ce  lea     ecx, [rdi-5Ah]; nVirtKey
0x1800570d1  call    cs:__imp_GetKeyState
0x1800570d7  test    ax, ax
0x1800570da  jns     short loc_180057128
0x1800570dc  mov     edx, 7F02h; lpCursorName
0x1800570e1  xor     ecx, ecx; hInstance
0x1800570e3  call    cs:__imp_LoadCursorW
0x1800570e9  mov     rcx, rax; hCursor
0x1800570ec  call    cs:__imp_SetCursor
0x1800570f2  mov     edi, r15d
0x1800570f5  mov     rsi, rax
0x1800570f8  cmp     [rbx+1ACh], r15d
0x1800570ff  jle     short loc_18005711A
0x180057101  or      r8d, 0FFFFFFFFh
0x180057105  mov     edx, edi
0x180057107  mov     rcx, rbx
0x18005710a  call    ListView_RSetColumnWidth
0x18005710f  add     edi, r12d
0x180057112  cmp     edi, [rbx+1ACh]
0x180057118  jl      short loc_180057101
0x18005711a  mov     rcx, rsi; hCursor
0x18005711d  call    cs:__imp_SetCursor
0x180057123  jmp     loc_1800572AF
0x180057128  mov     ecx, 12h; nVirtKey
0x18005712d  call    cs:__imp_GetKeyState
0x180057133  test    ax, ax
0x180057136  js      loc_1800572BA
0x18005713c  test    byte ptr [rbx+10h], 4
0x180057140  jz      short loc_180057148
0x180057142  mov     esi, r15d
0x180057145  mov     r14d, r15d
0x180057148  mov     edx, [rbx+90h]
0x18005714e  mov     r8d, edi
0x180057151  mov     rcx, rbx
0x180057154  call    ListView_Arrow
0x180057159  mov     edi, eax
0x18005715b  cmp     eax, 0FFFFFFFFh
0x18005715e  jz      short loc_1800571BB
0x180057160  test    r14d, r14d
0x180057163  jz      short loc_18005717A
0x180057165  mov     r8d, r12d
0x180057168  mov     edx, eax; int
0x18005716a  mov     rcx, rbx; int
0x18005716d  call    ListView_SelectRangeTo
0x180057172  mov     r9d, r15d
0x180057175  mov     esi, r15d
0x180057178  jmp     short loc_18005718F
0x18005717a  test    esi, esi
0x18005717c  jnz     short loc_180057189
0x18005717e  mov     [rbx+94h], edi
0x180057184  mov     r9d, r12d
0x180057187  jmp     short loc_18005718C
0x180057189  mov     r9d, r15d
0x18005718c  xor     esi, r12d
0x18005718f  mov     r8d, esi
0x180057192  mov     [rsp+0C0h+wRemoveMsg], r15d
0x180057197  mov     edx, edi
0x180057199  mov     rcx, rbx
0x18005719c  call    ListView_SetFocusSel
0x1800571a1  lea     rcx, c_szSelect; "CCSelect"
0x1800571a8  mov     [rbx+28Ch], r15d
0x1800571af  mov     [rbx+278h], r15d
0x1800571b6  call    CCPlaySound
0x1800571bb  mov     edx, 200h
0x1800571c0  mov     r8d, 2Bh ; '+'
0x1800571c6  mov     rcx, rbx
0x1800571c9  call    ListView_CancelPendingTimer
0x1800571ce  test    eax, eax
0x1800571d0  jz      loc_1800572AF
0x1800571d6  mov     edx, [rbx+90h]; int
0x1800571dc  xor     r8d, r8d
0x1800571df  mov     rcx, rbx; int
0x1800571e2  call    ListView_OnEnsureVisible
0x1800571e7  mov     rcx, [rbx]; hWnd
0x1800571ea  call    cs:__imp_UpdateWindow
0x1800571f0  jmp     loc_1800572AF
0x1800571f5  test    esi, esi
0x1800571f7  jz      short loc_180057214
0x1800571f9  mov     edx, [rbx+90h]
0x1800571ff  mov     rcx, rbx
0x180057202  mov     [rbx+94h], edx
0x180057208  call    ListView_ToggleSelection
0x18005720d  add     [rbx+0C0h], r12d
0x180057214  test    r14d, r14d
0x180057217  jz      short loc_18005722A
0x180057219  mov     edx, [rbx+90h]; int
0x18005721f  mov     r8d, r12d
0x180057222  mov     rcx, rbx; int
0x180057225  call    ListView_SelectRangeTo
0x18005722a  test    byte ptr [rbx+4Ch], 4
0x18005722e  jz      short loc_1800572AF
0x180057230  mov     edx, [rbx+90h]
0x180057236  cmp     edx, 0FFFFFFFFh
0x180057239  jz      short loc_1800572AF
0x18005723b  mov     rcx, rbx
0x18005723e  call    ListView_HandleStateIconClick
0x180057243  jmp     short loc_1800572AF
0x180057245  xor     r8d, r8d
0x180057248  mov     rcx, rbx
0x18005724b  lea     edx, [r8-4]
0x18005724f  call    CCSendNotify
0x180057254  mov     rcx, rsi; hWnd
0x180057257  call    cs:__imp_IsWindow
0x18005725d  test    eax, eax
0x18005725f  jz      short loc_1800572BA
0x180057261  xor     edx, edx; Val
0x180057263  lea     rcx, [rbp+4Fh+Msg]; void *
0x180057267  lea     r8d, [rdx+48h]; Size
0x18005726b  call    memset
0x180057270  mov     eax, [rbx+90h]
0x180057276  mov     dword ptr [rbp+4Fh+Msg.lParam], eax
0x180057279  mov     dword ptr [rbp+4Fh+Msg.lParam+4], r15d
0x18005727d  mov     [rbp+4Fh+Msg.pt.y], r15d
0x180057281  mov     qword ptr [rbp+4Fh+Msg+2Ch], 0FFFFFFFFFFFFFFFFh
0x180057289  call    GetLVKeyFlags
0x18005728e  lea     r8, [rbp+4Fh+Msg]
0x180057292  mov     [rbp+4Fh+var_30], eax
0x180057295  mov     edx, 0FFFFFF8Eh
0x18005729a  mov     rcx, rbx
0x18005729d  call    CCSendNotify
0x1800572a2  mov     rcx, rsi; hWnd
0x1800572a5  call    cs:__imp_IsWindow
0x1800572ab  test    eax, eax
0x1800572ad  jz      short loc_1800572BA
0x1800572af  mov     edx, r12d
0x1800572b2  mov     rcx, rbx
0x1800572b5  call    CCNotifyNavigationKeyUsage
0x1800572ba  lea     r11, [rsp+0C0h+var_20]
0x1800572c2  mov     rbx, [r11+30h]
0x1800572c6  mov     rsi, [r11+38h]
0x1800572ca  mov     rsp, r11
0x1800572cd  pop     r15
0x1800572cf  pop     r14
0x1800572d1  pop     r12
0x1800572d3  pop     rdi
0x1800572d4  pop     rbp
0x1800572d5  retn
```
