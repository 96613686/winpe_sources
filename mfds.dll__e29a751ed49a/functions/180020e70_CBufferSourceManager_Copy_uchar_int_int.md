# CBufferSourceManager::Copy_(uchar *,int,int *)

- ea: `0x180020e70`
- end: `0x1800212ac`
- name: `?Copy_@CBufferSourceManager@@MEAAHPEAEHPEAH@Z`
- size: `1084`
- prototype: `int(CBufferSourceManager *__hidden this, unsigned __int8 *, int, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800052c0`
- `0x180020e70`
- `0x180074a12`
- `0x18007c8e8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020ee3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020fac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021063`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020ee3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020fac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020eb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021101`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002113c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020eb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021101`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002113c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020ff6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800210ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020ff6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800210ad`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020ec8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020f92`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021049`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020ec8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020f92`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021049`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180021188`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002120e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002125d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180021188`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002120e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002125d`

## string_xrefs

- `0x180020f0c`: `CBufferSourceManager::Copy_`

## pseudocode

```c
__int64 __fastcall CBufferSourceManager::Copy_(void **this, unsigned __int8 *a2, int a3, int *a4)
{
  CallStackTracing *v4; // rbx
  size_t v6; // rbp
  char *v9; // rdi
  DWORD LastError; // r14d
  char *Value; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // eax
  GUID *v15; // rdi
  DWORD v16; // esi
  GUID *v17; // rax
  int v18; // eax
  int v19; // eax
  GUID *v21; // rdi
  DWORD v22; // esi
  GUID *v23; // rax
  int v24; // eax
  int v25; // eax
  CallStackTracing *v26; // rcx
  __int64 v27; // rax
  CallStackTracing *v28; // rcx
  __int64 v29; // rax
  CallStackTracing *v30; // rcx
  __int64 v31; // rax
  CallStackTracing *v32; // rax
  CallStackTracing *v33; // rax
  CallStackTracing *v34; // rax

  v4 = CallStackTracing::s_wpInstance;
  v6 = a3;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v4 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v4 + 8) )
  {
    v9 = (char *)v4 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v4 + 3));
    if ( Value )
    {
      v9 = Value;
    }
    else if ( !GetLastError() )
    {
      v26 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v32;
        if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        {
          v26 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v27 = (**(__int64 (__fastcall ***)(CallStackTracing *))v26)(v26);
      if ( v27 )
        v9 = (char *)v27;
    }
    SetLastError(LastError);
    v12 = *((unsigned int *)v9 + 497);
    v4 = CallStackTracing::s_wpInstance;
    if ( (unsigned int)v12 < *((_DWORD *)v9 + 498) )
    {
      v13 = 2 * v12;
      *(_QWORD *)&v9[8 * v13] = "CBufferSourceManager::Copy_";
      *(_DWORD *)&v9[8 * v13 + 8] = 264;
    }
    ++*((_DWORD *)v9 + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
  {
    WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 17), 15, &WPP_2790e164590a3ed111972434a23f3cea_Traceguids, this, a2, v6);
    v4 = CallStackTracing::s_wpInstance;
  }
  v14 = *((_DWORD *)this + 24) + *((_DWORD *)this + 84) - *((_DWORD *)this + 86);
  *a4 = v14;
  if ( (v6 & 0x80000000) != 0LL || (int)v6 > v14 )
  {
    if ( *((_BYTE *)v4 + 8) )
    {
      v21 = (GUID *)((char *)v4 + 208);
      v22 = GetLastError();
      v23 = (GUID *)TlsGetValue(*((_DWORD *)v4 + 3));
      if ( v23 )
      {
        v21 = v23;
      }
      else if ( !GetLastError() )
      {
        v30 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v30 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        v31 = (**(__int64 (__fastcall ***)(CallStackTracing *))v30)(v30);
        if ( v31 )
          v21 = (GUID *)v31;
      }
      SetLastError(v22);
      v24 = *(_DWORD *)&v21[124].Data2;
      if ( v24 )
      {
        v25 = v24 - 1;
        *(_DWORD *)&v21[124].Data2 = v25;
        if ( !v25 )
        {
          *(_DWORD *)&v21[124].Data2 = 0;
          *(_QWORD *)&v21[126].Data1 = 0;
          *(_DWORD *)&v21[124].Data4[4] = 0;
          v21[125] = GUID_00000000_0000_0000_0000_000000000000;
          *(_DWORD *)v21[126].Data4 = 0;
          v21[124].Data1 = GetCurrentThreadId();
        }
      }
    }
    return 0;
  }
  else
  {
    memcpy_0(this[43], a2, v6);
    *a4 -= v6;
    this[43] = (char *)this[43] + v6;
    if ( *((_BYTE *)v4 + 8) )
    {
      v15 = (GUID *)((char *)v4 + 208);
      v16 = GetLastError();
      v17 = (GUID *)TlsGetValue(*((_DWORD *)v4 + 3));
      if ( v17 )
      {
        v15 = v17;
      }
      else if ( !GetLastError() )
      {
        v28 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v28 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        v29 = (**(__int64 (__fastcall ***)(CallStackTracing *))v28)(v28);
        if ( v29 )
          v15 = (GUID *)v29;
      }
      SetLastError(v16);
      v18 = *(_DWORD *)&v15[124].Data2;
      if ( v18 )
      {
        v19 = v18 - 1;
        *(_DWORD *)&v15[124].Data2 = v19;
        if ( !v19 )
        {
          *(_DWORD *)&v15[124].Data2 = 0;
          *(_QWORD *)&v15[126].Data1 = 0;
          *(_DWORD *)&v15[124].Data4[4] = 0;
          v15[125] = GUID_00000000_0000_0000_0000_000000000000;
          *(_DWORD *)v15[126].Data4 = 0;
          v15[124].Data1 = GetCurrentThreadId();
        }
      }
    }
    return 1;
  }
}

```

