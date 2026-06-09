# FwPlumber::AbortPolicy(void)

- ea: `0x18006d73c`
- end: `0x18006d91a`
- name: `?AbortPolicy@FwPlumber@@YAXXZ`
- size: `478`
- prototype: `void __fastcall(FwPlumber *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006d714`

## callees

- `0x1800192e0`
- `0x18001f5d0`
- `0x180021b80`
- `0x1800238f4`
- `0x1800596e0`
- `0x18006d73c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18006d895`
- `ntdll!EtwEventWrite` at `0x18006d8cf`
- `ntdll!EtwEventWrite` at `0x18006d907`
- `ntdll!EtwEventWrite` at `0x18006d895`
- `ntdll!EtwEventWrite` at `0x18006d8cf`
- `ntdll!EtwEventWrite` at `0x18006d907`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d85b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d85b`
- `fwbase!FwFree` at `0x18006d7ca`
- `fwbase!FwFree` at `0x18006d7ed`
- `fwbase!FwFree` at `0x18006d7ca`
- `fwbase!FwFree` at `0x18006d7ed`
- `fwpuclnt!FwpmTransactionAbort0` at `0x18006d8a8`
- `fwpuclnt!FwpmTransactionAbort0` at `0x18006d8a8`

## pseudocode

```c
void __fastcall FwPlumber::AbortPolicy(FwPlumber *this, __int64 a2, int a3)
{
  FwPlumber *v3; // rcx
  unsigned int v4; // edx
  DWORD v5; // ebx
  unsigned int v6; // edx
  FwPlumber *v7; // rcx

  v3 = (FwPlumber *)WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 121, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids);
  LOBYTE(v3) = byte_180138020 == 0;
  FwPlumber::ThrowIf(v3, 87, a3);
  byte_180138020 = 0;
  if ( dword_180137F58 )
  {
    if ( qword_180137FD0 )
      FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(qword_180137FD0, v4);
    qword_180137FD0 = qword_180137F40;
    qword_180137F40 = 0;
    if ( (_QWORD)xmmword_180138000 )
    {
      FwFree(xmmword_180138000);
      *(_QWORD *)&xmmword_180138000 = 0;
    }
    if ( (_QWORD)xmmword_180138010 )
    {
      FwFree(xmmword_180138010);
      *(_QWORD *)&xmmword_180138010 = 0;
    }
    dword_180137F58 = 0;
  }
  if ( dword_180137F2C )
  {
    if ( qword_180137F80 && (_DWORD)xmmword_180137F88 == 1 && qword_180137F80 )
      FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(qword_180137F80, v4);
    qword_180137F80 = qword_180138040;
    qword_180138040 = 0;
    if ( *((_QWORD *)&xmmword_180137F88 + 1) )
    {
      LocalFree(*((HLOCAL *)&xmmword_180137F88 + 1));
      *((_QWORD *)&xmmword_180137F88 + 1) = 0;
    }
    dword_180137F2C = 0;
  }
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_BFE_TransactionAbort_Enter, 0, 0);
  v5 = FwpmTransactionAbort0(engineHandle);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_BFE_TransactionAbort_Exit, 0, 0);
  FwPlumberTrackError(v5, (struct _FW_PLUMBER_ERROR_TRACKING *)&g_FwAbortDynamic);
  FwPlumber::ThrowIf32Error(v7, v6);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_Plumber_Policy_Abort, 0, 0);
}

