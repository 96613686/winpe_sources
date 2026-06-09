# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x18000891c`
- end: `0x180008a40`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180005dc4`

## callees

- `0x18000891c`
- `0x180008a48`
- `0x18000a010`

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
0x18000891c  mov     [rsp+arg_0], rbx
0x180008921  mov     [rsp+arg_10], r8d
0x180008926  push    rdi
0x180008927  sub     rsp, 50h
0x18000892b  mov     ebx, edx
0x18000892d  mov     r10d, r8d
0x180008930  and     ebx, 1
0x180008933  mov     rdi, rcx
0x180008936  mov     r9d, r8d
0x180008939  test    r8d, r8d
0x18000893c  jz      loc_1800089E7
0x180008942  sub     r9d, 1
0x180008946  jz      loc_1800089DA
0x18000894c  sub     r9d, 1
0x180008950  jz      short loc_1800089CB
0x180008952  sub     r9d, 1
0x180008956  jz      short loc_1800089BC
0x180008958  sub     r9d, 1
0x18000895c  jz      short loc_1800089AD
0x18000895e  sub     r9d, 1
0x180008962  jz      short loc_18000899E
0x180008964  cmp     r9d, 1
0x180008968  jz      short loc_18000898F
0x18000896a  sub     r10b, 64h ; 'd'
0x18000896e  cmp     r10b, 31h ; '1'
0x180008972  ja      short loc_1800089E7
0x180008974  mov     eax, ebx
0x180008976  neg     eax
0x180008978  movzx   eax, r10b
0x18000897c  sbb     r8d, r8d
0x18000897f  and     r8d, 0FFFFFFCEh
0x180008983  add     r8d, 96h
0x18000898a  add     r8d, eax
0x18000898d  jmp     short loc_1800089ED
0x18000898f  mov     eax, ebx
0x180008991  xor     eax, 1
0x180008994  lea     r8d, ds:9[rax*2]
0x18000899c  jmp     short loc_1800089ED
0x18000899e  mov     eax, ebx
0x1800089a0  xor     eax, 1
0x1800089a3  lea     r8d, ds:8[rax*2]
0x1800089ab  jmp     short loc_1800089ED
0x1800089ad  mov     eax, ebx
0x1800089af  xor     eax, 1
0x1800089b2  lea     r8d, ds:3[rax*4]
0x1800089ba  jmp     short loc_1800089ED
0x1800089bc  mov     eax, ebx
0x1800089be  xor     eax, 1
0x1800089c1  lea     r8d, ds:2[rax*4]
0x1800089c9  jmp     short loc_1800089ED
0x1800089cb  mov     eax, ebx
0x1800089cd  xor     eax, 1
0x1800089d0  lea     r8d, ds:1[rax*4]
0x1800089d8  jmp     short loc_1800089ED
0x1800089da  mov     r8d, ebx
0x1800089dd  xor     r8d, 1
0x1800089e1  shl     r8d, 2
0x1800089e5  jmp     short loc_1800089ED
0x1800089e7  mov     r8d, 0FFh
0x1800089ed  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x1800089f2  test    eax, eax
0x1800089f4  jz      short loc_180008A35
0x1800089f6  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800089fd  test    rax, rax
0x180008a00  jz      short loc_180008A35
0x180008a02  mov     rdx, [rdi+10h]
0x180008a06  lea     rcx, [rsp+58h+arg_10]
0x180008a0b  mov     [rsp+58h+var_20], 1
0x180008a14  mov     r9d, ebx
0x180008a17  mov     [rsp+58h+var_28], 0
0x180008a1c  xor     r8d, r8d
0x180008a1f  mov     [rsp+58h+var_30], 0
0x180008a28  mov     [rsp+58h+var_38], rcx
0x180008a2d  mov     ecx, [rdi+18h]
0x180008a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a35  mov     rbx, [rsp+58h+arg_0]
0x180008a3a  add     rsp, 50h
0x180008a3e  pop     rdi
0x180008a3f  retn
```
