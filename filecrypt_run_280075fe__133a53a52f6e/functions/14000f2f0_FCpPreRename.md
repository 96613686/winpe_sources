# FCpPreRename

- ea: `0x14000f2f0`
- end: `0x14000f86c`
- name: `FCpPreRename`
- size: `1404`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000f2c0`

## callees

- `0x140002fd0`
- `0x140003134`
- `0x14000f2f0`
- `0x14000f880`
- `0x14000f960`
- `0x1400101c0`
- `0x140010250`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f4b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f5f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f797`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f7bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013725`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f4b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f5f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f797`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f7bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013725`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000f48e`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000f5d3`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000f48e`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000f5d3`
- `FLTMGR!FltGetStreamContext` at `0x14000f3be`
- `FLTMGR!FltGetStreamContext` at `0x14000f3be`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000f7d2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000f806`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001367f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001369c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000f7d2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000f806`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001367f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001369c`
- `FLTMGR!FltGetFileNameInformation` at `0x14000f3e3`
- `FLTMGR!FltGetFileNameInformation` at `0x14000f3e3`
- `FLTMGR!FltReleaseContext` at `0x14000f70c`
- `FLTMGR!FltReleaseContext` at `0x14000f7ec`
- `FLTMGR!FltReleaseContext` at `0x140013662`
- `FLTMGR!FltReleaseContext` at `0x1400136b9`
- `FLTMGR!FltReleaseContext` at `0x14000f70c`
- `FLTMGR!FltReleaseContext` at `0x14000f7ec`
- `FLTMGR!FltReleaseContext` at `0x140013662`
- `FLTMGR!FltReleaseContext` at `0x1400136b9`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x14000f524`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x14000f524`
- `FLTMGR!FltParseFileNameInformation` at `0x14000f402`
- `FLTMGR!FltParseFileNameInformation` at `0x14000f543`
- `FLTMGR!FltParseFileNameInformation` at `0x14000f402`
- `FLTMGR!FltParseFileNameInformation` at `0x14000f543`
- `FLTMGR!FltGetVolumeContext` at `0x14000f388`
- `FLTMGR!FltGetVolumeContext` at `0x14000f388`

## pseudocode

