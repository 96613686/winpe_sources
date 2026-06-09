# GetHomeDirConfigPreference(ushort * *,ushort * *)

- ea: `0x18002249c`
- end: `0x1800226e7`
- name: `?GetHomeDirConfigPreference@@YAJPEAPEAG0@Z`
- size: `587`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180007aa8`
- `0x18003483c`

## callees

- `0x1800053a0`
- `0x18000d460`
- `0x1800111a0`
- `0x180015108`
- `0x18002249c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800225ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800225ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002259f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002259f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800224f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800224f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022537`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002260c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022537`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002260c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002258c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002258c`

## string_xrefs

- `0x1800224c6`: `System\CurrentControlSet\Services\ProfSvc\Parameters`
- `0x18002267e`: `System\CurrentControlSet\Services\ProfSvc\Parameters`

## pseudocode

```c
__int64 __fastcall GetHomeDirConfigPreference(BYTE **a1, unsigned __int16 **a2)
{
  BYTE *v4; // rsi
  LSTATUS v5; // eax
  bool v6; // sf
  HKEY v7; // r14
  BYTE *v8; // rdi
  LSTATUS v9; // eax
  signed int v10; // ebx
  HANDLE ProcessHeap; // rax
  LSTATUS v13; // eax
  __int64 v14; // rdx
  unsigned int v15; // ebx
  unsigned __int16 *v16; // rax
  BYTE *v17; // [rsp+30h] [rbp-30h] BYREF
  __int64 v18; // [rsp+38h] [rbp-28h]
  __int64 v19; // [rsp+40h] [rbp-20h]
  unsigned __int16 *v20; // [rsp+48h] [rbp-18h] BYREF
  __int64 v21; // [rsp+50h] [rbp-10h]
  __int64 v22; // [rsp+58h] [rbp-8h]
  DWORD cbData; // [rsp+A0h] [rbp+40h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp+50h] BYREF

  *a1 = 0;
  *a2 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  hKey = 0;
  v4 = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\ProfSvc\\Parameters",
         0,
         0x20019u,
         &hKey);
  v6 = v5 < 0;
  if ( v5 > 0 )
    v6 = 1;
  if ( v6 )
    goto LABEL_13;
  v7 = hKey;
  Type = 0;
  cbData = 0;
  v8 = 0;
  v9 = RegQueryValueExW(hKey, L"HomeDir", 0, &Type, 0, &cbData);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 < 0 )
    goto LABEL_12;
  if ( Type - 1 > 1 || !cbData || (cbData & 1) != 0 )
    goto LABEL_23;
  v8 = (BYTE *)Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Alloc(cbData);
  if ( !v8 )
  {
    v10 = -2147024882;
    goto LABEL_12;
  }
  v13 = RegQueryValueExW(v7, L"HomeDir", 0, &Type, v8, &cbData);
  v10 = v13;
  if ( v13 > 0 )
    v10 = (unsigned __int16)v13 | 0x80070000;
  if ( v10 >= 0 )
  {
    v14 = cbData >> 1;
    if ( !*(_WORD *)&v8[2 * (unsigned int)(v14 - 1)] )
    {
      v18 = 0;
      v19 = 0;
      if ( (_DWORD)v14 )
      {
        v17 = v8;
        v18 = v14 - 1;
        v4 = v8;
        v19 = (unsigned int)v14;
        *(_WORD *)&v8[2 * v14 - 2] = 0;
      }
      v8 = 0;
      goto LABEL_12;
    }
LABEL_23:
    v10 = -2147024883;
  }
LABEL_12:
  Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v8);
  RegCloseKey(hKey);
  if ( v10 < 0 )
  {
LABEL_13:
    if ( v4 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    return 2147943568LL;
  }
  v20 = 0;
  v21 = 0;
  v22 = 0;
  if ( (int)Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeNoExpand(
              &v20,
              -2147483646,
              L"System\\CurrentControlSet\\Services\\ProfSvc\\Parameters",
              L"HomeDirDrive") >= 0 )
  {
    v16 = v20;
    v15 = 0;
    *a1 = v4;
    *a2 = v16;
    v17 = 0;
    v19 = 0;
    v18 = 0;
    v20 = 0;
    v22 = 0;
    v21 = 0;
  }
  else
  {
    v15 = -2147023728;
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v20);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v17);
  return v15;
}

