# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x180014898`
- end: `0x1800149bc`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180014e48`

## callees

- `0x180014898`
- `0x1800149c4`
- `0x18001a010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        unsigned __int64 a2,
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
0x180014898  mov     [rsp+arg_0], rbx
0x18001489d  mov     [rsp+arg_10], r8d
0x1800148a2  push    rdi
0x1800148a3  sub     rsp, 50h
0x1800148a7  mov     ebx, edx
0x1800148a9  mov     r10d, r8d
0x1800148ac  and     ebx, 1
0x1800148af  mov     rdi, rcx
0x1800148b2  mov     r9d, r8d
0x1800148b5  test    r8d, r8d
0x1800148b8  jz      loc_180014963
0x1800148be  sub     r9d, 1
0x1800148c2  jz      loc_180014956
0x1800148c8  sub     r9d, 1
0x1800148cc  jz      short loc_180014947
0x1800148ce  sub     r9d, 1
0x1800148d2  jz      short loc_180014938
0x1800148d4  sub     r9d, 1
0x1800148d8  jz      short loc_180014929
0x1800148da  sub     r9d, 1
0x1800148de  jz      short loc_18001491A
0x1800148e0  cmp     r9d, 1
0x1800148e4  jz      short loc_18001490B
0x1800148e6  sub     r10b, 64h ; 'd'
0x1800148ea  cmp     r10b, 31h ; '1'
0x1800148ee  ja      short loc_180014963
0x1800148f0  mov     eax, ebx
0x1800148f2  neg     eax
0x1800148f4  movzx   eax, r10b
0x1800148f8  sbb     r8d, r8d
0x1800148fb  and     r8d, 0FFFFFFCEh
0x1800148ff  add     r8d, 96h
0x180014906  add     r8d, eax
0x180014909  jmp     short loc_180014969
0x18001490b  mov     eax, ebx
0x18001490d  xor     eax, 1
0x180014910  lea     r8d, ds:9[rax*2]
0x180014918  jmp     short loc_180014969
0x18001491a  mov     eax, ebx
0x18001491c  xor     eax, 1
0x18001491f  lea     r8d, ds:8[rax*2]
0x180014927  jmp     short loc_180014969
0x180014929  mov     eax, ebx
0x18001492b  xor     eax, 1
0x18001492e  lea     r8d, ds:3[rax*4]
0x180014936  jmp     short loc_180014969
0x180014938  mov     eax, ebx
0x18001493a  xor     eax, 1
0x18001493d  lea     r8d, ds:2[rax*4]
0x180014945  jmp     short loc_180014969
0x180014947  mov     eax, ebx
0x180014949  xor     eax, 1
0x18001494c  lea     r8d, ds:1[rax*4]
0x180014954  jmp     short loc_180014969
0x180014956  mov     r8d, ebx
0x180014959  xor     r8d, 1
0x18001495d  shl     r8d, 2
0x180014961  jmp     short loc_180014969
0x180014963  mov     r8d, 0FFh
0x180014969  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x18001496e  test    eax, eax
0x180014970  jz      short loc_1800149B1
0x180014972  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180014979  test    rax, rax
0x18001497c  jz      short loc_1800149B1
0x18001497e  mov     rdx, [rdi+10h]
0x180014982  lea     rcx, [rsp+58h+arg_10]
0x180014987  mov     [rsp+58h+var_20], 1
0x180014990  mov     r9d, ebx
0x180014993  mov     [rsp+58h+var_28], 0
0x180014998  xor     r8d, r8d
0x18001499b  mov     [rsp+58h+var_30], 0
0x1800149a4  mov     [rsp+58h+var_38], rcx
0x1800149a9  mov     ecx, [rdi+18h]
0x1800149ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149b1  mov     rbx, [rsp+58h+arg_0]
0x1800149b6  add     rsp, 50h
0x1800149ba  pop     rdi
0x1800149bb  retn
```
