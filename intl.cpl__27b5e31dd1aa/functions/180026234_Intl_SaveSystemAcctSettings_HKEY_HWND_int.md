# Intl_SaveSystemAcctSettings(HKEY__ *,HWND__ *,int)

- ea: `0x180026234`
- end: `0x1800262fc`
- name: `?Intl_SaveSystemAcctSettings@@YAKPEAUHKEY__@@PEAUHWND__@@H@Z`
- size: `200`
- prototype: `unsigned int __fastcall(HKEY, HWND, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000dce0`
- `0x180017cf0`
- `0x180022100`
- `0x180022180`

## callees

- `0x180013058`
- `0x180026234`
- `0x18002665c`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800262d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800262d3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180026284`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180026284`

## pseudocode

```c
__int64 __fastcall Intl_SaveSystemAcctSettings(HKEY a1, HWND a2, int a3)
{
  unsigned int v6; // edi
  const unsigned __int16 *v7; // rdx
  const unsigned __int16 *v8; // rdx
  WINBOOL IsMember; // [rsp+20h] [rbp-20h] BYREF
  _DWORD SidToCheck[4]; // [rsp+28h] [rbp-18h] BYREF

  SidToCheck[0] = 257;
  SidToCheck[1] = 83886080;
  SidToCheck[2] = 18;
  v6 = 0;
  IsMember = 0;
  if ( !CheckTokenMembership(0, SidToCheck, &IsMember) || !IsMember )
    Intl_SaveValuesToSystemAccts(a1, v7, L".DEFAULT\\Control Panel\\International");
  Intl_SaveValuesToSystemAccts(a1, v7, L"S-1-5-19\\Control Panel\\International");
  Intl_SaveValuesToSystemAccts(a1, v8, L"S-1-5-20\\Control Panel\\International");
  if ( a3 && !(unsigned int)Input_SaveSystemAcctInputSettings(a2, a1) )
    return GetLastError();
  return v6;
}

```

## disassembly

```asm
0x180026234  mov     [rsp-18h+arg_10], rbx
0x180026239  mov     [rsp-18h+arg_18], rsi
0x18002623e  push    rbp
0x18002623f  push    rdi
0x180026240  push    r14
0x180026242  mov     rbp, rsp
0x180026245  sub     rsp, 40h
0x180026249  mov     rax, cs:__security_cookie
0x180026250  xor     rax, rsp
0x180026253  mov     [rbp+var_8], rax
0x180026257  mov     esi, r8d
0x18002625a  mov     [rbp+SidToCheck], 101h
0x180026261  mov     r14, rdx
0x180026264  mov     [rbp+var_14], 5000000h
0x18002626b  mov     rbx, rcx
0x18002626e  mov     [rbp+var_10], 12h
0x180026275  xor     edi, edi
0x180026277  lea     r8, [rbp+IsMember]; IsMember
0x18002627b  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x18002627f  mov     [rbp+IsMember], edi
0x180026282  xor     ecx, ecx; TokenHandle
0x180026284  call    cs:__imp_CheckTokenMembership
0x18002628a  test    eax, eax
0x18002628c  jz      short loc_180026293
0x18002628e  cmp     [rbp+IsMember], edi
0x180026291  jnz     short loc_1800262A2
0x180026293  lea     r8, ?c_szCPanelIntl_DefUser@@3QBGB; ".DEFAULT\\Control Panel\\International"
0x18002629a  mov     rcx, rbx; HKEY
0x18002629d  call    ?Intl_SaveValuesToSystemAccts@@YAXPEAUHKEY__@@PEBG1@Z; Intl_SaveValuesToSystemAccts(HKEY__ *,ushort const *,ushort const *)
0x1800262a2  lea     r8, ?c_szCPanelIntl_19@@3QBGB; "S-1-5-19\\Control Panel\\International"
0x1800262a9  mov     rcx, rbx; HKEY
0x1800262ac  call    ?Intl_SaveValuesToSystemAccts@@YAXPEAUHKEY__@@PEBG1@Z; Intl_SaveValuesToSystemAccts(HKEY__ *,ushort const *,ushort const *)
0x1800262b1  lea     r8, ?c_szCPanelIntl_20@@3QBGB; "S-1-5-20\\Control Panel\\International"
0x1800262b8  mov     rcx, rbx; HKEY
0x1800262bb  call    ?Intl_SaveValuesToSystemAccts@@YAXPEAUHKEY__@@PEBG1@Z; Intl_SaveValuesToSystemAccts(HKEY__ *,ushort const *,ushort const *)
0x1800262c0  test    esi, esi
0x1800262c2  jz      short loc_1800262DB
0x1800262c4  mov     rdx, rbx; HKEY
0x1800262c7  mov     rcx, r14; HWND
0x1800262ca  call    ?Input_SaveSystemAcctInputSettings@@YAHPEAUHWND__@@PEAUHKEY__@@@Z; Input_SaveSystemAcctInputSettings(HWND__ *,HKEY__ *)
0x1800262cf  test    eax, eax
0x1800262d1  jnz     short loc_1800262DB
0x1800262d3  call    cs:__imp_GetLastError
0x1800262d9  mov     edi, eax
0x1800262db  mov     eax, edi
0x1800262dd  mov     rcx, [rbp+var_8]
0x1800262e1  xor     rcx, rsp; StackCookie
0x1800262e4  call    __security_check_cookie
0x1800262e9  mov     rbx, [rsp+40h+arg_10]
0x1800262ee  mov     rsi, [rsp+40h+arg_18]
0x1800262f3  add     rsp, 40h
0x1800262f7  pop     r14
0x1800262f9  pop     rdi
0x1800262fa  pop     rbp
0x1800262fb  retn
```
