# BreakDownKeyString

- ea: `0x140001e90`
- end: `0x140001fe3`
- name: `BreakDownKeyString`
- size: `339`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140003c48`
- `0x14000406c`
- `0x140004354`
- `0x140004bbc`
- `0x140006a5c`
- `0x14000752c`
- `0x140008fe8`
- `0x140009ae4`
- `0x14000a0a0`

## callees

- `0x140001e90`
- `0x1400024a4`
- `0x140002940`
- `0x140002b70`
- `0x14000c62c`
- `0x14000c810`
- `0x14000c9c0`
- `0x14000cd48`
- `0x14000daa4`
- `0x14000e228`
- `0x14000e450`
- `0x14000e4e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140001f6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140001f6d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140001ebb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140001efc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140001fb4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140001ebb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140001efc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140001fb4`

## pseudocode

```c
__int64 __fastcall BreakDownKeyString(WCHAR *a1, int *a2)
{
  unsigned int v4; // r14d
  _WORD *Memory; // rax
  const WCHAR *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r8
  int Char2; // eax
  const WCHAR *v11; // rdi
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 *ResString2FromModule; // rax
  __int64 v16; // r8
  void *v17; // [rsp+50h] [rbp+8h] BYREF

  if ( !a1 || !a2 || (unsigned int)*a2 > 0xB )
  {
    v7 = 87;
    goto LABEL_19;
  }
  v4 = lstrlenW(a1) + 1;
  Memory = AllocateMemory(2 * v4);
  v17 = Memory;
  v6 = Memory;
  if ( Memory )
  {
    StringCopyW(Memory, a1, v4);
    TrimString2(v6);
    if ( (unsigned int)lstrlenW(v6) <= 2 || (unsigned int)StringCompareExW(v6, L"\\\\", v8, 2) )
    {
      v11 = v6;
    }
    else
    {
      Char2 = FindChar2(v6, 92, v9, 2);
      if ( Char2 == -1 )
      {
        v11 = 0;
      }
      else
      {
        v6[Char2] = 0;
        v11 = &v6[Char2 + 1];
      }
      v12 = ParseMachineName(v6);
      if ( v12 != 1 )
        goto LABEL_14;
      if ( !v11 )
        goto LABEL_13;
    }
    if ( lstrlenW(v11) )
    {
      v12 = ParseKeyName(v11, a2, v16);
      goto LABEL_14;
    }
LABEL_13:
    SetLastError(0x80040152);
    ResString2FromModule = GetResString2FromModule(v13, 0x68u, 0);
    SetReason2(1, (const wchar_t *)ResString2FromModule, &g_wszOptions[10 * *a2]);
    v12 = 0;
LABEL_14:
    FreeMemory(&v17);
    return v12;
  }
  v7 = 0xFFFFFFFFLL;
LABEL_19:
  SaveErrorMessage(v7);
  return 0;
}

