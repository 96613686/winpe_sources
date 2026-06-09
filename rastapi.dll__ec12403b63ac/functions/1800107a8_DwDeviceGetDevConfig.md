# DwDeviceGetDevConfig

- ea: `0x1800107a8`
- end: `0x180010897`
- name: `DwDeviceGetDevConfig`
- size: `239`
- prototype: `__int64 __fastcall(char *String2, void *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000feb0`
- `0x18000fec0`

## callees

- `0x18000d92c`
- `0x1800107a8`
- `0x180010c04`
- `0x180012340`
- `0x180029266`

## import_xrefs

- `msvcrt!_stricmp` at `0x1800107cf`
- `msvcrt!_stricmp` at `0x180010818`
- `msvcrt!_stricmp` at `0x1800107cf`
- `msvcrt!_stricmp` at `0x180010818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001088a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001088a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010880`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010880`

## string_xrefs

- `0x1800107e5`: `DeviceGetDevConfig: port %s not found`

## pseudocode

```c
__int64 __fastcall DwDeviceGetDevConfig(char *String2, void *a2, unsigned int *a3)
{
  HLOCAL i; // rbx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  const void *v12; // rdx
  unsigned int v13; // ebx
  unsigned int DevConfig; // esi

  for ( i = RasPortsList; ; i = (HLOCAL)*((_QWORD *)i + 1) )
  {
    if ( !i )
    {
      RasTapiTrace("DeviceGetDevConfig: port %s not found");
      RasTapiTrace(" ");
      return 615;
    }
    if ( !_stricmp((const char *)i + 24, String2) )
      break;
  }
  if ( !_stricmp((const char *)i + 64, "MODEM") )
  {
    GetMutex(v9, v8, v10, v11);
    v12 = (const void *)*((_QWORD *)i + 133);
    if ( v12 )
    {
      v13 = *((_DWORD *)i + 268);
      if ( *a3 < v13 )
      {
        DevConfig = 603;
      }
      else
      {
        memcpy_0(a2, v12, v13);
        DevConfig = 0;
      }
      *a3 = v13;
    }
    else
    {
      DevConfig = DwGetDevConfig(*(_DWORD *)(*((_QWORD *)i + 27) + 8LL));
    }
    if ( !ReleaseMutex(RasTapiMutex) )
      GetLastError();
    return DevConfig;
  }
  else
  {
    *a3 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x1800107a8  push    rbx
0x1800107aa  push    rbp
0x1800107ab  push    rsi
0x1800107ac  push    rdi
0x1800107ad  push    r14
0x1800107af  sub     rsp, 20h
0x1800107b3  mov     rbx, cs:RasPortsList
0x1800107ba  mov     r14d, r9d
0x1800107bd  mov     rdi, r8
0x1800107c0  mov     rbp, rdx
0x1800107c3  mov     rsi, rcx
0x1800107c6  jmp     short loc_1800107DD
0x1800107c8  lea     rcx, [rbx+18h]; String1
0x1800107cc  mov     rdx, rsi; String2
0x1800107cf  call    cs:__imp__stricmp
0x1800107d5  test    eax, eax
0x1800107d7  jz      short loc_18001080D
0x1800107d9  mov     rbx, [rbx+8]
0x1800107dd  test    rbx, rbx
0x1800107e0  jnz     short loc_1800107C8
0x1800107e2  mov     rdx, rsi
0x1800107e5  lea     rcx, aDevicegetdevco_1; "DeviceGetDevConfig: port %s not found"
0x1800107ec  call    RasTapiTrace
0x1800107f1  lea     rcx, asc_18002C0B8; " "
0x1800107f8  call    RasTapiTrace
0x1800107fd  mov     eax, 267h
0x180010802  add     rsp, 20h
0x180010806  pop     r14
0x180010808  pop     rdi
0x180010809  pop     rsi
0x18001080a  pop     rbp
0x18001080b  pop     rbx
0x18001080c  retn
0x18001080d  lea     rcx, [rbx+40h]; String1
0x180010811  lea     rdx, aModem; "MODEM"
0x180010818  call    cs:__imp__stricmp
0x18001081e  test    eax, eax
0x180010820  jz      short loc_18001082C
0x180010822  mov     dword ptr [rdi], 0
0x180010828  xor     eax, eax
0x18001082a  jmp     short loc_180010802
0x18001082c  call    GetMutex
0x180010831  mov     rdx, [rbx+428h]; Src
0x180010838  test    rdx, rdx
0x18001083b  jz      short loc_18001085F
0x18001083d  mov     ebx, [rbx+430h]
0x180010843  cmp     [rdi], ebx
0x180010845  jb      short loc_180010856
0x180010847  mov     r8d, ebx; Size
0x18001084a  mov     rcx, rbp; void *
0x18001084d  call    memcpy_0
0x180010852  xor     esi, esi
0x180010854  jmp     short loc_18001085B
0x180010856  mov     esi, 25Bh
0x18001085b  mov     [rdi], ebx
0x18001085d  jmp     short loc_180010879
0x18001085f  mov     rcx, [rbx+0D8h]
0x180010866  mov     r9d, r14d
0x180010869  mov     r8, rdi
0x18001086c  mov     rdx, rbp
0x18001086f  mov     ecx, [rcx+8]; dwDeviceID
0x180010872  call    DwGetDevConfig
0x180010877  mov     esi, eax
0x180010879  mov     rcx, cs:RasTapiMutex; hMutex
0x180010880  call    cs:__imp_ReleaseMutex
0x180010886  test    eax, eax
0x180010888  jnz     short loc_180010890
0x18001088a  call    cs:__imp_GetLastError
0x180010890  mov     eax, esi
0x180010892  jmp     loc_180010802
```
