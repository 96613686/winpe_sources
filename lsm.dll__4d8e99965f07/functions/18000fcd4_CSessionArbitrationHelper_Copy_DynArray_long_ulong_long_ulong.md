# CSessionArbitrationHelper::Copy(DynArray<long,ulong> &,long * *,ulong *)

- ea: `0x18000fcd4`
- end: `0x18000ff9d`
- name: `?Copy@CSessionArbitrationHelper@@AEAAJAEAV?$DynArray@JK@@PEAPEAJPEAK@Z`
- size: `713`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800102d0`
- `0x18008e690`
- `0x18008ea50`
- `0x18008ee70`

## callees

- `0x1800077a0`
- `0x18000c684`
- `0x18000f320`
- `0x18000fcd4`
- `0x18004ec5c`
- `0x18004f174`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18000fece`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18000fece`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ff5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ff5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fefd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fefd`

## string_xrefs

- `0x18000fd4b`: `CSessionArbitrationHelper::Copy`

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
0x18000fcd4  mov     [rsp-40h+arg_10], r8
0x18000fcd9  mov     [rsp-40h+arg_0], rcx
0x18000fcde  push    rbp
0x18000fcdf  push    rbx
0x18000fce0  push    rsi
0x18000fce1  push    rdi
0x18000fce2  push    r12
0x18000fce4  push    r13
0x18000fce6  push    r14
0x18000fce8  push    r15
0x18000fcea  mov     rbp, rsp
0x18000fced  sub     rsp, 58h
0x18000fcf1  mov     qword ptr [r8], 0
0x18000fcf8  mov     rcx, rdx
0x18000fcfb  mov     dword ptr [r9], 0
0x18000fd02  mov     r13, r9
0x18000fd05  mov     rax, [rdx]
0x18000fd08  mov     r12, r8
0x18000fd0b  mov     r15, rdx
0x18000fd0e  mov     rax, [rax+18h]
0x18000fd12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd17  mov     esi, eax
0x18000fd19  test    eax, eax
0x18000fd1b  jnz     short loc_18000FD24
0x18000fd1d  xor     ebx, ebx
0x18000fd1f  jmp     loc_18000FF89
0x18000fd24  lea     rcx, [rbp+arg_0]; struct ISessionManagerInternal **
0x18000fd28  mov     [rbp+arg_8], 0
0x18000fd30  mov     [rbp+arg_0], 0
0x18000fd38  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18000fd3d  mov     rcx, [rbp+arg_0]
0x18000fd41  mov     ebx, eax
0x18000fd43  mov     [rbp+arg_18], rcx
0x18000fd47  test    eax, eax
0x18000fd49  jns     short loc_18000FD7D
0x18000fd4b  lea     r9, aCsessionarbitr_5; "CSessionArbitrationHelper::Copy"
0x18000fd52  mov     r8d, eax
0x18000fd55  lea     rdx, aCutilsGetinsta_0; "CUtils::GetInstanceOfSessionManager fai"...
0x18000fd5c  mov     ecx, 8; int
0x18000fd61  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000fd66  lea     rcx, [rbp+arg_8]
0x18000fd6a  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18000fd6f  lea     rcx, [rbp+arg_18]
0x18000fd73  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18000fd78  jmp     loc_18000FF89
0x18000fd7d  mov     rax, [rcx]
0x18000fd80  lea     rdx, [rbp+arg_8]
0x18000fd84  mov     byte ptr [rbp+arg_0], 0
0x18000fd88  mov     rax, [rax+18h]
0x18000fd8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd91  test    eax, eax
0x18000fd93  jns     short loc_18000FDBD
0x18000fd95  xor     edi, edi
0x18000fd97  lea     rdx, aGetsessionlist; "GetSessionList() failed; skipping sessi"...
0x18000fd9e  lea     ecx, [rdi+4]; int
0x18000fda1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000fda6  lea     rcx, [rbp+arg_8]
0x18000fdaa  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18000fdaf  lea     rcx, [rbp+arg_18]
0x18000fdb3  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18000fdb8  jmp     loc_18000FEF4
0x18000fdbd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000fdc4  mov     eax, 10h
0x18000fdc9  mul     rsi
0x18000fdcc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fdd3  cmovb   rax, rcx
0x18000fdd7  mov     rcx, rax; unsigned __int64
0x18000fdda  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000fddf  mov     rdi, rax
0x18000fde2  test    rax, rax
0x18000fde5  jnz     short loc_18000FDFB
0x18000fde7  lea     rdx, aMemoryAllocati_0; "memory allocation failed; skipping sess"...
0x18000fdee  lea     ecx, [rax+4]; int
0x18000fdf1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000fdf6  jmp     loc_18000FEDE
0x18000fdfb  xor     ebx, ebx
0x18000fdfd  cmp     ebx, esi
0x18000fdff  jnb     loc_18000FEBB
0x18000fe05  mov     rax, [r15]
0x18000fe08  mov     edx, ebx
0x18000fe0a  mov     r14d, ebx
0x18000fe0d  mov     rcx, r15
0x18000fe10  shl     r14, 4
0x18000fe14  add     r14, rdi
0x18000fe17  mov     [rbp+var_28], 0
0x18000fe1f  mov     rax, [rax+28h]
0x18000fe23  mov     r8, r14
0x18000fe26  mov     [rbp+var_18], 0
0x18000fe2e  mov     [rbp+var_20], 0
0x18000fe36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe3b  test    eax, eax
0x18000fe3d  jz      short loc_18000FEB2
0x18000fe3f  mov     rcx, [rbp+arg_8]
0x18000fe43  lea     r8, [rbp+var_28]
0x18000fe47  mov     edx, [r14]
0x18000fe4a  mov     rax, [rcx]
0x18000fe4d  mov     rax, [rax+18h]
0x18000fe51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe56  test    eax, eax
0x18000fe58  js      short loc_18000FEA9
0x18000fe5a  mov     rcx, [rbp+var_28]
0x18000fe5e  lea     r9, [r14+8]
0x18000fe62  lea     r8, [rbp+var_20]
0x18000fe66  lea     rdx, [rbp+var_18]
0x18000fe6a  mov     rax, [rcx]
0x18000fe6d  mov     rax, [rax+0C8h]
0x18000fe74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe79  test    eax, eax
0x18000fe7b  js      short loc_18000FE8D
0x18000fe7d  lea     rcx, [rbp+var_28]
0x18000fe81  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18000fe86  inc     ebx
0x18000fe88  jmp     loc_18000FDFD
0x18000fe8d  lea     rdx, aGettimesFailed; "GetTimes() failed; skipping session lis"...
0x18000fe94  mov     ecx, 4; int
0x18000fe99  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000fe9e  lea     rcx, [rbp+var_28]
0x18000fea2  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18000fea7  jmp     short loc_18000FEDE
0x18000fea9  lea     rdx, aFindsessionbyi_4; "FindSessionById() failed; skipping sess"...
0x18000feb0  jmp     short loc_18000FE94
0x18000feb2  lea     rdx, aGetatFailedSki; "GetAt() failed; skipping session list s"...
0x18000feb9  jmp     short loc_18000FE94
0x18000febb  lea     r9, ?CompareSessionLogonTime@@YAHPEBX0@Z; CompareFunction
0x18000fec2  mov     r8d, 10h; SizeOfElements
0x18000fec8  mov     rdx, rsi; NumOfElements
0x18000fecb  mov     rcx, rdi; Base
0x18000fece  call    cs:__imp_qsort
0x18000fed5  nop     dword ptr [rax+rax+00h]
0x18000feda  mov     byte ptr [rbp+arg_0], 1
0x18000fede  lea     rcx, [rbp+arg_8]
0x18000fee2  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18000fee7  lea     rcx, [rbp+arg_18]
0x18000feeb  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18000fef0  mov     r12, [rbp+arg_10]
0x18000fef4  lea     ebx, ds:0[rsi*4]
0x18000fefb  mov     ecx, ebx; cb
0x18000fefd  call    cs:__imp_CoTaskMemAlloc
0x18000ff04  nop     dword ptr [rax+rax+00h]
0x18000ff09  mov     rsi, rax
0x18000ff0c  test    rax, rax
0x18000ff0f  jnz     short loc_18000FF18
0x18000ff11  mov     ebx, 8007000Eh
0x18000ff16  jmp     short loc_18000FF7C
0x18000ff18  shr     ebx, 2
0x18000ff1b  xor     r14d, r14d
0x18000ff1e  cmp     r14d, ebx
0x18000ff21  jnb     short loc_18000FF72
0x18000ff23  cmp     byte ptr [rbp+arg_0], 0
0x18000ff27  jz      short loc_18000FF3D
0x18000ff29  test    rdi, rdi
0x18000ff2c  jz      short loc_18000FF3D
0x18000ff2e  mov     eax, r14d
0x18000ff31  add     rax, rax
0x18000ff34  mov     eax, [rdi+rax*8]
0x18000ff37  mov     [rsi+r14*4], eax
0x18000ff3b  jmp     short loc_18000FF57
0x18000ff3d  mov     rcx, [r15]
0x18000ff40  lea     r8, [rsi+r14*4]
0x18000ff44  mov     edx, r14d
0x18000ff47  mov     rax, [rcx+28h]
0x18000ff4b  mov     rcx, r15
0x18000ff4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff53  test    eax, eax
0x18000ff55  jz      short loc_18000FF5C
0x18000ff57  inc     r14d
0x18000ff5a  jmp     short loc_18000FF1E
0x18000ff5c  mov     rcx, rsi; pv
0x18000ff5f  call    cs:__imp_CoTaskMemFree
0x18000ff66  nop     dword ptr [rax+rax+00h]
0x18000ff6b  mov     ebx, 8007000Dh
0x18000ff70  jmp     short loc_18000FF7C
0x18000ff72  mov     [r12], rsi
0x18000ff76  mov     [r13+0], ebx
0x18000ff7a  xor     ebx, ebx
0x18000ff7c  test    rdi, rdi
0x18000ff7f  jz      short loc_18000FF89
0x18000ff81  mov     rcx, rdi; Block
0x18000ff84  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ff89  mov     eax, ebx
0x18000ff8b  add     rsp, 58h
0x18000ff8f  pop     r15
0x18000ff91  pop     r14
0x18000ff93  pop     r13
0x18000ff95  pop     r12
0x18000ff97  pop     rdi
0x18000ff98  pop     rsi
0x18000ff99  pop     rbx
0x18000ff9a  pop     rbp
0x18000ff9b  retn
```
