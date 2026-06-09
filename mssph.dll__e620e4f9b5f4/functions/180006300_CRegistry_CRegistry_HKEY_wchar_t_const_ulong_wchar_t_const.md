# CRegistry::CRegistry(HKEY__ *,wchar_t const *,ulong,wchar_t const *)

- ea: `0x180006300`
- end: `0x180006425`
- name: `??0CRegistry@@QEAA@PEAUHKEY__@@PEB_WK1@Z`
- size: `293`
- prototype: `CRegistry *__fastcall(CRegistry *this, HKEY, wchar_t *, REGSAM)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c5a0`

## callees

- `0x180006300`
- `0x180006430`
- `0x18000fcd0`
- `0x18001ff2c`
- `0x180020064`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006377`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800063bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006377`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800063bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800063ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800063ad`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800063eb`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800063eb`

## pseudocode

```c
CRegistry *__fastcall CRegistry::CRegistry(CRegistry *this, HKEY a2, wchar_t *a3, REGSAM a4)
{
  _WORD *v8; // rcx
  bool v9; // al
  wchar_t *v10; // rdx
  LSTATUS v11; // eax
  const wchar_t *v13; // rcx
  unsigned int v14; // r9d
  struct CSearchRegistryRedirectHelper *v15[4]; // [rsp+30h] [rbp-278h] BYREF
  wchar_t v16[264]; // [rsp+50h] [rbp-258h] BYREF

  v15[2] = this;
  v8 = (_WORD *)((char *)this + 32);
  *((_QWORD *)this + 2) = v8;
  *((_QWORD *)this + 3) = 65;
  *v8 = 0;
  *((_QWORD *)this + 1) = &TLMString<64,64,32767>::`vftable';
  *(_QWORD *)this = &CRegistry::`vftable';
  *((_DWORD *)this + 42) = 1;
  CLMString::operator=((char *)this + 8, a3);
  SetLastError(0);
  v15[0] = 0;
  v9 = a2 == HKEY_LOCAL_MACHINE
    && a3
    && (unsigned __int8)RtlIsStateSeparationEnabled()
    && GetSearchRegistryRedirect(v13, v15)
    && CSearchRegistryRedirectHelper::MapRegistryKeyPath(v15[0], a3, v16, v14) >= 0;
  v10 = v16;
  if ( !v9 )
    v10 = a3;
  v11 = RegOpenKeyExW(a2, v10, 0, a4, (PHKEY)this + 22);
  if ( v11 )
  {
    *((_QWORD *)this + 22) = 0;
    SetLastError(v11);
  }
  return this;
}

```

## disassembly

```asm
0x180006300  push    rbx
0x180006302  push    rbp
0x180006303  push    rsi
0x180006304  push    rdi
0x180006305  push    r14
0x180006307  push    r15
0x180006309  sub     rsp, 278h
0x180006310  mov     rax, cs:__security_cookie
0x180006317  xor     rax, rsp
0x18000631a  mov     [rsp+2A8h+var_48], rax
0x180006322  mov     r14d, r9d
0x180006325  mov     rsi, r8
0x180006328  mov     rbp, rdx
0x18000632b  mov     rbx, rcx
0x18000632e  mov     [rsp+2A8h+var_268], rcx
0x180006333  add     rcx, 20h ; ' '
0x180006337  mov     [rbx+10h], rcx
0x18000633b  mov     qword ptr [rbx+18h], 41h ; 'A'
0x180006343  xor     r15d, r15d
0x180006346  mov     [rcx], r15w
0x18000634a  lea     rax, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x180006351  mov     [rbx+8], rax
0x180006355  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18000635c  mov     [rbx], rax
0x18000635f  mov     dword ptr [rbx+0A8h], 1
0x180006369  mov     rdx, r8
0x18000636c  lea     rcx, [rbx+8]
0x180006370  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180006375  xor     ecx, ecx; dwErrCode
0x180006377  call    cs:__imp_SetLastError
0x18000637d  mov     [rsp+2A8h+var_278], r15
0x180006382  cmp     rbp, 0FFFFFFFF80000002h
0x180006389  jz      short loc_1800063E6
0x18000638b  xor     al, al
0x18000638d  lea     rdi, [rbx+0B0h]
0x180006394  lea     rdx, [rsp+2A8h+var_258]
0x180006399  test    al, al
0x18000639b  cmovz   rdx, rsi; lpSubKey
0x18000639f  mov     [rsp+2A8h+phkResult], rdi; phkResult
0x1800063a4  mov     r9d, r14d; samDesired
0x1800063a7  xor     r8d, r8d; ulOptions
0x1800063aa  mov     rcx, rbp; hKey
0x1800063ad  call    cs:__imp_RegOpenKeyExW
0x1800063b3  test    eax, eax
0x1800063b5  jz      short loc_1800063C3
0x1800063b7  mov     [rdi], r15
0x1800063ba  mov     ecx, eax; dwErrCode
0x1800063bc  call    cs:__imp_SetLastError
0x1800063c2  nop
0x1800063c3  mov     rax, rbx
0x1800063c6  mov     rcx, [rsp+2A8h+var_48]
0x1800063ce  xor     rcx, rsp; StackCookie
0x1800063d1  call    __security_check_cookie
0x1800063d6  add     rsp, 278h
0x1800063dd  pop     r15
0x1800063df  pop     r14
0x1800063e1  pop     rdi
0x1800063e2  pop     rsi
0x1800063e3  pop     rbp
0x1800063e4  pop     rbx
0x1800063e5  retn
0x1800063e6  test    rsi, rsi
0x1800063e9  jz      short loc_18000638B
0x1800063eb  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800063f1  test    al, al
0x1800063f3  jz      short loc_18000638B
0x1800063f5  lea     rdx, [rsp+2A8h+var_278]; struct CSearchRegistryRedirectHelper **
0x1800063fa  call    ?GetSearchRegistryRedirect@@YA_NPEB_WPEAPEAVCSearchRegistryRedirectHelper@@@Z; GetSearchRegistryRedirect(wchar_t const *,CSearchRegistryRedirectHelper * *)
0x1800063ff  test    al, al
0x180006401  jz      short loc_18000638B
0x180006403  lea     r8, [rsp+2A8h+var_258]; wchar_t *
0x180006408  mov     rdx, rsi; wchar_t *
0x18000640b  mov     rcx, [rsp+2A8h+var_278]; this
0x180006410  call    ?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z; CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)
0x180006415  test    eax, eax
0x180006417  js      loc_18000638B
0x18000641d  mov     al, 1
0x18000641f  jmp     loc_18000638D
```
