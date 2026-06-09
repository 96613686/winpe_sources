# netDbGetCompInfo

- ea: `0x1800371a0`
- end: `0x180037442`
- name: `netDbGetCompInfo`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037a14`

## callees

- `0x1800348f0`
- `0x1800371a0`
- `0x1800374dc`
- `0x1800380d4`
- `0x18003ccb8`
- `0x18004d0c6`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800373f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800373fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037405`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800373f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800373fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037405`
- `USER32!GetActiveWindow` at `0x18003724a`
- `USER32!GetActiveWindow` at `0x18003724a`

## string_xrefs

- `0x18003740e`: `GetCompInfo: fail %S`

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
    if ( !(unsigned int)CompareStringWrapW(*(PCNZWCH *)(a2 + 24), (&off_1800504F0)[2 * i]) )
    {
      *(_DWORD *)(a2 + 52) = *((_DWORD *)&off_1800504F0 + 4 * i + 2);
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
0x1800371a0  mov     [rsp+arg_10], rbx
0x1800371a5  mov     [rsp+arg_18], rbp
0x1800371aa  push    rsi
0x1800371ab  push    rdi
0x1800371ac  push    r13
0x1800371ae  push    r14
0x1800371b0  push    r15
0x1800371b2  sub     rsp, 50h
0x1800371b6  mov     rax, cs:__security_cookie
0x1800371bd  xor     rax, rsp
0x1800371c0  mov     [rsp+78h+var_30], rax
0x1800371c5  mov     rax, [rcx]
0x1800371c8  xorps   xmm0, xmm0
0x1800371cb  mov     rdi, rdx
0x1800371ce  mov     [rsp+78h+var_48], 0
0x1800371d6  movups  [rsp+78h+Buf1], xmm0
0x1800371db  lea     rdx, [rsp+78h+var_48]
0x1800371e0  mov     rbp, r8
0x1800371e3  mov     rax, [rax+38h]
0x1800371e7  mov     rsi, rcx
0x1800371ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371ef  test    eax, eax
0x1800371f1  js      loc_18003741A
0x1800371f7  test    byte ptr [rsp+78h+var_48], 8
0x1800371fc  jnz     loc_18003741A
0x180037202  mov     rax, [rsi]
0x180037205  lea     r14, [rdi+8]
0x180037209  mov     rdx, r14
0x18003720c  mov     rcx, rsi
0x18003720f  mov     rax, [rax+18h]
0x180037213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037218  test    eax, eax
0x18003721a  js      loc_18003741A
0x180037220  test    [rsp+78h+var_48], 80h
0x180037228  mov     eax, 0
0x18003722d  mov     r13d, 1
0x180037233  setnz   al
0x180037236  test    [rsp+78h+var_48], 80h
0x18003723e  mov     [rdi+24h], eax
0x180037241  jz      short loc_18003726E
0x180037243  mov     rax, [rsi]
0x180037246  mov     rbx, [rax+70h]
0x18003724a  call    cs:__imp_GetActiveWindow
0x180037250  xor     r9d, r9d
0x180037253  mov     r8d, r13d
0x180037256  mov     rdx, rax
0x180037259  mov     rcx, rsi
0x18003725c  mov     rax, rbx
0x18003725f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037264  xor     ecx, ecx
0x180037266  test    eax, eax
0x180037268  setz    cl
0x18003726b  mov     [rdi+24h], ecx
0x18003726e  mov     rax, [rsi]
0x180037271  lea     rdx, [rsp+78h+Buf1]
0x180037276  mov     rcx, rsi
0x180037279  mov     rax, [rax+50h]
0x18003727d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037282  test    eax, eax
0x180037284  js      loc_1800373EE
0x18003728a  mov     rax, [rsi]
0x18003728d  lea     rdx, [rdi+18h]
0x180037291  mov     rcx, rsi
0x180037294  mov     rax, [rax+30h]
0x180037298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003729d  test    eax, eax
0x18003729f  js      loc_1800373EE
0x1800372a5  mov     rax, [rsi]
0x1800372a8  lea     rdx, [rdi+10h]
0x1800372ac  mov     rcx, rsi
0x1800372af  mov     rax, [rax+28h]
0x1800372b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372b8  test    eax, eax
0x1800372ba  js      loc_1800373EE
0x1800372c0  mov     ebx, 10h
0x1800372c5  lea     rdx, GUID_DEVCLASS_NETCLIENT; Buf2
0x1800372cc  mov     r8d, ebx; Size
0x1800372cf  lea     rcx, [rsp+78h+Buf1]; Buf1
0x1800372d4  call    memcmp_0
0x1800372d9  test    eax, eax
0x1800372db  jnz     short loc_1800372E5
0x1800372dd  mov     dword ptr [rdi], 2
0x1800372e3  jmp     short loc_180037305
0x1800372e5  mov     r8, rbx; Size
0x1800372e8  lea     rdx, GUID_DEVCLASS_NETSERVICE; Buf2
0x1800372ef  lea     rcx, [rsp+78h+Buf1]; Buf1
0x1800372f4  call    memcmp_0
0x1800372f9  neg     eax
0x1800372fb  sbb     ecx, ecx
0x1800372fd  and     ecx, 3
0x180037300  add     ecx, r13d
0x180037303  mov     [rdi], ecx
0x180037305  mov     dword ptr [rdi+34h], 0F0000000h
0x18003730c  lea     rax, off_1800504F0; "ms_tcpip"
0x180037313  xor     ebx, ebx
0x180037315  cmp     ebx, 4
0x180037318  jnb     short loc_180037345
0x18003731a  mov     rcx, [rdi+18h]; lpString1
0x18003731e  mov     r14d, ebx
0x180037321  add     r14, r14
0x180037324  mov     rdx, [rax+r14*8]; lpString2
0x180037328  call    CompareStringWrapW
0x18003732d  test    eax, eax
0x18003732f  lea     rax, off_1800504F0; "ms_tcpip"
0x180037336  jz      short loc_18003733D
0x180037338  add     ebx, r13d
0x18003733b  jmp     short loc_180037315
0x18003733d  mov     eax, [rax+r14*8+8]
0x180037342  mov     [rdi+34h], eax
0x180037345  cmp     dword ptr [rdi+34h], 0F0000000h
0x18003734c  jz      loc_18003741A
0x180037352  cmp     dword ptr [rdi], 4
0x180037355  jnz     short loc_18003738B
0x180037357  mov     rcx, rdi
0x18003735a  call    netDbLoadProtcolInfo
0x18003735f  mov     ecx, [rdi+34h]
0x180037362  sub     ecx, r13d
0x180037365  jz      short loc_180037373
0x180037367  xor     eax, eax
0x180037369  cmp     ecx, r13d
0x18003736c  jnz     short loc_18003737B
0x18003736e  cmp     [rbp+34h], eax
0x180037371  jmp     short loc_180037378
0x180037373  xor     eax, eax
0x180037375  cmp     [rbp+30h], eax
0x180037378  setz    al
0x18003737b  mov     [rdi+30h], eax
0x18003737e  test    eax, eax
0x180037380  jz      short loc_18003739F
0x180037382  mov     dword ptr [rdi+38h], 0
0x180037389  jmp     short loc_18003739F
0x18003738b  cmp     [rdi], r13d
0x18003738e  jnz     short loc_18003739F
0x180037390  lea     rcx, [rdi+38h]
0x180037394  call    svcGetEnabling
0x180037399  mov     eax, [rdi+38h]
0x18003739c  mov     [rdi+3Ch], eax
0x18003739f  mov     [rdi+20h], r13d
0x1800373a3  mov     rcx, rsi
0x1800373a6  mov     [rdi+28h], rsi
0x1800373aa  mov     rax, [rsi]
0x1800373ad  mov     rax, [rax+8]
0x1800373b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373b6  mov     rax, [rsi]
0x1800373b9  lea     rdx, [rsp+78h+var_44]
0x1800373be  mov     [rsp+78h+var_44], 0
0x1800373c6  mov     rcx, rsi
0x1800373c9  mov     ebx, r13d
0x1800373cc  mov     rax, [rax+38h]
0x1800373d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373d5  test    eax, eax
0x1800373d7  js      short loc_1800373E6
0x1800373d9  test    byte ptr [rsp+78h+var_44], 20h
0x1800373de  mov     ecx, 0
0x1800373e3  cmovnz  ebx, ecx
0x1800373e6  mov     [rdi+54h], ebx
0x1800373e9  mov     eax, r13d
0x1800373ec  jmp     short loc_18003741C
0x1800373ee  mov     rcx, [rdi+18h]; pv
0x1800373f2  call    cs:__imp_CoTaskMemFree
0x1800373f8  mov     rcx, [rdi+10h]; pv
0x1800373fc  call    cs:__imp_CoTaskMemFree
0x180037402  mov     rcx, [r14]; pv
0x180037405  call    cs:__imp_CoTaskMemFree
0x18003740b  mov     rdx, [r14]
0x18003740e  lea     rcx, aGetcompinfoFai; "GetCompInfo: fail %S"
0x180037415  call    DbgOutputTrace
0x18003741a  xor     eax, eax
0x18003741c  mov     rcx, [rsp+78h+var_30]
0x180037421  xor     rcx, rsp; StackCookie
0x180037424  call    __security_check_cookie
0x180037429  lea     r11, [rsp+78h+var_28]
0x18003742e  mov     rbx, [r11+40h]
0x180037432  mov     rbp, [r11+48h]
0x180037436  mov     rsp, r11
0x180037439  pop     r15
0x18003743b  pop     r14
0x18003743d  pop     r13
0x18003743f  pop     rdi
0x180037440  pop     rsi
0x180037441  retn
```
