# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x180007090`
- end: `0x1800071b4`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `292`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64, int))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800026e0`

## callees

- `0x180007090`
- `0x1800071bc`
- `0x180009010`

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
0x180007090  mov     [rsp+arg_0], rbx
0x180007095  mov     [rsp+arg_10], r8d
0x18000709a  push    rdi
0x18000709b  sub     rsp, 50h
0x18000709f  mov     ebx, edx
0x1800070a1  mov     r10d, r8d
0x1800070a4  and     ebx, 1
0x1800070a7  mov     rdi, rcx
0x1800070aa  mov     r9d, r8d
0x1800070ad  test    r8d, r8d
0x1800070b0  jz      loc_18000715B
0x1800070b6  sub     r9d, 1
0x1800070ba  jz      loc_18000714E
0x1800070c0  sub     r9d, 1
0x1800070c4  jz      short loc_18000713F
0x1800070c6  sub     r9d, 1
0x1800070ca  jz      short loc_180007130
0x1800070cc  sub     r9d, 1
0x1800070d0  jz      short loc_180007121
0x1800070d2  sub     r9d, 1
0x1800070d6  jz      short loc_180007112
0x1800070d8  cmp     r9d, 1
0x1800070dc  jz      short loc_180007103
0x1800070de  sub     r10b, 64h ; 'd'
0x1800070e2  cmp     r10b, 31h ; '1'
0x1800070e6  ja      short loc_18000715B
0x1800070e8  mov     eax, ebx
0x1800070ea  neg     eax
0x1800070ec  movzx   eax, r10b
0x1800070f0  sbb     r8d, r8d
0x1800070f3  and     r8d, 0FFFFFFCEh
0x1800070f7  add     r8d, 96h
0x1800070fe  add     r8d, eax
0x180007101  jmp     short loc_180007161
0x180007103  mov     eax, ebx
0x180007105  xor     eax, 1
0x180007108  lea     r8d, ds:9[rax*2]
0x180007110  jmp     short loc_180007161
0x180007112  mov     eax, ebx
0x180007114  xor     eax, 1
0x180007117  lea     r8d, ds:8[rax*2]
0x18000711f  jmp     short loc_180007161
0x180007121  mov     eax, ebx
0x180007123  xor     eax, 1
0x180007126  lea     r8d, ds:3[rax*4]
0x18000712e  jmp     short loc_180007161
0x180007130  mov     eax, ebx
0x180007132  xor     eax, 1
0x180007135  lea     r8d, ds:2[rax*4]
0x18000713d  jmp     short loc_180007161
0x18000713f  mov     eax, ebx
0x180007141  xor     eax, 1
0x180007144  lea     r8d, ds:1[rax*4]
0x18000714c  jmp     short loc_180007161
0x18000714e  mov     r8d, ebx
0x180007151  xor     r8d, 1
0x180007155  shl     r8d, 2
0x180007159  jmp     short loc_180007161
0x18000715b  mov     r8d, 0FFh
0x180007161  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x180007166  test    eax, eax
0x180007168  jz      short loc_1800071A9
0x18000716a  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180007171  test    rax, rax
0x180007174  jz      short loc_1800071A9
0x180007176  mov     rdx, [rdi+10h]
0x18000717a  lea     rcx, [rsp+58h+arg_10]
0x18000717f  mov     [rsp+58h+var_20], 1
0x180007188  mov     r9d, ebx
0x18000718b  mov     [rsp+58h+var_28], 0
0x180007190  xor     r8d, r8d
0x180007193  mov     [rsp+58h+var_30], 0
0x18000719c  mov     [rsp+58h+var_38], rcx
0x1800071a1  mov     ecx, [rdi+18h]
0x1800071a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071a9  mov     rbx, [rsp+58h+arg_0]
0x1800071ae  add     rsp, 50h
0x1800071b2  pop     rdi
0x1800071b3  retn
```
