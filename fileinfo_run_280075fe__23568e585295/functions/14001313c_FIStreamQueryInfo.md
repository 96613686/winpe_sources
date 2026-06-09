# FIStreamQueryInfo

- ea: `0x14001313c`
- end: `0x140013346`
- name: `FIStreamQueryInfo`
- size: `522`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140012bd8`
- `0x140016910`

## callees

- `0x140001c00`
- `0x140001da0`
- `0x14001313c`
- `0x14001334c`
- `0x140014520`

## import_xrefs

- `ntoskrnl!PfFileInfoNotify` at `0x1400131d3`
- `ntoskrnl!PfFileInfoNotify` at `0x1400131d3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400132fb`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001331f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400132fb`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001331f`
- `FLTMGR!FltGetFileNameInformation` at `0x140013258`
- `FLTMGR!FltGetFileNameInformation` at `0x140013258`
- `FLTMGR!FltIsDirectory` at `0x1400132aa`
- `FLTMGR!FltIsDirectory` at `0x1400132aa`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140013274`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140013274`

## pseudocode

```c
__int64 __fastcall FIStreamQueryInfo(
        PFLT_CALLBACK_DATA CallbackData,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        unsigned int a4,
        _DWORD *a5)
{
  struct _FLT_CALLBACK_DATA *v5; // rbx
  int v6; // r14d
  char v7; // r13
  FLT_FILE_NAME_OPTIONS v9; // edi
  _DWORD *v10; // rsi
  unsigned int v11; // r15d
  NTSTATUS v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // eax
  PFLT_FILE_NAME_INFORMATION FileNameInformation[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v18; // [rsp+30h] [rbp-20h]
  _DWORD v19[3]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v20; // [rsp+44h] [rbp-Ch]
  int v21; // [rsp+4Ch] [rbp-4h]
  unsigned __int8 IsDirectory; // [rsp+A8h] [rbp+58h] BYREF

  IsDirectory = 0;
  v5 = CallbackData;
  v18 = 0;
  v6 = (a4 >> 2) & 1;
  v7 = a4;
  *(_OWORD *)FileNameInformation = 0;
  v9 = FIGetFileNameOptions(a3);
  if ( (v7 & 2) != 0 )
    v9 = v9 & 0xFFFFF8FF | 0x200;
  v10 = a5;
  while ( 1 )
  {
    if ( (v10[14] & 0x40) != 0 )
    {
      v11 = v10[16];
      v20 = 0;
      v21 = 0;
      v19[0] = 15;
      v19[1] = 7;
      v19[2] = 8;
      PfFileInfoNotify(v19);
      LODWORD(v18) = HIDWORD(v20);
      HIDWORD(FileNameInformation[1]) = dword_1400093D0
                                      + ((((MEMORY[0xFFFFF78000000004] * HIDWORD(MEMORY[0xFFFFF78000000320])) << 8)
                                        + ((MEMORY[0xFFFFF78000000004] * (unsigned __int64)MEMORY[0xFFFFF78000000320]) >> 24)) >> 10);
    }
    else
    {
      FILockSharedAcquire(v10 + 10);
      v11 = v10[16];
      HIDWORD(FileNameInformation[1]) = v10[15];
      LODWORD(v18) = v11;
      FILockExclusiveRelease(v10 + 10);
      v5 = CallbackData;
    }
    v12 = v5
        ? FltGetFileNameInformation(v5, v9, FileNameInformation)
        : FltGetFileNameInformationUnsafe(a3, a2, v9, FileNameInformation);
    v13 = v12;
    if ( v12 >= 0 )
    {
      if ( v6 )
      {
        FltIsDirectory(a3, a2, &IsDirectory);
        v14 = LODWORD(FileNameInformation[1]) | 8;
        LODWORD(FileNameInformation[1]) |= 8u;
        if ( IsDirectory )
          LODWORD(FileNameInformation[1]) = v14 | 4;
        v6 = 0;
      }
    }
    else
    {
      if ( (v7 & 1) != 0 )
        goto LABEL_22;
      FileNameInformation[0] = 0;
    }
    v15 = FIStreamSetFileInfo(v10, FileNameInformation, v11);
    v13 = v15;
    if ( v15 >= 0 )
      break;
    if ( v15 != -1073741267 )
      goto LABEL_22;
    v5 = CallbackData;
    if ( FileNameInformation[0] )
    {
      FltReleaseFileNameInformation(FileNameInformation[0]);
      FileNameInformation[0] = 0;
    }
  }
  v13 = 0;
LABEL_22:
  if ( FileNameInformation[0] )
    FltReleaseFileNameInformation(FileNameInformation[0]);
  return v13;
}

```

## disassembly

```asm
0x14001313c  mov     [rsp-38h+arg_10], rbx
0x140013141  mov     [rsp-38h+Instance], rdx
0x140013146  mov     [rsp-38h+arg_0], rcx
0x14001314b  push    rbp
0x14001314c  push    rsi
0x14001314d  push    rdi
0x14001314e  push    r12
0x140013150  push    r13
0x140013152  push    r14
0x140013154  push    r15
0x140013156  mov     rbp, rsp
0x140013159  sub     rsp, 50h
0x14001315d  mov     r14d, r9d
0x140013160  mov     [rbp+IsDirectory], 0
0x140013164  mov     rbx, rcx
0x140013167  shr     r14d, 2
0x14001316b  xorps   xmm0, xmm0
0x14001316e  xor     eax, eax
0x140013170  mov     rcx, r8
0x140013173  mov     [rbp+var_20], rax
0x140013177  and     r14d, 1
0x14001317b  mov     r13d, r9d
0x14001317e  mov     r12, r8
0x140013181  movups  xmmword ptr [rbp+FileNameInformation], xmm0
0x140013185  call    FIGetFileNameOptions
0x14001318a  mov     edi, eax
0x14001318c  test    r13b, 2
0x140013190  jz      short loc_14001319C
0x140013192  and     edi, 0FFFFFAFFh
0x140013198  bts     edi, 9
0x14001319c  mov     rsi, [rbp+arg_20]
0x1400131a0  mov     eax, [rsi+38h]
0x1400131a3  test    al, 40h
0x1400131a5  jz      short loc_140013226
0x1400131a7  mov     r15d, [rsi+40h]
0x1400131ab  lea     rcx, [rbp+var_18]
0x1400131af  mov     [rbp+var_C], 0
0x1400131b7  mov     [rbp+var_4], 0
0x1400131be  mov     [rbp+var_18], 0Fh
0x1400131c5  mov     [rbp+var_14], 7
0x1400131cc  mov     [rbp+var_10], 8
0x1400131d3  call    cs:__imp_PfFileInfoNotify
0x1400131da  nop     dword ptr [rax+rax+00h]
0x1400131df  mov     eax, dword ptr [rbp+var_C+4]
0x1400131e2  mov     rcx, 0FFFFF78000000004h
0x1400131ec  mov     dword ptr [rbp+var_20], eax
0x1400131ef  mov     rax, 0FFFFF78000000320h
0x1400131f9  mov     rax, [rax]
0x1400131fc  mov     ecx, [rcx]
0x1400131fe  mov     edx, eax
0x140013200  imul    rdx, rcx
0x140013204  shr     rax, 20h
0x140013208  shr     rdx, 18h
0x14001320c  imul    rax, rcx
0x140013210  shl     rax, 8
0x140013214  add     rdx, rax
0x140013217  shr     rdx, 0Ah
0x14001321b  add     edx, cs:dword_1400093D0
0x140013221  mov     dword ptr [rbp+FileNameInformation+0Ch], edx
0x140013224  jmp     short loc_14001324A
0x140013226  lea     rcx, [rsi+28h]
0x14001322a  call    FILockSharedAcquire
0x14001322f  mov     eax, [rsi+3Ch]
0x140013232  lea     rcx, [rsi+28h]
0x140013236  mov     r15d, [rsi+40h]
0x14001323a  mov     dword ptr [rbp+FileNameInformation+0Ch], eax
0x14001323d  mov     dword ptr [rbp+var_20], r15d
0x140013241  call    FILockExclusiveRelease
0x140013246  mov     rbx, [rbp+arg_0]
0x14001324a  test    rbx, rbx
0x14001324d  jz      short loc_140013266
0x14001324f  lea     r8, [rbp+FileNameInformation]; FileNameInformation
0x140013253  mov     edx, edi; NameOptions
0x140013255  mov     rcx, rbx; CallbackData
0x140013258  call    cs:__imp_FltGetFileNameInformation
0x14001325f  nop     dword ptr [rax+rax+00h]
0x140013264  jmp     short loc_140013280
0x140013266  mov     rdx, [rbp+Instance]; Instance
0x14001326a  lea     r9, [rbp+FileNameInformation]; FileNameInformation
0x14001326e  mov     r8d, edi; NameOptions
0x140013271  mov     rcx, r12; FileObject
0x140013274  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14001327b  nop     dword ptr [rax+rax+00h]
0x140013280  mov     ebx, eax
0x140013282  test    eax, eax
0x140013284  jns     short loc_14001329A
0x140013286  test    r13b, 1
0x14001328a  jnz     loc_140013316
0x140013290  mov     [rbp+FileNameInformation], 0
0x140013298  jmp     short loc_1400132CE
0x14001329a  test    r14d, r14d
0x14001329d  jz      short loc_1400132CE
0x14001329f  mov     rdx, [rbp+Instance]; Instance
0x1400132a3  lea     r8, [rbp+IsDirectory]; IsDirectory
0x1400132a7  mov     rcx, r12; FileObject
0x1400132aa  call    cs:__imp_FltIsDirectory
0x1400132b1  nop     dword ptr [rax+rax+00h]
0x1400132b6  mov     eax, dword ptr [rbp+FileNameInformation+8]
0x1400132b9  or      eax, 8
0x1400132bc  cmp     [rbp+IsDirectory], 0
0x1400132c0  mov     dword ptr [rbp+FileNameInformation+8], eax
0x1400132c3  jz      short loc_1400132CB
0x1400132c5  or      eax, 4
0x1400132c8  mov     dword ptr [rbp+FileNameInformation+8], eax
0x1400132cb  xor     r14d, r14d
0x1400132ce  mov     r8d, r15d
0x1400132d1  lea     rdx, [rbp+FileNameInformation]
0x1400132d5  mov     rcx, rsi
0x1400132d8  call    FIStreamSetFileInfo
0x1400132dd  mov     ebx, eax
0x1400132df  test    eax, eax
0x1400132e1  jns     short loc_140013314
0x1400132e3  cmp     eax, 0C000022Dh
0x1400132e8  jnz     short loc_140013316
0x1400132ea  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x1400132ee  mov     rbx, [rbp+arg_0]
0x1400132f2  test    rcx, rcx
0x1400132f5  jz      loc_1400131A0
0x1400132fb  call    cs:__imp_FltReleaseFileNameInformation
0x140013302  nop     dword ptr [rax+rax+00h]
0x140013307  mov     [rbp+FileNameInformation], 0
0x14001330f  jmp     loc_1400131A0
0x140013314  xor     ebx, ebx
0x140013316  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x14001331a  test    rcx, rcx
0x14001331d  jz      short loc_14001332B
0x14001331f  call    cs:__imp_FltReleaseFileNameInformation
0x140013326  nop     dword ptr [rax+rax+00h]
0x14001332b  mov     eax, ebx
0x14001332d  mov     rbx, [rsp+50h+arg_10]
0x140013335  add     rsp, 50h
0x140013339  pop     r15
0x14001333b  pop     r14
0x14001333d  pop     r13
0x14001333f  pop     r12
0x140013341  pop     rdi
0x140013342  pop     rsi
0x140013343  pop     rbp
0x140013344  retn
```
