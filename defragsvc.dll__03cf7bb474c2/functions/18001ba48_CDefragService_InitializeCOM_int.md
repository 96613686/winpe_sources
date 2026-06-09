# CDefragService::InitializeCOM(int)

- ea: `0x18001ba48`
- end: `0x18001bb03`
- name: `?InitializeCOM@CDefragService@@QEAAJH@Z`
- size: `187`
- prototype: `__int64 __fastcall(CDefragService *__hidden this, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b6a8`
- `0x18004a710`
- `0x18004a7a0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001ba48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bad2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bad2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001ba79`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001ba93`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001ba79`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001ba93`

## string_xrefs

- `0x18001ba60`: `CDefragService::InitializeCOM`

## pseudocode

```c
__int64 __fastcall CDefragService::InitializeCOM(CDefragService *this, int a2)
{
  HRESULT v3; // ebx
  HRESULT v5; // [rsp+20h] [rbp-48h] BYREF
  __int16 v6; // [rsp+24h] [rbp-44h]
  __int16 v7; // [rsp+26h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v5, "CDefragService::InitializeCOM", 896, 1);
  v3 = CoInitializeEx(0, 0xCu);
  v5 = v3;
  if ( v3 == -2147467263 )
  {
    v3 = CoInitializeEx(0, 4u);
    v5 = v3;
  }
  if ( a2 && v3 == -2147417850 )
  {
    v3 = 0;
    v5 = 0;
    v6 = 915;
  }
  else if ( v3 >= 0 )
  {
    v6 = 917;
    dword_180089AD4 = GetCurrentThreadId();
    dword_180089ADC = 1;
    v3 = v5;
  }
  else
  {
    v7 = 917;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001ba48  mov     [rsp+arg_0], rbx
0x18001ba4d  push    rdi
0x18001ba4e  sub     rsp, 60h
0x18001ba52  mov     edi, edx
0x18001ba54  mov     r9d, 1; unsigned __int16
0x18001ba5a  mov     r8d, 380h; unsigned __int16
0x18001ba60  lea     rdx, aCdefragservice; "CDefragService::InitializeCOM"
0x18001ba67  lea     rcx, [rsp+68h+var_48]; this
0x18001ba6c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001ba71  nop
0x18001ba72  mov     edx, 0Ch; dwCoInit
0x18001ba77  xor     ecx, ecx; pvReserved
0x18001ba79  call    cs:__imp_CoInitializeEx
0x18001ba7f  mov     ebx, eax
0x18001ba81  mov     [rsp+68h+var_48], eax
0x18001ba85  cmp     eax, 80004001h
0x18001ba8a  jnz     short loc_18001BA9F
0x18001ba8c  mov     edx, 4; dwCoInit
0x18001ba91  xor     ecx, ecx; pvReserved
0x18001ba93  call    cs:__imp_CoInitializeEx
0x18001ba99  mov     ebx, eax
0x18001ba9b  mov     [rsp+68h+var_48], eax
0x18001ba9f  test    edi, edi
0x18001baa1  jz      short loc_18001BABD
0x18001baa3  cmp     ebx, 80010106h
0x18001baa9  jnz     short loc_18001BABD
0x18001baab  xor     ebx, ebx
0x18001baad  mov     [rsp+68h+var_48], ebx
0x18001bab1  mov     eax, 393h
0x18001bab6  mov     [rsp+68h+var_44], ax
0x18001babb  jmp     short loc_18001BAEC
0x18001babd  mov     eax, 395h
0x18001bac2  test    ebx, ebx
0x18001bac4  jns     short loc_18001BACD
0x18001bac6  mov     [rsp+68h+var_42], ax
0x18001bacb  jmp     short loc_18001BAEC
0x18001bacd  mov     [rsp+68h+var_44], ax
0x18001bad2  call    cs:__imp_GetCurrentThreadId
0x18001bad8  mov     cs:dword_180089AD4, eax
0x18001bade  mov     cs:dword_180089ADC, 1
0x18001bae8  mov     ebx, [rsp+68h+var_48]
0x18001baec  lea     rcx, [rsp+68h+var_48]; this
0x18001baf1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001baf6  mov     eax, ebx
0x18001baf8  mov     rbx, [rsp+68h+arg_0]
0x18001bafd  add     rsp, 60h
0x18001bb01  pop     rdi
0x18001bb02  retn
```
