# KGT_Initialize(KEYGUARD_TELEMETRY_GLOBAL *)

- ea: `0x180028bec`
- end: `0x180028d54`
- name: `?KGT_Initialize@@YAHPEAUKEYGUARD_TELEMETRY_GLOBAL@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016b98`

## callees

- `0x18000af80`
- `0x18001d350`
- `0x18001d44c`
- `0x180028bec`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x180028c45`
- `ntdll!RtlInitializeCriticalSection` at `0x180028c45`
- `ntdll!RtlDeleteCriticalSection` at `0x180028d2e`
- `ntdll!RtlDeleteCriticalSection` at `0x180028d2e`
- `ntdll!RtlDllShutdownInProgress` at `0x180028c64`
- `ntdll!RtlDllShutdownInProgress` at `0x180028c64`

## string_xrefs

- `0x180028cc7`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\telemetry-init.cpp`
- `0x180028d0e`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\telemetry-init.cpp`

## pseudocode

```c
__int64 __fastcall KGT_Initialize(struct _RTL_CRITICAL_SECTION *a1)
{
  __int64 v1; // r9
  __int64 v2; // rcx
  const char *v3; // rdx
  unsigned int v4; // ebx
  __int64 v5; // rdi
  NTSTATUS v6; // eax
  int v7; // eax
  int v8; // edi
  int v9; // ebx
  const char *v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r9
  int v13; // eax
  unsigned int i; // ebx
  PRTL_CRITICAL_SECTION CriticalSection; // [rsp+20h] [rbp-28h]
  _DWORD v17[2]; // [rsp+28h] [rbp-20h]
  struct _RTL_CRITICAL_SECTION *v18; // [rsp+30h] [rbp-18h]
  int v19; // [rsp+38h] [rbp-10h]

  if ( a1 )
  {
    CriticalSection = a1;
    v18 = a1 + 1;
    v4 = 0;
    v17[0] = 0;
    v19 = 0;
    do
    {
      v5 = 2LL * (int)v4;
      v6 = RtlInitializeCriticalSection(*(PRTL_CRITICAL_SECTION *)&v17[4 * v4 - 2]);
      if ( v6 < 0 )
      {
        v1 = 60;
        v3 = "status";
        v2 = (unsigned int)v6;
        goto LABEL_16;
      }
      ++v4;
      v17[2 * v5] = 1;
    }
    while ( v4 < 2 );
    if ( RtlDllShutdownInProgress() )
      goto LABEL_17;
    v7 = TlgRegisterAggregateProviderEx(&dword_180079160);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v13 = TlgRegisterAggregateProviderEx(&dword_180079128);
      v9 = v13;
      if ( v13 >= 0 )
      {
        dword_18007A77C = 1;
        return 1;
      }
      v11 = (unsigned int)v13;
      v10 = "hrTlgCore";
      v12 = 85;
    }
    else
    {
      v9 = -2147467259;
      v10 = "hrTlg";
      v11 = (unsigned int)v7;
      v12 = 79;
    }
    DebugTraceError(v11, v10, "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\telemetry-init.cpp", v12);
    if ( v8 >= 0 )
    {
      TlgUnregisterAggregateProvider(&dword_180079160);
      if ( v9 >= 0 )
        TlgUnregisterAggregateProvider(&dword_180079128);
    }
  }
  else
  {
    v1 = 40;
    v2 = 2148073486LL;
    v3 = "NTE_NO_MEMORY";
LABEL_16:
    DebugTraceError(v2, v3, "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\telemetry-init.cpp", v1);
  }
LABEL_17:
  for ( i = 0; i < 2; ++i )
  {
    if ( v17[4 * i] )
      RtlDeleteCriticalSection(*(PRTL_CRITICAL_SECTION *)&v17[4 * i - 2]);
  }
  return 0;
}

