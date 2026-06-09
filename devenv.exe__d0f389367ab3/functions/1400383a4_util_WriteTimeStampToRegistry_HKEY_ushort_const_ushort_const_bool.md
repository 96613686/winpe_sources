# util_WriteTimeStampToRegistry(HKEY__ *,ushort const *,ushort const *,bool)

- ea: `0x1400383a4`
- end: `0x140038549`
- name: `?util_WriteTimeStampToRegistry@@YAXPEAUHKEY__@@PEBG1_N@Z`
- size: `421`
- prototype: `void __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000ccfc`
- `0x140036a64`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140007740`
- `0x140033ab0`
- `0x1400383a4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14003847f`
- `ADVAPI32!RegCloseKey` at `0x14003851d`
- `ADVAPI32!RegCloseKey` at `0x14003847f`
- `ADVAPI32!RegCloseKey` at `0x14003851d`
- `ADVAPI32!RegOpenKeyExW` at `0x140038429`
- `ADVAPI32!RegOpenKeyExW` at `0x14003846d`
- `ADVAPI32!RegOpenKeyExW` at `0x140038429`
- `ADVAPI32!RegOpenKeyExW` at `0x14003846d`
- `ADVAPI32!RegSetValueExW` at `0x14003850e`
- `ADVAPI32!RegSetValueExW` at `0x14003850e`
- `KERNEL32!SystemTimeToFileTime` at `0x1400383e2`
- `KERNEL32!SystemTimeToFileTime` at `0x1400383e2`
- `KERNEL32!GetSystemTime` at `0x1400383d4`
- `KERNEL32!GetSystemTime` at `0x1400383d4`

## string_xrefs

- `0x1400384b7`: `Cannot find a place to write out the '%s' value!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall util_WriteTimeStampToRegistry(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, char a4)
{
  HKEY v8; // rbx
  HKEY v9; // rsi
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  struct ATL::IAtlStringMgr *Instance; // rax
  HKEY v13; // rdx
  HKEY phkResult; // [rsp+48h] [rbp-28h] BYREF
  struct _FILETIME FileTime; // [rsp+50h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-18h] BYREF

  GetSystemTime(&SystemTime);
  SystemTimeToFileTime(&SystemTime, &FileTime);
  v8 = (HKEY)FileTime;
  v9 = 0;
  if ( a4 )
  {
    phkResult = 0;
    v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 2u, &phkResult);
    if ( !v10 )
      v9 = phkResult;
    if ( (v10 != 0 ? v10 : 0) == 0 )
      goto LABEL_12;
  }
  phkResult = 0;
  v11 = RegOpenKeyExW(hKey, lpSubKey, 0, 2u, &phkResult);
  if ( v11 )
    goto LABEL_9;
  if ( v9 )
    v11 = RegCloseKey(v9);
  v9 = phkResult;
  if ( v11 )
  {
LABEL_9:
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    phkResult = (HKEY)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                     + 24);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &phkResult,
      L"Cannot find a place to write out the '%s' value!",
      lpValueName);
    v13 = phkResult - 6;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)phkResult - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
    }
  }
  else
  {
LABEL_12:
    phkResult = v8;
    RegSetValueExW(v9, lpValueName, 0, 0xBu, (const BYTE *)&phkResult, 8u);
  }
  if ( v9 )
    RegCloseKey(v9);
}

