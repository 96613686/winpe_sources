# netDbGetCompInfo

- ea: `0x1800290a0`
- end: `0x180029342`
- name: `netDbGetCompInfo`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002990c`

## callees

- `0x180026710`
- `0x1800290a0`
- `0x1800293dc`
- `0x180029fc0`
- `0x18002c1b0`
- `0x18002f376`
- `0x18002f3b0`
- `0x180030010`

## import_xrefs

- `USER32!GetActiveWindow` at `0x18002914a`
- `USER32!GetActiveWindow` at `0x18002914a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800292f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800292fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029305`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800292f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800292fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029305`

## string_xrefs

- `0x18002930e`: `GetCompInfo: fail %S`

## pseudocode

```c
__int64 __fastcall netDbGetCompInfo(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  LPVOID *v7; // r14
  __int64 (__fastcall *v8)(__int64 *, HWND, __int64, _QWORD); // rbx
  HWND ActiveWindow; // rax
  unsigned int i; // ebx
  int v11; // eax
  bool v12; // zf
  __int64 v13; // rax
  BOOL v14; // ebx
  int v16; // [rsp+30h] [rbp-48h] BYREF
  int v17; // [rsp+34h] [rbp-44h] BYREF
  __int128 Buf1; // [rsp+38h] [rbp-40h] BYREF

  v3 = *a1;
  v16 = 0;
  Buf1 = 0;
  if ( (*(int (__fastcall **)(__int64 *, int *))(v3 + 56))(a1, &v16) < 0 )
    return 0;
  if ( (v16 & 8) != 0 )
    return 0;
  v7 = (LPVOID *)(a2 + 8);
  if ( (*(int (__fastcall **)(__int64 *, __int64))(*a1 + 24))(a1, a2 + 8) < 0 )
    return 0;
  v12 = (v16 & 0x80) == 0;
  *(_DWORD *)(a2 + 36) = (v16 & 0x80) != 0;
  if ( !v12 )
  {
    v8 = *(__int64 (__fastcall **)(__int64 *, HWND, __int64, _QWORD))(*a1 + 112);
    ActiveWindow = GetActiveWindow();
    *(_DWORD *)(a2 + 36) = v8(a1, ActiveWindow, 1, 0) == 0;
  }
  if ( (*(int (__fastcall **)(__int64 *, __int128 *))(*a1 + 80))(a1, &Buf1) < 0
    || (*(int (__fastcall **)(__int64 *, __int64))(*a1 + 48))(a1, a2 + 24) < 0
    || (*(int (__fastcall **)(__int64 *, __int64))(*a1 + 40))(a1, a2 + 16) < 0 )
  {
    CoTaskMemFree(*(LPVOID *)(a2 + 24));
    CoTaskMemFree(*(LPVOID *)(a2 + 16));
    CoTaskMemFree(*v7);
    DbgOutputTrace("GetCompInfo: fail %S", (const wchar_t *)*v7);
    return 0;
  }
  if ( !memcmp_0(&Buf1, &GUID_DEVCLASS_NETCLIENT, 0x10u) )
    *(_DWORD *)a2 = 2;
  else
    *(_DWORD *)a2 = memcmp_0(&Buf1, &GUID_DEVCLASS_NETSERVICE, 0x10u) != 0 ? 4 : 1;
  *(_DWORD *)(a2 + 52) = -268435456;
  for ( i = 0; i < 4; ++i )
  {
    if ( !(unsigned int)CompareStringWrapW(*(PCNZWCH *)(a2 + 24), (&off_180034970)[2 * i]) )
    {
      *(_DWORD *)(a2 + 52) = *((_DWORD *)&off_180034970 + 4 * i + 2);
      break;
    }
  }
  if ( *(_DWORD *)(a2 + 52) == -268435456 )
    return 0;
  if ( *(_DWORD *)a2 != 4 )
  {
    if ( *(_DWORD *)a2 == 1 )
    {
      svcGetEnabling(a2 + 56);
      *(_DWORD *)(a2 + 60) = *(_DWORD *)(a2 + 56);
    }
    goto LABEL_28;
  }
  netDbLoadProtcolInfo(a2);
  if ( *(_DWORD *)(a2 + 52) == 1 )
  {
    v11 = 0;
    v12 = *(_DWORD *)(a3 + 48) == 0;
  }
  else
  {
    v11 = 0;
    if ( *(_DWORD *)(a2 + 52) != 2 )
      goto LABEL_24;
    v12 = *(_DWORD *)(a3 + 52) == 0;
  }
  LOBYTE(v11) = v12;
LABEL_24:
  *(_DWORD *)(a2 + 48) = v11;
  if ( v11 )
    *(_DWORD *)(a2 + 56) = 0;
LABEL_28:
  *(_DWORD *)(a2 + 32) = 1;
  *(_QWORD *)(a2 + 40) = a1;
  (*(void (__fastcall **)(__int64 *))(*a1 + 8))(a1);
  v13 = *a1;
  v17 = 0;
  v14 = 1;
  if ( (*(int (__fastcall **)(__int64 *, int *))(v13 + 56))(a1, &v17) >= 0 )
    v14 = (v17 & 0x20) == 0;
  *(_DWORD *)(a2 + 84) = v14;
  return 1;
}

```

