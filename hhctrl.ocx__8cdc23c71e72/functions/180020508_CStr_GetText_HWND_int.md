# CStr::GetText(HWND__ *,int)

- ea: `0x180020508`
- end: `0x18002071d`
- name: `?GetText@CStr@@QEAAHPEAUHWND__@@H@Z`
- size: `533`
- prototype: `int(CStr *__hidden this, HWND, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001a4d0`
- `0x18001b480`

## callees

- `0x180006708`
- `0x180013b20`
- `0x180020508`
- `0x18006a7ac`
- `0x180075c90`

## import_xrefs

- `msvcrt!_msize` at `0x1800206e5`
- `msvcrt!_msize` at `0x1800206e5`
- `msvcrt!free` at `0x180020537`
- `msvcrt!free` at `0x180020537`
- `KERNEL32!lstrcmpiA` at `0x180020574`
- `KERNEL32!lstrcmpiA` at `0x1800205bc`
- `KERNEL32!lstrcmpiA` at `0x180020663`
- `KERNEL32!lstrcmpiA` at `0x180020574`
- `KERNEL32!lstrcmpiA` at `0x1800205bc`
- `KERNEL32!lstrcmpiA` at `0x180020663`
- `USER32!GetWindowTextA` at `0x1800206f4`
- `USER32!GetWindowTextA` at `0x1800206f4`
- `USER32!GetWindowTextLengthA` at `0x1800206c6`
- `USER32!GetWindowTextLengthA` at `0x1800206c6`
- `USER32!GetClassNameA` at `0x180020562`
- `USER32!GetClassNameA` at `0x1800205aa`
- `USER32!GetClassNameA` at `0x180020562`
- `USER32!GetClassNameA` at `0x1800205aa`
- `USER32!SendMessageA` at `0x1800205dd`
- `USER32!SendMessageA` at `0x180020602`
- `USER32!SendMessageA` at `0x180020618`
- `USER32!SendMessageA` at `0x18002063e`
- `USER32!SendMessageA` at `0x18002067e`
- `USER32!SendMessageA` at `0x1800205dd`
- `USER32!SendMessageA` at `0x180020602`
- `USER32!SendMessageA` at `0x180020618`
- `USER32!SendMessageA` at `0x18002063e`
- `USER32!SendMessageA` at `0x18002067e`
- `USER32!GetDlgItem` at `0x180020583`
- `USER32!GetDlgItem` at `0x180020583`

## string_xrefs

- `0x180020657`: `ComboBox`

## pseudocode

```c
int __fastcall CStr::GetText(LPSTR *this, HWND DlgItem)
{
  LPSTR v4; // rcx
  int v5; // esi
  int v6; // eax
  CHAR *v7; // rax
  WPARAM v8; // r8
  UINT v9; // edx
  WPARAM v11; // rbp
  int v12; // eax
  int v13; // esi
  CHAR *v14; // rax
  int WindowTextLengthA; // eax
  CHAR *v16; // rax
  int v17; // eax
  CHAR ClassName[272]; // [rsp+20h] [rbp-138h] BYREF

  v4 = *this;
  if ( v4 )
    free(v4);
  if ( !(unsigned int)IsValidWindow(DlgItem) )
    goto LABEL_17;
  v5 = 111;
  GetClassNameA(DlgItem, ClassName, 260);
  if ( lstrcmpiA(ClassName, "#32770") )
    goto LABEL_7;
  DlgItem = GetDlgItem(DlgItem, 111);
  if ( !(unsigned int)IsValidWindow(DlgItem) )
  {
LABEL_17:
    v14 = (CHAR *)lcCalloc(1);
    *this = v14;
    if ( !v14 )
      goto LABEL_23;
    return 0;
  }
  v5 = -1;
  GetClassNameA(DlgItem, ClassName, 260);
LABEL_7:
  if ( !lstrcmpiA(ClassName, "ListBox") )
  {
    if ( v5 != -1 || (v5 = SendMessageA(DlgItem, 0x188u, 0, 0), v5 != -1) )
    {
      if ( (unsigned int)SendMessageA(DlgItem, 0x18Au, v5, 0) != -1 )
      {
        v6 = SendMessageA(DlgItem, 0x18Au, v5, 0);
        v7 = (CHAR *)lcCalloc(v6 + 1);
        *this = v7;
        if ( v7 )
        {
          v8 = v5;
          v9 = 393;
          return SendMessageA(DlgItem, v9, v8, (LPARAM)v7) != 0;
        }
        goto LABEL_23;
      }
    }
    goto LABEL_17;
  }
  if ( v5 >= 0 && !lstrcmpiA(ClassName, "ComboBox") )
  {
    v11 = v5;
    v12 = SendMessageA(DlgItem, 0x149u, v5, 0);
    v13 = v12;
    if ( v12 != -1 )
    {
      v7 = (CHAR *)lcCalloc(v12 + 1);
      *this = v7;
      if ( v13 < 0 || v7 )
      {
        v8 = v11;
        v9 = 328;
        return SendMessageA(DlgItem, v9, v8, (LPARAM)v7) != 0;
      }
LABEL_23:
      OOM();
    }
    goto LABEL_17;
  }
  WindowTextLengthA = GetWindowTextLengthA(DlgItem);
  v16 = (CHAR *)lcCalloc(WindowTextLengthA + 1);
  *this = v16;
  if ( !v16 )
    goto LABEL_23;
  v17 = _msize(v16);
  return GetWindowTextA(DlgItem, *this, v17);
}

```