```

## disassembly

```asm
0x180028bec  mov     [rsp+arg_0], rbx
0x180028bf1  mov     [rsp+arg_8], rbp
0x180028bf6  push    rdi
0x180028bf7  sub     rsp, 40h
0x180028bfb  mov     ebp, 1
0x180028c00  test    rcx, rcx
0x180028c03  jnz     short loc_180028C1A
0x180028c05  lea     r9d, [rbp+27h]
0x180028c09  mov     ecx, 8009000Eh
0x180028c0e  lea     rdx, aNteNoMemory; "NTE_NO_MEMORY"
0x180028c15  jmp     loc_180028D0E
0x180028c1a  lea     rax, [rcx+28h]
0x180028c1e  mov     [rsp+48h+CriticalSection], rcx
0x180028c23  mov     [rsp+48h+var_18], rax
0x180028c28  xor     ebx, ebx
0x180028c2a  mov     [rsp+48h+var_20], 0
0x180028c32  mov     [rsp+48h+var_10], 0
0x180028c3a  movsxd  rdi, ebx
0x180028c3d  add     rdi, rdi
0x180028c40  mov     rcx, [rsp+rdi*8+48h+CriticalSection]; CriticalSection
0x180028c45  call    cs:__imp_RtlInitializeCriticalSection
0x180028c4c  nop     dword ptr [rax+rax+00h]
0x180028c51  test    eax, eax
0x180028c53  js      loc_180028CFF
0x180028c59  add     ebx, ebp
0x180028c5b  mov     [rsp+rdi*8+48h+var_20], ebp
0x180028c5f  cmp     ebx, 2
0x180028c62  jb      short loc_180028C3A
0x180028c64  call    cs:__imp_RtlDllShutdownInProgress
0x180028c6b  nop     dword ptr [rax+rax+00h]
0x180028c70  test    al, al
0x180028c72  jnz     loc_180028D1A
0x180028c78  mov     r9d, ebp
0x180028c7b  lea     rcx, dword_180079160; CallbackContext
0x180028c82  call    TlgRegisterAggregateProviderEx
0x180028c87  mov     edi, eax
0x180028c89  test    eax, eax
0x180028c8b  jns     short loc_180028CA3
0x180028c8d  mov     ebx, 80004005h
0x180028c92  lea     rdx, aHrtlg; "hrTlg"
0x180028c99  mov     ecx, eax
0x180028c9b  mov     r9d, 4Fh ; 'O'
0x180028ca1  jmp     short loc_180028CC7
0x180028ca3  mov     r9d, ebp
0x180028ca6  lea     rcx, dword_180079128; CallbackContext
0x180028cad  call    TlgRegisterAggregateProviderEx
0x180028cb2  mov     ebx, eax
0x180028cb4  test    eax, eax
0x180028cb6  jns     short loc_180028CF5
0x180028cb8  mov     ecx, eax
0x180028cba  lea     rdx, aHrtlgcore; "hrTlgCore"
0x180028cc1  mov     r9d, 55h ; 'U'
0x180028cc7  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180028cce  call    DebugTraceError
0x180028cd3  test    edi, edi
0x180028cd5  js      short loc_180028D1A
0x180028cd7  lea     rcx, dword_180079160
0x180028cde  call    TlgUnregisterAggregateProvider
0x180028ce3  test    ebx, ebx
0x180028ce5  js      short loc_180028D1A
0x180028ce7  lea     rcx, dword_180079128
0x180028cee  call    TlgUnregisterAggregateProvider
0x180028cf3  jmp     short loc_180028D1A
0x180028cf5  mov     cs:dword_18007A77C, ebp
0x180028cfb  mov     eax, ebp
0x180028cfd  jmp     short loc_180028D43
0x180028cff  mov     r9d, 3Ch ; '<'
0x180028d05  lea     rdx, aStatus_0; "status"
0x180028d0c  mov     ecx, eax
0x180028d0e  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180028d15  call    DebugTraceError
0x180028d1a  xor     ebx, ebx
0x180028d1c  movsxd  rcx, ebx
0x180028d1f  add     rcx, rcx
0x180028d22  cmp     [rsp+rcx*8+48h+var_20], 0
0x180028d27  jz      short loc_180028D3A
0x180028d29  mov     rcx, [rsp+rcx*8+48h+CriticalSection]; CriticalSection
0x180028d2e  call    cs:__imp_RtlDeleteCriticalSection
0x180028d35  nop     dword ptr [rax+rax+00h]
0x180028d3a  add     ebx, ebp
0x180028d3c  cmp     ebx, 2
0x180028d3f  jb      short loc_180028D1C
0x180028d41  xor     eax, eax
0x180028d43  mov     rbx, [rsp+48h+arg_0]
0x180028d48  mov     rbp, [rsp+48h+arg_8]
0x180028d4d  add     rsp, 40h
0x180028d51  pop     rdi
0x180028d52  retn
```
