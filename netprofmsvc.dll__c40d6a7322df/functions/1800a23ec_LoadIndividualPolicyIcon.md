# LoadIndividualPolicyIcon

- ea: `0x1800a23ec`
- end: `0x1800a25c4`
- name: `LoadIndividualPolicyIcon`
- size: `472`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpValue)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ce64c`

## callees

- `0x180015628`
- `0x180035cd8`
- `0x180035dc4`
- `0x18005530c`
- `0x1800a23ec`
- `0x1800a88a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a24a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a2505`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a24a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a2505`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2567`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2567`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2441`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a24e6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a2441`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a24e6`

## string_xrefs

- `0x1800a2456`: `onecore\net\netprofiles\service\src\host\lib\policy.cpp`
- `0x1800a2485`: `onecore\net\netprofiles\service\src\host\lib\policy.cpp`
- `0x1800a2553`: `onecore\net\netprofiles\service\src\host\lib\policy.cpp`
- `0x1800a258a`: `onecore\net\netprofiles\service\src\host\lib\policy.cpp`

## pseudocode

```c
int __fastcall LoadIndividualPolicyIcon(HKEY hkey, LPCWSTR lpValue, unsigned __int8 **a3, unsigned int *a4)
{
  unsigned int ValueW; // eax
  unsigned int v10; // ebx
  void *pvData; // rdi
  __int64 v12; // rdx
  LSTATUS v13; // eax
  int v14; // esi
  __int64 v15; // r9
  SIZE_T v16; // rsi
  unsigned __int8 *v17; // rax
  unsigned __int8 *v18; // rbx
  unsigned __int8 *i; // rcx
  int v20; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-78h]
  unsigned int v22; // [rsp+40h] [rbp-58h] BYREF
  void *v23; // [rsp+48h] [rbp-50h] BYREF
  SIZE_T cb; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  LODWORD(cb) = 0;
  ValueW = RegGetValueW(hkey, 0, lpValue, 2u, 0, 0, (LPDWORD)&cb);
  if ( ValueW )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x50F,
             (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\policy.cpp",
             (const char *)ValueW,
             pdwType);
  if ( (unsigned int)cb < 6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x512,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\policy.cpp",
      (const char *)0x80070057LL,
      pdwType);
    return -2147024809;
  }
  v10 = ((unsigned int)cb >> 1) - 1;
  pvData = CoTaskMemAlloc((unsigned int)cb);
  v23 = pvData;
  if ( !pvData )
  {
    v12 = 1302;
LABEL_16:
    v14 = -2147024882;
    v15 = 2147942414LL;
    goto LABEL_17;
  }
  v13 = RegGetValueW(hkey, 0, lpValue, 2u, 0, pvData, (LPDWORD)&cb);
  v14 = v13;
  if ( v13 >= 0 )
  {
    v16 = v10 >> 1;
    v17 = (unsigned __int8 *)CoTaskMemAlloc(v16);
    v18 = v17;
    if ( v17 )
    {
      for ( i = &v17[v16]; v17 != i; ++v17 )
        *v17 = 0;
      v22 = 0;
      v20 = BytesFromHexString((const wchar_t *)pvData, v16, v18, &v22);
      v14 = v20;
      if ( v20 >= 0 )
      {
        *a3 = v18;
        *a4 = v22;
        v14 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x51F,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\policy.cpp",
          (const char *)(unsigned int)v20,
          pdwType);
        CoTaskMemFree(v18);
      }
      goto LABEL_18;
    }
    v12 = 1308;
    goto LABEL_16;
  }
  v15 = (unsigned int)v13;
  v12 = 1303;
LABEL_17:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\policy.cpp",
    (const char *)v15,
    pdwType);
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v23);
  return v14;
}

