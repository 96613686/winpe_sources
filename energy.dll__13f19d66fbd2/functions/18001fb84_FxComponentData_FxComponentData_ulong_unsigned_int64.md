# FxComponentData::FxComponentData(ulong,unsigned __int64)

- ea: `0x18001fb84`
- end: `0x18001fca4`
- name: `??0FxComponentData@@QEAA@K_K@Z`
- size: `288`
- prototype: `FxComponentData *__fastcall(FxComponentData *this, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001f820`

## callees

- `0x18001e790`
- `0x18001f1f0`
- `0x18001fb84`
- `0x18001fe8c`
- `0x180020164`
- `0x180020208`
- `0x1800202b8`
- `0x180020454`
- `0x18003bb60`
- `0x18003bf74`
- `0x18004ca90`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18001fbf2`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18001fbf2`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18001fc65`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18001fc65`

## string_xrefs

- `0x18001fbdc`: `Component `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
FxComponentData *__fastcall FxComponentData::FxComponentData(FxComponentData *this, __int64 a2)
{
  unsigned int v2; // ebx
  __int64 v4; // rax
  _QWORD v6[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v7[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v8[128]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v9[104]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v10; // [rsp+140h] [rbp+40h] BYREF
  __int128 v11; // [rsp+150h] [rbp+50h]

  v2 = a2;
  BlockerData::BlockerData(this, a2);
  *(_QWORD *)this = &FxComponentData::`vftable';
  *((_DWORD *)this + 146) = v2;
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v7);
  v4 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v7, "Component ");
  std::basic_ostream<unsigned short>::operator<<(v4, v2);
  v10 = 0;
  v11 = 0;
  std::wstring::_Construct_empty(&v10);
  std::basic_stringbuf<unsigned short>::_Get_buffer_view(v8, v6);
  if ( v6[0] )
    std::wstring::assign(&v10, v6[0], v6[1]);
  std::wstring::operator=((char *)this + 8, &v10);
  if ( *((_QWORD *)&v11 + 1) > 7u )
    std::_Deallocate<16>((void *)v10, 2LL * *((_QWORD *)&v11 + 1) + 2);
  std::basic_ostringstream<unsigned short>::~basic_ostringstream<unsigned short>(v9);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v9);
  return this;
}

```

## disassembly

```asm
0x18001fb84  mov     [rsp-8+arg_10], rbx
0x18001fb89  mov     [rsp-8+arg_18], rdi
0x18001fb8e  push    rbp
0x18001fb8f  lea     rbp, [rsp-70h]
0x18001fb94  sub     rsp, 170h
0x18001fb9b  mov     rax, cs:__security_cookie
0x18001fba2  xor     rax, rsp
0x18001fba5  mov     [rbp+70h+var_10], rax
0x18001fba9  mov     ebx, edx
0x18001fbab  mov     rdi, rcx
0x18001fbae  mov     [rsp+170h+var_148], rcx
0x18001fbb3  mov     [rsp+170h+var_150], 0
0x18001fbbb  call    ??0BlockerData@@QEAA@W4BlockerType@@_K@Z; BlockerData::BlockerData(BlockerType,unsigned __int64)
0x18001fbc0  nop
0x18001fbc1  lea     rax, ??_7FxComponentData@@6B@; const FxComponentData::`vftable'
0x18001fbc8  mov     [rdi], rax
0x18001fbcb  mov     [rdi+248h], ebx
0x18001fbd1  lea     rcx, [rsp+170h+var_120]
0x18001fbd6  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18001fbdb  nop
0x18001fbdc  lea     rdx, aComponent_1; "Component "
0x18001fbe3  lea     rcx, [rsp+170h+var_120]
0x18001fbe8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18001fbed  mov     edx, ebx
0x18001fbef  mov     rcx, rax
0x18001fbf2  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x18001fbf8  nop
0x18001fbf9  xorps   xmm0, xmm0
0x18001fbfc  movups  [rbp+70h+var_30], xmm0
0x18001fc00  xorps   xmm1, xmm1
0x18001fc03  movdqu  [rbp+70h+var_20], xmm1
0x18001fc08  lea     rcx, [rbp+70h+var_30]
0x18001fc0c  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18001fc11  mov     [rsp+170h+var_150], 2
0x18001fc19  lea     rdx, [rsp+170h+var_140]
0x18001fc1e  lea     rcx, [rsp+170h+var_118]
0x18001fc23  call    ?_Get_buffer_view@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AU_Buffer_view@12@XZ; std::basic_stringbuf<ushort>::_Get_buffer_view(void)
0x18001fc28  mov     rdx, [rsp+170h+var_140]
0x18001fc2d  test    rdx, rdx
0x18001fc30  jz      short loc_18001FC41
0x18001fc32  mov     r8, [rsp+170h+var_138]
0x18001fc37  lea     rcx, [rbp+70h+var_30]
0x18001fc3b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x18001fc40  nop
0x18001fc41  lea     rcx, [rdi+8]
0x18001fc45  lea     rdx, [rbp+70h+var_30]
0x18001fc49  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001fc4e  mov     rdx, qword ptr [rbp+70h+var_20+8]
0x18001fc52  cmp     rdx, 7
0x18001fc56  ja      short loc_18001FC90
0x18001fc58  lea     rcx, [rbp+70h+var_98]
0x18001fc5c  call    ??1?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_ostringstream<ushort>::~basic_ostringstream<ushort>(void)
0x18001fc61  lea     rcx, [rbp+70h+var_98]
0x18001fc65  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x18001fc6b  nop
0x18001fc6c  mov     rax, rdi
0x18001fc6f  mov     rcx, [rbp+70h+var_10]
0x18001fc73  xor     rcx, rsp; StackCookie
0x18001fc76  call    __security_check_cookie
0x18001fc7b  lea     r11, [rsp+170h+var_s0]
0x18001fc83  mov     rbx, [r11+20h]
0x18001fc87  mov     rdi, [r11+28h]
0x18001fc8b  mov     rsp, r11
0x18001fc8e  pop     rbp
0x18001fc8f  retn
0x18001fc90  lea     rdx, ds:2[rdx*2]
0x18001fc98  mov     rcx, qword ptr [rbp+70h+var_30]
0x18001fc9c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001fca1  jmp     short loc_18001FC58
```
