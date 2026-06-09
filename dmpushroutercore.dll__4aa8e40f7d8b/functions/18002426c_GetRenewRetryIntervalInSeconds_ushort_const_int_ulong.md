# GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)

- ea: `0x18002426c`
- end: `0x180024385`
- name: `?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z`
- size: `281`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ea90`

## callees

- `0x18002426c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002436a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002436a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800242dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800242dc`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800242a9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800242a9`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180024316`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180024316`

## pseudocode

```c
__int64 __fastcall GetRenewRetryIntervalInSeconds(const unsigned __int16 *a1, int a2, unsigned int *a3)
{
  unsigned __int64 v6; // rdi
  char IsStateSeparationEnabled; // al
  LSTATUS v8; // eax
  signed int v9; // ebx
  HKEY v10; // rcx
  const unsigned __int16 *v11; // r8
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  unsigned int v15; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  v15 = 0;
  hKey = 0;
  LODWORD(v6) = a2 != 0 ? 604800 : 1209600;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)off_18003CA70 + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         0,
         0x20019u,
         &hKey);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  v10 = hKey;
  if ( v9 >= 0 )
  {
    v11 = L"RetryInterval";
    if ( !a2 )
      v11 = L"RetryAfterExpiryInterval";
    if ( (int)OmaDmRegistryGetDWORD(hKey, a1, v11, &v15) >= 0
      && ((v12 = 24LL * v15, v12 > 0xFFFFFFFF)
       || (v13 = 60LL * (unsigned int)v12, v13 > 0xFFFFFFFF)
       || (v6 = 60LL * (unsigned int)v13, v6 > 0xFFFFFFFF)) )
    {
      v9 = -2147024362;
    }
    else
    {
      v9 = 0;
      *a3 = v6;
    }
    v10 = hKey;
  }
  hKey = 0;
  if ( v10 )
    RegCloseKey(v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002426c  mov     [rsp+arg_0], rbx
0x180024271  mov     [rsp+arg_10], rbp
0x180024276  push    rsi
0x180024277  push    rdi
0x180024278  push    r14
0x18002427a  sub     rsp, 30h
0x18002427e  mov     eax, edx
0x180024280  mov     [rsp+48h+arg_8], 0
0x180024288  neg     eax
0x18002428a  mov     [rsp+48h+hKey], 0
0x180024293  mov     rsi, r8
0x180024296  mov     ebp, edx
0x180024298  sbb     edi, edi
0x18002429a  mov     r14, rcx
0x18002429d  and     edi, 0FFF6C580h
0x1800242a3  add     edi, 127500h
0x1800242a9  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800242af  lea     rcx, off_18003CA70; "Software\\Microsoft\\Enrollments"
0x1800242b6  mov     r9d, 20019h; samDesired
0x1800242bc  neg     al
0x1800242be  lea     rax, [rsp+48h+hKey]
0x1800242c3  sbb     rdx, rdx
0x1800242c6  mov     [rsp+48h+phkResult], rax; phkResult
0x1800242cb  and     edx, 8
0x1800242ce  xor     r8d, r8d; ulOptions
0x1800242d1  mov     rdx, [rdx+rcx]; lpSubKey
0x1800242d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800242dc  call    cs:__imp_RegOpenKeyExW
0x1800242e2  mov     ebx, eax
0x1800242e4  test    eax, eax
0x1800242e6  jle     short loc_1800242F1
0x1800242e8  movzx   ebx, ax
0x1800242eb  or      ebx, 80070000h
0x1800242f1  mov     rcx, [rsp+48h+hKey]
0x1800242f6  test    ebx, ebx
0x1800242f8  js      short loc_18002435C
0x1800242fa  lea     rax, aRetryafterexpi; "RetryAfterExpiryInterval"
0x180024301  test    ebp, ebp
0x180024303  lea     r8, aRetryinterval; "RetryInterval"
0x18002430a  mov     rdx, r14
0x18002430d  cmovz   r8, rax
0x180024311  lea     r9, [rsp+48h+arg_8]
0x180024316  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002431c  test    eax, eax
0x18002431e  js      short loc_18002434C
0x180024320  mov     eax, [rsp+48h+arg_8]
0x180024324  mov     edx, 0FFFFFFFFh
0x180024329  lea     rcx, [rax+rax*2]
0x18002432d  shl     rcx, 3
0x180024331  cmp     rcx, rdx
0x180024334  ja      short loc_180024352
0x180024336  mov     eax, ecx
0x180024338  imul    rcx, rax, 3Ch ; '<'
0x18002433c  cmp     rcx, rdx
0x18002433f  ja      short loc_180024352
0x180024341  mov     eax, ecx
0x180024343  imul    rdi, rax, 3Ch ; '<'
0x180024347  cmp     rdi, rdx
0x18002434a  ja      short loc_180024352
0x18002434c  xor     ebx, ebx
0x18002434e  mov     [rsi], edi
0x180024350  jmp     short loc_180024357
0x180024352  mov     ebx, 80070216h
0x180024357  mov     rcx, [rsp+48h+hKey]; hKey
0x18002435c  mov     [rsp+48h+hKey], 0
0x180024365  test    rcx, rcx
0x180024368  jz      short loc_180024370
0x18002436a  call    cs:__imp_RegCloseKey
0x180024370  mov     rbp, [rsp+48h+arg_10]
0x180024375  mov     eax, ebx
0x180024377  mov     rbx, [rsp+48h+arg_0]
0x18002437c  add     rsp, 30h
0x180024380  pop     r14
0x180024382  pop     rdi
0x180024383  pop     rsi
0x180024384  retn
```
