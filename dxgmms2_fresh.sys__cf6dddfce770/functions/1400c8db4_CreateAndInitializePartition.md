# CreateAndInitializePartition

- ea: `0x1400c8db4`
- end: `0x1400c900e`
- name: `CreateAndInitializePartition`
- size: `602`
- prototype: `__int64 __fastcall(struct _EPARTITION *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400c9488`

## callees

- `0x140003490`
- `0x140004268`
- `0x14002dbd0`
- `0x14002f480`
- `0x140058f50`
- `0x140059380`
- `0x1400c898c`
- `0x1400c8db4`

## import_xrefs

- `ntoskrnl!ZwManagePartition` at `0x1400c8eba`
- `ntoskrnl!ZwManagePartition` at `0x1400c8eba`
- `ntoskrnl!ObCloseHandle` at `0x1400c8fdc`
- `ntoskrnl!ObCloseHandle` at `0x1400c8fdc`
- `ntoskrnl!PsPartitionType` at `0x1400c8e16`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400c8e32`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400c8e32`
- `watchdog!WdLogSingleEntry2` at `0x1400c8e50`
- `watchdog!WdLogSingleEntry2` at `0x1400c8e50`
- `watchdog!WdLogSingleEntry0` at `0x1400c8f83`
- `watchdog!WdLogSingleEntry0` at `0x1400c8f83`
- `watchdog!WdLogSingleEntry1` at `0x1400c8ed5`
- `watchdog!WdLogSingleEntry1` at `0x1400c8ed5`

## string_xrefs

- `0x1400c8e65`: `Failed to open partition handle, EPartition=0x%p, Status=0x%.8x`

## pseudocode

