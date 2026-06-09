# LsapInitializeGlobals

- ea: `0x140002b9c`
- end: `0x140002c1e`
- name: `LsapInitializeGlobals`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1400031bc`

## callees

- `0x140002b9c`
- `0x140003c04`
- `0x140003ce8`
- `0x140003e9c`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x140002bb9`
- `ntdll!RtlInitializeResource` at `0x140002bb9`

## pseudocode

```c
__int64 LsapInitializeGlobals()
{
  __int64 result; // rax

  result = LsapBuildWellKnownSids();
  if ( (int)result >= 0 )
  {
    result = LsapBuildSD();
    if ( (int)result >= 0 )
    {
      RtlInitializeResource(&gLsaIfLock);
      qword_14000C278 = (__int64)&gLsapIfList;
      gLsapIfList = (__int64)&gLsapIfList;
      qword_14000C2E8 = (__int64)&gLsapExtensionList;
      gLsapExtensionList = (__int64)&gLsapExtensionList;
      _interlockedbittestandset(&gHasInitLsaIfConfig, 1u);
      result = LsapRegisterInterface(0, 0, (__int64)&gLsapRmFunctions);
      if ( (int)result >= 0 )
        return LsapRegisterInterface(0, 1u, (__int64)&gLsapCallbackFunctions);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140002b9c  sub     rsp, 28h
0x140002ba0  call    LsapBuildWellKnownSids
0x140002ba5  test    eax, eax
0x140002ba7  js      short loc_140002C19
0x140002ba9  call    LsapBuildSD
0x140002bae  test    eax, eax
0x140002bb0  js      short loc_140002C19
0x140002bb2  lea     rcx, gLsaIfLock; Resource
0x140002bb9  call    cs:__imp_RtlInitializeResource
0x140002bbf  lea     rax, gLsapIfList
0x140002bc6  xor     edx, edx
0x140002bc8  mov     cs:qword_14000C278, rax
0x140002bcf  lea     r8, gLsapRmFunctions
0x140002bd6  mov     cs:gLsapIfList, rax
0x140002bdd  xor     ecx, ecx
0x140002bdf  lea     rax, gLsapExtensionList
0x140002be6  mov     cs:qword_14000C2E8, rax
0x140002bed  mov     cs:gLsapExtensionList, rax
0x140002bf4  lock bts cs:gHasInitLsaIfConfig, 1
0x140002bfd  call    LsapRegisterInterface
0x140002c02  test    eax, eax
0x140002c04  js      short loc_140002C19
0x140002c06  lea     r8, gLsapCallbackFunctions
0x140002c0d  mov     edx, 1
0x140002c12  xor     ecx, ecx
0x140002c14  call    LsapRegisterInterface
0x140002c19  add     rsp, 28h
0x140002c1d  retn
```
