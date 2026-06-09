# IsNgenOffline(void)

- ea: `0x180037c10`
- end: `0x180037e4c`
- name: `?IsNgenOffline@@YA_NXZ`
- size: `572`
- prototype: `bool(void)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000dbac`
- `0x1800100bc`
- `0x180010530`
- `0x18001b038`
- `0x18002f454`
- `0x1800375ac`

## callees

- `0x180030568`
- `0x18003691c`
- `0x180036fd0`
- `0x180037c10`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180037d75`
- `KERNEL32!HeapFree` at `0x180037daa`
- `KERNEL32!HeapFree` at `0x180037ddf`
- `KERNEL32!HeapFree` at `0x180037e14`
- `KERNEL32!HeapFree` at `0x180037d75`
- `KERNEL32!HeapFree` at `0x180037daa`
- `KERNEL32!HeapFree` at `0x180037ddf`
- `KERNEL32!HeapFree` at `0x180037e14`
- `KERNEL32!GetProcessHeap` at `0x180037d60`
- `KERNEL32!GetProcessHeap` at `0x180037d95`
- `KERNEL32!GetProcessHeap` at `0x180037dca`
- `KERNEL32!GetProcessHeap` at `0x180037dff`
- `KERNEL32!GetProcessHeap` at `0x180037d60`
- `KERNEL32!GetProcessHeap` at `0x180037d95`
- `KERNEL32!GetProcessHeap` at `0x180037dca`
- `KERNEL32!GetProcessHeap` at `0x180037dff`

## string_xrefs

- `0x180037c44`: `InstallRoot`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
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

  if ( !byte_180070799 )
  {
    ConfigString_DontUse = REGUTIL::GetConfigString_DontUse_(L"InstallRoot", 1, 1, 0);
    v22 = ConfigString_DontUse;
    v24 = ConfigString_DontUse != 0;
    v23 = v24;
    v25 = 0;
    CLRConfig::GetConfigValue((const struct CLRConfig::ConfigStringInfo *)&CLRConfig::UNSUPPORTED_NicPath, &v25);
    v0 = v25;
    v20 = v25;
    v1 = v25 != 0;
    v21 = v1;
    v26 = 0;
    CLRConfig::GetConfigValue((const struct CLRConfig::ConfigStringInfo *)&CLRConfig::UNSUPPORTED_RegistryRoot, &v26);
    v2 = v26;
    v18 = v26;
    v3 = v26 != 0;
    v19 = v3;
    v27 = 0;
    CLRConfig::GetConfigValue((const struct CLRConfig::ConfigStringInfo *)&CLRConfig::UNSUPPORTED_AssemblyPath, &v27);
    v4 = v27;
    v16 = v27;
    v5 = v27 != 0;
    v17 = v5;
    lpMem = 0;
    CLRConfig::GetConfigValue(
      (const struct CLRConfig::ConfigStringInfo *)&CLRConfig::UNSUPPORTED_AssemblyPath2,
      (unsigned __int16 **)&lpMem);
    v6 = lpMem;
    v14 = lpMem;
    v15 = lpMem != 0;
    if ( ConfigString_DontUse && v0 && v4 && lpMem && v2 )
      byte_18007079B = 1;
    byte_180070799 = 1;
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
  return byte_18007079B;
}

```

## disassembly

