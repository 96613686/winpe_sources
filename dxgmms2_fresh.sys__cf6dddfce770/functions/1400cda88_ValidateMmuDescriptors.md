# ValidateMmuDescriptors

- ea: `0x1400cda88`
- end: `0x1400cdbf8`
- name: `ValidateMmuDescriptors`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400cba0c`

## callees

- `0x140004268`
- `0x1400cda88`

## import_xrefs

- `watchdog!WdLogSingleEntry3` at `0x1400cdbb7`
- `watchdog!WdLogSingleEntry3` at `0x1400cdbb7`
- `watchdog!WdLogSingleEntry2` at `0x1400cdab3`
- `watchdog!WdLogSingleEntry2` at `0x1400cdb3c`
- `watchdog!WdLogSingleEntry2` at `0x1400cdb78`
- `watchdog!WdLogSingleEntry2` at `0x1400cdab3`
- `watchdog!WdLogSingleEntry2` at `0x1400cdb3c`
- `watchdog!WdLogSingleEntry2` at `0x1400cdb78`

## string_xrefs

- `0x1400cdbc8`: `Invalid value for DXGK_MMUDESCRIPTOR[%u]::Flags. Value (%u) cannot contain the bits (%u), or set reserved bits`
- `0x1400cdb4d`: `DXGK_MMUDESCRIPTOR[%u]::Size (%I64u) must be page aligned`
- `0x1400cdb89`: `DXGK_MMUDESCRIPTOR[%u]::Size (%I64u) cannot be 0`

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
0x1400cda88  push    rbx
0x1400cda8a  push    rbp
0x1400cda8b  push    rsi
0x1400cda8c  push    rdi
0x1400cda8d  sub     rsp, 58h
0x1400cda91  mov     rbp, rdx
0x1400cda94  cmp     r9d, 0FFFFh
0x1400cda9b  jz      short loc_1400CDAF7
0x1400cda9d  cmp     r9d, r8d
0x1400cdaa0  jb      short loc_1400CDAF7
0x1400cdaa2  mov     ebx, r8d
0x1400cdaa5  mov     ecx, 1
0x1400cdaaa  mov     r8d, r8d
0x1400cdaad  mov     edx, r9d
0x1400cdab0  mov     edi, r9d
0x1400cdab3  call    cs:__imp_WdLogSingleEntry2
0x1400cdaba  nop     dword ptr [rax+rax+00h]
0x1400cdabf  xor     esi, esi
0x1400cdac1  mov     cs:WdLogGlobalForLineNumber, 183h
0x1400cdacb  mov     [rsp+78h+var_40], rsi
0x1400cdad0  lea     r9, aDisplaymmuidUM; "DisplayMmuId (%u) must be a valid ID (N"...
0x1400cdad7  mov     [rsp+78h+var_48], rsi
0x1400cdadc  mov     [rsp+78h+var_50], rbx
0x1400cdae1  mov     edx, 40000h
0x1400cdae6  mov     [rsp+78h+var_58], rdi
0x1400cdaeb  call    DxgkLogInternalTriageEvent
0x1400cdaf0  xor     al, al
0x1400cdaf2  jmp     loc_1400CDBEE
0x1400cdaf7  xor     esi, esi
0x1400cdaf9  movzx   edx, si
0x1400cdafc  lea     ecx, [rsi+1]
0x1400cdaff  movzx   eax, dx
0x1400cdb02  cmp     eax, r8d
0x1400cdb05  jnb     loc_1400CDBEC
0x1400cdb0b  movzx   edi, dx
0x1400cdb0e  mov     ebx, edi
0x1400cdb10  add     rbx, rbx
0x1400cdb13  mov     eax, [rbp+rbx*8+0]
0x1400cdb17  test    eax, eax
0x1400cdb19  jnz     loc_1400CDBAE
0x1400cdb1f  mov     rax, [rbp+rbx*8+8]
0x1400cdb24  test    rax, rax
0x1400cdb27  jz      short loc_1400CDB72
0x1400cdb29  test    rax, 0FFFh
0x1400cdb2f  jnz     short loc_1400CDB36
0x1400cdb31  add     dx, cx
0x1400cdb34  jmp     short loc_1400CDAFF
0x1400cdb36  mov     r8, rax
0x1400cdb39  mov     rdx, rdi
0x1400cdb3c  call    cs:__imp_WdLogSingleEntry2
0x1400cdb43  nop     dword ptr [rax+rax+00h]
0x1400cdb48  mov     [rsp+78h+var_40], rsi
0x1400cdb4d  lea     r9, aDxgkMmudescrip; "DXGK_MMUDESCRIPTOR[%u]::Size (%I64u) mu"...
0x1400cdb54  mov     cs:WdLogGlobalForLineNumber, 1A3h
0x1400cdb5e  mov     rax, [rbp+rbx*8+8]
0x1400cdb63  mov     [rsp+78h+var_48], rsi
0x1400cdb68  mov     [rsp+78h+var_50], rax
0x1400cdb6d  jmp     loc_1400CDAE1
0x1400cdb72  xor     r8d, r8d
0x1400cdb75  mov     rdx, rdi
0x1400cdb78  call    cs:__imp_WdLogSingleEntry2
0x1400cdb7f  nop     dword ptr [rax+rax+00h]
0x1400cdb84  mov     [rsp+78h+var_40], rsi
0x1400cdb89  lea     r9, aDxgkMmudescrip_0; "DXGK_MMUDESCRIPTOR[%u]::Size (%I64u) ca"...
0x1400cdb90  mov     cs:WdLogGlobalForLineNumber, 19Ah
0x1400cdb9a  mov     rax, [rbp+rbx*8+8]
0x1400cdb9f  mov     [rsp+78h+var_48], rsi
0x1400cdba4  mov     [rsp+78h+var_50], rax
0x1400cdba9  jmp     loc_1400CDAE1
0x1400cdbae  mov     r8, rax
0x1400cdbb1  xor     r9d, r9d
0x1400cdbb4  mov     rdx, rdi
0x1400cdbb7  call    cs:__imp_WdLogSingleEntry3
0x1400cdbbe  nop     dword ptr [rax+rax+00h]
0x1400cdbc3  mov     [rsp+78h+var_40], rsi
0x1400cdbc8  lea     r9, aInvalidValueFo_1; "Invalid value for DXGK_MMUDESCRIPTOR[%u"...
0x1400cdbcf  mov     cs:WdLogGlobalForLineNumber, 191h
0x1400cdbd9  mov     eax, [rbp+rbx*8+0]
0x1400cdbdd  mov     [rsp+78h+var_48], rsi
0x1400cdbe2  mov     [rsp+78h+var_50], rax
0x1400cdbe7  jmp     loc_1400CDAE1
0x1400cdbec  mov     al, cl
0x1400cdbee  add     rsp, 58h
0x1400cdbf2  pop     rdi
0x1400cdbf3  pop     rsi
0x1400cdbf4  pop     rbp
0x1400cdbf5  pop     rbx
0x1400cdbf6  retn
```
