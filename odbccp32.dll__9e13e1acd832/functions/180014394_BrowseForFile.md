# BrowseForFile

- ea: `0x180014394`
- end: `0x180014506`
- name: `BrowseForFile`
- size: `370`
- prototype: `BOOL __fastcall(HWND, WCHAR *, __int64, UINT, UINT uID, int, const WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dc70`

## callees

- `0x180002368`
- `0x180014394`
- `0x180014aae`
- `0x180014ae0`

## import_xrefs

- `USER32!LoadStringW` at `0x180014401`
- `USER32!LoadStringW` at `0x18001441b`
- `USER32!LoadStringW` at `0x180014401`
- `USER32!LoadStringW` at `0x18001441b`
- `COMDLG32!GetOpenFileNameW` at `0x1800144da`
- `COMDLG32!GetOpenFileNameW` at `0x1800144da`
- `COMDLG32!GetSaveFileNameW` at `0x1800144d2`
- `COMDLG32!GetSaveFileNameW` at `0x1800144d2`

## pseudocode

```c
BOOL __fastcall BrowseForFile(HWND a1, WCHAR *a2, __int64 a3, UINT a4, UINT uID, int a6, const WCHAR *a7)
{
  int i; // edx
  __int64 v11; // rax
  tagOFNW v13; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR v14[104]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Buffer[104]; // [rsp+190h] [rbp+90h] BYREF

  *(&v13.lStructSize + 1) = 0;
  memset_0(&v13, 0, 0x94u);
  LoadStringW(g_hResDLL, a4, Buffer, 100);
  for ( i = LoadStringW(g_hResDLL, uID, v14, 100) - 1; i >= 0; --i )
  {
    if ( v14[i] == 124 )
    {
      if ( (unsigned __int64)(2LL * i) >= 0xC8 )
        _report_rangecheckfailure();
      v14[i] = 0;
    }
  }
  memset_0(&v13, 0, sizeof(v13));
  v13.hInstance = g_hResDLL;
  v13.lpstrFilter = v14;
  v11 = -1;
  v13.lStructSize = 152;
  v13.hwndOwner = a1;
  do
    ++v11;
  while ( v14[v11] );
  v13.lpstrFile = a2;
  v13.lpstrDefExt = &v14[v11 + 3];
  v13.nMaxFile = 260;
  v13.lpstrTitle = Buffer;
  v13.lpstrInitialDir = a7;
  v13.Flags = 2062;
  if ( a6 )
    return GetSaveFileNameW(&v13);
  else
    return GetOpenFileNameW(&v13);
}

```

## disassembly

```asm
0x180014394  mov     [rsp-8+arg_10], rbx
0x180014399  push    rbp
0x18001439a  push    rsi
0x18001439b  push    rdi
0x18001439c  push    r14
0x18001439e  push    r15
0x1800143a0  lea     rbp, [rsp-170h]
0x1800143a8  sub     rsp, 270h
0x1800143af  mov     rax, cs:__security_cookie
0x1800143b6  xor     rax, rsp
0x1800143b9  mov     [rbp+190h+var_30], rax
0x1800143c0  mov     rsi, [rbp+190h+arg_30]
0x1800143c7  mov     rdi, rdx
0x1800143ca  mov     r14, rcx
0x1800143cd  xor     eax, eax
0x1800143cf  xor     edx, edx; Val
0x1800143d1  mov     dword ptr [rsp+290h+var_270+4], eax
0x1800143d5  lea     rcx, [rsp+290h+var_270]; void *
0x1800143da  mov     r8d, 94h; Size
0x1800143e0  mov     ebx, r9d
0x1800143e3  call    memset_0
0x1800143e8  mov     rcx, cs:g_hResDLL; hInstance
0x1800143ef  lea     r8, [rbp+190h+Buffer]; lpBuffer
0x1800143f6  mov     r15d, 64h ; 'd'
0x1800143fc  mov     edx, ebx; uID
0x1800143fe  mov     r9d, r15d; cchBufferMax
0x180014401  call    cs:__imp_LoadStringW
0x180014407  mov     edx, [rbp+190h+uID]; uID
0x18001440d  lea     r8, [rbp+190h+var_1D0]; lpBuffer
0x180014411  mov     rcx, cs:g_hResDLL; hInstance
0x180014418  mov     r9d, r15d; cchBufferMax
0x18001441b  call    cs:__imp_LoadStringW
0x180014421  xor     r15d, r15d
0x180014424  lea     edx, [rax-1]
0x180014427  test    edx, edx
0x180014429  js      short loc_180014452
0x18001442b  movsxd  rcx, edx
0x18001442e  add     rcx, rcx
0x180014431  cmp     [rbp+rcx+190h+var_1D0], 7Ch ; '|'
0x180014437  jnz     short loc_180014448
0x180014439  cmp     rcx, 0C8h
0x180014440  jnb     short loc_18001444C
0x180014442  mov     [rbp+rcx+190h+var_1D0], r15w
0x180014448  dec     edx
0x18001444a  jmp     short loc_180014427
0x18001444c  call    __report_rangecheckfailure
0x180014452  mov     ebx, 98h
0x180014457  lea     rcx, [rsp+290h+var_270]; void *
0x18001445c  mov     r8d, ebx; Size
0x18001445f  xor     edx, edx; Val
0x180014461  call    memset_0
0x180014466  mov     rax, cs:g_hResDLL
0x18001446d  lea     rcx, [rbp+190h+var_1D0]
0x180014471  mov     [rsp+290h+var_270.hInstance], rax
0x180014476  lea     rax, [rbp+190h+var_1D0]
0x18001447a  mov     [rsp+290h+var_270.lpstrFilter], rax
0x18001447f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014483  mov     [rsp+290h+var_270.lStructSize], ebx
0x180014487  mov     [rsp+290h+var_270.hwndOwner], r14
0x18001448c  inc     rax
0x18001448f  cmp     [rcx+rax*2], r15w
0x180014494  jnz     short loc_18001448C
0x180014496  lea     rax, [rbp+rax*2+190h+var_1CA]
0x18001449b  mov     [rsp+290h+var_270.lpstrFile], rdi
0x1800144a0  lea     rcx, [rsp+290h+var_270]; LPOPENFILENAMEW
0x1800144a5  mov     [rbp+190h+var_270.lpstrDefExt], rax
0x1800144a9  lea     rax, [rbp+190h+Buffer]
0x1800144b0  mov     [rsp+290h+var_270.nMaxFile], 104h
0x1800144b8  mov     [rsp+290h+var_270.lpstrTitle], rax
0x1800144bd  mov     [rsp+290h+var_270.lpstrInitialDir], rsi
0x1800144c2  mov     [rbp+190h+var_270.Flags], 80Eh
0x1800144c9  cmp     [rbp+190h+arg_28], r15d
0x1800144d0  jz      short loc_1800144DA
0x1800144d2  call    cs:__imp_GetSaveFileNameW
0x1800144d8  jmp     short loc_1800144E0
0x1800144da  call    cs:__imp_GetOpenFileNameW
0x1800144e0  mov     rcx, [rbp+190h+var_30]
0x1800144e7  xor     rcx, rsp; StackCookie
0x1800144ea  call    __security_check_cookie
0x1800144ef  mov     rbx, [rsp+290h+arg_10]
0x1800144f7  add     rsp, 270h
0x1800144fe  pop     r15
0x180014500  pop     r14
0x180014502  pop     rdi
0x180014503  pop     rsi
0x180014504  pop     rbp
0x180014505  retn
```
