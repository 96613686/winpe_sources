# MsRdlsDBFactory::CreateRdlsDBInstance(ushort *,ushort *,ushort *)

- ea: `0x180083a10`
- end: `0x180083b84`
- name: `?CreateRdlsDBInstance@MsRdlsDBFactory@@UEAAPEAVIRdlsDB@@PEAG00@Z`
- size: `372`
- prototype: `struct IRdlsDB *(MsRdlsDBFactory *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x18000205c`
- `0x180083a10`
- `0x1800841e8`
- `0x180086288`
- `0x1800a5010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180083aa0`
- `ADVAPI32!RegQueryValueExW` at `0x180083ad6`
- `ADVAPI32!RegQueryValueExW` at `0x180083aa0`
- `ADVAPI32!RegQueryValueExW` at `0x180083ad6`
- `ADVAPI32!RegOpenKeyExW` at `0x180083a6d`
- `ADVAPI32!RegOpenKeyExW` at `0x180083a6d`
- `ADVAPI32!RegCloseKey` at `0x180083b5a`
- `ADVAPI32!RegCloseKey` at `0x180083b5a`

## string_xrefs

- `0x180083a5f`: `SYSTEM\CurrentControlSet\Services\TermServLicensing\Parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct IRdlsDB *__fastcall MsRdlsDBFactory::CreateRdlsDBInstance(
        MsRdlsDBFactory *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v8; // rcx
  unsigned int v9; // r14d
  struct IRdlsDB *v10; // rbx
  CRdlsDBWID *v11; // rax
  struct IRdlsDB *Instance; // rax
  DWORD cbData; // [rsp+30h] [rbp-20h] BYREF
  BYTE lpData[4]; // [rsp+34h] [rbp-1Ch] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey[2]; // [rsp+40h] [rbp-10h] BYREF

  hKey[0] = 0;
  cbData = 4;
  *(_DWORD *)lpData = 0;
  *(_DWORD *)Data = 2;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\TermServLicensing\\Parameters",
          0,
          1u,
          hKey) )
  {
    RegQueryValueExW(hKey[0], L"TransactionLockMethod", 0, 0, Data, &cbData);
    cbData = 4;
    RegQueryValueExW(hKey[0], L"IsSQLDB", 0, 0, lpData, &cbData);
  }
  if ( *(_DWORD *)lpData == 1 )
  {
    v9 = *(_DWORD *)Data;
    v10 = CRdlsDBWID::m_RdlsDB;
    if ( !CRdlsDBWID::m_RdlsDB )
    {
      v11 = (CRdlsDBWID *)operator new(0x38u);
      hKey[1] = (HKEY)v11;
      if ( v11 )
        v10 = CRdlsDBWID::CRdlsDBWID(v11, a3, a4, v9);
      else
        v10 = 0;
      CRdlsDBWID::m_RdlsDB = v10;
    }
  }
  else
  {
    if ( *(_DWORD *)lpData == 2 )
      Instance = (struct IRdlsDB *)(*(__int64 (__fastcall **)(MsRdlsDBFactory *, HKEY, unsigned __int16 *, unsigned __int16 *))(*(_QWORD *)this + 8LL))(
                                     this,
                                     hKey[0],
                                     a3,
                                     a4);
    else
      Instance = CRdlsDBJet::CreateInstance(v8, a2, a3, a4);
    v10 = Instance;
  }
  RegCloseKey(hKey[0]);
  return v10;
}

```

## disassembly

