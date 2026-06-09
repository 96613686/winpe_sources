# DusmCache::SetEnableOperatorToast(DusmConnection const &,int)

- ea: `0x18001d5e4`
- end: `0x18001d66e`
- name: `?SetEnableOperatorToast@DusmCache@@SAXAEBVDusmConnection@@H@Z`
- size: `138`
- prototype: `void __fastcall(const struct DusmConnection *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015cc0`

## callees

- `0x18001d5e4`
- `0x18001d87c`
- `0x180020048`
- `0x18002c174`

## string_xrefs

- `0x18001d633`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001d65c`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001d64a`: `DusmCache::SetEnableOperatorToast::mediaType`
- `0x18001d621`: `DusmCache::SetEnableOperatorToast::iccid`

## pseudocode

```c
void __fastcall DusmCache::SetEnableOperatorToast(const struct DusmConnection *a1, int a2)
{
  const char *v4; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( *((_DWORD *)a1 + 4) != 3 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x41A,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
      (const char *)0x57,
      (unsigned int)"DusmCache::SetEnableOperatorToast::mediaType",
      v4);
  if ( !*((_QWORD *)a1 + 20) )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x41F,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
      (const char *)0x57,
      (unsigned int)"DusmCache::SetEnableOperatorToast::iccid",
      v4);
  DusmStore::SetEnableOperatorToast(a1, a2);
  DusmCore::SetEnableOperatorToast(a1, a2);
}

```

## disassembly

```asm
0x18001d5e4  mov     [rsp+arg_0], rbx
0x18001d5e9  push    rdi
0x18001d5ea  sub     rsp, 30h
0x18001d5ee  cmp     dword ptr [rcx+10h], 3
0x18001d5f2  mov     edi, edx
0x18001d5f4  mov     rbx, rcx
0x18001d5f7  jnz     short loc_18001D645
0x18001d5f9  cmp     qword ptr [rcx+0A0h], 0
0x18001d601  jz      short loc_18001D61C
0x18001d603  call    ?SetEnableOperatorToast@DusmStore@@SAXAEBVDusmConnection@@H@Z; DusmStore::SetEnableOperatorToast(DusmConnection const &,int)
0x18001d608  mov     edx, edi; int
0x18001d60a  mov     rcx, rbx; struct DusmConnection *
0x18001d60d  mov     rbx, [rsp+38h+arg_0]
0x18001d612  add     rsp, 30h
0x18001d616  pop     rdi
0x18001d617  jmp     ?SetEnableOperatorToast@DusmCore@@SAXAEBVDusmConnection@@H@Z; DusmCore::SetEnableOperatorToast(DusmConnection const &,int)
0x18001d61c  mov     rcx, [rsp+38h]; this
0x18001d621  lea     rax, aDusmcacheSeten_0; "DusmCache::SetEnableOperatorToast::icci"...
0x18001d628  mov     r9d, 57h ; 'W'; char *
0x18001d62e  mov     qword ptr [rsp+38h+var_18], rax; unsigned int
0x18001d633  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001d63a  mov     edx, 41Fh; void *
0x18001d63f  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001d645  mov     rcx, [rsp+38h]; this
0x18001d64a  lea     rax, aDusmcacheSeten; "DusmCache::SetEnableOperatorToast::medi"...
0x18001d651  mov     r9d, 57h ; 'W'; char *
0x18001d657  mov     qword ptr [rsp+38h+var_18], rax; unsigned int
0x18001d65c  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001d663  mov     edx, 41Ah; void *
0x18001d668  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