```c
__int64 __fastcall FCpPreRename(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  void *v4; // r14
  void *v5; // r15
  char v6; // si
  char v7; // r12
  int VolumeContext; // edi
  __int64 v9; // r8
  PFLT_CONTEXT v10; // rcx
  int v11; // eax
  int v12; // edx
  int v13; // ecx
  int v14; // r9d
  unsigned int v15; // ebx
  PFLT_CONTEXT v16; // rcx
  int v18; // [rsp+48h] [rbp-F0h]
  PFLT_CONTEXT Context; // [rsp+50h] [rbp-E8h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+58h] [rbp-E0h] BYREF
  PFLT_FILE_NAME_INFORMATION RetFileNameInformation; // [rsp+60h] [rbp-D8h] BYREF
  PFLT_CONTEXT v22; // [rsp+68h] [rbp-D0h] BYREF
  void *v23; // [rsp+70h] [rbp-C8h]
  void *v24; // [rsp+78h] [rbp-C0h]
  PVOID v25[2]; // [rsp+80h] [rbp-B8h] BYREF
  PVOID v26[2]; // [rsp+90h] [rbp-A8h] BYREF
  PVOID EaBuffer; // [rsp+A0h] [rbp-98h]
  __int128 Parameter; // [rsp+A8h] [rbp-90h] BYREF
  __int128 v29; // [rsp+B8h] [rbp-80h]
  __int64 v30; // [rsp+C8h] [rbp-70h]
  PVOID P[2]; // [rsp+D0h] [rbp-68h] BYREF
  __int128 v32; // [rsp+E0h] [rbp-58h]
  __int64 v33; // [rsp+F0h] [rbp-48h]

  Context = 0;
  *(_OWORD *)v25 = 0;
  *(_OWORD *)v26 = 0;
  FileNameInformation = 0;
  RetFileNameInformation = 0;
  EaBuffer = CallbackData->Iopb->Parameters.Create.EaBuffer;
  v4 = 0;
  v23 = 0;
  v5 = 0;
  v24 = 0;
  v22 = 0;
  v6 = 0;
  v7 = 0;
  VolumeContext = FltGetVolumeContext(*(PFLT_FILTER *)(a2 + 8), *(PFLT_VOLUME *)(a2 + 16), &Context);
  if ( VolumeContext >= 0 )
  {
    v10 = Context;
    if ( !*((_BYTE *)Context + 49) )
      goto LABEL_28;
    if ( FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &v22) >= 0 )
    {
      v4 = (void *)*((_QWORD *)v22 + 3);
      v23 = v4;
      v18 = *((_DWORD *)v22 + 8);
    }
    else
    {
      VolumeContext = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
      if ( VolumeContext < 0 )
        goto LABEL_22;
      VolumeContext = FltParseFileNameInformation(FileNameInformation);
      if ( VolumeContext < 0 )
        goto LABEL_22;
      VolumeContext = FCpConstructFullPath(FileNameInformation, v25);
      if ( VolumeContext < 0 )
        goto LABEL_22;
      v6 = 1;
      v29 = 0;
      v30 = 0;
      Parameter = (unsigned __int64)v25;
      if ( KeExpandKernelStackAndCalloutEx(FCpObtainSecurityInfoCallout, &Parameter, 0x3000u, 0, 0) < 0 )
      {
        VolumeContext = FCpObtainSecurityInfoWorker((PCUNICODE_STRING)v25);
        v4 = v23;
        v11 = 0;
      }
      else
      {
        if ( *((_QWORD *)&Parameter + 1) )
          ExFreePoolWithTag(*((PVOID *)&Parameter + 1), 0x70537453u);
        v4 = (void *)v29;
        v23 = (void *)v29;
        v11 = DWORD2(v29);
        VolumeContext = v30;
      }
      v18 = v11;
      if ( VolumeContext < 0 )
        goto LABEL_22;
    }
    VolumeContext = FltGetDestinationFileNameInformation(
                      *(PFLT_INSTANCE *)(a2 + 24),
                      *(PFILE_OBJECT *)(a2 + 32),
                      *((HANDLE *)EaBuffer + 1),
                      (PWSTR)EaBuffer + 10,
                      *((_DWORD *)EaBuffer + 4),
                      0x101u,
                      &RetFileNameInformation);
    if ( VolumeContext >= 0 )
    {
      VolumeContext = FltParseFileNameInformation(RetFileNameInformation);
      if ( VolumeContext >= 0 )
      {
        VolumeContext = FCpConstructFullPath(RetFileNameInformation, v26);
        if ( VolumeContext >= 0 )
        {
          v7 = 1;
          P[1] = 0;
          v32 = 0;
          v33 = 0;
          P[0] = v26;
          if ( KeExpandKernelStackAndCalloutEx(FCpObtainSecurityInfoCallout, P, 0x3000u, 0, 0) < 0 )
          {
            VolumeContext = FCpObtainSecurityInfoWorker((PCUNICODE_STRING)v26);
            v5 = v24;
          }
          else
          {
            if ( P[1] )
              ExFreePoolWithTag(P[1], 0x70537453u);
            v5 = (void *)v32;
            v24 = (void *)v32;
            VolumeContext = v33;
          }
          if ( VolumeContext >= 0 && (!(unsigned __int8)FCpEqualChamberIds(v4, v5) || v14 != v18) )
          {
            VolumeContext = -1073741637;
            if ( (Microsoft_Windows_FileCryptEnableBits & 2) != 0 )
              McTemplateK0zzd_EtwWriteTransfer(v13, v12, v9, (_DWORD)v4, (__int64)v5, 187);
          }
        }
      }
    }
  }
LABEL_22:
  v10 = Context;
LABEL_28:
  if ( v10 )
  {
    FltReleaseContext(v10);
    Context = 0;
  }
  v15 = 1;
  if ( FileNameInformation )
  {
    FltReleaseFileNameInformation(FileNameInformation);
    FileNameInformation = 0;
  }
  if ( RetFileNameInformation )
  {
    FltReleaseFileNameInformation(RetFileNameInformation);
    RetFileNameInformation = 0;
  }
  v16 = v22;
  if ( v22 )
  {
    FltReleaseContext(v22);
    v22 = 0;
  }
  else if ( v4 )
  {
    FCpFreeChamberId(v4);
  }
  if ( v5 )
    FCpFreeChamberId(v5);
  if ( v6 )
  {
    ExFreePoolWithTag(v25[1], 0x666E4346u);
    LODWORD(v25[0]) = 0;
  }
  if ( v7 )
  {
    ExFreePoolWithTag(v26[1], 0x666E4346u);
    LODWORD(v26[0]) = 0;
  }
  if ( VolumeContext < 0 )
  {
    CallbackData->IoStatus.Status = VolumeContext;
    CallbackData->IoStatus.Information = 0;
    v15 = 4;
    if ( (Microsoft_Windows_FileCryptEnableBits & 2) != 0 )
      McTemplateK0d_EtwWriteTransfer(v16, PreRenameFailure, v9, (unsigned int)VolumeContext);
  }
  return v15;
}

```

