# CVolume::GetExtentTableFromSize(unsigned __int64,ulong *,ITableManager * *)

- ea: `0x180007ff0`
- end: `0x1800081ce`
- name: `?GetExtentTableFromSize@CVolume@@UEAAJ_KPEAKPEAPEAUITableManager@@@Z`
- size: `478`
- prototype: `__int64 __fastcall(CVolume *__hidden this, unsigned __int64, unsigned int *, struct ITableManager **)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180006400`
- `0x180007ff0`
- `0x180046494`
- `0x18004a92c`
- `0x18006a010`

## import_xrefs

- `SXSHARED!SxTracerGetThreadContextRetail` at `0x180008046`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x180008046`

## string_xrefs

- `0x180008027`: `CVolume::GetExtentTableFromSize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVolume::GetExtentTableFromSize(
        CVolume *this,
        unsigned __int64 a2,
        unsigned int *a3,
        struct ITableManager **a4)
{
  int ThreadContextRetail; // eax
  CSxGlobalTracer *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // ebx
  unsigned int i; // eax
  __int64 v13; // rsi
  struct ITableManager *v14; // rcx
  __int64 v16; // rdx
  int v17; // [rsp+20h] [rbp-48h] BYREF
  __int64 v18; // [rsp+24h] [rbp-44h]
  __int16 v19; // [rsp+2Ch] [rbp-3Ch]
  const char *v20; // [rsp+30h] [rbp-38h]
  __int128 v21; // [rsp+38h] [rbp-30h] BYREF
  __int64 v22; // [rsp+48h] [rbp-20h]
  int v23; // [rsp+50h] [rbp-18h]

  v17 = 0;
  v18 = 941;
  v19 = 1;
  v20 = "CVolume::GetExtentTableFromSize";
  v21 = 0;
  v22 = 0;
  v23 = 0;
  ThreadContextRetail = SxTracerGetThreadContextRetail((char *)&v21 + 8);
  if ( ThreadContextRetail >= 0 )
  {
    *(_QWORD *)&v21 = *(_QWORD *)(*((_QWORD *)&v21 + 1) + 32LL);
    *(_QWORD *)(*((_QWORD *)&v21 + 1) + 32LL) = &v17;
LABEL_3:
    v9 = WPP_GLOBAL_Control;
LABEL_4:
    v10 = 1;
    goto LABEL_5;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CSxGlobalTracer *)&WPP_GLOBAL_Control )
    goto LABEL_4;
  v10 = 1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids,
      (unsigned int)ThreadContextRetail);
    goto LABEL_3;
  }
LABEL_5:
  if ( v19 )
  {
    if ( v19 == 1 )
    {
      if ( v9 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v9 + 7) & 0x20000000) == 0 )
        goto LABEL_9;
      v16 = 12;
LABEL_23:
      WPP_SF_s(*((_QWORD *)v9 + 2), v16, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids, v20);
      goto LABEL_9;
    }
    if ( v9 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x20000) != 0 )
    {
      v16 = 13;
      goto LABEL_23;
    }
  }
  else if ( v9 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x8000000) != 0 )
  {
    v16 = 11;
    goto LABEL_23;
  }
LABEL_9:
  if ( a4 )
  {
    *a4 = 0;
  }
  else if ( !a3 )
  {
    v11 = -2147024809;
    v17 = -2147024809;
    WORD1(v18) = 946;
    goto LABEL_19;
  }
  v11 = 0;
  v17 = 0;
  LOWORD(v18) = 946;
  for ( i = 0; i < 0xF; ++i )
  {
    v13 = i;
    a2 >>= 1;
    if ( !a2 )
      break;
  }
  if ( a4 )
  {
    v14 = (struct ITableManager *)*((_QWORD *)this + v13 + 30);
    *a4 = v14;
    if ( v14 )
    {
      (*(void (__fastcall **)(struct ITableManager *, __int64))(*(_QWORD *)v14 + 8LL))(v14, v10);
      v11 = v17;
    }
  }
  if ( a3 )
    *a3 = v13;
LABEL_19:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return v11;
}

