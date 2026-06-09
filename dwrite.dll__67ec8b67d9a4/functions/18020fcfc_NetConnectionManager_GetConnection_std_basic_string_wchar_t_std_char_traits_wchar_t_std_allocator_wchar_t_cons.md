# NetConnectionManager::GetConnection(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ushort,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18020fcfc`
- end: `0x18020fff6`
- name: `?GetConnection@NetConnectionManager@@QEAA?AV?$IntrusivePtr@VNetConnection@@@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@G00@Z`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801fb280`

## callees

- `0x180124e28`
- `0x18012a85c`
- `0x1801409e0`
- `0x1801446c8`
- `0x18018b780`
- `0x1801c856c`
- `0x1801cd438`
- `0x1801db610`
- `0x1801ef8d4`
- `0x18020fcfc`
- `0x18020fffc`
- `0x180210034`
- `0x180212490`
- `0x180212f4c`
- `0x18021deb8`
- `0x180254390`
- `0x1802543b0`

## import_xrefs

- `kernel32!GetLastError` at `0x18020fe0f`
- `kernel32!GetLastError` at `0x18020fe0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18020ffc2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18020ffc2`
- `WININET!InternetCreateUrlW` at `0x18020fe05`
- `WININET!InternetCreateUrlW` at `0x18020fe4b`
- `WININET!InternetCreateUrlW` at `0x18020fe05`
- `WININET!InternetCreateUrlW` at `0x18020fe4b`
- `WININET!InternetConnectW` at `0x18020ff17`
- `WININET!InternetConnectW` at `0x18020ff17`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
NetConnection **__fastcall NetConnectionManager::GetConnection(
        __int64 a1,
        NetConnection **a2,
        __int64 a3,
        INTERNET_PORT a4,
        __int64 a5,
        __int64 a6)
{
  WCHAR *v10; // rdi
  WCHAR *v11; // r14
  WCHAR *v12; // rax
  DWORD v13; // r8d
  DWORD *v14; // rax
  DWORD v15; // edx
  DWORD *v16; // rcx
  WCHAR *v17; // r8
  WCHAR *v18; // r8
  LPWSTR *v19; // rcx
  __int64 v20; // r15
  __int64 v21; // rax
  NetConnection *v22; // rcx
  NetConnection *v23; // rbx
  HINTERNET v24; // rbx
  _QWORD *v25; // rdi
  NetConnection *v26; // rbx
  DWORD dwUrlLength[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v29; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v30[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct $2B4FDC4BF487E67F052937EE78FAE255 UrlComponents; // [rsp+70h] [rbp-90h] BYREF
  NetConnection **v33; // [rsp+E0h] [rbp-20h]
  char v34[16]; // [rsp+E8h] [rbp-18h] BYREF
  LPWSTR lpszUrl[2]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v36[2]; // [rsp+108h] [rbp+8h]
  unsigned __int64 v37; // [rsp+110h] [rbp+10h]

  v33 = a2;
  v10 = (WCHAR *)a5;
  v11 = (WCHAR *)a6;
  *a2 = 0;
  dwUrlLength[1] = 1;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.nPort = a4;
  if ( *(_QWORD *)(a3 + 24) <= 7u )
    v12 = (WCHAR *)a3;
  else
    v12 = *(WCHAR **)a3;
  UrlComponents.lpszHostName = v12;
  v13 = *(_DWORD *)(a3 + 16);
  UrlComponents.dwHostNameLength = v13;
  v14 = (DWORD *)(a5 + 16);
  if ( *(_QWORD *)(a5 + 16) )
  {
    if ( *(_QWORD *)(a5 + 24) > 7u )
      v10 = *(WCHAR **)a5;
    UrlComponents.lpszUserName = v10;
    v15 = *v14;
    UrlComponents.dwUserNameLength = *v14;
  }
  else
  {
    v15 = *v14;
  }
  v16 = (DWORD *)(a6 + 16);
  if ( *(_QWORD *)(a6 + 16) )
  {
    if ( *(_QWORD *)(a6 + 24) > 7u )
      v11 = *(WCHAR **)a6;
    UrlComponents.lpszPassword = v11;
    UrlComponents.dwPasswordLength = *v16;
  }
  dwUrlLength[0] = v15 + v13 + 17 + *v16;
  std::wstring::wstring(lpszUrl, dwUrlLength[0]);
  v17 = (WCHAR *)lpszUrl;
  if ( v37 > 7 )
    v17 = lpszUrl[0];
  if ( !InternetCreateUrlW(&UrlComponents, 0, v17, dwUrlLength) )
  {
    if ( GetLastError() != 122 )
      goto LABEL_20;
    dwUrlLength[0] = (dwUrlLength[0] >> 1) + 1;
    std::wstring::resize(lpszUrl, dwUrlLength[0]);
    v18 = (WCHAR *)lpszUrl;
    if ( v37 > 7 )
      v18 = lpszUrl[0];
    if ( !InternetCreateUrlW(&UrlComponents, 0, v18, dwUrlLength) )
LABEL_20:
      OSException::ThrowLastError();
  }
  std::wstring::resize(lpszUrl, dwUrlLength[0]);
  v19 = lpszUrl;
  if ( v37 > 7 )
    v19 = (LPWSTR *)lpszUrl[0];
  v20 = HashBlob(v19, 2LL * *(_QWORD *)v36, v36[0]);
  LockHolder::LockHolder((LockHolder *)lpCriticalSection, (struct Lock *)(a1 + 8));
  v21 = HashTableImpl::Find(
          a1 + 56,
          v30,
          (unsigned int)v20,
          lpszUrl,
          HashTable<std::wstring,NetConnection>::IsEqualKeyWrapper);
  if ( *(_QWORD *)v21 == *(_QWORD *)(a1 + 72) + 24LL * *(unsigned int *)(a1 + 80) )
  {
    v24 = InternetConnectW(
            *(HINTERNET *)(a1 + 48),
            UrlComponents.lpszHostName,
            UrlComponents.nPort,
            UrlComponents.lpszUserName,
            UrlComponents.lpszPassword,
            3u,
            0,
            0);
    v30[0] = v24;
    if ( !v24 )
      OSException::ThrowLastError();
    v25 = operator new(0x40u);
    v29 = v25;
    *(_DWORD *)v25 = 0;
    v25[1] = a1;
    _InterlockedIncrement((volatile signed __int32 *)a1);
    *((_DWORD *)v25 + 4) = v20;
    std::wstring::wstring(v25 + 3, lpszUrl);
    v25[7] = v24;
    v30[0] = 0;
    v29 = v25;
    HashTableImpl::Add(a1 + 56, v34, v20, v25);
    v29 = 0;
    v26 = *a2;
    *a2 = (NetConnection *)v25;
    AddReference<NetConnection>(v25);
    ReleaseReference<NetConnection>(v26);
    ScopedPtr<NetConnection>::~ScopedPtr<NetConnection>(&v29);
    ScopedHandle<NetHandlePolicy,void *>::~ScopedHandle<NetHandlePolicy,void *>(v30);
  }
  else
  {
    v22 = *(NetConnection **)(*(_QWORD *)v21 + 8LL);
    v23 = *a2;
    *a2 = v22;
    AddReference<NetConnection>(v22);
    ReleaseReference<NetConnection>(v23);
  }
  LeaveCriticalSection(lpCriticalSection[0]);
  std::wstring::_Tidy_deallocate(lpszUrl);
  return a2;
}

```

