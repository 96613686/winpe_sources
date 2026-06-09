# CBufferSourceManager::ResetForNext_(void)

- ea: `0x180009620`
- end: `0x1800098da`
- name: `?ResetForNext_@CBufferSourceManager@@AEAAXXZ`
- size: `698`
- prototype: `void __fastcall(CBufferSourceManager *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180005050`
- `0x180007230`
- `0x18000acb0`

## callees

- `0x180009620`
- `0x18002d514`
- `0x18007c8e8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000967f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000971b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000967f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000971b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000978b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000978b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009763`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009763`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009665`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009701`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009665`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009701`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000980e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000988b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000980e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000988b`

## pseudocode

```c
void __fastcall CBufferSourceManager::ResetForNext_(CBufferSourceManager *this)
{
  CallStackTracing *v1; // rbx
  char *v3; // rdi
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  GUID *v8; // rdi
  DWORD v9; // esi
  GUID *v10; // rax
  int v11; // eax
  int v12; // eax
  CallStackTracing *v13; // rcx
  __int64 v14; // rax
  CallStackTracing *v15; // rcx
  __int64 v16; // rax
  CallStackTracing *v17; // rax
  CallStackTracing *v18; // rax

  v1 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v1 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v1 + 8) )
  {
    v3 = (char *)v1 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v1 + 3));
    if ( Value )
    {
      v3 = Value;
    }
    else if ( !GetLastError() )
    {
      v13 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v13 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v14 = (**(__int64 (__fastcall ***)(CallStackTracing *))v13)(v13);
      if ( v14 )
        v3 = (char *)v14;
    }
    SetLastError(LastError);
    v6 = *((unsigned int *)v3 + 497);
    v1 = CallStackTracing::s_wpInstance;
    if ( (unsigned int)v6 < *((_DWORD *)v3 + 498) )
    {
      v7 = 2 * v6;
      *(_QWORD *)&v3[8 * v7] = "CBufferSourceManager::ResetForNext_";
      *(_DWORD *)&v3[8 * v7 + 8] = 146;
    }
    ++*((_DWORD *)v3 + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 10, &WPP_2790e164590a3ed111972434a23f3cea_Traceguids, this);
    v1 = CallStackTracing::s_wpInstance;
  }
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 7) = 0;
  *((_DWORD *)this + 84) = 0;
  if ( *((_BYTE *)v1 + 8) )
  {
    v8 = (GUID *)((char *)v1 + 208);
    v9 = GetLastError();
    v10 = (GUID *)TlsGetValue(*((_DWORD *)v1 + 3));
    if ( v10 )
    {
      v8 = v10;
    }
    else if ( !GetLastError() )
    {
      v15 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v15 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v16 = (**(__int64 (__fastcall ***)(CallStackTracing *))v15)(v15);
      if ( v16 )
        v8 = (GUID *)v16;
    }
    SetLastError(v9);
    v11 = *(_DWORD *)&v8[124].Data2;
    if ( v11 )
    {
      v12 = v11 - 1;
      *(_DWORD *)&v8[124].Data2 = v12;
      if ( !v12 )
      {
        *(_DWORD *)&v8[124].Data2 = 0;
        *(_QWORD *)&v8[126].Data1 = 0;
        *(_DWORD *)&v8[124].Data4[4] = 0;
        v8[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v8[126].Data4 = 0;
        v8[124].Data1 = GetCurrentThreadId();
      }
    }
  }
}

```

## disassembly

