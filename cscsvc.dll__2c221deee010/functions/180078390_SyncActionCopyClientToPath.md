# SyncActionCopyClientToPath

- ea: `0x180078390`
- end: `0x1800788f1`
- name: `SyncActionCopyClientToPath`
- size: `1377`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, installer_update`

## callees

- `0x180001ad0`
- `0x1800030f0`
- `0x1800223c0`
- `0x18002d8ec`
- `0x1800360c0`
- `0x180036394`
- `0x18003c560`
- `0x18003e928`
- `0x18007291c`
- `0x180075a00`
- `0x180076be4`
- `0x180076de4`
- `0x180078390`
- `0x18007bd44`
- `0x18007c56c`
- `0x18007d1a0`

## string_xrefs

- `0x1800783ee`: `SyncActionCopyClientToPath: Context: 0x%p FullPath: [%ws] Item: 0x%p Parameter: 0x%p Flags: 0x%x`
- `0x18007844e`: `SyncActionCopyClientToPath: TICA 0x%p TICO: 0x%p CallerContext: 0x%p Result: 0x%x`
- `0x1800784d1`: `SyncActionCopyClientToPath: Called with a directory, which is not supported -- exiting with %x`
- `0x18007857b`: `SyncActionCopyClientToPath: SyncCreateUNCPathSpecial failed with %x`
- `0x1800785ff`: `SyncActionCopyClientToPath: SyncActionHasFileChanged failed with %x`
- `0x180078829`: `SyncActionCopyClientToPath: '%ws' has changed since enumeration [%x] (disconnected=%d)`
- `0x180078677`: `SyncActionCopyClientToPath: SyncCreateFileByPath failed for '%ws' [%x] with %x`
- `0x1800786e5`: `SyncActionCopyClientToPath: SyncSetFileDeleted failed with %x`
- `0x18007872f`: `SyncActionCopyClientToPath: SyncActionCopyFile (%x) failed with %x`
- `0x1800787bc`: `SyncActionCopyClientToPath: SyncActionCopyAttributes failed with %x`
- `0x1800787fd`: `SyncActionCopyClientToPath: SyncUnSetFileDeleted failed with %x`
- `0x1800788ae`: `SyncActionCopyClientToPath: Result: 0x%x  Return: %x`

## pseudocode

```c
__int64 __fastcall SyncActionCopyClientToPath(__int64 a1)
{
  CObjectMonitor *v2; // rdx
  int v3; // r8d
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rdx
  unsigned int v8; // eax
  char v9; // cl
  int v10; // edx
  unsigned int *v11; // r15
  unsigned int HasFileChanged; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  ULONG v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  char v21; // bl
  ULONG v23[2]; // [rsp+20h] [rbp-58h]
  int v24; // [rsp+20h] [rbp-58h]
  int v25; // [rsp+28h] [rbp-50h]
  HANDLE FileHandle; // [rsp+60h] [rbp-18h] BYREF
  __int64 v27; // [rsp+B0h] [rbp+38h] BYREF
  int v28; // [rsp+B8h] [rbp+40h] BYREF
  int v29; // [rsp+C0h] [rbp+48h] BYREF
  HANDLE Handle; // [rsp+C8h] [rbp+50h] BYREF

  FileHandle = 0;
  Handle = 0;
  LOBYTE(v27) = 0;
  v28 = 0;
  v29 = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncActionCopyClientToPath: Context: 0x%p FullPath: [%ws] Item: 0x%p Parameter: 0x%p Flags: 0x%x",
        *(_QWORD *)a1,
        *(_QWORD *)(a1 + 8),
        *(_QWORD *)(a1 + 16),
        *(_QWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32));
      WPP_SF_qSqqD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        93,
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
      v23[0] = *(_DWORD *)(a1 + 104);
      SyncTraceOutputInternal(
        L"SyncActionCopyClientToPath: TICA 0x%p TICO: 0x%p CallerContext: 0x%p Result: 0x%x",
        *(_QWORD *)(a1 + 64),
        *(_QWORD *)(a1 + 72),
        *(_QWORD *)(a1 + 96),
        *(_QWORD *)v23);
      WPP_SF_qqqD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        94,
        WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
        *(_QWORD *)(a1 + 64),
        *(_QWORD *)(a1 + 72),
        *(_QWORD *)(a1 + 96),
        *(_DWORD *)(a1 + 104));
      v2 = WPP_GLOBAL_Control;
    }
  }
  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 16) + 128LL) & 0x10) == 0 )
  {
    LOBYTE(v2) = 1;
    SyncActionpUpdateActionFlag(a1, v2, &v28, &v29);
    v8 = SyncCreateUNCPathSpecial(&Handle, v7, *(const WCHAR **)(a1 + 8), 129, 5u, v25, v29, 0, (char *)&v27, 0, v28);
    v4 = v8;
    if ( v8 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_53;
      }
      SyncTraceOutputInternal(L"SyncActionCopyClientToPath: SyncCreateUNCPathSpecial failed with %x", v8);
      v5 = 96;
    }
    else
    {
      if ( (_BYTE)v27 )
      {
        v9 = 0;
        v10 = 0;
      }
      else
      {
        v9 = 1;
        v10 = (int)Handle;
      }
      v11 = (unsigned int *)(a1 + 104);
      HasFileChanged = SyncActionHasFileChanged(
                         *(_QWORD *)a1,
                         v10,
                         (_DWORD)Handle,
                         (_DWORD)Handle,
                         v9,
                         1,
                         1,
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
          goto LABEL_53;
        }
        SyncTraceOutputInternal(L"SyncActionCopyClientToPath: SyncActionHasFileChanged failed with %x", HasFileChanged);
        v5 = 97;
      }
      else
      {
        if ( (*v11 & 0x1F0) != 0 || !(_BYTE)v27 )
        {
          v2 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            v21 = v27;
            SyncTraceOutputInternal(
              L"SyncActionCopyClientToPath: '%ws' has changed since enumeration [%x] (disconnected=%d)",
              *(_QWORD *)(a1 + 8),
              *v11,
              (unsigned __int8)v27);
            WPP_SF_SdD(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              98,
              (unsigned int)WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
              *(_QWORD *)(a1 + 8),
              *v11,
              v21);
            v2 = WPP_GLOBAL_Control;
          }
          v4 = -1073741823;
          goto LABEL_53;
        }
        v15 = 0;
        if ( Handle )
          v15 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 128LL);
        v16 = SyncCreateFileByPath(&FileHandle, v13, **(const wchar_t ***)(a1 + 24), v14, v24, v15);
        v4 = v16;
        if ( v16 )
        {
          v2 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            SyncTraceOutputInternal(
              L"SyncActionCopyClientToPath: SyncCreateFileByPath failed for '%ws' [%x] with %x",
              *(_QWORD *)(a1 + 8),
              *(unsigned int *)(a1 + 104),
              v16);
            WPP_SF_SdD(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              99,
              (unsigned int)WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
              *(_QWORD *)(a1 + 8),
              *(_DWORD *)(a1 + 104),
              v4);
            goto LABEL_12;
          }
          goto LABEL_53;
        }
        v17 = SyncSetFileDeleted(FileHandle);
        v4 = v17;
        if ( v17 )
        {
          v2 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
          {
            goto LABEL_53;
          }
          SyncTraceOutputInternal(L"SyncActionCopyClientToPath: SyncSetFileDeleted failed with %x", v17);
          v5 = 100;
        }
        else
        {
          v18 = SyncActionCopyFile(a1, Handle, FileHandle);
          v4 = v18;
          if ( v18 )
          {
            v2 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              SyncTraceOutputInternal(
                L"SyncActionCopyClientToPath: SyncActionCopyFile (%x) failed with %x",
                *(unsigned int *)(*(_QWORD *)(a1 + 16) + 96LL),
                v18);
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                101,
                WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
                *(unsigned int *)(*(_QWORD *)(a1 + 16) + 96LL),
                v4);
              goto LABEL_12;
            }
            goto LABEL_53;
          }
          v19 = SyncActionCopyAttributesWithAdjustment(Handle, FileHandle, 0, 0, 0, 0);
          v4 = v19;
          if ( v19 )
          {
            v2 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
            {
              goto LABEL_53;
            }
            SyncTraceOutputInternal(L"SyncActionCopyClientToPath: SyncActionCopyAttributes failed with %x", v19);
            v5 = 102;
          }
          else
          {
            v20 = SyncUnSetFileDeleted(FileHandle);
            v4 = v20;
            if ( !v20 )
              goto LABEL_12;
            v2 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
            {
              goto LABEL_53;
            }
            SyncTraceOutputInternal(L"SyncActionCopyClientToPath: SyncUnSetFileDeleted failed with %x", v20);
            v5 = 103;
          }
        }
      }
    }
    v6 = v4;
    goto LABEL_11;
  }
  v4 = -1073741637;
  if ( v2 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 108) & 1) != 0 )
  {
    SyncTraceOutputInternal(
      L"SyncActionCopyClientToPath: Called with a directory, which is not supported -- exiting with %x",
      3221225659LL);
    v5 = 95;
    v6 = 3221225659LL;
LABEL_11:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), v5, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids, v6);
LABEL_12:
    v2 = WPP_GLOBAL_Control;
  }
