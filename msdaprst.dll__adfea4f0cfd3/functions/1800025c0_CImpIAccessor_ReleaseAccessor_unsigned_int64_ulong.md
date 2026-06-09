# CImpIAccessor::ReleaseAccessor(unsigned __int64,ulong *)

- ea: `0x1800025c0`
- end: `0x18000271f`
- name: `?ReleaseAccessor@CImpIAccessor@@UEAAJ_KPEAK@Z`
- size: `351`
- prototype: `int(CImpIAccessor *__hidden this, unsigned __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001db8`
- `0x1800025c0`
- `0x180016584`
- `0x180017408`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800025f8`
- `KERNEL32!GetCurrentThreadId` at `0x1800025f8`
- `KERNEL32!LeaveCriticalSection` at `0x1800026c7`
- `KERNEL32!LeaveCriticalSection` at `0x1800026fd`
- `KERNEL32!LeaveCriticalSection` at `0x1800026c7`
- `KERNEL32!LeaveCriticalSection` at `0x1800026fd`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000261f`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000261f`
- `MSDART!UMSEnterCSWraper` at `0x1800025e6`
- `MSDART!UMSEnterCSWraper` at `0x1800025e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIAccessor::ReleaseAccessor(CImpIAccessor *this, unsigned int a2, unsigned int *a3)
{
  __int64 v6; // rbx
  void *v7; // rcx
  signed __int32 v8; // eax
  bool v9; // cc
  unsigned int v10; // eax
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  bool v13; // zf
  __int64 v14; // rcx
  unsigned int v16; // edi
  __int64 v17; // rcx
  void *v18; // [rsp+40h] [rbp+8h] BYREF
  __int64 v19; // [rsp+50h] [rbp+18h]

  v6 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v6);
  if ( !*(_DWORD *)(v6 + 12) )
    *(_DWORD *)(v6 + 8) = GetCurrentThreadId();
  ++*(_DWORD *)(v6 + 12);
  ++*(_DWORD *)(v6 + 16);
  v19 = v6;
  v18 = 0;
  SetErrorInfo(0, 0);
  if ( a3 )
    *a3 = 0;
  if ( CExtBuffer::GetItemOfExtBuffer(*(CExtBuffer **)(*((_QWORD *)this + 3) + 192LL), a2, &v18) >= 0 && (v7 = v18) != 0 )
  {
    v8 = _InterlockedExchangeAdd((volatile signed __int32 *)v18 + 1, 0xFFFFFFFF);
    v9 = v8 <= 1;
    v10 = v8 - 1;
    if ( v9 )
    {
      operator delete(v7);
      if ( a3 )
        *a3 = 0;
      if ( a2 && (v11 = *(_QWORD *)(*((_QWORD *)this + 3) + 192LL), a2 <= *(_DWORD *)(v11 + 4)) )
        v12 = (_QWORD *)(*(_QWORD *)(v11 + 24) + *(_DWORD *)v11 * (a2 - 1));
      else
        v12 = 0;
      *v12 = 0;
    }
    else if ( a3 )
    {
      *a3 = v10;
    }
    --*(_DWORD *)(v6 + 16);
    v13 = (*(_DWORD *)(v6 + 12))-- == 1;
    if ( v13 )
      *(_DWORD *)(v6 + 8) = -1;
    v14 = *(_QWORD *)v6;
    --*(_DWORD *)(v14 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
    return 0;
  }
  else
  {
    v16 = Exit(-2147217920, 0);
    --*(_DWORD *)(v6 + 16);
    v13 = (*(_DWORD *)(v6 + 12))-- == 1;
    if ( v13 )
      *(_DWORD *)(v6 + 8) = -1;
    v17 = *(_QWORD *)v6;
    --*(_DWORD *)(v17 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 8));
    return v16;
  }
}

