# ParseDeleteCmdLine

- ea: `0x14000752c`
- end: `0x14000782d`
- name: `ParseDeleteCmdLine`
- size: `769`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140006f9c`

## callees

- `0x140001e90`
- `0x140002b70`
- `0x14000752c`
- `0x14000c62c`
- `0x14000cd48`
- `0x14000d010`
- `0x14000daa4`
- `0x14000e228`
- `0x14000e450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400075cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400077c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400077f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400075cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400077c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400077f4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140007650`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140007650`

## string_xrefs

- `0x1400075e3`: `DELETE`
- `0x1400077d5`: `DELETE`
- `0x140007586`: `DELETE`

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
  if ( !(unsigned int)BreakDownKeyString(*(_QWORD *)(a2 + 16), a3) )
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
0x14000752c  push    rbx
0x14000752e  push    rbp
0x14000752f  push    rsi
0x140007530  push    rdi
0x140007531  push    r12
0x140007533  push    r13
0x140007535  push    r14
0x140007537  push    r15
0x140007539  sub     rsp, 28h
0x14000753d  mov     rdi, r9
0x140007540  mov     rsi, r8
0x140007543  mov     r14, rdx
0x140007546  mov     r13d, ecx
0x140007549  test    ecx, ecx
0x14000754b  jz      loc_140007810
0x140007551  test    rdx, rdx
0x140007554  jz      loc_140007810
0x14000755a  test    r8, r8
0x14000755d  jz      loc_140007810
0x140007563  test    r9, r9
0x140007566  jz      loc_140007810
0x14000756c  cmp     dword ptr [r8], 0Bh
0x140007570  ja      loc_140007810
0x140007576  lea     eax, [rcx-3]
0x140007579  cmp     eax, 4
0x14000757c  ja      loc_1400077EF
0x140007582  mov     rcx, [r14+8]; lpString1
0x140007586  lea     rdx, aDelete; "DELETE"
0x14000758d  xor     r9d, r9d
0x140007590  call    StringCompareExW
0x140007595  test    eax, eax
0x140007597  jnz     loc_140007810
0x14000759d  mov     rcx, [r14+10h]; lpString
0x1400075a1  lea     rdx, aHH; "-?|/?|-h|/h"
0x1400075a8  call    InString
0x1400075ad  mov     ebx, 1
0x1400075b2  cmp     eax, ebx
0x1400075b4  jnz     short loc_1400075F4
0x1400075b6  lea     ebp, [rbx+2]
0x1400075b9  cmp     r13d, ebp
0x1400075bc  jnz     short loc_1400075C7
0x1400075be  mov     [rdi], ebx
0x1400075c0  mov     eax, ebx
0x1400075c2  jmp     loc_14000781C
0x1400075c7  mov     ecx, 800401E4h; dwErrCode
0x1400075cc  call    cs:__imp_SetLastError
0x1400075d2  xor     r8d, r8d
0x1400075d5  lea     edx, [r8+67h]
0x1400075d9  call    GetResString2FromModule
0x1400075de  mov     ecx, ebx
0x1400075e0  mov     rdx, rax
0x1400075e3  lea     r8, aDelete_0; "DELETE"
0x1400075ea  call    SetReason2
0x1400075ef  jmp     loc_14000781A
0x1400075f4  mov     rcx, [r14+10h]
0x1400075f8  mov     rdx, rsi
0x1400075fb  call    BreakDownKeyString
0x140007600  test    eax, eax
0x140007602  jz      loc_14000781A
0x140007608  xor     edi, edi
0x14000760a  xor     r15d, r15d
0x14000760d  lea     ebp, [rdi+3]
0x140007610  cmp     r13d, ebp
0x140007613  jbe     loc_1400077E6
0x140007619  mov     r12d, ebp
0x14000761c  lea     rdx, aV_0; "/v"
0x140007623  xor     r9d, r9d
0x140007626  mov     rcx, [r14+r12*8]; lpString1
0x14000762a  call    StringCompareExW
0x14000762f  test    eax, eax
0x140007631  jnz     short loc_14000768E
0x140007633  cmp     r15d, ebx
0x140007636  jz      loc_1400077BB
0x14000763c  inc     ebp
0x14000763e  cmp     ebp, r13d
0x140007641  jnb     loc_1400077BB
0x140007647  mov     rcx, [r14+rbp*8]; lpString
0x14000764b  test    rcx, rcx
0x14000764e  jz      short loc_140007656
0x140007650  call    cs:__imp_lstrlenW
0x140007656  inc     eax
0x140007658  mov     [rsp+68h+arg_0], eax
0x14000765c  lea     ecx, ds:0Ah[rax*2]; dwBytes
0x140007663  call    AllocateMemory
0x140007668  mov     [rsi+60h], rax
0x14000766c  test    rax, rax
0x14000766f  jz      loc_1400077AD
0x140007675  mov     r8d, [rsp+68h+arg_0]
0x14000767a  mov     rcx, rax
0x14000767d  mov     rdx, [r14+rbp*8]
0x140007681  mov     r15d, ebx
0x140007684  call    StringCopyW
0x140007689  jmp     loc_1400077A0
0x14000768e  mov     rcx, [r14+r12*8]; lpString1
0x140007692  lea     rdx, aVe_0; "/ve"
0x140007699  xor     r9d, r9d
0x14000769c  call    StringCompareExW
0x1400076a1  test    eax, eax
0x1400076a3  jnz     short loc_1400076CB
0x1400076a5  cmp     r15d, ebx
0x1400076a8  jz      loc_1400077BB
0x1400076ae  lea     ecx, [rax+4]; dwBytes
0x1400076b1  call    AllocateMemory
0x1400076b6  mov     [rsi+60h], rax
0x1400076ba  test    rax, rax
0x1400076bd  jz      loc_1400077AD
0x1400076c3  mov     r15d, ebx
0x1400076c6  jmp     loc_1400077A0
0x1400076cb  mov     rcx, [r14+r12*8]; lpString1
0x1400076cf  lea     rdx, aVa; "/va"
0x1400076d6  xor     r9d, r9d
0x1400076d9  call    StringCompareExW
0x1400076de  test    eax, eax
0x1400076e0  jnz     short loc_1400076F6
0x1400076e2  cmp     r15d, ebx
0x1400076e5  jz      loc_1400077BB
0x1400076eb  mov     r15d, ebx
0x1400076ee  mov     [rsi+1Ch], ebx
0x1400076f1  jmp     loc_1400077A0
0x1400076f6  mov     rcx, [r14+r12*8]; lpString1
0x1400076fa  lea     rdx, asc_140010CFC; "/f"
0x140007701  xor     r9d, r9d
0x140007704  call    StringCompareExW
0x140007709  test    eax, eax
0x14000770b  jnz     short loc_14000771E
0x14000770d  cmp     [rsi+18h], ebx
0x140007710  jz      loc_1400077BB
0x140007716  mov     [rsi+18h], ebx
0x140007719  jmp     loc_1400077A0
0x14000771e  mov     rcx, [r14+r12*8]; lpString1
0x140007722  lea     rdx, aReg32; "/reg:32"
0x140007729  xor     r9d, r9d
0x14000772c  call    StringCompareExW
0x140007731  test    eax, eax
0x140007733  jz      short loc_14000778E
0x140007735  mov     rcx, [r14+r12*8]; lpString1
0x140007739  lea     rdx, aReg32_0; "-reg:32"
0x140007740  xor     r9d, r9d
0x140007743  call    StringCompareExW
0x140007748  test    eax, eax
0x14000774a  jz      short loc_14000778E
0x14000774c  mov     rcx, [r14+r12*8]; lpString1
0x140007750  lea     rdx, aReg64_0; "/reg:64"
0x140007757  xor     r9d, r9d
0x14000775a  call    StringCompareExW
0x14000775f  test    eax, eax
0x140007761  jz      short loc_14000777A
0x140007763  mov     rcx, [r14+r12*8]; lpString1
0x140007767  lea     rdx, aReg64; "-reg:64"
0x14000776e  xor     r9d, r9d
0x140007771  call    StringCompareExW
0x140007776  test    eax, eax
0x140007778  jnz     short loc_1400077BB
0x14000777a  cmp     [rsi+8Ch], edi
0x140007780  jnz     short loc_1400077BB
0x140007782  mov     dword ptr [rsi+8Ch], 100h
0x14000778c  jmp     short loc_1400077A0
0x14000778e  cmp     [rsi+8Ch], edi
0x140007794  jnz     short loc_1400077BB
0x140007796  mov     dword ptr [rsi+8Ch], 200h
0x1400077a0  add     ebp, ebx
0x1400077a2  cmp     ebp, r13d
0x1400077a5  jb      loc_140007619
0x1400077ab  jmp     short loc_1400077E6
0x1400077ad  mov     ecx, 0Eh
0x1400077b2  mov     edi, ecx
0x1400077b4  call    SaveErrorMessage
0x1400077b9  jmp     short loc_1400077E6
0x1400077bb  mov     ecx, 800401E4h; dwErrCode
0x1400077c0  mov     edi, 67h ; 'g'
0x1400077c5  call    cs:__imp_SetLastError
0x1400077cb  xor     r8d, r8d
0x1400077ce  mov     edx, edi
0x1400077d0  call    GetResString2FromModule
0x1400077d5  lea     r8, aDelete_0; "DELETE"
0x1400077dc  mov     rdx, rax
0x1400077df  mov     ecx, ebx
0x1400077e1  call    SetReason2
0x1400077e6  xor     eax, eax
0x1400077e8  test    edi, edi
0x1400077ea  setz    al
0x1400077ed  jmp     short loc_14000781C
0x1400077ef  mov     ecx, 800401E4h; dwErrCode
0x1400077f4  call    cs:__imp_SetLastError
0x1400077fa  xor     r8d, r8d
0x1400077fd  lea     edx, [r8+67h]
0x140007801  call    GetResString2FromModule
0x140007806  mov     ecx, 1
0x14000780b  jmp     loc_1400075E0
0x140007810  mov     ecx, 57h ; 'W'
0x140007815  call    SaveErrorMessage
0x14000781a  xor     eax, eax
0x14000781c  add     rsp, 28h
0x140007820  pop     r15
0x140007822  pop     r14
0x140007824  pop     r13
0x140007826  pop     r12
0x140007828  pop     rdi
0x140007829  pop     rsi
0x14000782a  pop     rbp
0x14000782b  pop     rbx
0x14000782c  retn
```
