# SyncClientOnlySyncPrepCompleteDirCallback

- ea: `0x18001cc40`
- end: `0x18001d156`
- name: `SyncClientOnlySyncPrepCompleteDirCallback`
- size: `1302`
- prototype: `__int64 __usercall@<rax>(LPVOID lpMem@<rcx>, HANDLE Handle@<rdx>, HANDLE@<r8>, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001cc40`
- `0x1800360c0`
- `0x180036394`
- `0x18003c460`
- `0x18004fef4`
- `0x180073fe8`

## import_xrefs

- `ntdll!NtClose` at `0x18001cd08`
- `ntdll!NtClose` at `0x18001cd43`
- `ntdll!NtClose` at `0x18001cd08`
- `ntdll!NtClose` at `0x18001cd43`
- `ntdll!RtlNtStatusToDosError` at `0x18001cca8`
- `ntdll!RtlNtStatusToDosError` at `0x18001cca8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cdae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cdae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cda0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cda0`

## string_xrefs

- `0x18001ce11`: `SyncEnumDefaultCompleteDirCallback: Ctx: 0x%p pHdl: 0x%p sHdl: 0x%p SyncStatus: 0x%x Status: 0x%x`
- `0x18001d0ed`: `SyncEnumDefaultCompleteDirCallback: 0x%x`
- `0x18001cf15`: `SyncClientOnlySyncPrepCompleteDirCallback: Ctx: 0x%p LocalHdl: 0x%p DummyHdl: 0x%p LocalStatus: 0x%x DummyStatus: 0x%x`
- `0x18001cf8b`: `SyncClientOnlySyncPrepCompleteDirCallback: LocalStatus = %x`
- `0x18001d126`: `SyncClientOnlySyncPrepCompleteDirCallback: 0x%x`

## pseudocode

