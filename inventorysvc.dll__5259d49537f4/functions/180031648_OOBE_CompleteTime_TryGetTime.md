# OOBE::CompleteTime::TryGetTime

- ea: `0x180031648`
- end: `0x180031890`
- name: `OOBE::CompleteTime::TryGetTime`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003060c`

## callees

- `0x18000ec54`
- `0x180031544`
- `0x180031648`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003181c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180031867`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003181c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180031867`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003187d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003187d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003176c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003176c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800316f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003178c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800317db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800317ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800316f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003178c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800317db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800317ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800316b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031721`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800316b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031721`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800316a1`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800316dd`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800316a1`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800316dd`

## string_xrefs

- `0x180031693`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompleteTimestamp`
- `0x1800316cf`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompleteTimestamp`
- `0x18003169a`: `OOBECompleteTimestamp`
- `0x1800316d6`: `OOBECompleteTimestamp`
- `0x18003180f`: `OOBECompleteTimestamp`
- `0x1800317c0`: `onecoreuap\internal\shell\inc\OobeCompleteTime.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OOBE::CompleteTime::TryGetTime(bool *a1, _OWORD *a2)
{
  LPVOID v4; // rax
  void *v5; // rbx
  WCHAR *v6; // rax
  const unsigned __int16 *v7; // r8
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  signed int v10; // ebx
  unsigned __int16 **phkResult; // [rsp+20h] [rbp-30h]
  int phkResulta; // [rsp+20h] [rbp-30h]
  unsigned __int64 *pvData; // [rsp+28h] [rbp-28h]
  unsigned int pcbData; // [rsp+30h] [rbp-20h]
  HKEY hkey[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  SIZE_T cb; // [rsp+80h] [rbp+30h] BYREF
  DWORD v19; // [rsp+90h] [rbp+40h] BYREF
  LPCWSTR lpSubKey; // [rsp+98h] [rbp+48h] BYREF

  *a1 = 0;
  v19 = 16;
  *a2 = 0;
  hkey[0] = 0;
  lpSubKey = 0;
  LODWORD(cb) = 0;
  phkResult = (unsigned __int16 **)&cb;
  if ( (unsigned int)GetPersistedRegistryLocationW(
                       L"OOBECompleteTimestamp",
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\OOBECompleteTimestamp",
                       &lpSubKey,
                       0) == 234 )
  {
    v4 = CoTaskMemAlloc((unsigned int)cb);
    v5 = v4;
    if ( v4 )
    {
      phkResult = 0;
      if ( (unsigned int)GetPersistedRegistryLocationW(
                           L"OOBECompleteTimestamp",
                           L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\OOBECompleteTimestamp",
                           v4,
                           (unsigned int)cb) )
        CoTaskMemFree(v5);
      else
        lpSubKey = (LPCWSTR)v5;
    }
  }
  if ( lpSubKey )
    goto LABEL_10;
  lpSubKey = 0;
  hkey[1] = 0;
  if ( !is_mul_ok(0x45u, 2u) )
  {
    v8 = -2147024362;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OobeRedirectionKeyHelper.h",
      (const char *)v8,
      (int)phkResult);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OobeCompleteTime.h",
      (const char *)v8,
      phkResulta);
    if ( lpSubKey )
      CoTaskMemFree((LPVOID)lpSubKey);
    goto LABEL_23;
  }
  v6 = (WCHAR *)CoTaskMemAlloc(0x8Au);
  lpSubKey = v6;
  v8 = v6 == 0 ? 0x8007000E : 0;
  if ( !v6 )
    goto LABEL_18;
  StringCchCopyNExW(v6, 0x45u, v7, 0x44u, phkResult, pvData, pcbData);
LABEL_10:
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, hkey);
  v10 = v9;
  if ( !v9 )
  {
    if ( lpSubKey )
      CoTaskMemFree((LPVOID)lpSubKey);
    goto LABEL_22;
  }
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( lpSubKey )
    CoTaskMemFree((LPVOID)lpSubKey);
  if ( v10 >= 0 )