```

## disassembly

```asm
0x1400383a4  push    rbp
0x1400383a6  push    rbx
0x1400383a7  push    rsi
0x1400383a8  push    rdi
0x1400383a9  push    r12
0x1400383ab  push    r14
0x1400383ad  push    r15
0x1400383af  mov     rbp, rsp
0x1400383b2  sub     rsp, 70h
0x1400383b6  mov     rax, cs:__security_cookie
0x1400383bd  xor     rax, rsp
0x1400383c0  mov     [rbp+var_8], rax
0x1400383c4  mov     dil, r9b
0x1400383c7  mov     r15, r8
0x1400383ca  mov     r14, rdx
0x1400383cd  mov     r12, rcx
0x1400383d0  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1400383d4  call    cs:__imp_GetSystemTime
0x1400383da  lea     rdx, [rbp+FileTime]; lpFileTime
0x1400383de  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1400383e2  call    cs:__imp_SystemTimeToFileTime
0x1400383e8  mov     rbx, qword ptr [rbp+FileTime.dwLowDateTime]
0x1400383ec  xorps   xmm0, xmm0
0x1400383ef  xor     eax, eax
0x1400383f1  movups  [rbp+var_40], xmm0
0x1400383f5  mov     [rbp+var_30], rax
0x1400383f9  xor     esi, esi
0x1400383fb  mov     qword ptr [rbp+var_40], rsi
0x1400383ff  and     dword ptr [rbp+var_40+8], eax
0x140038402  and     [rbp+var_30], rax
0x140038406  test    dil, dil
0x140038409  jz      short loc_140038450
0x14003840b  and     [rbp+var_28], rsi
0x14003840f  lea     rax, [rbp+var_28]
0x140038413  mov     [rsp+70h+phkResult], rax; phkResult
0x140038418  lea     r9d, [rsi+2]; samDesired
0x14003841c  xor     r8d, r8d; ulOptions
0x14003841f  mov     rdx, r14; lpSubKey
0x140038422  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140038429  call    cs:__imp_RegOpenKeyExW
0x14003842f  test    eax, eax
0x140038431  jnz     short loc_14003843E
0x140038433  mov     rsi, [rbp+var_28]
0x140038437  mov     qword ptr [rbp+var_40], rsi
0x14003843b  and     dword ptr [rbp+var_40+8], eax
0x14003843e  mov     r8d, eax
0x140038441  neg     r8d
0x140038444  sbb     r10d, r10d
0x140038447  test    eax, r10d
0x14003844a  jz      loc_1400384EA
0x140038450  and     [rbp+var_28], 0
0x140038455  lea     rax, [rbp+var_28]
0x140038459  mov     [rsp+70h+phkResult], rax; phkResult
0x14003845e  mov     r9d, 2; samDesired
0x140038464  xor     r8d, r8d; ulOptions
0x140038467  mov     rdx, r14; lpSubKey
0x14003846a  mov     rcx, r12; hKey
0x14003846d  call    cs:__imp_RegOpenKeyExW
0x140038473  test    eax, eax
0x140038475  jnz     short loc_140038495
0x140038477  test    rsi, rsi
0x14003847a  jz      short loc_140038485
0x14003847c  mov     rcx, rsi; hKey
0x14003847f  call    cs:__imp_RegCloseKey
0x140038485  mov     rsi, [rbp+var_28]
0x140038489  mov     qword ptr [rbp+var_40], rsi
0x14003848d  and     dword ptr [rbp+var_40+8], 0
0x140038491  test    eax, eax
0x140038493  jz      short loc_1400384EA
0x140038495  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14003849a  mov     rcx, rax
0x14003849d  test    rax, rax
0x1400384a0  jz      loc_14003853E
0x1400384a6  mov     rax, [rax]
0x1400384a9  call    qword ptr [rax+18h]
0x1400384ac  add     rax, 18h
0x1400384b0  mov     [rbp+var_28], rax
0x1400384b4  mov     r8, r15
0x1400384b7  lea     rdx, aCannotFindAPla_0; "Cannot find a place to write out the '%"...
0x1400384be  lea     rcx, [rbp+var_28]
0x1400384c2  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1400384c7  mov     rdx, [rbp+var_28]
0x1400384cb  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400384cf  or      eax, 0FFFFFFFFh
0x1400384d2  lock xadd [rdx+10h], eax
0x1400384d7  sub     eax, 1
0x1400384da  jg      short loc_140038515
0x1400384dc  lfence
0x1400384df  mov     rcx, [rdx]
0x1400384e2  mov     rax, [rcx]
0x1400384e5  call    qword ptr [rax+8]
0x1400384e8  jmp     short loc_140038515
0x1400384ea  mov     [rbp+var_28], rbx
0x1400384ee  mov     [rsp+70h+cbData], 8; cbData
0x1400384f6  lea     rax, [rbp+var_28]
0x1400384fa  mov     [rsp+70h+phkResult], rax; lpData
0x1400384ff  mov     r9d, 0Bh; dwType
0x140038505  xor     r8d, r8d; Reserved
0x140038508  mov     rdx, r15; lpValueName
0x14003850b  mov     rcx, rsi; hKey
0x14003850e  call    cs:__imp_RegSetValueExW
0x140038514  nop
0x140038515  test    rsi, rsi
0x140038518  jz      short loc_140038523
0x14003851a  mov     rcx, rsi; hKey
0x14003851d  call    cs:__imp_RegCloseKey
0x140038523  mov     rcx, [rbp+var_8]
0x140038527  xor     rcx, rsp; StackCookie
0x14003852a  call    __security_check_cookie
0x14003852f  add     rsp, 70h
0x140038533  pop     r15
0x140038535  pop     r14
0x140038537  pop     r12
0x140038539  pop     rdi
0x14003853a  pop     rsi
0x14003853b  pop     rbx
0x14003853c  pop     rbp
0x14003853d  retn
0x14003853e  mov     ecx, 80004005h; int
0x140038543  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
