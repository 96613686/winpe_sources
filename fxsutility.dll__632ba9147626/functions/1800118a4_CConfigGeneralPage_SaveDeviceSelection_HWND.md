# CConfigGeneralPage::SaveDeviceSelection(HWND__ *)

- ea: `0x1800118a4`
- end: `0x180011b25`
- name: `?SaveDeviceSelection@CConfigGeneralPage@@AEAAKPEAUHWND__@@@Z`
- size: `641`
- prototype: `unsigned int(CConfigGeneralPage *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800122c0`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x180006270`
- `0x180006318`
- `0x180006db4`
- `0x180006e84`
- `0x1800118a4`
- `0x1800159c0`

## import_xrefs

- `FXSAPI!FaxSetPortExW` at `0x180011977`
- `FXSAPI!FaxSetPortExW` at `0x180011a86`
- `FXSAPI!FaxSetPortExW` at `0x180011977`
- `FXSAPI!FaxSetPortExW` at `0x180011a86`
- `KERNEL32!GetLastError` at `0x180011981`
- `KERNEL32!GetLastError` at `0x180011a90`
- `KERNEL32!GetLastError` at `0x180011981`
- `KERNEL32!GetLastError` at `0x180011a90`
- `USER32!GetWindowTextLengthW` at `0x180011907`
- `USER32!GetWindowTextLengthW` at `0x180011907`
- `USER32!GetDlgItem` at `0x1800118c1`
- `USER32!GetDlgItem` at `0x1800118c1`
- `USER32!GetWindowTextW` at `0x180011935`
- `USER32!GetWindowTextW` at `0x180011935`

## pseudocode

```c
__int64 __fastcall CConfigGeneralPage::SaveDeviceSelection(CConfigGeneralPage *this, HWND a2)
{
  HWND DlgItem; // r14
  unsigned int v4; // ebp
  WCHAR *v5; // rax
  unsigned __int16 *v6; // rsi
  DWORD LastError; // ebx
  unsigned __int16 *v9; // rax
  int v10; // edx
  int v11; // ecx
  int v12; // ebp
  int v13; // r14d
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  bool v18; // zf
  __int64 v19; // r9
  __int64 v20; // rcx
  unsigned __int16 *v21; // rax
  int v22; // edx
  int v23; // r8d
  int v24; // eax
  void *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8

  DlgItem = GetDlgItem(a2, 4581);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  v4 = GetWindowTextLengthW(DlgItem) + 1;
  v5 = (WCHAR *)pMemAlloc(2LL * v4);
  v6 = v5;
  if ( !v5 )
    return 8;
  LastError = 0;
  GetWindowTextW(DlgItem, v5, v4);
  v9 = v6;
  do
  {
    v10 = *(unsigned __int16 *)((char *)v9 + *((_QWORD *)this + 7) - (_QWORD)v6);
    v11 = *v9 - v10;
    if ( v11 )
      break;
    ++v9;
  }
  while ( v10 );
  if ( v11 )
  {
    v12 = *((_DWORD *)this + 22);
    v13 = *((_DWORD *)this + 23);
    v14 = *((unsigned int *)this + 13);
    v15 = *((_QWORD *)this + 15);
    *((_QWORD *)this + 11) = 0;
    if ( !(unsigned int)FaxSetPortExW(v15, v14, (char *)this + 48) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_44;
        }
        v17 = 31;
        goto LABEL_17;
      }
    }
    v18 = *((_DWORD *)this + 10) == 0;
    *((_DWORD *)this + 22) = v12;
    *((_DWORD *)this + 23) = v13;
    if ( v18 )
    {
LABEL_25:
      v24 = 0;
    }
    else
    {
      v19 = *((_QWORD *)this + 4);
      v20 = 0;
      while ( 1 )
      {
        v21 = v6;
        do
        {
          v22 = *(unsigned __int16 *)((char *)v21 + *(_QWORD *)(v19 + 72 * v20 + 8) - (_QWORD)v6);
          v23 = *v21 - v22;
          if ( v23 )
            break;
          ++v21;
        }
        while ( v22 );
        if ( !v23 )
          break;
        v20 = (unsigned int)(v20 + 1);
        if ( (unsigned int)v20 >= *((_DWORD *)this + 10) )
          goto LABEL_25;
      }
      v24 = *(_DWORD *)(v19 + 72 * v20 + 4);
    }
    v25 = (void *)*((_QWORD *)this + 7);
    *((_DWORD *)this + 13) = v24;
    pMemFree(v25);
    v26 = StringDup(v6);
    *((_QWORD *)this + 7) = v26;
    if ( !v26 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, v28, v6);
      }
      goto LABEL_44;
    }
    if ( (unsigned int)FaxSetPortExW(*((_QWORD *)this + 15), *((unsigned int *)this + 13), (char *)this + 48)
      || (LastError = GetLastError()) == 0 )
    {
      LastError = SetDeviceToMonitor(*((unsigned int *)this + 13));
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_f5b496eade1b3798203481970613ce29_Traceguids, LastError);
        }
        LastError = 0;
      }
      goto LABEL_44;
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 33;
LABEL_17:
      WPP_SF_d(v16[2], v17, &WPP_f5b496eade1b3798203481970613ce29_Traceguids, LastError);
    }
  }
