# PrjfOpenAndCheckEmptyPartialDirectory

- ea: `0x140007300`
- end: `0x140007525`
- name: `PrjfOpenAndCheckEmptyPartialDirectory`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x140007990`

## callees

- `0x140007300`
- `0x14000d754`
- `0x14002a6b4`
- `0x14003be88`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140007508`
- `ntoskrnl!ObfDereferenceObject` at `0x140007508`
- `FLTMGR!FltClose` at `0x1400074f3`
- `FLTMGR!FltClose` at `0x1400074f3`

## pseudocode

```c
__int64 __fastcall PrjfOpenAndCheckEmptyPartialDirectory(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        __int64 a3,
        __int64 a4,
        _BYTE *a5)
{
  int v8; // eax
  int v9; // edx
  int v10; // r8d
  __int64 v11; // r9
  unsigned int v12; // ebx
  int IsDirectoryEmpty; // eax
  int v14; // edx
  int v15; // r8d
  __int64 v17; // [rsp+20h] [rbp-60h]
  char v18; // [rsp+60h] [rbp-20h] BYREF
  char v19[7]; // [rsp+61h] [rbp-1Fh] BYREF
  PVOID Object; // [rsp+68h] [rbp-18h] BYREF
  HANDLE FileHandle; // [rsp+70h] [rbp-10h] BYREF

  FileHandle = 0;
  Object = 0;
  v18 = 0;
  v19[0] = 0;
  v8 = PrjfOpenAsReparsePoint(a3, a4, a2, 128, v17, &FileHandle, (PFILE_OBJECT *)&Object, &v18, 0, 0, 0, 0);
  v12 = v8;
  if ( v8 >= 0 )
  {
    if ( v18 )
    {
      IsDirectoryEmpty = PrjfIsDirectoryEmpty(a1, a2, (struct _FILE_OBJECT *)Object, v11, v19);
      v12 = IsDirectoryEmpty;
      if ( IsDirectoryEmpty >= 0 )
      {
        *a5 = v19[0];
      }
      else if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0
             || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 0x20;
        LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          525,
          v14,
          v15,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          13,
          118,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          185,
          IsDirectoryEmpty,
          a3);
      }
    }
    else
    {
      v12 = -1073741195;
      if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = BYTE1(xmmword_14001A3D0) & 0x20;
        LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          525,
          v9,
          v10,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          13,
          117,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          169,
          117,
          a3);
      }
    }
  }
  else if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = BYTE1(xmmword_14001A3D0) & 0x20;
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDdZ(
      525,
      v9,
      v10,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      13,
      116,
      (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
      153,
      v8,
      a3);
  }
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  return v12;
}

```

## disassembly

