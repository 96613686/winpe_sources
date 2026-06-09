# CMVCellularEmulator::GetValue(ushort const *,ulong *,uchar *,ulong const *)

- ea: `0x180010690`
- end: `0x180010814`
- name: `?GetValue@CMVCellularEmulator@@UEAAJPEBGPEAKPEAEPEBK@Z`
- size: `388`
- prototype: `__int64 __fastcall(CMVCellularEmulator *this, const unsigned __int16 *, unsigned int *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800076a4`
- `0x180010690`
- `0x18001192c`
- `0x180011c08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010731`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001078b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800107e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800107f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010731`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001078b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800107e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800107f7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800107cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800107cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010704`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001075e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010704`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001075e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMVCellularEmulator::GetValue(
        CMVCellularEmulator *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  unsigned int v8; // ebx
  unsigned int v10; // eax
  unsigned int ValueW; // eax
  __int64 v12; // rdx
  const struct Uicc *v13; // rax
  int phkResult; // [rsp+20h] [rbp-30h]
  unsigned int phkResulta; // [rsp+20h] [rbp-30h]
  unsigned int phkResultb; // [rsp+20h] [rbp-30h]
  HKEY hkey; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HKEY hKey; // [rsp+70h] [rbp+20h] BYREF

  if ( !*((_QWORD *)this + 2) )
  {
    v8 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
      (const char *)0x8007139FLL,
      phkResult);
    return v8;
  }
  hKey = 0;
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, gc_wszRegCellularEmulator, 0, 0x20019u, &hKey);
  if ( v10 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x114,
           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
           (const char *)v10,
           phkResulta);
LABEL_6:
    if ( hKey )
      RegCloseKey(hKey);
    return v8;
  }
  hkey = 0;
  ValueW = RegOpenKeyExW(hKey, L"Datastore", 0, 0x20019u, &hkey);
  if ( ValueW )
  {
    v12 = 280;
    goto LABEL_10;
  }
  v13 = CellState::SelectUicc(*((CellState **)this + 2), (CMVCellularEmulator *)((char *)this + 24));
  if ( *((_QWORD *)v13 + 3) >= 8u )
    v13 = *(const struct Uicc **)v13;
  ValueW = RegGetValueW(hkey, (LPCWSTR)v13, a2, 8u, 0, a4, a3);
  if ( ValueW )
  {
    v12 = 285;
LABEL_10:
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v12,
           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
           (const char *)ValueW,
           phkResultb);
    if ( hkey )
      RegCloseKey(hkey);
    goto LABEL_6;
  }
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180010690  mov     [rsp-18h+arg_8], rbx
0x180010695  mov     [rsp-18h+arg_10], rsi
0x18001069a  push    rbp
0x18001069b  push    rdi
0x18001069c  push    r14
0x18001069e  mov     rbp, rsp
0x1800106a1  sub     rsp, 50h
0x1800106a5  mov     rdi, r9
0x1800106a8  mov     rsi, r8
0x1800106ab  mov     r14, rdx
0x1800106ae  mov     rbx, rcx
0x1800106b1  cmp     qword ptr [rcx+10h], 0
0x1800106b6  jnz     short loc_1800106DC
0x1800106b8  mov     rcx, [rbp+18h]; this
0x1800106bc  mov     ebx, 8007139Fh
0x1800106c1  mov     r9d, ebx; char *
0x1800106c4  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800106cb  mov     edx, 10Fh; void *
0x1800106d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800106d5  mov     eax, ebx
0x1800106d7  jmp     loc_1800107FF
0x1800106dc  mov     [rbp+hKey], 0
0x1800106e4  lea     rax, [rbp+hKey]
0x1800106e8  mov     [rsp+50h+phkResult], rax; unsigned int
0x1800106ed  mov     r9d, 20019h; samDesired
0x1800106f3  xor     r8d, r8d; ulOptions
0x1800106f6  mov     rdx, cs:?gc_wszRegCellularEmulator@@3PEBGEB; lpSubKey
0x1800106fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010704  call    cs:__imp_RegOpenKeyExW
0x18001070a  test    eax, eax
0x18001070c  jz      short loc_180010739
0x18001070e  mov     rcx, [rbp+18h]; this
0x180010712  mov     r9d, eax; char *
0x180010715  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001071c  mov     edx, 114h; void *
0x180010721  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010726  mov     ebx, eax
0x180010728  mov     rcx, [rbp+hKey]; hKey
0x18001072c  test    rcx, rcx
0x18001072f  jz      short loc_1800106D5
0x180010731  call    cs:__imp_RegCloseKey
0x180010737  jmp     short loc_1800106D5
0x180010739  mov     [rbp+hkey], 0
0x180010741  lea     rax, [rbp+hkey]
0x180010745  mov     [rsp+50h+phkResult], rax; unsigned int
0x18001074a  mov     r9d, 20019h; samDesired
0x180010750  xor     r8d, r8d; ulOptions
0x180010753  lea     rdx, ?c_datastoreKeyName@@3QBGB; "Datastore"
0x18001075a  mov     rcx, [rbp+hKey]; hKey
0x18001075e  call    cs:__imp_RegOpenKeyExW
0x180010764  test    eax, eax
0x180010766  jz      short loc_180010793
0x180010768  mov     edx, 118h; void *
0x18001076d  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180010774  mov     r9d, eax; char *
0x180010777  mov     rcx, [rbp+18h]; this
0x18001077b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010780  mov     ebx, eax
0x180010782  mov     rcx, [rbp+hkey]; hKey
0x180010786  test    rcx, rcx
0x180010789  jz      short loc_180010728
0x18001078b  call    cs:__imp_RegCloseKey
0x180010791  jmp     short loc_180010728
0x180010793  lea     rdx, [rbx+18h]; struct __MIDL___MIDL_itf_mvcellular_0000_0000_0002 *
0x180010797  mov     rcx, [rbx+10h]; this
0x18001079b  call    ?SelectUicc@CellState@@QEAAAEBUUicc@@AEBU__MIDL___MIDL_itf_mvcellular_0000_0000_0002@@@Z; CellState::SelectUicc(__MIDL___MIDL_itf_mvcellular_0000_0000_0002 const &)
0x1800107a0  cmp     qword ptr [rax+18h], 8
0x1800107a5  jb      short loc_1800107AA
0x1800107a7  mov     rax, [rax]
0x1800107aa  mov     [rsp+50h+pcbData], rsi; pcbData
0x1800107af  mov     [rsp+50h+pvData], rdi; pvData
0x1800107b4  mov     [rsp+50h+phkResult], 0; pdwType
0x1800107bd  mov     r9d, 8; dwFlags
0x1800107c3  mov     r8, r14; lpValue
0x1800107c6  mov     rdx, rax; lpSubKey
0x1800107c9  mov     rcx, [rbp+hkey]; hkey
0x1800107cd  call    cs:__imp_RegGetValueW
0x1800107d3  test    eax, eax
0x1800107d5  jz      short loc_1800107DE
0x1800107d7  mov     edx, 11Dh
0x1800107dc  jmp     short loc_18001076D
0x1800107de  mov     rcx, [rbp+hkey]; hKey
0x1800107e2  test    rcx, rcx
0x1800107e5  jz      short loc_1800107EE
0x1800107e7  call    cs:__imp_RegCloseKey
0x1800107ed  nop
0x1800107ee  mov     rcx, [rbp+hKey]; hKey
0x1800107f2  test    rcx, rcx
0x1800107f5  jz      short loc_1800107FD
0x1800107f7  call    cs:__imp_RegCloseKey
0x1800107fd  xor     eax, eax
0x1800107ff  lea     r11, [rsp+50h+var_s0]
0x180010804  mov     rbx, [r11+28h]
0x180010808  mov     rsi, [r11+30h]
0x18001080c  mov     rsp, r11
0x18001080f  pop     r14
0x180010811  pop     rdi
0x180010812  pop     rbp
0x180010813  retn
```
