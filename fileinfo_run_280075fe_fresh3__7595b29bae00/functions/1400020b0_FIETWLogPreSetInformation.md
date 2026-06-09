# FIETWLogPreSetInformation

- ea: `0x1400020b0`
- end: `0x1400024cb`
- name: `FIETWLogPreSetInformation`
- size: `1051`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140002cc0`

## callees

- `0x1400020b0`
- `0x140003920`
- `0x140003a00`
- `0x140014520`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140002165`
- `ntoskrnl!PsGetThreadId` at `0x140002326`
- `ntoskrnl!PsGetThreadId` at `0x140002165`
- `ntoskrnl!PsGetThreadId` at `0x140002326`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400024b5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400024b5`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x1400021ee`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x1400021ee`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002279`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140002279`
- `FLTMGR!FltGetFileNameInformation` at `0x140002383`
- `FLTMGR!FltGetFileNameInformation` at `0x140002383`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x140002473`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x140002473`

## pseudocode

```c
void __fastcall FIETWLogPreSetInformation(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rbx
  void (__fastcall *v5)(const PETHREAD, _QWORD **, __int64, __int64, __int16, __int128 *); // r14
  ULONG Options; // ebx
  struct _KTHREAD *Thread; // rcx
  unsigned int ThreadId; // eax
  __int16 v9; // r13
  __int16 v10; // r12
  __int128 *v11; // r15
  _DWORD *EaBuffer; // rcx
  unsigned __int8 v13; // cl
  struct _KTHREAD *v14; // rcx
  unsigned int v15; // eax
  __int64 v16; // rcx
  FLT_FILE_NAME_OPTIONS v17; // eax
  NTSTATUS DestinationFileNameInformation; // eax
  wchar_t *Buffer; // rax
  PETHREAD v20; // rcx
  PFLT_IO_PARAMETER_BLOCK v21; // rcx
  struct _FLT_INSTANCE *v22; // rdi
  PVOID v23; // r12
  struct _FILE_OBJECT *TargetFileObject; // rbx
  FLT_FILE_NAME_OPTIONS NameOptions; // eax
  int FileNameLength; // [rsp+28h] [rbp-E0h]
  ULONG v27[2]; // [rsp+48h] [rbp-C0h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-B8h] BYREF
  struct _UNICODE_STRING FileNameInformation_8; // [rsp+58h] [rbp-B0h] BYREF
  HANDLE RootDirectory; // [rsp+68h] [rbp-A0h]
  _QWORD RootDirectory_8[4]; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int64 v32; // [rsp+90h] [rbp-78h]
  __int128 v33; // [rsp+98h] [rbp-70h] BYREF
  _OWORD v34[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v35; // [rsp+C8h] [rbp-40h] BYREF
  __int128 *v36; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v37; // [rsp+E0h] [rbp-28h]
  wchar_t *v38; // [rsp+E8h] [rbp-20h]
  int Length; // [rsp+F0h] [rbp-18h]
  int v40; // [rsp+F4h] [rbp-14h]
  ULONG *v41; // [rsp+F8h] [rbp-10h]
  __int64 v42; // [rsp+100h] [rbp-8h]

  Iopb = CallbackData->Iopb;
  v32 = 0;
  FileNameInformation = 0;
  v33 = 0;
  LOWORD(v27[0]) = 0;
  memset(v34, 0, sizeof(v34));
  memset(RootDirectory_8, 0, sizeof(RootDirectory_8));
  FileNameInformation_8 = 0;
  v35 = 0;
  v5 = *(void (__fastcall **)(const PETHREAD, _QWORD **, __int64, __int64, __int16, __int128 *))(qword_140009A00 + 16);
  Options = Iopb->Parameters.Create.Options;
  if ( !v5 )
    goto LABEL_15;
  RootDirectory_8[0] = CallbackData;
  Thread = CallbackData->Thread;
  memset(&RootDirectory_8[1], 0, 24);
  v32 = 0;
  if ( Thread )
    ThreadId = (unsigned int)PsGetThreadId(Thread);
  else
    ThreadId = -1;
  v32 = __PAIR64__(Options, ThreadId);
  RootDirectory_8[1] = *(_QWORD *)(a2 + 32);
  RootDirectory_8[2] = *(_QWORD *)(RootDirectory_8[1] + 24LL);
  if ( Options != 10 )
  {
    if ( Options == 13 || Options == 64 )
    {
      v10 = 1094;
      EaBuffer = CallbackData->Iopb->Parameters.Create.EaBuffer;
      if ( Options == 64 )
        v13 = *EaBuffer & 1;
      else
        v13 = *(_BYTE *)EaBuffer;
      RootDirectory_8[3] = v13;
      v9 = v13 != 0 ? 0x44F : 0;
      goto LABEL_12;
    }
    if ( Options == 11 )
      goto LABEL_36;
    if ( Options != 65 )
    {
      if ( Options != 72 )
      {
        v9 = 0;
        v10 = 1093;
        if ( Options - 19 <= 1 )
          RootDirectory_8[3] = *(_QWORD *)CallbackData->Iopb->Parameters.Create.EaBuffer;
        goto LABEL_12;
      }
LABEL_36:
      v10 = 1106;
      v9 = 1105;
      goto LABEL_12;
    }
  }
  v10 = 1095;
  v9 = 1104;
LABEL_12:
  v37 = 40;
  v36 = (__int128 *)RootDirectory_8;
  v11 = &v35;
  if ( (int)FltGetActivityIdCallbackData(CallbackData, &v35) < 0 )
    v11 = 0;
  v5(CallbackData->Thread, (_QWORD **)&v36, 1, 0x4000000, v10, v11);
  if ( v9 )
  {
    v14 = CallbackData->Thread;
    memset(v34, 0, sizeof(v34));
    v33 = (unsigned __int64)CallbackData;
    if ( v14 )
      v15 = (unsigned int)PsGetThreadId(v14);
    else
      v15 = -1;
    v16 = *(_QWORD *)(a2 + 32);
    *(_QWORD *)&v34[1] = __PAIR64__(Options, v15);
    *((_QWORD *)&v33 + 1) = v16;
    *(_QWORD *)&v34[0] = *(_QWORD *)(v16 + 24);
    FileNameInformation_8 = 0;
    if ( Options == 10 || Options == 65 || Options == 72 || Options == 11 )
    {
      v21 = CallbackData->Iopb;
      v22 = *(struct _FLT_INSTANCE **)(a2 + 24);
      v23 = v21->Parameters.Create.EaBuffer;
      TargetFileObject = v21->TargetFileObject;
      RootDirectory = (HANDLE)*((_QWORD *)v23 + 1);
      v27[1] = *((_DWORD *)v23 + 4);
      NameOptions = FIGetFileNameOptions(v21->TargetFileObject);
      DestinationFileNameInformation = FltGetDestinationFileNameInformation(
                                         v22,
                                         TargetFileObject,
                                         RootDirectory,
                                         (PWSTR)v23 + 10,
                                         v27[1],
                                         NameOptions,
                                         &FileNameInformation);
    }
    else
    {
      v17 = FIGetFileNameOptions(v16);
      DestinationFileNameInformation = FltGetFileNameInformation(CallbackData, v17, &FileNameInformation);
    }
    if ( DestinationFileNameInformation >= 0 )
      FileNameInformation_8 = FileNameInformation->Name;
    Buffer = FileNameInformation_8.Buffer;
    if ( !FileNameInformation_8.Buffer )
    {
      RtlInitUnicodeString(&FileNameInformation_8, FIUnknown);
      Buffer = FileNameInformation_8.Buffer;
    }
    v38 = Buffer;
    Length = FileNameInformation_8.Length;
    v36 = &v33;
    v20 = CallbackData->Thread;
    LOWORD(v27[0]) = 0;
    v41 = v27;
    v37 = 40;
    v40 = 0;
    v42 = 2;
    LOWORD(FileNameLength) = v9;
    v5(v20, (_QWORD **)&v36, 3, 0x4000000, FileNameLength, v11);
  }
LABEL_15:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
}

```

## disassembly

```asm
0x1400020b0  mov     r11, rsp
0x1400020b3  push    rbp
0x1400020b4  lea     rbp, [r11-48h]
0x1400020b8  sub     rsp, 140h
0x1400020bf  mov     rax, cs:__security_cookie
0x1400020c6  xor     rax, rsp
0x1400020c9  mov     [rbp+40h+var_40], rax
0x1400020cd  mov     [r11+18h], rbx
0x1400020d1  xorps   xmm0, xmm0
0x1400020d4  mov     rbx, [rcx+10h]
0x1400020d8  xor     eax, eax
0x1400020da  mov     [rbp+40h+var_B8], rax
0x1400020de  xorps   xmm1, xmm1
0x1400020e1  mov     rax, cs:qword_140009A00
0x1400020e8  mov     [r11-10h], rsi
0x1400020ec  mov     rsi, rcx
0x1400020ef  mov     [r11-18h], rdi
0x1400020f3  mov     rdi, rdx
0x1400020f6  xor     edx, edx
0x1400020f8  mov     [r11-30h], r14
0x1400020fc  mov     [rsp+140h+FileNameInformation], rdx
0x140002101  movups  [rbp+40h+var_B0], xmm0
0x140002105  mov     word ptr [rsp+140h+var_100], dx
0x14000210a  movups  [rbp+40h+var_A0], xmm0
0x14000210e  movups  [rbp+40h+var_90], xmm0
0x140002112  movups  xmmword ptr [rsp+140h+RootDirectory+8], xmm1
0x140002117  movups  [rsp+140h+var_D0+8], xmm1
0x14000211c  movups  xmmword ptr [rsp+140h+FileNameInformation+8], xmm0
0x140002121  movups  [rbp+40h+var_80], xmm0
0x140002125  mov     r14, [rax+10h]
0x140002129  mov     ebx, [rbx+20h]
0x14000212c  test    r14, r14
0x14000212f  jz      loc_14000224F
0x140002135  mov     [r11-20h], r12
0x140002139  mov     [rsp+140h+RootDirectory+8], rcx
0x14000213e  mov     rcx, [rcx+8]; Thread
0x140002142  mov     [r11-28h], r13
0x140002146  mov     [r11-38h], r15
0x14000214a  mov     qword ptr [rsp+140h+var_D0], rdx
0x14000214f  mov     qword ptr [rsp+140h+var_D0+8], rdx
0x140002154  mov     [rbp+40h+var_C0], rdx
0x140002158  mov     [rbp+40h+var_B8], rdx
0x14000215c  test    rcx, rcx
0x14000215f  jz      loc_140002495
0x140002165  call    cs:__imp_PsGetThreadId
0x14000216c  nop     dword ptr [rax+rax+00h]
0x140002171  xor     edx, edx
0x140002173  mov     dword ptr [rbp+40h+var_B8], eax
0x140002176  mov     rax, [rdi+20h]
0x14000217a  mov     qword ptr [rsp+140h+var_D0], rax
0x14000217f  mov     rax, [rax+18h]
0x140002183  mov     qword ptr [rsp+140h+var_D0+8], rax
0x140002188  mov     dword ptr [rbp+40h+var_B8+4], ebx
0x14000218b  cmp     ebx, 0Ah
0x14000218e  jz      loc_1400022AF
0x140002194  cmp     ebx, 0Dh
0x140002197  jz      loc_1400022C0
0x14000219d  cmp     ebx, 40h ; '@'
0x1400021a0  jz      loc_1400022C0
0x1400021a6  cmp     ebx, 0Bh
0x1400021a9  jz      loc_140002484
0x1400021af  cmp     ebx, 41h ; 'A'
0x1400021b2  jz      loc_1400022AF
0x1400021b8  cmp     ebx, 48h ; 'H'
0x1400021bb  jz      loc_140002484
0x1400021c1  lea     eax, [rbx-13h]
0x1400021c4  mov     r13d, edx
0x1400021c7  mov     r12d, 445h
0x1400021cd  cmp     eax, 1
0x1400021d0  jbe     loc_14000229B
0x1400021d6  lea     rax, [rsp+140h+RootDirectory+8]
0x1400021db  mov     [rbp+40h+var_68], 28h ; '('
0x1400021e3  lea     rdx, [rbp+40h+var_80]
0x1400021e7  mov     [rbp+40h+var_70], rax
0x1400021eb  mov     rcx, rsi
0x1400021ee  call    cs:__imp_FltGetActivityIdCallbackData
0x1400021f5  nop     dword ptr [rax+rax+00h]
0x1400021fa  xor     ecx, ecx
0x1400021fc  lea     r15, [rbp+40h+var_80]
0x140002200  test    eax, eax
0x140002202  lea     rdx, [rbp+40h+var_70]
0x140002206  mov     r9d, 4000000h
0x14000220c  mov     r8d, 1
0x140002212  cmovs   r15, rcx
0x140002216  mov     rax, r14
0x140002219  mov     rcx, [rsi+8]
0x14000221d  mov     qword ptr [rsp+140h+NameOptions], r15
0x140002222  mov     word ptr [rsp+140h+FileNameLength], r12w
0x140002228  call    _guard_dispatch_icall
0x14000222d  test    r13w, r13w
0x140002231  jnz     loc_1400022F5
0x140002237  mov     r13, [rsp+140h+var_20]
0x14000223f  mov     r12, [rsp+140h+var_18]
0x140002247  mov     r15, [rsp+140h+var_30]
0x14000224f  mov     rcx, [rsp+140h+FileNameInformation]; FileNameInformation
0x140002254  mov     r14, [rsp+140h+var_28]
0x14000225c  mov     rdi, [rsp+140h+var_10]
0x140002264  mov     rsi, [rsp+138h]
0x14000226c  mov     rbx, [rsp+140h+arg_10]
0x140002274  test    rcx, rcx
0x140002277  jz      short loc_140002285
0x140002279  call    cs:__imp_FltReleaseFileNameInformation
0x140002280  nop     dword ptr [rax+rax+00h]
0x140002285  mov     rcx, [rbp+40h+var_40]
0x140002289  xor     rcx, rsp; StackCookie
0x14000228c  call    __security_check_cookie
0x140002291  add     rsp, 140h
0x140002298  pop     rbp
0x140002299  retn
0x14000229b  mov     rax, [rsi+10h]
0x14000229f  mov     rcx, [rax+38h]
0x1400022a3  mov     rax, [rcx]
0x1400022a6  mov     [rbp+40h+var_C0], rax
0x1400022aa  jmp     loc_1400021D6
0x1400022af  mov     r12d, 447h
0x1400022b5  mov     r13d, 450h
0x1400022bb  jmp     loc_1400021D6
0x1400022c0  mov     rax, [rsi+10h]
0x1400022c4  mov     r12d, 446h
0x1400022ca  mov     rcx, [rax+38h]
0x1400022ce  cmp     ebx, 40h ; '@'
0x1400022d1  jnz     loc_140002416
0x1400022d7  mov     ecx, [rcx]
0x1400022d9  and     cl, 1
0x1400022dc  movzx   eax, cl
0x1400022df  neg     cl
0x1400022e1  mov     [rbp+40h+var_C0], rax
0x1400022e5  sbb     ax, ax
0x1400022e8  and     ax, 44Fh
0x1400022ec  movzx   r13d, ax
0x1400022f0  jmp     loc_1400021D6
0x1400022f5  mov     rcx, [rsi+8]; Thread
0x1400022f9  xorps   xmm0, xmm0
0x1400022fc  mov     qword ptr [rbp+40h+var_B0+8], 0
0x140002304  mov     qword ptr [rbp+40h+var_A0], 0
0x14000230c  mov     qword ptr [rbp+40h+var_90+8], 0
0x140002314  mov     qword ptr [rbp+40h+var_B0], rsi
0x140002318  movdqu  [rbp+40h+var_A0+8], xmm0
0x14000231d  test    rcx, rcx
0x140002320  jz      loc_14000249F
0x140002326  call    cs:__imp_PsGetThreadId
0x14000232d  nop     dword ptr [rax+rax+00h]
0x140002332  mov     rcx, [rdi+20h]
0x140002336  xorps   xmm0, xmm0
0x140002339  mov     dword ptr [rbp+40h+var_90], eax
0x14000233c  mov     qword ptr [rbp+40h+var_B0+8], rcx
0x140002340  mov     rax, [rcx+18h]
0x140002344  mov     qword ptr [rbp+40h+var_A0], rax
0x140002348  mov     dword ptr [rbp+40h+var_90+4], ebx
0x14000234b  movups  xmmword ptr [rsp+140h+FileNameInformation+8], xmm0
0x140002350  cmp     ebx, 0Ah
0x140002353  jz      loc_14000241E
0x140002359  cmp     ebx, 41h ; 'A'
0x14000235c  jz      loc_14000241E
0x140002362  cmp     ebx, 48h ; 'H'
0x140002365  jz      loc_14000241E
0x14000236b  cmp     ebx, 0Bh
0x14000236e  jz      loc_14000241E
0x140002374  call    FIGetFileNameOptions
0x140002379  mov     edx, eax; NameOptions
0x14000237b  lea     r8, [rsp+140h+FileNameInformation]; FileNameInformation
0x140002380  mov     rcx, rsi; CallbackData
0x140002383  call    cs:__imp_FltGetFileNameInformation
0x14000238a  nop     dword ptr [rax+rax+00h]
0x14000238f  test    eax, eax
0x140002391  js      short loc_1400023A1
0x140002393  mov     rax, [rsp+140h+FileNameInformation]
0x140002398  movups  xmm0, xmmword ptr [rax+8]
0x14000239c  movups  xmmword ptr [rsp+140h+FileNameInformation+8], xmm0
0x1400023a1  mov     rax, [rsp+140h+var_E8]
0x1400023a6  test    rax, rax
0x1400023a9  jz      loc_1400024A9
0x1400023af  mov     [rbp+40h+var_60], rax
0x1400023b3  lea     rcx, [rbp+40h+var_B0]
0x1400023b7  movzx   eax, word ptr [rsp+140h+FileNameInformation+8]
0x1400023bc  lea     rdx, [rbp+40h+var_70]
0x1400023c0  mov     [rbp+40h+var_58], eax
0x1400023c3  mov     r9d, 4000000h
0x1400023c9  xor     eax, eax
0x1400023cb  mov     [rbp+40h+var_70], rcx
0x1400023cf  mov     rcx, [rsi+8]
0x1400023d3  mov     r8d, 3
0x1400023d9  mov     word ptr [rsp+140h+var_100], ax
0x1400023de  lea     rax, [rsp+140h+var_100]
0x1400023e3  mov     [rbp+40h+var_50], rax
0x1400023e7  mov     rax, r14
0x1400023ea  mov     qword ptr [rsp+140h+NameOptions], r15
0x1400023ef  mov     [rbp+40h+var_68], 28h ; '('
0x1400023f7  mov     [rbp+40h+var_54], 0
0x1400023fe  mov     [rbp+40h+var_48], 2
0x140002406  mov     word ptr [rsp+140h+FileNameLength], r13w
0x14000240c  call    _guard_dispatch_icall
0x140002411  jmp     loc_140002237
0x140002416  movzx   ecx, byte ptr [rcx]
0x140002419  jmp     loc_1400022DC
0x14000241e  mov     rcx, [rsi+10h]
0x140002422  mov     rdi, [rdi+18h]
0x140002426  mov     r12, [rcx+38h]
0x14000242a  mov     rbx, [rcx+8]
0x14000242e  mov     rax, [r12+8]
0x140002433  mov     [rsp+140h+RootDirectory], rax
0x140002438  mov     eax, [r12+10h]
0x14000243d  mov     [rsp+140h+var_100+4], eax
0x140002441  mov     rax, rcx
0x140002444  mov     rcx, [rcx+8]
0x140002448  call    FIGetFileNameOptions
0x14000244d  mov     r8, [rsp+140h+RootDirectory]; RootDirectory
0x140002452  lea     rcx, [rsp+140h+FileNameInformation]
0x140002457  mov     [rsp+30h], rcx; RetFileNameInformation
0x14000245c  lea     r9, [r12+14h]; FileName
0x140002461  mov     [rsp+140h+NameOptions], eax; NameOptions
0x140002465  mov     rdx, rbx; FileObject
0x140002468  mov     eax, [rsp+140h+var_100+4]
0x14000246c  mov     rcx, rdi; Instance
0x14000246f  mov     [rsp+140h+FileNameLength], eax; FileNameLength
0x140002473  call    cs:__imp_FltGetDestinationFileNameInformation
0x14000247a  nop     dword ptr [rax+rax+00h]
0x14000247f  jmp     loc_14000238F
0x140002484  mov     r12d, 452h
0x14000248a  mov     r13d, 451h
0x140002490  jmp     loc_1400021D6
0x140002495  mov     eax, 0FFFFFFFFh
0x14000249a  jmp     loc_140002173
0x14000249f  mov     eax, 0FFFFFFFFh
0x1400024a4  jmp     loc_140002332
0x1400024a9  lea     rdx, FIUnknown; "\\FI_UNKNOWN"
0x1400024b0  lea     rcx, [rsp+140h+FileNameInformation+8]; DestinationString
0x1400024b5  call    cs:__imp_RtlInitUnicodeString
0x1400024bc  nop     dword ptr [rax+rax+00h]
0x1400024c1  mov     rax, [rsp+140h+var_E8]
0x1400024c6  jmp     loc_1400023AF
```
