# LuafvCreateStoreRootPathWorker

- ea: `0x1400173b0`
- end: `0x1400175d4`
- name: `LuafvCreateStoreRootPathWorker`
- size: `548`
- prototype: `void __fastcall(PFLT_GENERIC_WORKITEM FltWorkItem, struct _FLT_INSTANCE *FltObject, char *Context)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x140017190`
- `0x1400173b0`
- `0x14001dd90`
- `0x1400218d8`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400175b9`
- `ntoskrnl!KeSetEvent` at `0x1400175b9`
- `ntoskrnl!SeExports` at `0x14001744a`
- `FLTMGR!FltReleaseContext` at `0x1400175a0`
- `FLTMGR!FltReleaseContext` at `0x1400175a0`
- `FLTMGR!FltGetInstanceContext` at `0x1400173fd`
- `FLTMGR!FltGetInstanceContext` at `0x1400173fd`
- `FLTMGR!FltClose` at `0x14001757f`
- `FLTMGR!FltClose` at `0x14001757f`
- `FLTMGR!FltCreateFileEx2` at `0x140017557`
- `FLTMGR!FltCreateFileEx2` at `0x140017557`

## pseudocode

```c
void __fastcall LuafvCreateStoreRootPathWorker(
        PFLT_GENERIC_WORKITEM FltWorkItem,
        struct _FLT_INSTANCE *FltObject,
        char *Context)
{
  NTSTATUS InstanceContext; // ebx
  __int64 v6; // rcx
  __int64 v7; // rdx
  PSID SeAliasAdminsSid; // r8
  void *v9; // rsi
  void **v10; // rcx
  __int128 v11; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  PSID SeLocalSystemSid; // [rsp+C0h] [rbp-40h] BYREF
  int v14; // [rsp+C8h] [rbp-38h]
  int v15; // [rsp+CCh] [rbp-34h]
  PSID v16; // [rsp+D0h] [rbp-30h]
  int v17; // [rsp+D8h] [rbp-28h]
  int v18; // [rsp+DCh] [rbp-24h]
  PSID SeWorldSid; // [rsp+E0h] [rbp-20h]
  int v20; // [rsp+E8h] [rbp-18h]
  int v21; // [rsp+ECh] [rbp-14h]
  _QWORD v22[2]; // [rsp+F0h] [rbp-10h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp+0h] BYREF
  void *FileHandle; // [rsp+148h] [rbp+48h] BYREF
  PFLT_CONTEXT Contexta; // [rsp+150h] [rbp+50h] BYREF
  void *v26; // [rsp+158h] [rbp+58h] BYREF

  Contexta = 0;
  FileHandle = 0;
  v26 = 0;
  v11 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  InstanceContext = FltGetInstanceContext(FltObject, &Contexta);
  if ( InstanceContext >= 0 )
  {
    v6 = *((_QWORD *)Contexta + 3);
    v22[1] = &LuafvStoreRoot;
    v22[0] = v6 + 56;
    InstanceContext = LuafvAllocateAndBuildString(v22, 2, &v11);
    if ( InstanceContext >= 0 )
    {
      v14 = 3;
      v17 = 3;
      v20 = 0;
      v21 = 1179817;
      SeAliasAdminsSid = SeExports->SeAliasAdminsSid;
      SeLocalSystemSid = SeExports->SeLocalSystemSid;
      v15 = 0x1FFFFF;
      v18 = 0x1FFFFF;
      SeWorldSid = SeExports->SeWorldSid;
      v16 = SeAliasAdminsSid;
      InstanceContext = LuafvBuildSecurityDescriptor(&SeLocalSystemSid, v7, SeAliasAdminsSid, &v26);
      if ( InstanceContext >= 0 )
      {
        v9 = v26;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&v11;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        ObjectAttributes.SecurityDescriptor = v26;
        ObjectAttributes.SecurityQualityOfService = 0;
        InstanceContext = FltCreateFileEx2(
                            LuafvDriverData,
                            FltObject,
                            &FileHandle,
                            0,
                            0x1C0100u,
                            &ObjectAttributes,
                            &IoStatusBlock,
                            0,
                            0x12u,
                            7u,
                            3u,
                            0x4021u,
                            0,
                            0,
                            0x900u,
                            0);
        if ( InstanceContext >= 0 )
        {
          v10 = (void **)*((_QWORD *)Context + 1);
          if ( v10 )
            *v10 = FileHandle;
          else
            FltClose(FileHandle);
        }
        LuafvFreePool(v9);
      }
      LuafvFreePool(*((_QWORD *)&v11 + 1));
    }
    FltReleaseContext(Contexta);
  }
  *(_DWORD *)Context = InstanceContext;
  KeSetEvent((PRKEVENT)(Context + 16), 1, 0);
}

