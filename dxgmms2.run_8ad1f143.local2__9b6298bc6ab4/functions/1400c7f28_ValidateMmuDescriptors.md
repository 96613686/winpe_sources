# ValidateMmuDescriptors

- ea: `0x1400c7f28`
- end: `0x1400c8098`
- name: `ValidateMmuDescriptors`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400c5eac`

## callees

- `0x1400045ec`
- `0x1400c7f28`

## import_xrefs

- `watchdog!WdLogSingleEntry3` at `0x1400c8057`
- `watchdog!WdLogSingleEntry3` at `0x1400c8057`
- `watchdog!WdLogSingleEntry2` at `0x1400c7f53`
- `watchdog!WdLogSingleEntry2` at `0x1400c7fdc`
- `watchdog!WdLogSingleEntry2` at `0x1400c8018`
- `watchdog!WdLogSingleEntry2` at `0x1400c7f53`
- `watchdog!WdLogSingleEntry2` at `0x1400c7fdc`
- `watchdog!WdLogSingleEntry2` at `0x1400c8018`

## string_xrefs

- `0x1400c8029`: `DXGK_MMUDESCRIPTOR[%u]::Size (%I64u) cannot be 0`
- `0x1400c8068`: `Invalid value for DXGK_MMUDESCRIPTOR[%u]::Flags. Value (%u) cannot contain the bits (%u), or set reserved bits`
- `0x1400c7fed`: `DXGK_MMUDESCRIPTOR[%u]::Size (%I64u) must be page aligned`

## pseudocode

```c
char __fastcall ValidateMmuDescriptors(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  __int64 v5; // rbx
  __int64 v6; // rdi
  int v7; // ecx
  int v8; // r8d
  unsigned __int16 i; // dx
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rax
  int v14; // ecx
  int v15; // r8d
  int v16; // ecx
  int v17; // r8d
  int v18; // ecx
  int v19; // r8d

  if ( a4 == 0xFFFF || a4 < a3 )
  {
    for ( i = 0; i < a3; ++i )
    {
      v11 = i;
      v12 = 2LL * i;
      if ( *(_DWORD *)(a2 + 16LL * i) )
      {
        WdLogSingleEntry3(1, i, *(unsigned int *)(a2 + 16LL * i), 0);
        WdLogGlobalForLineNumber = 401;
        DxgkLogInternalTriageEvent(
          v18,
          0x40000,
          v19,
          (unsigned int)L"Invalid value for DXGK_MMUDESCRIPTOR[%u]::Flags. Value (%u) cannot contain the bits (%u), or set reserved bits",
          v11,
          *(unsigned int *)(a2 + 8 * v12),
          0,
          0);
        return 0;
      }
      v13 = *(_QWORD *)(a2 + 16LL * i + 8);
      if ( !v13 )
      {
        WdLogSingleEntry2(1, i, 0);
        WdLogGlobalForLineNumber = 410;
        DxgkLogInternalTriageEvent(
          v16,
          0x40000,
          v17,
          (unsigned int)L"DXGK_MMUDESCRIPTOR[%u]::Size (%I64u) cannot be 0",
          v11,
          *(_QWORD *)(a2 + 8 * v12 + 8),
          0,
          0);
        return 0;
      }
      if ( (v13 & 0xFFF) != 0 )
      {
        WdLogSingleEntry2(1, i, *(_QWORD *)(a2 + 16LL * i + 8));
        WdLogGlobalForLineNumber = 419;
        DxgkLogInternalTriageEvent(
          v14,
          0x40000,
          v15,
          (unsigned int)L"DXGK_MMUDESCRIPTOR[%u]::Size (%I64u) must be page aligned",
          v11,
          *(_QWORD *)(a2 + 8 * v12 + 8),
          0,
          0);
        return 0;
      }
    }
    return 1;
  }
  else
  {
    v5 = a3;
    v6 = a4;
    WdLogSingleEntry2(1, a4, a3);
    WdLogGlobalForLineNumber = 387;
    DxgkLogInternalTriageEvent(
      v7,
      0x40000,
      v8,
      (unsigned int)L"DisplayMmuId (%u) must be a valid ID (NumMmus=%u), or DXGK_INVALID_MMU_ID if not supported",
      v6,
      v5,
      0,
      0);
    return 0;
  }
}

