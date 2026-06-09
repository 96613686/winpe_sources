# CicBridge::GetControlClassForBackingStore(HWND__ *)

- ea: `0x18004e810`
- end: `0x18004ea23`
- name: `?GetControlClassForBackingStore@CicBridge@@SA?AW4ControlClass@@PEAUHWND__@@@Z`
- size: `531`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004e334`
- `0x18004e738`

## callees

- `0x18004e810`
- `0x18007310c`
- `0x18009c868`
- `0x18009eaea`
- `0x1800e1400`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004e937`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004e9a0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004e9de`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004e937`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004e9a0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004e9de`
- `USER32!RealGetWindowClassW` at `0x18004e852`
- `USER32!RealGetWindowClassW` at `0x18004e852`

## pseudocode

```c
__int64 __fastcall CicBridge::GetControlClassForBackingStore(HWND a1)
{
  UINT WindowClassW; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned __int64 v6; // rcx
  unsigned int v7; // esi
  unsigned __int64 v8; // rbx
  __int64 v9; // rdi
  WCHAR lpString2[8]; // [rsp+30h] [rbp-268h] BYREF
  WCHAR String2[8]; // [rsp+40h] [rbp-258h] BYREF
  WCHAR v13[16]; // [rsp+50h] [rbp-248h] BYREF
  WCHAR ptszClassName[264]; // [rsp+70h] [rbp-228h] BYREF

  memset_0(ptszClassName, 0, 0x208u);
  WindowClassW = RealGetWindowClassW(a1, ptszClassName, 0x103u);
  if ( WindowClassW - 1 > 0x102 )
    return -1;
  v6 = 2LL * WindowClassW;
  if ( v6 >= 0x208 )
    _report_rangecheckfailure(v6, v3, v4, v5);
  ptszClassName[WindowClassW] = 0;
  v7 = -1;
  v8 = -1;
  wcscpy(lpString2, L"ATL:");
  wcscpy(v13, L"WindowsForms10.");
  do
    ++v8;
  while ( ptszClassName[v8] );
  if ( v8 > 4 && CompareStringW(0x7Fu, 1u, ptszClassName, 4, lpString2, 4) == 2 )
  {
    v9 = 4;
  }
  else
  {
    v9 = 0;
    if ( v8 > 0xF && CompareStringW(0x7Fu, 1u, ptszClassName, 15, v13, 15) == 2 )
      v9 = 15;
  }
  wcscpy(String2, L"Edit");
  if ( CompareStringW(0x7Fu, 1u, &ptszClassName[v9], 4, String2, 4) == 2
    && !CicBridge::IsYoudaoDict()
    && CicBridge::IsEditControlUnicode(a1) )
  {
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18004e810  mov     [rsp+arg_18], rbp
0x18004e815  push    rsi
0x18004e816  sub     rsp, 290h
0x18004e81d  mov     rax, cs:__security_cookie
0x18004e824  xor     rax, rsp
0x18004e827  mov     [rsp+298h+var_18], rax
0x18004e82f  mov     rbp, rcx
0x18004e832  xor     edx, edx; Val
0x18004e834  lea     rcx, [rsp+298h+ptszClassName]; void *
0x18004e839  mov     r8d, 208h; Size
0x18004e83f  call    memset_0
0x18004e844  mov     r8d, 103h; cchClassNameMax
0x18004e84a  lea     rdx, [rsp+298h+ptszClassName]; ptszClassName
0x18004e84f  mov     rcx, rbp; hwnd
0x18004e852  call    cs:__imp_RealGetWindowClassW
0x18004e858  lea     ecx, [rax-1]
0x18004e85b  cmp     ecx, 102h
0x18004e861  ja      loc_18004E9F0
0x18004e867  mov     eax, eax
0x18004e869  lea     rcx, [rax+rax]
0x18004e86d  cmp     rcx, 208h
0x18004e874  jnb     loc_18004EA1D
0x18004e87a  movsd   xmm0, qword ptr cs:aAtl; "ATL:"
0x18004e882  xor     eax, eax
0x18004e884  movups  xmm1, xmmword ptr cs:aWindowsforms10+10h; "orms10."
0x18004e88b  mov     [rsp+rcx+298h+ptszClassName], ax
0x18004e890  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18004e897  movzx   eax, word ptr cs:aAtl+8; ""
0x18004e89e  mov     [rsp+298h+arg_8], rbx
0x18004e8a6  mov     rbx, rsi
0x18004e8a9  movsd   qword ptr [rsp+298h+var_268], xmm0
0x18004e8af  movups  xmm0, xmmword ptr cs:aWindowsforms10; "WindowsForms10."
0x18004e8b6  mov     [rsp+298h+var_260], ax
0x18004e8bb  lea     rax, [rsp+298h+ptszClassName]
0x18004e8c0  mov     [rsp+298h+arg_10], rdi
0x18004e8c8  movups  xmmword ptr [rsp+298h+var_248], xmm0
0x18004e8cd  movups  [rsp+298h+var_238], xmm1
0x18004e8d2  inc     rbx
0x18004e8d5  cmp     word ptr [rax+rbx*2], 0
0x18004e8da  jnz     short loc_18004E8D2
0x18004e8dc  cmp     rbx, 4
0x18004e8e0  ja      loc_18004E979
0x18004e8e6  xor     edi, edi
0x18004e8e8  cmp     rbx, 0Fh
0x18004e8ec  ja      loc_18004E9B9
0x18004e8f2  movzx   eax, word ptr cs:aEdit+8; ""
0x18004e8f9  lea     r8, [rsp+298h+ptszClassName]
0x18004e8fe  movsd   xmm0, qword ptr cs:aEdit; "Edit"
0x18004e906  lea     r8, [r8+rdi*2]; lpString1
0x18004e90a  mov     [rsp+298h+var_250], ax
0x18004e90f  mov     edx, 1; dwCmpFlags
0x18004e914  lea     rax, [rsp+298h+String2]
0x18004e919  mov     [rsp+298h+cchCount2], 4; cchCount2
0x18004e921  mov     ecx, 7Fh; Locale
0x18004e926  mov     [rsp+298h+lpString2], rax; lpString2
0x18004e92b  mov     r9d, 4; cchCount1
0x18004e931  movsd   qword ptr [rsp+298h+String2], xmm0
0x18004e937  call    cs:__imp_CompareStringW
0x18004e93d  mov     rdi, [rsp+298h+arg_10]
0x18004e945  mov     rbx, [rsp+298h+arg_8]
0x18004e94d  cmp     eax, 2
0x18004e950  jz      loc_18004E9FC
0x18004e956  mov     eax, esi
0x18004e958  mov     rcx, [rsp+298h+var_18]
0x18004e960  xor     rcx, rsp; StackCookie
0x18004e963  call    __security_check_cookie
0x18004e968  mov     rbp, [rsp+298h+arg_18]
0x18004e970  add     rsp, 290h
0x18004e977  pop     rsi
0x18004e978  retn
0x18004e979  lea     rax, [rsp+298h+var_268]
0x18004e97e  mov     [rsp+298h+cchCount2], 4; cchCount2
0x18004e986  mov     r9d, 4; cchCount1
0x18004e98c  mov     [rsp+298h+lpString2], rax; lpString2
0x18004e991  lea     r8, [rsp+298h+ptszClassName]; lpString1
0x18004e996  mov     edx, 1; dwCmpFlags
0x18004e99b  mov     ecx, 7Fh; Locale
0x18004e9a0  call    cs:__imp_CompareStringW
0x18004e9a6  cmp     eax, 2
0x18004e9a9  jnz     loc_18004E8E6
0x18004e9af  mov     edi, 4
0x18004e9b4  jmp     loc_18004E8F2
0x18004e9b9  mov     ebx, 0Fh
0x18004e9be  lea     rax, [rsp+298h+var_248]
0x18004e9c3  mov     [rsp+298h+cchCount2], ebx; cchCount2
0x18004e9c7  lea     r8, [rsp+298h+ptszClassName]; lpString1
0x18004e9cc  mov     r9d, ebx; cchCount1
0x18004e9cf  mov     [rsp+298h+lpString2], rax; lpString2
0x18004e9d4  mov     edx, 1; dwCmpFlags
0x18004e9d9  mov     ecx, 7Fh; Locale
0x18004e9de  call    cs:__imp_CompareStringW
0x18004e9e4  cmp     eax, 2
0x18004e9e7  cmovz   rdi, rbx
0x18004e9eb  jmp     loc_18004E8F2
0x18004e9f0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18004e9f7  jmp     loc_18004E958
0x18004e9fc  call    ?IsYoudaoDict@CicBridge@@SA_NXZ; CicBridge::IsYoudaoDict(void)
0x18004ea01  test    al, al
0x18004ea03  jnz     loc_18004E956
0x18004ea09  mov     rcx, rbp; hWnd
0x18004ea0c  call    ?IsEditControlUnicode@CicBridge@@SA_NPEAUHWND__@@@Z; CicBridge::IsEditControlUnicode(HWND__ *)
0x18004ea11  xor     ecx, ecx
0x18004ea13  test    al, al
0x18004ea15  cmovnz  esi, ecx
0x18004ea18  jmp     loc_18004E956
0x18004ea1d  call    __report_rangecheckfailure
```