```

## disassembly

```asm
0x1800a23ec  mov     r11, rsp
0x1800a23ef  push    rbx
0x1800a23f0  push    rbp
0x1800a23f1  push    rsi
0x1800a23f2  push    rdi
0x1800a23f3  push    r14
0x1800a23f5  push    r15
0x1800a23f7  sub     rsp, 68h
0x1800a23fb  mov     rax, cs:__security_cookie
0x1800a2402  xor     rax, rsp
0x1800a2405  mov     [rsp+98h+var_40], rax
0x1800a240a  mov     r15, r9
0x1800a240d  mov     r14, r8
0x1800a2410  mov     rbp, rdx
0x1800a2413  mov     rsi, rcx
0x1800a2416  mov     dword ptr [rsp+98h+cb], 0
0x1800a241e  lea     rax, [r11-48h]
0x1800a2422  mov     [r11-68h], rax
0x1800a2426  mov     qword ptr [r11-70h], 0
0x1800a242e  mov     qword ptr [r11-78h], 0
0x1800a2436  mov     r9d, 2; dwFlags
0x1800a243c  mov     r8, rdx; lpValue
0x1800a243f  xor     edx, edx; lpSubKey
0x1800a2441  call    cs:__imp_RegGetValueW
0x1800a2447  test    eax, eax
0x1800a2449  jz      short loc_1800A246C
0x1800a244b  mov     rcx, [rsp+98h]; this
0x1800a2453  mov     r9d, eax; char *
0x1800a2456  lea     r8, aOnecoreNetNetp_16; "onecore\\net\\netprofiles\\service\\src"...
0x1800a245d  mov     edx, 50Fh; void *
0x1800a2462  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a2467  jmp     loc_1800A25AA
0x1800a246c  mov     ecx, dword ptr [rsp+98h+cb]; cb
0x1800a2470  cmp     ecx, 6
0x1800a2473  jnb     short loc_1800A249D
0x1800a2475  mov     rcx, [rsp+98h]; this
0x1800a247d  mov     ebx, 80070057h
0x1800a2482  mov     r9d, ebx; char *
0x1800a2485  lea     r8, aOnecoreNetNetp_16; "onecore\\net\\netprofiles\\service\\src"...
0x1800a248c  mov     edx, 512h; void *
0x1800a2491  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2496  mov     eax, ebx
0x1800a2498  jmp     loc_1800A25AA
0x1800a249d  mov     ebx, ecx
0x1800a249f  shr     ebx, 1
0x1800a24a1  dec     ebx
0x1800a24a3  call    cs:__imp_CoTaskMemAlloc
0x1800a24a9  mov     rdi, rax
0x1800a24ac  mov     [rsp+98h+var_50], rax
0x1800a24b1  test    rax, rax
0x1800a24b4  jnz     short loc_1800A24C0
0x1800a24b6  mov     edx, 516h
0x1800a24bb  jmp     loc_1800A2582
0x1800a24c0  lea     rax, [rsp+98h+cb]
0x1800a24c5  mov     [rsp+98h+pcbData], rax; pcbData
0x1800a24ca  mov     [rsp+98h+pvData], rdi; pvData
0x1800a24cf  mov     [rsp+98h+pdwType], 0; int
0x1800a24d8  mov     r9d, 2; dwFlags
0x1800a24de  mov     r8, rbp; lpValue
0x1800a24e1  xor     edx, edx; lpSubKey
0x1800a24e3  mov     rcx, rsi; hkey
0x1800a24e6  call    cs:__imp_RegGetValueW
0x1800a24ec  mov     esi, eax
0x1800a24ee  test    eax, eax
0x1800a24f0  jns     short loc_1800A24FF
0x1800a24f2  mov     r9d, eax
0x1800a24f5  mov     edx, 517h
0x1800a24fa  jmp     loc_1800A258A
0x1800a24ff  shr     ebx, 1
0x1800a2501  mov     esi, ebx
0x1800a2503  mov     ecx, ebx; cb
0x1800a2505  call    cs:__imp_CoTaskMemAlloc
0x1800a250b  mov     rbx, rax
0x1800a250e  test    rax, rax
0x1800a2511  jz      short loc_1800A257D
0x1800a2513  lea     rcx, [rsi+rax]
0x1800a2517  cmp     rax, rcx
0x1800a251a  jz      short loc_1800A2528
0x1800a251c  xor     edx, edx
0x1800a251e  mov     [rax], dl
0x1800a2520  inc     rax
0x1800a2523  cmp     rax, rcx
0x1800a2526  jnz     short loc_1800A251C
0x1800a2528  mov     [rsp+98h+var_58], 0
0x1800a2530  lea     r9, [rsp+98h+var_58]; unsigned int *
0x1800a2535  mov     r8, rbx; unsigned __int8 *
0x1800a2538  mov     edx, esi; unsigned int
0x1800a253a  mov     rcx, rdi; wchar_t *
0x1800a253d  call    ?BytesFromHexString@@YAJPEB_WKPEAEPEAK@Z; BytesFromHexString(wchar_t const *,ulong,uchar *,ulong *)
0x1800a2542  mov     esi, eax
0x1800a2544  test    eax, eax
0x1800a2546  jns     short loc_1800A256F
0x1800a2548  mov     rcx, [rsp+98h]; this
0x1800a2550  mov     r9d, eax; char *
0x1800a2553  lea     r8, aOnecoreNetNetp_16; "onecore\\net\\netprofiles\\service\\src"...
0x1800a255a  mov     edx, 51Fh; void *
0x1800a255f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2564  mov     rcx, rbx; pv
0x1800a2567  call    cs:__imp_CoTaskMemFree
0x1800a256d  jmp     short loc_1800A259E
0x1800a256f  mov     [r14], rbx
0x1800a2572  mov     eax, [rsp+98h+var_58]
0x1800a2576  mov     [r15], eax
0x1800a2579  xor     esi, esi
0x1800a257b  jmp     short loc_1800A259E
0x1800a257d  mov     edx, 51Ch; void *
0x1800a2582  mov     esi, 8007000Eh
0x1800a2587  mov     r9d, esi; char *
0x1800a258a  lea     r8, aOnecoreNetNetp_16; "onecore\\net\\netprofiles\\service\\src"...
0x1800a2591  mov     rcx, [rsp+98h]; this
0x1800a2599  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a259e  lea     rcx, [rsp+98h+var_50]
0x1800a25a3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a25a8  mov     eax, esi
0x1800a25aa  mov     rcx, [rsp+98h+var_40]
0x1800a25af  xor     rcx, rsp; StackCookie
0x1800a25b2  call    __security_check_cookie
0x1800a25b7  add     rsp, 68h
0x1800a25bb  pop     r15
0x1800a25bd  pop     r14
0x1800a25bf  pop     rdi
0x1800a25c0  pop     rsi
0x1800a25c1  pop     rbp
0x1800a25c2  pop     rbx
0x1800a25c3  retn
```
