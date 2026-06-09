# DllRegisterServerTest

- ea: `0x18018ae9c`
- end: `0x18018b120`
- name: `DllRegisterServerTest`
- size: `644`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180194930`

## callees

- `0x180010ac0`
- `0x180014160`
- `0x18018ae9c`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18018b0e0`
- `ADVAPI32!RegCloseKey` at `0x18018b0e0`
- `ADVAPI32!RegSetValueExW` at `0x18018b074`
- `ADVAPI32!RegSetValueExW` at `0x18018b0c5`
- `ADVAPI32!RegSetValueExW` at `0x18018b074`
- `ADVAPI32!RegSetValueExW` at `0x18018b0c5`
- `KERNEL32!GetLastError` at `0x18018af09`
- `KERNEL32!GetLastError` at `0x18018af09`
- `KERNEL32!GetModuleFileNameW` at `0x18018aef9`
- `KERNEL32!GetModuleFileNameW` at `0x18018aef9`
- `KERNEL32!lstrlenW` at `0x18018b044`
- `KERNEL32!lstrlenW` at `0x18018b093`
- `KERNEL32!lstrlenW` at `0x18018b044`
- `KERNEL32!lstrlenW` at `0x18018b093`
- `RPCRT4!NdrDllRegisterProxy` at `0x18018aed1`
- `RPCRT4!NdrDllRegisterProxy` at `0x18018aed1`

## pseudocode

```c
HRESULT DllRegisterServerTest()
{
  HRESULT result; // eax
  int v1; // ebx
  int i; // esi
  const unsigned __int16 *v3; // r8
  const unsigned __int16 * near **v4; // rdi
  int v5; // eax
  const unsigned __int16 * near *v6; // rcx
  int v7; // eax
  HKEY hKey[2]; // [rsp+50h] [rbp-E8h] BYREF
  unsigned __int16 v9[80]; // [rsp+60h] [rbp-D8h] BYREF

  result = NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, &CLSID_PSFactoryBuffer);
  if ( !result )
  {
    if ( GetModuleFileNameW(g_hInstance, &szRegFilePath, 0x103u) )
    {
      v1 = 0;
      word_180311D96 = 0;
      for ( i = 0; i < 10; ++i )
      {
        result = StringCchPrintfW(&szRegCLSID, 0x28u, L"{%08lX-0000-0000-C000-000000000046}", *(&rgCLSID.Data1 + 4 * i));
        if ( result < 0 )
          return result;
        v3 = (const unsigned __int16 *)(&rgszProgId)[i];
        if ( v3 )
        {
          result = StringCchCopyW(&szRegProgId, 0x28u, v3);
          if ( result < 0 )
            return result;
        }
        v4 = &rgszRegData;
        result = StringCchCopyW(&szRegDescription, 0x64u, (const unsigned __int16 *)(&rgszDescription)[i]);
        if ( result < 0 )
          return result;
        while ( *v4 )
        {
          if ( v4[1] && v4[2] )
          {
            result = StringCchPrintfW(v9, 0x50u, (const unsigned __int16 *)*v4);
            if ( result < 0 )
              return result;
            hKey[0] = 0;
            if ( (unsigned int)((__int64 (__fastcall *)(unsigned __int64, unsigned __int16 *, _QWORD, _QWORD, _DWORD, int, _QWORD, HKEY *, _QWORD))RegCreateKeyAPI)(
                                 0xFFFFFFFF80000000uLL,
                                 v9,
                                 0,
                                 0,
                                 0,
                                 131103,
                                 0,
                                 hKey,
                                 0)
              || (v5 = lstrlenW((LPCWSTR)v4[2]), RegSetValueExW(hKey[0], 0, 0, 1u, (const BYTE *)v4[2], 2 * v5 + 2)) )
            {
              ++v1;
            }
            v6 = v4[3];
            if ( v6 )
            {
              v7 = lstrlenW((LPCWSTR)v6 + 1);
              if ( RegSetValueExW(hKey[0], (LPCWSTR)v4[3], 0, 1u, (const BYTE *)v4[4], 2 * v7 + 2) )
                ++v1;
            }
            v4 += 5;
            RegCloseKey(hKey[0]);
          }
        }
      }
      return v1 != 0 ? 0x80040201 : 0;
    }
    else
    {
      return GetLastError();
    }
  }
  return result;
}

```