```

## disassembly

```asm
0x180007ff0  push    rbp
0x180007ff2  push    rbx
0x180007ff3  push    rsi
0x180007ff4  push    rdi
0x180007ff5  push    r12
0x180007ff7  push    r13
0x180007ff9  push    r14
0x180007ffb  push    r15
0x180007ffd  mov     rbp, rsp
0x180008000  sub     rsp, 68h
0x180008004  mov     rdi, r9
0x180008007  mov     r14, r8
0x18000800a  mov     r15, rdx
0x18000800d  mov     r12, rcx
0x180008010  xor     r13d, r13d
0x180008013  mov     [rbp+var_48], r13d
0x180008017  mov     [rbp+var_44], 3ADh
0x18000801f  lea     eax, [r13+1]
0x180008023  mov     [rbp+var_3C], ax
0x180008027  lea     rax, aCvolumeGetexte_0; "CVolume::GetExtentTableFromSize"
0x18000802e  mov     [rbp+var_38], rax
0x180008032  xorps   xmm0, xmm0
0x180008035  movdqu  [rbp+var_30], xmm0
0x18000803a  mov     [rbp+var_20], r13
0x18000803e  mov     [rbp+var_18], r13d
0x180008042  lea     rcx, [rbp+var_30+8]
0x180008046  call    cs:__imp_SxTracerGetThreadContextRetail
0x18000804c  lea     rsi, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x180008053  lea     rbx, WPP_GLOBAL_Control
0x18000805a  test    eax, eax
0x18000805c  js      loc_18000814B
0x180008062  mov     rcx, qword ptr [rbp+var_30+8]
0x180008066  mov     rax, [rcx+20h]
0x18000806a  mov     qword ptr [rbp+var_30], rax
0x18000806e  lea     rax, [rbp+var_48]
0x180008072  mov     [rcx+20h], rax
0x180008076  mov     rcx, cs:WPP_GLOBAL_Control
0x18000807d  mov     edx, 1
0x180008082  movzx   eax, [rbp+var_3C]
0x180008086  test    ax, ax
0x180008089  jz      loc_180008182
0x18000808f  cmp     ax, dx
0x180008092  jnz     loc_18000811F
0x180008098  cmp     rcx, rbx
0x18000809b  jz      short loc_1800080AA
0x18000809d  test    dword ptr [rcx+1Ch], 20000000h
0x1800080a4  jnz     loc_18000819F
0x1800080aa  test    rdi, rdi
0x1800080ad  jz      loc_1800081A6
0x1800080b3  mov     [rdi], r13
0x1800080b6  mov     ebx, r13d
0x1800080b9  mov     [rbp+var_48], ebx
0x1800080bc  mov     eax, 3B2h
0x1800080c1  mov     word ptr [rbp+var_44], ax
0x1800080c5  mov     eax, r13d
0x1800080c8  mov     esi, eax
0x1800080ca  shr     r15, 1
0x1800080cd  jz      short loc_1800080D6
0x1800080cf  inc     eax
0x1800080d1  cmp     eax, 0Fh
0x1800080d4  jb      short loc_1800080C8
0x1800080d6  test    rdi, rdi
0x1800080d9  jz      short loc_1800080FA
0x1800080db  mov     rcx, [r12+rsi*8+0F0h]
0x1800080e3  mov     [rdi], rcx
0x1800080e6  test    rcx, rcx
0x1800080e9  jz      short loc_1800080FA
0x1800080eb  mov     rax, [rcx]
0x1800080ee  mov     rax, [rax+8]
0x1800080f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080f7  mov     ebx, [rbp+var_48]
0x1800080fa  test    r14, r14
0x1800080fd  jnz     loc_1800081C5
0x180008103  lea     rcx, [rbp+var_48]; this
0x180008107  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000810c  mov     eax, ebx
0x18000810e  add     rsp, 68h
0x180008112  pop     r15
0x180008114  pop     r14
0x180008116  pop     r13
0x180008118  pop     r12
0x18000811a  pop     rdi
0x18000811b  pop     rsi
0x18000811c  pop     rbx
0x18000811d  pop     rbp
0x18000811e  retn
0x18000811f  cmp     rcx, rbx
0x180008122  jz      short loc_1800080AA
0x180008124  test    dword ptr [rcx+1Ch], 20000h
0x18000812b  jz      loc_1800080AA
0x180008131  mov     edx, 0Dh
0x180008136  mov     r9, [rbp+var_38]
0x18000813a  mov     r8, rsi
0x18000813d  mov     rcx, [rcx+10h]
0x180008141  call    WPP_SF_s
0x180008146  jmp     loc_1800080AA
0x18000814b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008152  cmp     rcx, rbx
0x180008155  jz      loc_18000807D
0x18000815b  mov     edx, 1
0x180008160  test    [rcx+1Ch], dl
0x180008163  jz      loc_180008082
0x180008169  mov     edx, 0Ah
0x18000816e  mov     r9d, eax
0x180008171  mov     r8, rsi
0x180008174  mov     rcx, [rcx+10h]
0x180008178  call    WPP_SF_d
0x18000817d  jmp     loc_180008076
0x180008182  cmp     rcx, rbx
0x180008185  jz      loc_1800080AA
0x18000818b  test    dword ptr [rcx+1Ch], 8000000h
0x180008192  jz      loc_1800080AA
0x180008198  mov     edx, 0Bh
0x18000819d  jmp     short loc_180008136
0x18000819f  mov     edx, 0Ch
0x1800081a4  jmp     short loc_180008136
0x1800081a6  test    r14, r14
0x1800081a9  jnz     loc_1800080B6
0x1800081af  mov     ebx, 80070057h
0x1800081b4  mov     [rbp+var_48], ebx
0x1800081b7  mov     eax, 3B2h
0x1800081bc  mov     word ptr [rbp+var_44+2], ax
0x1800081c0  jmp     loc_180008103
0x1800081c5  mov     [r14], esi
0x1800081c8  jmp     loc_180008103
```
