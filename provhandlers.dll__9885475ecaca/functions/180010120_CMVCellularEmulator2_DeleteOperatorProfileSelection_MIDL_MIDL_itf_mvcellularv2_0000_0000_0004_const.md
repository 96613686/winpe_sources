# CMVCellularEmulator2::DeleteOperatorProfileSelection(__MIDL___MIDL_itf_mvcellularv2_0000_0000_0004 const *)

- ea: `0x180010120`
- end: `0x180010353`
- name: `?DeleteOperatorProfileSelection@CMVCellularEmulator2@@UEAAJPEBU__MIDL___MIDL_itf_mvcellularv2_0000_0000_0004@@@Z`
- size: `563`
- prototype: `__int64 __fastcall(CMVCellularEmulator2 *this, const WCHAR *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x1800076a4`
- `0x180010120`
- `0x18001192c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800101ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010212`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010222`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010282`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010292`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800102a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800102ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800102fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001030a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001031e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001032e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001033e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800101ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010212`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010222`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010282`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010292`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800102a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800102ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800102fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001030a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001031e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001032e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001033e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800102bb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800102bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001017f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800101e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010253`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001017f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800101e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010253`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CMVCellularEmulator2::DeleteOperatorProfileSelection(CMVCellularEmulator2 *this, const WCHAR *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  int phkResult; // [rsp+20h] [rbp-18h]
  unsigned int phkResulta; // [rsp+20h] [rbp-18h]
  unsigned int phkResultb; // [rsp+20h] [rbp-18h]
  unsigned int phkResultc; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  HKEY v18; // [rsp+50h] [rbp+18h] BYREF
  HKEY v19; // [rsp+58h] [rbp+20h] BYREF

  if ( *((_QWORD *)this + 2) )
  {
    hKey = 0;
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, gc_wszRegCellularEmulator, 0, 2u, &hKey);
    if ( v4 )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x180,
             (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
             (const char *)v4,
             phkResulta);
      if ( hKey )
        RegCloseKey(hKey);
      return v5;
    }
    else
    {
      v18 = 0;
      v6 = RegOpenKeyExW(hKey, L"Datastore", 0, 2u, &v18);
      if ( v6 )
      {
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x184,
               (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
               (const char *)v6,
               phkResultb);
        if ( v18 )
          RegCloseKey(v18);
        if ( hKey )
          RegCloseKey(hKey);
        return v7;
      }
      else
      {
        v19 = 0;
        v8 = RegOpenKeyExW(v18, a2, 0, 2u, &v19);
        if ( v8 )
        {
          v9 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x188,
                 (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
                 (const char *)v8,
                 phkResultc);
          if ( v19 )
            RegCloseKey(v19);
          if ( v18 )
            RegCloseKey(v18);
          if ( hKey )
            RegCloseKey(hKey);
          return v9;
        }
        else
        {
          v10 = RegDeleteValueW(v19, L"ProfileSelection");
          if ( v10 )
          {
            v11 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x18B,
                    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
                    (const char *)v10,
                    phkResultc);
            if ( v19 )
              RegCloseKey(v19);
            if ( v18 )
              RegCloseKey(v18);
            if ( hKey )
              RegCloseKey(hKey);
            return v11;
          }
          else
          {
            if ( v19 )
              RegCloseKey(v19);
            if ( v18 )
              RegCloseKey(v18);
            if ( hKey )
              RegCloseKey(hKey);
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
      (void *)0x17B,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
      (const char *)0x8007139FLL,
      phkResult);
    return 2147947423LL;
  }
}

```

## disassembly

