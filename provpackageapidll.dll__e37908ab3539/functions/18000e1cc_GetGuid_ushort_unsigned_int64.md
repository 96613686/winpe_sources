# GetGuid(ushort *,unsigned __int64)

- ea: `0x18000e1cc`
- end: `0x18000e31f`
- name: `?GetGuid@@YAJPEAG_K@Z`
- size: `339`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009740`

## callees

- `0x180001510`
- `0x180006014`
- `0x18000e1cc`
- `0x18000eecc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000e202`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000e202`

## string_xrefs

- `0x18000e23b`: `    Failed to create GUID`

## pseudocode

```c
__int64 __fastcall GetGuid(unsigned __int16 *a1)
{
  HRESULT v2; // eax
  unsigned int v3; // edi
  int v5; // eax
  int v6; // [rsp+20h] [rbp-49h]
  int Data2; // [rsp+20h] [rbp-49h]
  __int64 v8; // [rsp+20h] [rbp-49h]
  HRESULT v9; // [rsp+28h] [rbp-41h]
  int Data3; // [rsp+28h] [rbp-41h]
  __int64 v11; // [rsp+28h] [rbp-41h]
  int v12; // [rsp+30h] [rbp-39h]
  int v13; // [rsp+38h] [rbp-31h]
  int v14; // [rsp+40h] [rbp-29h]
  int v15; // [rsp+48h] [rbp-21h]
  int v16; // [rsp+50h] [rbp-19h]
  int v17; // [rsp+58h] [rbp-11h]
  int v18; // [rsp+60h] [rbp-9h]
  int v19; // [rsp+68h] [rbp-1h]
  GUID pguid; // [rsp+70h] [rbp+7h] BYREF

  *a1 = 0;
  pguid = 0;
  v2 = CoCreateGuid(&pguid);
  v3 = v2;
  if ( v2 < 0 )
  {
    v9 = v2;
    v6 = 366;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "GetGuid",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
      v6,
      v9);
    ProvPackageLog(3, L"    Failed to create GUID");
    return v3;
  }
  v19 = pguid.Data4[7];
  v18 = pguid.Data4[6];
  v17 = pguid.Data4[5];
  v16 = pguid.Data4[4];
  v15 = pguid.Data4[3];
  v14 = pguid.Data4[2];
  v13 = pguid.Data4[1];
  v12 = pguid.Data4[0];
  Data3 = pguid.Data3;
  Data2 = pguid.Data2;
  v5 = StringCbPrintfW(
         a1,
         0x4Eu,
         L"{%08X-%04hX-%04hX-%02X%02X-%02X%02X%02X%02X%02X%02X}",
         pguid.Data1,
         Data2,
         Data3,
         v12,
         v13,
         v14,
         v15,
         v16,
         v17,
         v18,
         v19);
  v3 = v5;
  if ( v5 < 0 )
  {
    LODWORD(v11) = v5;
    LODWORD(v8) = 371;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "GetGuid",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
      v8,
      v11);
    ProvPackageLog(3, L"    Failed to convert GUID to string");
    return v3;
  }
  return 0;
}

```

## disassembly

