# CToolBar32::get_accRole(tagVARIANT,tagVARIANT *)

- ea: `0x18000c8a0`
- end: `0x18000cab5`
- name: `?get_accRole@CToolBar32@@UEAAJUtagVARIANT@@PEAU2@@Z`
- size: `533`
- prototype: `__int64 __fastcall(CToolBar32 *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x1800065b4`
- `0x18000b890`
- `0x18000baa0`
- `0x18000c8a0`
- `0x18001e4c0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000ca61`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000ca61`
- `USER32!GetParent` at `0x18000ca34`
- `USER32!GetParent` at `0x18000ca34`
- `USER32!GetClassNameW` at `0x18000ca4c`
- `USER32!GetClassNameW` at `0x18000ca4c`

## string_xrefs

- `0x18000ca17`: `CAccessible::AccSendMessageTimeout`
- `0x18000ca56`: `MSTaskSwWClass`

## pseudocode

```c
__int64 __fastcall CToolBar32::get_accRole(HWND *this, struct tagVARIANT *a2, struct tagVARIANT *a3)
{
  LONG lVal; // edx
  HWND v8; // r14
  int v9; // esi
  HWND v10; // r15
  BOOL v11; // r14d
  HWND v12; // r9
  HWND Parent; // rax
  int v14; // [rsp+30h] [rbp-89h] BYREF
  int v15; // [rsp+34h] [rbp-85h]
  __int64 v16; // [rsp+38h] [rbp-81h] BYREF
  struct _TBBUTTON v17; // [rsp+40h] [rbp-79h] BYREF
  WCHAR ClassName[64]; // [rsp+60h] [rbp-59h] BYREF

  a3->vt = 0;
  if ( !(*((unsigned int (__fastcall **)(HWND *))*this + 30))(this) )
    return 2147942487LL;
  lVal = a2->lVal;
  if ( !lVal )
  {
    a3->vt = 3;
    a3->lVal = 22;
    return 0;
  }
  memset(&v17, 0, sizeof(v17));
  if ( !(unsigned int)CToolBar32::GetItemData((CToolBar32 *)this, lVal, &v17) )
    return 1;
  a3->vt = 3;
  v8 = this[10];
  v14 = *((_DWORD *)this + 25);
  v15 = *((_DWORD *)this + 17);
  v16 = 0;
  v9 = SendMessageTimeoutHelper((struct OLEACC_TIMEOUTDATA *)&v14, v8, 0x431u, 0, 0, &v16);
  if ( v9 < 0 )
  {
    v12 = v8;
LABEL_13:
    Error::IAccessibleError(0, L"CAccessible::AccSendMessageTimeout", v9, v12, 5002);
    return (unsigned int)v9;
  }
  v10 = this[10];
  v14 = *((_DWORD *)this + 25);
  v11 = v16 != 0;
  v15 = *((_DWORD *)this + 17);
  v9 = SendMessageTimeoutHelper((struct OLEACC_TIMEOUTDATA *)&v14, v10, 0x455u, 0, 0, &v16);
  if ( v9 < 0 )
  {
    v12 = v10;
    goto LABEL_13;
  }
  if ( (v17.fsStyle & 1) == 0 )
  {
    if ( (v17.fsStyle & 2) != 0 )
    {
      Parent = GetParent(this[10]);
      if ( !Parent || !GetClassNameW(Parent, ClassName, 64) || lstrcmpW(ClassName, L"MSTaskSwWClass") )
      {
        a3->lVal = (v17.fsStyle & 4 | 0xB0u) >> 2;
        return 0;
      }
    }
    else
    {
      if ( (v17.fsStyle & 8) != 0 && (v16 & 1) != 0 )
      {
        a3->lVal = 62;
        return 0;
      }
      if ( !v11 || v17.iBitmap == -2 )
      {
        a3->lVal = 12;
        return 0;
      }
    }
    a3->lVal = 43;
    return 0;
  }
  a3->lVal = 21;
  return 0;
}

