# CTableManager::Insert(ulong)

- ea: `0x180005650`
- end: `0x1800057ef`
- name: `?Insert@CTableManager@@UEAAJK@Z`
- size: `415`
- prototype: `__int64 __fastcall(CTableManager *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180005650`
- `0x180006400`
- `0x180046494`
- `0x18004a92c`

## import_xrefs

- `ntdll!RtlInsertElementGenericTableAvl` at `0x18000570a`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18000570a`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x1800056a0`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x1800056a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTableManager::Insert(CTableManager *this, int a2)
{
  unsigned int v3; // ebx
  int ThreadContextRetail; // eax
  CSxGlobalTracer *v5; // rcx
  bool v6; // zf
  __int16 v7; // ax
  __int64 v9; // rdx
  unsigned int v10; // [rsp+20h] [rbp-40h] BYREF
  __int64 v11; // [rsp+24h] [rbp-3Ch]
  __int16 v12; // [rsp+2Ch] [rbp-34h]
  const char *v13; // [rsp+30h] [rbp-30h]
  __int128 v14; // [rsp+38h] [rbp-28h] BYREF
  __int64 v15; // [rsp+48h] [rbp-18h]
  int v16; // [rsp+50h] [rbp-10h]
  unsigned __int8 NewElement; // [rsp+80h] [rbp+20h] BYREF
  int Buffer; // [rsp+88h] [rbp+28h] BYREF

  Buffer = a2;
  v3 = 0;
  v10 = 0;
  v11 = 220;
  v12 = 1;
  v13 = "CTableManager::Insert";
  v14 = 0;
  v15 = 0;
  v16 = 0;
  ThreadContextRetail = SxTracerGetThreadContextRetail((char *)&v14 + 8);
  if ( ThreadContextRetail >= 0 )
  {
    *(_QWORD *)&v14 = *(_QWORD *)(*((_QWORD *)&v14 + 1) + 32LL);
    *(_QWORD *)(*((_QWORD *)&v14 + 1) + 32LL) = &v10;
LABEL_3:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_4;
  }
  v5 = WPP_GLOBAL_Control;
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
  if ( v12 )
  {
    if ( v12 == 1 )
    {
      if ( v5 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v5 + 7) & 0x20000000) == 0 )
        goto LABEL_8;
      v9 = 12;
LABEL_17:
      WPP_SF_s(*((_QWORD *)v5 + 2), v9, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids, v13);
      goto LABEL_8;
    }
    if ( v5 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x20000) != 0 )
    {
      v9 = 13;
      goto LABEL_17;
    }
  }
  else if ( v5 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x8000000) != 0 )
  {
    v9 = 11;
    goto LABEL_17;
  }
LABEL_8:
  NewElement = 0;
  v6 = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)((char *)this + 40), &Buffer, 4u, &NewElement) == 0;
  v7 = 232;
  if ( v6 )
  {
    v3 = -2147024882;
LABEL_13:
    WORD1(v11) = v7;
    goto LABEL_11;
  }
  LOWORD(v11) = 232;
  v7 = 237;
  if ( !NewElement )
  {
    v3 = -1996488684;
    goto LABEL_13;
  }
  LOWORD(v11) = 237;
  *((_DWORD *)this + 36) = 1;
LABEL_11:
  v10 = v3;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  return v3;
}

