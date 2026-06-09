# SyncOpenUNCPathForPinAndFill

- ea: `0x180031d38`
- end: `0x180032033`
- name: `SyncOpenUNCPathForPinAndFill`
- size: `763`
- prototype: `__int64 __usercall@<rax>(PHANDLE FileHandle@<rcx>, ULONG, int, __int64, char, int, char)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180002540`
- `0x18007ab30`

## callees

- `0x1800023f0`
- `0x1800068b0`
- `0x1800223c0`
- `0x180031d38`
- `0x1800360c0`
- `0x180036394`
- `0x18003c4e8`
- `0x1800469c0`
- `0x18005fa04`
- `0x180073e1c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180031e88`
- `ntdll!RtlInitUnicodeString` at `0x180031e88`

## string_xrefs

- `0x180031d8c`: `SyncOpenUNCPathForPinAndFill: Handle: 0x%p UNCPath: 0x%p DesiredAccess: 0x%x`
- `0x180031dd6`: `SyncOpenUNCPathForPinAndFill: ShareAccess: 0x%x CreateOptions: 0x%x SyncOpenFlags: 0x%x`
- `0x180031e50`: `: Invalid SyncOpenFlags %x`
- `0x180031f0d`: `SyncOpenUNCPathForPinAndFill: CscDriverOpenItem failed for '%ws' with %x`
- `0x180031f4e`: `SyncOpenUNCPathForPinAndFill: SyncHandleIsDisconnected failed for '%ws' with %x`
- `0x180031fe0`: `SyncOpenUNCPathForPinAndFill: Handle = %p, Disconnected = %c, status = 0x%08x`

## pseudocode

```c
__int64 __fastcall SyncOpenUNCPathForPinAndFill(
        PHANDLE FileHandle,
        __int64 a2,
        const WCHAR *a3,
        int a4,
        ULONG a5,
        int a6,
        _BYTE *a7,
        char a8,
        unsigned int a9)
{
  CObjectMonitor *v12; // rax
  unsigned int IsDisconnected; // ebx
  CObjectMonitor *v14; // rax
  int v15; // edx
  int v16; // edi
  __int64 v17; // r8
  __int64 v18; // r8
  int v20; // [rsp+20h] [rbp-68h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF

  DestinationString = 0;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncOpenUNCPathForPinAndFill: Handle: 0x%p UNCPath: 0x%p DesiredAccess: 0x%x",
        FileHandle);
      WPP_SF_qqD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        25,
        WPP_f707efbc203434f979e24425cc714701_Traceguids,
        FileHandle,
        a3,
        a4);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v12 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncOpenUNCPathForPinAndFill: ShareAccess: 0x%x CreateOptions: 0x%x SyncOpenFlags: 0x%x",
        a5,
        2056,
        a9);
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        26,
        WPP_f707efbc203434f979e24425cc714701_Traceguids,
        a5,
        2056,
        a9);
    }
  }
  *FileHandle = 0;
  if ( a7 )
    *a7 = 0;
  if ( (a9 & 0xFFFFFFF8) == 0 )
  {
    RtlInitUnicodeString(&DestinationString, a3);
    IsDisconnected = CscDriverOpenItemWithDispositionEx(FileHandle, a4, a5, 1u, 2056);
    if ( IsDisconnected )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_24;
      }
      SyncTraceOutputInternal(
        L"SyncOpenUNCPathForPinAndFill: CscDriverOpenItem failed for '%ws' with %x",
        a3,
        IsDisconnected);
      v15 = 28;
    }
    else
    {
      if ( !a7 )
        goto LABEL_23;
      IsDisconnected = SyncHandleIsDisconnected(*FileHandle, a7);
      if ( !IsDisconnected )
        goto LABEL_23;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_24;
      }
      SyncTraceOutputInternal(
        L"SyncOpenUNCPathForPinAndFill: SyncHandleIsDisconnected failed for '%ws' with %x",
        a3,
        IsDisconnected);
      v15 = 29;
    }
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      v15,
      (unsigned int)WPP_f707efbc203434f979e24425cc714701_Traceguids,
      (_DWORD)a3,
      IsDisconnected);
    goto LABEL_23;
  }
  IsDisconnected = -1073741811;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    SyncTraceOutputInternal(L": Invalid SyncOpenFlags %x", a9);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 27, WPP_f707efbc203434f979e24425cc714701_Traceguids, a9);
LABEL_23:
    v14 = WPP_GLOBAL_Control;
  }
LABEL_24:
  if ( *FileHandle )
    ++OpenedHandles;
  if ( IsDisconnected && *FileHandle )
  {
    SyncCloseFile(*FileHandle);
    *FileHandle = 0;
    v14 = WPP_GLOBAL_Control;
  }
  if ( v14 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 108) & 8) != 0 )
  {
    LOBYTE(v16) = 63;
    if ( a7 )
      v17 = *a7 != 0 ? 89 : 78;
    else
      v17 = 63;
    SyncTraceOutputInternal(
      L"SyncOpenUNCPathForPinAndFill: Handle = %p, Disconnected = %c, status = 0x%08x",
      *FileHandle,
      v17,
      IsDisconnected);
    if ( a7 )
      v16 = *a7 != 0 ? 89 : 78;
    LOBYTE(v20) = v16;
    WPP_SF_qcD(*((_QWORD *)WPP_GLOBAL_Control + 12), 30, v18, *FileHandle, v20, IsDisconnected);
  }
  return IsDisconnected;
}

```

