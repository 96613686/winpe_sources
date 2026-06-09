# NativeMsh::PwrshCommon::GetTrustedAssemblyList(ushort const *,std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool &)

- ea: `0x180008310`
- end: `0x1800083d9`
- name: `?GetTrustedAssemblyList@PwrshCommon@NativeMsh@@MEAAXPEBGAEAV?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z`
- size: `201`
- prototype: `void ***__fastcall(__int64, __int64, __int64, _BYTE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007018`
- `0x180007208`
- `0x180008310`
- `0x1800096b0`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800083a9`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800083a9`

## pseudocode

```c
void ***__fastcall NativeMsh::PwrshCommon::GetTrustedAssemblyList(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  void ***v8; // rbx
  void ***result; // rax
  void *v10[2]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v11; // [rsp+40h] [rbp-58h]
  unsigned __int64 v12; // [rsp+48h] [rbp-50h]

  v8 = (void ***)off_180014000;
  do
  {
    v12 = 7;
    v11 = 0;
    LOWORD(v10[0]) = 0;
    (*(void (__fastcall **)(__int64, __int64, void **, void **))(*(_QWORD *)a1 + 8LL))(a1, a2, *v8, v10);
    if ( v11 )
    {
      if ( *a4 )
        *a4 = 0;
      else
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(a3 + 16);
      std::operator<<<unsigned short>(a3 + 16, v10);
    }
    if ( v12 >= 8 )
      operator delete(v10[0]);
    ++v8;
    result = std::_Error_objects<int>::_System_object;
  }
  while ( v8 != std::_Error_objects<int>::_System_object );
  return result;
}

```

## disassembly

```asm
0x180008310  push    rbx
0x180008312  push    rbp
0x180008313  push    rsi
0x180008314  push    rdi
0x180008315  push    r14
0x180008317  push    r15
0x180008319  sub     rsp, 68h
0x18000831d  mov     rax, cs:__security_cookie
0x180008324  xor     rax, rsp
0x180008327  mov     [rsp+98h+var_48], rax
0x18000832c  mov     rsi, r9
0x18000832f  mov     rbp, r8
0x180008332  mov     r15, rdx
0x180008335  mov     r14, rcx
0x180008338  lea     rbx, off_180014000; "Microsoft.CSharp"
0x18000833f  mov     [rsp+98h+var_50], 7
0x180008348  mov     [rsp+98h+var_58], 0
0x180008351  xor     eax, eax
0x180008353  mov     word ptr [rsp+98h+var_68], ax
0x180008358  mov     rax, [r14]
0x18000835b  lea     r9, [rsp+98h+var_68]
0x180008360  mov     r8, [rbx]
0x180008363  mov     rdx, r15
0x180008366  mov     rcx, r14
0x180008369  mov     rax, [rax+8]
0x18000836d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008372  cmp     [rsp+98h+var_58], 0
0x180008378  jbe     short loc_18000839C
0x18000837a  cmp     byte ptr [rsi], 0
0x18000837d  jz      short loc_180008384
0x18000837f  mov     byte ptr [rsi], 0
0x180008382  jmp     short loc_18000838D
0x180008384  lea     rcx, [rbp+10h]
0x180008388  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18000838d  lea     rdx, [rsp+98h+var_68]
0x180008392  lea     rcx, [rbp+10h]
0x180008396  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18000839b  nop
0x18000839c  cmp     [rsp+98h+var_50], 8
0x1800083a2  jb      short loc_1800083AF
0x1800083a4  mov     rcx, [rsp+98h+var_68]
0x1800083a9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800083af  add     rbx, 8
0x1800083b3  lea     rax, ?_System_object@?$_Error_objects@H@std@@2V_System_error_category@2@A; std::_System_error_category std::_Error_objects<int>::_System_object
0x1800083ba  cmp     rbx, rax
0x1800083bd  jnz     short loc_18000833F
0x1800083bf  mov     rcx, [rsp+98h+var_48]
0x1800083c4  xor     rcx, rsp; StackCookie
0x1800083c7  call    __security_check_cookie
0x1800083cc  add     rsp, 68h
0x1800083d0  pop     r15
0x1800083d2  pop     r14
0x1800083d4  pop     rdi
0x1800083d5  pop     rsi
0x1800083d6  pop     rbp
0x1800083d7  pop     rbx
0x1800083d8  retn
```
