# GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)

- ea: `0x18002d850`
- end: `0x18002d990`
- name: `?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z`
- size: `320`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180050558`

## callees

- `0x18000dd20`
- `0x18002d850`
- `0x18002d998`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d8b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d8b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d8e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d976`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d8e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d976`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18002d90c`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18002d90c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetRenewRetryIntervalInSeconds(const unsigned __int16 *a1, int a2, unsigned int *a3)
{
  int v6; // edi
  const WCHAR *v7; // rax
  LSTATUS v8; // eax
  signed int v9; // ebx
  HKEY v10; // rcx
  const unsigned __int16 *v11; // r8
  HKEY v12; // rcx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v15; // [rsp+78h] [rbp+38h] BYREF
  unsigned int v16; // [rsp+88h] [rbp+48h] BYREF

  v16 = 0;
  v6 = a2 != 0 ? 604800 : 1209600;
  v15 = v6;
  hKey = 0;
  v7 = (const WCHAR *)DMGetKnownRegPath(1);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, &hKey);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 < 0 )
  {
    v10 = hKey;
    hKey = 0;
    if ( v10 )
      RegCloseKey(v10);
    return (unsigned int)v9;
  }
  v11 = L"RetryInterval";
  if ( !a2 )
    v11 = L"RetryAfterExpiryInterval";
  if ( (int)OmaDmRegistryGetDWORD(hKey, a1, v11, &v16) < 0 )
  {
    v9 = 0;
LABEL_15:
    *a3 = v6;
    goto LABEL_16;
  }
  v9 = ULongLongToULong(24LL * v16, &v15);
  if ( v9 >= 0 )
  {
    v9 = ULongLongToULong(60LL * v15, &v15);
    if ( v9 >= 0 )
    {
      v9 = ULongLongToULong(60LL * v15, &v15);
      if ( v9 >= 0 )
      {
        v6 = v15;
        goto LABEL_15;
      }
    }
  }
LABEL_16:
  v12 = hKey;
  hKey = 0;
  if ( v12 )
    RegCloseKey(v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002d850  mov     [rsp-28h+arg_0], rbx
0x18002d855  push    rbp
0x18002d856  push    rsi
0x18002d857  push    rdi
0x18002d858  push    r14
0x18002d85a  push    r15
0x18002d85c  mov     rbp, rsp
0x18002d85f  sub     rsp, 40h
0x18002d863  mov     rsi, r8
0x18002d866  mov     r14d, edx
0x18002d869  mov     r15, rcx
0x18002d86c  mov     [rbp+arg_18], 0
0x18002d873  mov     eax, edx
0x18002d875  neg     eax
0x18002d877  sbb     edi, edi
0x18002d879  and     edi, 0FFF6C580h
0x18002d87f  add     edi, 127500h
0x18002d885  mov     [rbp+arg_8], edi
0x18002d888  mov     [rbp+hKey], 0
0x18002d890  mov     ecx, 1
0x18002d895  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18002d89a  lea     rcx, [rbp+hKey]
0x18002d89e  mov     [rsp+40h+phkResult], rcx; phkResult
0x18002d8a3  mov     r9d, 20019h; samDesired
0x18002d8a9  xor     r8d, r8d; ulOptions
0x18002d8ac  mov     rdx, rax; lpSubKey
0x18002d8af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d8b6  call    cs:__imp_RegOpenKeyExW
0x18002d8bc  mov     ebx, eax
0x18002d8be  test    eax, eax
0x18002d8c0  jle     short loc_18002D8CB
0x18002d8c2  movzx   ebx, ax
0x18002d8c5  or      ebx, 80070000h
0x18002d8cb  test    ebx, ebx
0x18002d8cd  jns     short loc_18002D8EC
0x18002d8cf  mov     rcx, [rbp+hKey]; hKey
0x18002d8d3  mov     [rbp+hKey], 0
0x18002d8db  test    rcx, rcx
0x18002d8de  jz      short loc_18002D8E7
0x18002d8e0  call    cs:__imp_RegCloseKey
0x18002d8e6  nop
0x18002d8e7  jmp     loc_18002D97D
0x18002d8ec  lea     rax, aRetryafterexpi; "RetryAfterExpiryInterval"
0x18002d8f3  lea     r8, aRetryinterval; "RetryInterval"
0x18002d8fa  test    r14d, r14d
0x18002d8fd  cmovz   r8, rax
0x18002d901  lea     r9, [rbp+arg_18]
0x18002d905  mov     rdx, r15
0x18002d908  mov     rcx, [rbp+hKey]
0x18002d90c  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002d912  test    eax, eax
0x18002d914  jns     short loc_18002D91A
0x18002d916  xor     ebx, ebx
0x18002d918  jmp     short loc_18002D963
0x18002d91a  mov     eax, [rbp+arg_18]
0x18002d91d  lea     rcx, [rax+rax*2]
0x18002d921  shl     rcx, 3; unsigned __int64
0x18002d925  lea     rdx, [rbp+arg_8]; unsigned int *
0x18002d929  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002d92e  mov     ebx, eax
0x18002d930  test    eax, eax
0x18002d932  js      short loc_18002D965
0x18002d934  mov     eax, [rbp+arg_8]
0x18002d937  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x18002d93b  lea     rdx, [rbp+arg_8]; unsigned int *
0x18002d93f  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002d944  mov     ebx, eax
0x18002d946  test    eax, eax
0x18002d948  js      short loc_18002D965
0x18002d94a  mov     eax, [rbp+arg_8]
0x18002d94d  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x18002d951  lea     rdx, [rbp+arg_8]; unsigned int *
0x18002d955  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002d95a  mov     ebx, eax
0x18002d95c  test    eax, eax
0x18002d95e  js      short loc_18002D965
0x18002d960  mov     edi, [rbp+arg_8]
0x18002d963  mov     [rsi], edi
0x18002d965  mov     rcx, [rbp+hKey]; hKey
0x18002d969  mov     [rbp+hKey], 0
0x18002d971  test    rcx, rcx
0x18002d974  jz      short loc_18002D97D
0x18002d976  call    cs:__imp_RegCloseKey
0x18002d97c  nop
0x18002d97d  mov     eax, ebx
0x18002d97f  mov     rbx, [rsp+40h+arg_0]
0x18002d984  add     rsp, 40h
0x18002d988  pop     r15
0x18002d98a  pop     r14
0x18002d98c  pop     rdi
0x18002d98d  pop     rsi
0x18002d98e  pop     rbp
0x18002d98f  retn
```