LABEL_44:
  pMemFree(v6);
  return LastError;
}

```

## disassembly

```asm
0x1800118a4  push    rbx
0x1800118a6  push    rbp
0x1800118a7  push    rsi
0x1800118a8  push    rdi
0x1800118a9  push    r13
0x1800118ab  push    r14
0x1800118ad  push    r15
0x1800118af  sub     rsp, 20h
0x1800118b3  mov     rax, rdx
0x1800118b6  mov     rdi, rcx
0x1800118b9  mov     rcx, rax; hDlg
0x1800118bc  mov     edx, 11E5h; nIDDlgItem
0x1800118c1  call    cs:__imp_GetDlgItem
0x1800118c7  mov     r14, rax
0x1800118ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118d1  lea     rax, WPP_GLOBAL_Control
0x1800118d8  mov     r13d, 100h
0x1800118de  cmp     rcx, rax
0x1800118e1  jz      short loc_180011904
0x1800118e3  test    [rcx+1Ch], r13d
0x1800118e7  jz      short loc_180011904
0x1800118e9  cmp     byte ptr [rcx+19h], 5
0x1800118ed  jb      short loc_180011904
0x1800118ef  mov     rcx, [rcx+10h]
0x1800118f3  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x1800118fa  mov     edx, 1Eh
0x1800118ff  call    WPP_SF_
0x180011904  mov     rcx, r14; hWnd
0x180011907  call    cs:__imp_GetWindowTextLengthW
0x18001190d  lea     ebp, [rax+1]
0x180011910  mov     ecx, ebp
0x180011912  add     rcx, rcx; dwBytes
0x180011915  call    pMemAlloc
0x18001191a  mov     rsi, rax
0x18001191d  test    rax, rax
0x180011920  jnz     short loc_18001192A
0x180011922  lea     eax, [rsi+8]
0x180011925  jmp     loc_180011B16
0x18001192a  mov     r8d, ebp; nMaxCount
0x18001192d  mov     rdx, rsi; lpString
0x180011930  mov     rcx, r14; hWnd
0x180011933  xor     ebx, ebx
0x180011935  call    cs:__imp_GetWindowTextW
0x18001193b  mov     r8, [rdi+38h]
0x18001193f  mov     rax, rsi
0x180011942  sub     r8, rsi
0x180011945  movzx   ecx, word ptr [rax]
0x180011948  movzx   edx, word ptr [rax+r8]
0x18001194d  sub     ecx, edx
0x18001194f  jnz     short loc_180011959
0x180011951  add     rax, 2
0x180011955  test    edx, edx
0x180011957  jnz     short loc_180011945
0x180011959  test    ecx, ecx
0x18001195b  jz      loc_180011B0C
0x180011961  mov     ebp, [rdi+58h]
0x180011964  lea     r8, [rdi+30h]
0x180011968  mov     r14d, [rdi+5Ch]
0x18001196c  mov     edx, [rdi+34h]
0x18001196f  mov     rcx, [rdi+78h]
0x180011973  mov     [rdi+58h], rbx
0x180011977  call    cs:__imp_FaxSetPortExW
0x18001197d  test    eax, eax
0x18001197f  jnz     short loc_1800119D5
0x180011981  call    cs:__imp_GetLastError
0x180011987  mov     ebx, eax
0x180011989  test    eax, eax
0x18001198b  jz      short loc_1800119D5
0x18001198d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011994  lea     rax, WPP_GLOBAL_Control
0x18001199b  cmp     rcx, rax
0x18001199e  jz      loc_180011B0C
0x1800119a4  test    [rcx+1Ch], r13d
0x1800119a8  jz      loc_180011B0C
0x1800119ae  cmp     byte ptr [rcx+19h], 2
0x1800119b2  jb      loc_180011B0C
0x1800119b8  mov     edx, 1Fh
0x1800119bd  mov     rcx, [rcx+10h]
0x1800119c1  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x1800119c8  mov     r9d, ebx
0x1800119cb  call    WPP_SF_d
0x1800119d0  jmp     loc_180011B0C
0x1800119d5  cmp     dword ptr [rdi+28h], 0
0x1800119d9  mov     [rdi+58h], ebp
0x1800119dc  mov     [rdi+5Ch], r14d
0x1800119e0  jbe     short loc_180011A19
0x1800119e2  mov     r9, [rdi+20h]
0x1800119e6  xor     ecx, ecx
0x1800119e8  lea     r11, [rcx+rcx*8]
0x1800119ec  mov     rax, rsi
0x1800119ef  mov     r10, [r9+r11*8+8]
0x1800119f4  sub     r10, rsi
0x1800119f7  movzx   r8d, word ptr [rax]
0x1800119fb  movzx   edx, word ptr [rax+r10]
0x180011a00  sub     r8d, edx
0x180011a03  jnz     short loc_180011A0D
0x180011a05  add     rax, 2
0x180011a09  test    edx, edx
0x180011a0b  jnz     short loc_1800119F7
0x180011a0d  test    r8d, r8d
0x180011a10  jz      short loc_180011A74
0x180011a12  inc     ecx
0x180011a14  cmp     ecx, [rdi+28h]
0x180011a17  jb      short loc_1800119E8
0x180011a19  xor     eax, eax
0x180011a1b  mov     rcx, [rdi+38h]; lpMem
0x180011a1f  mov     [rdi+34h], eax
0x180011a22  call    pMemFree
0x180011a27  mov     rcx, rsi; unsigned __int16 *
0x180011a2a  call    StringDup
0x180011a2f  mov     [rdi+38h], rax
0x180011a33  test    rax, rax
0x180011a36  jnz     short loc_180011A7B
0x180011a38  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a3f  lea     rax, WPP_GLOBAL_Control
0x180011a46  cmp     rcx, rax
0x180011a49  jz      loc_180011B0C
0x180011a4f  test    [rcx+1Ch], r13d
0x180011a53  jz      loc_180011B0C
0x180011a59  cmp     byte ptr [rcx+19h], 2
0x180011a5d  jb      loc_180011B0C
0x180011a63  mov     rcx, [rcx+10h]
0x180011a67  mov     r9, rsi
0x180011a6a  call    WPP_SF_S
0x180011a6f  jmp     loc_180011B0C
0x180011a74  mov     eax, [r9+r11*8+4]
0x180011a79  jmp     short loc_180011A1B
0x180011a7b  mov     edx, [rdi+34h]
0x180011a7e  lea     r8, [rdi+30h]
0x180011a82  mov     rcx, [rdi+78h]
0x180011a86  call    cs:__imp_FaxSetPortExW
0x180011a8c  test    eax, eax
0x180011a8e  jnz     short loc_180011AC5
0x180011a90  call    cs:__imp_GetLastError
0x180011a96  mov     ebx, eax
0x180011a98  test    eax, eax
0x180011a9a  jz      short loc_180011AC5
0x180011a9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011aa3  lea     rax, WPP_GLOBAL_Control
0x180011aaa  cmp     rcx, rax
0x180011aad  jz      short loc_180011B0C
0x180011aaf  test    [rcx+1Ch], r13d
0x180011ab3  jz      short loc_180011B0C
0x180011ab5  cmp     byte ptr [rcx+19h], 2
0x180011ab9  jb      short loc_180011B0C
0x180011abb  mov     edx, 21h ; '!'
0x180011ac0  jmp     loc_1800119BD
0x180011ac5  mov     ecx, [rdi+34h]
0x180011ac8  call    SetDeviceToMonitor
0x180011acd  mov     ebx, eax
0x180011acf  test    eax, eax
0x180011ad1  jz      short loc_180011B0C
0x180011ad3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ada  lea     rax, WPP_GLOBAL_Control
0x180011ae1  cmp     rcx, rax
0x180011ae4  jz      short loc_180011B0A
0x180011ae6  test    [rcx+1Ch], r13d
0x180011aea  jz      short loc_180011B0A
0x180011aec  cmp     byte ptr [rcx+19h], 3
0x180011af0  jb      short loc_180011B0A
0x180011af2  mov     rcx, [rcx+10h]
0x180011af6  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180011afd  mov     edx, 22h ; '"'
0x180011b02  mov     r9d, ebx
0x180011b05  call    WPP_SF_d
0x180011b0a  xor     ebx, ebx
0x180011b0c  mov     rcx, rsi; lpMem
0x180011b0f  call    pMemFree
0x180011b14  mov     eax, ebx
0x180011b16  add     rsp, 20h
0x180011b1a  pop     r15
0x180011b1c  pop     r14
0x180011b1e  pop     r13
0x180011b20  pop     rdi
0x180011b21  pop     rsi
0x180011b22  pop     rbp
0x180011b23  pop     rbx
0x180011b24  retn
```