```

## disassembly

```asm
0x1800025c0  mov     [rsp+arg_8], rbx
0x1800025c5  mov     [rsp+arg_18], rbp
0x1800025ca  push    rsi
0x1800025cb  push    rdi
0x1800025cc  push    r14
0x1800025ce  sub     rsp, 20h
0x1800025d2  mov     rdi, r8
0x1800025d5  mov     rbp, rdx
0x1800025d8  mov     r14, rcx
0x1800025db  mov     rbx, [rcx+18h]
0x1800025df  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1800025e3  mov     rcx, rbx
0x1800025e6  call    cs:__imp_UMSEnterCSWraper
0x1800025ed  nop     dword ptr [rax+rax+00h]
0x1800025f2  cmp     dword ptr [rbx+0Ch], 0
0x1800025f6  jnz     short loc_180002607
0x1800025f8  call    cs:__imp_GetCurrentThreadId
0x1800025ff  nop     dword ptr [rax+rax+00h]
0x180002604  mov     [rbx+8], eax
0x180002607  inc     dword ptr [rbx+0Ch]
0x18000260a  inc     dword ptr [rbx+10h]
0x18000260d  mov     [rsp+38h+arg_10], rbx
0x180002612  mov     [rsp+38h+arg_0], 0
0x18000261b  xor     edx, edx; perrinfo
0x18000261d  xor     ecx, ecx; dwReserved
0x18000261f  call    cs:__imp_SetErrorInfo
0x180002626  nop     dword ptr [rax+rax+00h]
0x18000262b  test    rdi, rdi
0x18000262e  jz      short loc_180002636
0x180002630  mov     dword ptr [rdi], 0
0x180002636  mov     rcx, [r14+18h]
0x18000263a  lea     r8, [rsp+38h+arg_0]; void *
0x18000263f  mov     edx, ebp; unsigned int
0x180002641  mov     rcx, [rcx+0C0h]; this
0x180002648  call    ?GetItemOfExtBuffer@CExtBuffer@@QEAAJKPEAX@Z; CExtBuffer::GetItemOfExtBuffer(ulong,void *)
0x18000264d  test    eax, eax
0x18000264f  js      loc_1800026D7
0x180002655  mov     rcx, [rsp+38h+arg_0]; void *
0x18000265a  test    rcx, rcx
0x18000265d  jz      short loc_1800026D7
0x18000265f  or      eax, 0FFFFFFFFh
0x180002662  lock xadd [rcx+4], eax
0x180002667  sub     eax, 1
0x18000266a  jg      short loc_1800026A8
0x18000266c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002671  test    rdi, rdi
0x180002674  jz      short loc_18000267C
0x180002676  mov     dword ptr [rdi], 0
0x18000267c  cmp     ebp, 1
0x18000267f  jb      short loc_18000269D
0x180002681  mov     rax, [r14+18h]
0x180002685  mov     rdx, [rax+0C0h]
0x18000268c  cmp     ebp, [rdx+4]
0x18000268f  ja      short loc_18000269D
0x180002691  lea     ecx, [rbp-1]
0x180002694  imul    ecx, [rdx]
0x180002697  add     rcx, [rdx+18h]
0x18000269b  jmp     short loc_18000269F
0x18000269d  xor     ecx, ecx
0x18000269f  mov     qword ptr [rcx], 0
0x1800026a6  jmp     short loc_1800026AF
0x1800026a8  test    rdi, rdi
0x1800026ab  jz      short loc_1800026AF
0x1800026ad  mov     [rdi], eax
0x1800026af  or      edx, 0FFFFFFFFh
0x1800026b2  add     [rbx+10h], edx
0x1800026b5  add     [rbx+0Ch], edx
0x1800026b8  jnz     short loc_1800026BD
0x1800026ba  mov     [rbx+8], edx
0x1800026bd  mov     rcx, [rbx]
0x1800026c0  dec     dword ptr [rcx+30h]
0x1800026c3  add     rcx, 8; lpCriticalSection
0x1800026c7  call    cs:__imp_LeaveCriticalSection
0x1800026ce  nop     dword ptr [rax+rax+00h]
0x1800026d3  xor     eax, eax
0x1800026d5  jmp     short loc_18000270B
0x1800026d7  xor     edx, edx; unsigned int
0x1800026d9  mov     ecx, 80040E00h; int
0x1800026de  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800026e3  mov     edi, eax
0x1800026e5  or      edx, 0FFFFFFFFh
0x1800026e8  add     [rbx+10h], edx
0x1800026eb  add     [rbx+0Ch], edx
0x1800026ee  jnz     short loc_1800026F3
0x1800026f0  mov     [rbx+8], edx
0x1800026f3  mov     rcx, [rbx]
0x1800026f6  dec     dword ptr [rcx+30h]
0x1800026f9  add     rcx, 8; lpCriticalSection
0x1800026fd  call    cs:__imp_LeaveCriticalSection
0x180002704  nop     dword ptr [rax+rax+00h]
0x180002709  mov     eax, edi
0x18000270b  mov     rbx, [rsp+38h+arg_8]
0x180002710  mov     rbp, [rsp+38h+arg_18]
0x180002715  add     rsp, 20h
0x180002719  pop     r14
0x18000271b  pop     rdi
0x18000271c  pop     rsi
0x18000271d  retn
```
