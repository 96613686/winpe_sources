# CPackage::EnumVerbs(IEnumOLEVERB * *)

- ea: `0x180005470`
- end: `0x1800058b4`
- name: `?EnumVerbs@CPackage@@UEAAJPEAPEAUIEnumOLEVERB@@@Z`
- size: `1092`
- prototype: `__int64 __fastcall(CPackage *__hidden this, struct IEnumOLEVERB **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800041d4`
- `0x180005470`
- `0x180008600`
- `0x1800092d0`
- `0x18000a6ec`
- `0x18000a718`
- `0x18000cbbe`
- `0x18000cbf0`
- `0x18000e010`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180005713`
- `KERNEL32!lstrlenW` at `0x180005713`
- `KERNEL32!lstrcmpW` at `0x1800056ee`
- `KERNEL32!lstrcmpW` at `0x1800056ee`
- `ole32!OleRegEnumVerbs` at `0x1800055ad`
- `ole32!OleRegEnumVerbs` at `0x180005826`
- `ole32!OleRegEnumVerbs` at `0x1800055ad`
- `ole32!OleRegEnumVerbs` at `0x180005826`
- `USER32!CreatePopupMenu` at `0x18000550f`
- `USER32!CreatePopupMenu` at `0x18000550f`
- `USER32!GetMenuItemInfoW` at `0x180005693`
- `USER32!GetMenuItemInfoW` at `0x180005693`
- `USER32!DestroyMenu` at `0x1800057af`
- `USER32!DestroyMenu` at `0x1800057af`
- `USER32!GetMenuItemCount` at `0x18000555c`
- `USER32!GetMenuItemCount` at `0x18000555c`
- `USER32!InsertMenuW` at `0x1800055fc`
- `USER32!InsertMenuW` at `0x1800055fc`
- `USER32!GetMenuState` at `0x18000566e`
- `USER32!GetMenuState` at `0x18000566e`

## pseudocode

```c
__int64 __fastcall CPackage::EnumVerbs(CPackage *this, struct IEnumOLEVERB **a2)
{
  CPackage *v2; // rdi
  CPackage *v3; // rax
  __int64 v4; // rcx
  LPENUMOLEVERB v5; // r14
  int inited; // ebx
  HMENU PopupMenu; // rax
  LPENUMOLEVERB v8; // r12
  HMENU v9; // rsi
  int MenuItemCount; // eax
  int v11; // r13d
  struct tagOLEVERB *v12; // r14
  UINT i; // ebx
  signed int v14; // ebx
  CPackage *v15; // rdi
  UINT v16; // r15d
  const WCHAR *dwTypeData; // rcx
  unsigned __int16 *v18; // rax
  __int64 v19; // r11
  struct tagOLEVERB *v20; // rsi
  UINT uId; // [rsp+40h] [rbp-C0h] BYREF
  LPENUMOLEVERB v23; // [rsp+48h] [rbp-B8h] BYREF
  LPENUMOLEVERB ppenum; // [rsp+50h] [rbp-B0h] BYREF
  CPackage *v25; // [rsp+58h] [rbp-A8h]
  __int64 v26; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v27; // [rsp+68h] [rbp-98h]
  CPackage *v28; // [rsp+70h] [rbp-90h]
  struct tagMENUITEMINFOW mii; // [rsp+80h] [rbp-80h] BYREF
  WCHAR String1[264]; // [rsp+D0h] [rbp-30h] BYREF
  char v31; // [rsp+2E0h] [rbp+1E0h] BYREF

  v2 = (CPackage *)((char *)this - 16);
  v25 = this;
  v23 = (LPENUMOLEVERB)a2;
  v3 = this;
  ppenum = 0;
  v4 = *((_QWORD *)this + 27);
  v5 = (LPENUMOLEVERB)a2;
  v28 = v2;
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    v3 = v25;
    *((_QWORD *)v2 + 29) = 0;
  }
  if ( !v5 )
    return (unsigned int)-2147024809;
  if ( !*((_QWORD *)v3 + 12) )
  {
    inited = 0x40000;
    v20 = (struct tagOLEVERB *)operator new(0x48u);
    if ( v20 )
    {
      v23 = 0;
      uId = 0;
      if ( OleRegEnumVerbs(&CLSID_CPackage, &v23) >= 0 )
      {
        ((void (__fastcall *)(LPENUMOLEVERB, __int64, struct tagOLEVERB *, UINT *))v23->lpVtbl->Next)(v23, 3, v20, &uId);
        ((void (__fastcall *)(LPENUMOLEVERB))v23->lpVtbl->Release)(v23);
      }
      inited = CPackage::InitVerbEnum(v2, v20, uId);
      if ( inited < 0 )
      {
        operator delete(v20);
        return (unsigned int)inited;
      }
    }
    goto LABEL_36;
  }
  inited = CPackage::GetContextMenu(v2, (struct IContextMenu **)&ppenum);
  if ( inited >= 0 )
  {
    PopupMenu = CreatePopupMenu();
    v8 = ppenum;
    v9 = PopupMenu;
    if ( PopupMenu )
    {
      inited = ((__int64 (__fastcall *)(LPENUMOLEVERB, HMENU, _QWORD, __int64, int, _DWORD))ppenum->lpVtbl->Next)(
                 ppenum,
                 PopupMenu,
                 0,
                 2,
                 0xFFFF,
                 0);
      if ( inited >= 0 )
      {
        MenuItemCount = GetMenuItemCount(v9);
        v11 = MenuItemCount;
        if ( MenuItemCount <= 0 )
        {
          inited = -2147221120;
        }
        else
        {
          v12 = (struct tagOLEVERB *)operator new(saturated_mul((unsigned int)(MenuItemCount + 3), 0x18u));
          if ( v12 )
          {
            ppenum = 0;
            uId = 0;
            if ( OleRegEnumVerbs(&CLSID_CPackage, &ppenum) >= 0 )
            {
              ((void (__fastcall *)(LPENUMOLEVERB, __int64, struct tagOLEVERB *, UINT *))ppenum->lpVtbl->Next)(
                ppenum,
                3,
                v12,
                &uId);
              if ( uId )
              {
                for ( i = 0; i < uId; ++i )
                  InsertMenuW(v9, i, 0x400u, i, v12[i].lpszVerbName);
              }
              ((void (__fastcall *)(LPENUMOLEVERB))ppenum->lpVtbl->Release)(ppenum);
            }
            memset_0(&mii, 0, sizeof(mii));
            mii.cbSize = 80;
            v14 = uId;
            mii.fMask = 51;
            if ( uId < uId + v11 )
            {
              v15 = v25;
              v16 = uId;
              do
              {
                mii.cch = 260;
                mii.dwTypeData = (LPWSTR)&v31;
                LODWORD(v25) = GetMenuState(v9, v16, 0x400u);
                if ( ((unsigned __int16)v25 & 0x114) == 0 && GetMenuItemInfoW(v9, v16, 1, &mii) && !mii.fType )
                {
                  if ( ((int (__fastcall *)(LPENUMOLEVERB, _QWORD, __int64))v8->lpVtbl->Reset)(v8, mii.wID - 2, 4) < 0 )
                    String1[0] = 0;
                  if ( !lstrcmpW(String1, L"properties") )
                  {
                    dwTypeData = mii.dwTypeData;
                    v12[v14].lVerb = v16;
                    *((_DWORD *)v15 + 56) = v16;
                    v26 = 3LL * v14;
                    v27 = lstrlenW(dwTypeData) + 1LL;
                    v18 = (unsigned __int16 *)operator new(saturated_mul(v27, 2u));
                    v19 = v26;
                    v12[(unsigned __int64)v26 / 3].lpszVerbName = v18;
                    if ( v18 )
                      StringCchCopyW(v18, v27, mii.dwTypeData);
                    ++v14;
                    *(&v12->fuFlags + 2 * v19) = (unsigned int)v25;
                    *(&v12->grfAttribs + 2 * v19) = 2;
                  }
                }
                ++v16;
              }
              while ( v16 < v11 + uId );
              v2 = v28;
            }
            inited = CPackage::InitVerbEnum(v2, v12, v14);
            if ( inited < 0 )
              operator delete(v12);
          }
          else
          {
            inited = -2147024882;
          }
          v5 = v23;
        }
      }
      DestroyMenu(v9);
    }
    else
    {
      inited = -2147024882;
    }
    ((void (__fastcall *)(LPENUMOLEVERB))v8->lpVtbl->Release)(v8);
    if ( inited >= 0 )
    {
LABEL_36:
      v5->lpVtbl = (struct IEnumOLEVERBVtbl *)v2;
      (*(void (__fastcall **)(CPackage *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180005470  mov     [rsp-8+arg_10], rbx
0x180005475  push    rbp
0x180005476  push    rsi
0x180005477  push    rdi
0x180005478  push    r12
0x18000547a  push    r13
0x18000547c  push    r14
0x18000547e  push    r15
0x180005480  lea     rbp, [rsp-400h]
0x180005488  sub     rsp, 500h
0x18000548f  mov     rax, cs:__security_cookie
0x180005496  xor     rax, rsp
0x180005499  mov     [rbp+430h+var_40], rax
0x1800054a0  lea     rdi, [rcx-10h]
0x1800054a4  mov     [rsp+530h+var_4D8], rcx
0x1800054a9  xor     r15d, r15d
0x1800054ac  mov     [rsp+530h+var_4E8], rdx
0x1800054b1  mov     rax, rcx
0x1800054b4  mov     [rsp+530h+ppenum], r15
0x1800054b9  mov     rcx, [rdi+0E8h]
0x1800054c0  mov     r14, rdx
0x1800054c3  mov     [rsp+530h+var_4C0], rdi
0x1800054c8  test    rcx, rcx
0x1800054cb  jz      short loc_1800054E5
0x1800054cd  mov     rax, [rcx]
0x1800054d0  mov     rax, [rax+10h]
0x1800054d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054d9  mov     rax, [rsp+530h+var_4D8]
0x1800054de  mov     [rdi+0E8h], r15
0x1800054e5  test    r14, r14
0x1800054e8  jz      loc_180005883
0x1800054ee  cmp     [rax+60h], r15
0x1800054f2  jz      loc_1800057F9
0x1800054f8  lea     rdx, [rsp+530h+ppenum]; struct IContextMenu **
0x1800054fd  mov     rcx, rdi; this
0x180005500  call    ?GetContextMenu@CPackage@@IEAAJPEAPEAUIContextMenu@@@Z; CPackage::GetContextMenu(IContextMenu * *)
0x180005505  mov     ebx, eax
0x180005507  test    eax, eax
0x180005509  js      loc_180005888
0x18000550f  call    cs:__imp_CreatePopupMenu
0x180005515  mov     r12, [rsp+530h+ppenum]
0x18000551a  mov     rsi, rax
0x18000551d  test    rax, rax
0x180005520  jz      loc_1800057C5
0x180005526  mov     rcx, [r12]
0x18000552a  mov     r9d, 2
0x180005530  mov     [rsp+530h+var_508], r15d
0x180005535  xor     r8d, r8d
0x180005538  mov     rdx, rsi
0x18000553b  mov     dword ptr [rsp+530h+lpNewItem], 0FFFFh
0x180005543  mov     rax, [rcx+18h]
0x180005547  mov     rcx, r12
0x18000554a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000554f  mov     ebx, eax
0x180005551  test    eax, eax
0x180005553  js      loc_1800057AC
0x180005559  mov     rcx, rsi; hMenu
0x18000555c  call    cs:__imp_GetMenuItemCount
0x180005562  mov     r13d, eax
0x180005565  test    eax, eax
0x180005567  jle     loc_1800057BE
0x18000556d  lea     edx, [rax+3]
0x180005570  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005577  mov     eax, 18h
0x18000557c  mul     rdx
0x18000557f  cmovb   rax, rcx
0x180005583  mov     rcx, rax; unsigned __int64
0x180005586  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000558b  mov     r14, rax
0x18000558e  test    rax, rax
0x180005591  jz      loc_1800057B7
0x180005597  lea     rdx, [rsp+530h+ppenum]; ppenum
0x18000559c  mov     [rsp+530h+ppenum], r15
0x1800055a1  lea     rcx, CLSID_CPackage; clsid
0x1800055a8  mov     [rsp+530h+uId], r15d
0x1800055ad  call    cs:__imp_OleRegEnumVerbs
0x1800055b3  test    eax, eax
0x1800055b5  js      short loc_18000561B
0x1800055b7  mov     rcx, [rsp+530h+ppenum]
0x1800055bc  lea     r9, [rsp+530h+uId]
0x1800055c1  mov     r8, r14
0x1800055c4  mov     edx, 3
0x1800055c9  mov     rax, [rcx]
0x1800055cc  mov     rax, [rax+18h]
0x1800055d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055d5  mov     eax, [rsp+530h+uId]
0x1800055d9  test    eax, eax
0x1800055db  jz      short loc_18000560A
0x1800055dd  mov     ebx, r15d
0x1800055e0  mov     r9d, ebx; uIDNewItem
0x1800055e3  mov     r8d, 400h; uFlags
0x1800055e9  mov     edx, ebx; uPosition
0x1800055eb  lea     rax, [r9+r9*2]
0x1800055ef  mov     rcx, [r14+rax*8+8]
0x1800055f4  mov     [rsp+530h+lpNewItem], rcx; lpNewItem
0x1800055f9  mov     rcx, rsi; hMenu
0x1800055fc  call    cs:__imp_InsertMenuW
0x180005602  inc     ebx
0x180005604  cmp     ebx, [rsp+530h+uId]
0x180005608  jb      short loc_1800055E0
0x18000560a  mov     rcx, [rsp+530h+ppenum]
0x18000560f  mov     rax, [rcx]
0x180005612  mov     rax, [rax+10h]
0x180005616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000561b  mov     ebx, 50h ; 'P'
0x180005620  lea     rcx, [rbp+430h+mii]; void *
0x180005624  mov     r8d, ebx; Size
0x180005627  xor     edx, edx; Val
0x180005629  call    memset_0
0x18000562e  mov     [rbp+430h+mii.cbSize], ebx
0x180005631  mov     ebx, [rsp+530h+uId]
0x180005635  mov     [rbp+430h+mii.fMask], 33h ; '3'
0x18000563c  lea     eax, [rbx+r13]
0x180005640  cmp     ebx, eax
0x180005642  jnb     loc_18000578B
0x180005648  mov     rdi, [rsp+530h+var_4D8]
0x18000564d  mov     r15d, ebx
0x180005650  lea     rax, [rbp+430h+var_250]
0x180005657  mov     [rbp+430h+mii.cch], 104h
0x18000565e  mov     r8d, 400h; uFlags
0x180005664  mov     [rbp+430h+mii.dwTypeData], rax
0x180005668  mov     edx, r15d; uId
0x18000566b  mov     rcx, rsi; hMenu
0x18000566e  call    cs:__imp_GetMenuState
0x180005674  mov     dword ptr [rsp+530h+var_4D8], eax
0x180005678  test    eax, 114h
0x18000567d  jnz     loc_180005773
0x180005683  lea     r9, [rbp+430h+mii]; lpmii
0x180005687  mov     r8d, 1; fByPosition
0x18000568d  mov     edx, r15d; item
0x180005690  mov     rcx, rsi; hmenu
0x180005693  call    cs:__imp_GetMenuItemInfoW
0x180005699  test    eax, eax
0x18000569b  jz      loc_180005773
0x1800056a1  cmp     [rbp+430h+mii.fType], 0
0x1800056a5  jnz     loc_180005773
0x1800056ab  mov     rcx, [r12]
0x1800056af  xor     r9d, r9d
0x1800056b2  mov     edx, [rbp+430h+mii.wID]
0x1800056b5  mov     [rsp+530h+var_508], 104h
0x1800056bd  add     edx, 0FFFFFFFEh
0x1800056c0  mov     rax, [rcx+28h]
0x1800056c4  lea     r8d, [r9+4]
0x1800056c8  lea     rcx, [rbp+430h+String1]
0x1800056cc  mov     [rsp+530h+lpNewItem], rcx
0x1800056d1  mov     rcx, r12
0x1800056d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056d9  test    eax, eax
0x1800056db  jns     short loc_1800056E3
0x1800056dd  xor     eax, eax
0x1800056df  mov     [rbp+430h+String1], ax
0x1800056e3  lea     rdx, String2; "properties"
0x1800056ea  lea     rcx, [rbp+430h+String1]; lpString1
0x1800056ee  call    cs:__imp_lstrcmpW
0x1800056f4  test    eax, eax
0x1800056f6  jnz     short loc_180005773
0x1800056f8  mov     rcx, [rbp+430h+mii.dwTypeData]; lpString
0x1800056fc  movsxd  rax, ebx
0x1800056ff  lea     rax, [rax+rax*2]
0x180005703  mov     [r14+rax*8], r15d
0x180005707  mov     [rdi+0E0h], r15d
0x18000570e  mov     [rsp+530h+var_4D0], rax
0x180005713  call    cs:__imp_lstrlenW
0x180005719  movsxd  rcx, eax
0x18000571c  mov     eax, 2
0x180005721  inc     rcx
0x180005724  mul     rcx
0x180005727  mov     [rsp+530h+var_4C8], rcx
0x18000572c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005733  cmovb   rax, rcx
0x180005737  mov     rcx, rax; unsigned __int64
0x18000573a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000573f  mov     r11, [rsp+530h+var_4D0]
0x180005744  mov     [r14+r11*8+8], rax
0x180005749  test    rax, rax
0x18000574c  jz      short loc_18000575F
0x18000574e  mov     r8, [rbp+430h+mii.dwTypeData]; unsigned __int16 *
0x180005752  mov     rcx, rax; unsigned __int16 *
0x180005755  mov     rdx, [rsp+530h+var_4C8]; unsigned __int64
0x18000575a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000575f  mov     eax, dword ptr [rsp+530h+var_4D8]
0x180005763  inc     ebx
0x180005765  mov     [r14+r11*8+10h], eax
0x18000576a  mov     dword ptr [r14+r11*8+14h], 2
0x180005773  mov     ecx, [rsp+530h+uId]
0x180005777  inc     r15d
0x18000577a  add     ecx, r13d
0x18000577d  cmp     r15d, ecx
0x180005780  jb      loc_180005650
0x180005786  mov     rdi, [rsp+530h+var_4C0]
0x18000578b  mov     r8d, ebx; unsigned int
0x18000578e  mov     rdx, r14; struct tagOLEVERB *
0x180005791  mov     rcx, rdi; this
0x180005794  call    ?InitVerbEnum@CPackage@@IEAAJPEAUtagOLEVERB@@K@Z; CPackage::InitVerbEnum(tagOLEVERB *,ulong)
0x180005799  mov     ebx, eax
0x18000579b  test    eax, eax
0x18000579d  jns     short loc_1800057A7
0x18000579f  mov     rcx, r14; lpMem
0x1800057a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800057a7  mov     r14, [rsp+530h+var_4E8]
0x1800057ac  mov     rcx, rsi; hMenu
0x1800057af  call    cs:__imp_DestroyMenu
0x1800057b5  jmp     short loc_1800057CA
0x1800057b7  mov     ebx, 8007000Eh
0x1800057bc  jmp     short loc_1800057A7
0x1800057be  mov     ebx, 80040180h
0x1800057c3  jmp     short loc_1800057AC
0x1800057c5  mov     ebx, 8007000Eh
0x1800057ca  mov     rax, [r12]
0x1800057ce  mov     rcx, r12
0x1800057d1  mov     rax, [rax+10h]
0x1800057d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057da  test    ebx, ebx
0x1800057dc  js      loc_180005888
0x1800057e2  mov     [r14], rdi
0x1800057e5  mov     rcx, rdi
0x1800057e8  mov     rax, [rdi]
0x1800057eb  mov     rax, [rax+8]
0x1800057ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057f4  jmp     loc_180005888
0x1800057f9  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800057fe  mov     ebx, 40000h
0x180005803  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005808  mov     rsi, rax
0x18000580b  test    rax, rax
0x18000580e  jz      short loc_1800057E2
0x180005810  lea     rdx, [rsp+530h+var_4E8]; ppenum
0x180005815  mov     [rsp+530h+var_4E8], r15
0x18000581a  lea     rcx, CLSID_CPackage; clsid
0x180005821  mov     [rsp+530h+uId], r15d
0x180005826  call    cs:__imp_OleRegEnumVerbs
0x18000582c  test    eax, eax
0x18000582e  js      short loc_18000585F
0x180005830  mov     rcx, [rsp+530h+var_4E8]
0x180005835  lea     r9, [rsp+530h+uId]
0x18000583a  mov     r8, rsi
0x18000583d  mov     edx, 3
0x180005842  mov     rax, [rcx]
0x180005845  mov     rax, [rax+18h]
0x180005849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000584e  mov     rcx, [rsp+530h+var_4E8]
0x180005853  mov     rax, [rcx]
0x180005856  mov     rax, [rax+10h]
0x18000585a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000585f  mov     r8d, [rsp+530h+uId]; unsigned int
0x180005864  mov     rdx, rsi; struct tagOLEVERB *
0x180005867  mov     rcx, rdi; this
0x18000586a  call    ?InitVerbEnum@CPackage@@IEAAJPEAUtagOLEVERB@@K@Z; CPackage::InitVerbEnum(tagOLEVERB *,ulong)
0x18000586f  mov     ebx, eax
0x180005871  test    eax, eax
0x180005873  jns     loc_1800057E2
0x180005879  mov     rcx, rsi; lpMem
0x18000587c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005881  jmp     short loc_180005888
0x180005883  mov     ebx, 80070057h
0x180005888  mov     eax, ebx
0x18000588a  mov     rcx, [rbp+430h+var_40]
0x180005891  xor     rcx, rsp; StackCookie
0x180005894  call    __security_check_cookie
0x180005899  mov     rbx, [rsp+530h+arg_10]
0x1800058a1  add     rsp, 500h
0x1800058a8  pop     r15
0x1800058aa  pop     r14
0x1800058ac  pop     r13
0x1800058ae  pop     r12
0x1800058b0  pop     rdi
0x1800058b1  pop     rsi
0x1800058b2  pop     rbp
0x1800058b3  retn
```
