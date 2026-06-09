# CImpIRowset::GetNextRows(unsigned __int64,__int64,__int64,unsigned __int64 *,unsigned __int64 * *)

- ea: `0x180018010`
- end: `0x180018328`
- name: `?GetNextRows@CImpIRowset@@UEAAJ_K_J1PEA_KPEAPEA_K@Z`
- size: `792`
- prototype: `__int64 __fastcall(CImpIRowset *__hidden this, unsigned __int64, __int64, __int64, unsigned __int64 *, unsigned __int64 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18001156c`
- `0x180016584`
- `0x1800174e0`
- `0x180017978`
- `0x180018010`
- `0x180021294`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180018050`
- `KERNEL32!GetCurrentThreadId` at `0x180018050`
- `KERNEL32!LeaveCriticalSection` at `0x1800180c6`
- `KERNEL32!LeaveCriticalSection` at `0x18001812b`
- `KERNEL32!LeaveCriticalSection` at `0x1800182c1`
- `KERNEL32!LeaveCriticalSection` at `0x180018301`
- `KERNEL32!LeaveCriticalSection` at `0x1800180c6`
- `KERNEL32!LeaveCriticalSection` at `0x18001812b`
- `KERNEL32!LeaveCriticalSection` at `0x1800182c1`
- `KERNEL32!LeaveCriticalSection` at `0x180018301`
- `ole32!CoTaskMemAlloc` at `0x18001820e`
- `ole32!CoTaskMemAlloc` at `0x18001820e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180018072`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180018072`
- `MSDART!UMSEnterCSWraper` at `0x18001803d`
- `MSDART!UMSEnterCSWraper` at `0x18001803d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CImpIRowset::GetNextRows(
        CImpIRowset *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 *a5,
        unsigned __int64 **a6)
{
  __int64 v9; // rbx
  unsigned __int64 *v10; // r13
  unsigned __int64 **v11; // r15
  bool v12; // sf
  bool v13; // zf
  __int64 v14; // rcx
  __int64 v16; // r9
  int v17; // ecx
  __int64 v18; // rcx
  int NextSlots; // eax
  unsigned int v20; // r8d
  unsigned int v21; // ebp
  int v22; // esi
  __int64 v23; // r14
  int v24; // eax
  unsigned __int64 *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // rcx
  unsigned int v30; // edi
  __int64 v31; // rcx
  unsigned int v32; // [rsp+70h] [rbp+8h] BYREF
  __int64 v33; // [rsp+78h] [rbp+10h]

  v33 = a2;
  v9 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v9);
  if ( !*(_DWORD *)(v9 + 12) )
    *(_DWORD *)(v9 + 8) = GetCurrentThreadId();
  ++*(_DWORD *)(v9 + 12);
  ++*(_DWORD *)(v9 + 16);
  v32 = 0;
  SetErrorInfo(0, 0);
  v10 = a5;
  if ( !a5 || (v11 = a6) == 0 )
  {
    v17 = -2147024809;
    goto LABEL_44;
  }
  *a5 = 0;
  if ( a4 )
  {
    if ( a4 < 0 )
    {
LABEL_42:
      v17 = -2147217884;
      goto LABEL_44;
    }
    v12 = a3 < 0;
  }
  else
  {
    v12 = a3 < 0;
    if ( !a3 )
    {
      --*(_DWORD *)(v9 + 16);
LABEL_8:
      v13 = (*(_DWORD *)(v9 + 12))-- == 1;
      if ( v13 )
        *(_DWORD *)(v9 + 8) = -1;
      v14 = *(_QWORD *)v9;
      --*(_DWORD *)(v14 + 48);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
      return 0;
    }
  }
  if ( v12 )
    goto LABEL_42;
  if ( (unsigned int)CBitArray::ArrayEmpty(*(CBitArray **)(*((_QWORD *)this + 3) + 208LL)) )
  {
    v17 = -2147217883;
LABEL_44:
    v30 = Exit(v17, 0);
    --*(_DWORD *)(v9 + 16);
    v13 = (*(_DWORD *)(v9 + 12))-- == 1;
    if ( v13 )
      *(_DWORD *)(v9 + 8) = -1;
    v31 = *(_QWORD *)v9;
    --*(_DWORD *)(v31 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v31 + 8));
    return v30;
  }
  if ( (*(_DWORD *)(v16 + 248) & 0x100) != 0 )
    goto LABEL_17;
  if ( (int)CRowset::Rebind(
              (CRowset *)v16,
              (unsigned __int8 *)(*(_QWORD *)(v16 + 224)
                                + (unsigned int)(*(_DWORD *)(v16 + 220) * *(_DWORD *)(v16 + 232)))) < 0 )
  {
LABEL_21:
    v17 = -2147467259;
    goto LABEL_44;
  }
  NextSlots = GetNextSlots(*(struct tagLSTSLOT **)(*((_QWORD *)this + 3) + 200LL), 1u, &v32);
  if ( NextSlots < 0 )
  {
LABEL_23:
    v17 = NextSlots;
    goto LABEL_44;
  }
  v21 = 1;
  v22 = 1;
  v23 = a3 + 1;
  while ( v22 <= v23 )
  {
    v24 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 3) + 56LL))(*((_QWORD *)this + 3), v33);
    if ( v24 == 1 )
    {
      v21 = 0;
      *(_DWORD *)(*((_QWORD *)this + 3) + 248LL) |= 0x100u;
      break;
    }
    if ( v24 < 0 )
      goto LABEL_21;
    ++v22;
  }
  *(_DWORD *)(*((_QWORD *)this + 3) + 244LL) = *(_DWORD *)(*((_QWORD *)this + 3) + 240LL);
  *(_DWORD *)(*((_QWORD *)this + 3) + 240LL) += v22 - 1;
  *(_DWORD *)(*((_QWORD *)this + 3) + 236LL) += v22 - 1;
  *v10 = v21;
  if ( !*v11 )
  {
    v25 = (unsigned __int64 *)CoTaskMemAlloc(8u);
    *v11 = v25;
    if ( !v25 )
    {
      v17 = -2147024882;
      goto LABEL_44;
    }
  }
  v26 = *((_QWORD *)this + 3);
  if ( v21 )
  {
    v27 = *(_DWORD *)(v26 + 220) * v32;
    v28 = *(_QWORD *)(v26 + 224);
    ++*(_DWORD *)(v27 + v28);
    *(_QWORD *)(v27 + v28 + 16) = *(unsigned int *)(*((_QWORD *)this + 3) + 244LL) + 1LL;
    ++*(_DWORD *)(*((_QWORD *)this + 3) + 264LL);
    **v11 = v32;
  }
  else
  {
    NextSlots = ReleaseSlots(*(struct tagLSTSLOT **)(v26 + 200), v32, v20);
    if ( NextSlots < 0 )
      goto LABEL_23;
  }
  if ( (*(_DWORD *)(*((_QWORD *)this + 3) + 248LL) & 0x100) != 0 )
  {
LABEL_17:
    --*(_DWORD *)(v9 + 16);
    v13 = (*(_DWORD *)(v9 + 12))-- == 1;
    if ( v13 )
      *(_DWORD *)(v9 + 8) = -1;
    v18 = *(_QWORD *)v9;
    --*(_DWORD *)(v18 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 8));
    return 265926;
  }
  --*(_DWORD *)(v9 + 16);
  if ( a4 <= 1 )
    goto LABEL_8;
  v13 = (*(_DWORD *)(v9 + 12))-- == 1;
  if ( v13 )
    *(_DWORD *)(v9 + 8) = -1;
  v29 = *(_QWORD *)v9;
  --*(_DWORD *)(v29 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v29 + 8));
  return 265920;
}

```