```

## disassembly

```asm
0x1400173b0  push    rbp
0x1400173b2  push    rbx
0x1400173b3  push    rsi
0x1400173b4  push    rdi
0x1400173b5  push    r14
0x1400173b7  lea     rbp, [rsp-10h]
0x1400173bc  sub     rsp, 110h
0x1400173c3  xorps   xmm0, xmm0
0x1400173c6  mov     [rbp+30h+Context], 0
0x1400173ce  mov     r14, rdx
0x1400173d1  mov     [rbp+30h+FileHandle], 0
0x1400173d9  xor     eax, eax
0x1400173db  lea     rdx, [rbp+30h+Context]; Context
0x1400173df  movups  xmmword ptr [rbp+30h+var_A0.ObjectName], xmm0
0x1400173e3  mov     rcx, r14; Instance
0x1400173e6  mov     [rbp+30h+arg_18], rax
0x1400173ea  movups  xmmword ptr [rbp+30h+var_A0+1Ch], xmm0
0x1400173ee  mov     rdi, r8
0x1400173f1  movups  [rbp+30h+var_B0], xmm0
0x1400173f5  movups  xmmword ptr [rbp+30h+var_A0.Length], xmm0
0x1400173f9  movups  xmmword ptr [rbp+30h+var_30], xmm0
0x1400173fd  call    cs:__imp_FltGetInstanceContext
0x140017404  nop     dword ptr [rax+rax+00h]
0x140017409  mov     ebx, eax
0x14001740b  test    eax, eax
0x14001740d  js      loc_1400175AC
0x140017413  mov     rax, [rbp+30h+Context]
0x140017417  lea     r8, [rbp+30h+var_B0]
0x14001741b  mov     edx, 2
0x140017420  mov     rcx, [rax+18h]
0x140017424  lea     rax, LuafvStoreRoot
0x14001742b  add     rcx, 38h ; '8'
0x14001742f  mov     [rbp+30h+var_38], rax
0x140017433  mov     [rbp+30h+var_40], rcx
0x140017437  lea     rcx, [rbp+30h+var_40]
0x14001743b  call    LuafvAllocateAndBuildString
0x140017440  mov     ebx, eax
0x140017442  test    eax, eax
0x140017444  js      loc_14001759C
0x14001744a  mov     rax, cs:__imp_SeExports
0x140017451  lea     r9, [rbp+30h+arg_18]
0x140017455  mov     [rbp+30h+var_68], 3
0x14001745c  mov     [rbp+30h+var_58], 3
0x140017463  mov     [rbp+30h+var_48], 0
0x14001746a  mov     rcx, [rax]
0x14001746d  mov     [rbp+30h+var_44], 1200A9h
0x140017474  mov     rax, [rcx+108h]
0x14001747b  mov     r8, [rcx+110h]
0x140017482  mov     [rbp+30h+var_70], rax
0x140017486  mov     eax, 1FFFFFh
0x14001748b  mov     [rbp+30h+var_64], eax
0x14001748e  mov     [rbp+30h+var_54], eax
0x140017491  mov     rax, [rcx+0C0h]
0x140017498  lea     rcx, [rbp+30h+var_70]
0x14001749c  mov     [rbp+30h+var_50], rax
0x1400174a0  mov     [rbp+30h+var_60], r8
0x1400174a4  call    LuafvBuildSecurityDescriptor
0x1400174a9  mov     ebx, eax
0x1400174ab  test    eax, eax
0x1400174ad  js      loc_140017593
0x1400174b3  mov     rsi, [rbp+30h+arg_18]
0x1400174b7  lea     rax, [rbp+30h+var_B0]
0x1400174bb  mov     rcx, cs:LuafvDriverData; Filter
0x1400174c2  lea     r8, [rbp+30h+FileHandle]; FileHandle
0x1400174c6  mov     [rsp+130h+DriverContext], 0; DriverContext
0x1400174cf  xor     r9d, r9d; FileObject
0x1400174d2  mov     [rsp+130h+Flags], 900h; Flags
0x1400174da  mov     rdx, r14; Instance
0x1400174dd  mov     [rsp+130h+EaLength], 0; EaLength
0x1400174e5  mov     [rsp+130h+EaBuffer], 0; EaBuffer
0x1400174ee  mov     [rsp+130h+CreateOptions], 4021h; CreateOptions
0x1400174f6  mov     [rsp+130h+CreateDisposition], 3; CreateDisposition
0x1400174fe  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x140017506  mov     [rsp+130h+FileAttributes], 12h; FileAttributes
0x14001750e  mov     [rbp+30h+var_A0.ObjectName], rax
0x140017512  lea     rax, [rbp+30h+var_30]
0x140017516  mov     [rsp+130h+AllocationSize], 0; AllocationSize
0x14001751f  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x140017524  lea     rax, [rbp+30h+var_A0]
0x140017528  mov     [rsp+130h+ObjectAttributes], rax; ObjectAttributes
0x14001752d  mov     [rsp+130h+DesiredAccess], 1C0100h; DesiredAccess
0x140017535  mov     [rbp+30h+var_A0.Length], 30h ; '0'
0x14001753c  mov     [rbp+30h+var_A0.RootDirectory], 0
0x140017544  mov     [rbp+30h+var_A0.Attributes], 240h
0x14001754b  mov     [rbp+30h+var_A0.SecurityDescriptor], rsi
0x14001754f  mov     [rbp+30h+var_A0.SecurityQualityOfService], 0
0x140017557  call    cs:__imp_FltCreateFileEx2
0x14001755e  nop     dword ptr [rax+rax+00h]
0x140017563  mov     ebx, eax
0x140017565  test    eax, eax
0x140017567  js      short loc_14001758B
0x140017569  mov     rcx, [rdi+8]
0x14001756d  test    rcx, rcx
0x140017570  jz      short loc_14001757B
0x140017572  mov     rax, [rbp+30h+FileHandle]
0x140017576  mov     [rcx], rax
0x140017579  jmp     short loc_14001758B
0x14001757b  mov     rcx, [rbp+30h+FileHandle]; FileHandle
0x14001757f  call    cs:__imp_FltClose
0x140017586  nop     dword ptr [rax+rax+00h]
0x14001758b  mov     rcx, rsi
0x14001758e  call    LuafvFreePool
0x140017593  mov     rcx, qword ptr [rbp+30h+var_B0+8]
0x140017597  call    LuafvFreePool
0x14001759c  mov     rcx, [rbp+30h+Context]; Context
0x1400175a0  call    cs:__imp_FltReleaseContext
0x1400175a7  nop     dword ptr [rax+rax+00h]
0x1400175ac  xor     r8d, r8d; Wait
0x1400175af  mov     [rdi], ebx
0x1400175b1  lea     rcx, [rdi+10h]; Event
0x1400175b5  lea     edx, [r8+1]; Increment
0x1400175b9  call    cs:__imp_KeSetEvent
0x1400175c0  nop     dword ptr [rax+rax+00h]
0x1400175c5  add     rsp, 110h
0x1400175cc  pop     r14
0x1400175ce  pop     rdi
0x1400175cf  pop     rsi
0x1400175d0  pop     rbx
0x1400175d1  pop     rbp
0x1400175d2  retn
```
