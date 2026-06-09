# CSessionArbitrationHelper::Copy(DynArray<long,ulong> &,long * *,ulong *)

- ea: `0x18002c144`
- end: `0x18002c3fa`
- name: `?Copy@CSessionArbitrationHelper@@AEAAJAEAV?$DynArray@JK@@PEAPEAJPEAK@Z`
- size: `694`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180021560`
- `0x180089900`
- `0x180089cc0`
- `0x18008a0e0`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x180014ff0`
- `0x18002c144`
- `0x18004b86c`
- `0x18004bd84`
- `0x180097010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18002c33e`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18002c33e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c3c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c3c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c367`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c367`

## string_xrefs

- `0x18002c1bb`: `CSessionArbitrationHelper::Copy`

## pseudocode

```c
__int64 __fastcall CSessionArbitrationHelper::Copy(
        struct ISessionManagerInternal *a1,
        __int64 *a2,
        _QWORD *a3,
        unsigned int *a4)
{
  _QWORD *v5; // r12
  unsigned int v7; // eax
  unsigned __int64 v8; // rsi
  unsigned int v9; // ebx
  int InstanceOfSessionManagerInternal; // eax
  struct ISessionManagerInternal *v11; // rcx
  __int64 v12; // rax
  char *v13; // rdi
  unsigned __int64 v14; // rax
  unsigned int i; // ebx
  __int64 v16; // rax
  char *v17; // r14
  unsigned int (__fastcall *v18)(__int64 *, _QWORD, char *); // rax
  unsigned int v19; // ebx
  _DWORD *v20; // rsi
  unsigned int v21; // ebx
  __int64 j; // r14
  __int64 v24; // [rsp+30h] [rbp-28h] BYREF
  __int64 v25; // [rsp+38h] [rbp-20h] BYREF
  __int64 v26[3]; // [rsp+40h] [rbp-18h] BYREF
  struct ISessionManagerInternal *v27; // [rsp+A0h] [rbp+48h] BYREF
  __int64 v28; // [rsp+A8h] [rbp+50h] BYREF
  _QWORD *v29; // [rsp+B0h] [rbp+58h]
  struct ISessionManagerInternal *v30; // [rsp+B8h] [rbp+60h] BYREF

  v29 = a3;
  v27 = a1;
  *a3 = 0;
  *a4 = 0;
  v5 = a3;
  v7 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 24))(a2);
  v8 = v7;
  if ( v7 )
  {
    v28 = 0;
    v27 = 0;
    InstanceOfSessionManagerInternal = ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&v27);
    v11 = v27;
    v9 = InstanceOfSessionManagerInternal;
    v30 = v27;
    if ( InstanceOfSessionManagerInternal >= 0 )
    {
      v12 = *(_QWORD *)v27;
      LOBYTE(v27) = 0;
      if ( (*(int (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(v12 + 24))(v11, &v28) >= 0 )
      {
        v14 = 16 * v8;
        if ( !is_mul_ok(v8, 0x10u) )
          v14 = -1;
        v13 = (char *)operator new(v14, (const struct std::nothrow_t *)&std::nothrow);
        if ( v13 )
        {
          for ( i = 0; i < (unsigned int)v8; ++i )
          {
            v16 = *a2;
            v17 = &v13[16 * i];
            v24 = 0;
            v18 = *(unsigned int (__fastcall **)(__int64 *, _QWORD, char *))(v16 + 40);
            v26[0] = 0;
            v25 = 0;
            if ( !v18(a2, i, v17) )
            {
              _DbgPrintMessage(4, "GetAt() failed; skipping session list sort..");
              goto LABEL_18;
            }
            if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v28 + 24LL))(
                   v28,
                   *(unsigned int *)v17,
                   &v24) < 0 )
            {
              _DbgPrintMessage(4, "FindSessionById() failed; skipping session list sort..");
              goto LABEL_18;
            }
            if ( (*(int (__fastcall **)(__int64, __int64 *, __int64 *, unsigned int *))(*(_QWORD *)v24 + 200LL))(
                   v24,
                   v26,
                   &v25,
                   (unsigned int *)v17 + 2) < 0 )
            {
              _DbgPrintMessage(4, "GetTimes() failed; skipping session list sort..");
LABEL_18:
              SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v24);
              goto LABEL_22;
            }
            SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v24);
          }
          qsort(v13, v8, 0x10u, CompareSessionLogonTime);
          LOBYTE(v27) = 1;
        }
        else
        {
          _DbgPrintMessage(4, "memory allocation failed; skipping session list sort..");
        }
LABEL_22:
        SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v28);
        SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v30);
        v5 = v29;
      }
      else
      {
        v13 = 0;
        _DbgPrintMessage(4, "GetSessionList() failed; skipping session list sort..");
        SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v28);
        SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v30);
      }
      v19 = 4 * v8;
      v20 = CoTaskMemAlloc((unsigned int)(4 * v8));
      if ( v20 )
      {
        v21 = v19 >> 2;
        for ( j = 0; (unsigned int)j < v21; j = (unsigned int)(j + 1) )
        {
          if ( (_BYTE)v27 && v13 )
          {
            v20[j] = *(_DWORD *)&v13[16 * (unsigned int)j];
          }
          else if ( !(*(unsigned int (__fastcall **)(__int64 *, _QWORD, _DWORD *))(*a2 + 40))(
                       a2,
                       (unsigned int)j,
                       &v20[j]) )
          {
            CoTaskMemFree(v20);
            v9 = -2147024883;
            goto LABEL_34;
          }
        }
        *v5 = v20;
        *a4 = v21;
        v9 = 0;
      }
      else
      {
        v9 = -2147024882;
      }
LABEL_34:
      if ( v13 )
        operator delete(v13);
    }
    else
    {
      _DbgPrintMessage(
        8,
        "CUtils::GetInstanceOfSessionManager failed: 0x%x in %s",
        InstanceOfSessionManagerInternal,
        "CSessionArbitrationHelper::Copy");
      SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v28);
      SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v30);
    }
  }
  else
  {
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18002c144  mov     [rsp-40h+arg_10], r8
0x18002c149  mov     [rsp-40h+arg_0], rcx
0x18002c14e  push    rbp
0x18002c14f  push    rbx
0x18002c150  push    rsi
0x18002c151  push    rdi
0x18002c152  push    r12
0x18002c154  push    r13
0x18002c156  push    r14
0x18002c158  push    r15
0x18002c15a  mov     rbp, rsp
0x18002c15d  sub     rsp, 58h
0x18002c161  mov     qword ptr [r8], 0
0x18002c168  mov     rcx, rdx
0x18002c16b  mov     dword ptr [r9], 0
0x18002c172  mov     r13, r9
0x18002c175  mov     rax, [rdx]
0x18002c178  mov     r12, r8
0x18002c17b  mov     r15, rdx
0x18002c17e  mov     rax, [rax+18h]
0x18002c182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c187  mov     esi, eax
0x18002c189  test    eax, eax
0x18002c18b  jnz     short loc_18002C194
0x18002c18d  xor     ebx, ebx
0x18002c18f  jmp     loc_18002C3E7
0x18002c194  lea     rcx, [rbp+arg_0]; struct ISessionManagerInternal **
0x18002c198  mov     [rbp+arg_8], 0
0x18002c1a0  mov     [rbp+arg_0], 0
0x18002c1a8  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18002c1ad  mov     rcx, [rbp+arg_0]
0x18002c1b1  mov     ebx, eax
0x18002c1b3  mov     [rbp+arg_18], rcx
0x18002c1b7  test    eax, eax
0x18002c1b9  jns     short loc_18002C1ED
0x18002c1bb  lea     r9, aCsessionarbitr_5; "CSessionArbitrationHelper::Copy"
0x18002c1c2  mov     r8d, eax
0x18002c1c5  lea     rdx, aCutilsGetinsta_0; "CUtils::GetInstanceOfSessionManager fai"...
0x18002c1cc  mov     ecx, 8; int
0x18002c1d1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c1d6  lea     rcx, [rbp+arg_8]
0x18002c1da  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18002c1df  lea     rcx, [rbp+arg_18]
0x18002c1e3  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18002c1e8  jmp     loc_18002C3E7
0x18002c1ed  mov     rax, [rcx]
0x18002c1f0  lea     rdx, [rbp+arg_8]
0x18002c1f4  mov     byte ptr [rbp+arg_0], 0
0x18002c1f8  mov     rax, [rax+18h]
0x18002c1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c201  test    eax, eax
0x18002c203  jns     short loc_18002C22D
0x18002c205  xor     edi, edi
0x18002c207  lea     rdx, aGetsessionlist; "GetSessionList() failed; skipping sessi"...
0x18002c20e  lea     ecx, [rdi+4]; int
0x18002c211  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c216  lea     rcx, [rbp+arg_8]
0x18002c21a  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18002c21f  lea     rcx, [rbp+arg_18]
0x18002c223  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18002c228  jmp     loc_18002C35E
0x18002c22d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002c234  mov     eax, 10h
0x18002c239  mul     rsi
0x18002c23c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002c243  cmovb   rax, rcx
0x18002c247  mov     rcx, rax; unsigned __int64
0x18002c24a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002c24f  mov     rdi, rax
0x18002c252  test    rax, rax
0x18002c255  jnz     short loc_18002C26B
0x18002c257  lea     rdx, aMemoryAllocati_0; "memory allocation failed; skipping sess"...
0x18002c25e  lea     ecx, [rax+4]; int
0x18002c261  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c266  jmp     loc_18002C348
0x18002c26b  xor     ebx, ebx
0x18002c26d  cmp     ebx, esi
0x18002c26f  jnb     loc_18002C32B
0x18002c275  mov     rax, [r15]
0x18002c278  mov     edx, ebx
0x18002c27a  mov     r14d, ebx
0x18002c27d  mov     rcx, r15
0x18002c280  shl     r14, 4
0x18002c284  add     r14, rdi
0x18002c287  mov     [rbp+var_28], 0
0x18002c28f  mov     rax, [rax+28h]
0x18002c293  mov     r8, r14
0x18002c296  mov     [rbp+var_18], 0
0x18002c29e  mov     [rbp+var_20], 0
0x18002c2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2ab  test    eax, eax
0x18002c2ad  jz      short loc_18002C322
0x18002c2af  mov     rcx, [rbp+arg_8]
0x18002c2b3  lea     r8, [rbp+var_28]
0x18002c2b7  mov     edx, [r14]
0x18002c2ba  mov     rax, [rcx]
0x18002c2bd  mov     rax, [rax+18h]
0x18002c2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2c6  test    eax, eax
0x18002c2c8  js      short loc_18002C319
0x18002c2ca  mov     rcx, [rbp+var_28]
0x18002c2ce  lea     r9, [r14+8]
0x18002c2d2  lea     r8, [rbp+var_20]
0x18002c2d6  lea     rdx, [rbp+var_18]
0x18002c2da  mov     rax, [rcx]
0x18002c2dd  mov     rax, [rax+0C8h]
0x18002c2e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2e9  test    eax, eax
0x18002c2eb  js      short loc_18002C2FD
0x18002c2ed  lea     rcx, [rbp+var_28]
0x18002c2f1  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18002c2f6  inc     ebx
0x18002c2f8  jmp     loc_18002C26D
0x18002c2fd  lea     rdx, aGettimesFailed; "GetTimes() failed; skipping session lis"...
0x18002c304  mov     ecx, 4; int
0x18002c309  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c30e  lea     rcx, [rbp+var_28]
0x18002c312  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18002c317  jmp     short loc_18002C348
0x18002c319  lea     rdx, aFindsessionbyi_4; "FindSessionById() failed; skipping sess"...
0x18002c320  jmp     short loc_18002C304
0x18002c322  lea     rdx, aGetatFailedSki; "GetAt() failed; skipping session list s"...
0x18002c329  jmp     short loc_18002C304
0x18002c32b  lea     r9, ?CompareSessionLogonTime@@YAHPEBX0@Z; CompareFunction
0x18002c332  mov     r8d, 10h; SizeOfElements
0x18002c338  mov     rdx, rsi; NumOfElements
0x18002c33b  mov     rcx, rdi; Base
0x18002c33e  call    cs:__imp_qsort
0x18002c344  mov     byte ptr [rbp+arg_0], 1
0x18002c348  lea     rcx, [rbp+arg_8]
0x18002c34c  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18002c351  lea     rcx, [rbp+arg_18]
0x18002c355  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18002c35a  mov     r12, [rbp+arg_10]
0x18002c35e  lea     ebx, ds:0[rsi*4]
0x18002c365  mov     ecx, ebx; cb
0x18002c367  call    cs:__imp_CoTaskMemAlloc
0x18002c36d  mov     rsi, rax
0x18002c370  test    rax, rax
0x18002c373  jnz     short loc_18002C37C
0x18002c375  mov     ebx, 8007000Eh
0x18002c37a  jmp     short loc_18002C3DA
0x18002c37c  shr     ebx, 2
0x18002c37f  xor     r14d, r14d
0x18002c382  cmp     r14d, ebx
0x18002c385  jnb     short loc_18002C3D0
0x18002c387  cmp     byte ptr [rbp+arg_0], 0
0x18002c38b  jz      short loc_18002C3A1
0x18002c38d  test    rdi, rdi
0x18002c390  jz      short loc_18002C3A1
0x18002c392  mov     eax, r14d
0x18002c395  add     rax, rax
0x18002c398  mov     eax, [rdi+rax*8]
0x18002c39b  mov     [rsi+r14*4], eax
0x18002c39f  jmp     short loc_18002C3BB
0x18002c3a1  mov     rcx, [r15]
0x18002c3a4  lea     r8, [rsi+r14*4]
0x18002c3a8  mov     edx, r14d
0x18002c3ab  mov     rax, [rcx+28h]
0x18002c3af  mov     rcx, r15
0x18002c3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c3b7  test    eax, eax
0x18002c3b9  jz      short loc_18002C3C0
0x18002c3bb  inc     r14d
0x18002c3be  jmp     short loc_18002C382
0x18002c3c0  mov     rcx, rsi; pv
0x18002c3c3  call    cs:__imp_CoTaskMemFree
0x18002c3c9  mov     ebx, 8007000Dh
0x18002c3ce  jmp     short loc_18002C3DA
0x18002c3d0  mov     [r12], rsi
0x18002c3d4  mov     [r13+0], ebx
0x18002c3d8  xor     ebx, ebx
0x18002c3da  test    rdi, rdi
0x18002c3dd  jz      short loc_18002C3E7
0x18002c3df  mov     rcx, rdi; Block
0x18002c3e2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c3e7  mov     eax, ebx
0x18002c3e9  add     rsp, 58h
0x18002c3ed  pop     r15
0x18002c3ef  pop     r14
0x18002c3f1  pop     r13
0x18002c3f3  pop     r12
0x18002c3f5  pop     rdi
0x18002c3f6  pop     rsi
0x18002c3f7  pop     rbx
0x18002c3f8  pop     rbp
0x18002c3f9  retn
```
