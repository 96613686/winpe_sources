# IsInvalidOfflineNgenEnvironment(void)

- ea: `0x140008ed0`
- end: `0x140009101`
- name: `?IsInvalidOfflineNgenEnvironment@@YAHXZ`
- size: `561`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x140009104`

## callees

- `0x140008ed0`
- `0x14000a10c`
- `0x14000a610`
- `0x14000fe04`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140009028`
- `KERNEL32!HeapFree` at `0x14000905d`
- `KERNEL32!HeapFree` at `0x140009092`
- `KERNEL32!HeapFree` at `0x1400090c8`
- `KERNEL32!HeapFree` at `0x140009028`
- `KERNEL32!HeapFree` at `0x14000905d`
- `KERNEL32!HeapFree` at `0x140009092`
- `KERNEL32!HeapFree` at `0x1400090c8`
- `KERNEL32!GetProcessHeap` at `0x140009013`
- `KERNEL32!GetProcessHeap` at `0x140009048`
- `KERNEL32!GetProcessHeap` at `0x14000907d`
- `KERNEL32!GetProcessHeap` at `0x1400090b3`
- `KERNEL32!GetProcessHeap` at `0x140009013`
- `KERNEL32!GetProcessHeap` at `0x140009048`
- `KERNEL32!GetProcessHeap` at `0x14000907d`
- `KERNEL32!GetProcessHeap` at `0x1400090b3`

## string_xrefs

- `0x140008ef4`: `InstallRoot`

## pseudocode

```c
__int64 IsInvalidOfflineNgenEnvironment(void)
{
  unsigned int v0; // r15d
  unsigned __int16 *v1; // r14
  void *v2; // rsi
  BOOL v3; // r13d
  void *v4; // rdi
  BOOL v5; // r12d
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v8; // rax
  HANDLE v9; // rax
  HANDLE v10; // rax
  unsigned __int16 *ConfigString_DontUse; // [rsp+20h] [rbp-50h]
  unsigned __int16 *v13; // [rsp+B0h] [rbp+40h] BYREF
  BOOL v14; // [rsp+B8h] [rbp+48h]
  LPVOID lpMem; // [rsp+C0h] [rbp+50h] BYREF

  v0 = 1;
  ConfigString_DontUse = REGUTIL::GetConfigString_DontUse_(L"InstallRoot", 1, 1, 0);
  v14 = ConfigString_DontUse != 0;
  v13 = 0;
  CLRConfig::GetConfigValue((wchar_t **)&CLRConfig::UNSUPPORTED_NicPath, &v13);
  v1 = v13;
  LODWORD(v13) = v13 != 0;
  lpMem = 0;
  CLRConfig::GetConfigValue((wchar_t **)&CLRConfig::UNSUPPORTED_RegistryRoot, (unsigned __int16 **)&lpMem);
  v2 = lpMem;
  v3 = lpMem != 0;
  lpMem = 0;
  CLRConfig::GetConfigValue((wchar_t **)&CLRConfig::UNSUPPORTED_AssemblyPath, (unsigned __int16 **)&lpMem);
  v4 = lpMem;
  v5 = lpMem != 0;
  lpMem = 0;
  CLRConfig::GetConfigValue((wchar_t **)&CLRConfig::UNSUPPORTED_AssemblyPath2, (unsigned __int16 **)&lpMem);
  v6 = lpMem;
  if ( !ConfigString_DontUse )
    goto LABEL_10;
  if ( !v1 )
  {
    if ( v4 || lpMem || v2 )
      goto LABEL_11;
LABEL_10:
    v0 = 0;
    goto LABEL_11;
  }
  if ( v4 && lpMem && v2 )
    goto LABEL_10;
LABEL_11:
  if ( lpMem )
  {
    ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
    if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
    {
      ProcessHeap = GetProcessHeap();
      `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
    }
    HeapFree(ProcessHeap, 0, v6);
  }
  if ( v5 && v4 )
  {
    v8 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
    if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
    {
      v8 = GetProcessHeap();
      `ClrFreeInProcessHeap'::`2'::ProcessHeap = v8;
    }
    HeapFree(v8, 0, v4);
  }
  if ( v3 && v2 )
  {
    v9 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
    if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
    {
      v9 = GetProcessHeap();
      `ClrFreeInProcessHeap'::`2'::ProcessHeap = v9;
    }
    HeapFree(v9, 0, v2);
  }
  if ( (_DWORD)v13 && v1 )
  {
    v10 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
    if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
    {
      v10 = GetProcessHeap();
      `ClrFreeInProcessHeap'::`2'::ProcessHeap = v10;
    }
    HeapFree(v10, 0, v1);
  }
  if ( v14 )
    operator delete(ConfigString_DontUse);
  return v0;
}