## disassembly

```asm
0x180020e70  mov     [rsp+arg_10], rbx
0x180020e75  mov     [rsp+arg_18], rbp
0x180020e7a  push    rsi
0x180020e7b  push    r12
0x180020e7d  push    r15
0x180020e7f  sub     rsp, 30h
0x180020e83  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180020e8a  mov     r15, r9
0x180020e8d  movsxd  rbp, r8d
0x180020e90  mov     r12, rdx
0x180020e93  mov     rsi, rcx
0x180020e96  test    rbx, rbx
0x180020e99  jz      loc_180021177
0x180020e9f  cmp     byte ptr [rbx+8], 0
0x180020ea3  mov     [rsp+48h+arg_0], rdi
0x180020ea8  jz      short loc_180020F25
0x180020eaa  lea     rdi, [rbx+0D0h]
0x180020eb1  mov     [rsp+48h+arg_8], r14
0x180020eb6  call    cs:__imp_GetLastError
0x180020ebd  nop     dword ptr [rax+rax+00h]
0x180020ec2  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180020ec5  mov     r14d, eax
0x180020ec8  call    cs:__imp_TlsGetValue
0x180020ecf  nop     dword ptr [rax+rax+00h]
0x180020ed4  test    rax, rax
0x180020ed7  jz      loc_1800210C6
0x180020edd  mov     rdi, rax
0x180020ee0  mov     ecx, r14d; dwErrCode
0x180020ee3  call    cs:__imp_SetLastError
0x180020eea  nop     dword ptr [rax+rax+00h]
0x180020eef  mov     eax, [rdi+7C4h]
0x180020ef5  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180020efc  mov     r14, [rsp+48h+arg_8]
0x180020f01  cmp     eax, [rdi+7C8h]
0x180020f07  jnb     short loc_180020F1F
0x180020f09  add     rax, rax
0x180020f0c  lea     rcx, aCbuffersourcem_11; "CBufferSourceManager::Copy_"
0x180020f13  mov     [rdi+rax*8], rcx
0x180020f17  mov     dword ptr [rdi+rax*8+8], 108h
0x180020f1f  inc     dword ptr [rdi+7C4h]
0x180020f25  cmp     cs:byte_1800EACCB, 20h ; ' '
0x180020f2c  jnb     loc_1800211D7
0x180020f32  mov     eax, [rsi+150h]
0x180020f38  add     eax, [rsi+60h]
0x180020f3b  sub     eax, [rsi+158h]
0x180020f41  mov     [r15], eax
0x180020f44  test    ebp, ebp
0x180020f46  js      loc_180021027
0x180020f4c  cmp     ebp, eax
0x180020f4e  jg      loc_180021027
0x180020f54  mov     rcx, [rsi+158h]; void *
0x180020f5b  mov     r8, rbp; Size
0x180020f5e  mov     rdx, r12; Src
0x180020f61  call    memcpy_0
0x180020f66  sub     [r15], ebp
0x180020f69  add     [rsi+158h], rbp
0x180020f70  cmp     byte ptr [rbx+8], 0
0x180020f74  jz      loc_180021008
0x180020f7a  lea     rdi, [rbx+0D0h]
0x180020f81  call    cs:__imp_GetLastError
0x180020f88  nop     dword ptr [rax+rax+00h]
0x180020f8d  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180020f90  mov     esi, eax
0x180020f92  call    cs:__imp_TlsGetValue
0x180020f99  nop     dword ptr [rax+rax+00h]
0x180020f9e  test    rax, rax
0x180020fa1  jz      loc_180021101
0x180020fa7  mov     rdi, rax
0x180020faa  mov     ecx, esi; dwErrCode
0x180020fac  call    cs:__imp_SetLastError
0x180020fb3  nop     dword ptr [rax+rax+00h]
0x180020fb8  mov     eax, [rdi+7C4h]
0x180020fbe  test    eax, eax
0x180020fc0  jz      short loc_180021008
0x180020fc2  sub     eax, 1
0x180020fc5  mov     [rdi+7C4h], eax
0x180020fcb  jnz     short loc_180021008
0x180020fcd  xor     eax, eax
0x180020fcf  mov     [rdi+7C4h], eax
0x180020fd5  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180020fdc  mov     [rdi+7E0h], rax
0x180020fe3  mov     [rdi+7CCh], eax
0x180020fe9  movups  xmmword ptr [rdi+7D0h], xmm0
0x180020ff0  mov     [rdi+7E8h], eax
0x180020ff6  call    cs:__imp_GetCurrentThreadId
0x180020ffd  nop     dword ptr [rax+rax+00h]
0x180021002  mov     [rdi+7C0h], eax
0x180021008  mov     eax, 1
0x18002100d  mov     rdi, [rsp+48h+arg_0]
0x180021012  mov     rbx, [rsp+48h+arg_10]
0x180021017  mov     rbp, [rsp+48h+arg_18]
0x18002101c  add     rsp, 30h
0x180021020  pop     r15
0x180021022  pop     r12
0x180021024  pop     rsi
0x180021025  retn
0x180021027  cmp     byte ptr [rbx+8], 0
0x18002102b  jz      loc_1800210BF
0x180021031  lea     rdi, [rbx+0D0h]
0x180021038  call    cs:__imp_GetLastError
0x18002103f  nop     dword ptr [rax+rax+00h]
0x180021044  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180021047  mov     esi, eax
0x180021049  call    cs:__imp_TlsGetValue
0x180021050  nop     dword ptr [rax+rax+00h]
0x180021055  test    rax, rax
0x180021058  jz      loc_18002113C
0x18002105e  mov     rdi, rax
0x180021061  mov     ecx, esi; dwErrCode
0x180021063  call    cs:__imp_SetLastError
0x18002106a  nop     dword ptr [rax+rax+00h]
0x18002106f  mov     eax, [rdi+7C4h]
0x180021075  test    eax, eax
0x180021077  jz      short loc_1800210BF
0x180021079  sub     eax, 1
0x18002107c  mov     [rdi+7C4h], eax
0x180021082  jnz     short loc_1800210BF
0x180021084  xor     eax, eax
0x180021086  mov     [rdi+7C4h], eax
0x18002108c  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180021093  mov     [rdi+7E0h], rax
0x18002109a  mov     [rdi+7CCh], eax
0x1800210a0  movups  xmmword ptr [rdi+7D0h], xmm0
0x1800210a7  mov     [rdi+7E8h], eax
0x1800210ad  call    cs:__imp_GetCurrentThreadId
0x1800210b4  nop     dword ptr [rax+rax+00h]
0x1800210b9  mov     [rdi+7C0h], eax
0x1800210bf  xor     eax, eax
0x1800210c1  jmp     loc_18002100D
0x1800210c6  call    cs:__imp_GetLastError
0x1800210cd  nop     dword ptr [rax+rax+00h]
0x1800210d2  test    eax, eax
0x1800210d4  jnz     loc_180020EE0
0x1800210da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800210e1  test    rcx, rcx
0x1800210e4  jz      loc_180021188
0x1800210ea  mov     rax, [rcx]
0x1800210ed  mov     rax, [rax]
0x1800210f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210f5  test    rax, rax
0x1800210f8  cmovnz  rdi, rax
0x1800210fc  jmp     loc_180020EE0
0x180021101  call    cs:__imp_GetLastError
0x180021108  nop     dword ptr [rax+rax+00h]
0x18002110d  test    eax, eax
0x18002110f  jnz     loc_180020FAA
0x180021115  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002111c  test    rcx, rcx
0x18002111f  jz      loc_18002120E
0x180021125  mov     rax, [rcx]
0x180021128  mov     rax, [rax]
0x18002112b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021130  test    rax, rax
0x180021133  cmovnz  rdi, rax
0x180021137  jmp     loc_180020FAA
0x18002113c  call    cs:__imp_GetLastError
0x180021143  nop     dword ptr [rax+rax+00h]
0x180021148  test    eax, eax
0x18002114a  jnz     loc_180021061
0x180021150  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021157  test    rcx, rcx
0x18002115a  jz      loc_18002125D
0x180021160  mov     rax, [rcx]
0x180021163  mov     rax, [rax]
0x180021166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002116b  test    rax, rax
0x18002116e  cmovnz  rdi, rax
0x180021172  jmp     loc_180021061
0x180021177  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002117c  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021183  jmp     loc_180020E9F
0x180021188  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002118f  nop     dword ptr [rax+rax+00h]
0x180021194  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002119b  mov     rcx, rax
0x18002119e  test    rax, rax
0x1800211a1  jz      short loc_1800211C4
0x1800211a3  mov     rax, [rax]
0x1800211a6  mov     edx, 7F0h
0x1800211ab  mov     rax, [rax+8]
0x1800211af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211b4  test    eax, eax
0x1800211b6  jz      short loc_1800211C4
0x1800211b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800211bf  jmp     loc_1800210EA
0x1800211c4  lea     rcx, qword_1800EB130
0x1800211cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800211d2  jmp     loc_1800210EA
0x1800211d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211de  lea     r8, WPP_2790e164590a3ed111972434a23f3cea_Traceguids
0x1800211e5  mov     edx, 0Fh
0x1800211ea  mov     [rsp+48h+var_20], ebp
0x1800211ee  mov     r9, rsi
0x1800211f1  mov     [rsp+48h+var_28], r12
0x1800211f6  mov     rcx, [rcx+88h]
0x1800211fd  call    WPP_SF_qqD
0x180021202  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021209  jmp     loc_180020F32
0x18002120e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180021215  nop     dword ptr [rax+rax+00h]
0x18002121a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180021221  mov     rcx, rax
0x180021224  test    rax, rax
0x180021227  jz      short loc_18002124A
0x180021229  mov     rax, [rax]
0x18002122c  mov     edx, 7F0h
0x180021231  mov     rax, [rax+8]
0x180021235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002123a  test    eax, eax
0x18002123c  jz      short loc_18002124A
0x18002123e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021245  jmp     loc_180021125
0x18002124a  lea     rcx, qword_1800EB130
0x180021251  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180021258  jmp     loc_180021125
0x18002125d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180021264  nop     dword ptr [rax+rax+00h]
0x180021269  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180021270  mov     rcx, rax
0x180021273  test    rax, rax
0x180021276  jz      short loc_180021299
0x180021278  mov     rax, [rax]
0x18002127b  mov     edx, 7F0h
0x180021280  mov     rax, [rax+8]
0x180021284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021289  test    eax, eax
0x18002128b  jz      short loc_180021299
0x18002128d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021294  jmp     loc_180021160
0x180021299  lea     rcx, qword_1800EB130
0x1800212a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800212a7  jmp     loc_180021160
```