```asm
0x180037c10  push    rbp
0x180037c12  push    rbx
0x180037c13  push    rsi
0x180037c14  push    rdi
0x180037c15  push    r12
0x180037c17  push    r13
0x180037c19  push    r14
0x180037c1b  push    r15
0x180037c1d  lea     rbp, [rsp-1Fh]
0x180037c22  sub     rsp, 88h
0x180037c29  mov     al, cs:byte_180070799
0x180037c2f  xor     ebx, ebx
0x180037c31  test    al, al
0x180037c33  jnz     loc_180037E32
0x180037c39  xor     r9d, r9d
0x180037c3c  lea     edi, [rbx+1]
0x180037c3f  mov     r8d, edi
0x180037c42  mov     edx, edi
0x180037c44  lea     rcx, aInstallroot; "InstallRoot"
0x180037c4b  call    ?GetConfigString_DontUse_@REGUTIL@@SAPEAGPEBGHW4CORConfigLevel@1@H@Z; REGUTIL::GetConfigString_DontUse_(ushort const *,int,REGUTIL::CORConfigLevel,int)
0x180037c50  mov     rcx, rax
0x180037c53  mov     [rbp+57h+var_98], rax
0x180037c57  mov     [rbp+57h+var_50], rax
0x180037c5b  mov     [rbp+57h+var_48], ebx
0x180037c5e  mov     eax, ebx
0x180037c60  test    rcx, rcx
0x180037c63  cmovnz  eax, edi
0x180037c66  mov     [rbp+57h+arg_0], eax
0x180037c69  mov     [rbp+57h+var_48], eax
0x180037c6c  mov     [rbp+57h+arg_8], rbx
0x180037c70  lea     rdx, [rbp+57h+arg_8]; unsigned __int16 **
0x180037c74  lea     rcx, ?UNSUPPORTED_NicPath@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x180037c7b  call    ?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)
0x180037c80  mov     r14, [rbp+57h+arg_8]
0x180037c84  mov     [rbp+57h+var_60], r14
0x180037c88  mov     [rbp+57h+var_58], ebx
0x180037c8b  mov     r13d, ebx
0x180037c8e  test    r14, r14
0x180037c91  cmovnz  r13d, edi
0x180037c95  mov     [rbp+57h+var_58], r13d
0x180037c99  mov     [rbp+57h+arg_10], rbx
0x180037c9d  lea     rdx, [rbp+57h+arg_10]; unsigned __int16 **
0x180037ca1  lea     rcx, ?UNSUPPORTED_RegistryRoot@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x180037ca8  call    ?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)
0x180037cad  mov     rsi, [rbp+57h+arg_10]
0x180037cb1  mov     [rbp+57h+var_70], rsi
0x180037cb5  mov     [rbp+57h+var_68], ebx
0x180037cb8  mov     r12d, ebx
0x180037cbb  test    rsi, rsi
0x180037cbe  cmovnz  r12d, edi
0x180037cc2  mov     [rbp+57h+var_68], r12d
0x180037cc6  mov     [rbp+57h+arg_18], rbx
0x180037cca  lea     rdx, [rbp+57h+arg_18]; unsigned __int16 **
0x180037cce  lea     rcx, ?UNSUPPORTED_AssemblyPath@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x180037cd5  call    ?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)
0x180037cda  mov     rdi, [rbp+57h+arg_18]
0x180037cde  mov     [rbp+57h+var_80], rdi
0x180037ce2  mov     [rbp+57h+var_78], ebx
0x180037ce5  mov     r15d, ebx
0x180037ce8  test    rdi, rdi
0x180037ceb  lea     eax, [rbx+1]
0x180037cee  cmovnz  r15d, eax
0x180037cf2  mov     [rbp+57h+var_78], r15d
0x180037cf6  mov     [rbp+57h+lpMem], rbx
0x180037cfa  lea     rdx, [rbp+57h+lpMem]; unsigned __int16 **
0x180037cfe  lea     rcx, ?UNSUPPORTED_AssemblyPath2@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x180037d05  call    ?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)
0x180037d0a  mov     rbx, [rbp+57h+lpMem]
0x180037d0e  mov     [rbp+57h+var_90], rbx
0x180037d12  and     [rbp+57h+var_88], 0
0x180037d16  xor     eax, eax
0x180037d18  test    rbx, rbx
0x180037d1b  lea     ecx, [rax+1]
0x180037d1e  cmovnz  eax, ecx
0x180037d21  mov     [rbp+57h+var_88], eax
0x180037d24  cmp     [rbp+57h+var_98], 0
0x180037d29  jz      short loc_180037D45
0x180037d2b  test    r14, r14
0x180037d2e  jz      short loc_180037D45
0x180037d30  test    rdi, rdi
0x180037d33  jz      short loc_180037D45
0x180037d35  test    rbx, rbx
0x180037d38  jz      short loc_180037D45
0x180037d3a  test    rsi, rsi
0x180037d3d  jz      short loc_180037D45
0x180037d3f  mov     cs:byte_18007079B, cl
0x180037d45  mov     cs:byte_180070799, cl
0x180037d4b  test    eax, eax
0x180037d4d  jz      short loc_180037D7F
0x180037d4f  test    rbx, rbx
0x180037d52  jz      short loc_180037D7B
0x180037d54  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180037d5b  test    rax, rax
0x180037d5e  jnz     short loc_180037D6D
0x180037d60  call    cs:__imp_GetProcessHeap
0x180037d66  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180037d6d  mov     r8, rbx; lpMem
0x180037d70  xor     edx, edx; dwFlags
0x180037d72  mov     rcx, rax; hHeap
0x180037d75  call    cs:__imp_HeapFree
0x180037d7b  and     [rbp+57h+var_88], 0
0x180037d7f  test    r15d, r15d
0x180037d82  jz      short loc_180037DB4
0x180037d84  test    rdi, rdi
0x180037d87  jz      short loc_180037DB0
0x180037d89  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180037d90  test    rax, rax
0x180037d93  jnz     short loc_180037DA2
0x180037d95  call    cs:__imp_GetProcessHeap
0x180037d9b  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180037da2  mov     r8, rdi; lpMem
0x180037da5  xor     edx, edx; dwFlags
0x180037da7  mov     rcx, rax; hHeap
0x180037daa  call    cs:__imp_HeapFree
0x180037db0  and     [rbp+57h+var_78], 0
0x180037db4  test    r12d, r12d
0x180037db7  jz      short loc_180037DE9
0x180037db9  test    rsi, rsi
0x180037dbc  jz      short loc_180037DE5
0x180037dbe  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180037dc5  test    rax, rax
0x180037dc8  jnz     short loc_180037DD7
0x180037dca  call    cs:__imp_GetProcessHeap
0x180037dd0  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180037dd7  mov     r8, rsi; lpMem
0x180037dda  xor     edx, edx; dwFlags
0x180037ddc  mov     rcx, rax; hHeap
0x180037ddf  call    cs:__imp_HeapFree
0x180037de5  and     [rbp+57h+var_68], 0
0x180037de9  test    r13d, r13d
0x180037dec  jz      short loc_180037E1E
0x180037dee  test    r14, r14
0x180037df1  jz      short loc_180037E1A
0x180037df3  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180037dfa  test    rax, rax
0x180037dfd  jnz     short loc_180037E0C
0x180037dff  call    cs:__imp_GetProcessHeap
0x180037e05  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180037e0c  mov     r8, r14; lpMem
0x180037e0f  xor     edx, edx; dwFlags
0x180037e11  mov     rcx, rax; hHeap
0x180037e14  call    cs:__imp_HeapFree
0x180037e1a  and     [rbp+57h+var_58], 0
0x180037e1e  cmp     [rbp+57h+arg_0], 0
0x180037e22  jz      short loc_180037E32
0x180037e24  mov     rcx, [rbp+57h+var_98]; lpMem
0x180037e28  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180037e2d  xor     ebx, ebx
0x180037e2f  mov     [rbp+57h+var_48], ebx
0x180037e32  mov     al, cs:byte_18007079B
0x180037e38  add     rsp, 88h
0x180037e3f  pop     r15
0x180037e41  pop     r14
0x180037e43  pop     r13
0x180037e45  pop     r12
0x180037e47  pop     rdi
0x180037e48  pop     rsi
0x180037e49  pop     rbx
0x180037e4a  pop     rbp
0x180037e4b  retn
```
