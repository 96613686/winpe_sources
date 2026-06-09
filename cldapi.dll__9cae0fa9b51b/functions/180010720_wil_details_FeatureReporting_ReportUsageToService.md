# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x180010720`
- end: `0x180010837`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180010cb4`

## callees

- `0x180010720`
- `0x180010840`
- `0x18001e010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  unsigned int v7; // [rsp+70h] [rbp+18h] BYREF

  v7 = a3;
  v3 = a2 & 1;
  v4 = a3;
  if ( a3 )
  {
    v4 = a3 - 1;
    if ( a3 == 1 )
    {
      v5 = 4 * (unsigned int)!(a2 & 1);
      goto LABEL_17;
    }
    v4 = a3 - 2;
    if ( a3 == 2 )
    {
      v5 = 4 * (unsigned int)!(a2 & 1) + 1;
      goto LABEL_17;
    }
    v4 = a3 - 3;
    if ( a3 == 3 )
    {
      v5 = 4 * (unsigned int)!(a2 & 1) + 2;
      goto LABEL_17;
    }
    v4 = a3 - 4;
    if ( a3 == 4 )
    {
      v5 = 4 * (unsigned int)!(a2 & 1) + 3;
      goto LABEL_17;
    }
    v4 = a3 - 5;
    if ( a3 == 5 )
    {
      v5 = 2 * (unsigned int)!(a2 & 1) + 8;
      goto LABEL_17;
    }
    if ( a3 == 6 )
    {
      v5 = 2 * (unsigned int)!(a2 & 1) + 9;
      goto LABEL_17;
    }
    if ( (unsigned __int8)(a3 - 100) <= 0x31u )
    {
      v5 = (unsigned __int8)(a3 - 100) + (v3 != 0 ? 100 : 150);
      goto LABEL_17;
    }
  }
  v5 = 255;
LABEL_17:
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil_details_FeatureReporting_ReportUsageToServiceDirect(
                                                                                                     v4,
                                                                                                     a2,
                                                                                                     v5);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(57207774, &Feature_57207774_logged_traits, 0, v3, &v7, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180010720  mov     [rsp+arg_10], r8d
0x180010725  push    rbx
0x180010726  sub     rsp, 50h
0x18001072a  mov     ebx, edx
0x18001072c  mov     r9d, r8d
0x18001072f  and     ebx, 1
0x180010732  mov     ecx, r8d
0x180010735  test    r8d, r8d
0x180010738  jz      loc_1800107DD
0x18001073e  sub     ecx, 1
0x180010741  jz      loc_1800107D0
0x180010747  sub     ecx, 1
0x18001074a  jz      short loc_1800107C1
0x18001074c  sub     ecx, 1
0x18001074f  jz      short loc_1800107B2
0x180010751  sub     ecx, 1
0x180010754  jz      short loc_1800107A3
0x180010756  sub     ecx, 1
0x180010759  jz      short loc_180010794
0x18001075b  cmp     ecx, 1
0x18001075e  jz      short loc_180010785
0x180010760  sub     r9b, 64h ; 'd'
0x180010764  cmp     r9b, 31h ; '1'
0x180010768  ja      short loc_1800107DD
0x18001076a  mov     eax, ebx
0x18001076c  neg     eax
0x18001076e  movzx   eax, r9b
0x180010772  sbb     r8d, r8d
0x180010775  and     r8d, 0FFFFFFCEh
0x180010779  add     r8d, 96h
0x180010780  add     r8d, eax
0x180010783  jmp     short loc_1800107E3
0x180010785  mov     eax, ebx
0x180010787  xor     eax, 1
0x18001078a  lea     r8d, ds:9[rax*2]
0x180010792  jmp     short loc_1800107E3
0x180010794  mov     eax, ebx
0x180010796  xor     eax, 1
0x180010799  lea     r8d, ds:8[rax*2]
0x1800107a1  jmp     short loc_1800107E3
0x1800107a3  mov     eax, ebx
0x1800107a5  xor     eax, 1
0x1800107a8  lea     r8d, ds:3[rax*4]
0x1800107b0  jmp     short loc_1800107E3
0x1800107b2  mov     eax, ebx
0x1800107b4  xor     eax, 1
0x1800107b7  lea     r8d, ds:2[rax*4]
0x1800107bf  jmp     short loc_1800107E3
0x1800107c1  mov     eax, ebx
0x1800107c3  xor     eax, 1
0x1800107c6  lea     r8d, ds:1[rax*4]
0x1800107ce  jmp     short loc_1800107E3
0x1800107d0  mov     r8d, ebx
0x1800107d3  xor     r8d, 1
0x1800107d7  shl     r8d, 2
0x1800107db  jmp     short loc_1800107E3
0x1800107dd  mov     r8d, 0FFh
0x1800107e3  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x1800107e8  test    eax, eax
0x1800107ea  jz      short loc_180010830
0x1800107ec  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800107f3  test    rax, rax
0x1800107f6  jz      short loc_180010830
0x1800107f8  mov     rdx, cs:off_180027E60
0x1800107ff  lea     rcx, [rsp+58h+arg_10]
0x180010804  mov     [rsp+58h+var_20], 1
0x18001080d  mov     r9d, ebx
0x180010810  mov     [rsp+58h+var_28], 0
0x180010815  xor     r8d, r8d
0x180010818  mov     [rsp+58h+var_30], 0
0x180010821  mov     [rsp+58h+var_38], rcx
0x180010826  mov     ecx, 368EBDEh
0x18001082b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010830  add     rsp, 50h
0x180010834  pop     rbx
0x180010835  retn
```
