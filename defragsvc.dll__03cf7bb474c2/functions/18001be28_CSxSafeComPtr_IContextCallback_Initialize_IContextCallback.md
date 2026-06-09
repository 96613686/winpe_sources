# CSxSafeComPtr<IContextCallback>::Initialize(IContextCallback *)

- ea: `0x18001be28`
- end: `0x18001bf27`
- name: `?Initialize@?$CSxSafeComPtr@UIContextCallback@@@@QEAAJPEAUIContextCallback@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b6a8`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001be28`
- `0x18001c624`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bf0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bf0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001be7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001be7c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001beba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001beba`

## string_xrefs

- `0x18001be44`: `CSxSafeComPtr<struct IContextCallback>::Initialize`

## pseudocode

```c
__int64 __fastcall CSxSafeComPtr<IContextCallback>::Initialize(LPVOID *ppv, __int64 a2)
{
  __int16 v4; // ax
  unsigned int v5; // ebx
  HRESULT Instance; // [rsp+30h] [rbp-48h] BYREF
  __int16 v8; // [rsp+34h] [rbp-44h]
  __int16 v9; // [rsp+36h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&Instance,
    "CSxSafeComPtr<struct IContextCallback>::Initialize",
    82,
    1);
  Instance = CSxSafeCriticalSection::Init((LPCRITICAL_SECTION)(ppv + 2));
  if ( Instance >= 0 )
  {
    v8 = 84;
    EnterCriticalSection((LPCRITICAL_SECTION)(ppv + 2));
    if ( *((_BYTE *)ppv + 64) )
    {
      Instance = 1;
      v8 = 90;
LABEL_11:
      LeaveCriticalSection((LPCRITICAL_SECTION)(ppv + 2));
      goto LABEL_12;
    }
    if ( !*ppv )
    {
      Instance = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, ppv);
      v4 = 99;
      if ( Instance < 0 )
      {
LABEL_7:
        v9 = v4;
        goto LABEL_11;
      }
      v8 = 99;
    }
    Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, LPVOID *))(*(_QWORD *)*ppv + 24LL))(
                 *ppv,
                 a2,
                 &GUID_000001da_0000_0000_c000_000000000046,
                 ppv + 1);
    v4 = 107;
    if ( Instance >= 0 )
    {
      v8 = 107;
      *((_BYTE *)ppv + 64) = 1;
      goto LABEL_11;
    }
    goto LABEL_7;
  }
  v9 = 84;
LABEL_12:
  v5 = Instance;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&Instance);
  return v5;
}

```

## disassembly

```asm
0x18001be28  push    rbp
0x18001be2a  push    rbx
0x18001be2b  push    rsi
0x18001be2c  push    rdi
0x18001be2d  mov     rbp, rsp
0x18001be30  sub     rsp, 78h
0x18001be34  mov     rsi, rdx
0x18001be37  mov     rdi, rcx
0x18001be3a  mov     r9d, 1; unsigned __int16
0x18001be40  lea     r8d, [r9+51h]; unsigned __int16
0x18001be44  lea     rdx, aCsxsafecomptrS_1; "CSxSafeComPtr<struct IContextCallback>:"...
0x18001be4b  lea     rcx, [rbp+var_48]; this
0x18001be4f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001be54  lea     rbx, [rdi+10h]
0x18001be58  mov     rcx, rbx; lpCriticalSection
0x18001be5b  call    ?Init@CSxSafeCriticalSection@@QEAAJXZ; CSxSafeCriticalSection::Init(void)
0x18001be60  mov     [rbp+var_48], eax
0x18001be63  test    eax, eax
0x18001be65  mov     eax, 54h ; 'T'
0x18001be6a  jns     short loc_18001BE75
0x18001be6c  mov     [rbp+var_42], ax
0x18001be70  jmp     loc_18001BF10
0x18001be75  mov     [rbp+var_44], ax
0x18001be79  mov     rcx, rbx; lpCriticalSection
0x18001be7c  call    cs:__imp_EnterCriticalSection
0x18001be82  mov     al, [rdi+40h]
0x18001be85  test    al, al
0x18001be87  jz      short loc_18001BE9B
0x18001be89  mov     [rbp+var_48], 1
0x18001be90  mov     eax, 5Ah ; 'Z'
0x18001be95  mov     [rbp+var_44], ax
0x18001be99  jmp     short loc_18001BF07
0x18001be9b  cmp     qword ptr [rdi], 0
0x18001be9f  jnz     short loc_18001BED6
0x18001bea1  mov     [rsp+78h+ppv], rdi; ppv
0x18001bea6  lea     r9, IID_IGlobalInterfaceTable; riid
0x18001bead  xor     edx, edx; pUnkOuter
0x18001beaf  lea     r8d, [rdx+1]; dwClsContext
0x18001beb3  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18001beba  call    cs:__imp_CoCreateInstance
0x18001bec0  mov     [rbp+var_48], eax
0x18001bec3  test    eax, eax
0x18001bec5  mov     eax, 63h ; 'c'
0x18001beca  jns     short loc_18001BED2
0x18001becc  mov     [rbp+var_42], ax
0x18001bed0  jmp     short loc_18001BF07
0x18001bed2  mov     [rbp+var_44], ax
0x18001bed6  mov     rcx, [rdi]
0x18001bed9  mov     rax, [rcx]
0x18001bedc  lea     r9, [rdi+8]
0x18001bee0  lea     r8, _GUID_000001da_0000_0000_c000_000000000046
0x18001bee7  mov     rdx, rsi
0x18001beea  mov     rax, [rax+18h]
0x18001beee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bef3  mov     [rbp+var_48], eax
0x18001bef6  test    eax, eax
0x18001bef8  mov     eax, 6Bh ; 'k'
0x18001befd  js      short loc_18001BECC
0x18001beff  mov     [rbp+var_44], ax
0x18001bf03  mov     byte ptr [rdi+40h], 1
0x18001bf07  mov     rcx, rbx; lpCriticalSection
0x18001bf0a  call    cs:__imp_LeaveCriticalSection
0x18001bf10  mov     ebx, [rbp+var_48]
0x18001bf13  lea     rcx, [rbp+var_48]; this
0x18001bf17  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001bf1c  mov     eax, ebx
0x18001bf1e  add     rsp, 78h
0x18001bf22  pop     rdi
0x18001bf23  pop     rsi
0x18001bf24  pop     rbx
0x18001bf25  pop     rbp
0x18001bf26  retn
```
