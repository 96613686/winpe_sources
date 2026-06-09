# CMVCellularEmulator2::LoadOperatorProfileSelection(__MIDL___MIDL_itf_mvcellularv2_0000_0000_0004 const *,ulong *,uchar * *)

- ea: `0x1800111d0`
- end: `0x180011498`
- name: `?LoadOperatorProfileSelection@CMVCellularEmulator2@@UEAAJPEBU__MIDL___MIDL_itf_mvcellularv2_0000_0000_0004@@PEAKPEAPEAE@Z`
- size: `712`
- prototype: `__int64 __fastcall(CMVCellularEmulator2 *this, const WCHAR *, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800076a4`
- `0x1800111d0`
- `0x18001192c`
- `0x180012d80`
- `0x180012da0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011273`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800112d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800112e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001134d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001135e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011417`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011428`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011441`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011452`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011273`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800112d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800112e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001134d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001135e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011417`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011428`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011441`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011452`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001131e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800113e8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001131e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800113e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011244`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800112a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011244`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800112a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800113a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800113a5`

## string_xrefs

- `0x180011476`: `onecoreuap\admin\prov\multivariant\common\inc\MvTypes.h`
- `0x180011487`: `onecoreuap\admin\prov\multivariant\common\inc\MvTypes.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMVCellularEmulator2::LoadOperatorProfileSelection(
        CMVCellularEmulator2 *this,
        const WCHAR *a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  unsigned int ValueW; // eax
  unsigned int v13; // ebx
  unsigned __int64 v14; // rsi
  SIZE_T v15; // rax
  __int64 v16; // r9
  unsigned __int8 *pvData; // rax
  const char *v18; // r9
  unsigned __int8 *v19; // rbx
  unsigned int v20; // eax
  unsigned int v21; // ebx
  const char *v22; // r9
  __int64 *v23; // rdx
  __int64 v24; // [rsp+0h] [rbp-68h] BYREF
  PHKEY phkResult; // [rsp+20h] [rbp-48h]
  HKEY hKey[2]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY hkey; // [rsp+70h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 2) )
  {
    hKey[0] = 0;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, gc_wszRegCellularEmulator, 0, 0x20019u, hKey);
    if ( v8 )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x166,
             (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
             (const char *)v8,
             (unsigned int)phkResult);
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
      return v9;
    }
    else
    {
      hkey = 0;
      v10 = RegOpenKeyExW(hKey[0], L"Datastore", 0, 0x20019u, &hkey);
      if ( v10 )
      {
        v11 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x16A,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
                (const char *)v10,
                (unsigned int)phkResult);
        if ( hkey )
          RegCloseKey(hkey);
        if ( hKey[0] )
          RegCloseKey(hKey[0]);
        return v11;
      }
      else
      {
        ValueW = RegGetValueW(hkey, a2, L"ProfileSelection", 8u, 0, 0, a3);
        if ( ValueW )
        {
          v13 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x16E,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
                  (const char *)ValueW,
                  (unsigned int)phkResult);
          if ( hkey )
            RegCloseKey(hkey);
          if ( hKey[0] )
            RegCloseKey(hKey[0]);
          return v13;
        }
        else
        {
          v14 = *a3;
          hKey[1] = 0;
          v15 = v14;
          if ( is_mul_ok(v14, 1u) )
          {
            v16 = 0;
          }
          else
          {
            v15 = -1;
            v16 = 2147942934LL;
          }
          if ( (int)v16 < 0 )
          {
            try
            {
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x3B,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvTypes.h",
                (const char *)v16,
                (int)phkResult);
            }
            catch ( ... )
            {
              v23 = &v24;
              *((_DWORD *)v23 + 28) = wil::details::in1diag3::Return_CaughtException(
                                        (wil::details::in1diag3 *)v23[13],
                                        (void *)0x175,
                                        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
                                        v22);
              return (unsigned int)hkey;
            }
          }
          pvData = (unsigned __int8 *)CoTaskMemRealloc(0, v15);
          v19 = pvData;
          if ( (_DWORD)v14 && !pvData )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x3F,
              (int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvTypes.h",
              v18);
          v20 = RegGetValueW(hkey, a2, L"ProfileSelection", 8u, 0, pvData, a3);
          if ( v20 )
          {
            v21 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x171,
                    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
                    (const char *)v20,
                    (unsigned int)phkResult);
            if ( hkey )
              RegCloseKey(hkey);
            if ( hKey[0] )
              RegCloseKey(hKey[0]);
            return v21;
          }
          else
          {
            *a4 = v19;
            *a3 = v14;
            if ( hkey )
              RegCloseKey(hkey);
            if ( hKey[0] )
              RegCloseKey(hKey[0]);
            return 0;
          }
        }
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x161,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
      (const char *)0x8007139FLL,
      (int)phkResult);
    return 2147947423LL;
  }
}

```

