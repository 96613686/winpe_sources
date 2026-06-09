# UserPropSheet::UpdateUserName(HWND__ *,IDiskQuotaUser *)

- ea: `0x1800184c0`
- end: `0x180018678`
- name: `?UpdateUserName@UserPropSheet@@AEAAXPEAUHWND__@@PEAUIDiskQuotaUser@@@Z`
- size: `440`
- prototype: `void(UserPropSheet *__hidden this, HWND, struct IDiskQuotaUser *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1800177fc`

## callees

- `0x180001510`
- `0x1800184c0`
- `0x180019d24`
- `0x180019dd0`
- `0x180019ee0`
- `0x180019fb0`
- `0x18001a468`
- `0x18001f010`

## import_xrefs

- `USER32!GetParent` at `0x180018625`
- `USER32!GetParent` at `0x180018625`
- `USER32!SendMessageW` at `0x180018639`
- `USER32!SendMessageW` at `0x180018639`
- `USER32!SetDlgItemTextW` at `0x1800185fa`
- `USER32!SetDlgItemTextW` at `0x1800185fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UserPropSheet::UpdateUserName(UserPropSheet *this, HWND a2, struct IDiskQuotaUser *a3)
{
  unsigned int v5; // r8d
  LPCWSTR *v6; // rbx
  LPARAM v7; // rbx
  HWND Parent; // rax
  int v9; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v10[8]; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR *v11; // [rsp+50h] [rbp-B0h]
  _BYTE v12[8]; // [rsp+58h] [rbp-A8h] BYREF
  LPARAM *v13; // [rsp+60h] [rbp-A0h]
  _WORD v14[264]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v15[264]; // [rsp+280h] [rbp+180h] BYREF

  CString::CString((CString *)v10);
  v9 = 0;
  ((void (__fastcall *)(struct IDiskQuotaUser *, int *))a3->lpVtbl[1].GetSidLength)(a3, &v9);
  if ( v9 )
  {
    v5 = 40559;
    switch ( v9 )
    {
      case 1:
        v5 = 40557;
        break;
      case 2:
        CString::Format((CString *)v10, g_hInstDll, 0x9E71u);
        goto LABEL_15;
      case 3:
        CString::Format((CString *)v10, g_hInstDll, 0x9E70u);
        goto LABEL_15;
      case 5:
        CString::Format((CString *)v10, g_hInstDll, 0x9E6Eu);
        goto LABEL_15;
    }
    CString::Format((CString *)v10, g_hInstDll, v5);
    goto LABEL_15;
  }
  ((void (__fastcall *)(struct IDiskQuotaUser *, _QWORD, _QWORD, _WORD *, int, _WORD *, int))a3->lpVtbl->GetQuotaThreshold)(
    a3,
    0,
    0,
    v14,
    260,
    v15,
    260);
  if ( v14[0] )
  {
    if ( v15[0] )
      CString::Format((CString *)v10, g_hInstDll, 0x9EB5u, v15, v14);
    else
      CString::operator=(v10, v14);
  }
LABEL_15:
  v6 = v11;
  SetDlgItemTextW(a2, 1020, *v11);
  CString::CString((CString *)v12, g_hInstDll, 40548, *v6);
  v7 = *v13;
  Parent = GetParent(a2);
  SendMessageW(Parent, 0x478u, 0, v7);
  CString::~CString((CString *)v12);
  CString::~CString((CString *)v10);
}

```

## disassembly