```asm
0x180009620  mov     [rsp+arg_8], rbx
0x180009625  mov     [rsp+arg_10], rbp
0x18000962a  push    rsi
0x18000962b  sub     rsp, 20h
0x18000962f  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009636  mov     rsi, rcx
0x180009639  test    rbx, rbx
0x18000963c  jz      loc_1800097FD
0x180009642  cmp     byte ptr [rbx+8], 0
0x180009646  mov     [rsp+28h+arg_0], rdi
0x18000964b  jz      short loc_1800096BC
0x18000964d  lea     rdi, [rbx+0D0h]
0x180009654  call    cs:__imp_GetLastError
0x18000965b  nop     dword ptr [rax+rax+00h]
0x180009660  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180009663  mov     ebp, eax
0x180009665  call    cs:__imp_TlsGetValue
0x18000966c  nop     dword ptr [rax+rax+00h]
0x180009671  test    rax, rax
0x180009674  jz      loc_18000978B
0x18000967a  mov     rdi, rax
0x18000967d  mov     ecx, ebp; dwErrCode
0x18000967f  call    cs:__imp_SetLastError
0x180009686  nop     dword ptr [rax+rax+00h]
0x18000968b  mov     eax, [rdi+7C4h]
0x180009691  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009698  cmp     eax, [rdi+7C8h]
0x18000969e  jnb     short loc_1800096B6
0x1800096a0  add     rax, rax
0x1800096a3  lea     rcx, aCbuffersourcem_0; "CBufferSourceManager::ResetForNext_"
0x1800096aa  mov     [rdi+rax*8], rcx
0x1800096ae  mov     dword ptr [rdi+rax*8+8], 92h
0x1800096b6  inc     dword ptr [rdi+7C4h]
0x1800096bc  cmp     cs:byte_1800EACCB, 20h ; ' '
0x1800096c3  jnb     loc_18000985D
0x1800096c9  xor     ebp, ebp
0x1800096cb  mov     [rsi+158h], rbp
0x1800096d2  mov     [rsi+60h], rbp
0x1800096d6  mov     [rsi+1Ch], ebp
0x1800096d9  mov     [rsi+150h], ebp
0x1800096df  cmp     [rbx+8], bpl
0x1800096e3  jz      loc_180009775
0x1800096e9  lea     rdi, [rbx+0D0h]
0x1800096f0  call    cs:__imp_GetLastError
0x1800096f7  nop     dword ptr [rax+rax+00h]
0x1800096fc  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x1800096ff  mov     esi, eax
0x180009701  call    cs:__imp_TlsGetValue
0x180009708  nop     dword ptr [rax+rax+00h]
0x18000970d  test    rax, rax
0x180009710  jz      loc_1800097C2
0x180009716  mov     rdi, rax
0x180009719  mov     ecx, esi; dwErrCode
0x18000971b  call    cs:__imp_SetLastError
0x180009722  nop     dword ptr [rax+rax+00h]
0x180009727  mov     eax, [rdi+7C4h]
0x18000972d  test    eax, eax
0x18000972f  jz      short loc_180009775
0x180009731  sub     eax, 1
0x180009734  mov     [rdi+7C4h], eax
0x18000973a  jnz     short loc_180009775
0x18000973c  mov     [rdi+7C4h], ebp
0x180009742  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180009749  mov     [rdi+7E0h], rbp
0x180009750  mov     [rdi+7CCh], ebp
0x180009756  movups  xmmword ptr [rdi+7D0h], xmm0
0x18000975d  mov     [rdi+7E8h], ebp
0x180009763  call    cs:__imp_GetCurrentThreadId
0x18000976a  nop     dword ptr [rax+rax+00h]
0x18000976f  mov     [rdi+7C0h], eax
0x180009775  mov     rdi, [rsp+28h+arg_0]
0x18000977a  mov     rbx, [rsp+28h+arg_8]
0x18000977f  mov     rbp, [rsp+28h+arg_10]
0x180009784  add     rsp, 20h
0x180009788  pop     rsi
0x180009789  retn
0x18000978b  call    cs:__imp_GetLastError
0x180009792  nop     dword ptr [rax+rax+00h]
0x180009797  test    eax, eax
0x180009799  jnz     loc_18000967D
0x18000979f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800097a6  test    rcx, rcx
0x1800097a9  jz      short loc_18000980E
0x1800097ab  mov     rax, [rcx]
0x1800097ae  mov     rax, [rax]
0x1800097b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097b6  test    rax, rax
0x1800097b9  cmovnz  rdi, rax
0x1800097bd  jmp     loc_18000967D
0x1800097c2  call    cs:__imp_GetLastError
0x1800097c9  nop     dword ptr [rax+rax+00h]
0x1800097ce  test    eax, eax
0x1800097d0  jnz     loc_180009719
0x1800097d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800097dd  test    rcx, rcx
0x1800097e0  jz      loc_18000988B
0x1800097e6  mov     rax, [rcx]
0x1800097e9  mov     rax, [rax]
0x1800097ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097f1  test    rax, rax
0x1800097f4  cmovnz  rdi, rax
0x1800097f8  jmp     loc_180009719
0x1800097fd  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180009802  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009809  jmp     loc_180009642
0x18000980e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180009815  nop     dword ptr [rax+rax+00h]
0x18000981a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180009821  mov     rcx, rax
0x180009824  test    rax, rax
0x180009827  jz      short loc_18000984A
0x180009829  mov     rax, [rax]
0x18000982c  mov     edx, 7F0h
0x180009831  mov     rax, [rax+8]
0x180009835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000983a  test    eax, eax
0x18000983c  jz      short loc_18000984A
0x18000983e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009845  jmp     loc_1800097AB
0x18000984a  lea     rcx, qword_1800EB130
0x180009851  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180009858  jmp     loc_1800097AB
0x18000985d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009864  lea     r8, WPP_2790e164590a3ed111972434a23f3cea_Traceguids
0x18000986b  mov     edx, 0Ah
0x180009870  mov     r9, rsi
0x180009873  mov     rcx, [rcx+88h]
0x18000987a  call    WPP_SF_q
0x18000987f  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009886  jmp     loc_1800096C9
0x18000988b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180009892  nop     dword ptr [rax+rax+00h]
0x180009897  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000989e  mov     rcx, rax
0x1800098a1  test    rax, rax
0x1800098a4  jz      short loc_1800098C7
0x1800098a6  mov     rax, [rax]
0x1800098a9  mov     edx, 7F0h
0x1800098ae  mov     rax, [rax+8]
0x1800098b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098b7  test    eax, eax
0x1800098b9  jz      short loc_1800098C7
0x1800098bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800098c2  jmp     loc_1800097E6
0x1800098c7  lea     rcx, qword_1800EB130
0x1800098ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800098d5  jmp     loc_1800097E6
```
