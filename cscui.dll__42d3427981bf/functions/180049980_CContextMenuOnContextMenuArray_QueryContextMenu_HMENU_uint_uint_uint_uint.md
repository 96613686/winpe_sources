# CContextMenuOnContextMenuArray::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x180049980`
- end: `0x180049b0a`
- name: `?QueryContextMenu@CContextMenuOnContextMenuArray@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `394`
- prototype: `int(CContextMenuOnContextMenuArray *__hidden this, HMENU, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180049980`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180049a8b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180049a8b`
- `USER32!GetMenuItemCount` at `0x180049a42`
- `USER32!GetMenuItemCount` at `0x180049a42`
- `USER32!InsertMenuW` at `0x1800499d0`
- `USER32!InsertMenuW` at `0x1800499d0`
- `USER32!GetMenuStringW` at `0x180049a75`
- `USER32!GetMenuStringW` at `0x180049a75`
- `USER32!DeleteMenu` at `0x180049adb`
- `USER32!DeleteMenu` at `0x180049adb`

## pseudocode

```c
__int64 __fastcall CContextMenuOnContextMenuArray::QueryContextMenu(
        CContextMenuOnContextMenuArray *this,
        HMENU a2,
        UINT a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  unsigned int v6; // ebx
  UINT v7; // r14d
  __int64 v10; // rsi
  int v11; // r15d
  int v12; // eax
  int v13; // ecx
  unsigned int v14; // eax
  int MenuItemCount; // ecx
  int i; // ebp
  UINT v17; // r13d
  int v19; // [rsp+40h] [rbp-E8h]
  WCHAR String[64]; // [rsp+50h] [rbp-D8h] BYREF

  v6 = a4;
  v7 = a3;
  *((_DWORD *)this + 15) = a4;
  if ( InsertMenuW(a2, a3, 0x400u, 0, L"{44075D61-2050-4DF4-BC5D-CBA88A84E75B}") )
  {
    v10 = 0;
    v11 = 1;
    if ( !*((_DWORD *)this + 14) )
      goto LABEL_16;
    do
    {
      if ( v6 >= a5 )
        break;
      v12 = (*(__int64 (__fastcall **)(CContextMenuOnContextMenuArray *, _QWORD, HMENU, _QWORD, unsigned int, unsigned int, unsigned int))(*(_QWORD *)this + 64LL))(
              this,
              (unsigned int)v10,
              a2,
              v7,
              v6,
              a5,
              a6);
      if ( v12 < 0 )
      {
        if ( (_DWORD)v10 )
        {
          *((_DWORD *)this + v10 + 16) = *((_DWORD *)this + (unsigned int)(v10 - 1) + 16);
        }
        else
        {
          *((_DWORD *)this + v10 + 16) = 0;
          ++v6;
        }
      }
      else
      {
        v11 = 0;
        v13 = (__int16)v12 + 1;
        v14 = v6 + (__int16)v12 - *((_DWORD *)this + 15);
        v6 += v13;
        *((_DWORD *)this + v10 + 16) = v14;
        MenuItemCount = GetMenuItemCount(a2);
        v19 = MenuItemCount;
        for ( i = 0; i < MenuItemCount; ++i )
        {
          v17 = (v7 + i) % MenuItemCount;
          if ( GetMenuStringW(a2, v17, String, 60, 0x400u)
            && !lstrcmpW(String, L"{44075D61-2050-4DF4-BC5D-CBA88A84E75B}") )
          {
            v7 = v17;
            v11 = 1;
            break;
          }
          MenuItemCount = v19;
        }
      }
      v10 = (unsigned int)(v10 + 1);
    }
    while ( (unsigned int)v10 < *((_DWORD *)this + 14) );
    if ( v11 )
LABEL_16:
      DeleteMenu(a2, v7, 0x400u);
  }
  return v6 - *((_DWORD *)this + 15);
}

```

## disassembly

```asm
0x180049980  push    rbx
0x180049982  push    rbp
0x180049983  push    rsi
0x180049984  push    rdi
0x180049985  push    r12
0x180049987  push    r13
0x180049989  push    r14
0x18004998b  push    r15
0x18004998d  sub     rsp, 0E8h
0x180049994  mov     rax, cs:__security_cookie
0x18004999b  xor     rax, rsp
0x18004999e  mov     [rsp+128h+var_58], rax
0x1800499a6  mov     ebx, r9d
0x1800499a9  lea     rax, NewItem; "{44075D61-2050-4DF4-BC5D-CBA88A84E75B}"
0x1800499b0  mov     r14d, r8d
0x1800499b3  mov     [rcx+3Ch], ebx
0x1800499b6  mov     r12, rdx
0x1800499b9  mov     [rsp+128h+lpNewItem], rax; lpNewItem
0x1800499be  mov     rdi, rcx
0x1800499c1  xor     r9d, r9d; uIDNewItem
0x1800499c4  mov     rcx, r12; hMenu
0x1800499c7  mov     r8d, 400h; uFlags
0x1800499cd  mov     edx, r14d; uPosition
0x1800499d0  call    cs:__imp_InsertMenuW
0x1800499d6  test    eax, eax
0x1800499d8  jz      loc_180049AE1
0x1800499de  xor     esi, esi
0x1800499e0  lea     r15d, [rsi+1]
0x1800499e4  cmp     [rdi+38h], esi
0x1800499e7  jbe     loc_180049ACF
0x1800499ed  mov     ecx, [rsp+128h+arg_20]
0x1800499f4  cmp     ebx, ecx
0x1800499f6  jnb     loc_180049ACA
0x1800499fc  mov     edx, [rsp+128h+arg_28]
0x180049a03  mov     r9d, r14d
0x180049a06  mov     rax, [rdi]
0x180049a09  mov     r8, r12
0x180049a0c  mov     [rsp+128h+var_F8], edx
0x180049a10  mov     edx, esi
0x180049a12  mov     [rsp+128h+var_100], ecx
0x180049a16  mov     rcx, rdi
0x180049a19  mov     dword ptr [rsp+128h+lpNewItem], ebx
0x180049a1d  mov     rax, [rax+40h]
0x180049a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a26  test    eax, eax
0x180049a28  js      short loc_180049AA8
0x180049a2a  movsx   ecx, ax
0x180049a2d  xor     r15d, r15d
0x180049a30  mov     eax, ecx
0x180049a32  inc     ecx
0x180049a34  sub     eax, [rdi+3Ch]
0x180049a37  add     eax, ebx
0x180049a39  add     ebx, ecx
0x180049a3b  mov     rcx, r12; hMenu
0x180049a3e  mov     [rdi+rsi*4+40h], eax
0x180049a42  call    cs:__imp_GetMenuItemCount
0x180049a48  mov     ecx, eax
0x180049a4a  mov     [rsp+128h+var_E8], eax
0x180049a4e  xor     ebp, ebp
0x180049a50  cmp     ebp, ecx
0x180049a52  jge     short loc_180049ABF
0x180049a54  lea     eax, [r14+rbp]
0x180049a58  mov     dword ptr [rsp+128h+lpNewItem], 400h; flags
0x180049a60  xor     edx, edx; uIDItem
0x180049a62  lea     r8, [rsp+128h+String]; lpString
0x180049a67  div     ecx
0x180049a69  mov     r9d, 3Ch ; '<'; cchMax
0x180049a6f  mov     rcx, r12; hMenu
0x180049a72  mov     r13d, edx
0x180049a75  call    cs:__imp_GetMenuStringW
0x180049a7b  test    eax, eax
0x180049a7d  jz      short loc_180049A95
0x180049a7f  lea     rdx, NewItem; "{44075D61-2050-4DF4-BC5D-CBA88A84E75B}"
0x180049a86  lea     rcx, [rsp+128h+String]; lpString1
0x180049a8b  call    cs:__imp_lstrcmpW
0x180049a91  test    eax, eax
0x180049a93  jz      short loc_180049A9D
0x180049a95  mov     ecx, [rsp+128h+var_E8]
0x180049a99  inc     ebp
0x180049a9b  jmp     short loc_180049A50
0x180049a9d  mov     r14d, r13d
0x180049aa0  mov     r15d, 1
0x180049aa6  jmp     short loc_180049ABF
0x180049aa8  test    esi, esi
0x180049aaa  jnz     short loc_180049AB4
0x180049aac  mov     [rdi+rsi*4+40h], esi
0x180049ab0  inc     ebx
0x180049ab2  jmp     short loc_180049ABF
0x180049ab4  lea     eax, [rsi-1]
0x180049ab7  mov     eax, [rdi+rax*4+40h]
0x180049abb  mov     [rdi+rsi*4+40h], eax
0x180049abf  inc     esi
0x180049ac1  cmp     esi, [rdi+38h]
0x180049ac4  jb      loc_1800499ED
0x180049aca  test    r15d, r15d
0x180049acd  jz      short loc_180049AE1
0x180049acf  mov     r8d, 400h; uFlags
0x180049ad5  mov     edx, r14d; uPosition
0x180049ad8  mov     rcx, r12; hMenu
0x180049adb  call    cs:__imp_DeleteMenu
0x180049ae1  sub     ebx, [rdi+3Ch]
0x180049ae4  mov     eax, ebx
0x180049ae6  mov     rcx, [rsp+128h+var_58]
0x180049aee  xor     rcx, rsp; StackCookie
0x180049af1  call    __security_check_cookie
0x180049af6  add     rsp, 0E8h
0x180049afd  pop     r15
0x180049aff  pop     r14
0x180049b01  pop     r13
0x180049b03  pop     r12
0x180049b05  pop     rdi
0x180049b06  pop     rsi
0x180049b07  pop     rbp
0x180049b08  pop     rbx
0x180049b09  retn
```
