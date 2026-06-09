# MkvReader::EnableBuffering(__int64)

- ea: `0x1800437cc`
- end: `0x180043a9d`
- name: `?EnableBuffering@MkvReader@@QEBAJ_J@Z`
- size: `721`
- prototype: `__int64 __fastcall(MkvReader *__hidden this, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001ede0`
- `0x18001f300`

## callees

- `0x180002e14`
- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180041698`
- `0x1800437cc`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043925`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800439f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043925`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800439f5`

## string_xrefs

- `0x1800438ea`: `MkvReader::EnableBuffering`
- `0x180043982`: `MkvReader::EnableBuffering`
- `0x180043a52`: `MkvReader::EnableBuffering`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvReader::EnableBuffering(MkvReader *this, __int64 a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rcx
  double v8; // xmm1_8
  __int64 v9; // rcx
  double v10; // xmm0_8
  __int64 v11; // rdx
  int v12; // edi
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _QWORD v26[2]; // [rsp+30h] [rbp-40h] BYREF
  int *v27; // [rsp+40h] [rbp-30h]
  int v28; // [rsp+48h] [rbp-28h]
  __int64 v29; // [rsp+50h] [rbp-20h]
  __int64 v30; // [rsp+58h] [rbp-18h]
  __int64 v31; // [rsp+60h] [rbp-10h]
  int v32; // [rsp+68h] [rbp-8h]
  char v33; // [rsp+90h] [rbp+20h] BYREF
  __int64 v34; // [rsp+A0h] [rbp+30h] BYREF
  int v35; // [rsp+A8h] [rbp+38h] BYREF
  int v36; // [rsp+ACh] [rbp+3Ch]

  v34 = 0;
  Microsoft::WRL::ComPtr<IMFByteStream>::As<IMFByteStreamBuffering>((char *)this + 16, &v34);
  if ( v34 )
  {
    memset_0(v26, 0, 0x40u);
    v5 = v31;
    if ( a2 >= 0 )
      v5 = a2;
    v31 = v5;
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 2) + 32LL))(*((_QWORD *)this + 2), v26);
    v7 = v26[0];
    if ( v6 < 0 )
      v7 = -1;
    v26[0] = v7;
    v26[1] = v7;
    if ( v7 && a2 > 0 )
    {
      v8 = (double)(int)a2 / 10000000.0;
      if ( v8 > 0.0 )
      {
        v9 = 8 * v7;
        if ( v9 < 0 )
          v10 = (double)(int)(v9 & 1 | ((unsigned __int64)v9 >> 1))
              + (double)(int)(v9 & 1 | ((unsigned __int64)v9 >> 1));
        else
          v10 = (double)(int)v9;
        v35 = (int)(v10 / v8);
        v36 = 10000;
        v27 = &v35;
        v28 = 1;
      }
    }
    else
    {
      v27 = 0;
      v28 = 0;
    }
    v29 = 0;
    v30 = 0;
    v32 = 1065353216;
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v33, "MkvReader::EnableBuffering", 189);
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v34 + 24LL))(v34, v26);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 32LL))(v34, 1);
      if ( v12 >= 0 )
      {
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v33);
        v4 = 0;
        goto LABEL_40;
      }
      v22 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
        CallStackTracing::s_wpInstance = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v12 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "MkvReader::EnableBuffering", 190, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_27;
      v18 = 17;
    }
    else
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v13, v14);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != v12 )
          CallStackContext::TraceFailure(v17, "MkvReader::EnableBuffering", 189, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_27;
      v18 = 16;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids, this, v12);
LABEL_27:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v33);
    v4 = v12;
    goto LABEL_40;
  }
  v4 = 1;
LABEL_40:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  return v4;
}