```

## disassembly

```asm
0x180005650  mov     [rsp-18h+arg_10], rbx
0x180005655  mov     [rsp-18h+arg_18], rsi
0x18000565a  mov     [rsp-18h+Buffer], edx
0x18000565e  push    rbp
0x18000565f  push    rdi
0x180005660  push    r15
0x180005662  mov     rbp, rsp
0x180005665  sub     rsp, 60h
0x180005669  mov     rdi, rcx
0x18000566c  xor     ebx, ebx
0x18000566e  mov     [rbp+var_40], ebx
0x180005671  mov     [rbp+var_3C], 0DCh
0x180005679  lea     r15d, [rbx+1]
0x18000567d  mov     [rbp+var_34], r15w
0x180005682  lea     rax, aCtablemanagerI; "CTableManager::Insert"
0x180005689  mov     [rbp+var_30], rax
0x18000568d  xorps   xmm0, xmm0
0x180005690  movdqu  [rbp+var_28], xmm0
0x180005695  mov     [rbp+var_18], rbx
0x180005699  mov     [rbp+var_10], ebx
0x18000569c  lea     rcx, [rbp+var_28+8]
0x1800056a0  call    cs:__imp_SxTracerGetThreadContextRetail
0x1800056a6  lea     rsi, WPP_GLOBAL_Control
0x1800056ad  test    eax, eax
0x1800056af  js      loc_180005794
0x1800056b5  mov     rcx, qword ptr [rbp+var_28+8]
0x1800056b9  mov     rax, [rcx+20h]
0x1800056bd  mov     qword ptr [rbp+var_28], rax
0x1800056c1  lea     rax, [rbp+var_40]
0x1800056c5  mov     [rcx+20h], rax
0x1800056c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056d0  movzx   eax, [rbp+var_34]
0x1800056d4  test    ax, ax
0x1800056d7  jz      loc_1800057CB
0x1800056dd  cmp     ax, r15w
0x1800056e1  jnz     short loc_180005761
0x1800056e3  cmp     rcx, rsi
0x1800056e6  jz      short loc_1800056F5
0x1800056e8  test    dword ptr [rcx+1Ch], 20000000h
0x1800056ef  jnz     loc_1800057E8
0x1800056f5  mov     [rbp+NewElement], bl
0x1800056f8  lea     rcx, [rdi+28h]; Table
0x1800056fc  lea     r9, [rbp+NewElement]; NewElement
0x180005700  mov     r8d, 4; BufferSize
0x180005706  lea     rdx, [rbp+Buffer]; Buffer
0x18000570a  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180005710  test    rax, rax
0x180005713  mov     eax, 0E8h
0x180005718  jz      short loc_180005756
0x18000571a  mov     word ptr [rbp+var_3C], ax
0x18000571e  mov     eax, 0EDh
0x180005723  cmp     [rbp+NewElement], bl
0x180005726  jz      short loc_18000578D
0x180005728  mov     word ptr [rbp+var_3C], ax
0x18000572c  mov     [rdi+90h], r15d
0x180005733  mov     [rbp+var_40], ebx
0x180005736  lea     rcx, [rbp+var_40]; this
0x18000573a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000573f  mov     eax, ebx
0x180005741  lea     r11, [rsp+60h+var_s0]
0x180005746  mov     rbx, [r11+30h]
0x18000574a  mov     rsi, [r11+38h]
0x18000574e  mov     rsp, r11
0x180005751  pop     r15
0x180005753  pop     rdi
0x180005754  pop     rbp
0x180005755  retn
0x180005756  mov     ebx, 8007000Eh
0x18000575b  mov     word ptr [rbp+var_3C+2], ax
0x18000575f  jmp     short loc_180005733
0x180005761  cmp     rcx, rsi
0x180005764  jz      short loc_1800056F5
0x180005766  test    dword ptr [rcx+1Ch], 20000h
0x18000576d  jz      short loc_1800056F5
0x18000576f  mov     edx, 0Dh
0x180005774  mov     r9, [rbp+var_30]
0x180005778  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x18000577f  mov     rcx, [rcx+10h]
0x180005783  call    WPP_SF_s
0x180005788  jmp     loc_1800056F5
0x18000578d  mov     ebx, 89000014h
0x180005792  jmp     short loc_18000575B
0x180005794  mov     rcx, cs:WPP_GLOBAL_Control
0x18000579b  cmp     rcx, rsi
0x18000579e  jz      loc_1800056D0
0x1800057a4  test    [rcx+1Ch], r15b
0x1800057a8  jz      loc_1800056D0
0x1800057ae  mov     edx, 0Ah
0x1800057b3  mov     r9d, eax
0x1800057b6  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x1800057bd  mov     rcx, [rcx+10h]
0x1800057c1  call    WPP_SF_d
0x1800057c6  jmp     loc_1800056C9
0x1800057cb  cmp     rcx, rsi
0x1800057ce  jz      loc_1800056F5
0x1800057d4  test    dword ptr [rcx+1Ch], 8000000h
0x1800057db  jz      loc_1800056F5
0x1800057e1  mov     edx, 0Bh
0x1800057e6  jmp     short loc_180005774
0x1800057e8  mov     edx, 0Ch
0x1800057ed  jmp     short loc_180005774
```
