# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x180022210`
- end: `0x180022334`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `292`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64, int))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800226a8`

## callees

- `0x180022210`
- `0x18002233c`
- `0x180027010`

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
0x180022210  mov     [rsp+arg_0], rbx
0x180022215  mov     [rsp+arg_10], r8d
0x18002221a  push    rdi
0x18002221b  sub     rsp, 50h
0x18002221f  mov     ebx, edx
0x180022221  mov     r10d, r8d
0x180022224  and     ebx, 1
0x180022227  mov     rdi, rcx
0x18002222a  mov     r9d, r8d
0x18002222d  test    r8d, r8d
0x180022230  jz      loc_1800222DB
0x180022236  sub     r9d, 1
0x18002223a  jz      loc_1800222CE
0x180022240  sub     r9d, 1
0x180022244  jz      short loc_1800222BF
0x180022246  sub     r9d, 1
0x18002224a  jz      short loc_1800222B0
0x18002224c  sub     r9d, 1
0x180022250  jz      short loc_1800222A1
0x180022252  sub     r9d, 1
0x180022256  jz      short loc_180022292
0x180022258  cmp     r9d, 1
0x18002225c  jz      short loc_180022283
0x18002225e  sub     r10b, 64h ; 'd'
0x180022262  cmp     r10b, 31h ; '1'
0x180022266  ja      short loc_1800222DB
0x180022268  mov     eax, ebx
0x18002226a  neg     eax
0x18002226c  movzx   eax, r10b
0x180022270  sbb     r8d, r8d
0x180022273  and     r8d, 0FFFFFFCEh
0x180022277  add     r8d, 96h
0x18002227e  add     r8d, eax
0x180022281  jmp     short loc_1800222E1
0x180022283  mov     eax, ebx
0x180022285  xor     eax, 1
0x180022288  lea     r8d, ds:9[rax*2]
0x180022290  jmp     short loc_1800222E1
0x180022292  mov     eax, ebx
0x180022294  xor     eax, 1
0x180022297  lea     r8d, ds:8[rax*2]
0x18002229f  jmp     short loc_1800222E1
0x1800222a1  mov     eax, ebx
0x1800222a3  xor     eax, 1
0x1800222a6  lea     r8d, ds:3[rax*4]
0x1800222ae  jmp     short loc_1800222E1
0x1800222b0  mov     eax, ebx
0x1800222b2  xor     eax, 1
0x1800222b5  lea     r8d, ds:2[rax*4]
0x1800222bd  jmp     short loc_1800222E1
0x1800222bf  mov     eax, ebx
0x1800222c1  xor     eax, 1
0x1800222c4  lea     r8d, ds:1[rax*4]
0x1800222cc  jmp     short loc_1800222E1
0x1800222ce  mov     r8d, ebx
0x1800222d1  xor     r8d, 1
0x1800222d5  shl     r8d, 2
0x1800222d9  jmp     short loc_1800222E1
0x1800222db  mov     r8d, 0FFh
0x1800222e1  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x1800222e6  test    eax, eax
0x1800222e8  jz      short loc_180022329
0x1800222ea  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800222f1  test    rax, rax
0x1800222f4  jz      short loc_180022329
0x1800222f6  mov     rdx, [rdi+10h]
0x1800222fa  lea     rcx, [rsp+58h+arg_10]
0x1800222ff  mov     [rsp+58h+var_20], 1
0x180022308  mov     r9d, ebx
0x18002230b  mov     [rsp+58h+var_28], 0
0x180022310  xor     r8d, r8d
0x180022313  mov     [rsp+58h+var_30], 0
0x18002231c  mov     [rsp+58h+var_38], rcx
0x180022321  mov     ecx, [rdi+18h]
0x180022324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022329  mov     rbx, [rsp+58h+arg_0]
0x18002232e  add     rsp, 50h
0x180022332  pop     rdi
0x180022333  retn
```