```asm
0x180010120  push    rbx
0x180010122  sub     rsp, 30h
0x180010126  mov     rbx, rdx
0x180010129  cmp     qword ptr [rcx+10h], 0
0x18001012e  jnz     short loc_180010155
0x180010130  mov     rcx, [rsp+38h]; this
0x180010135  mov     ebx, 8007139Fh
0x18001013a  mov     r9d, ebx; char *
0x18001013d  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180010144  mov     edx, 17Bh; void *
0x180010149  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001014e  mov     eax, ebx
0x180010150  jmp     loc_18001034C
0x180010155  mov     [rsp+38h+hKey], 0
0x18001015e  lea     rax, [rsp+38h+hKey]
0x180010163  mov     qword ptr [rsp+38h+phkResult], rax; unsigned int
0x180010168  mov     r9d, 2; samDesired
0x18001016e  xor     r8d, r8d; ulOptions
0x180010171  mov     rdx, cs:?gc_wszRegCellularEmulator@@3PEBGEB; lpSubKey
0x180010178  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001017f  call    cs:__imp_RegOpenKeyExW
0x180010185  test    eax, eax
0x180010187  jz      short loc_1800101BB
0x180010189  mov     rcx, [rsp+38h]; this
0x18001018e  mov     r9d, eax; char *
0x180010191  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180010198  mov     edx, 180h; void *
0x18001019d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800101a2  mov     ebx, eax
0x1800101a4  mov     rcx, [rsp+38h+hKey]; hKey
0x1800101a9  test    rcx, rcx
0x1800101ac  jz      short loc_1800101B4
0x1800101ae  call    cs:__imp_RegCloseKey
0x1800101b4  mov     eax, ebx
0x1800101b6  jmp     loc_18001034C
0x1800101bb  mov     [rsp+38h+arg_10], 0
0x1800101c4  lea     rax, [rsp+38h+arg_10]
0x1800101c9  mov     qword ptr [rsp+38h+phkResult], rax; unsigned int
0x1800101ce  mov     r9d, 2; samDesired
0x1800101d4  xor     r8d, r8d; ulOptions
0x1800101d7  lea     rdx, ?c_datastoreKeyName@@3QBGB; "Datastore"
0x1800101de  mov     rcx, [rsp+38h+hKey]; hKey
0x1800101e3  call    cs:__imp_RegOpenKeyExW
0x1800101e9  test    eax, eax
0x1800101eb  jz      short loc_18001022F
0x1800101ed  mov     rcx, [rsp+38h]; this
0x1800101f2  mov     r9d, eax; char *
0x1800101f5  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800101fc  mov     edx, 184h; void *
0x180010201  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010206  mov     ebx, eax
0x180010208  mov     rcx, [rsp+38h+arg_10]; hKey
0x18001020d  test    rcx, rcx
0x180010210  jz      short loc_180010218
0x180010212  call    cs:__imp_RegCloseKey
0x180010218  mov     rcx, [rsp+38h+hKey]; hKey
0x18001021d  test    rcx, rcx
0x180010220  jz      short loc_180010228
0x180010222  call    cs:__imp_RegCloseKey
0x180010228  mov     eax, ebx
0x18001022a  jmp     loc_18001034C
0x18001022f  mov     [rsp+38h+arg_18], 0
0x180010238  lea     rax, [rsp+38h+arg_18]
0x18001023d  mov     qword ptr [rsp+38h+phkResult], rax; unsigned int
0x180010242  mov     r9d, 2; samDesired
0x180010248  xor     r8d, r8d; ulOptions
0x18001024b  mov     rdx, rbx; lpSubKey
0x18001024e  mov     rcx, [rsp+38h+arg_10]; hKey
0x180010253  call    cs:__imp_RegOpenKeyExW
0x180010259  test    eax, eax
0x18001025b  jz      short loc_1800102AF
0x18001025d  mov     rcx, [rsp+38h]; this
0x180010262  mov     r9d, eax; char *
0x180010265  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001026c  mov     edx, 188h; void *
0x180010271  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010276  mov     ebx, eax
0x180010278  mov     rcx, [rsp+38h+arg_18]; hKey
0x18001027d  test    rcx, rcx
0x180010280  jz      short loc_180010288
0x180010282  call    cs:__imp_RegCloseKey
0x180010288  mov     rcx, [rsp+38h+arg_10]; hKey
0x18001028d  test    rcx, rcx
0x180010290  jz      short loc_180010298
0x180010292  call    cs:__imp_RegCloseKey
0x180010298  mov     rcx, [rsp+38h+hKey]; hKey
0x18001029d  test    rcx, rcx
0x1800102a0  jz      short loc_1800102A8
0x1800102a2  call    cs:__imp_RegCloseKey
0x1800102a8  mov     eax, ebx
0x1800102aa  jmp     loc_18001034C
0x1800102af  lea     rdx, ?gc_wszProfileSelection@@3QBGB; "ProfileSelection"
0x1800102b6  mov     rcx, [rsp+38h+arg_18]; hKey
0x1800102bb  call    cs:__imp_RegDeleteValueW
0x1800102c1  test    eax, eax
0x1800102c3  jz      short loc_180010314
0x1800102c5  mov     rcx, [rsp+38h]; this
0x1800102ca  mov     r9d, eax; char *
0x1800102cd  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800102d4  mov     edx, 18Bh; void *
0x1800102d9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800102de  mov     ebx, eax
0x1800102e0  mov     rcx, [rsp+38h+arg_18]; hKey
0x1800102e5  test    rcx, rcx
0x1800102e8  jz      short loc_1800102F0
0x1800102ea  call    cs:__imp_RegCloseKey
0x1800102f0  mov     rcx, [rsp+38h+arg_10]; hKey
0x1800102f5  test    rcx, rcx
0x1800102f8  jz      short loc_180010300
0x1800102fa  call    cs:__imp_RegCloseKey
0x180010300  mov     rcx, [rsp+38h+hKey]; hKey
0x180010305  test    rcx, rcx
0x180010308  jz      short loc_180010310
0x18001030a  call    cs:__imp_RegCloseKey
0x180010310  mov     eax, ebx
0x180010312  jmp     short loc_18001034C
0x180010314  mov     rcx, [rsp+38h+arg_18]; hKey
0x180010319  test    rcx, rcx
0x18001031c  jz      short loc_180010324
0x18001031e  call    cs:__imp_RegCloseKey
0x180010324  mov     rcx, [rsp+38h+arg_10]; hKey
0x180010329  test    rcx, rcx
0x18001032c  jz      short loc_180010334
0x18001032e  call    cs:__imp_RegCloseKey
0x180010334  mov     rcx, [rsp+38h+hKey]; hKey
0x180010339  test    rcx, rcx
0x18001033c  jz      short loc_180010344
0x18001033e  call    cs:__imp_RegCloseKey
0x180010344  xor     eax, eax
0x180010346  jmp     short loc_18001034C
0x180010348  mov     eax, dword ptr [rsp+38h+hKey]
0x18001034c  add     rsp, 30h
0x180010350  pop     rbx
0x180010351  retn
```