```

## disassembly

```asm
0x18002249c  mov     [rsp-38h+arg_18], rbx
0x1800224a1  push    rbp
0x1800224a2  push    rsi
0x1800224a3  push    rdi
0x1800224a4  push    r12
0x1800224a6  push    r13
0x1800224a8  push    r14
0x1800224aa  push    r15
0x1800224ac  mov     rbp, rsp
0x1800224af  sub     rsp, 60h
0x1800224b3  xor     r13d, r13d
0x1800224b6  lea     rax, [rbp+hKey]
0x1800224ba  mov     [rcx], r13
0x1800224bd  mov     r15, rdx
0x1800224c0  mov     [rdx], r13
0x1800224c3  mov     r12, rcx
0x1800224c6  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Pr"...
0x1800224cd  mov     [rbp+var_30], r13
0x1800224d1  mov     r9d, 20019h; samDesired
0x1800224d7  mov     [rbp+var_28], r13
0x1800224db  xor     r8d, r8d; ulOptions
0x1800224de  mov     [rbp+var_20], r13
0x1800224e2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800224e9  mov     [rbp+hKey], r13
0x1800224ed  mov     esi, r13d
0x1800224f0  mov     [rsp+60h+phkResult], rax; phkResult
0x1800224f5  call    cs:__imp_RegOpenKeyExW
0x1800224fb  test    eax, eax
0x1800224fd  jg      loc_1800225D0
0x180022503  js      loc_18002259A
0x180022509  mov     r14, [rbp+hKey]
0x18002250d  lea     rax, [rbp+cbData]
0x180022511  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180022516  lea     r9, [rbp+Type]; lpType
0x18002251a  mov     rcx, r14; hKey
0x18002251d  mov     [rsp+60h+phkResult], r13; lpData
0x180022522  xor     r8d, r8d; lpReserved
0x180022525  mov     [rbp+Type], r13d
0x180022529  lea     rdx, aHomedir; "HomeDir"
0x180022530  mov     [rbp+cbData], r13d
0x180022534  mov     rdi, r13
0x180022537  call    cs:__imp_RegQueryValueExW
0x18002253d  mov     ebx, eax
0x18002253f  test    eax, eax
0x180022541  jg      loc_1800225DF
0x180022547  test    ebx, ebx
0x180022549  js      short loc_180022580
0x18002254b  mov     eax, [rbp+Type]
0x18002254e  dec     eax
0x180022550  cmp     eax, 1
0x180022553  ja      loc_180022669
0x180022559  mov     eax, [rbp+cbData]
0x18002255c  test    eax, eax
0x18002255e  jz      loc_180022669
0x180022564  test    al, 1
0x180022566  jnz     loc_180022669
0x18002256c  mov     ecx, eax
0x18002256e  call    ?Alloc@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAPEAG_K@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Alloc(unsigned __int64)
0x180022573  mov     rdi, rax
0x180022576  test    rax, rax
0x180022579  jnz     short loc_1800225ED
0x18002257b  mov     ebx, 8007000Eh
0x180022580  mov     rcx, rdi
0x180022583  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180022588  mov     rcx, [rbp+hKey]; hKey
0x18002258c  call    cs:__imp_RegCloseKey
0x180022592  test    ebx, ebx
0x180022594  jns     loc_180022673
0x18002259a  test    rsi, rsi
0x18002259d  jz      short loc_1800225B3
0x18002259f  call    cs:__imp_GetProcessHeap
0x1800225a5  mov     r8, rsi; lpMem
0x1800225a8  xor     edx, edx; dwFlags
0x1800225aa  mov     rcx, rax; hHeap
0x1800225ad  call    cs:__imp_HeapFree
0x1800225b3  mov     eax, 80070490h
0x1800225b8  mov     rbx, [rsp+60h+arg_18]
0x1800225c0  add     rsp, 60h
0x1800225c4  pop     r15
0x1800225c6  pop     r14
0x1800225c8  pop     r13
0x1800225ca  pop     r12
0x1800225cc  pop     rdi
0x1800225cd  pop     rsi
0x1800225ce  pop     rbp
0x1800225cf  retn
0x1800225d0  movzx   eax, ax
0x1800225d3  or      eax, 80070000h
0x1800225d8  test    eax, eax
0x1800225da  jmp     loc_180022503
0x1800225df  movzx   ebx, ax
0x1800225e2  or      ebx, 80070000h
0x1800225e8  jmp     loc_180022547
0x1800225ed  lea     rax, [rbp+cbData]
0x1800225f1  xor     r8d, r8d; lpReserved
0x1800225f4  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1800225f9  lea     r9, [rbp+Type]; lpType
0x1800225fd  lea     rdx, aHomedir; "HomeDir"
0x180022604  mov     [rsp+60h+phkResult], rdi; lpData
0x180022609  mov     rcx, r14; hKey
0x18002260c  call    cs:__imp_RegQueryValueExW
0x180022612  mov     ebx, eax
0x180022614  test    eax, eax
0x180022616  jg      short loc_18002265E
0x180022618  test    ebx, ebx
0x18002261a  js      loc_180022580
0x180022620  mov     edx, [rbp+cbData]
0x180022623  shr     edx, 1
0x180022625  lea     eax, [rdx-1]
0x180022628  cmp     [rdi+rax*2], r13w
0x18002262d  jnz     short loc_180022669
0x18002262f  mov     [rbp+var_28], r13
0x180022633  mov     [rbp+var_20], r13
0x180022637  mov     ecx, edx
0x180022639  test    edx, edx
0x18002263b  jz      short loc_180022656
0x18002263d  lea     rax, [rdx-1]
0x180022641  mov     [rbp+var_30], rdi
0x180022645  mov     [rbp+var_28], rax
0x180022649  mov     rsi, rdi
0x18002264c  mov     [rbp+var_20], rcx
0x180022650  mov     [rdi+rdx*2-2], r13w
0x180022656  mov     rdi, r13
0x180022659  jmp     loc_180022580
0x18002265e  movzx   ebx, ax
0x180022661  or      ebx, 80070000h
0x180022667  jmp     short loc_180022618
0x180022669  mov     ebx, 8007000Dh
0x18002266e  jmp     loc_180022580
0x180022673  lea     r9, aHomedirdrive; "HomeDirDrive"
0x18002267a  mov     [rbp+var_18], r13
0x18002267e  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Pr"...
0x180022685  mov     [rbp+var_10], r13
0x180022689  mov     rdx, 0FFFFFFFF80000002h
0x180022690  mov     [rbp+var_8], r13
0x180022694  lea     rcx, [rbp+var_18]
0x180022698  call    ?InitializeNoExpand@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeNoExpand(HKEY__ *,ushort const *,ushort const *)
0x18002269d  test    eax, eax
0x18002269f  jns     short loc_1800226A8
0x1800226a1  mov     ebx, 80070490h
0x1800226a6  jmp     short loc_1800226CE
0x1800226a8  mov     rax, [rbp+var_18]
0x1800226ac  mov     ebx, r13d
0x1800226af  mov     [r12], rsi
0x1800226b3  mov     [r15], rax
0x1800226b6  mov     [rbp+var_30], r13
0x1800226ba  mov     [rbp+var_20], r13
0x1800226be  mov     [rbp+var_28], r13
0x1800226c2  mov     [rbp+var_18], r13
0x1800226c6  mov     [rbp+var_8], r13
0x1800226ca  mov     [rbp+var_10], r13
0x1800226ce  lea     rcx, [rbp+var_18]
0x1800226d2  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800226d7  lea     rcx, [rbp+var_30]
0x1800226db  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800226e0  mov     eax, ebx
0x1800226e2  jmp     loc_1800225B8
```
