# CDefragOperation::_OptimizeMoveForVolsnap(unsigned __int64,int *)

- ea: `0x1800081d4`
- end: `0x180008358`
- name: `?_OptimizeMoveForVolsnap@CDefragOperation@@IEAAJ_KPEAH@Z`
- size: `388`
- prototype: `__int64 __fastcall(CDefragOperation *__hidden this, unsigned __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180031a5c`

## callees

- `0x180006400`
- `0x1800081d4`
- `0x180046494`
- `0x18004a92c`

## import_xrefs

- `SXSHARED!SxTracerGetThreadContextRetail` at `0x180008226`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x180008226`

## string_xrefs

- `0x180008207`: `CDefragOperation::_OptimizeMoveForVolsnap`

## pseudocode

```c
__int64 __fastcall CDefragOperation::_OptimizeMoveForVolsnap(CDefragOperation *this, unsigned __int64 a2, int *a3)
{
  int ThreadContextRetail; // eax
  CSxGlobalTracer *v7; // rcx
  unsigned int v8; // ebx
  __int64 v10; // rdx
  unsigned int v11; // [rsp+20h] [rbp-40h] BYREF
  __int64 v12; // [rsp+24h] [rbp-3Ch]
  __int16 v13; // [rsp+2Ch] [rbp-34h]
  const char *v14; // [rsp+30h] [rbp-30h]
  __int128 v15; // [rsp+38h] [rbp-28h] BYREF
  __int64 v16; // [rsp+48h] [rbp-18h]
  int v17; // [rsp+50h] [rbp-10h]

  v11 = 0;
  v12 = 643;
  v13 = 1;
  v14 = "CDefragOperation::_OptimizeMoveForVolsnap";
  v15 = 0;
  v16 = 0;
  v17 = 0;
  ThreadContextRetail = SxTracerGetThreadContextRetail((char *)&v15 + 8);
  if ( ThreadContextRetail >= 0 )
  {
    *(_QWORD *)&v15 = *(_QWORD *)(*((_QWORD *)&v15 + 1) + 32LL);
    *(_QWORD *)(*((_QWORD *)&v15 + 1) + 32LL) = &v11;
LABEL_3:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_4;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids,
      (unsigned int)ThreadContextRetail);
    goto LABEL_3;
  }
LABEL_4:
  if ( v13 )
  {
    if ( v13 == 1 )
    {
      if ( v7 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v7 + 7) & 0x20000000) == 0 )
        goto LABEL_8;
      v10 = 12;
    }
    else
    {
      if ( v7 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v7 + 7) & 0x20000) == 0 )
        goto LABEL_8;
      v10 = 13;
    }
  }
  else
  {
    if ( v7 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v7 + 7) & 0x8000000) == 0 )
      goto LABEL_8;
    v10 = 11;
  }
  WPP_SF_s(*((_QWORD *)v7 + 2), v10, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids, v14);
LABEL_8:
  if ( a3 )
  {
    *a3 = 0;
    v8 = 0;
    LOWORD(v12) = 647;
    *a3 = a2 >= (unsigned int)(4 * *((_DWORD *)this + 65));
  }
  else
  {
    v8 = -2147024809;
    WORD1(v12) = 647;
  }
  v11 = v8;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11);
  return v8;
}

