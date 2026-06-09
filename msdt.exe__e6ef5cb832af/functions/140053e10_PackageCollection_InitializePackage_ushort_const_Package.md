# PackageCollection::InitializePackage(ushort const *,Package *)

- ea: `0x140053e10`
- end: `0x1400540cf`
- name: `?InitializePackage@PackageCollection@@AEAAJPEBGPEAVPackage@@@Z`
- size: `703`
- prototype: `__int64 __fastcall(PackageCollection *__hidden this, LPCWSTR lpPathName, struct Package *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140052d60`
- `0x140053590`
- `0x14005421c`

## callees

- `0x140020420`
- `0x140053e10`
- `0x140054de0`
- `0x1400596a4`
- `0x140059ce0`
- `0x140059e6c`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140053f15`
- `KERNEL32!GetLastError` at `0x140053f56`
- `KERNEL32!GetLastError` at `0x140053f15`
- `KERNEL32!GetLastError` at `0x140053f56`
- `KERNEL32!SetDllDirectoryW` at `0x140053f05`
- `KERNEL32!SetDllDirectoryW` at `0x140053f46`
- `KERNEL32!SetDllDirectoryW` at `0x140053f05`
- `KERNEL32!SetDllDirectoryW` at `0x140053f46`
- `OLEAUT32!__imp_SysAllocString` at `0x140053eca`
- `OLEAUT32!__imp_SysAllocString` at `0x140053eca`
- `OLEAUT32!__imp_SysFreeString` at `0x14005407f`
- `OLEAUT32!__imp_SysFreeString` at `0x140054093`
- `OLEAUT32!__imp_SysFreeString` at `0x14005407f`
- `OLEAUT32!__imp_SysFreeString` at `0x140054093`
- `ole32!CoCreateInstance` at `0x140053fa2`
- `ole32!CoCreateInstance` at `0x140053fa2`

## pseudocode

```c
__int64 __fastcall PackageCollection::InitializePackage(
        PackageCollection *this,
        LPCWSTR lpPathName,
        struct Package *a3)
{
  OLECHAR *v3; // rsi
  int v7; // r9d
  signed int v8; // ebx
  int v9; // r12d
  int Answers; // eax
  unsigned __int16 *v11; // rbp
  signed int LastError; // eax
  signed int v13; // eax
  int Instance; // eax
  int v15; // r9d
  struct IScriptedDiagnosticExecution *ppv; // [rsp+68h] [rbp+10h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  bstrString = 0;
  ppv = 0;
  if ( !lpPathName )
  {
    v7 = 1262;
LABEL_3:
    v8 = -2147024809;
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::InitializePackage", v7, -2147024809);
    goto LABEL_43;
  }
  if ( !a3 )
  {
    v7 = 1263;
    goto LABEL_3;
  }
  v9 = *((_DWORD *)a3 + 27);
  if ( v9 )
  {
    Answers = Package::get_Answers(a3, &bstrString);
    v8 = Answers;
    if ( Answers < 0 )
    {
      v11 = 0;
      SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::InitializePackage", 1270, Answers);
      v3 = bstrString;
      goto LABEL_39;
    }
    v3 = bstrString;
  }
  v11 = SysAllocString(lpPathName);
  if ( v11 )
  {
    if ( *((_DWORD *)this + 16) )
    {
      v8 = -2147467260;
    }
    else
    {
      if ( SetDllDirectoryW(0) )
        goto LABEL_22;
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 >= 0 )
      {
LABEL_22:
        if ( SetDllDirectoryW(lpPathName) )
          goto LABEL_24;
        v13 = GetLastError();
        v8 = v13;
        if ( v13 > 0 )
          v8 = (unsigned __int16)v13 | 0x80070000;
        if ( v8 >= 0 )
        {
LABEL_24:
          Instance = CoCreateInstance(&CLSID_CScriptedDiag, 0, 0x15u, &IID_IScriptedDiagnosticExecution, (LPVOID *)&ppv);
          v8 = Instance;
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(struct IScriptedDiagnosticExecution *, unsigned __int16 *, _QWORD, OLECHAR *))(*(_QWORD *)ppv + 56LL))(
                         ppv,
                         v11,
                         *((_QWORD *)this + 7),
                         v3);
            v8 = Instance;
            if ( Instance >= 0 )
            {
              if ( Instance == 3932421 )
              {
                v8 = -2143551224;
                SdpDebugPrint(
                  1u,
                  "Met ERROR: %s:%d - hr = 0x%08X\n",
                  "PackageCollection::InitializePackage",
                  1306,
                  -2143551224);
                goto LABEL_39;
              }
              if ( v9 )
                *((_DWORD *)a3 + 28) = 1;
              *((_QWORD *)a3 + 2) = this;
              Instance = Package::set_Engine(a3, ppv);
              v8 = Instance;
              if ( Instance >= 0 )
              {
                Instance = Package::set_PackageLocation(a3, v11);
                v8 = Instance;
                if ( Instance >= 0 )
                {
                  Instance = PackageCollection::LoadPackageInfo(this, a3);
                  v8 = Instance;
                  if ( Instance >= 0 )
                    goto LABEL_39;
                  v15 = 1324;
                }
                else
                {
                  v15 = 1321;
                }
              }
              else
              {
                v15 = 1318;
              }
            }
            else
            {
              v15 = 1302;
            }
          }
          else
          {
            v15 = 1296;
          }
          SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::InitializePackage", v15, Instance);
          goto LABEL_39;
        }
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::InitializePackage", 1285, v8);
      }
      else
      {
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::InitializePackage", 1282, v8);
      }
    }
  }
  else
  {
    v8 = -2147024882;
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::InitializePackage", 1274, -2147024882);
  }