```

## disassembly

```asm
0x1400c7f28  push    rbx
0x1400c7f2a  push    rbp
0x1400c7f2b  push    rsi
0x1400c7f2c  push    rdi
0x1400c7f2d  sub     rsp, 58h
0x1400c7f31  mov     rbp, rdx
0x1400c7f34  cmp     r9d, 0FFFFh
0x1400c7f3b  jz      short loc_1400C7F97
0x1400c7f3d  cmp     r9d, r8d
0x1400c7f40  jb      short loc_1400C7F97
0x1400c7f42  mov     ebx, r8d
0x1400c7f45  mov     ecx, 1
0x1400c7f4a  mov     r8d, r8d
0x1400c7f4d  mov     edx, r9d
0x1400c7f50  mov     edi, r9d
0x1400c7f53  call    cs:__imp_WdLogSingleEntry2
0x1400c7f5a  nop     dword ptr [rax+rax+00h]
0x1400c7f5f  xor     esi, esi
0x1400c7f61  mov     cs:WdLogGlobalForLineNumber, 183h
0x1400c7f6b  mov     [rsp+78h+var_40], rsi
0x1400c7f70  lea     r9, aDisplaymmuidUM; "DisplayMmuId (%u) must be a valid ID (N"...
0x1400c7f77  mov     [rsp+78h+var_48], rsi
0x1400c7f7c  mov     [rsp+78h+var_50], rbx
0x1400c7f81  mov     edx, 40000h
0x1400c7f86  mov     [rsp+78h+var_58], rdi
0x1400c7f8b  call    DxgkLogInternalTriageEvent
0x1400c7f90  xor     al, al
0x1400c7f92  jmp     loc_1400C808E
0x1400c7f97  xor     esi, esi
0x1400c7f99  movzx   edx, si
0x1400c7f9c  lea     ecx, [rsi+1]
0x1400c7f9f  movzx   eax, dx
0x1400c7fa2  cmp     eax, r8d
0x1400c7fa5  jnb     loc_1400C808C
0x1400c7fab  movzx   edi, dx
0x1400c7fae  mov     ebx, edi
0x1400c7fb0  add     rbx, rbx
0x1400c7fb3  mov     eax, [rbp+rbx*8+0]
0x1400c7fb7  test    eax, eax
0x1400c7fb9  jnz     loc_1400C804E
0x1400c7fbf  mov     rax, [rbp+rbx*8+8]
0x1400c7fc4  test    rax, rax
0x1400c7fc7  jz      short loc_1400C8012
0x1400c7fc9  test    rax, 0FFFh
0x1400c7fcf  jnz     short loc_1400C7FD6
0x1400c7fd1  add     dx, cx
0x1400c7fd4  jmp     short loc_1400C7F9F
0x1400c7fd6  mov     r8, rax
0x1400c7fd9  mov     rdx, rdi
0x1400c7fdc  call    cs:__imp_WdLogSingleEntry2
0x1400c7fe3  nop     dword ptr [rax+rax+00h]
0x1400c7fe8  mov     [rsp+78h+var_40], rsi
0x1400c7fed  lea     r9, aDxgkMmudescrip; "DXGK_MMUDESCRIPTOR[%u]::Size (%I64u) mu"...
0x1400c7ff4  mov     cs:WdLogGlobalForLineNumber, 1A3h
0x1400c7ffe  mov     rax, [rbp+rbx*8+8]
0x1400c8003  mov     [rsp+78h+var_48], rsi
0x1400c8008  mov     [rsp+78h+var_50], rax
0x1400c800d  jmp     loc_1400C7F81
0x1400c8012  xor     r8d, r8d
0x1400c8015  mov     rdx, rdi
0x1400c8018  call    cs:__imp_WdLogSingleEntry2
0x1400c801f  nop     dword ptr [rax+rax+00h]
0x1400c8024  mov     [rsp+78h+var_40], rsi
0x1400c8029  lea     r9, aDxgkMmudescrip_0; "DXGK_MMUDESCRIPTOR[%u]::Size (%I64u) ca"...
0x1400c8030  mov     cs:WdLogGlobalForLineNumber, 19Ah
0x1400c803a  mov     rax, [rbp+rbx*8+8]
0x1400c803f  mov     [rsp+78h+var_48], rsi
0x1400c8044  mov     [rsp+78h+var_50], rax
0x1400c8049  jmp     loc_1400C7F81
0x1400c804e  mov     r8, rax
0x1400c8051  xor     r9d, r9d
0x1400c8054  mov     rdx, rdi
0x1400c8057  call    cs:__imp_WdLogSingleEntry3
0x1400c805e  nop     dword ptr [rax+rax+00h]
0x1400c8063  mov     [rsp+78h+var_40], rsi
0x1400c8068  lea     r9, aInvalidValueFo_1; "Invalid value for DXGK_MMUDESCRIPTOR[%u"...
0x1400c806f  mov     cs:WdLogGlobalForLineNumber, 191h
0x1400c8079  mov     eax, [rbp+rbx*8+0]
0x1400c807d  mov     [rsp+78h+var_48], rsi
0x1400c8082  mov     [rsp+78h+var_50], rax
0x1400c8087  jmp     loc_1400C7F81
0x1400c808c  mov     al, cl
0x1400c808e  add     rsp, 58h
0x1400c8092  pop     rdi
0x1400c8093  pop     rsi
0x1400c8094  pop     rbp
0x1400c8095  pop     rbx
0x1400c8096  retn
```