```

## disassembly

```asm
0x140008ed0  mov     [rsp-38h+arg_18], rbx
0x140008ed5  push    rbp
0x140008ed6  push    rsi
0x140008ed7  push    rdi
0x140008ed8  push    r12
0x140008eda  push    r13
0x140008edc  push    r14
0x140008ede  push    r15
0x140008ee0  mov     rbp, rsp
0x140008ee3  sub     rsp, 70h
0x140008ee7  xor     r9d, r9d
0x140008eea  lea     r15d, [r9+1]
0x140008eee  mov     r8d, r15d
0x140008ef1  mov     edx, r15d
0x140008ef4  lea     rcx, aInstallroot; "InstallRoot"
0x140008efb  call    ?GetConfigString_DontUse_@REGUTIL@@SAPEAGPEBGHW4CORConfigLevel@1@H@Z; REGUTIL::GetConfigString_DontUse_(ushort const *,int,REGUTIL::CORConfigLevel,int)
0x140008f00  mov     rcx, rax
0x140008f03  mov     [rbp+var_50], rax
0x140008f07  xor     ebx, ebx
0x140008f09  mov     [rbp+var_48], ebx
0x140008f0c  mov     eax, ebx
0x140008f0e  test    rcx, rcx
0x140008f11  cmovnz  eax, r15d
0x140008f15  mov     [rbp+arg_8], eax
0x140008f18  mov     [rbp+var_48], eax
0x140008f1b  mov     [rbp+arg_0], rbx
0x140008f1f  lea     rdx, [rbp+arg_0]; unsigned __int16 **
0x140008f23  lea     rcx, ?UNSUPPORTED_NicPath@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x140008f2a  call    ?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)
0x140008f2f  mov     r14, [rbp+arg_0]
0x140008f33  mov     [rbp+var_10], r14
0x140008f37  mov     [rbp+var_8], ebx
0x140008f3a  mov     eax, ebx
0x140008f3c  test    r14, r14
0x140008f3f  cmovnz  eax, r15d
0x140008f43  mov     dword ptr [rbp+arg_0], eax
0x140008f46  mov     [rbp+var_8], eax
0x140008f49  mov     [rbp+lpMem], rbx
0x140008f4d  lea     rdx, [rbp+lpMem]; unsigned __int16 **
0x140008f51  lea     rcx, ?UNSUPPORTED_RegistryRoot@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x140008f58  call    ?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)
0x140008f5d  mov     rsi, [rbp+lpMem]
0x140008f61  mov     [rbp+var_20], rsi
0x140008f65  mov     [rbp+var_18], ebx
0x140008f68  mov     r13d, ebx
0x140008f6b  test    rsi, rsi
0x140008f6e  cmovnz  r13d, r15d
0x140008f72  mov     [rbp+var_18], r13d
0x140008f76  mov     [rbp+lpMem], rbx
0x140008f7a  lea     rdx, [rbp+lpMem]; unsigned __int16 **
0x140008f7e  lea     rcx, ?UNSUPPORTED_AssemblyPath@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x140008f85  call    ?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)
0x140008f8a  mov     rdi, [rbp+lpMem]
0x140008f8e  mov     [rbp+var_30], rdi
0x140008f92  mov     [rbp+var_28], ebx
0x140008f95  mov     r12d, ebx
0x140008f98  test    rdi, rdi
0x140008f9b  cmovnz  r12d, r15d
0x140008f9f  mov     [rbp+var_28], r12d
0x140008fa3  mov     [rbp+lpMem], rbx
0x140008fa7  lea     rdx, [rbp+lpMem]; unsigned __int16 **
0x140008fab  lea     rcx, ?UNSUPPORTED_AssemblyPath2@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x140008fb2  call    ?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)
0x140008fb7  mov     rbx, [rbp+lpMem]
0x140008fbb  mov     [rbp+var_40], rbx
0x140008fbf  and     [rbp+var_38], 0
0x140008fc3  xor     eax, eax
0x140008fc5  test    rbx, rbx
0x140008fc8  cmovnz  eax, r15d
0x140008fcc  mov     [rbp+var_38], eax
0x140008fcf  cmp     [rbp+var_50], 0
0x140008fd4  jz      short loc_140008FFB
0x140008fd6  test    r14, r14
0x140008fd9  jnz     short loc_140008FEC
0x140008fdb  test    rdi, rdi
0x140008fde  jnz     short loc_140008FFE
0x140008fe0  test    rbx, rbx
0x140008fe3  jnz     short loc_140008FFE
0x140008fe5  test    rsi, rsi
0x140008fe8  jz      short loc_140008FFB
0x140008fea  jmp     short loc_140008FFE
0x140008fec  test    rdi, rdi
0x140008fef  jz      short loc_140008FFE
0x140008ff1  test    rbx, rbx
0x140008ff4  jz      short loc_140008FFE
0x140008ff6  test    rsi, rsi
0x140008ff9  jz      short loc_140008FFE
0x140008ffb  xor     r15d, r15d
0x140008ffe  test    eax, eax
0x140009000  jz      short loc_140009032
0x140009002  test    rbx, rbx
0x140009005  jz      short loc_14000902E
0x140009007  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14000900e  test    rax, rax
0x140009011  jnz     short loc_140009020
0x140009013  call    cs:__imp_GetProcessHeap
0x140009019  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140009020  mov     r8, rbx; lpMem
0x140009023  xor     edx, edx; dwFlags
0x140009025  mov     rcx, rax; hHeap
0x140009028  call    cs:__imp_HeapFree
0x14000902e  and     [rbp+var_38], 0
0x140009032  test    r12d, r12d
0x140009035  jz      short loc_140009067
0x140009037  test    rdi, rdi
0x14000903a  jz      short loc_140009063
0x14000903c  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140009043  test    rax, rax
0x140009046  jnz     short loc_140009055
0x140009048  call    cs:__imp_GetProcessHeap
0x14000904e  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140009055  mov     r8, rdi; lpMem
0x140009058  xor     edx, edx; dwFlags
0x14000905a  mov     rcx, rax; hHeap
0x14000905d  call    cs:__imp_HeapFree
0x140009063  and     [rbp+var_28], 0
0x140009067  test    r13d, r13d
0x14000906a  jz      short loc_14000909C
0x14000906c  test    rsi, rsi
0x14000906f  jz      short loc_140009098
0x140009071  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140009078  test    rax, rax
0x14000907b  jnz     short loc_14000908A
0x14000907d  call    cs:__imp_GetProcessHeap
0x140009083  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14000908a  mov     r8, rsi; lpMem
0x14000908d  xor     edx, edx; dwFlags
0x14000908f  mov     rcx, rax; hHeap
0x140009092  call    cs:__imp_HeapFree
0x140009098  and     [rbp+var_18], 0
0x14000909c  cmp     dword ptr [rbp+arg_0], 0
0x1400090a0  jz      short loc_1400090D2
0x1400090a2  test    r14, r14
0x1400090a5  jz      short loc_1400090CE
0x1400090a7  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400090ae  test    rax, rax
0x1400090b1  jnz     short loc_1400090C0
0x1400090b3  call    cs:__imp_GetProcessHeap
0x1400090b9  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400090c0  mov     r8, r14; lpMem
0x1400090c3  xor     edx, edx; dwFlags
0x1400090c5  mov     rcx, rax; hHeap
0x1400090c8  call    cs:__imp_HeapFree
0x1400090ce  and     [rbp+var_8], 0
0x1400090d2  cmp     [rbp+arg_8], 0
0x1400090d6  jz      short loc_1400090E6
0x1400090d8  mov     rcx, [rbp+var_50]; lpMem
0x1400090dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400090e1  xor     ebx, ebx
0x1400090e3  mov     [rbp+var_48], ebx
0x1400090e6  mov     eax, r15d
0x1400090e9  mov     rbx, [rsp+70h+arg_18]
0x1400090f1  add     rsp, 70h
0x1400090f5  pop     r15
0x1400090f7  pop     r14
0x1400090f9  pop     r13
0x1400090fb  pop     r12
0x1400090fd  pop     rdi
0x1400090fe  pop     rsi
0x1400090ff  pop     rbp
0x140009100  retn
```
