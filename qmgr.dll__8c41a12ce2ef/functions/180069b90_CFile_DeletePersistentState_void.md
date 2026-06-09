# CFile::DeletePersistentState(void)

- ea: `0x180069b90`
- end: `0x180069f04`
- name: `?DeletePersistentState@CFile@@QEAAJXZ`
- size: `884`
- prototype: `__int64 __fastcall(CFile *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180069668`

## callees

- `0x18000b4d0`
- `0x1800292a0`
- `0x180034760`
- `0x180069b90`
- `0x1800a3de8`
- `0x1800ab7fc`
- `0x1800b6d34`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069bff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069bff`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180069c70`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180069dd4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180069c70`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180069dd4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180069e48`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180069e48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180069d22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180069d22`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFile::DeletePersistentState(CFile *this)
{
  TaskScheduler *v2; // r15
  int v3; // esi
  DWORD CurrentThreadId; // eax
  int v5; // edx
  int v6; // ecx
  int v7; // r8d
  int v8; // edi
  __int64 v9; // r12
  int v10; // eax
  bool v11; // r13
  void *v12; // rax
  size_t v13; // rax
  int v14; // eax
  ULONGLONG v15; // rax
  EVENT_LOG *v16; // rcx
  ULONGLONG v17; // rdi
  __int64 result; // rax
  const ComError *v19; // rbx
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-188h] BYREF
  __int64 v21; // [rsp+40h] [rbp-178h]
  const ComError *v22[2]; // [rsp+48h] [rbp-170h] BYREF
  int v23; // [rsp+58h] [rbp-160h]
  __int64 v24; // [rsp+60h] [rbp-158h]
  bool v25; // [rsp+68h] [rbp-150h]
  void **pExceptionObject; // [rsp+70h] [rbp-148h] BYREF
  __int128 v27; // [rsp+78h] [rbp-140h]
  int v28; // [rsp+88h] [rbp-130h]
  int v29; // [rsp+8Ch] [rbp-12Ch]
  int v30; // [rsp+90h] [rbp-128h]
  void **v31; // [rsp+D0h] [rbp-E8h] BYREF
  __int128 v32; // [rsp+D8h] [rbp-E0h]
  int v33; // [rsp+E8h] [rbp-D0h]
  int v34; // [rsp+ECh] [rbp-CCh]
  int v35; // [rsp+F0h] [rbp-C8h]
  void **v36; // [rsp+130h] [rbp-88h] BYREF
  __int128 v37; // [rsp+138h] [rbp-80h]
  int v38; // [rsp+148h] [rbp-70h]
  int v39; // [rsp+14Ch] [rbp-6Ch]
  int v40; // [rsp+150h] [rbp-68h]
  __int64 v41; // [rsp+1C0h] [rbp+8h] BYREF
  ULONGLONG TickCount64; // [rsp+1C8h] [rbp+10h]

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids, this);
  v2 = (CJobManager *)((char *)g_Manager + 520);
  v22[1] = (CJobManager *)((char *)g_Manager + 520);
  v3 = 0;
  v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  if ( *((_DWORD *)v2 + 14) == CurrentThreadId )
  {
    v5 = 0;
    v6 = 0;
    v7 = 0;
    v8 = 0;
  }
  else
  {
    v3 = 1;
    v23 = 1;
    TaskScheduler::LockWriter(v2, 0);
    v5 = 1;
    v6 = 1;
    v7 = 1;
    v8 = 1;
  }
  try
  {
    if ( *(_BYTE *)(*((_QWORD *)this + 33) + 936LL) )
    {
      v8 = v7;
      v6 = v5;
    }
    else
    {
      v41 = *((_QWORD *)this + 50);
      if ( v41 )
      {
        TickCount64 = GetTickCount64();
        v9 = *((_QWORD *)g_Manager + 83);
        v24 = v9;
        LOBYTE(v41) = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 24LL))(v9, &v41);
        if ( v10 < 0 )
        {
          v27 = 0;
          pExceptionObject = &ComError::`vftable';
          v28 = v10;
          v29 = 16;
          v30 = 1;
          throw (ComError *)&pExceptionObject;
        }
        v11 = (_BYTE)v41 == 0;
        v25 = (_BYTE)v41 == 0;
        pvar[0] = 0;
        v21 = 0;
        v12 = CoTaskMemAlloc(0x10u);
        pvar[1] = v12;
        if ( !v12 )
        {
          v37 = 0;
          v36 = &ComError::`vftable';
          v38 = -2147024882;
          v39 = 3462;
          v40 = 1;
          throw (ComError *)&v36;
        }
        v13 = CTCoAllocPolicy::_CoTaskMemSize(v12);
        memset_0(pvar[1], 0, v13);
        LOWORD(pvar[0]) = 72;
        *(_OWORD *)pvar[1] = *((_OWORD *)this + 24);
        v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, PROPVARIANT *))(**((_QWORD **)g_Manager + 83) + 80LL))(
                *((_QWORD *)g_Manager + 83),
                1,
                pvar);
        if ( v14 < 0 )
        {
          v32 = 0;
          v31 = &ComError::`vftable';
          v33 = v14;
          v34 = 3465;
          v35 = 1;
          throw (ComError *)&v31;
        }
        v15 = GetTickCount64();
        v17 = v15 - TickCount64;
        if ( v15 - TickCount64 > 0x3A98 )
          EVENT_LOG::ReportSerialize(v16, v15 - TickCount64);
        v41 = 0;
        *((_QWORD *)this + 50) = 0;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids, v17);
        PropVariantClear(pvar);
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 32LL))(v9);
        for ( ; v3; --v3 )
          TaskScheduler::UnlockWriter(v2);
        return 0;
      }
    }
    if ( v6 )
    {
      do
      {
        TaskScheduler::UnlockWriter(v2);
        --v8;
      }
      while ( v8 );
    }
    result = 0;
  }
  catch ( const ComError *v22 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v19 = v22[0];
    }
    else
    {
      v19 = v22[0];
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        &WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids,
        *((unsigned int *)v22[0] + 6),
        *((_DWORD *)v22[0] + 7));
    }
    LODWORD(v41) = *((_DWORD *)v19 + 6);
    return (unsigned int)v41;
  }
  return result;
}

