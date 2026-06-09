# DusmCache::SetSource(DusmConnection const &,_DUSM_SOURCE)

- ea: `0x18001d7c4`
- end: `0x18001d84e`
- name: `?SetSource@DusmCache@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015e70`

## callees

- `0x18001d7c4`
- `0x18001d87c`
- `0x1800203f4`
- `0x18002cfdc`

## string_xrefs

- `0x18001d813`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001d83c`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001d82a`: `DusmCache::SetSource::mediaType`
- `0x18001d801`: `DusmCache::SetSource::iccid`

## pseudocode

```c
__int64 __fastcall DusmCache::SetSource(__int64 a1, unsigned int a2)
{
  const char *v5; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( *(_DWORD *)(a1 + 16) != 3 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x376,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
      (const char *)0x57,
      (unsigned int)"DusmCache::SetSource::mediaType",
      v5);
  if ( !*(_QWORD *)(a1 + 160) )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x37B,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
      (const char *)0x57,
      (unsigned int)"DusmCache::SetSource::iccid",
      v5);
  DusmStore::SetSource(a1, a2);
  return DusmCore::SetSource(a1, a2);
}

```

## disassembly

```asm
0x18001d7c4  mov     [rsp+arg_0], rbx
0x18001d7c9  push    rdi
0x18001d7ca  sub     rsp, 30h
0x18001d7ce  cmp     dword ptr [rcx+10h], 3
0x18001d7d2  mov     edi, edx
0x18001d7d4  mov     rbx, rcx
0x18001d7d7  jnz     short loc_18001D825
0x18001d7d9  cmp     qword ptr [rcx+0A0h], 0
0x18001d7e1  jz      short loc_18001D7FC
0x18001d7e3  call    ?SetSource@DusmStore@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@@Z; DusmStore::SetSource(DusmConnection const &,_DUSM_SOURCE)
0x18001d7e8  mov     edx, edi
0x18001d7ea  mov     rcx, rbx
0x18001d7ed  mov     rbx, [rsp+38h+arg_0]
0x18001d7f2  add     rsp, 30h
0x18001d7f6  pop     rdi
0x18001d7f7  jmp     ?SetSource@DusmCore@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@@Z; DusmCore::SetSource(DusmConnection const &,_DUSM_SOURCE)
0x18001d7fc  mov     rcx, [rsp+38h]; this
0x18001d801  lea     rax, aDusmcacheSetso; "DusmCache::SetSource::iccid"
0x18001d808  mov     r9d, 57h ; 'W'; char *
0x18001d80e  mov     qword ptr [rsp+38h+var_18], rax; unsigned int
0x18001d813  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001d81a  mov     edx, 37Bh; void *
0x18001d81f  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001d825  mov     rcx, [rsp+38h]; this
0x18001d82a  lea     rax, aDusmcacheSetso_0; "DusmCache::SetSource::mediaType"
0x18001d831  mov     r9d, 57h ; 'W'; char *
0x18001d837  mov     qword ptr [rsp+38h+var_18], rax; unsigned int
0x18001d83c  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001d843  mov     edx, 376h; void *
0x18001d848  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
