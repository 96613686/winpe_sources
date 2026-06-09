# DiscpDiscoverViaHBA

- ea: `0x180009618`
- end: `0x180009891`
- name: `DiscpDiscoverViaHBA`
- size: `633`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180005098`
- `0x180009358`
- `0x180013a1c`

## callees

- `0x180008af8`
- `0x180008e84`
- `0x180009618`

## import_xrefs

- `ISCSIUM!DiscpExecuteMethod` at `0x180009694`
- `ISCSIUM!DiscpExecuteMethod` at `0x180009771`
- `ISCSIUM!DiscpExecuteMethod` at `0x180009694`
- `ISCSIUM!DiscpExecuteMethod` at `0x180009771`
- `ISCSIUM!DiscpReportEventlogWithStatus` at `0x18000987a`
- `ISCSIUM!DiscpReportEventlogWithStatus` at `0x18000987a`
- `ISCSIUM!DiscpFreeMemory` at `0x18000981e`
- `ISCSIUM!DiscpFreeMemory` at `0x180009839`
- `ISCSIUM!DiscpFreeMemory` at `0x180009848`
- `ISCSIUM!DiscpFreeMemory` at `0x18000981e`
- `ISCSIUM!DiscpFreeMemory` at `0x180009839`
- `ISCSIUM!DiscpFreeMemory` at `0x180009848`

## pseudocode

```c
__int64 __fastcall DiscpDiscoverViaHBA(__int64 a1, _QWORD *a2)
{
  __int64 v4; // r8
  unsigned int *v5; // rcx
  unsigned int v6; // ebx
  unsigned int v7; // r14d
  int v8; // esi
  _QWORD *v9; // rax
  _QWORD *v10; // rcx
  __int64 v11; // r8
  unsigned int v12; // eax
  unsigned int v13; // r14d
  int v14; // esi
  _QWORD *v15; // rax
  _QWORD *v16; // rcx
  _QWORD *v17; // rsi
  _QWORD *v18; // rcx
  int v20; // [rsp+30h] [rbp-30h]
  unsigned int *v21; // [rsp+50h] [rbp-10h] BYREF
  void *v22; // [rsp+58h] [rbp-8h] BYREF
  int v23; // [rsp+A0h] [rbp+40h] BYREF
  int v24; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int *v25; // [rsp+B0h] [rbp+50h] BYREF
  _QWORD *v26; // [rsp+B8h] [rbp+58h] BYREF

  a2[1] = a2;
  *a2 = a2;
  v4 = *(_QWORD *)(a1 + 40);
  v26 = 0;
  v21 = 0;
  v23 = 4096;
  v25 = 0;
  if ( !(unsigned int)DiscpExecuteMethod(MSiSCSI_DiscoveryOperations_GUID, 0, v4, 11, 0, 0, &v25, &v23, 8) )
  {
    v5 = v25;
    v6 = *v25;
    if ( !*v25 )
    {
      v7 = v25[1];
      v22 = v25 + 2;
      v8 = 0;
      v24 = v23 - 8;
      if ( !v7 )
        goto LABEL_30;
      while ( !v6 )
      {
        v6 = DiscpCreateDiscoveredTarget2(&v22, (unsigned int *)&v24, a1, (__int64)&v26);
        if ( !v6 )
        {
          v9 = v26;
          if ( v26 )
          {
            v10 = (_QWORD *)a2[1];
            if ( (_QWORD *)*v10 != a2 )
LABEL_22:
              __fastfail(3u);
            *v26 = a2;
            v9[1] = v10;
            *v10 = v9;
            a2[1] = v9;
          }
        }
        if ( ++v8 >= v7 )
        {
          if ( !v6 )
            goto LABEL_29;
          break;
        }
      }
    }
  }
  v11 = *(_QWORD *)(a1 + 40);
  v23 = 4096;
  v12 = DiscpExecuteMethod(MSiSCSI_DiscoveryOperations_GUID, 0, v11, 10, 0, 0, &v21, &v23, 8);
  v6 = v12;
  if ( v12 )
  {
    if ( v12 - 4200 <= 2 )
      v6 = -268500924;
    goto LABEL_25;
  }
  v6 = *v21;
  if ( *v21 )
  {
LABEL_25:
    v17 = (_QWORD *)*a2;
    while ( v17 != a2 )
    {
      v18 = v17;
      v17 = (_QWORD *)*v17;
      DiscpFreeMemory(v18);
    }
    a2[1] = a2;
    *a2 = a2;
    goto LABEL_29;
  }
  v13 = v21[1];
  v22 = v21 + 2;
  v14 = 0;
  v24 = v23 - 8;
  if ( v13 )
  {
    while ( !v6 )
    {
      v6 = DiscpCreateDiscoveredTarget(&v22, (unsigned int *)&v24, a1, (__int64)&v26);
      if ( !v6 )
      {
        v15 = v26;
        if ( v26 )
        {
          v16 = (_QWORD *)a2[1];
          if ( (_QWORD *)*v16 != a2 )
            goto LABEL_22;
          *v26 = a2;
          v15[1] = v16;
          *v16 = v15;
          a2[1] = v15;
        }
      }
      if ( ++v14 >= v13 )
      {
        if ( v6 )
          goto LABEL_25;
        goto LABEL_29;
      }
    }
    goto LABEL_25;
  }
LABEL_29:
  v5 = v25;
LABEL_30:
  if ( v5 )
    DiscpFreeMemory(v5);
  if ( v21 )
    DiscpFreeMemory(v21);
  if ( v6 )
  {
    LOWORD(v20) = 1;
    DiscpReportEventlogWithStatus(115, 2, 0, v6, 0, 0, v20);
  }
  return v6;
}

