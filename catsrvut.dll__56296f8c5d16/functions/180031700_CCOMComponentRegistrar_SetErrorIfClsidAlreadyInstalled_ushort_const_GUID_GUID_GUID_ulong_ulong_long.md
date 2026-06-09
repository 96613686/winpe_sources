# CCOMComponentRegistrar::SetErrorIfClsidAlreadyInstalled(ushort const *,_GUID,_GUID,_GUID,ulong *,ulong *,long *)

- ea: `0x180031700`
- end: `0x180031883`
- name: `?SetErrorIfClsidAlreadyInstalled@CCOMComponentRegistrar@@UEAAJPEBGU_GUID@@11PEAK2PEAJ@Z`
- size: `387`
- prototype: `__int64 __fastcall(CCOMComponentRegistrar *__hidden this, const unsigned __int16 *, struct _GUID *, struct _GUID *, struct _GUID *, unsigned int *, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000d9d4`
- `0x18002f750`
- `0x180031700`
- `0x1800326d4`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031790`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031790`
- `api-ms-win-core-com-private-l1-1-0!CoGetModuleType` at `0x180031778`
- `api-ms-win-core-com-private-l1-1-0!CoGetModuleType` at `0x180031778`

## pseudocode

```c
__int64 __fastcall CCOMComponentRegistrar::SetErrorIfClsidAlreadyInstalled(
        CCOMComponentRegistrar *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        struct _GUID *a4,
        struct _GUID *a5,
        unsigned int *a6,
        unsigned int *a7,
        int *a8)
{
  int ModuleType; // ebx
  int v12; // ebx
  LPVOID v13; // rax
  __int64 v14; // rax
  __int64 v15; // r10
  __int64 (__fastcall *v16)(__int64, struct _GUID *, struct _GUID *, _QWORD, _DWORD, int, __int128 *); // rax
  __int64 v17; // rcx
  int v18; // r9d
  int v20; // [rsp+40h] [rbp-38h] BYREF
  struct _GUID *v21; // [rsp+48h] [rbp-30h] BYREF
  int v22; // [rsp+50h] [rbp-28h] BYREF
  __int64 v23; // [rsp+58h] [rbp-20h]
  __int128 v24; // [rsp+60h] [rbp-18h] BYREF

  v21 = a5;
  v22 = 1;
  v23 = 0;
  v20 = 0;
  if ( a2 && a6 && a7 && a8 )
  {
    ModuleType = CoGetModuleType(a2, &v20);
    if ( ModuleType >= 0 )
    {
      v12 = v20;
      v13 = CoTaskMemAlloc(0x90u);
      if ( v13
        && (v14 = CRegDBComponentProvider::CRegDBComponentProvider((__int64)v13, v12), v23 = v14, (v15 = v14) != 0) )
      {
        v16 = *(__int64 (__fastcall **)(__int64, struct _GUID *, struct _GUID *, _QWORD, _DWORD, int, __int128 *))(*(_QWORD *)v14 + 8LL);
        v24 = (__int128)*a4;
        ModuleType = v16(v15, a3, v21, 0, 0, 1, &v24);
        switch ( ModuleType )
        {
          case -2146368509:
            goto LABEL_12;
          case -2146368508:
            *a6 |= 0x200u;
            *a7 |= 0x10u;
            *a8 = -2146368508;
            goto LABEL_12;
          case 0:
LABEL_12:
            v18 = *((_DWORD *)this + 42);
            LODWORD(v21) = 0;
            ModuleType = CCOMComponentRegistrar::IsClassLegacyConfigured(v17, 0, (__int64)a3, v18, &v21);
            if ( !ModuleType )
            {
              if ( (_DWORD)v21 )
              {
                *a6 |= 0x200u;
                *a7 |= 0x10u;
                *a8 = -2146368508;
              }
            }
            break;
        }
      }
      else
      {
        ModuleType = -2147024882;
      }
    }
    CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v22);
    return (unsigned int)ModuleType;
  }
  CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>((__int64)&v22);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180031700  push    rbp
0x180031702  push    rbx
0x180031703  push    rsi
0x180031704  push    rdi
0x180031705  push    r12
0x180031707  push    r13
0x180031709  push    r14
0x18003170b  push    r15
0x18003170d  mov     rbp, rsp
0x180031710  sub     rsp, 78h
0x180031714  mov     rdi, [rbp+arg_28]
0x180031718  mov     r13, rcx
0x18003171b  mov     rcx, [rbp+arg_20]
0x18003171f  mov     r12, r9
0x180031722  mov     rsi, [rbp+arg_30]
0x180031726  mov     r15, r8
0x180031729  mov     r14, [rbp+arg_38]
0x180031730  mov     rax, rdx
0x180031733  mov     [rbp+var_30], rcx
0x180031737  mov     [rbp+var_28], 1
0x18003173e  mov     [rbp+var_20], 0
0x180031746  mov     [rbp+var_38], 0
0x18003174d  test    rdx, rdx
0x180031750  jz      loc_180031864
0x180031756  test    rdi, rdi
0x180031759  jz      loc_180031864
0x18003175f  test    rsi, rsi
0x180031762  jz      loc_180031864
0x180031768  test    r14, r14
0x18003176b  jz      loc_180031864
0x180031771  lea     rdx, [rbp+var_38]
0x180031775  mov     rcx, rax
0x180031778  call    cs:__imp_CoGetModuleType
0x18003177e  mov     ebx, eax
0x180031780  test    eax, eax
0x180031782  js      loc_180031857
0x180031788  mov     ebx, [rbp+var_38]
0x18003178b  mov     ecx, 90h; cb
0x180031790  call    cs:__imp_CoTaskMemAlloc
0x180031796  test    rax, rax
0x180031799  jz      loc_180031852
0x18003179f  mov     edx, ebx
0x1800317a1  mov     rcx, rax
0x1800317a4  call    ??0CRegDBComponentProvider@@QEAA@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@@Z; CRegDBComponentProvider::CRegDBComponentProvider(__MIDL___MIDL_itf_registrar_0000_0000_0001)
0x1800317a9  mov     [rbp+var_20], rax
0x1800317ad  mov     r10, rax
0x1800317b0  test    rax, rax
0x1800317b3  jz      loc_180031852
0x1800317b9  mov     rcx, [rax]
0x1800317bc  xor     r9d, r9d
0x1800317bf  movups  xmm0, xmmword ptr [r12]
0x1800317c4  mov     r8, [rbp+var_30]
0x1800317c8  xor     r12d, r12d
0x1800317cb  mov     rdx, r15
0x1800317ce  mov     rax, [rcx+8]
0x1800317d2  lea     rcx, [rbp+var_18]
0x1800317d6  mov     [rsp+78h+var_48], rcx
0x1800317db  mov     rcx, r10
0x1800317de  mov     [rsp+78h+var_50], 1
0x1800317e6  mov     dword ptr [rsp+78h+var_58], r12d
0x1800317eb  movdqu  [rbp+var_18], xmm0
0x1800317f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800317f5  mov     ebx, eax
0x1800317f7  mov     eax, 80110404h
0x1800317fc  cmp     ebx, 80110403h
0x180031802  jz      short loc_180031818
0x180031804  cmp     ebx, eax
0x180031806  jnz     short loc_180031814
0x180031808  bts     dword ptr [rdi], 9
0x18003180c  or      dword ptr [rsi], 10h
0x18003180f  mov     [r14], eax
0x180031812  jmp     short loc_180031818
0x180031814  test    ebx, ebx
0x180031816  jnz     short loc_180031857
0x180031818  mov     r9d, [r13+0A8h]
0x18003181f  lea     rax, [rbp+var_30]
0x180031823  mov     r8, r15
0x180031826  mov     [rsp+78h+var_58], rax
0x18003182b  xor     edx, edx
0x18003182d  mov     dword ptr [rbp+var_30], r12d
0x180031831  call    ?IsClassLegacyConfigured@CCOMComponentRegistrar@@AEAAJPEAUISimpleTableDispenser@@PEAU_GUID@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@PEAH@Z; CCOMComponentRegistrar::IsClassLegacyConfigured(ISimpleTableDispenser *,_GUID *,__MIDL___MIDL_itf_registrar_0000_0000_0001,int *)
0x180031836  mov     ebx, eax
0x180031838  test    eax, eax
0x18003183a  jnz     short loc_180031857
0x18003183c  cmp     dword ptr [rbp+var_30], r12d
0x180031840  jz      short loc_180031857
0x180031842  bts     dword ptr [rdi], 9
0x180031846  or      dword ptr [rsi], 10h
0x180031849  mov     dword ptr [r14], 80110404h
0x180031850  jmp     short loc_180031857
0x180031852  mov     ebx, 8007000Eh
0x180031857  lea     rcx, [rbp+var_28]
0x18003185b  call    ??1?$CPtr@VCRegDBProvider@@@@QEAA@XZ; CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>(void)
0x180031860  mov     eax, ebx
0x180031862  jmp     short loc_180031872
0x180031864  lea     rcx, [rbp+var_28]
0x180031868  call    ??1?$CPtr@VCRegDBProvider@@@@QEAA@XZ; CPtr<CRegDBProvider>::~CPtr<CRegDBProvider>(void)
0x18003186d  mov     eax, 80070057h
0x180031872  add     rsp, 78h
0x180031876  pop     r15
0x180031878  pop     r14
0x18003187a  pop     r13
0x18003187c  pop     r12
0x18003187e  pop     rdi
0x18003187f  pop     rsi
0x180031880  pop     rbx
0x180031881  pop     rbp
0x180031882  retn
```
