# IsNgenOffline(void)

- ea: `0x140010454`
- end: `0x140010690`
- name: `?IsNgenOffline@@YA_NXZ`
- size: `572`
- prototype: `char(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x140002168`
- `0x140004694`
- `0x140004b08`

## callees

- `0x14000a10c`
- `0x14000a610`
- `0x14000fe04`
- `0x140010454`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400105b9`
- `KERNEL32!HeapFree` at `0x1400105ee`
- `KERNEL32!HeapFree` at `0x140010623`
- `KERNEL32!HeapFree` at `0x140010658`
- `KERNEL32!HeapFree` at `0x1400105b9`
- `KERNEL32!HeapFree` at `0x1400105ee`
- `KERNEL32!HeapFree` at `0x140010623`
- `KERNEL32!HeapFree` at `0x140010658`
- `KERNEL32!GetProcessHeap` at `0x1400105a4`
- `KERNEL32!GetProcessHeap` at `0x1400105d9`
- `KERNEL32!GetProcessHeap` at `0x14001060e`
- `KERNEL32!GetProcessHeap` at `0x140010643`
- `KERNEL32!GetProcessHeap` at `0x1400105a4`
- `KERNEL32!GetProcessHeap` at `0x1400105d9`
- `KERNEL32!GetProcessHeap` at `0x14001060e`
- `KERNEL32!GetProcessHeap` at `0x140010643`

## string_xrefs

- `0x140010488`: `InstallRoot`

## pseudocode

```c
char IsNgenOffline(void)
{
  unsigned __int16 *v0; // r14
  BOOL v1; // r13d
  unsigned __int16 *v2; // rsi
  BOOL v3; // r12d
  unsigned __int16 *v4; // rdi
  BOOL v5; // r15d
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v8; // rax
  HANDLE v9; // rax
  HANDLE v10; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-49h] BYREF
  void *ConfigString_DontUse; // [rsp+28h] [rbp-41h]
  LPVOID v14; // [rsp+30h] [rbp-39h]
  BOOL v15; // [rsp+38h] [rbp-31h]
  unsigned __int16 *v16; // [rsp+40h] [rbp-29h]
  BOOL v17; // [rsp+48h] [rbp-21h]
  unsigned __int16 *v18; // [rsp+50h] [rbp-19h]
  BOOL v19; // [rsp+58h] [rbp-11h]
  unsigned __int16 *v20; // [rsp+60h] [rbp-9h]
  BOOL v21; // [rsp+68h] [rbp-1h]
  void *v22; // [rsp+70h] [rbp+7h]
  BOOL v23; // [rsp+78h] [rbp+Fh]
  BOOL v24; // [rsp+D0h] [rbp+67h]
  unsigned __int16 *v25; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned __int16 *v26; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int16 *v27; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( !byte_140028184 )
  {
    ConfigString_DontUse = REGUTIL::GetConfigString_DontUse_(L"InstallRoot", 1, 1, 0);
    v22 = ConfigString_DontUse;
    v24 = ConfigString_DontUse != 0;
    v23 = v24;
    v25 = 0;
    CLRConfig::GetConfigValue((wchar_t **)&CLRConfig::UNSUPPORTED_NicPath, &v25);
    v0 = v25;
    v20 = v25;
    v1 = v25 != 0;
    v21 = v1;
    v26 = 0;
    CLRConfig::GetConfigValue((wchar_t **)&CLRConfig::UNSUPPORTED_RegistryRoot, &v26);
    v2 = v26;
    v18 = v26;
    v3 = v26 != 0;
    v19 = v3;
    v27 = 0;
    CLRConfig::GetConfigValue((wchar_t **)&CLRConfig::UNSUPPORTED_AssemblyPath, &v27);
    v4 = v27;
    v16 = v27;
    v5 = v27 != 0;
    v17 = v5;
    lpMem = 0;
    CLRConfig::GetConfigValue((wchar_t **)&CLRConfig::UNSUPPORTED_AssemblyPath2, (unsigned __int16 **)&lpMem);
    v6 = lpMem;
    v14 = lpMem;
    v15 = lpMem != 0;
    if ( ConfigString_DontUse && v0 && v4 && lpMem && v2 )
      byte_140028185 = 1;
    byte_140028184 = 1;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v6);
      v15 = 0;
    }
    if ( v5 )
    {
      if ( v4 )
      {
        v8 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v8 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v8;
        }
        HeapFree(v8, 0, v4);
      }
      v17 = 0;
    }
    if ( v3 )
    {
      if ( v2 )
      {
        v9 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v9 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v9;
        }
        HeapFree(v9, 0, v2);
      }
      v19 = 0;
    }
    if ( v1 )
    {
      if ( v0 )
      {
        v10 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v10 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v10;
        }
        HeapFree(v10, 0, v0);
      }
      v21 = 0;
    }
    if ( v24 )
    {
      operator delete(ConfigString_DontUse);
      v23 = 0;
    }
  }
  return byte_140028185;
}

