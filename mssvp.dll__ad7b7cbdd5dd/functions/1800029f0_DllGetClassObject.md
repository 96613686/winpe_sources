# DllGetClassObject

- ea: `0x1800029f0`
- end: `0x180002b43`
- name: `DllGetClassObject`
- size: `339`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800029f0`
- `0x18000a0f8`
- `0x18000bd18`
- `0x18003d010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180002a3a`
- `RPCRT4!NdrDllGetClassObject` at `0x180002a3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ac4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ac4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  HRESULT result; // eax
  __int64 v8; // rcx
  HRESULT v9; // r15d
  __int64 v10; // rdi
  _RTL_CRITICAL_SECTION *v11; // [rsp+30h] [rbp-48h] BYREF
  char v12; // [rsp+38h] [rbp-40h]

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  result = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  if ( result )
  {
    if ( !ppv )
      return -2147467261;
    *ppv = 0;
    v10 = qword_1800546E8;
    if ( qword_1800546E8 )
    {
      while ( 1 )
      {
        v8 = *(_QWORD *)v10;
        if ( !*(_QWORD *)v10 )
          break;
        if ( *(_QWORD *)(v10 + 16)
          && rclsid->Data1 == *(_DWORD *)v8
          && *(_DWORD *)&rclsid->Data2 == *(_DWORD *)(v8 + 4)
          && *(_DWORD *)rclsid->Data4 == *(_DWORD *)(v8 + 8)
          && *(_DWORD *)&rclsid->Data4[4] == *(_DWORD *)(v8 + 12) )
        {
          v9 = 0;
          if ( !*(_QWORD *)(v10 + 32) )
          {
            v11 = &CriticalSection;
            EnterCriticalSection(&CriticalSection);
            v12 = 1;
            if ( !*(_QWORD *)(v10 + 32) )
              v9 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v10 + 16))(
                     *(_QWORD *)(v10 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v10 + 32);
            ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v11);
          }
          v8 = *(_QWORD *)(v10 + 32);
          if ( v8 )
            v9 = (**(__int64 (__fastcall ***)(__int64, const IID *const, LPVOID *))v8)(v8, riid, ppv);
          if ( *ppv || v9 )
            return v9;
          return ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)v8, rclsid, riid, ppv);
        }
        v10 += 72;
      }
    }
    return ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)v8, rclsid, riid, ppv);
  }
  return result;
}

```

## disassembly

```asm
0x1800029f0  push    rbx
0x1800029f2  push    rbp
0x1800029f3  push    rsi
0x1800029f4  push    rdi
0x1800029f5  push    r14
0x1800029f7  push    r15
0x1800029f9  sub     rsp, 48h
0x1800029fd  mov     rbx, r8
0x180002a00  mov     rbp, rdx
0x180002a03  mov     rsi, rcx
0x180002a06  mov     rax, cs:aProxyFileList
0x180002a0d  mov     r8, [rax+8]
0x180002a11  mov     rax, [r8]
0x180002a14  test    rax, rax
0x180002a17  jz      short loc_180002A1C
0x180002a19  mov     rax, [rax]
0x180002a1c  lea     rcx, gPFactory
0x180002a23  mov     [rsp+78h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x180002a28  mov     [rsp+78h+pclsid], rax; pclsid
0x180002a2d  lea     r9, aProxyFileList; pProxyFileList
0x180002a34  mov     r8, rbx; ppv
0x180002a37  mov     rcx, rsi; rclsid
0x180002a3a  call    cs:__imp_NdrDllGetClassObject
0x180002a40  test    eax, eax
0x180002a42  jnz     short loc_180002A51
0x180002a44  add     rsp, 48h
0x180002a48  pop     r15
0x180002a4a  pop     r14
0x180002a4c  pop     rdi
0x180002a4d  pop     rsi
0x180002a4e  pop     rbp
0x180002a4f  pop     rbx
0x180002a50  retn
0x180002a51  test    rbx, rbx
0x180002a54  jnz     short loc_180002A61
0x180002a56  mov     r15d, 80004003h
0x180002a5c  jmp     loc_180002B33
0x180002a61  mov     qword ptr [rbx], 0
0x180002a68  mov     rdi, cs:qword_1800546E8
0x180002a6f  test    rdi, rdi
0x180002a72  jz      loc_180002B22
0x180002a78  mov     rcx, [rdi]
0x180002a7b  test    rcx, rcx
0x180002a7e  jz      loc_180002B22
0x180002a84  cmp     qword ptr [rdi+10h], 0
0x180002a89  jz      short loc_180002AA9
0x180002a8b  mov     eax, [rcx]
0x180002a8d  cmp     [rsi], eax
0x180002a8f  jnz     short loc_180002AA9
0x180002a91  mov     eax, [rcx+4]
0x180002a94  cmp     [rsi+4], eax
0x180002a97  jnz     short loc_180002AA9
0x180002a99  mov     eax, [rcx+8]
0x180002a9c  cmp     [rsi+8], eax
0x180002a9f  jnz     short loc_180002AA9
0x180002aa1  mov     eax, [rcx+0Ch]
0x180002aa4  cmp     [rsi+0Ch], eax
0x180002aa7  jz      short loc_180002AAF
0x180002aa9  add     rdi, 48h ; 'H'
0x180002aad  jmp     short loc_180002A78
0x180002aaf  xor     r15d, r15d
0x180002ab2  cmp     [rdi+20h], r15
0x180002ab6  jnz     short loc_180002AFA
0x180002ab8  lea     rcx, CriticalSection; lpCriticalSection
0x180002abf  mov     [rsp+78h+var_48], rcx
0x180002ac4  call    cs:__imp_EnterCriticalSection
0x180002aca  mov     [rsp+78h+var_40], 1
0x180002acf  cmp     [rdi+20h], r15
0x180002ad3  jnz     short loc_180002AF0
0x180002ad5  lea     r8, [rdi+20h]
0x180002ad9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180002ae0  mov     rcx, [rdi+18h]
0x180002ae4  mov     rax, [rdi+10h]
0x180002ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aed  mov     r15d, eax
0x180002af0  lea     rcx, [rsp+78h+var_48]
0x180002af5  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180002afa  mov     rcx, [rdi+20h]
0x180002afe  test    rcx, rcx
0x180002b01  jz      short loc_180002B17
0x180002b03  mov     rax, [rcx]
0x180002b06  mov     r8, rbx
0x180002b09  mov     rdx, rbp
0x180002b0c  mov     rax, [rax]
0x180002b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b14  mov     r15d, eax
0x180002b17  cmp     qword ptr [rbx], 0
0x180002b1b  jnz     short loc_180002B33
0x180002b1d  test    r15d, r15d
0x180002b20  jnz     short loc_180002B33
0x180002b22  mov     r9, rbx; void **
0x180002b25  mov     r8, rbp; struct _GUID *
0x180002b28  mov     rdx, rsi; struct _GUID *
0x180002b2b  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180002b30  mov     r15d, eax
0x180002b33  mov     eax, r15d
0x180002b36  add     rsp, 48h
0x180002b3a  pop     r15
0x180002b3c  pop     r14
0x180002b3e  pop     rdi
0x180002b3f  pop     rsi
0x180002b40  pop     rbp
0x180002b41  pop     rbx
0x180002b42  retn
```