## disassembly

```asm
0x180018010  mov     [rsp+arg_10], rbx
0x180018015  mov     [rsp+arg_8], rdx
0x18001801a  push    rbp
0x18001801b  push    rsi
0x18001801c  push    rdi
0x18001801d  push    r12
0x18001801f  push    r13
0x180018021  push    r14
0x180018023  push    r15
0x180018025  sub     rsp, 30h
0x180018029  mov     r12, r9
0x18001802c  mov     r14, r8
0x18001802f  mov     rdi, rcx
0x180018032  mov     rbx, [rcx+18h]
0x180018036  sub     rbx, 0FFFFFFFFFFFFFF80h
0x18001803a  mov     rcx, rbx
0x18001803d  call    cs:__imp_UMSEnterCSWraper
0x180018044  nop     dword ptr [rax+rax+00h]
0x180018049  xor     ebp, ebp
0x18001804b  cmp     [rbx+0Ch], ebp
0x18001804e  jnz     short loc_18001805F
0x180018050  call    cs:__imp_GetCurrentThreadId
0x180018057  nop     dword ptr [rax+rax+00h]
0x18001805c  mov     [rbx+8], eax
0x18001805f  inc     dword ptr [rbx+0Ch]
0x180018062  inc     dword ptr [rbx+10h]
0x180018065  mov     [rsp+68h+var_48], rbx
0x18001806a  mov     [rsp+68h+arg_0], ebp
0x18001806e  xor     edx, edx; perrinfo
0x180018070  xor     ecx, ecx; dwReserved
0x180018072  call    cs:__imp_SetErrorInfo
0x180018079  nop     dword ptr [rax+rax+00h]
0x18001807e  mov     r13, [rsp+68h+arg_20]
0x180018086  test    r13, r13
0x180018089  jz      loc_1800182DB
0x18001808f  mov     r15, [rsp+68h+arg_28]
0x180018097  test    r15, r15
0x18001809a  jz      loc_1800182DB
0x1800180a0  mov     [r13+0], rbp
0x1800180a4  test    r12, r12
0x1800180a7  jnz     short loc_1800180D9
0x1800180a9  test    r14, r14
0x1800180ac  jnz     short loc_1800180E2
0x1800180ae  or      edx, 0FFFFFFFFh
0x1800180b1  add     [rbx+10h], edx
0x1800180b4  add     [rbx+0Ch], edx
0x1800180b7  jnz     short loc_1800180BC
0x1800180b9  mov     [rbx+8], edx
0x1800180bc  mov     rcx, [rbx]
0x1800180bf  dec     dword ptr [rcx+30h]
0x1800180c2  add     rcx, 8; lpCriticalSection
0x1800180c6  call    cs:__imp_LeaveCriticalSection
0x1800180cd  nop     dword ptr [rax+rax+00h]
0x1800180d2  xor     eax, eax
0x1800180d4  jmp     loc_18001830F
0x1800180d9  js      loc_1800182D4
0x1800180df  test    r14, r14
0x1800180e2  js      loc_1800182D4
0x1800180e8  mov     r9, [rdi+18h]
0x1800180ec  mov     rcx, [r9+0D0h]; this
0x1800180f3  call    ?ArrayEmpty@CBitArray@@QEAAJXZ; CBitArray::ArrayEmpty(void)
0x1800180f8  test    eax, eax
0x1800180fa  jz      short loc_180018106
0x1800180fc  mov     ecx, 80040E25h
0x180018101  jmp     loc_1800182E0
0x180018106  test    dword ptr [r9+0F8h], 100h
0x180018111  jz      short loc_180018141
0x180018113  or      edx, 0FFFFFFFFh
0x180018116  add     [rbx+10h], edx
0x180018119  add     [rbx+0Ch], edx
0x18001811c  jnz     short loc_180018121
0x18001811e  mov     [rbx+8], edx
0x180018121  mov     rcx, [rbx]
0x180018124  dec     dword ptr [rcx+30h]
0x180018127  add     rcx, 8; lpCriticalSection
0x18001812b  call    cs:__imp_LeaveCriticalSection
0x180018132  nop     dword ptr [rax+rax+00h]
0x180018137  mov     eax, 40EC6h
0x18001813c  jmp     loc_18001830F
0x180018141  mov     edx, [r9+0E8h]
0x180018148  imul    edx, [r9+0DCh]
0x180018150  add     rdx, [r9+0E0h]; unsigned __int8 *
0x180018157  mov     rcx, r9; this
0x18001815a  call    ?Rebind@CRowset@@QEAAJPEAE@Z; CRowset::Rebind(uchar *)
0x18001815f  test    eax, eax
0x180018161  jns     short loc_18001816D
0x180018163  mov     ecx, 80004005h
0x180018168  jmp     loc_1800182E0
0x18001816d  mov     rcx, [rdi+18h]
0x180018171  lea     r8, [rsp+68h+arg_0]; unsigned int *
0x180018176  mov     edx, 1; unsigned int
0x18001817b  mov     rcx, [rcx+0C8h]; struct tagLSTSLOT *
0x180018182  call    ?GetNextSlots@@YAJPEAUtagLSTSLOT@@KPEAK@Z; GetNextSlots(tagLSTSLOT *,ulong,ulong *)
0x180018187  test    eax, eax
0x180018189  jns     short loc_180018192
0x18001818b  mov     ecx, eax
0x18001818d  jmp     loc_1800182E0
0x180018192  mov     ebp, 1
0x180018197  mov     esi, ebp
0x180018199  inc     r14
0x18001819c  movsxd  rax, esi
0x18001819f  cmp     rax, r14
0x1800181a2  jg      short loc_1800181D3
0x1800181a4  mov     rcx, [rdi+18h]
0x1800181a8  mov     rax, [rcx]
0x1800181ab  mov     rdx, [rsp+68h+arg_8]
0x1800181b0  mov     rax, [rax+38h]
0x1800181b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181b9  cmp     eax, ebp
0x1800181bb  jz      short loc_1800181C5
0x1800181bd  test    eax, eax
0x1800181bf  js      short loc_180018163
0x1800181c1  inc     esi
0x1800181c3  jmp     short loc_18001819C
0x1800181c5  xor     ebp, ebp
0x1800181c7  mov     rax, [rdi+18h]
0x1800181cb  bts     dword ptr [rax+0F8h], 8
0x1800181d3  mov     rcx, [rdi+18h]
0x1800181d7  mov     eax, [rcx+0F0h]
0x1800181dd  mov     [rcx+0F4h], eax
0x1800181e3  mov     rcx, [rdi+18h]
0x1800181e7  lea     eax, [rsi-1]
0x1800181ea  add     [rcx+0F0h], eax
0x1800181f0  mov     rcx, [rdi+18h]
0x1800181f4  lea     eax, [rsi-1]
0x1800181f7  add     [rcx+0ECh], eax
0x1800181fd  mov     eax, ebp
0x1800181ff  mov     [r13+0], rax
0x180018203  cmp     qword ptr [r15], 0
0x180018207  jnz     short loc_18001822C
0x180018209  mov     ecx, 8; cb
0x18001820e  call    cs:__imp_CoTaskMemAlloc
0x180018215  nop     dword ptr [rax+rax+00h]
0x18001821a  mov     [r15], rax
0x18001821d  test    rax, rax
0x180018220  jnz     short loc_18001822C
0x180018222  mov     ecx, 8007000Eh
0x180018227  jmp     loc_1800182E0
0x18001822c  mov     rcx, [rdi+18h]
0x180018230  test    ebp, ebp
0x180018232  jnz     short loc_18001824D
0x180018234  mov     edx, [rsp+68h+arg_0]; unsigned int
0x180018238  mov     rcx, [rcx+0C8h]; struct tagLSTSLOT *
0x18001823f  call    ?ReleaseSlots@@YAJPEAUtagLSTSLOT@@KK@Z; ReleaseSlots(tagLSTSLOT *,ulong,ulong)
0x180018244  test    eax, eax
0x180018246  jns     short loc_18001828B
0x180018248  jmp     loc_18001818B
0x18001824d  mov     eax, [rsp+68h+arg_0]
0x180018251  imul    eax, [rcx+0DCh]
0x180018258  mov     r8d, eax
0x18001825b  mov     rdx, [rcx+0E0h]
0x180018262  inc     dword ptr [rax+rdx]
0x180018265  mov     rax, [rdi+18h]
0x180018269  mov     ecx, [rax+0F4h]
0x18001826f  inc     rcx
0x180018272  mov     [r8+rdx+10h], rcx
0x180018277  mov     rax, [rdi+18h]
0x18001827b  inc     dword ptr [rax+108h]
0x180018281  mov     ecx, [rsp+68h+arg_0]
0x180018285  mov     rax, [r15]
0x180018288  mov     [rax], rcx
0x18001828b  mov     rax, [rdi+18h]
0x18001828f  or      edx, 0FFFFFFFFh
0x180018292  test    dword ptr [rax+0F8h], 100h
0x18001829c  jnz     loc_180018116
0x1800182a2  add     [rbx+10h], edx
0x1800182a5  cmp     r12, 1
0x1800182a9  jle     loc_1800180B4
0x1800182af  add     [rbx+0Ch], edx
0x1800182b2  jnz     short loc_1800182B7
0x1800182b4  mov     [rbx+8], edx
0x1800182b7  mov     rcx, [rbx]
0x1800182ba  dec     dword ptr [rcx+30h]
0x1800182bd  add     rcx, 8; lpCriticalSection
0x1800182c1  call    cs:__imp_LeaveCriticalSection
0x1800182c8  nop     dword ptr [rax+rax+00h]
0x1800182cd  mov     eax, 40EC0h
0x1800182d2  jmp     short loc_18001830F
0x1800182d4  mov     ecx, 80040E24h
0x1800182d9  jmp     short loc_1800182E0
0x1800182db  mov     ecx, 80070057h; int
0x1800182e0  xor     edx, edx; unsigned int
0x1800182e2  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800182e7  mov     edi, eax
0x1800182e9  or      edx, 0FFFFFFFFh
0x1800182ec  add     [rbx+10h], edx
0x1800182ef  add     [rbx+0Ch], edx
0x1800182f2  jnz     short loc_1800182F7
0x1800182f4  mov     [rbx+8], edx
0x1800182f7  mov     rcx, [rbx]
0x1800182fa  dec     dword ptr [rcx+30h]
0x1800182fd  add     rcx, 8; lpCriticalSection
0x180018301  call    cs:__imp_LeaveCriticalSection
0x180018308  nop     dword ptr [rax+rax+00h]
0x18001830d  mov     eax, edi
0x18001830f  mov     rbx, [rsp+68h+arg_10]
0x180018317  add     rsp, 30h
0x18001831b  pop     r15
0x18001831d  pop     r14
0x18001831f  pop     r13
0x180018321  pop     r12
0x180018323  pop     rdi
0x180018324  pop     rsi
0x180018325  pop     rbp
0x180018326  retn
```