```asm
0x1800184c0  mov     [rsp-8+arg_0], rbx
0x1800184c5  mov     [rsp-8+arg_18], rdi
0x1800184ca  push    rbp
0x1800184cb  lea     rbp, [rsp-3A0h]
0x1800184d3  sub     rsp, 4A0h
0x1800184da  mov     rax, cs:__security_cookie
0x1800184e1  xor     rax, rsp
0x1800184e4  mov     [rbp+3A0h+var_10], rax
0x1800184eb  mov     rbx, r8
0x1800184ee  mov     rdi, rdx
0x1800184f1  lea     rcx, [rsp+4A0h+var_458]; this
0x1800184f6  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x1800184fb  nop
0x1800184fc  mov     [rsp+4A0h+var_460], 0
0x180018504  mov     rax, [rbx]
0x180018507  lea     rdx, [rsp+4A0h+var_460]
0x18001850c  mov     rcx, rbx
0x18001850f  mov     rax, [rax+88h]
0x180018516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001851b  mov     eax, [rsp+4A0h+var_460]
0x18001851f  test    eax, eax
0x180018521  jnz     short loc_1800185A1
0x180018523  mov     rax, [rbx]
0x180018526  mov     edx, 104h
0x18001852b  mov     [rsp+4A0h+var_470], edx
0x18001852f  lea     rcx, [rbp+3A0h+var_220]
0x180018536  mov     [rsp+4A0h+var_478], rcx
0x18001853b  mov     dword ptr [rsp+4A0h+var_480], edx
0x18001853f  lea     r9, [rsp+4A0h+var_430]
0x180018544  xor     r8d, r8d
0x180018547  xor     edx, edx
0x180018549  mov     rcx, rbx
0x18001854c  mov     rax, [rax+20h]
0x180018550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018555  xor     eax, eax
0x180018557  cmp     ax, [rsp+4A0h+var_430]
0x18001855c  jz      loc_1800185EA
0x180018562  lea     rcx, [rsp+4A0h+var_458]; this
0x180018567  cmp     ax, [rbp+3A0h+var_220]
0x18001856e  jz      short loc_180018595
0x180018570  lea     rax, [rsp+4A0h+var_430]
0x180018575  mov     [rsp+4A0h+var_480], rax
0x18001857a  lea     r9, [rbp+3A0h+var_220]
0x180018581  mov     r8d, 9EB5h; unsigned int
0x180018587  mov     rdx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x18001858e  call    ?Format@CString@@QEAAHPEAUHINSTANCE__@@IZZ; CString::Format(HINSTANCE__ *,uint,...)
0x180018593  jmp     short loc_1800185EA
0x180018595  lea     rdx, [rsp+4A0h+var_430]
0x18001859a  call    ??4CString@@QEAAAEAV0@PEBG@Z; CString::operator=(ushort const *)
0x18001859f  jmp     short loc_1800185EA
0x1800185a1  mov     r8d, 9E6Fh
0x1800185a7  sub     eax, 1
0x1800185aa  jz      short loc_1800185D3
0x1800185ac  sub     eax, 1
0x1800185af  jz      short loc_1800185CB
0x1800185b1  sub     eax, 1
0x1800185b4  jz      short loc_1800185C3
0x1800185b6  cmp     eax, 2
0x1800185b9  jnz     short loc_1800185D9
0x1800185bb  mov     r8d, 9E6Eh
0x1800185c1  jmp     short loc_1800185D9
0x1800185c3  mov     r8d, 9E70h
0x1800185c9  jmp     short loc_1800185D9
0x1800185cb  mov     r8d, 9E71h
0x1800185d1  jmp     short loc_1800185D9
0x1800185d3  mov     r8d, 9E6Dh; unsigned int
0x1800185d9  mov     rdx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x1800185e0  lea     rcx, [rsp+4A0h+var_458]; this
0x1800185e5  call    ?Format@CString@@QEAAHPEAUHINSTANCE__@@IZZ; CString::Format(HINSTANCE__ *,uint,...)
0x1800185ea  mov     rbx, [rsp+4A0h+var_450]
0x1800185ef  mov     r8, [rbx]; lpString
0x1800185f2  mov     edx, 3FCh; nIDDlgItem
0x1800185f7  mov     rcx, rdi; hDlg
0x1800185fa  call    cs:__imp_SetDlgItemTextW
0x180018600  mov     r9, [rbx]
0x180018603  mov     r8d, 9E64h; int
0x180018609  mov     rdx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180018610  lea     rcx, [rsp+4A0h+var_448]; this
0x180018615  call    ??0CString@@QEAA@PEAUHINSTANCE__@@HZZ; CString::CString(HINSTANCE__ *,int,...)
0x18001861a  mov     rax, [rsp+4A0h+var_440]
0x18001861f  mov     rbx, [rax]
0x180018622  mov     rcx, rdi; hWnd
0x180018625  call    cs:__imp_GetParent
0x18001862b  mov     r9, rbx; lParam
0x18001862e  xor     r8d, r8d; wParam
0x180018631  mov     edx, 478h; Msg
0x180018636  mov     rcx, rax; hWnd
0x180018639  call    cs:__imp_SendMessageW
0x18001863f  lea     rcx, [rsp+4A0h+var_448]; this
0x180018644  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180018649  nop
0x18001864a  lea     rcx, [rsp+4A0h+var_458]; this
0x18001864f  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180018654  mov     rcx, [rbp+3A0h+var_10]
0x18001865b  xor     rcx, rsp; StackCookie
0x18001865e  call    __security_check_cookie
0x180018663  lea     r11, [rsp+4A0h+var_s0]
0x18001866b  mov     rbx, [r11+10h]
0x18001866f  mov     rdi, [r11+28h]
0x180018673  mov     rsp, r11
0x180018676  pop     rbp
0x180018677  retn
```
