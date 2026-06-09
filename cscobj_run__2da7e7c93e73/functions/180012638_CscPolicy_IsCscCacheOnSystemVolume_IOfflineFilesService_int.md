# CscPolicy_IsCscCacheOnSystemVolume(IOfflineFilesService *,int *)

- ea: `0x180012638`
- end: `0x1800128db`
- name: `?CscPolicy_IsCscCacheOnSystemVolume@@YAJPEAUIOfflineFilesService@@PEAH@Z`
- size: `675`
- prototype: `__int64 __fastcall(struct IOfflineFilesService *, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180011fd0`

## callees

- `0x1800046c0`
- `0x1800083f0`
- `0x180008550`
- `0x180009864`
- `0x18000b7c0`
- `0x18000f5cc`
- `0x180011e38`
- `0x180012638`
- `0x180014068`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001287e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001287e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001269c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001269c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001280f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001280f`

## pseudocode

```c
__int64 __fastcall CscPolicy_IsCscCacheOnSystemVolume(struct IOfflineFilesService *a1, int *a2)
{
  __int64 v3; // rax
  int Error; // ebx
  UstVarLib *v5; // rcx
  const WCHAR *ConstBuffer; // rax
  PCNZWCH lpString2; // rdx
  int v8; // eax
  const wchar_t *v9; // r9
  LPVOID pv[2]; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v12[260]; // [rsp+40h] [rbp-C0h] BYREF
  int v13; // [rsp+248h] [rbp+148h]
  _WORD *v14; // [rsp+250h] [rbp+150h]
  _WORD *v15; // [rsp+258h] [rbp+158h]
  _WORD *v16; // [rsp+260h] [rbp+160h]
  __int64 v17; // [rsp+268h] [rbp+168h]
  __int64 v18; // [rsp+270h] [rbp+170h]
  _WORD v19[260]; // [rsp+280h] [rbp+180h] BYREF
  int v20; // [rsp+488h] [rbp+388h]
  _WORD *v21; // [rsp+490h] [rbp+390h]
  _WORD *v22; // [rsp+498h] [rbp+398h]
  _WORD *v23; // [rsp+4A0h] [rbp+3A0h]
  __int64 v24; // [rsp+4A8h] [rbp+3A8h]
  __int64 v25; // [rsp+4B0h] [rbp+3B0h]
  WCHAR Buffer[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  *a2 = 0;
  v3 = *(_QWORD *)a1;
  pv[0] = 0;
  Error = (*(__int64 (__fastcall **)(struct IOfflineFilesService *, LPVOID *))(v3 + 136))(a1, pv);
  if ( Error < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        38,
        WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
        (unsigned int)Error);
  }
  else
  {
    if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) )
    {
      v22 = v19;
      v20 = 34078720;
      v23 = v19;
      v24 = 520;
      v21 = v19;
      v19[0] = 0;
      v25 = 520;
      Error = CPath::Copy((CPath *)v19, (const unsigned __int16 *)pv[0]);
      if ( Error >= 0 )
      {
        v17 = 520;
        v15 = v12;
        v18 = 520;
        v16 = v12;
        v13 = 34078720;
        v14 = v12;
        v12[0] = 0;
        Error = CPath::Copy((CPath *)v12, Buffer);
        if ( Error >= 0 )
        {
          Error = CPath::StripToRoot((CPath *)v19);
          if ( Error >= 0 )
          {
            Error = CPath::StripToRoot((CPath *)v12);
            if ( Error >= 0 )
            {
              CPath::_GetConstBuffer((CPath *)v12);
              ConstBuffer = CPath::_GetConstBuffer((CPath *)v19);
              v8 = CompareStringW(0x7Fu, 1u, ConstBuffer, -1, lpString2, -1);
              *a2 = v8 == 2;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(char *)(WPP_GLOBAL_Control + 28LL) < 0 )
              {
                v9 = L"is";
                if ( v8 != 2 )
                  v9 = L"is not";
                WPP_SF_S(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  37,
                  WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
                  v9);
              }
            }
          }
        }
        CPath::~CPath((CPath *)v12);
      }
      CPath::~CPath((CPath *)v19);
    }
    else
    {
      Error = UstVarLib::ResultFromLastError(v5);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          36,
          WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
          (unsigned int)Error);
    }
    CoTaskMemFree(pv[0]);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180012638  mov     [rsp-8+arg_10], rbx