## disassembly

```asm
0x18018ae9c  push    rbx
0x18018ae9e  push    rbp
0x18018ae9f  push    rsi
0x18018aea0  push    rdi
0x18018aea1  push    r12
0x18018aea3  sub     rsp, 110h
0x18018aeaa  mov     rax, cs:__security_cookie
0x18018aeb1  xor     rax, rsp
0x18018aeb4  mov     [rsp+138h+var_38], rax
0x18018aebc  mov     rcx, cs:hProxyDll; hDll
0x18018aec3  lea     r8, CLSID_PSFactoryBuffer; pclsid
0x18018aeca  lea     rdx, aProxyFileList; pProxyFileList
0x18018aed1  call    cs:__imp_NdrDllRegisterProxy
0x18018aed8  nop     dword ptr [rax+rax+00h]
0x18018aedd  test    eax, eax
0x18018aedf  jnz     loc_18018B101
0x18018aee5  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18018aeec  lea     rdx, ?szRegFilePath@@3PAGA; lpFilename
0x18018aef3  mov     r8d, 103h; nSize
0x18018aef9  call    cs:__imp_GetModuleFileNameW
0x18018af00  nop     dword ptr [rax+rax+00h]
0x18018af05  test    eax, eax
0x18018af07  jnz     short loc_18018AF1A
0x18018af09  call    cs:__imp_GetLastError
0x18018af10  nop     dword ptr [rax+rax+00h]
0x18018af15  jmp     loc_18018B101
0x18018af1a  xor     eax, eax
0x18018af1c  lea     r12, cs:180000000h
0x18018af23  xor     ebx, ebx
0x18018af25  mov     cs:word_180311D96, ax
0x18018af2c  xor     esi, esi
0x18018af2e  cmp     esi, 0Ah
0x18018af31  jge     loc_18018B0F8
0x18018af37  movsxd  rbp, esi
0x18018af3a  lea     r8, a08lx00000000C0; "{%08lX-0000-0000-C000-000000000046}"
0x18018af41  mov     r9, rbp
0x18018af44  lea     rcx, ?szRegCLSID@@3PAGA; unsigned __int16 *
0x18018af4b  add     r9, r9
0x18018af4e  mov     edx, 28h ; '('; unsigned __int64
0x18018af53  mov     r9d, dword ptr ds:rva ?rgCLSID@@3QBU_GUID@@B.Data1[r12+r9*8]; _GUID const near * const rgCLSID ...
0x18018af5b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18018af60  test    eax, eax
0x18018af62  js      loc_18018B101
0x18018af68  mov     r8, ds:rva ?rgszProgId@@3QBQEBGB[r12+rbp*8]; unsigned __int16 *
0x18018af70  test    r8, r8
0x18018af73  jz      short loc_18018AF8E
0x18018af75  mov     edx, 28h ; '('; unsigned __int64
0x18018af7a  lea     rcx, ?szRegProgId@@3PAGA; unsigned __int16 *
0x18018af81  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18018af86  test    eax, eax
0x18018af88  js      loc_18018B101
0x18018af8e  mov     r8, ds:rva ?rgszDescription@@3QBQEBGB[r12+rbp*8]; unsigned __int16 *
0x18018af96  lea     rcx, ?szRegDescription@@3PAGA; unsigned __int16 *
0x18018af9d  mov     edx, 64h ; 'd'; unsigned __int64
0x18018afa2  lea     rdi, ?rgszRegData@@3PAPEBGA; ushort const * near * rgszRegData
0x18018afa9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18018afae  test    eax, eax
0x18018afb0  js      loc_18018B101
0x18018afb6  mov     r8, [rdi]; unsigned __int16 *
0x18018afb9  test    r8, r8
0x18018afbc  jz      loc_18018B0F1
0x18018afc2  mov     r9, [rdi+8]
0x18018afc6  test    r9, r9
0x18018afc9  jz      short loc_18018AFB6
0x18018afcb  cmp     qword ptr [rdi+10h], 0
0x18018afd0  jz      short loc_18018AFB6
0x18018afd2  mov     edx, 50h ; 'P'; unsigned __int64
0x18018afd7  lea     rcx, [rsp+138h+var_D8]; unsigned __int16 *
0x18018afdc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18018afe1  test    eax, eax
0x18018afe3  js      loc_18018B101
0x18018afe9  mov     [rsp+138h+var_F8], 0
0x18018aff2  lea     rax, [rsp+138h+hKey]
0x18018aff7  mov     [rsp+138h+var_100], rax
0x18018affc  lea     rdx, [rsp+138h+var_D8]
0x18018b001  mov     rax, cs:?RegCreateKeyAPI@@3P6AJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@ZEA; long (*RegCreateKeyAPI)(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18018b008  xor     r9d, r9d
0x18018b00b  mov     [rsp+138h+var_108], 0
0x18018b014  xor     r8d, r8d
0x18018b017  mov     [rsp+138h+cbData], 2001Fh
0x18018b01f  mov     rcx, 0FFFFFFFF80000000h
0x18018b026  mov     dword ptr [rsp+138h+lpData], 0
0x18018b02e  mov     [rsp+138h+hKey], 0
0x18018b037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b03c  test    eax, eax
0x18018b03e  jnz     short loc_18018B084
0x18018b040  mov     rcx, [rdi+10h]; lpString
0x18018b044  call    cs:__imp_lstrlenW
0x18018b04b  nop     dword ptr [rax+rax+00h]
0x18018b050  mov     rcx, [rsp+138h+hKey]; hKey
0x18018b055  mov     r9d, 1; dwType
0x18018b05b  xor     r8d, r8d; Reserved
0x18018b05e  xor     edx, edx; lpValueName
0x18018b060  lea     eax, ds:2[rax*2]
0x18018b067  mov     [rsp+138h+cbData], eax; cbData
0x18018b06b  mov     rax, [rdi+10h]
0x18018b06f  mov     [rsp+138h+lpData], rax; lpData
0x18018b074  call    cs:__imp_RegSetValueExW
0x18018b07b  nop     dword ptr [rax+rax+00h]
0x18018b080  test    eax, eax
0x18018b082  jz      short loc_18018B086
0x18018b084  inc     ebx
0x18018b086  mov     rcx, [rdi+18h]
0x18018b08a  test    rcx, rcx
0x18018b08d  jz      short loc_18018B0D7
0x18018b08f  add     rcx, 2; lpString
0x18018b093  call    cs:__imp_lstrlenW
0x18018b09a  nop     dword ptr [rax+rax+00h]
0x18018b09f  mov     rdx, [rdi+18h]; lpValueName
0x18018b0a3  mov     r9d, 1; dwType
0x18018b0a9  mov     rcx, [rsp+138h+hKey]; hKey
0x18018b0ae  xor     r8d, r8d; Reserved
0x18018b0b1  lea     eax, ds:2[rax*2]
0x18018b0b8  mov     [rsp+138h+cbData], eax; cbData
0x18018b0bc  mov     rax, [rdi+20h]
0x18018b0c0  mov     [rsp+138h+lpData], rax; lpData
0x18018b0c5  call    cs:__imp_RegSetValueExW
0x18018b0cc  nop     dword ptr [rax+rax+00h]
0x18018b0d1  test    eax, eax
0x18018b0d3  jz      short loc_18018B0D7
0x18018b0d5  inc     ebx
0x18018b0d7  mov     rcx, [rsp+138h+hKey]; hKey
0x18018b0dc  add     rdi, 28h ; '('
0x18018b0e0  call    cs:__imp_RegCloseKey
0x18018b0e7  nop     dword ptr [rax+rax+00h]
0x18018b0ec  jmp     loc_18018AFB6
0x18018b0f1  inc     esi
0x18018b0f3  jmp     loc_18018AF2E
0x18018b0f8  neg     ebx
0x18018b0fa  sbb     eax, eax
0x18018b0fc  and     eax, 80040201h
0x18018b101  mov     rcx, [rsp+138h+var_38]
0x18018b109  xor     rcx, rsp; StackCookie
0x18018b10c  call    __security_check_cookie
0x18018b111  add     rsp, 110h
0x18018b118  pop     r12
0x18018b11a  pop     rdi
0x18018b11b  pop     rsi
0x18018b11c  pop     rbp
0x18018b11d  pop     rbx
0x18018b11e  retn
```
