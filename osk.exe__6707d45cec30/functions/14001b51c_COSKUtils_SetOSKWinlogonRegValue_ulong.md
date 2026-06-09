# COSKUtils::SetOSKWinlogonRegValue(ulong)

- ea: `0x14001b51c`
- end: `0x14001b66c`
- name: `?SetOSKWinlogonRegValue@COSKUtils@@CAXK@Z`
- size: `336`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000e16c`
- `0x14001b674`

## callees

- `0x140005c90`
- `0x140009524`
- `0x140009938`
- `0x1400170d8`
- `0x14001b51c`
- `0x14001b6f0`
- `0x14001c768`
- `0x14001caa4`
- `0x14001cf70`
- `0x14001d250`
- `0x14001d298`
- `0x140020ebc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001b614`
- `KERNEL32!CloseHandle` at `0x14001b614`
- `KERNEL32!OpenMutexW` at `0x14001b5eb`
- `KERNEL32!OpenMutexW` at `0x14001b5eb`

## string_xrefs

- `0x14001b573`: `Software\Microsoft\Windows NT\CurrentVersion\AccessibilityTemp`
- `0x14001b603`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`
- `0x14001b621`: `SecureConfiguration`
- `0x14001b5fc`: `Configuration`
- `0x14001b628`: `Configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall COSKUtils::SetOSKWinlogonRegValue(unsigned int a1)
{
  unsigned __int16 *v2; // r9
  int v3; // edx
  int v4; // edx
  const unsigned __int16 *v5; // rcx
  HANDLE v6; // rsi
  bool v7; // bl
  const unsigned __int16 *v8; // rdi
  const unsigned __int16 **v9; // rax
  const unsigned __int16 *v10; // rcx
  HKEY v11; // [rsp+30h] [rbp-D0h]
  _QWORD v12[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[384]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v14; // [rsp+1F8h] [rbp+F8h] BYREF

  if ( COSKUtils::ShouldRunSecure() )
  {
    v6 = OpenMutexW(0x100000u, 0, L"Global\\Windows.Machine.OOBE");
    v7 = a1 & 1;
    if ( v6 )
    {
      CATUtils::_UpdateConfigurationValue(
        v5,
        v7,
        L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\OOBE",
        L"Configuration");
      CloseHandle(v6);
    }
    else
    {
      v8 = L"Configuration";
      if ( !(unsigned int)CATUtils::IsInteractiveUser() )
        v8 = L"SecureConfiguration";
      v9 = (const unsigned __int16 **)CATUtils::SessionKeyString((__int64)&v14);
      CATUtils::_UpdateConfigurationValue(v10, v7, *v9, v8);
      ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
    }
  }
  else
  {
    memset(v12, 0, 24);
    if ( !(unsigned int)ATL::CRegKey::Create(
                          (ATL::CRegKey *)v12,
                          HKEY_CURRENT_USER,
                          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AccessibilityTemp",
                          v2,
                          1u,
                          0x2001Fu,
                          v11,
                          0) )
    {
      ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v12, L"osk", a1);
      ATL::CRegKey::Close((ATL::CRegKey *)v12);
    }
    ATManager::ATManager((ATManager *)v13, v3);
    StartList::Synchronize((StartList *)v13, v4);
    ATManager::~ATManager((ATManager *)v13);
    ATL::CRegKey::Close((ATL::CRegKey *)v12);
  }
}

```

## disassembly

