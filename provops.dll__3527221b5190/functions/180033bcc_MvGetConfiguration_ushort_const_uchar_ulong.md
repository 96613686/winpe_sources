# MvGetConfiguration(ushort const *,uchar *,ulong *)

- ea: `0x180033bcc`
- end: `0x180033d23`
- name: `?MvGetConfiguration@@YAJPEBGPEAEPEAK@Z`
- size: `343`
- prototype: `int __fastcall(const unsigned __int16 *, unsigned __int8 *pvData, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f8d0`
- `0x180010b40`

## callees

- `0x180017914`
- `0x180033b88`
- `0x180033bcc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033c28`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033c86`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033cc9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033c28`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033c86`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033cc9`

## string_xrefs

- `0x180033c9d`: `Software\Microsoft\Multivariant\InImageConfigurations`
- `0x180033c44`: `onecoreuap\admin\prov\multivariant\common\src\mvregistryutils.cpp`
- `0x180033cd4`: `onecoreuap\admin\prov\multivariant\common\src\mvregistryutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, gc_wszRegMultivariant, L"DatastoreRoot", 2u, 0, pvData, (LPDWORD)&pcbData);
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
               L"DatastoreRoot",
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
              L"DatastoreRoot",
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
        (const char *)L"DatastoreRoot");
    }
  }
  *a3 = (unsigned int)pcbData;
  return 0;
}

```

## disassembly

```asm
0x180033bcc  mov     r11, rsp
0x180033bcf  mov     [r11+10h], rbx
0x180033bd3  mov     [r11+18h], rsi
0x180033bd7  mov     [r11+8], rcx
0x180033bdb  push    rdi
0x180033bdc  push    r14
0x180033bde  push    r15
0x180033be0  sub     rsp, 40h
0x180033be4  mov     eax, [r8]
0x180033be7  lea     r14, ?gc_wszDatastoreRoot@@3QBGB; "DatastoreRoot"
0x180033bee  mov     dword ptr [rsp+58h+arg_0], eax
0x180033bf2  mov     rbx, r8
0x180033bf5  lea     rax, [r11+8]
0x180033bf9  mov     rdi, rdx
0x180033bfc  mov     [r11-28h], rax
0x180033c00  mov     esi, 2
0x180033c05  mov     [r11-30h], rdx
0x180033c09  mov     r15, 0FFFFFFFF80000002h
0x180033c10  mov     rdx, cs:?gc_wszRegMultivariant@@3PEBGEB; lpSubKey
0x180033c17  mov     r9d, esi; dwFlags
0x180033c1a  mov     r8, r14; lpValue
0x180033c1d  mov     qword ptr [r11-38h], 0
0x180033c25  mov     rcx, r15; hkey
0x180033c28  call    cs:__imp_RegGetValueW
0x180033c2e  test    eax, eax
0x180033c30  jz      loc_180033CFD
0x180033c36  cmp     eax, esi
0x180033c38  jz      short loc_180033C58
0x180033c3a  mov     edx, 227h; void *
0x180033c3f  mov     rcx, [rsp+58h]; this
0x180033c44  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180033c4b  mov     r9d, eax; char *
0x180033c4e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033c53  jmp     loc_180033D05
0x180033c58  mov     eax, [rbx]
0x180033c5a  lea     rdx, ?gc_wszRegMultivariantReadOnly@@3QBGB; "Software\\Microsoft\\Multivariant"
0x180033c61  mov     dword ptr [rsp+58h+arg_0], eax
0x180033c65  mov     r9d, esi; dwFlags
0x180033c68  lea     rax, [rsp+58h+arg_0]
0x180033c6d  mov     r8, r14; lpValue
0x180033c70  mov     [rsp+58h+pcbData], rax; pcbData
0x180033c75  mov     rcx, r15; hkey
0x180033c78  mov     [rsp+58h+pvData], rdi; pvData
0x180033c7d  mov     [rsp+58h+pdwType], 0; pdwType
0x180033c86  call    cs:__imp_RegGetValueW
0x180033c8c  test    eax, eax
0x180033c8e  jz      short loc_180033CFD
0x180033c90  cmp     eax, esi
0x180033c92  jz      short loc_180033C9B
0x180033c94  mov     edx, 23Ch
0x180033c99  jmp     short loc_180033C3F
0x180033c9b  mov     eax, [rbx]
0x180033c9d  lea     rdx, ?gc_wszRegInImageConfigurations@@3QBGB; "Software\\Microsoft\\Multivariant\\InIm"...
0x180033ca4  mov     dword ptr [rsp+58h+arg_0], eax
0x180033ca8  mov     r9d, esi; dwFlags
0x180033cab  lea     rax, [rsp+58h+arg_0]
0x180033cb0  mov     r8, r14; lpValue
0x180033cb3  mov     [rsp+58h+pcbData], rax; pcbData
0x180033cb8  mov     rcx, r15; hkey
0x180033cbb  mov     [rsp+58h+pvData], rdi; pvData
0x180033cc0  mov     [rsp+58h+pdwType], 0; pdwType
0x180033cc9  call    cs:__imp_RegGetValueW
0x180033ccf  mov     rcx, [rsp+58h]; this
0x180033cd4  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180033cdb  mov     r9d, esi; char *
0x180033cde  test    eax, eax
0x180033ce0  jnz     short loc_180033D19
0x180033ce2  lea     rax, aMissingRegValu; "Missing reg value %ws is found in backu"...
0x180033ce9  mov     [rsp+58h+pvData], r14; char *
0x180033cee  mov     edx, 24Eh; void *
0x180033cf3  mov     [rsp+58h+pdwType], rax; unsigned int
0x180033cf8  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180033cfd  mov     eax, dword ptr [rsp+58h+arg_0]
0x180033d01  mov     [rbx], eax
0x180033d03  xor     eax, eax
0x180033d05  mov     rbx, [rsp+58h+arg_8]
0x180033d0a  mov     rsi, [rsp+58h+arg_10]
0x180033d0f  add     rsp, 40h
0x180033d13  pop     r15
0x180033d15  pop     r14
0x180033d17  pop     rdi
0x180033d18  retn
0x180033d19  mov     edx, 258h
0x180033d1e  jmp     loc_180033C4E
```
