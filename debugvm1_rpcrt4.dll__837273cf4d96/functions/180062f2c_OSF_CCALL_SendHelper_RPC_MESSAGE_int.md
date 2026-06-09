# OSF_CCALL::SendHelper(_RPC_MESSAGE *,int *)

- ea: `0x180062f2c`
- end: `0x1800634b0`
- name: `?SendHelper@OSF_CCALL@@QEAAJPEAU_RPC_MESSAGE@@PEAH@Z`
- size: `1412`
- prototype: `__int64 __fastcall(OSF_CCALL *__hidden this, struct _RPC_MESSAGE *, int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800624f8`

## callees

- `0x1800191d0`
- `0x180021ce0`
- `0x18002b7c0`
- `0x180055f50`
- `0x180061948`
- `0x18006203c`
- `0x1800620fc`
- `0x180062964`
- `0x180062f2c`
- `0x1800634b8`
- `0x180063510`
- `0x1800635d0`
- `0x1800637cc`
- `0x18009ea0c`
- `0x1800a3fd4`
- `0x1800ac7b4`
- `0x1800ad660`
- `0x1800ca031`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18006300e`
- `ntdll!RtlLeaveCriticalSection` at `0x18006311b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800631ab`
- `ntdll!RtlLeaveCriticalSection` at `0x180063241`
- `ntdll!RtlLeaveCriticalSection` at `0x180063286`
- `ntdll!RtlLeaveCriticalSection` at `0x180063324`
- `ntdll!RtlLeaveCriticalSection` at `0x1800633a7`
- `ntdll!RtlLeaveCriticalSection` at `0x18006345e`
- `ntdll!RtlLeaveCriticalSection` at `0x18006300e`
- `ntdll!RtlLeaveCriticalSection` at `0x18006311b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800631ab`
- `ntdll!RtlLeaveCriticalSection` at `0x180063241`
- `ntdll!RtlLeaveCriticalSection` at `0x180063286`
- `ntdll!RtlLeaveCriticalSection` at `0x180063324`
- `ntdll!RtlLeaveCriticalSection` at `0x1800633a7`
- `ntdll!RtlLeaveCriticalSection` at `0x18006345e`
- `ntdll!RtlEnterCriticalSection` at `0x180062fb5`
- `ntdll!RtlEnterCriticalSection` at `0x180063057`
- `ntdll!RtlEnterCriticalSection` at `0x1800632f5`
- `ntdll!RtlEnterCriticalSection` at `0x180062fb5`
- `ntdll!RtlEnterCriticalSection` at `0x180063057`
- `ntdll!RtlEnterCriticalSection` at `0x1800632f5`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800632bd`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800632bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800632b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800632b5`

## pseudocode

```c
__int64 __fastcall OSF_CCALL::SendHelper(OSF_CCALL *this, struct _RPC_MESSAGE *a2, int *a3)
{
  int v3; // r12d
  _QWORD *v7; // r15
  struct _RTL_CRITICAL_SECTION *v8; // rbp
  size_t v9; // r14
  unsigned int v10; // ebx
  void *Buffer; // r15
  unsigned int BufferLength; // r12d
  unsigned int v13; // eax
  OSF_CCALL **v14; // rcx
  int v15; // eax
  unsigned int v16; // eax
  int v17; // ecx
  struct _RTL_CRITICAL_SECTION *v18; // rcx
  __int64 result; // rax
  __int64 v20; // rbp
  int v21; // ebp
  int v22; // edx
  char *v23; // rbx
  DWORD CurrentProcessId; // edi
  unsigned int CommandLineW; // eax
  int v26; // ebx
  int v27; // eax
  _DWORD *v28; // rbx
  unsigned int v29; // r14d
  signed int v30; // edx
  unsigned int BufferDo; // eax
  int v32; // [rsp+28h] [rbp-60h]
  int v33; // [rsp+30h] [rbp-58h]
  void *v34; // [rsp+A0h] [rbp+18h] BYREF
  void *v35; // [rsp+A8h] [rbp+20h]

  v3 = 0;
  v34 = 0;
  *a3 = 0;
  if ( !*((_DWORD *)this + 127) )
    *((_DWORD *)this + 127) = a2->BufferLength;
  v7 = (_QWORD *)((char *)this + 24);
  if ( (a2->RpcFlags & 0x2000) == 0 )
  {
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 464);
    *((_QWORD *)this + 52) = a2->Buffer;
    LODWORD(v9) = 0;
    v10 = 0;
    goto LABEL_5;
  }
  if ( !*v7 && *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 34) + 408LL) + 256LL) )
  {
    if ( !(unsigned int)ShouldSkipLogging(2u) && (Microsoft_Windows_RPC_EventsEnableBits & 1) != 0 )
    {
      v23 = (char *)a2->RpcInterfaceInformation + 4;
      CurrentProcessId = GetCurrentProcessId();
      CommandLineW = (unsigned int)GetCommandLineW();
      McTemplateU0zdzj_EtwEventWriteTransfer(
        (unsigned int)L"ncacn_http",
        (unsigned int)RPC_EVENTLOG_SYNC_PIPE_USE_ERR,
        CommandLineW,
        CurrentProcessId,
        (__int64)L"ncacn_http",
        (__int64)v23);
    }
    v10 = 1764;
    v22 = 1764;
    goto LABEL_47;
  }
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 464);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 464));
  if ( *v7 || *((_DWORD *)this + 80) )
  {
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 464));
  }
  else
  {
    v26 = *((_DWORD *)this + 66);
    *((_DWORD *)this + 153) = 1;
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 464));
    if ( v26 == 2 )
    {
      REFERENCED_OBJECT::AddReference(this);
      v27 = OSF_CCONNECTION::AddCall(*((OSF_CCONNECTION **)this + 34), this);
      v28 = (_DWORD *)*((_QWORD *)this + 34);
      v29 = v27;
      LogEvent(0x6Eu, 0x63u, v28, 0, 0, v32, v33);
      v28[26] = 0;
      if ( v29 || (v29 = OSF_CCALL::SendAlterContextPDU(this)) != 0 )
      {
        (*(void (__fastcall **)(OSF_CCALL *))(*(_QWORD *)this + 32LL))(this);
        return v29;
      }
    }
    EVENT::Wait((OSF_CCALL *)((char *)this + 424), -1);
  }
  result = OSF_CCALL::CheckPipeSendForIncompleteBuffer(this, a2);
  v10 = result;
  if ( !(_DWORD)result )
  {
    v30 = a2->BufferLength % *((_DWORD *)this + 90);
    v9 = v30;
    if ( v30 )
    {
      BufferDo = OSF_CCALL::GetBufferDo(this, v30, &v34);
      v10 = BufferDo;
      if ( BufferDo )
      {
        v22 = BufferDo;
LABEL_47:
        OSF_CCALL::CallFailed(this, v22, 0, 0);
        OSF_CCALL::UnregisterCallForCancels(this);
        return v10;
      }
      a2->BufferLength -= v9;
      memcpy_0(v34, (char *)a2->Buffer + a2->BufferLength, v9);
    }
LABEL_5:
    v35 = 0;
    REFERENCED_OBJECT::AddReference(this);
    while ( 1 )
    {
      if ( *((_DWORD *)this + 8) != 997 )
      {
        v10 = *((_DWORD *)this + 8);
        if ( v10 == 1727 )
        {
          if ( v3 )
            v10 = 1726;
        }
        else if ( ((v10 + 1073606648) & 0xFFFFFFF5) == 0 && v10 != -1073606640 || v10 == 1726 && !v3 )
        {
          v10 = 1727;
        }
        if ( *(OSF_CCALL **)(*((_QWORD *)this + 34) + 32LL) != this )
          REFERENCED_OBJECT::RemoveReference(this);
LABEL_20:
        Buffer = v35;
        BufferLength = (unsigned int)v35;
        goto LABEL_21;
      }
      RtlEnterCriticalSection(v8);
      if ( !*((_QWORD *)this + 39) )
        break;
      if ( *v7 || *((int *)this + 135) < 4 )
      {
        if ( (unsigned int)QUEUE::PutOnQueue((OSF_CCALL *)((char *)this + 528), a2->Buffer, a2->BufferLength) )
        {
          v10 = 14;
          if ( *(OSF_CCALL **)(*((_QWORD *)this + 34) + 32LL) != this )
            REFERENCED_OBJECT::RemoveReference(this);
        }
        else
        {
          a2->Buffer = 0;
          a2->BufferLength = 0;
        }
        RtlLeaveCriticalSection(v8);
        goto LABEL_20;
      }
      v3 = 1;
      *((_DWORD *)this + 153) = 1;
      RtlLeaveCriticalSection(v8);
      EVENT::Wait((OSF_CCALL *)((char *)this + 424), -1);
    }
    *((_DWORD *)this + 81) = 0;
    *((_QWORD *)this + 39) = a2->Buffer;
    *((_DWORD *)this + 82) = a2->BufferLength;
    Buffer = a2->Buffer;
    BufferLength = a2->BufferLength;
    a2->Buffer = 0;
    a2->BufferLength = 0;
    if ( !*((_DWORD *)this + 85) )
    {
      RtlLeaveCriticalSection(v8);
      goto LABEL_11;
    }
    ++*((_DWORD *)this + 128);
    *((_DWORD *)this + 85) = 0;
    RtlLeaveCriticalSection(v8);
    v13 = OSF_CCALL::RegisterCallForCancels(this);
    v14 = (OSF_CCALL **)*((_QWORD *)this + 34);
    v10 = v13;
    if ( !v13 )
    {
      v15 = OSF_CCONNECTION::AddCall((OSF_CCONNECTION *)v14, this);
      *a3 = 1;
      v10 = v15;
      if ( v15 )
      {
        if ( *(OSF_CCALL **)(*((_QWORD *)this + 34) + 32LL) != this )
          goto LABEL_40;
        goto LABEL_41;
      }
LABEL_11:
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)this + 34) + 216LL));
      v16 = *((_DWORD *)this + 66);
      if ( v16 <= 0xC )
      {
        v17 = 6720;
        if ( _bittest(&v17, v16) )
        {
          v18 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)this + 34) + 216LL);
          goto LABEL_29;
        }
      }
      v20 = *((_QWORD *)this + 34);
      if ( *(OSF_CCALL **)(v20 + 32) == this && *(_DWORD *)(v20 + 104) )
      {
        LogEvent(0x6Eu, 0x63u, (void *)v20, 0, 0, v32, v33);
        *(_DWORD *)(v20 + 104) = 0;
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)this + 34) + 216LL));
        v10 = OSF_CCALL::SendData(this, 0);
        if ( !v10 )
        {
LABEL_22:
          if ( (_DWORD)v9 )
          {
            v10 = 1913;
            a2->Buffer = v34;
            a2->BufferLength = v9;
            *((_DWORD *)this + 108) = v9;
          }
          else
          {
            *((_DWORD *)this + 108) = 0;
          }
          goto LABEL_24;
        }
