# ATL::IDispEventSimpleImpl<0,CMsftDiscFormat2TrackAtOnce,&_GUID const IID_DWriteEngine2Events>::InvokeFromFuncInfo(void (CMsftDiscFormat2TrackAtOnce::*)(void),ATL::_ATL_FUNC_INFO &,tagDISPPARAMS *,tagVARIANT *)

- ea: `0x18000ac88`
- end: `0x18000ae36`
- name: `?InvokeFromFuncInfo@?$IDispEventSimpleImpl@$0A@VCMsftDiscFormat2TrackAtOnce@@$1?IID_DWriteEngine2Events@@3U_GUID@@B@ATL@@QEAAJP8CMsftDiscFormat2TrackAtOnce@@EAAXXZAEAU_ATL_FUNC_INFO@2@PEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(int, int, int, int, VARIANT *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bba0`
- `0x180026e70`
- `0x18002e650`
- `0x180038140`

## callees

- `0x18000ac88`
- `0x18004984a`
- `0x180049880`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000adb9`
- `OLEAUT32!__imp_VariantInit` at `0x18000adb9`
- `OLEAUT32!__imp_VariantClear` at `0x18000ae00`
- `OLEAUT32!__imp_VariantClear` at `0x18000ae00`
- `OLEAUT32!__imp_DispCallFunc` at `0x18000adf4`
- `OLEAUT32!__imp_DispCallFunc` at `0x18000adf4`

## pseudocode

```c
__int64 __fastcall ATL::IDispEventSimpleImpl<0,CMsftDiscFormat2TrackAtOnce,&_GUID const IID_DWriteEngine2Events>::InvokeFromFuncInfo(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        __int64 a4,
        VARIANT *a5)
{
  unsigned int v5; // ebx
  unsigned int v8; // r14d
  __int64 v9; // r12
  bool v10; // cf
  unsigned int v11; // ebx
  void *prgpvarg; // rdi
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rax
  VARIANTARG *pvargResult; // rdx
  unsigned int v20; // ebx
  _QWORD pvInstance[2]; // [rsp+48h] [rbp-79h] BYREF
  __int128 v24; // [rsp+58h] [rbp-69h]
  __int64 (__fastcall *v25)(); // [rsp+68h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-51h] BYREF
  _BYTE v27[64]; // [rsp+90h] [rbp-31h] BYREF

  v5 = *(__int16 *)(a3 + 6);
  v8 = v5;
  if ( *(_DWORD *)(a4 + 16) != v5 )
    return 2147500037LL;
  v9 = (a1 - 48) & -(__int64)(a1 != 0);
  if ( (__int16)v5 > 8 )
    return 2147500037LL;
  memset_0(v27, 0, sizeof(v27));
  v10 = (_WORD)v5 != 0;
  v11 = *(_DWORD *)(a4 + 20);
  prgpvarg = (void *)((unsigned __int64)v27 & -(__int64)v10);
  if ( v11 > v8 )
    return 2147500037LL;
  if ( v11 )
    memset_0(prgpvarg, 0, 8LL * v11);
  v13 = 0;
  while ( (unsigned int)v13 < v11 )
  {
    v14 = *(_QWORD *)(a4 + 8);
    if ( *(_DWORD *)(v14 + 4 * v13) >= v11 )
      return 2147500037LL;
    if ( *(_DWORD *)(v14 + 4 * v13) >= 8u )
      return 2147500037LL;
    v15 = *(unsigned int *)(v14 + 4 * v13);
    if ( *((_QWORD *)prgpvarg + v15) )
      return 2147500037LL;
    v16 = 3 * v13;
    v13 = (unsigned int)(v13 + 1);
    *((_QWORD *)prgpvarg + v15) = *(_QWORD *)a4 + 8 * v16;
  }
  while ( (unsigned int)v13 < *(_DWORD *)(a4 + 16) )
  {
    v17 = *(_QWORD *)a4 + 24 * v13;
    v18 = (unsigned int)(*(__int16 *)(a3 + 6) - (_DWORD)v13 - 1);
    v13 = (unsigned int)(v13 + 1);
    *((_QWORD *)prgpvarg + v18) = v17;
  }
  pvInstance[1] = v9;
  v25 = CComStdCallThunkHelper;
  pvInstance[0] = &v25;
  v24 = *a2;
  VariantInit(&pvarg);
  pvargResult = &pvarg;
  if ( a5 )
    pvargResult = a5;
  v20 = DispCallFunc(
          pvInstance,
          0,
          *(CALLCONV *)a3,
          *(_WORD *)(a3 + 4),
          *(__int16 *)(a3 + 6),
          (VARTYPE *)(a3 + 8),
          (VARIANTARG **)prgpvarg,
          pvargResult);
  VariantClear(&pvarg);
  return v20;
}

