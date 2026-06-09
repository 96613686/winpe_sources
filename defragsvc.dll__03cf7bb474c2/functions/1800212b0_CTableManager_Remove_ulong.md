# CTableManager::Remove(ulong)

- ea: `0x1800212b0`
- end: `0x180021428`
- name: `?Remove@CTableManager@@UEAAJK@Z`
- size: `376`
- prototype: `__int64 __fastcall(CTableManager *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x180006400`
- `0x1800212b0`
- `0x180046494`
- `0x18004a92c`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002135d`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002135d`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x180021300`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x180021300`

## string_xrefs

- `0x1800212e2`: `CTableManager::Remove`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTableManager::Remove(CTableManager *this, int a2)
{
  int ThreadContextRetail; // eax
  CSxGlobalTracer *v4; // rcx
  unsigned int v5; // ebx
  __int64 v7; // rdx
  int v8; // [rsp+20h] [rbp-40h] BYREF
  __int64 v9; // [rsp+24h] [rbp-3Ch]
  __int16 v10; // [rsp+2Ch] [rbp-34h]
  const char *v11; // [rsp+30h] [rbp-30h]
  __int128 v12; // [rsp+38h] [rbp-28h] BYREF
  __int64 v13; // [rsp+48h] [rbp-18h]
  int v14; // [rsp+50h] [rbp-10h]
  int Buffer; // [rsp+88h] [rbp+28h] BYREF

  Buffer = a2;
  v8 = 0;
  v9 = 265;
  v10 = 1;
  v11 = "CTableManager::Remove";
  v12 = 0;
  v13 = 0;
  v14 = 0;
  ThreadContextRetail = SxTracerGetThreadContextRetail((char *)&v12 + 8);
  if ( ThreadContextRetail >= 0 )
  {
    *(_QWORD *)&v12 = *(_QWORD *)(*((_QWORD *)&v12 + 1) + 32LL);
    *(_QWORD *)(*((_QWORD *)&v12 + 1) + 32LL) = &v8;
LABEL_3:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_4;
  }
  v4 = WPP_GLOBAL_Control;
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
  if ( v10 )
  {
    if ( v10 == 1 )
    {
      if ( v4 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v4 + 7) & 0x20000000) == 0 )
        goto LABEL_8;
      v7 = 12;
    }
    else
    {
      if ( v4 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v4 + 7) & 0x20000) == 0 )
        goto LABEL_8;
      v7 = 13;
    }
  }
  else
  {
    if ( v4 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v4 + 7) & 0x8000000) == 0 )
      goto LABEL_8;
    v7 = 11;
  }
  WPP_SF_s(*((_QWORD *)v4 + 2), v7, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids, v11);
LABEL_8:
  if ( RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)this + 40), &Buffer) )
  {
    *((_DWORD *)this + 36) = 1;
    v5 = v8;
  }
  else
  {
    v5 = 150995203;
    v8 = 150995203;
    LOWORD(v9) = 272;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return v5;
}

```

## disassembly

```asm
0x1800212b0  mov     [rsp-18h+arg_0], rbx
0x1800212b5  mov     [rsp-18h+arg_10], rsi
0x1800212ba  mov     [rsp-18h+Buffer], edx
0x1800212be  push    rbp
0x1800212bf  push    rdi
0x1800212c0  push    r14
0x1800212c2  mov     rbp, rsp
0x1800212c5  sub     rsp, 60h
0x1800212c9  mov     rbx, rcx
0x1800212cc  xor     esi, esi
0x1800212ce  mov     [rbp+var_40], esi
0x1800212d1  mov     [rbp+var_3C], 109h
0x1800212d9  lea     r14d, [rsi+1]
0x1800212dd  mov     [rbp+var_34], r14w
0x1800212e2  lea     rax, aCtablemanagerR_0; "CTableManager::Remove"
0x1800212e9  mov     [rbp+var_30], rax
0x1800212ed  xorps   xmm0, xmm0
0x1800212f0  movdqu  [rbp+var_28], xmm0
0x1800212f5  mov     [rbp+var_18], rsi
0x1800212f9  mov     [rbp+var_10], esi
0x1800212fc  lea     rcx, [rbp+var_28+8]
0x180021300  call    cs:__imp_SxTracerGetThreadContextRetail
0x180021306  lea     rdi, WPP_GLOBAL_Control
0x18002130d  test    eax, eax
0x18002130f  js      loc_1800213CD
0x180021315  mov     rcx, qword ptr [rbp+var_28+8]
0x180021319  mov     rax, [rcx+20h]
0x18002131d  mov     qword ptr [rbp+var_28], rax
0x180021321  lea     rax, [rbp+var_40]
0x180021325  mov     [rcx+20h], rax
0x180021329  mov     rcx, cs:WPP_GLOBAL_Control
0x180021330  movzx   eax, [rbp+var_34]
0x180021334  test    ax, ax
0x180021337  jz      loc_180021404
0x18002133d  cmp     ax, r14w
0x180021341  jnz     short loc_1800213A4
0x180021343  cmp     rcx, rdi
0x180021346  jz      short loc_180021355
0x180021348  test    dword ptr [rcx+1Ch], 20000000h
0x18002134f  jnz     loc_180021421
0x180021355  lea     rcx, [rbx+28h]; Table
0x180021359  lea     rdx, [rbp+Buffer]; Buffer
0x18002135d  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180021363  test    al, al
0x180021365  jz      short loc_180021391
0x180021367  mov     [rbx+90h], r14d
0x18002136e  mov     ebx, [rbp+var_40]
0x180021371  lea     rcx, [rbp+var_40]; this
0x180021375  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002137a  mov     eax, ebx
0x18002137c  lea     r11, [rsp+60h+var_s0]
0x180021381  mov     rbx, [r11+20h]
0x180021385  mov     rsi, [r11+30h]
0x180021389  mov     rsp, r11
0x18002138c  pop     r14
0x18002138e  pop     rdi
0x18002138f  pop     rbp
0x180021390  retn
0x180021391  mov     ebx, 9000103h
0x180021396  mov     [rbp+var_40], ebx
0x180021399  mov     eax, 110h
0x18002139e  mov     word ptr [rbp+var_3C], ax
0x1800213a2  jmp     short loc_180021371
0x1800213a4  cmp     rcx, rdi
0x1800213a7  jz      short loc_180021355
0x1800213a9  test    dword ptr [rcx+1Ch], 20000h
0x1800213b0  jz      short loc_180021355
0x1800213b2  mov     edx, 0Dh
0x1800213b7  mov     r9, [rbp+var_30]
0x1800213bb  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x1800213c2  mov     rcx, [rcx+10h]
0x1800213c6  call    WPP_SF_s
0x1800213cb  jmp     short loc_180021355
0x1800213cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213d4  cmp     rcx, rdi
0x1800213d7  jz      loc_180021330
0x1800213dd  test    [rcx+1Ch], r14b
0x1800213e1  jz      loc_180021330
0x1800213e7  mov     edx, 0Ah
0x1800213ec  mov     r9d, eax
0x1800213ef  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x1800213f6  mov     rcx, [rcx+10h]
0x1800213fa  call    WPP_SF_d
0x1800213ff  jmp     loc_180021329
0x180021404  cmp     rcx, rdi
0x180021407  jz      loc_180021355
0x18002140d  test    dword ptr [rcx+1Ch], 8000000h
0x180021414  jz      loc_180021355
0x18002141a  mov     edx, 0Bh
0x18002141f  jmp     short loc_1800213B7
0x180021421  mov     edx, 0Ch
0x180021426  jmp     short loc_1800213B7
```
