# CStatusBar::_CacheZonesIcons(void)

- ea: `0x180023554`
- end: `0x180023708`
- name: `?_CacheZonesIcons@CStatusBar@@IEAAXXZ`
- size: `436`
- prototype: `void __fastcall(CStatusBar *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800239bc`

## callees

- `0x180002240`
- `0x180002b60`
- `0x180023554`
- `0x180028010`

## import_xrefs

- `SHELL32!ExtractAssociatedIconExW` at `0x1800236bb`
- `SHELL32!ExtractAssociatedIconExW` at `0x1800236bb`
- `SHELL32!ExtractIconExW` at `0x180023696`
- `SHELL32!ExtractIconExW` at `0x180023696`
- `SHLWAPI!StrToIntW` at `0x18002366f`
- `SHLWAPI!StrToIntW` at `0x18002366f`
- `SHLWAPI!StrChrW` at `0x18002365b`
- `SHLWAPI!StrChrW` at `0x18002365b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800235a7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800235a7`

## pseudocode

```c
void __fastcall CStatusBar::_CacheZonesIcons(CStatusBar *this)
{
  LPVOID *ppv; // rdi
  LPVOID v3; // rcx
  int i; // ebx
  LPVOID v5; // rcx
  PWSTR v6; // rax
  HICON AssociatedIcon; // rax
  WORD piIconIndex[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v9; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v10; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v11; // [rsp+3Ch] [rbp-C4h] BYREF
  HICON phiconSmall; // [rsp+40h] [rbp-C0h] BYREF
  int v13; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[920]; // [rsp+54h] [rbp-ACh] BYREF
  WCHAR pszStart[274]; // [rsp+3ECh] [rbp+2ECh] BYREF

  ppv = (LPVOID *)((char *)this + 24);
  v9 = 0;
  if ( !*((_QWORD *)this + 3) )
    CoCreateInstance(&CLSID_InternetZoneManager, 0, 1u, &IID_IInternetZoneManager, ppv);
  v3 = *ppv;
  if ( *ppv )
  {
    v10 = 0;
    if ( (*(int (__fastcall **)(LPVOID, unsigned int *, unsigned int *, _QWORD))(*(_QWORD *)v3 + 88LL))(
           v3,
           &v10,
           &v9,
           0) >= 0 )
    {
      for ( i = 0; i < v9; ++i )
      {
        v11 = 0;
        v13 = 1460;
        memset_0(v14, 0, 0x5B0u);
        v5 = *ppv;
        piIconIndex[0] = 0;
        phiconSmall = 0;
        (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v5 + 96LL))(
          v5,
          v10,
          (unsigned int)i,
          &v11);
        (*(void (__fastcall **)(LPVOID, _QWORD, int *))(*(_QWORD *)*ppv + 24LL))(*ppv, v11, &v13);
        v6 = StrChrW(pszStart, 0x23u);
        if ( v6 )
        {
          *v6 = 0;
          piIconIndex[0] = StrToIntW(v6 + 1);
          ExtractIconExW(pszStart, -piIconIndex[0], 0, &phiconSmall, 1u);
          AssociatedIcon = phiconSmall;
        }
        else
        {
          AssociatedIcon = ExtractAssociatedIconExW(g_hinst, pszStart, piIconIndex, piIconIndex);
        }
        if ( i < 12 )
          *((_QWORD *)this + i + 4) = AssociatedIcon;
      }
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)*ppv + 104LL))(*ppv, v10);
    }
  }
}

```

## disassembly

