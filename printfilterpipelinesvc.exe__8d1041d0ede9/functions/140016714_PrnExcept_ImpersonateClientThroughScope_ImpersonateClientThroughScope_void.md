# PrnExcept::ImpersonateClientThroughScope::ImpersonateClientThroughScope(void)

- ea: `0x140016714`
- end: `0x140016738`
- name: `??0ImpersonateClientThroughScope@PrnExcept@@QEAA@XZ`
- size: `36`
- prototype: `PrnExcept::ImpersonateClientThroughScope *__fastcall(PrnExcept::ImpersonateClientThroughScope *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001026c`
- `0x140011af8`
- `0x140012404`
- `0x140016b1c`

## callees

- `0x140016714`
- `0x14004650c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001671d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14001671d`

## pseudocode

```c
PrnExcept::ImpersonateClientThroughScope *__fastcall PrnExcept::ImpersonateClientThroughScope::ImpersonateClientThroughScope(
        PrnExcept::ImpersonateClientThroughScope *this)
{
  HRESULT v2; // eax
  int v3; // edx
  const char *v4; // r8
  unsigned int v5; // r9d

  v2 = CoImpersonateClient();
  if ( v2 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v2, v3, v4, v5);
  return this;
}

```

## disassembly

```asm
0x140016714  push    rbx
0x140016716  sub     rsp, 20h
0x14001671a  mov     rbx, rcx
0x14001671d  call    cs:__imp_CoImpersonateClient
0x140016723  test    eax, eax
0x140016725  jns     short loc_14001672F
0x140016727  mov     ecx, eax; this
0x140016729  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x14001672f  mov     rax, rbx
0x140016732  add     rsp, 20h
0x140016736  pop     rbx
0x140016737  retn
```
