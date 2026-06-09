# MvGetConfiguration(ushort const *,uchar *,ulong *)

- ea: `0x180033630`
- end: `0x18003377d`
- name: `?MvGetConfiguration@@YAJPEBGPEAEPEAK@Z`
- size: `333`
- prototype: `__int64 __fastcall(char *, PVOID pvData, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013f30`
- `0x18002db60`
- `0x18002e904`

## callees

- `0x180009900`
- `0x1800335ec`
- `0x180033630`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033683`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800336e1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033724`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033683`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800336e1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033724`

## string_xrefs

- `0x1800336f8`: `Software\Microsoft\Multivariant\InImageConfigurations`
- `0x18003369f`: `onecoreuap\admin\prov\multivariant\common\src\mvregistryutils.cpp`
- `0x18003372f`: `onecoreuap\admin\prov\multivariant\common\src\mvregistryutils.cpp`

## pseudocode

```c
int __fastcall MvGetConfiguration(const WCHAR *a1, PVOID pvData, unsigned int *a3)
{
  unsigned int ValueW; // eax
  __int64 v7; // rdx
  wil::details::in1diag3 *v8; // rcx
  __int64 v9; // r9
  LSTATUS v11; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD pcbData; // [rsp+70h] [rbp+18h] BYREF

  pcbData = *a3;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, gc_wszRegMultivariant, a1, 2u, 0, pvData, &pcbData);
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      v7 = 551;
LABEL_4:
      v8 = retaddr;
      v9 = ValueW;
      return wil::details::in1diag3::Return_Win32(
               v8,
               (void *)v7,
               (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvregistryutils.cpp",
               (const char *)v9,
               pdwType);
    }
    pcbData = *a3;
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Multivariant", a1, 2u, 0, pvData, &pcbData);
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        v7 = 572;
        goto LABEL_4;
      }
      pcbData = *a3;
      v11 = RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Multivariant\\InImageConfigurations",
              a1,
              2u,
              0,
              pvData,
              &pcbData);
      v8 = retaddr;
      v9 = 2;
      if ( v11 )
      {
        v7 = 600;
        return wil::details::in1diag3::Return_Win32(
                 v8,
                 (void *)v7,
                 (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvregistryutils.cpp",
                 (const char *)v9,
                 pdwType);
      }
      wil::details::in1diag3::Log_Win32Msg(
        retaddr,
        (void *)0x24E,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvregistryutils.cpp",
        (const char *)2,
        (unsigned int)"Missing reg value %ws is found in backup.",
        (const char *)a1);
    }
  }
  *a3 = pcbData;
  return 0;
}

```

## disassembly

```asm
0x180033630  mov     r11, rsp
0x180033633  mov     [r11+8], rbx
0x180033637  mov     [r11+10h], rbp
0x18003363b  push    rsi
0x18003363c  push    rdi
0x18003363d  push    r15
0x18003363f  sub     rsp, 40h
0x180033643  mov     eax, [r8]
0x180033646  mov     rbx, r8
0x180033649  mov     [rsp+58h+arg_10], eax
0x18003364d  mov     rsi, rdx
0x180033650  lea     rax, [r11+18h]
0x180033654  mov     rdi, rcx
0x180033657  mov     [r11-28h], rax
0x18003365b  mov     r8, rcx; lpValue
0x18003365e  mov     [r11-30h], rdx
0x180033662  mov     ebp, 2
0x180033667  mov     rdx, cs:?gc_wszRegMultivariant@@3PEBGEB; lpSubKey
0x18003366e  mov     r15, 0FFFFFFFF80000002h
0x180033675  mov     r9d, ebp; dwFlags
0x180033678  mov     qword ptr [r11-38h], 0
0x180033680  mov     rcx, r15; hkey
0x180033683  call    cs:__imp_RegGetValueW
0x180033689  test    eax, eax
0x18003368b  jz      loc_180033758
0x180033691  cmp     eax, ebp
0x180033693  jz      short loc_1800336B3
0x180033695  mov     edx, 227h; void *
0x18003369a  mov     rcx, [rsp+58h]; this
0x18003369f  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800336a6  mov     r9d, eax; char *
0x1800336a9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800336ae  jmp     loc_180033760
0x1800336b3  mov     eax, [rbx]
0x1800336b5  lea     rdx, ?gc_wszRegMultivariantReadOnly@@3QBGB; "Software\\Microsoft\\Multivariant"
0x1800336bc  mov     [rsp+58h+arg_10], eax
0x1800336c0  mov     r9d, ebp; dwFlags
0x1800336c3  lea     rax, [rsp+58h+arg_10]
0x1800336c8  mov     r8, rdi; lpValue
0x1800336cb  mov     [rsp+58h+pcbData], rax; pcbData
0x1800336d0  mov     rcx, r15; hkey
0x1800336d3  mov     [rsp+58h+pvData], rsi; pvData
0x1800336d8  mov     [rsp+58h+pdwType], 0; pdwType
0x1800336e1  call    cs:__imp_RegGetValueW
0x1800336e7  test    eax, eax
0x1800336e9  jz      short loc_180033758
0x1800336eb  cmp     eax, ebp
0x1800336ed  jz      short loc_1800336F6
0x1800336ef  mov     edx, 23Ch
0x1800336f4  jmp     short loc_18003369A
0x1800336f6  mov     eax, [rbx]
0x1800336f8  lea     rdx, ?gc_wszRegInImageConfigurations@@3QBGB; "Software\\Microsoft\\Multivariant\\InIm"...
0x1800336ff  mov     [rsp+58h+arg_10], eax
0x180033703  mov     r9d, ebp; dwFlags
0x180033706  lea     rax, [rsp+58h+arg_10]
0x18003370b  mov     r8, rdi; lpValue
0x18003370e  mov     [rsp+58h+pcbData], rax; pcbData
0x180033713  mov     rcx, r15; hkey
0x180033716  mov     [rsp+58h+pvData], rsi; pvData
0x18003371b  mov     [rsp+58h+pdwType], 0; pdwType
0x180033724  call    cs:__imp_RegGetValueW
0x18003372a  mov     rcx, [rsp+58h]; this
0x18003372f  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180033736  mov     r9d, ebp; char *
0x180033739  test    eax, eax
0x18003373b  jnz     short loc_180033773
0x18003373d  lea     rax, aMissingRegValu; "Missing reg value %ws is found in backu"...
0x180033744  mov     [rsp+58h+pvData], rdi; char *
0x180033749  mov     edx, 24Eh; void *
0x18003374e  mov     [rsp+58h+pdwType], rax; unsigned int
0x180033753  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180033758  mov     eax, [rsp+58h+arg_10]
0x18003375c  mov     [rbx], eax
0x18003375e  xor     eax, eax
0x180033760  mov     rbx, [rsp+58h+arg_0]
0x180033765  mov     rbp, [rsp+58h+arg_8]
0x18003376a  add     rsp, 40h
0x18003376e  pop     r15
0x180033770  pop     rdi
0x180033771  pop     rsi
0x180033772  retn
0x180033773  mov     edx, 258h
0x180033778  jmp     loc_1800336A9
```
