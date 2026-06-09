# ATL::IDispEventSimpleImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents>::InvokeFromFuncInfo(void (CRedbookWriterEvent::*)(void),ATL::_ATL_FUNC_INFO &,tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180016224`
- end: `0x1800163d7`
- name: `?InvokeFromFuncInfo@?$IDispEventSimpleImpl@$00VCRedbookWriterEvent@@$1?IID_DDiscFormat2TrackAtOnceEvents@@3U_GUID@@B@ATL@@QEAAJP8CRedbookWriterEvent@@EAAXXZAEAU_ATL_FUNC_INFO@2@PEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(int, int, int, int, VARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015fa0`

## callees

- `0x180016224`
- `0x1800184ce`
- `0x180018500`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001635a`
- `OLEAUT32!__imp_VariantInit` at `0x18001635a`
- `OLEAUT32!__imp_VariantClear` at `0x1800163a1`
- `OLEAUT32!__imp_VariantClear` at `0x1800163a1`
- `OLEAUT32!__imp_DispCallFunc` at `0x180016395`
- `OLEAUT32!__imp_DispCallFunc` at `0x180016395`

## pseudocode

```c
__int64 __fastcall ATL::IDispEventSimpleImpl<1,CRedbookWriterEvent,&_GUID const IID_DDiscFormat2TrackAtOnceEvents>::InvokeFromFuncInfo(
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
  __int64 v13; // r9
  __int64 v14; // r8
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
  v9 = (a1 - 8) & -(__int64)(a1 != 0);
  if ( (__int16)v5 > 8 )
    return 2147500037LL;
  memset_0(v27, 0, sizeof(v27));
  v10 = (_WORD)v5 != 0;
  v11 = *(_DWORD *)(a4 + 20);
  prgpvarg = (void *)((unsigned __int64)v27 & -(__int64)v10);
  if ( v11 > v8 )
    return 2147500037LL;
  if ( v11 )
  {
    memset_0(prgpvarg, 0, 8LL * v11);
    v13 = *(_QWORD *)(a4 + 8);
    v14 = 0;
    while ( *(_DWORD *)(v13 + 4 * v14) < v11 )
    {
      if ( *(_DWORD *)(v13 + 4 * v14) >= 8u )
        break;
      v15 = *(unsigned int *)(v13 + 4 * v14);
      if ( *((_QWORD *)prgpvarg + v15) )
        break;
      v16 = 3 * v14;
      v14 = (unsigned int)(v14 + 1);
      *((_QWORD *)prgpvarg + v15) = *(_QWORD *)a4 + 8 * v16;
      if ( (unsigned int)v14 >= v11 )
        goto LABEL_13;
    }
    return 2147500037LL;
  }
  v14 = 0;
LABEL_13:
  while ( (unsigned int)v14 < *(_DWORD *)(a4 + 16) )
  {
    v17 = *(_QWORD *)a4 + 24 * v14;
    v18 = (unsigned int)(*(__int16 *)(a3 + 6) - (_DWORD)v14 - 1);
    v14 = (unsigned int)(v14 + 1);
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
0x180016224  mov     [rsp-8+arg_0], rbx
0x180016229  push    rbp
0x18001622a  push    rsi
0x18001622b  push    rdi
0x18001622c  push    r12
0x18001622e  push    r13
0x180016230  push    r14
0x180016232  push    r15
0x180016234  lea     rbp, [rsp-1Fh]
0x180016239  sub     rsp, 0E0h
0x180016240  mov     rax, cs:__security_cookie
0x180016247  xor     rax, rsp
0x18001624a  mov     [rbp+4Fh+var_40], rax
0x18001624e  movsx   ebx, word ptr [r8+6]
0x180016253  mov     rsi, r9
0x180016256  mov     r15, r8
0x180016259  mov     r13, [rbp+4Fh+arg_20]
0x18001625d  mov     r14d, ebx
0x180016260  mov     [rsp+110h+var_D0], rdx
0x180016265  cmp     [r9+10h], ebx
0x180016269  jnz     loc_1800163AB
0x18001626f  lea     rax, [rcx-8]
0x180016273  neg     rcx
0x180016276  sbb     r12, r12
0x180016279  and     r12, rax
0x18001627c  mov     eax, 8
0x180016281  cmp     bx, ax
0x180016284  jg      loc_1800163AB
0x18001628a  xor     edx, edx; Val
0x18001628c  lea     r8d, [rax+38h]; Size
0x180016290  lea     rcx, [rbp+4Fh+var_80]; void *
0x180016294  call    memset_0
0x180016299  neg     bx
0x18001629c  lea     rax, [rbp+4Fh+var_80]
0x1800162a0  mov     ebx, [rsi+14h]
0x1800162a3  sbb     rdi, rdi
0x1800162a6  and     rdi, rax
0x1800162a9  cmp     ebx, r14d
0x1800162ac  ja      loc_1800163AB
0x1800162b2  test    ebx, ebx
0x1800162b4  jz      short loc_18001630B
0x1800162b6  mov     r8d, ebx
0x1800162b9  xor     edx, edx; Val
0x1800162bb  shl     r8, 3; Size
0x1800162bf  mov     rcx, rdi; void *
0x1800162c2  call    memset_0
0x1800162c7  mov     r9, [rsi+8]
0x1800162cb  xor     r8d, r8d
0x1800162ce  cmp     [r9+r8*4], ebx
0x1800162d2  jnb     loc_1800163AB
0x1800162d8  cmp     dword ptr [r9+r8*4], 8
0x1800162dd  jnb     loc_1800163AB
0x1800162e3  mov     edx, [r9+r8*4]
0x1800162e7  cmp     qword ptr [rdi+rdx*8], 0
0x1800162ec  jnz     loc_1800163AB
0x1800162f2  mov     rax, [rsi]
0x1800162f5  lea     rcx, [r8+r8*2]
0x1800162f9  inc     r8d
0x1800162fc  lea     rcx, [rax+rcx*8]
0x180016300  mov     [rdi+rdx*8], rcx
0x180016304  cmp     r8d, ebx
0x180016307  jb      short loc_1800162CE
0x180016309  jmp     short loc_18001632C
0x18001630b  xor     r8d, r8d
0x18001630e  jmp     short loc_18001632C
0x180016310  mov     rax, [rsi]
0x180016313  lea     rcx, [r8+r8*2]
0x180016317  lea     rdx, [rax+rcx*8]
0x18001631b  movsx   eax, word ptr [r15+6]
0x180016320  sub     eax, r8d
0x180016323  dec     eax
0x180016325  inc     r8d
0x180016328  mov     [rdi+rax*8], rdx
0x18001632c  cmp     r8d, [rsi+10h]
0x180016330  jb      short loc_180016310
0x180016332  lea     rax, CComStdCallThunkHelper
0x180016339  mov     [rbp+4Fh+var_C0], r12
0x18001633d  mov     [rbp+4Fh+var_A8], rax
0x180016341  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180016345  lea     rax, [rbp+4Fh+var_A8]
0x180016349  mov     [rbp+4Fh+pvInstance], rax
0x18001634d  mov     rax, [rsp+110h+var_D0]
0x180016352  movaps  xmm0, xmmword ptr [rax]
0x180016355  movdqu  [rbp+4Fh+var_B8], xmm0
0x18001635a  call    cs:__imp_VariantInit
0x180016360  movsx   ecx, word ptr [r15+6]
0x180016365  lea     rax, [r15+8]
0x180016369  movzx   r9d, word ptr [r15+4]; vtReturn
0x18001636e  lea     rdx, [rbp+4Fh+pvarg]
0x180016372  mov     r8d, [r15]; cc
0x180016375  test    r13, r13
0x180016378  cmovnz  rdx, r13
0x18001637c  mov     [rsp+110h+pvargResult], rdx; pvargResult
0x180016381  xor     edx, edx; oVft
0x180016383  mov     [rsp+110h+prgpvarg], rdi; prgpvarg
0x180016388  mov     [rsp+110h+prgvt], rax; prgvt
0x18001638d  mov     [rsp+110h+cActuals], ecx; cActuals
0x180016391  lea     rcx, [rbp+4Fh+pvInstance]; pvInstance
0x180016395  call    cs:__imp_DispCallFunc
0x18001639b  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18001639f  mov     ebx, eax
0x1800163a1  call    cs:__imp_VariantClear
0x1800163a7  mov     eax, ebx
0x1800163a9  jmp     short loc_1800163B0
0x1800163ab  mov     eax, 80004005h
0x1800163b0  mov     rcx, [rbp+4Fh+var_40]
0x1800163b4  xor     rcx, rsp; StackCookie
0x1800163b7  call    __security_check_cookie
0x1800163bc  mov     rbx, [rsp+110h+arg_0]
0x1800163c4  add     rsp, 0E0h
0x1800163cb  pop     r15
0x1800163cd  pop     r14
0x1800163cf  pop     r13
0x1800163d1  pop     r12
0x1800163d3  pop     rdi
0x1800163d4  pop     rsi
0x1800163d5  pop     rbp
0x1800163d6  retn
```
