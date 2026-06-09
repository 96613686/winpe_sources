# PrintLogoHelper(void)

- ea: `0x140007388`
- end: `0x140007501`
- name: `?PrintLogoHelper@@YAXXZ`
- size: `377`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000750c`
- `0x1400081c0`
- `0x140009104`

## callees

- `0x140006e3c`
- `0x1400072ec`
- `0x140007388`
- `0x14000a610`
- `0x14000b010`
- `0x14000bd40`
- `0x140013200`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140007497`
- `KERNEL32!HeapFree` at `0x1400074d3`
- `KERNEL32!HeapFree` at `0x140007497`
- `KERNEL32!HeapFree` at `0x1400074d3`
- `KERNEL32!GetProcessHeap` at `0x140007482`
- `KERNEL32!GetProcessHeap` at `0x1400074be`
- `KERNEL32!GetProcessHeap` at `0x140007482`
- `KERNEL32!GetProcessHeap` at `0x1400074be`

## string_xrefs

- `0x1400073c3`: `Copyright (c) Microsoft Corporation.  All rights reserved.\n`

## pseudocode

```c
void PrintLogoHelper(void)
{
  void *v0; // rbx
  BOOL v1; // edi
  HANDLE ProcessHeap; // rax
  void *v3; // rbx
  HANDLE v4; // rax
  LPVOID lpMem[2]; // [rsp+28h] [rbp-E0h] BYREF
  BOOL v6; // [rsp+38h] [rbp-D0h]
  int v7; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v8; // [rsp+4Ch] [rbp-BCh]
  LPVOID v9; // [rsp+58h] [rbp-B0h]
  __int16 v10; // [rsp+60h] [rbp-A8h] BYREF

  Output("Microsoft (R) CLR Native Image Generator - Version 4.8.9222.0\n");
  Output("Copyright (c) Microsoft Corporation.  All rights reserved.\n");
  v8 = 512;
  v9 = &v10;
  v7 = 2;
  v10 = 0;
  lpMem[0] = 0;
  CLRConfig::GetConfigValue((wchar_t **)&CLRConfig::EXTERNAL_ZapSet, (unsigned __int16 **)lpMem);
  v0 = lpMem[0];
  lpMem[1] = lpMem[0];
  v1 = lpMem[0] != 0;
  v6 = v1;
  if ( lpMem[0] )
  {
    SString::Printf((SString *)&v7, L"Operating on zapset \"%s\"\n", lpMem[0]);
    SString::ConvertToUnicode((SString *)&v7);
    CCompileProgressNotification::LogWorker((__int64)cCompileProgressNotification, 2, L"%s", v9);
  }
  if ( v1 )
  {
    if ( v0 )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v0);
    }
    v6 = 0;
  }
  if ( (v8 & 0x800000000LL) != 0 )
  {
    v3 = v9;
    if ( v9 )
    {
      v4 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v4 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v4;
      }
      HeapFree(v4, 0, v3);
    }
  }
}

```

## disassembly