```

## disassembly

```asm
0x180069b90  mov     [rsp+arg_10], rbx
0x180069b95  mov     [rsp+arg_18], rsi
0x180069b9a  push    rdi
0x180069b9b  push    r12
0x180069b9d  push    r13
0x180069b9f  push    r14
0x180069ba1  push    r15
0x180069ba3  sub     rsp, 190h
0x180069baa  mov     r14, rcx
0x180069bad  lea     rax, WPP_GLOBAL_Control
0x180069bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180069bbb  mov     ebx, 1
0x180069bc0  cmp     rcx, rax
0x180069bc3  jz      short loc_180069BE1
0x180069bc5  test    [rcx+1Ch], bl
0x180069bc8  jz      short loc_180069BE1
0x180069bca  lea     edx, [rbx+48h]
0x180069bcd  mov     r9, r14
0x180069bd0  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x180069bd7  mov     rcx, [rcx+10h]
0x180069bdb  call    WPP_SF_q
0x180069be0  nop
0x180069be1  mov     r15, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180069be8  add     r15, 208h
0x180069bef  mov     [rsp+1B8h+var_168], r15
0x180069bf4  xor     r13d, r13d
0x180069bf7  mov     esi, r13d
0x180069bfa  mov     [rsp+1B8h+var_160], r13d
0x180069bff  call    cs:__imp_GetCurrentThreadId
0x180069c05  cmp     [r15+38h], eax
0x180069c09  jnz     short loc_180069C19
0x180069c0b  mov     edx, r13d
0x180069c0e  mov     ecx, r13d
0x180069c11  mov     r8d, r13d
0x180069c14  mov     edi, r13d
0x180069c17  jmp     short loc_180069C32
0x180069c19  mov     esi, ebx
0x180069c1b  mov     [rsp+1B8h+var_160], ebx
0x180069c1f  xor     edx, edx; void *
0x180069c21  mov     rcx, r15; this
0x180069c24  call    ?LockWriter@TaskScheduler@@QEAA_NPEAX@Z; TaskScheduler::LockWriter(void *)
0x180069c29  mov     edx, ebx
0x180069c2b  mov     ecx, ebx
0x180069c2d  mov     r8d, ebx
0x180069c30  mov     edi, ebx
0x180069c32  mov     rax, [r14+108h]
0x180069c39  cmp     [rax+3A8h], r13b
0x180069c40  jnz     loc_180069EC5
0x180069c46  mov     eax, [r14+194h]
0x180069c4d  mov     dword ptr [rsp+1B8h+arg_0+4], eax
0x180069c54  mov     eax, [r14+190h]
0x180069c5b  mov     dword ptr [rsp+1B8h+arg_0], eax
0x180069c62  cmp     [rsp+1B8h+arg_0], r13
0x180069c6a  jz      loc_180069ECA
0x180069c70  call    cs:__imp_GetTickCount64
0x180069c76  mov     [rsp+1B8h+arg_8], rax
0x180069c7e  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180069c85  mov     r12, [rcx+298h]
0x180069c8c  mov     [rsp+1B8h+var_158], r12
0x180069c91  movzx   edi, r13b
0x180069c95  mov     byte ptr [rsp+1B8h+arg_0], r13b
0x180069c9d  mov     rcx, [r12]
0x180069ca1  mov     rax, [rcx+18h]
0x180069ca5  lea     rdx, [rsp+1B8h+arg_0]
0x180069cad  mov     rcx, r12
0x180069cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069cb5  test    eax, eax
0x180069cb7  jns     short loc_180069CF7
0x180069cb9  xorps   xmm0, xmm0
0x180069cbc  movups  [rsp+1B8h+var_140], xmm0
0x180069cc1  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180069cc8  mov     [rsp+1B8h+pExceptionObject], rcx
0x180069ccd  mov     [rsp+1B8h+var_130], eax
0x180069cd4  mov     [rsp+1B8h+var_12C], 10h
0x180069cdf  mov     [rsp+1B8h+var_128], ebx
0x180069ce6  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180069ced  lea     rcx, [rsp+1B8h+pExceptionObject]; pExceptionObject
0x180069cf2  call    _CxxThrowException_0
0x180069cf7  mov     r13d, edi
0x180069cfa  cmp     byte ptr [rsp+1B8h+arg_0], 0
0x180069d02  cmovz   r13d, ebx
0x180069d06  mov     [rsp+1B8h+var_150], r13b
0x180069d0b  xorps   xmm0, xmm0
0x180069d0e  xor     eax, eax
0x180069d10  movups  xmmword ptr [rsp+1B8h+pvar], xmm0
0x180069d15  mov     [rsp+1B8h+var_178], rax
0x180069d1a  mov     word ptr [rsp+1B8h+pvar], ax
0x180069d1f  lea     ecx, [rax+10h]; cb
0x180069d22  call    cs:__imp_CoTaskMemAlloc
0x180069d28  mov     [rsp+1B8h+pvar+8], rax
0x180069d2d  test    rax, rax
0x180069d30  jz      loc_180069E79
0x180069d36  mov     rcx, rax; void *
0x180069d39  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180069d3e  mov     r8, rax; Size
0x180069d41  xor     edx, edx; Val
0x180069d43  mov     rcx, [rsp+1B8h+pvar+8]; void *
0x180069d48  call    memset_0
0x180069d4d  mov     eax, 48h ; 'H'
0x180069d52  mov     word ptr [rsp+1B8h+pvar], ax
0x180069d57  movups  xmm0, xmmword ptr [r14+180h]
0x180069d5f  mov     rax, [rsp+1B8h+pvar+8]
0x180069d64  movdqu  xmmword ptr [rax], xmm0
0x180069d68  mov     rax, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180069d6f  mov     rcx, [rax+298h]
0x180069d76  mov     rax, [rcx]
0x180069d79  lea     r8, [rsp+1B8h+pvar]
0x180069d7e  mov     edx, ebx
0x180069d80  mov     rax, [rax+50h]
0x180069d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069d89  test    eax, eax
0x180069d8b  jns     short loc_180069DD4
0x180069d8d  xorps   xmm0, xmm0
0x180069d90  movups  [rsp+1B8h+var_E0], xmm0
0x180069d98  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180069d9f  mov     [rsp+1B8h+var_E8], rcx
0x180069da7  mov     [rsp+1B8h+var_D0], eax
0x180069dae  mov     [rsp+1B8h+var_CC], 0D89h
0x180069db9  mov     [rsp+1B8h+var_C8], ebx
0x180069dc0  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180069dc7  lea     rcx, [rsp+1B8h+var_E8]; pExceptionObject
0x180069dcf  call    _CxxThrowException_0
0x180069dd4  call    cs:__imp_GetTickCount64
0x180069dda  mov     rdi, rax
0x180069ddd  sub     rdi, [rsp+1B8h+arg_8]
0x180069de5  cmp     rdi, 3A98h
0x180069dec  jbe     short loc_180069DF6
0x180069dee  mov     rdx, rdi; unsigned __int64
0x180069df1  call    ?ReportSerialize@EVENT_LOG@@QEAAJ_K@Z; EVENT_LOG::ReportSerialize(unsigned __int64)
0x180069df6  mov     [rsp+1B8h+arg_0], 0
0x180069e02  mov     rcx, [rsp+1B8h+arg_0]
0x180069e0a  mov     [r14+190h], rcx
0x180069e11  mov     rcx, cs:WPP_GLOBAL_Control
0x180069e18  lea     rax, WPP_GLOBAL_Control
0x180069e1f  cmp     rcx, rax
0x180069e22  jz      short loc_180069E43
0x180069e24  test    byte ptr [rcx+1Ch], 20h
0x180069e28  jz      short loc_180069E43
0x180069e2a  mov     edx, 4Ah ; 'J'
0x180069e2f  mov     r9, rdi
0x180069e32  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x180069e39  mov     rcx, [rcx+10h]
0x180069e3d  call    WPP_SF_q
0x180069e42  nop
0x180069e43  lea     rcx, [rsp+1B8h+pvar]; pvar
0x180069e48  call    cs:__imp_PropVariantClear
0x180069e4e  nop
0x180069e4f  test    r13b, r13b
0x180069e52  jz      short loc_180069E65
0x180069e54  mov     rax, [r12]
0x180069e58  mov     rcx, r12
0x180069e5b  mov     rax, [rax+20h]
0x180069e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069e64  nop
0x180069e65  test    esi, esi
0x180069e67  jz      short loc_180069E75
0x180069e69  mov     rcx, r15; this
0x180069e6c  call    ?UnlockWriter@TaskScheduler@@QEAAXXZ; TaskScheduler::UnlockWriter(void)
0x180069e71  sub     esi, ebx
0x180069e73  jnz     short loc_180069E69
0x180069e75  xor     eax, eax
0x180069e77  jmp     short loc_180069EE6
0x180069e79  xorps   xmm0, xmm0
0x180069e7c  movups  [rsp+1B8h+var_80], xmm0
0x180069e84  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180069e8b  mov     [rsp+1B8h+var_88], rcx
0x180069e93  mov     [rsp+1B8h+var_70], 8007000Eh
0x180069e9e  mov     [rsp+1B8h+var_6C], 0D86h
0x180069ea9  mov     [rsp+1B8h+var_68], ebx
0x180069eb0  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180069eb7  lea     rcx, [rsp+1B8h+var_88]; pExceptionObject
0x180069ebf  call    _CxxThrowException_0
0x180069ec5  mov     edi, r8d
0x180069ec8  mov     ecx, edx
0x180069eca  test    ecx, ecx
0x180069ecc  jz      short loc_180069EDB
0x180069ece  mov     rcx, r15; this
0x180069ed1  call    ?UnlockWriter@TaskScheduler@@QEAAXXZ; TaskScheduler::UnlockWriter(void)
0x180069ed6  sub     edi, 1
0x180069ed9  jnz     short loc_180069ECE
0x180069edb  xor     eax, eax
0x180069edd  jmp     short loc_180069EE6
0x180069edf  mov     eax, dword ptr [rsp+1B8h+arg_0]
0x180069ee6  lea     r11, [rsp+1B8h+var_28]
0x180069eee  mov     rbx, [r11+40h]
0x180069ef2  mov     rsi, [r11+48h]
0x180069ef6  mov     rsp, r11
0x180069ef9  pop     r15
0x180069efb  pop     r14
0x180069efd  pop     r13
0x180069eff  pop     r12
0x180069f01  pop     rdi
0x180069f02  retn
```
