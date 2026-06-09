# CHttpWriter::WinhttpCallback(ulong,void *,ulong)

- ea: `0x1800789d0`
- end: `0x180078d94`
- name: `?WinhttpCallback@CHttpWriter@@UEAAXKPEAXK@Z`
- size: `964`
- prototype: `void __fastcall(CHttpWriter *__hidden this, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x180033420`
- `0x180033480`
- `0x180034170`
- `0x180055f50`
- `0x1800789d0`
- `0x180078d9c`
- `0x180080410`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a7558`
- `0x1800ab7fc`
- `0x1800bd5c8`
- `0x1800beaec`
- `0x1800bedb0`
- `0x1800bef38`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180078b17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180078cdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180078b17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180078cdf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180078b25`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180078ced`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180078b25`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180078ced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078d10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078d10`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180078b0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180078b65`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180078b0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180078b65`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall CHttpWriter::WinhttpCallback(CHttpWriter *this, int a2, unsigned int *a3, unsigned int a4)
{
  EVENT_LOG *v7; // rcx
  char *v8; // r14
  char v9; // bl
  int TickCount64; // r13d
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v13; // rdx
  EVENT_LOG *v14; // rcx
  int v15; // eax
  void (__fastcall *v16)(char *); // rax
  int v17; // eax
  unsigned int *v18; // rdx
  unsigned int v19; // eax
  unsigned int v20; // edx
  HANDLE v21; // rax
  DWORD v22; // eax
  char v23[8]; // [rsp+30h] [rbp-A8h] BYREF
  CCritSec2 *v24; // [rsp+38h] [rbp-A0h]

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      225,
      &WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids,
      (char *)this - 304,
      a2);
    v7 = WPP_GLOBAL_Control;
  }
  if ( a2 == 2048 )
  {
    if ( v7 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x800) != 0 )
      WPP_SF_q(*((_QWORD *)v7 + 2), 226, &WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids, (char *)this - 304);
    CEvent::Set((CHttpWriter *)((char *)this + 432));
    return;
  }
  v24 = (CHttpWriter *)((char *)this - 296);
  CCritSec2::enter((CHttpWriter *)((char *)this - 296));
  v23[0] = 1;
  if ( a2 == 0x10000 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 227, &WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids, *a3);
    *((_DWORD *)this + 159) = MapSecureHttpErrorCode(*a3);
LABEL_57:
    HoldCritSec::~HoldCritSec((HoldCritSec *)v23);
    return;
  }
  v8 = (char *)this - 304;
  if ( !*((_QWORD *)this + 51) || *((_BYTE *)this + 640) )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 228, &WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids);
    goto LABEL_57;
  }
  v9 = 0;
  if ( *((_BYTE *)this - 184) )
  {
    TickCount64 = GetTickCount64();
    CurrentThread = GetCurrentThread();
    if ( SetThreadPriority(CurrentThread, 0x10000) )
    {
      v9 = 1;
      v15 = GetTickCount64();
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = v15 - TickCount64;
        v13 = 51;
        goto LABEL_24;
      }
    }
    else if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      v13 = 50;
      v14 = WPP_GLOBAL_Control;
LABEL_24:
      WPP_SF_d(*((_QWORD *)v14 + 2), v13, &WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids, LastError);
    }
  }
  switch ( a2 )
  {
    case 0x10:
      (*(void (__fastcall **)(char *, char *))(*((_QWORD *)this + 27) + 8LL))((char *)this + 216, v23);
      break;
    case 0x4000:
      CHttpWriter::OnRedirect((CHttpWriter *)((char *)this - 304), (const unsigned __int16 *)a3);
      break;
    case 0x20000:
      v16 = *(void (__fastcall **)(char *))(*(_QWORD *)v8 + 520LL);
LABEL_34:
      v16((char *)this - 304);
      break;
    case 0x40000:
      CHttpWriter::OnDataAvailable((CHttpWriter *)((char *)this - 304), *a3);
      break;
    case 0x80000:
      (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v8 + 528LL))((char *)this - 304, a4);
      break;
    case 0x100000:
      v19 = *a3;
      *((_DWORD *)v8 + 31) += *a3;
      CAbstractFile::_OnWriteCompleted((CHttpWriter *)((char *)this - 304), v19);
      (*(void (__fastcall **)(char *, _QWORD, _QWORD, __int64))(*((_QWORD *)v8 + 65) + 56LL))(v8 + 520, 0, v20, 5);
      break;
    case 0x200000:
      v17 = a3[2];
      if ( v17 == 12017 )
      {
        v17 = 12002;
      }
      else if ( v17 == 12175 )
      {
        v18 = (unsigned int *)((char *)this + 636);
        goto LABEL_40;
      }
      v18 = (unsigned int *)((char *)this + 636);
      *((_DWORD *)this + 159) = v17;
LABEL_40:
      CHttpWriter::DealWithSendError((CHttpWriter *)((char *)this - 304), *v18);
      break;
    case 0x400000:
      v16 = *(void (__fastcall **)(char *))(*(_QWORD *)v8 + 504LL);
      goto LABEL_34;
    default:
      break;
  }
  CHttpWriter::StatePump((CHttpWriter *)((char *)this - 304));
  if ( v9 )
  {
    v21 = GetCurrentThread();
    if ( !SetThreadPriority(v21, 0x20000)
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v22 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids, v22);
    }
  }
  if ( v23[0] )
    CCritSec2::leave(v24);
}

```

