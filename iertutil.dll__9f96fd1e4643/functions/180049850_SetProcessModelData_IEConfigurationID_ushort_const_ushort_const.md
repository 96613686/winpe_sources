# SetProcessModelData(IEConfigurationID,ushort const *,ushort const *)

- ea: `0x180049850`
- end: `0x180049af5`
- name: `?SetProcessModelData@@YAJW4IEConfigurationID@@PEBG1@Z`
- size: `677`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180018410`
- `0x18001d0f0`
- `0x180031f00`
- `0x1800323f0`
- `0x180032580`
- `0x180049850`
- `0x18004c320`
- `0x180051f30`
- `0x18005e8e4`
- `0x180060830`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004988e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004988e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180049aa1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180049aa1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180049907`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18004993f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180049907`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18004993f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049a0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049a0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800498e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049923`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800498e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049923`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800498bc`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800498d9`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800498bc`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800498d9`

## string_xrefs

- `0x18004996f`: `onecoreuap\inetcore\iertutil\ieconfiguration.cpp`

## pseudocode

```c
__int64 __fastcall SetProcessModelData(unsigned int a1, __int64 a2, const unsigned __int16 *a3)
{
  int ProcessAppContainerSIDStrW; // ebx
  DWORD LastError; // eax
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdi
  __int64 v11; // r8
  __int64 v12; // r8
  const unsigned __int16 *v13; // rdx
  struct IBrowsingEnvironment *CorrectBrowsingEnvironment; // r12
  __int64 (__fastcall *v15)(struct IBrowsingEnvironment *, _QWORD, __int64, __int64, __int64, __int64, HKEY *); // r15
  __int64 String; // r14
  __int64 v17; // rsi
  char Bool; // di
  char v19; // bl
  DWORD CurrentProcessId; // eax
  __int64 v21; // r9
  __int64 v22; // r8
  int v24; // [rsp+20h] [rbp-38h]
  HKEY hKey; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  HKEY phkResult; // [rsp+B8h] [rbp+60h] BYREF

  ProcessAppContainerSIDStrW = 0;
  if ( !byte_180298EE8 )
  {
    IEConfiguration_GetDWORD(268435516);
    LastError = GetLastError();
    if ( a1 == 268435519 )
    {
      if ( LastError == 2 )
      {
        phkResult = 0;
        if ( RegOpenKeyW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Internet Explorer\\SpartanPlan", &phkResult) )
        {
          InitOnceExecuteOnce(&stru_180299FB8, InitOnceDeviceFamily, 0, 0);
          a1 = 268435528 - (byte_180298C9C != 0);
        }
        else
        {
          hKey = 0;
          if ( RegOpenKeyW(phkResult, L"MIL", &hKey) )
          {
            InitOnceExecuteOnce(&stru_180299FB8, InitOnceDeviceFamily, 0, 0);
            a1 = (byte_180298C9C != 0) + 268435527;
          }
          else
          {
            RegCloseKey(hKey);
            a1 = 268435531;
          }
          RegCloseKey(phkResult);
        }
LABEL_11:
        LOBYTE(v8) = 1;
        v9 = IEConfiguration_SetBool(a1, v8);
        ProcessAppContainerSIDStrW = v9;
        if ( v9 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0xB53,
            (unsigned int)"onecoreuap\\inetcore\\iertutil\\ieconfiguration.cpp",
            (const char *)(unsigned int)v9,
            v24);
      }
    }
    else if ( LastError == 2 )
    {
      goto LABEL_11;
    }
    byte_180298EE8 = 1;
  }
  if ( (unsigned __int8)IEConfiguration_GetBool(268435519) )
  {
    if ( a2 )
    {
      v10 = -1;
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(a2 + 2 * v11) );
      ProcessAppContainerSIDStrW = IEConfiguration_SetString(268435506, a2);
      if ( ProcessAppContainerSIDStrW < 0 )
        return (unsigned int)ProcessAppContainerSIDStrW;
    }
    else
    {
      phkResult = 0;
      ProcessAppContainerSIDStrW = GetProcessAppContainerSIDStrW(0, (unsigned __int16 **)&phkResult);
      if ( ProcessAppContainerSIDStrW < 0 )
        return (unsigned int)ProcessAppContainerSIDStrW;
      v10 = -1;
      v12 = -1;
      do
        ++v12;
      while ( *((_WORD *)phkResult + v12) );
      IEConfiguration_SetString(268435506, phkResult);
      LocalFree(phkResult);
    }
    if ( a3 )
    {
      do
        ++v10;
      while ( a3[v10] );
      v13 = a3;
    }
    else
    {
      v13 = L"Spartan_Authority_Package_Moniker_TBD";
    }
    ProcessAppContainerSIDStrW = IEConfiguration_SetString(268435507, v13);
  }
  if ( ProcessAppContainerSIDStrW >= 0 && !(unsigned int)IEConfiguration_GetDWORD(536870930) )
  {
    LODWORD(phkResult) = 0;
    CorrectBrowsingEnvironment = GetCorrectBrowsingEnvironment();
    v15 = *(__int64 (__fastcall **)(struct IBrowsingEnvironment *, _QWORD, __int64, __int64, __int64, __int64, HKEY *))(*(_QWORD *)CorrectBrowsingEnvironment + 88LL);
    String = IEConfiguration_GetString(268435507);
    v17 = IEConfiguration_GetString(268435506);
    Bool = IEConfiguration_GetBool(268435520);
    v19 = IEConfiguration_GetBool(268435519);
    CurrentProcessId = GetCurrentProcessId();
    LOBYTE(v21) = Bool;
    LOBYTE(v22) = v19;
    ProcessAppContainerSIDStrW = v15(CorrectBrowsingEnvironment, CurrentProcessId, v22, v21, v17, String, &phkResult);
    if ( ProcessAppContainerSIDStrW >= 0 )
      return (unsigned int)IEConfiguration_SetDWORD(536870930, (unsigned int)phkResult);
  }
  return (unsigned int)ProcessAppContainerSIDStrW;
}

