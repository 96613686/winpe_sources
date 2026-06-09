# IsolationAwareCreatePropertySheetPageW

- ea: `0x180014008`
- end: `0x18001410c`
- name: `IsolationAwareCreatePropertySheetPageW`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800133c0`

## callees

- `0x1800071a0`
- `0x180008b74`
- `0x180014008`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800140f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019167`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800140f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800140cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001913b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800140cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001913b`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800140e6`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180019155`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800140e6`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180019155`

## string_xrefs

- `0x180014061`: `CreatePropertySheetPageW`

## pseudocode

```c
__int64 __fastcall IsolationAwareCreatePropertySheetPageW(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  __int64 v5; // rax
  int v6; // eax
  int v7; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  v3 = `IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  if ( v3 )
    goto LABEL_8;
  v5 = PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("CreatePropertySheetPageW");
  if ( v5 )
  {
    `IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn = v5;
LABEL_8:
    v6 = *(_DWORD *)(a1 + 4);
    if ( (v6 & 0x4000) == 0 && *(_DWORD *)a1 >= 0x60u )
    {
      *(_DWORD *)(a1 + 4) = v6 | 0x4000;
      *(_QWORD *)(a1 + 88) = WinbaseIsolationAwarePrivateT_UnPgpgk;
    }
    v2 = ((__int64 (__fastcall *)(__int64))`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(a1);
  }
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v2 )
    {
      v7 = 0;
      LastError = 0;
    }
    else
    {
      v7 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v7 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x180014008  mov     rax, rsp
0x18001400b  mov     [rax+10h], rbx
0x18001400f  mov     [rax+18h], rsi
0x180014013  push    rdi
0x180014014  sub     rsp, 30h
0x180014018  mov     rdi, rcx
0x18001401b  xor     ebx, ebx
0x18001401d  mov     [rax-18h], rbx
0x180014021  mov     rsi, cs:?s_pfn@?1??IsolationAwareCreatePropertySheetPageW@@9@4P6APEAU_PSP@@PEBU_PROPSHEETPAGEW@@@ZEA; _PSP * (*`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(_PROPSHEETPAGEW const *)
0x180014028  mov     [rax+8], rbx
0x18001402c  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, ebx
0x180014032  jnz     short loc_18001405C
0x180014034  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, ebx
0x18001403a  jnz     short loc_18001405C
0x18001403c  lea     rcx, [rax+8]; lpCookie
0x180014040  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180014045  test    eax, eax
0x180014047  jnz     short loc_18001405C
0x180014049  xor     eax, eax
0x18001404b  mov     rbx, [rsp+38h+arg_8]
0x180014050  mov     rsi, [rsp+38h+arg_10]
0x180014055  add     rsp, 30h
0x180014059  pop     rdi
0x18001405a  retn
0x18001405c  test    rsi, rsi
0x18001405f  jnz     short loc_180014079
0x180014061  lea     rcx, aCreateproperty; "CreatePropertySheetPageW"
0x180014068  call    PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18001406d  test    rax, rax
0x180014070  jz      short loc_1800140B1
0x180014072  mov     cs:?s_pfn@?1??IsolationAwareCreatePropertySheetPageW@@9@4P6APEAU_PSP@@PEBU_PROPSHEETPAGEW@@@ZEA, rax; _PSP * (*`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(_PROPSHEETPAGEW const *)
0x180014079  mov     eax, [rdi+4]
0x18001407c  mov     ecx, 4000h
0x180014081  test    ecx, eax
0x180014083  jnz     short loc_18001409A
0x180014085  cmp     dword ptr [rdi], 60h ; '`'
0x180014088  jb      short loc_18001409A
0x18001408a  or      eax, ecx
0x18001408c  mov     [rdi+4], eax
0x18001408f  mov     rax, cs:WinbaseIsolationAwarePrivateT_UnPgpgk
0x180014096  mov     [rdi+58h], rax
0x18001409a  mov     rcx, rdi
0x18001409d  mov     rax, cs:?s_pfn@?1??IsolationAwareCreatePropertySheetPageW@@9@4P6APEAU_PSP@@PEBU_PROPSHEETPAGEW@@@ZEA; _PSP * (*`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(_PROPSHEETPAGEW const *)
0x1800140a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140a9  mov     rbx, rax
0x1800140ac  mov     [rsp+38h+var_18], rax
0x1800140b1  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800140b8  jz      short loc_1800140C3
0x1800140ba  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800140c1  jnz     short loc_180014104
0x1800140c3  test    rbx, rbx
0x1800140c6  jnz     short loc_1800140DB
0x1800140c8  lea     esi, [rbx+1]
0x1800140cb  call    cs:__imp_GetLastError
0x1800140d2  nop     dword ptr [rax+rax+00h]
0x1800140d7  mov     edi, eax
0x1800140d9  jmp     short loc_1800140DF
0x1800140db  xor     esi, esi
0x1800140dd  xor     edi, edi
0x1800140df  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x1800140e4  xor     ecx, ecx; dwFlags
0x1800140e6  call    cs:__imp_DeactivateActCtx
0x1800140ed  nop     dword ptr [rax+rax+00h]
0x1800140f2  test    esi, esi
0x1800140f4  jz      short loc_180014104
0x1800140f6  mov     ecx, edi; dwErrCode
0x1800140f8  call    cs:__imp_SetLastError
0x1800140ff  nop     dword ptr [rax+rax+00h]
0x180014104  mov     rax, rbx
0x180014107  jmp     loc_18001404B
0x180019112  push    rbx
0x180019114  push    rbp
0x180019115  push    rdi
0x180019116  sub     rsp, 20h
0x18001911a  mov     rbp, rdx
0x18001911d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180019124  jz      short loc_18001912F
0x180019126  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001912d  jnz     short loc_180019174
0x18001912f  cmp     qword ptr [rbp+20h], 0
0x180019134  jnz     short loc_18001914B
0x180019136  mov     edi, 1
0x18001913b  call    cs:__imp_GetLastError
0x180019142  nop     dword ptr [rax+rax+00h]
0x180019147  mov     ebx, eax
0x180019149  jmp     short loc_18001914F
0x18001914b  xor     edi, edi
0x18001914d  xor     ebx, ebx
0x18001914f  mov     rdx, [rbp+40h]; ulCookie
0x180019153  xor     ecx, ecx; dwFlags
0x180019155  call    cs:__imp_DeactivateActCtx
0x18001915c  nop     dword ptr [rax+rax+00h]
0x180019161  test    edi, edi
0x180019163  jz      short loc_180019174
0x180019165  mov     ecx, ebx; dwErrCode
0x180019167  call    cs:__imp_SetLastError
0x18001916e  nop     dword ptr [rax+rax+00h]
0x180019173  nop
0x180019174  add     rsp, 20h
0x180019178  pop     rdi
0x180019179  pop     rbp
0x18001917a  pop     rbx
0x18001917b  retn
```
