# TraceConfigureLastBranchRecord

- ea: `0x18000d5f0`
- end: `0x18000d76e`
- name: `TraceConfigureLastBranchRecord`
- size: `382`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x180001560`
- `0x180001ee2`
- `0x18000d5f0`

## import_xrefs

- `ntdll!NtSetSystemInformation` at `0x18000d67a`
- `ntdll!NtSetSystemInformation` at `0x18000d6ac`
- `ntdll!NtSetSystemInformation` at `0x18000d738`
- `ntdll!NtSetSystemInformation` at `0x18000d67a`
- `ntdll!NtSetSystemInformation` at `0x18000d6ac`
- `ntdll!NtSetSystemInformation` at `0x18000d738`

## pseudocode

```c
ULONG __fastcall TraceConfigureLastBranchRecord(__int64 a1, int a2, __int64 a3, unsigned int a4)
{
  int v9; // eax
  __int64 v10; // r9
  __int64 v11; // rcx
  unsigned __int8 v12; // r8
  _QWORD *v13; // r10
  _QWORD v14[2]; // [rsp+20h] [rbp-50h] BYREF
  int v15; // [rsp+30h] [rbp-40h]
  int v16; // [rsp+34h] [rbp-3Ch]
  _DWORD SystemInformation[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v18; // [rsp+40h] [rbp-30h]
  __int128 v19; // [rsp+48h] [rbp-28h]
  __int64 v20; // [rsp+58h] [rbp-18h]

  SystemInformation[1] = 0;
  v20 = 0;
  v19 = 0;
  if ( a4 > 4 )
    return 1292;
  if ( a4 && !a3 || (a2 & 3) == 3 )
    return 87;
  SystemInformation[0] = 20;
  v18 = a1;
  v9 = NtSetSystemInformation(SystemPerformanceTraceInformation, SystemInformation, 0x10u);
  if ( v9 < 0 )
    return RtlNtStatusToDosError_0(v9);
  v14[0] = 19;
  v16 = 0;
  v14[1] = a1;
  v15 = a2;
  v9 = NtSetSystemInformation(SystemPerformanceTraceInformation, v14, 0x18u);
  if ( v9 < 0 )
    return RtlNtStatusToDosError_0(v9);
  if ( !a4 )
    return 0;
  v10 = 0;
  v11 = 0;
  do
  {
    v12 = 0;
    while ( 1 )
    {
      v13 = (_QWORD *)*((_QWORD *)&EtwpGuidMap + v12);
      if ( *v13 == *(_QWORD *)(a3 + 24 * v11) && v13[1] == *(_QWORD *)(a3 + 24 * v11 + 8) )
        break;
      if ( ++v12 >= 0x20u )
        goto LABEL_17;
    }
    *((_DWORD *)&v19 + v10) = (v12 << 8) | *(unsigned __int8 *)(a3 + 24 * v11 + 16);
    v10 = (unsigned int)(v10 + 1);
LABEL_17:
    v11 = (unsigned int)(v11 + 1);
  }
  while ( (unsigned int)v11 < a4 );
  SystemInformation[0] = 20;
  v18 = a1;
  v9 = NtSetSystemInformation(SystemPerformanceTraceInformation, SystemInformation, 4 * v10 + 16);
  if ( v9 )
    return RtlNtStatusToDosError_0(v9);
  else
    return 0;
}

```

## disassembly

```asm
0x18000d5f0  mov     [rsp-18h+arg_10], rbx
0x18000d5f5  mov     [rsp-18h+arg_18], rsi
0x18000d5fa  push    rbp
0x18000d5fb  push    rdi
0x18000d5fc  push    r14
0x18000d5fe  mov     rbp, rsp
0x18000d601  sub     rsp, 70h
0x18000d605  mov     rax, cs:__security_cookie
0x18000d60c  xor     rax, rsp
0x18000d60f  mov     [rbp+var_10], rax
0x18000d613  mov     [rbp+var_34], 0
0x18000d61a  xorps   xmm0, xmm0
0x18000d61d  mov     [rbp+var_18], 0
0x18000d625  mov     ebx, r9d
0x18000d628  mov     rsi, r8
0x18000d62b  mov     edi, edx
0x18000d62d  mov     r14, rcx
0x18000d630  movdqu  [rbp+var_28], xmm0
0x18000d635  cmp     r9d, 4
0x18000d639  jbe     short loc_18000D645
0x18000d63b  mov     eax, 50Ch
0x18000d640  jmp     loc_18000D74D
0x18000d645  test    ebx, ebx
0x18000d647  jz      short loc_18000D64E
0x18000d649  test    rsi, rsi
0x18000d64c  jz      short loc_18000D657
0x18000d64e  mov     eax, edi
0x18000d650  and     eax, 3
0x18000d653  cmp     al, 3
0x18000d655  jnz     short loc_18000D661
0x18000d657  mov     eax, 57h ; 'W'
0x18000d65c  jmp     loc_18000D74D
0x18000d661  mov     r8d, 10h; SystemInformationLength
0x18000d667  mov     [rbp+SystemInformation], 14h
0x18000d66e  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x18000d672  mov     [rbp+var_30], r14
0x18000d676  lea     ecx, [r8+0Fh]; SystemInformationClass
0x18000d67a  call    cs:__imp_NtSetSystemInformation
0x18000d680  test    eax, eax
0x18000d682  js      loc_18000D746
0x18000d688  mov     r8d, 18h; SystemInformationLength
0x18000d68e  mov     [rbp+var_50], 13h
0x18000d696  lea     rdx, [rbp+var_50]; SystemInformation
0x18000d69a  mov     [rbp+var_3C], 0
0x18000d6a1  mov     [rbp+var_48], r14
0x18000d6a5  mov     [rbp+var_40], edi
0x18000d6a8  lea     ecx, [r8+7]; SystemInformationClass
0x18000d6ac  call    cs:__imp_NtSetSystemInformation
0x18000d6b2  test    eax, eax
0x18000d6b4  js      loc_18000D746
0x18000d6ba  test    ebx, ebx
0x18000d6bc  jz      loc_18000D742
0x18000d6c2  xor     r9d, r9d
0x18000d6c5  xor     ecx, ecx
0x18000d6c7  test    ebx, ebx
0x18000d6c9  jz      short loc_18000D71C
0x18000d6cb  xor     r8b, r8b
0x18000d6ce  lea     rdx, [rcx+rcx*2]
0x18000d6d2  movzx   eax, r8b
0x18000d6d6  lea     r10, EtwpGuidMap
0x18000d6dd  mov     r10, [r10+rax*8]
0x18000d6e1  mov     rax, [r10]
0x18000d6e4  cmp     rax, [rsi+rdx*8]
0x18000d6e8  jnz     short loc_18000D6F5
0x18000d6ea  mov     rax, [r10+8]
0x18000d6ee  cmp     rax, [rsi+rdx*8+8]
0x18000d6f3  jz      short loc_18000D700
0x18000d6f5  inc     r8b
0x18000d6f8  cmp     r8b, 20h ; ' '
0x18000d6fc  jb      short loc_18000D6D2
0x18000d6fe  jmp     short loc_18000D716
0x18000d700  movzx   edx, byte ptr [rsi+rdx*8+10h]
0x18000d705  movzx   eax, r8b
0x18000d709  shl     eax, 8
0x18000d70c  or      edx, eax
0x18000d70e  mov     dword ptr [rbp+r9*4+var_28], edx
0x18000d713  inc     r9d
0x18000d716  inc     ecx
0x18000d718  cmp     ecx, ebx
0x18000d71a  jb      short loc_18000D6CB
0x18000d71c  lea     r8d, ds:10h[r9*4]; SystemInformationLength
0x18000d724  mov     [rbp+SystemInformation], 14h
0x18000d72b  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x18000d72f  mov     [rbp+var_30], r14
0x18000d733  mov     ecx, 1Fh; SystemInformationClass
0x18000d738  call    cs:__imp_NtSetSystemInformation
0x18000d73e  test    eax, eax
0x18000d740  jnz     short loc_18000D746
0x18000d742  xor     eax, eax
0x18000d744  jmp     short loc_18000D74D
0x18000d746  mov     ecx, eax; Status
0x18000d748  call    RtlNtStatusToDosError_0
0x18000d74d  mov     rcx, [rbp+var_10]
0x18000d751  xor     rcx, rsp; StackCookie
0x18000d754  call    __security_check_cookie
0x18000d759  lea     r11, [rsp+70h+var_s0]
0x18000d75e  mov     rbx, [r11+30h]
0x18000d762  mov     rsi, [r11+38h]
0x18000d766  mov     rsp, r11
0x18000d769  pop     r14
0x18000d76b  pop     rdi
0x18000d76c  pop     rbp
0x18000d76d  retn
```