```

## disassembly

```asm
0x180049850  push    rbp
0x180049852  push    rbx
0x180049853  push    rsi
0x180049854  push    rdi
0x180049855  push    r12
0x180049857  push    r13
0x180049859  push    r14
0x18004985b  push    r15
0x18004985d  mov     rbp, rsp
0x180049860  sub     rsp, 58h
0x180049864  xor     r13d, r13d
0x180049867  mov     r14, r8
0x18004986a  cmp     cs:byte_180298EE8, r13b
0x180049871  mov     rsi, rdx
0x180049874  mov     edi, ecx
0x180049876  mov     ebx, r13d
0x180049879  mov     r15d, 1000003Fh
0x18004987f  jnz     loc_18004998B
0x180049885  lea     ecx, [r15-3]
0x180049889  call    ?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18004988e  call    cs:__imp_GetLastError
0x180049894  cmp     edi, r15d
0x180049897  jnz     loc_180049957
0x18004989d  cmp     eax, 2
0x1800498a0  jnz     loc_180049984
0x1800498a6  lea     r8, [rbp+phkResult]; phkResult
0x1800498aa  mov     [rbp+phkResult], r13
0x1800498ae  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Internet Explorer"...
0x1800498b5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800498bc  call    cs:__imp_RegOpenKeyW
0x1800498c2  test    eax, eax
0x1800498c4  jnz     short loc_18004992B
0x1800498c6  mov     rcx, [rbp+phkResult]; hKey
0x1800498ca  lea     r8, [rbp+hKey]; phkResult
0x1800498ce  lea     rdx, aMil_0; "MIL"
0x1800498d5  mov     [rbp+hKey], r13
0x1800498d9  call    cs:__imp_RegOpenKeyW
0x1800498df  test    eax, eax
0x1800498e1  jnz     short loc_1800498F3
0x1800498e3  mov     rcx, [rbp+hKey]; hKey
0x1800498e7  call    cs:__imp_RegCloseKey
0x1800498ed  lea     edi, [r15+0Ch]
0x1800498f1  jmp     short loc_18004991F
0x1800498f3  xor     r9d, r9d; Context
0x1800498f6  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800498fd  xor     r8d, r8d; Parameter
0x180049900  lea     rcx, stru_180299FB8; InitOnce
0x180049907  call    cs:__imp_InitOnceExecuteOnce
0x18004990d  mov     al, cs:byte_180298C9C
0x180049913  neg     al
0x180049915  sbb     edi, edi
0x180049917  neg     edi
0x180049919  add     edi, 10000047h
0x18004991f  mov     rcx, [rbp+phkResult]; hKey
0x180049923  call    cs:__imp_RegCloseKey
0x180049929  jmp     short loc_18004995C
0x18004992b  xor     r9d, r9d; Context
0x18004992e  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180049935  xor     r8d, r8d; Parameter
0x180049938  lea     rcx, stru_180299FB8; InitOnce
0x18004993f  call    cs:__imp_InitOnceExecuteOnce
0x180049945  mov     al, cs:byte_180298C9C
0x18004994b  neg     al
0x18004994d  sbb     edi, edi
0x18004994f  add     edi, 10000048h
0x180049955  jmp     short loc_18004995C
0x180049957  cmp     eax, 2
0x18004995a  jnz     short loc_180049984
0x18004995c  mov     dl, 1
0x18004995e  mov     ecx, edi
0x180049960  call    ?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x180049965  mov     ebx, eax
0x180049967  test    eax, eax
0x180049969  jns     short loc_180049984
0x18004996b  mov     rcx, [rbp+40h]; this
0x18004996f  lea     r8, aOnecoreuapInet_11; "onecoreuap\\inetcore\\iertutil\\ieconfi"...
0x180049976  mov     r9d, eax; char *
0x180049979  mov     edx, 0B53h; void *
0x18004997e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180049984  mov     cs:byte_180298EE8, 1
0x18004998b  mov     ecx, r15d
0x18004998e  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180049993  mov     r12d, 10000032h
0x180049999  lea     r15d, [r12+1]
0x18004999e  test    al, al
0x1800499a0  jz      loc_180049A41
0x1800499a6  test    rsi, rsi
0x1800499a9  jz      short loc_1800499D3
0x1800499ab  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800499af  mov     r8, rdi
0x1800499b2  inc     r8
0x1800499b5  cmp     [rsi+r8*2], r13w
0x1800499ba  jnz     short loc_1800499B2
0x1800499bc  mov     rdx, rsi
0x1800499bf  mov     ecx, r12d
0x1800499c2  call    ?IEConfiguration_SetString@@YAJW4IEConfigurationID@@PEAGK@Z; IEConfiguration_SetString(IEConfigurationID,ushort *,ulong)
0x1800499c7  mov     ebx, eax
0x1800499c9  test    eax, eax
0x1800499cb  js      loc_180049AE2
0x1800499d1  jmp     short loc_180049A13
0x1800499d3  lea     rdx, [rbp+phkResult]; unsigned __int16 **
0x1800499d7  mov     [rbp+phkResult], r13
0x1800499db  xor     ecx, ecx; unsigned int
0x1800499dd  call    ?GetProcessAppContainerSIDStrW@@YAJKPEAPEAG@Z; GetProcessAppContainerSIDStrW(ulong,ushort * *)
0x1800499e2  mov     ebx, eax
0x1800499e4  test    eax, eax
0x1800499e6  js      loc_180049AE2
0x1800499ec  mov     rdx, [rbp+phkResult]
0x1800499f0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800499f4  mov     r8, rdi
0x1800499f7  inc     r8
0x1800499fa  cmp     [rdx+r8*2], r13w
0x1800499ff  jnz     short loc_1800499F7
0x180049a01  mov     ecx, r12d
0x180049a04  call    ?IEConfiguration_SetString@@YAJW4IEConfigurationID@@PEAGK@Z; IEConfiguration_SetString(IEConfigurationID,ushort *,ulong)
0x180049a09  mov     rcx, [rbp+phkResult]; hMem
0x180049a0d  call    cs:__imp_LocalFree
0x180049a13  test    r14, r14
0x180049a16  jz      short loc_180049A2A
0x180049a18  inc     rdi
0x180049a1b  cmp     [r14+rdi*2], r13w
0x180049a20  jnz     short loc_180049A18
0x180049a22  mov     r8d, edi
0x180049a25  mov     rdx, r14
0x180049a28  jmp     short loc_180049A37
0x180049a2a  mov     r8d, 25h ; '%'
0x180049a30  lea     rdx, aSpartanAuthori; "Spartan_Authority_Package_Moniker_TBD"
0x180049a37  mov     ecx, r15d
0x180049a3a  call    ?IEConfiguration_SetString@@YAJW4IEConfigurationID@@PEAGK@Z; IEConfiguration_SetString(IEConfigurationID,ushort *,ulong)
0x180049a3f  mov     ebx, eax
0x180049a41  test    ebx, ebx
0x180049a43  js      loc_180049AE2
0x180049a49  mov     ecx, 20000012h
0x180049a4e  call    ?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180049a53  test    eax, eax
0x180049a55  jnz     loc_180049AE2
0x180049a5b  mov     dword ptr [rbp+phkResult], r13d
0x180049a5f  call    ?GetCorrectBrowsingEnvironment@@YAPEAUIBrowsingEnvironment@@XZ; GetCorrectBrowsingEnvironment(void)
0x180049a64  mov     ecx, 10000033h
0x180049a69  mov     r12, rax
0x180049a6c  mov     rdx, [rax]
0x180049a6f  mov     r15, [rdx+58h]
0x180049a73  call    ?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x180049a78  mov     ecx, 10000032h
0x180049a7d  mov     r14, rax
0x180049a80  call    ?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x180049a85  mov     ecx, 10000040h
0x180049a8a  mov     rsi, rax
0x180049a8d  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180049a92  mov     ecx, 1000003Fh
0x180049a97  mov     dil, al
0x180049a9a  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180049a9f  mov     bl, al
0x180049aa1  call    cs:__imp_GetCurrentProcessId
0x180049aa7  lea     rdx, [rbp+phkResult]
0x180049aab  mov     r9b, dil
0x180049aae  mov     [rsp+58h+var_28], rdx
0x180049ab3  mov     r8b, bl
0x180049ab6  mov     edx, eax
0x180049ab8  mov     [rsp+58h+var_30], r14
0x180049abd  mov     rax, r15
0x180049ac0  mov     [rsp+58h+var_38], rsi
0x180049ac5  mov     rcx, r12
0x180049ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049acd  mov     ebx, eax
0x180049acf  test    eax, eax
0x180049ad1  js      short loc_180049AE2
0x180049ad3  mov     edx, dword ptr [rbp+phkResult]
0x180049ad6  mov     ecx, 20000012h
0x180049adb  call    ?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z; IEConfiguration_SetDWORD(IEConfigurationID,ulong)
0x180049ae0  mov     ebx, eax
0x180049ae2  mov     eax, ebx
0x180049ae4  add     rsp, 58h
0x180049ae8  pop     r15
0x180049aea  pop     r14
0x180049aec  pop     r13
0x180049aee  pop     r12
0x180049af0  pop     rdi
0x180049af1  pop     rsi
0x180049af2  pop     rbx
0x180049af3  pop     rbp
0x180049af4  retn
```
