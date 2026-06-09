# ClrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)

- ea: `0x180037964`
- end: `0x180037ad1`
- name: `?ClrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z`
- size: `365`
- prototype: `LSTATUS __fastcall(HKEY, const unsigned __int16 *, __int64, unsigned __int16 *, DWORD dwOptions, REGSAM samDesired, struct _SECURITY_ATTRIBUTES *, HKEY *phkResult)`
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003874`
- `0x180003a54`
- `0x180006328`
- `0x180016920`
- `0x180016ca8`
- `0x180017a10`
- `0x180019444`
- `0x18001b57c`

## callees

- `0x1800375ac`
- `0x18003784c`
- `0x180037964`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180037a3c`
- `ADVAPI32!RegCreateKeyExW` at `0x180037ab1`
- `ADVAPI32!RegCreateKeyExW` at `0x180037a3c`
- `ADVAPI32!RegCreateKeyExW` at `0x180037ab1`
- `KERNEL32!HeapFree` at `0x180037a74`
- `KERNEL32!HeapFree` at `0x180037a74`
- `KERNEL32!GetProcessHeap` at `0x180037a5f`
- `KERNEL32!GetProcessHeap` at `0x180037a5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LSTATUS __fastcall ClrRegCreateKeyEx(
        HKEY a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        DWORD dwOptions,
        REGSAM samDesired,
        struct _SECURITY_ATTRIBUTES *a7,
        HKEY *phkResult)
{
  LSTATUS result; // eax
  LSTATUS Key; // edi
  int v12; // eax
  const WCHAR *v13; // rdx
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+58h] [rbp-18h] BYREF
  int v17; // [rsp+60h] [rbp-10h]

  if ( !byte_180070040 )
  {
    result = ParseRegistryRootConfigValue();
    if ( result )
      return result;
    byte_180070040 = 1;
  }
  if ( !qword_180070038 )
    return RegCreateKeyExW(a1, a2, 0, 0, dwOptions, samDesired, 0, phkResult, 0);
  v17 = 0;
  lpMem = 0;
  Key = RedirectKey(samDesired, a1, a2, (unsigned __int16 **)&lpMem);
  v12 = v17;
  v13 = (const WCHAR *)lpMem;
  if ( lpMem )
    v12 = 1;
  v17 = v12;
  if ( !Key )
  {
    if ( !lpMem )
      v13 = a2;
    Key = RegCreateKeyExW(a1, v13, 0, 0, dwOptions, samDesired, 0, phkResult, 0);
  }
  if ( v17 )
  {
    v14 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v14);
    }
    v17 = 0;
  }
  return Key;
}

```

## disassembly

