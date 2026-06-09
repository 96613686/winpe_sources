# CAbstractMultiRangeTransfer::OnAsyncOpCompleted(HoldCritSec *)

- ea: `0x1800558c0`
- end: `0x180055a44`
- name: `?OnAsyncOpCompleted@CAbstractMultiRangeTransfer@@MEAAXPEAVHoldCritSec@@@Z`
- size: `388`
- prototype: `void __fastcall(CAbstractMultiRangeTransfer *__hidden this, struct HoldCritSec *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800558c0`
- `0x180055a4c`
- `0x180055c10`
- `0x18009e9c8`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800558f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005596c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800558f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005596c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180055904`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18005597b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180055904`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18005597b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800559df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800559df`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800558ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180055918`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800558ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180055918`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAbstractMultiRangeTransfer::OnAsyncOpCompleted(
        CAbstractMultiRangeTransfer *this,
        struct HoldCritSec *a2)
{
  struct HoldCritSec *v2; // rsi
  CAbstractMultiRangeTransfer *v3; // rdi
  char v4; // bl
  int TickCount64; // r15d
  HANDLE CurrentThread; // rax
  int v7; // eax
  HANDLE v8; // rax
  DWORD v9; // eax
  DWORD LastError; // eax
  bool v11; // r8
  int v12; // edx
  ComError *v13; // [rsp+20h] [rbp-38h] BYREF

  v2 = a2;
  v3 = this;
  v4 = 0;
  if ( *((_BYTE *)this + 400) )
  {
    TickCount64 = GetTickCount64();
    CurrentThread = GetCurrentThread();
    if ( SetThreadPriority(CurrentThread, 0x10000) )
    {
      v4 = 1;
      v7 = GetTickCount64();
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          &WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids,
          (unsigned int)(v7 - TickCount64));
    }
    else if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids, LastError);
    }
  }
  try
  {
    (*((void (__fastcall **)(CAbstractMultiRangeTransfer *))v3 + 79))(v3);
  }
  catch ( ComError *v13 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_20fca9fb9c3b3acfa950c734de940ed2_Traceguids);
    v12 = *((_DWORD *)v13 + 6);
    *((_DWORD *)this + 20) = 3;
    *((_DWORD *)this + 18) = v12;
    *((_DWORD *)this + 19) = 5;
    CAbstractMultiRangeTransfer::GotoState(this, 0xCu, v11);
    v3 = this;
    v2 = a2;
    goto LABEL_7;
  }
  if ( v4 )
  {
    v8 = GetCurrentThread();
    if ( !SetThreadPriority(v8, 0x20000)
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v9 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids, v9);
    }
  }
LABEL_7:
  CAbstractMultiRangeTransfer::StatePump(v3);
  CAbstractMultiRangeTransfer::CheckForJobCallback(v3, v2);
}

```

## disassembly

```asm
0x1800558c0  mov     [rsp+arg_8], rdx
0x1800558c5  mov     [rsp+arg_0], rcx
0x1800558ca  push    rbx
0x1800558cb  push    rsi
0x1800558cc  push    rdi
0x1800558cd  push    r14
0x1800558cf  push    r15
0x1800558d1  sub     rsp, 30h
0x1800558d5  mov     rsi, rdx
0x1800558d8  mov     rdi, rcx
0x1800558db  xor     bl, bl
0x1800558dd  mov     [rsp+58h+arg_10], bl
0x1800558e1  cmp     [rcx+190h], bl
0x1800558e7  jz      loc_180055A29
0x1800558ed  call    cs:__imp_GetTickCount64
0x1800558f3  mov     r15, rax
0x1800558f6  call    cs:__imp_GetCurrentThread
0x1800558fc  mov     rcx, rax; hThread
0x1800558ff  mov     edx, 10000h; nPriority
0x180055904  call    cs:__imp_SetThreadPriority
0x18005590a  test    eax, eax
0x18005590c  jz      loc_1800559BE
0x180055912  mov     bl, 1
0x180055914  mov     [rsp+58h+arg_10], bl
0x180055918  call    cs:__imp_GetTickCount64
0x18005591e  lea     r14, WPP_GLOBAL_Control
0x180055925  mov     rcx, cs:WPP_GLOBAL_Control
0x18005592c  cmp     rcx, r14
0x18005592f  jz      short loc_18005593A
0x180055931  test    [rcx+1Ch], bl
0x180055934  jnz     loc_180055A09
0x18005593a  mov     rcx, rdi
0x18005593d  mov     rax, [rdi+278h]
0x180055944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055949  nop
0x18005594a  test    bl, bl
0x18005594c  jnz     short loc_18005596C
0x18005594e  mov     rcx, rdi; this
0x180055951  call    ?StatePump@CAbstractMultiRangeTransfer@@IEAAXXZ; CAbstractMultiRangeTransfer::StatePump(void)
0x180055956  mov     rdx, rsi; struct HoldCritSec *
0x180055959  mov     rcx, rdi; this
0x18005595c  add     rsp, 30h
0x180055960  pop     r15
0x180055962  pop     r14
0x180055964  pop     rdi
0x180055965  pop     rsi
0x180055966  pop     rbx
0x180055967  jmp     ?CheckForJobCallback@CAbstractMultiRangeTransfer@@IEAAXPEAVHoldCritSec@@@Z; CAbstractMultiRangeTransfer::CheckForJobCallback(HoldCritSec *)
0x18005596c  call    cs:__imp_GetCurrentThread
0x180055972  nop
0x180055973  mov     rcx, rax; hThread
0x180055976  mov     edx, 20000h; nPriority
0x18005597b  call    cs:__imp_SetThreadPriority
0x180055981  test    eax, eax
0x180055983  jnz     short loc_18005594E
0x180055985  mov     rax, cs:WPP_GLOBAL_Control
0x18005598c  cmp     rax, r14
0x18005598f  jz      short loc_18005594E
0x180055991  test    byte ptr [rax+1Ch], 2
0x180055995  jz      short loc_18005594E
0x180055997  call    cs:__imp_GetLastError
0x18005599d  mov     edx, 34h ; '4'
0x1800559a2  mov     r9d, eax
0x1800559a5  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x1800559ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800559b3  mov     rcx, [rcx+10h]
0x1800559b7  call    WPP_SF_d
0x1800559bc  jmp     short loc_18005594E
0x1800559be  lea     r14, WPP_GLOBAL_Control
0x1800559c5  mov     rax, cs:WPP_GLOBAL_Control
0x1800559cc  cmp     rax, r14
0x1800559cf  jz      loc_18005593A
0x1800559d5  test    byte ptr [rax+1Ch], 2
0x1800559d9  jz      loc_18005593A
0x1800559df  call    cs:__imp_GetLastError
0x1800559e5  mov     edx, 32h ; '2'
0x1800559ea  mov     r9d, eax
0x1800559ed  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x1800559f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800559fb  mov     rcx, [rcx+10h]
0x1800559ff  call    WPP_SF_d
0x180055a04  jmp     loc_18005593A
0x180055a09  sub     eax, r15d
0x180055a0c  mov     edx, 33h ; '3'
0x180055a11  mov     r9d, eax
0x180055a14  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x180055a1b  mov     rcx, [rcx+10h]
0x180055a1f  call    WPP_SF_d
0x180055a24  jmp     loc_18005593A
0x180055a29  lea     r14, WPP_GLOBAL_Control
0x180055a30  jmp     loc_18005593A
0x180055a35  mov     rdi, [rsp+58h+arg_0]
0x180055a3a  mov     rsi, [rsp+58h+arg_8]
0x180055a3f  jmp     loc_18005594E
```