## disassembly

```asm
0x14000f2f0  mov     r11, rsp
0x14000f2f3  mov     [r11+18h], r8
0x14000f2f7  mov     [r11+8], rcx
0x14000f2fb  push    rbx
0x14000f2fc  push    rsi
0x14000f2fd  push    rdi
0x14000f2fe  push    r12
0x14000f300  push    r13
0x14000f302  push    r14
0x14000f304  push    r15
0x14000f306  sub     rsp, 100h
0x14000f30d  mov     rbx, rdx
0x14000f310  mov     r13, rcx
0x14000f313  xor     ecx, ecx
0x14000f315  mov     [rsp+138h+Context], rcx
0x14000f31a  xorps   xmm0, xmm0
0x14000f31d  movups  xmmword ptr [rsp+138h+var_B8], xmm0
0x14000f325  xorps   xmm1, xmm1
0x14000f328  movups  xmmword ptr [rsp+138h+var_A8], xmm1
0x14000f330  mov     [rsp+138h+FileNameInformation], rcx
0x14000f335  mov     [rsp+138h+var_D8], rcx
0x14000f33a  mov     rax, [r13+10h]
0x14000f33e  mov     rax, [rax+38h]
0x14000f342  mov     [rsp+138h+var_98], rax
0x14000f34a  mov     r14d, ecx
0x14000f34d  mov     [rsp+138h+var_C8], rcx
0x14000f352  mov     r15d, ecx
0x14000f355  mov     [rsp+138h+var_C0], rcx
0x14000f35a  mov     [r11+18h], ecx
0x14000f35e  mov     [r11+20h], ecx
0x14000f362  mov     [rsp+138h+var_D0], rcx
0x14000f367  mov     [rsp+138h+var_F8], ecx
0x14000f36b  xor     sil, sil
0x14000f36e  mov     [rsp+138h+var_F4], sil
0x14000f373  xor     r12b, r12b
0x14000f376  mov     [rsp+138h+var_F3], r12b
0x14000f37b  lea     r8, [rsp+138h+Context]; Context
0x14000f380  mov     rdx, [rdx+10h]; Volume
0x14000f384  mov     rcx, [rbx+8]; Filter
0x14000f388  call    cs:__imp_FltGetVolumeContext
0x14000f38f  nop     dword ptr [rax+rax+00h]
0x14000f394  mov     edi, eax
0x14000f396  mov     [rsp+138h+var_F8], eax
0x14000f39a  test    eax, eax
0x14000f39c  js      loc_14000F64F
0x14000f3a2  mov     rcx, [rsp+138h+Context]; Context
0x14000f3a7  cmp     [rcx+31h], r12b
0x14000f3ab  jz      loc_14000F707
0x14000f3b1  lea     r8, [rsp+138h+var_D0]; Context
0x14000f3b6  mov     rdx, [rbx+20h]; FileObject
0x14000f3ba  mov     rcx, [rbx+18h]; Instance
0x14000f3be  call    cs:__imp_FltGetStreamContext
0x14000f3c5  nop     dword ptr [rax+rax+00h]
0x14000f3ca  mov     [rsp+138h+var_F8], eax
0x14000f3ce  test    eax, eax
0x14000f3d0  jns     loc_14000F6B8
0x14000f3d6  lea     r8, [rsp+138h+FileNameInformation]; FileNameInformation
0x14000f3db  mov     edx, 101h; NameOptions
0x14000f3e0  mov     rcx, r13; CallbackData
0x14000f3e3  call    cs:__imp_FltGetFileNameInformation
0x14000f3ea  nop     dword ptr [rax+rax+00h]
0x14000f3ef  mov     edi, eax
0x14000f3f1  mov     [rsp+138h+var_F8], eax
0x14000f3f5  test    eax, eax
0x14000f3f7  js      loc_14000F64F
0x14000f3fd  mov     rcx, [rsp+138h+FileNameInformation]; FileNameInformation
0x14000f402  call    cs:__imp_FltParseFileNameInformation
0x14000f409  nop     dword ptr [rax+rax+00h]
0x14000f40e  mov     edi, eax
0x14000f410  mov     [rsp+138h+var_F8], eax
0x14000f414  test    eax, eax
0x14000f416  js      loc_14000F64F
0x14000f41c  lea     rdx, [rsp+138h+var_B8]
0x14000f424  mov     rcx, [rsp+138h+FileNameInformation]
0x14000f429  call    FCpConstructFullPath
0x14000f42e  mov     edi, eax
0x14000f430  mov     [rsp+138h+var_F8], eax
0x14000f434  test    eax, eax
0x14000f436  js      loc_14000F64F
0x14000f43c  mov     sil, 1
0x14000f43f  mov     [rsp+138h+var_F4], sil
0x14000f444  xorps   xmm0, xmm0
0x14000f447  xor     eax, eax
0x14000f449  movups  [rsp+138h+Parameter], xmm0
0x14000f451  movups  [rsp+138h+var_80], xmm0
0x14000f459  mov     [rsp+138h+var_70], rax
0x14000f461  lea     rax, [rsp+138h+var_B8]
0x14000f469  mov     qword ptr [rsp+138h+Parameter], rax
0x14000f471  mov     [rsp+138h+var_118], r15; Context
0x14000f476  xor     r9d, r9d; Wait
0x14000f479  mov     r8d, 3000h; Size
0x14000f47f  lea     rdx, [rsp+138h+Parameter]; Parameter
0x14000f487  lea     rcx, FCpObtainSecurityInfoCallout; Callout
0x14000f48e  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14000f495  nop     dword ptr [rax+rax+00h]
0x14000f49a  test    eax, eax
0x14000f49c  js      loc_14000F659
0x14000f4a2  mov     rcx, qword ptr [rsp+138h+Parameter+8]; P
0x14000f4aa  test    rcx, rcx
0x14000f4ad  jz      short loc_14000F4C0
0x14000f4af  mov     edx, 70537453h; Tag
0x14000f4b4  call    cs:__imp_ExFreePoolWithTag
0x14000f4bb  nop     dword ptr [rax+rax+00h]
0x14000f4c0  mov     r14, qword ptr [rsp+138h+var_80]
0x14000f4c8  mov     [rsp+138h+var_C8], r14
0x14000f4cd  mov     eax, dword ptr [rsp+138h+var_80+8]
0x14000f4d4  mov     [rsp+138h+arg_10], eax
0x14000f4db  mov     edi, dword ptr [rsp+138h+var_70]
0x14000f4e2  mov     [rsp+138h+var_F0], eax
0x14000f4e6  mov     [rsp+138h+var_F8], edi
0x14000f4ea  test    edi, edi
0x14000f4ec  js      loc_14000F64F
0x14000f4f2  mov     r8, [rsp+138h+var_98]
0x14000f4fa  lea     r9, [r8+14h]; FileName
0x14000f4fe  lea     rax, [rsp+138h+var_D8]
0x14000f503  mov     [rsp+138h+RetFileNameInformation], rax; RetFileNameInformation
0x14000f508  mov     [rsp+138h+NameOptions], 101h; NameOptions
0x14000f510  mov     eax, [r8+10h]
0x14000f514  mov     dword ptr [rsp+138h+var_118], eax; FileNameLength
0x14000f518  mov     r8, [r8+8]; RootDirectory
0x14000f51c  mov     rdx, [rbx+20h]; FileObject
0x14000f520  mov     rcx, [rbx+18h]; Instance
0x14000f524  call    cs:__imp_FltGetDestinationFileNameInformation
0x14000f52b  nop     dword ptr [rax+rax+00h]
0x14000f530  mov     edi, eax
0x14000f532  mov     [rsp+138h+var_F8], eax
0x14000f536  test    eax, eax
0x14000f538  js      loc_14000F64F
0x14000f53e  mov     rcx, [rsp+138h+var_D8]; FileNameInformation
0x14000f543  call    cs:__imp_FltParseFileNameInformation
0x14000f54a  nop     dword ptr [rax+rax+00h]
0x14000f54f  mov     edi, eax
0x14000f551  mov     [rsp+138h+var_F8], eax
0x14000f555  test    eax, eax
0x14000f557  js      loc_14000F64F
0x14000f55d  lea     rdx, [rsp+138h+var_A8]
0x14000f565  mov     rcx, [rsp+138h+var_D8]
0x14000f56a  call    FCpConstructFullPath
0x14000f56f  mov     edi, eax
0x14000f571  mov     [rsp+138h+var_F8], eax
0x14000f575  test    eax, eax
0x14000f577  js      loc_14000F64F
0x14000f57d  mov     r12b, 1
0x14000f580  mov     [rsp+138h+var_F3], r12b
0x14000f585  xorps   xmm0, xmm0
0x14000f588  xor     eax, eax
0x14000f58a  movups  xmmword ptr [rsp+138h+P], xmm0
0x14000f592  movups  [rsp+138h+var_58], xmm0
0x14000f59a  mov     [rsp+138h+var_48], rax
0x14000f5a2  lea     rax, [rsp+138h+var_A8]
0x14000f5aa  mov     [rsp+138h+P], rax
0x14000f5b2  mov     [rsp+138h+var_118], 0; Context
0x14000f5bb  xor     r9d, r9d; Wait
0x14000f5be  mov     r8d, 3000h; Size
0x14000f5c4  lea     rdx, [rsp+138h+P]; Parameter
0x14000f5cc  lea     rcx, FCpObtainSecurityInfoCallout; Callout
0x14000f5d3  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14000f5da  nop     dword ptr [rax+rax+00h]
0x14000f5df  test    eax, eax
0x14000f5e1  js      loc_14000F688
0x14000f5e7  mov     rcx, [rsp+138h+P+8]; P
0x14000f5ef  test    rcx, rcx
0x14000f5f2  jz      short loc_14000F605
0x14000f5f4  mov     edx, 70537453h; Tag
0x14000f5f9  call    cs:__imp_ExFreePoolWithTag
0x14000f600  nop     dword ptr [rax+rax+00h]
0x14000f605  mov     r15, qword ptr [rsp+138h+var_58]
0x14000f60d  mov     [rsp+138h+var_C0], r15
0x14000f612  mov     r9d, dword ptr [rsp+138h+var_58+8]
0x14000f61a  mov     [rsp+138h+arg_18], r9d
0x14000f622  mov     edi, dword ptr [rsp+138h+var_48]
0x14000f629  mov     [rsp+138h+var_F8], edi
0x14000f62d  test    edi, edi
0x14000f62f  js      short loc_14000F64F
0x14000f631  mov     rdx, r15
0x14000f634  mov     rcx, r14
0x14000f637  call    FCpEqualChamberIds
0x14000f63c  test    al, al
0x14000f63e  jz      loc_14000F6D9
0x14000f644  cmp     r9d, [rsp+138h+var_F0]
0x14000f649  jnz     loc_14000F6D9
0x14000f64f  mov     rcx, [rsp+138h+Context]
0x14000f654  jmp     loc_14000F707
0x14000f659  lea     r9, [rsp+138h+arg_10]
0x14000f661  lea     r8, [rsp+138h+var_C8]
0x14000f666  xor     edx, edx
0x14000f668  lea     rcx, [rsp+138h+var_B8]; String2
0x14000f670  call    FCpObtainSecurityInfoWorker
0x14000f675  mov     edi, eax
0x14000f677  mov     r14, [rsp+138h+var_C8]
0x14000f67c  mov     eax, [rsp+138h+arg_10]
0x14000f683  jmp     loc_14000F4E2
0x14000f688  lea     r9, [rsp+138h+arg_18]
0x14000f690  lea     r8, [rsp+138h+var_C0]
0x14000f695  xor     edx, edx
0x14000f697  lea     rcx, [rsp+138h+var_A8]; String2
0x14000f69f  call    FCpObtainSecurityInfoWorker
0x14000f6a4  mov     edi, eax
0x14000f6a6  mov     r15, [rsp+138h+var_C0]
0x14000f6ab  mov     r9d, [rsp+138h+arg_18]
0x14000f6b3  jmp     loc_14000F629
0x14000f6b8  mov     rax, [rsp+138h+var_D0]
0x14000f6bd  mov     r14, [rax+18h]
0x14000f6c1  mov     [rsp+138h+var_C8], r14
0x14000f6c6  mov     eax, [rax+20h]
0x14000f6c9  mov     [rsp+138h+var_F0], eax
0x14000f6cd  mov     [rsp+138h+arg_10], eax
0x14000f6d4  jmp     loc_14000F4F2
0x14000f6d9  mov     edi, 0C00000BBh
0x14000f6de  mov     [rsp+138h+var_F8], edi
0x14000f6e2  movzx   eax, byte ptr cs:Microsoft_Windows_FileCryptEnableBits
0x14000f6e9  test    al, 2
0x14000f6eb  jz      loc_14000F64F
0x14000f6f1  mov     [rsp+138h+NameOptions], edi
0x14000f6f5  mov     [rsp+138h+var_118], r15
0x14000f6fa  mov     r9, r14
0x14000f6fd  call    McTemplateK0zzd_EtwWriteTransfer
0x14000f702  jmp     loc_14000F64F
0x14000f707  test    rcx, rcx
0x14000f70a  jz      short loc_14000F721
0x14000f70c  call    cs:__imp_FltReleaseContext
0x14000f713  nop     dword ptr [rax+rax+00h]
0x14000f718  mov     [rsp+138h+Context], 0
0x14000f721  mov     ebx, 1
0x14000f726  mov     rcx, [rsp+138h+FileNameInformation]; FileNameInformation
0x14000f72b  test    rcx, rcx
0x14000f72e  jnz     loc_14000F806
0x14000f734  mov     rcx, [rsp+138h+var_D8]; FileNameInformation
0x14000f739  test    rcx, rcx
0x14000f73c  jnz     loc_14000F7D2
0x14000f742  mov     rcx, [rsp+138h+var_D0]; Context
0x14000f747  test    rcx, rcx
0x14000f74a  jnz     loc_14000F7EC
0x14000f750  test    r14, r14
0x14000f753  jnz     loc_14000F820
0x14000f759  test    r15, r15
0x14000f75c  jnz     loc_14000F82D
0x14000f762  test    sil, sil
0x14000f765  jnz     short loc_14000F78A
0x14000f767  test    r12b, r12b
0x14000f76a  jnz     short loc_14000F7AE
0x14000f76c  test    edi, edi
0x14000f76e  js      loc_14000F83A
0x14000f774  mov     eax, ebx
0x14000f776  add     rsp, 100h
0x14000f77d  pop     r15
0x14000f77f  pop     r14
0x14000f781  pop     r13
0x14000f783  pop     r12
0x14000f785  pop     rdi
0x14000f786  pop     rsi
0x14000f787  pop     rbx
0x14000f788  retn
0x14000f78a  mov     edx, 666E4346h; Tag
0x14000f78f  mov     rcx, [rsp+138h+var_B8+8]; P
0x14000f797  call    cs:__imp_ExFreePoolWithTag
0x14000f79e  nop     dword ptr [rax+rax+00h]
0x14000f7a3  xor     eax, eax
0x14000f7a5  mov     dword ptr [rsp+138h+var_B8], eax
0x14000f7ac  jmp     short loc_14000F767
0x14000f7ae  mov     edx, 666E4346h; Tag
0x14000f7b3  mov     rcx, [rsp+138h+var_A8+8]; P
0x14000f7bb  call    cs:__imp_ExFreePoolWithTag
0x14000f7c2  nop     dword ptr [rax+rax+00h]
0x14000f7c7  xor     eax, eax
0x14000f7c9  mov     dword ptr [rsp+138h+var_A8], eax
0x14000f7d0  jmp     short loc_14000F76C
0x14000f7d2  call    cs:__imp_FltReleaseFileNameInformation
0x14000f7d9  nop     dword ptr [rax+rax+00h]
0x14000f7de  mov     [rsp+138h+var_D8], 0
0x14000f7e7  jmp     loc_14000F742
0x14000f7ec  call    cs:__imp_FltReleaseContext
0x14000f7f3  nop     dword ptr [rax+rax+00h]
0x14000f7f8  mov     [rsp+138h+var_D0], 0
0x14000f801  jmp     loc_14000F759
0x14000f806  call    cs:__imp_FltReleaseFileNameInformation
0x14000f80d  nop     dword ptr [rax+rax+00h]
0x14000f812  mov     [rsp+138h+FileNameInformation], 0
0x14000f81b  jmp     loc_14000F734
0x14000f820  mov     rcx, r14; P
0x14000f823  call    FCpFreeChamberId
0x14000f828  jmp     loc_14000F759
0x14000f82d  mov     rcx, r15; P
0x14000f830  call    FCpFreeChamberId
0x14000f835  jmp     loc_14000F762
0x14000f83a  mov     [r13+18h], edi
0x14000f83e  mov     qword ptr [r13+20h], 0
0x14000f846  mov     ebx, 4
0x14000f84b  test    byte ptr cs:Microsoft_Windows_FileCryptEnableBits, 2
0x14000f852  jz      loc_14000F774
0x14000f858  mov     r9d, edi
0x14000f85b  lea     rdx, PreRenameFailure
0x14000f862  call    McTemplateK0d_EtwWriteTransfer
0x14000f867  jmp     loc_14000F774
0x140013650  push    rbp
0x140013652  sub     rsp, 40h
0x140013656  mov     rbp, rdx
0x140013659  mov     rcx, [rbp+50h]; Context
0x14001365d  test    rcx, rcx
0x140013660  jz      short loc_140013676
  ... truncated ...
```
