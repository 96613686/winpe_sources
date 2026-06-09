# MvGetConfiguration(ushort const *,uchar *,ulong *)

- ea: `0x18003755c`
- end: `0x1800376b3`
- name: `?MvGetConfiguration@@YAJPEBGPEAEPEAK@Z`
- size: `343`
- prototype: `int __fastcall(const unsigned __int16 *, unsigned __int8 *pvData, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180032d84`

## callees

- `0x18001192c`
- `0x180037518`
- `0x18003755c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800375b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180037616`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180037659`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800375b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180037616`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180037659`

## string_xrefs

- `0x180037577`: `CellularClsid`
- `0x18003762d`: `Software\Microsoft\Multivariant\InImageConfigurations`
- `0x1800375d4`: `onecoreuap\admin\prov\multivariant\common\src\mvregistryutils.cpp`
- `0x180037664`: `onecoreuap\admin\prov\multivariant\common\src\mvregistryutils.cpp`

## pseudocode

```c
int __fastcall MvGetConfiguration(const unsigned __int16 *a1, unsigned __int8 *pvData, unsigned int *a3)
{
  unsigned int ValueW; // eax
  __int64 v6; // rdx
  wil::details::in1diag3 *v7; // rcx
  __int64 v8; // r9
  LSTATUS v10; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  const unsigned __int16 *pcbData; // [rsp+60h] [rbp+8h] BYREF

  pcbData = a1;
  LODWORD(pcbData) = *a3;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, gc_wszRegMultivariant, L"CellularClsid", 2u, 0, pvData, (LPDWORD)&pcbData);
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      v6 = 551;
LABEL_4:
      v7 = retaddr;
      v8 = ValueW;
      return wil::details::in1diag3::Return_Win32(
               v7,
               (void *)v6,
               (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvregistryutils.cpp",
               (const char *)v8,
               pdwType);
    }
    LODWORD(pcbData) = *a3;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Multivariant",
               L"CellularClsid",
               2u,
               0,
               pvData,
               (LPDWORD)&pcbData);
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        v6 = 572;
        goto LABEL_4;
      }
      LODWORD(pcbData) = *a3;
      v10 = RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Multivariant\\InImageConfigurations",
              L"CellularClsid",
              2u,
              0,
              pvData,
              (LPDWORD)&pcbData);
      v7 = retaddr;
      v8 = 2;
      if ( v10 )
      {
        v6 = 600;
        return wil::details::in1diag3::Return_Win32(
                 v7,
                 (void *)v6,
                 (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvregistryutils.cpp",
                 (const char *)v8,
                 pdwType);
      }
      wil::details::in1diag3::Log_Win32Msg(
        retaddr,
        (void *)0x24E,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvregistryutils.cpp",
        (const char *)2,
        (unsigned int)"Missing reg value %ws is found in backup.",
        (const char *)L"CellularClsid");
    }
  }
  *a3 = (unsigned int)pcbData;
  return 0;
}

```

## disassembly

```asm
0x18003755c  mov     r11, rsp
0x18003755f  mov     [r11+10h], rbx
0x180037563  mov     [r11+18h], rsi
0x180037567  mov     [r11+8], rcx
0x18003756b  push    rdi
0x18003756c  push    r14
0x18003756e  push    r15
0x180037570  sub     rsp, 40h
0x180037574  mov     eax, [r8]
0x180037577  lea     r14, ?gc_wszCellularClsid@@3QBGB; "CellularClsid"
0x18003757e  mov     dword ptr [rsp+58h+arg_0], eax
0x180037582  mov     rbx, r8
0x180037585  lea     rax, [r11+8]
0x180037589  mov     rdi, rdx
0x18003758c  mov     [r11-28h], rax
0x180037590  mov     esi, 2
0x180037595  mov     [r11-30h], rdx
0x180037599  mov     r15, 0FFFFFFFF80000002h
0x1800375a0  mov     rdx, cs:?gc_wszRegMultivariant@@3PEBGEB; lpSubKey
0x1800375a7  mov     r9d, esi; dwFlags
0x1800375aa  mov     r8, r14; lpValue
0x1800375ad  mov     qword ptr [r11-38h], 0
0x1800375b5  mov     rcx, r15; hkey
0x1800375b8  call    cs:__imp_RegGetValueW
0x1800375be  test    eax, eax
0x1800375c0  jz      loc_18003768D
0x1800375c6  cmp     eax, esi
0x1800375c8  jz      short loc_1800375E8
0x1800375ca  mov     edx, 227h; void *
0x1800375cf  mov     rcx, [rsp+58h]; this
0x1800375d4  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800375db  mov     r9d, eax; char *
0x1800375de  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800375e3  jmp     loc_180037695
0x1800375e8  mov     eax, [rbx]
0x1800375ea  lea     rdx, ?gc_wszRegMultivariantReadOnly@@3QBGB; "Software\\Microsoft\\Multivariant"
0x1800375f1  mov     dword ptr [rsp+58h+arg_0], eax
0x1800375f5  mov     r9d, esi; dwFlags
0x1800375f8  lea     rax, [rsp+58h+arg_0]
0x1800375fd  mov     r8, r14; lpValue
0x180037600  mov     [rsp+58h+pcbData], rax; pcbData
0x180037605  mov     rcx, r15; hkey
0x180037608  mov     [rsp+58h+pvData], rdi; pvData
0x18003760d  mov     [rsp+58h+pdwType], 0; pdwType
0x180037616  call    cs:__imp_RegGetValueW
0x18003761c  test    eax, eax
0x18003761e  jz      short loc_18003768D
0x180037620  cmp     eax, esi
0x180037622  jz      short loc_18003762B
0x180037624  mov     edx, 23Ch
0x180037629  jmp     short loc_1800375CF
0x18003762b  mov     eax, [rbx]
0x18003762d  lea     rdx, ?gc_wszRegInImageConfigurations@@3QBGB; "Software\\Microsoft\\Multivariant\\InIm"...
0x180037634  mov     dword ptr [rsp+58h+arg_0], eax
0x180037638  mov     r9d, esi; dwFlags
0x18003763b  lea     rax, [rsp+58h+arg_0]
0x180037640  mov     r8, r14; lpValue
0x180037643  mov     [rsp+58h+pcbData], rax; pcbData
0x180037648  mov     rcx, r15; hkey
0x18003764b  mov     [rsp+58h+pvData], rdi; pvData
0x180037650  mov     [rsp+58h+pdwType], 0; pdwType
0x180037659  call    cs:__imp_RegGetValueW
0x18003765f  mov     rcx, [rsp+58h]; this
0x180037664  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18003766b  mov     r9d, esi; char *
0x18003766e  test    eax, eax
0x180037670  jnz     short loc_1800376A9
0x180037672  lea     rax, aMissingRegValu; "Missing reg value %ws is found in backu"...
0x180037679  mov     [rsp+58h+pvData], r14; char *
0x18003767e  mov     edx, 24Eh; void *
0x180037683  mov     [rsp+58h+pdwType], rax; unsigned int
0x180037688  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18003768d  mov     eax, dword ptr [rsp+58h+arg_0]
0x180037691  mov     [rbx], eax
0x180037693  xor     eax, eax
0x180037695  mov     rbx, [rsp+58h+arg_8]
0x18003769a  mov     rsi, [rsp+58h+arg_10]
0x18003769f  add     rsp, 40h
0x1800376a3  pop     r15
0x1800376a5  pop     r14
0x1800376a7  pop     rdi
0x1800376a8  retn
0x1800376a9  mov     edx, 258h
0x1800376ae  jmp     loc_1800375DE
```