## disassembly

```asm
0x1800290a0  mov     [rsp+arg_10], rbx
0x1800290a5  mov     [rsp+arg_18], rbp
0x1800290aa  push    rsi
0x1800290ab  push    rdi
0x1800290ac  push    r13
0x1800290ae  push    r14
0x1800290b0  push    r15
0x1800290b2  sub     rsp, 50h
0x1800290b6  mov     rax, cs:__security_cookie
0x1800290bd  xor     rax, rsp
0x1800290c0  mov     [rsp+78h+var_30], rax
0x1800290c5  mov     rax, [rcx]
0x1800290c8  xorps   xmm0, xmm0
0x1800290cb  mov     rdi, rdx
0x1800290ce  mov     [rsp+78h+var_48], 0
0x1800290d6  movups  [rsp+78h+Buf1], xmm0
0x1800290db  lea     rdx, [rsp+78h+var_48]
0x1800290e0  mov     rbp, r8
0x1800290e3  mov     rax, [rax+38h]
0x1800290e7  mov     rsi, rcx
0x1800290ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290ef  test    eax, eax
0x1800290f1  js      loc_18002931A
0x1800290f7  test    byte ptr [rsp+78h+var_48], 8
0x1800290fc  jnz     loc_18002931A
0x180029102  mov     rax, [rsi]
0x180029105  lea     r14, [rdi+8]
0x180029109  mov     rdx, r14
0x18002910c  mov     rcx, rsi
0x18002910f  mov     rax, [rax+18h]
0x180029113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029118  test    eax, eax
0x18002911a  js      loc_18002931A
0x180029120  test    [rsp+78h+var_48], 80h
0x180029128  mov     eax, 0
0x18002912d  mov     r13d, 1
0x180029133  setnz   al
0x180029136  test    [rsp+78h+var_48], 80h
0x18002913e  mov     [rdi+24h], eax
0x180029141  jz      short loc_18002916E
0x180029143  mov     rax, [rsi]
0x180029146  mov     rbx, [rax+70h]
0x18002914a  call    cs:__imp_GetActiveWindow
0x180029150  xor     r9d, r9d
0x180029153  mov     r8d, r13d
0x180029156  mov     rdx, rax
0x180029159  mov     rcx, rsi
0x18002915c  mov     rax, rbx
0x18002915f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029164  xor     ecx, ecx
0x180029166  test    eax, eax
0x180029168  setz    cl
0x18002916b  mov     [rdi+24h], ecx
0x18002916e  mov     rax, [rsi]
0x180029171  lea     rdx, [rsp+78h+Buf1]
0x180029176  mov     rcx, rsi
0x180029179  mov     rax, [rax+50h]
0x18002917d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029182  test    eax, eax
0x180029184  js      loc_1800292EE
0x18002918a  mov     rax, [rsi]
0x18002918d  lea     rdx, [rdi+18h]
0x180029191  mov     rcx, rsi
0x180029194  mov     rax, [rax+30h]
0x180029198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002919d  test    eax, eax
0x18002919f  js      loc_1800292EE
0x1800291a5  mov     rax, [rsi]
0x1800291a8  lea     rdx, [rdi+10h]
0x1800291ac  mov     rcx, rsi
0x1800291af  mov     rax, [rax+28h]
0x1800291b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291b8  test    eax, eax
0x1800291ba  js      loc_1800292EE
0x1800291c0  mov     ebx, 10h
0x1800291c5  lea     rdx, GUID_DEVCLASS_NETCLIENT; Buf2
0x1800291cc  mov     r8d, ebx; Size
0x1800291cf  lea     rcx, [rsp+78h+Buf1]; Buf1
0x1800291d4  call    memcmp_0
0x1800291d9  test    eax, eax
0x1800291db  jnz     short loc_1800291E5
0x1800291dd  mov     dword ptr [rdi], 2
0x1800291e3  jmp     short loc_180029205
0x1800291e5  mov     r8, rbx; Size
0x1800291e8  lea     rdx, GUID_DEVCLASS_NETSERVICE; Buf2
0x1800291ef  lea     rcx, [rsp+78h+Buf1]; Buf1
0x1800291f4  call    memcmp_0
0x1800291f9  neg     eax
0x1800291fb  sbb     ecx, ecx
0x1800291fd  and     ecx, 3
0x180029200  add     ecx, r13d
0x180029203  mov     [rdi], ecx
0x180029205  mov     dword ptr [rdi+34h], 0F0000000h
0x18002920c  lea     rax, off_180034970; "ms_tcpip"
0x180029213  xor     ebx, ebx
0x180029215  cmp     ebx, 4
0x180029218  jnb     short loc_180029245
0x18002921a  mov     rcx, [rdi+18h]; lpString1
0x18002921e  mov     r14d, ebx
0x180029221  add     r14, r14
0x180029224  mov     rdx, [rax+r14*8]; lpString2
0x180029228  call    CompareStringWrapW
0x18002922d  test    eax, eax
0x18002922f  lea     rax, off_180034970; "ms_tcpip"
0x180029236  jz      short loc_18002923D
0x180029238  add     ebx, r13d
0x18002923b  jmp     short loc_180029215
0x18002923d  mov     eax, [rax+r14*8+8]
0x180029242  mov     [rdi+34h], eax
0x180029245  cmp     dword ptr [rdi+34h], 0F0000000h
0x18002924c  jz      loc_18002931A
0x180029252  cmp     dword ptr [rdi], 4
0x180029255  jnz     short loc_18002928B
0x180029257  mov     rcx, rdi
0x18002925a  call    netDbLoadProtcolInfo
0x18002925f  mov     ecx, [rdi+34h]
0x180029262  sub     ecx, r13d
0x180029265  jz      short loc_180029273
0x180029267  xor     eax, eax
0x180029269  cmp     ecx, r13d
0x18002926c  jnz     short loc_18002927B
0x18002926e  cmp     [rbp+34h], eax
0x180029271  jmp     short loc_180029278
0x180029273  xor     eax, eax
0x180029275  cmp     [rbp+30h], eax
0x180029278  setz    al
0x18002927b  mov     [rdi+30h], eax
0x18002927e  test    eax, eax
0x180029280  jz      short loc_18002929F
0x180029282  mov     dword ptr [rdi+38h], 0
0x180029289  jmp     short loc_18002929F
0x18002928b  cmp     [rdi], r13d
0x18002928e  jnz     short loc_18002929F
0x180029290  lea     rcx, [rdi+38h]
0x180029294  call    svcGetEnabling
0x180029299  mov     eax, [rdi+38h]
0x18002929c  mov     [rdi+3Ch], eax
0x18002929f  mov     [rdi+20h], r13d
0x1800292a3  mov     rcx, rsi
0x1800292a6  mov     [rdi+28h], rsi
0x1800292aa  mov     rax, [rsi]
0x1800292ad  mov     rax, [rax+8]
0x1800292b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292b6  mov     rax, [rsi]
0x1800292b9  lea     rdx, [rsp+78h+var_44]
0x1800292be  mov     [rsp+78h+var_44], 0
0x1800292c6  mov     rcx, rsi
0x1800292c9  mov     ebx, r13d
0x1800292cc  mov     rax, [rax+38h]
0x1800292d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292d5  test    eax, eax
0x1800292d7  js      short loc_1800292E6
0x1800292d9  test    byte ptr [rsp+78h+var_44], 20h
0x1800292de  mov     ecx, 0
0x1800292e3  cmovnz  ebx, ecx
0x1800292e6  mov     [rdi+54h], ebx
0x1800292e9  mov     eax, r13d
0x1800292ec  jmp     short loc_18002931C
0x1800292ee  mov     rcx, [rdi+18h]; pv
0x1800292f2  call    cs:__imp_CoTaskMemFree
0x1800292f8  mov     rcx, [rdi+10h]; pv
0x1800292fc  call    cs:__imp_CoTaskMemFree
0x180029302  mov     rcx, [r14]; pv
0x180029305  call    cs:__imp_CoTaskMemFree
0x18002930b  mov     rdx, [r14]
0x18002930e  lea     rcx, aGetcompinfoFai; "GetCompInfo: fail %S"
0x180029315  call    DbgOutputTrace
0x18002931a  xor     eax, eax
0x18002931c  mov     rcx, [rsp+78h+var_30]
0x180029321  xor     rcx, rsp; StackCookie
0x180029324  call    __security_check_cookie
0x180029329  lea     r11, [rsp+78h+var_28]
0x18002932e  mov     rbx, [r11+40h]
0x180029332  mov     rbp, [r11+48h]
0x180029336  mov     rsp, r11
0x180029339  pop     r15
0x18002933b  pop     r14
0x18002933d  pop     r13
0x18002933f  pop     rdi
0x180029340  pop     rsi
0x180029341  retn
```