## disassembly

```asm
0x180020508  mov     [rsp+arg_10], rbx
0x18002050d  push    rbp
0x18002050e  push    rsi
0x18002050f  push    rdi
0x180020510  sub     rsp, 140h
0x180020517  mov     rax, cs:__security_cookie
0x18002051e  xor     rax, rsp
0x180020521  mov     [rsp+158h+var_28], rax
0x180020529  mov     rdi, rcx
0x18002052c  mov     rbx, rdx
0x18002052f  mov     rcx, [rcx]; Block
0x180020532  test    rcx, rcx
0x180020535  jz      short loc_18002053D
0x180020537  call    cs:__imp_free
0x18002053d  mov     rcx, rbx; HWND
0x180020540  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x180020545  test    eax, eax
0x180020547  jz      loc_18002068C
0x18002054d  mov     ebp, 104h
0x180020552  lea     rdx, [rsp+158h+ClassName]; lpClassName
0x180020557  mov     r8d, ebp; nMaxCount
0x18002055a  mov     rcx, rbx; hWnd
0x18002055d  mov     esi, 6Fh ; 'o'
0x180020562  call    cs:__imp_GetClassNameA
0x180020568  lea     rdx, a32770; "#32770"
0x18002056f  lea     rcx, [rsp+158h+ClassName]; lpString1
0x180020574  call    cs:__imp_lstrcmpiA
0x18002057a  test    eax, eax
0x18002057c  jnz     short loc_1800205B0
0x18002057e  mov     edx, esi; nIDDlgItem
0x180020580  mov     rcx, rbx; hDlg
0x180020583  call    cs:__imp_GetDlgItem
0x180020589  mov     rcx, rax; HWND
0x18002058c  mov     rbx, rax
0x18002058f  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x180020594  test    eax, eax
0x180020596  jz      loc_18002068C
0x18002059c  or      esi, 0FFFFFFFFh
0x18002059f  lea     rdx, [rsp+158h+ClassName]; lpClassName
0x1800205a4  mov     r8d, ebp; nMaxCount
0x1800205a7  mov     rcx, rbx; hWnd
0x1800205aa  call    cs:__imp_GetClassNameA
0x1800205b0  lea     rdx, aListbox; "ListBox"
0x1800205b7  lea     rcx, [rsp+158h+ClassName]; lpString1
0x1800205bc  call    cs:__imp_lstrcmpiA
0x1800205c2  test    eax, eax
0x1800205c4  jnz     loc_180020653
0x1800205ca  cmp     esi, 0FFFFFFFFh
0x1800205cd  jnz     short loc_1800205EF
0x1800205cf  xor     r9d, r9d; lParam
0x1800205d2  xor     r8d, r8d; wParam
0x1800205d5  mov     edx, 188h; Msg
0x1800205da  mov     rcx, rbx; hWnd
0x1800205dd  call    cs:__imp_SendMessageA
0x1800205e3  mov     rsi, rax
0x1800205e6  cmp     eax, 0FFFFFFFFh
0x1800205e9  jz      loc_18002068C
0x1800205ef  movsxd  rsi, esi
0x1800205f2  mov     ebp, 18Ah
0x1800205f7  mov     r8, rsi; wParam
0x1800205fa  mov     edx, ebp; Msg
0x1800205fc  xor     r9d, r9d; lParam
0x1800205ff  mov     rcx, rbx; hWnd
0x180020602  call    cs:__imp_SendMessageA
0x180020608  cmp     eax, 0FFFFFFFFh
0x18002060b  jz      short loc_18002068C
0x18002060d  xor     r9d, r9d; lParam
0x180020610  mov     r8, rsi; wParam
0x180020613  mov     edx, ebp; Msg
0x180020615  mov     rcx, rbx; hWnd
0x180020618  call    cs:__imp_SendMessageA
0x18002061e  lea     ecx, [rax+1]; int
0x180020621  call    ?lcCalloc@@YAPEAXH@Z; lcCalloc(int)
0x180020626  mov     [rdi], rax
0x180020629  test    rax, rax
0x18002062c  jz      loc_1800206DC
0x180020632  mov     r8, rsi; wParam
0x180020635  lea     edx, [rbp-1]; Msg
0x180020638  mov     r9, rax; lParam
0x18002063b  mov     rcx, rbx; hWnd
0x18002063e  call    cs:__imp_SendMessageA
0x180020644  xor     ecx, ecx
0x180020646  test    rax, rax
0x180020649  setnz   cl
0x18002064c  mov     eax, ecx
0x18002064e  jmp     loc_1800206FA
0x180020653  test    esi, esi
0x180020655  js      short loc_1800206C3
0x180020657  lea     rdx, aCombobox; "ComboBox"
0x18002065e  lea     rcx, [rsp+158h+ClassName]; lpString1
0x180020663  call    cs:__imp_lstrcmpiA
0x180020669  test    eax, eax
0x18002066b  jnz     short loc_1800206C3
0x18002066d  movsxd  rbp, esi
0x180020670  xor     r9d, r9d; lParam
0x180020673  mov     r8, rbp; wParam
0x180020676  mov     edx, 149h; Msg
0x18002067b  mov     rcx, rbx; hWnd
0x18002067e  call    cs:__imp_SendMessageA
0x180020684  mov     rsi, rax
0x180020687  cmp     eax, 0FFFFFFFFh
0x18002068a  jnz     short loc_1800206A2
0x18002068c  mov     ecx, 1; int
0x180020691  call    ?lcCalloc@@YAPEAXH@Z; lcCalloc(int)
0x180020696  mov     [rdi], rax
0x180020699  test    rax, rax
0x18002069c  jz      short loc_1800206DC
0x18002069e  xor     eax, eax
0x1800206a0  jmp     short loc_1800206FA
0x1800206a2  lea     ecx, [rax+1]; int
0x1800206a5  call    ?lcCalloc@@YAPEAXH@Z; lcCalloc(int)
0x1800206aa  mov     [rdi], rax
0x1800206ad  test    esi, esi
0x1800206af  js      short loc_1800206B6
0x1800206b1  test    rax, rax
0x1800206b4  jz      short loc_1800206DC
0x1800206b6  mov     r8, rbp
0x1800206b9  mov     edx, 148h
0x1800206be  jmp     loc_180020638
0x1800206c3  mov     rcx, rbx; hWnd
0x1800206c6  call    cs:__imp_GetWindowTextLengthA
0x1800206cc  lea     ecx, [rax+1]; int
0x1800206cf  call    ?lcCalloc@@YAPEAXH@Z; lcCalloc(int)
0x1800206d4  mov     [rdi], rax
0x1800206d7  test    rax, rax
0x1800206da  jnz     short loc_1800206E2
0x1800206dc  call    ?OOM@@YAXXZ; OOM(void)
0x1800206e2  mov     rcx, rax; Block
0x1800206e5  call    cs:__imp__msize
0x1800206eb  mov     rdx, [rdi]; lpString
0x1800206ee  mov     rcx, rbx; hWnd
0x1800206f1  mov     r8d, eax; nMaxCount
0x1800206f4  call    cs:__imp_GetWindowTextA
0x1800206fa  mov     rcx, [rsp+158h+var_28]
0x180020702  xor     rcx, rsp; StackCookie
0x180020705  call    __security_check_cookie
0x18002070a  mov     rbx, [rsp+158h+arg_10]
0x180020712  add     rsp, 140h
0x180020719  pop     rdi
0x18002071a  pop     rsi
0x18002071b  pop     rbp
0x18002071c  retn
```
