# PackageCollection::Diagnose(IPackage *)

- ea: `0x140053590`
- end: `0x14005379d`
- name: `?Diagnose@PackageCollection@@UEAAJPEAVIPackage@@@Z`
- size: `525`
- prototype: `__int64 __fastcall(PackageCollection *__hidden this, struct IPackage *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x140020420`
- `0x140053590`
- `0x140053e10`
- `0x1400591ac`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140053669`
- `KERNEL32!GetLastError` at `0x1400536a8`
- `KERNEL32!GetLastError` at `0x140053669`
- `KERNEL32!GetLastError` at `0x1400536a8`
- `KERNEL32!SetDllDirectoryW` at `0x140053653`
- `KERNEL32!SetDllDirectoryW` at `0x140053698`
- `KERNEL32!SetDllDirectoryW` at `0x140053653`
- `KERNEL32!SetDllDirectoryW` at `0x140053698`
- `OLEAUT32!__imp_SysFreeString` at `0x140053766`
- `OLEAUT32!__imp_SysFreeString` at `0x140053783`
- `OLEAUT32!__imp_SysFreeString` at `0x140053766`
- `OLEAUT32!__imp_SysFreeString` at `0x140053783`

## pseudocode

```c
__int64 __fastcall PackageCollection::Diagnose(PackageCollection *this, struct IPackage *a2)
{
  signed int v4; // ebx
  int v5; // r14d
  int updated; // eax
  int v7; // r9d
  signed int LastError; // eax
  signed int v9; // eax
  LPCWSTR lpPathName; // [rsp+68h] [rbp+38h] BYREF
  __int64 v12; // [rsp+70h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+48h] BYREF

  lpPathName = 0;
  bstrString = 0;
  v12 = 0;
  if ( a2 )
  {
    v4 = 0;
    if ( !*((_DWORD *)a2 + 27) )
      return (unsigned int)v4;
    v5 = *((_DWORD *)a2 + 28);
    updated = (*(__int64 (__fastcall **)(struct IPackage *, LPCWSTR *))(*(_QWORD *)a2 + 80LL))(a2, &lpPathName);
    v4 = updated;
    if ( updated >= 0 )
    {
      if ( v5 || (updated = PackageCollection::InitializePackage(this, lpPathName, a2), v4 = updated, updated >= 0) )
      {
        updated = (*(__int64 (__fastcall **)(struct IPackage *, __int64 *))(*(_QWORD *)a2 + 96LL))(a2, &v12);
        v4 = updated;
        if ( updated >= 0 )
        {
          if ( !SetDllDirectoryW(0) )
          {
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
            if ( v4 < 0 )
            {
              SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::Diagnose", 592, v4);
              goto LABEL_28;
            }
          }
          if ( !SetDllDirectoryW(lpPathName) )
          {
            v9 = GetLastError();
            v4 = v9;
            if ( v9 > 0 )
              v4 = (unsigned __int16)v9 | 0x80070000;
            if ( v4 < 0 )
            {
              SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::Diagnose", 595, v4);
              goto LABEL_28;
            }
          }
          if ( *((_DWORD *)this + 16) )
          {
            v4 = -2147467260;
            SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::Diagnose", 599, -2147467260);
            goto LABEL_28;
          }
          updated = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v12 + 144LL))(v12, &bstrString);
          v4 = updated;
          if ( updated >= 0 )
          {
            updated = Package::UpdateRootCausesWithDiagnoseXml(a2, bstrString);
            v4 = updated;
            if ( updated >= 0 )
              goto LABEL_28;
            v7 = 609;
          }
          else
          {
            v7 = 603;
          }
        }
        else
        {
          v7 = 589;
        }
      }
      else
      {
        v7 = 585;
      }
    }
    else
    {
      v7 = 581;
    }
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::Diagnose", v7, updated);
    goto LABEL_28;
  }
  v4 = -2147024809;
  SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::Diagnose", 566, -2147024809);
