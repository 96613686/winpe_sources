# DusmCache::SetOperatorCycleData(DusmConnection const &,_DUSM_OPERATOR_CYCLE_DATA const &)

- ea: `0x18001d6a4`
- end: `0x18001d730`
- name: `?SetOperatorCycleData@DusmCache@@SAXAEBVDusmConnection@@AEBU_DUSM_OPERATOR_CYCLE_DATA@@@Z`
- size: `140`
- prototype: `void __fastcall(const struct DusmConnection *, const struct _DUSM_OPERATOR_CYCLE_DATA *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015cc0`

## callees

- `0x18001d6a4`
- `0x18001d87c`
- `0x180020184`
- `0x18002c650`

## string_xrefs

- `0x18001d6f5`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001d71e`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001d70c`: `DusmCache::SetOperatorCycleData::mediaType`
- `0x18001d6e3`: `DusmCache::SetOperatorCycleData::iccid`

## pseudocode

```c
void __fastcall DusmCache::SetOperatorCycleData(const struct DusmConnection *a1, const BYTE *a2)
{
  const char *v4; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( *((_DWORD *)a1 + 4) != 3 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x350,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
      (const char *)0x57,
      (unsigned int)"DusmCache::SetOperatorCycleData::mediaType",
      v4);
  if ( !*((_QWORD *)a1 + 20) )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x355,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
      (const char *)0x57,
      (unsigned int)"DusmCache::SetOperatorCycleData::iccid",
      v4);
  DusmStore::SetOperatorCycleData(a1, a2);
  DusmCore::SetOperatorCycleData(a1, (const struct _DUSM_OPERATOR_CYCLE_DATA *)a2);
}

```

## disassembly

```asm
0x18001d6a4  mov     [rsp+arg_0], rbx
0x18001d6a9  push    rdi
0x18001d6aa  sub     rsp, 30h
0x18001d6ae  cmp     dword ptr [rcx+10h], 3
0x18001d6b2  mov     rdi, rdx
0x18001d6b5  mov     rbx, rcx
0x18001d6b8  jnz     short loc_18001D707
0x18001d6ba  cmp     qword ptr [rcx+0A0h], 0
0x18001d6c2  jz      short loc_18001D6DE
0x18001d6c4  call    ?SetOperatorCycleData@DusmStore@@SAXAEBVDusmConnection@@AEBU_DUSM_OPERATOR_CYCLE_DATA@@@Z; DusmStore::SetOperatorCycleData(DusmConnection const &,_DUSM_OPERATOR_CYCLE_DATA const &)
0x18001d6c9  mov     rdx, rdi; struct _DUSM_OPERATOR_CYCLE_DATA *
0x18001d6cc  mov     rcx, rbx; struct DusmConnection *
0x18001d6cf  mov     rbx, [rsp+38h+arg_0]
0x18001d6d4  add     rsp, 30h
0x18001d6d8  pop     rdi
0x18001d6d9  jmp     ?SetOperatorCycleData@DusmCore@@SAXAEBVDusmConnection@@AEBU_DUSM_OPERATOR_CYCLE_DATA@@@Z; DusmCore::SetOperatorCycleData(DusmConnection const &,_DUSM_OPERATOR_CYCLE_DATA const &)
0x18001d6de  mov     rcx, [rsp+38h]; this
0x18001d6e3  lea     rax, aDusmcacheSetop_0; "DusmCache::SetOperatorCycleData::iccid"
0x18001d6ea  mov     r9d, 57h ; 'W'; char *
0x18001d6f0  mov     qword ptr [rsp+38h+var_18], rax; unsigned int
0x18001d6f5  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001d6fc  mov     edx, 355h; void *
0x18001d701  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001d707  mov     rcx, [rsp+38h]; this
0x18001d70c  lea     rax, aDusmcacheSetop; "DusmCache::SetOperatorCycleData::mediaT"...
0x18001d713  mov     r9d, 57h ; 'W'; char *
0x18001d719  mov     qword ptr [rsp+38h+var_18], rax; unsigned int
0x18001d71e  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001d725  mov     edx, 350h; void *
0x18001d72a  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
