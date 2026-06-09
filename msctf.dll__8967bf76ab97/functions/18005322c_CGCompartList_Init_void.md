# CGCompartList::Init(void)

- ea: `0x18005322c`
- end: `0x1800535b1`
- name: `?Init@CGCompartList@@QEAAXXZ`
- size: `901`
- prototype: `void __fastcall(CGCompartList *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180052ff8`

## callees

- `0x1800139a4`
- `0x1800250fc`
- `0x180040694`
- `0x18005322c`
- `0x1800539d8`
- `0x18005d0f0`
- `0x180068f74`
- `0x1800a18d4`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180053485`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005350e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180053485`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005350e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800532b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053342`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800532b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053342`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800532dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053368`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005357b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053589`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800532dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053368`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005357b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053589`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18005330f`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18005330f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800534aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800534aa`

## string_xrefs

- `0x1800532b0`: `SOFTWARE\Microsoft\CTF\Compartment`
- `0x180053338`: `SOFTWARE\Microsoft\CTF\Compartment`
- `0x180053502`: `GlobalCompartment`

## pseudocode

```c
void __fastcall CGCompartList::Init(CGCompartList *this)
{
  HKEY v2; // rsi
  HKEY v3; // r14
  __int64 v4; // rbx
  LSTATUS v5; // ebx
  unsigned int v6; // r12d
  BYTE *v7; // rbx
  int v8; // eax
  int v9; // eax
  __int64 v10; // rcx
  BYTE Data[8]; // [rsp+30h] [rbp-2F8h] BYREF
  void **v12; // [rsp+38h] [rbp-2F0h] BYREF
  HKEY v13; // [rsp+40h] [rbp-2E8h]
  void **v14; // [rsp+48h] [rbp-2E0h] BYREF
  HKEY v15; // [rsp+50h] [rbp-2D8h]
  DWORD cbData; // [rsp+58h] [rbp-2D0h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp-2CCh] BYREF
  DWORD lpcbData; // [rsp+60h] [rbp-2C8h] BYREF
  DWORD v19; // [rsp+64h] [rbp-2C4h] BYREF
  unsigned int v20; // [rsp+68h] [rbp-2C0h]
  HKEY v21; // [rsp+70h] [rbp-2B8h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-2B0h] BYREF
  HKEY v23; // [rsp+80h] [rbp-2A8h] BYREF
  void **v24; // [rsp+88h] [rbp-2A0h] BYREF
  HKEY v25; // [rsp+90h] [rbp-298h]
  HKEY hKey[2]; // [rsp+98h] [rbp-290h] BYREF
  __int64 v27; // [rsp+A8h] [rbp-280h]
  HKEY v28; // [rsp+B8h] [rbp-270h]
  __int64 v29; // [rsp+C0h] [rbp-268h]
  unsigned __int16 v30[264]; // [rsp+D0h] [rbp-258h] BYREF

  if ( !*(_BYTE *)this )
  {
    *(_BYTE *)this = 1;
    v24 = &CPreloadRegKey::`vftable';
    v2 = 0;
    v25 = 0;
    v28 = 0;
    v29 = -2147483646;
    phkResult = 0;
    hKey[0] = 0;
    v3 = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\CTF\\Compartment", 0, 0x20019u, &phkResult) )
      v3 = phkResult;
    v28 = v3;
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    v4 = -2147483647;
    v27 = -2147483647;
    v23 = 0;
    v21 = 0;
    if ( !RegOpenCurrentUser(0x20019u, &v21) )
      v4 = (__int64)v21;
    v27 = v4;
    v5 = RegOpenKeyExW((HKEY)v4, L"SOFTWARE\\Microsoft\\CTF\\Compartment", 0, 0x20019u, &v23);
    if ( !v5 )
    {
      v2 = v23;
      v25 = v23;
    }
    if ( v21 )
      RegCloseKey(v21);
    if ( !v5 )
    {
      v6 = 0;
      v20 = 0;
      while ( !(unsigned int)CMyRegKey::EnumKey((CMyRegKey *)&v24, v6, v30, 0x104u) )
      {
        v14 = &CPreloadRegKey::`vftable';
        v15 = 0;
        v12 = &CPreloadRegKey::`vftable';
        v13 = 0;
        *(_OWORD *)hKey = 0;
        if ( (unsigned int)StringToCLSID(v30, (struct _GUID *)hKey) )
        {
          if ( !CMyRegKey::Open((CMyRegKey *)&v14, v2, v30, 0x20019u) )
          {
            *(_DWORD *)Data = 0;
            if ( v3 )
            {
              if ( !CMyRegKey::Open((CMyRegKey *)&v12, v3, v30, 0x20019u) )
              {
                Type = 0;
                cbData = 4;
                if ( RegQueryValueExW(v13, L"NonInit", 0, &Type, Data, &cbData) )
                  *(_DWORD *)Data = 0;
              }
            }
            if ( !*(_DWORD *)Data )
            {
              v7 = (BYTE *)LocalAlloc(0x40u, 0x1Cu);
              if ( !v7 )
                goto LABEL_24;
              lpcbData = 28;
              v19 = 3;
              if ( RegQueryValueExW(v15, L"GlobalCompartment", 0, &v19, v7, &lpcbData)
                || !CVoidPtrArray::Append((CGCompartList *)((char *)this + 8)) )
              {
                cicMemFree(v7);
LABEL_24:
                v12 = &CPreloadRegKey::`vftable';
                CInputDllRegKey::Close((CInputDllRegKey *)&v12);
                v14 = &CPreloadRegKey::`vftable';
                CInputDllRegKey::Close((CInputDllRegKey *)&v14);
                break;
              }
              v8 = *((_DWORD *)this + 6);
              *((_DWORD *)v7 + 4) = v8;
              v9 = v8 - 1;
              if ( v9 >= 0 && v9 < *((_DWORD *)this + 6) )
              {
                v10 = *((_QWORD *)this + 2);
                if ( v10 )
                  *(_QWORD *)(v10 + 8LL * v9) = v7;
              }
            }
          }
          v20 = ++v6;
        }
        v12 = &CPreloadRegKey::`vftable';
        CInputDllRegKey::Close((CInputDllRegKey *)&v12);
        v14 = &CPreloadRegKey::`vftable';
        CInputDllRegKey::Close((CInputDllRegKey *)&v14);
      }
    }
    if ( v3 )
      RegCloseKey(v3);
    if ( v2 )
      RegCloseKey(v2);
  }
}

