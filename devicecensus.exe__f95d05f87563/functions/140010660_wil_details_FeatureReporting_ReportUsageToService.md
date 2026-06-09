# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140010660`
- end: `0x140010784`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `292`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64, int))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140010c10`

## callees

- `0x140010660`
- `0x14001078c`
- `0x140012010`

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
0x140010660  mov     [rsp+arg_0], rbx
0x140010665  mov     [rsp+arg_10], r8d
0x14001066a  push    rdi
0x14001066b  sub     rsp, 50h
0x14001066f  mov     ebx, edx
0x140010671  mov     r10d, r8d
0x140010674  and     ebx, 1
0x140010677  mov     rdi, rcx
0x14001067a  mov     r9d, r8d
0x14001067d  test    r8d, r8d
0x140010680  jz      loc_14001072B
0x140010686  sub     r9d, 1
0x14001068a  jz      loc_14001071E
0x140010690  sub     r9d, 1
0x140010694  jz      short loc_14001070F
0x140010696  sub     r9d, 1
0x14001069a  jz      short loc_140010700
0x14001069c  sub     r9d, 1
0x1400106a0  jz      short loc_1400106F1
0x1400106a2  sub     r9d, 1
0x1400106a6  jz      short loc_1400106E2
0x1400106a8  cmp     r9d, 1
0x1400106ac  jz      short loc_1400106D3
0x1400106ae  sub     r10b, 64h ; 'd'
0x1400106b2  cmp     r10b, 31h ; '1'
0x1400106b6  ja      short loc_14001072B
0x1400106b8  mov     eax, ebx
0x1400106ba  neg     eax
0x1400106bc  movzx   eax, r10b
0x1400106c0  sbb     r8d, r8d
0x1400106c3  and     r8d, 0FFFFFFCEh
0x1400106c7  add     r8d, 96h
0x1400106ce  add     r8d, eax
0x1400106d1  jmp     short loc_140010731
0x1400106d3  mov     eax, ebx
0x1400106d5  xor     eax, 1
0x1400106d8  lea     r8d, ds:9[rax*2]
0x1400106e0  jmp     short loc_140010731
0x1400106e2  mov     eax, ebx
0x1400106e4  xor     eax, 1
0x1400106e7  lea     r8d, ds:8[rax*2]
0x1400106ef  jmp     short loc_140010731
0x1400106f1  mov     eax, ebx
0x1400106f3  xor     eax, 1
0x1400106f6  lea     r8d, ds:3[rax*4]
0x1400106fe  jmp     short loc_140010731
0x140010700  mov     eax, ebx
0x140010702  xor     eax, 1
0x140010705  lea     r8d, ds:2[rax*4]
0x14001070d  jmp     short loc_140010731
0x14001070f  mov     eax, ebx
0x140010711  xor     eax, 1
0x140010714  lea     r8d, ds:1[rax*4]
0x14001071c  jmp     short loc_140010731
0x14001071e  mov     r8d, ebx
0x140010721  xor     r8d, 1
0x140010725  shl     r8d, 2
0x140010729  jmp     short loc_140010731
0x14001072b  mov     r8d, 0FFh
0x140010731  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x140010736  test    eax, eax
0x140010738  jz      short loc_140010779
0x14001073a  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140010741  test    rax, rax
0x140010744  jz      short loc_140010779
0x140010746  mov     rdx, [rdi+10h]
0x14001074a  lea     rcx, [rsp+58h+arg_10]
0x14001074f  mov     [rsp+58h+var_20], 1
0x140010758  mov     r9d, ebx
0x14001075b  mov     [rsp+58h+var_28], 0
0x140010760  xor     r8d, r8d
0x140010763  mov     [rsp+58h+var_30], 0
0x14001076c  mov     [rsp+58h+var_38], rcx
0x140010771  mov     ecx, [rdi+18h]
0x140010774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010779  mov     rbx, [rsp+58h+arg_0]
0x14001077e  add     rsp, 50h
0x140010782  pop     rdi
0x140010783  retn
```
