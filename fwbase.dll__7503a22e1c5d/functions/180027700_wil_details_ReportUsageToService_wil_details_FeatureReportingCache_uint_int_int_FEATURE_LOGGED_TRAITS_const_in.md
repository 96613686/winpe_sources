# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180027700`
- end: `0x180027854`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `340`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800293a0`
- `0x180029460`
- `0x18002dea0`
- `0x18002df50`
- `0x18002e010`
- `0x18002e0d0`
- `0x18002e180`

## callees

- `0x180027700`
- `0x180027860`
- `0x180030010`

## pseudocode

```c
void __fastcall wil::details::ReportUsageToService(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  if ( a7 && (unsigned int)wil::details::ReportUsageToServiceDirect(a1, a2) )
  {
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, 0, 1);
  }
}

```

## disassembly

```asm
0x180027700  push    rsi
0x180027702  push    rdi
0x180027703  sub     rsp, 58h
0x180027707  mov     rsi, [rsp+68h+arg_20]
0x18002770f  mov     edi, edx
0x180027711  movsxd  rdx, [rsp+68h+arg_30]
0x180027719  mov     r10, rcx
0x18002771c  test    edx, edx
0x18002771e  jz      loc_18002782E
0x180027724  mov     [rsp+68h+var_18], rbx
0x180027729  mov     ebx, [rsp+68h+arg_28]
0x180027730  cmp     edx, 6; switch 7 cases
0x180027733  ja      short def_180027747; jumptable 0000000180027747 default case
0x180027735  lea     r11, __ImageBase
0x18002773c  mov     ecx, ds:(jpt_180027747 - 180000000h)[r11+rdx*4]
0x180027744  add     rcx, r11
0x180027747  jmp     rcx; switch jump
0x180027749  xor     ecx, ecx; jumptable 0000000180027747 case 1
0x18002774b  mov     eax, 4
0x180027750  test    ebx, ebx
0x180027752  cmovz   ecx, eax
0x180027755  jmp     short loc_1800277CF
0x180027757  test    ebx, ebx; jumptable 0000000180027747 case 2
0x180027759  mov     ecx, 1
0x18002775e  mov     eax, 5
0x180027763  cmovz   ecx, eax
0x180027766  jmp     short loc_1800277CF
0x180027768  test    ebx, ebx; jumptable 0000000180027747 case 3
0x18002776a  mov     ecx, 2
0x18002776f  mov     eax, 6
0x180027774  cmovz   ecx, eax
0x180027777  jmp     short loc_1800277CF
0x180027779  test    ebx, ebx; jumptable 0000000180027747 case 4
0x18002777b  mov     ecx, 3
0x180027780  mov     eax, 7
0x180027785  cmovz   ecx, eax
0x180027788  jmp     short loc_1800277CF
0x18002778a  test    ebx, ebx; jumptable 0000000180027747 case 5
0x18002778c  mov     ecx, 8
0x180027791  mov     eax, 0Ah
0x180027796  cmovz   ecx, eax
0x180027799  jmp     short loc_1800277CF
0x18002779b  test    ebx, ebx; jumptable 0000000180027747 case 6
0x18002779d  mov     ecx, 9
0x1800277a2  mov     eax, 0Bh
0x1800277a7  cmovz   ecx, eax
0x1800277aa  jmp     short loc_1800277CF
0x1800277ac  sub     dl, 64h ; 'd'; jumptable 0000000180027747 default case
0x1800277af  cmp     dl, 31h ; '1'
0x1800277b2  ja      short loc_1800277CA; jumptable 0000000180027747 case 0
0x1800277b4  test    ebx, ebx
0x1800277b6  mov     eax, 96h
0x1800277bb  mov     ecx, 64h ; 'd'
0x1800277c0  cmovz   ecx, eax
0x1800277c3  movzx   eax, dl
0x1800277c6  add     ecx, eax
0x1800277c8  jmp     short loc_1800277CF
0x1800277ca  mov     ecx, 0FFh; jumptable 0000000180027747 case 0
0x1800277cf  movzx   eax, byte ptr [rsi+4]
0x1800277d3  mov     edx, edi
0x1800277d5  mov     byte ptr [rsp+68h+var_30], al
0x1800277d9  mov     dword ptr [rsp+68h+var_48], ecx
0x1800277dd  mov     rcx, r10
0x1800277e0  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x1800277e5  test    eax, eax
0x1800277e7  jz      short loc_180027829
0x1800277e9  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800277f0  test    rax, rax
0x1800277f3  jz      short loc_180027829
0x1800277f5  mov     [rsp+68h+var_30], 1
0x1800277fe  lea     rcx, [rsp+68h+arg_30]
0x180027806  mov     [rsp+68h+var_38], 0
0x18002780b  mov     r9d, ebx
0x18002780e  mov     [rsp+68h+var_40], 0
0x180027817  xor     r8d, r8d
0x18002781a  mov     [rsp+68h+var_48], rcx
0x18002781f  mov     rdx, rsi
0x180027822  mov     ecx, edi
0x180027824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027829  mov     rbx, [rsp+68h+var_18]
0x18002782e  add     rsp, 58h
0x180027832  pop     rdi
0x180027833  pop     rsi
0x180027834  retn
```