0x18001263d  push    rbp
0x18001263e  push    rsi
0x18001263f  push    rdi
0x180012640  lea     rbp, [rsp-5E0h]
0x180012648  sub     rsp, 6E0h
0x18001264f  mov     rax, cs:__security_cookie
0x180012656  xor     rax, rsp
0x180012659  mov     [rbp+5F0h+var_20], rax
0x180012660  mov     dword ptr [rdx], 0
0x180012666  mov     rdi, rdx
0x180012669  mov     rax, [rcx]
0x18001266c  lea     rdx, [rsp+6F0h+pv]
0x180012671  mov     [rsp+6F0h+pv], 0
0x18001267a  mov     rax, [rax+88h]
0x180012681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012686  mov     ebx, eax
0x180012688  test    eax, eax
0x18001268a  js      loc_180012886
0x180012690  mov     edx, 104h; uSize
0x180012695  lea     rcx, [rbp+5F0h+Buffer]; lpBuffer
0x18001269c  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800126a2  test    eax, eax
0x1800126a4  jnz     short loc_1800126EB
0x1800126a6  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x1800126ab  mov     ebx, eax
0x1800126ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126b4  lea     rax, WPP_GLOBAL_Control
0x1800126bb  cmp     rcx, rax
0x1800126be  jz      loc_180012879
0x1800126c4  test    byte ptr [rcx+1Ch], 2
0x1800126c8  jz      loc_180012879
0x1800126ce  mov     rcx, [rcx+10h]
0x1800126d2  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x1800126d9  mov     edx, 24h ; '$'
0x1800126de  mov     r9d, ebx
0x1800126e1  call    WPP_SF_d
0x1800126e6  jmp     loc_180012879
0x1800126eb  mov     rdx, [rsp+6F0h+pv]; unsigned __int16 *
0x1800126f0  lea     rax, [rbp+5F0h+var_470]
0x1800126f7  mov     [rbp+5F0h+var_258], rax
0x1800126fe  lea     rcx, [rbp+5F0h+var_470]; this
0x180012705  lea     rax, [rbp+5F0h+var_470]
0x18001270c  mov     [rbp+5F0h+var_268], 2080000h
0x180012716  mov     [rbp+5F0h+var_250], rax
0x18001271d  mov     esi, 208h
0x180012722  lea     rax, [rbp+5F0h+var_470]
0x180012729  mov     [rbp+5F0h+var_248], rsi
0x180012730  mov     [rbp+5F0h+var_260], rax
0x180012737  xor     eax, eax
0x180012739  mov     [rbp+5F0h+var_470], ax
0x180012740  mov     [rbp+5F0h+var_240], rsi
0x180012747  call    ?Copy@CPath@@QEAAJPEBG@Z; CPath::Copy(ushort const *)
0x18001274c  mov     ebx, eax
0x18001274e  test    eax, eax
0x180012750  js      loc_18001286D
0x180012756  lea     rax, [rsp+6F0h+var_6B0]
0x18001275b  mov     [rbp+5F0h+var_488], rsi
0x180012762  mov     [rbp+5F0h+var_498], rax
0x180012769  lea     rdx, [rbp+5F0h+Buffer]; unsigned __int16 *
0x180012770  lea     rax, [rsp+6F0h+var_6B0]
0x180012775  mov     [rbp+5F0h+var_480], rsi
0x18001277c  mov     [rbp+5F0h+var_490], rax
0x180012783  lea     rcx, [rsp+6F0h+var_6B0]; this
0x180012788  lea     rax, [rsp+6F0h+var_6B0]
0x18001278d  mov     [rbp+5F0h+var_4A8], 2080000h
0x180012797  mov     [rbp+5F0h+var_4A0], rax
0x18001279e  xor     eax, eax
0x1800127a0  mov     [rsp+6F0h+var_6B0], ax
0x1800127a5  call    ?Copy@CPath@@QEAAJPEBG@Z; CPath::Copy(ushort const *)
0x1800127aa  mov     ebx, eax
0x1800127ac  test    eax, eax
0x1800127ae  js      loc_180012863
0x1800127b4  lea     rcx, [rbp+5F0h+var_470]; this
0x1800127bb  call    ?StripToRoot@CPath@@QEAAJXZ; CPath::StripToRoot(void)
0x1800127c0  mov     ebx, eax
0x1800127c2  test    eax, eax
0x1800127c4  js      loc_180012863
0x1800127ca  lea     rcx, [rsp+6F0h+var_6B0]; this
0x1800127cf  call    ?StripToRoot@CPath@@QEAAJXZ; CPath::StripToRoot(void)
0x1800127d4  mov     ebx, eax
0x1800127d6  test    eax, eax
0x1800127d8  js      loc_180012863
0x1800127de  lea     rcx, [rsp+6F0h+var_6B0]; this
0x1800127e3  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x1800127e8  lea     rcx, [rbp+5F0h+var_470]; this
0x1800127ef  mov     rdx, rax
0x1800127f2  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x1800127f7  or      r9d, 0FFFFFFFFh; cchCount1
0x1800127fb  mov     r8, rax; lpString1
0x1800127fe  mov     [rsp+6F0h+cchCount2], r9d; cchCount2
0x180012803  mov     [rsp+6F0h+lpString2], rdx; lpString2
0x180012808  lea     edx, [r9+2]; dwCmpFlags
0x18001280c  lea     ecx, [rdx+7Eh]; Locale
0x18001280f  call    cs:__imp_CompareStringW
0x180012815  lea     edx, [rax-2]
0x180012818  xor     eax, eax
0x18001281a  test    edx, edx
0x18001281c  setz    al
0x18001281f  mov     [rdi], eax
0x180012821  mov     rcx, cs:WPP_GLOBAL_Control
0x180012828  lea     rax, WPP_GLOBAL_Control
0x18001282f  cmp     rcx, rax
0x180012832  jz      short loc_180012863
0x180012834  test    byte ptr [rcx+1Ch], 80h
0x180012838  jz      short loc_180012863
0x18001283a  mov     rcx, [rcx+10h]
0x18001283e  lea     rax, aIsNot; "is not"
0x180012845  test    edx, edx
0x180012847  lea     r9, aIs; "is"
0x18001284e  mov     edx, 25h ; '%'
0x180012853  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x18001285a  cmovnz  r9, rax
0x18001285e  call    WPP_SF_S
0x180012863  lea     rcx, [rsp+6F0h+var_6B0]; this
0x180012868  call    ??1CPath@@QEAA@XZ; CPath::~CPath(void)
0x18001286d  lea     rcx, [rbp+5F0h+var_470]; this
0x180012874  call    ??1CPath@@QEAA@XZ; CPath::~CPath(void)
0x180012879  mov     rcx, [rsp+6F0h+pv]; pv
0x18001287e  call    cs:__imp_CoTaskMemFree
0x180012884  jmp     short loc_1800128B7
0x180012886  mov     rcx, cs:WPP_GLOBAL_Control
0x18001288d  lea     rax, WPP_GLOBAL_Control
0x180012894  cmp     rcx, rax
0x180012897  jz      short loc_1800128B7
0x180012899  test    byte ptr [rcx+1Ch], 2
0x18001289d  jz      short loc_1800128B7
0x18001289f  mov     rcx, [rcx+10h]
0x1800128a3  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x1800128aa  mov     edx, 26h ; '&'
0x1800128af  mov     r9d, ebx
0x1800128b2  call    WPP_SF_d
0x1800128b7  mov     eax, ebx
0x1800128b9  mov     rcx, [rbp+5F0h+var_20]
0x1800128c0  xor     rcx, rsp; StackCookie
0x1800128c3  call    __security_check_cookie
0x1800128c8  mov     rbx, [rsp+6F0h+arg_10]
0x1800128d0  add     rsp, 6E0h
0x1800128d7  pop     rdi
0x1800128d8  pop     rsi
0x1800128d9  pop     rbp
0x1800128da  retn
```
