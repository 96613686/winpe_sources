# Win32PointerApi::ReadRegistryUINT(HKEY__ *,ushort *,ushort *,uint,uint *)

- ea: `0x1400305e4`
- end: `0x1400306f1`
- name: `?ReadRegistryUINT@Win32PointerApi@@CAJPEAUHKEY__@@PEAG1IPEAI@Z`
- size: `269`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14003054c`

## callees

- `0x140004b1c`
- `0x140011054`
- `0x1400305e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400306e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400306e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003068d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003068d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400306c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400306c8`

## string_xrefs

- `0x14003067f`: `Software\Policies\Microsoft\Windows NT\Terminal Services\`

## pseudocode

```c
__int64 __fastcall Win32PointerApi::ReadRegistryUINT(
        HKEY a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int *a5)
{
  unsigned int *v5; // rbx
  HKEY v6; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v8; // ebx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int16 *Type; // [rsp+58h] [rbp+20h] BYREF
  unsigned __int16 *cbData; // [rsp+60h] [rbp+28h] BYREF
  unsigned int Data; // [rsp+68h] [rbp+30h] BYREF

  Data = a4;
  cbData = a3;
  Type = a2;
  v5 = a5;
  v6 = 0;
  hKey = 0;
  if ( a5 )
  {
    *a5 = 1;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\",
            0,
            0x20019u,
            &hKey) )
    {
      Data = 0;
      LODWORD(Type) = 0;
      LODWORD(cbData) = 4;
      if ( !RegQueryValueExW(hKey, L"TouchRemotingEnabled", 0, (LPDWORD)&Type, (LPBYTE)&Data, (LPDWORD)&cbData) )
        *v5 = Data;
    }
    v6 = hKey;
    v8 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        (unsigned int)WPP_d9b380fd558c3c7db75e41607391f8f6_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"puVal");
      v6 = hKey;
    }
    v8 = -2147467261;
  }
  if ( v6 )
    RegCloseKey(v6);
  return v8;
}

```

## disassembly

```asm
0x1400305e4  mov     rax, rsp
0x1400305e7  mov     [rax+20h], r9d
0x1400305eb  mov     [rax+18h], r8
0x1400305ef  mov     [rax+10h], rdx
0x1400305f3  mov     [rax+8], rcx
0x1400305f7  push    rbp
0x1400305f8  push    rbx
0x1400305f9  mov     rbp, rsp
0x1400305fc  sub     rsp, 38h
0x140030600  mov     rbx, [rbp+arg_20]
0x140030604  xor     ecx, ecx
0x140030606  mov     [rbp+hKey], rcx
0x14003060a  test    rbx, rbx
0x14003060d  jnz     short loc_140030667
0x14003060f  mov     rax, cs:WPP_GLOBAL_Control
0x140030616  lea     rdx, WPP_GLOBAL_Control
0x14003061d  cmp     rax, rdx
0x140030620  jz      short loc_140030660
0x140030622  test    byte ptr [rax+1Ch], 8
0x140030626  jz      short loc_140030660
0x140030628  cmp     byte ptr [rax+19h], 2
0x14003062c  jb      short loc_140030660
0x14003062e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140030633  lea     rcx, aPuval; "puVal"
0x14003063a  mov     r9d, eax
0x14003063d  mov     [rsp+38h+phkResult], rcx
0x140030642  lea     edx, [rbx+40h]
0x140030645  mov     rcx, cs:WPP_GLOBAL_Control
0x14003064c  lea     r8, WPP_d9b380fd558c3c7db75e41607391f8f6_Traceguids
0x140030653  mov     rcx, [rcx+10h]
0x140030657  call    WPP_SF_Ds
0x14003065c  mov     rcx, [rbp+hKey]
0x140030660  mov     ebx, 80004003h
0x140030665  jmp     short loc_1400306DD
0x140030667  lea     rax, [rbp+hKey]
0x14003066b  mov     dword ptr [rbx], 1
0x140030671  mov     r9d, 20019h; samDesired
0x140030677  mov     [rsp+38h+phkResult], rax; phkResult
0x14003067c  xor     r8d, r8d; ulOptions
0x14003067f  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x140030686  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003068d  call    cs:__imp_RegOpenKeyExW
0x140030693  test    eax, eax
0x140030695  jnz     short loc_1400306D7
0x140030697  mov     rcx, [rbp+hKey]; hKey
0x14003069b  lea     r9, [rbp+Type]; lpType
0x14003069f  mov     [rbp+Data], eax
0x1400306a2  lea     rdx, aTouchremotinge; "TouchRemotingEnabled"
0x1400306a9  mov     dword ptr [rbp+Type], eax
0x1400306ac  xor     r8d, r8d; lpReserved
0x1400306af  lea     rax, [rbp+cbData]
0x1400306b3  mov     dword ptr [rbp+cbData], 4
0x1400306ba  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1400306bf  lea     rax, [rbp+Data]
0x1400306c3  mov     [rsp+38h+phkResult], rax; lpData
0x1400306c8  call    cs:__imp_RegQueryValueExW
0x1400306ce  test    eax, eax
0x1400306d0  jnz     short loc_1400306D7
0x1400306d2  mov     eax, [rbp+Data]
0x1400306d5  mov     [rbx], eax
0x1400306d7  mov     rcx, [rbp+hKey]; hKey
0x1400306db  xor     ebx, ebx
0x1400306dd  test    rcx, rcx
0x1400306e0  jz      short loc_1400306E8
0x1400306e2  call    cs:__imp_RegCloseKey
0x1400306e8  mov     eax, ebx
0x1400306ea  add     rsp, 38h
0x1400306ee  pop     rbx
0x1400306ef  pop     rbp
0x1400306f0  retn
```
