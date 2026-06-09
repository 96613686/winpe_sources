# ReadString

- ea: `0x1800356f8`
- end: `0x180035831`
- name: `ReadString`
- size: `313`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180031b4c`
- `0x180034ff0`

## callees

- `0x180022bd2`
- `0x1800327a8`
- `0x1800356f8`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003580a`
- `ntdll!RtlFreeHeap` at `0x18003580a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003573b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800357c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003573b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800357c5`

## string_xrefs

- `0x18003574d`: `Failed to read string length`
- `0x1800357d7`: `Failed to read the string from the registry`

## pseudocode

```c
__int64 __fastcall ReadString(HKEY hKey, LPCWSTR lpValueName, BYTE **a3)
{
  unsigned int Value; // eax
  unsigned int v7; // ebx
  const wchar_t *v8; // rdx
  __int64 v9; // rcx
  BYTE *HeapRoutine; // rax
  BYTE *lpData; // rdi
  const wchar_t *v12; // rdx
  DWORD Type[10]; // [rsp+30h] [rbp-28h] BYREF
  size_t Size; // [rsp+78h] [rbp+20h] BYREF

  Type[0] = 0;
  LODWORD(Size) = 0;
  Value = RegQueryValueExW(hKey, lpValueName, 0, Type, 0, (LPDWORD)&Size);
  v7 = Value;
  if ( Value )
  {
    v8 = L"Failed to read string length";
    v9 = Value;
LABEL_5:
    LogError(v9, v8);
    return v7;
  }
  LODWORD(Size) = Size + 2;
  HeapRoutine = (BYTE *)SockAllocateHeapRoutine(SockPrivateHeap, 0, (unsigned int)Size);
  lpData = HeapRoutine;
  if ( !HeapRoutine )
  {
    v7 = 8;
    v9 = 8;
    v8 = L"Failed to allocate space for the string value";
    goto LABEL_5;
  }
  memset_0(HeapRoutine, 0, (unsigned int)Size);
  v7 = RegQueryValueExW(hKey, lpValueName, 0, Type, lpData, (LPDWORD)&Size);
  if ( v7 )
  {
    v12 = L"Failed to read the string from the registry";
  }
  else
  {
    if ( Type[0] - 1 <= 1 )
    {
      *a3 = lpData;
      return v7;
    }
    v7 = 1804;
    v12 = L"Expected REG_SZ or REG_EXPAND_SZ value, and got a different value type";
  }
  LogError(v7, v12);
  RtlFreeHeap(SockPrivateHeap, 0, lpData);
  return v7;
}

```

## disassembly

```asm
0x1800356f8  mov     r11, rsp
0x1800356fb  mov     [r11+8], rbx
0x1800356ff  mov     [r11+10h], rbp
0x180035703  push    rsi
0x180035704  push    rdi
0x180035705  push    r14
0x180035707  sub     rsp, 40h
0x18003570b  lea     rax, [r11+20h]
0x18003570f  mov     [rsp+58h+Type], 0
0x180035717  mov     rsi, r8
0x18003571a  mov     [r11-30h], rax
0x18003571e  lea     r9, [r11-28h]; lpType
0x180035722  mov     qword ptr [r11-38h], 0
0x18003572a  xor     r8d, r8d; lpReserved
0x18003572d  mov     dword ptr [rsp+58h+Size], 0
0x180035735  mov     rbp, rdx
0x180035738  mov     r14, rcx
0x18003573b  call    cs:__imp_RegQueryValueExW
0x180035742  nop     dword ptr [rax+rax+00h]
0x180035747  mov     ebx, eax
0x180035749  test    eax, eax
0x18003574b  jz      short loc_180035758
0x18003574d  lea     rdx, aFailedToReadSt; "Failed to read string length"
0x180035754  mov     ecx, eax
0x180035756  jmp     short loc_18003578F
0x180035758  mov     eax, dword ptr [rsp+58h+Size]
0x18003575c  xor     edx, edx
0x18003575e  mov     rcx, cs:SockPrivateHeap
0x180035765  add     eax, 2
0x180035768  mov     dword ptr [rsp+58h+Size], eax
0x18003576c  mov     r8d, eax
0x18003576f  mov     rax, cs:SockAllocateHeapRoutine
0x180035776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003577b  mov     rdi, rax
0x18003577e  test    rax, rax
0x180035781  jnz     short loc_180035799
0x180035783  lea     ebx, [rax+8]
0x180035786  mov     ecx, ebx
0x180035788  lea     rdx, aFailedToAlloca_2; "Failed to allocate space for the string"...
0x18003578f  call    LogError
0x180035794  jmp     loc_18003581B
0x180035799  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x18003579e  xor     edx, edx; Val
0x1800357a0  mov     rcx, rdi; void *
0x1800357a3  call    memset_0
0x1800357a8  lea     rax, [rsp+58h+Size]
0x1800357ad  xor     r8d, r8d; lpReserved
0x1800357b0  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800357b5  lea     r9, [rsp+58h+Type]; lpType
0x1800357ba  mov     rdx, rbp; lpValueName
0x1800357bd  mov     [rsp+58h+lpData], rdi; lpData
0x1800357c2  mov     rcx, r14; hKey
0x1800357c5  call    cs:__imp_RegQueryValueExW
0x1800357cc  nop     dword ptr [rax+rax+00h]
0x1800357d1  mov     ebx, eax
0x1800357d3  test    eax, eax
0x1800357d5  jz      short loc_1800357E0
0x1800357d7  lea     rdx, aFailedToReadTh_11; "Failed to read the string from the regi"...
0x1800357de  jmp     short loc_1800357F7
0x1800357e0  mov     eax, [rsp+58h+Type]
0x1800357e4  dec     eax
0x1800357e6  cmp     eax, 1
0x1800357e9  jbe     short loc_180035818
0x1800357eb  mov     ebx, 70Ch
0x1800357f0  lea     rdx, aExpectedRegSzO; "Expected REG_SZ or REG_EXPAND_SZ value,"...
0x1800357f7  mov     ecx, ebx
0x1800357f9  call    LogError
0x1800357fe  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180035805  mov     r8, rdi; P
0x180035808  xor     edx, edx; Flags
0x18003580a  call    cs:__imp_RtlFreeHeap
0x180035811  nop     dword ptr [rax+rax+00h]
0x180035816  jmp     short loc_18003581B
0x180035818  mov     [rsi], rdi
0x18003581b  mov     rbp, [rsp+58h+arg_8]
0x180035820  mov     eax, ebx
0x180035822  mov     rbx, [rsp+58h+arg_0]
0x180035827  add     rsp, 40h
0x18003582b  pop     r14
0x18003582d  pop     rdi
0x18003582e  pop     rsi
0x18003582f  retn
```