```c
__int64 __fastcall CreateAndInitializePartition(struct _EPARTITION *a1, bool a2, VIDMM_PARTITION **a3)
{
  DXGGLOBAL *Global; // rax
  NTSTATUS v7; // eax
  __int64 v8; // rdi
  int v9; // ecx
  int v10; // r8d
  int v11; // eax
  int v12; // ecx
  int v13; // r8d
  VIDMM_PARTITION *v14; // rax
  VIDMM_PARTITION *v15; // rax
  int v17; // ecx
  int v18; // r8d
  HANDLE Handle; // [rsp+50h] [rbp-128h] BYREF
  _QWORD v20[31]; // [rsp+58h] [rbp-120h] BYREF

  Handle = 0;
  Global = DXGGLOBAL::GetGlobal();
  DXGGLOBAL::GetMaximumGlobalAdapterCount(Global);
  memset(v20, 0, sizeof(v20));
  v7 = ObOpenObjectByPointer(a1, 0x200u, 0, 0, PsPartitionType, 0, &Handle);
  v8 = v7;
  if ( v7 >= 0 )
  {
    HIDWORD(v20[0]) = -1;
    LODWORD(v20[1]) = -1;
    v11 = ZwManagePartition(Handle, 0, 0, v20, 248);
    v8 = v11;
    if ( v11 >= 0 )
    {
      *a3 = 0;
      v14 = (VIDMM_PARTITION *)operator new(120, 1647667542, 256);
      if ( v14 )
      {
        v15 = VIDMM_PARTITION::VIDMM_PARTITION(v14, a1, Handle, a2, v20[29], v20[6] << 12);
        if ( v15 )
        {
          _InterlockedIncrement((volatile signed __int32 *)v15 + 25);
          *a3 = v15;
          return 0;
        }
      }
      _InterlockedIncrement(&dword_1400877F0);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 1059;
      DxgkLogInternalTriageEvent(
        v17,
        262145,
        v18,
        (unsigned int)L"Couldn't allocate memory for VIDMM_PARTITION.",
        1059,
        0,
        0,
        0);
      LODWORD(v8) = -1073741801;
    }
    else
    {
      WdLogSingleEntry1(1, v11);
      WdLogGlobalForLineNumber = 1042;
      DxgkLogInternalTriageEvent(
        v12,
        0x40000,
        v13,
        (unsigned int)L"Failed to get partition information from ZwManagePartition. Status=0x%.8x",
        v8,
        0,
        0,
        0);
    }
  }
  else
  {
    WdLogSingleEntry2(1, a1, v7);
    WdLogGlobalForLineNumber = 1010;
    DxgkLogInternalTriageEvent(
      v9,
      0x40000,
      v10,
      (unsigned int)L"Failed to open partition handle, EPartition=0x%p, Status=0x%.8x",
      (__int64)a1,
      v8,
      0,
      0);
  }
  if ( Handle )
    ObCloseHandle(Handle, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400c8db4  mov     [rsp+arg_18], rbx
0x1400c8db9  push    rbp
0x1400c8dba  push    rsi
0x1400c8dbb  push    rdi
0x1400c8dbc  sub     rsp, 160h
0x1400c8dc3  mov     rax, cs:__security_cookie
0x1400c8dca  xor     rax, rsp
0x1400c8dcd  mov     [rsp+178h+var_28], rax
0x1400c8dd5  mov     rbx, r8
0x1400c8dd8  mov     [rsp+178h+var_128], 0
0x1400c8de1  mov     bpl, dl
0x1400c8de4  mov     rsi, rcx
0x1400c8de7  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1400c8dec  mov     rcx, rax; this
0x1400c8def  call    ?GetMaximumGlobalAdapterCount@DXGGLOBAL@@QEBAKXZ; DXGGLOBAL::GetMaximumGlobalAdapterCount(void)
0x1400c8df4  xor     edx, edx; Val
0x1400c8df6  lea     rcx, [rsp+178h+var_120]; void *
0x1400c8dfb  mov     r8d, 0F8h; Size
0x1400c8e01  call    memset
0x1400c8e06  lea     rax, [rsp+178h+var_128]
0x1400c8e0b  xor     r9d, r9d; DesiredAccess
0x1400c8e0e  mov     [rsp+178h+Handle], rax; Handle
0x1400c8e13  xor     r8d, r8d; PassedAccessState
0x1400c8e16  mov     rax, cs:__imp_PsPartitionType
0x1400c8e1d  mov     edx, 200h; HandleAttributes
0x1400c8e22  mov     [rsp+178h+AccessMode], 0; AccessMode
0x1400c8e27  mov     rcx, [rax]
0x1400c8e2a  mov     [rsp+178h+ObjectType], rcx; ObjectType
0x1400c8e2f  mov     rcx, rsi; Object
0x1400c8e32  call    cs:__imp_ObOpenObjectByPointer
0x1400c8e39  nop     dword ptr [rax+rax+00h]
0x1400c8e3e  movsxd  rdi, eax
0x1400c8e41  test    eax, eax
0x1400c8e43  jns     short loc_1400C8E98
0x1400c8e45  mov     r8, rdi
0x1400c8e48  mov     rdx, rsi
0x1400c8e4b  mov     ecx, 1
0x1400c8e50  call    cs:__imp_WdLogSingleEntry2
0x1400c8e57  nop     dword ptr [rax+rax+00h]
0x1400c8e5c  mov     [rsp+178h+var_140], 0
0x1400c8e65  lea     r9, aFailedToOpenPa; "Failed to open partition handle, EParti"...
0x1400c8e6c  mov     [rsp+178h+Handle], 0
0x1400c8e75  mov     qword ptr [rsp+178h+AccessMode], rdi
0x1400c8e7a  mov     [rsp+178h+ObjectType], rsi
0x1400c8e7f  mov     cs:WdLogGlobalForLineNumber, 3F2h
0x1400c8e89  mov     edx, 40000h
0x1400c8e8e  call    DxgkLogInternalTriageEvent
0x1400c8e93  jmp     loc_1400C8FD0
0x1400c8e98  mov     rcx, [rsp+178h+var_128]
0x1400c8e9d  lea     r9, [rsp+178h+var_120]
0x1400c8ea2  or      eax, 0FFFFFFFFh
0x1400c8ea5  mov     dword ptr [rsp+178h+ObjectType], 0F8h
0x1400c8ead  xor     r8d, r8d
0x1400c8eb0  mov     [rsp+178h+var_11C], eax
0x1400c8eb4  xor     edx, edx
0x1400c8eb6  mov     [rsp+178h+var_118], eax
0x1400c8eba  call    cs:__imp_ZwManagePartition
0x1400c8ec1  nop     dword ptr [rax+rax+00h]
0x1400c8ec6  movsxd  rdi, eax
0x1400c8ec9  test    eax, eax
0x1400c8ecb  jns     short loc_1400C8F17
0x1400c8ecd  mov     rdx, rdi
0x1400c8ed0  mov     ecx, 1
0x1400c8ed5  call    cs:__imp_WdLogSingleEntry1
0x1400c8edc  nop     dword ptr [rax+rax+00h]
0x1400c8ee1  mov     [rsp+178h+var_140], 0
0x1400c8eea  lea     r9, aFailedToGetPar; "Failed to get partition information fro"...
0x1400c8ef1  mov     [rsp+178h+Handle], 0
0x1400c8efa  mov     qword ptr [rsp+178h+AccessMode], 0
0x1400c8f03  mov     [rsp+178h+ObjectType], rdi
0x1400c8f08  mov     cs:WdLogGlobalForLineNumber, 412h
0x1400c8f12  jmp     loc_1400C8E89
0x1400c8f17  mov     edx, 62356956h
0x1400c8f1c  mov     qword ptr [rbx], 0
0x1400c8f23  mov     ecx, 78h ; 'x'
0x1400c8f28  mov     r8d, 100h
0x1400c8f2e  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400c8f33  test    rax, rax
0x1400c8f36  jz      short loc_1400C8F77
0x1400c8f38  mov     rcx, [rsp+178h+var_F0]
0x1400c8f40  mov     r9b, bpl; bool
0x1400c8f43  mov     r8, [rsp+178h+var_128]; void *
0x1400c8f48  mov     rdx, rsi; struct _EPARTITION *
0x1400c8f4b  shl     rcx, 0Ch
0x1400c8f4f  mov     qword ptr [rsp+178h+AccessMode], rcx; unsigned __int64
0x1400c8f54  mov     ecx, [rsp+178h+var_38]
0x1400c8f5b  mov     dword ptr [rsp+178h+ObjectType], ecx; unsigned int
0x1400c8f5f  mov     rcx, rax; this
0x1400c8f62  call    ??0VIDMM_PARTITION@@QEAA@PEAU_EPARTITION@@PEAX_NK_K@Z; VIDMM_PARTITION::VIDMM_PARTITION(_EPARTITION *,void *,bool,ulong,unsigned __int64)
0x1400c8f67  test    rax, rax
0x1400c8f6a  jz      short loc_1400C8F77
0x1400c8f6c  lock inc dword ptr [rax+64h]
0x1400c8f70  mov     [rbx], rax
0x1400c8f73  xor     eax, eax
0x1400c8f75  jmp     short loc_1400C8FEA
0x1400c8f77  lock inc cs:dword_1400877F0
0x1400c8f7e  mov     ecx, 6
0x1400c8f83  call    cs:__imp_WdLogSingleEntry0
0x1400c8f8a  nop     dword ptr [rax+rax+00h]
0x1400c8f8f  mov     [rsp+178h+var_140], 0
0x1400c8f98  lea     r9, aCouldnTAllocat_17; "Couldn't allocate memory for VIDMM_PART"...
0x1400c8f9f  mov     eax, 423h
0x1400c8fa4  mov     [rsp+178h+Handle], 0
0x1400c8fad  mov     qword ptr [rsp+178h+AccessMode], 0
0x1400c8fb6  mov     edx, 40001h
0x1400c8fbb  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c8fc1  mov     [rsp+178h+ObjectType], rax
0x1400c8fc6  call    DxgkLogInternalTriageEvent
0x1400c8fcb  mov     edi, 0C0000017h
0x1400c8fd0  mov     rcx, [rsp+178h+var_128]; Handle
0x1400c8fd5  test    rcx, rcx
0x1400c8fd8  jz      short loc_1400C8FE8
0x1400c8fda  xor     edx, edx; PreviousMode
0x1400c8fdc  call    cs:__imp_ObCloseHandle
0x1400c8fe3  nop     dword ptr [rax+rax+00h]
0x1400c8fe8  mov     eax, edi
0x1400c8fea  mov     rcx, [rsp+178h+var_28]
0x1400c8ff2  xor     rcx, rsp; StackCookie
0x1400c8ff5  call    __security_check_cookie
0x1400c8ffa  mov     rbx, [rsp+178h+arg_18]
0x1400c9002  add     rsp, 160h
0x1400c9009  pop     rdi
0x1400c900a  pop     rsi
0x1400c900b  pop     rbp
0x1400c900c  retn
```
