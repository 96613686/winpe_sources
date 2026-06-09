# LuafvCreateStoreRootPathWorker

- ea: `0x140017360`
- end: `0x140017584`
- name: `LuafvCreateStoreRootPathWorker`
- size: `548`
- prototype: `void __fastcall(PFLT_GENERIC_WORKITEM FltWorkItem, struct _FLT_INSTANCE *FltObject, char *Context)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x140017140`
- `0x140017360`
- `0x14001dd40`
- `0x140021888`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140017569`
- `ntoskrnl!KeSetEvent` at `0x140017569`
- `ntoskrnl!SeExports` at `0x1400173fa`
- `FLTMGR!FltReleaseContext` at `0x140017550`
- `FLTMGR!FltReleaseContext` at `0x140017550`
- `FLTMGR!FltGetInstanceContext` at `0x1400173ad`
- `FLTMGR!FltGetInstanceContext` at `0x1400173ad`
- `FLTMGR!FltClose` at `0x14001752f`
- `FLTMGR!FltClose` at `0x14001752f`
- `FLTMGR!FltCreateFileEx2` at `0x140017507`
- `FLTMGR!FltCreateFileEx2` at `0x140017507`

## pseudocode

```c
void __fastcall LuafvCreateStoreRootPathWorker(
        PFLT_GENERIC_WORKITEM FltWorkItem,
        struct _FLT_INSTANCE *FltObject,
        char *Context)
{
  int InstanceContext; // ebx
  __int64 v6; // rcx
  __int64 v7; // rdx
  PSID SeAliasAdminsSid; // r8
  struct _ACL *v9; // rsi
  void **v10; // rcx
  struct _UNICODE_STRING v11; // [rsp+80h] [rbp-80h] BYREF
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
  struct _ACL *v26; // [rsp+158h] [rbp+58h] BYREF

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
    InstanceContext = LuafvAllocateAndBuildString((__int64)v22, 2u, &v11);
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
      InstanceContext = LuafvBuildSecurityDescriptor((__int64)&SeLocalSystemSid, v7, SeAliasAdminsSid, &v26);
      if ( InstanceContext >= 0 )
      {
        v9 = v26;
        ObjectAttributes.ObjectName = &v11;
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
      LuafvFreePool(v11.Buffer);
    }
    FltReleaseContext(Contexta);
  }
  *(_DWORD *)Context = InstanceContext;
  KeSetEvent((PRKEVENT)(Context + 16), 1, 0);
}

