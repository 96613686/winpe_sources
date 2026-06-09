# CToolBar32::get_accState(tagVARIANT,tagVARIANT *)

- ea: `0x18001b8c0`
- end: `0x18001bb15`
- name: `?get_accState@CToolBar32@@UEAAJUtagVARIANT@@PEAU2@@Z`
- size: `597`
- prototype: `__int64 __fastcall(CToolBar32 *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x1800056a4`
- `0x180005ca0`
- `0x18000612c`
- `0x180006510`
- `0x1800065b4`
- `0x18001b8c0`
- `0x18001e4c0`
- `0x180046e78`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001ba77`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18001ba77`
- `USER32!GetParent` at `0x18001ba4a`
- `USER32!GetParent` at `0x18001ba4a`
- `USER32!GetClassNameW` at `0x18001ba62`
- `USER32!GetClassNameW` at `0x18001ba62`

## string_xrefs

- `0x18001ba6c`: `MSTaskSwWClass`

## pseudocode

```c
__int64 __fastcall CToolBar32::get_accState(CToolBar32 *this, struct tagVARIANT *a2, struct tagVARIANT *a3)
{
  __int128 v3; // xmm0
  IRecordInfo *pRecInfo; // xmm1_8
  __int64 v7; // rax
  __int64 result; // rax
  int ItemData; // eax
  BYTE fsState; // cl
  LONG v11; // eax
  HWND *v12; // rbx
  HWND v13; // r8
  int v14; // eax
  HWND Parent; // rax
  LONG lVal; // eax
  HWND v17; // rbx
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  struct tagVARIANT v19; // [rsp+48h] [rbp-B8h] BYREF
  struct _TBBUTTON v20; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ClassName[64]; // [rsp+80h] [rbp-80h] BYREF

  v3 = *(_OWORD *)&a2->vt;
  pRecInfo = a2->pRecInfo;
  a3->vt = 0;
  v7 = *(_QWORD *)this;
  *(_OWORD *)&v19.vt = v3;
  v19.pRecInfo = pRecInfo;
  if ( !(*(unsigned int (__fastcall **)(CToolBar32 *, struct tagVARIANT *))(v7 + 240))(this, &v19) )
    return 2147942487LL;
  if ( !v19.lVal )
  {
    *(_QWORD *)&v20.iBitmap = *(_QWORD *)&v19.vt;
    *(_DWORD *)&v20.fsState = 0;
    HIDWORD(v20.dwData) = *((_DWORD *)&v19.decVal + 5);
    *(_QWORD *)&v20.bReserved[2] = *(ULONGLONG *)((char *)&v19.decVal.Lo64 + 4);
    return CClient::get_accState(this, (struct tagVARIANT *)&v20, a3);
  }
  v18 = 0;
  memset(&v20, 0, sizeof(v20));
  ItemData = CToolBar32::GetItemData(this, v19.lVal, &v20);
  a3->vt = 3;
  if ( !ItemData )
  {
    a3->lVal = 0x8000;
    return 0;
  }
  fsState = v20.fsState;
  v11 = 0;
  a3->lVal = 0;
  if ( (fsState & 1) != 0 )
  {
    a3->lVal = 16;
    v11 = 16;
  }
  if ( (fsState & 2) != 0 )
  {
    v11 |= 8u;
    a3->lVal = v11;
  }
  if ( (fsState & 4) == 0 )
  {
    v11 |= 1u;
    a3->lVal = v11;
  }
  v12 = (HWND *)((char *)this + 80);
  if ( (fsState & 8) != 0 )
  {
    a3->lVal = v11 | 0x8000;
  }
  else
  {
    result = CAccessible::AccSendMessageTimeout(this, 0, *v12, 0x455u, 0, 0, &v18);
    if ( (int)result < 0 )
      return result;
    v13 = *v12;
    if ( (v18 & 0x10) != 0 )
      v14 = IsPartiallyClippedByWindow((struct IAccessible *)this, &v19, v13);
    else
      v14 = IsClippedByWindow((struct IAccessible *)this, &v19, v13);
    if ( v14 )
      a3->lVal |= 0x18000u;
    fsState = v20.fsState;
  }
  if ( (fsState & 0x10) != 0 )
    a3->lVal |= 0x20u;
  Parent = GetParent(*v12);
  if ( Parent )
  {
    if ( GetClassNameW(Parent, ClassName, 64) )
    {
      if ( !lstrcmpW(ClassName, L"MSTaskSwWClass") )
      {
        lVal = a3->lVal;
        if ( (lVal & 0x10) != 0 )
          a3->lVal = lVal & 0xFFFFFFE7 | 8;
      }
    }
  }
  result = CAccessible::AccSendMessageTimeout(this, 0, *v12, 0x447u, 0, 0, &v18);
  if ( (int)result >= 0 )
  {
    if ( v18 == v19.lVal - 1 )
    {
      a3->lVal |= 0x80u;
      v17 = *v12;
      if ( MyGetFocus() == v17 )
        a3->lVal |= 4u;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001b8c0  mov     [rsp-8+arg_18], rbx
0x18001b8c5  push    rbp
0x18001b8c6  push    rsi
0x18001b8c7  push    rdi
0x18001b8c8  lea     rbp, [rsp-10h]
0x18001b8cd  sub     rsp, 110h
0x18001b8d4  mov     rax, cs:__security_cookie
0x18001b8db  xor     rax, rsp
0x18001b8de  mov     [rbp+20h+var_20], rax
0x18001b8e2  movups  xmm0, xmmword ptr [rdx]
0x18001b8e5  xor     eax, eax
0x18001b8e7  mov     rdi, r8
0x18001b8ea  movsd   xmm1, qword ptr [rdx+10h]
0x18001b8ef  mov     rsi, rcx
0x18001b8f2  mov     [r8], ax
0x18001b8f6  lea     rdx, [rsp+120h+var_D8]
0x18001b8fb  mov     rax, [rcx]
0x18001b8fe  movups  xmmword ptr [rsp+120h+var_D8], xmm0
0x18001b903  movsd   qword ptr [rsp+120h+var_D8+10h], xmm1
0x18001b909  mov     rax, [rax+0F0h]
0x18001b910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b915  test    eax, eax
0x18001b917  jnz     short loc_18001B923
0x18001b919  mov     eax, 80070057h
0x18001b91e  jmp     loc_18001BAEC
0x18001b923  mov     edx, dword ptr [rsp+120h+var_D8+8]; int
0x18001b927  mov     rcx, rsi; this
0x18001b92a  test    edx, edx
0x18001b92c  jnz     short loc_18001B962
0x18001b92e  mov     rax, qword ptr [rsp+120h+var_D8]
0x18001b933  mov     r8, rdi; struct tagVARIANT *
0x18001b936  movsd   xmm0, qword ptr [rsp+120h+var_D8+0Ch]
0x18001b93c  mov     qword ptr [rsp+120h+var_C0], rax
0x18001b941  mov     eax, dword ptr [rsp+120h+var_D8+14h]
0x18001b945  mov     dword ptr [rsp+120h+var_C0+8], edx
0x18001b949  lea     rdx, [rsp+120h+var_C0]; struct tagVARIANT
0x18001b94e  mov     dword ptr [rsp+120h+var_C0+14h], eax
0x18001b952  movsd   qword ptr [rsp+120h+var_C0+0Ch], xmm0
0x18001b958  call    ?get_accState@CClient@@UEAAJUtagVARIANT@@PEAU2@@Z; CClient::get_accState(tagVARIANT,tagVARIANT *)
0x18001b95d  jmp     loc_18001BAEC
0x18001b962  xorps   xmm0, xmm0
0x18001b965  mov     [rsp+120h+var_E0], 0
0x18001b96e  lea     r8, [rsp+120h+var_C0]; struct _TBBUTTON *
0x18001b973  movups  xmmword ptr [rsp+120h+var_C0], xmm0
0x18001b978  movups  xmmword ptr [rsp+70h], xmm0
0x18001b97d  call    ?GetItemData@CToolBar32@@QEAAHHPEAU_TBBUTTON@@@Z; CToolBar32::GetItemData(int,_TBBUTTON *)
0x18001b982  mov     word ptr [rdi], 3
0x18001b987  test    eax, eax
0x18001b989  jnz     short loc_18001B997
0x18001b98b  mov     dword ptr [rdi+8], 8000h
0x18001b992  jmp     loc_18001BAEA
0x18001b997  mov     cl, [rsp+120h+var_C0+8]
0x18001b99b  xor     eax, eax
0x18001b99d  mov     dword ptr [rdi+8], 0
0x18001b9a4  test    cl, 1
0x18001b9a7  jz      short loc_18001B9B5
0x18001b9a9  mov     dword ptr [rdi+8], 10h
0x18001b9b0  mov     eax, 10h
0x18001b9b5  test    cl, 2
0x18001b9b8  jz      short loc_18001B9C0
0x18001b9ba  or      eax, 8
0x18001b9bd  mov     [rdi+8], eax
0x18001b9c0  test    cl, 4
0x18001b9c3  jnz     short loc_18001B9CB
0x18001b9c5  or      eax, 1
0x18001b9c8  mov     [rdi+8], eax
0x18001b9cb  lea     rbx, [rsi+50h]
0x18001b9cf  test    cl, 8
0x18001b9d2  jz      short loc_18001B9DD
0x18001b9d4  bts     eax, 0Fh
0x18001b9d8  mov     [rdi+8], eax
0x18001b9db  jmp     short loc_18001BA3E
0x18001b9dd  mov     r8, [rbx]; HWND
0x18001b9e0  lea     rax, [rsp+120h+var_E0]
0x18001b9e5  mov     [rsp+120h+var_F0], rax; __int64 *
0x18001b9ea  mov     r9d, 455h; unsigned int
0x18001b9f0  mov     [rsp+120h+var_F8], 0; __int64
0x18001b9f9  xor     edx, edx; bool
0x18001b9fb  mov     rcx, rsi; this
0x18001b9fe  mov     [rsp+120h+var_100], 0; unsigned __int64
0x18001ba07  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18001ba0c  test    eax, eax
0x18001ba0e  js      loc_18001BAEC
0x18001ba14  test    byte ptr [rsp+120h+var_E0], 10h
0x18001ba19  lea     rdx, [rsp+120h+var_D8]; struct tagVARIANT *
0x18001ba1e  mov     r8, [rbx]; HWND
0x18001ba21  mov     rcx, rsi; struct IAccessible *
0x18001ba24  jz      loc_18001BB0B
0x18001ba2a  call    ?IsPartiallyClippedByWindow@@YAHPEAUIAccessible@@AEAUtagVARIANT@@PEAUHWND__@@@Z; IsPartiallyClippedByWindow(IAccessible *,tagVARIANT &,HWND__ *)
0x18001ba2f  test    eax, eax
0x18001ba31  jz      short loc_18001BA3A
0x18001ba33  or      dword ptr [rdi+8], 18000h
0x18001ba3a  mov     cl, [rsp+120h+var_C0+8]
0x18001ba3e  test    cl, 10h
0x18001ba41  jz      short loc_18001BA47
0x18001ba43  or      dword ptr [rdi+8], 20h
0x18001ba47  mov     rcx, [rbx]; hWnd
0x18001ba4a  call    cs:__imp_GetParent
0x18001ba50  test    rax, rax
0x18001ba53  jz      short loc_18001BA91
0x18001ba55  mov     r8d, 40h ; '@'; nMaxCount
0x18001ba5b  lea     rdx, [rbp+20h+ClassName]; lpClassName
0x18001ba5f  mov     rcx, rax; hWnd
0x18001ba62  call    cs:__imp_GetClassNameW
0x18001ba68  test    eax, eax
0x18001ba6a  jz      short loc_18001BA91
0x18001ba6c  lea     rdx, aMstaskswwclass; "MSTaskSwWClass"
0x18001ba73  lea     rcx, [rbp+20h+ClassName]; lpString1
0x18001ba77  call    cs:__imp_lstrcmpW
0x18001ba7d  test    eax, eax
0x18001ba7f  jnz     short loc_18001BA91
0x18001ba81  mov     eax, [rdi+8]
0x18001ba84  test    al, 10h
0x18001ba86  jz      short loc_18001BA91
0x18001ba88  and     eax, 0FFFFFFEFh
0x18001ba8b  or      eax, 8
0x18001ba8e  mov     [rdi+8], eax
0x18001ba91  mov     r8, [rbx]; HWND
0x18001ba94  lea     rax, [rsp+120h+var_E0]
0x18001ba99  mov     [rsp+120h+var_F0], rax; __int64 *
0x18001ba9e  mov     r9d, 447h; unsigned int
0x18001baa4  mov     [rsp+120h+var_F8], 0; __int64
0x18001baad  xor     edx, edx; bool
0x18001baaf  mov     rcx, rsi; this
0x18001bab2  mov     [rsp+120h+var_100], 0; unsigned __int64
0x18001babb  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18001bac0  test    eax, eax
0x18001bac2  js      short loc_18001BAEC
0x18001bac4  mov     eax, dword ptr [rsp+120h+var_D8+8]
0x18001bac8  dec     eax
0x18001baca  movsxd  rcx, eax
0x18001bacd  cmp     [rsp+120h+var_E0], rcx
0x18001bad2  jnz     short loc_18001BAEA
0x18001bad4  bts     dword ptr [rdi+8], 7
0x18001bad9  mov     rbx, [rbx]
0x18001badc  call    ?MyGetFocus@@YAPEAUHWND__@@XZ; MyGetFocus(void)
0x18001bae1  cmp     rax, rbx
0x18001bae4  jnz     short loc_18001BAEA
0x18001bae6  or      dword ptr [rdi+8], 4
0x18001baea  xor     eax, eax
0x18001baec  mov     rcx, [rbp+20h+var_20]
0x18001baf0  xor     rcx, rsp; StackCookie
0x18001baf3  call    __security_check_cookie
0x18001baf8  mov     rbx, [rsp+120h+arg_18]
0x18001bb00  add     rsp, 110h
0x18001bb07  pop     rdi
0x18001bb08  pop     rsi
0x18001bb09  pop     rbp
0x18001bb0a  retn
0x18001bb0b  call    ?IsClippedByWindow@@YAHPEAUIAccessible@@AEAUtagVARIANT@@PEAUHWND__@@@Z; IsClippedByWindow(IAccessible *,tagVARIANT &,HWND__ *)
0x18001bb10  jmp     loc_18001BA2F
```
