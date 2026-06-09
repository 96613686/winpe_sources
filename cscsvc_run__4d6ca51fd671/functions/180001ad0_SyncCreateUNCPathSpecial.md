# SyncCreateUNCPathSpecial

- ea: `0x180001ad0`
- end: `0x180001e55`
- name: `SyncCreateUNCPathSpecial`
- size: `901`
- prototype: `__int64 __usercall@<rax>(PHANDLE FileHandle@<rcx>, ULONG, int, int, char, __int64, __int64, int)`
- caller_count: `8`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001e60`
- `0x180077bc0`
- `0x180078390`
- `0x180079250`
- `0x18007a350`
- `0x18007ab30`
- `0x18007b5fc`
- `0x18007ed50`

## callees

- `0x180001ad0`
- `0x1800023f0`
- `0x1800068b0`
- `0x1800223c0`
- `0x1800360c0`
- `0x180036394`
- `0x18003c4e8`
- `0x1800469c0`
- `0x180073f64`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180001c97`
- `ntdll!RtlInitUnicodeString` at `0x180001c97`

## string_xrefs

- `0x180001b43`: `SyncCreateUNCPathSpecial: Handle: 0x%p UNCPath: 0x%p DesiredAccess: 0x%x, OpenSparseDeleted: %d IsDirectoryOpen = %c`
- `0x180001bab`: `SyncCreateUNCPathSpecial: ShareAccess: 0x%x CreateDisposition: 0x%x CreateOptions: 0x%x`
- `0x180001c2e`: `SyncCreateUNCPathSpecial: Invalid SyncOpenFlags %x`
- `0x180001d54`: `SyncCreateUNCPathSpecial: CscDriverOpenItem failed for '%ws' with %x`
- `0x180001dba`: `SyncCreateUNCPathSpecial: SyncHandleIsDisconnected failed for '%ws' with %x`
- `0x180001e17`: `SyncCreateUNCPathSpecial: %x`

## pseudocode

```c
__int64 __fastcall SyncCreateUNCPathSpecial(
        PHANDLE FileHandle,
        __int64 a2,
        const WCHAR *a3,
        int a4,
        ULONG a5,
        int a6,
        unsigned int a7,
        unsigned __int8 a8,
        char *a9,
        _BYTE *a10,
        unsigned int a11)
{
  CObjectMonitor *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  char v17; // cl
  char v18; // si
  unsigned int IsDisconnected; // ebx
  CObjectMonitor *v20; // rax
  int v21; // r12d
  int v22; // r13d
  char v23; // si
  int v24; // ecx
  int v25; // eax
  int v26; // ecx
  int v27; // eax
  int v28; // r9d
  int v29; // edx
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-58h] BYREF
  char v33; // [rsp+F0h] [rbp+58h]

  DestinationString = 0;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncCreateUNCPathSpecial: Handle: 0x%p UNCPath: 0x%p DesiredAccess: 0x%x, OpenSparseDeleted: %d IsDirectoryOpen = %c",
        FileHandle);
      if ( a10 )
        v17 = *a10 != 0 ? 89 : 78;
      else
        v17 = 78;
      WPP_SF_qqDdc(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        v15,
        v16,
        FileHandle,
        a3,
        a4,
        a8,
        v17,
        *(_QWORD *)&DestinationString.Length,
        DestinationString.Buffer);
      v14 = WPP_GLOBAL_Control;
    }
    if ( v14 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncCreateUNCPathSpecial: ShareAccess: 0x%x CreateDisposition: 0x%x CreateOptions: 0x%x",
        a5,
        1,
        a7);
      WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 12), 20, WPP_f707efbc203434f979e24425cc714701_Traceguids, a5, 1, a7);
    }
  }
  v18 = a11;
  *FileHandle = 0;
  if ( (a11 & 0xFFFFFFF8) == 0 )
  {
    v33 = 0;
    v21 = v18 & 4;
    v22 = v18 & 2;
    v23 = v18 & 1;
    if ( a9 )
      v33 = *a9;
    RtlInitUnicodeString(&DestinationString, a3);
    v24 = a8 != 0 ? 16386 : 0x4000;
    if ( a10 && *a10 )
      v24 |= 4u;
    v25 = v24 | 0x80;
    if ( !v33 )
      v25 = v24;
    v26 = v25 | 0x3000;
    if ( !v23 )
      v26 = v25;
    v27 = v26 | 0x1000;
    if ( !v21 )
      v27 = v26;
    v28 = v27 | 0x20000;
    if ( !v22 )
      v28 = v27;
    IsDisconnected = CscDriverOpenItemWithDispositionEx(FileHandle, 0, &DestinationString, v28, a4, a5, 1u, a7);
    if ( IsDisconnected )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_38;
      }
      SyncTraceOutputInternal(
        L"SyncCreateUNCPathSpecial: CscDriverOpenItem failed for '%ws' with %x",
        a3,
        IsDisconnected);
      v29 = 22;
    }
    else
    {
      if ( !a9 )
        goto LABEL_37;
      IsDisconnected = SyncHandleIsDisconnected(*FileHandle, a9);
      if ( !IsDisconnected )
        goto LABEL_37;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_38;
      }
      SyncTraceOutputInternal(
        L"SyncCreateUNCPathSpecial: SyncHandleIsDisconnected failed for '%ws' with %x",
        a3,
        IsDisconnected);
      v29 = 23;
    }
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      v29,
      (unsigned int)WPP_f707efbc203434f979e24425cc714701_Traceguids,
      (_DWORD)a3,
      IsDisconnected);
    goto LABEL_37;
  }
  IsDisconnected = -1073741811;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    SyncTraceOutputInternal(L"SyncCreateUNCPathSpecial: Invalid SyncOpenFlags %x", a11);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 21, WPP_f707efbc203434f979e24425cc714701_Traceguids, a11);
LABEL_37:
    v20 = WPP_GLOBAL_Control;
  }
LABEL_38:
  if ( *FileHandle )
    ++OpenedHandles;
  if ( IsDisconnected && *FileHandle )
  {
    SyncCloseFile(*FileHandle);
    *FileHandle = 0;
    v20 = WPP_GLOBAL_Control;
  }
  if ( v20 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v20 + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncCreateUNCPathSpecial: %x", IsDisconnected);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 24, WPP_f707efbc203434f979e24425cc714701_Traceguids, IsDisconnected);
  }
  return IsDisconnected;
}

```