```

## disassembly

```asm
0x140017360  push    rbp
0x140017362  push    rbx
0x140017363  push    rsi
0x140017364  push    rdi
0x140017365  push    r14
0x140017367  lea     rbp, [rsp-10h]
0x14001736c  sub     rsp, 110h
0x140017373  xorps   xmm0, xmm0
0x140017376  mov     [rbp+30h+Context], 0
0x14001737e  mov     r14, rdx
0x140017381  mov     [rbp+30h+FileHandle], 0
0x140017389  xor     eax, eax
0x14001738b  lea     rdx, [rbp+30h+Context]; Context
0x14001738f  movups  xmmword ptr [rbp+30h+var_A0.ObjectName], xmm0
0x140017393  mov     rcx, r14; Instance
0x140017396  mov     [rbp+30h+arg_18], rax
0x14001739a  movups  xmmword ptr [rbp+30h+var_A0+1Ch], xmm0
0x14001739e  mov     rdi, r8
0x1400173a1  movups  [rbp+30h+var_B0], xmm0
0x1400173a5  movups  xmmword ptr [rbp+30h+var_A0.Length], xmm0
0x1400173a9  movups  xmmword ptr [rbp+30h+var_30], xmm0
0x1400173ad  call    cs:__imp_FltGetInstanceContext
0x1400173b4  nop     dword ptr [rax+rax+00h]
0x1400173b9  mov     ebx, eax
0x1400173bb  test    eax, eax
0x1400173bd  js      loc_14001755C
0x1400173c3  mov     rax, [rbp+30h+Context]
0x1400173c7  lea     r8, [rbp+30h+var_B0]
0x1400173cb  mov     edx, 2
0x1400173d0  mov     rcx, [rax+18h]
0x1400173d4  lea     rax, LuafvStoreRoot
0x1400173db  add     rcx, 38h ; '8'
0x1400173df  mov     [rbp+30h+var_38], rax
0x1400173e3  mov     [rbp+30h+var_40], rcx
0x1400173e7  lea     rcx, [rbp+30h+var_40]
0x1400173eb  call    LuafvAllocateAndBuildString
0x1400173f0  mov     ebx, eax
0x1400173f2  test    eax, eax
0x1400173f4  js      loc_14001754C
0x1400173fa  mov     rax, cs:__imp_SeExports
0x140017401  lea     r9, [rbp+30h+arg_18]
0x140017405  mov     [rbp+30h+var_68], 3
0x14001740c  mov     [rbp+30h+var_58], 3
0x140017413  mov     [rbp+30h+var_48], 0
0x14001741a  mov     rcx, [rax]
0x14001741d  mov     [rbp+30h+var_44], 1200A9h
0x140017424  mov     rax, [rcx+108h]
0x14001742b  mov     r8, [rcx+110h]
0x140017432  mov     [rbp+30h+var_70], rax
0x140017436  mov     eax, 1FFFFFh
0x14001743b  mov     [rbp+30h+var_64], eax
0x14001743e  mov     [rbp+30h+var_54], eax
0x140017441  mov     rax, [rcx+0C0h]
0x140017448  lea     rcx, [rbp+30h+var_70]
0x14001744c  mov     [rbp+30h+var_50], rax
0x140017450  mov     [rbp+30h+var_60], r8
0x140017454  call    LuafvBuildSecurityDescriptor
0x140017459  mov     ebx, eax
0x14001745b  test    eax, eax
0x14001745d  js      loc_140017543
0x140017463  mov     rsi, [rbp+30h+arg_18]
0x140017467  lea     rax, [rbp+30h+var_B0]
0x14001746b  mov     rcx, cs:LuafvDriverData; Filter
0x140017472  lea     r8, [rbp+30h+FileHandle]; FileHandle
0x140017476  mov     [rsp+130h+DriverContext], 0; DriverContext
0x14001747f  xor     r9d, r9d; FileObject
0x140017482  mov     [rsp+130h+Flags], 900h; Flags
0x14001748a  mov     rdx, r14; Instance
0x14001748d  mov     [rsp+130h+EaLength], 0; EaLength
0x140017495  mov     [rsp+130h+EaBuffer], 0; EaBuffer
0x14001749e  mov     [rsp+130h+CreateOptions], 4021h; CreateOptions
0x1400174a6  mov     [rsp+130h+CreateDisposition], 3; CreateDisposition
0x1400174ae  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x1400174b6  mov     [rsp+130h+FileAttributes], 12h; FileAttributes
0x1400174be  mov     [rbp+30h+var_A0.ObjectName], rax
0x1400174c2  lea     rax, [rbp+30h+var_30]
0x1400174c6  mov     [rsp+130h+AllocationSize], 0; AllocationSize
0x1400174cf  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x1400174d4  lea     rax, [rbp+30h+var_A0]
0x1400174d8  mov     [rsp+130h+ObjectAttributes], rax; ObjectAttributes
0x1400174dd  mov     [rsp+130h+DesiredAccess], 1C0100h; DesiredAccess
0x1400174e5  mov     [rbp+30h+var_A0.Length], 30h ; '0'
0x1400174ec  mov     [rbp+30h+var_A0.RootDirectory], 0
0x1400174f4  mov     [rbp+30h+var_A0.Attributes], 240h
0x1400174fb  mov     [rbp+30h+var_A0.SecurityDescriptor], rsi
0x1400174ff  mov     [rbp+30h+var_A0.SecurityQualityOfService], 0
0x140017507  call    cs:__imp_FltCreateFileEx2
0x14001750e  nop     dword ptr [rax+rax+00h]
0x140017513  mov     ebx, eax
0x140017515  test    eax, eax
0x140017517  js      short loc_14001753B
0x140017519  mov     rcx, [rdi+8]
0x14001751d  test    rcx, rcx
0x140017520  jz      short loc_14001752B
0x140017522  mov     rax, [rbp+30h+FileHandle]
0x140017526  mov     [rcx], rax
0x140017529  jmp     short loc_14001753B
0x14001752b  mov     rcx, [rbp+30h+FileHandle]; FileHandle
0x14001752f  call    cs:__imp_FltClose
0x140017536  nop     dword ptr [rax+rax+00h]
0x14001753b  mov     rcx, rsi
0x14001753e  call    LuafvFreePool
0x140017543  mov     rcx, qword ptr [rbp+30h+var_B0+8]
0x140017547  call    LuafvFreePool
0x14001754c  mov     rcx, [rbp+30h+Context]; Context
0x140017550  call    cs:__imp_FltReleaseContext
0x140017557  nop     dword ptr [rax+rax+00h]
0x14001755c  xor     r8d, r8d; Wait
0x14001755f  mov     [rdi], ebx
0x140017561  lea     rcx, [rdi+10h]; Event
0x140017565  lea     edx, [r8+1]; Increment
0x140017569  call    cs:__imp_KeSetEvent
0x140017570  nop     dword ptr [rax+rax+00h]
0x140017575  add     rsp, 110h
0x14001757c  pop     r14
0x14001757e  pop     rdi
0x14001757f  pop     rsi
0x140017580  pop     rbx
0x140017581  pop     rbp
0x140017582  retn
```