```

## disassembly

```asm
0x140010454  push    rbp
0x140010456  push    rbx
0x140010457  push    rsi
0x140010458  push    rdi
0x140010459  push    r12
0x14001045b  push    r13
0x14001045d  push    r14
0x14001045f  push    r15
0x140010461  lea     rbp, [rsp-1Fh]
0x140010466  sub     rsp, 88h
0x14001046d  mov     al, cs:byte_140028184
0x140010473  xor     ebx, ebx
0x140010475  test    al, al
0x140010477  jnz     loc_140010676
0x14001047d  xor     r9d, r9d
0x140010480  lea     edi, [rbx+1]
0x140010483  mov     r8d, edi
0x140010486  mov     edx, edi
0x140010488  lea     rcx, aInstallroot; "InstallRoot"
0x14001048f  call    ?GetConfigString_DontUse_@REGUTIL@@SAPEAGPEBGHW4CORConfigLevel@1@H@Z; REGUTIL::GetConfigString_DontUse_(ushort const *,int,REGUTIL::CORConfigLevel,int)
0x140010494  mov     rcx, rax
0x140010497  mov     [rbp+57h+var_98], rax
0x14001049b  mov     [rbp+57h+var_50], rax
0x14001049f  mov     [rbp+57h+var_48], ebx
0x1400104a2  mov     eax, ebx
0x1400104a4  test    rcx, rcx
0x1400104a7  cmovnz  eax, edi
0x1400104aa  mov     [rbp+57h+arg_0], eax
0x1400104ad  mov     [rbp+57h+var_48], eax
0x1400104b0  mov     [rbp+57h+arg_8], rbx
0x1400104b4  lea     rdx, [rbp+57h+arg_8]; unsigned __int16 **
0x1400104b8  lea     rcx, ?UNSUPPORTED_NicPath@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x1400104bf  call    ?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)
0x1400104c4  mov     r14, [rbp+57h+arg_8]
0x1400104c8  mov     [rbp+57h+var_60], r14
0x1400104cc  mov     [rbp+57h+var_58], ebx
0x1400104cf  mov     r13d, ebx
0x1400104d2  test    r14, r14
0x1400104d5  cmovnz  r13d, edi
0x1400104d9  mov     [rbp+57h+var_58], r13d
0x1400104dd  mov     [rbp+57h+arg_10], rbx
0x1400104e1  lea     rdx, [rbp+57h+arg_10]; unsigned __int16 **
0x1400104e5  lea     rcx, ?UNSUPPORTED_RegistryRoot@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x1400104ec  call    ?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)
0x1400104f1  mov     rsi, [rbp+57h+arg_10]
0x1400104f5  mov     [rbp+57h+var_70], rsi
0x1400104f9  mov     [rbp+57h+var_68], ebx
0x1400104fc  mov     r12d, ebx
0x1400104ff  test    rsi, rsi
0x140010502  cmovnz  r12d, edi
0x140010506  mov     [rbp+57h+var_68], r12d
0x14001050a  mov     [rbp+57h+arg_18], rbx
0x14001050e  lea     rdx, [rbp+57h+arg_18]; unsigned __int16 **
0x140010512  lea     rcx, ?UNSUPPORTED_AssemblyPath@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x140010519  call    ?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)
0x14001051e  mov     rdi, [rbp+57h+arg_18]
0x140010522  mov     [rbp+57h+var_80], rdi
0x140010526  mov     [rbp+57h+var_78], ebx
0x140010529  mov     r15d, ebx
0x14001052c  test    rdi, rdi
0x14001052f  lea     eax, [rbx+1]
0x140010532  cmovnz  r15d, eax
0x140010536  mov     [rbp+57h+var_78], r15d
0x14001053a  mov     [rbp+57h+lpMem], rbx
0x14001053e  lea     rdx, [rbp+57h+lpMem]; unsigned __int16 **
0x140010542  lea     rcx, ?UNSUPPORTED_AssemblyPath2@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x140010549  call    ?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)
0x14001054e  mov     rbx, [rbp+57h+lpMem]
0x140010552  mov     [rbp+57h+var_90], rbx
0x140010556  and     [rbp+57h+var_88], 0
0x14001055a  xor     eax, eax
0x14001055c  test    rbx, rbx
0x14001055f  lea     ecx, [rax+1]
0x140010562  cmovnz  eax, ecx
0x140010565  mov     [rbp+57h+var_88], eax
0x140010568  cmp     [rbp+57h+var_98], 0
0x14001056d  jz      short loc_140010589
0x14001056f  test    r14, r14
0x140010572  jz      short loc_140010589
0x140010574  test    rdi, rdi
0x140010577  jz      short loc_140010589
0x140010579  test    rbx, rbx
0x14001057c  jz      short loc_140010589
0x14001057e  test    rsi, rsi
0x140010581  jz      short loc_140010589
0x140010583  mov     cs:byte_140028185, cl
0x140010589  mov     cs:byte_140028184, cl
0x14001058f  test    eax, eax
0x140010591  jz      short loc_1400105C3
0x140010593  test    rbx, rbx
0x140010596  jz      short loc_1400105BF
0x140010598  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14001059f  test    rax, rax
0x1400105a2  jnz     short loc_1400105B1
0x1400105a4  call    cs:__imp_GetProcessHeap
0x1400105aa  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400105b1  mov     r8, rbx; lpMem
0x1400105b4  xor     edx, edx; dwFlags
0x1400105b6  mov     rcx, rax; hHeap
0x1400105b9  call    cs:__imp_HeapFree
0x1400105bf  and     [rbp+57h+var_88], 0
0x1400105c3  test    r15d, r15d
0x1400105c6  jz      short loc_1400105F8
0x1400105c8  test    rdi, rdi
0x1400105cb  jz      short loc_1400105F4
0x1400105cd  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400105d4  test    rax, rax
0x1400105d7  jnz     short loc_1400105E6
0x1400105d9  call    cs:__imp_GetProcessHeap
0x1400105df  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400105e6  mov     r8, rdi; lpMem
0x1400105e9  xor     edx, edx; dwFlags
0x1400105eb  mov     rcx, rax; hHeap
0x1400105ee  call    cs:__imp_HeapFree
0x1400105f4  and     [rbp+57h+var_78], 0
0x1400105f8  test    r12d, r12d
0x1400105fb  jz      short loc_14001062D
0x1400105fd  test    rsi, rsi
0x140010600  jz      short loc_140010629
0x140010602  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140010609  test    rax, rax
0x14001060c  jnz     short loc_14001061B
0x14001060e  call    cs:__imp_GetProcessHeap
0x140010614  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14001061b  mov     r8, rsi; lpMem
0x14001061e  xor     edx, edx; dwFlags
0x140010620  mov     rcx, rax; hHeap
0x140010623  call    cs:__imp_HeapFree
0x140010629  and     [rbp+57h+var_68], 0
0x14001062d  test    r13d, r13d
0x140010630  jz      short loc_140010662
0x140010632  test    r14, r14
0x140010635  jz      short loc_14001065E
0x140010637  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14001063e  test    rax, rax
0x140010641  jnz     short loc_140010650
0x140010643  call    cs:__imp_GetProcessHeap
0x140010649  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140010650  mov     r8, r14; lpMem
0x140010653  xor     edx, edx; dwFlags
0x140010655  mov     rcx, rax; hHeap
0x140010658  call    cs:__imp_HeapFree
0x14001065e  and     [rbp+57h+var_58], 0
0x140010662  cmp     [rbp+57h+arg_0], 0
0x140010666  jz      short loc_140010676
0x140010668  mov     rcx, [rbp+57h+var_98]; lpMem
0x14001066c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140010671  xor     ebx, ebx
0x140010673  mov     [rbp+57h+var_48], ebx
0x140010676  mov     al, cs:byte_140028185
0x14001067c  add     rsp, 88h
0x140010683  pop     r15
0x140010685  pop     r14
0x140010687  pop     r13
0x140010689  pop     r12
0x14001068b  pop     rdi
0x14001068c  pop     rsi
0x14001068d  pop     rbx
0x14001068e  pop     rbp
0x14001068f  retn
```
