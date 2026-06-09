# FwPlumber::AbortPolicy(void)

- ea: `0x18006869c`
- end: `0x18006885a`
- name: `?AbortPolicy@FwPlumber@@YAXXZ`
- size: `446`
- prototype: `void __fastcall(FwPlumber *this, __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180068678`

## callees

- `0x180017110`
- `0x18001d2b4`
- `0x18001f830`
- `0x180054b54`
- `0x18006869c`
- `0x180068dec`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800687e3`
- `ntdll!EtwEventWrite` at `0x180068814`
- `ntdll!EtwEventWrite` at `0x18006884e`
- `ntdll!EtwEventWrite` at `0x1800687e3`
- `ntdll!EtwEventWrite` at `0x180068814`
- `ntdll!EtwEventWrite` at `0x18006884e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800687af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800687af`
- `fwbase!FwFree` at `0x18006872a`
- `fwbase!FwFree` at `0x180068747`
- `fwbase!FwFree` at `0x18006872a`
- `fwbase!FwFree` at `0x180068747`
- `fwpuclnt!FwpmTransactionAbort0` at `0x1800687f0`
- `fwpuclnt!FwpmTransactionAbort0` at `0x1800687f0`

## pseudocode

```c
void __fastcall FwPlumber::AbortPolicy(FwPlumber *this, __int64 a2, int a3)
{
  FwPlumber *v3; // rcx
  unsigned int v4; // edx
  DWORD v5; // ebx
  unsigned int v6; // edx
  FwPlumber *v7; // rcx
  __int64 v8; // r10

  v3 = (FwPlumber *)WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 121, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids);
  LOBYTE(v3) = byte_180131E88 == 0;
  FwPlumber::ThrowIf(v3, 87, a3);
  byte_180131E88 = 0;
  if ( dword_180131DC8 )
  {
    if ( qword_180131E38 )
      FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(qword_180131E38, v4);
    qword_180131E38 = qword_180131DB0;
    qword_180131DB0 = 0;
    if ( (_QWORD)xmmword_180131E60 )
    {
      FwFree(xmmword_180131E60);
      *(_QWORD *)&xmmword_180131E60 = 0;
    }
    if ( (_QWORD)xmmword_180131E70 )
    {
      FwFree(xmmword_180131E70);
      *(_QWORD *)&xmmword_180131E70 = 0;
    }
    dword_180131DC8 = 0;
  }
  if ( dword_180131D9C )
  {
    if ( qword_180131DF0 && (_DWORD)xmmword_180131DF8 == 1 && qword_180131DF0 )
      FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(qword_180131DF0, v4);
    qword_180131DF0 = qword_180131EA8;
    qword_180131EA8 = 0;
    if ( *((_QWORD *)&xmmword_180131DF8 + 1) )
    {
      LocalFree(*((HLOCAL *)&xmmword_180131DF8 + 1));
      *((_QWORD *)&xmmword_180131DF8 + 1) = 0;
    }
    dword_180131D9C = 0;
  }
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_BFE_TransactionAbort_Enter, 0, 0);
  v5 = FwpmTransactionAbort0(engineHandle);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_BFE_TransactionAbort_Exit, 0, 0);
  FwPlumberTrackError(v5, (struct _FW_PLUMBER_ERROR_TRACKING *)&g_FwAbortDynamic);
  if ( v5 )
    FwPlumber::ThrowWin32(v7, v6);
  if ( v8 )
    EtwEventWrite(v8, MPS_SVC_Plumber_Policy_Abort, 0, 0);
}

