# GetHomeDirConfigPreference(ushort * *,ushort * *)

- ea: `0x18002568c`
- end: `0x18002590c`
- name: `?GetHomeDirConfigPreference@@YAJPEAPEAG0@Z`
- size: `640`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800054cc`
- `0x180034f78`

## callees

- `0x18000b020`
- `0x18000b060`
- `0x18000e1a0`
- `0x180010524`
- `0x18002568c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800257b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800257b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800257a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800257a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800256e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800256e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002572d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002581f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002572d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002581f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002578c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002578c`

## string_xrefs

- `0x1800256b6`: `System\CurrentControlSet\Services\ProfSvc\Parameters`
- `0x1800258a3`: `System\CurrentControlSet\Services\ProfSvc\Parameters`

## pseudocode

```c
__int64 __fastcall GetHomeDirConfigPreference(BYTE **a1, unsigned __int16 **a2)
{
  BYTE *v4; // rdi
  LSTATUS v5; // eax
  bool v6; // sf
  HKEY v7; // r14
  BYTE *v8; // rsi
  LSTATUS v9; // eax
  signed int v10; // ebx
  HANDLE ProcessHeap; // rax
  LSTATUS v13; // eax
  __int64 v14; // r14
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
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v17);
      if ( (_DWORD)v14 )
      {
        v17 = v8;
        v18 = v14 - 1;
        v4 = v8;
        v19 = (unsigned int)v14;
        *(_WORD *)&v8[2 * v14 - 2] = 0;
      }
      else
      {
        v4 = v17;
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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v20);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v17);
  return v15;
}

