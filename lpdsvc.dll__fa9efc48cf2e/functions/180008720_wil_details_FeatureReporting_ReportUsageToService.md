# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x180008720`
- end: `0x180008836`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `278`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64, unsigned int))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180008cb4`

## callees

- `0x180008720`
- `0x18000883c`
- `0x18000e010`

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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(57118291, &Feature_LpdDeprecationAndRemoval_logged_traits, 0, v3, &v7, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180008720  mov     [rsp+arg_10], r8d
0x180008725  push    rbx
0x180008726  sub     rsp, 50h
0x18000872a  mov     ebx, edx
0x18000872c  mov     r9d, r8d
0x18000872f  and     ebx, 1
0x180008732  mov     ecx, r8d
0x180008735  test    r8d, r8d
0x180008738  jz      loc_1800087DD
0x18000873e  sub     ecx, 1
0x180008741  jz      loc_1800087D0
0x180008747  sub     ecx, 1
0x18000874a  jz      short loc_1800087C1
0x18000874c  sub     ecx, 1
0x18000874f  jz      short loc_1800087B2
0x180008751  sub     ecx, 1
0x180008754  jz      short loc_1800087A3
0x180008756  sub     ecx, 1
0x180008759  jz      short loc_180008794
0x18000875b  cmp     ecx, 1
0x18000875e  jz      short loc_180008785
0x180008760  sub     r9b, 64h ; 'd'
0x180008764  cmp     r9b, 31h ; '1'
0x180008768  ja      short loc_1800087DD
0x18000876a  mov     eax, ebx
0x18000876c  neg     eax
0x18000876e  movzx   eax, r9b
0x180008772  sbb     r8d, r8d
0x180008775  and     r8d, 0FFFFFFCEh
0x180008779  add     r8d, 96h
0x180008780  add     r8d, eax
0x180008783  jmp     short loc_1800087E3
0x180008785  mov     eax, ebx
0x180008787  xor     eax, 1
0x18000878a  lea     r8d, ds:9[rax*2]
0x180008792  jmp     short loc_1800087E3
0x180008794  mov     eax, ebx
0x180008796  xor     eax, 1
0x180008799  lea     r8d, ds:8[rax*2]
0x1800087a1  jmp     short loc_1800087E3
0x1800087a3  mov     eax, ebx
0x1800087a5  xor     eax, 1
0x1800087a8  lea     r8d, ds:3[rax*4]
0x1800087b0  jmp     short loc_1800087E3
0x1800087b2  mov     eax, ebx
0x1800087b4  xor     eax, 1
0x1800087b7  lea     r8d, ds:2[rax*4]
0x1800087bf  jmp     short loc_1800087E3
0x1800087c1  mov     eax, ebx
0x1800087c3  xor     eax, 1
0x1800087c6  lea     r8d, ds:1[rax*4]
0x1800087ce  jmp     short loc_1800087E3
0x1800087d0  mov     r8d, ebx
0x1800087d3  xor     r8d, 1
0x1800087d7  shl     r8d, 2
0x1800087db  jmp     short loc_1800087E3
0x1800087dd  mov     r8d, 0FFh
0x1800087e3  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x1800087e8  test    eax, eax
0x1800087ea  jz      short loc_180008830
0x1800087ec  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800087f3  test    rax, rax
0x1800087f6  jz      short loc_180008830
0x1800087f8  mov     rdx, cs:off_180010EE8
0x1800087ff  lea     rcx, [rsp+58h+arg_10]
0x180008804  mov     [rsp+58h+var_20], 1
0x18000880d  mov     r9d, ebx
0x180008810  mov     [rsp+58h+var_28], 0
0x180008815  xor     r8d, r8d
0x180008818  mov     [rsp+58h+var_30], 0
0x180008821  mov     [rsp+58h+var_38], rcx
0x180008826  mov     ecx, 3678E53h
0x18000882b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008830  add     rsp, 50h
0x180008834  pop     rbx
0x180008835  retn
```
