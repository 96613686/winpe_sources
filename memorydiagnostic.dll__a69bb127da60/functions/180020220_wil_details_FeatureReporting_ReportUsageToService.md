# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x180020220`
- end: `0x180020336`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `278`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64, unsigned int))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002072c`

## callees

- `0x180020220`
- `0x18002033c`
- `0x180023010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        __int64 a2,
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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(60288851, &Feature_ShadowAdmin_logged_traits, 0, v3, &v7, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180020220  mov     [rsp+arg_10], r8d
0x180020225  push    rbx
0x180020226  sub     rsp, 50h
0x18002022a  mov     ebx, edx
0x18002022c  mov     r9d, r8d
0x18002022f  and     ebx, 1
0x180020232  mov     ecx, r8d
0x180020235  test    r8d, r8d
0x180020238  jz      loc_1800202DD
0x18002023e  sub     ecx, 1
0x180020241  jz      loc_1800202D0
0x180020247  sub     ecx, 1
0x18002024a  jz      short loc_1800202C1
0x18002024c  sub     ecx, 1
0x18002024f  jz      short loc_1800202B2
0x180020251  sub     ecx, 1
0x180020254  jz      short loc_1800202A3
0x180020256  sub     ecx, 1
0x180020259  jz      short loc_180020294
0x18002025b  cmp     ecx, 1
0x18002025e  jz      short loc_180020285
0x180020260  sub     r9b, 64h ; 'd'
0x180020264  cmp     r9b, 31h ; '1'
0x180020268  ja      short loc_1800202DD
0x18002026a  mov     eax, ebx
0x18002026c  neg     eax
0x18002026e  movzx   eax, r9b
0x180020272  sbb     r8d, r8d
0x180020275  and     r8d, 0FFFFFFCEh
0x180020279  add     r8d, 96h
0x180020280  add     r8d, eax
0x180020283  jmp     short loc_1800202E3
0x180020285  mov     eax, ebx
0x180020287  xor     eax, 1
0x18002028a  lea     r8d, ds:9[rax*2]
0x180020292  jmp     short loc_1800202E3
0x180020294  mov     eax, ebx
0x180020296  xor     eax, 1
0x180020299  lea     r8d, ds:8[rax*2]
0x1800202a1  jmp     short loc_1800202E3
0x1800202a3  mov     eax, ebx
0x1800202a5  xor     eax, 1
0x1800202a8  lea     r8d, ds:3[rax*4]
0x1800202b0  jmp     short loc_1800202E3
0x1800202b2  mov     eax, ebx
0x1800202b4  xor     eax, 1
0x1800202b7  lea     r8d, ds:2[rax*4]
0x1800202bf  jmp     short loc_1800202E3
0x1800202c1  mov     eax, ebx
0x1800202c3  xor     eax, 1
0x1800202c6  lea     r8d, ds:1[rax*4]
0x1800202ce  jmp     short loc_1800202E3
0x1800202d0  mov     r8d, ebx
0x1800202d3  xor     r8d, 1
0x1800202d7  shl     r8d, 2
0x1800202db  jmp     short loc_1800202E3
0x1800202dd  mov     r8d, 0FFh
0x1800202e3  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x1800202e8  test    eax, eax
0x1800202ea  jz      short loc_180020330
0x1800202ec  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800202f3  test    rax, rax
0x1800202f6  jz      short loc_180020330
0x1800202f8  mov     rdx, cs:off_18002D190
0x1800202ff  lea     rcx, [rsp+58h+arg_10]
0x180020304  mov     [rsp+58h+var_20], 1
0x18002030d  mov     r9d, ebx
0x180020310  mov     [rsp+58h+var_28], 0
0x180020315  xor     r8d, r8d
0x180020318  mov     [rsp+58h+var_30], 0
0x180020321  mov     [rsp+58h+var_38], rcx
0x180020326  mov     ecx, 397EF53h
0x18002032b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020330  add     rsp, 50h
0x180020334  pop     rbx
0x180020335  retn
```
