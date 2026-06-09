# CopyKeyNameFromLeftToRight

- ea: `0x140009374`
- end: `0x140009492`
- name: `CopyKeyNameFromLeftToRight`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000957c`

## callees

- `0x140002ce4`
- `0x140009374`
- `0x14000ce50`
- `0x14000d694`
- `0x14000e600`
- `0x14000f0c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400093b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400093b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400093fc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140009438`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400093fc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140009438`

## string_xrefs

- `0x1400093ce`: `COMPARE`

## pseudocode

```c
__int64 __fastcall CopyKeyNameFromLeftToRight(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 ResString2FromModule; // rax
  const WCHAR *v6; // rcx
  int v7; // eax
  unsigned int v8; // esi
  _WORD *Memory; // rax
  const WCHAR *v10; // rcx
  int v11; // eax
  unsigned int v12; // esi
  _WORD *v13; // rax
  __int64 v15; // rcx

  if ( !a1 || !a2 )
  {
    v15 = 87;
LABEL_17:
    SaveErrorMessage(v15);
    return 0;
  }
  if ( *(_DWORD *)(a2 + 16) != 1 || a1[1] == -2147483646 || a1[1] == -2147483645 )
  {
    *(_QWORD *)(a2 + 8) = a1[1];
    v6 = (const WCHAR *)a1[11];
    if ( v6 )
      v7 = lstrlenW(v6);
    else
      v7 = 0;
    v8 = v7 + 1;
    Memory = AllocateMemory((unsigned int)(2 * (v7 + 1)));
    *(_QWORD *)(a2 + 88) = Memory;
    if ( Memory )
    {
      StringCopyW(Memory, (_WORD *)a1[11], v8);
      v10 = (const WCHAR *)a1[10];
      v11 = v10 ? lstrlenW(v10) : 0;
      v12 = v11 + 1;
      v13 = AllocateMemory((unsigned int)(2 * (v11 + 1)));
      *(_QWORD *)(a2 + 80) = v13;
      if ( v13 )
      {
        StringCopyW(v13, (_WORD *)a1[10], v12);
        return 1;
      }
    }
    v15 = 14;
    goto LABEL_17;
  }
  SetLastError(0x800401E4);
  ResString2FromModule = GetResString2FromModule(v4, 105, 0);
  SetReason2(1, ResString2FromModule, L"COMPARE");
  return 0;
}

```

## disassembly

```asm
0x140009374  mov     [rsp+arg_0], rbx
0x140009379  mov     [rsp+arg_8], rsi
0x14000937e  push    rdi
0x14000937f  sub     rsp, 20h
0x140009383  mov     rdi, rdx
0x140009386  mov     rbx, rcx
0x140009389  test    rcx, rcx
0x14000938c  jz      loc_140009475
0x140009392  test    rdx, rdx
0x140009395  jz      loc_140009475
0x14000939b  cmp     dword ptr [rdx+10h], 1
0x14000939f  jnz     short loc_1400093E7
0x1400093a1  mov     rax, [rcx+8]
0x1400093a5  add     rax, 7FFFFFFEh
0x1400093ab  cmp     rax, 1
0x1400093af  jbe     short loc_1400093E7
0x1400093b1  mov     ecx, 800401E4h; dwErrCode
0x1400093b6  call    cs:__imp_SetLastError
0x1400093bd  nop     dword ptr [rax+rax+00h]
0x1400093c2  xor     r8d, r8d
0x1400093c5  lea     edx, [r8+69h]
0x1400093c9  call    GetResString2FromModule
0x1400093ce  lea     r8, aCompare_0; "COMPARE"
0x1400093d5  mov     rdx, rax
0x1400093d8  mov     ecx, 1
0x1400093dd  call    SetReason2
0x1400093e2  jmp     loc_14000947F
0x1400093e7  mov     rax, [rcx+8]
0x1400093eb  mov     [rdx+8], rax
0x1400093ef  mov     rcx, [rcx+58h]; lpString
0x1400093f3  test    rcx, rcx
0x1400093f6  jnz     short loc_1400093FC
0x1400093f8  xor     eax, eax
0x1400093fa  jmp     short loc_140009408
0x1400093fc  call    cs:__imp_lstrlenW
0x140009403  nop     dword ptr [rax+rax+00h]
0x140009408  lea     esi, [rax+1]
0x14000940b  lea     ecx, [rsi+rsi]; dwBytes
0x14000940e  call    AllocateMemory
0x140009413  mov     [rdi+58h], rax
0x140009417  test    rax, rax
0x14000941a  jz      short loc_14000946E
0x14000941c  mov     rdx, [rbx+58h]
0x140009420  mov     r8d, esi
0x140009423  mov     rcx, rax
0x140009426  call    StringCopyW
0x14000942b  mov     rcx, [rbx+50h]; lpString
0x14000942f  test    rcx, rcx
0x140009432  jnz     short loc_140009438
0x140009434  xor     eax, eax
0x140009436  jmp     short loc_140009444
0x140009438  call    cs:__imp_lstrlenW
0x14000943f  nop     dword ptr [rax+rax+00h]
0x140009444  lea     esi, [rax+1]
0x140009447  lea     ecx, [rsi+rsi]; dwBytes
0x14000944a  call    AllocateMemory
0x14000944f  mov     [rdi+50h], rax
0x140009453  test    rax, rax
0x140009456  jz      short loc_14000946E
0x140009458  mov     rdx, [rbx+50h]
0x14000945c  mov     r8d, esi
0x14000945f  mov     rcx, rax
0x140009462  call    StringCopyW
0x140009467  mov     eax, 1
0x14000946c  jmp     short loc_140009481
0x14000946e  mov     ecx, 0Eh
0x140009473  jmp     short loc_14000947A
0x140009475  mov     ecx, 57h ; 'W'
0x14000947a  call    SaveErrorMessage
0x14000947f  xor     eax, eax
0x140009481  mov     rbx, [rsp+28h+arg_0]
0x140009486  mov     rsi, [rsp+28h+arg_8]
0x14000948b  add     rsp, 20h
0x14000948f  pop     rdi
0x140009490  retn
```
