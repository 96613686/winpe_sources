# SyncActionCopyServerToPath

- ea: `0x180078900`
- end: `0x180078ded`
- name: `SyncActionCopyServerToPath`
- size: `1261`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops`

## callees

- `0x1800030f0`
- `0x1800223c0`
- `0x18002d8ec`
- `0x1800360c0`
- `0x180036394`
- `0x18003c4e8`
- `0x18003e928`
- `0x18007291c`
- `0x1800731e0`
- `0x180075a00`
- `0x180076be4`
- `0x180076de4`
- `0x180078900`
- `0x18007c56c`
- `0x18007d1a0`

## string_xrefs

- `0x180078961`: `SyncActionCopyServerToPath: Context: 0x%p FullPath: [%ws] Item: 0x%p Parameter: 0x%p Flags: 0x%x`
- `0x1800789c1`: `SyncActionCopyServerToPath: TICA 0x%p TICO: 0x%p CallerContext: 0x%p Result: 0x%x`
- `0x180078a3d`: `SyncActionCopyServerToPath: Called with a directory, which is not supported -- exiting with %x`
- `0x180078ab0`: `SyncActionCopyServerToPath: SyncCreateUNCPathServerOnly failed with %x`
- `0x180078b22`: `SyncActionCopyServerToPath: SyncActionHasFileChanged failed with %x`
- `0x180078b56`: `SyncActionCopyServerToPath: '%ws' has changed since enumeration [%x]`
- `0x180078bd6`: `SyncActionCopyServerToPath: SyncCreateFileByPath failed for '%ws' with %x`
- `0x180078c35`: `SyncActionCopyServerToPath: SyncSetFileDeleted failed with %x`
- `0x180078c7f`: `SyncActionCopyServerToPath: SyncActionCopyFile (%x) failed with %x`
- `0x180078d0b`: `SyncActionCopyServerToPath: SyncActionCopyAttributes failed with %x`
- `0x180078d41`: `SyncActionCopyServerToPath: SyncUnSetFileDeleted failed with %x`
- `0x180078da7`: `SyncActionCopyServerToPath: Result: 0x%x  Return: %x`

## pseudocode

```c
__int64 __fastcall SyncActionCopyServerToPath(__int64 a1)
{
  CObjectMonitor *v2; // rdx
  int v3; // r8d
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r9
  unsigned int v7; // eax
  unsigned int *v8; // r14
  unsigned int HasFileChanged; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  char v16[8]; // [rsp+20h] [rbp-30h]
  int v17; // [rsp+20h] [rbp-30h]
  HANDLE FileHandle; // [rsp+80h] [rbp+30h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+38h] BYREF

  FileHandle = 0;
  Handle = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncActionCopyServerToPath: Context: 0x%p FullPath: [%ws] Item: 0x%p Parameter: 0x%p Flags: 0x%x",
        *(_QWORD *)a1,
        *(_QWORD *)(a1 + 8),
        *(_QWORD *)(a1 + 16),
        *(_QWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32));
      WPP_SF_qSqqD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        105,
        v3,
        *(_QWORD *)a1,
        *(_QWORD *)(a1 + 8),
        *(_QWORD *)(a1 + 16),
        *(_QWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32));
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 108) & 4) != 0 )
    {
      *(_DWORD *)v16 = *(_DWORD *)(a1 + 104);
      SyncTraceOutputInternal(
        L"SyncActionCopyServerToPath: TICA 0x%p TICO: 0x%p CallerContext: 0x%p Result: 0x%x",
        *(_QWORD *)(a1 + 64),
        *(_QWORD *)(a1 + 72),
        *(_QWORD *)(a1 + 96),
        *(_QWORD *)v16);
      WPP_SF_qqqD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        106,
        WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
        *(_QWORD *)(a1 + 64),
        *(_QWORD *)(a1 + 72),
        *(_QWORD *)(a1 + 96),
        *(_DWORD *)(a1 + 104));
      v2 = WPP_GLOBAL_Control;
    }
  }
  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 16) + 96LL) & 0x10) == 0 )
  {
    v7 = SyncCreateUNCPathServerOnly(&Handle, 0, *(_QWORD *)(a1 + 8), 129, 0, 5, 1, 0);
    v4 = v7;
    if ( v7 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_47;
      }
      SyncTraceOutputInternal(L"SyncActionCopyServerToPath: SyncCreateUNCPathServerOnly failed with %x", v7);
      v5 = 108;
      goto LABEL_44;
    }
    v8 = (unsigned int *)(a1 + 104);
    HasFileChanged = SyncActionHasFileChanged(
                       *(_QWORD *)a1,
                       (_DWORD)Handle,
                       0,
                       0,
                       1,
                       0,
                       0,
                       *(_QWORD *)(a1 + 16),
                       a1 + 104,
                       *(_DWORD *)(a1 + 32));
    v4 = HasFileChanged;
    if ( HasFileChanged )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_47;
      }
      SyncTraceOutputInternal(L"SyncActionCopyServerToPath: SyncActionHasFileChanged failed with %x", HasFileChanged);
      v5 = 109;
      goto LABEL_44;
    }
    if ( (*v8 & 0x1F0) != 0 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(
          L"SyncActionCopyServerToPath: '%ws' has changed since enumeration [%x]",
          *(_QWORD *)(a1 + 8),
          *v8);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          110,
          (unsigned int)WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
          *(_QWORD *)(a1 + 8),
          *v8);
        v2 = WPP_GLOBAL_Control;
      }
      v4 = -1073741823;
      goto LABEL_47;
    }
    v10 = SyncCreateFileByPath(&FileHandle, v17, 0);
    v4 = v10;
    if ( v10 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_47;
      }
      SyncTraceOutputInternal(
        L"SyncActionCopyServerToPath: SyncCreateFileByPath failed for '%ws' with %x",
        *(_QWORD *)(a1 + 8),
        v10);
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        111,
        (unsigned int)WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
        *(_QWORD *)(a1 + 8),
        v4);
      goto LABEL_46;
    }
    v11 = SyncSetFileDeleted(FileHandle);
    v4 = v11;
    if ( v11 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_47;
      }
      SyncTraceOutputInternal(L"SyncActionCopyServerToPath: SyncSetFileDeleted failed with %x", v11);
      v5 = 112;
    }
    else
    {
      v12 = SyncActionCopyFile(a1, Handle, FileHandle);
      v4 = v12;
      if ( v12 )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_47;
        }
        SyncTraceOutputInternal(
          L"SyncActionCopyServerToPath: SyncActionCopyFile (%x) failed with %x",
          *(unsigned int *)(*(_QWORD *)(a1 + 16) + 96LL),
          v12);
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          113,
          WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
          *(unsigned int *)(*(_QWORD *)(a1 + 16) + 96LL),
          v4);