```asm
0x14001b51c  push    rbp
0x14001b51e  push    rbx
0x14001b51f  push    rsi
0x14001b520  push    rdi
0x14001b521  lea     rbp, [rsp-0C8h]
0x14001b529  sub     rsp, 1C8h
0x14001b530  mov     ebx, ecx
0x14001b532  call    ?ShouldRunSecure@COSKUtils@@SA_NXZ; COSKUtils::ShouldRunSecure(void)
0x14001b537  test    al, al
0x14001b539  jnz     loc_14001B5DD
0x14001b53f  mov     [rsp+1E0h+var_1A0], 0
0x14001b548  mov     [rsp+1E0h+var_198], 0
0x14001b551  mov     [rsp+1E0h+var_190], 0
0x14001b55a  mov     [rsp+1E0h+var_1A8], 0; unsigned int *
0x14001b563  mov     [rsp+1E0h+var_1B8], 2001Fh; REGSAM
0x14001b56b  mov     [rsp+1E0h+var_1C0], 1; DWORD
0x14001b573  lea     r8, aSoftwareMicros_12; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001b57a  mov     rdx, 0FFFFFFFF80000001h; hKey
0x14001b581  lea     rcx, [rsp+1E0h+var_1A0]; this
0x14001b586  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x14001b58b  test    eax, eax
0x14001b58d  jnz     short loc_14001B5AD
0x14001b58f  mov     r8d, ebx; unsigned int
0x14001b592  lea     rdx, aOsk; "osk"
0x14001b599  lea     rcx, [rsp+1E0h+var_1A0]; this
0x14001b59e  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x14001b5a3  lea     rcx, [rsp+1E0h+var_1A0]; this
0x14001b5a8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001b5ad  lea     rcx, [rsp+1E0h+var_180]; this
0x14001b5b2  call    ??0ATManager@@QEAA@H@Z; ATManager::ATManager(int)
0x14001b5b7  nop
0x14001b5b8  lea     rcx, [rsp+1E0h+var_180]; this
0x14001b5bd  call    ?Synchronize@StartList@@QEAAJH@Z; StartList::Synchronize(int)
0x14001b5c2  nop
0x14001b5c3  lea     rcx, [rsp+1E0h+var_180]; this
0x14001b5c8  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x14001b5cd  nop
0x14001b5ce  lea     rcx, [rsp+1E0h+var_1A0]; this
0x14001b5d3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001b5d8  jmp     loc_14001B660
0x14001b5dd  lea     r8, aGlobalWindowsM_0; "Global\\Windows.Machine.OOBE"
0x14001b5e4  xor     edx, edx; bInheritHandle
0x14001b5e6  mov     ecx, 100000h; dwDesiredAccess
0x14001b5eb  call    cs:__imp_OpenMutexW
0x14001b5f1  mov     rsi, rax
0x14001b5f4  and     bl, 1
0x14001b5f7  test    rax, rax
0x14001b5fa  jz      short loc_14001B61C
0x14001b5fc  lea     r9, aConfiguration_0; "Configuration"
0x14001b603  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001b60a  mov     dl, bl; bool
0x14001b60c  call    ?_UpdateConfigurationValue@CATUtils@@CAXPEBG_N00@Z; CATUtils::_UpdateConfigurationValue(ushort const *,bool,ushort const *,ushort const *)
0x14001b611  mov     rcx, rsi; hObject
0x14001b614  call    cs:__imp_CloseHandle
0x14001b61a  jmp     short loc_14001B660
0x14001b61c  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x14001b621  lea     rcx, aSecureconfigur; "SecureConfiguration"
0x14001b628  lea     rdi, aConfiguration_0; "Configuration"
0x14001b62f  test    eax, eax
0x14001b631  cmovz   rdi, rcx
0x14001b635  lea     rcx, [rbp+0E0h+arg_8]
0x14001b63c  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x14001b641  nop
0x14001b642  mov     r9, rdi; unsigned __int16 *
0x14001b645  mov     r8, [rax]; unsigned __int16 *
0x14001b648  mov     dl, bl; bool
0x14001b64a  call    ?_UpdateConfigurationValue@CATUtils@@CAXPEBG_N00@Z; CATUtils::_UpdateConfigurationValue(ushort const *,bool,ushort const *,ushort const *)
0x14001b64f  nop
0x14001b650  mov     rcx, [rbp+0E0h+arg_8]
0x14001b657  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001b65b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001b660  add     rsp, 1C8h
0x14001b667  pop     rdi
0x14001b668  pop     rsi
0x14001b669  pop     rbx
0x14001b66a  pop     rbp
0x14001b66b  retn
```