```asm
0x180023554  push    rbp
0x180023556  push    rbx
0x180023557  push    rsi
0x180023558  push    rdi
0x180023559  lea     rbp, [rsp-528h]
0x180023561  sub     rsp, 628h
0x180023568  mov     rax, cs:__security_cookie
0x18002356f  xor     rax, rsp
0x180023572  mov     [rbp+540h+var_30], rax
0x180023579  lea     rdi, [rcx+18h]
0x18002357d  mov     [rsp+640h+var_60C], 0
0x180023585  cmp     qword ptr [rdi], 0
0x180023589  mov     rsi, rcx
0x18002358c  jnz     short loc_1800235AD
0x18002358e  xor     edx, edx; pUnkOuter
0x180023590  mov     [rsp+640h+ppv], rdi; ppv
0x180023595  lea     r9, IID_IInternetZoneManager; riid
0x18002359c  lea     rcx, CLSID_InternetZoneManager; rclsid
0x1800235a3  lea     r8d, [rdx+1]; dwClsContext
0x1800235a7  call    cs:__imp_CoCreateInstance
0x1800235ad  mov     rcx, [rdi]
0x1800235b0  test    rcx, rcx
0x1800235b3  jz      loc_1800236ED
0x1800235b9  mov     [rsp+640h+var_608], 0
0x1800235c1  lea     r8, [rsp+640h+var_60C]
0x1800235c6  mov     rax, [rcx]
0x1800235c9  lea     rdx, [rsp+640h+var_608]
0x1800235ce  xor     r9d, r9d
0x1800235d1  mov     rax, [rax+58h]
0x1800235d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235da  test    eax, eax
0x1800235dc  js      loc_1800236ED
0x1800235e2  xor     ebx, ebx
0x1800235e4  cmp     [rsp+640h+var_60C], ebx
0x1800235e8  jbe     loc_1800236DA
0x1800235ee  xor     edx, edx; Val
0x1800235f0  mov     [rsp+640h+var_604], 0
0x1800235f8  mov     r8d, 5B0h; Size
0x1800235fe  mov     [rsp+640h+var_5F0], 5B4h
0x180023606  lea     rcx, [rsp+640h+var_5EC]; void *
0x18002360b  call    memset_0
0x180023610  mov     rcx, [rdi]
0x180023613  lea     r9, [rsp+640h+var_604]
0x180023618  mov     edx, [rsp+640h+var_608]
0x18002361c  xor     eax, eax
0x18002361e  mov     [rsp+640h+piIconIndex], ax
0x180023623  mov     r8d, ebx
0x180023626  mov     [rsp+640h+phiconSmall], rax
0x18002362b  mov     rax, [rcx]
0x18002362e  mov     rax, [rax+60h]
0x180023632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023637  mov     rcx, [rdi]
0x18002363a  lea     r8, [rsp+640h+var_5F0]
0x18002363f  mov     edx, [rsp+640h+var_604]
0x180023643  mov     rax, [rcx]
0x180023646  mov     rax, [rax+18h]
0x18002364a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002364f  mov     edx, 23h ; '#'; wMatch
0x180023654  lea     rcx, [rbp+540h+pszStart]; pszStart
0x18002365b  call    cs:__imp_StrChrW
0x180023661  test    rax, rax
0x180023664  jz      short loc_1800236A3
0x180023666  xor     ecx, ecx
0x180023668  mov     [rax], cx
0x18002366b  lea     rcx, [rax+2]; pszSrc
0x18002366f  call    cs:__imp_StrToIntW
0x180023675  lea     r9, [rsp+640h+phiconSmall]; phiconSmall
0x18002367a  mov     dword ptr [rsp+640h+ppv], 1; nIcons
0x180023682  movzx   edx, ax
0x180023685  lea     rcx, [rbp+540h+pszStart]; lpszFile
0x18002368c  neg     edx; nIconIndex
0x18002368e  mov     [rsp+640h+piIconIndex], ax
0x180023693  xor     r8d, r8d; phiconLarge
0x180023696  call    cs:__imp_ExtractIconExW
0x18002369c  mov     rax, [rsp+640h+phiconSmall]
0x1800236a1  jmp     short loc_1800236C1
0x1800236a3  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInst
0x1800236aa  lea     r9, [rsp+640h+piIconIndex]; piIconId
0x1800236af  lea     r8, [rsp+640h+piIconIndex]; piIconIndex
0x1800236b4  lea     rdx, [rbp+540h+pszStart]; pszIconPath
0x1800236bb  call    cs:__imp_ExtractAssociatedIconExW
0x1800236c1  cmp     ebx, 0Ch
0x1800236c4  jge     short loc_1800236CE
0x1800236c6  movsxd  rcx, ebx
0x1800236c9  mov     [rsi+rcx*8+20h], rax
0x1800236ce  inc     ebx
0x1800236d0  cmp     ebx, [rsp+640h+var_60C]
0x1800236d4  jb      loc_1800235EE
0x1800236da  mov     rcx, [rdi]
0x1800236dd  mov     edx, [rsp+640h+var_608]
0x1800236e1  mov     rax, [rcx]
0x1800236e4  mov     rax, [rax+68h]
0x1800236e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236ed  mov     rcx, [rbp+540h+var_30]
0x1800236f4  xor     rcx, rsp; StackCookie
0x1800236f7  call    __security_check_cookie
0x1800236fc  add     rsp, 628h
0x180023703  pop     rdi
0x180023704  pop     rsi
0x180023705  pop     rbx
0x180023706  pop     rbp
0x180023707  retn
```
