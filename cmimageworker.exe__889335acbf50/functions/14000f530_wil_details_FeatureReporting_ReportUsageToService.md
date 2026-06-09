# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x14000f530`
- end: `0x14000f647`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x14000f9f4`

## callees

- `0x14000f530`
- `0x14000f650`
- `0x140034010`

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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(50974410, &Feature_WcRemoveFileOwnershipTOCTOU_logged_traits, 0, v3, &v7, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x14000f530  mov     [rsp+arg_10], r8d
0x14000f535  push    rbx
0x14000f536  sub     rsp, 50h
0x14000f53a  mov     ebx, edx
0x14000f53c  mov     r9d, r8d
0x14000f53f  and     ebx, 1
0x14000f542  mov     ecx, r8d
0x14000f545  test    r8d, r8d
0x14000f548  jz      loc_14000F5ED
0x14000f54e  sub     ecx, 1
0x14000f551  jz      loc_14000F5E0
0x14000f557  sub     ecx, 1
0x14000f55a  jz      short loc_14000F5D1
0x14000f55c  sub     ecx, 1
0x14000f55f  jz      short loc_14000F5C2
0x14000f561  sub     ecx, 1
0x14000f564  jz      short loc_14000F5B3
0x14000f566  sub     ecx, 1
0x14000f569  jz      short loc_14000F5A4
0x14000f56b  cmp     ecx, 1
0x14000f56e  jz      short loc_14000F595
0x14000f570  sub     r9b, 64h ; 'd'
0x14000f574  cmp     r9b, 31h ; '1'
0x14000f578  ja      short loc_14000F5ED
0x14000f57a  mov     eax, ebx
0x14000f57c  neg     eax
0x14000f57e  movzx   eax, r9b
0x14000f582  sbb     r8d, r8d
0x14000f585  and     r8d, 0FFFFFFCEh
0x14000f589  add     r8d, 96h
0x14000f590  add     r8d, eax
0x14000f593  jmp     short loc_14000F5F3
0x14000f595  mov     eax, ebx
0x14000f597  xor     eax, 1
0x14000f59a  lea     r8d, ds:9[rax*2]
0x14000f5a2  jmp     short loc_14000F5F3
0x14000f5a4  mov     eax, ebx
0x14000f5a6  xor     eax, 1
0x14000f5a9  lea     r8d, ds:8[rax*2]
0x14000f5b1  jmp     short loc_14000F5F3
0x14000f5b3  mov     eax, ebx
0x14000f5b5  xor     eax, 1
0x14000f5b8  lea     r8d, ds:3[rax*4]
0x14000f5c0  jmp     short loc_14000F5F3
0x14000f5c2  mov     eax, ebx
0x14000f5c4  xor     eax, 1
0x14000f5c7  lea     r8d, ds:2[rax*4]
0x14000f5cf  jmp     short loc_14000F5F3
0x14000f5d1  mov     eax, ebx
0x14000f5d3  xor     eax, 1
0x14000f5d6  lea     r8d, ds:1[rax*4]
0x14000f5de  jmp     short loc_14000F5F3
0x14000f5e0  mov     r8d, ebx
0x14000f5e3  xor     r8d, 1
0x14000f5e7  shl     r8d, 2
0x14000f5eb  jmp     short loc_14000F5F3
0x14000f5ed  mov     r8d, 0FFh
0x14000f5f3  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x14000f5f8  test    eax, eax
0x14000f5fa  jz      short loc_14000F640
0x14000f5fc  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000f603  test    rax, rax
0x14000f606  jz      short loc_14000F640
0x14000f608  mov     rdx, cs:off_14003BBD8
0x14000f60f  lea     rcx, [rsp+58h+arg_10]
0x14000f614  mov     [rsp+58h+var_20], 1
0x14000f61d  mov     r9d, ebx
0x14000f620  mov     [rsp+58h+var_28], 0
0x14000f625  xor     r8d, r8d
0x14000f628  mov     [rsp+58h+var_30], 0
0x14000f631  mov     [rsp+58h+var_38], rcx
0x14000f636  mov     ecx, 309CECAh
0x14000f63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f640  add     rsp, 50h
0x14000f644  pop     rbx
0x14000f645  retn
```