```

## disassembly

```asm
0x140001e90  push    rbx
0x140001e92  push    rsi
0x140001e93  push    rdi
0x140001e94  push    r14
0x140001e96  sub     rsp, 28h
0x140001e9a  mov     rsi, rdx
0x140001e9d  mov     rdi, rcx
0x140001ea0  test    rcx, rcx
0x140001ea3  jz      loc_140001FCD
0x140001ea9  test    rdx, rdx
0x140001eac  jz      loc_140001FCD
0x140001eb2  cmp     dword ptr [rdx], 0Bh
0x140001eb5  ja      loc_140001FCD
0x140001ebb  call    cs:__imp_lstrlenW
0x140001ec1  lea     r14d, [rax+1]
0x140001ec5  lea     ecx, [r14+r14]; dwBytes
0x140001ec9  call    AllocateMemory
0x140001ece  mov     [rsp+48h+arg_0], rax
0x140001ed3  mov     rbx, rax
0x140001ed6  test    rax, rax
0x140001ed9  jnz     short loc_140001EE3
0x140001edb  or      ecx, 0FFFFFFFFh
0x140001ede  jmp     loc_140001FD2
0x140001ee3  mov     r8d, r14d
0x140001ee6  mov     rdx, rdi
0x140001ee9  mov     rcx, rbx
0x140001eec  call    StringCopyW
0x140001ef1  mov     rcx, rbx; lpString
0x140001ef4  call    TrimString2
0x140001ef9  mov     rcx, rbx; lpString
0x140001efc  call    cs:__imp_lstrlenW
0x140001f02  mov     edi, 2
0x140001f07  cmp     eax, edi
0x140001f09  jbe     loc_140001FAE
0x140001f0f  mov     r9d, edi
0x140001f12  lea     rdx, String2; "\\\\"
0x140001f19  mov     rcx, rbx; lpString1
0x140001f1c  call    StringCompareExW
0x140001f21  test    eax, eax
0x140001f23  jnz     loc_140001FAE
0x140001f29  lea     edx, [rdi+5Ah]
0x140001f2c  mov     r9d, edi
0x140001f2f  mov     rcx, rbx
0x140001f32  call    FindChar2
0x140001f37  cmp     eax, 0FFFFFFFFh
0x140001f3a  jz      short loc_140001F4F
0x140001f3c  movsxd  rcx, eax
0x140001f3f  xor     eax, eax
0x140001f41  lea     rdi, [rcx+1]
0x140001f45  mov     [rbx+rcx*2], ax
0x140001f49  lea     rdi, [rbx+rdi*2]
0x140001f4d  jmp     short loc_140001F51
0x140001f4f  xor     edi, edi
0x140001f51  mov     rdx, rsi
0x140001f54  mov     rcx, rbx; lpString1
0x140001f57  call    ParseMachineName
0x140001f5c  mov     ebx, eax
0x140001f5e  cmp     eax, 1
0x140001f61  jnz     short loc_140001FA0
0x140001f63  test    rdi, rdi
0x140001f66  jnz     short loc_140001FB1
0x140001f68  mov     ecx, 80040152h; dwErrCode
0x140001f6d  call    cs:__imp_SetLastError
0x140001f73  xor     r8d, r8d
0x140001f76  lea     edx, [r8+68h]
0x140001f7a  call    GetResString2FromModule
0x140001f7f  movsxd  rdx, dword ptr [rsi]
0x140001f82  mov     ecx, 1
0x140001f87  lea     r8, [rdx+rdx*4]
0x140001f8b  lea     rdx, g_wszOptions; "QUERY"
0x140001f92  lea     r8, [rdx+r8*4]
0x140001f96  mov     rdx, rax
0x140001f99  call    SetReason2
0x140001f9e  xor     ebx, ebx
0x140001fa0  lea     rcx, [rsp+48h+arg_0]
0x140001fa5  call    FreeMemory
0x140001faa  mov     eax, ebx
0x140001fac  jmp     short loc_140001FD9
0x140001fae  mov     rdi, rbx
0x140001fb1  mov     rcx, rdi; lpString
0x140001fb4  call    cs:__imp_lstrlenW
0x140001fba  test    eax, eax
0x140001fbc  jz      short loc_140001F68
0x140001fbe  mov     rdx, rsi
0x140001fc1  mov     rcx, rdi; lpString1
0x140001fc4  call    ParseKeyName
0x140001fc9  mov     ebx, eax
0x140001fcb  jmp     short loc_140001FA0
0x140001fcd  mov     ecx, 57h ; 'W'
0x140001fd2  call    SaveErrorMessage
0x140001fd7  xor     eax, eax
0x140001fd9  add     rsp, 28h
0x140001fdd  pop     r14
0x140001fdf  pop     rdi
0x140001fe0  pop     rsi
0x140001fe1  pop     rbx
0x140001fe2  retn
```
