# ServiceManager::ServiceManager(wchar_t const *,bool,bool)

- ea: `0x18000dfb0`
- end: `0x18000e175`
- name: `??0ServiceManager@@QEAA@PEB_W_N1@Z`
- size: `453`
- prototype: `ServiceManager *__fastcall(ServiceManager *this, const wchar_t *, __int64, char)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18000c2a0`

## callees

- `0x180001f60`
- `0x18000ab70`
- `0x18000c7b8`
- `0x18000cd98`
- `0x18000cee8`
- `0x18000d338`
- `0x18000d4e8`
- `0x18000ddd8`
- `0x18000dfb0`
- `0x18000e588`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e13a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e13a`

## string_xrefs

- `0x18000e168`: `RegOpenKeyExW`
- `0x18000e057`: `System\CurrentControlSet\Services\`

## pseudocode

```c
ServiceManager *__fastcall ServiceManager::ServiceManager(ServiceManager *this, const wchar_t *a2, __int64 a3, char a4)
{
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r9
  int v12; // eax
  DWORD v14; // [rsp+20h] [rbp-69h]
  int v15; // [rsp+30h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-51h] BYREF
  int v17; // [rsp+40h] [rbp-49h]
  ServiceManager *v18; // [rsp+50h] [rbp-39h]
  LPCVOID v19[2]; // [rsp+60h] [rbp-29h] BYREF
  __int64 v20; // [rsp+70h] [rbp-19h]
  unsigned __int64 v21; // [rsp+78h] [rbp-11h]
  LPCVOID lpMem[3]; // [rsp+80h] [rbp-9h] BYREF
  unsigned __int64 v23; // [rsp+98h] [rbp+Fh]
  LPCVOID v24[3]; // [rsp+A0h] [rbp+17h] BYREF
  unsigned __int64 v25; // [rsp+B8h] [rbp+2Fh]

  v18 = this;
  CriticalSection::CriticalSection((ServiceManager *)((char *)this + 8), 0x64u);
  *(_QWORD *)this = &ServiceManager::`vftable';
  *((_BYTE *)this + 64) = 0;
  *((_QWORD *)this + 9) = a2;
  *((_BYTE *)this + 80) = 0;
  Event::Event((ServiceManager *)((char *)this + 88));
  *((_QWORD *)this + 13) = 0;
  *((_BYTE *)this + 140) = a4;
  *((_DWORD *)this + 28) = 32;
  *(_QWORD *)((char *)this + 116) = 1;
  *(_QWORD *)((char *)this + 124) = 0;
  *(_QWORD *)((char *)this + 132) = 0;
  v15 = 0;
  v7 = *((_QWORD *)this + 9);
  *(_OWORD *)v19 = 0;
  v20 = 0;
  v21 = 0;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Construct<1,wchar_t const *>(
    v19,
    L"System\\CurrentControlSet\\Services\\",
    0x22u);
  v8 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v24, v19, v7);
  v9 = std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(lpMem, v8, L"\\Parameters");
  if ( *(_QWORD *)(v9 + 24) > 7u )
    v9 = *(_QWORD *)v9;
  hKey = 0;
  v17 = 1;
  if ( (unsigned int)RegistryKey::Create((__int64)&hKey, v10, (const WCHAR *)v9, v11, v14) )
    SystemError::Throw(L"RegOpenKeyExW");
  if ( v23 > 7 )
    operator delete(lpMem[0]);
  lpMem[2] = 0;
  v23 = 7;
  LOWORD(lpMem[0]) = 0;
  if ( v25 > 7 )
    operator delete(v24[0]);
  v24[2] = 0;
  v25 = 7;
  LOWORD(v24[0]) = 0;
  if ( v21 > 7 )
    operator delete(v19[0]);
  v20 = 0;
  v21 = 7;
  LOWORD(v19[0]) = 0;
  if ( (unsigned int)RegistryKey::QueryValue(&hKey, L"WaitHint", &v15) )
    v12 = 50000;
  else
    v12 = 1000 * v15;
  *((_DWORD *)this + 21) = v12;
  if ( hKey )
    RegCloseKey(hKey);
  return this;
}

```

## disassembly

```asm
0x18000dfb0  mov     [rsp-8+arg_8], rbx
0x18000dfb5  mov     [rsp-8+arg_10], rsi
0x18000dfba  push    rbp
0x18000dfbb  push    rdi
0x18000dfbc  push    r14
0x18000dfbe  lea     rbp, [rsp-47h]
0x18000dfc3  sub     rsp, 0D0h
0x18000dfca  mov     rax, cs:__security_cookie
0x18000dfd1  xor     rax, rsp
0x18000dfd4  mov     [rbp+57h+var_20], rax
0x18000dfd8  mov     dil, r9b
0x18000dfdb  mov     rbx, rdx
0x18000dfde  mov     rsi, rcx
0x18000dfe1  mov     [rbp+57h+var_90], rcx
0x18000dfe5  add     rcx, 8; this
0x18000dfe9  mov     edx, 64h ; 'd'; unsigned int
0x18000dfee  call    ??0CriticalSection@@QEAA@I@Z; CriticalSection::CriticalSection(uint)
0x18000dff3  nop
0x18000dff4  lea     rax, ??_7ServiceManager@@6B@; const ServiceManager::`vftable'
0x18000dffb  mov     [rsi], rax
0x18000dffe  xor     r14d, r14d
0x18000e001  mov     [rsi+40h], r14b
0x18000e005  mov     [rsi+48h], rbx
0x18000e009  mov     [rsi+50h], r14b
0x18000e00d  lea     rcx, [rsi+58h]; this
0x18000e011  call    ??0Event@@QEAA@_N0@Z; Event::Event(bool,bool)
0x18000e016  nop
0x18000e017  mov     [rsi+68h], r14
0x18000e01b  mov     [rsi+8Ch], dil
0x18000e022  mov     dword ptr [rsi+70h], 20h ; ' '
0x18000e029  lea     edi, [r14+1]
0x18000e02d  mov     [rsi+74h], rdi
0x18000e031  mov     [rsi+7Ch], r14
0x18000e035  mov     [rsi+84h], r14
0x18000e03c  mov     [rbp+57h+var_B0], r14d
0x18000e040  mov     rbx, [rsi+48h]
0x18000e044  xorps   xmm0, xmm0
0x18000e047  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18000e04b  mov     [rbp+57h+var_70], r14
0x18000e04f  mov     [rbp+57h+var_68], r14
0x18000e053  lea     r8d, [r14+22h]
0x18000e057  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\"
0x18000e05e  lea     rcx, [rbp+57h+var_80]
0x18000e062  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXQEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000e067  nop
0x18000e068  mov     r8, rbx
0x18000e06b  lea     rdx, [rbp+57h+var_80]
0x18000e06f  lea     rcx, [rbp+57h+var_40]
0x18000e073  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&,wchar_t const * const)
0x18000e078  nop
0x18000e079  lea     r8, aParameters; "\\Parameters"
0x18000e080  mov     rdx, rax
0x18000e083  lea     rcx, [rbp+57h+lpMem]
0x18000e087  call    ??$?H_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &&,wchar_t const * const)
0x18000e08c  nop
0x18000e08d  lea     ebx, [rdi+6]
0x18000e090  cmp     [rax+18h], rbx
0x18000e094  jbe     short loc_18000E099
0x18000e096  mov     rax, [rax]
0x18000e099  mov     [rbp+57h+hKey], r14
0x18000e09d  mov     [rbp+57h+var_A0], edi
0x18000e0a0  mov     r8, rax
0x18000e0a3  lea     rcx, [rbp+57h+hKey]
0x18000e0a7  call    ?Create@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK_N@Z; RegistryKey::Create(HKEY__ *,wchar_t const *,ulong,bool)
0x18000e0ac  test    eax, eax
0x18000e0ae  jnz     loc_18000E168
0x18000e0b4  cmp     [rbp+57h+var_48], rbx
0x18000e0b8  jbe     short loc_18000E0C3
0x18000e0ba  mov     rcx, [rbp+57h+lpMem]; lpMem
0x18000e0be  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e0c3  mov     [rbp+57h+var_50], r14
0x18000e0c7  mov     [rbp+57h+var_48], rbx
0x18000e0cb  mov     word ptr [rbp+57h+lpMem], r14w
0x18000e0d0  cmp     [rbp+57h+var_28], rbx
0x18000e0d4  jbe     short loc_18000E0DF
0x18000e0d6  mov     rcx, [rbp+57h+var_40]; lpMem
0x18000e0da  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e0df  mov     [rbp+57h+var_30], r14
0x18000e0e3  mov     [rbp+57h+var_28], rbx
0x18000e0e7  mov     word ptr [rbp+57h+var_40], r14w
0x18000e0ec  cmp     [rbp+57h+var_68], rbx
0x18000e0f0  jbe     short loc_18000E0FB
0x18000e0f2  mov     rcx, [rbp+57h+var_80]; lpMem
0x18000e0f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e0fb  mov     [rbp+57h+var_70], r14
0x18000e0ff  mov     [rbp+57h+var_68], rbx
0x18000e103  mov     word ptr [rbp+57h+var_80], r14w
0x18000e108  lea     r8, [rbp+57h+var_B0]
0x18000e10c  lea     rdx, aWaithint; "WaitHint"
0x18000e113  lea     rcx, [rbp+57h+hKey]
0x18000e117  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z; RegistryKey::QueryValue(wchar_t const *,uint &)
0x18000e11c  test    eax, eax
0x18000e11e  jnz     short loc_18000E129
0x18000e120  imul    eax, [rbp+57h+var_B0], 3E8h
0x18000e127  jmp     short loc_18000E12E
0x18000e129  mov     eax, 0C350h
0x18000e12e  mov     [rsi+54h], eax
0x18000e131  mov     rcx, [rbp+57h+hKey]; hKey
0x18000e135  test    rcx, rcx
0x18000e138  jz      short loc_18000E141
0x18000e13a  call    cs:__imp_RegCloseKey
0x18000e140  nop
0x18000e141  mov     rax, rsi
0x18000e144  mov     rcx, [rbp+57h+var_20]
0x18000e148  xor     rcx, rsp; StackCookie
0x18000e14b  call    __security_check_cookie
0x18000e150  lea     r11, [rsp+0E0h+var_10]
0x18000e158  mov     rbx, [r11+28h]
0x18000e15c  mov     rsi, [r11+30h]
0x18000e160  mov     rsp, r11
0x18000e163  pop     r14
0x18000e165  pop     rdi
0x18000e166  pop     rbp
0x18000e167  retn
0x18000e168  lea     rcx, aRegopenkeyexw; "RegOpenKeyExW"
0x18000e16f  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
```
