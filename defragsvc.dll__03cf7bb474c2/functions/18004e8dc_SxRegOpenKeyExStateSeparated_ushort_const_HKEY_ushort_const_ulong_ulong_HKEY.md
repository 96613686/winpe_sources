# SxRegOpenKeyExStateSeparated(ushort const *,HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)

- ea: `0x18004e8dc`
- end: `0x18004e9ff`
- name: `?SxRegOpenKeyExStateSeparated@@YAJPEBGPEAUHKEY__@@0KKPEAPEAU1@@Z`
- size: `291`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY, const unsigned __int16 *, unsigned int, unsigned int, PHKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800298ec`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800156a0`
- `0x18004e8dc`
- `0x180067b0a`
- `0x180067b30`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18004e964`
- `ntdll!RtlGetPersistedStateLocation` at `0x18004e964`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004e987`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004e987`

## string_xrefs

- `0x18004e909`: `SxRegOpenKeyExStateSeparated`

## pseudocode

```c
__int64 __fastcall SxRegOpenKeyExStateSeparated(
        const unsigned __int16 *a1,
        HKEY a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5,
        PHKEY phkResult)
{
  int PersistedStateLocation; // eax
  LSTATUS v7; // eax
  signed int v8; // ebx
  __int16 v9; // ax
  bool v10; // sf
  signed int v12; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v13; // [rsp+44h] [rbp-BCh]
  __int16 v14; // [rsp+46h] [rbp-BAh]
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "SxRegOpenKeyExStateSeparated", 239, 2);
  memset_0(SubKey, 0, 0x208u);
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"OptimalLayout",
                             0,
                             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OptimalLayout",
                             0,
                             SubKey,
                             260,
                             0);
  if ( PersistedStateLocation < 0 )
  {
    v8 = HRESULTFromNTSTATUS((unsigned int)PersistedStateLocation);
    v12 = v8;
    v10 = v8 < 0;
    v9 = 267;
  }
  else
  {
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, phkResult);
    v8 = v7;
    if ( !v7 )
    {
      v8 = v12;
      goto LABEL_11;
    }
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    v12 = v8;
    v9 = 262;
    v10 = v8 < 0;
  }
  if ( v10 )
    v14 = v9;
  else
    v13 = v9;
LABEL_11:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004e8dc  mov     [rsp-8+arg_0], rbx
0x18004e8e1  push    rbp
0x18004e8e2  lea     rbp, [rsp-1A0h]
0x18004e8ea  sub     rsp, 2A0h
0x18004e8f1  mov     rax, cs:__security_cookie
0x18004e8f8  xor     rax, rsp
0x18004e8fb  mov     [rbp+1A0h+var_10], rax
0x18004e902  mov     rbx, [rbp+1A0h+arg_28]
0x18004e909  lea     rdx, aSxregopenkeyex; "SxRegOpenKeyExStateSeparated"
0x18004e910  mov     r9d, 2; unsigned __int16
0x18004e916  lea     rcx, [rsp+2A0h+var_260]; this
0x18004e91b  mov     r8d, 0EFh; unsigned __int16
0x18004e921  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004e926  xor     edx, edx; Val
0x18004e928  lea     rcx, [rbp+1A0h+SubKey]; void *
0x18004e92c  mov     r8d, 208h; Size
0x18004e932  call    memset_0
0x18004e937  lea     rax, [rbp+1A0h+SubKey]
0x18004e93b  mov     [rsp+2A0h+var_270], 0
0x18004e944  mov     [rsp+2A0h+var_278], 104h
0x18004e94c  lea     r8, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18004e953  xor     r9d, r9d
0x18004e956  mov     [rsp+2A0h+phkResult], rax
0x18004e95b  xor     edx, edx
0x18004e95d  lea     rcx, aOptimallayout; "OptimalLayout"
0x18004e964  call    cs:__imp_RtlGetPersistedStateLocation
0x18004e96a  test    eax, eax
0x18004e96c  js      short loc_18004E9B8
0x18004e96e  mov     r9d, 20019h; samDesired
0x18004e974  mov     [rsp+2A0h+phkResult], rbx; phkResult
0x18004e979  xor     r8d, r8d; ulOptions
0x18004e97c  lea     rdx, [rbp+1A0h+SubKey]; lpSubKey
0x18004e980  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004e987  call    cs:__imp_RegOpenKeyExW
0x18004e98d  mov     ebx, eax
0x18004e98f  test    eax, eax
0x18004e991  jz      short loc_18004E9B2
0x18004e993  jle     short loc_18004E99E
0x18004e995  movzx   ebx, ax
0x18004e998  or      ebx, 80070000h
0x18004e99e  mov     [rsp+2A0h+var_260], ebx
0x18004e9a2  mov     eax, 106h
0x18004e9a7  test    ebx, ebx
0x18004e9a9  jns     short loc_18004E9CE
0x18004e9ab  mov     [rsp+2A0h+var_25A], ax
0x18004e9b0  jmp     short loc_18004E9D3
0x18004e9b2  mov     ebx, [rsp+2A0h+var_260]
0x18004e9b6  jmp     short loc_18004E9D3
0x18004e9b8  mov     ecx, eax
0x18004e9ba  call    HRESULTFromNTSTATUS
0x18004e9bf  mov     ebx, eax
0x18004e9c1  mov     [rsp+2A0h+var_260], eax
0x18004e9c5  test    eax, eax
0x18004e9c7  mov     eax, 10Bh
0x18004e9cc  jmp     short loc_18004E9A9
0x18004e9ce  mov     [rsp+2A0h+var_25C], ax
0x18004e9d3  lea     rcx, [rsp+2A0h+var_260]; this
0x18004e9d8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004e9dd  mov     eax, ebx
0x18004e9df  mov     rcx, [rbp+1A0h+var_10]
0x18004e9e6  xor     rcx, rsp; StackCookie
0x18004e9e9  call    __security_check_cookie
0x18004e9ee  mov     rbx, [rsp+2A0h+arg_0]
0x18004e9f6  add     rsp, 2A0h
0x18004e9fd  pop     rbp
0x18004e9fe  retn
```