```

## disassembly

```asm
0x18000ac88  mov     [rsp-8+arg_0], rbx
0x18000ac8d  push    rbp
0x18000ac8e  push    rsi
0x18000ac8f  push    rdi
0x18000ac90  push    r12
0x18000ac92  push    r13
0x18000ac94  push    r14
0x18000ac96  push    r15
0x18000ac98  lea     rbp, [rsp-1Fh]
0x18000ac9d  sub     rsp, 0E0h
0x18000aca4  mov     rax, cs:__security_cookie
0x18000acab  xor     rax, rsp
0x18000acae  mov     [rbp+4Fh+var_40], rax
0x18000acb2  movsx   ebx, word ptr [r8+6]
0x18000acb7  mov     rsi, r9
0x18000acba  mov     r15, r8
0x18000acbd  mov     r13, [rbp+4Fh+arg_20]
0x18000acc1  mov     r14d, ebx
0x18000acc4  mov     [rsp+110h+var_D0], rdx
0x18000acc9  cmp     [r9+10h], ebx
0x18000accd  jnz     loc_18000AE0A
0x18000acd3  lea     rax, [rcx-30h]
0x18000acd7  neg     rcx
0x18000acda  sbb     r12, r12
0x18000acdd  and     r12, rax
0x18000ace0  mov     eax, 8
0x18000ace5  cmp     bx, ax
0x18000ace8  jg      loc_18000AE0A
0x18000acee  xor     edx, edx; Val
0x18000acf0  lea     r8d, [rax+38h]; Size
0x18000acf4  lea     rcx, [rbp+4Fh+var_80]; void *
0x18000acf8  call    memset_0
0x18000acfd  neg     bx
0x18000ad00  lea     rax, [rbp+4Fh+var_80]
0x18000ad04  mov     ebx, [rsi+14h]
0x18000ad07  sbb     rdi, rdi
0x18000ad0a  and     rdi, rax
0x18000ad0d  cmp     ebx, r14d
0x18000ad10  ja      loc_18000AE0A
0x18000ad16  test    ebx, ebx
0x18000ad18  jz      short loc_18000AD2B
0x18000ad1a  mov     r8d, ebx
0x18000ad1d  xor     edx, edx; Val
0x18000ad1f  shl     r8, 3; Size
0x18000ad23  mov     rcx, rdi; void *
0x18000ad26  call    memset_0
0x18000ad2b  xor     r8d, r8d
0x18000ad2e  cmp     r8d, ebx
0x18000ad31  jnb     short loc_18000AD8B
0x18000ad33  mov     rax, [rsi+8]
0x18000ad37  cmp     [rax+r8*4], ebx
0x18000ad3b  jnb     loc_18000AE0A
0x18000ad41  cmp     dword ptr [rax+r8*4], 8
0x18000ad46  jnb     loc_18000AE0A
0x18000ad4c  mov     edx, [rax+r8*4]
0x18000ad50  cmp     qword ptr [rdi+rdx*8], 0
0x18000ad55  jnz     loc_18000AE0A
0x18000ad5b  mov     rax, [rsi]
0x18000ad5e  lea     rcx, [r8+r8*2]
0x18000ad62  inc     r8d
0x18000ad65  lea     rcx, [rax+rcx*8]
0x18000ad69  mov     [rdi+rdx*8], rcx
0x18000ad6d  jmp     short loc_18000AD2E
0x18000ad6f  mov     rax, [rsi]
0x18000ad72  lea     rcx, [r8+r8*2]
0x18000ad76  lea     rdx, [rax+rcx*8]
0x18000ad7a  movsx   eax, word ptr [r15+6]
0x18000ad7f  sub     eax, r8d
0x18000ad82  dec     eax
0x18000ad84  inc     r8d
0x18000ad87  mov     [rdi+rax*8], rdx
0x18000ad8b  cmp     r8d, [rsi+10h]
0x18000ad8f  jb      short loc_18000AD6F
0x18000ad91  lea     rax, CComStdCallThunkHelper
0x18000ad98  mov     [rbp+4Fh+var_C0], r12
0x18000ad9c  mov     [rbp+4Fh+var_A8], rax
0x18000ada0  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18000ada4  lea     rax, [rbp+4Fh+var_A8]
0x18000ada8  mov     [rbp+4Fh+pvInstance], rax
0x18000adac  mov     rax, [rsp+110h+var_D0]
0x18000adb1  movaps  xmm0, xmmword ptr [rax]
0x18000adb4  movdqu  [rbp+4Fh+var_B8], xmm0
0x18000adb9  call    cs:__imp_VariantInit
0x18000adbf  movsx   ecx, word ptr [r15+6]
0x18000adc4  lea     rax, [r15+8]
0x18000adc8  movzx   r9d, word ptr [r15+4]; vtReturn
0x18000adcd  lea     rdx, [rbp+4Fh+pvarg]
0x18000add1  mov     r8d, [r15]; cc
0x18000add4  test    r13, r13
0x18000add7  cmovnz  rdx, r13
0x18000addb  mov     [rsp+110h+pvargResult], rdx; pvargResult
0x18000ade0  xor     edx, edx; oVft
0x18000ade2  mov     [rsp+110h+prgpvarg], rdi; prgpvarg
0x18000ade7  mov     [rsp+110h+prgvt], rax; prgvt
0x18000adec  mov     [rsp+110h+cActuals], ecx; cActuals
0x18000adf0  lea     rcx, [rbp+4Fh+pvInstance]; pvInstance
0x18000adf4  call    cs:__imp_DispCallFunc
0x18000adfa  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18000adfe  mov     ebx, eax
0x18000ae00  call    cs:__imp_VariantClear
0x18000ae06  mov     eax, ebx
0x18000ae08  jmp     short loc_18000AE0F
0x18000ae0a  mov     eax, 80004005h
0x18000ae0f  mov     rcx, [rbp+4Fh+var_40]
0x18000ae13  xor     rcx, rsp; StackCookie
0x18000ae16  call    __security_check_cookie
0x18000ae1b  mov     rbx, [rsp+110h+arg_0]
0x18000ae23  add     rsp, 0E0h
0x18000ae2a  pop     r15
0x18000ae2c  pop     r14
0x18000ae2e  pop     r13
0x18000ae30  pop     r12
0x18000ae32  pop     rdi
0x18000ae33  pop     rsi
0x18000ae34  pop     rbp
0x18000ae35  retn
```