```asm
0x18000e1cc  push    rbp
0x18000e1ce  push    rbx
0x18000e1cf  push    rsi
0x18000e1d0  push    rdi
0x18000e1d1  push    r14
0x18000e1d3  push    r15
0x18000e1d5  lea     rbp, [rsp-2Fh]
0x18000e1da  sub     rsp, 98h
0x18000e1e1  mov     rax, cs:__security_cookie
0x18000e1e8  xor     rax, rsp
0x18000e1eb  mov     [rbp+57h+var_40], rax
0x18000e1ef  xor     eax, eax
0x18000e1f1  mov     r15, rcx
0x18000e1f4  mov     [rcx], ax
0x18000e1f7  xorps   xmm0, xmm0
0x18000e1fa  lea     rcx, [rbp+57h+pguid]; pguid
0x18000e1fe  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x18000e202  call    cs:__imp_CoCreateGuid
0x18000e208  mov     edi, eax
0x18000e20a  test    eax, eax
0x18000e20c  jns     short loc_18000E250
0x18000e20e  mov     dword ptr [rsp+0C0h+var_98], eax
0x18000e212  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000e219  mov     ebx, 3
0x18000e21e  mov     dword ptr [rsp+0C0h+var_A0], 16Eh
0x18000e226  mov     ecx, ebx
0x18000e228  lea     r8, aGetguid; "GetGuid"
0x18000e22f  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000e236  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e23b  lea     rdx, aFailedToCreate_12; "    Failed to create GUID"
0x18000e242  mov     ecx, ebx
0x18000e244  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e249  mov     eax, edi
0x18000e24b  jmp     loc_18000E303
0x18000e250  movzx   edx, [rbp+57h+pguid.Data4+6]
0x18000e254  mov     rcx, r15; unsigned __int16 *
0x18000e257  movzx   r8d, [rbp+57h+pguid.Data4+5]
0x18000e25c  movzx   r9d, [rbp+57h+pguid.Data4+4]
0x18000e261  movzx   eax, [rbp+57h+pguid.Data4+7]
0x18000e265  movzx   r10d, [rbp+57h+pguid.Data4+3]
0x18000e26a  movzx   r11d, [rbp+57h+pguid.Data4+2]
0x18000e26f  movzx   ebx, [rbp+57h+pguid.Data4+1]
0x18000e273  movzx   edi, [rbp+57h+pguid.Data4]
0x18000e277  movzx   esi, [rbp+57h+pguid.Data3]
0x18000e27b  movzx   r14d, [rbp+57h+pguid.Data2]
0x18000e280  mov     [rsp+0C0h+var_58], eax
0x18000e284  mov     [rsp+0C0h+var_60], edx
0x18000e288  mov     edx, 4Eh ; 'N'; unsigned __int64
0x18000e28d  mov     [rsp+0C0h+var_68], r8d
0x18000e292  lea     r8, a08x04hx04hx02x; "{%08X-%04hX-%04hX-%02X%02X-%02X%02X%02X"...
0x18000e299  mov     [rsp+0C0h+var_70], r9d
0x18000e29e  mov     r9d, [rbp+57h+pguid.Data1]
0x18000e2a2  mov     [rsp+0C0h+var_78], r10d
0x18000e2a7  mov     [rsp+0C0h+var_80], r11d
0x18000e2ac  mov     [rsp+0C0h+var_88], ebx
0x18000e2b0  mov     [rsp+0C0h+var_90], edi
0x18000e2b4  mov     dword ptr [rsp+0C0h+var_98], esi
0x18000e2b8  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x18000e2bd  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e2c2  mov     edi, eax
0x18000e2c4  test    eax, eax
0x18000e2c6  jns     short loc_18000E301
0x18000e2c8  mov     dword ptr [rsp+0C0h+var_98], eax
0x18000e2cc  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000e2d3  mov     ebx, 3
0x18000e2d8  mov     dword ptr [rsp+0C0h+var_A0], 173h
0x18000e2e0  mov     ecx, ebx
0x18000e2e2  lea     r8, aGetguid; "GetGuid"
0x18000e2e9  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000e2f0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e2f5  lea     rdx, aFailedToConver_1; "    Failed to convert GUID to string"
0x18000e2fc  jmp     loc_18000E242
0x18000e301  xor     eax, eax
0x18000e303  mov     rcx, [rbp+57h+var_40]
0x18000e307  xor     rcx, rsp; StackCookie
0x18000e30a  call    __security_check_cookie
0x18000e30f  add     rsp, 98h
0x18000e316  pop     r15
0x18000e318  pop     r14
0x18000e31a  pop     rdi
0x18000e31b  pop     rsi
0x18000e31c  pop     rbx
0x18000e31d  pop     rbp
0x18000e31e  retn
```
