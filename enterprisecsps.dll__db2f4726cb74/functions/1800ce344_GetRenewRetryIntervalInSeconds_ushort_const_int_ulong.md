# GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)

- ea: `0x1800ce344`
- end: `0x1800ce49d`
- name: `?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z`
- size: `345`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001b900`
- `0x1800223d0`

## callees

- `0x180015e90`
- `0x18002201c`
- `0x1800ce344`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ce3da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ce47c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ce3da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ce47c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ce3aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ce3aa`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800ce40c`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800ce40c`

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
0x1800ce344  mov     [rsp-28h+arg_0], rbx
0x1800ce349  push    rbp
0x1800ce34a  push    rsi
0x1800ce34b  push    rdi
0x1800ce34c  push    r14
0x1800ce34e  push    r15
0x1800ce350  mov     rbp, rsp
0x1800ce353  sub     rsp, 40h
0x1800ce357  mov     rsi, r8
0x1800ce35a  mov     r14d, edx
0x1800ce35d  mov     r15, rcx
0x1800ce360  mov     [rbp+arg_18], 0
0x1800ce367  mov     eax, edx
0x1800ce369  neg     eax
0x1800ce36b  sbb     edi, edi
0x1800ce36d  and     edi, 0FFF6C580h
0x1800ce373  add     edi, 127500h
0x1800ce379  mov     [rbp+arg_8], edi
0x1800ce37c  mov     [rbp+hKey], 0
0x1800ce384  mov     ecx, 1
0x1800ce389  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800ce38e  lea     rcx, [rbp+hKey]
0x1800ce392  mov     [rsp+40h+phkResult], rcx; phkResult
0x1800ce397  mov     r9d, 20019h; samDesired
0x1800ce39d  xor     r8d, r8d; ulOptions
0x1800ce3a0  mov     rdx, rax; lpSubKey
0x1800ce3a3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ce3aa  call    cs:__imp_RegOpenKeyExW
0x1800ce3b1  nop     dword ptr [rax+rax+00h]
0x1800ce3b6  mov     ebx, eax
0x1800ce3b8  test    eax, eax
0x1800ce3ba  jle     short loc_1800CE3C5
0x1800ce3bc  movzx   ebx, ax
0x1800ce3bf  or      ebx, 80070000h
0x1800ce3c5  test    ebx, ebx
0x1800ce3c7  jns     short loc_1800CE3EC
0x1800ce3c9  mov     rcx, [rbp+hKey]; hKey
0x1800ce3cd  mov     [rbp+hKey], 0
0x1800ce3d5  test    rcx, rcx
0x1800ce3d8  jz      short loc_1800CE3E7
0x1800ce3da  call    cs:__imp_RegCloseKey
0x1800ce3e1  nop     dword ptr [rax+rax+00h]
0x1800ce3e6  nop
0x1800ce3e7  jmp     loc_1800CE489
0x1800ce3ec  lea     rax, aRetryafterexpi; "RetryAfterExpiryInterval"
0x1800ce3f3  lea     r8, aRetryinterval; "RetryInterval"
0x1800ce3fa  test    r14d, r14d
0x1800ce3fd  cmovz   r8, rax
0x1800ce401  lea     r9, [rbp+arg_18]
0x1800ce405  mov     rdx, r15
0x1800ce408  mov     rcx, [rbp+hKey]
0x1800ce40c  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800ce413  nop     dword ptr [rax+rax+00h]
0x1800ce418  test    eax, eax
0x1800ce41a  jns     short loc_1800CE420
0x1800ce41c  xor     ebx, ebx
0x1800ce41e  jmp     short loc_1800CE469
0x1800ce420  mov     eax, [rbp+arg_18]
0x1800ce423  lea     rcx, [rax+rax*2]
0x1800ce427  shl     rcx, 3; unsigned __int64
0x1800ce42b  lea     rdx, [rbp+arg_8]; unsigned int *
0x1800ce42f  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800ce434  mov     ebx, eax
0x1800ce436  test    eax, eax
0x1800ce438  js      short loc_1800CE46B
0x1800ce43a  mov     eax, [rbp+arg_8]
0x1800ce43d  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x1800ce441  lea     rdx, [rbp+arg_8]; unsigned int *
0x1800ce445  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800ce44a  mov     ebx, eax
0x1800ce44c  test    eax, eax
0x1800ce44e  js      short loc_1800CE46B
0x1800ce450  mov     eax, [rbp+arg_8]
0x1800ce453  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x1800ce457  lea     rdx, [rbp+arg_8]; unsigned int *
0x1800ce45b  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800ce460  mov     ebx, eax
0x1800ce462  test    eax, eax
0x1800ce464  js      short loc_1800CE46B
0x1800ce466  mov     edi, [rbp+arg_8]
0x1800ce469  mov     [rsi], edi
0x1800ce46b  mov     rcx, [rbp+hKey]; hKey
0x1800ce46f  mov     [rbp+hKey], 0
0x1800ce477  test    rcx, rcx
0x1800ce47a  jz      short loc_1800CE489
0x1800ce47c  call    cs:__imp_RegCloseKey
0x1800ce483  nop     dword ptr [rax+rax+00h]
0x1800ce488  nop
0x1800ce489  mov     eax, ebx
0x1800ce48b  mov     rbx, [rsp+40h+arg_0]
0x1800ce490  add     rsp, 40h
0x1800ce494  pop     r15
0x1800ce496  pop     r14
0x1800ce498  pop     rdi
0x1800ce499  pop     rsi
0x1800ce49a  pop     rbp
0x1800ce49b  retn
```