LABEL_46:
        v2 = WPP_GLOBAL_Control;
        goto LABEL_47;
      }
      v13 = SyncActionCopyAttributesWithAdjustment(Handle, FileHandle, 0, 0, 0, 0);
      v4 = v13;
      if ( v13 )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_47;
        }
        SyncTraceOutputInternal(L"SyncActionCopyServerToPath: SyncActionCopyAttributes failed with %x", v13);
        v5 = 114;
      }
      else
      {
        v14 = SyncUnSetFileDeleted(FileHandle);
        v4 = v14;
        if ( !v14 )
          goto LABEL_46;
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_47;
        }
        SyncTraceOutputInternal(L"SyncActionCopyServerToPath: SyncUnSetFileDeleted failed with %x", v14);
        v5 = 115;
      }
    }
LABEL_44:
    v6 = v4;
    goto LABEL_45;
  }
  v4 = -1073741637;
  if ( v2 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 108) & 1) != 0 )
  {
    SyncTraceOutputInternal(
      L"SyncActionCopyServerToPath: Called with a directory, which is not supported -- exiting with %x",
      3221225659LL);
    v5 = 107;
    v6 = 3221225659LL;
LABEL_45:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), v5, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids, v6);
    goto LABEL_46;
  }
LABEL_47:
  if ( Handle )
  {
    SyncCloseFile(Handle);
    v2 = WPP_GLOBAL_Control;
  }
  if ( FileHandle )
  {
    SyncCloseFile(FileHandle);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncActionCopyServerToPath: Result: 0x%x  Return: %x", *(unsigned int *)(a1 + 104), v4);
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      116,
      WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
      *(unsigned int *)(a1 + 104),
      v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180078900  mov     [rsp-28h+arg_10], rbx
0x180078905  push    rbp
0x180078906  push    rdi
0x180078907  push    r12
0x180078909  push    r13
0x18007890b  push    r14
0x18007890d  mov     rbp, rsp
0x180078910  sub     rsp, 50h
0x180078914  mov     rdi, rcx
0x180078917  mov     [rbp+FileHandle], 0
0x18007891f  mov     [rbp+Handle], 0
0x180078927  mov     rdx, cs:WPP_GLOBAL_Control
0x18007892e  lea     r12, WPP_GLOBAL_Control
0x180078935  lea     r13, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids
0x18007893c  cmp     rdx, r12
0x18007893f  jz      loc_180078A19
0x180078945  test    byte ptr [rdx+6Ch], 4
0x180078949  jz      short loc_1800789B3
0x18007894b  mov     eax, [rcx+20h]
0x18007894e  mov     r9, [rcx+10h]
0x180078952  mov     r8, [rcx+8]
0x180078956  mov     rdx, [rcx]
0x180078959  mov     [rsp+50h+var_28], eax
0x18007895d  mov     rax, [rcx+18h]
0x180078961  lea     rcx, aSyncactioncopy_11; "SyncActionCopyServerToPath: Context: 0x"...
0x180078968  mov     qword ptr [rsp+50h+var_30], rax
0x18007896d  call    SyncTraceOutputInternal
0x180078972  mov     eax, [rdi+20h]
0x180078975  mov     edx, 69h ; 'i'
0x18007897a  mov     rcx, cs:WPP_GLOBAL_Control
0x180078981  mov     r9, [rdi]
0x180078984  mov     dword ptr [rsp+50h+var_18], eax
0x180078988  mov     rax, [rdi+18h]
0x18007898c  mov     rcx, [rcx+60h]
0x180078990  mov     [rsp+50h+var_20], rax
0x180078995  mov     rax, [rdi+10h]
0x180078999  mov     qword ptr [rsp+50h+var_28], rax
0x18007899e  mov     rax, [rdi+8]
0x1800789a2  mov     qword ptr [rsp+50h+var_30], rax
0x1800789a7  call    WPP_SF_qSqqD
0x1800789ac  mov     rdx, cs:WPP_GLOBAL_Control
0x1800789b3  cmp     rdx, r12
0x1800789b6  jz      short loc_180078A19
0x1800789b8  test    byte ptr [rdx+6Ch], 4
0x1800789bc  jz      short loc_180078A19
0x1800789be  mov     eax, [rdi+68h]
0x1800789c1  lea     rcx, aSyncactioncopy_15; "SyncActionCopyServerToPath: TICA 0x%p T"...
0x1800789c8  mov     r9, [rdi+60h]
0x1800789cc  mov     r8, [rdi+48h]
0x1800789d0  mov     rdx, [rdi+40h]
0x1800789d4  mov     dword ptr [rsp+50h+var_30], eax
0x1800789d8  call    SyncTraceOutputInternal
0x1800789dd  mov     eax, [rdi+68h]
0x1800789e0  mov     edx, 6Ah ; 'j'
0x1800789e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800789ec  mov     r8, r13
0x1800789ef  mov     r9, [rdi+40h]
0x1800789f3  mov     dword ptr [rsp+50h+var_20], eax
0x1800789f7  mov     rax, [rdi+60h]
0x1800789fb  mov     rcx, [rcx+60h]
0x1800789ff  mov     qword ptr [rsp+50h+var_28], rax
0x180078a04  mov     rax, [rdi+48h]
0x180078a08  mov     qword ptr [rsp+50h+var_30], rax
0x180078a0d  call    WPP_SF_qqqD
0x180078a12  mov     rdx, cs:WPP_GLOBAL_Control
0x180078a19  mov     rax, [rdi+10h]
0x180078a1d  test    byte ptr [rax+60h], 10h
0x180078a21  jz      short loc_180078A59
0x180078a23  mov     ebx, 0C00000BBh
0x180078a28  cmp     rdx, r12
0x180078a2b  jz      loc_180078D6F
0x180078a31  test    byte ptr [rdx+6Ch], 1
0x180078a35  jz      loc_180078D6F
0x180078a3b  mov     edx, ebx
0x180078a3d  lea     rcx, aSyncactioncopy_41; "SyncActionCopyServerToPath: Called with"...
0x180078a44  call    SyncTraceOutputInternal
0x180078a49  mov     edx, 6Bh ; 'k'
0x180078a4e  mov     r9d, 0C00000BBh
0x180078a54  jmp     loc_180078D55
0x180078a59  mov     r8, [rdi+8]
0x180078a5d  lea     rcx, [rbp+Handle]
0x180078a61  mov     dword ptr [rsp+50h+var_18], 0
0x180078a69  mov     r9d, 81h
0x180078a6f  mov     dword ptr [rsp+50h+var_20], 1
0x180078a77  xor     edx, edx
0x180078a79  mov     [rsp+50h+var_28], 5
0x180078a81  mov     dword ptr [rsp+50h+var_30], 0
0x180078a89  call    SyncCreateUNCPathServerOnly
0x180078a8e  mov     ebx, eax
0x180078a90  test    eax, eax
0x180078a92  jz      short loc_180078AC6
0x180078a94  mov     rdx, cs:WPP_GLOBAL_Control
0x180078a9b  cmp     rdx, r12
0x180078a9e  jz      loc_180078D6F
0x180078aa4  test    byte ptr [rdx+6Ch], 1
0x180078aa8  jz      loc_180078D6F
0x180078aae  mov     edx, eax
0x180078ab0  lea     rcx, aSyncactioncopy_14; "SyncActionCopyServerToPath: SyncCreateU"...
0x180078ab7  call    SyncTraceOutputInternal
0x180078abc  mov     edx, 6Ch ; 'l'
0x180078ac1  jmp     loc_180078D52
0x180078ac6  mov     eax, [rdi+20h]
0x180078ac9  lea     r14, [rdi+68h]
0x180078acd  mov     rdx, [rbp+Handle]
0x180078ad1  xor     r9d, r9d
0x180078ad4  mov     rcx, [rdi]
0x180078ad7  xor     r8d, r8d
0x180078ada  mov     [rsp+50h+var_8], eax
0x180078ade  mov     rax, [rdi+10h]
0x180078ae2  mov     [rsp+50h+var_10], r14
0x180078ae7  mov     [rsp+50h+var_18], rax
0x180078aec  mov     byte ptr [rsp+50h+var_20], 0
0x180078af1  mov     byte ptr [rsp+50h+var_28], 0
0x180078af6  mov     [rsp+50h+var_30], 1; int
0x180078afb  call    SyncActionHasFileChanged
0x180078b00  mov     ebx, eax
0x180078b02  test    eax, eax
0x180078b04  jz      short loc_180078B38
0x180078b06  mov     rdx, cs:WPP_GLOBAL_Control
0x180078b0d  cmp     rdx, r12
0x180078b10  jz      loc_180078D6F
0x180078b16  test    byte ptr [rdx+6Ch], 1
0x180078b1a  jz      loc_180078D6F
0x180078b20  mov     edx, eax
0x180078b22  lea     rcx, aSyncactioncopy_40; "SyncActionCopyServerToPath: SyncActionH"...
0x180078b29  call    SyncTraceOutputInternal
0x180078b2e  mov     edx, 6Dh ; 'm'
0x180078b33  jmp     loc_180078D52
0x180078b38  test    dword ptr [r14], 1F0h
0x180078b3f  jz      short loc_180078B9A
0x180078b41  mov     rdx, cs:WPP_GLOBAL_Control
0x180078b48  cmp     rdx, r12
0x180078b4b  jz      short loc_180078B90
0x180078b4d  test    byte ptr [rdx+6Ch], 1
0x180078b51  jz      short loc_180078B90
0x180078b53  mov     r8d, [r14]
0x180078b56  lea     rcx, aSyncactioncopy_16; "SyncActionCopyServerToPath: '%ws' has c"...
0x180078b5d  mov     rdx, [rdi+8]
0x180078b61  call    SyncTraceOutputInternal
0x180078b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180078b6d  mov     edx, 6Eh ; 'n'
0x180078b72  mov     eax, [r14]
0x180078b75  mov     r8, r13
0x180078b78  mov     r9, [rdi+8]
0x180078b7c  mov     dword ptr [rsp+50h+var_30], eax
0x180078b80  mov     rcx, [rcx+60h]
0x180078b84  call    WPP_SF_Sd
0x180078b89  mov     rdx, cs:WPP_GLOBAL_Control
0x180078b90  mov     ebx, 0C0000001h
0x180078b95  jmp     loc_180078D6F
0x180078b9a  mov     r8, [rdi+18h]
0x180078b9e  lea     rcx, [rbp+FileHandle]; FileHandle
0x180078ba2  mov     [rsp+50h+var_28], 0; int
0x180078baa  mov     r8, [r8]
0x180078bad  call    SyncCreateFileByPath
0x180078bb2  mov     ebx, eax
0x180078bb4  test    eax, eax
0x180078bb6  jz      short loc_180078C0A
0x180078bb8  mov     rdx, cs:WPP_GLOBAL_Control
0x180078bbf  cmp     rdx, r12
0x180078bc2  jz      loc_180078D6F
0x180078bc8  test    byte ptr [rdx+6Ch], 1
0x180078bcc  jz      loc_180078D6F
0x180078bd2  mov     rdx, [rdi+8]
0x180078bd6  lea     rcx, aSyncactioncopy_12; "SyncActionCopyServerToPath: SyncCreateF"...
0x180078bdd  mov     r8d, eax
0x180078be0  call    SyncTraceOutputInternal
0x180078be5  mov     rcx, cs:WPP_GLOBAL_Control
0x180078bec  mov     edx, 6Fh ; 'o'
0x180078bf1  mov     r9, [rdi+8]
0x180078bf5  mov     r8, r13
0x180078bf8  mov     dword ptr [rsp+50h+var_30], ebx
0x180078bfc  mov     rcx, [rcx+60h]
0x180078c00  call    WPP_SF_Sd
0x180078c05  jmp     loc_180078D68
0x180078c0a  mov     rcx, [rbp+FileHandle]; FileHandle
0x180078c0e  call    SyncSetFileDeleted
0x180078c13  mov     ebx, eax
0x180078c15  test    eax, eax
0x180078c17  jz      short loc_180078C4B
0x180078c19  mov     rdx, cs:WPP_GLOBAL_Control
0x180078c20  cmp     rdx, r12
0x180078c23  jz      loc_180078D6F
0x180078c29  test    byte ptr [rdx+6Ch], 1
0x180078c2d  jz      loc_180078D6F
0x180078c33  mov     edx, eax
0x180078c35  lea     rcx, aSyncactioncopy_38; "SyncActionCopyServerToPath: SyncSetFile"...
0x180078c3c  call    SyncTraceOutputInternal
0x180078c41  mov     edx, 70h ; 'p'
0x180078c46  jmp     loc_180078D52
0x180078c4b  mov     r8, [rbp+FileHandle]
0x180078c4f  mov     rcx, rdi
0x180078c52  mov     rdx, [rbp+Handle]
0x180078c56  call    SyncActionCopyFile
0x180078c5b  mov     ebx, eax
0x180078c5d  test    eax, eax
0x180078c5f  jz      short loc_180078CBA
0x180078c61  mov     rdx, cs:WPP_GLOBAL_Control
0x180078c68  cmp     rdx, r12
0x180078c6b  jz      loc_180078D6F
0x180078c71  test    byte ptr [rdx+6Ch], 1
0x180078c75  jz      loc_180078D6F
0x180078c7b  mov     rdx, [rdi+10h]
0x180078c7f  lea     rcx, aSyncactioncopy_10; "SyncActionCopyServerToPath: SyncActionC"...
0x180078c86  mov     r8d, eax
0x180078c89  mov     edx, [rdx+60h]
0x180078c8c  call    SyncTraceOutputInternal
0x180078c91  mov     r9, [rdi+10h]
0x180078c95  mov     edx, 71h ; 'q'
0x180078c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180078ca1  mov     r8, r13
0x180078ca4  mov     dword ptr [rsp+50h+var_30], ebx
0x180078ca8  mov     r9d, [r9+60h]
0x180078cac  mov     rcx, [rcx+60h]
0x180078cb0  call    WPP_SF_dd
0x180078cb5  jmp     loc_180078D68
0x180078cba  mov     r8, [rdi+10h]
0x180078cbe  xor     r9d, r9d
0x180078cc1  mov     rdx, [rbp+FileHandle]; FileHandle
0x180078cc5  add     r8, 48h ; 'H'
0x180078cc9  mov     rcx, [rbp+Handle]; hHandle
0x180078ccd  mov     [rsp+50h+var_18], 0; __int64
0x180078cd6  mov     [rsp+50h+var_20], 0; __int64
0x180078cdf  mov     [rsp+50h+var_28], 0; int
0x180078ce7  mov     [rsp+50h+var_30], 0; char
0x180078cec  call    SyncActionCopyAttributesWithAdjustment
0x180078cf1  mov     ebx, eax
0x180078cf3  test    eax, eax
0x180078cf5  jz      short loc_180078D1E
0x180078cf7  mov     rdx, cs:WPP_GLOBAL_Control
0x180078cfe  cmp     rdx, r12
0x180078d01  jz      short loc_180078D6F
0x180078d03  test    byte ptr [rdx+6Ch], 1
0x180078d07  jz      short loc_180078D6F
0x180078d09  mov     edx, eax
0x180078d0b  lea     rcx, aSyncactioncopy_28; "SyncActionCopyServerToPath: SyncActionC"...
0x180078d12  call    SyncTraceOutputInternal
0x180078d17  mov     edx, 72h ; 'r'
0x180078d1c  jmp     short loc_180078D52
0x180078d1e  mov     rcx, [rbp+FileHandle]; FileHandle
0x180078d22  call    SyncUnSetFileDeleted
0x180078d27  mov     ebx, eax
0x180078d29  test    eax, eax
0x180078d2b  jz      short loc_180078D68
0x180078d2d  mov     rdx, cs:WPP_GLOBAL_Control
0x180078d34  cmp     rdx, r12
0x180078d37  jz      short loc_180078D6F
0x180078d39  test    byte ptr [rdx+6Ch], 1
0x180078d3d  jz      short loc_180078D6F
0x180078d3f  mov     edx, eax
0x180078d41  lea     rcx, aSyncactioncopy_21; "SyncActionCopyServerToPath: SyncUnSetFi"...
0x180078d48  call    SyncTraceOutputInternal
0x180078d4d  mov     edx, 73h ; 's'
0x180078d52  mov     r9d, ebx
0x180078d55  mov     rcx, cs:WPP_GLOBAL_Control
0x180078d5c  mov     r8, r13
0x180078d5f  mov     rcx, [rcx+60h]
0x180078d63  call    WPP_SF_d
0x180078d68  mov     rdx, cs:WPP_GLOBAL_Control
0x180078d6f  mov     rcx, [rbp+Handle]; Handle
0x180078d73  test    rcx, rcx
0x180078d76  jz      short loc_180078D84
0x180078d78  call    SyncCloseFile
0x180078d7d  mov     rdx, cs:WPP_GLOBAL_Control
0x180078d84  mov     rcx, [rbp+FileHandle]; Handle
0x180078d88  test    rcx, rcx
0x180078d8b  jz      short loc_180078D99
0x180078d8d  call    SyncCloseFile
0x180078d92  mov     rdx, cs:WPP_GLOBAL_Control
0x180078d99  cmp     rdx, r12
0x180078d9c  jz      short loc_180078DD6
0x180078d9e  test    byte ptr [rdx+6Ch], 8
0x180078da2  jz      short loc_180078DD6
0x180078da4  mov     edx, [rdi+68h]
0x180078da7  lea     rcx, aSyncactioncopy_20; "SyncActionCopyServerToPath: Result: 0x%"...
0x180078dae  mov     r8d, ebx
0x180078db1  call    SyncTraceOutputInternal
0x180078db6  mov     rcx, cs:WPP_GLOBAL_Control
0x180078dbd  mov     edx, 74h ; 't'
0x180078dc2  mov     r9d, [rdi+68h]
0x180078dc6  mov     r8, r13
0x180078dc9  mov     dword ptr [rsp+50h+var_30], ebx
0x180078dcd  mov     rcx, [rcx+60h]
0x180078dd1  call    WPP_SF_dd
0x180078dd6  mov     eax, ebx
0x180078dd8  mov     rbx, [rsp+50h+arg_10]
0x180078de0  add     rsp, 50h
0x180078de4  pop     r14
0x180078de6  pop     r13
0x180078de8  pop     r12
0x180078dea  pop     rdi
0x180078deb  pop     rbp
0x180078dec  retn
```