```c
__int64 __fastcall SyncClientOnlySyncPrepCompleteDirCallback(
        _QWORD *lpMem,
        char *Handle,
        HANDLE a3,
        unsigned int a4,
        int a5)
{
  int v7; // r12d
  NTSTATUS v8; // ebp
  CObjectMonitor *v11; // rax
  CObjectMonitor *v12; // rax
  HANDLE ProcessHeap; // rax
  CObjectMonitor *v14; // rax
  __int64 v16; // [rsp+20h] [rbp-48h]
  __int64 v18; // [rsp+28h] [rbp-40h]

  v7 = 0;
  v8 = 0;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(
      L"SyncClientOnlySyncPrepCompleteDirCallback: Ctx: 0x%p LocalHdl: 0x%p DummyHdl: 0x%p LocalStatus: 0x%x DummyStatus: 0x%x",
      lpMem,
      Handle,
      a3,
      a4,
      a5);
    WPP_SF_qqqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      30,
      WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids,
      lpMem,
      Handle,
      a3,
      a4,
      a5);
    v11 = WPP_GLOBAL_Control;
  }
  if ( a4 )
  {
    if ( v11 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncClientOnlySyncPrepCompleteDirCallback: LocalStatus = %x", a4);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 31, WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids, a4);
      v11 = WPP_GLOBAL_Control;
    }
    v7 = 2048;
    v8 = a4;
  }
  if ( v11 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 108) & 4) != 0 )
  {
    LODWORD(v18) = v8;
    LODWORD(v16) = v7;
    SyncTraceOutputInternal(
      L"SyncEnumDefaultCompleteDirCallback: Ctx: 0x%p pHdl: 0x%p sHdl: 0x%p SyncStatus: 0x%x Status: 0x%x",
      lpMem,
      Handle,
      a3,
      v16,
      v18);
    WPP_SF_qqqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      44,
      WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids,
      lpMem,
      Handle,
      a3,
      v7,
      v8);
  }
  *(_DWORD *)(lpMem[1] + 4LL) = RtlNtStatusToDosError(v8);
  *(_DWORD *)lpMem[1] |= v7;
  if ( v8 )
    *(_QWORD *)(lpMem[1] + 8LL) = 0;
  if ( lpMem[1] == *(_QWORD *)(*(_QWORD *)(*lpMem + 16LL) + 16LL) )
    goto LABEL_22;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(L"SyncCloseFile: FileHandle: 0x%p", Handle);
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 92, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, Handle);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v12 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncCloseFile: %p", Handle);
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 93, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, Handle);
      v12 = WPP_GLOBAL_Control;
    }
  }
  if ( (unsigned __int64)(Handle - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    _InterlockedIncrement64(&ClosedHandles);
    NtClose(Handle);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v12 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncCloseFile");
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 94, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids);
    v12 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
    goto LABEL_23;
  if ( v12 != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v12 + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(L"SyncCloseFile: FileHandle: 0x%p", a3);
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 92, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, a3);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v12 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncCloseFile: %p", a3);
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 93, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, a3);
      v12 = WPP_GLOBAL_Control;
    }
  }
  if ( a3 != (HANDLE)-1LL )
  {
    _InterlockedIncrement64(&ClosedHandles);
    NtClose(a3);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v12 != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v12 + 108) & 8) == 0 )
    {
LABEL_23:
      if ( v12 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 108) & 4) != 0 )
      {
        SyncTraceOutputInternal(L"SyncEnumFreeContext: DirContext: 0x%p", lpMem);
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids, lpMem);
      }
      goto LABEL_26;
    }
    SyncTraceOutputInternal(L"SyncCloseFile");
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 94, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids);
LABEL_22:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_23;
  }
LABEL_26:
  ++NumFree;
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, lpMem);
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumFreeContext");
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 13, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids);
      v14 = WPP_GLOBAL_Control;
    }
    if ( v14 != (CObjectMonitor *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v14 + 108) & 8) != 0 )
      {
        SyncTraceOutputInternal(L"SyncEnumDefaultCompleteDirCallback: 0x%x", 0);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 45, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids, 0);
        v14 = WPP_GLOBAL_Control;
      }
      if ( v14 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 108) & 8) != 0 )
      {
        SyncTraceOutputInternal(L"SyncClientOnlySyncPrepCompleteDirCallback: 0x%x", 0);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 32, WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids, 0);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001cc40  mov     rax, rsp
0x18001cc43  push    r13
0x18001cc45  sub     rsp, 60h
0x18001cc49  mov     [rax+10h], rbp
0x18001cc4d  mov     [rax+18h], rsi
0x18001cc51  mov     rsi, r8
0x18001cc54  mov     [rax-10h], rdi
0x18001cc58  mov     rdi, rcx
0x18001cc5b  mov     [rax-18h], r12
0x18001cc5f  xor     r12d, r12d
0x18001cc62  mov     [rax-20h], r14
0x18001cc66  xor     ebp, ebp
0x18001cc68  mov     [rax-28h], r15
0x18001cc6c  mov     r14d, r9d
0x18001cc6f  mov     r15, rdx
0x18001cc72  mov     rax, cs:WPP_GLOBAL_Control
0x18001cc79  lea     r13, WPP_GLOBAL_Control
0x18001cc80  cmp     rax, r13
0x18001cc83  jz      short loc_18001CC8F
0x18001cc85  test    byte ptr [rax+6Ch], 4
0x18001cc89  jnz     loc_18001CF10
0x18001cc8f  test    r14d, r14d
0x18001cc92  jnz     loc_18001CF7D
0x18001cc98  mov     r14, [rsp+68h+var_20]
0x18001cc9d  cmp     rax, r13
0x18001cca0  jnz     loc_18001CE03
0x18001cca6  mov     ecx, ebp; Status
0x18001cca8  call    cs:__imp_RtlNtStatusToDosError
0x18001ccae  mov     rcx, [rdi+8]
0x18001ccb2  mov     [rcx+4], eax
0x18001ccb5  mov     rax, [rdi+8]
0x18001ccb9  or      [rax], r12d
0x18001ccbc  mov     r12, [rsp+68h+var_18]
0x18001ccc1  test    ebp, ebp
0x18001ccc3  mov     rbp, [rsp+68h+arg_8]
0x18001ccc8  jnz     loc_18001CFCB
0x18001ccce  mov     rax, [rdi]
0x18001ccd1  mov     rcx, [rax+10h]
0x18001ccd5  mov     rax, [rcx+10h]
0x18001ccd9  cmp     [rdi+8], rax
0x18001ccdd  jz      loc_18001CD83
0x18001cce3  mov     rax, cs:WPP_GLOBAL_Control
0x18001ccea  cmp     rax, r13
0x18001cced  jnz     loc_18001CE62
0x18001ccf3  lea     rcx, [r15-1]
0x18001ccf7  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001ccfb  ja      short loc_18001CD15
0x18001ccfd  lock inc cs:ClosedHandles
0x18001cd05  mov     rcx, r15; Handle
0x18001cd08  call    cs:__imp_NtClose
0x18001cd0e  mov     rax, cs:WPP_GLOBAL_Control
0x18001cd15  cmp     rax, r13
0x18001cd18  jz      short loc_18001CD24
0x18001cd1a  test    byte ptr [rax+6Ch], 8
0x18001cd1e  jnz     loc_18001D016
0x18001cd24  test    rsi, rsi
0x18001cd27  jz      short loc_18001CD8A
0x18001cd29  cmp     rax, r13
0x18001cd2c  jnz     loc_18001CEB9
0x18001cd32  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001cd36  jz      short loc_18001CD50
0x18001cd38  lock inc cs:ClosedHandles
0x18001cd40  mov     rcx, rsi; Handle
0x18001cd43  call    cs:__imp_NtClose
0x18001cd49  mov     rax, cs:WPP_GLOBAL_Control
0x18001cd50  cmp     rax, r13
0x18001cd53  jz      short loc_18001CD99
0x18001cd55  test    byte ptr [rax+6Ch], 8
0x18001cd59  jz      short loc_18001CD8A
0x18001cd5b  lea     rcx, aSyncclosefile; "SyncCloseFile"
0x18001cd62  call    SyncTraceOutputInternal
0x18001cd67  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd6e  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x18001cd75  mov     edx, 5Eh ; '^'
0x18001cd7a  mov     rcx, [rcx+60h]
0x18001cd7e  call    WPP_SF_
0x18001cd83  mov     rax, cs:WPP_GLOBAL_Control
0x18001cd8a  cmp     rax, r13
0x18001cd8d  jz      short loc_18001CD99
0x18001cd8f  test    byte ptr [rax+6Ch], 4
0x18001cd93  jnz     loc_18001D084
0x18001cd99  inc     cs:NumFree
0x18001cda0  call    cs:__imp_GetProcessHeap
0x18001cda6  mov     r8, rdi; lpMem
0x18001cda9  xor     edx, edx; dwFlags
0x18001cdab  mov     rcx, rax; hHeap
0x18001cdae  call    cs:__imp_HeapFree
0x18001cdb4  mov     rax, cs:WPP_GLOBAL_Control
0x18001cdbb  mov     r15, [rsp+68h+var_28]
0x18001cdc0  mov     rdi, [rsp+68h+var_10]
0x18001cdc5  mov     rsi, [rsp+68h+arg_10]
0x18001cdcd  cmp     rax, r13
0x18001cdd0  jz      short loc_18001CDFA
0x18001cdd2  test    byte ptr [rax+6Ch], 8
0x18001cdd6  jnz     loc_18001D0B7
0x18001cddc  cmp     rax, r13
0x18001cddf  jz      short loc_18001CDFA
0x18001cde1  test    byte ptr [rax+6Ch], 8
0x18001cde5  jnz     loc_18001D0EB
0x18001cdeb  cmp     rax, r13
0x18001cdee  jz      short loc_18001CDFA
0x18001cdf0  test    byte ptr [rax+6Ch], 8
0x18001cdf4  jnz     loc_18001D124
0x18001cdfa  xor     eax, eax
0x18001cdfc  add     rsp, 60h
0x18001ce00  pop     r13
0x18001ce02  retn
0x18001ce03  test    byte ptr [rax+6Ch], 4
0x18001ce07  jz      loc_18001CCA6
0x18001ce0d  mov     dword ptr [rsp+68h+var_40], ebp
0x18001ce11  lea     rcx, aSyncenumdefaul_4; "SyncEnumDefaultCompleteDirCallback: Ctx"...
0x18001ce18  mov     r9, rsi
0x18001ce1b  mov     dword ptr [rsp+68h+var_48], r12d
0x18001ce20  mov     r8, r15
0x18001ce23  mov     rdx, rdi
0x18001ce26  call    SyncTraceOutputInternal
0x18001ce2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce32  lea     r8, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids
0x18001ce39  mov     [rsp+68h+var_30], ebp
0x18001ce3d  mov     edx, 2Ch ; ','
0x18001ce42  mov     [rsp+68h+var_38], r12d
0x18001ce47  mov     r9, rdi
0x18001ce4a  mov     [rsp+68h+var_40], rsi
0x18001ce4f  mov     rcx, [rcx+60h]
0x18001ce53  mov     [rsp+68h+var_48], r15
0x18001ce58  call    WPP_SF_qqqdD
0x18001ce5d  jmp     loc_18001CCA6
0x18001ce62  test    byte ptr [rax+6Ch], 4
0x18001ce66  jnz     loc_18001CFDC
0x18001ce6c  cmp     rax, r13
0x18001ce6f  jz      loc_18001CCF3
0x18001ce75  test    byte ptr [rax+6Ch], 1
0x18001ce79  jz      loc_18001CCF3
0x18001ce7f  mov     rdx, r15
0x18001ce82  lea     rcx, aSyncclosefileP; "SyncCloseFile: %p"
0x18001ce89  call    SyncTraceOutputInternal
0x18001ce8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce95  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x18001ce9c  mov     edx, 5Dh ; ']'
0x18001cea1  mov     r9, r15
0x18001cea4  mov     rcx, [rcx+60h]
0x18001cea8  call    WPP_SF_q
0x18001cead  mov     rax, cs:WPP_GLOBAL_Control
0x18001ceb4  jmp     loc_18001CCF3
0x18001ceb9  test    byte ptr [rax+6Ch], 4
0x18001cebd  jnz     loc_18001D04A
0x18001cec3  cmp     rax, r13
0x18001cec6  jz      loc_18001CD32
0x18001cecc  test    byte ptr [rax+6Ch], 1
0x18001ced0  jz      loc_18001CD32
0x18001ced6  mov     rdx, rsi
0x18001ced9  lea     rcx, aSyncclosefileP; "SyncCloseFile: %p"
0x18001cee0  call    SyncTraceOutputInternal
0x18001cee5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ceec  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x18001cef3  mov     edx, 5Dh ; ']'
0x18001cef8  mov     r9, rsi
0x18001cefb  mov     rcx, [rcx+60h]
0x18001ceff  call    WPP_SF_q
0x18001cf04  mov     rax, cs:WPP_GLOBAL_Control
0x18001cf0b  jmp     loc_18001CD32
0x18001cf10  mov     [rsp+68h+arg_0], rbx
0x18001cf15  lea     rcx, aSyncclientonly_1; "SyncClientOnlySyncPrepCompleteDirCallba"...
0x18001cf1c  mov     ebx, [rsp+68h+arg_20]
0x18001cf23  mov     r9, rsi
0x18001cf26  mov     dword ptr [rsp+68h+var_40], ebx
0x18001cf2a  mov     r8, r15
0x18001cf2d  mov     rdx, rdi
0x18001cf30  mov     dword ptr [rsp+68h+var_48], r14d
0x18001cf35  call    SyncTraceOutputInternal
0x18001cf3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf41  lea     r8, WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids
0x18001cf48  mov     [rsp+68h+var_30], ebx
0x18001cf4c  mov     edx, 1Eh
0x18001cf51  mov     [rsp+68h+var_38], r14d
0x18001cf56  mov     r9, rdi
0x18001cf59  mov     [rsp+68h+var_40], rsi
0x18001cf5e  mov     rcx, [rcx+60h]
0x18001cf62  mov     [rsp+68h+var_48], r15
0x18001cf67  call    WPP_SF_qqqdD
0x18001cf6c  mov     rax, cs:WPP_GLOBAL_Control
0x18001cf73  mov     rbx, [rsp+68h+arg_0]
0x18001cf78  jmp     loc_18001CC8F
0x18001cf7d  cmp     rax, r13
0x18001cf80  jz      short loc_18001CFBD
0x18001cf82  test    byte ptr [rax+6Ch], 1
0x18001cf86  jz      short loc_18001CFBD
0x18001cf88  mov     edx, r14d
0x18001cf8b  lea     rcx, aSyncclientonly_13; "SyncClientOnlySyncPrepCompleteDirCallba"...
0x18001cf92  call    SyncTraceOutputInternal
0x18001cf97  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf9e  lea     r8, WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids
0x18001cfa5  mov     edx, 1Fh
0x18001cfaa  mov     r9d, r14d
0x18001cfad  mov     rcx, [rcx+60h]
0x18001cfb1  call    WPP_SF_d
0x18001cfb6  mov     rax, cs:WPP_GLOBAL_Control
0x18001cfbd  mov     r12d, 800h
0x18001cfc3  mov     ebp, r14d
0x18001cfc6  jmp     loc_18001CC98
0x18001cfcb  mov     rax, [rdi+8]
0x18001cfcf  mov     qword ptr [rax+8], 0
0x18001cfd7  jmp     loc_18001CCCE
0x18001cfdc  mov     rdx, r15
0x18001cfdf  lea     rcx, aSyncclosefileF; "SyncCloseFile: FileHandle: 0x%p"
0x18001cfe6  call    SyncTraceOutputInternal
0x18001cfeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cff2  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x18001cff9  mov     edx, 5Ch ; '\'
0x18001cffe  mov     r9, r15
0x18001d001  mov     rcx, [rcx+60h]
0x18001d005  call    WPP_SF_q
0x18001d00a  mov     rax, cs:WPP_GLOBAL_Control
0x18001d011  jmp     loc_18001CE6C
0x18001d016  lea     rcx, aSyncclosefile; "SyncCloseFile"
0x18001d01d  call    SyncTraceOutputInternal
0x18001d022  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d029  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x18001d030  mov     edx, 5Eh ; '^'
0x18001d035  mov     rcx, [rcx+60h]
0x18001d039  call    WPP_SF_
0x18001d03e  mov     rax, cs:WPP_GLOBAL_Control
0x18001d045  jmp     loc_18001CD24
0x18001d04a  mov     rdx, rsi
0x18001d04d  lea     rcx, aSyncclosefileF; "SyncCloseFile: FileHandle: 0x%p"
0x18001d054  call    SyncTraceOutputInternal
0x18001d059  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d060  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x18001d067  mov     edx, 5Ch ; '\'
0x18001d06c  mov     r9, rsi
0x18001d06f  mov     rcx, [rcx+60h]
0x18001d073  call    WPP_SF_q
0x18001d078  mov     rax, cs:WPP_GLOBAL_Control
0x18001d07f  jmp     loc_18001CEC3
0x18001d084  mov     rdx, rdi
0x18001d087  lea     rcx, aSyncenumfreeco; "SyncEnumFreeContext: DirContext: 0x%p"
0x18001d08e  call    SyncTraceOutputInternal
0x18001d093  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d09a  lea     r8, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids
0x18001d0a1  mov     edx, 0Ch
0x18001d0a6  mov     r9, rdi
0x18001d0a9  mov     rcx, [rcx+60h]
0x18001d0ad  call    WPP_SF_q
0x18001d0b2  jmp     loc_18001CD99
0x18001d0b7  lea     rcx, aSyncenumfreeco_0; "SyncEnumFreeContext"
0x18001d0be  call    SyncTraceOutputInternal
0x18001d0c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0ca  lea     r8, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids
0x18001d0d1  mov     edx, 0Dh
0x18001d0d6  mov     rcx, [rcx+60h]
0x18001d0da  call    WPP_SF_
0x18001d0df  mov     rax, cs:WPP_GLOBAL_Control
0x18001d0e6  jmp     loc_18001CDDC
0x18001d0eb  xor     edx, edx
0x18001d0ed  lea     rcx, aSyncenumdefaul_1; "SyncEnumDefaultCompleteDirCallback: 0x%"...
0x18001d0f4  call    SyncTraceOutputInternal
0x18001d0f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d100  lea     r8, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids
0x18001d107  mov     edx, 2Dh ; '-'
0x18001d10c  xor     r9d, r9d
0x18001d10f  mov     rcx, [rcx+60h]
0x18001d113  call    WPP_SF_d
0x18001d118  mov     rax, cs:WPP_GLOBAL_Control
0x18001d11f  jmp     loc_18001CDEB
0x18001d124  xor     edx, edx
0x18001d126  lea     rcx, aSyncclientonly_15; "SyncClientOnlySyncPrepCompleteDirCallba"...
0x18001d12d  call    SyncTraceOutputInternal
0x18001d132  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d139  lea     r8, WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids
0x18001d140  mov     edx, 20h ; ' '
0x18001d145  xor     r9d, r9d
0x18001d148  mov     rcx, [rcx+60h]
0x18001d14c  call    WPP_SF_d
0x18001d151  jmp     loc_18001CDFA
```
