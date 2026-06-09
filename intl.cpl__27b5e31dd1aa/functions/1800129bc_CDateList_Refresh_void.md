# CDateList::_Refresh(void)

- ea: `0x1800129bc`
- end: `0x180012b4f`
- name: `?_Refresh@CDateList@@AEAAXXZ`
- size: `403`
- prototype: `void __fastcall(CDateList *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180012950`

## callees

- `0x1800129bc`
- `0x180018924`
- `0x180018980`
- `0x18002a112`
- `0x18002a150`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180012a0e`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180012a96`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180012ae0`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180012a0e`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180012a96`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180012ae0`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x180012ac4`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x180012ac4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012b00`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012b00`
- `api-ms-win-core-localization-l2-1-0!EnumCalendarInfoExEx` at `0x180012a33`
- `api-ms-win-core-localization-l2-1-0!EnumCalendarInfoExEx` at `0x180012a6c`
- `api-ms-win-core-localization-l2-1-0!EnumCalendarInfoExEx` at `0x180012a33`
- `api-ms-win-core-localization-l2-1-0!EnumCalendarInfoExEx` at `0x180012a6c`

## pseudocode

```c
void __fastcall CDateList::_Refresh(CDateList *this)
{
  const WCHAR *v2; // rcx
  _DWORD *v3; // rax
  WCHAR LCData[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t v5[6]; // [rsp+34h] [rbp-CCh] BYREF
  WCHAR v6[80]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR LocaleName[88]; // [rsp+E0h] [rbp-20h] BYREF

  if ( (unsigned int)CListBase::_InitializeList(this) )
  {
    v2 = (const WCHAR *)*((_QWORD *)this + 5);
    wcscpy(LCData, L"\x01");
    GetLocaleInfoEx(v2, 0x20001009u, LCData, 2);
    EnumCalendarInfoExEx(
      CDateList::_s_FillDatesProc,
      *((LPCWSTR *)this + 5),
      *(CALID *)LCData,
      0,
      *((_DWORD *)this + 6),
      (LPARAM)this);
    v3 = (_DWORD *)*((_QWORD *)this + 1);
    if ( (!v3 || !*v3) && *(_DWORD *)LCData != 1 )
      EnumCalendarInfoExEx(
        CDateList::_s_FillDatesProc,
        *((LPCWSTR *)this + 5),
        1u,
        0,
        *((_DWORD *)this + 6),
        (LPARAM)this);
    memset_0(v6, 0, sizeof(v6));
    if ( GetLocaleInfoEx(*((LPCWSTR *)this + 5), *((_DWORD *)this + 7), v6, 80) > 0
      && !CListBase::_SelectDefaultItem(this, v6) )
    {
      wcscpy(v5, L"\x01");
      if ( GetUserDefaultLocaleName(LocaleName, 85) )
      {
        if ( GetLocaleInfoEx(0, 0x20001009u, v5, 2)
          && CompareStringOrdinal(LocaleName, -1, *((LPCWCH *)this + 5), -1, 0) == 2
          && *(_DWORD *)v5 == *(_DWORD *)LCData )
        {
          (*(void (__fastcall **)(CDateList *, WCHAR *, __int64))(*(_QWORD *)this + 40LL))(this, v6, 1);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800129bc  mov     [rsp-8+arg_8], rbx
0x1800129c1  push    rbp
0x1800129c2  lea     rbp, [rsp-0A0h]
0x1800129ca  sub     rsp, 1A0h
0x1800129d1  mov     rax, cs:__security_cookie
0x1800129d8  xor     rax, rsp
0x1800129db  mov     [rbp+0A0h+var_10], rax
0x1800129e2  mov     rbx, rcx
0x1800129e5  call    ?_InitializeList@CListBase@@IEAAHXZ; CListBase::_InitializeList(void)
0x1800129ea  test    eax, eax
0x1800129ec  jz      loc_180012B2F
0x1800129f2  mov     rcx, [rbx+28h]; lpLocaleName
0x1800129f6  lea     r8, [rsp+1A0h+LCData]; lpLCData
0x1800129fb  mov     r9d, 2; cchData
0x180012a01  mov     dword ptr [rsp+1A0h+LCData], 1
0x180012a09  mov     edx, 20001009h; LCType
0x180012a0e  call    cs:__imp_GetLocaleInfoEx
0x180012a14  mov     eax, [rbx+18h]
0x180012a17  lea     rcx, ?_s_FillDatesProc@CDateList@@CAHPEAGK0_J@Z; pCalInfoEnumProcExEx
0x180012a1e  mov     r8d, dword ptr [rsp+1A0h+LCData]; Calendar
0x180012a23  xor     r9d, r9d; lpReserved
0x180012a26  mov     rdx, [rbx+28h]; lpLocaleName
0x180012a2a  mov     [rsp+1A0h+lParam], rbx; lParam
0x180012a2f  mov     [rsp+1A0h+CalType], eax; CalType
0x180012a33  call    cs:__imp_EnumCalendarInfoExEx
0x180012a39  mov     rax, [rbx+8]
0x180012a3d  test    rax, rax
0x180012a40  jz      short loc_180012A47
0x180012a42  cmp     dword ptr [rax], 0
0x180012a45  jnz     short loc_180012A72
0x180012a47  cmp     dword ptr [rsp+1A0h+LCData], 1
0x180012a4c  jz      short loc_180012A72
0x180012a4e  mov     eax, [rbx+18h]
0x180012a51  lea     rcx, ?_s_FillDatesProc@CDateList@@CAHPEAGK0_J@Z; pCalInfoEnumProcExEx
0x180012a58  mov     rdx, [rbx+28h]; lpLocaleName
0x180012a5c  xor     r9d, r9d; lpReserved
0x180012a5f  mov     [rsp+1A0h+lParam], rbx; lParam
0x180012a64  mov     [rsp+1A0h+CalType], eax; CalType
0x180012a68  lea     r8d, [r9+1]; Calendar
0x180012a6c  call    cs:__imp_EnumCalendarInfoExEx
0x180012a72  xor     edx, edx; Val
0x180012a74  lea     rcx, [rsp+1A0h+var_160]; void *
0x180012a79  mov     r8d, 0A0h; Size
0x180012a7f  call    memset_0
0x180012a84  mov     edx, [rbx+1Ch]; LCType
0x180012a87  lea     r8, [rsp+1A0h+var_160]; lpLCData
0x180012a8c  mov     rcx, [rbx+28h]; lpLocaleName
0x180012a90  mov     r9d, 50h ; 'P'; cchData
0x180012a96  call    cs:__imp_GetLocaleInfoEx
0x180012a9c  test    eax, eax
0x180012a9e  jle     loc_180012B2F
0x180012aa4  lea     rdx, [rsp+1A0h+var_160]; unsigned __int16 *
0x180012aa9  mov     rcx, rbx; this
0x180012aac  call    ?_SelectDefaultItem@CListBase@@IEAAHPEBG@Z; CListBase::_SelectDefaultItem(ushort const *)
0x180012ab1  test    eax, eax
0x180012ab3  jnz     short loc_180012B2F
0x180012ab5  lea     edx, [rax+55h]; cchLocaleName
0x180012ab8  mov     dword ptr [rsp+1A0h+var_16C], 1
0x180012ac0  lea     rcx, [rbp+0A0h+LocaleName]; lpLocaleName
0x180012ac4  call    cs:__imp_GetUserDefaultLocaleName
0x180012aca  test    eax, eax
0x180012acc  jz      short loc_180012B2F
0x180012ace  mov     r9d, 2; cchData
0x180012ad4  lea     r8, [rsp+1A0h+var_16C]; lpLCData
0x180012ad9  mov     edx, 20001009h; LCType
0x180012ade  xor     ecx, ecx; lpLocaleName
0x180012ae0  call    cs:__imp_GetLocaleInfoEx
0x180012ae6  test    eax, eax
0x180012ae8  jz      short loc_180012B2F
0x180012aea  mov     r8, [rbx+28h]; lpString2
0x180012aee  lea     rcx, [rbp+0A0h+LocaleName]; lpString1
0x180012af2  or      edx, 0FFFFFFFFh; cchCount1
0x180012af5  mov     [rsp+1A0h+CalType], 0; bIgnoreCase
0x180012afd  mov     r9d, edx; cchCount2
0x180012b00  call    cs:__imp_CompareStringOrdinal
0x180012b06  cmp     eax, 2
0x180012b09  jnz     short loc_180012B2F
0x180012b0b  mov     eax, dword ptr [rsp+1A0h+LCData]
0x180012b0f  cmp     dword ptr [rsp+1A0h+var_16C], eax
0x180012b13  jnz     short loc_180012B2F
0x180012b15  mov     rax, [rbx]
0x180012b18  lea     rdx, [rsp+1A0h+var_160]
0x180012b1d  mov     r8d, 1
0x180012b23  mov     rcx, rbx
0x180012b26  mov     rax, [rax+28h]
0x180012b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b2f  mov     rcx, [rbp+0A0h+var_10]
0x180012b36  xor     rcx, rsp; StackCookie
0x180012b39  call    __security_check_cookie
0x180012b3e  mov     rbx, [rsp+1A0h+arg_8]
0x180012b46  add     rsp, 1A0h
0x180012b4d  pop     rbp
0x180012b4e  retn
```
