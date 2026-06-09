# OmaDmCloseSession_Impl(ushort const *)

- ea: `0x18000ef50`
- end: `0x18000efda`
- name: `?OmaDmCloseSession_Impl@@YAJPEBG@Z`
- size: `138`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180015bb0`

## callees

- `0x1800075f0`
- `0x180007930`
- `0x18000c974`
- `0x18000ef50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000efa3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000efa3`

## pseudocode

```c
__int64 __fastcall OmaDmCloseSession_Impl(LPCWSTR lpSubKey)
{
  int AccountRootKeyByInitiationId; // ebx
  LSTATUS v3; // eax
  HKEY hKey; // [rsp+30h] [rbp+8h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp+10h] BYREF

  hObject = 0;
  hKey = 0;
  if ( lpSubKey )
  {
    AccountRootKeyByInitiationId = AcquireOmaDmMutex(&hObject);
    if ( AccountRootKeyByInitiationId >= 0 )
    {
      AccountRootKeyByInitiationId = GetAccountRootKeyByInitiationId((__int64)lpSubKey, (__int64)&hKey);
      if ( AccountRootKeyByInitiationId >= 0 )
      {
        v3 = RegDeleteTreeW(hKey, lpSubKey);
        if ( v3 )
        {
          if ( v3 > 0 )
            AccountRootKeyByInitiationId = (unsigned __int16)v3 | 0x80070000;
          else
            AccountRootKeyByInitiationId = v3;
        }
      }
    }
  }
  else
  {
    AccountRootKeyByInitiationId = 0;
  }
  ReleaseOmaDmMutex(hObject);
  return (unsigned int)AccountRootKeyByInitiationId;
}

```

## disassembly

```asm
0x18000ef50  mov     [rsp+arg_10], rbx
0x18000ef55  push    rdi
0x18000ef56  sub     rsp, 20h
0x18000ef5a  mov     [rsp+28h+hObject], 0
0x18000ef63  mov     rdi, rcx
0x18000ef66  mov     [rsp+28h+hKey], 0
0x18000ef6f  test    rcx, rcx
0x18000ef72  jnz     short loc_18000EF78
0x18000ef74  xor     ebx, ebx
0x18000ef76  jmp     short loc_18000EFC2
0x18000ef78  lea     rcx, [rsp+28h+hObject]; void **
0x18000ef7d  call    ?AcquireOmaDmMutex@@YAJPEAPEAX@Z; AcquireOmaDmMutex(void * *)
0x18000ef82  mov     ebx, eax
0x18000ef84  test    eax, eax
0x18000ef86  js      short loc_18000EFC2
0x18000ef88  lea     rdx, [rsp+28h+hKey]
0x18000ef8d  mov     rcx, rdi
0x18000ef90  call    GetAccountRootKeyByInitiationId
0x18000ef95  mov     ebx, eax
0x18000ef97  test    eax, eax
0x18000ef99  js      short loc_18000EFC2
0x18000ef9b  mov     rcx, [rsp+28h+hKey]; hKey
0x18000efa0  mov     rdx, rdi; lpSubKey
0x18000efa3  call    cs:__imp_RegDeleteTreeW
0x18000efaa  nop     dword ptr [rax+rax+00h]
0x18000efaf  test    eax, eax
0x18000efb1  jz      short loc_18000EFC2
0x18000efb3  jg      short loc_18000EFB9
0x18000efb5  mov     ebx, eax
0x18000efb7  jmp     short loc_18000EFC2
0x18000efb9  movzx   ebx, ax
0x18000efbc  or      ebx, 80070000h
0x18000efc2  mov     rcx, [rsp+28h+hObject]; hObject
0x18000efc7  call    ?ReleaseOmaDmMutex@@YAXPEAX@Z; ReleaseOmaDmMutex(void *)
0x18000efcc  mov     eax, ebx
0x18000efce  mov     rbx, [rsp+28h+arg_10]
0x18000efd3  add     rsp, 20h
0x18000efd7  pop     rdi
0x18000efd8  retn
```
