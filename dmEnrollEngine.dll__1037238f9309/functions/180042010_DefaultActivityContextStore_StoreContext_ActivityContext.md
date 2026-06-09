# DefaultActivityContextStore::StoreContext(ActivityContext &)

- ea: `0x180042010`
- end: `0x18004232f`
- name: `?StoreContext@DefaultActivityContextStore@@UEAAJAEAVActivityContext@@@Z`
- size: `799`
- prototype: `__int64 __fastcall(DefaultActivityContextStore *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800067a0`
- `0x180007040`
- `0x180007120`
- `0x1800071c0`
- `0x18000d560`
- `0x180010950`
- `0x18002e1a0`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800421d5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800421d5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042236`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042280`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800422af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042236`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042280`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800422af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042187`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042187`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042308`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042308`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004207d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004207d`

## string_xrefs

- `0x18004225d`: `AttemptCounter`
- `0x18004228c`: `Rollback`

## pseudocode

```c
__int64 __fastcall DefaultActivityContextStore::StoreContext(
        DefaultActivityContextStore *this,
        struct ActivityContext *a2)
{
  HKEY v2; // rbx
  signed int v4; // edi
  const unsigned __int16 *EnrollmentsRootKey; // rax
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  const unsigned __int16 *v8; // r8
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v11[4]; // [rsp+54h] [rbp-ACh] BYREF
  BYTE v12[8]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v13; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v16[40]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v18[39]; // [rsp+D2h] [rbp-2Eh] BYREF
  WCHAR SubKey[264]; // [rsp+120h] [rbp+20h] BYREF