```

## disassembly

```asm
0x180009618  push    rbp
0x18000961a  push    rbx
0x18000961b  push    rsi
0x18000961c  push    rdi
0x18000961d  push    r13
0x18000961f  push    r14
0x180009621  push    r15
0x180009623  mov     rbp, rsp
0x180009626  sub     rsp, 60h
0x18000962a  mov     [rsp+60h+var_20], 8
0x180009632  lea     rax, [rbp+arg_0]
0x180009636  mov     [rsp+60h+var_28], rax
0x18000963b  mov     rdi, rdx
0x18000963e  mov     [rdx+8], rdx
0x180009642  lea     rax, [rbp+arg_10]
0x180009646  mov     [rdx], rdx
0x180009649  mov     r15, rcx
0x18000964c  mov     r8, [rcx+28h]
0x180009650  mov     r9d, 0Bh
0x180009656  mov     [rsp+60h+var_30], rax
0x18000965b  lea     rcx, MSiSCSI_DiscoveryOperations_GUID
0x180009662  mov     dword ptr [rsp+60h+var_38], 0
0x18000966a  xor     edx, edx
0x18000966c  mov     [rsp+60h+var_40], 0
0x180009675  mov     [rbp+arg_18], 0
0x18000967d  mov     [rbp+var_10], 0
0x180009685  mov     [rbp+arg_0], 1000h
0x18000968c  mov     [rbp+arg_10], 0
0x180009694  call    cs:__imp_DiscpExecuteMethod
0x18000969a  mov     esi, 2
0x18000969f  lea     r13d, [rsi-1]
0x1800096a3  test    eax, eax
0x1800096a5  jnz     loc_18000972C
0x1800096ab  mov     rcx, [rbp+arg_10]
0x1800096af  mov     ebx, [rcx]
0x1800096b1  test    ebx, ebx
0x1800096b3  jnz     short loc_18000972C
0x1800096b5  mov     r14d, [rcx+4]
0x1800096b9  lea     rax, [rcx+8]
0x1800096bd  mov     [rbp+var_8], rax
0x1800096c1  xor     esi, esi
0x1800096c3  mov     eax, [rbp+arg_0]
0x1800096c6  add     eax, 0FFFFFFF8h
0x1800096c9  mov     [rbp+arg_8], eax
0x1800096cc  test    r14d, r14d
0x1800096cf  jz      loc_180009834
0x1800096d5  test    ebx, ebx
0x1800096d7  jnz     short loc_180009727
0x1800096d9  lea     r9, [rbp+arg_18]
0x1800096dd  mov     r8, r15
0x1800096e0  lea     rdx, [rbp+arg_8]
0x1800096e4  lea     rcx, [rbp+var_8]
0x1800096e8  call    DiscpCreateDiscoveredTarget2
0x1800096ed  mov     ebx, eax
0x1800096ef  test    eax, eax
0x1800096f1  jnz     short loc_180009717
0x1800096f3  mov     rax, [rbp+arg_18]
0x1800096f7  test    rax, rax
0x1800096fa  jz      short loc_180009717
0x1800096fc  mov     rcx, [rdi+8]
0x180009700  cmp     [rcx], rdi
0x180009703  jnz     loc_1800097FD
0x180009709  mov     [rax], rdi
0x18000970c  mov     [rax+8], rcx
0x180009710  mov     [rcx], rax
0x180009713  mov     [rdi+8], rax
0x180009717  add     esi, r13d
0x18000971a  cmp     esi, r14d
0x18000971d  jb      short loc_1800096D5
0x18000971f  test    ebx, ebx
0x180009721  jz      loc_180009830
0x180009727  mov     esi, 2
0x18000972c  mov     r8, [r15+28h]
0x180009730  lea     rax, [rbp+arg_0]
0x180009734  mov     [rsp+60h+var_20], 8
0x18000973c  lea     rcx, MSiSCSI_DiscoveryOperations_GUID
0x180009743  mov     [rsp+60h+var_28], rax
0x180009748  mov     r9d, 0Ah
0x18000974e  lea     rax, [rbp+var_10]
0x180009752  mov     [rbp+arg_0], 1000h
0x180009759  mov     [rsp+60h+var_30], rax
0x18000975e  xor     edx, edx
0x180009760  mov     dword ptr [rsp+60h+var_38], 0
0x180009768  mov     [rsp+60h+var_40], 0
0x180009771  call    cs:__imp_DiscpExecuteMethod
0x180009777  mov     ebx, eax
0x180009779  test    eax, eax
0x18000977b  jnz     loc_180009804
0x180009781  mov     rcx, [rbp+var_10]
0x180009785  mov     ebx, [rcx]
0x180009787  test    ebx, ebx
0x180009789  jnz     loc_180009813
0x18000978f  mov     r14d, [rcx+4]
0x180009793  lea     rax, [rcx+8]
0x180009797  mov     [rbp+var_8], rax
0x18000979b  xor     esi, esi
0x18000979d  mov     eax, [rbp+arg_0]
0x1800097a0  add     eax, 0FFFFFFF8h
0x1800097a3  mov     [rbp+arg_8], eax
0x1800097a6  test    r14d, r14d
0x1800097a9  jz      loc_180009830
0x1800097af  test    ebx, ebx
0x1800097b1  jnz     short loc_180009813
0x1800097b3  lea     r9, [rbp+arg_18]
0x1800097b7  mov     r8, r15
0x1800097ba  lea     rdx, [rbp+arg_8]
0x1800097be  lea     rcx, [rbp+var_8]
0x1800097c2  call    DiscpCreateDiscoveredTarget
0x1800097c7  mov     ebx, eax
0x1800097c9  test    eax, eax
0x1800097cb  jnz     short loc_1800097ED
0x1800097cd  mov     rax, [rbp+arg_18]
0x1800097d1  test    rax, rax
0x1800097d4  jz      short loc_1800097ED
0x1800097d6  mov     rcx, [rdi+8]
0x1800097da  cmp     [rcx], rdi
0x1800097dd  jnz     short loc_1800097FD
0x1800097df  mov     [rax], rdi
0x1800097e2  mov     [rax+8], rcx
0x1800097e6  mov     [rcx], rax
0x1800097e9  mov     [rdi+8], rax
0x1800097ed  add     esi, r13d
0x1800097f0  mov     eax, ebx
0x1800097f2  cmp     esi, r14d
0x1800097f5  jb      short loc_1800097AF
0x1800097f7  test    eax, eax
0x1800097f9  jnz     short loc_180009813
0x1800097fb  jmp     short loc_180009830
0x1800097fd  mov     ecx, 3
0x180009802  int     29h; Win8: RtlFailFast(ecx)
0x180009804  add     eax, 0FFFFEF98h
0x180009809  mov     ecx, 0EFFF0044h
0x18000980e  cmp     eax, esi
0x180009810  cmovbe  ebx, ecx
0x180009813  mov     rsi, [rdi]
0x180009816  jmp     short loc_180009824
0x180009818  mov     rcx, rsi
0x18000981b  mov     rsi, [rsi]
0x18000981e  call    cs:__imp_DiscpFreeMemory
0x180009824  cmp     rsi, rdi
0x180009827  jnz     short loc_180009818
0x180009829  mov     [rdi+8], rdi
0x18000982d  mov     [rdi], rdi
0x180009830  mov     rcx, [rbp+arg_10]
0x180009834  test    rcx, rcx
0x180009837  jz      short loc_18000983F
0x180009839  call    cs:__imp_DiscpFreeMemory
0x18000983f  mov     rcx, [rbp+var_10]
0x180009843  test    rcx, rcx
0x180009846  jz      short loc_18000984E
0x180009848  call    cs:__imp_DiscpFreeMemory
0x18000984e  test    ebx, ebx
0x180009850  jz      short loc_180009880
0x180009852  mov     rax, [r15+28h]
0x180009856  xor     ecx, ecx
0x180009858  mov     [rsp+60h+var_28], rax
0x18000985d  mov     r9d, ebx
0x180009860  mov     word ptr [rsp+60h+var_30], r13w
0x180009866  mov     [rsp+60h+var_38], rcx
0x18000986b  lea     edx, [rcx+2]
0x18000986e  mov     [rsp+60h+var_40], rcx
0x180009873  movzx   r8d, cx
0x180009877  lea     ecx, [rdx+71h]
0x18000987a  call    cs:__imp_DiscpReportEventlogWithStatus
0x180009880  mov     eax, ebx
0x180009882  add     rsp, 60h
0x180009886  pop     r15
0x180009888  pop     r14
0x18000988a  pop     r13
0x18000988c  pop     rdi
0x18000988d  pop     rsi
0x18000988e  pop     rbx
0x18000988f  pop     rbp
0x180009890  retn
```