LABEL_53:
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
    SyncTraceOutputInternal(L"SyncActionCopyClientToPath: Result: 0x%x  Return: %x", *(unsigned int *)(a1 + 104), v4);
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      104,
      WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
      *(unsigned int *)(a1 + 104),
      v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180078390  push    rbp
0x180078392  push    rbx
0x180078393  push    rdi
0x180078394  push    r12
0x180078396  push    r13
0x180078398  push    r15
0x18007839a  mov     rbp, rsp
0x18007839d  sub     rsp, 78h
0x1800783a1  xor     r12d, r12d
0x1800783a4  mov     rdi, rcx
0x1800783a7  mov     [rbp+FileHandle], r12
0x1800783ab  mov     [rbp+Handle], r12
0x1800783af  mov     byte ptr [rbp+arg_0], r12b
0x1800783b3  mov     [rbp+arg_8], r12d
0x1800783b7  mov     [rbp+arg_10], r12d
0x1800783bb  mov     rdx, cs:WPP_GLOBAL_Control
0x1800783c2  lea     r13, WPP_GLOBAL_Control
0x1800783c9  cmp     rdx, r13
0x1800783cc  jz      loc_1800784AA
0x1800783d2  test    byte ptr [rdx+6Ch], 4
0x1800783d6  jz      short loc_180078440
0x1800783d8  mov     eax, [rcx+20h]
0x1800783db  mov     r9, [rcx+10h]
0x1800783df  mov     r8, [rcx+8]
0x1800783e3  mov     rdx, [rcx]
0x1800783e6  mov     [rsp+78h+var_50], eax
0x1800783ea  mov     rax, [rcx+18h]
0x1800783ee  lea     rcx, aSyncactioncopy_33; "SyncActionCopyClientToPath: Context: 0x"...
0x1800783f5  mov     qword ptr [rsp+78h+var_58], rax
0x1800783fa  call    SyncTraceOutputInternal
0x1800783ff  mov     eax, [rdi+20h]
0x180078402  lea     edx, [r12+5Dh]
0x180078407  mov     rcx, cs:WPP_GLOBAL_Control
0x18007840e  mov     r9, [rdi]
0x180078411  mov     dword ptr [rsp+78h+var_40], eax
0x180078415  mov     rax, [rdi+18h]
0x180078419  mov     rcx, [rcx+60h]
0x18007841d  mov     [rsp+78h+var_48], rax
0x180078422  mov     rax, [rdi+10h]
0x180078426  mov     qword ptr [rsp+78h+var_50], rax
0x18007842b  mov     rax, [rdi+8]
0x18007842f  mov     qword ptr [rsp+78h+var_58], rax
0x180078434  call    WPP_SF_qSqqD
0x180078439  mov     rdx, cs:WPP_GLOBAL_Control
0x180078440  cmp     rdx, r13
0x180078443  jz      short loc_1800784AA
0x180078445  test    byte ptr [rdx+6Ch], 4
0x180078449  jz      short loc_1800784AA
0x18007844b  mov     eax, [rdi+68h]
0x18007844e  lea     rcx, aSyncactioncopy_29; "SyncActionCopyClientToPath: TICA 0x%p T"...
0x180078455  mov     r9, [rdi+60h]
0x180078459  mov     r8, [rdi+48h]
0x18007845d  mov     rdx, [rdi+40h]
0x180078461  mov     [rsp+78h+var_58], eax
0x180078465  call    SyncTraceOutputInternal
0x18007846a  mov     eax, [rdi+68h]
0x18007846d  lea     r8, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids
0x180078474  mov     rcx, cs:WPP_GLOBAL_Control
0x18007847b  mov     edx, 5Eh ; '^'
0x180078480  mov     r9, [rdi+40h]
0x180078484  mov     dword ptr [rsp+78h+var_48], eax
0x180078488  mov     rax, [rdi+60h]
0x18007848c  mov     rcx, [rcx+60h]
0x180078490  mov     qword ptr [rsp+78h+var_50], rax; int
0x180078495  mov     rax, [rdi+48h]
0x180078499  mov     qword ptr [rsp+78h+var_58], rax
0x18007849e  call    WPP_SF_qqqD
0x1800784a3  mov     rdx, cs:WPP_GLOBAL_Control
0x1800784aa  mov     rax, [rdi+10h]
0x1800784ae  test    byte ptr [rax+80h], 10h
0x1800784b5  jz      short loc_18007850B
0x1800784b7  mov     ebx, 0C00000BBh
0x1800784bc  cmp     rdx, r13
0x1800784bf  jz      loc_180078876
0x1800784c5  test    byte ptr [rdx+6Ch], 1
0x1800784c9  jz      loc_180078876
0x1800784cf  mov     edx, ebx
0x1800784d1  lea     rcx, aSyncactioncopy_22; "SyncActionCopyClientToPath: Called with"...
0x1800784d8  call    SyncTraceOutputInternal
0x1800784dd  mov     edx, 5Fh ; '_'
0x1800784e2  mov     r9d, 0C00000BBh
0x1800784e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800784ef  lea     r8, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids
0x1800784f6  mov     rcx, [rcx+60h]
0x1800784fa  call    WPP_SF_d
0x1800784ff  mov     rdx, cs:WPP_GLOBAL_Control
0x180078506  jmp     loc_180078876
0x18007850b  lea     r9, [rbp+arg_10]
0x18007850f  mov     dl, 1
0x180078511  lea     r8, [rbp+arg_8]
0x180078515  mov     rcx, rdi
0x180078518  call    SyncActionpUpdateActionFlag
0x18007851d  mov     eax, [rbp+arg_8]
0x180078520  lea     rcx, [rbp+Handle]; FileHandle
0x180078524  mov     r8, [rdi+8]
0x180078528  mov     r9d, 81h
0x18007852e  mov     [rsp+78h+var_28], eax; int
0x180078532  lea     rax, [rbp+arg_0]
0x180078536  mov     [rsp+78h+var_30], r12; __int64
0x18007853b  mov     [rsp+78h+var_38], rax; __int64
0x180078540  mov     eax, [rbp+arg_10]
0x180078543  mov     [rsp+78h+var_40], r12b; char
0x180078548  mov     dword ptr [rsp+78h+var_48], eax; int
0x18007854c  mov     [rsp+78h+var_58], 5; ULONG
0x180078554  call    SyncCreateUNCPathSpecial
0x180078559  mov     ebx, eax
0x18007855b  test    eax, eax
0x18007855d  jz      short loc_180078594
0x18007855f  mov     rdx, cs:WPP_GLOBAL_Control
0x180078566  cmp     rdx, r13
0x180078569  jz      loc_180078876
0x18007856f  test    byte ptr [rdx+6Ch], 1
0x180078573  jz      loc_180078876
0x180078579  mov     edx, eax
0x18007857b  lea     rcx, aSyncactioncopy_4; "SyncActionCopyClientToPath: SyncCreateU"...
0x180078582  call    SyncTraceOutputInternal
0x180078587  mov     edx, 60h ; '`'
0x18007858c  mov     r9d, ebx
0x18007858f  jmp     loc_1800784E8
0x180078594  mov     r8, [rbp+Handle]
0x180078598  cmp     byte ptr [rbp+arg_0], r12b
0x18007859c  jnz     short loc_1800785A5
0x18007859e  mov     cl, 1
0x1800785a0  mov     rdx, r8
0x1800785a3  jmp     short loc_1800785AB
0x1800785a5  mov     cl, r12b
0x1800785a8  mov     rdx, r12
0x1800785ab  mov     eax, [rdi+20h]
0x1800785ae  lea     r15, [rdi+68h]
0x1800785b2  mov     dword ptr [rsp+78h+var_30], eax
0x1800785b6  mov     r9, r8
0x1800785b9  mov     rax, [rdi+10h]
0x1800785bd  mov     [rsp+78h+var_38], r15
0x1800785c2  mov     qword ptr [rsp+78h+var_40], rax
0x1800785c7  mov     byte ptr [rsp+78h+var_48], 1
0x1800785cc  mov     byte ptr [rsp+78h+var_50], 1
0x1800785d1  mov     byte ptr [rsp+78h+var_58], cl; int
0x1800785d5  mov     rcx, [rdi]
0x1800785d8  call    SyncActionHasFileChanged
0x1800785dd  mov     ebx, eax
0x1800785df  test    eax, eax
0x1800785e1  jz      short loc_180078615
0x1800785e3  mov     rdx, cs:WPP_GLOBAL_Control
0x1800785ea  cmp     rdx, r13
0x1800785ed  jz      loc_180078876
0x1800785f3  test    byte ptr [rdx+6Ch], 1
0x1800785f7  jz      loc_180078876
0x1800785fd  mov     edx, eax
0x1800785ff  lea     rcx, aSyncactioncopy_39; "SyncActionCopyClientToPath: SyncActionH"...
0x180078606  call    SyncTraceOutputInternal
0x18007860b  mov     edx, 61h ; 'a'
0x180078610  jmp     loc_18007858C
0x180078615  test    dword ptr [r15], 1F0h
0x18007861c  jnz     loc_180078813
0x180078622  cmp     byte ptr [rbp+arg_0], r12b
0x180078626  jz      loc_180078813
0x18007862c  mov     eax, r12d
0x18007862f  cmp     [rbp+Handle], r12
0x180078633  jz      short loc_18007863F
0x180078635  mov     rax, [rdi+10h]
0x180078639  mov     eax, [rax+80h]
0x18007863f  mov     r8, [rdi+18h]
0x180078643  lea     rcx, [rbp+FileHandle]; FileHandle
0x180078647  mov     [rsp+78h+var_50], eax; int
0x18007864b  mov     r8, [r8]
0x18007864e  call    SyncCreateFileByPath
0x180078653  mov     ebx, eax
0x180078655  test    eax, eax
0x180078657  jz      short loc_1800786BA
0x180078659  mov     rdx, cs:WPP_GLOBAL_Control
0x180078660  cmp     rdx, r13
0x180078663  jz      loc_180078876
0x180078669  test    byte ptr [rdx+6Ch], 1
0x18007866d  jz      loc_180078876
0x180078673  mov     r8d, [rdi+68h]
0x180078677  lea     rcx, aSyncactioncopy_32; "SyncActionCopyClientToPath: SyncCreateF"...
0x18007867e  mov     rdx, [rdi+8]
0x180078682  mov     r9d, eax
0x180078685  call    SyncTraceOutputInternal
0x18007868a  mov     rcx, cs:WPP_GLOBAL_Control
0x180078691  lea     r8, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids
0x180078698  mov     eax, [rdi+68h]
0x18007869b  mov     edx, 63h ; 'c'
0x1800786a0  mov     r9, [rdi+8]
0x1800786a4  mov     [rsp+78h+var_50], ebx
0x1800786a8  mov     rcx, [rcx+60h]
0x1800786ac  mov     [rsp+78h+var_58], eax
0x1800786b0  call    WPP_SF_SdD
0x1800786b5  jmp     loc_1800784FF
0x1800786ba  mov     rcx, [rbp+FileHandle]; FileHandle
0x1800786be  call    SyncSetFileDeleted
0x1800786c3  mov     ebx, eax
0x1800786c5  test    eax, eax
0x1800786c7  jz      short loc_1800786FB
0x1800786c9  mov     rdx, cs:WPP_GLOBAL_Control
0x1800786d0  cmp     rdx, r13
0x1800786d3  jz      loc_180078876
0x1800786d9  test    byte ptr [rdx+6Ch], 1
0x1800786dd  jz      loc_180078876
0x1800786e3  mov     edx, eax
0x1800786e5  lea     rcx, aSyncactioncopy_35; "SyncActionCopyClientToPath: SyncSetFile"...
0x1800786ec  call    SyncTraceOutputInternal
0x1800786f1  mov     edx, 64h ; 'd'
0x1800786f6  jmp     loc_18007858C
0x1800786fb  mov     r8, [rbp+FileHandle]
0x1800786ff  mov     rcx, rdi
0x180078702  mov     rdx, [rbp+Handle]
0x180078706  call    SyncActionCopyFile
0x18007870b  mov     ebx, eax
0x18007870d  test    eax, eax
0x18007870f  jz      short loc_18007876E
0x180078711  mov     rdx, cs:WPP_GLOBAL_Control
0x180078718  cmp     rdx, r13
0x18007871b  jz      loc_180078876
0x180078721  test    byte ptr [rdx+6Ch], 1
0x180078725  jz      loc_180078876
0x18007872b  mov     rdx, [rdi+10h]
0x18007872f  lea     rcx, aSyncactioncopy_19; "SyncActionCopyClientToPath: SyncActionC"...
0x180078736  mov     r8d, eax
0x180078739  mov     edx, [rdx+60h]
0x18007873c  call    SyncTraceOutputInternal
0x180078741  mov     r9, [rdi+10h]
0x180078745  lea     r8, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids
0x18007874c  mov     rcx, cs:WPP_GLOBAL_Control
0x180078753  mov     edx, 65h ; 'e'
0x180078758  mov     [rsp+78h+var_58], ebx
0x18007875c  mov     r9d, [r9+60h]
0x180078760  mov     rcx, [rcx+60h]
0x180078764  call    WPP_SF_dd
0x180078769  jmp     loc_1800784FF
0x18007876e  mov     r8, [rdi+10h]
0x180078772  xor     r9d, r9d
0x180078775  mov     rdx, [rbp+FileHandle]; FileHandle
0x180078779  add     r8, 68h ; 'h'
0x18007877d  mov     rcx, [rbp+Handle]; hHandle
0x180078781  mov     qword ptr [rsp+78h+var_40], r12; __int64
0x180078786  mov     [rsp+78h+var_48], r12; __int64
0x18007878b  mov     [rsp+78h+var_50], r12d; int
0x180078790  mov     byte ptr [rsp+78h+var_58], r12b; char
0x180078795  call    SyncActionCopyAttributesWithAdjustment
0x18007879a  mov     ebx, eax
0x18007879c  test    eax, eax
0x18007879e  jz      short loc_1800787D2
0x1800787a0  mov     rdx, cs:WPP_GLOBAL_Control
0x1800787a7  cmp     rdx, r13
0x1800787aa  jz      loc_180078876
0x1800787b0  test    byte ptr [rdx+6Ch], 1
0x1800787b4  jz      loc_180078876
0x1800787ba  mov     edx, eax
0x1800787bc  lea     rcx, aSyncactioncopy_2; "SyncActionCopyClientToPath: SyncActionC"...
0x1800787c3  call    SyncTraceOutputInternal
0x1800787c8  mov     edx, 66h ; 'f'
0x1800787cd  jmp     loc_18007858C
0x1800787d2  mov     rcx, [rbp+FileHandle]; FileHandle
0x1800787d6  call    SyncUnSetFileDeleted
0x1800787db  mov     ebx, eax
0x1800787dd  test    eax, eax
0x1800787df  jz      loc_1800784FF
0x1800787e5  mov     rdx, cs:WPP_GLOBAL_Control
0x1800787ec  cmp     rdx, r13
0x1800787ef  jz      loc_180078876
0x1800787f5  test    byte ptr [rdx+6Ch], 1
0x1800787f9  jz      short loc_180078876
0x1800787fb  mov     edx, eax
0x1800787fd  lea     rcx, aSyncactioncopy_30; "SyncActionCopyClientToPath: SyncUnSetFi"...
0x180078804  call    SyncTraceOutputInternal
0x180078809  mov     edx, 67h ; 'g'
0x18007880e  jmp     loc_18007858C
0x180078813  mov     rdx, cs:WPP_GLOBAL_Control
0x18007881a  cmp     rdx, r13
0x18007881d  jz      short loc_180078871
0x18007881f  test    byte ptr [rdx+6Ch], 1
0x180078823  jz      short loc_180078871
0x180078825  movzx   ebx, byte ptr [rbp+arg_0]
0x180078829  lea     rcx, aSyncactioncopy_31; "SyncActionCopyClientToPath: '%ws' has c"...
0x180078830  mov     r8d, [r15]
0x180078833  mov     r9d, ebx
0x180078836  mov     rdx, [rdi+8]
0x18007883a  call    SyncTraceOutputInternal
0x18007883f  mov     rcx, cs:WPP_GLOBAL_Control
0x180078846  lea     r8, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids
0x18007884d  mov     eax, [r15]
0x180078850  mov     edx, 62h ; 'b'
0x180078855  mov     r9, [rdi+8]
0x180078859  mov     [rsp+78h+var_50], ebx
0x18007885d  mov     rcx, [rcx+60h]
0x180078861  mov     [rsp+78h+var_58], eax
0x180078865  call    WPP_SF_SdD
0x18007886a  mov     rdx, cs:WPP_GLOBAL_Control
0x180078871  mov     ebx, 0C0000001h
0x180078876  mov     rcx, [rbp+Handle]; Handle
0x18007887a  test    rcx, rcx
0x18007887d  jz      short loc_18007888B
0x18007887f  call    SyncCloseFile
0x180078884  mov     rdx, cs:WPP_GLOBAL_Control
0x18007888b  mov     rcx, [rbp+FileHandle]; Handle
0x18007888f  test    rcx, rcx
0x180078892  jz      short loc_1800788A0
0x180078894  call    SyncCloseFile
0x180078899  mov     rdx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
