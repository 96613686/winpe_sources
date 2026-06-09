# NgcStatusStorage::Load(void)

- ea: `0x180008f74`
- end: `0x18000903b`
- name: `?Load@NgcStatusStorage@@QEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(NgcStatusStorage *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180025788`

## callees

- `0x180008f74`
- `0x180009050`
- `0x180026f88`
- `0x180027448`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180008f94`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180008f94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009028`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009028`

## string_xrefs

- `0x180008fa9`: `RegOpenCurrentUser`
- `0x180008fbb`: `RegOpenCurrentUserKey`
- `0x180008fc5`: `%s: RegOpenCurrentUser failed with win32 error code: 0x%08x. samDesired = %lu.`
- `0x180008fe5`: `OpenRootKey`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::Load(NgcStatusStorage *this)
{
  LSTATUS v2; // eax
  const unsigned __int16 *v3; // r8
  signed int v4; // ebx
  bool v5; // sf
  __int64 v6; // r9
  const wchar_t *v7; // r8
  int v8; // eax
  HKEY phkResult; // [rsp+38h] [rbp+10h] BYREF

  phkResult = 0;
  v2 = RegOpenCurrentUser(0x20019u, &phkResult);
  v4 = v2;
  if ( v2 )
  {
    Logger::WriteRegistryFailureEvent(v2, L"RegOpenCurrentUser", L"HKEY_CURRENT_USER");
    Logger::TraceError(
      L"%s: RegOpenCurrentUser failed with win32 error code: 0x%08x. samDesired = %lu.",
      L"RegOpenCurrentUserKey",
      (unsigned int)v4,
      131097);
    v5 = v4 < 0;
    if ( v4 <= 0 )
      goto LABEL_5;
    v4 = (unsigned __int16)v4 | 0x80070000;
  }
  v5 = v4 < 0;
LABEL_5:
  if ( v5 )
  {
    v6 = (unsigned int)v4;
    v7 = L"OpenRootKey";
  }
  else
  {
    v8 = NgcStatusStorage::Load(this, phkResult, v3);
    v4 = v8;
    if ( v8 >= 0 )
      goto LABEL_10;
    v6 = (unsigned int)v8;
    v7 = L"NgcStatusStorage::Load";
  }
  Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"NgcStatusStorage::Load", v7, v6);
LABEL_10:
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180008f74  mov     [rsp+arg_0], rbx
0x180008f79  push    rdi
0x180008f7a  sub     rsp, 20h
0x180008f7e  mov     rdi, rcx
0x180008f81  mov     [rsp+28h+phkResult], 0
0x180008f8a  mov     ecx, 20019h; samDesired
0x180008f8f  lea     rdx, [rsp+28h+phkResult]; phkResult
0x180008f94  call    cs:__imp_RegOpenCurrentUser
0x180008f9a  mov     ebx, eax
0x180008f9c  test    eax, eax
0x180008f9e  jz      short loc_180008FDE
0x180008fa0  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180008fa7  mov     ecx, eax; unsigned int
0x180008fa9  lea     rdx, aRegopencurrent; "RegOpenCurrentUser"
0x180008fb0  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x180008fb5  mov     r9d, 20019h
0x180008fbb  lea     rdx, aRegopencurrent_0; "RegOpenCurrentUserKey"
0x180008fc2  mov     r8d, ebx
0x180008fc5  lea     rcx, aSRegopencurren; "%s: RegOpenCurrentUser failed with win3"...
0x180008fcc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008fd1  test    ebx, ebx
0x180008fd3  jle     short loc_180008FE0
0x180008fd5  movzx   ebx, bx
0x180008fd8  or      ebx, 80070000h
0x180008fde  test    ebx, ebx
0x180008fe0  jns     short loc_180008FEE
0x180008fe2  mov     r9d, ebx
0x180008fe5  lea     r8, aOpenrootkey; "OpenRootKey"
0x180008fec  jmp     short loc_18000900B
0x180008fee  mov     rdx, [rsp+28h+phkResult]; hKey
0x180008ff3  mov     rcx, rdi; this
0x180008ff6  call    ?Load@NgcStatusStorage@@QEAAJPEAUHKEY__@@PEBG@Z; NgcStatusStorage::Load(HKEY__ *,ushort const *)
0x180008ffb  mov     ebx, eax
0x180008ffd  test    eax, eax
0x180008fff  jns     short loc_18000901E
0x180009001  mov     r9d, eax
0x180009004  lea     r8, aNgcstatusstora; "NgcStatusStorage::Load"
0x18000900b  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180009012  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180009019  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000901e  mov     rcx, [rsp+28h+phkResult]; hKey
0x180009023  test    rcx, rcx
0x180009026  jz      short loc_18000902E
0x180009028  call    cs:__imp_RegCloseKey
0x18000902e  mov     eax, ebx
0x180009030  mov     rbx, [rsp+28h+arg_0]
0x180009035  add     rsp, 20h
0x180009039  pop     rdi
0x18000903a  retn
```
