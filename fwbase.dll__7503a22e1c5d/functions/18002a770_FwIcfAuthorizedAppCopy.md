# FwIcfAuthorizedAppCopy

- ea: `0x18002a770`
- end: `0x18002a8a7`
- name: `FwIcfAuthorizedAppCopy`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800045f0`
- `0x1800047e0`
- `0x180004840`
- `0x180004c80`
- `0x18002a770`
- `0x18002abe0`

## string_xrefs

- `0x18002a7f7`: `FwIcfAuthorizedAppCopy`
- `0x18002a829`: `FwIcfAuthorizedAppCopy`

## pseudocode

```c
__int64 __fastcall FwIcfAuthorizedAppCopy(__int64 a1, __int64 a2)
{
  _WORD *v4; // rcx
  int v5; // ebx
  __int64 v6; // rax
  __int64 v7; // xmm1_8
  __int128 v8; // xmm0
  __int64 v9; // rax
  __int128 v11; // [rsp+20h] [rbp-20h] BYREF
  __int64 v12; // [rsp+30h] [rbp-10h]
  __int64 v13; // [rsp+60h] [rbp+20h] BYREF
  __int64 v14; // [rsp+68h] [rbp+28h] BYREF
  __int64 v15; // [rsp+70h] [rbp+30h] BYREF

  v13 = 0;
  v14 = 0;
  v4 = *(_WORD **)a1;
  v15 = 0;
  v11 = 0;
  v12 = 0;
  v5 = FwStringCopy(v4, &v13);
  if ( v5 >= 0
    && (v5 = FwStringCopy(*(_WORD **)(a1 + 8), &v14), v5 >= 0)
    && (v5 = FwStringCopy(*(_WORD **)(a1 + 16), &v15), v5 >= 0)
    && (v5 = FwIcfSubNetsCopy(a1 + 24, &v11), v5 >= 0) )
  {
    v6 = v13;
    *(_OWORD *)a2 = *(_OWORD *)a1;
    *(_OWORD *)(a2 + 16) = *(_OWORD *)(a1 + 16);
    *(_OWORD *)(a2 + 32) = *(_OWORD *)(a1 + 32);
    *(_OWORD *)(a2 + 48) = *(_OWORD *)(a1 + 48);
    *(_OWORD *)(a2 + 64) = *(_OWORD *)(a1 + 64);
    *(_OWORD *)(a2 + 80) = *(_OWORD *)(a1 + 80);
    v7 = v12;
    *(_OWORD *)(a2 + 96) = *(_OWORD *)(a1 + 96);
    *(_QWORD *)a2 = v6;
    v8 = v11;
    *(_QWORD *)(a2 + 8) = v14;
    v9 = v15;
    *(_OWORD *)(a2 + 24) = v8;
    *(_QWORD *)(a2 + 16) = v9;
    *(_QWORD *)(a2 + 40) = v7;
  }
  else
  {
    FwReportReturnError("FwIcfAuthorizedAppCopy", (unsigned int)v5);
    FwIcfSubNetsDestroy(&v11);
    FwFree(v15);
    FwFree(v14);
    FwFree(v13);
    return (unsigned int)FwReportReturnError("FwIcfAuthorizedAppCopy", (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002a770  mov     [rsp-18h+arg_18], rbx
0x18002a775  push    rbp
0x18002a776  push    rsi
0x18002a777  push    rdi
0x18002a778  mov     rbp, rsp
0x18002a77b  sub     rsp, 40h
0x18002a77f  mov     rsi, rdx
0x18002a782  mov     [rbp+arg_0], 0
0x18002a78a  mov     rdi, rcx
0x18002a78d  mov     [rbp+arg_8], 0
0x18002a795  mov     rcx, [rcx]; Src
0x18002a798  lea     rdx, [rbp+arg_0]
0x18002a79c  xorps   xmm0, xmm0
0x18002a79f  mov     [rbp+arg_10], 0
0x18002a7a7  xor     eax, eax
0x18002a7a9  movups  [rbp+var_20], xmm0
0x18002a7ad  mov     [rbp+var_10], rax
0x18002a7b1  call    FwStringCopy
0x18002a7b6  mov     ebx, eax
0x18002a7b8  test    eax, eax
0x18002a7ba  js      short loc_18002A7F5
0x18002a7bc  mov     rcx, [rdi+8]; Src
0x18002a7c0  lea     rdx, [rbp+arg_8]
0x18002a7c4  call    FwStringCopy
0x18002a7c9  mov     ebx, eax
0x18002a7cb  test    eax, eax
0x18002a7cd  js      short loc_18002A7F5
0x18002a7cf  mov     rcx, [rdi+10h]; Src
0x18002a7d3  lea     rdx, [rbp+arg_10]
0x18002a7d7  call    FwStringCopy
0x18002a7dc  mov     ebx, eax
0x18002a7de  test    eax, eax
0x18002a7e0  js      short loc_18002A7F5
0x18002a7e2  lea     rcx, [rdi+18h]
0x18002a7e6  lea     rdx, [rbp+var_20]
0x18002a7ea  call    FwIcfSubNetsCopy
0x18002a7ef  mov     ebx, eax
0x18002a7f1  test    eax, eax
0x18002a7f3  jns     short loc_18002A839
0x18002a7f5  mov     edx, ebx
0x18002a7f7  lea     rcx, aFwicfauthorize_3; "FwIcfAuthorizedAppCopy"
0x18002a7fe  call    FwReportReturnError
0x18002a803  lea     rcx, [rbp+var_20]
0x18002a807  call    FwIcfSubNetsDestroy
0x18002a80c  mov     rcx, [rbp+arg_10]
0x18002a810  call    FwFree
0x18002a815  mov     rcx, [rbp+arg_8]
0x18002a819  call    FwFree
0x18002a81e  mov     rcx, [rbp+arg_0]
0x18002a822  call    FwFree
0x18002a827  mov     edx, ebx
0x18002a829  lea     rcx, aFwicfauthorize_3; "FwIcfAuthorizedAppCopy"
0x18002a830  call    FwReportReturnError
0x18002a835  mov     ebx, eax
0x18002a837  jmp     short loc_18002A898
0x18002a839  movups  xmm0, xmmword ptr [rdi]
0x18002a83c  mov     rax, [rbp+arg_0]
0x18002a840  movups  xmmword ptr [rsi], xmm0
0x18002a843  movups  xmm1, xmmword ptr [rdi+10h]
0x18002a847  movups  xmmword ptr [rsi+10h], xmm1
0x18002a84b  movups  xmm0, xmmword ptr [rdi+20h]
0x18002a84f  movups  xmmword ptr [rsi+20h], xmm0
0x18002a853  movups  xmm1, xmmword ptr [rdi+30h]
0x18002a857  movups  xmmword ptr [rsi+30h], xmm1
0x18002a85b  movups  xmm0, xmmword ptr [rdi+40h]
0x18002a85f  movups  xmmword ptr [rsi+40h], xmm0
0x18002a863  movups  xmm1, xmmword ptr [rdi+50h]
0x18002a867  movups  xmmword ptr [rsi+50h], xmm1
0x18002a86b  movups  xmm0, xmmword ptr [rdi+60h]
0x18002a86f  movsd   xmm1, [rbp+var_10]
0x18002a874  movups  xmmword ptr [rsi+60h], xmm0
0x18002a878  mov     [rsi], rax
0x18002a87b  mov     rax, [rbp+arg_8]
0x18002a87f  movups  xmm0, [rbp+var_20]
0x18002a883  mov     [rsi+8], rax
0x18002a887  mov     rax, [rbp+arg_10]
0x18002a88b  movups  xmmword ptr [rsi+18h], xmm0
0x18002a88f  mov     [rsi+10h], rax
0x18002a893  movsd   qword ptr [rsi+28h], xmm1
0x18002a898  mov     eax, ebx
0x18002a89a  mov     rbx, [rsp+40h+arg_18]
0x18002a89f  add     rsp, 40h
0x18002a8a3  pop     rdi
0x18002a8a4  pop     rsi
0x18002a8a5  pop     rbp
0x18002a8a6  retn
```
