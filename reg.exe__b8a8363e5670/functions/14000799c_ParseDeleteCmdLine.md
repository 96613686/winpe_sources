# ParseDeleteCmdLine

- ea: `0x14000799c`
- end: `0x140007cb6`
- name: `ParseDeleteCmdLine`
- size: `794`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400073d4`

## callees

- `0x140001e90`
- `0x140002ce4`
- `0x14000799c`
- `0x14000ce50`
- `0x14000d694`
- `0x14000d990`
- `0x14000e600`
- `0x14000ee5c`
- `0x14000f0c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007a3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007c41`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007c76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007a3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007c41`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007c76`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140007ac6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140007ac6`

## string_xrefs

- `0x140007a59`: `DELETE`
- `0x140007c57`: `DELETE`
- `0x1400079f6`: `DELETE`

## pseudocode

```c
__int64 __fastcall ParseDeleteCmdLine(unsigned int a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  __int64 v9; // rcx
  __int64 ResString2FromModule; // rax
  __int64 v11; // r8
  int v12; // edi
  int v13; // r15d
  __int64 v14; // rbp
  int v15; // eax
  __int64 v16; // r8
  const WCHAR *v17; // rcx
  _WORD *Memory; // rax
  __int64 v19; // r8
  LPVOID v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // [rsp+70h] [rbp+8h]

  if ( !a1 || !a2 || !a3 || !a4 || *(_DWORD *)a3 > 0xBu )
    goto LABEL_45;
  if ( a1 - 3 > 4 )
  {
LABEL_11:
    SetLastError(0x800401E4);
    ResString2FromModule = GetResString2FromModule(v9, 103, 0);
    SetReason2(1, ResString2FromModule, L"DELETE");
    return 0;
  }
  if ( (unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8), L"DELETE", a3, 0) )
  {
LABEL_45:
    SaveErrorMessage(87);
    return 0;
  }
  if ( (unsigned int)InString(*(LPCWSTR *)(a2 + 16), L"-?|/?|-h|/h") == 1 )
  {
    if ( a1 == 3 )
    {
      *a4 = 1;
      return 1;
    }
    goto LABEL_11;
  }
  if ( !(unsigned int)BreakDownKeyString(*(const WCHAR **)(a2 + 16), (int *)a3) )
    return 0;
  v12 = 0;
  v13 = 0;
  LODWORD(v14) = 3;
  if ( a1 <= 3 )
    return v12 == 0;
  while ( 1 )
  {
    v15 = StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"/v", v11, 0);
    if ( v15 )
      break;
    if ( v13 == 1 )
      goto LABEL_42;
    v14 = (unsigned int)(v14 + 1);
    if ( (unsigned int)v14 >= a1 )
      goto LABEL_42;
    v17 = *(const WCHAR **)(a2 + 8 * v14);
    if ( v17 )
      v15 = lstrlenW(v17);
    v23 = v15 + 1;
    Memory = AllocateMemory((unsigned int)(2 * (v15 + 1) + 10));
    *(_QWORD *)(a3 + 96) = Memory;
    if ( !Memory )
    {
LABEL_41:
      v12 = 14;
      SaveErrorMessage(14);
      return v12 == 0;
    }
    v13 = 1;
    StringCopyW(Memory, *(_WORD **)(a2 + 8 * v14), v23);
LABEL_39:
    LODWORD(v14) = v14 + 1;
    if ( (unsigned int)v14 >= a1 )
      return v12 == 0;
  }
  if ( !(unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"/ve", v16, 0) )
  {
    if ( v13 == 1 )
      goto LABEL_42;
    v20 = AllocateMemory(4u);
    *(_QWORD *)(a3 + 96) = v20;
    if ( !v20 )
      goto LABEL_41;
    v13 = 1;
    goto LABEL_39;
  }
  if ( !(unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"/va", v19, 0) )
  {
    if ( v13 == 1 )
      goto LABEL_42;
    v13 = 1;
    *(_DWORD *)(a3 + 28) = 1;
    goto LABEL_39;
  }
  if ( !(unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"/f", v11, 0) )
  {
    if ( *(_DWORD *)(a3 + 24) == 1 )
      goto LABEL_42;
    *(_DWORD *)(a3 + 24) = 1;
    goto LABEL_39;
  }
  if ( !(unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"/reg:32", v11, 0)
    || !(unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"-reg:32", v11, 0) )
  {
    if ( *(_DWORD *)(a3 + 140) )
      goto LABEL_42;
    *(_DWORD *)(a3 + 140) = 512;
    goto LABEL_39;
  }
  if ( (!(unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"/reg:64", v11, 0)
     || !(unsigned int)StringCompareExW(*(PCNZWCH *)(a2 + 8LL * (unsigned int)v14), L"-reg:64", v11, 0))
    && !*(_DWORD *)(a3 + 140) )
  {
    *(_DWORD *)(a3 + 140) = 256;
    goto LABEL_39;
  }
LABEL_42:
  v12 = 103;
  SetLastError(0x800401E4);
  v22 = GetResString2FromModule(v21, 103, 0);
  SetReason2(1, v22, L"DELETE");
  return v12 == 0;
}

```

