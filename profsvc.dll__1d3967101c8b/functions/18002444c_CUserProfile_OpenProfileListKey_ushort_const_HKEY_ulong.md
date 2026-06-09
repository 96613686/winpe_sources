# CUserProfile::OpenProfileListKey(ushort const *,HKEY__ * *,ulong *)

- ea: `0x18002444c`
- end: `0x180024561`
- name: `?OpenProfileListKey@CUserProfile@@IEAAJPEBGPEAPEAUHKEY__@@PEAK@Z`
- size: `277`
- prototype: `int(CUserProfile *__hidden this, const unsigned __int16 *, HKEY *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ecc4`
- `0x18002b2a0`

## callees

- `0x18002444c`
- `0x18002e648`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024494`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024494`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800244e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800244e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024500`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024544`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024500`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024544`

## string_xrefs

- `0x180024524`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfile::OpenProfileListKey(
        CUserProfile *this,
        const unsigned __int16 *a2,
        HKEY *a3,
        unsigned int *a4)
{
  unsigned int v6; // eax
  LSTATUS ValueW; // eax
  bool v8; // sf
  HKEY v9; // rax
  HKEY v10; // rcx
  unsigned int v12; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  CUserProfile *pcbData; // [rsp+50h] [rbp+8h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  pcbData = this;
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  hkey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0xF003Fu, &hkey);
  if ( v6 == 2 )
    goto LABEL_16;
  if ( !v6 )
  {
    if ( !a4 )
      goto LABEL_9;
    LODWORD(pcbData) = 4;
    ValueW = RegGetValueW(hkey, 0, L"State", 0x10u, 0, a4, (LPDWORD)&pcbData);
    v8 = ValueW < 0;
    if ( ValueW > 0 )
      v8 = 1;
    if ( !v8 )
    {
LABEL_9:
      v9 = hkey;
      v10 = 0;
      hkey = 0;
      *a3 = v9;
LABEL_10:
      if ( v10 )
        RegCloseKey(v10);
      return 0;
    }
LABEL_16:
    v10 = hkey;
    goto LABEL_10;
  }
  v12 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0xB1F,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
          (const char *)v6,
          phkResult);
  if ( hkey )
    RegCloseKey(hkey);
  return v12;
}

```

## disassembly

```asm
0x18002444c  mov     [rsp+arg_8], rbx
0x180024451  mov     [rsp+arg_0], rcx
0x180024456  push    rdi
0x180024457  sub     rsp, 40h
0x18002445b  mov     qword ptr [r8], 0
0x180024462  mov     rbx, r9
0x180024465  mov     rdi, r8
0x180024468  test    r9, r9
0x18002446b  jnz     loc_18002454E
0x180024471  lea     rax, [rsp+48h+hkey]
0x180024476  mov     [rsp+48h+hkey], 0
0x18002447f  mov     r9d, 0F003Fh; samDesired
0x180024485  mov     [rsp+48h+phkResult], rax; unsigned int
0x18002448a  xor     r8d, r8d; ulOptions
0x18002448d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024494  call    cs:__imp_RegOpenKeyExW
0x18002449a  cmp     eax, 2
0x18002449d  jz      loc_18002455A
0x1800244a3  test    eax, eax
0x1800244a5  jnz     short loc_18002451F
0x1800244a7  test    rbx, rbx
0x1800244aa  jz      short loc_1800244EC
0x1800244ac  mov     rcx, [rsp+48h+hkey]; hkey
0x1800244b1  lea     rax, [rsp+48h+arg_0]
0x1800244b6  mov     [rsp+48h+pcbData], rax; pcbData
0x1800244bb  lea     r8, aState; "State"
0x1800244c2  mov     [rsp+48h+pvData], rbx; pvData
0x1800244c7  mov     r9d, 10h; dwFlags
0x1800244cd  xor     edx, edx; lpSubKey
0x1800244cf  mov     [rsp+48h+phkResult], 0; pdwType
0x1800244d8  mov     dword ptr [rsp+48h+arg_0], 4
0x1800244e0  call    cs:__imp_RegGetValueW
0x1800244e6  test    eax, eax
0x1800244e8  jg      short loc_180024513
0x1800244ea  js      short loc_18002455A
0x1800244ec  mov     rax, [rsp+48h+hkey]
0x1800244f1  xor     ecx, ecx; hKey
0x1800244f3  mov     [rsp+48h+hkey], rcx
0x1800244f8  mov     [rdi], rax
0x1800244fb  test    rcx, rcx
0x1800244fe  jz      short loc_180024506
0x180024500  call    cs:__imp_RegCloseKey
0x180024506  xor     eax, eax
0x180024508  mov     rbx, [rsp+48h+arg_8]
0x18002450d  add     rsp, 40h
0x180024511  pop     rdi
0x180024512  retn
0x180024513  movzx   eax, ax
0x180024516  or      eax, 80070000h
0x18002451b  test    eax, eax
0x18002451d  jmp     short loc_1800244EA
0x18002451f  mov     rcx, [rsp+48h]; this
0x180024524  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002452b  mov     r9d, eax; char *
0x18002452e  mov     edx, 0B1Fh; void *
0x180024533  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180024538  mov     rcx, [rsp+48h+hkey]; hKey
0x18002453d  mov     ebx, eax
0x18002453f  test    rcx, rcx
0x180024542  jz      short loc_18002454A
0x180024544  call    cs:__imp_RegCloseKey
0x18002454a  mov     eax, ebx
0x18002454c  jmp     short loc_180024508
0x18002454e  mov     dword ptr [r9], 0
0x180024555  jmp     loc_180024471
0x18002455a  mov     rcx, [rsp+48h+hkey]
0x18002455f  jmp     short loc_1800244FB
```