```

## disassembly

```asm
0x18006869c  push    rbx
0x18006869e  sub     rsp, 20h
0x1800686a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800686a9  lea     rax, WPP_GLOBAL_Control
0x1800686b0  cmp     rcx, rax
0x1800686b3  jz      short loc_1800686D0
0x1800686b5  test    byte ptr [rcx+1Ch], 8
0x1800686b9  jz      short loc_1800686D0
0x1800686bb  mov     rcx, [rcx+10h]
0x1800686bf  lea     r8, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids
0x1800686c6  mov     edx, 79h ; 'y'
0x1800686cb  call    WPP_SF_
0x1800686d0  cmp     cs:byte_180131E88, 0
0x1800686d7  mov     edx, 80070057h; bool
0x1800686dc  setz    cl; this
0x1800686df  call    ?ThrowIf@FwPlumber@@YAX_NJ@Z; FwPlumber::ThrowIf(bool,long)
0x1800686e4  cmp     cs:dword_180131DC8, 0
0x1800686eb  mov     cs:byte_180131E88, 0
0x1800686f2  jz      short loc_180068762
0x1800686f4  mov     rcx, cs:qword_180131E38; this
0x1800686fb  test    rcx, rcx
0x1800686fe  jz      short loc_180068705
0x180068700  call    ??_GFILTER_HANDLE@FwPlumber@@QEAAPEAXI@Z; FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(uint)
0x180068705  mov     rax, cs:qword_180131DB0
0x18006870c  mov     rcx, qword ptr cs:xmmword_180131E60
0x180068713  mov     cs:qword_180131E38, rax
0x18006871a  mov     cs:qword_180131DB0, 0
0x180068725  test    rcx, rcx
0x180068728  jz      short loc_18006873B
0x18006872a  call    cs:__imp_FwFree
0x180068730  mov     qword ptr cs:xmmword_180131E60, 0
0x18006873b  mov     rcx, qword ptr cs:xmmword_180131E70
0x180068742  test    rcx, rcx
0x180068745  jz      short loc_180068758
0x180068747  call    cs:__imp_FwFree
0x18006874d  mov     qword ptr cs:xmmword_180131E70, 0
0x180068758  mov     cs:dword_180131DC8, 0
0x180068762  cmp     cs:dword_180131D9C, 0
0x180068769  jz      short loc_1800687CA
0x18006876b  mov     rcx, cs:qword_180131DF0; this
0x180068772  test    rcx, rcx
0x180068775  jz      short loc_18006878A
0x180068777  cmp     dword ptr cs:xmmword_180131DF8, 1
0x18006877e  jnz     short loc_18006878A
0x180068780  test    rcx, rcx
0x180068783  jz      short loc_18006878A
0x180068785  call    ??_GFILTER_HANDLE@FwPlumber@@QEAAPEAXI@Z; FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(uint)
0x18006878a  mov     rax, cs:qword_180131EA8
0x180068791  mov     rcx, qword ptr cs:xmmword_180131DF8+8; hMem
0x180068798  mov     cs:qword_180131DF0, rax
0x18006879f  mov     cs:qword_180131EA8, 0
0x1800687aa  test    rcx, rcx
0x1800687ad  jz      short loc_1800687C0
0x1800687af  call    cs:__imp_LocalFree
0x1800687b5  mov     qword ptr cs:xmmword_180131DF8+8, 0
0x1800687c0  mov     cs:dword_180131D9C, 0
0x1800687ca  mov     rcx, cs:g_Provider
0x1800687d1  test    rcx, rcx
0x1800687d4  jz      short loc_1800687E9
0x1800687d6  xor     r9d, r9d
0x1800687d9  lea     rdx, MPS_SVC_BFE_TransactionAbort_Enter
0x1800687e0  xor     r8d, r8d
0x1800687e3  call    cs:__imp_EtwEventWrite
0x1800687e9  mov     rcx, cs:engineHandle; engineHandle
0x1800687f0  call    cs:__imp_FwpmTransactionAbort0
0x1800687f6  mov     r10, cs:g_Provider
0x1800687fd  mov     ebx, eax
0x1800687ff  test    r10, r10
0x180068802  jz      short loc_180068821
0x180068804  xor     r9d, r9d
0x180068807  lea     rdx, MPS_SVC_BFE_TransactionAbort_Exit
0x18006880e  xor     r8d, r8d
0x180068811  mov     rcx, r10
0x180068814  call    cs:__imp_EtwEventWrite
0x18006881a  mov     r10, cs:g_Provider
0x180068821  lea     rdx, ?g_FwAbortDynamic@@3U_FW_PLUMBER_ERROR_TRACKING@@A; struct _FW_PLUMBER_ERROR_TRACKING *
0x180068828  mov     ecx, ebx; unsigned int
0x18006882a  call    ?FwPlumberTrackError@@YAXKPEAU_FW_PLUMBER_ERROR_TRACKING@@@Z; FwPlumberTrackError(ulong,_FW_PLUMBER_ERROR_TRACKING *)
0x18006882f  test    ebx, ebx
0x180068831  jz      short loc_180068839
0x180068833  call    ?ThrowWin32@FwPlumber@@YAXK@Z; FwPlumber::ThrowWin32(ulong)
0x180068839  test    r10, r10
0x18006883c  jz      short loc_180068854
0x18006883e  xor     r9d, r9d
0x180068841  lea     rdx, MPS_SVC_Plumber_Policy_Abort
0x180068848  xor     r8d, r8d
0x18006884b  mov     rcx, r10
0x18006884e  call    cs:__imp_EtwEventWrite
0x180068854  add     rsp, 20h
0x180068858  pop     rbx
0x180068859  retn
```