```asm
0x180083a10  mov     r11, rsp
0x180083a13  mov     [r11+8], rbx
0x180083a17  mov     [r11+10h], rsi
0x180083a1b  mov     [r11+18h], rdi
0x180083a1f  mov     [r11+20h], r14
0x180083a23  push    rbp
0x180083a24  mov     rbp, rsp
0x180083a27  sub     rsp, 50h
0x180083a2b  mov     rdi, r9
0x180083a2e  mov     rsi, r8
0x180083a31  mov     r14, rdx
0x180083a34  mov     rbx, rcx
0x180083a37  and     [rbp+hKey], 0
0x180083a3c  mov     [rbp+cbData], 4
0x180083a43  and     dword ptr [rbp+var_1C], 0
0x180083a47  mov     dword ptr [rbp+Data], 2
0x180083a4e  lea     rax, [rbp+hKey]
0x180083a52  mov     [r11-38h], rax
0x180083a56  mov     r9d, 1; samDesired
0x180083a5c  xor     r8d, r8d; ulOptions
0x180083a5f  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x180083a66  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180083a6d  call    cs:__imp_RegOpenKeyExW
0x180083a74  nop     dword ptr [rax+rax+00h]
0x180083a79  test    eax, eax
0x180083a7b  jnz     short loc_180083AE2
0x180083a7d  lea     rax, [rbp+cbData]
0x180083a81  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180083a86  lea     rax, [rbp+Data]
0x180083a8a  mov     [rsp+50h+lpData], rax; lpData
0x180083a8f  xor     r9d, r9d; lpType
0x180083a92  xor     r8d, r8d; lpReserved
0x180083a95  lea     rdx, aTransactionloc; "TransactionLockMethod"
0x180083a9c  mov     rcx, [rbp+hKey]; hKey
0x180083aa0  call    cs:__imp_RegQueryValueExW
0x180083aa7  nop     dword ptr [rax+rax+00h]
0x180083aac  mov     [rbp+cbData], 4
0x180083ab3  lea     rax, [rbp+cbData]
0x180083ab7  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180083abc  lea     rax, [rbp+var_1C]
0x180083ac0  mov     [rsp+50h+lpData], rax; lpData
0x180083ac5  xor     r9d, r9d; lpType
0x180083ac8  xor     r8d, r8d; lpReserved
0x180083acb  lea     rdx, aIssqldb; "IsSQLDB"
0x180083ad2  mov     rcx, [rbp+hKey]; hKey
0x180083ad6  call    cs:__imp_RegQueryValueExW
0x180083add  nop     dword ptr [rax+rax+00h]
0x180083ae2  cmp     dword ptr [rbp+var_1C], 1
0x180083ae6  jnz     short loc_180083B2A
0x180083ae8  mov     r14d, dword ptr [rbp+Data]
0x180083aec  mov     rbx, cs:?m_RdlsDB@CRdlsDBWID@@1PEAVIRdlsDB@@EA; IRdlsDB * CRdlsDBWID::m_RdlsDB
0x180083af3  test    rbx, rbx
0x180083af6  jnz     short loc_180083B56
0x180083af8  lea     ecx, [rbx+38h]; Size
0x180083afb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180083b00  mov     [rbp+var_8], rax
0x180083b04  test    rax, rax
0x180083b07  jz      short loc_180083B1F
0x180083b09  mov     r9d, r14d; unsigned int
0x180083b0c  mov     r8, rdi; unsigned __int16 *
0x180083b0f  mov     rdx, rsi; unsigned __int16 *
0x180083b12  mov     rcx, rax; this
0x180083b15  call    ??0CRdlsDBWID@@IEAA@PEAG0K@Z; CRdlsDBWID::CRdlsDBWID(ushort *,ushort *,ulong)
0x180083b1a  mov     rbx, rax
0x180083b1d  jmp     short loc_180083B21
0x180083b1f  xor     ebx, ebx
0x180083b21  mov     cs:?m_RdlsDB@CRdlsDBWID@@1PEAVIRdlsDB@@EA, rbx; IRdlsDB * CRdlsDBWID::m_RdlsDB
0x180083b28  jmp     short loc_180083B56
0x180083b2a  mov     r9, rdi; unsigned __int16 *
0x180083b2d  mov     r8, rsi; unsigned __int16 *
0x180083b30  cmp     dword ptr [rbp+var_1C], 2
0x180083b34  jnz     short loc_180083B4B
0x180083b36  mov     rax, [rbx]
0x180083b39  mov     rdx, [rbp+hKey]
0x180083b3d  mov     rcx, rbx
0x180083b40  mov     rax, [rax+8]
0x180083b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b49  jmp     short loc_180083B53
0x180083b4b  mov     rdx, r14; unsigned __int16 *
0x180083b4e  call    ?CreateInstance@CRdlsDBJet@@SAPEAVIRdlsDB@@PEAG000@Z; CRdlsDBJet::CreateInstance(ushort *,ushort *,ushort *,ushort *)
0x180083b53  mov     rbx, rax
0x180083b56  mov     rcx, [rbp+hKey]; hKey
0x180083b5a  call    cs:__imp_RegCloseKey
0x180083b61  nop     dword ptr [rax+rax+00h]
0x180083b66  mov     rax, rbx
0x180083b69  mov     rbx, [rsp+50h+arg_0]
0x180083b6e  mov     rsi, [rsp+50h+arg_8]
0x180083b73  mov     rdi, [rsp+50h+arg_10]
0x180083b78  mov     r14, [rsp+50h+arg_18]
0x180083b7d  add     rsp, 50h
0x180083b81  pop     rbp
0x180083b82  retn
```