```

## disassembly

```asm
0x18006d73c  push    rbx
0x18006d73e  sub     rsp, 20h
0x18006d742  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d749  lea     rax, WPP_GLOBAL_Control
0x18006d750  cmp     rcx, rax
0x18006d753  jz      short loc_18006D770
0x18006d755  test    byte ptr [rcx+1Ch], 8
0x18006d759  jz      short loc_18006D770
0x18006d75b  mov     rcx, [rcx+10h]
0x18006d75f  lea     r8, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids
0x18006d766  mov     edx, 79h ; 'y'
0x18006d76b  call    WPP_SF_
0x18006d770  cmp     cs:byte_180138020, 0
0x18006d777  mov     edx, 80070057h; bool
0x18006d77c  setz    cl; this
0x18006d77f  call    ?ThrowIf@FwPlumber@@YAX_NJ@Z; FwPlumber::ThrowIf(bool,long)
0x18006d784  cmp     cs:dword_180137F58, 0
0x18006d78b  mov     cs:byte_180138020, 0
0x18006d792  jz      short loc_18006D80E
0x18006d794  mov     rcx, cs:qword_180137FD0; this
0x18006d79b  test    rcx, rcx
0x18006d79e  jz      short loc_18006D7A5
0x18006d7a0  call    ??_GFILTER_HANDLE@FwPlumber@@QEAAPEAXI@Z; FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(uint)
0x18006d7a5  mov     rax, cs:qword_180137F40
0x18006d7ac  mov     rcx, qword ptr cs:xmmword_180138000
0x18006d7b3  mov     cs:qword_180137FD0, rax
0x18006d7ba  mov     cs:qword_180137F40, 0
0x18006d7c5  test    rcx, rcx
0x18006d7c8  jz      short loc_18006D7E1
0x18006d7ca  call    cs:__imp_FwFree
0x18006d7d1  nop     dword ptr [rax+rax+00h]
0x18006d7d6  mov     qword ptr cs:xmmword_180138000, 0
0x18006d7e1  mov     rcx, qword ptr cs:xmmword_180138010
0x18006d7e8  test    rcx, rcx
0x18006d7eb  jz      short loc_18006D804
0x18006d7ed  call    cs:__imp_FwFree
0x18006d7f4  nop     dword ptr [rax+rax+00h]
0x18006d7f9  mov     qword ptr cs:xmmword_180138010, 0
0x18006d804  mov     cs:dword_180137F58, 0
0x18006d80e  cmp     cs:dword_180137F2C, 0
0x18006d815  jz      short loc_18006D87C
0x18006d817  mov     rcx, cs:qword_180137F80; this
0x18006d81e  test    rcx, rcx
0x18006d821  jz      short loc_18006D836
0x18006d823  cmp     dword ptr cs:xmmword_180137F88, 1
0x18006d82a  jnz     short loc_18006D836
0x18006d82c  test    rcx, rcx
0x18006d82f  jz      short loc_18006D836
0x18006d831  call    ??_GFILTER_HANDLE@FwPlumber@@QEAAPEAXI@Z; FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(uint)
0x18006d836  mov     rax, cs:qword_180138040
0x18006d83d  mov     rcx, qword ptr cs:xmmword_180137F88+8; hMem
0x18006d844  mov     cs:qword_180137F80, rax
0x18006d84b  mov     cs:qword_180138040, 0
0x18006d856  test    rcx, rcx
0x18006d859  jz      short loc_18006D872
0x18006d85b  call    cs:__imp_LocalFree
0x18006d862  nop     dword ptr [rax+rax+00h]
0x18006d867  mov     qword ptr cs:xmmword_180137F88+8, 0
0x18006d872  mov     cs:dword_180137F2C, 0
0x18006d87c  mov     rcx, cs:g_Provider
0x18006d883  test    rcx, rcx
0x18006d886  jz      short loc_18006D8A1
0x18006d888  xor     r9d, r9d
0x18006d88b  lea     rdx, MPS_SVC_BFE_TransactionAbort_Enter
0x18006d892  xor     r8d, r8d
0x18006d895  call    cs:__imp_EtwEventWrite
0x18006d89c  nop     dword ptr [rax+rax+00h]
0x18006d8a1  mov     rcx, cs:engineHandle; engineHandle
0x18006d8a8  call    cs:__imp_FwpmTransactionAbort0
0x18006d8af  nop     dword ptr [rax+rax+00h]
0x18006d8b4  mov     rcx, cs:g_Provider
0x18006d8bb  mov     ebx, eax
0x18006d8bd  test    rcx, rcx
0x18006d8c0  jz      short loc_18006D8DB
0x18006d8c2  xor     r9d, r9d
0x18006d8c5  lea     rdx, MPS_SVC_BFE_TransactionAbort_Exit
0x18006d8cc  xor     r8d, r8d
0x18006d8cf  call    cs:__imp_EtwEventWrite
0x18006d8d6  nop     dword ptr [rax+rax+00h]
0x18006d8db  lea     rdx, ?g_FwAbortDynamic@@3U_FW_PLUMBER_ERROR_TRACKING@@A; struct _FW_PLUMBER_ERROR_TRACKING *
0x18006d8e2  mov     ecx, ebx; unsigned int
0x18006d8e4  call    ?FwPlumberTrackError@@YAXKPEAU_FW_PLUMBER_ERROR_TRACKING@@@Z; FwPlumberTrackError(ulong,_FW_PLUMBER_ERROR_TRACKING *)
0x18006d8e9  call    ?ThrowIf32Error@FwPlumber@@YAXK@Z; FwPlumber::ThrowIf32Error(ulong)
0x18006d8ee  mov     rcx, cs:g_Provider
0x18006d8f5  test    rcx, rcx
0x18006d8f8  jz      short loc_18006D913
0x18006d8fa  xor     r9d, r9d
0x18006d8fd  lea     rdx, MPS_SVC_Plumber_Policy_Abort
0x18006d904  xor     r8d, r8d
0x18006d907  call    cs:__imp_EtwEventWrite
0x18006d90e  nop     dword ptr [rax+rax+00h]
0x18006d913  add     rsp, 20h
0x18006d917  pop     rbx
0x18006d918  retn
```
