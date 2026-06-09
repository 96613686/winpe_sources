# CLogger::GetLogLevel(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,LogLevel *)

- ea: `0x180034aa4`
- end: `0x180034bec`
- name: `?GetLogLevel@CLogger@@CAJV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAW4LogLevel@@@Z`
- size: `328`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034e4c`
- `0x180035080`

## callees

- `0x180001da0`
- `0x180002e20`
- `0x1800048c0`
- `0x1800059ec`
- `0x180006270`
- `0x18002b28c`
- `0x180034aa4`
- `0x180035e64`
- `0x1800368b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034b98`

## string_xrefs

- `0x180034ad4`: `Software\Microsoft\Windows Search\Gather\Windows\SystemIndex\Protocols\Mapi`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CLogger::GetLogLevel(wchar_t *a1, unsigned __int8 *a2)
{
  unsigned int v4; // r9d
  __int64 v5; // r9
  DWORD LastError; // ebx
  const wchar_t *v8; // [rsp+20h] [rbp-E0h]
  const wchar_t *v9; // [rsp+20h] [rbp-E0h]
  unsigned int v10; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v11; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *v12[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[192]; // [rsp+50h] [rbp-B0h] BYREF

  v12[1] = a1;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    v12,
    "Software\\Microsoft\\Windows Search\\Gather\\Windows\\SystemIndex\\Protocols\\Mapi");
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &v11,
    "LogLevel.");
  ATL::CSimpleStringT<wchar_t,0>::Append(&v11, *(_QWORD *)a1, *(unsigned int *)(*(_QWORD *)a1 - 16LL));
  *(_DWORD *)a2 = 3;
  CRegistry::CRegistry((CRegistry *)v13, HKEY_LOCAL_MACHINE, v12[0], v4, v8);
  if ( !GetLastError() )
  {
    v10 = 4;
    CRegistry::GetValue((CRegistry *)v13, v11, a2, &v10);
  }
  if ( GetLastError() )
  {
    CRegistry::Init((CRegistry *)v13, HKEY_CURRENT_USER, v12[0], v5, v9);
    if ( !GetLastError() )
    {
      v10 = 4;
      CRegistry::GetValue((CRegistry *)v13, v11, a2, &v10);
    }
  }
  LastError = GetLastError();
  CRegistry::~CRegistry((CRegistry *)v13);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v11);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(v12);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(a1);
  return LastError;
}

```

## disassembly

```asm
0x180034aa4  mov     [rsp-8+arg_10], rbx
0x180034aa9  mov     [rsp-8+arg_18], rdi
0x180034aae  push    rbp
0x180034aaf  lea     rbp, [rsp-20h]
0x180034ab4  sub     rsp, 120h
0x180034abb  mov     rax, cs:__security_cookie
0x180034ac2  xor     rax, rsp
0x180034ac5  mov     [rbp+20h+var_10], rax
0x180034ac9  mov     rbx, rdx
0x180034acc  mov     rdi, rcx
0x180034acf  mov     [rsp+120h+var_D8], rcx
0x180034ad4  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows Search\\Ga"...
0x180034adb  lea     rcx, [rsp+120h+var_E0]
0x180034ae0  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(char const *)
0x180034ae5  nop
0x180034ae6  lea     rdx, aLoglevel; "LogLevel."
0x180034aed  lea     rcx, [rsp+120h+var_E8]
0x180034af2  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(char const *)
0x180034af7  nop
0x180034af8  mov     rdx, [rdi]
0x180034afb  mov     r8d, [rdx-10h]
0x180034aff  lea     rcx, [rsp+120h+var_E8]
0x180034b04  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *,int)
0x180034b09  mov     dword ptr [rbx], 3
0x180034b0f  mov     r8, [rsp+120h+var_E0]; wchar_t *
0x180034b14  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180034b1b  lea     rcx, [rsp+120h+var_D0]; this
0x180034b20  call    ??0CRegistry@@QEAA@PEAUHKEY__@@PEB_WK1@Z; CRegistry::CRegistry(HKEY__ *,wchar_t const *,ulong,wchar_t const *)
0x180034b25  nop
0x180034b26  call    cs:__imp_GetLastError
0x180034b2c  test    eax, eax
0x180034b2e  jnz     short loc_180034B4F
0x180034b30  mov     [rsp+120h+var_F0], 4
0x180034b38  lea     r9, [rsp+120h+var_F0]; unsigned int *
0x180034b3d  mov     r8, rbx; unsigned __int8 *
0x180034b40  mov     rdx, [rsp+120h+var_E8]; wchar_t *
0x180034b45  lea     rcx, [rsp+120h+var_D0]; this
0x180034b4a  call    ?GetValue@CRegistry@@QEAAHPEB_WPEAEPEAK@Z; CRegistry::GetValue(wchar_t const *,uchar *,ulong *)
0x180034b4f  call    cs:__imp_GetLastError
0x180034b55  test    eax, eax
0x180034b57  jz      short loc_180034B98
0x180034b59  mov     r8, [rsp+120h+var_E0]; wchar_t *
0x180034b5e  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x180034b65  lea     rcx, [rsp+120h+var_D0]; this
0x180034b6a  call    ?Init@CRegistry@@QEAAJPEAUHKEY__@@PEB_WK1@Z; CRegistry::Init(HKEY__ *,wchar_t const *,ulong,wchar_t const *)
0x180034b6f  call    cs:__imp_GetLastError
0x180034b75  test    eax, eax
0x180034b77  jnz     short loc_180034B98
0x180034b79  mov     [rsp+120h+var_F0], 4
0x180034b81  lea     r9, [rsp+120h+var_F0]; unsigned int *
0x180034b86  mov     r8, rbx; unsigned __int8 *
0x180034b89  mov     rdx, [rsp+120h+var_E8]; wchar_t *
0x180034b8e  lea     rcx, [rsp+120h+var_D0]; this
0x180034b93  call    ?GetValue@CRegistry@@QEAAHPEB_WPEAEPEAK@Z; CRegistry::GetValue(wchar_t const *,uchar *,ulong *)
0x180034b98  call    cs:__imp_GetLastError
0x180034b9e  mov     ebx, eax
0x180034ba0  lea     rcx, [rsp+120h+var_D0]; this
0x180034ba5  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180034baa  nop
0x180034bab  lea     rcx, [rsp+120h+var_E8]
0x180034bb0  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180034bb5  nop
0x180034bb6  lea     rcx, [rsp+120h+var_E0]
0x180034bbb  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180034bc0  nop
0x180034bc1  mov     rcx, rdi
0x180034bc4  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180034bc9  mov     eax, ebx
0x180034bcb  mov     rcx, [rbp+20h+var_10]
0x180034bcf  xor     rcx, rsp; StackCookie
0x180034bd2  call    __security_check_cookie
0x180034bd7  lea     r11, [rsp+120h+var_s0]
0x180034bdf  mov     rbx, [r11+20h]
0x180034be3  mov     rdi, [r11+28h]
0x180034be7  mov     rsp, r11
0x180034bea  pop     rbp
0x180034beb  retn
```