  *(_DWORD *)Data = 32;
  v2 = 0;
  *(_DWORD *)v11 = 0;
  *(_DWORD *)v12 = 0;
  hKey[0] = 0;
  phkResult = 0;
  SubKey[0] = 0;
  v16[0] = 0;
  sz = 0;
  if ( StringFromGUID2((const GUID *const)((char *)a2 + 8), &sz, 39) != 39 )
    return (unsigned int)-2147418113;
  v13 = 0;
  v4 = StringCchLengthW(&sz, 0x27u, &v13);
  if ( v4 < 0 )
    goto LABEL_24;
  if ( v13 - 2 > 0x24 )
    goto LABEL_23;
  v4 = StringCchCopyW(v16, 0x27u, v18);
  if ( v4 < 0 )
    goto LABEL_24;
  v4 = StringCchLengthW(v16, 0x27u, &v13);
  if ( v4 < 0 )
    goto LABEL_24;
  if ( v13 - 2 > 0x24 )
  {
LABEL_23:
    v4 = -2147418113;
    goto LABEL_24;
  }
  *((_WORD *)&hKey[1] + v13 + 3) = 0;
  EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
  v4 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%s", EnrollmentsRootKey, L"Context", v16);
  if ( v4 < 0 )
    return (unsigned int)v4;
  v6 = RegOpenKeyExW((HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL), SubKey, 0, 0xF003Fu, &phkResult);
  if ( v6 == 2 )
    v6 = RegCreateKeyExW((HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL), SubKey, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  if ( v6 )
  {
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
    else
      return (unsigned int)v6;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hKey,
    phkResult);
  v2 = hKey[0];
  *(_DWORD *)Data = *((_DWORD *)a2 + 8);
  v7 = RegSetValueExW(hKey[0], L"ActivityType", 0, 4u, Data, 4u);
  if ( v7 )
  {
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    else
      v4 = v7;
  }
  else
  {
    *(_DWORD *)v11 = *((_DWORD *)a2 + 242);
    RegSetValueExW(v2, L"AttemptCounter", 0, 4u, v11, 4u);
    *(_DWORD *)v12 = *((_DWORD *)a2 + 108);
    RegSetValueExW(v2, L"Rollback", 0, 4u, v12, 4u);
    if ( a2 != (struct ActivityContext *)-448LL )
      v4 = WriteStringToRegistry(v2, L"OrchestratorType", (const unsigned __int16 *)a2 + 224);
    v8 = (&off_1800AF008)[2 * *(int *)Data];
    if ( v8 )
      WriteStringToRegistry(v2, L"ActivityTypeName", v8);
  }
LABEL_24:
  if ( v2 )
    RegCloseKey(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180042010  push    rbp
0x180042012  push    rbx
0x180042013  push    rsi
0x180042014  push    rdi
0x180042015  push    r12
0x180042017  push    r15
0x180042019  lea     rbp, [rsp-248h]
0x180042021  sub     rsp, 348h
0x180042028  mov     rax, cs:__security_cookie
0x18004202f  xor     rax, rsp
0x180042032  mov     [rbp+270h+var_40], rax
0x180042039  xor     eax, eax
0x18004203b  mov     dword ptr [rsp+370h+Data], 20h ; ' '
0x180042043  xor     ebx, ebx
0x180042045  mov     dword ptr [rsp+370h+var_31C], 0
0x18004204d  mov     rsi, rdx
0x180042050  mov     dword ptr [rsp+370h+var_318], 0
0x180042058  lea     rcx, [rdx+8]; rguid
0x18004205c  mov     [rsp+370h+hKey], rbx
0x180042061  lea     rdx, [rbp+270h+sz]; lpsz
0x180042065  mov     [rsp+370h+var_308], rbx
0x18004206a  lea     r15d, [rbx+27h]
0x18004206e  mov     [rbp+270h+SubKey], ax
0x180042072  mov     r8d, r15d; cchMax
0x180042075  mov     [rbp+270h+var_2F0], ax
0x180042079  mov     [rbp+270h+sz], ax
0x18004207d  call    cs:__imp_StringFromGUID2
0x180042083  cmp     eax, r15d
0x180042086  jz      short loc_180042092
0x180042088  mov     edi, 8000FFFFh
0x18004208d  jmp     loc_18004230E
0x180042092  lea     r8, [rsp+370h+var_310]; unsigned __int64 *
0x180042097  mov     [rsp+370h+var_310], rbx
0x18004209c  mov     rdx, r15; unsigned __int64
0x18004209f  lea     rcx, [rbp+270h+sz]; unsigned __int16 *
0x1800420a3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800420a8  mov     edi, eax
0x1800420aa  test    eax, eax
0x1800420ac  js      loc_180042300
0x1800420b2  mov     rax, [rsp+370h+var_310]
0x1800420b7  add     rax, 0FFFFFFFFFFFFFFFEh
0x1800420bb  cmp     rax, 24h ; '$'
0x1800420bf  ja      loc_1800422FB
0x1800420c5  lea     r8, [rbp+270h+var_29E]; unsigned __int16 *
0x1800420c9  mov     rdx, r15; unsigned __int64
0x1800420cc  lea     rcx, [rbp+270h+var_2F0]; unsigned __int16 *
0x1800420d0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800420d5  mov     edi, eax
0x1800420d7  test    eax, eax
0x1800420d9  js      loc_180042300
0x1800420df  lea     r8, [rsp+370h+var_310]; unsigned __int64 *
0x1800420e4  mov     rdx, r15; unsigned __int64
0x1800420e7  lea     rcx, [rbp+270h+var_2F0]; unsigned __int16 *
0x1800420eb  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800420f0  mov     edi, eax
0x1800420f2  test    eax, eax
0x1800420f4  js      loc_180042300
0x1800420fa  mov     rcx, [rsp+370h+var_310]
0x1800420ff  lea     rax, [rcx-2]
0x180042103  cmp     rax, 24h ; '$'
0x180042107  ja      loc_1800422FB
0x18004210d  xor     eax, eax
0x18004210f  mov     [rsp+rcx*2+370h+var_2F2], ax
0x180042114  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x180042119  lea     rcx, [rbp+270h+var_2F0]
0x18004211d  mov     r9, rax
0x180042120  mov     qword ptr [rsp+370h+samDesired], rcx
0x180042125  lea     r8, aSSS; "%s\\%s\\%s"
0x18004212c  lea     rcx, aContext_0; "Context"
0x180042133  mov     edx, 104h; unsigned __int64
0x180042138  mov     [rsp+370h+phkResult], rcx
0x18004213d  lea     rcx, [rbp+270h+SubKey]; unsigned __int16 *
0x180042141  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042146  mov     edi, eax
0x180042148  test    eax, eax
0x18004214a  js      loc_18004230E
0x180042150  xor     ecx, ecx
0x180042152  lea     rax, [rsp+370h+var_308]
0x180042157  mov     r12d, 2000h
0x18004215d  mov     [rsp+370h+phkResult], rax; phkResult
0x180042162  cmp     cs:word_1800AFC84, r12w
0x18004216a  lea     rdx, [rbp+270h+SubKey]; lpSubKey
0x18004216e  mov     rbx, 0FFFFFFFF80000001h
0x180042175  mov     r15d, 0F003Fh
0x18004217b  setnz   cl
0x18004217e  mov     r9d, r15d; samDesired
0x180042181  add     rcx, rbx; hKey
0x180042184  xor     r8d, r8d; ulOptions
0x180042187  call    cs:__imp_RegOpenKeyExW
0x18004218d  cmp     eax, 2
0x180042190  jnz     short loc_1800421DB
0x180042192  xor     ecx, ecx
0x180042194  mov     [rsp+370h+lpdwDisposition], 0; lpdwDisposition
0x18004219d  cmp     cs:word_1800AFC84, r12w
0x1800421a5  lea     rax, [rsp+370h+var_308]
0x1800421aa  mov     [rsp+370h+var_338], rax; phkResult
0x1800421af  lea     rdx, [rbp+270h+SubKey]; lpSubKey
0x1800421b3  setnz   cl
0x1800421b6  mov     [rsp+370h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800421bf  add     rcx, rbx; hKey
0x1800421c2  mov     [rsp+370h+samDesired], r15d; samDesired
0x1800421c7  xor     r9d, r9d; lpClass
0x1800421ca  mov     dword ptr [rsp+370h+phkResult], 0; dwOptions
0x1800421d2  xor     r8d, r8d; Reserved
0x1800421d5  call    cs:__imp_RegCreateKeyExW
0x1800421db  test    eax, eax
0x1800421dd  jz      short loc_1800421F6
0x1800421df  jg      short loc_1800421E8
0x1800421e1  mov     edi, eax
0x1800421e3  jmp     loc_18004230E
0x1800421e8  movzx   edi, ax
0x1800421eb  or      edi, 80070000h
0x1800421f1  jmp     loc_18004230E
0x1800421f6  mov     rdx, [rsp+370h+var_308]
0x1800421fb  lea     rcx, [rsp+370h+hKey]
0x180042200  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180042205  mov     eax, [rsi+20h]
0x180042208  lea     rdx, aActivitytype; "ActivityType"
0x18004220f  mov     rbx, [rsp+370h+hKey]
0x180042214  mov     r15d, 4
0x18004221a  mov     dword ptr [rsp+370h+Data], eax
0x18004221e  mov     r9d, r15d; dwType
0x180042221  lea     rax, [rsp+370h+Data]
0x180042226  mov     [rsp+370h+samDesired], r15d; cbData
0x18004222b  xor     r8d, r8d; Reserved
0x18004222e  mov     [rsp+370h+phkResult], rax; lpData
0x180042233  mov     rcx, rbx; hKey
0x180042236  call    cs:__imp_RegSetValueExW
0x18004223c  test    eax, eax
0x18004223e  jz      short loc_180042257
0x180042240  jg      short loc_180042249
0x180042242  mov     edi, eax
0x180042244  jmp     loc_180042300
0x180042249  movzx   edi, ax
0x18004224c  or      edi, 80070000h
0x180042252  jmp     loc_180042300
0x180042257  mov     eax, [rsi+3C8h]
0x18004225d  lea     rdx, aAttemptcounter; "AttemptCounter"
0x180042264  mov     dword ptr [rsp+370h+var_31C], eax
0x180042268  mov     r9d, r15d; dwType
0x18004226b  lea     rax, [rsp+370h+var_31C]
0x180042270  mov     [rsp+370h+samDesired], r15d; cbData
0x180042275  xor     r8d, r8d; Reserved
0x180042278  mov     [rsp+370h+phkResult], rax; lpData
0x18004227d  mov     rcx, rbx; hKey
0x180042280  call    cs:__imp_RegSetValueExW
0x180042286  mov     eax, [rsi+1B0h]
0x18004228c  lea     rdx, aRollback; "Rollback"
0x180042293  mov     dword ptr [rsp+370h+var_318], eax
0x180042297  mov     r9d, r15d; dwType
0x18004229a  lea     rax, [rsp+370h+var_318]
0x18004229f  mov     [rsp+370h+samDesired], r15d; cbData
0x1800422a4  xor     r8d, r8d; Reserved
0x1800422a7  mov     [rsp+370h+phkResult], rax; lpData
0x1800422ac  mov     rcx, rbx; hKey
0x1800422af  call    cs:__imp_RegSetValueExW
0x1800422b5  lea     r8, [rsi+1C0h]; unsigned __int16 *
0x1800422bc  test    r8, r8
0x1800422bf  jz      short loc_1800422D2
0x1800422c1  lea     rdx, aOrchestratorty; "OrchestratorType"
0x1800422c8  mov     rcx, rbx; hKey
0x1800422cb  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x1800422d0  mov     edi, eax
0x1800422d2  movsxd  rax, dword ptr [rsp+370h+Data]
0x1800422d7  lea     r8, off_1800AF008; "AT_MDM_RENEWAL_DISCOVERY"
0x1800422de  add     rax, rax
0x1800422e1  mov     r8, [r8+rax*8]; unsigned __int16 *
0x1800422e5  test    r8, r8
0x1800422e8  jz      short loc_180042300
0x1800422ea  lea     rdx, aActivitytypena; "ActivityTypeName"
0x1800422f1  mov     rcx, rbx; hKey
0x1800422f4  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x1800422f9  jmp     short loc_180042300
0x1800422fb  mov     edi, 8000FFFFh
0x180042300  test    rbx, rbx
0x180042303  jz      short loc_18004230E
0x180042305  mov     rcx, rbx; hKey
0x180042308  call    cs:__imp_RegCloseKey
0x18004230e  mov     eax, edi
0x180042310  mov     rcx, [rbp+270h+var_40]
0x180042317  xor     rcx, rsp; StackCookie
0x18004231a  call    __security_check_cookie
0x18004231f  add     rsp, 348h
0x180042326  pop     r15
0x180042328  pop     r12
0x18004232a  pop     rdi
0x18004232b  pop     rsi
0x18004232c  pop     rbx
0x18004232d  pop     rbp
0x18004232e  retn
```
