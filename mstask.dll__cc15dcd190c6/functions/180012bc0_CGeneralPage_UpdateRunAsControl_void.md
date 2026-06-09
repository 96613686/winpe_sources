# CGeneralPage::_UpdateRunAsControl(void)

- ea: `0x180012bc0`
- end: `0x180012c2f`
- name: `?_UpdateRunAsControl@CGeneralPage@@AEAAXXZ`
- size: `111`
- prototype: `void __fastcall(CGeneralPage *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800116c0`
- `0x1800127b0`

## callees

- `0x180012bc0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012c23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012c23`
- `USER32!SetDlgItemTextW` at `0x180012c0e`
- `USER32!SetDlgItemTextW` at `0x180012c0e`

## pseudocode

```c
void __fastcall CGeneralPage::_UpdateRunAsControl(CGeneralPage *this)
{
  const WCHAR *v2; // r8
  HWND v3; // rcx
  WCHAR *v4; // rcx
  LPCWSTR lpString; // [rsp+30h] [rbp+8h] BYREF

  lpString = 0;
  if ( (*(int (__fastcall **)(_QWORD, LPCWSTR *))(**((_QWORD **)this + 86) + 248LL))(*((_QWORD *)this + 86), &lpString) >= 0 )
  {
    v2 = lpString;
    if ( lpString )
    {
      v3 = (HWND)*((_QWORD *)this + 14);
      *((_DWORD *)this + 193) = 0;
      SetDlgItemTextW(v3, 1659, v2);
      v4 = (WCHAR *)lpString;
      *((_DWORD *)this + 193) = 1;
      CoTaskMemFree(v4);
    }
  }
}

```

## disassembly

```asm
0x180012bc0  push    rbx
0x180012bc2  sub     rsp, 20h
0x180012bc6  mov     rbx, rcx
0x180012bc9  mov     [rsp+28h+lpString], 0
0x180012bd2  mov     rcx, [rcx+2B0h]
0x180012bd9  lea     rdx, [rsp+28h+lpString]
0x180012bde  mov     rax, [rcx]
0x180012be1  mov     rax, [rax+0F8h]
0x180012be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bed  test    eax, eax
0x180012bef  js      short loc_180012C29
0x180012bf1  mov     r8, [rsp+28h+lpString]; lpString
0x180012bf6  test    r8, r8
0x180012bf9  jz      short loc_180012C29
0x180012bfb  mov     rcx, [rbx+70h]; hDlg
0x180012bff  mov     edx, 67Bh; nIDDlgItem
0x180012c04  mov     dword ptr [rbx+304h], 0
0x180012c0e  call    cs:__imp_SetDlgItemTextW
0x180012c14  mov     rcx, [rsp+28h+lpString]; pv
0x180012c19  mov     dword ptr [rbx+304h], 1
0x180012c23  call    cs:__imp_CoTaskMemFree
0x180012c29  add     rsp, 20h
0x180012c2d  pop     rbx
0x180012c2e  retn
```