## disassembly

```asm
0x1800111d0  mov     [rsp+arg_8], rbx
0x1800111d5  mov     [rsp+arg_10], rsi
0x1800111da  push    rdi
0x1800111db  push    r14
0x1800111dd  push    r15
0x1800111df  sub     rsp, 50h
0x1800111e3  mov     r15, r9
0x1800111e6  mov     rdi, r8
0x1800111e9  mov     r14, rdx
0x1800111ec  cmp     qword ptr [rcx+10h], 0
0x1800111f1  jnz     short loc_180011218
0x1800111f3  mov     rcx, [rsp+68h]; this
0x1800111f8  mov     ebx, 8007139Fh
0x1800111fd  mov     r9d, ebx; char *
0x180011200  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180011207  mov     edx, 161h; void *
0x18001120c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011211  mov     eax, ebx
0x180011213  jmp     loc_180011460
0x180011218  mov     [rsp+68h+hKey], 0
0x180011221  lea     rax, [rsp+68h+hKey]
0x180011226  mov     [rsp+68h+phkResult], rax; unsigned int
0x18001122b  mov     ebx, 20019h
0x180011230  mov     r9d, ebx; samDesired
0x180011233  xor     r8d, r8d; ulOptions
0x180011236  mov     rdx, cs:?gc_wszRegCellularEmulator@@3PEBGEB; lpSubKey
0x18001123d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011244  call    cs:__imp_RegOpenKeyExW
0x18001124a  test    eax, eax
0x18001124c  jz      short loc_180011280
0x18001124e  mov     rcx, [rsp+68h]; this
0x180011253  mov     r9d, eax; char *
0x180011256  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001125d  mov     edx, 166h; void *
0x180011262  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180011267  mov     ebx, eax
0x180011269  mov     rcx, [rsp+68h+hKey]; hKey
0x18001126e  test    rcx, rcx
0x180011271  jz      short loc_180011279
0x180011273  call    cs:__imp_RegCloseKey
0x180011279  mov     eax, ebx
0x18001127b  jmp     loc_180011460
0x180011280  mov     [rsp+68h+hkey], 0
0x180011289  lea     rax, [rsp+68h+hkey]
0x18001128e  mov     [rsp+68h+phkResult], rax; unsigned int
0x180011293  mov     r9d, ebx; samDesired
0x180011296  xor     r8d, r8d; ulOptions
0x180011299  lea     rdx, ?c_datastoreKeyName@@3QBGB; "Datastore"
0x1800112a0  mov     rcx, [rsp+68h+hKey]; hKey
0x1800112a5  call    cs:__imp_RegOpenKeyExW
0x1800112ab  test    eax, eax
0x1800112ad  jz      short loc_1800112F2
0x1800112af  mov     rcx, [rsp+68h]; this
0x1800112b4  mov     r9d, eax; char *
0x1800112b7  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800112be  mov     edx, 16Ah; void *
0x1800112c3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800112c8  mov     ebx, eax
0x1800112ca  mov     rcx, [rsp+68h+hkey]; hKey
0x1800112cf  test    rcx, rcx
0x1800112d2  jz      short loc_1800112DB
0x1800112d4  call    cs:__imp_RegCloseKey
0x1800112da  nop
0x1800112db  mov     rcx, [rsp+68h+hKey]; hKey
0x1800112e0  test    rcx, rcx
0x1800112e3  jz      short loc_1800112EB
0x1800112e5  call    cs:__imp_RegCloseKey
0x1800112eb  mov     eax, ebx
0x1800112ed  jmp     loc_180011460
0x1800112f2  mov     [rsp+68h+pcbData], rdi; pcbData
0x1800112f7  mov     [rsp+68h+pvData], 0; pvData
0x180011300  mov     [rsp+68h+phkResult], 0; int
0x180011309  mov     r9d, 8; dwFlags
0x18001130f  lea     r8, ?gc_wszProfileSelection@@3QBGB; "ProfileSelection"
0x180011316  mov     rdx, r14; lpSubKey
0x180011319  mov     rcx, [rsp+68h+hkey]; hkey
0x18001131e  call    cs:__imp_RegGetValueW
0x180011324  test    eax, eax
0x180011326  jz      short loc_18001136B
0x180011328  mov     rcx, [rsp+68h]; this
0x18001132d  mov     r9d, eax; char *
0x180011330  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180011337  mov     edx, 16Eh; void *
0x18001133c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180011341  mov     ebx, eax
0x180011343  mov     rcx, [rsp+68h+hkey]; hKey
0x180011348  test    rcx, rcx
0x18001134b  jz      short loc_180011354
0x18001134d  call    cs:__imp_RegCloseKey
0x180011353  nop
0x180011354  mov     rcx, [rsp+68h+hKey]; hKey
0x180011359  test    rcx, rcx
0x18001135c  jz      short loc_180011364
0x18001135e  call    cs:__imp_RegCloseKey
0x180011364  mov     eax, ebx
0x180011366  jmp     loc_180011460
0x18001136b  mov     esi, [rdi]
0x18001136d  mov     [rsp+68h+var_20], 0
0x180011376  mov     eax, 1
0x18001137b  mul     rsi
0x18001137e  test    rdx, rdx
0x180011381  jnz     short loc_180011388
0x180011383  xor     r9d, r9d
0x180011386  jmp     short loc_180011392
0x180011388  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001138c  mov     r9d, 80070216h; char *
0x180011392  mov     rcx, [rsp+68h]; this
0x180011397  test    r9d, r9d
0x18001139a  js      loc_180011476
0x1800113a0  mov     rdx, rax; cb
0x1800113a3  xor     ecx, ecx; pv
0x1800113a5  call    cs:__imp_CoTaskMemRealloc
0x1800113ab  mov     rbx, rax
0x1800113ae  test    esi, esi
0x1800113b0  jz      short loc_1800113C0
0x1800113b2  mov     rcx, [rsp+68h]; this
0x1800113b7  test    rax, rax
0x1800113ba  jz      loc_180011487
0x1800113c0  mov     [rsp+68h+pcbData], rdi; pcbData
0x1800113c5  mov     [rsp+68h+pvData], rbx; pvData
0x1800113ca  mov     [rsp+68h+phkResult], 0; unsigned int
0x1800113d3  mov     r9d, 8; dwFlags
0x1800113d9  lea     r8, ?gc_wszProfileSelection@@3QBGB; "ProfileSelection"
0x1800113e0  mov     rdx, r14; lpSubKey
0x1800113e3  mov     rcx, [rsp+68h+hkey]; hkey
0x1800113e8  call    cs:__imp_RegGetValueW
0x1800113ee  test    eax, eax
0x1800113f0  jz      short loc_180011432
0x1800113f2  mov     rcx, [rsp+68h]; this
0x1800113f7  mov     r9d, eax; char *
0x1800113fa  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180011401  mov     edx, 171h; void *
0x180011406  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001140b  mov     ebx, eax
0x18001140d  mov     rcx, [rsp+68h+hkey]; hKey
0x180011412  test    rcx, rcx
0x180011415  jz      short loc_18001141E
0x180011417  call    cs:__imp_RegCloseKey
0x18001141d  nop
0x18001141e  mov     rcx, [rsp+68h+hKey]; hKey
0x180011423  test    rcx, rcx
0x180011426  jz      short loc_18001142E
0x180011428  call    cs:__imp_RegCloseKey
0x18001142e  mov     eax, ebx
0x180011430  jmp     short loc_180011460
0x180011432  mov     [r15], rbx
0x180011435  mov     [rdi], esi
0x180011437  mov     rcx, [rsp+68h+hkey]; hKey
0x18001143c  test    rcx, rcx
0x18001143f  jz      short loc_180011448
0x180011441  call    cs:__imp_RegCloseKey
0x180011447  nop
0x180011448  mov     rcx, [rsp+68h+hKey]; hKey
0x18001144d  test    rcx, rcx
0x180011450  jz      short loc_180011458
0x180011452  call    cs:__imp_RegCloseKey
0x180011458  xor     eax, eax
0x18001145a  jmp     short loc_180011460
0x18001145c  mov     eax, dword ptr [rsp+68h+hkey]
0x180011460  lea     r11, [rsp+68h+var_18]
0x180011465  mov     rbx, [r11+28h]
0x180011469  mov     rsi, [r11+30h]
0x18001146d  mov     rsp, r11
0x180011470  pop     r15
0x180011472  pop     r14
0x180011474  pop     rdi
0x180011475  retn
0x180011476  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001147d  mov     edx, 3Bh ; ';'; void *
0x180011482  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011487  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001148e  lea     edx, [rax+3Fh]; void *
0x180011491  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
