# SxRegCreateKeyExStateSeparated(ushort const *,HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)

- ea: `0x18002a720`
- end: `0x18002a866`
- name: `?SxRegCreateKeyExStateSeparated@@YAJPEBGPEAUHKEY__@@0KPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z`
- size: `326`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, REGSAM, struct _SECURITY_ATTRIBUTES *, PHKEY, unsigned int *)`
- caller_count: `7`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800298ec`
- `0x180029dbc`
- `0x18002a02c`
- `0x18002a1d0`
- `0x18002a4b0`
- `0x1800384b8`
- `0x1800546e8`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800156a0`
- `0x18002a720`
- `0x180067b0a`
- `0x180067b30`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18002a7a8`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002a7a8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a7ec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a7ec`

## string_xrefs

- `0x18002a74f`: `SxRegCreateKeyExStateSeparated`

## pseudocode

```c
__int64 __fastcall SxRegCreateKeyExStateSeparated(
        const unsigned __int16 *a1,
        HKEY a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned int a6,
        REGSAM samDesired,
        struct _SECURITY_ATTRIBUTES *a8,
        PHKEY phkResult)
{
  int PersistedStateLocation; // eax
  LSTATUS Key; // eax
  signed int v13; // ebx
  __int16 v14; // ax
  bool v15; // sf
  signed int v17; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v18; // [rsp+54h] [rbp-ACh]
  __int16 v19; // [rsp+56h] [rbp-AAh]
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "SxRegCreateKeyExStateSeparated", 290, 2);
  memset_0(SubKey, 0, 0x208u);
  PersistedStateLocation = RtlGetPersistedStateLocation(a1, 0, a3, 0, SubKey, 260, 0);
  if ( PersistedStateLocation < 0 )
  {
    v13 = HRESULTFromNTSTATUS((unsigned int)PersistedStateLocation);
    v17 = v13;
    v15 = v13 < 0;
    v14 = 322;
  }
  else
  {
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, samDesired, 0, phkResult, 0);
    v13 = Key;
    if ( !Key )
    {
      v13 = v17;
      goto LABEL_11;
    }
    if ( Key > 0 )
      v13 = (unsigned __int16)Key | 0x80070000;
    v17 = v13;
    v14 = 317;
    v15 = v13 < 0;
  }
  if ( v15 )
    v19 = v14;
  else
    v18 = v14;
LABEL_11:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002a720  mov     [rsp-8+arg_8], rbx
0x18002a725  push    rbp
0x18002a726  push    rsi
0x18002a727  push    rdi
0x18002a728  lea     rbp, [rsp-1B0h]
0x18002a730  sub     rsp, 2B0h
0x18002a737  mov     rax, cs:__security_cookie
0x18002a73e  xor     rax, rsp
0x18002a741  mov     [rbp+1C0h+var_20], rax
0x18002a748  mov     rsi, [rbp+1C0h+arg_40]
0x18002a74f  lea     rdx, aSxregcreatekey; "SxRegCreateKeyExStateSeparated"
0x18002a756  mov     rdi, r8
0x18002a759  mov     rbx, rcx
0x18002a75c  mov     r8d, 122h; unsigned __int16
0x18002a762  lea     rcx, [rsp+2C0h+var_270]; this
0x18002a767  mov     r9d, 2; unsigned __int16
0x18002a76d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002a772  xor     edx, edx; Val
0x18002a774  lea     rcx, [rbp+1C0h+SubKey]; void *
0x18002a778  mov     r8d, 208h; Size
0x18002a77e  call    memset_0
0x18002a783  lea     rax, [rbp+1C0h+SubKey]
0x18002a787  mov     [rsp+2C0h+lpSecurityAttributes], 0
0x18002a790  mov     [rsp+2C0h+samDesired], 104h
0x18002a798  xor     r9d, r9d
0x18002a79b  mov     r8, rdi
0x18002a79e  mov     qword ptr [rsp+2C0h+dwOptions], rax
0x18002a7a3  xor     edx, edx
0x18002a7a5  mov     rcx, rbx
0x18002a7a8  call    cs:__imp_RtlGetPersistedStateLocation
0x18002a7ae  test    eax, eax
0x18002a7b0  js      short loc_18002A81D
0x18002a7b2  mov     eax, [rbp+1C0h+arg_30]
0x18002a7b8  lea     rdx, [rbp+1C0h+SubKey]; lpSubKey
0x18002a7bc  mov     [rsp+2C0h+lpdwDisposition], 0; lpdwDisposition
0x18002a7c5  xor     r9d, r9d; lpClass
0x18002a7c8  mov     [rsp+2C0h+phkResult], rsi; phkResult
0x18002a7cd  xor     r8d, r8d; Reserved
0x18002a7d0  mov     [rsp+2C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002a7d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a7e0  mov     [rsp+2C0h+samDesired], eax; samDesired
0x18002a7e4  mov     [rsp+2C0h+dwOptions], 0; dwOptions
0x18002a7ec  call    cs:__imp_RegCreateKeyExW
0x18002a7f2  mov     ebx, eax
0x18002a7f4  test    eax, eax
0x18002a7f6  jz      short loc_18002A817
0x18002a7f8  jle     short loc_18002A803
0x18002a7fa  movzx   ebx, ax
0x18002a7fd  or      ebx, 80070000h
0x18002a803  mov     [rsp+2C0h+var_270], ebx
0x18002a807  mov     eax, 13Dh
0x18002a80c  test    ebx, ebx
0x18002a80e  jns     short loc_18002A833
0x18002a810  mov     [rsp+2C0h+var_26A], ax
0x18002a815  jmp     short loc_18002A838
0x18002a817  mov     ebx, [rsp+2C0h+var_270]
0x18002a81b  jmp     short loc_18002A838
0x18002a81d  mov     ecx, eax
0x18002a81f  call    HRESULTFromNTSTATUS
0x18002a824  mov     ebx, eax
0x18002a826  mov     [rsp+2C0h+var_270], eax
0x18002a82a  test    eax, eax
0x18002a82c  mov     eax, 142h
0x18002a831  jmp     short loc_18002A80E
0x18002a833  mov     [rsp+2C0h+var_26C], ax
0x18002a838  lea     rcx, [rsp+2C0h+var_270]; this
0x18002a83d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002a842  mov     eax, ebx
0x18002a844  mov     rcx, [rbp+1C0h+var_20]
0x18002a84b  xor     rcx, rsp; StackCookie
0x18002a84e  call    __security_check_cookie
0x18002a853  mov     rbx, [rsp+2C0h+arg_8]
0x18002a85b  add     rsp, 2B0h
0x18002a862  pop     rdi
0x18002a863  pop     rsi
0x18002a864  pop     rbp
0x18002a865  retn
```