## disassembly

```asm
0x18020fcfc  push    rbp
0x18020fcfe  push    rbx
0x18020fcff  push    rsi
0x18020fd00  push    rdi
0x18020fd01  push    r12
0x18020fd03  push    r13
0x18020fd05  push    r14
0x18020fd07  push    r15
0x18020fd09  lea     rbp, [rsp-28h]
0x18020fd0e  sub     rsp, 128h
0x18020fd15  mov     rax, cs:__security_cookie
0x18020fd1c  xor     rax, rsp
0x18020fd1f  mov     [rbp+60h+var_48], rax
0x18020fd23  movzx   ebx, r9w
0x18020fd27  mov     r15, r8
0x18020fd2a  mov     rsi, rdx
0x18020fd2d  mov     r13, rcx
0x18020fd30  mov     [rbp+60h+var_80], rdx
0x18020fd34  mov     rdi, [rbp+60h+arg_20]
0x18020fd3b  mov     r14, [rbp+60h+arg_28]
0x18020fd42  mov     [rsp+160h+var_11C], 0
0x18020fd4a  mov     qword ptr [rdx], 0
0x18020fd51  mov     [rsp+160h+var_11C], 1
0x18020fd59  mov     r12d, 68h ; 'h'
0x18020fd5f  mov     r8d, r12d; Size
0x18020fd62  xor     edx, edx; Val
0x18020fd64  lea     rcx, [rsp+160h+UrlComponents]; void *
0x18020fd69  call    memset_0
0x18020fd6e  mov     [rsp+160h+UrlComponents.dwStructSize], r12d
0x18020fd73  mov     [rbp+60h+UrlComponents.nPort], bx
0x18020fd77  cmp     qword ptr [r15+18h], 7
0x18020fd7c  jbe     short loc_18020FD83
0x18020fd7e  mov     rax, [r15]
0x18020fd81  jmp     short loc_18020FD86
0x18020fd83  mov     rax, r15
0x18020fd86  mov     [rbp+60h+UrlComponents.lpszHostName], rax
0x18020fd8a  mov     r8d, [r15+10h]
0x18020fd8e  mov     [rbp+60h+UrlComponents.dwHostNameLength], r8d
0x18020fd92  lea     rax, [rdi+10h]
0x18020fd96  xor     ebx, ebx
0x18020fd98  cmp     [rax], rbx
0x18020fd9b  jnz     short loc_18020FDA1
0x18020fd9d  mov     edx, [rax]
0x18020fd9f  jmp     short loc_18020FDB4
0x18020fda1  cmp     qword ptr [rdi+18h], 7
0x18020fda6  jbe     short loc_18020FDAB
0x18020fda8  mov     rdi, [rdi]
0x18020fdab  mov     [rbp+60h+UrlComponents.lpszUserName], rdi
0x18020fdaf  mov     edx, [rax]
0x18020fdb1  mov     [rbp+60h+UrlComponents.dwUserNameLength], edx
0x18020fdb4  lea     rcx, [r14+10h]
0x18020fdb8  cmp     [rcx], rbx
0x18020fdbb  jz      short loc_18020FDD0
0x18020fdbd  cmp     qword ptr [r14+18h], 7
0x18020fdc2  jbe     short loc_18020FDC7
0x18020fdc4  mov     r14, [r14]
0x18020fdc7  mov     [rbp+60h+UrlComponents.lpszPassword], r14
0x18020fdcb  mov     eax, [rcx]
0x18020fdcd  mov     [rbp+60h+UrlComponents.dwPasswordLength], eax
0x18020fdd0  mov     eax, [rcx]
0x18020fdd2  add     r8d, 11h
0x18020fdd6  add     eax, r8d
0x18020fdd9  add     eax, edx
0x18020fddb  mov     [rsp+160h+dwUrlLength], eax
0x18020fddf  mov     edx, eax
0x18020fde1  lea     rcx, [rbp+60h+lpszUrl]
0x18020fde5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x18020fdea  nop
0x18020fdeb  lea     r8, [rbp+60h+lpszUrl]
0x18020fdef  cmp     [rbp+60h+var_50], 7
0x18020fdf4  cmova   r8, [rbp+60h+lpszUrl]; lpszUrl
0x18020fdf9  lea     r9, [rsp+160h+dwUrlLength]; lpdwUrlLength
0x18020fdfe  xor     edx, edx; dwFlags
0x18020fe00  lea     rcx, [rsp+160h+UrlComponents]; lpUrlComponents
0x18020fe05  call    cs:__imp_InternetCreateUrlW
0x18020fe0b  test    eax, eax
0x18020fe0d  jnz     short loc_18020FE5B
0x18020fe0f  call    cs:__imp_GetLastError
0x18020fe15  cmp     eax, 7Ah ; 'z'
0x18020fe18  jnz     short loc_18020FE55
0x18020fe1a  mov     eax, [rsp+160h+dwUrlLength]
0x18020fe1e  shr     eax, 1
0x18020fe20  inc     eax
0x18020fe22  mov     [rsp+160h+dwUrlLength], eax
0x18020fe26  mov     edx, eax
0x18020fe28  lea     rcx, [rbp+60h+lpszUrl]
0x18020fe2c  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18020fe31  lea     r8, [rbp+60h+lpszUrl]
0x18020fe35  cmp     [rbp+60h+var_50], 7
0x18020fe3a  cmova   r8, [rbp+60h+lpszUrl]; lpszUrl
0x18020fe3f  lea     r9, [rsp+160h+dwUrlLength]; lpdwUrlLength
0x18020fe44  xor     edx, edx; dwFlags
0x18020fe46  lea     rcx, [rsp+160h+UrlComponents]; lpUrlComponents
0x18020fe4b  call    cs:__imp_InternetCreateUrlW
0x18020fe51  test    eax, eax
0x18020fe53  jnz     short loc_18020FE5B
0x18020fe55  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x18020fe5b  mov     edx, [rsp+160h+dwUrlLength]
0x18020fe5f  lea     rcx, [rbp+60h+lpszUrl]
0x18020fe63  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18020fe68  lea     rcx, [rbp+60h+lpszUrl]
0x18020fe6c  cmp     [rbp+60h+var_50], 7
0x18020fe71  cmova   rcx, [rbp+60h+lpszUrl]; void *
0x18020fe76  mov     rdx, qword ptr [rbp+60h+var_58]
0x18020fe7a  mov     r8d, edx; unsigned int
0x18020fe7d  add     rdx, rdx; unsigned __int64
0x18020fe80  call    ?HashBlob@@YAIPEBX_KI@Z; HashBlob(void const *,unsigned __int64,uint)
0x18020fe85  mov     r15d, eax
0x18020fe88  lea     rdx, [r13+8]; struct Lock *
0x18020fe8c  lea     rcx, [rsp+160h+lpCriticalSection]; this
0x18020fe91  call    ??0LockHolder@@QEAA@AEAVLock@@@Z; LockHolder::LockHolder(Lock &)
0x18020fe96  nop
0x18020fe97  lea     rax, ?IsEqualKeyWrapper@?$HashTable@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VNetConnection@@@@CA_NPEBX0@Z; HashTable<std::wstring,NetConnection>::IsEqualKeyWrapper(void const *,void const *)
0x18020fe9e  mov     [rsp+160h+lpszPassword], rax
0x18020fea3  lea     r9, [rbp+60h+lpszUrl]
0x18020fea7  mov     r8d, r15d
0x18020feaa  lea     rdx, [rsp+160h+var_110]
0x18020feaf  lea     rcx, [r13+38h]
0x18020feb3  call    ?Find@HashTableImpl@@QEBA?AViterator@1@_KPEBXP6A_N11@Z@Z; HashTableImpl::Find(unsigned __int64,void const *,bool (*)(void const *,void const *))
0x18020feb8  mov     rdx, [rax]
0x18020febb  mov     eax, [r13+50h]
0x18020febf  lea     rcx, [rax+rax*2]
0x18020fec3  mov     rax, [r13+48h]
0x18020fec7  lea     rcx, [rax+rcx*8]
0x18020fecb  cmp     rdx, rcx
0x18020fece  jz      short loc_18020FEEC
0x18020fed0  mov     rcx, [rdx+8]
0x18020fed4  mov     rbx, [rsi]
0x18020fed7  mov     [rsi], rcx
0x18020feda  call    ??$AddReference@VNetConnection@@@@YAXPEAVNetConnection@@@Z; AddReference<NetConnection>(NetConnection *)
0x18020fedf  mov     rcx, rbx; this
0x18020fee2  call    ??$ReleaseReference@VNetConnection@@@@YAXPEAVNetConnection@@@Z; ReleaseReference<NetConnection>(NetConnection *)
0x18020fee7  jmp     loc_18020FFBD
0x18020feec  mov     [rsp+160h+dwContext], rbx; dwContext
0x18020fef1  mov     [rsp+160h+dwFlags], ebx; dwFlags
0x18020fef5  mov     [rsp+160h+dwService], 3; dwService
0x18020fefd  mov     rax, [rbp+60h+UrlComponents.lpszPassword]
0x18020ff01  mov     [rsp+160h+lpszPassword], rax; lpszPassword
0x18020ff06  mov     r9, [rbp+60h+UrlComponents.lpszUserName]; lpszUserName
0x18020ff0a  movzx   r8d, [rbp+60h+UrlComponents.nPort]; nServerPort
0x18020ff0f  mov     rdx, [rbp+60h+UrlComponents.lpszHostName]; lpszServerName
0x18020ff13  mov     rcx, [r13+30h]; hInternet
0x18020ff17  call    cs:__imp_InternetConnectW
0x18020ff1d  mov     rbx, rax
0x18020ff20  mov     [rsp+160h+var_110], rax
0x18020ff25  test    rax, rax
0x18020ff28  jnz     short loc_18020FF30
0x18020ff2a  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x18020ff30  mov     ecx, 40h ; '@'; Size
0x18020ff35  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18020ff3a  mov     rdi, rax
0x18020ff3d  mov     [rsp+160h+var_118], rax
0x18020ff42  mov     dword ptr [rax], 0
0x18020ff48  mov     [rax+8], r13
0x18020ff4c  lock inc dword ptr [r13+0]
0x18020ff51  mov     [rax+10h], r15d
0x18020ff55  lea     rcx, [rax+18h]
0x18020ff59  lea     rdx, [rbp+60h+lpszUrl]
0x18020ff5d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18020ff62  mov     [rdi+38h], rbx
0x18020ff66  mov     [rsp+160h+var_110], 0
0x18020ff6f  mov     [rsp+160h+var_118], rdi
0x18020ff74  mov     r9, rdi
0x18020ff77  mov     r8, r15
0x18020ff7a  lea     rdx, [rbp+60h+var_78]
0x18020ff7e  lea     rcx, [r13+38h]
0x18020ff82  call    ?Add@HashTableImpl@@QEAA?AViterator@1@_KPEAX@Z; HashTableImpl::Add(unsigned __int64,void *)
0x18020ff87  mov     [rsp+160h+var_118], 0
0x18020ff90  mov     rbx, [rsi]
0x18020ff93  mov     [rsi], rdi
0x18020ff96  mov     rcx, rdi
0x18020ff99  call    ??$AddReference@VNetConnection@@@@YAXPEAVNetConnection@@@Z; AddReference<NetConnection>(NetConnection *)
0x18020ff9e  mov     rcx, rbx; this
0x18020ffa1  call    ??$ReleaseReference@VNetConnection@@@@YAXPEAVNetConnection@@@Z; ReleaseReference<NetConnection>(NetConnection *)
0x18020ffa6  nop
0x18020ffa7  lea     rcx, [rsp+160h+var_118]
0x18020ffac  call    ??1?$ScopedPtr@VNetConnection@@@@QEAA@XZ; ScopedPtr<NetConnection>::~ScopedPtr<NetConnection>(void)
0x18020ffb1  nop
0x18020ffb2  lea     rcx, [rsp+160h+var_110]
0x18020ffb7  call    ??1?$ScopedHandle@UNetHandlePolicy@@PEAX@@QEAA@XZ; ScopedHandle<NetHandlePolicy,void *>::~ScopedHandle<NetHandlePolicy,void *>(void)
0x18020ffbc  nop
0x18020ffbd  mov     rcx, [rsp+160h+lpCriticalSection]; lpCriticalSection
0x18020ffc2  call    cs:__imp_LeaveCriticalSection
0x18020ffc8  nop
0x18020ffc9  lea     rcx, [rbp+60h+lpszUrl]
0x18020ffcd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18020ffd2  mov     rax, rsi
0x18020ffd5  mov     rcx, [rbp+60h+var_48]
0x18020ffd9  xor     rcx, rsp; StackCookie
0x18020ffdc  call    __security_check_cookie
0x18020ffe1  add     rsp, 128h
0x18020ffe8  pop     r15
0x18020ffea  pop     r14
0x18020ffec  pop     r13
0x18020ffee  pop     r12
0x18020fff0  pop     rdi
0x18020fff1  pop     rsi
0x18020fff2  pop     rbx
0x18020fff3  pop     rbp
0x18020fff4  retn
```
