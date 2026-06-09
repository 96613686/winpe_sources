# SetEmailInfo(CUserObject *,ulong,MapiRecipDescW *)

- ea: `0x180067bfc`
- end: `0x180067cec`
- name: `?SetEmailInfo@@YAJPEAVCUserObject@@KPEAUMapiRecipDescW@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(struct CUserObject *, unsigned int, struct MapiRecipDescW *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180067504`
- `0x1800675cc`

## callees

- `0x180009340`
- `0x1800254e0`
- `0x180067bfc`
- `0x180070720`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067cb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067cc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067cb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067cc1`
- `SHCORE!SHStrDupW` at `0x180067c5e`
- `SHCORE!SHStrDupW` at `0x180067ca8`
- `SHCORE!SHStrDupW` at `0x180067c5e`
- `SHCORE!SHStrDupW` at `0x180067ca8`

## pseudocode

```c
__int64 __fastcall SetEmailInfo(struct CUserObject *a1, ULONG a2, struct MapiRecipDescW *a3)
{
  HRESULT DisplayName; // ebx
  WCHAR psz[520]; // [rsp+20h] [rbp-848h] BYREF
  WCHAR v8[520]; // [rsp+430h] [rbp-438h] BYREF

  DisplayName = 1;
  if ( *((_DWORD *)a1 + 10) == 1 && *((_DWORD *)a1 + 12) != 4 )
  {
    a3->ulRecipClass = a2;
    DisplayName = CUserObject::GetDisplayName(a1, psz, 0x208u);
    if ( DisplayName >= 0 )
      DisplayName = SHStrDupW(psz, &a3->lpszName);
    a3->lpszAddress = 0;
    if ( DisplayName < 0 )
      goto LABEL_10;
    if ( *((_QWORD *)a1 + 3) )
    {
      DisplayName = StringCchPrintfW(v8, 0x208u, L"smtp:%s");
      if ( DisplayName >= 0 )
        DisplayName = SHStrDupW(v8, &a3->lpszAddress);
      if ( DisplayName < 0 )
      {
LABEL_10:
        CoTaskMemFree(a3->lpszName);
        CoTaskMemFree(a3->lpszAddress);
      }
    }
  }
  return (unsigned int)DisplayName;
}

```

## disassembly

```asm
0x180067bfc  mov     [rsp+arg_8], rbx
0x180067c01  push    rbp
0x180067c02  push    rsi
0x180067c03  push    rdi
0x180067c04  sub     rsp, 850h
0x180067c0b  mov     rax, cs:__security_cookie
0x180067c12  xor     rax, rsp
0x180067c15  mov     [rsp+868h+var_28], rax
0x180067c1d  mov     ebx, 1
0x180067c22  mov     rbp, r8
0x180067c25  mov     rsi, rcx
0x180067c28  cmp     [rcx+28h], ebx
0x180067c2b  jnz     loc_180067CC7
0x180067c31  cmp     dword ptr [rcx+30h], 4
0x180067c35  jz      loc_180067CC7
0x180067c3b  mov     [r8+4], edx
0x180067c3f  mov     r8d, 208h; unsigned int
0x180067c45  lea     rdx, [rsp+868h+psz]; unsigned __int16 *
0x180067c4a  call    ?GetDisplayName@CUserObject@@QEAAJPEAGK@Z; CUserObject::GetDisplayName(ushort *,ulong)
0x180067c4f  mov     ebx, eax
0x180067c51  test    eax, eax
0x180067c53  js      short loc_180067C66
0x180067c55  lea     rdx, [rbp+8]; ppwsz
0x180067c59  lea     rcx, [rsp+868h+psz]; psz
0x180067c5e  call    cs:__imp_SHStrDupW
0x180067c64  mov     ebx, eax
0x180067c66  lea     rdi, [rbp+10h]
0x180067c6a  mov     qword ptr [rdi], 0
0x180067c71  test    ebx, ebx
0x180067c73  js      short loc_180067CB4
0x180067c75  mov     r9, [rsi+18h]
0x180067c79  test    r9, r9
0x180067c7c  jz      short loc_180067CC7
0x180067c7e  lea     r8, aSmtpS; "smtp:%s"
0x180067c85  mov     edx, 208h; unsigned __int64
0x180067c8a  lea     rcx, [rsp+868h+var_438]; unsigned __int16 *
0x180067c92  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180067c97  mov     ebx, eax
0x180067c99  test    eax, eax
0x180067c9b  js      short loc_180067CB0
0x180067c9d  mov     rdx, rdi; ppwsz
0x180067ca0  lea     rcx, [rsp+868h+var_438]; psz
0x180067ca8  call    cs:__imp_SHStrDupW
0x180067cae  mov     ebx, eax
0x180067cb0  test    ebx, ebx
0x180067cb2  jns     short loc_180067CC7
0x180067cb4  mov     rcx, [rbp+8]; pv
0x180067cb8  call    cs:__imp_CoTaskMemFree
0x180067cbe  mov     rcx, [rdi]; pv
0x180067cc1  call    cs:__imp_CoTaskMemFree
0x180067cc7  mov     eax, ebx
0x180067cc9  mov     rcx, [rsp+868h+var_28]
0x180067cd1  xor     rcx, rsp; StackCookie
0x180067cd4  call    __security_check_cookie
0x180067cd9  mov     rbx, [rsp+868h+arg_8]
0x180067ce1  add     rsp, 850h
0x180067ce8  pop     rdi
0x180067ce9  pop     rsi
0x180067cea  pop     rbp
0x180067ceb  retn
```
