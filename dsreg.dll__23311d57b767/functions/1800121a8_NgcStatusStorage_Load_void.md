# NgcStatusStorage::Load(void)

- ea: `0x1800121a8`
- end: `0x180012278`
- name: `?Load@NgcStatusStorage@@QEAAJXZ`
- size: `208`
- prototype: `__int64 __fastcall(NgcStatusStorage *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800108e0`
- `0x18007dc54`
- `0x18007e78c`

## callees

- `0x1800084f4`
- `0x1800121a8`
- `0x180012280`
- `0x180043e54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800121c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800121c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001222f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001222f`

## string_xrefs

- `0x1800121e1`: `RegOpenCurrentUser`
- `0x1800121f3`: `RegOpenCurrentUserKey`
- `0x1800121fd`: `%s: RegOpenCurrentUser failed with win32 error code: 0x%08x. samDesired = %lu.`
- `0x180012250`: `OpenRootKey`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::Load(NgcStatusStorage *this)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  bool v4; // sf
  int v5; // eax
  __int64 v7; // r9
  const wchar_t *v8; // r8
  HKEY phkResult; // [rsp+38h] [rbp+10h] BYREF

  phkResult = 0;
  v2 = RegOpenCurrentUser(0x20019u, &phkResult);
  v3 = v2;
  if ( !v2 )
    goto LABEL_2;
  Logger::WriteRegistryFailureEvent(v2, L"RegOpenCurrentUser", L"HKEY_CURRENT_USER");
  Logger::TraceError(
    L"%s: RegOpenCurrentUser failed with win32 error code: 0x%08x. samDesired = %lu.",
    L"RegOpenCurrentUserKey",
    (unsigned int)v3,
    131097);
  v4 = v3 < 0;
  if ( v3 > 0 )
  {
    v3 = (unsigned __int16)v3 | 0x80070000;
LABEL_2:
    v4 = v3 < 0;
  }
  if ( v4 )
  {
    v7 = (unsigned int)v3;
    v8 = L"OpenRootKey";
  }
  else
  {
    v5 = NgcStatusStorage::Load(this, phkResult, 0);
    v3 = v5;
    if ( v5 >= 0 )
      goto LABEL_6;
    v7 = (unsigned int)v5;
    v8 = L"NgcStatusStorage::Load";
  }
  Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"NgcStatusStorage::Load", v8, v7);
LABEL_6:
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800121a8  mov     [rsp+arg_0], rbx
0x1800121ad  push    rdi
0x1800121ae  sub     rsp, 20h
0x1800121b2  mov     rdi, rcx
0x1800121b5  mov     [rsp+28h+phkResult], 0
0x1800121be  mov     ecx, 20019h; samDesired
0x1800121c3  lea     rdx, [rsp+28h+phkResult]; phkResult
0x1800121c8  call    cs:__imp_RegOpenCurrentUser
0x1800121ce  mov     ebx, eax
0x1800121d0  test    eax, eax
0x1800121d2  jnz     short loc_1800121D8
0x1800121d4  test    ebx, ebx
0x1800121d6  jmp     short loc_18001220D
0x1800121d8  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x1800121df  mov     ecx, ebx; unsigned int
0x1800121e1  lea     rdx, aRegopencurrent; "RegOpenCurrentUser"
0x1800121e8  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x1800121ed  mov     r9d, 20019h
0x1800121f3  lea     rdx, aRegopencurrent_0; "RegOpenCurrentUserKey"
0x1800121fa  mov     r8d, ebx
0x1800121fd  lea     rcx, aSRegopencurren; "%s: RegOpenCurrentUser failed with win3"...
0x180012204  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180012209  test    ebx, ebx
0x18001220b  jg      short loc_180012242
0x18001220d  js      short loc_18001224D
0x18001220f  mov     rdx, [rsp+28h+phkResult]; hKey
0x180012214  xor     r8d, r8d; unsigned __int16 *
0x180012217  mov     rcx, rdi; this
0x18001221a  call    ?Load@NgcStatusStorage@@QEAAJPEAUHKEY__@@PEBG@Z; NgcStatusStorage::Load(HKEY__ *,ushort const *)
0x18001221f  mov     ebx, eax
0x180012221  test    eax, eax
0x180012223  js      short loc_180012259
0x180012225  mov     rcx, [rsp+28h+phkResult]; hKey
0x18001222a  test    rcx, rcx
0x18001222d  jz      short loc_180012235
0x18001222f  call    cs:__imp_RegCloseKey
0x180012235  mov     eax, ebx
0x180012237  mov     rbx, [rsp+28h+arg_0]
0x18001223c  add     rsp, 20h
0x180012240  pop     rdi
0x180012241  retn
0x180012242  movzx   ebx, bx
0x180012245  or      ebx, 80070000h
0x18001224b  jmp     short loc_1800121D4
0x18001224d  mov     r9d, ebx
0x180012250  lea     r8, aOpenrootkey; "OpenRootKey"
0x180012257  jmp     short loc_180012263
0x180012259  mov     r9d, eax
0x18001225c  lea     r8, aNgcstatusstora_0; "NgcStatusStorage::Load"
0x180012263  lea     rdx, aNgcstatusstora_0; "NgcStatusStorage::Load"
0x18001226a  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180012271  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180012276  jmp     short loc_180012225
```
