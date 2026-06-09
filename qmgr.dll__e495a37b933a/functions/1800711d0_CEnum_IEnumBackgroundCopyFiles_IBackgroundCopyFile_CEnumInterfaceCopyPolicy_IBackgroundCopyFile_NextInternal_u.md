# CEnum<IEnumBackgroundCopyFiles,IBackgroundCopyFile *,CEnumInterfaceCopyPolicy<IBackgroundCopyFile>>::NextInternal(ulong,IBackgroundCopyFile * * const,ulong *)

- ea: `0x1800711d0`
- end: `0x18007147b`
- name: `?NextInternal@?$CEnum@UIEnumBackgroundCopyFiles@@PEAUIBackgroundCopyFile@@V?$CEnumInterfaceCopyPolicy@UIBackgroundCopyFile@@@@@@QEAAJKQEAPEAUIBackgroundCopyFile@@PEAK@Z`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800e2950`

## callees

- `0x1800711d0`
- `0x180097318`
- `0x180098fa4`
- `0x18009d024`
- `0x1800a3420`
- `0x1800a3de8`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071220`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071263`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071220`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071263`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007123c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007123c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007144b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007144b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180071256`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180071256`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall CEnum<IEnumBackgroundCopyFiles,IBackgroundCopyFile *,CEnumInterfaceCopyPolicy<IBackgroundCopyFile>>::NextInternal(
        __int64 a1,
        unsigned int a2,
        void *a3,
        _DWORD *a4)
{
  _DWORD *v4; // r13
  __int64 v6; // rdi
  _QWORD *v7; // r15
  __int64 v8; // r14
  int v9; // esi
  int v10; // r12d
  __int64 v11; // rbx
  __int64 v12; // rcx
  unsigned __int64 v13; // rdx
  __int64 v14; // rcx
  BOOL v15; // ebx
  void *v16; // r8
  __int64 v17; // rdx
  int v20; // [rsp+50h] [rbp-138h]
  __int64 v21; // [rsp+58h] [rbp-130h]
  int v22; // [rsp+60h] [rbp-128h]
  void **pExceptionObject; // [rsp+80h] [rbp-108h] BYREF
  __int128 v27; // [rsp+88h] [rbp-100h]
  int v28; // [rsp+98h] [rbp-F0h]
  int v29; // [rsp+9Ch] [rbp-ECh]
  int v30; // [rsp+A0h] [rbp-E8h]
  void **v31; // [rsp+E0h] [rbp-A8h] BYREF
  _DWORD v32[22]; // [rsp+E8h] [rbp-A0h] BYREF

  v4 = a4;
  v6 = a2;
  v7 = (_QWORD *)a1;
  v8 = a1 + 56;
  v21 = a1 + 56;
  if ( *(_DWORD *)(a1 + 112) == GetCurrentThreadId() )
  {
    v9 = 0;
    v22 = 0;
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)v8);
    ++*(_DWORD *)(v8 + 52);
    while ( *(_DWORD *)(v8 + 48) )
      WaitForSingleObject(*(HANDLE *)(v8 + 40), 0xFFFFFFFF);
    *(_DWORD *)(v8 + 56) = GetCurrentThreadId();
    v9 = 1;
    v22 = 1;
  }
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_qDqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_645d716d443e33997b5a63ffe9578c5c_Traceguids,
      v7,
      v6,
      a3,
      v4);
  v10 = 0;
  if ( (_DWORD)v6 )
    memset_0(a3, 0, 8 * v6);
  try
  {
    if ( !v4 && (_DWORD)v6 != 1 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_645d716d443e33997b5a63ffe9578c5c_Traceguids);
      v27 = 0;
      pExceptionObject = &ComError::`vftable';
      v28 = -2147024809;
      v29 = 0;
      v30 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v11 = 0;
    while ( (unsigned int)v11 < (unsigned int)v6 )
    {
      v12 = v7[15];
      v13 = v7[18];
      if ( v13 >= (v7[16] - v12) >> 3 )
        break;
      v14 = *(_QWORD *)(v12 + 8 * v13);
      *((_QWORD *)a3 + v11) = v14;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      ++v10;
      v11 = (unsigned int)(v11 + 1);
      ++v7[18];
    }
    if ( v4 )
      *v4 = v10;
    v15 = v10 != v6;
  }
  catch ( ComError v31 )
  {
    v20 = v32[4];
    v31 = &std::bad_alloc::`vftable';
    o___std_exception_destroy_0(v32);
    LODWORD(v6) = a2;
    v15 = v20;
    v9 = v22;
    v8 = v21;
    v7 = (_QWORD *)a1;
    v16 = a3;
    v4 = a4;
    goto LABEL_25;
  }
  v16 = a3;
LABEL_25:
  v17 = 1;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    if ( v4 )
      v17 = (unsigned int)*v4;
    WPP_SF_qDDqqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v16, v7, v15, v6, v16, v4, v17);
  }
  for ( ; v9; --v9 )
  {
    --*(_DWORD *)(v8 + 52);
    *(_DWORD *)(v8 + 56) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)v8);
  }
  return v15;
}

```

## disassembly

```asm
0x1800711d0  mov     [rsp+arg_8], edx
0x1800711d4  push    rbx
0x1800711d5  push    rsi
0x1800711d6  push    rdi
0x1800711d7  push    r12
0x1800711d9  push    r13
0x1800711db  push    r14
0x1800711dd  push    r15
0x1800711df  sub     rsp, 150h
0x1800711e6  mov     rax, cs:__security_cookie
0x1800711ed  xor     rax, rsp
0x1800711f0  mov     [rsp+188h+var_48], rax
0x1800711f8  mov     r13, r9
0x1800711fb  mov     rbx, r8
0x1800711fe  mov     [rsp+188h+var_138], rbx
0x180071203  mov     edi, edx
0x180071205  mov     r15, rcx
0x180071208  mov     [rsp+188h+var_120], rcx
0x18007120d  mov     [rsp+188h+var_118], rbx
0x180071212  mov     [rsp+188h+var_110], r9
0x180071217  lea     r14, [rcx+38h]
0x18007121b  mov     [rsp+188h+var_130], r14
0x180071220  call    cs:__imp_GetCurrentThreadId
0x180071226  cmp     [r14+38h], eax
0x18007122a  jnz     short loc_180071239
0x18007122c  xor     esi, esi
0x18007122e  mov     [rsp+188h+var_128], esi
0x180071232  mov     edx, 1
0x180071237  jmp     short loc_180071278
0x180071239  mov     rcx, r14; lpCriticalSection
0x18007123c  call    cs:__imp_EnterCriticalSection
0x180071242  inc     dword ptr [r14+34h]
0x180071246  cmp     dword ptr [r14+30h], 0
0x18007124b  jz      short loc_180071263
0x18007124d  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180071252  mov     rcx, [r14+28h]; hHandle
0x180071256  call    cs:__imp_WaitForSingleObject
0x18007125c  cmp     dword ptr [r14+30h], 0
0x180071261  jnz     short loc_18007124D
0x180071263  call    cs:__imp_GetCurrentThreadId
0x180071269  mov     [r14+38h], eax
0x18007126d  mov     edx, 1
0x180071272  mov     esi, edx
0x180071274  mov     [rsp+188h+var_128], edx
0x180071278  lea     rax, WPP_GLOBAL_Control
0x18007127f  mov     rcx, cs:WPP_GLOBAL_Control
0x180071286  cmp     rcx, rax
0x180071289  jz      short loc_1800712C3
0x18007128b  test    byte ptr [rcx+1Ch], 8
0x18007128f  jz      short loc_1800712C3
0x180071291  mov     edx, 0Bh
0x180071296  mov     [rsp+188h+var_158], r13
0x18007129b  mov     [rsp+188h+var_160], rbx
0x1800712a0  mov     [rsp+188h+var_168], edi
0x1800712a4  mov     r9, r15
0x1800712a7  lea     r8, WPP_645d716d443e33997b5a63ffe9578c5c_Traceguids
0x1800712ae  mov     rcx, [rcx+10h]
0x1800712b2  call    WPP_SF_qDqq
0x1800712b7  lea     rax, WPP_GLOBAL_Control
0x1800712be  mov     edx, 1
0x1800712c3  xor     r12d, r12d
0x1800712c6  test    edi, edi
0x1800712c8  jz      short loc_1800712E7
0x1800712ca  mov     r8, rdi
0x1800712cd  shl     r8, 3; Size
0x1800712d1  xor     edx, edx; Val
0x1800712d3  mov     rcx, rbx; void *
0x1800712d6  call    memset_0
0x1800712db  lea     rax, WPP_GLOBAL_Control
0x1800712e2  mov     edx, 1
0x1800712e7  test    r13, r13
0x1800712ea  jnz     short loc_180071368
0x1800712ec  cmp     edi, 1
0x1800712ef  jz      short loc_180071368
0x1800712f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800712f8  cmp     rcx, rax
0x1800712fb  jz      short loc_18007131D
0x1800712fd  test    byte ptr [rcx+1Ch], 2
0x180071301  jz      short loc_18007131D
0x180071303  mov     edx, 0Ch
0x180071308  lea     r8, WPP_645d716d443e33997b5a63ffe9578c5c_Traceguids
0x18007130f  mov     rcx, [rcx+10h]
0x180071313  call    WPP_SF_
0x180071318  mov     edx, 1
0x18007131d  xorps   xmm0, xmm0
0x180071320  movups  [rsp+188h+var_100], xmm0
0x180071328  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18007132f  mov     [rsp+188h+pExceptionObject], rax
0x180071337  mov     [rsp+188h+var_F0], 80070057h
0x180071342  mov     [rsp+188h+var_EC], 0
0x18007134d  mov     [rsp+188h+var_E8], edx
0x180071354  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18007135b  lea     rcx, [rsp+188h+pExceptionObject]; pExceptionObject
0x180071363  call    _CxxThrowException_0
0x180071368  xor     ebx, ebx
0x18007136a  cmp     ebx, edi
0x18007136c  jnb     short loc_1800713B3
0x18007136e  mov     rcx, [r15+78h]
0x180071372  mov     rdx, [r15+90h]
0x180071379  mov     rax, [r15+80h]
0x180071380  sub     rax, rcx
0x180071383  sar     rax, 3
0x180071387  cmp     rdx, rax
0x18007138a  jnb     short loc_1800713B3
0x18007138c  mov     rcx, [rcx+rdx*8]
0x180071390  mov     rdx, [rsp+188h+var_138]
0x180071395  mov     [rdx+rbx*8], rcx
0x180071399  mov     rax, [rcx]
0x18007139c  mov     rax, [rax+8]
0x1800713a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800713a5  inc     r12d
0x1800713a8  inc     ebx
0x1800713aa  inc     qword ptr [r15+90h]
0x1800713b1  jmp     short loc_18007136A
0x1800713b3  test    r13, r13
0x1800713b6  jz      short loc_1800713BC
0x1800713b8  mov     [r13+0], r12d
0x1800713bc  xor     ebx, ebx
0x1800713be  cmp     r12d, edi
0x1800713c1  setnz   bl
0x1800713c4  mov     r8, [rsp+188h+var_138]
0x1800713c9  jmp     short loc_1800713EE
0x1800713cb  mov     edi, [rsp+188h+arg_8]
0x1800713d2  mov     ebx, dword ptr [rsp+188h+var_138]
0x1800713d6  mov     esi, [rsp+188h+var_128]
0x1800713da  mov     r14, [rsp+188h+var_130]
0x1800713df  mov     r15, [rsp+188h+var_120]
0x1800713e4  mov     r8, [rsp+188h+var_118]
0x1800713e9  mov     r13, [rsp+188h+var_110]
0x1800713ee  lea     rax, WPP_GLOBAL_Control
0x1800713f5  mov     edx, 1
0x1800713fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180071401  cmp     rcx, rax
0x180071404  jz      short loc_180071438
0x180071406  test    byte ptr [rcx+1Ch], 8
0x18007140a  jz      short loc_180071438
0x18007140c  test    r13, r13
0x18007140f  jz      short loc_180071415
0x180071411  mov     edx, [r13+0]
0x180071415  mov     [rsp+188h+var_148], edx
0x180071419  mov     [rsp+188h+var_150], r13
0x18007141e  mov     [rsp+188h+var_158], r8
0x180071423  mov     dword ptr [rsp+188h+var_160], edi
0x180071427  mov     [rsp+188h+var_168], ebx
0x18007142b  mov     r9, r15
0x18007142e  mov     rcx, [rcx+10h]
0x180071432  call    WPP_SF_qDDqqD
0x180071437  nop
0x180071438  test    esi, esi
0x18007143a  jz      short loc_180071456
0x18007143c  dec     dword ptr [r14+34h]
0x180071440  mov     dword ptr [r14+38h], 0
0x180071448  mov     rcx, r14; lpCriticalSection
0x18007144b  call    cs:__imp_LeaveCriticalSection
0x180071451  sub     esi, 1
0x180071454  jnz     short loc_18007143C
0x180071456  mov     eax, ebx
0x180071458  mov     rcx, [rsp+188h+var_48]
0x180071460  xor     rcx, rsp; StackCookie
0x180071463  call    __security_check_cookie
0x180071468  add     rsp, 150h
0x18007146f  pop     r15
0x180071471  pop     r14
0x180071473  pop     r13
0x180071475  pop     r12
0x180071477  pop     rdi
0x180071478  pop     rsi
0x180071479  pop     rbx
0x18007147a  retn
```
