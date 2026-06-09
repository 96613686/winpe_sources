# CommonInit(AutoCoInitialize &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x18000632c`
- end: `0x1800063c4`
- name: `?CommonInit@@YAJAEAVAutoCoInitialize@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `152`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800058e0`
- `0x180005c00`
- `0x180005d20`

## callees

- `0x180005f08`
- `0x18000632c`

## import_xrefs

- `DMCmnUtils!DmIsSystemOrAdmin` at `0x180006373`
- `DMCmnUtils!DmIsSystemOrAdmin` at `0x180006373`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000639a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000639a`
- `ext-ms-win-shell-embeddedmode-l1-1-0!IsEmbeddedModeAllowed` at `0x180006350`
- `ext-ms-win-shell-embeddedmode-l1-1-0!IsEmbeddedModeAllowed` at `0x180006350`

## pseudocode

```c
HRESULT __fastcall CommonInit(_DWORD *a1, char *a2)
{
  HRESULT result; // eax
  int v5; // [rsp+40h] [rbp+18h] BYREF
  int v6; // [rsp+48h] [rbp+20h] BYREF

  v5 = 0;
  v6 = 0;
  result = IsEmbeddedModeAllowed(&v5);
  if ( result >= 0 )
  {
    if ( !v5 )
      return -2147024846;
    result = DmIsSystemOrAdmin(&v6);
    if ( result >= 0 )
    {
      if ( !v6 )
        return -2147024891;
      if ( !*a1 )
      {
        result = CoInitializeEx(0, 0);
        if ( result < 0 )
          return result;
        *a1 = 1;
      }
      return AcquireEnrollmentAccessMutex(a2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000632c  mov     rax, rsp
0x18000632f  mov     [rax+8], rbx
0x180006333  push    rdi
0x180006334  sub     rsp, 20h
0x180006338  mov     rbx, rcx
0x18000633b  mov     dword ptr [rax+18h], 0
0x180006342  lea     rcx, [rax+18h]
0x180006346  mov     dword ptr [rax+20h], 0
0x18000634d  mov     rdi, rdx
0x180006350  call    cs:__imp_IsEmbeddedModeAllowed
0x180006357  nop     dword ptr [rax+rax+00h]
0x18000635c  test    eax, eax
0x18000635e  js      short loc_1800063B8
0x180006360  cmp     [rsp+28h+arg_10], 0
0x180006365  jnz     short loc_18000636E
0x180006367  mov     eax, 80070032h
0x18000636c  jmp     short loc_1800063B8
0x18000636e  lea     rcx, [rsp+28h+arg_18]
0x180006373  call    cs:__imp_?DmIsSystemOrAdmin@@YAJPEAH@Z; DmIsSystemOrAdmin(int *)
0x18000637a  nop     dword ptr [rax+rax+00h]
0x18000637f  test    eax, eax
0x180006381  js      short loc_1800063B8
0x180006383  cmp     [rsp+28h+arg_18], 0
0x180006388  jnz     short loc_180006391
0x18000638a  mov     eax, 80070005h
0x18000638f  jmp     short loc_1800063B8
0x180006391  cmp     dword ptr [rbx], 0
0x180006394  jnz     short loc_1800063B0
0x180006396  xor     edx, edx; dwCoInit
0x180006398  xor     ecx, ecx; pvReserved
0x18000639a  call    cs:__imp_CoInitializeEx
0x1800063a1  nop     dword ptr [rax+rax+00h]
0x1800063a6  test    eax, eax
0x1800063a8  js      short loc_1800063B8
0x1800063aa  mov     dword ptr [rbx], 1
0x1800063b0  mov     rcx, rdi
0x1800063b3  call    ?AcquireEnrollmentAccessMutex@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; AcquireEnrollmentAccessMutex(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x1800063b8  mov     rbx, [rsp+28h+arg_0]
0x1800063bd  add     rsp, 20h
0x1800063c1  pop     rdi
0x1800063c2  retn
```