```

## disassembly

```asm
0x1800437cc  mov     [rsp-18h+arg_8], rbx
0x1800437d1  push    rbp
0x1800437d2  push    rsi
0x1800437d3  push    rdi
0x1800437d4  mov     rbp, rsp
0x1800437d7  sub     rsp, 70h
0x1800437db  mov     rdi, rdx
0x1800437de  mov     rsi, rcx
0x1800437e1  mov     [rbp+arg_10], 0
0x1800437e9  lea     rdx, [rbp+arg_10]
0x1800437ed  add     rcx, 10h
0x1800437f1  call    ??$As@UIMFByteStreamBuffering@@@?$ComPtr@UIMFByteStream@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMFByteStreamBuffering@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IMFByteStream>::As<IMFByteStreamBuffering>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IMFByteStreamBuffering>>)
0x1800437f6  cmp     [rbp+arg_10], 0
0x1800437fb  jnz     short loc_180043807
0x1800437fd  mov     ebx, 1
0x180043802  jmp     loc_180043A82
0x180043807  xor     edx, edx; Val
0x180043809  lea     r8d, [rdx+40h]; Size
0x18004380d  lea     rcx, [rbp+var_40]; void *
0x180043811  call    memset_0
0x180043816  mov     rax, [rbp+var_10]
0x18004381a  test    rdi, rdi
0x18004381d  cmovns  rax, rdi
0x180043821  mov     [rbp+var_10], rax
0x180043825  mov     rcx, [rsi+10h]
0x180043829  mov     rax, [rcx]
0x18004382c  lea     rdx, [rbp+var_40]
0x180043830  mov     rax, [rax+20h]
0x180043834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043839  mov     rcx, [rbp+var_40]
0x18004383d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180043841  test    eax, eax
0x180043843  cmovs   rcx, rdx
0x180043847  mov     [rbp+var_40], rcx
0x18004384b  mov     [rbp+var_38], rcx
0x18004384f  lea     ebx, [rdx+2]
0x180043852  test    rcx, rcx
0x180043855  jz      short loc_1800438BE
0x180043857  test    rdi, rdi
0x18004385a  jle     short loc_1800438BE
0x18004385c  xorps   xmm1, xmm1
0x18004385f  cvtsi2sd xmm1, rdi
0x180043864  divsd   xmm1, cs:__real@416312d000000000
0x18004386c  comisd  xmm1, cs:__real@0000000000000000
0x180043874  jbe     short loc_1800438CD
0x180043876  shl     rcx, 3
0x18004387a  xorps   xmm0, xmm0
0x18004387d  test    rcx, rcx
0x180043880  js      short loc_180043889
0x180043882  cvtsi2sd xmm0, rcx
0x180043887  jmp     short loc_18004389E
0x180043889  mov     rax, rcx
0x18004388c  shr     rax, 1
0x18004388f  and     rcx, rbx
0x180043892  or      rax, rcx
0x180043895  cvtsi2sd xmm0, rax
0x18004389a  addsd   xmm0, xmm0
0x18004389e  divsd   xmm0, xmm1
0x1800438a2  cvttsd2si rax, xmm0
0x1800438a7  mov     [rbp+arg_18], eax
0x1800438aa  mov     [rbp+arg_1C], 2710h
0x1800438b1  lea     rax, [rbp+arg_18]
0x1800438b5  mov     [rbp+var_30], rax
0x1800438b9  mov     [rbp+var_28], ebx
0x1800438bc  jmp     short loc_1800438CD
0x1800438be  mov     [rbp+var_30], 0
0x1800438c6  mov     [rbp+var_28], 0
0x1800438cd  mov     [rbp+var_20], 0
0x1800438d5  mov     [rbp+var_18], 0
0x1800438dd  mov     [rbp+var_8], 3F800000h
0x1800438e4  mov     r8d, 0BDh; int
0x1800438ea  lea     rdx, aMkvreaderEnabl; "MkvReader::EnableBuffering"
0x1800438f1  lea     rcx, [rbp+arg_0]; this
0x1800438f5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800438fa  nop
0x1800438fb  mov     rcx, [rbp+arg_10]
0x1800438ff  mov     rax, [rcx]
0x180043902  lea     rdx, [rbp+var_40]
0x180043906  mov     rax, [rax+18h]
0x18004390a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004390f  mov     edi, eax
0x180043911  test    eax, eax
0x180043913  jns     loc_1800439CD
0x180043919  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043920  test    rcx, rcx
0x180043923  jnz     short loc_180043966
0x180043925  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004392b  mov     rcx, rax
0x18004392e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043935  test    rax, rax
0x180043938  jz      short loc_180043958
0x18004393a  mov     rax, [rax]
0x18004393d  mov     edx, 7F0h
0x180043942  mov     rax, [rax+8]
0x180043946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004394b  test    eax, eax
0x18004394d  jz      short loc_180043958
0x18004394f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043956  jmp     short loc_180043966
0x180043958  lea     rcx, qword_1800D6F70; this
0x18004395f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180043966  cmp     byte ptr [rcx+8], 0
0x18004396a  jz      short loc_180043991
0x18004396c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043971  cmp     [rax+7CCh], edi
0x180043977  jz      short loc_180043991
0x180043979  mov     r9d, edi; int
0x18004397c  mov     r8d, 0BDh; int
0x180043982  lea     rdx, aMkvreaderEnabl; "MkvReader::EnableBuffering"
0x180043989  mov     rcx, rax; this
0x18004398c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043991  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180043997  jb      short loc_1800439BD
0x180043999  mov     edx, 10h
0x18004399e  mov     [rsp+70h+var_50], edi
0x1800439a2  mov     r9, rsi
0x1800439a5  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x1800439ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800439b3  mov     rcx, [rcx+10h]
0x1800439b7  call    WPP_SF_qD
0x1800439bc  nop
0x1800439bd  lea     rcx, [rbp+arg_0]; this
0x1800439c1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800439c6  mov     ebx, edi
0x1800439c8  jmp     loc_180043A82
0x1800439cd  mov     rcx, [rbp+arg_10]
0x1800439d1  mov     rax, [rcx]
0x1800439d4  mov     edx, ebx
0x1800439d6  mov     rax, [rax+20h]
0x1800439da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800439df  mov     edi, eax
0x1800439e1  test    eax, eax
0x1800439e3  jns     loc_180043A77
0x1800439e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800439f0  test    rcx, rcx
0x1800439f3  jnz     short loc_180043A36
0x1800439f5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800439fb  mov     rcx, rax
0x1800439fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043a05  test    rax, rax
0x180043a08  jz      short loc_180043A28
0x180043a0a  mov     rax, [rax]
0x180043a0d  mov     edx, 7F0h
0x180043a12  mov     rax, [rax+8]
0x180043a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a1b  test    eax, eax
0x180043a1d  jz      short loc_180043A28
0x180043a1f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043a26  jmp     short loc_180043A36
0x180043a28  lea     rcx, qword_1800D6F70; this
0x180043a2f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180043a36  cmp     byte ptr [rcx+8], 0
0x180043a3a  jz      short loc_180043A61
0x180043a3c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043a41  cmp     [rax+7CCh], edi
0x180043a47  jz      short loc_180043A61
0x180043a49  mov     r9d, edi; int
0x180043a4c  mov     r8d, 0BEh; int
0x180043a52  lea     rdx, aMkvreaderEnabl; "MkvReader::EnableBuffering"
0x180043a59  mov     rcx, rax; this
0x180043a5c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180043a61  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180043a67  jb      loc_1800439BD
0x180043a6d  mov     edx, 11h
0x180043a72  jmp     loc_18004399E
0x180043a77  lea     rcx, [rbp+arg_0]; this
0x180043a7b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180043a80  xor     ebx, ebx
0x180043a82  lea     rcx, [rbp+arg_10]
0x180043a86  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043a8b  mov     eax, ebx
0x180043a8d  mov     rbx, [rsp+70h+arg_8]
0x180043a95  add     rsp, 70h
0x180043a99  pop     rdi
0x180043a9a  pop     rsi
0x180043a9b  pop     rbp
0x180043a9c  retn
```