```

## disassembly

```asm
0x18000c8a0  mov     [rsp-8+arg_18], rbx
0x18000c8a5  push    rbp
0x18000c8a6  push    rsi
0x18000c8a7  push    rdi
0x18000c8a8  push    r14
0x18000c8aa  push    r15
0x18000c8ac  lea     rbp, [rsp-37h]
0x18000c8b1  sub     rsp, 0F0h
0x18000c8b8  mov     rax, cs:__security_cookie
0x18000c8bf  xor     rax, rsp
0x18000c8c2  mov     [rbp+57h+var_30], rax
0x18000c8c6  xor     eax, eax
0x18000c8c8  mov     rbx, r8
0x18000c8cb  mov     [r8], ax
0x18000c8cf  mov     rsi, rdx
0x18000c8d2  mov     rax, [rcx]
0x18000c8d5  mov     rdi, rcx
0x18000c8d8  mov     rax, [rax+0F0h]
0x18000c8df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8e4  test    eax, eax
0x18000c8e6  jnz     short loc_18000C910
0x18000c8e8  mov     eax, 80070057h
0x18000c8ed  mov     rcx, [rbp+57h+var_30]
0x18000c8f1  xor     rcx, rsp; StackCookie
0x18000c8f4  call    __security_check_cookie
0x18000c8f9  mov     rbx, [rsp+110h+arg_18]
0x18000c901  add     rsp, 0F0h
0x18000c908  pop     r15
0x18000c90a  pop     r14
0x18000c90c  pop     rdi
0x18000c90d  pop     rsi
0x18000c90e  pop     rbp
0x18000c90f  retn
0x18000c910  mov     edx, [rsi+8]; int
0x18000c913  test    edx, edx
0x18000c915  jz      loc_18000C9E9
0x18000c91b  xorps   xmm0, xmm0
0x18000c91e  lea     r8, [rbp+57h+var_D0]; struct _TBBUTTON *
0x18000c922  mov     rcx, rdi; this
0x18000c925  movups  xmmword ptr [rbp+57h+var_D0.iBitmap], xmm0
0x18000c929  movups  xmmword ptr [rbp+57h+var_D0.dwData], xmm0
0x18000c92d  call    ?GetItemData@CToolBar32@@QEAAHHPEAU_TBBUTTON@@@Z; CToolBar32::GetItemData(int,_TBBUTTON *)
0x18000c932  test    eax, eax
0x18000c934  jz      loc_18000C9FA
0x18000c93a  mov     word ptr [rbx], 3
0x18000c93f  lea     rcx, [rsp+110h+var_E0]; struct OLEACC_TIMEOUTDATA *
0x18000c944  mov     eax, [rdi+64h]
0x18000c947  xor     r9d, r9d; unsigned __int64
0x18000c94a  mov     r14, [rdi+50h]
0x18000c94e  mov     r8d, 431h; unsigned int
0x18000c954  mov     [rsp+110h+var_E0], eax
0x18000c958  mov     rdx, r14; HWND
0x18000c95b  mov     eax, [rdi+44h]
0x18000c95e  mov     [rsp+110h+var_DC], eax
0x18000c962  lea     rax, [rsp+110h+var_D8]
0x18000c967  mov     [rsp+110h+var_E8], rax; __int64 *
0x18000c96c  mov     [rsp+110h+var_F0], 0; __int64
0x18000c975  mov     [rsp+110h+var_D8], 0
0x18000c97e  call    ?SendMessageTimeoutHelper@@YAJPEAUOLEACC_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; SendMessageTimeoutHelper(OLEACC_TIMEOUTDATA *,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18000c983  mov     esi, eax
0x18000c985  test    eax, eax
0x18000c987  js      short loc_18000CA04
0x18000c989  mov     eax, [rdi+64h]
0x18000c98c  lea     rcx, [rsp+110h+var_E0]; struct OLEACC_TIMEOUTDATA *
0x18000c991  mov     r15, [rdi+50h]
0x18000c995  xor     r14d, r14d
0x18000c998  cmp     [rsp+110h+var_D8], r14
0x18000c99d  mov     r8d, 455h; unsigned int
0x18000c9a3  mov     [rsp+110h+var_E0], eax
0x18000c9a7  mov     rdx, r15; HWND
0x18000c9aa  mov     eax, [rdi+44h]
0x18000c9ad  setnz   r14b
0x18000c9b1  mov     [rsp+110h+var_DC], eax
0x18000c9b5  xor     r9d, r9d; unsigned __int64
0x18000c9b8  lea     rax, [rsp+110h+var_D8]
0x18000c9bd  mov     [rsp+110h+var_E8], rax; __int64 *
0x18000c9c2  mov     [rsp+110h+var_F0], 0; __int64
0x18000c9cb  call    ?SendMessageTimeoutHelper@@YAJPEAUOLEACC_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; SendMessageTimeoutHelper(OLEACC_TIMEOUTDATA *,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18000c9d0  mov     esi, eax
0x18000c9d2  test    eax, eax
0x18000c9d4  js      short loc_18000CA09
0x18000c9d6  mov     al, [rbp+57h+var_D0.fsStyle]
0x18000c9d9  test    al, 1
0x18000c9db  jz      short loc_18000CA2C
0x18000c9dd  mov     dword ptr [rbx+8], 15h
0x18000c9e4  jmp     loc_18000CAAE
0x18000c9e9  mov     word ptr [rbx], 3
0x18000c9ee  mov     dword ptr [rbx+8], 16h
0x18000c9f5  jmp     loc_18000CAAE
0x18000c9fa  mov     eax, 1
0x18000c9ff  jmp     loc_18000C8ED
0x18000ca04  mov     r9, r14
0x18000ca07  jmp     short loc_18000CA0C
0x18000ca09  mov     r9, r15; HWND
0x18000ca0c  mov     r8d, esi; int
0x18000ca0f  mov     dword ptr [rsp+110h+var_F0], 138Ah; int
0x18000ca17  lea     rdx, aCaccessibleAcc; "CAccessible::AccSendMessageTimeout"
0x18000ca1e  xor     ecx, ecx; struct IUnknown *
0x18000ca20  call    ?IAccessibleError@Error@@SAXPEAUIUnknown@@PEBGJPEAUHWND__@@H@Z; Error::IAccessibleError(IUnknown *,ushort const *,long,HWND__ *,int)
0x18000ca25  mov     eax, esi
0x18000ca27  jmp     loc_18000C8ED
0x18000ca2c  test    al, 2
0x18000ca2e  jz      short loc_18000CA7F
0x18000ca30  mov     rcx, [rdi+50h]; hWnd
0x18000ca34  call    cs:__imp_GetParent
0x18000ca3a  test    rax, rax
0x18000ca3d  jz      short loc_18000CA6B
0x18000ca3f  mov     r8d, 40h ; '@'; nMaxCount
0x18000ca45  lea     rdx, [rbp+57h+ClassName]; lpClassName
0x18000ca49  mov     rcx, rax; hWnd
0x18000ca4c  call    cs:__imp_GetClassNameW
0x18000ca52  test    eax, eax
0x18000ca54  jz      short loc_18000CA6B
0x18000ca56  lea     rdx, aMstaskswwclass; "MSTaskSwWClass"
0x18000ca5d  lea     rcx, [rbp+57h+ClassName]; lpString1
0x18000ca61  call    cs:__imp_lstrcmpW
0x18000ca67  test    eax, eax
0x18000ca69  jz      short loc_18000CA9E
0x18000ca6b  movzx   eax, [rbp+57h+var_D0.fsStyle]
0x18000ca6f  and     eax, 4
0x18000ca72  or      eax, 0B0h
0x18000ca77  shr     eax, 2
0x18000ca7a  mov     [rbx+8], eax
0x18000ca7d  jmp     short loc_18000CAAE
0x18000ca7f  test    al, 8
0x18000ca81  jz      short loc_18000CA93
0x18000ca83  test    byte ptr [rsp+110h+var_D8], 1
0x18000ca88  jz      short loc_18000CA93
0x18000ca8a  mov     dword ptr [rbx+8], 3Eh ; '>'
0x18000ca91  jmp     short loc_18000CAAE
0x18000ca93  test    r14d, r14d
0x18000ca96  jz      short loc_18000CAA7
0x18000ca98  cmp     [rbp+57h+var_D0.iBitmap], 0FFFFFFFEh
0x18000ca9c  jz      short loc_18000CAA7
0x18000ca9e  mov     dword ptr [rbx+8], 2Bh ; '+'
0x18000caa5  jmp     short loc_18000CAAE
0x18000caa7  mov     dword ptr [rbx+8], 0Ch
0x18000caae  xor     eax, eax
0x18000cab0  jmp     loc_18000C8ED
```