```asm
0x140007388  mov     rax, rsp
0x14000738b  mov     [rax+8], rbx
0x14000738f  mov     [rax+10h], rsi
0x140007393  mov     [rax+18h], rdi
0x140007397  push    rbp
0x140007398  lea     rbp, [rax-178h]
0x14000739f  sub     rsp, 270h
0x1400073a6  mov     rax, cs:__security_cookie
0x1400073ad  xor     rax, rsp
0x1400073b0  mov     [rbp+170h+var_10], rax
0x1400073b7  lea     rcx, aMicrosoftRClrN; "Microsoft (R) CLR Native Image Generato"...
0x1400073be  call    ?Output@@YAXPEBD@Z; Output(char const *)
0x1400073c3  lea     rcx, aCopyrightCMicr; "Copyright (c) Microsoft Corporation.  A"...
0x1400073ca  call    ?Output@@YAXPEBD@Z; Output(char const *)
0x1400073cf  xor     esi, esi
0x1400073d1  mov     qword ptr [rsp+270h+var_230], rsi
0x1400073d6  mov     qword ptr [rsp+44h], 200h
0x1400073df  mov     [rsp+270h+var_220], rsi
0x1400073e4  lea     rax, [rsp+270h+var_218]
0x1400073e9  mov     [rsp+270h+var_220], rax
0x1400073ee  mov     [rsp+270h+var_230], 2
0x1400073f6  mov     rax, [rsp+270h+var_220]
0x1400073fb  mov     [rax], si
0x1400073fe  mov     [rsp+270h+lpMem], rsi
0x140007403  lea     rdx, [rsp+270h+lpMem]; unsigned __int16 **
0x140007408  lea     rcx, ?EXTERNAL_ZapSet@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x14000740f  call    ?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)
0x140007414  mov     rbx, [rsp+270h+lpMem]
0x140007419  mov     qword ptr [rsp+270h+var_248], rbx
0x14000741e  mov     [rsp+270h+var_240], esi
0x140007422  mov     edi, esi
0x140007424  lea     eax, [rsi+1]
0x140007427  test    rbx, rbx
0x14000742a  cmovnz  edi, eax
0x14000742d  mov     [rsp+270h+var_240], edi
0x140007431  jz      short loc_14000746D
0x140007433  mov     r8, rbx
0x140007436  lea     rdx, aOperatingOnZap; "Operating on zapset \"%s\"\n"
0x14000743d  lea     rcx, [rsp+270h+var_230]; this
0x140007442  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x140007447  lea     rcx, [rsp+270h+var_230]; this
0x14000744c  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140007451  mov     r9, [rsp+270h+var_220]
0x140007456  lea     r8, aS; "%s"
0x14000745d  lea     edx, [rsi+2]
0x140007460  lea     rcx, ?cCompileProgressNotification@@3VCCompileProgressNotification@@A; CCompileProgressNotification cCompileProgressNotification
0x140007467  call    ?LogWorker@CCompileProgressNotification@@AEAAXW4CorSvcLogLevel@@PEAGZZ; CCompileProgressNotification::LogWorker(CorSvcLogLevel,ushort *,...)
0x14000746c  nop
0x14000746d  test    edi, edi
0x14000746f  jz      short loc_1400074A1
0x140007471  test    rbx, rbx
0x140007474  jz      short loc_14000749D
0x140007476  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14000747d  test    rax, rax
0x140007480  jnz     short loc_14000748F
0x140007482  call    cs:__imp_GetProcessHeap
0x140007488  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14000748f  mov     r8, rbx; lpMem
0x140007492  xor     edx, edx; dwFlags
0x140007494  mov     rcx, rax; hHeap
0x140007497  call    cs:__imp_HeapFree
0x14000749d  mov     [rsp+270h+var_240], esi
0x1400074a1  test    byte ptr [rsp+270h+var_228], 8
0x1400074a6  jz      short loc_1400074D9
0x1400074a8  mov     rbx, [rsp+270h+var_220]
0x1400074ad  test    rbx, rbx
0x1400074b0  jz      short loc_1400074D9
0x1400074b2  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400074b9  test    rax, rax
0x1400074bc  jnz     short loc_1400074CB
0x1400074be  call    cs:__imp_GetProcessHeap
0x1400074c4  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400074cb  mov     r8, rbx; lpMem
0x1400074ce  xor     edx, edx; dwFlags
0x1400074d0  mov     rcx, rax; hHeap
0x1400074d3  call    cs:__imp_HeapFree
0x1400074d9  mov     rcx, [rbp+170h+var_10]
0x1400074e0  xor     rcx, rsp; StackCookie
0x1400074e3  call    __security_check_cookie
0x1400074e8  lea     r11, [rsp+270h+var_s0]
0x1400074f0  mov     rbx, [r11+10h]
0x1400074f4  mov     rsi, [r11+18h]
0x1400074f8  mov     rdi, [r11+20h]
0x1400074fc  mov     rsp, r11
0x1400074ff  pop     rbp
0x140007500  retn
```