```

## disassembly

```asm
0x1800081d4  push    rbp
0x1800081d6  push    rbx
0x1800081d7  push    rsi
0x1800081d8  push    rdi
0x1800081d9  push    r13
0x1800081db  push    r14
0x1800081dd  push    r15
0x1800081df  mov     rbp, rsp
0x1800081e2  sub     rsp, 60h
0x1800081e6  mov     rdi, r8
0x1800081e9  mov     rsi, rdx
0x1800081ec  mov     r14, rcx
0x1800081ef  xor     r15d, r15d
0x1800081f2  mov     [rbp+var_40], r15d
0x1800081f6  mov     [rbp+var_3C], 283h
0x1800081fe  lea     r13d, [r15+1]
0x180008202  mov     [rbp+var_34], r13w
0x180008207  lea     rax, aCdefragoperati_25; "CDefragOperation::_OptimizeMoveForVolsn"...
0x18000820e  mov     [rbp+var_30], rax
0x180008212  xorps   xmm0, xmm0
0x180008215  movdqu  [rbp+var_28], xmm0
0x18000821a  mov     [rbp+var_18], r15
0x18000821e  mov     [rbp+var_10], r15d
0x180008222  lea     rcx, [rbp+var_28+8]
0x180008226  call    cs:__imp_SxTracerGetThreadContextRetail
0x18000822c  lea     rbx, WPP_GLOBAL_Control
0x180008233  test    eax, eax
0x180008235  js      loc_1800082EE
0x18000823b  mov     rcx, qword ptr [rbp+var_28+8]
0x18000823f  mov     rax, [rcx+20h]
0x180008243  mov     qword ptr [rbp+var_28], rax
0x180008247  lea     rax, [rbp+var_40]
0x18000824b  mov     [rcx+20h], rax
0x18000824f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008256  movzx   eax, [rbp+var_34]
0x18000825a  test    ax, ax
0x18000825d  jz      loc_180008325
0x180008263  cmp     ax, r13w
0x180008267  jnz     short loc_1800082C5
0x180008269  cmp     rcx, rbx
0x18000826c  jz      short loc_18000827B
0x18000826e  test    dword ptr [rcx+1Ch], 20000000h
0x180008275  jnz     loc_180008342
0x18000827b  mov     eax, 287h
0x180008280  test    rdi, rdi
0x180008283  jz      loc_180008349
0x180008289  mov     [rdi], r15d
0x18000828c  mov     ebx, r15d
0x18000828f  mov     word ptr [rbp+var_3C], ax
0x180008293  mov     ecx, [r14+104h]
0x18000829a  shl     ecx, 2
0x18000829d  mov     eax, r15d
0x1800082a0  cmp     rsi, rcx
0x1800082a3  setnb   al
0x1800082a6  mov     [rdi], eax
0x1800082a8  mov     [rbp+var_40], ebx
0x1800082ab  lea     rcx, [rbp+var_40]; this
0x1800082af  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800082b4  mov     eax, ebx
0x1800082b6  add     rsp, 60h
0x1800082ba  pop     r15
0x1800082bc  pop     r14
0x1800082be  pop     r13
0x1800082c0  pop     rdi
0x1800082c1  pop     rsi
0x1800082c2  pop     rbx
0x1800082c3  pop     rbp
0x1800082c4  retn
0x1800082c5  cmp     rcx, rbx
0x1800082c8  jz      short loc_18000827B
0x1800082ca  test    dword ptr [rcx+1Ch], 20000h
0x1800082d1  jz      short loc_18000827B
0x1800082d3  mov     edx, 0Dh
0x1800082d8  mov     r9, [rbp+var_30]
0x1800082dc  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x1800082e3  mov     rcx, [rcx+10h]
0x1800082e7  call    WPP_SF_s
0x1800082ec  jmp     short loc_18000827B
0x1800082ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082f5  cmp     rcx, rbx
0x1800082f8  jz      loc_180008256
0x1800082fe  test    [rcx+1Ch], r13b
0x180008302  jz      loc_180008256
0x180008308  mov     edx, 0Ah
0x18000830d  mov     r9d, eax
0x180008310  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x180008317  mov     rcx, [rcx+10h]
0x18000831b  call    WPP_SF_d
0x180008320  jmp     loc_18000824F
0x180008325  cmp     rcx, rbx
0x180008328  jz      loc_18000827B
0x18000832e  test    dword ptr [rcx+1Ch], 8000000h
0x180008335  jz      loc_18000827B
0x18000833b  mov     edx, 0Bh
0x180008340  jmp     short loc_1800082D8
0x180008342  mov     edx, 0Ch
0x180008347  jmp     short loc_1800082D8
0x180008349  mov     ebx, 80070057h
0x18000834e  mov     word ptr [rbp+var_3C+2], ax
0x180008352  jmp     loc_1800082A8
```