```

## disassembly

```asm
0x18002568c  mov     [rsp-38h+arg_18], rbx
0x180025691  push    rbp
0x180025692  push    rsi
0x180025693  push    rdi
0x180025694  push    r12
0x180025696  push    r13
0x180025698  push    r14
0x18002569a  push    r15
0x18002569c  mov     rbp, rsp
0x18002569f  sub     rsp, 60h
0x1800256a3  xor     r13d, r13d
0x1800256a6  lea     rax, [rbp+hKey]
0x1800256aa  mov     [rcx], r13
0x1800256ad  mov     r15, rdx
0x1800256b0  mov     [rdx], r13
0x1800256b3  mov     r12, rcx
0x1800256b6  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Pr"...
0x1800256bd  mov     [rbp+var_30], r13
0x1800256c1  mov     r9d, 20019h; samDesired
0x1800256c7  mov     [rbp+var_28], r13
0x1800256cb  xor     r8d, r8d; ulOptions
0x1800256ce  mov     [rbp+var_20], r13
0x1800256d2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800256d9  mov     [rbp+hKey], r13
0x1800256dd  mov     edi, r13d
0x1800256e0  mov     [rsp+60h+phkResult], rax; phkResult
0x1800256e5  call    cs:__imp_RegOpenKeyExW
0x1800256ec  nop     dword ptr [rax+rax+00h]
0x1800256f1  test    eax, eax
0x1800256f3  jg      loc_1800257E3
0x1800256f9  js      loc_1800257A0
0x1800256ff  mov     r14, [rbp+hKey]
0x180025703  lea     rax, [rbp+cbData]
0x180025707  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18002570c  lea     r9, [rbp+Type]; lpType
0x180025710  mov     rcx, r14; hKey
0x180025713  mov     [rsp+60h+phkResult], r13; lpData
0x180025718  xor     r8d, r8d; lpReserved
0x18002571b  mov     [rbp+Type], r13d
0x18002571f  lea     rdx, aHomedir; "HomeDir"
0x180025726  mov     [rbp+cbData], r13d
0x18002572a  mov     rsi, r13
0x18002572d  call    cs:__imp_RegQueryValueExW
0x180025734  nop     dword ptr [rax+rax+00h]
0x180025739  mov     ebx, eax
0x18002573b  test    eax, eax
0x18002573d  jg      loc_1800257F2
0x180025743  test    ebx, ebx
0x180025745  js      short loc_180025780
0x180025747  mov     eax, [rbp+Type]
0x18002574a  dec     eax
0x18002574c  cmp     eax, 1
0x18002574f  ja      loc_180025888
0x180025755  mov     eax, [rbp+cbData]
0x180025758  test    eax, eax
0x18002575a  jz      loc_180025888
0x180025760  test    al, 1
0x180025762  jnz     loc_180025888
0x180025768  mov     ecx, eax
0x18002576a  call    ?Alloc@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAPEAG_K@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Alloc(unsigned __int64)
0x18002576f  mov     rsi, rax
0x180025772  test    rax, rax
0x180025775  jnz     loc_180025800
0x18002577b  mov     ebx, 8007000Eh
0x180025780  mov     rcx, rsi
0x180025783  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180025788  mov     rcx, [rbp+hKey]; hKey
0x18002578c  call    cs:__imp_RegCloseKey
0x180025793  nop     dword ptr [rax+rax+00h]
0x180025798  test    ebx, ebx
0x18002579a  jns     loc_180025898
0x1800257a0  test    rdi, rdi
0x1800257a3  jz      short loc_1800257C5
0x1800257a5  call    cs:__imp_GetProcessHeap
0x1800257ac  nop     dword ptr [rax+rax+00h]
0x1800257b1  mov     r8, rdi; lpMem
0x1800257b4  xor     edx, edx; dwFlags
0x1800257b6  mov     rcx, rax; hHeap
0x1800257b9  call    cs:__imp_HeapFree
0x1800257c0  nop     dword ptr [rax+rax+00h]
0x1800257c5  mov     eax, 80070490h
0x1800257ca  mov     rbx, [rsp+60h+arg_18]
0x1800257d2  add     rsp, 60h
0x1800257d6  pop     r15
0x1800257d8  pop     r14
0x1800257da  pop     r13
0x1800257dc  pop     r12
0x1800257de  pop     rdi
0x1800257df  pop     rsi
0x1800257e0  pop     rbp
0x1800257e1  retn
0x1800257e3  movzx   eax, ax
0x1800257e6  or      eax, 80070000h
0x1800257eb  test    eax, eax
0x1800257ed  jmp     loc_1800256F9
0x1800257f2  movzx   ebx, ax
0x1800257f5  or      ebx, 80070000h
0x1800257fb  jmp     loc_180025743
0x180025800  lea     rax, [rbp+cbData]
0x180025804  xor     r8d, r8d; lpReserved
0x180025807  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18002580c  lea     r9, [rbp+Type]; lpType
0x180025810  lea     rdx, aHomedir; "HomeDir"
0x180025817  mov     [rsp+60h+phkResult], rsi; lpData
0x18002581c  mov     rcx, r14; hKey
0x18002581f  call    cs:__imp_RegQueryValueExW
0x180025826  nop     dword ptr [rax+rax+00h]
0x18002582b  mov     ebx, eax
0x18002582d  test    eax, eax
0x18002582f  jg      short loc_18002587D
0x180025831  test    ebx, ebx
0x180025833  js      loc_180025780
0x180025839  mov     r14d, [rbp+cbData]
0x18002583d  shr     r14d, 1
0x180025840  lea     eax, [r14-1]
0x180025844  cmp     [rsi+rax*2], r13w
0x180025849  jnz     short loc_180025888
0x18002584b  lea     rcx, [rbp+var_30]
0x18002584f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180025854  mov     ecx, r14d
0x180025857  test    r14d, r14d
0x18002585a  jz      short loc_180025892
0x18002585c  lea     rax, [r14-1]
0x180025860  mov     [rbp+var_30], rsi
0x180025864  mov     [rbp+var_28], rax
0x180025868  mov     rdi, rsi
0x18002586b  mov     [rbp+var_20], rcx
0x18002586f  mov     [rsi+r14*2-2], r13w
0x180025875  mov     rsi, r13
0x180025878  jmp     loc_180025780
0x18002587d  movzx   ebx, ax
0x180025880  or      ebx, 80070000h
0x180025886  jmp     short loc_180025831
0x180025888  mov     ebx, 8007000Dh
0x18002588d  jmp     loc_180025780
0x180025892  mov     rdi, [rbp+var_30]
0x180025896  jmp     short loc_180025875
0x180025898  lea     r9, aHomedirdrive; "HomeDirDrive"
0x18002589f  mov     [rbp+var_18], r13
0x1800258a3  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Pr"...
0x1800258aa  mov     [rbp+var_10], r13
0x1800258ae  mov     rdx, 0FFFFFFFF80000002h
0x1800258b5  mov     [rbp+var_8], r13
0x1800258b9  lea     rcx, [rbp+var_18]
0x1800258bd  call    ?InitializeNoExpand@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeNoExpand(HKEY__ *,ushort const *,ushort const *)
0x1800258c2  test    eax, eax
0x1800258c4  jns     short loc_1800258CD
0x1800258c6  mov     ebx, 80070490h
0x1800258cb  jmp     short loc_1800258F3
0x1800258cd  mov     rax, [rbp+var_18]
0x1800258d1  mov     ebx, r13d
0x1800258d4  mov     [r12], rdi
0x1800258d8  mov     [r15], rax
0x1800258db  mov     [rbp+var_30], r13
0x1800258df  mov     [rbp+var_20], r13
0x1800258e3  mov     [rbp+var_28], r13
0x1800258e7  mov     [rbp+var_18], r13
0x1800258eb  mov     [rbp+var_8], r13
0x1800258ef  mov     [rbp+var_10], r13
0x1800258f3  lea     rcx, [rbp+var_18]
0x1800258f7  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800258fc  lea     rcx, [rbp+var_30]
0x180025900  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180025905  mov     eax, ebx
0x180025907  jmp     loc_1800257CA
```
