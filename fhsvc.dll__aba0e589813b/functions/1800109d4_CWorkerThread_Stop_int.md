# CWorkerThread::Stop(int)

- ea: `0x1800109d4`
- end: `0x180010aff`
- name: `?Stop@CWorkerThread@@QEAAJH@Z`
- size: `299`
- prototype: `__int64 __fastcall(CWorkerThread *this, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800020c0`
- `0x1800062b0`
- `0x1800065c0`
- `0x18000f14c`
- `0x18000f2c0`
- `0x180010848`

## callees

- `0x18000ca14`
- `0x18000d910`
- `0x1800109d4`
- `0x180010c84`
- `0x180010e8c`
- `0x180013010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180010aca`
- `KERNEL32!SetEvent` at `0x180010aca`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x180010ab9`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x180010ab9`

## pseudocode

```c
__int64 __fastcall CWorkerThread::Stop(CWorkerThread *this, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // esi
  unsigned int v6; // edi
  PVOID *v7; // rcx
  int v8; // eax

  v4 = a2;
  v6 = 0;
  if ( !*((_DWORD *)this + 12) )
  {
    if ( (Microsoft_Windows_FileHistory_ServiceEnableBits & 1) != 0 )
      McTemplateU0zt_EventWriteTransfer(this, BackupStopStart, *((_QWORD *)this + 3), (unsigned int)a2);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
          *((_QWORD *)this + 3));
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
      {
        LOBYTE(a4) = v4;
        WPP_SF_c(v7[2], a2, a3, a4);
      }
    }
    *((_DWORD *)this + 18) = 4;
    if ( *((_QWORD *)this + 5) && (v7 = (PVOID *)*((_QWORD *)this + 2)) != 0 )
    {
      v8 = (*((__int64 (__fastcall **)(PVOID *))*v7 + 9))(v7);
      v6 = v8;
      if ( v8 < 0 )
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
            (unsigned int)v8);
      }
      if ( v4 )
      {
        WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 5), 1);
        *((_DWORD *)this + 12) = 1;
        SetEvent(*((HANDLE *)this + 7));
      }
    }
    else
    {
      v6 = -2147418113;
    }
    if ( (Microsoft_Windows_FileHistory_ServiceEnableBits & 1) != 0 )
      McTemplateU0zt_EventWriteTransfer(v7, BackupStopStop, *((_QWORD *)this + 3), v4);
  }
  return v6;
}

```

## disassembly

```asm
0x1800109d4  push    rbx
0x1800109d6  push    rsi
0x1800109d7  push    rdi
0x1800109d8  push    r14
0x1800109da  sub     rsp, 28h
0x1800109de  mov     esi, edx
0x1800109e0  mov     rbx, rcx
0x1800109e3  xor     edi, edi
0x1800109e5  cmp     [rcx+30h], edi
0x1800109e8  jnz     loc_180010AF3
0x1800109ee  test    cs:Microsoft_Windows_FileHistory_ServiceEnableBits, 1
0x1800109f5  jz      short loc_180010A0A
0x1800109f7  mov     r9d, edx
0x1800109fa  mov     r8, [rcx+18h]
0x1800109fe  lea     rdx, BackupStopStart
0x180010a05  call    McTemplateU0zt_EventWriteTransfer
0x180010a0a  lea     r14, WPP_GLOBAL_Control
0x180010a11  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a18  cmp     rcx, r14
0x180010a1b  jz      short loc_180010A5A
0x180010a1d  test    byte ptr [rcx+1Ch], 8
0x180010a21  jz      short loc_180010A43
0x180010a23  mov     edx, 29h ; ')'
0x180010a28  mov     r9, [rbx+18h]
0x180010a2c  lea     r8, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x180010a33  mov     rcx, [rcx+10h]
0x180010a37  call    WPP_SF_S
0x180010a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a43  cmp     rcx, r14
0x180010a46  jz      short loc_180010A5A
0x180010a48  test    byte ptr [rcx+1Ch], 8
0x180010a4c  jz      short loc_180010A5A
0x180010a4e  mov     r9b, sil
0x180010a51  mov     rcx, [rcx+10h]
0x180010a55  call    WPP_SF_c
0x180010a5a  mov     dword ptr [rbx+48h], 4
0x180010a61  cmp     [rbx+28h], rdi
0x180010a65  jz      short loc_180010AD2
0x180010a67  mov     rcx, [rbx+10h]
0x180010a6b  test    rcx, rcx
0x180010a6e  jz      short loc_180010AD2
0x180010a70  mov     rax, [rcx]
0x180010a73  mov     rax, [rax+48h]
0x180010a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a7c  mov     edi, eax
0x180010a7e  test    eax, eax
0x180010a80  jns     short loc_180010AAC
0x180010a82  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a89  cmp     rcx, r14
0x180010a8c  jz      short loc_180010AAC
0x180010a8e  test    byte ptr [rcx+1Ch], 2
0x180010a92  jz      short loc_180010AAC
0x180010a94  mov     edx, 2Bh ; '+'
0x180010a99  mov     r9d, eax
0x180010a9c  lea     r8, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x180010aa3  mov     rcx, [rcx+10h]
0x180010aa7  call    WPP_SF_d
0x180010aac  test    esi, esi
0x180010aae  jz      short loc_180010AD7
0x180010ab0  mov     edx, 1; fCancelPendingCallbacks
0x180010ab5  mov     rcx, [rbx+28h]; pwk
0x180010ab9  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180010abf  mov     dword ptr [rbx+30h], 1
0x180010ac6  mov     rcx, [rbx+38h]; hEvent
0x180010aca  call    cs:__imp_SetEvent
0x180010ad0  jmp     short loc_180010AD7
0x180010ad2  mov     edi, 8000FFFFh
0x180010ad7  test    cs:Microsoft_Windows_FileHistory_ServiceEnableBits, 1
0x180010ade  jz      short loc_180010AF3
0x180010ae0  mov     r9d, esi
0x180010ae3  mov     r8, [rbx+18h]
0x180010ae7  lea     rdx, BackupStopStop
0x180010aee  call    McTemplateU0zt_EventWriteTransfer
0x180010af3  mov     eax, edi
0x180010af5  add     rsp, 28h
0x180010af9  pop     r14
0x180010afb  pop     rdi
0x180010afc  pop     rsi
0x180010afd  pop     rbx
0x180010afe  retn
```
