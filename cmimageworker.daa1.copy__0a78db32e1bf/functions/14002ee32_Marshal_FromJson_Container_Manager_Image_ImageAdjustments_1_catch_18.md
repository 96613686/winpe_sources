# _Marshal::FromJson_Container::Manager::Image::ImageAdjustments__::_1_::catch$18

- ea: `0x14002ee32`
- end: `0x14002efbb`
- name: `_Marshal::FromJson_Container::Manager::Image::ImageAdjustments__::_1_::catch$18`
- size: `393`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x140002c18`
- `0x140012934`
- `0x140015168`
- `0x14001f36c`
- `0x14001fff4`
- `0x14002ee32`

## pseudocode

```c
__int64 __fastcall Marshal::FromJson_Container::Manager::Image::ImageAdjustments__::_1_::catch_18(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rdi
  __int64 v5; // rax
  __int64 *v6; // rdi
  unsigned __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rsi
  __int64 v10; // r14

  *(_OWORD *)(a2 + 176) = 0;
  *(_QWORD *)(a2 + 192) = 0;
  *(_QWORD *)(a2 + 200) = 0;
  std::wstring::_Construct<1,unsigned short const *>(a2 + 176, L"$", 1);
  *(_DWORD *)(a2 + 208) = 13;
  *(_OWORD *)(a2 + 80) = 0;
  *(_QWORD *)(a2 + 96) = 0;
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Buy_nonzero(a2 + 80, 1);
  *(_QWORD *)(a2 + 160) = a2 + 80;
  v3 = *(_QWORD *)(a2 + 80);
  v4 = a2 + 176;
  *(_QWORD *)(a2 + 56) = v3;
  *(_QWORD *)(a2 + 64) = v3;
  *(_QWORD *)(a2 + 72) = a2 + 80;
  do
  {
    std::pair<std::wstring,enum Marshal::UnmarshalError>::pair<std::wstring,enum Marshal::UnmarshalError>(v3, v4);
    v3 += 40;
    *(_QWORD *)(a2 + 64) = v3;
    v4 += 40;
  }
  while ( v4 != a2 + 216 );
  *(_QWORD *)(a2 + 88) = v3;
  v5 = *(_QWORD *)(a2 + 120);
  *(_BYTE *)v5 = 0;
  v6 = (__int64 *)(v5 + 8);
  *(_QWORD *)(v5 + 8) = 0;
  *(_QWORD *)(v5 + 16) = 0;
  *(_QWORD *)(v5 + 24) = 0;
  v7 = 0xCCCCCCCCCCCCCCCDuLL * ((v3 - *(_QWORD *)(a2 + 80)) >> 3);
  if ( v7 )
  {
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Buy_nonzero(v6, v7);
    *(_QWORD *)(a2 + 160) = v6;
    v8 = *v6;
    v9 = *(_QWORD *)(a2 + 80);
    v10 = *(_QWORD *)(a2 + 88);
    *(_QWORD *)(a2 + 56) = *v6;
    *(_QWORD *)(a2 + 64) = v8;
    *(_QWORD *)(a2 + 72) = v6;
    while ( v9 != v10 )
    {
      std::pair<std::wstring,enum Marshal::UnmarshalError>::pair<std::wstring,enum Marshal::UnmarshalError>(v8, v9);
      v8 += 40;
      *(_QWORD *)(a2 + 64) = v8;
      v9 += 40;
    }
    v6[1] = v8;
  }
  *(_DWORD *)(a2 + 48) |= 1u;
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(a2 + 80);
  `eh vector destructor iterator'(
    (void *)(a2 + 176),
    0x28u,
    1u,
    std::pair<std::wstring,enum Marshal::UnmarshalError>::~pair<std::wstring,enum Marshal::UnmarshalError>);
  return 0;
}

```

## disassembly

```asm
0x14002ee32  mov     [rsp+arg_8], rdx
0x14002ee37  push    rbx
0x14002ee38  push    rbp
0x14002ee39  push    rsi
0x14002ee3a  push    rdi
0x14002ee3b  push    r14
0x14002ee3d  sub     rsp, 30h
0x14002ee41  mov     rbp, rdx
0x14002ee44  xorps   xmm0, xmm0
0x14002ee47  movups  xmmword ptr [rbp+0B0h], xmm0
0x14002ee4e  mov     qword ptr [rbp+0C0h], 0
0x14002ee59  mov     qword ptr [rbp+0C8h], 0
0x14002ee64  mov     r8d, 1
0x14002ee6a  lea     rdx, asc_14003732C; "$"
0x14002ee71  lea     rcx, [rbp+0B0h]
0x14002ee78  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14002ee7d  mov     dword ptr [rbp+0D0h], 0Dh
0x14002ee87  xorps   xmm0, xmm0
0x14002ee8a  movdqu  xmmword ptr [rbp+50h], xmm0
0x14002ee8f  mov     qword ptr [rbp+60h], 0
0x14002ee97  mov     edx, 1
0x14002ee9c  lea     rcx, [rbp+50h]
0x14002eea0  call    ?_Buy_nonzero@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAX_K@Z; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Buy_nonzero(unsigned __int64)
0x14002eea5  lea     rax, [rbp+50h]
0x14002eea9  mov     [rbp+0A0h], rax
0x14002eeb0  mov     rbx, [rbp+50h]
0x14002eeb4  lea     rdi, [rbp+0B0h]
0x14002eebb  mov     [rbp+38h], rbx
0x14002eebf  mov     [rbp+40h], rbx
0x14002eec3  lea     rax, [rbp+50h]
0x14002eec7  mov     [rbp+48h], rax
0x14002eecb  mov     rdx, rdi
0x14002eece  mov     rcx, rbx
0x14002eed1  call    ??0?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@QEAA@AEBU01@@Z; std::pair<std::wstring,Marshal::UnmarshalError>::pair<std::wstring,Marshal::UnmarshalError>(std::pair<std::wstring,Marshal::UnmarshalError> const &)
0x14002eed6  add     rbx, 28h ; '('
0x14002eeda  mov     [rbp+40h], rbx
0x14002eede  add     rdi, 28h ; '('
0x14002eee2  lea     rax, [rbp+0D8h]
0x14002eee9  cmp     rdi, rax
0x14002eeec  jnz     short loc_14002EECB
0x14002eeee  mov     [rbp+58h], rbx
0x14002eef2  mov     rax, [rbp+78h]
0x14002eef6  mov     byte ptr [rax], 0
0x14002eef9  lea     rdi, [rax+8]
0x14002eefd  mov     qword ptr [rdi], 0
0x14002ef04  mov     qword ptr [rdi+8], 0
0x14002ef0c  mov     qword ptr [rdi+10h], 0
0x14002ef14  sub     rbx, [rbp+50h]
0x14002ef18  sar     rbx, 3
0x14002ef1c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14002ef26  imul    rbx, rax
0x14002ef2a  test    rbx, rbx
0x14002ef2d  jz      short loc_14002EF7A
0x14002ef2f  mov     rdx, rbx
0x14002ef32  mov     rcx, rdi
0x14002ef35  call    ?_Buy_nonzero@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAX_K@Z; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Buy_nonzero(unsigned __int64)
0x14002ef3a  mov     [rbp+0A0h], rdi
0x14002ef41  mov     rbx, [rdi]
0x14002ef44  mov     rsi, [rbp+50h]
0x14002ef48  mov     r14, [rbp+58h]
0x14002ef4c  mov     [rbp+38h], rbx
0x14002ef50  mov     [rbp+40h], rbx
0x14002ef54  mov     [rbp+48h], rdi
0x14002ef58  jmp     short loc_14002EF71
0x14002ef5a  mov     rdx, rsi
0x14002ef5d  mov     rcx, rbx
0x14002ef60  call    ??0?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@QEAA@AEBU01@@Z; std::pair<std::wstring,Marshal::UnmarshalError>::pair<std::wstring,Marshal::UnmarshalError>(std::pair<std::wstring,Marshal::UnmarshalError> const &)
0x14002ef65  add     rbx, 28h ; '('
0x14002ef69  mov     [rbp+40h], rbx
0x14002ef6d  add     rsi, 28h ; '('
0x14002ef71  cmp     rsi, r14
0x14002ef74  jnz     short loc_14002EF5A
0x14002ef76  mov     [rdi+8], rbx
0x14002ef7a  or      dword ptr [rbp+30h], 1
0x14002ef7e  lea     rcx, [rbp+50h]
0x14002ef82  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x14002ef87  nop
0x14002ef88  lea     r9, ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@QEAA@XZ; void (*)(void *)
0x14002ef8f  mov     edx, 28h ; '('; unsigned __int64
0x14002ef94  lea     r8d, [rdx-27h]; unsigned __int64
0x14002ef98  lea     rcx, [rbp+0B0h]; void *
0x14002ef9f  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14002efa4  nop
0x14002efa5  mov     rax, 0
0x14002efaf  add     rsp, 30h
0x14002efb3  pop     r14
0x14002efb5  pop     rdi
0x14002efb6  pop     rsi
0x14002efb7  pop     rbp
0x14002efb8  pop     rbx
0x14002efb9  retn
```