LABEL_40:
        REFERENCED_OBJECT::RemoveReference(this);
LABEL_41:
        v21 = 0;
        goto LABEL_33;
      }
      v18 = (struct _RTL_CRITICAL_SECTION *)(v20 + 216);
LABEL_29:
      RtlLeaveCriticalSection(v18);
LABEL_21:
      if ( !v10 )
        goto LABEL_22;
      goto LABEL_41;
    }
    v21 = 1;
    if ( v14[4] != this )
      REFERENCED_OBJECT::RemoveReference(this);
LABEL_33:
    if ( (_DWORD)v9 )
      OSF_CCALL::FreeBufferDo(this, v34);
    *((_DWORD *)this + 8) = v10;
    if ( !v21 )
      OSF_CCALL::UnregisterCallForCancels(this);
    if ( Buffer )
    {
      a2->Buffer = Buffer;
      a2->BufferLength = BufferLength;
    }
LABEL_24:
    REFERENCED_OBJECT::RemoveReference(this);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x180062f2c  mov     rax, rsp
0x180062f2f  push    rbx
0x180062f30  push    rbp
0x180062f31  push    rsi
0x180062f32  push    rdi
0x180062f33  push    r12
0x180062f35  push    r13
0x180062f37  push    r14
0x180062f39  push    r15
0x180062f3b  sub     rsp, 48h
0x180062f3f  xor     r12d, r12d
0x180062f42  mov     r13, r8
0x180062f45  mov     rdi, rdx
0x180062f48  mov     rsi, rcx
0x180062f4b  mov     [rax+18h], r12
0x180062f4f  mov     [r8], r12d
0x180062f52  cmp     [rcx+1FCh], r12d
0x180062f59  jnz     short loc_180062F64
0x180062f5b  mov     eax, [rdx+18h]
0x180062f5e  mov     [rcx+1FCh], eax
0x180062f64  test    dword ptr [rdx+48h], 2000h
0x180062f6b  lea     r15, [rcx+18h]
0x180062f6f  jnz     loc_1800631B6
0x180062f75  mov     rax, [rdx+10h]
0x180062f79  lea     rbp, [rcx+1D0h]
0x180062f80  mov     [rcx+1A0h], rax
0x180062f87  mov     r14d, r12d
0x180062f8a  mov     ebx, r12d
0x180062f8d  mov     rcx, rsi; this
0x180062f90  mov     [rsp+88h+arg_0], r12d
0x180062f98  mov     [rsp+88h+arg_18], r12
0x180062fa0  call    ?AddReference@REFERENCED_OBJECT@@QEAAHXZ; REFERENCED_OBJECT::AddReference(void)
0x180062fa5  cmp     dword ptr [rsi+20h], 3E5h
0x180062fac  jnz     loc_180063089
0x180062fb2  mov     rcx, rbp; CriticalSection
0x180062fb5  call    cs:__imp_RtlEnterCriticalSection
0x180062fbb  xor     ecx, ecx
0x180062fbd  cmp     [rsi+138h], rcx
0x180062fc4  jnz     loc_180063260
0x180062fca  mov     [rsi+144h], ecx
0x180062fd0  mov     rax, [rdi+10h]
0x180062fd4  mov     [rsi+138h], rax
0x180062fdb  mov     eax, [rdi+18h]
0x180062fde  mov     [rsi+148h], eax
0x180062fe4  mov     r15, [rdi+10h]
0x180062fe8  mov     r12d, [rdi+18h]
0x180062fec  mov     [rdi+10h], rcx
0x180062ff0  mov     [rdi+18h], ecx
0x180062ff3  cmp     [rsi+154h], ecx
0x180062ff9  jz      loc_1800631A8
0x180062fff  inc     dword ptr [rsi+200h]
0x180063005  mov     [rsi+154h], ecx
0x18006300b  mov     rcx, rbp; CriticalSection
0x18006300e  call    cs:__imp_RtlLeaveCriticalSection
0x180063014  mov     rcx, rsi; this
0x180063017  call    ?RegisterCallForCancels@OSF_CCALL@@AEAAJXZ; OSF_CCALL::RegisterCallForCancels(void)
0x18006301c  mov     rcx, [rsi+110h]; this
0x180063023  mov     ebx, eax
0x180063025  test    eax, eax
0x180063027  jnz     loc_180063141
0x18006302d  mov     rdx, rsi; struct OSF_CCALL *
0x180063030  call    ?AddCall@OSF_CCONNECTION@@QEAAJPEAVOSF_CCALL@@@Z; OSF_CCONNECTION::AddCall(OSF_CCALL *)
0x180063035  mov     dword ptr [r13+0], 1
0x18006303d  mov     ebx, eax
0x18006303f  test    eax, eax
0x180063041  jnz     loc_18006318A
0x180063047  mov     rcx, [rsi+110h]
0x18006304e  mov     r13d, 0D8h
0x180063054  add     rcx, r13; CriticalSection
0x180063057  call    cs:__imp_RtlEnterCriticalSection
0x18006305d  mov     eax, [rsi+108h]
0x180063063  cmp     eax, 0Ch
0x180063066  ja      loc_180063103
0x18006306c  mov     ecx, 1A40h
0x180063071  bt      ecx, eax
0x180063074  jnb     loc_180063103
0x18006307a  mov     rcx, [rsi+110h]
0x180063081  add     rcx, r13
0x180063084  jmp     loc_18006311B
0x180063089  mov     ebx, [rsi+20h]
0x18006308c  mov     ecx, 6BFh
0x180063091  cmp     ebx, ecx
0x180063093  jz      loc_180063476
0x180063099  lea     eax, [rbx+3FFDEFF8h]
0x18006309f  test    eax, 0FFFFFFF5h
0x1800630a4  jnz     loc_180063489
0x1800630aa  cmp     ebx, 0C0021010h
0x1800630b0  jz      loc_180063489
0x1800630b6  mov     ebx, ecx
0x1800630b8  mov     rax, [rsi+110h]
0x1800630bf  cmp     [rax+20h], rsi
0x1800630c3  jnz     loc_1800634A3
0x1800630c9  mov     r15, [rsp+88h+arg_18]
0x1800630d1  mov     r12d, r15d
0x1800630d4  test    ebx, ebx
0x1800630d6  jnz     loc_18006319F
0x1800630dc  test    r14d, r14d
0x1800630df  jnz     short loc_180063123
0x1800630e1  mov     [rsi+1B0h], r14d
0x1800630e8  mov     rcx, rsi; this
0x1800630eb  call    ?RemoveReference@REFERENCED_OBJECT@@UEAAXXZ; REFERENCED_OBJECT::RemoveReference(void)
0x1800630f0  mov     eax, ebx
0x1800630f2  add     rsp, 48h
0x1800630f6  pop     r15
0x1800630f8  pop     r14
0x1800630fa  pop     r13
0x1800630fc  pop     r12
0x1800630fe  pop     rdi
0x1800630ff  pop     rsi
0x180063100  pop     rbp
0x180063101  pop     rbx
0x180063102  retn
0x180063103  mov     rbp, [rsi+110h]
0x18006310a  cmp     [rbp+20h], rsi
0x18006310e  jz      loc_18006320E
0x180063114  lea     rcx, [rbp+0D8h]; CriticalSection
0x18006311b  call    cs:__imp_RtlLeaveCriticalSection
0x180063121  jmp     short loc_1800630D4
0x180063123  mov     rax, [rsp+88h+arg_10]
0x18006312b  mov     ebx, 779h
0x180063130  mov     [rdi+10h], rax
0x180063134  mov     [rdi+18h], r14d
0x180063138  mov     [rsi+1B0h], r14d
0x18006313f  jmp     short loc_1800630E8
0x180063141  mov     ebp, 1
0x180063146  cmp     [rcx+20h], rsi
0x18006314a  jnz     loc_180063469
0x180063150  test    r14d, r14d
0x180063153  jz      short loc_180063165
0x180063155  mov     rdx, [rsp+88h+arg_10]; void *
0x18006315d  mov     rcx, rsi; this
0x180063160  call    ?FreeBufferDo@OSF_CCALL@@QEAAXPEAX@Z; OSF_CCALL::FreeBufferDo(void *)
0x180063165  mov     [rsi+20h], ebx
0x180063168  test    ebp, ebp
0x18006316a  jnz     short loc_180063174
0x18006316c  mov     rcx, rsi; this
0x18006316f  call    ?UnregisterCallForCancels@OSF_CCALL@@AEAAXXZ; OSF_CCALL::UnregisterCallForCancels(void)
0x180063174  test    r15, r15
0x180063177  jz      loc_1800630E8
0x18006317d  mov     [rdi+10h], r15
0x180063181  mov     [rdi+18h], r12d
0x180063185  jmp     loc_1800630E8
0x18006318a  mov     rax, [rsi+110h]
0x180063191  cmp     [rax+20h], rsi
0x180063195  jz      short loc_18006319F
0x180063197  mov     rcx, rsi; this
0x18006319a  call    ?RemoveReference@REFERENCED_OBJECT@@UEAAXXZ; REFERENCED_OBJECT::RemoveReference(void)
0x18006319f  mov     ebp, [rsp+88h+arg_0]
0x1800631a6  jmp     short loc_180063150
0x1800631a8  mov     rcx, rbp; CriticalSection
0x1800631ab  call    cs:__imp_RtlLeaveCriticalSection
0x1800631b1  jmp     loc_180063047
0x1800631b6  cmp     [r15], r12
0x1800631b9  jnz     loc_1800632EB
0x1800631bf  mov     rax, [rcx+110h]
0x1800631c6  mov     rcx, [rax+198h]
0x1800631cd  cmp     [rcx+100h], r12
0x1800631d4  jz      loc_1800632EB
0x1800631da  mov     ecx, 2; unsigned int
0x1800631df  call    ?ShouldSkipLogging@@YAHK@Z; ShouldSkipLogging(ulong)
0x1800631e4  test    eax, eax
0x1800631e6  jz      loc_1800632A0
0x1800631ec  mov     ebx, 6E4h
0x1800631f1  mov     edx, ebx; int
0x1800631f3  xor     r9d, r9d; int
0x1800631f6  xor     r8d, r8d; int
0x1800631f9  mov     rcx, rsi; this
0x1800631fc  call    ?CallFailed@OSF_CCALL@@AEAAXJHH@Z; OSF_CCALL::CallFailed(long,int,int)
0x180063201  mov     rcx, rsi; this
0x180063204  call    ?UnregisterCallForCancels@OSF_CCALL@@AEAAXXZ; OSF_CCALL::UnregisterCallForCancels(void)
0x180063209  jmp     loc_1800630F0
0x18006320e  cmp     dword ptr [rbp+68h], 0
0x180063212  jz      loc_180063114
0x180063218  xor     r9d, r9d; void *
0x18006321b  mov     [rsp+88h+var_68], 0; unsigned __int64
0x180063224  mov     r8, rbp; void *
0x180063227  mov     dl, 63h ; 'c'; unsigned __int8
0x180063229  mov     cl, 6Eh ; 'n'; unsigned __int8
0x18006322b  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180063230  mov     dword ptr [rbp+68h], 0
0x180063237  mov     rcx, [rsi+110h]
0x18006323e  add     rcx, r13; CriticalSection
0x180063241  call    cs:__imp_RtlLeaveCriticalSection
0x180063247  xor     edx, edx; unsigned __int8 *
0x180063249  mov     rcx, rsi; this
0x18006324c  call    ?SendData@OSF_CCALL@@QEAAJPEAE@Z; OSF_CCALL::SendData(uchar *)
0x180063251  mov     ebx, eax
0x180063253  test    eax, eax
0x180063255  jnz     loc_180063197
0x18006325b  jmp     loc_1800630DC
0x180063260  cmp     [r15], rcx
0x180063263  jnz     loc_180063418
0x180063269  cmp     dword ptr [rsi+21Ch], 4
0x180063270  jl      loc_180063418
0x180063276  mov     r12d, 1
0x18006327c  mov     rcx, rbp; CriticalSection
0x18006327f  mov     [rsi+264h], r12d
0x180063286  call    cs:__imp_RtlLeaveCriticalSection
0x18006328c  lea     rcx, [rsi+1A8h]; this
0x180063293  or      edx, 0FFFFFFFFh; int
0x180063296  call    ?Wait@EVENT@@QEAAHJ@Z; EVENT::Wait(long)
0x18006329b  jmp     loc_180062FA5
0x1800632a0  test    cs:Microsoft_Windows_RPC_EventsEnableBits, 1
0x1800632a7  jz      loc_1800631EC
0x1800632ad  mov     rbx, [rdi+28h]
0x1800632b1  add     rbx, 4
0x1800632b5  call    cs:__imp_GetCurrentProcessId
0x1800632bb  mov     edi, eax
0x1800632bd  call    cs:__imp_GetCommandLineW
0x1800632c3  lea     rcx, aNcacnHttp; "ncacn_http"
0x1800632ca  mov     [rsp+88h+var_60], rbx
0x1800632cf  mov     r8, rax
0x1800632d2  mov     [rsp+88h+var_68], rcx
0x1800632d7  mov     r9d, edi
0x1800632da  lea     rdx, RPC_EVENTLOG_SYNC_PIPE_USE_ERR
0x1800632e1  call    McTemplateU0zdzj_EtwEventWriteTransfer
0x1800632e6  jmp     loc_1800631EC
0x1800632eb  lea     rbp, [rsi+1D0h]
0x1800632f2  mov     rcx, rbp; CriticalSection
0x1800632f5  call    cs:__imp_RtlEnterCriticalSection
0x1800632fb  cmp     [r15], r12
0x1800632fe  jnz     loc_1800633A4
0x180063304  cmp     [rsi+140h], r12d
0x18006330b  jnz     loc_1800633A4
0x180063311  mov     ebx, [rsi+108h]
0x180063317  mov     rcx, rbp; CriticalSection
0x18006331a  mov     dword ptr [rsi+264h], 1
0x180063324  call    cs:__imp_RtlLeaveCriticalSection
0x18006332a  cmp     ebx, 2
0x18006332d  jnz     short loc_180063393
0x18006332f  mov     rcx, rsi; this
0x180063332  call    ?AddReference@REFERENCED_OBJECT@@QEAAHXZ; REFERENCED_OBJECT::AddReference(void)
0x180063337  mov     rcx, [rsi+110h]; this
0x18006333e  mov     rdx, rsi; struct OSF_CCALL *
0x180063341  call    ?AddCall@OSF_CCONNECTION@@QEAAJPEAVOSF_CCALL@@@Z; OSF_CCONNECTION::AddCall(OSF_CCALL *)
0x180063346  mov     rbx, [rsi+110h]
0x18006334d  xor     r9d, r9d; void *
0x180063350  mov     r8, rbx; void *
0x180063353  mov     [rsp+88h+var_68], r12; unsigned __int64
0x180063358  mov     dl, 63h ; 'c'; unsigned __int8
0x18006335a  mov     cl, 6Eh ; 'n'; unsigned __int8
0x18006335c  mov     r14d, eax
0x18006335f  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180063364  mov     [rbx+68h], r12d
0x180063368  test    r14d, r14d
0x18006336b  jnz     short loc_18006337C
0x18006336d  mov     rcx, rsi; this
0x180063370  call    ?SendAlterContextPDU@OSF_CCALL@@AEAAJXZ; OSF_CCALL::SendAlterContextPDU(void)
0x180063375  mov     r14d, eax
0x180063378  test    eax, eax
0x18006337a  jz      short loc_180063393
0x18006337c  mov     rax, [rsi]
0x18006337f  mov     rcx, rsi
0x180063382  mov     rax, [rax+20h]
0x180063386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006338b  mov     eax, r14d
0x18006338e  jmp     loc_1800630F2
0x180063393  lea     rcx, [rsi+1A8h]; this
0x18006339a  or      edx, 0FFFFFFFFh; int
0x18006339d  call    ?Wait@EVENT@@QEAAHJ@Z; EVENT::Wait(long)
0x1800633a2  jmp     short loc_1800633AD
0x1800633a4  mov     rcx, rbp; CriticalSection
0x1800633a7  call    cs:__imp_RtlLeaveCriticalSection
0x1800633ad  mov     rdx, rdi; struct _RPC_MESSAGE *
0x1800633b0  mov     rcx, rsi; this
0x1800633b3  call    ?CheckPipeSendForIncompleteBuffer@OSF_CCALL@@QEAAJPEAU_RPC_MESSAGE@@@Z; OSF_CCALL::CheckPipeSendForIncompleteBuffer(_RPC_MESSAGE *)
0x1800633b8  mov     ebx, eax
0x1800633ba  test    eax, eax
0x1800633bc  jnz     loc_1800630F2
0x1800633c2  mov     eax, [rdi+18h]
0x1800633c5  xor     edx, edx
0x1800633c7  div     dword ptr [rsi+168h]
0x1800633cd  movsxd  r14, edx
0x1800633d0  test    edx, edx
0x1800633d2  jz      loc_180062F8D
0x1800633d8  lea     r8, [rsp+88h+arg_10]; void **
0x1800633e0  mov     edx, r14d; unsigned int
0x1800633e3  mov     rcx, rsi; this
0x1800633e6  call    ?GetBufferDo@OSF_CCALL@@QEAAJIPEAPEAX@Z; OSF_CCALL::GetBufferDo(uint,void * *)
0x1800633eb  mov     ebx, eax
0x1800633ed  test    eax, eax
0x1800633ef  jz      short loc_1800633F8
0x1800633f1  mov     edx, eax
0x1800633f3  jmp     loc_1800631F3
0x1800633f8  sub     [rdi+18h], r14d
0x1800633fc  mov     r8, r14; Size
0x1800633ff  mov     edx, [rdi+18h]
0x180063402  add     rdx, [rdi+10h]; Src
0x180063406  mov     rcx, [rsp+88h+arg_10]; void *
0x18006340e  call    memcpy_0
0x180063413  jmp     loc_180062F8D
0x180063418  mov     r8d, [rdi+18h]; unsigned int
0x18006341c  lea     rcx, [rsi+210h]; this
0x180063423  mov     rdx, [rdi+10h]; void *
0x180063427  call    ?PutOnQueue@QUEUE@@QEAAHPEAXI@Z; QUEUE::PutOnQueue(void *,uint)
0x18006342c  test    eax, eax
0x18006342e  jz      short loc_18006344C
0x180063430  mov     rax, [rsi+110h]
0x180063437  mov     ebx, 0Eh
0x18006343c  cmp     [rax+20h], rsi
  ... truncated ...
```
