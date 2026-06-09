# Intl_RegOpenCurrentUser(void)

- ea: `0x180026038`
- end: `0x1800260dc`
- name: `?Intl_RegOpenCurrentUser@@YAPEAUHKEY__@@XZ`
- size: `164`
- prototype: `HKEY(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017cf0`

## callees

- `0x180026038`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180026098`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180026098`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18002605a`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18002605a`

## pseudocode

```c
HKEY Intl_RegOpenCurrentUser(void)
{
  void *ppInterface; // [rsp+30h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp+10h] BYREF

  phkResult = HKEY_CURRENT_USER;
  ppInterface = 0;
  if ( CoGetCallContext(&GUID_0000013e_0000_0000_c000_000000000046, &ppInterface) >= 0 )
  {
    if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface)
      && (*(int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface) >= 0
      && RegOpenCurrentUser(0x20019u, &phkResult) )
    {
      phkResult = HKEY_CURRENT_USER;
    }
    if ( ppInterface )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 40LL))(ppInterface);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
    }
  }
  return phkResult;
}

```

## disassembly

```asm
0x180026038  sub     rsp, 28h
0x18002603c  lea     rdx, [rsp+28h+ppInterface]; ppInterface
0x180026041  mov     [rsp+28h+phkResult], 0FFFFFFFF80000001h
0x18002604a  lea     rcx, _GUID_0000013e_0000_0000_c000_000000000046; riid
0x180026051  mov     [rsp+28h+ppInterface], 0
0x18002605a  call    cs:__imp_CoGetCallContext
0x180026060  test    eax, eax
0x180026062  js      short loc_1800260D2
0x180026064  mov     rcx, [rsp+28h+ppInterface]
0x180026069  mov     rax, [rcx]
0x18002606c  mov     rax, [rax+30h]
0x180026070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026075  test    eax, eax
0x180026077  jnz     short loc_1800260AB
0x180026079  mov     rcx, [rsp+28h+ppInterface]
0x18002607e  mov     rax, [rcx]
0x180026081  mov     rax, [rax+20h]
0x180026085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002608a  test    eax, eax
0x18002608c  js      short loc_1800260AB
0x18002608e  lea     rdx, [rsp+28h+phkResult]; phkResult
0x180026093  mov     ecx, 20019h; samDesired
0x180026098  call    cs:__imp_RegOpenCurrentUser
0x18002609e  test    eax, eax
0x1800260a0  jz      short loc_1800260AB
0x1800260a2  mov     [rsp+28h+phkResult], 0FFFFFFFF80000001h
0x1800260ab  mov     rcx, [rsp+28h+ppInterface]
0x1800260b0  test    rcx, rcx
0x1800260b3  jz      short loc_1800260D2
0x1800260b5  mov     rax, [rcx]
0x1800260b8  mov     rax, [rax+28h]
0x1800260bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260c1  mov     rcx, [rsp+28h+ppInterface]
0x1800260c6  mov     rax, [rcx]
0x1800260c9  mov     rax, [rax+10h]
0x1800260cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260d2  mov     rax, [rsp+28h+phkResult]
0x1800260d7  add     rsp, 28h
0x1800260db  retn
```
