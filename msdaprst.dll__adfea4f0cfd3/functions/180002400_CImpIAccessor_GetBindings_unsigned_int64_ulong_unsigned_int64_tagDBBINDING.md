# CImpIAccessor::GetBindings(unsigned __int64,ulong *,unsigned __int64 *,tagDBBINDING * *)

- ea: `0x180002400`
- end: `0x1800025b5`
- name: `?GetBindings@CImpIAccessor@@UEAAJ_KPEAKPEA_KPEAPEAUtagDBBINDING@@@Z`
- size: `437`
- prototype: `int(CImpIAccessor *__hidden this, unsigned __int64, unsigned int *, unsigned __int64 *, struct tagDBBINDING **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180002400`
- `0x180016584`
- `0x180017408`
- `0x18002f092`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000243f`
- `KERNEL32!GetCurrentThreadId` at `0x18000243f`
- `KERNEL32!LeaveCriticalSection` at `0x18000251c`
- `KERNEL32!LeaveCriticalSection` at `0x180002559`
- `KERNEL32!LeaveCriticalSection` at `0x18000258f`
- `KERNEL32!LeaveCriticalSection` at `0x18000251c`
- `KERNEL32!LeaveCriticalSection` at `0x180002559`
- `KERNEL32!LeaveCriticalSection` at `0x18000258f`
- `ole32!CoTaskMemAlloc` at `0x1800024d5`
- `ole32!CoTaskMemAlloc` at `0x1800024d5`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180002466`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180002466`
- `MSDART!UMSEnterCSWraper` at `0x18000242d`
- `MSDART!UMSEnterCSWraper` at `0x18000242d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIAccessor::GetBindings(
        CImpIAccessor *this,
        unsigned int a2,
        unsigned int *a3,
        unsigned __int64 *a4,
        struct tagDBBINDING **a5)
{
  __int64 v9; // rbx
  void **v10; // rsi
  unsigned int *v11; // rdi
  unsigned int v12; // ebp
  LPVOID v13; // rax
  bool v14; // zf
  __int64 v15; // rcx
  int v17; // ecx
  unsigned int v18; // edi
  __int64 v19; // rcx
  unsigned int v20; // esi
  __int64 v21; // rcx
  unsigned int *v22; // [rsp+50h] [rbp+8h] BYREF
  __int64 v23; // [rsp+60h] [rbp+18h]

  v9 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v9);
  if ( !*(_DWORD *)(v9 + 12) )
    *(_DWORD *)(v9 + 8) = GetCurrentThreadId();
  ++*(_DWORD *)(v9 + 12);
  ++*(_DWORD *)(v9 + 16);
  v23 = v9;
  v22 = 0;
  SetErrorInfo(0, 0);
  if ( a3 && a4 && (v10 = (void **)a5) != 0 )
  {
    *a3 = 0;
    *a4 = 0;
    *v10 = 0;
    if ( CExtBuffer::GetItemOfExtBuffer(*(CExtBuffer **)(*((_QWORD *)this + 3) + 192LL), a2, &v22) >= 0
      && (v11 = v22) != 0 )
    {
      v12 = 88 * v22[2];
      v13 = CoTaskMemAlloc(v12);
      *v10 = v13;
      if ( v13 )
      {
        *a3 = *v11;
        *a4 = v11[2];
        memcpy_0(*v10, v11 + 4, v12);
        --*(_DWORD *)(v9 + 16);
        v14 = (*(_DWORD *)(v9 + 12))-- == 1;
        if ( v14 )
          *(_DWORD *)(v9 + 8) = -1;
        v15 = *(_QWORD *)v9;
        --*(_DWORD *)(v15 + 48);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
        return 0;
      }
      v17 = -2147024882;
    }
    else
    {
      v17 = -2147217920;
    }
    v18 = Exit(v17, 0);
    --*(_DWORD *)(v9 + 16);
    v14 = (*(_DWORD *)(v9 + 12))-- == 1;
    if ( v14 )
      *(_DWORD *)(v9 + 8) = -1;
    v19 = *(_QWORD *)v9;
    --*(_DWORD *)(v19 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 8));
    return v18;
  }
  else
  {
    v20 = Exit(-2147024809, 0);
    --*(_DWORD *)(v9 + 16);
    v14 = (*(_DWORD *)(v9 + 12))-- == 1;
    if ( v14 )
      *(_DWORD *)(v9 + 8) = -1;
    v21 = *(_QWORD *)v9;
    --*(_DWORD *)(v21 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v21 + 8));
    return v20;
  }
}

