# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x180016878`
- end: `0x18001699c`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `292`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180012e00`
- `0x180015e8c`
- `0x1800164ac`
- `0x180019980`
- `0x18001c3a0`

## callees

- `0x180016878`
- `0x1800199e8`
- `0x180020010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        __int64 a2,
        int a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v3; // ebx
  __int64 v5; // r8
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  int v7; // [rsp+70h] [rbp+18h] BYREF

  v7 = a3;
  v3 = a2 & 1;
  if ( a3 )
  {
    switch ( a3 )
    {
      case 1:
        v5 = 4 * (unsigned int)!(a2 & 1);
        goto LABEL_17;
      case 2:
        v5 = 4 * (unsigned int)!(a2 & 1) + 1;
        goto LABEL_17;
      case 3:
        v5 = 4 * (unsigned int)!(a2 & 1) + 2;
        goto LABEL_17;
      case 4:
        v5 = 4 * (unsigned int)!(a2 & 1) + 3;
        goto LABEL_17;
      case 5:
        v5 = 2 * (unsigned int)!(a2 & 1) + 8;
        goto LABEL_17;
      case 6:
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
                                                                                                     a1,
                                                                                                     a2,
                                                                                                     v5);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(*(unsigned int *)(a1 + 24), *(_QWORD *)(a1 + 16), 0, v3, &v7, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180016878  mov     [rsp+arg_0], rbx
0x18001687d  mov     [rsp+arg_10], r8d
0x180016882  push    rdi
0x180016883  sub     rsp, 50h
0x180016887  mov     ebx, edx
0x180016889  mov     r10d, r8d
0x18001688c  and     ebx, 1
0x18001688f  mov     rdi, rcx
0x180016892  mov     r9d, r8d
0x180016895  test    r8d, r8d
0x180016898  jz      loc_180016943
0x18001689e  sub     r9d, 1
0x1800168a2  jz      loc_180016936
0x1800168a8  sub     r9d, 1
0x1800168ac  jz      short loc_180016927
0x1800168ae  sub     r9d, 1
0x1800168b2  jz      short loc_180016918
0x1800168b4  sub     r9d, 1
0x1800168b8  jz      short loc_180016909
0x1800168ba  sub     r9d, 1
0x1800168be  jz      short loc_1800168FA
0x1800168c0  cmp     r9d, 1
0x1800168c4  jz      short loc_1800168EB
0x1800168c6  sub     r10b, 64h ; 'd'
0x1800168ca  cmp     r10b, 31h ; '1'
0x1800168ce  ja      short loc_180016943
0x1800168d0  mov     eax, ebx
0x1800168d2  neg     eax
0x1800168d4  movzx   eax, r10b
0x1800168d8  sbb     r8d, r8d
0x1800168db  and     r8d, 0FFFFFFCEh
0x1800168df  add     r8d, 96h
0x1800168e6  add     r8d, eax
0x1800168e9  jmp     short loc_180016949
0x1800168eb  mov     eax, ebx
0x1800168ed  xor     eax, 1
0x1800168f0  lea     r8d, ds:9[rax*2]
0x1800168f8  jmp     short loc_180016949
0x1800168fa  mov     eax, ebx
0x1800168fc  xor     eax, 1
0x1800168ff  lea     r8d, ds:8[rax*2]
0x180016907  jmp     short loc_180016949
0x180016909  mov     eax, ebx
0x18001690b  xor     eax, 1
0x18001690e  lea     r8d, ds:3[rax*4]
0x180016916  jmp     short loc_180016949
0x180016918  mov     eax, ebx
0x18001691a  xor     eax, 1
0x18001691d  lea     r8d, ds:2[rax*4]
0x180016925  jmp     short loc_180016949
0x180016927  mov     eax, ebx
0x180016929  xor     eax, 1
0x18001692c  lea     r8d, ds:1[rax*4]
0x180016934  jmp     short loc_180016949
0x180016936  mov     r8d, ebx
0x180016939  xor     r8d, 1
0x18001693d  shl     r8d, 2
0x180016941  jmp     short loc_180016949
0x180016943  mov     r8d, 0FFh
0x180016949  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x18001694e  test    eax, eax
0x180016950  jz      short loc_180016991
0x180016952  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180016959  test    rax, rax
0x18001695c  jz      short loc_180016991
0x18001695e  mov     rdx, [rdi+10h]
0x180016962  lea     rcx, [rsp+58h+arg_10]
0x180016967  mov     [rsp+58h+var_20], 1
0x180016970  mov     r9d, ebx
0x180016973  mov     [rsp+58h+var_28], 0
0x180016978  xor     r8d, r8d
0x18001697b  mov     [rsp+58h+var_30], 0
0x180016984  mov     [rsp+58h+var_38], rcx
0x180016989  mov     ecx, [rdi+18h]
0x18001698c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016991  mov     rbx, [rsp+58h+arg_0]
0x180016996  add     rsp, 50h
0x18001699a  pop     rdi
0x18001699b  retn
```
