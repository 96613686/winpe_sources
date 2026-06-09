# tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(ushort,char const *)

- ea: `0x1800165dc`
- end: `0x18001668c`
- name: `?complete_and_succeed@?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXGPEBD@Z`
- size: `176`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800078f0`
- `0x1800079dc`
- `0x180007a38`
- `0x180007b00`
- `0x180007b54`
- `0x1800087a4`
- `0x180008be0`
- `0x180009504`
- `0x180012024`
- `0x180013df0`
- `0x1800145d0`
- `0x180014cd0`
- `0x1800150d0`

## callees

- `0x1800165dc`
- `0x180016694`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180016664`
- `KERNEL32!LeaveCriticalSection` at `0x180016664`
- `KERNEL32!EnterCriticalSection` at `0x180016612`
- `KERNEL32!EnterCriticalSection` at `0x180016612`

## pseudocode

```c
void __fastcall tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>>::complete_and_succeed(
        __int64 a1,
        __int16 a2,
        __int64 a3)
{
  LPVOID v3; // rdi

  v3 = g_usageTipTest;
  if ( g_usageTipTest )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)g_usageTipTest + 5);
    if ( !*((_BYTE *)v3 + 168) )
    {
      *((_BYTE *)v3 + 168) = 1;
      *((_WORD *)v3 + 85) = a2;
      *((_QWORD *)v3 + 22) = a3;
    }
    *((_DWORD *)v3 + 18) |= 0x300u;
    if ( *((_QWORD *)v3 + 31) )
      tip2::details::shared_data<0,0,1>::complete_helper((__int64)v3 + 8, 2);
    if ( v3 != (LPVOID)-200LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)v3 + 5);
  }
}

```

## disassembly

```asm
0x1800165dc  mov     rax, rsp
0x1800165df  mov     [rax+8], rbx
0x1800165e3  mov     [rax+10h], rbp
0x1800165e7  mov     [rax+18h], rsi
0x1800165eb  mov     [rax+20h], rdi
0x1800165ef  push    r14
0x1800165f1  sub     rsp, 20h
0x1800165f5  mov     rdi, cs:?g_usageTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>> g_usageTipTest
0x1800165fc  mov     rbp, r8
0x1800165ff  movzx   r14d, dx
0x180016603  test    rdi, rdi
0x180016606  jz      short loc_180016670
0x180016608  lea     rsi, [rdi+0C8h]
0x18001660f  mov     rcx, rsi; lpCriticalSection
0x180016612  call    cs:__imp_EnterCriticalSection
0x180016619  nop     dword ptr [rax+rax+00h]
0x18001661e  cmp     byte ptr [rdi+0A8h], 0
0x180016625  jnz     short loc_18001663D
0x180016627  mov     byte ptr [rdi+0A8h], 1
0x18001662e  mov     [rdi+0AAh], r14w
0x180016636  mov     [rdi+0B0h], rbp
0x18001663d  or      dword ptr [rdi+48h], 300h
0x180016644  cmp     qword ptr [rdi+0F8h], 0
0x18001664c  jz      short loc_18001665C
0x18001664e  mov     edx, 2
0x180016653  lea     rcx, [rdi+8]
0x180016657  call    ?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)
0x18001665c  test    rsi, rsi
0x18001665f  jz      short loc_180016670
0x180016661  mov     rcx, rsi; lpCriticalSection
0x180016664  call    cs:__imp_LeaveCriticalSection
0x18001666b  nop     dword ptr [rax+rax+00h]
0x180016670  mov     rbx, [rsp+28h+arg_0]
0x180016675  mov     rbp, [rsp+28h+arg_8]
0x18001667a  mov     rsi, [rsp+28h+arg_10]
0x18001667f  mov     rdi, [rsp+28h+arg_18]
0x180016684  add     rsp, 20h
0x180016688  pop     r14
0x18001668a  retn
```
