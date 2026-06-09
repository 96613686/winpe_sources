# MvSetUIStatus(IMVHandler *,__MIDL___MIDL_itf_mvengine_0000_0000_0002)

- ea: `0x18003774c`
- end: `0x1800378a0`
- name: `?MvSetUIStatus@@YAJPEAUIMVHandler@@W4__MIDL___MIDL_itf_mvengine_0000_0000_0002@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(struct IMVHandler *, const unsigned int *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002d570`
- `0x18002eb90`

## callees

- `0x1800376bc`
- `0x18003774c`
- `0x18003b9a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800377ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800377ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800377cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800377cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800377a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800377c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037874`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800377a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800377c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037874`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003785e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003785e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003781a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003781a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MvSetUIStatus(
        struct IMVHandler *a1,
        const unsigned int *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int ContextSubKeyPath; // ebx
  LSTATUS v6; // eax
  bool v7; // cc
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  *(_DWORD *)Data = (_DWORD)a2;
  hKey = 0;
  ContextSubKeyPath = MvGetContextSubKeyPath(a1, a2, a3, a4, SubKey);
  if ( ContextSubKeyPath < 0 )
  {
LABEL_2:
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)ContextSubKeyPath;
  }
  hKey = 0;
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 2u, 0, &hKey, 0);
  ContextSubKeyPath = v6;
  v7 = v6 <= 0;
  if ( v6 || (v6 = RegSetValueExW(hKey, L"UIRequired", 0, 4u, Data, 4u), ContextSubKeyPath = v6, v7 = v6 <= 0, v6) )
  {
    if ( !v7 )
      ContextSubKeyPath = (unsigned __int16)v6 | 0x80070000;
    goto LABEL_2;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18003774c  mov     [rsp-8+arg_10], rbx
0x180037751  mov     [rsp-8+arg_18], rdi
0x180037756  push    rbp
0x180037757  lea     rbp, [rsp-180h]
0x18003775f  sub     rsp, 280h
0x180037766  mov     rax, cs:__security_cookie
0x18003776d  xor     rax, rsp
0x180037770  mov     [rbp+180h+var_10], rax
0x180037777  mov     dword ptr [rsp+280h+Data], edx
0x18003777b  mov     [rsp+280h+hKey], 0
0x180037784  lea     rax, [rsp+280h+SubKey]
0x180037789  mov     qword ptr [rsp+280h+dwOptions], rax; unsigned __int16 *
0x18003778e  call    ?MvGetContextSubKeyPath@@YAJPEAUIMVHandler@@PEBKPEBG2PEAGKPEAU_MVProvisionData@@@Z; MvGetContextSubKeyPath(IMVHandler *,ulong const *,ushort const *,ushort const *,ushort *,ulong,_MVProvisionData *)
0x180037793  mov     ebx, eax
0x180037795  test    eax, eax
0x180037797  jns     short loc_1800377B0
0x180037799  mov     rcx, [rsp+280h+hKey]; hKey
0x18003779e  test    rcx, rcx
0x1800377a1  jz      short loc_1800377A9
0x1800377a3  call    cs:__imp_RegCloseKey
0x1800377a9  mov     eax, ebx
0x1800377ab  jmp     loc_18003787C
0x1800377b0  mov     rdi, [rsp+280h+hKey]
0x1800377b5  test    rdi, rdi
0x1800377b8  jz      short loc_1800377D3
0x1800377ba  call    cs:__imp_GetLastError
0x1800377c0  mov     ebx, eax
0x1800377c2  mov     rcx, rdi; hKey
0x1800377c5  call    cs:__imp_RegCloseKey
0x1800377cb  mov     ecx, ebx; dwErrCode
0x1800377cd  call    cs:__imp_SetLastError
0x1800377d3  mov     [rsp+280h+hKey], 0
0x1800377dc  mov     [rsp+280h+lpdwDisposition], 0; lpdwDisposition
0x1800377e5  lea     rax, [rsp+280h+hKey]
0x1800377ea  mov     [rsp+280h+phkResult], rax; phkResult
0x1800377ef  mov     [rsp+280h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800377f8  mov     [rsp+280h+samDesired], 2; samDesired
0x180037800  mov     [rsp+280h+dwOptions], 0; dwOptions
0x180037808  xor     r9d, r9d; lpClass
0x18003780b  xor     r8d, r8d; Reserved
0x18003780e  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x180037813  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003781a  call    cs:__imp_RegCreateKeyExW
0x180037820  mov     ebx, eax
0x180037822  test    eax, eax
0x180037824  jz      short loc_18003783A
0x180037826  jle     loc_180037799
0x18003782c  movzx   ebx, ax
0x18003782f  or      ebx, 80070000h
0x180037835  jmp     loc_180037799
0x18003783a  mov     r9d, 4; dwType
0x180037840  mov     [rsp+280h+samDesired], r9d; cbData
0x180037845  lea     rax, [rsp+280h+Data]
0x18003784a  mov     qword ptr [rsp+280h+dwOptions], rax; lpData
0x18003784f  xor     r8d, r8d; Reserved
0x180037852  lea     rdx, ?gc_wszUIRequired@@3QBGB; "UIRequired"
0x180037859  mov     rcx, [rsp+280h+hKey]; hKey
0x18003785e  call    cs:__imp_RegSetValueExW
0x180037864  mov     ebx, eax
0x180037866  test    eax, eax
0x180037868  jnz     short loc_180037826
0x18003786a  mov     rcx, [rsp+280h+hKey]; hKey
0x18003786f  test    rcx, rcx
0x180037872  jz      short loc_18003787A
0x180037874  call    cs:__imp_RegCloseKey
0x18003787a  xor     eax, eax
0x18003787c  mov     rcx, [rbp+180h+var_10]
0x180037883  xor     rcx, rsp; StackCookie
0x180037886  call    __security_check_cookie
0x18003788b  lea     r11, [rsp+280h+var_s0]
0x180037893  mov     rbx, [r11+20h]
0x180037897  mov     rdi, [r11+28h]
0x18003789b  mov     rsp, r11
0x18003789e  pop     rbp
0x18003789f  retn
```
