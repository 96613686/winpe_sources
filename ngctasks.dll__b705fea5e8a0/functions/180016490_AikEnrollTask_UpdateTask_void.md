# AikEnrollTask::UpdateTask(void)

- ea: `0x180016490`
- end: `0x180016568`
- name: `?UpdateTask@AikEnrollTask@@QEAAJXZ`
- size: `216`
- prototype: `__int64 __fastcall(AikEnrollTask *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800154ec`
- `0x1800161f4`
- `0x180016570`

## callees

- `0x180008ab0`
- `0x18000cc34`
- `0x180016490`
- `0x180022010`

## string_xrefs

- `0x180016536`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AikEnrollTask::UpdateTask(AikEnrollTask *this)
{
  __int64 v2; // rcx
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v6; // [rsp+50h] [rbp-19h] BYREF
  __int128 v7; // [rsp+60h] [rbp-9h]
  __int64 v8; // [rsp+70h] [rbp+7h]
  __int128 v9; // [rsp+80h] [rbp+17h]
  __int64 v10; // [rsp+90h] [rbp+27h]
  int v11[4]; // [rsp+A0h] [rbp+37h] BYREF
  __int64 v12; // [rsp+B0h] [rbp+47h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v7 = 0;
  LOWORD(v7) = 1;
  v6 = 0;
  v2 = *((_QWORD *)this + 1);
  v8 = 0;
  v9 = 0;
  v10 = 0;
  *(_OWORD *)v11 = 0;
  v12 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v2 + 136LL))(
         v2,
         *(_QWORD *)this,
         *((_QWORD *)this + 2),
         20);
  v4 = v3;
  if ( v3 >= 0 )
    v4 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
      (const char *)(unsigned int)v3,
      (int)v11);
  ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(&v6);
  return v4;
}

```

## disassembly

```asm
0x180016490  mov     [rsp-8+arg_0], rbx
0x180016495  push    rbp
0x180016496  lea     rbp, [rsp-57h]
0x18001649b  sub     rsp, 0C0h
0x1800164a2  mov     rdx, rcx
0x1800164a5  xorps   xmm2, xmm2
0x1800164a8  xor     r9d, r9d
0x1800164ab  xorps   xmm0, xmm0
0x1800164ae  xor     r8d, r8d
0x1800164b1  movups  [rbp+57h+var_60], xmm0
0x1800164b5  lea     eax, [r9+1]
0x1800164b9  mov     word ptr [rbp+57h+var_60], ax
0x1800164bd  mov     [rbp+57h+var_70], r8
0x1800164c1  mov     rcx, [rcx+8]
0x1800164c5  movups  xmm0, [rbp+57h+var_60]
0x1800164c9  movaps  [rbp+57h+var_60], xmm0
0x1800164cd  mov     [rbp+57h+var_50], r8
0x1800164d1  movaps  [rbp+57h+var_40], xmm2
0x1800164d5  mov     [rbp+57h+var_30], r9
0x1800164d9  movaps  xmmword ptr [rbp+57h+var_20], xmm2
0x1800164dd  mov     [rbp+57h+var_10], r9
0x1800164e1  mov     rax, [rcx]
0x1800164e4  lea     r8, [rbp+57h+var_70]
0x1800164e8  mov     [rsp+0C0h+var_80], r8
0x1800164ed  lea     r8, [rbp+57h+var_60]
0x1800164f1  mov     [rsp+0C0h+var_88], r8
0x1800164f6  mov     [rsp+0C0h+var_90], 5
0x1800164fe  lea     r8, [rbp+57h+var_40]
0x180016502  mov     [rsp+0C0h+var_98], r8
0x180016507  lea     r8, [rbp+57h+var_20]
0x18001650b  mov     qword ptr [rsp+0C0h+var_A0], r8; int
0x180016510  mov     r9d, 14h
0x180016516  mov     r8, [rdx+10h]
0x18001651a  mov     rdx, [rdx]
0x18001651d  mov     rax, [rax+88h]
0x180016524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016529  mov     ebx, eax
0x18001652b  test    eax, eax
0x18001652d  jns     short loc_18001654A
0x18001652f  mov     rcx, [rbp+5Fh]; this
0x180016533  mov     r9d, eax; char *
0x180016536  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001653d  mov     edx, 1B6h; void *
0x180016542  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016547  nop
0x180016548  jmp     short loc_18001654C
0x18001654a  xor     ebx, ebx
0x18001654c  lea     rcx, [rbp+57h+var_70]
0x180016550  call    ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
0x180016555  mov     eax, ebx
0x180016557  mov     rbx, [rsp+0C0h+arg_0]
0x18001655f  add     rsp, 0C0h
0x180016566  pop     rbp
0x180016567  retn
```