## disassembly

```asm
0x1800789d0  mov     [rsp+arg_10], rbx
0x1800789d5  mov     [rsp+arg_18], r9d
0x1800789da  mov     [rsp+arg_0], rcx
0x1800789df  push    rsi
0x1800789e0  push    rdi
0x1800789e1  push    r12
0x1800789e3  push    r13
0x1800789e5  push    r14
0x1800789e7  sub     rsp, 0B0h
0x1800789ee  mov     r12, r8
0x1800789f1  mov     esi, edx
0x1800789f3  mov     rdi, rcx
0x1800789f6  lea     r13, WPP_GLOBAL_Control
0x1800789fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180078a04  mov     ebx, 800h
0x180078a09  cmp     rcx, r13
0x180078a0c  jz      short loc_180078A3A
0x180078a0e  test    [rcx+1Ch], ebx
0x180078a11  jz      short loc_180078A3A
0x180078a13  lea     r9, [rdi-130h]
0x180078a1a  mov     edx, 0E1h
0x180078a1f  mov     [rsp+0D8h+var_B8], esi
0x180078a23  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x180078a2a  mov     rcx, [rcx+10h]
0x180078a2e  call    WPP_SF_qD
0x180078a33  mov     rcx, cs:WPP_GLOBAL_Control
0x180078a3a  cmp     esi, ebx
0x180078a3c  jnz     short loc_180078A75
0x180078a3e  cmp     rcx, r13
0x180078a41  jz      short loc_180078A64
0x180078a43  test    [rcx+1Ch], ebx
0x180078a46  jz      short loc_180078A64
0x180078a48  lea     r9, [rdi-130h]
0x180078a4f  mov     edx, 0E2h
0x180078a54  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x180078a5b  mov     rcx, [rcx+10h]
0x180078a5f  call    WPP_SF_q
0x180078a64  lea     rcx, [rdi+1B0h]; this
0x180078a6b  call    ?Set@CEvent@@QEAAXXZ; CEvent::Set(void)
0x180078a70  jmp     loc_180078D7C
0x180078a75  mov     [rsp+0D8h+var_A8], 0
0x180078a7a  lea     rcx, [rdi-128h]; this
0x180078a81  mov     [rsp+0D8h+var_A0], rcx
0x180078a86  call    ?enter@CCritSec2@@QEAAXXZ; CCritSec2::enter(void)
0x180078a8b  mov     [rsp+0D8h+var_A8], 1
0x180078a90  cmp     esi, 10000h
0x180078a96  jnz     short loc_180078AD7
0x180078a98  mov     rcx, cs:WPP_GLOBAL_Control
0x180078a9f  cmp     rcx, r13
0x180078aa2  jz      short loc_180078AC3
0x180078aa4  test    byte ptr [rcx+1Ch], 2
0x180078aa8  jz      short loc_180078AC3
0x180078aaa  mov     edx, 0E3h
0x180078aaf  mov     r9d, [r12]
0x180078ab3  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x180078aba  mov     rcx, [rcx+10h]
0x180078abe  call    WPP_SF_d
0x180078ac3  mov     ecx, [r12]; unsigned int
0x180078ac7  call    ?MapSecureHttpErrorCode@@YAKK@Z; MapSecureHttpErrorCode(ulong)
0x180078acc  mov     [rdi+27Ch], eax
0x180078ad2  jmp     loc_180078D72
0x180078ad7  lea     r14, [rdi-130h]
0x180078ade  cmp     qword ptr [r14+2C8h], 0
0x180078ae6  jz      loc_180078D4B
0x180078aec  cmp     byte ptr [rdi+280h], 0
0x180078af3  jnz     loc_180078D4B
0x180078af9  xor     bl, bl
0x180078afb  mov     [rsp+0D8h+arg_8], bl
0x180078b02  cmp     [rdi-0B8h], bl
0x180078b08  jz      loc_180078B9F
0x180078b0e  call    cs:__imp_GetTickCount64
0x180078b14  mov     r13, rax
0x180078b17  call    cs:__imp_GetCurrentThread
0x180078b1d  mov     rcx, rax; hThread
0x180078b20  mov     edx, 10000h; nPriority
0x180078b25  call    cs:__imp_SetThreadPriority
0x180078b2b  test    eax, eax
0x180078b2d  jnz     short loc_180078B5C
0x180078b2f  mov     rax, cs:WPP_GLOBAL_Control
0x180078b36  lea     rdx, WPP_GLOBAL_Control
0x180078b3d  cmp     rax, rdx
0x180078b40  jz      short loc_180078B9F
0x180078b42  test    byte ptr [rax+1Ch], 2
0x180078b46  jz      short loc_180078B9F
0x180078b48  call    cs:__imp_GetLastError
0x180078b4e  mov     edx, 32h ; '2'
0x180078b53  mov     rcx, cs:WPP_GLOBAL_Control
0x180078b5a  jmp     short loc_180078B8B
0x180078b5c  mov     bl, 1
0x180078b5e  mov     [rsp+0D8h+arg_8], bl
0x180078b65  call    cs:__imp_GetTickCount64
0x180078b6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180078b72  lea     rdx, WPP_GLOBAL_Control
0x180078b79  cmp     rcx, rdx
0x180078b7c  jz      short loc_180078B9F
0x180078b7e  test    [rcx+1Ch], bl
0x180078b81  jz      short loc_180078B9F
0x180078b83  sub     eax, r13d
0x180078b86  mov     edx, 33h ; '3'
0x180078b8b  mov     r9d, eax
0x180078b8e  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x180078b95  mov     rcx, [rcx+10h]
0x180078b99  call    WPP_SF_d
0x180078b9e  nop
0x180078b9f  cmp     esi, 10h
0x180078ba2  jz      loc_180078CBA
0x180078ba8  cmp     esi, 4000h
0x180078bae  jz      loc_180078CAD
0x180078bb4  cmp     esi, 20000h
0x180078bba  jz      loc_180078C9E
0x180078bc0  cmp     esi, 40000h
0x180078bc6  jz      loc_180078C90
0x180078bcc  cmp     esi, 80000h
0x180078bd2  jz      loc_180078C75
0x180078bd8  cmp     esi, 100000h
0x180078bde  jz      short loc_180078C43
0x180078be0  cmp     esi, 200000h
0x180078be6  jz      short loc_180078C08
0x180078be8  cmp     esi, 400000h
0x180078bee  jnz     loc_180078CD2
0x180078bf4  mov     rax, [r14]
0x180078bf7  mov     rax, [rax+1F8h]
0x180078bfe  mov     rcx, r14
0x180078c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078c06  jmp     short loc_180078C3E
0x180078c08  mov     eax, [r12+8]
0x180078c0d  cmp     eax, 2EF1h
0x180078c12  jnz     short loc_180078C1B
0x180078c14  mov     eax, 2EE2h
0x180078c19  jmp     short loc_180078C22
0x180078c1b  cmp     eax, 2F8Fh
0x180078c20  jz      short loc_180078C2D
0x180078c22  lea     rdx, [rdi+27Ch]
0x180078c29  mov     [rdx], eax
0x180078c2b  jmp     short loc_180078C34
0x180078c2d  lea     rdx, [rdi+27Ch]
0x180078c34  mov     edx, [rdx]; unsigned int
0x180078c36  mov     rcx, r14; this
0x180078c39  call    ?DealWithSendError@CHttpWriter@@AEAAXK@Z; CHttpWriter::DealWithSendError(ulong)
0x180078c3e  jmp     loc_180078CD2
0x180078c43  mov     eax, [r12]
0x180078c47  add     [r14+7Ch], eax
0x180078c4b  mov     edx, eax; unsigned __int64
0x180078c4d  mov     rcx, r14; this
0x180078c50  call    ?_OnWriteCompleted@CAbstractFile@@IEAAX_K@Z; CAbstractFile::_OnWriteCompleted(unsigned __int64)
0x180078c55  lea     rcx, [r14+208h]
0x180078c5c  mov     rax, [rcx]
0x180078c5f  mov     r9d, 5
0x180078c65  mov     r8d, edx
0x180078c68  xor     edx, edx
0x180078c6a  mov     rax, [rax+38h]
0x180078c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078c73  jmp     short loc_180078C3E
0x180078c75  mov     rax, [r14]
0x180078c78  mov     edx, [rsp+0D8h+arg_18]
0x180078c7f  mov     rcx, r14
0x180078c82  mov     rax, [rax+210h]
0x180078c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078c8e  jmp     short loc_180078C3E
0x180078c90  mov     edx, [r12]; unsigned int
0x180078c94  mov     rcx, r14; this
0x180078c97  call    ?OnDataAvailable@CHttpWriter@@AEAAXK@Z; CHttpWriter::OnDataAvailable(ulong)
0x180078c9c  jmp     short loc_180078C3E
0x180078c9e  mov     rax, [r14]
0x180078ca1  mov     rax, [rax+208h]
0x180078ca8  jmp     loc_180078BFE
0x180078cad  mov     rdx, r12; unsigned __int16 *
0x180078cb0  mov     rcx, r14; this
0x180078cb3  call    ?OnRedirect@CHttpWriter@@AEAAXPEBG@Z; CHttpWriter::OnRedirect(ushort const *)
0x180078cb8  jmp     short loc_180078C3E
0x180078cba  lea     rcx, [rdi+0D8h]
0x180078cc1  mov     rax, [rcx]
0x180078cc4  lea     rdx, [rsp+0D8h+var_A8]
0x180078cc9  mov     rax, [rax+8]
0x180078ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078cd2  mov     rcx, r14; this
0x180078cd5  call    ?StatePump@CHttpWriter@@AEAAXXZ; CHttpWriter::StatePump(void)
0x180078cda  nop
0x180078cdb  test    bl, bl
0x180078cdd  jz      short loc_180078D36
0x180078cdf  call    cs:__imp_GetCurrentThread
0x180078ce5  mov     rcx, rax; hThread
0x180078ce8  mov     edx, 20000h; nPriority
0x180078ced  call    cs:__imp_SetThreadPriority
0x180078cf3  test    eax, eax
0x180078cf5  jnz     short loc_180078D36
0x180078cf7  mov     rax, cs:WPP_GLOBAL_Control
0x180078cfe  lea     rcx, WPP_GLOBAL_Control
0x180078d05  cmp     rax, rcx
0x180078d08  jz      short loc_180078D36
0x180078d0a  test    byte ptr [rax+1Ch], 2
0x180078d0e  jz      short loc_180078D36
0x180078d10  call    cs:__imp_GetLastError
0x180078d16  mov     edx, 34h ; '4'
0x180078d1b  mov     r9d, eax
0x180078d1e  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x180078d25  mov     rcx, cs:WPP_GLOBAL_Control
0x180078d2c  mov     rcx, [rcx+10h]
0x180078d30  call    WPP_SF_d
0x180078d35  nop
0x180078d36  jmp     short $+2
0x180078d38  cmp     [rsp+0D8h+var_A8], 0
0x180078d3d  jz      short loc_180078D7C
0x180078d3f  mov     rcx, [rsp+0D8h+var_A0]; this
0x180078d44  call    ?leave@CCritSec2@@QEAAXXZ; CCritSec2::leave(void)
0x180078d49  jmp     short loc_180078D7C
0x180078d4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180078d52  cmp     rcx, r13
0x180078d55  jz      short loc_180078D72
0x180078d57  test    [rcx+1Ch], ebx
0x180078d5a  jz      short loc_180078D72
0x180078d5c  mov     edx, 0E4h
0x180078d61  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x180078d68  mov     rcx, [rcx+10h]
0x180078d6c  call    WPP_SF_
0x180078d71  nop
0x180078d72  lea     rcx, [rsp+0D8h+var_A8]; this
0x180078d77  call    ??1HoldCritSec@@QEAA@XZ; HoldCritSec::~HoldCritSec(void)
0x180078d7c  mov     rbx, [rsp+0D8h+arg_10]
0x180078d84  add     rsp, 0B0h
0x180078d8b  pop     r14
0x180078d8d  pop     r13
0x180078d8f  pop     r12
0x180078d91  pop     rdi
0x180078d92  pop     rsi
0x180078d93  retn
```