LABEL_28:
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( lpPathName )
  {
    SysFreeString((BSTR)lpPathName);
    lpPathName = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140053590  push    rbp
0x140053592  push    rbx
0x140053593  push    rsi
0x140053594  push    rdi
0x140053595  push    r14
0x140053597  mov     rbp, rsp
0x14005359a  sub     rsp, 30h
0x14005359e  mov     [rbp+lpPathName], 0
0x1400535a6  mov     rdi, rdx
0x1400535a9  mov     [rbp+bstrString], 0
0x1400535b1  mov     rsi, rcx
0x1400535b4  mov     [rbp+arg_10], 0
0x1400535bc  test    rdx, rdx
0x1400535bf  jnz     short loc_1400535D5
0x1400535c1  mov     ebx, 80070057h
0x1400535c6  mov     r9d, 236h
0x1400535cc  mov     [rsp+30h+var_10], ebx
0x1400535d0  jmp     loc_140053728
0x1400535d5  xor     ebx, ebx
0x1400535d7  cmp     [rdx+6Ch], ebx
0x1400535da  jz      loc_14005378F
0x1400535e0  mov     r14d, [rdx+70h]
0x1400535e4  mov     rax, [rdx]
0x1400535e7  mov     rcx, rdi
0x1400535ea  lea     rdx, [rbp+lpPathName]
0x1400535ee  mov     rax, [rax+50h]
0x1400535f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400535f7  mov     ebx, eax
0x1400535f9  test    eax, eax
0x1400535fb  jns     short loc_140053608
0x1400535fd  mov     r9d, 245h
0x140053603  jmp     loc_140053724
0x140053608  test    r14d, r14d
0x14005360b  jnz     short loc_14005362D
0x14005360d  mov     rdx, [rbp+lpPathName]; lpPathName
0x140053611  mov     r8, rdi; struct Package *
0x140053614  mov     rcx, rsi; this
0x140053617  call    ?InitializePackage@PackageCollection@@AEAAJPEBGPEAVPackage@@@Z; PackageCollection::InitializePackage(ushort const *,Package *)
0x14005361c  mov     ebx, eax
0x14005361e  test    eax, eax
0x140053620  jns     short loc_14005362D
0x140053622  mov     r9d, 249h
0x140053628  jmp     loc_140053724
0x14005362d  mov     rax, [rdi]
0x140053630  lea     rdx, [rbp+arg_10]
0x140053634  mov     rcx, rdi
0x140053637  mov     rax, [rax+60h]
0x14005363b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053640  mov     ebx, eax
0x140053642  test    eax, eax
0x140053644  jns     short loc_140053651
0x140053646  mov     r9d, 24Dh
0x14005364c  jmp     loc_140053724
0x140053651  xor     ecx, ecx; lpPathName
0x140053653  call    cs:__imp_SetDllDirectoryW
0x14005365a  nop     dword ptr [rax+rax+00h]
0x14005365f  mov     r14d, 80070000h
0x140053665  test    eax, eax
0x140053667  jnz     short loc_140053694
0x140053669  call    cs:__imp_GetLastError
0x140053670  nop     dword ptr [rax+rax+00h]
0x140053675  mov     ebx, eax
0x140053677  test    eax, eax
0x140053679  jle     short loc_140053681
0x14005367b  movzx   ebx, ax
0x14005367e  or      ebx, r14d
0x140053681  test    ebx, ebx
0x140053683  jns     short loc_140053694
0x140053685  mov     [rsp+30h+var_10], ebx
0x140053689  mov     r9d, 250h
0x14005368f  jmp     loc_140053728
0x140053694  mov     rcx, [rbp+lpPathName]; lpPathName
0x140053698  call    cs:__imp_SetDllDirectoryW
0x14005369f  nop     dword ptr [rax+rax+00h]
0x1400536a4  test    eax, eax
0x1400536a6  jnz     short loc_1400536D0
0x1400536a8  call    cs:__imp_GetLastError
0x1400536af  nop     dword ptr [rax+rax+00h]
0x1400536b4  mov     ebx, eax
0x1400536b6  test    eax, eax
0x1400536b8  jle     short loc_1400536C0
0x1400536ba  movzx   ebx, ax
0x1400536bd  or      ebx, r14d
0x1400536c0  test    ebx, ebx
0x1400536c2  jns     short loc_1400536D0
0x1400536c4  mov     [rsp+30h+var_10], ebx
0x1400536c8  mov     r9d, 253h
0x1400536ce  jmp     short loc_140053728
0x1400536d0  cmp     dword ptr [rsi+40h], 0
0x1400536d4  jz      short loc_1400536E7
0x1400536d6  mov     ebx, 80004004h
0x1400536db  mov     r9d, 257h
0x1400536e1  mov     [rsp+30h+var_10], ebx
0x1400536e5  jmp     short loc_140053728
0x1400536e7  mov     rcx, [rbp+arg_10]
0x1400536eb  lea     rdx, [rbp+bstrString]
0x1400536ef  mov     rax, [rcx]
0x1400536f2  mov     rax, [rax+90h]
0x1400536f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400536fe  mov     ebx, eax
0x140053700  test    eax, eax
0x140053702  jns     short loc_14005370C
0x140053704  mov     r9d, 25Bh
0x14005370a  jmp     short loc_140053724
0x14005370c  mov     rdx, [rbp+bstrString]; psz
0x140053710  mov     rcx, rdi; this
0x140053713  call    ?UpdateRootCausesWithDiagnoseXml@Package@@QEAAJPEAG@Z; Package::UpdateRootCausesWithDiagnoseXml(ushort *)
0x140053718  mov     ebx, eax
0x14005371a  test    eax, eax
0x14005371c  jns     short loc_140053740
0x14005371e  mov     r9d, 261h
0x140053724  mov     [rsp+30h+var_10], eax
0x140053728  lea     r8, aPackagecollect_7; "PackageCollection::Diagnose"
0x14005372f  mov     ecx, 1; Level
0x140053734  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x14005373b  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140053740  mov     rcx, [rbp+arg_10]
0x140053744  test    rcx, rcx
0x140053747  jz      short loc_14005375D
0x140053749  mov     rax, [rcx]
0x14005374c  mov     rax, [rax+10h]
0x140053750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053755  mov     [rbp+arg_10], 0
0x14005375d  mov     rcx, [rbp+lpPathName]; bstrString
0x140053761  test    rcx, rcx
0x140053764  jz      short loc_14005377A
0x140053766  call    cs:__imp_SysFreeString
0x14005376d  nop     dword ptr [rax+rax+00h]
0x140053772  mov     [rbp+lpPathName], 0
0x14005377a  mov     rcx, [rbp+bstrString]; bstrString
0x14005377e  test    rcx, rcx
0x140053781  jz      short loc_14005378F
0x140053783  call    cs:__imp_SysFreeString
0x14005378a  nop     dword ptr [rax+rax+00h]
0x14005378f  mov     eax, ebx
0x140053791  add     rsp, 30h
0x140053795  pop     r14
0x140053797  pop     rdi
0x140053798  pop     rsi
0x140053799  pop     rbx
0x14005379a  pop     rbp
0x14005379b  retn
```
