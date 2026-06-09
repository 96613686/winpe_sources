# GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)

- ea: `0x18001d85c`
- end: `0x18001d975`
- name: `?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z`
- size: `281`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18000be00`

## callees

- `0x18001d85c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d95a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d95a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d8cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d8cc`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001d899`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001d899`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18001d906`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18001d906`

## pseudocode

```c
__int64 __fastcall GetRenewRetryIntervalInSeconds(const unsigned __int16 *a1, __int64 a2, unsigned int *a3)
{
  int v4; // ebp
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
  v4 = a2;
  LODWORD(v6) = (_DWORD)a2 != 0 ? 604800 : 1209600;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1, a2);
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)off_180021160 + (IsStateSeparationEnabled != 0 ? 8 : 0)),
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
    if ( !v4 )
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
0x18001d85c  mov     [rsp+arg_0], rbx
0x18001d861  mov     [rsp+arg_10], rbp
0x18001d866  push    rsi
0x18001d867  push    rdi
0x18001d868  push    r14
0x18001d86a  sub     rsp, 30h
0x18001d86e  mov     eax, edx
0x18001d870  mov     [rsp+48h+arg_8], 0
0x18001d878  neg     eax
0x18001d87a  mov     [rsp+48h+hKey], 0
0x18001d883  mov     rsi, r8
0x18001d886  mov     ebp, edx
0x18001d888  sbb     edi, edi
0x18001d88a  mov     r14, rcx
0x18001d88d  and     edi, 0FFF6C580h
0x18001d893  add     edi, 127500h
0x18001d899  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001d89f  lea     rcx, off_180021160; "Software\\Microsoft\\Enrollments"
0x18001d8a6  mov     r9d, 20019h; samDesired
0x18001d8ac  neg     al
0x18001d8ae  lea     rax, [rsp+48h+hKey]
0x18001d8b3  sbb     rdx, rdx
0x18001d8b6  mov     [rsp+48h+phkResult], rax; phkResult
0x18001d8bb  and     edx, 8
0x18001d8be  xor     r8d, r8d; ulOptions
0x18001d8c1  mov     rdx, [rdx+rcx]; lpSubKey
0x18001d8c5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d8cc  call    cs:__imp_RegOpenKeyExW
0x18001d8d2  mov     ebx, eax
0x18001d8d4  test    eax, eax
0x18001d8d6  jle     short loc_18001D8E1
0x18001d8d8  movzx   ebx, ax
0x18001d8db  or      ebx, 80070000h
0x18001d8e1  mov     rcx, [rsp+48h+hKey]
0x18001d8e6  test    ebx, ebx
0x18001d8e8  js      short loc_18001D94C
0x18001d8ea  lea     rax, aRetryafterexpi; "RetryAfterExpiryInterval"
0x18001d8f1  test    ebp, ebp
0x18001d8f3  lea     r8, aRetryinterval; "RetryInterval"
0x18001d8fa  mov     rdx, r14
0x18001d8fd  cmovz   r8, rax
0x18001d901  lea     r9, [rsp+48h+arg_8]
0x18001d906  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001d90c  test    eax, eax
0x18001d90e  js      short loc_18001D93C
0x18001d910  mov     eax, [rsp+48h+arg_8]
0x18001d914  mov     edx, 0FFFFFFFFh
0x18001d919  lea     rcx, [rax+rax*2]
0x18001d91d  shl     rcx, 3
0x18001d921  cmp     rcx, rdx
0x18001d924  ja      short loc_18001D942
0x18001d926  mov     eax, ecx
0x18001d928  imul    rcx, rax, 3Ch ; '<'
0x18001d92c  cmp     rcx, rdx
0x18001d92f  ja      short loc_18001D942
0x18001d931  mov     eax, ecx
0x18001d933  imul    rdi, rax, 3Ch ; '<'
0x18001d937  cmp     rdi, rdx
0x18001d93a  ja      short loc_18001D942
0x18001d93c  xor     ebx, ebx
0x18001d93e  mov     [rsi], edi
0x18001d940  jmp     short loc_18001D947
0x18001d942  mov     ebx, 80070216h
0x18001d947  mov     rcx, [rsp+48h+hKey]; hKey
0x18001d94c  mov     [rsp+48h+hKey], 0
0x18001d955  test    rcx, rcx
0x18001d958  jz      short loc_18001D960
0x18001d95a  call    cs:__imp_RegCloseKey
0x18001d960  mov     rbp, [rsp+48h+arg_10]
0x18001d965  mov     eax, ebx
0x18001d967  mov     rbx, [rsp+48h+arg_0]
0x18001d96c  add     rsp, 30h
0x18001d970  pop     r14
0x18001d972  pop     rdi
0x18001d973  pop     rsi
0x18001d974  retn
```
