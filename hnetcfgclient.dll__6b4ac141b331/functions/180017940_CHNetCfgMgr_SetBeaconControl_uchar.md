# CHNetCfgMgr::SetBeaconControl(uchar)

- ea: `0x180017940`
- end: `0x180017a67`
- name: `?SetBeaconControl@CHNetCfgMgr@@UEAAJE@Z`
- size: `295`
- prototype: `__int64 __fastcall(CHNetCfgMgr *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000a484`
- `0x180017940`
- `0x180018090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017a12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017a12`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017a07`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017a07`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800179d5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800179d5`

## string_xrefs

- `0x18001799f`: `System\CurrentControlSet\Control\Network\SharedAccessConnection`

## pseudocode

```c
__int64 __fastcall CHNetCfgMgr::SetBeaconControl(CHNetCfgMgr *this, unsigned __int8 a2, __int64 a3, __int64 a4)
{
  int v4; // edi
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  int Data; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  v4 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = a2 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, a4);
  }
  hKey = 0;
  v5 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Network\\SharedAccessConnection",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         0);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
  }
  else
  {
    Data = v4;
    RegSetValueExW(hKey, L"EnableControl", 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 211, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x180017940  mov     [rsp+arg_0], rbx
0x180017945  mov     [rsp+arg_8], rbp
0x18001794a  push    rdi
0x18001794b  sub     rsp, 50h
0x18001794f  movzx   edi, dl
0x180017952  mov     rcx, cs:WPP_GLOBAL_Control
0x180017959  lea     rbp, WPP_GLOBAL_Control
0x180017960  cmp     rcx, rbp
0x180017963  jz      short loc_18001798C
0x180017965  test    byte ptr [rcx+1Ch], 8
0x180017969  jz      short loc_18001798C
0x18001796b  cmp     byte ptr [rcx+19h], 6
0x18001796f  jb      short loc_18001798C
0x180017971  mov     rcx, [rcx+10h]
0x180017975  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18001797c  test    dl, dl
0x18001797e  mov     edx, 0D2h
0x180017983  setnz   r9b
0x180017987  call    WPP_SF_c
0x18001798c  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180017995  lea     rax, [rsp+58h+hKey]
0x18001799a  mov     [rsp+58h+phkResult], rax; phkResult
0x18001799f  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Net"...
0x1800179a6  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800179af  xor     r9d, r9d; lpClass
0x1800179b2  mov     [rsp+58h+samDesired], 2; samDesired
0x1800179ba  xor     r8d, r8d; Reserved
0x1800179bd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800179c4  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800179cc  mov     [rsp+58h+hKey], 0
0x1800179d5  call    cs:__imp_RegCreateKeyExW
0x1800179db  mov     ebx, eax
0x1800179dd  test    eax, eax
0x1800179df  jnz     short loc_180017A1A
0x1800179e1  mov     rcx, [rsp+58h+hKey]; hKey
0x1800179e6  lea     r9d, [rax+4]; dwType
0x1800179ea  lea     rax, [rsp+58h+Data]
0x1800179ef  mov     [rsp+58h+samDesired], r9d; cbData
0x1800179f4  xor     r8d, r8d; Reserved
0x1800179f7  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800179fc  lea     rdx, aEnablecontrol; "EnableControl"
0x180017a03  mov     [rsp+58h+Data], edi
0x180017a07  call    cs:__imp_RegSetValueExW
0x180017a0d  mov     rcx, [rsp+58h+hKey]; hKey
0x180017a12  call    cs:__imp_RegCloseKey
0x180017a18  jmp     short loc_180017A25
0x180017a1a  jle     short loc_180017A25
0x180017a1c  movzx   ebx, ax
0x180017a1f  or      ebx, 80070000h
0x180017a25  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a2c  cmp     rcx, rbp
0x180017a2f  jz      short loc_180017A55
0x180017a31  test    byte ptr [rcx+1Ch], 8
0x180017a35  jz      short loc_180017A55
0x180017a37  cmp     byte ptr [rcx+19h], 6
0x180017a3b  jb      short loc_180017A55
0x180017a3d  mov     rcx, [rcx+10h]
0x180017a41  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180017a48  mov     edx, 0D3h
0x180017a4d  mov     r9d, ebx
0x180017a50  call    WPP_SF_d
0x180017a55  mov     rbp, [rsp+58h+arg_8]
0x180017a5a  mov     eax, ebx
0x180017a5c  mov     rbx, [rsp+58h+arg_0]
0x180017a61  add     rsp, 50h
0x180017a65  pop     rdi
0x180017a66  retn
```
