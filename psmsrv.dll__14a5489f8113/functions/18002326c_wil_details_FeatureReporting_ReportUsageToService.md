# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x18002326c`
- end: `0x180023394`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800236f8`

## callees

- `0x18002326c`
- `0x18002339c`
- `0x18002f010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v6; // ebx
  __int64 v7; // r8
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  int v9; // [rsp+70h] [rbp+18h] BYREF

  v9 = a3;
  v6 = a2 & 1;
  if ( a3 )
  {
    switch ( a3 )
    {
      case 1:
        v7 = 4 * (unsigned int)!(a2 & 1);
        goto LABEL_17;
      case 2:
        v7 = 4 * (unsigned int)!(a2 & 1) + 1;
        goto LABEL_17;
      case 3:
        v7 = 4 * (unsigned int)!(a2 & 1) + 2;
        goto LABEL_17;
      case 4:
        v7 = 4 * (unsigned int)!(a2 & 1) + 3;
        goto LABEL_17;
      case 5:
        v7 = 2 * (unsigned int)!(a2 & 1) + 8;
        goto LABEL_17;
      case 6:
        v7 = 2 * (unsigned int)!(a2 & 1) + 9;
        goto LABEL_17;
    }
    if ( (unsigned __int8)(a3 - 100) <= 0x31u )
    {
      v7 = (unsigned __int8)(a3 - 100) + (v6 != 0 ? 100 : 150);
      goto LABEL_17;
    }
  }
  v7 = 255;
LABEL_17:
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil_details_FeatureReporting_ReportUsageToServiceDirect(
                                                                                                     a1,
                                                                                                     a2,
                                                                                                     v7);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(*(unsigned int *)(a1 + 24), *(_QWORD *)(a1 + 16), 0, v6, &v9, 0, 0, a4);
  }
  return result;
}

```

## disassembly

```asm
0x18002326c  mov     [rsp+arg_0], rbx
0x180023271  mov     [rsp+arg_8], rsi
0x180023276  mov     [rsp+arg_10], r8d
0x18002327b  push    rdi
0x18002327c  sub     rsp, 50h
0x180023280  mov     rdi, rcx
0x180023283  mov     ebx, edx
0x180023285  mov     ecx, 1
0x18002328a  mov     rsi, r9
0x18002328d  and     ebx, ecx
0x18002328f  mov     r11d, r8d
0x180023292  mov     r10d, r8d
0x180023295  test    r8d, r8d
0x180023298  jz      loc_180023337
0x18002329e  sub     r10d, ecx
0x1800232a1  jz      loc_18002332B
0x1800232a7  sub     r10d, ecx
0x1800232aa  jz      short loc_18002331D
0x1800232ac  sub     r10d, ecx
0x1800232af  jz      short loc_18002330F
0x1800232b1  sub     r10d, ecx
0x1800232b4  jz      short loc_180023301
0x1800232b6  sub     r10d, ecx
0x1800232b9  jz      short loc_1800232F3
0x1800232bb  cmp     r10d, ecx
0x1800232be  jz      short loc_1800232E5
0x1800232c0  sub     r11b, 64h ; 'd'
0x1800232c4  cmp     r11b, 31h ; '1'
0x1800232c8  ja      short loc_180023337
0x1800232ca  mov     eax, ebx
0x1800232cc  neg     eax
0x1800232ce  movzx   eax, r11b
0x1800232d2  sbb     r8d, r8d
0x1800232d5  and     r8d, 0FFFFFFCEh
0x1800232d9  add     r8d, 96h
0x1800232e0  add     r8d, eax
0x1800232e3  jmp     short loc_18002333D
0x1800232e5  mov     eax, ebx
0x1800232e7  xor     eax, ecx
0x1800232e9  lea     r8d, ds:9[rax*2]
0x1800232f1  jmp     short loc_18002333D
0x1800232f3  mov     eax, ebx
0x1800232f5  xor     eax, ecx
0x1800232f7  lea     r8d, ds:8[rax*2]
0x1800232ff  jmp     short loc_18002333D
0x180023301  mov     eax, ebx
0x180023303  xor     eax, ecx
0x180023305  lea     r8d, ds:3[rax*4]
0x18002330d  jmp     short loc_18002333D
0x18002330f  mov     eax, ebx
0x180023311  xor     eax, ecx
0x180023313  lea     r8d, ds:2[rax*4]
0x18002331b  jmp     short loc_18002333D
0x18002331d  mov     eax, ebx
0x18002331f  xor     eax, ecx
0x180023321  lea     r8d, ds:1[rax*4]
0x180023329  jmp     short loc_18002333D
0x18002332b  mov     r8d, ebx
0x18002332e  xor     r8d, ecx
0x180023331  shl     r8d, 2
0x180023335  jmp     short loc_18002333D
0x180023337  mov     r8d, 0FFh
0x18002333d  mov     rcx, rdi
0x180023340  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x180023345  test    eax, eax
0x180023347  jz      short loc_180023384
0x180023349  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180023350  test    rax, rax
0x180023353  jz      short loc_180023384
0x180023355  mov     rdx, [rdi+10h]
0x180023359  lea     rcx, [rsp+58h+arg_10]
0x18002335e  mov     [rsp+58h+var_20], rsi
0x180023363  mov     r9d, ebx
0x180023366  mov     [rsp+58h+var_28], 0
0x18002336b  xor     r8d, r8d
0x18002336e  mov     [rsp+58h+var_30], 0
0x180023377  mov     [rsp+58h+var_38], rcx
0x18002337c  mov     ecx, [rdi+18h]
0x18002337f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023384  mov     rbx, [rsp+58h+arg_0]
0x180023389  mov     rsi, [rsp+58h+arg_8]
0x18002338e  add     rsp, 50h
0x180023392  pop     rdi
0x180023393  retn
```