```

## disassembly

```asm
0x18005322c  mov     r11, rsp
0x18005322f  push    rbx
0x180053230  push    rsi
0x180053231  push    r12
0x180053233  push    r13
0x180053235  push    r14
0x180053237  push    r15
0x180053239  sub     rsp, 2F8h
0x180053240  mov     rax, cs:__security_cookie
0x180053247  xor     rax, rsp
0x18005324a  mov     [rsp+328h+var_48], rax
0x180053252  mov     r15, rcx
0x180053255  cmp     byte ptr [rcx], 0
0x180053258  jnz     loc_18005358F
0x18005325e  mov     byte ptr [rcx], 1
0x180053261  lea     r13, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x180053268  mov     [r11-2A0h], r13
0x18005326f  xor     esi, esi
0x180053271  mov     [r11-298h], rsi
0x180053278  mov     [r11-270h], rsi
0x18005327f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180053286  mov     [rsp+328h+var_268], rcx
0x18005328e  mov     [rsp+328h+var_2B0], rsi
0x180053293  mov     [r11-290h], rsi
0x18005329a  lea     rax, [rsp+328h+var_2B0]
0x18005329f  mov     [rsp+328h+phkResult], rax; phkResult
0x1800532a4  mov     r12d, 20019h
0x1800532aa  mov     r9d, r12d; samDesired
0x1800532ad  xor     r8d, r8d; ulOptions
0x1800532b0  lea     rdx, ?c_szCompartKey@@3QBGB; "SOFTWARE\\Microsoft\\CTF\\Compartment"
0x1800532b7  call    cs:__imp_RegOpenKeyExW
0x1800532bd  xor     r14d, r14d
0x1800532c0  test    eax, eax
0x1800532c2  cmovz   r14, [rsp+328h+var_2B0]
0x1800532c8  mov     [rsp+328h+var_270], r14
0x1800532d0  mov     rcx, [rsp+328h+hKey]; hKey
0x1800532d8  test    rcx, rcx
0x1800532db  jz      short loc_1800532E3
0x1800532dd  call    cs:__imp_RegCloseKey
0x1800532e3  mov     rbx, 0FFFFFFFF80000001h
0x1800532ea  mov     [rsp+328h+var_280], rbx
0x1800532f2  mov     [rsp+328h+var_2A8], 0
0x1800532fe  mov     [rsp+328h+var_2B8], 0
0x180053307  lea     rdx, [rsp+328h+var_2B8]; phkResult
0x18005330c  mov     ecx, r12d; samDesired
0x18005330f  call    cs:__imp_RegOpenCurrentUser
0x180053315  test    eax, eax
0x180053317  cmovz   rbx, [rsp+328h+var_2B8]
0x18005331d  mov     [rsp+328h+var_280], rbx
0x180053325  lea     rax, [rsp+328h+var_2A8]
0x18005332d  mov     [rsp+328h+phkResult], rax; phkResult
0x180053332  mov     r9d, r12d; samDesired
0x180053335  xor     r8d, r8d; ulOptions
0x180053338  lea     rdx, ?c_szCompartKey@@3QBGB; "SOFTWARE\\Microsoft\\CTF\\Compartment"
0x18005333f  mov     rcx, rbx; hKey
0x180053342  call    cs:__imp_RegOpenKeyExW
0x180053348  mov     ebx, eax
0x18005334a  test    eax, eax
0x18005334c  jnz     short loc_18005335E
0x18005334e  mov     rsi, [rsp+328h+var_2A8]
0x180053356  mov     [rsp+328h+var_298], rsi
0x18005335e  mov     rcx, [rsp+328h+var_2B8]; hKey
0x180053363  test    rcx, rcx
0x180053366  jz      short loc_18005336E
0x180053368  call    cs:__imp_RegCloseKey
0x18005336e  test    ebx, ebx
0x180053370  jnz     loc_180053561
0x180053376  xor     r12d, r12d
0x180053379  mov     [rsp+328h+var_2C0], r12d
0x18005337e  mov     r9d, 104h; unsigned int
0x180053384  lea     r8, [rsp+328h+var_258]; unsigned __int16 *
0x18005338c  mov     edx, r12d; unsigned int
0x18005338f  lea     rcx, [rsp+328h+var_2A0]; this
0x180053397  call    ?EnumKey@CMyRegKey@@QEAAJKPEAGK@Z; CMyRegKey::EnumKey(ulong,ushort *,ulong)
0x18005339c  test    eax, eax
0x18005339e  jnz     loc_180053561
0x1800533a4  mov     [rsp+328h+var_2E0], r13
0x1800533a9  mov     [rsp+328h+var_2D8], 0
0x1800533b2  mov     [rsp+328h+var_2F0], r13
0x1800533b7  mov     [rsp+328h+var_2E8], 0
0x1800533c0  xorps   xmm0, xmm0
0x1800533c3  movups  xmmword ptr [rsp+328h+hKey], xmm0
0x1800533cb  lea     rdx, [rsp+328h+hKey]; struct _GUID *
0x1800533d3  lea     rcx, [rsp+328h+var_258]; unsigned __int16 *
0x1800533db  call    ?StringToCLSID@@YAHPEBGPEAU_GUID@@@Z; StringToCLSID(ushort const *,_GUID *)
0x1800533e0  test    eax, eax
0x1800533e2  jnz     short loc_180053407
0x1800533e4  mov     [rsp+328h+var_2F0], r13
0x1800533e9  lea     rcx, [rsp+328h+var_2F0]; this
0x1800533ee  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800533f3  mov     [rsp+328h+var_2E0], r13
0x1800533f8  lea     rcx, [rsp+328h+var_2E0]; this
0x1800533fd  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180053402  jmp     loc_18005337E
0x180053407  mov     ebx, 20019h
0x18005340c  mov     r9d, ebx; unsigned int
0x18005340f  lea     r8, [rsp+328h+var_258]; unsigned __int16 *
0x180053417  mov     rdx, rsi; HKEY
0x18005341a  lea     rcx, [rsp+328h+var_2E0]; this
0x18005341f  call    ?Open@CMyRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CMyRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180053424  test    eax, eax
0x180053426  jnz     loc_180053547
0x18005342c  mov     dword ptr [rsp+328h+Data], eax
0x180053430  test    r14, r14
0x180053433  jz      short loc_180053497
0x180053435  mov     r9d, ebx; unsigned int
0x180053438  lea     r8, [rsp+328h+var_258]; unsigned __int16 *
0x180053440  mov     rdx, r14; HKEY
0x180053443  lea     rcx, [rsp+328h+var_2F0]; this
0x180053448  call    ?Open@CMyRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CMyRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18005344d  test    eax, eax
0x18005344f  jnz     short loc_180053497
0x180053451  mov     [rsp+328h+Type], eax
0x180053455  mov     [rsp+328h+cbData], 4
0x18005345d  lea     rax, [rsp+328h+cbData]
0x180053462  mov     [rsp+328h+lpcbData], rax; lpcbData
0x180053467  lea     rax, [rsp+328h+Data]
0x18005346c  mov     [rsp+328h+phkResult], rax; lpData
0x180053471  lea     r9, [rsp+328h+Type]; lpType
0x180053476  xor     r8d, r8d; lpReserved
0x180053479  lea     rdx, ?c_szNonInit@@3QBGB; "NonInit"
0x180053480  mov     rcx, [rsp+328h+var_2E8]; hKey
0x180053485  call    cs:__imp_RegQueryValueExW
0x18005348b  test    eax, eax
0x18005348d  jz      short loc_180053497
0x18005348f  mov     dword ptr [rsp+328h+Data], 0
0x180053497  cmp     dword ptr [rsp+328h+Data], 0
0x18005349c  jnz     loc_180053547
0x1800534a2  mov     edx, 1Ch; uBytes
0x1800534a7  lea     ecx, [rdx+24h]; uFlags
0x1800534aa  call    cs:__imp_LocalAlloc
0x1800534b0  mov     rbx, rax
0x1800534b3  test    rax, rax
0x1800534b6  jnz     short loc_1800534DB
0x1800534b8  mov     [rsp+328h+var_2F0], r13
0x1800534bd  lea     rcx, [rsp+328h+var_2F0]; this
0x1800534c2  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800534c7  mov     [rsp+328h+var_2E0], r13
0x1800534cc  lea     rcx, [rsp+328h+var_2E0]; this
0x1800534d1  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800534d6  jmp     loc_180053561
0x1800534db  mov     [rsp+328h+var_2C8], 1Ch
0x1800534e3  mov     [rsp+328h+var_2C4], 3
0x1800534eb  lea     rax, [rsp+328h+var_2C8]
0x1800534f0  mov     [rsp+328h+lpcbData], rax; lpcbData
0x1800534f5  mov     [rsp+328h+phkResult], rbx; lpData
0x1800534fa  lea     r9, [rsp+328h+var_2C4]; lpType
0x1800534ff  xor     r8d, r8d; lpReserved
0x180053502  lea     rdx, ?c_szGlobalCompartment@@3QBGB; "GlobalCompartment"
0x180053509  mov     rcx, [rsp+328h+var_2D8]; hKey
0x18005350e  call    cs:__imp_RegQueryValueExW
0x180053514  test    eax, eax
0x180053516  jnz     short loc_180053554
0x180053518  lea     rcx, [r15+8]; this
0x18005351c  call    ?Append@CVoidPtrArray@@QEAAPEAPEAXH@Z; CVoidPtrArray::Append(int)
0x180053521  test    rax, rax
0x180053524  jz      short loc_180053554
0x180053526  mov     eax, [r15+18h]
0x18005352a  mov     [rbx+10h], eax
0x18005352d  sub     eax, 1
0x180053530  js      short loc_180053547
0x180053532  cmp     eax, [r15+18h]
0x180053536  jge     short loc_180053547
0x180053538  mov     rcx, [r15+10h]
0x18005353c  test    rcx, rcx
0x18005353f  jz      short loc_180053547
0x180053541  cdqe
0x180053543  mov     [rcx+rax*8], rbx
0x180053547  inc     r12d
0x18005354a  mov     [rsp+328h+var_2C0], r12d
0x18005354f  jmp     loc_1800533E4
0x180053554  mov     rcx, rbx
0x180053557  call    cicMemFree
0x18005355c  jmp     loc_1800534B8
0x180053561  jmp     short loc_180053573
0x180053563  mov     rsi, [rsp+328h+var_298]
0x18005356b  mov     r14, [rsp+328h+var_270]
0x180053573  test    r14, r14
0x180053576  jz      short loc_180053581
0x180053578  mov     rcx, r14; hKey
0x18005357b  call    cs:__imp_RegCloseKey
0x180053581  test    rsi, rsi
0x180053584  jz      short loc_18005358F
0x180053586  mov     rcx, rsi; hKey
0x180053589  call    cs:__imp_RegCloseKey
0x18005358f  mov     rcx, [rsp+328h+var_48]
0x180053597  xor     rcx, rsp; StackCookie
0x18005359a  call    __security_check_cookie
0x18005359f  add     rsp, 2F8h
0x1800535a6  pop     r15
0x1800535a8  pop     r14
0x1800535aa  pop     r13
0x1800535ac  pop     r12
0x1800535ae  pop     rsi
0x1800535af  pop     rbx
0x1800535b0  retn
0x180107a69  push    rbp
0x180107a6b  sub     rsp, 30h
0x180107a6f  mov     rbp, rdx
0x180107a72  mov     dl, cs:?g_fEnableFailFast@@3_NA; bool
0x180107a78  call    ?CicExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@_N@Z; CicExceptionFilter(_EXCEPTION_POINTERS *,bool)
0x180107a7d  nop
0x180107a7e  add     rsp, 30h
0x180107a82  pop     rbp
0x180107a83  retn
```
