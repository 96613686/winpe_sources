# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140002600`
- end: `0x140002725`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `293`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64, int))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140002ac4`

## callees

- `0x140002600`
- `0x14000272c`
- `0x1400041f0`

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
0x140002600  mov     [rsp+arg_0], rbx
0x140002605  mov     [rsp+arg_10], r8d
0x14000260a  push    rdi
0x14000260b  sub     rsp, 50h
0x14000260f  mov     ebx, edx
0x140002611  mov     r10d, r8d
0x140002614  and     ebx, 1
0x140002617  mov     rdi, rcx
0x14000261a  mov     r9d, r8d
0x14000261d  test    r8d, r8d
0x140002620  jz      loc_1400026CB
0x140002626  sub     r9d, 1
0x14000262a  jz      loc_1400026BE
0x140002630  sub     r9d, 1
0x140002634  jz      short loc_1400026AF
0x140002636  sub     r9d, 1
0x14000263a  jz      short loc_1400026A0
0x14000263c  sub     r9d, 1
0x140002640  jz      short loc_140002691
0x140002642  sub     r9d, 1
0x140002646  jz      short loc_140002682
0x140002648  cmp     r9d, 1
0x14000264c  jz      short loc_140002673
0x14000264e  sub     r10b, 64h ; 'd'
0x140002652  cmp     r10b, 31h ; '1'
0x140002656  ja      short loc_1400026CB
0x140002658  mov     eax, ebx
0x14000265a  neg     eax
0x14000265c  movzx   eax, r10b
0x140002660  sbb     r8d, r8d
0x140002663  and     r8d, 0FFFFFFCEh
0x140002667  add     r8d, 96h
0x14000266e  add     r8d, eax
0x140002671  jmp     short loc_1400026D1
0x140002673  mov     eax, ebx
0x140002675  xor     eax, 1
0x140002678  lea     r8d, ds:9[rax*2]
0x140002680  jmp     short loc_1400026D1
0x140002682  mov     eax, ebx
0x140002684  xor     eax, 1
0x140002687  lea     r8d, ds:8[rax*2]
0x14000268f  jmp     short loc_1400026D1
0x140002691  mov     eax, ebx
0x140002693  xor     eax, 1
0x140002696  lea     r8d, ds:3[rax*4]
0x14000269e  jmp     short loc_1400026D1
0x1400026a0  mov     eax, ebx
0x1400026a2  xor     eax, 1
0x1400026a5  lea     r8d, ds:2[rax*4]
0x1400026ad  jmp     short loc_1400026D1
0x1400026af  mov     eax, ebx
0x1400026b1  xor     eax, 1
0x1400026b4  lea     r8d, ds:1[rax*4]
0x1400026bc  jmp     short loc_1400026D1
0x1400026be  mov     r8d, ebx
0x1400026c1  xor     r8d, 1
0x1400026c5  shl     r8d, 2
0x1400026c9  jmp     short loc_1400026D1
0x1400026cb  mov     r8d, 0FFh
0x1400026d1  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x1400026d6  test    eax, eax
0x1400026d8  jz      short loc_140002719
0x1400026da  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1400026e1  test    rax, rax
0x1400026e4  jz      short loc_140002719
0x1400026e6  mov     rdx, [rdi+10h]
0x1400026ea  lea     rcx, [rsp+58h+arg_10]
0x1400026ef  mov     [rsp+58h+var_20], 1
0x1400026f8  mov     r9d, ebx
0x1400026fb  mov     [rsp+58h+var_28], 0
0x140002700  xor     r8d, r8d
0x140002703  mov     [rsp+58h+var_30], 0
0x14000270c  mov     [rsp+58h+var_38], rcx
0x140002711  mov     ecx, [rdi+18h]
0x140002714  call    _guard_dispatch_icall
0x140002719  mov     rbx, [rsp+58h+arg_0]
0x14000271e  add     rsp, 50h
0x140002722  pop     rdi
0x140002723  retn
```
