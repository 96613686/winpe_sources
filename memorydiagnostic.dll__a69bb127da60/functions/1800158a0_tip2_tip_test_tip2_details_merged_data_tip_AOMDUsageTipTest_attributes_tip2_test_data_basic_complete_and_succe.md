# tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)

- ea: `0x1800158a0`
- end: `0x18001591f`
- name: `?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z`
- size: `127`
- prototype: `void __fastcall(__int64, __int16, __int64)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800078a8`
- `0x1800078f0`
- `0x1800079bc`
- `0x180007aa0`
- `0x180007b4c`
- `0x180007b94`
- `0x180008bf0`
- `0x1800094d4`
- `0x1800115f8`
- `0x1800132f0`
- `0x1800139d0`
- `0x180014030`
- `0x1800143d0`

## callees

- `0x1800158a0`
- `0x180015928`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180015910`
- `KERNEL32!LeaveCriticalSection` at `0x180015910`
- `KERNEL32!EnterCriticalSection` at `0x1800158c5`
- `KERNEL32!EnterCriticalSection` at `0x1800158c5`

## pseudocode

```c
void __fastcall tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
        __int64 a1,
        __int16 a2,
        __int64 a3)
{
  char *v3; // rbx

  v3 = (char *)g_usageTipTest;
  if ( g_usageTipTest )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)g_usageTipTest + 5);
    if ( !v3[168] )
    {
      v3[168] = 1;
      *((_WORD *)v3 + 85) = a2;
      *((_QWORD *)v3 + 22) = a3;
    }
    *((_DWORD *)v3 + 18) |= 0x300u;
    if ( *((_QWORD *)v3 + 31) )
      tip2::details::shared_data<0,0,1>::complete_helper(v3 + 8, 2);
    if ( v3 != (char *)-200LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)v3 + 5);
  }
}

```

## disassembly

```asm
0x1800158a0  push    rbx
0x1800158a2  push    rbp
0x1800158a3  push    rsi
0x1800158a4  push    rdi
0x1800158a5  sub     rsp, 28h
0x1800158a9  mov     rbx, cs:?g_usageTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>> g_usageTipTest
0x1800158b0  mov     rsi, r8
0x1800158b3  movzx   ebp, dx
0x1800158b6  test    rbx, rbx
0x1800158b9  jz      short loc_180015916
0x1800158bb  lea     rdi, [rbx+0C8h]
0x1800158c2  mov     rcx, rdi; lpCriticalSection
0x1800158c5  call    cs:__imp_EnterCriticalSection
0x1800158cb  cmp     byte ptr [rbx+0A8h], 0
0x1800158d2  jnz     short loc_1800158E9
0x1800158d4  mov     byte ptr [rbx+0A8h], 1
0x1800158db  mov     [rbx+0AAh], bp
0x1800158e2  mov     [rbx+0B0h], rsi
0x1800158e9  or      dword ptr [rbx+48h], 300h
0x1800158f0  cmp     qword ptr [rbx+0F8h], 0
0x1800158f8  jz      short loc_180015908
0x1800158fa  mov     edx, 2
0x1800158ff  lea     rcx, [rbx+8]
0x180015903  call    ?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)
0x180015908  test    rdi, rdi
0x18001590b  jz      short loc_180015916
0x18001590d  mov     rcx, rdi; lpCriticalSection
0x180015910  call    cs:__imp_LeaveCriticalSection
0x180015916  add     rsp, 28h
0x18001591a  pop     rdi
0x18001591b  pop     rsi
0x18001591c  pop     rbp
0x18001591d  pop     rbx
0x18001591e  retn
```