```asm
0x140007300  mov     r11, rsp
0x140007303  push    rbp
0x140007304  push    rbx
0x140007305  push    rsi
0x140007306  push    rdi
0x140007307  push    r14
0x140007309  mov     rbp, rsp
0x14000730c  sub     rsp, 80h
0x140007313  mov     qword ptr [r11-50h], 0
0x14000731b  mov     rsi, rcx
0x14000731e  mov     qword ptr [r11-58h], 0
0x140007326  lea     rcx, [rbp+var_20]
0x14000732a  mov     qword ptr [r11-60h], 0
0x140007332  mov     rax, r9
0x140007335  mov     qword ptr [r11-68h], 0
0x14000733d  mov     r14, r8
0x140007340  mov     [r11-70h], rcx
0x140007344  mov     rdi, rdx
0x140007347  lea     rcx, [rbp+Object]
0x14000734b  mov     [rbp+FileHandle], 0
0x140007353  mov     [r11-78h], rcx
0x140007357  mov     r8, rdx
0x14000735a  lea     rcx, [rbp+FileHandle]
0x14000735e  mov     [rbp+Object], 0
0x140007366  mov     [r11-80h], rcx
0x14000736a  mov     r9d, 80h
0x140007370  mov     rcx, r14
0x140007373  mov     [rbp+var_20], 0
0x140007377  mov     rdx, rax
0x14000737a  mov     [rbp+var_1F], 0
0x14000737e  call    PrjfOpenAsReparsePoint
0x140007383  mov     ebx, eax
0x140007385  test    eax, eax
0x140007387  jns     short loc_140007406
0x140007389  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14000738f  lea     rcx, WPP_RECORDER_INITIALIZED
0x140007396  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000739d  setnz   r8b
0x1400073a1  and     dl, 20h
0x1400073a4  jnz     short loc_1400073AF
0x1400073a6  test    r8b, r8b
0x1400073a9  jz      loc_1400074EA
0x1400073af  mov     [rsp+80h+var_28], r14
0x1400073b4  mov     [rsp+80h+var_30], eax
0x1400073b8  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400073bf  mov     [rsp+80h+var_38], 1499h
0x1400073c7  mov     [rsp+80h+var_40], rax
0x1400073cc  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x1400073d3  mov     [rsp+80h+var_48], rax
0x1400073d8  mov     [rsp+80h+var_50], 74h ; 't'
0x1400073df  mov     r9, cs:WPP_GLOBAL_Control
0x1400073e6  mov     ecx, 20Dh
0x1400073eb  mov     [rsp+80h+var_58], 0Dh
0x1400073f3  mov     byte ptr [rsp+80h+var_60], 2
0x1400073f8  mov     r9, [r9+40h]
0x1400073fc  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140007401  jmp     loc_1400074EA
0x140007406  cmp     [rbp+var_20], 0
0x14000740a  jnz     short loc_14000746C
0x14000740c  mov     ebx, 0C0000275h
0x140007411  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140007417  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000741e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140007425  setnz   r8b
0x140007429  and     dl, 20h
0x14000742c  jnz     short loc_140007437
0x14000742e  test    r8b, r8b
0x140007431  jz      loc_1400074EA
0x140007437  mov     [rsp+80h+var_28], r14
0x14000743c  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140007443  mov     [rsp+80h+var_30], ebx
0x140007447  mov     [rsp+80h+var_38], 14A9h
0x14000744f  mov     [rsp+80h+var_40], rax
0x140007454  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14000745b  mov     [rsp+80h+var_48], rax
0x140007460  mov     [rsp+80h+var_50], 75h ; 'u'
0x140007467  jmp     loc_1400073DF
0x14000746c  mov     r8, [rbp+Object]
0x140007470  lea     rax, [rbp+var_1F]
0x140007474  mov     rdx, rdi
0x140007477  mov     [rsp+80h+var_60], rax
0x14000747c  mov     rcx, rsi
0x14000747f  call    PrjfIsDirectoryEmpty
0x140007484  mov     ebx, eax
0x140007486  test    eax, eax
0x140007488  jns     short loc_1400074E1
0x14000748a  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140007490  lea     rcx, WPP_RECORDER_INITIALIZED
0x140007497  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000749e  setnz   r8b
0x1400074a2  and     dl, 20h
0x1400074a5  jnz     short loc_1400074AC
0x1400074a7  test    r8b, r8b
0x1400074aa  jz      short loc_1400074EA
0x1400074ac  mov     [rsp+80h+var_28], r14
0x1400074b1  mov     [rsp+80h+var_30], eax
0x1400074b5  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400074bc  mov     [rsp+80h+var_38], 14B9h
0x1400074c4  mov     [rsp+80h+var_40], rax
0x1400074c9  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x1400074d0  mov     [rsp+80h+var_48], rax
0x1400074d5  mov     [rsp+80h+var_50], 76h ; 'v'
0x1400074dc  jmp     loc_1400073DF
0x1400074e1  mov     rcx, [rbp+arg_20]
0x1400074e5  mov     al, [rbp+var_1F]
0x1400074e8  mov     [rcx], al
0x1400074ea  mov     rcx, [rbp+FileHandle]; FileHandle
0x1400074ee  test    rcx, rcx
0x1400074f1  jz      short loc_1400074FF
0x1400074f3  call    cs:__imp_FltClose
0x1400074fa  nop     dword ptr [rax+rax+00h]
0x1400074ff  mov     rcx, [rbp+Object]; Object
0x140007503  test    rcx, rcx
0x140007506  jz      short loc_140007514
0x140007508  call    cs:__imp_ObfDereferenceObject
0x14000750f  nop     dword ptr [rax+rax+00h]
0x140007514  mov     eax, ebx
0x140007516  add     rsp, 80h
0x14000751d  pop     r14
0x14000751f  pop     rdi
0x140007520  pop     rsi
0x140007521  pop     rbx
0x140007522  pop     rbp
0x140007523  retn
```