LABEL_22:
    *a1 = RegGetValueW(hkey[0], 0, L"OOBECompleteTimestamp", 0x20000008u, 0, a2, &v19) == 0;
LABEL_23:
  if ( !*a1 )
  {
    v19 = 16;
    *a1 = RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
            L"EndTimeStamp",
            0x20000008u,
            0,
            a2,
            &v19) == 0;
  }
  if ( hkey[0] )
    RegCloseKey(hkey[0]);
  return 0;
}

```

## disassembly

```asm
0x180031648  push    rbp
0x18003164a  push    rbx
0x18003164b  push    rsi
0x18003164c  push    rdi
0x18003164d  push    r15
0x18003164f  mov     rbp, rsp
0x180031652  sub     rsp, 50h
0x180031656  mov     rsi, rdx
0x180031659  mov     rdi, rcx
0x18003165c  mov     byte ptr [rcx], 0
0x18003165f  mov     [rbp+arg_10], 10h
0x180031666  xorps   xmm0, xmm0
0x180031669  movups  xmmword ptr [rdx], xmm0
0x18003166c  mov     [rbp+hkey], 0
0x180031674  mov     [rbp+lpSubKey], 0
0x18003167c  mov     dword ptr [rbp+cb], 0
0x180031683  lea     rax, [rbp+cb]
0x180031687  mov     [rsp+50h+phkResult], rax
0x18003168c  xor     r9d, r9d
0x18003168f  lea     r8, [rbp+lpSubKey]
0x180031693  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003169a  lea     rcx, aOobecompleteti; "OOBECompleteTimestamp"
0x1800316a1  call    cs:__imp_GetPersistedRegistryLocationW
0x1800316a7  cmp     eax, 0EAh
0x1800316ac  jnz     short loc_1800316F6
0x1800316ae  mov     ecx, dword ptr [rbp+cb]; cb
0x1800316b1  call    cs:__imp_CoTaskMemAlloc
0x1800316b7  mov     rbx, rax
0x1800316ba  test    rax, rax
0x1800316bd  jz      short loc_1800316F6
0x1800316bf  mov     [rsp+50h+phkResult], 0; int
0x1800316c8  mov     r9d, dword ptr [rbp+cb]
0x1800316cc  mov     r8, rax
0x1800316cf  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800316d6  lea     rcx, aOobecompleteti; "OOBECompleteTimestamp"
0x1800316dd  call    cs:__imp_GetPersistedRegistryLocationW
0x1800316e3  test    eax, eax
0x1800316e5  jnz     short loc_1800316ED
0x1800316e7  mov     [rbp+lpSubKey], rbx
0x1800316eb  jmp     short loc_1800316F6
0x1800316ed  mov     rcx, rbx; pv
0x1800316f0  call    cs:__imp_CoTaskMemFree
0x1800316f6  cmp     [rbp+lpSubKey], 0
0x1800316fb  jnz     short loc_18003174F
0x1800316fd  mov     [rbp+lpSubKey], 0
0x180031705  mov     [rbp+var_8], 0
0x18003170d  mov     eax, 2
0x180031712  lea     r15d, [rax+43h]
0x180031716  mul     r15
0x180031719  test    rdx, rdx
0x18003171c  jnz     short loc_18003179C
0x18003171e  mov     rcx, rax; cb
0x180031721  call    cs:__imp_CoTaskMemAlloc
0x180031727  mov     [rbp+lpSubKey], rax
0x18003172b  mov     rcx, rax
0x18003172e  neg     rcx
0x180031731  sbb     ebx, ebx
0x180031733  not     ebx
0x180031735  and     ebx, 8007000Eh
0x18003173b  test    rax, rax
0x18003173e  jz      short loc_1800317A1
0x180031740  lea     r9d, [r15-1]; unsigned __int64
0x180031744  mov     edx, r15d; unsigned __int64
0x180031747  mov     rcx, rax; unsigned __int16 *
0x18003174a  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18003174f  lea     rax, [rbp+hkey]
0x180031753  mov     [rsp+50h+phkResult], rax; phkResult
0x180031758  mov     r9d, 2001Fh; samDesired
0x18003175e  xor     r8d, r8d; ulOptions
0x180031761  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180031765  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003176c  call    cs:__imp_RegOpenKeyExW
0x180031772  mov     ebx, eax
0x180031774  test    eax, eax
0x180031776  jz      short loc_1800317E3
0x180031778  jle     short loc_180031783
0x18003177a  movzx   ebx, ax
0x18003177d  or      ebx, 80070000h
0x180031783  mov     rcx, [rbp+lpSubKey]; pv
0x180031787  test    rcx, rcx
0x18003178a  jz      short loc_180031792
0x18003178c  call    cs:__imp_CoTaskMemFree
0x180031792  test    ebx, ebx
0x180031794  js      loc_180031829
0x18003179a  jmp     short loc_1800317F2
0x18003179c  mov     ebx, 80070216h
0x1800317a1  mov     rcx, [rbp+28h]; this
0x1800317a5  mov     r9d, ebx; char *
0x1800317a8  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\OobeR"...
0x1800317af  mov     edx, 2Eh ; '.'; void *
0x1800317b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800317b9  mov     rcx, [rbp+28h]; this
0x1800317bd  mov     r9d, ebx; char *
0x1800317c0  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OobeC"...
0x1800317c7  mov     edx, 16h; void *
0x1800317cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800317d1  nop
0x1800317d2  mov     rcx, [rbp+lpSubKey]; pv
0x1800317d6  test    rcx, rcx
0x1800317d9  jz      short loc_180031829
0x1800317db  call    cs:__imp_CoTaskMemFree
0x1800317e1  jmp     short loc_180031829
0x1800317e3  mov     rcx, [rbp+lpSubKey]; pv
0x1800317e7  test    rcx, rcx
0x1800317ea  jz      short loc_1800317F2
0x1800317ec  call    cs:__imp_CoTaskMemFree
0x1800317f2  lea     rax, [rbp+arg_10]
0x1800317f6  mov     qword ptr [rsp+50h+pcbData], rax; pcbData
0x1800317fb  mov     [rsp+50h+pvData], rsi; pvData
0x180031800  mov     [rsp+50h+phkResult], 0; pdwType
0x180031809  mov     r9d, 20000008h; dwFlags
0x18003180f  lea     r8, aOobecompleteti; "OOBECompleteTimestamp"
0x180031816  xor     edx, edx; lpSubKey
0x180031818  mov     rcx, [rbp+hkey]; hkey
0x18003181c  call    cs:__imp_RegGetValueW
0x180031822  test    eax, eax
0x180031824  setz    al
0x180031827  mov     [rdi], al
0x180031829  cmp     byte ptr [rdi], 0
0x18003182c  jnz     short loc_180031874
0x18003182e  mov     [rbp+arg_10], 10h
0x180031835  lea     rax, [rbp+arg_10]
0x180031839  mov     qword ptr [rsp+50h+pcbData], rax; pcbData
0x18003183e  mov     [rsp+50h+pvData], rsi; pvData
0x180031843  mov     [rsp+50h+phkResult], 0; pdwType
0x18003184c  mov     r9d, 20000008h; dwFlags
0x180031852  lea     r8, aEndtimestamp; "EndTimeStamp"
0x180031859  lea     rdx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180031860  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180031867  call    cs:__imp_RegGetValueW
0x18003186d  test    eax, eax
0x18003186f  setz    al
0x180031872  mov     [rdi], al
0x180031874  mov     rcx, [rbp+hkey]; hKey
0x180031878  test    rcx, rcx
0x18003187b  jz      short loc_180031883
0x18003187d  call    cs:__imp_RegCloseKey
0x180031883  xor     eax, eax
0x180031885  add     rsp, 50h
0x180031889  pop     r15
0x18003188b  pop     rdi
0x18003188c  pop     rsi
0x18003188d  pop     rbx
0x18003188e  pop     rbp
0x18003188f  retn
```
