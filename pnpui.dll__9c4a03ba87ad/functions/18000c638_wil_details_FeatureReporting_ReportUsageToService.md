# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x18000c638`
- end: `0x18000c74e`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000cae4`

## callees

- `0x18000c638`
- `0x18000c754`
- `0x18000e010`

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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(60288851, &Feature_ShadowAdmin_logged_traits, 0, v3, &v7, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x18000c638  mov     [rsp+arg_10], r8d
0x18000c63d  push    rbx
0x18000c63e  sub     rsp, 50h
0x18000c642  mov     ebx, edx
0x18000c644  mov     r9d, r8d
0x18000c647  and     ebx, 1
0x18000c64a  mov     ecx, r8d
0x18000c64d  test    r8d, r8d
0x18000c650  jz      loc_18000C6F5
0x18000c656  sub     ecx, 1
0x18000c659  jz      loc_18000C6E8
0x18000c65f  sub     ecx, 1
0x18000c662  jz      short loc_18000C6D9
0x18000c664  sub     ecx, 1
0x18000c667  jz      short loc_18000C6CA
0x18000c669  sub     ecx, 1
0x18000c66c  jz      short loc_18000C6BB
0x18000c66e  sub     ecx, 1
0x18000c671  jz      short loc_18000C6AC
0x18000c673  cmp     ecx, 1
0x18000c676  jz      short loc_18000C69D
0x18000c678  sub     r9b, 64h ; 'd'
0x18000c67c  cmp     r9b, 31h ; '1'
0x18000c680  ja      short loc_18000C6F5
0x18000c682  mov     eax, ebx
0x18000c684  neg     eax
0x18000c686  movzx   eax, r9b
0x18000c68a  sbb     r8d, r8d
0x18000c68d  and     r8d, 0FFFFFFCEh
0x18000c691  add     r8d, 96h
0x18000c698  add     r8d, eax
0x18000c69b  jmp     short loc_18000C6FB
0x18000c69d  mov     eax, ebx
0x18000c69f  xor     eax, 1
0x18000c6a2  lea     r8d, ds:9[rax*2]
0x18000c6aa  jmp     short loc_18000C6FB
0x18000c6ac  mov     eax, ebx
0x18000c6ae  xor     eax, 1
0x18000c6b1  lea     r8d, ds:8[rax*2]
0x18000c6b9  jmp     short loc_18000C6FB
0x18000c6bb  mov     eax, ebx
0x18000c6bd  xor     eax, 1
0x18000c6c0  lea     r8d, ds:3[rax*4]
0x18000c6c8  jmp     short loc_18000C6FB
0x18000c6ca  mov     eax, ebx
0x18000c6cc  xor     eax, 1
0x18000c6cf  lea     r8d, ds:2[rax*4]
0x18000c6d7  jmp     short loc_18000C6FB
0x18000c6d9  mov     eax, ebx
0x18000c6db  xor     eax, 1
0x18000c6de  lea     r8d, ds:1[rax*4]
0x18000c6e6  jmp     short loc_18000C6FB
0x18000c6e8  mov     r8d, ebx
0x18000c6eb  xor     r8d, 1
0x18000c6ef  shl     r8d, 2
0x18000c6f3  jmp     short loc_18000C6FB
0x18000c6f5  mov     r8d, 0FFh
0x18000c6fb  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x18000c700  test    eax, eax
0x18000c702  jz      short loc_18000C748
0x18000c704  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000c70b  test    rax, rax
0x18000c70e  jz      short loc_18000C748
0x18000c710  mov     rdx, cs:off_180011B10
0x18000c717  lea     rcx, [rsp+58h+arg_10]
0x18000c71c  mov     [rsp+58h+var_20], 1
0x18000c725  mov     r9d, ebx
0x18000c728  mov     [rsp+58h+var_28], 0
0x18000c72d  xor     r8d, r8d
0x18000c730  mov     [rsp+58h+var_30], 0
0x18000c739  mov     [rsp+58h+var_38], rcx
0x18000c73e  mov     ecx, 397EF53h
0x18000c743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c748  add     rsp, 50h
0x18000c74c  pop     rbx
0x18000c74d  retn
```
