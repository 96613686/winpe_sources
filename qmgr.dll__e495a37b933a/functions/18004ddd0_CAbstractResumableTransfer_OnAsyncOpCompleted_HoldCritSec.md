# CAbstractResumableTransfer::OnAsyncOpCompleted(HoldCritSec *)

- ea: `0x18004ddd0`
- end: `0x18004df54`
- name: `?OnAsyncOpCompleted@CAbstractResumableTransfer@@MEAAXPEAVHoldCritSec@@@Z`
- size: `388`
- prototype: `void __fastcall(CAbstractResumableTransfer *__hidden this, struct HoldCritSec *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18004ddd0`
- `0x18004df60`
- `0x18004e1f0`
- `0x18009e9c8`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004de06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004de7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004de06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004de7c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18004de14`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18004de8b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18004de14`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18004de8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004deef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004deef`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004ddfd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004de28`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004ddfd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004de28`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAbstractResumableTransfer::OnAsyncOpCompleted(
        CAbstractResumableTransfer *this,
        struct HoldCritSec *a2)
{
  struct HoldCritSec *v2; // rsi
  CAbstractResumableTransfer *v3; // rdi
  char v4; // bl
  int TickCount64; // r15d
  HANDLE CurrentThread; // rax
  int v7; // eax
  HANDLE v8; // rax
  DWORD v9; // eax
  DWORD LastError; // eax
  int v11; // edx
  ComError *v12; // [rsp+20h] [rbp-38h] BYREF

  v2 = a2;
  v3 = this;
  v4 = 0;
  if ( *((_BYTE *)this + 384) )
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
          WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids,
          (unsigned int)(v7 - TickCount64));
    }
    else if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids, LastError);
    }
  }
  try
  {
    (*((void (__fastcall **)(CAbstractResumableTransfer *))v3 + 101))(v3);
  }
  catch ( ComError *v12 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_44a4faa8359c329a008e8d91ae2fb7e6_Traceguids);
    v11 = *((_DWORD *)v12 + 6);
    *((_DWORD *)this + 20) = 3;
    *((_DWORD *)this + 18) = v11;
    *((_DWORD *)this + 19) = 5;
    CAbstractResumableTransfer::GotoState(this, 12);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids, v9);
    }
  }
LABEL_7:
  CAbstractResumableTransfer::StatePump(v3);
  CAbstractResumableTransfer::CheckForJobCallback(v3, v2);
}

```

## disassembly

```asm
0x18004ddd0  mov     [rsp+arg_8], rdx
0x18004ddd5  mov     [rsp+arg_0], rcx
0x18004ddda  push    rbx
0x18004dddb  push    rsi
0x18004dddc  push    rdi
0x18004dddd  push    r14
0x18004dddf  push    r15
0x18004dde1  sub     rsp, 30h
0x18004dde5  mov     rsi, rdx
0x18004dde8  mov     rdi, rcx
0x18004ddeb  xor     bl, bl
0x18004dded  mov     [rsp+58h+arg_10], bl
0x18004ddf1  cmp     [rcx+180h], bl
0x18004ddf7  jz      loc_18004DF39
0x18004ddfd  call    cs:__imp_GetTickCount64
0x18004de03  mov     r15, rax
0x18004de06  call    cs:__imp_GetCurrentThread
0x18004de0c  mov     rcx, rax; hThread
0x18004de0f  mov     edx, 10000h; nPriority
0x18004de14  call    cs:__imp_SetThreadPriority
0x18004de1a  test    eax, eax
0x18004de1c  jz      loc_18004DECE
0x18004de22  mov     bl, 1
0x18004de24  mov     [rsp+58h+arg_10], bl
0x18004de28  call    cs:__imp_GetTickCount64
0x18004de2e  lea     r14, WPP_GLOBAL_Control
0x18004de35  mov     rcx, cs:WPP_GLOBAL_Control
0x18004de3c  cmp     rcx, r14
0x18004de3f  jz      short loc_18004DE4A
0x18004de41  test    [rcx+1Ch], bl
0x18004de44  jnz     loc_18004DF19
0x18004de4a  mov     rcx, rdi
0x18004de4d  mov     rax, [rdi+328h]
0x18004de54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de59  nop
0x18004de5a  test    bl, bl
0x18004de5c  jnz     short loc_18004DE7C
0x18004de5e  mov     rcx, rdi; this
0x18004de61  call    ?StatePump@CAbstractResumableTransfer@@IEAAXXZ; CAbstractResumableTransfer::StatePump(void)
0x18004de66  mov     rdx, rsi; struct HoldCritSec *
0x18004de69  mov     rcx, rdi; this
0x18004de6c  add     rsp, 30h
0x18004de70  pop     r15
0x18004de72  pop     r14
0x18004de74  pop     rdi
0x18004de75  pop     rsi
0x18004de76  pop     rbx
0x18004de77  jmp     ?CheckForJobCallback@CAbstractResumableTransfer@@IEAAXPEAVHoldCritSec@@@Z; CAbstractResumableTransfer::CheckForJobCallback(HoldCritSec *)
0x18004de7c  call    cs:__imp_GetCurrentThread
0x18004de82  nop
0x18004de83  mov     rcx, rax; hThread
0x18004de86  mov     edx, 20000h; nPriority
0x18004de8b  call    cs:__imp_SetThreadPriority
0x18004de91  test    eax, eax
0x18004de93  jnz     short loc_18004DE5E
0x18004de95  mov     rax, cs:WPP_GLOBAL_Control
0x18004de9c  cmp     rax, r14
0x18004de9f  jz      short loc_18004DE5E
0x18004dea1  test    byte ptr [rax+1Ch], 2
0x18004dea5  jz      short loc_18004DE5E
0x18004dea7  call    cs:__imp_GetLastError
0x18004dead  mov     edx, 34h ; '4'
0x18004deb2  mov     r9d, eax
0x18004deb5  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x18004debc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dec3  mov     rcx, [rcx+10h]
0x18004dec7  call    WPP_SF_d
0x18004decc  jmp     short loc_18004DE5E
0x18004dece  lea     r14, WPP_GLOBAL_Control
0x18004ded5  mov     rax, cs:WPP_GLOBAL_Control
0x18004dedc  cmp     rax, r14
0x18004dedf  jz      loc_18004DE4A
0x18004dee5  test    byte ptr [rax+1Ch], 2
0x18004dee9  jz      loc_18004DE4A
0x18004deef  call    cs:__imp_GetLastError
0x18004def5  mov     edx, 32h ; '2'
0x18004defa  mov     r9d, eax
0x18004defd  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x18004df04  mov     rcx, cs:WPP_GLOBAL_Control
0x18004df0b  mov     rcx, [rcx+10h]
0x18004df0f  call    WPP_SF_d
0x18004df14  jmp     loc_18004DE4A
0x18004df19  sub     eax, r15d
0x18004df1c  mov     edx, 33h ; '3'
0x18004df21  mov     r9d, eax
0x18004df24  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x18004df2b  mov     rcx, [rcx+10h]
0x18004df2f  call    WPP_SF_d
0x18004df34  jmp     loc_18004DE4A
0x18004df39  lea     r14, WPP_GLOBAL_Control
0x18004df40  jmp     loc_18004DE4A
0x18004df45  mov     rdi, [rsp+58h+arg_0]
0x18004df4a  mov     rsi, [rsp+58h+arg_8]
0x18004df4f  jmp     loc_18004DE5E
```
