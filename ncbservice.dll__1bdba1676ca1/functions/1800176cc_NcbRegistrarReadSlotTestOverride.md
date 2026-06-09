# NcbRegistrarReadSlotTestOverride

- ea: `0x1800176cc`
- end: `0x1800177fe`
- name: `NcbRegistrarReadSlotTestOverride`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015dc0`

## callees

- `0x18000a0a0`
- `0x180016d98`
- `0x1800176cc`
- `0x18001c500`
- `0x18001d09c`
- `0x180020350`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017744`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017744`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017781`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017781`

## pseudocode

```c
unsigned int NcbRegistrarReadSlotTestOverride()
{
  const WCHAR *v0; // rdx
  unsigned int result; // eax
  __int64 v2; // r9
  unsigned int Integer2; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
  }
  v0 = (const WCHAR *)&lpSubKey;
  hKey = 0;
  if ( *((_QWORD *)&xmmword_18004D9D0 + 1) > 7u )
    v0 = lpSubKey;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v0, 0, 0x20019u, &hKey);
  if ( !result )
  {
    Integer2 = GetInteger2(hKey, L"ReservedSlotTestOverride", 0);
    v6 = Integer2;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v5, v4, L"NcbReg: Test override value", Integer2);
    result = RegCloseKey(hKey);
    goto LABEL_15;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  v6 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    result = WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, result);
LABEL_15:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  g_NcbRegistrarSlotTestOverride = v6 != 0;
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 6u )
  {
    LOBYTE(v2) = v6 != 0;
    return WPP_SF_c(v7[2], 14, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v2);
  }
  return result;
}

```

## disassembly

```asm
0x1800176cc  mov     [rsp+arg_8], rbx
0x1800176d1  push    rsi
0x1800176d2  sub     rsp, 30h
0x1800176d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800176dd  lea     rsi, WPP_GLOBAL_Control
0x1800176e4  cmp     rcx, rsi
0x1800176e7  jz      short loc_18001770A
0x1800176e9  test    byte ptr [rcx+1Ch], 1
0x1800176ed  jz      short loc_18001770A
0x1800176ef  cmp     byte ptr [rcx+19h], 6
0x1800176f3  jb      short loc_18001770A
0x1800176f5  mov     rcx, [rcx+10h]
0x1800176f9  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x180017700  mov     edx, 0Ch
0x180017705  call    WPP_SF_
0x18001770a  cmp     qword ptr cs:xmmword_18004D9D0+8, 7
0x180017712  lea     rax, [rsp+38h+hKey]
0x180017717  lea     rdx, lpSubKey
0x18001771e  mov     [rsp+38h+hKey], 0
0x180017727  cmova   rdx, qword ptr cs:lpSubKey; lpSubKey
0x18001772f  mov     r9d, 20019h; samDesired
0x180017735  xor     r8d, r8d; ulOptions
0x180017738  mov     [rsp+38h+phkResult], rax; phkResult
0x18001773d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017744  call    cs:__imp_RegOpenKeyExW
0x18001774a  test    eax, eax
0x18001774c  jnz     short loc_180017789
0x18001774e  mov     rcx, [rsp+38h+hKey]
0x180017753  lea     rdx, aReservedslotte; "ReservedSlotTestOverride"
0x18001775a  xor     r8d, r8d
0x18001775d  call    GetInteger2
0x180017762  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180017769  mov     ebx, eax
0x18001776b  jz      short loc_18001777C
0x18001776d  mov     r9d, eax
0x180017770  lea     r8, aNcbregTestOver; "NcbReg: Test override value"
0x180017777  call    McTemplateU0zq_EventWriteTransfer
0x18001777c  mov     rcx, [rsp+38h+hKey]; hKey
0x180017781  call    cs:__imp_RegCloseKey
0x180017787  jmp     short loc_1800177B9
0x180017789  mov     rcx, cs:WPP_GLOBAL_Control
0x180017790  xor     ebx, ebx
0x180017792  cmp     rcx, rsi
0x180017795  jz      short loc_1800177C0
0x180017797  test    byte ptr [rcx+1Ch], 1
0x18001779b  jz      short loc_1800177C0
0x18001779d  cmp     byte ptr [rcx+19h], 3
0x1800177a1  jb      short loc_1800177C0
0x1800177a3  mov     rcx, [rcx+10h]
0x1800177a7  lea     edx, [rbx+0Dh]
0x1800177aa  mov     r9d, eax
0x1800177ad  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x1800177b4  call    WPP_SF_d
0x1800177b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177c0  test    ebx, ebx
0x1800177c2  setnz   r9b
0x1800177c6  mov     cs:g_NcbRegistrarSlotTestOverride, r9b
0x1800177cd  cmp     rcx, rsi
0x1800177d0  jz      short loc_1800177F3
0x1800177d2  test    byte ptr [rcx+1Ch], 1
0x1800177d6  jz      short loc_1800177F3
0x1800177d8  cmp     byte ptr [rcx+19h], 6
0x1800177dc  jb      short loc_1800177F3
0x1800177de  mov     rcx, [rcx+10h]
0x1800177e2  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x1800177e9  mov     edx, 0Eh
0x1800177ee  call    WPP_SF_c
0x1800177f3  mov     rbx, [rsp+38h+arg_8]
0x1800177f8  add     rsp, 30h
0x1800177fc  pop     rsi
0x1800177fd  retn
```
