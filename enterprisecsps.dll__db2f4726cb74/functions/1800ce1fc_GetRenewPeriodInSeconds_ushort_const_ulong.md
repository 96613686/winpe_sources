# GetRenewPeriodInSeconds(ushort const *,ulong *)

- ea: `0x1800ce1fc`
- end: `0x1800ce33b`
- name: `?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z`
- size: `319`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001b900`
- `0x1800223d0`

## callees

- `0x180015e90`
- `0x18002201c`
- `0x1800ce1fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ce284`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ce318`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ce284`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ce318`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ce254`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ce254`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800ce2a8`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800ce2a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetRenewPeriodInSeconds(const unsigned __int16 *a1, unsigned int *a2)
{
  unsigned int v4; // edi
  const WCHAR *v5; // rax
  LSTATUS v6; // eax
  signed int v7; // ebx
  HKEY v8; // rcx
  HKEY v9; // rcx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v12; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v13; // [rsp+78h] [rbp+38h] BYREF

  v13 = 0;
  v4 = 3628800;
  v12 = 3628800;
  hKey = 0;
  v5 = (const WCHAR *)DMGetKnownRegPath(1);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 < 0 )
  {
    v8 = hKey;
    hKey = 0;
    if ( v8 )
      RegCloseKey(v8);
    return (unsigned int)v7;
  }
  if ( (int)OmaDmRegistryGetDWORD(hKey, a1, L"RenewalPeriod", &v13) < 0 )
  {
    v7 = 0;
LABEL_13:
    *a2 = v4;
    goto LABEL_14;
  }
  v7 = ULongLongToULong(24LL * v13, &v12);
  if ( v7 >= 0 )
  {
    v7 = ULongLongToULong(60LL * v12, &v12);
    if ( v7 >= 0 )
    {
      v7 = ULongLongToULong(60LL * v12, &v12);
      if ( v7 >= 0 )
      {
        v4 = v12;
        goto LABEL_13;
      }
    }
  }
LABEL_14:
  v9 = hKey;
  hKey = 0;
  if ( v9 )
    RegCloseKey(v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800ce1fc  mov     [rsp-18h+arg_0], rbx
0x1800ce201  mov     [rsp-18h+arg_8], rsi
0x1800ce206  push    rbp
0x1800ce207  push    rdi
0x1800ce208  push    r14
0x1800ce20a  mov     rbp, rsp
0x1800ce20d  sub     rsp, 40h
0x1800ce211  mov     rsi, rdx
0x1800ce214  mov     r14, rcx
0x1800ce217  mov     [rbp+arg_18], 0
0x1800ce21e  mov     edi, 375F00h
0x1800ce223  mov     [rbp+arg_10], edi
0x1800ce226  mov     [rbp+hKey], 0
0x1800ce22e  mov     ecx, 1
0x1800ce233  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800ce238  lea     rcx, [rbp+hKey]
0x1800ce23c  mov     [rsp+40h+phkResult], rcx; phkResult
0x1800ce241  mov     r9d, 20019h; samDesired
0x1800ce247  xor     r8d, r8d; ulOptions
0x1800ce24a  mov     rdx, rax; lpSubKey
0x1800ce24d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ce254  call    cs:__imp_RegOpenKeyExW
0x1800ce25b  nop     dword ptr [rax+rax+00h]
0x1800ce260  mov     ebx, eax
0x1800ce262  test    eax, eax
0x1800ce264  jle     short loc_1800CE26F
0x1800ce266  movzx   ebx, ax
0x1800ce269  or      ebx, 80070000h
0x1800ce26f  test    ebx, ebx
0x1800ce271  jns     short loc_1800CE296
0x1800ce273  mov     rcx, [rbp+hKey]; hKey
0x1800ce277  mov     [rbp+hKey], 0
0x1800ce27f  test    rcx, rcx
0x1800ce282  jz      short loc_1800CE291
0x1800ce284  call    cs:__imp_RegCloseKey
0x1800ce28b  nop     dword ptr [rax+rax+00h]
0x1800ce290  nop
0x1800ce291  jmp     loc_1800CE325
0x1800ce296  lea     r9, [rbp+arg_18]
0x1800ce29a  lea     r8, aRenewalperiod; "RenewalPeriod"
0x1800ce2a1  mov     rdx, r14
0x1800ce2a4  mov     rcx, [rbp+hKey]
0x1800ce2a8  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800ce2af  nop     dword ptr [rax+rax+00h]
0x1800ce2b4  test    eax, eax
0x1800ce2b6  jns     short loc_1800CE2BC
0x1800ce2b8  xor     ebx, ebx
0x1800ce2ba  jmp     short loc_1800CE305
0x1800ce2bc  mov     eax, [rbp+arg_18]
0x1800ce2bf  lea     rcx, [rax+rax*2]
0x1800ce2c3  shl     rcx, 3; unsigned __int64
0x1800ce2c7  lea     rdx, [rbp+arg_10]; unsigned int *
0x1800ce2cb  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800ce2d0  mov     ebx, eax
0x1800ce2d2  test    eax, eax
0x1800ce2d4  js      short loc_1800CE307
0x1800ce2d6  mov     eax, [rbp+arg_10]
0x1800ce2d9  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x1800ce2dd  lea     rdx, [rbp+arg_10]; unsigned int *
0x1800ce2e1  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800ce2e6  mov     ebx, eax
0x1800ce2e8  test    eax, eax
0x1800ce2ea  js      short loc_1800CE307
0x1800ce2ec  mov     eax, [rbp+arg_10]
0x1800ce2ef  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x1800ce2f3  lea     rdx, [rbp+arg_10]; unsigned int *
0x1800ce2f7  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800ce2fc  mov     ebx, eax
0x1800ce2fe  test    eax, eax
0x1800ce300  js      short loc_1800CE307
0x1800ce302  mov     edi, [rbp+arg_10]
0x1800ce305  mov     [rsi], edi
0x1800ce307  mov     rcx, [rbp+hKey]; hKey
0x1800ce30b  mov     [rbp+hKey], 0
0x1800ce313  test    rcx, rcx
0x1800ce316  jz      short loc_1800CE325
0x1800ce318  call    cs:__imp_RegCloseKey
0x1800ce31f  nop     dword ptr [rax+rax+00h]
0x1800ce324  nop
0x1800ce325  mov     eax, ebx
0x1800ce327  mov     rbx, [rsp+40h+arg_0]
0x1800ce32c  mov     rsi, [rsp+40h+arg_8]
0x1800ce331  add     rsp, 40h
0x1800ce335  pop     r14
0x1800ce337  pop     rdi
0x1800ce338  pop     rbp
0x1800ce339  retn
```
