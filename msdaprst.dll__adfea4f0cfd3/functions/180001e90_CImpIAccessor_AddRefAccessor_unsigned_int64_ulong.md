# CImpIAccessor::AddRefAccessor(unsigned __int64,ulong *)

- ea: `0x180001e90`
- end: `0x180001faf`
- name: `?AddRefAccessor@CImpIAccessor@@UEAAJ_KPEAK@Z`
- size: `287`
- prototype: `int(CImpIAccessor *__hidden this, unsigned __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001e90`
- `0x180016584`
- `0x180017408`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180001ec8`
- `KERNEL32!GetCurrentThreadId` at `0x180001ec8`
- `KERNEL32!LeaveCriticalSection` at `0x180001f57`
- `KERNEL32!LeaveCriticalSection` at `0x180001f8d`
- `KERNEL32!LeaveCriticalSection` at `0x180001f57`
- `KERNEL32!LeaveCriticalSection` at `0x180001f8d`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180001eef`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180001eef`
- `MSDART!UMSEnterCSWraper` at `0x180001eb6`
- `MSDART!UMSEnterCSWraper` at `0x180001eb6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIAccessor::AddRefAccessor(CImpIAccessor *this, unsigned int a2, unsigned int *a3)
{
  __int64 v6; // rbx
  unsigned int v7; // eax
  bool v8; // zf
  __int64 v9; // rcx
  unsigned int v11; // esi
  __int64 v12; // rcx
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+50h] [rbp+18h]

  v6 = *((_QWORD *)this + 3) + 128LL;
  UMSEnterCSWraper(v6);
  if ( !*(_DWORD *)(v6 + 12) )
    *(_DWORD *)(v6 + 8) = GetCurrentThreadId();
  ++*(_DWORD *)(v6 + 12);
  ++*(_DWORD *)(v6 + 16);
  v14 = v6;
  v13 = 0;
  SetErrorInfo(0, 0);
  if ( a3 )
    *a3 = 0;
  if ( CExtBuffer::GetItemOfExtBuffer(*(CExtBuffer **)(*((_QWORD *)this + 3) + 192LL), a2, &v13) >= 0 && v13 )
  {
    v7 = _InterlockedIncrement((volatile signed __int32 *)(v13 + 4));
    if ( a3 )
      *a3 = v7;
    --*(_DWORD *)(v6 + 16);
    v8 = (*(_DWORD *)(v6 + 12))-- == 1;
    if ( v8 )
      *(_DWORD *)(v6 + 8) = -1;
    v9 = *(_QWORD *)v6;
    --*(_DWORD *)(v9 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
    return 0;
  }
  else
  {
    v11 = Exit(-2147217920, 0);
    --*(_DWORD *)(v6 + 16);
    v8 = (*(_DWORD *)(v6 + 12))-- == 1;
    if ( v8 )
      *(_DWORD *)(v6 + 8) = -1;
    v12 = *(_QWORD *)v6;
    --*(_DWORD *)(v12 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 8));
    return v11;
  }
}

```

## disassembly

```asm
0x180001e90  mov     [rsp+arg_8], rbx
0x180001e95  mov     [rsp+arg_18], rbp
0x180001e9a  push    rsi
0x180001e9b  push    rdi
0x180001e9c  push    r14
0x180001e9e  sub     rsp, 20h
0x180001ea2  mov     rsi, r8
0x180001ea5  mov     r14, rdx
0x180001ea8  mov     rbp, rcx
0x180001eab  mov     rbx, [rcx+18h]
0x180001eaf  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180001eb3  mov     rcx, rbx
0x180001eb6  call    cs:__imp_UMSEnterCSWraper
0x180001ebd  nop     dword ptr [rax+rax+00h]
0x180001ec2  cmp     dword ptr [rbx+0Ch], 0
0x180001ec6  jnz     short loc_180001ED7
0x180001ec8  call    cs:__imp_GetCurrentThreadId
0x180001ecf  nop     dword ptr [rax+rax+00h]
0x180001ed4  mov     [rbx+8], eax
0x180001ed7  inc     dword ptr [rbx+0Ch]
0x180001eda  inc     dword ptr [rbx+10h]
0x180001edd  mov     [rsp+38h+arg_10], rbx
0x180001ee2  mov     [rsp+38h+arg_0], 0
0x180001eeb  xor     edx, edx; perrinfo
0x180001eed  xor     ecx, ecx; dwReserved
0x180001eef  call    cs:__imp_SetErrorInfo
0x180001ef6  nop     dword ptr [rax+rax+00h]
0x180001efb  test    rsi, rsi
0x180001efe  jz      short loc_180001F06
0x180001f00  mov     dword ptr [rsi], 0
0x180001f06  mov     edx, r14d; unsigned int
0x180001f09  mov     rcx, [rbp+18h]
0x180001f0d  lea     r8, [rsp+38h+arg_0]; void *
0x180001f12  mov     rcx, [rcx+0C0h]; this
0x180001f19  call    ?GetItemOfExtBuffer@CExtBuffer@@QEAAJKPEAX@Z; CExtBuffer::GetItemOfExtBuffer(ulong,void *)
0x180001f1e  test    eax, eax
0x180001f20  js      short loc_180001F67
0x180001f22  mov     rcx, [rsp+38h+arg_0]
0x180001f27  test    rcx, rcx
0x180001f2a  jz      short loc_180001F67
0x180001f2c  mov     eax, 1
0x180001f31  lock xadd [rcx+4], eax
0x180001f36  inc     eax
0x180001f38  test    rsi, rsi
0x180001f3b  jz      short loc_180001F3F
0x180001f3d  mov     [rsi], eax
0x180001f3f  or      edx, 0FFFFFFFFh
0x180001f42  add     [rbx+10h], edx
0x180001f45  add     [rbx+0Ch], edx
0x180001f48  jnz     short loc_180001F4D
0x180001f4a  mov     [rbx+8], edx
0x180001f4d  mov     rcx, [rbx]
0x180001f50  dec     dword ptr [rcx+30h]
0x180001f53  add     rcx, 8; lpCriticalSection
0x180001f57  call    cs:__imp_LeaveCriticalSection
0x180001f5e  nop     dword ptr [rax+rax+00h]
0x180001f63  xor     eax, eax
0x180001f65  jmp     short loc_180001F9B
0x180001f67  xor     edx, edx; unsigned int
0x180001f69  mov     ecx, 80040E00h; int
0x180001f6e  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180001f73  mov     esi, eax
0x180001f75  or      edx, 0FFFFFFFFh
0x180001f78  add     [rbx+10h], edx
0x180001f7b  add     [rbx+0Ch], edx
0x180001f7e  jnz     short loc_180001F83
0x180001f80  mov     [rbx+8], edx
0x180001f83  mov     rcx, [rbx]
0x180001f86  dec     dword ptr [rcx+30h]
0x180001f89  add     rcx, 8; lpCriticalSection
0x180001f8d  call    cs:__imp_LeaveCriticalSection
0x180001f94  nop     dword ptr [rax+rax+00h]
0x180001f99  mov     eax, esi
0x180001f9b  mov     rbx, [rsp+38h+arg_8]
0x180001fa0  mov     rbp, [rsp+38h+arg_18]
0x180001fa5  add     rsp, 20h
0x180001fa9  pop     r14
0x180001fab  pop     rdi
0x180001fac  pop     rsi
0x180001fad  retn
```