## disassembly

```asm
0x14000799c  push    rbx
0x14000799e  push    rbp
0x14000799f  push    rsi
0x1400079a0  push    rdi
0x1400079a1  push    r12
0x1400079a3  push    r13
0x1400079a5  push    r14
0x1400079a7  push    r15
0x1400079a9  sub     rsp, 28h
0x1400079ad  mov     rdi, r9
0x1400079b0  mov     rsi, r8
0x1400079b3  mov     r14, rdx
0x1400079b6  mov     r13d, ecx
0x1400079b9  test    ecx, ecx
0x1400079bb  jz      loc_140007C98
0x1400079c1  test    rdx, rdx
0x1400079c4  jz      loc_140007C98
0x1400079ca  test    r8, r8
0x1400079cd  jz      loc_140007C98
0x1400079d3  test    r9, r9
0x1400079d6  jz      loc_140007C98
0x1400079dc  cmp     dword ptr [r8], 0Bh
0x1400079e0  ja      loc_140007C98
0x1400079e6  lea     eax, [rcx-3]
0x1400079e9  cmp     eax, 4
0x1400079ec  ja      loc_140007C71
0x1400079f2  mov     rcx, [r14+8]; lpString1
0x1400079f6  lea     rdx, aDelete; "DELETE"
0x1400079fd  xor     r9d, r9d
0x140007a00  call    StringCompareExW
0x140007a05  test    eax, eax
0x140007a07  jnz     loc_140007C98
0x140007a0d  mov     rcx, [r14+10h]; lpString
0x140007a11  lea     rdx, aHH; "-?|/?|-h|/h"
0x140007a18  call    InString
0x140007a1d  mov     ebx, 1
0x140007a22  cmp     eax, ebx
0x140007a24  jnz     short loc_140007A6A
0x140007a26  lea     ebp, [rbx+2]
0x140007a29  cmp     r13d, ebp
0x140007a2c  jnz     short loc_140007A37
0x140007a2e  mov     [rdi], ebx
0x140007a30  mov     eax, ebx
0x140007a32  jmp     loc_140007CA4
0x140007a37  mov     ecx, 800401E4h; dwErrCode
0x140007a3c  call    cs:__imp_SetLastError
0x140007a43  nop     dword ptr [rax+rax+00h]
0x140007a48  xor     r8d, r8d
0x140007a4b  lea     edx, [r8+67h]
0x140007a4f  call    GetResString2FromModule
0x140007a54  mov     ecx, ebx
0x140007a56  mov     rdx, rax
0x140007a59  lea     r8, aDelete_0; "DELETE"
0x140007a60  call    SetReason2
0x140007a65  jmp     loc_140007CA2
0x140007a6a  mov     rcx, [r14+10h]
0x140007a6e  mov     rdx, rsi
0x140007a71  call    BreakDownKeyString
0x140007a76  test    eax, eax
0x140007a78  jz      loc_140007CA2
0x140007a7e  xor     edi, edi
0x140007a80  xor     r15d, r15d
0x140007a83  lea     ebp, [rdi+3]
0x140007a86  cmp     r13d, ebp
0x140007a89  jbe     loc_140007C68
0x140007a8f  mov     r12d, ebp
0x140007a92  lea     rdx, aV_0; "/v"
0x140007a99  xor     r9d, r9d
0x140007a9c  mov     rcx, [r14+r12*8]; lpString1
0x140007aa0  call    StringCompareExW
0x140007aa5  test    eax, eax
0x140007aa7  jnz     short loc_140007B0A
0x140007aa9  cmp     r15d, ebx
0x140007aac  jz      loc_140007C37
0x140007ab2  inc     ebp
0x140007ab4  cmp     ebp, r13d
0x140007ab7  jnb     loc_140007C37
0x140007abd  mov     rcx, [r14+rbp*8]; lpString
0x140007ac1  test    rcx, rcx
0x140007ac4  jz      short loc_140007AD2
0x140007ac6  call    cs:__imp_lstrlenW
0x140007acd  nop     dword ptr [rax+rax+00h]
0x140007ad2  inc     eax
0x140007ad4  mov     [rsp+68h+arg_0], eax
0x140007ad8  lea     ecx, ds:0Ah[rax*2]; dwBytes
0x140007adf  call    AllocateMemory
0x140007ae4  mov     [rsi+60h], rax
0x140007ae8  test    rax, rax
0x140007aeb  jz      loc_140007C29
0x140007af1  mov     r8d, [rsp+68h+arg_0]
0x140007af6  mov     rcx, rax
0x140007af9  mov     rdx, [r14+rbp*8]
0x140007afd  mov     r15d, ebx
0x140007b00  call    StringCopyW
0x140007b05  jmp     loc_140007C1C
0x140007b0a  mov     rcx, [r14+r12*8]; lpString1
0x140007b0e  lea     rdx, aVe_0; "/ve"
0x140007b15  xor     r9d, r9d
0x140007b18  call    StringCompareExW
0x140007b1d  test    eax, eax
0x140007b1f  jnz     short loc_140007B47
0x140007b21  cmp     r15d, ebx
0x140007b24  jz      loc_140007C37
0x140007b2a  lea     ecx, [rax+4]; dwBytes
0x140007b2d  call    AllocateMemory
0x140007b32  mov     [rsi+60h], rax
0x140007b36  test    rax, rax
0x140007b39  jz      loc_140007C29
0x140007b3f  mov     r15d, ebx
0x140007b42  jmp     loc_140007C1C
0x140007b47  mov     rcx, [r14+r12*8]; lpString1
0x140007b4b  lea     rdx, aVa; "/va"
0x140007b52  xor     r9d, r9d
0x140007b55  call    StringCompareExW
0x140007b5a  test    eax, eax
0x140007b5c  jnz     short loc_140007B72
0x140007b5e  cmp     r15d, ebx
0x140007b61  jz      loc_140007C37
0x140007b67  mov     r15d, ebx
0x140007b6a  mov     [rsi+1Ch], ebx
0x140007b6d  jmp     loc_140007C1C
0x140007b72  mov     rcx, [r14+r12*8]; lpString1
0x140007b76  lea     rdx, asc_140011CFC; "/f"
0x140007b7d  xor     r9d, r9d
0x140007b80  call    StringCompareExW
0x140007b85  test    eax, eax
0x140007b87  jnz     short loc_140007B9A
0x140007b89  cmp     [rsi+18h], ebx
0x140007b8c  jz      loc_140007C37
0x140007b92  mov     [rsi+18h], ebx
0x140007b95  jmp     loc_140007C1C
0x140007b9a  mov     rcx, [r14+r12*8]; lpString1
0x140007b9e  lea     rdx, aReg32; "/reg:32"
0x140007ba5  xor     r9d, r9d
0x140007ba8  call    StringCompareExW
0x140007bad  test    eax, eax
0x140007baf  jz      short loc_140007C0A
0x140007bb1  mov     rcx, [r14+r12*8]; lpString1
0x140007bb5  lea     rdx, aReg32_0; "-reg:32"
0x140007bbc  xor     r9d, r9d
0x140007bbf  call    StringCompareExW
0x140007bc4  test    eax, eax
0x140007bc6  jz      short loc_140007C0A
0x140007bc8  mov     rcx, [r14+r12*8]; lpString1
0x140007bcc  lea     rdx, aReg64_0; "/reg:64"
0x140007bd3  xor     r9d, r9d
0x140007bd6  call    StringCompareExW
0x140007bdb  test    eax, eax
0x140007bdd  jz      short loc_140007BF6
0x140007bdf  mov     rcx, [r14+r12*8]; lpString1
0x140007be3  lea     rdx, aReg64; "-reg:64"
0x140007bea  xor     r9d, r9d
0x140007bed  call    StringCompareExW
0x140007bf2  test    eax, eax
0x140007bf4  jnz     short loc_140007C37
0x140007bf6  cmp     [rsi+8Ch], edi
0x140007bfc  jnz     short loc_140007C37
0x140007bfe  mov     dword ptr [rsi+8Ch], 100h
0x140007c08  jmp     short loc_140007C1C
0x140007c0a  cmp     [rsi+8Ch], edi
0x140007c10  jnz     short loc_140007C37
0x140007c12  mov     dword ptr [rsi+8Ch], 200h
0x140007c1c  add     ebp, ebx
0x140007c1e  cmp     ebp, r13d
0x140007c21  jb      loc_140007A8F
0x140007c27  jmp     short loc_140007C68
0x140007c29  mov     ecx, 0Eh
0x140007c2e  mov     edi, ecx
0x140007c30  call    SaveErrorMessage
0x140007c35  jmp     short loc_140007C68
0x140007c37  mov     ecx, 800401E4h; dwErrCode
0x140007c3c  mov     edi, 67h ; 'g'
0x140007c41  call    cs:__imp_SetLastError
0x140007c48  nop     dword ptr [rax+rax+00h]
0x140007c4d  xor     r8d, r8d
0x140007c50  mov     edx, edi
0x140007c52  call    GetResString2FromModule
0x140007c57  lea     r8, aDelete_0; "DELETE"
0x140007c5e  mov     rdx, rax
0x140007c61  mov     ecx, ebx
0x140007c63  call    SetReason2
0x140007c68  xor     eax, eax
0x140007c6a  test    edi, edi
0x140007c6c  setz    al
0x140007c6f  jmp     short loc_140007CA4
0x140007c71  mov     ecx, 800401E4h; dwErrCode
0x140007c76  call    cs:__imp_SetLastError
0x140007c7d  nop     dword ptr [rax+rax+00h]
0x140007c82  xor     r8d, r8d
0x140007c85  lea     edx, [r8+67h]
0x140007c89  call    GetResString2FromModule
0x140007c8e  mov     ecx, 1
0x140007c93  jmp     loc_140007A56
0x140007c98  mov     ecx, 57h ; 'W'
0x140007c9d  call    SaveErrorMessage
0x140007ca2  xor     eax, eax
0x140007ca4  add     rsp, 28h
0x140007ca8  pop     r15
0x140007caa  pop     r14
0x140007cac  pop     r13
0x140007cae  pop     r12
0x140007cb0  pop     rdi
0x140007cb1  pop     rsi
0x140007cb2  pop     rbp
0x140007cb3  pop     rbx
0x140007cb4  retn
```
