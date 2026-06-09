# CUmRdp::RpcStoreDefaultPrinter(ushort const *,ushort const *)

- ea: `0x140016e74`
- end: `0x14001701f`
- name: `?RpcStoreDefaultPrinter@CUmRdp@@QEAAIPEBG0@Z`
- size: `427`
- prototype: `unsigned int(CUmRdp *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017820`

## callees

- `0x140004b1c`
- `0x140005704`
- `0x140016e74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016f3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017007`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016f3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017007`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140016fee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140016fee`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140016ed3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140016f82`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140016ed3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140016f82`

## pseudocode

```c
__int64 __fastcall CUmRdp::RpcStoreDefaultPrinter(CUmRdp *this, const unsigned __int16 *a2, const BYTE *a3)
{
  unsigned int v4; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rdx
  __int64 v7; // rax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  if ( a3 && a2 )
  {
    v4 = RegCreateKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Terminal Server Client",
           0,
           0,
           0,
           0x20006u,
           0,
           &hKey,
           0);
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v6 = 20;
LABEL_8:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v6,
          WPP_e1878ade8ac733f4c5d20ac7d29e2f6b_Traceguids,
          CurrentThreadActivityIdPrefix,
          v4);
      }
    }
    else
    {
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      v4 = RegCreateKeyExW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Terminal Server Client\\DefaultPrinter",
             0,
             0,
             1u,
             0x20006u,
             0,
             &hKey,
             0);
      if ( v4 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v6 = 21;
          goto LABEL_8;
        }
      }
      else
      {
        v7 = -1;
        do
          ++v7;
        while ( *(_WORD *)&a3[2 * v7] );
        v4 = RegSetValueExW(hKey, L"DefaultPrinterStore", 0, 1u, a3, 2 * v7 + 2);
      }
    }
  }
  else
  {
    v4 = 87;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x140016e74  mov     r11, rsp
0x140016e77  mov     [r11+10h], rbx
0x140016e7b  mov     [r11+18h], rsi
0x140016e7f  mov     [r11+8], rcx
0x140016e83  push    rdi
0x140016e84  sub     rsp, 50h
0x140016e88  xor     esi, esi
0x140016e8a  mov     rdi, r8
0x140016e8d  mov     [r11+8], rsi
0x140016e91  test    r8, r8
0x140016e94  jz      loc_140016FF8
0x140016e9a  test    rdx, rdx
0x140016e9d  jz      loc_140016FF8
0x140016ea3  mov     [r11-18h], rsi
0x140016ea7  lea     rax, [r11+8]
0x140016eab  mov     [r11-20h], rax
0x140016eaf  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Terminal Server Cl"...
0x140016eb6  mov     [r11-28h], rsi
0x140016eba  xor     r9d, r9d; lpClass
0x140016ebd  mov     [rsp+58h+samDesired], 20006h; samDesired
0x140016ec5  xor     r8d, r8d; Reserved
0x140016ec8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140016ecf  mov     [rsp+58h+dwOptions], esi; dwOptions
0x140016ed3  call    cs:__imp_RegCreateKeyExW
0x140016ed9  mov     ebx, eax
0x140016edb  test    eax, eax
0x140016edd  jz      short loc_140016F35
0x140016edf  mov     rax, cs:WPP_GLOBAL_Control
0x140016ee6  lea     rcx, WPP_GLOBAL_Control
0x140016eed  cmp     rax, rcx
0x140016ef0  jz      loc_140016FFD
0x140016ef6  test    byte ptr [rax+1Ch], 1
0x140016efa  jz      loc_140016FFD
0x140016f00  cmp     byte ptr [rax+19h], 2
0x140016f04  jb      loc_140016FFD
0x140016f0a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140016f0f  lea     edx, [rsi+14h]
0x140016f12  mov     rcx, cs:WPP_GLOBAL_Control
0x140016f19  lea     r8, WPP_e1878ade8ac733f4c5d20ac7d29e2f6b_Traceguids
0x140016f20  mov     r9d, eax
0x140016f23  mov     [rsp+58h+dwOptions], ebx
0x140016f27  mov     rcx, [rcx+10h]
0x140016f2b  call    WPP_SF_Dd
0x140016f30  jmp     loc_140016FFD
0x140016f35  mov     rcx, [rsp+58h+hKey]; hKey
0x140016f3a  test    rcx, rcx
0x140016f3d  jz      short loc_140016F4A
0x140016f3f  call    cs:__imp_RegCloseKey
0x140016f45  mov     [rsp+58h+hKey], rsi
0x140016f4a  mov     [rsp+58h+lpdwDisposition], rsi; lpdwDisposition
0x140016f4f  lea     rax, [rsp+58h+hKey]
0x140016f54  mov     [rsp+58h+phkResult], rax; phkResult
0x140016f59  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Terminal Server Cl"...
0x140016f60  mov     [rsp+58h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x140016f65  xor     r9d, r9d; lpClass
0x140016f68  mov     [rsp+58h+samDesired], 20006h; samDesired
0x140016f70  xor     r8d, r8d; Reserved
0x140016f73  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140016f7a  mov     [rsp+58h+dwOptions], 1; dwOptions
0x140016f82  call    cs:__imp_RegCreateKeyExW
0x140016f88  mov     ebx, eax
0x140016f8a  test    eax, eax
0x140016f8c  jz      short loc_140016FBC
0x140016f8e  mov     rax, cs:WPP_GLOBAL_Control
0x140016f95  lea     rcx, WPP_GLOBAL_Control
0x140016f9c  cmp     rax, rcx
0x140016f9f  jz      short loc_140016FFD
0x140016fa1  test    byte ptr [rax+1Ch], 1
0x140016fa5  jz      short loc_140016FFD
0x140016fa7  cmp     byte ptr [rax+19h], 2
0x140016fab  jb      short loc_140016FFD
0x140016fad  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140016fb2  mov     edx, 15h
0x140016fb7  jmp     loc_140016F12
0x140016fbc  or      rax, 0FFFFFFFFFFFFFFFFh
0x140016fc0  inc     rax
0x140016fc3  cmp     [rdi+rax*2], si
0x140016fc7  jnz     short loc_140016FC0
0x140016fc9  mov     rcx, [rsp+58h+hKey]; hKey
0x140016fce  lea     eax, ds:2[rax*2]
0x140016fd5  mov     [rsp+58h+samDesired], eax; cbData
0x140016fd9  lea     rdx, aDefaultprinter; "DefaultPrinterStore"
0x140016fe0  mov     r9d, 1; dwType
0x140016fe6  mov     qword ptr [rsp+58h+dwOptions], rdi; lpData
0x140016feb  xor     r8d, r8d; Reserved
0x140016fee  call    cs:__imp_RegSetValueExW
0x140016ff4  mov     ebx, eax
0x140016ff6  jmp     short loc_140016FFD
0x140016ff8  mov     ebx, 57h ; 'W'
0x140016ffd  mov     rcx, [rsp+58h+hKey]; hKey
0x140017002  test    rcx, rcx
0x140017005  jz      short loc_14001700D
0x140017007  call    cs:__imp_RegCloseKey
0x14001700d  mov     rsi, [rsp+58h+arg_10]
0x140017012  mov     eax, ebx
0x140017014  mov     rbx, [rsp+58h+arg_8]
0x140017019  add     rsp, 50h
0x14001701d  pop     rdi
0x14001701e  retn
```