```asm
0x180037964  mov     [rsp-18h+arg_0], rbx
0x180037969  mov     [rsp-18h+arg_8], rsi
0x18003796e  mov     [rsp-18h+arg_10], rdi
0x180037973  push    rbp
0x180037974  push    r12
0x180037976  push    r14
0x180037978  mov     rbp, rsp
0x18003797b  sub     rsp, 70h
0x18003797f  mov     rbx, rdx
0x180037982  mov     rsi, rcx
0x180037985  and     [rbp+var_20], 0
0x180037989  mov     al, cs:byte_180070040
0x18003798f  mov     r12d, 1
0x180037995  test    al, al
0x180037997  jnz     short loc_1800379AD
0x180037999  call    ?ParseRegistryRootConfigValue@@YAJXZ; ParseRegistryRootConfigValue(void)
0x18003799e  test    eax, eax
0x1800379a0  jnz     loc_180037AB7
0x1800379a6  mov     cs:byte_180070040, r12b
0x1800379ad  cmp     cs:qword_180070038, 0
0x1800379b5  jz      loc_180037A82
0x1800379bb  and     [rbp+lpMem], 0
0x1800379c0  and     [rbp+var_10], 0
0x1800379c4  lea     rax, [rbp+lpMem]
0x1800379c8  mov     [rbp+arg_30], rax
0x1800379cc  and     [rbp+lpMem], 0
0x1800379d1  mov     [rbp+var_20], r12d
0x1800379d5  lea     r9, [rbp+lpMem]; unsigned __int16 **
0x1800379d9  mov     r8, rbx; unsigned __int16 *
0x1800379dc  mov     rdx, rsi; HKEY
0x1800379df  mov     r14d, [rbp+arg_28]
0x1800379e3  mov     ecx, r14d; unsigned int
0x1800379e6  call    ?RedirectKey@@YAJKPEAUHKEY__@@PEBGPEAPEAG@Z; RedirectKey(ulong,HKEY__ *,ushort const *,ushort * *)
0x1800379eb  mov     edi, eax
0x1800379ed  mov     eax, r12d
0x1800379f0  and     eax, 0FFFFFFFEh
0x1800379f3  mov     [rbp+var_20], eax
0x1800379f6  mov     eax, [rbp+var_10]
0x1800379f9  mov     rdx, [rbp+lpMem]
0x1800379fd  test    rdx, rdx
0x180037a00  cmovnz  eax, r12d
0x180037a04  mov     [rbp+var_10], eax
0x180037a07  test    edi, edi
0x180037a09  jnz     short loc_180037A44
0x180037a0b  test    rdx, rdx
0x180037a0e  cmovz   rdx, rbx; lpSubKey
0x180037a12  and     [rsp+70h+var_30], 0
0x180037a18  mov     rax, [rbp+arg_38]
0x180037a1c  mov     [rsp+70h+phkResult], rax; phkResult
0x180037a21  and     [rsp+70h+var_40], 0
0x180037a27  mov     [rsp+70h+samDesired], r14d; samDesired
0x180037a2c  mov     eax, [rbp+arg_20]
0x180037a2f  mov     [rsp+70h+dwOptions], eax; dwOptions
0x180037a33  xor     r9d, r9d; lpClass
0x180037a36  xor     r8d, r8d; Reserved
0x180037a39  mov     rcx, rsi; hKey
0x180037a3c  call    cs:__imp_RegCreateKeyExW
0x180037a42  mov     edi, eax
0x180037a44  cmp     [rbp+var_10], 0
0x180037a48  jz      short loc_180037A7E
0x180037a4a  mov     rbx, [rbp+lpMem]
0x180037a4e  test    rbx, rbx
0x180037a51  jz      short loc_180037A7A
0x180037a53  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180037a5a  test    rax, rax
0x180037a5d  jnz     short loc_180037A6C
0x180037a5f  call    cs:__imp_GetProcessHeap
0x180037a65  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180037a6c  mov     r8, rbx; lpMem
0x180037a6f  xor     edx, edx; dwFlags
0x180037a71  mov     rcx, rax; hHeap
0x180037a74  call    cs:__imp_HeapFree
0x180037a7a  and     [rbp+var_10], 0
0x180037a7e  mov     eax, edi
0x180037a80  jmp     short loc_180037AB7
0x180037a82  and     [rsp+70h+var_30], 0
0x180037a88  mov     rax, [rbp+arg_38]
0x180037a8c  mov     [rsp+70h+phkResult], rax; phkResult
0x180037a91  and     [rsp+70h+var_40], 0
0x180037a97  mov     eax, [rbp+arg_28]
0x180037a9a  mov     [rsp+70h+samDesired], eax; samDesired
0x180037a9e  mov     eax, [rbp+arg_20]
0x180037aa1  mov     [rsp+70h+dwOptions], eax; dwOptions
0x180037aa5  xor     r9d, r9d; lpClass
0x180037aa8  xor     r8d, r8d; Reserved
0x180037aab  mov     rdx, rbx; lpSubKey
0x180037aae  mov     rcx, rsi; hKey
0x180037ab1  call    cs:__imp_RegCreateKeyExW
0x180037ab7  lea     r11, [rsp+70h+var_s0]
0x180037abc  mov     rbx, [r11+20h]
0x180037ac0  mov     rsi, [r11+28h]
0x180037ac4  mov     rdi, [r11+30h]
0x180037ac8  mov     rsp, r11
0x180037acb  pop     r14
0x180037acd  pop     r12
0x180037acf  pop     rbp
0x180037ad0  retn
```
