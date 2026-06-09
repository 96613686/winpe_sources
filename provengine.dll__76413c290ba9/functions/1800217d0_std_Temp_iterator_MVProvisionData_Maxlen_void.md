# std::_Temp_iterator<_MVProvisionData *>::_Maxlen(void)

- ea: `0x1800217d0`
- end: `0x180021859`
- name: `?_Maxlen@?$_Temp_iterator@PEAU_MVProvisionData@@@std@@QEAA_JXZ`
- size: `137`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ba80`
- `0x18000c074`
- `0x18000efa4`

## callees

- `0x1800026c8`
- `0x1800217d0`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800217ff`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800217ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Temp_iterator<_MVProvisionData *>::_Maxlen(__int64 a1)
{
  _QWORD *v2; // rbx
  __int64 v3; // rbx
  void *v4; // rax

  v2 = *(_QWORD **)(a1 + 32);
  if ( !*v2 )
  {
    v3 = v2[3];
    if ( v3 > 0 )
    {
      if ( (unsigned __int64)v3 > 0x1FFFFFFFFFFFFFFFLL )
      {
        std::_Xbad_alloc();
        __debugbreak();
      }
      do
      {
        v4 = operator new(8 * v3, (const struct std::nothrow_t *)&std::nothrow);
        if ( v4 )
          break;
        v3 = (unsigned __int64)v3 >> 1;
      }
      while ( v3 );
      **(_QWORD **)(a1 + 32) = v4;
      *(_QWORD *)(*(_QWORD *)(a1 + 32) + 8LL) = v4;
      *(_QWORD *)(*(_QWORD *)(a1 + 32) + 16LL) = v4;
      *(_QWORD *)(*(_QWORD *)(a1 + 32) + 24LL) = v3;
    }
  }
  return *(_QWORD *)(*(_QWORD *)(a1 + 32) + 24LL);
}

```

## disassembly

```asm
0x1800217d0  mov     [rsp+arg_0], rbx
0x1800217d5  push    rdi
0x1800217d6  sub     rsp, 20h
0x1800217da  mov     rdi, rcx
0x1800217dd  mov     rbx, [rcx+20h]
0x1800217e1  cmp     qword ptr [rbx], 0
0x1800217e5  jnz     short loc_180021846
0x1800217e7  mov     rbx, [rbx+18h]
0x1800217eb  test    rbx, rbx
0x1800217ee  jle     short loc_180021846
0x1800217f0  mov     rax, 1FFFFFFFFFFFFFFFh
0x1800217fa  cmp     rbx, rax
0x1800217fd  jbe     short loc_180021806
0x1800217ff  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180021805  int     3; Trap to Debugger
0x180021806  lea     rcx, ds:0[rbx*8]; unsigned __int64
0x18002180e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021815  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002181a  mov     rdx, rax
0x18002181d  test    rax, rax
0x180021820  jnz     short loc_180021827
0x180021822  shr     rbx, 1
0x180021825  jnz     short loc_180021806
0x180021827  mov     rcx, [rdi+20h]
0x18002182b  mov     [rcx], rdx
0x18002182e  mov     rcx, [rdi+20h]
0x180021832  mov     [rcx+8], rdx
0x180021836  mov     rax, [rdi+20h]
0x18002183a  mov     [rax+10h], rdx
0x18002183e  mov     rax, [rdi+20h]
0x180021842  mov     [rax+18h], rbx
0x180021846  mov     rax, [rdi+20h]
0x18002184a  mov     rax, [rax+18h]
0x18002184e  mov     rbx, [rsp+28h+arg_0]
0x180021853  add     rsp, 20h
0x180021857  pop     rdi
0x180021858  retn
```
