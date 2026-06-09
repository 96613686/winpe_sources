# NatMergePortMapGuidListFromHNetConn(IHNetConnection *,_LIST_ENTRY *)

- ea: `0x180080530`
- end: `0x1800808b6`
- name: `?NatMergePortMapGuidListFromHNetConn@@YAJPEAUIHNetConnection@@PEAU_LIST_ENTRY@@@Z`
- size: `902`
- prototype: `__int64 __fastcall(struct IHNetConnection *, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180082d24`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180080530`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180080733`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180080733`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008074b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008074b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008085d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008085d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800806ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800806ec`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180080595`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180080595`

## pseudocode

```c
__int64 __fastcall NatMergePortMapGuidListFromHNetConn(struct IHNetConnection *a1, struct _LIST_ENTRY *a2)
{
  unsigned int v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rax
  int v10; // eax
  __m128i v11; // xmm6
  struct _LIST_ENTRY *Flink; // rcx
  unsigned __int64 v13; // xmm0_8
  unsigned __int64 v14; // rax
  HANDLE ProcessHeap; // rax
  __m128i *v16; // rax
  struct _LIST_ENTRY *Blink; // rcx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v22; // [rsp+30h] [rbp-30h] BYREF
  __int64 v23; // [rsp+38h] [rbp-28h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-20h] BYREF
  int v25; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids);
  }
  v4 = CoInitializeEx(0, 0);
  v6 = v4;
  if ( v4 == -2147417850 || !v4 )
  {
    v9 = *(_QWORD *)a1;
    LOBYTE(v5) = 1;
    v26 = 0;
    v4 = (*(__int64 (__fastcall **)(struct IHNetConnection *, __int64, __int64 *))(v9 + 104))(a1, v5, &v26);
    v6 = v4;
    if ( v4 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 99;
        goto LABEL_11;
      }
    }
    else
    {
LABEL_17:
      while ( 1 )
      {
        v25 = 0;
        v22 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v26 + 24LL))(
                v26,
                1,
                &v22,
                &v25);
        v6 = v10;
        if ( v10 < 0 )
          break;
        if ( !v25 )
        {
          v6 = 0;
          goto LABEL_50;
        }
        v23 = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 32LL))(v22, &v23);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        if ( v6 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = 101;
LABEL_39:
            v20 = v6;
LABEL_49:
            WPP_SF_d(v18[2], v19, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, v20);
            goto LABEL_50;
          }
          goto LABEL_50;
        }
        pv[0] = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v23 + 88LL))(v23, pv);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        if ( v6 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = 102;
            goto LABEL_39;
          }
          goto LABEL_50;
        }
        v11 = *(__m128i *)pv[0];
        CoTaskMemFree(pv[0]);
        Flink = a2->Flink;
        v13 = _mm_srli_si128(v11, 8).m128i_u64[0];
        pv[0] = 0;
        while ( Flink != a2 )
        {
          v14 = v11.m128i_i64[0] - (unsigned __int64)Flink[1].Flink;
          if ( (struct _LIST_ENTRY *)v11.m128i_i64[0] == Flink[1].Flink )
            v14 = v13 - (unsigned __int64)Flink[1].Blink;
          if ( !v14 )
            goto LABEL_17;
          Flink = Flink->Flink;
        }
        ProcessHeap = GetProcessHeap();
        v16 = (__m128i *)HeapAlloc(ProcessHeap, 8u, 0x20u);
        if ( !v16 )
        {
          v6 = -2147024882;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids);
          }
          goto LABEL_50;
        }
        v16->m128i_i64[0] = 0;
        v16->m128i_i64[1] = 0;
        v16[1] = v11;
        Blink = a2->Blink;
        if ( Blink->Flink != a2 )
          __fastfail(3u);
        v16->m128i_i64[0] = (__int64)a2;
        v16->m128i_i64[1] = (__int64)Blink;
        Blink->Flink = (struct _LIST_ENTRY *)v16;
        a2->Blink = (struct _LIST_ENTRY *)v16;
      }
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 100;
        v20 = (unsigned int)v10;
        goto LABEL_49;
      }
LABEL_50:
      if ( v26 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        v26 = 0;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 98;
LABEL_11:
      WPP_SF_d(v7[2], v8, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, v4);
    }
  }
  CoUninitialize();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x180080530  mov     [rsp-28h+arg_0], rbx
0x180080535  mov     [rsp-28h+arg_8], rsi
0x18008053a  push    rbp
0x18008053b  push    rdi
0x18008053c  push    r12
0x18008053e  push    r13
0x180080540  push    r15
0x180080542  mov     rbp, rsp
0x180080545  sub     rsp, 60h
0x180080549  movaps  [rsp+60h+var_10], xmm6
0x18008054e  mov     rdi, rdx
0x180080551  mov     rsi, rcx
0x180080554  mov     rcx, cs:WPP_GLOBAL_Control
0x18008055b  lea     r12, WPP_GLOBAL_Control
0x180080562  lea     r13, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x180080569  mov     r15d, 200h
0x18008056f  cmp     rcx, r12
0x180080572  jz      short loc_180080591
0x180080574  test    [rcx+1Ch], r15d
0x180080578  jz      short loc_180080591
0x18008057a  cmp     byte ptr [rcx+19h], 6
0x18008057e  jb      short loc_180080591
0x180080580  mov     rcx, [rcx+10h]
0x180080584  mov     edx, 61h ; 'a'
0x180080589  mov     r8, r13
0x18008058c  call    WPP_SF_
0x180080591  xor     edx, edx; dwCoInit
0x180080593  xor     ecx, ecx; pvReserved
0x180080595  call    cs:__imp_CoInitializeEx
0x18008059c  nop     dword ptr [rax+rax+00h]
0x1800805a1  mov     ebx, eax
0x1800805a3  cmp     eax, 80010106h
0x1800805a8  jz      short loc_1800805EB
0x1800805aa  test    eax, eax
0x1800805ac  jz      short loc_1800805EB
0x1800805ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800805b5  cmp     rcx, r12
0x1800805b8  jz      loc_18008085D
0x1800805be  test    [rcx+1Ch], r15d
0x1800805c2  jz      loc_18008085D
0x1800805c8  cmp     byte ptr [rcx+19h], 2
0x1800805cc  jb      loc_18008085D
0x1800805d2  mov     edx, 62h ; 'b'
0x1800805d7  mov     rcx, [rcx+10h]
0x1800805db  mov     r9d, eax
0x1800805de  mov     r8, r13
0x1800805e1  call    WPP_SF_d
0x1800805e6  jmp     loc_18008085D
0x1800805eb  mov     rax, [rsi]
0x1800805ee  lea     r8, [rbp+arg_18]
0x1800805f2  mov     dl, 1
0x1800805f4  mov     [rbp+arg_18], 0
0x1800805fc  mov     rcx, rsi
0x1800805ff  mov     rax, [rax+68h]
0x180080603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080608  mov     ebx, eax
0x18008060a  test    eax, eax
0x18008060c  jz      short loc_180080639
0x18008060e  mov     rcx, cs:WPP_GLOBAL_Control
0x180080615  cmp     rcx, r12
0x180080618  jz      loc_18008085D
0x18008061e  test    [rcx+1Ch], r15d
0x180080622  jz      loc_18008085D
0x180080628  cmp     byte ptr [rcx+19h], 2
0x18008062c  jb      loc_18008085D
0x180080632  mov     edx, 63h ; 'c'
0x180080637  jmp     short loc_1800805D7
0x180080639  mov     rcx, [rbp+arg_18]
0x18008063d  lea     r9, [rbp+arg_10]
0x180080641  mov     [rbp+arg_10], 0
0x180080648  lea     r8, [rbp+var_30]
0x18008064c  mov     [rbp+var_30], 0
0x180080654  mov     edx, 1
0x180080659  mov     rax, [rcx]
0x18008065c  mov     rax, [rax+18h]
0x180080660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080665  mov     ebx, eax
0x180080667  test    eax, eax
0x180080669  js      loc_180080814
0x18008066f  cmp     [rbp+arg_10], 0
0x180080673  jz      loc_180080810
0x180080679  mov     rcx, [rbp+var_30]
0x18008067d  lea     rdx, [rbp+var_28]
0x180080681  mov     [rbp+var_28], 0
0x180080689  mov     rax, [rcx]
0x18008068c  mov     rax, [rax+20h]
0x180080690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080695  mov     rcx, [rbp+var_30]
0x180080699  mov     ebx, eax
0x18008069b  mov     rax, [rcx]
0x18008069e  mov     rax, [rax+10h]
0x1800806a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800806a7  test    ebx, ebx
0x1800806a9  jnz     loc_1800807F1
0x1800806af  mov     rcx, [rbp+var_28]
0x1800806b3  lea     rdx, [rbp+pv]
0x1800806b7  mov     [rbp+pv], 0
0x1800806bf  mov     rax, [rcx]
0x1800806c2  mov     rax, [rax+58h]
0x1800806c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800806cb  mov     rcx, [rbp+var_28]
0x1800806cf  mov     ebx, eax
0x1800806d1  mov     rax, [rcx]
0x1800806d4  mov     rax, [rax+10h]
0x1800806d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800806dd  test    ebx, ebx
0x1800806df  jnz     loc_1800807CF
0x1800806e5  mov     rcx, [rbp+pv]; pv
0x1800806e9  movups  xmm6, xmmword ptr [rcx]
0x1800806ec  call    cs:__imp_CoTaskMemFree
0x1800806f3  nop     dword ptr [rax+rax+00h]
0x1800806f8  mov     rcx, [rdi]
0x1800806fb  movdqa  xmm0, xmm6
0x1800806ff  psrldq  xmm0, 8
0x180080704  mov     [rbp+pv], 0
0x18008070c  cmp     rcx, rdi
0x18008070f  jz      short loc_180080733
0x180080711  movq    rax, xmm6
0x180080716  sub     rax, [rcx+10h]
0x18008071a  jnz     short loc_180080725
0x18008071c  movq    rax, xmm0
0x180080721  sub     rax, [rcx+18h]
0x180080725  test    rax, rax
0x180080728  jz      loc_180080639
0x18008072e  mov     rcx, [rcx]
0x180080731  jmp     short loc_18008070C
0x180080733  call    cs:__imp_GetProcessHeap
0x18008073a  nop     dword ptr [rax+rax+00h]
0x18008073f  mov     edx, 8; dwFlags
0x180080744  mov     rcx, rax; hHeap
0x180080747  lea     r8d, [rdx+18h]; dwBytes
0x18008074b  call    cs:__imp_HeapAlloc
0x180080752  nop     dword ptr [rax+rax+00h]
0x180080757  test    rax, rax
0x18008075a  jz      short loc_180080793
0x18008075c  mov     qword ptr [rax], 0
0x180080763  mov     qword ptr [rax+8], 0
0x18008076b  movdqu  xmmword ptr [rax+10h], xmm6
0x180080770  mov     rcx, [rdi+8]
0x180080774  cmp     [rcx], rdi
0x180080777  jnz     short loc_18008078C
0x180080779  mov     [rax], rdi
0x18008077c  mov     [rax+8], rcx
0x180080780  mov     [rcx], rax
0x180080783  mov     [rdi+8], rax
0x180080787  jmp     loc_180080639
0x18008078c  mov     ecx, 3
0x180080791  int     29h; Win8: RtlFailFast(ecx)
0x180080793  mov     ebx, 8007000Eh
0x180080798  mov     rcx, cs:WPP_GLOBAL_Control
0x18008079f  cmp     rcx, r12
0x1800807a2  jz      loc_180080840
0x1800807a8  test    [rcx+1Ch], r15d
0x1800807ac  jz      loc_180080840
0x1800807b2  cmp     byte ptr [rcx+19h], 2
0x1800807b6  jb      loc_180080840
0x1800807bc  mov     rcx, [rcx+10h]
0x1800807c0  mov     edx, 67h ; 'g'
0x1800807c5  mov     r8, r13
0x1800807c8  call    WPP_SF_
0x1800807cd  jmp     short loc_180080840
0x1800807cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800807d6  cmp     rcx, r12
0x1800807d9  jz      short loc_180080840
0x1800807db  test    [rcx+1Ch], r15d
0x1800807df  jz      short loc_180080840
0x1800807e1  cmp     byte ptr [rcx+19h], 2
0x1800807e5  jb      short loc_180080840
0x1800807e7  mov     edx, 66h ; 'f'
0x1800807ec  mov     r9d, ebx
0x1800807ef  jmp     short loc_180080834
0x1800807f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800807f8  cmp     rcx, r12
0x1800807fb  jz      short loc_180080840
0x1800807fd  test    [rcx+1Ch], r15d
0x180080801  jz      short loc_180080840
0x180080803  cmp     byte ptr [rcx+19h], 2
0x180080807  jb      short loc_180080840
0x180080809  mov     edx, 65h ; 'e'
0x18008080e  jmp     short loc_1800807EC
0x180080810  xor     ebx, ebx
0x180080812  jmp     short loc_180080840
0x180080814  mov     rcx, cs:WPP_GLOBAL_Control
0x18008081b  cmp     rcx, r12
0x18008081e  jz      short loc_180080840
0x180080820  test    [rcx+1Ch], r15d
0x180080824  jz      short loc_180080840
0x180080826  cmp     byte ptr [rcx+19h], 2
0x18008082a  jb      short loc_180080840
0x18008082c  mov     edx, 64h ; 'd'
0x180080831  mov     r9d, eax
0x180080834  mov     rcx, [rcx+10h]
0x180080838  mov     r8, r13
0x18008083b  call    WPP_SF_d
0x180080840  mov     rcx, [rbp+arg_18]
0x180080844  test    rcx, rcx
0x180080847  jz      short loc_18008085D
0x180080849  mov     rax, [rcx]
0x18008084c  mov     rax, [rax+10h]
0x180080850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080855  mov     [rbp+arg_18], 0
0x18008085d  call    cs:__imp_CoUninitialize
0x180080864  nop     dword ptr [rax+rax+00h]
0x180080869  mov     rcx, cs:WPP_GLOBAL_Control
0x180080870  cmp     rcx, r12
0x180080873  jz      short loc_180080895
0x180080875  test    [rcx+1Ch], r15d
0x180080879  jz      short loc_180080895
0x18008087b  cmp     byte ptr [rcx+19h], 6
0x18008087f  jb      short loc_180080895
0x180080881  mov     rcx, [rcx+10h]
0x180080885  mov     edx, 68h ; 'h'
0x18008088a  mov     r9d, ebx
0x18008088d  mov     r8, r13
0x180080890  call    WPP_SF_d
0x180080895  movaps  xmm6, [rsp+60h+var_10]
0x18008089a  lea     r11, [rsp+60h+var_s0]
0x18008089f  mov     rsi, [r11+38h]
0x1800808a3  mov     eax, ebx
0x1800808a5  mov     rbx, [r11+30h]
0x1800808a9  mov     rsp, r11
0x1800808ac  pop     r15
0x1800808ae  pop     r13
0x1800808b0  pop     r12
0x1800808b2  pop     rdi
0x1800808b3  pop     rbp
0x1800808b4  retn
```