## disassembly

```asm
0x180031d38  push    rbx
0x180031d3a  push    rbp
0x180031d3b  push    rsi
0x180031d3c  push    rdi
0x180031d3d  push    r13
0x180031d3f  push    r14
0x180031d41  push    r15
0x180031d43  sub     rsp, 50h
0x180031d47  xorps   xmm0, xmm0
0x180031d4a  mov     r15d, r9d
0x180031d4d  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x180031d52  mov     rbp, r8
0x180031d55  mov     rsi, rcx
0x180031d58  mov     rax, cs:WPP_GLOBAL_Control
0x180031d5f  lea     r13, WPP_GLOBAL_Control
0x180031d66  mov     edi, [rsp+88h+arg_40]
0x180031d6d  mov     r14d, 808h
0x180031d73  mov     ebx, [rsp+88h+arg_20]
0x180031d7a  cmp     rax, r13
0x180031d7d  jz      loc_180031E0F
0x180031d83  test    byte ptr [rax+6Ch], 4
0x180031d87  jz      short loc_180031DC8
0x180031d89  mov     rdx, rcx
0x180031d8c  lea     rcx, aSyncopenuncpat; "SyncOpenUNCPathForPinAndFill: Handle: 0"...
0x180031d93  call    SyncTraceOutputInternal
0x180031d98  mov     rcx, cs:WPP_GLOBAL_Control
0x180031d9f  lea     r8, WPP_f707efbc203434f979e24425cc714701_Traceguids
0x180031da6  mov     edx, 19h
0x180031dab  mov     [rsp+88h+var_60], r15d
0x180031db0  mov     r9, rsi
0x180031db3  mov     qword ptr [rsp+88h+var_68], rbp
0x180031db8  mov     rcx, [rcx+60h]
0x180031dbc  call    WPP_SF_qqD
0x180031dc1  mov     rax, cs:WPP_GLOBAL_Control
0x180031dc8  cmp     rax, r13
0x180031dcb  jz      short loc_180031E0F
0x180031dcd  test    byte ptr [rax+6Ch], 4
0x180031dd1  jz      short loc_180031E0F
0x180031dd3  mov     r9d, edi
0x180031dd6  lea     rcx, aSyncopenuncpat_5; "SyncOpenUNCPathForPinAndFill: ShareAcce"...
0x180031ddd  mov     r8d, r14d
0x180031de0  mov     edx, ebx
0x180031de2  call    SyncTraceOutputInternal
0x180031de7  mov     rcx, cs:WPP_GLOBAL_Control
0x180031dee  lea     r8, WPP_f707efbc203434f979e24425cc714701_Traceguids
0x180031df5  mov     edx, 1Ah
0x180031dfa  mov     [rsp+88h+var_60], edi
0x180031dfe  mov     r9d, ebx
0x180031e01  mov     [rsp+88h+var_68], r14d
0x180031e06  mov     rcx, [rcx+60h]
0x180031e0a  call    WPP_SF_DDD
0x180031e0f  mov     r14, [rsp+88h+arg_30]
0x180031e17  mov     qword ptr [rsi], 0
0x180031e1e  test    r14, r14
0x180031e21  jz      short loc_180031E27
0x180031e23  mov     byte ptr [r14], 0
0x180031e27  test    edi, 0FFFFFFF8h
0x180031e2d  jz      short loc_180031E80
0x180031e2f  mov     ebx, 0C000000Dh
0x180031e34  mov     rax, cs:WPP_GLOBAL_Control
0x180031e3b  cmp     rax, r13
0x180031e3e  jz      loc_180031F87
0x180031e44  test    byte ptr [rax+6Ch], 1
0x180031e48  jz      loc_180031F87
0x180031e4e  mov     edx, edi
0x180031e50  lea     rcx, aInvalidSyncope; ": Invalid SyncOpenFlags %x"
0x180031e57  call    SyncTraceOutputInternal
0x180031e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e63  lea     r8, WPP_f707efbc203434f979e24425cc714701_Traceguids
0x180031e6a  mov     edx, 1Bh
0x180031e6f  mov     r9d, edi
0x180031e72  mov     rcx, [rcx+60h]
0x180031e76  call    WPP_SF_d
0x180031e7b  jmp     loc_180031F80
0x180031e80  mov     rdx, rbp; SourceString
0x180031e83  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x180031e88  call    cs:__imp_RtlInitUnicodeString
0x180031e8e  and     dil, 1
0x180031e92  mov     [rsp+88h+var_50], 808h; int
0x180031e9a  neg     dil
0x180031e9d  mov     [rsp+88h+var_58], 1; ULONG
0x180031ea5  mov     [rsp+88h+var_60], ebx; ULONG
0x180031ea9  lea     r8, [rsp+88h+DestinationString]
0x180031eae  sbb     eax, eax
0x180031eb0  mov     [rsp+88h+var_68], r15d; int
0x180031eb5  and     eax, 3000h
0x180031eba  add     eax, 4000h
0x180031ebf  mov     ecx, eax
0x180031ec1  bts     ecx, 0Fh
0x180031ec5  cmp     [rsp+88h+arg_38], 0
0x180031ecd  cmovz   ecx, eax
0x180031ed0  mov     r9d, ecx
0x180031ed3  bts     r9d, 10h
0x180031ed8  cmp     [rsp+88h+arg_48], 0
0x180031ee0  cmovz   r9d, ecx
0x180031ee4  xor     edx, edx
0x180031ee6  mov     rcx, rsi; FileHandle
0x180031ee9  call    CscDriverOpenItemWithDispositionEx
0x180031eee  mov     ebx, eax
0x180031ef0  test    eax, eax
0x180031ef2  jz      short loc_180031F23
0x180031ef4  mov     rax, cs:WPP_GLOBAL_Control
0x180031efb  cmp     rax, r13
0x180031efe  jz      loc_180031F87
0x180031f04  test    byte ptr [rax+6Ch], 1
0x180031f08  jz      short loc_180031F87
0x180031f0a  mov     r8d, ebx
0x180031f0d  lea     rcx, aSyncopenuncpat_4; "SyncOpenUNCPathForPinAndFill: CscDriver"...
0x180031f14  mov     rdx, rbp
0x180031f17  call    SyncTraceOutputInternal
0x180031f1c  mov     edx, 1Ch
0x180031f21  jmp     short loc_180031F62
0x180031f23  test    r14, r14
0x180031f26  jz      short loc_180031F80
0x180031f28  mov     rcx, [rsi]
0x180031f2b  mov     rdx, r14
0x180031f2e  call    SyncHandleIsDisconnected
0x180031f33  mov     ebx, eax
0x180031f35  test    eax, eax
0x180031f37  jz      short loc_180031F80
0x180031f39  mov     rax, cs:WPP_GLOBAL_Control
0x180031f40  cmp     rax, r13
0x180031f43  jz      short loc_180031F87
0x180031f45  test    byte ptr [rax+6Ch], 1
0x180031f49  jz      short loc_180031F87
0x180031f4b  mov     r8d, ebx
0x180031f4e  lea     rcx, aSyncopenuncpat_2; "SyncOpenUNCPathForPinAndFill: SyncHandl"...
0x180031f55  mov     rdx, rbp
0x180031f58  call    SyncTraceOutputInternal
0x180031f5d  mov     edx, 1Dh
0x180031f62  mov     rcx, cs:WPP_GLOBAL_Control
0x180031f69  lea     r8, WPP_f707efbc203434f979e24425cc714701_Traceguids
0x180031f70  mov     r9, rbp
0x180031f73  mov     [rsp+88h+var_68], ebx
0x180031f77  mov     rcx, [rcx+60h]
0x180031f7b  call    WPP_SF_Sd
0x180031f80  mov     rax, cs:WPP_GLOBAL_Control
0x180031f87  cmp     qword ptr [rsi], 0
0x180031f8b  jz      short loc_180031F94
0x180031f8d  inc     cs:OpenedHandles
0x180031f94  test    ebx, ebx
0x180031f96  jz      short loc_180031FB3
0x180031f98  mov     rcx, [rsi]; Handle
0x180031f9b  test    rcx, rcx
0x180031f9e  jz      short loc_180031FB3
0x180031fa0  call    SyncCloseFile
0x180031fa5  mov     qword ptr [rsi], 0
0x180031fac  mov     rax, cs:WPP_GLOBAL_Control
0x180031fb3  cmp     rax, r13
0x180031fb6  jz      short loc_180032022
0x180031fb8  test    byte ptr [rax+6Ch], 8
0x180031fbc  jz      short loc_180032022
0x180031fbe  mov     edi, 3Fh ; '?'
0x180031fc3  test    r14, r14
0x180031fc6  jz      short loc_180031FDA
0x180031fc8  mov     al, [r14]
0x180031fcb  neg     al
0x180031fcd  sbb     r8d, r8d
0x180031fd0  and     r8d, 0Bh
0x180031fd4  add     r8d, 4Eh ; 'N'
0x180031fd8  jmp     short loc_180031FDD
0x180031fda  mov     r8d, edi
0x180031fdd  mov     rdx, [rsi]
0x180031fe0  lea     rcx, aSyncopenuncpat_7; "SyncOpenUNCPathForPinAndFill: Handle = "...
0x180031fe7  mov     r9d, ebx
0x180031fea  call    SyncTraceOutputInternal
0x180031fef  test    r14, r14
0x180031ff2  jz      short loc_180032001
0x180031ff4  mov     al, [r14]
0x180031ff7  neg     al
0x180031ff9  sbb     edi, edi
0x180031ffb  and     edi, 0Bh
0x180031ffe  add     edi, 4Eh ; 'N'
0x180032001  mov     rcx, cs:WPP_GLOBAL_Control
0x180032008  mov     edx, 1Eh
0x18003200d  mov     r9, [rsi]
0x180032010  mov     [rsp+88h+var_60], ebx
0x180032014  mov     byte ptr [rsp+88h+var_68], dil
0x180032019  mov     rcx, [rcx+60h]
0x18003201d  call    WPP_SF_qcD
0x180032022  mov     eax, ebx
0x180032024  add     rsp, 50h
0x180032028  pop     r15
0x18003202a  pop     r14
0x18003202c  pop     r13
0x18003202e  pop     rdi
0x18003202f  pop     rsi
0x180032030  pop     rbp
0x180032031  pop     rbx
0x180032032  retn
```