LABEL_39:
  if ( v3 )
    SysFreeString(v3);
  if ( v11 )
    SysFreeString(v11);
LABEL_43:
  if ( ppv )
    (*(void (__fastcall **)(struct IScriptedDiagnosticExecution *))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140053e10  mov     rax, rsp
0x140053e13  mov     [rax+8], rbx
0x140053e17  mov     [rax+18h], rbp
0x140053e1b  push    rsi
0x140053e1c  push    rdi
0x140053e1d  push    r12
0x140053e1f  push    r14
0x140053e21  push    r15
0x140053e23  sub     rsp, 30h
0x140053e27  xor     esi, esi
0x140053e29  mov     rdi, r8
0x140053e2c  mov     [rax+20h], rsi
0x140053e30  mov     r14, rdx
0x140053e33  mov     [rax+10h], rsi
0x140053e37  mov     r15, rcx
0x140053e3a  test    rdx, rdx
0x140053e3d  jnz     short loc_140053E6D
0x140053e3f  mov     r9d, 4EEh
0x140053e45  mov     eax, 80070057h
0x140053e4a  lea     r8, aPackagecollect_0; "PackageCollection::InitializePackage"
0x140053e51  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140053e58  mov     dword ptr [rsp+58h+ppv], eax
0x140053e5c  mov     ecx, 1; Level
0x140053e61  mov     ebx, eax
0x140053e63  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140053e68  jmp     loc_14005409F
0x140053e6d  test    rdi, rdi
0x140053e70  jnz     short loc_140053E7A
0x140053e72  mov     r9d, 4EFh
0x140053e78  jmp     short loc_140053E45
0x140053e7a  mov     r12d, [r8+6Ch]
0x140053e7e  test    r12d, r12d
0x140053e81  jz      short loc_140053EC7
0x140053e83  lea     rdx, [rsp+58h+bstrString]; unsigned __int16 **
0x140053e88  mov     rcx, rdi; this
0x140053e8b  call    ?get_Answers@Package@@QEAAJPEAPEAG@Z; Package::get_Answers(ushort * *)
0x140053e90  mov     ebx, eax
0x140053e92  test    eax, eax
0x140053e94  jns     short loc_140053EC2
0x140053e96  xor     ebp, ebp
0x140053e98  mov     dword ptr [rsp+58h+ppv], eax
0x140053e9c  mov     r9d, 4F6h
0x140053ea2  lea     r8, aPackagecollect_0; "PackageCollection::InitializePackage"
0x140053ea9  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140053eb0  lea     ecx, [rbp+1]; Level
0x140053eb3  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140053eb8  mov     rsi, [rsp+58h+bstrString]
0x140053ebd  jmp     loc_140054077
0x140053ec2  mov     rsi, [rsp+58h+bstrString]
0x140053ec7  mov     rcx, r14; psz
0x140053eca  call    cs:__imp_SysAllocString
0x140053ed1  nop     dword ptr [rax+rax+00h]
0x140053ed6  mov     rbp, rax
0x140053ed9  test    rax, rax
0x140053edc  jnz     short loc_140053EF2
0x140053ede  mov     ebx, 8007000Eh
0x140053ee3  mov     r9d, 4FAh
0x140053ee9  mov     dword ptr [rsp+58h+ppv], ebx
0x140053eed  jmp     loc_14005405F
0x140053ef2  cmp     dword ptr [r15+40h], 0
0x140053ef7  jz      short loc_140053F03
0x140053ef9  mov     ebx, 80004004h
0x140053efe  jmp     loc_140054077
0x140053f03  xor     ecx, ecx; lpPathName
0x140053f05  call    cs:__imp_SetDllDirectoryW
0x140053f0c  nop     dword ptr [rax+rax+00h]
0x140053f11  test    eax, eax
0x140053f13  jnz     short loc_140053F43
0x140053f15  call    cs:__imp_GetLastError
0x140053f1c  nop     dword ptr [rax+rax+00h]
0x140053f21  mov     ebx, eax
0x140053f23  test    eax, eax
0x140053f25  jle     short loc_140053F30
0x140053f27  movzx   ebx, ax
0x140053f2a  or      ebx, 80070000h
0x140053f30  test    ebx, ebx
0x140053f32  jns     short loc_140053F43
0x140053f34  mov     dword ptr [rsp+58h+ppv], ebx
0x140053f38  mov     r9d, 502h
0x140053f3e  jmp     loc_14005405F
0x140053f43  mov     rcx, r14; lpPathName
0x140053f46  call    cs:__imp_SetDllDirectoryW
0x140053f4d  nop     dword ptr [rax+rax+00h]
0x140053f52  test    eax, eax
0x140053f54  jnz     short loc_140053F84
0x140053f56  call    cs:__imp_GetLastError
0x140053f5d  nop     dword ptr [rax+rax+00h]
0x140053f62  mov     ebx, eax
0x140053f64  test    eax, eax
0x140053f66  jle     short loc_140053F71
0x140053f68  movzx   ebx, ax
0x140053f6b  or      ebx, 80070000h
0x140053f71  test    ebx, ebx
0x140053f73  jns     short loc_140053F84
0x140053f75  mov     dword ptr [rsp+58h+ppv], ebx
0x140053f79  mov     r9d, 505h
0x140053f7f  jmp     loc_14005405F
0x140053f84  xor     edx, edx; pUnkOuter
0x140053f86  lea     rax, [rsp+58h+arg_8]
0x140053f8b  lea     r9, IID_IScriptedDiagnosticExecution; riid
0x140053f92  mov     [rsp+58h+ppv], rax; ppv
0x140053f97  lea     rcx, CLSID_CScriptedDiag; rclsid
0x140053f9e  lea     r8d, [rdx+15h]; dwClsContext
0x140053fa2  call    cs:__imp_CoCreateInstance
0x140053fa9  nop     dword ptr [rax+rax+00h]
0x140053fae  mov     ebx, eax
0x140053fb0  test    eax, eax
0x140053fb2  jns     short loc_140053FBF
0x140053fb4  mov     r9d, 510h
0x140053fba  jmp     loc_14005405B
0x140053fbf  mov     rcx, [rsp+58h+arg_8]
0x140053fc4  mov     r9, rsi
0x140053fc7  mov     r8, [r15+38h]
0x140053fcb  mov     rdx, rbp
0x140053fce  mov     rax, [rcx]
0x140053fd1  mov     rax, [rax+38h]
0x140053fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053fda  mov     ebx, eax
0x140053fdc  test    eax, eax
0x140053fde  jns     short loc_140053FE8
0x140053fe0  mov     r9d, 516h
0x140053fe6  jmp     short loc_14005405B
0x140053fe8  cmp     eax, 3C0105h
0x140053fed  jnz     short loc_140054000
0x140053fef  mov     ebx, 803C0108h
0x140053ff4  mov     r9d, 51Ah
0x140053ffa  mov     dword ptr [rsp+58h+ppv], ebx
0x140053ffe  jmp     short loc_14005405F
0x140054000  test    r12d, r12d
0x140054003  jz      short loc_14005400C
0x140054005  mov     dword ptr [rdi+70h], 1
0x14005400c  mov     [rdi+10h], r15
0x140054010  mov     rdx, [rsp+58h+arg_8]; struct IScriptedDiagnosticExecution *
0x140054015  mov     rcx, rdi; this
0x140054018  call    ?set_Engine@Package@@QEAAJPEAUIScriptedDiagnosticExecution@@@Z; Package::set_Engine(IScriptedDiagnosticExecution *)
0x14005401d  mov     ebx, eax
0x14005401f  test    eax, eax
0x140054021  jns     short loc_14005402B
0x140054023  mov     r9d, 526h
0x140054029  jmp     short loc_14005405B
0x14005402b  mov     rdx, rbp; unsigned __int16 *
0x14005402e  mov     rcx, rdi; this
0x140054031  call    ?set_PackageLocation@Package@@QEAAJPEBG@Z; Package::set_PackageLocation(ushort const *)
0x140054036  mov     ebx, eax
0x140054038  test    eax, eax
0x14005403a  jns     short loc_140054044
0x14005403c  mov     r9d, 529h
0x140054042  jmp     short loc_14005405B
0x140054044  mov     rdx, rdi; struct Package *
0x140054047  mov     rcx, r15; this
0x14005404a  call    ?LoadPackageInfo@PackageCollection@@AEAAJPEAVPackage@@@Z; PackageCollection::LoadPackageInfo(Package *)
0x14005404f  mov     ebx, eax
0x140054051  test    eax, eax
0x140054053  jns     short loc_140054077
0x140054055  mov     r9d, 52Ch
0x14005405b  mov     dword ptr [rsp+58h+ppv], eax
0x14005405f  lea     r8, aPackagecollect_0; "PackageCollection::InitializePackage"
0x140054066  mov     ecx, 1; Level
0x14005406b  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140054072  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140054077  test    rsi, rsi
0x14005407a  jz      short loc_14005408B
0x14005407c  mov     rcx, rsi; bstrString
0x14005407f  call    cs:__imp_SysFreeString
0x140054086  nop     dword ptr [rax+rax+00h]
0x14005408b  test    rbp, rbp
0x14005408e  jz      short loc_14005409F
0x140054090  mov     rcx, rbp; bstrString
0x140054093  call    cs:__imp_SysFreeString
0x14005409a  nop     dword ptr [rax+rax+00h]
0x14005409f  mov     rcx, [rsp+58h+arg_8]
0x1400540a4  test    rcx, rcx
0x1400540a7  jz      short loc_1400540B5
0x1400540a9  mov     rax, [rcx]
0x1400540ac  mov     rax, [rax+10h]
0x1400540b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400540b5  mov     rbp, [rsp+58h+arg_10]
0x1400540ba  mov     eax, ebx
0x1400540bc  mov     rbx, [rsp+58h+arg_0]
0x1400540c1  add     rsp, 30h
0x1400540c5  pop     r15
0x1400540c7  pop     r14
0x1400540c9  pop     r12
0x1400540cb  pop     rdi
0x1400540cc  pop     rsi
0x1400540cd  retn
```