```

## disassembly

```asm
0x180002400  mov     [rsp+arg_8], rbx
0x180002405  mov     [rsp+arg_18], rbp
0x18000240a  push    rsi
0x18000240b  push    rdi
0x18000240c  push    r12
0x18000240e  push    r14
0x180002410  push    r15
0x180002412  sub     rsp, 20h
0x180002416  mov     r14, r9
0x180002419  mov     r15, r8
0x18000241c  mov     r12, rdx
0x18000241f  mov     rbp, rcx
0x180002422  mov     rbx, [rcx+18h]
0x180002426  sub     rbx, 0FFFFFFFFFFFFFF80h
0x18000242a  mov     rcx, rbx
0x18000242d  call    cs:__imp_UMSEnterCSWraper
0x180002434  nop     dword ptr [rax+rax+00h]
0x180002439  cmp     dword ptr [rbx+0Ch], 0
0x18000243d  jnz     short loc_18000244E
0x18000243f  call    cs:__imp_GetCurrentThreadId
0x180002446  nop     dword ptr [rax+rax+00h]
0x18000244b  mov     [rbx+8], eax
0x18000244e  inc     dword ptr [rbx+0Ch]
0x180002451  inc     dword ptr [rbx+10h]
0x180002454  mov     [rsp+48h+arg_10], rbx
0x180002459  mov     [rsp+48h+arg_0], 0
0x180002462  xor     edx, edx; perrinfo
0x180002464  xor     ecx, ecx; dwReserved
0x180002466  call    cs:__imp_SetErrorInfo
0x18000246d  nop     dword ptr [rax+rax+00h]
0x180002472  test    r15, r15
0x180002475  jz      loc_180002569
0x18000247b  test    r14, r14
0x18000247e  jz      loc_180002569
0x180002484  mov     rsi, [rsp+48h+arg_20]
0x180002489  test    rsi, rsi
0x18000248c  jz      loc_180002569
0x180002492  mov     dword ptr [r15], 0
0x180002499  mov     qword ptr [r14], 0
0x1800024a0  mov     qword ptr [rsi], 0
0x1800024a7  mov     edx, r12d; unsigned int
0x1800024aa  mov     rcx, [rbp+18h]
0x1800024ae  lea     r8, [rsp+48h+arg_0]; void *
0x1800024b3  mov     rcx, [rcx+0C0h]; this
0x1800024ba  call    ?GetItemOfExtBuffer@CExtBuffer@@QEAAJKPEAX@Z; CExtBuffer::GetItemOfExtBuffer(ulong,void *)
0x1800024bf  test    eax, eax
0x1800024c1  js      short loc_180002533
0x1800024c3  mov     rdi, [rsp+48h+arg_0]
0x1800024c8  test    rdi, rdi
0x1800024cb  jz      short loc_180002533
0x1800024cd  imul    eax, [rdi+8], 58h ; 'X'
0x1800024d1  mov     ebp, eax
0x1800024d3  mov     ecx, eax; cb
0x1800024d5  call    cs:__imp_CoTaskMemAlloc
0x1800024dc  nop     dword ptr [rax+rax+00h]
0x1800024e1  mov     [rsi], rax
0x1800024e4  test    rax, rax
0x1800024e7  jz      short loc_18000252C
0x1800024e9  mov     eax, [rdi]
0x1800024eb  mov     [r15], eax
0x1800024ee  mov     eax, [rdi+8]
0x1800024f1  mov     [r14], rax
0x1800024f4  lea     rdx, [rdi+10h]; Src
0x1800024f8  mov     r8d, ebp; Size
0x1800024fb  mov     rcx, [rsi]; void *
0x1800024fe  call    memcpy_0
0x180002503  nop
0x180002504  or      edx, 0FFFFFFFFh
0x180002507  add     [rbx+10h], edx
0x18000250a  add     [rbx+0Ch], edx
0x18000250d  jnz     short loc_180002512
0x18000250f  mov     [rbx+8], edx
0x180002512  mov     rcx, [rbx]
0x180002515  dec     dword ptr [rcx+30h]
0x180002518  add     rcx, 8; lpCriticalSection
0x18000251c  call    cs:__imp_LeaveCriticalSection
0x180002523  nop     dword ptr [rax+rax+00h]
0x180002528  xor     eax, eax
0x18000252a  jmp     short loc_18000259D
0x18000252c  mov     ecx, 8007000Eh
0x180002531  jmp     short loc_180002538
0x180002533  mov     ecx, 80040E00h; int
0x180002538  xor     edx, edx; unsigned int
0x18000253a  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18000253f  mov     edi, eax
0x180002541  or      edx, 0FFFFFFFFh
0x180002544  add     [rbx+10h], edx
0x180002547  add     [rbx+0Ch], edx
0x18000254a  jnz     short loc_18000254F
0x18000254c  mov     [rbx+8], edx
0x18000254f  mov     rcx, [rbx]
0x180002552  dec     dword ptr [rcx+30h]
0x180002555  add     rcx, 8; lpCriticalSection
0x180002559  call    cs:__imp_LeaveCriticalSection
0x180002560  nop     dword ptr [rax+rax+00h]
0x180002565  mov     eax, edi
0x180002567  jmp     short loc_18000259D
0x180002569  xor     edx, edx; unsigned int
0x18000256b  mov     ecx, 80070057h; int
0x180002570  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180002575  mov     esi, eax
0x180002577  or      edx, 0FFFFFFFFh
0x18000257a  add     [rbx+10h], edx
0x18000257d  add     [rbx+0Ch], edx
0x180002580  jnz     short loc_180002585
0x180002582  mov     [rbx+8], edx
0x180002585  mov     rcx, [rbx]
0x180002588  dec     dword ptr [rcx+30h]
0x18000258b  add     rcx, 8; lpCriticalSection
0x18000258f  call    cs:__imp_LeaveCriticalSection
0x180002596  nop     dword ptr [rax+rax+00h]
0x18000259b  mov     eax, esi
0x18000259d  mov     rbx, [rsp+48h+arg_8]
0x1800025a2  mov     rbp, [rsp+48h+arg_18]
0x1800025a7  add     rsp, 20h
0x1800025ab  pop     r15
0x1800025ad  pop     r14
0x1800025af  pop     r12
0x1800025b1  pop     rdi
0x1800025b2  pop     rsi
0x1800025b3  retn
```
