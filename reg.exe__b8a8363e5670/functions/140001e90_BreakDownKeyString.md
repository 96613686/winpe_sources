# BreakDownKeyString

- ea: `0x140001e90`
- end: `0x140001ffc`
- name: `BreakDownKeyString`
- size: `364`
- prototype: `__int64 __fastcall(const WCHAR *, int *)`
- caller_count: `9`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140003e34`
- `0x14000426c`
- `0x14000456c`
- `0x140004e84`
- `0x140006e6c`
- `0x14000799c`
- `0x14000957c`
- `0x14000a0e0`
- `0x14000a6d8`

## callees

- `0x140001e90`
- `0x14000263c`
- `0x140002a78`
- `0x140002ce4`
- `0x14000ce50`
- `0x14000d0c4`
- `0x14000d2d0`
- `0x14000d694`
- `0x14000e600`
- `0x14000ee5c`
- `0x14000f0c0`
- `0x14000f15c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140001f79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140001f79`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140001ebb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140001f02`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140001fc6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140001ebb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140001f02`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140001fc6`

## pseudocode

```c
__int64 __fastcall BreakDownKeyString(const WCHAR *a1, int *a2)
{
  unsigned int v4; // r14d
  __int64 Memory; // rax
  const WCHAR *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // r8
  int Char2; // eax
  const WCHAR *v10; // rdi
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 ResString2FromModule; // rax
  __int64 v15; // r8
  __int64 v16; // [rsp+50h] [rbp+8h] BYREF

  if ( !a1 || !a2 || (unsigned int)*a2 > 0xB )
  {
    v7 = 87;
    goto LABEL_19;
  }
  v4 = lstrlenW(a1) + 1;
  Memory = AllocateMemory(2 * v4);
  v16 = Memory;
  v6 = (const WCHAR *)Memory;
  if ( Memory )
  {
    StringCopyW(Memory, a1, v4);
    TrimString2(v6);
    if ( (unsigned int)lstrlenW(v6) <= 2 || (unsigned int)StringCompareExW(v6, L"\\\\") )
    {
      v10 = v6;
    }
    else
    {
      Char2 = FindChar2(v6, 92, v8, 2);
      if ( Char2 == -1 )
      {
        v10 = 0;
      }
      else
      {
        v6[Char2] = 0;
        v10 = &v6[Char2 + 1];
      }
      v11 = ParseMachineName(v6);
      if ( v11 != 1 )
        goto LABEL_14;
      if ( !v10 )
        goto LABEL_13;
    }
    if ( lstrlenW(v10) )
    {
      v11 = ParseKeyName(v10, a2, v15);
      goto LABEL_14;
    }
LABEL_13:
    SetLastError(0x80040152);
    ResString2FromModule = GetResString2FromModule(v12, 104, 0);
    SetReason2(1, ResString2FromModule, &g_wszOptions[10 * *a2]);
    v11 = 0;
LABEL_14:
    FreeMemory(&v16);
    return v11;
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
0x140001ea3  jz      loc_140001FE5
0x140001ea9  test    rdx, rdx
0x140001eac  jz      loc_140001FE5
0x140001eb2  cmp     dword ptr [rdx], 0Bh
0x140001eb5  ja      loc_140001FE5
0x140001ebb  call    cs:__imp_lstrlenW
0x140001ec2  nop     dword ptr [rax+rax+00h]
0x140001ec7  lea     r14d, [rax+1]
0x140001ecb  lea     ecx, [r14+r14]; dwBytes
0x140001ecf  call    AllocateMemory
0x140001ed4  mov     [rsp+48h+arg_0], rax
0x140001ed9  mov     rbx, rax
0x140001edc  test    rax, rax
0x140001edf  jnz     short loc_140001EE9
0x140001ee1  or      ecx, 0FFFFFFFFh
0x140001ee4  jmp     loc_140001FEA
0x140001ee9  mov     r8d, r14d
0x140001eec  mov     rdx, rdi
0x140001eef  mov     rcx, rbx
0x140001ef2  call    StringCopyW
0x140001ef7  mov     rcx, rbx; lpString
0x140001efa  call    TrimString2
0x140001eff  mov     rcx, rbx; lpString
0x140001f02  call    cs:__imp_lstrlenW
0x140001f09  nop     dword ptr [rax+rax+00h]
0x140001f0e  mov     edi, 2
0x140001f13  cmp     eax, edi
0x140001f15  jbe     loc_140001FC0
0x140001f1b  mov     r9d, edi
0x140001f1e  lea     rdx, String2; "\\\\"
0x140001f25  mov     rcx, rbx; lpString1
0x140001f28  call    StringCompareExW
0x140001f2d  test    eax, eax
0x140001f2f  jnz     loc_140001FC0
0x140001f35  lea     edx, [rdi+5Ah]
0x140001f38  mov     r9d, edi
0x140001f3b  mov     rcx, rbx
0x140001f3e  call    FindChar2
0x140001f43  cmp     eax, 0FFFFFFFFh
0x140001f46  jz      short loc_140001F5B
0x140001f48  movsxd  rcx, eax
0x140001f4b  xor     eax, eax
0x140001f4d  lea     rdi, [rcx+1]
0x140001f51  mov     [rbx+rcx*2], ax
0x140001f55  lea     rdi, [rbx+rdi*2]
0x140001f59  jmp     short loc_140001F5D
0x140001f5b  xor     edi, edi
0x140001f5d  mov     rdx, rsi
0x140001f60  mov     rcx, rbx; lpString1
0x140001f63  call    ParseMachineName
0x140001f68  mov     ebx, eax
0x140001f6a  cmp     eax, 1
0x140001f6d  jnz     short loc_140001FB2
0x140001f6f  test    rdi, rdi
0x140001f72  jnz     short loc_140001FC3
0x140001f74  mov     ecx, 80040152h; dwErrCode
0x140001f79  call    cs:__imp_SetLastError
0x140001f80  nop     dword ptr [rax+rax+00h]
0x140001f85  xor     r8d, r8d
0x140001f88  lea     edx, [r8+68h]
0x140001f8c  call    GetResString2FromModule
0x140001f91  movsxd  rdx, dword ptr [rsi]
0x140001f94  mov     ecx, 1
0x140001f99  lea     r8, [rdx+rdx*4]
0x140001f9d  lea     rdx, g_wszOptions; "QUERY"
0x140001fa4  lea     r8, [rdx+r8*4]
0x140001fa8  mov     rdx, rax
0x140001fab  call    SetReason2
0x140001fb0  xor     ebx, ebx
0x140001fb2  lea     rcx, [rsp+48h+arg_0]
0x140001fb7  call    FreeMemory
0x140001fbc  mov     eax, ebx
0x140001fbe  jmp     short loc_140001FF1
0x140001fc0  mov     rdi, rbx
0x140001fc3  mov     rcx, rdi; lpString
0x140001fc6  call    cs:__imp_lstrlenW
0x140001fcd  nop     dword ptr [rax+rax+00h]
0x140001fd2  test    eax, eax
0x140001fd4  jz      short loc_140001F74
0x140001fd6  mov     rdx, rsi
0x140001fd9  mov     rcx, rdi; lpString1
0x140001fdc  call    ParseKeyName
0x140001fe1  mov     ebx, eax
0x140001fe3  jmp     short loc_140001FB2
0x140001fe5  mov     ecx, 57h ; 'W'
0x140001fea  call    SaveErrorMessage
0x140001fef  xor     eax, eax
0x140001ff1  add     rsp, 28h
0x140001ff5  pop     r14
0x140001ff7  pop     rdi
0x140001ff8  pop     rsi
0x140001ff9  pop     rbx
0x140001ffa  retn
```