## disassembly

```asm
0x180001ad0  mov     [rsp+arg_18], r9d
0x180001ad5  push    rbx
0x180001ad6  push    rbp
0x180001ad7  push    rsi
0x180001ad8  push    rdi
0x180001ad9  push    r12
0x180001adb  push    r13
0x180001add  push    r14
0x180001adf  push    r15
0x180001ae1  sub     rsp, 58h
0x180001ae5  xorps   xmm0, xmm0
0x180001ae8  mov     r14d, r9d
0x180001aeb  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x180001af0  mov     rbp, r8
0x180001af3  mov     rdi, rcx
0x180001af6  mov     rax, cs:WPP_GLOBAL_Control
0x180001afd  lea     r12, WPP_GLOBAL_Control
0x180001b04  mov     rbx, [rsp+98h+arg_48]
0x180001b0c  movzx   r15d, [rsp+98h+arg_38]
0x180001b15  cmp     rax, r12
0x180001b18  jz      loc_180001BF7
0x180001b1e  test    byte ptr [rax+6Ch], 4
0x180001b22  jz      short loc_180001B99
0x180001b24  test    rbx, rbx
0x180001b27  jz      short loc_180001B37
0x180001b29  mov     al, [rbx]
0x180001b2b  neg     al
0x180001b2d  sbb     ecx, ecx
0x180001b2f  and     ecx, 0Bh
0x180001b32  add     ecx, 4Eh ; 'N'
0x180001b35  jmp     short loc_180001B3C
0x180001b37  mov     ecx, 4Eh ; 'N'
0x180001b3c  mov     [rsp+98h+var_70], ecx
0x180001b40  mov     rdx, rdi
0x180001b43  lea     rcx, aSynccreateuncp_8; "SyncCreateUNCPathSpecial: Handle: 0x%p "...
0x180001b4a  mov     [rsp+98h+var_78], r15d
0x180001b4f  call    SyncTraceOutputInternal
0x180001b54  test    rbx, rbx
0x180001b57  jz      short loc_180001B67
0x180001b59  mov     al, [rbx]
0x180001b5b  neg     al
0x180001b5d  sbb     ecx, ecx
0x180001b5f  and     ecx, 0Bh
0x180001b62  add     ecx, 4Eh ; 'N'
0x180001b65  jmp     short loc_180001B6C
0x180001b67  mov     ecx, 4Eh ; 'N'
0x180001b6c  mov     byte ptr [rsp+98h+var_60], cl
0x180001b70  mov     r9, rdi
0x180001b73  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b7a  mov     [rsp+98h+var_68], r15d
0x180001b7f  mov     [rsp+98h+var_70], r14d
0x180001b84  mov     qword ptr [rsp+98h+var_78], rbp
0x180001b89  mov     rcx, [rcx+60h]
0x180001b8d  call    WPP_SF_qqDdc
0x180001b92  mov     rax, cs:WPP_GLOBAL_Control
0x180001b99  cmp     rax, r12
0x180001b9c  jz      short loc_180001BF7
0x180001b9e  test    byte ptr [rax+6Ch], 4
0x180001ba2  jz      short loc_180001BF7
0x180001ba4  mov     esi, [rsp+98h+arg_30]
0x180001bab  lea     rcx, aSynccreateuncp_9; "SyncCreateUNCPathSpecial: ShareAccess: "...
0x180001bb2  mov     edx, [rsp+98h+arg_20]
0x180001bb9  mov     r9d, esi
0x180001bbc  mov     r8d, 1
0x180001bc2  call    SyncTraceOutputInternal
0x180001bc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bce  lea     r8, WPP_f707efbc203434f979e24425cc714701_Traceguids
0x180001bd5  mov     r9d, [rsp+98h+arg_20]
0x180001bdd  mov     edx, 14h
0x180001be2  mov     [rsp+98h+var_70], esi
0x180001be6  mov     [rsp+98h+var_78], 1
0x180001bee  mov     rcx, [rcx+60h]
0x180001bf2  call    WPP_SF_DDD
0x180001bf7  mov     esi, [rsp+98h+arg_50]
0x180001bfe  mov     qword ptr [rdi], 0
0x180001c05  test    esi, 0FFFFFFF8h
0x180001c0b  jz      short loc_180001C5E
0x180001c0d  mov     ebx, 0C000000Dh
0x180001c12  mov     rax, cs:WPP_GLOBAL_Control
0x180001c19  cmp     rax, r12
0x180001c1c  jz      loc_180001DDE
0x180001c22  test    byte ptr [rax+6Ch], 1
0x180001c26  jz      loc_180001DDE
0x180001c2c  mov     edx, esi
0x180001c2e  lea     rcx, aSynccreateuncp_4; "SyncCreateUNCPathSpecial: Invalid SyncO"...
0x180001c35  call    SyncTraceOutputInternal
0x180001c3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c41  lea     r8, WPP_f707efbc203434f979e24425cc714701_Traceguids
0x180001c48  mov     edx, 15h
0x180001c4d  mov     r9d, esi
0x180001c50  mov     rcx, [rcx+60h]
0x180001c54  call    WPP_SF_d
0x180001c59  jmp     loc_180001DD7
0x180001c5e  mov     r14, [rsp+98h+arg_40]
0x180001c66  mov     r12d, esi
0x180001c69  mov     r13d, esi
0x180001c6c  mov     byte ptr [rsp+98h+arg_50], 0
0x180001c74  and     r12d, 4
0x180001c78  and     r13d, 2
0x180001c7c  and     sil, 1
0x180001c80  test    r14, r14
0x180001c83  jz      short loc_180001C8F
0x180001c85  mov     al, [r14]
0x180001c88  mov     byte ptr [rsp+98h+arg_50], al
0x180001c8f  mov     rdx, rbp; SourceString
0x180001c92  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x180001c97  call    cs:__imp_RtlInitUnicodeString
0x180001c9d  neg     r15b
0x180001ca0  sbb     ecx, ecx
0x180001ca2  and     ecx, 2
0x180001ca5  add     ecx, 4000h
0x180001cab  test    rbx, rbx
0x180001cae  jz      short loc_180001CB8
0x180001cb0  cmp     byte ptr [rbx], 0
0x180001cb3  jz      short loc_180001CB8
0x180001cb5  or      ecx, 4
0x180001cb8  mov     eax, ecx
0x180001cba  lea     r8, [rsp+98h+DestinationString]
0x180001cbf  bts     eax, 7
0x180001cc3  cmp     byte ptr [rsp+98h+arg_50], 0
0x180001ccb  cmovz   eax, ecx
0x180001cce  mov     ecx, eax
0x180001cd0  or      ecx, 3000h
0x180001cd6  test    sil, sil
0x180001cd9  cmovz   ecx, eax
0x180001cdc  mov     eax, ecx
0x180001cde  bts     eax, 0Ch
0x180001ce2  test    r12d, r12d
0x180001ce5  cmovz   eax, ecx
0x180001ce8  mov     rcx, rdi; FileHandle
0x180001ceb  mov     r9d, eax
0x180001cee  bts     r9d, 11h
0x180001cf3  test    r13d, r13d
0x180001cf6  cmovz   r9d, eax
0x180001cfa  mov     eax, [rsp+98h+arg_30]
0x180001d01  mov     [rsp+98h+var_60], eax; int
0x180001d05  xor     edx, edx
0x180001d07  mov     eax, [rsp+98h+arg_20]
0x180001d0e  mov     [rsp+98h+var_68], 1; ULONG
0x180001d16  mov     [rsp+98h+var_70], eax; ULONG
0x180001d1a  mov     eax, [rsp+98h+arg_18]
0x180001d21  mov     [rsp+98h+var_78], eax; int
0x180001d25  call    CscDriverOpenItemWithDispositionEx
0x180001d2a  mov     ebx, eax
0x180001d2c  test    eax, eax
0x180001d2e  jz      short loc_180001D88
0x180001d30  mov     rax, cs:WPP_GLOBAL_Control
0x180001d37  lea     r12, WPP_GLOBAL_Control
0x180001d3e  cmp     rax, r12
0x180001d41  jz      loc_180001DDE
0x180001d47  test    byte ptr [rax+6Ch], 1
0x180001d4b  jz      loc_180001DDE
0x180001d51  mov     r8d, ebx
0x180001d54  lea     rcx, aSynccreateuncp_0; "SyncCreateUNCPathSpecial: CscDriverOpen"...
0x180001d5b  mov     rdx, rbp
0x180001d5e  call    SyncTraceOutputInternal
0x180001d63  mov     edx, 16h
0x180001d68  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d6f  lea     r8, WPP_f707efbc203434f979e24425cc714701_Traceguids
0x180001d76  mov     r9, rbp
0x180001d79  mov     [rsp+98h+var_78], ebx
0x180001d7d  mov     rcx, [rcx+60h]
0x180001d81  call    WPP_SF_Sd
0x180001d86  jmp     short loc_180001DD7
0x180001d88  test    r14, r14
0x180001d8b  jz      short loc_180001DD0
0x180001d8d  mov     rcx, [rdi]
0x180001d90  mov     rdx, r14
0x180001d93  call    SyncHandleIsDisconnected
0x180001d98  mov     ebx, eax
0x180001d9a  test    eax, eax
0x180001d9c  jz      short loc_180001DD0
0x180001d9e  mov     rax, cs:WPP_GLOBAL_Control
0x180001da5  lea     r12, WPP_GLOBAL_Control
0x180001dac  cmp     rax, r12
0x180001daf  jz      short loc_180001DDE
0x180001db1  test    byte ptr [rax+6Ch], 1
0x180001db5  jz      short loc_180001DDE
0x180001db7  mov     r8d, ebx
0x180001dba  lea     rcx, aSynccreateuncp_5; "SyncCreateUNCPathSpecial: SyncHandleIsD"...
0x180001dc1  mov     rdx, rbp
0x180001dc4  call    SyncTraceOutputInternal
0x180001dc9  mov     edx, 17h
0x180001dce  jmp     short loc_180001D68
0x180001dd0  lea     r12, WPP_GLOBAL_Control
0x180001dd7  mov     rax, cs:WPP_GLOBAL_Control
0x180001dde  cmp     qword ptr [rdi], 0
0x180001de2  jz      short loc_180001DEB
0x180001de4  inc     cs:OpenedHandles
0x180001deb  test    ebx, ebx
0x180001ded  jz      short loc_180001E0A
0x180001def  mov     rcx, [rdi]; Handle
0x180001df2  test    rcx, rcx
0x180001df5  jz      short loc_180001E0A
0x180001df7  call    SyncCloseFile
0x180001dfc  mov     qword ptr [rdi], 0
0x180001e03  mov     rax, cs:WPP_GLOBAL_Control
0x180001e0a  cmp     rax, r12
0x180001e0d  jz      short loc_180001E42
0x180001e0f  test    byte ptr [rax+6Ch], 8
0x180001e13  jz      short loc_180001E42
0x180001e15  mov     edx, ebx
0x180001e17  lea     rcx, aSynccreateuncp_6; "SyncCreateUNCPathSpecial: %x"
0x180001e1e  call    SyncTraceOutputInternal
0x180001e23  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e2a  lea     r8, WPP_f707efbc203434f979e24425cc714701_Traceguids
0x180001e31  mov     edx, 18h
0x180001e36  mov     r9d, ebx
0x180001e39  mov     rcx, [rcx+60h]
0x180001e3d  call    WPP_SF_d
0x180001e42  mov     eax, ebx
0x180001e44  add     rsp, 58h
0x180001e48  pop     r15
0x180001e4a  pop     r14
0x180001e4c  pop     r13
0x180001e4e  pop     r12
0x180001e50  pop     rdi
0x180001e51  pop     rsi
0x180001e52  pop     rbp
0x180001e53  pop     rbx
0x180001e54  retn
```
