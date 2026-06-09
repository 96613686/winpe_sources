# PrjfOpenReparsePoint

- ea: `0x14003c668`
- end: `0x14003ca9c`
- name: `PrjfOpenReparsePoint`
- size: `1076`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, struct _UNICODE_STRING *, void *, ACCESS_MASK, ULONG CreateOptions, int, PVOID *, PHANDLE FileHandle, PFILE_OBJECT *FileObject)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14003be88`
- `0x14003c4b8`

## callees

- `0x14000b1d0`
- `0x14000d128`
- `0x14000d754`
- `0x140011b5c`
- `0x14003c668`

## import_xrefs

- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14003c760`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14003c760`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14003c894`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14003c894`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14003c7b6`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14003c7b6`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14003c6cb`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14003c6cb`
- `FLTMGR!FltCreateFileEx2` at `0x14003c94e`
- `FLTMGR!FltCreateFileEx2` at `0x14003c94e`

## pseudocode

```c
__int64 __fastcall PrjfOpenReparsePoint(
        PFLT_INSTANCE Instance,
        struct _UNICODE_STRING *a2,
        void *a3,
        ACCESS_MASK a4,
        ULONG CreateOptions,
        int a6,
        PVOID *a7,
        PHANDLE FileHandle,
        PFILE_OBJECT *FileObject)
{
  NTSTATUS v13; // eax
  int v14; // edx
  int v15; // r8d
  unsigned int v16; // edi
  NTSTATUS v18; // eax
  int v19; // edx
  int v20; // r8d
  _QWORD *v21; // rax
  PVOID *v22; // rsi
  PVOID *v23; // rax
  _QWORD *v24; // rcx
  _QWORD *v25; // rcx
  PVOID *v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rcx
  NTSTATUS v29; // eax
  int v30; // edx
  int v31; // r8d
  PVOID v32; // rcx
  PVOID *v33; // rax
  _QWORD *v34; // rdx
  PVOID **v35; // rcx
  int CleanupCallback; // [rsp+20h] [rbp-E0h]
  int LookasideList; // [rsp+28h] [rbp-D8h]
  int EcpContext; // [rsp+30h] [rbp-D0h]
  int AllocationSize; // [rsp+38h] [rbp-C8h]
  int FileAttributes; // [rsp+40h] [rbp-C0h]
  ULONG ShareAccess; // [rsp+48h] [rbp-B8h]
  PVOID v42; // [rsp+80h] [rbp-80h] BYREF
  PECP_LIST EcpList; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+90h] [rbp-70h] BYREF
  __int64 v45; // [rsp+B0h] [rbp-50h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E8h] [rbp-18h] BYREF

  v42 = 0;
  EcpList = 0;
  LOWORD(v45) = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v13 = FltAllocateExtraCreateParameterList(Globals, 0, &EcpList);
  v16 = v13;
  if ( v13 >= 0 )
  {
    v18 = FltAllocateExtraCreateParameterFromLookasideList(
            Globals,
            &ECP_TYPE_OPEN_REPARSE_GUID,
            0x10u,
            0,
            0,
            qword_14001A640,
            &v42);
    v16 = v18;
    if ( v18 >= 0 )
    {
      v21 = v42;
      v22 = 0;
      *((_QWORD *)v42 + 1) = v42;
      *v21 = v21;
      while ( 1 )
      {
        v23 = (PVOID *)*a7;
        if ( *a7 == a7 )
          break;
        if ( v23[1] != a7
          || (v24 = *v23, *((PVOID **)*v23 + 1) != v23)
          || (*a7 = v24, v24[1] = a7, v25 = v42, v26 = (PVOID *)*((_QWORD *)v42 + 1), *v26 != v42) )
        {
LABEL_36:
          __fastfail(3u);
        }
        *v23 = v42;
        v23[1] = v26;
        *v26 = v23;
        v25[1] = v23;
        if ( *((_DWORD *)v23 + 4) == -1610612702 )
          v22 = v23;
      }
      if ( FltInsertExtraCreateParameter(Globals, EcpList, v42) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v28, v27);
      DriverContext.Size = 40;
      *(_DWORD *)(&DriverContext.Size + 1) = 0;
      *(&DriverContext.Size + 3) = 0;
      DriverContext.ExtraCreateParameter = EcpList;
      v45 = 1;
      *(_OWORD *)&DriverContext.DeviceObjectHint = 0;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = a3;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = a2;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v29 = FltCreateFileEx2(
              Globals,
              Instance,
              FileHandle,
              FileObject,
              a4,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0,
              7u,
              1u,
              CreateOptions,
              0,
              0,
              0,
              &DriverContext);
      v16 = v29;
      if ( v29 >= 0 )
      {
        while ( 1 )
        {
          v32 = v42;
          v33 = *(PVOID **)v42;
          if ( *(PVOID *)v42 == v42 )
            break;
          if ( v33[1] != v42 )
            goto LABEL_36;
          v34 = *v33;
          if ( *((PVOID **)*v33 + 1) != v33 )
            goto LABEL_36;
          *(_QWORD *)v42 = v34;
          v34[1] = v32;
          v35 = (PVOID **)a7[1];
          if ( *v35 != a7 )
            goto LABEL_36;
          *v33 = a7;
          v33[1] = v35;
          *v35 = v33;
          a7[1] = v33;
        }
      }
      else if ( v29 == -1073741191 )
      {
        if ( v22 && (*((_DWORD *)v22 + 5) & 1) != 0 )
        {
          v16 = -1073741183;
          if ( (BYTE1(xmmword_14001A3E0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v30) = BYTE1(xmmword_14001A3E0) & 4;
            LOBYTE(v31) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDdZ(
              1034,
              v30,
              v31,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              4,
              10,
              57,
              (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
              91,
              129,
              (__int64)a2);
          }
        }
        else if ( (BYTE1(xmmword_14001A3D0) & 4) != 0
               || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v30) = BYTE1(xmmword_14001A3D0) & 4;
          LOBYTE(v31) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDdZP(
            (unsigned int)&WPP_RECORDER_INITIALIZED,
            v30,
            v31,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            CleanupCallback,
            LookasideList,
            EcpContext,
            AllocationSize,
            FileAttributes,
            ShareAccess,
            121,
            (__int64)a2,
            IoStatusBlock.Information);
        }
      }
    }
    else if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v19) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        517,
        v19,
        v20,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        56,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        6,
        v18);
    }
  }
  else if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = xmmword_14001A3D0 & 0x20;
    LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      517,
      v14,
      v15,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      5,
      55,
      (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
      248,
      v13);
  }
  if ( EcpList )
    FltFreeExtraCreateParameterList(Globals, EcpList);
  return v16;
}

```

## disassembly

```asm
0x14003c668  push    rbp
0x14003c66a  push    rbx
0x14003c66b  push    rsi
0x14003c66c  push    rdi
0x14003c66d  push    r12
0x14003c66f  push    r13
0x14003c671  push    r14
0x14003c673  push    r15
0x14003c675  lea     rbp, [rsp-8]
0x14003c67a  sub     rsp, 108h
0x14003c681  xorps   xmm0, xmm0
0x14003c684  mov     [rbp+40h+var_C0], 0
0x14003c68c  mov     r12, r8
0x14003c68f  mov     [rbp+40h+EcpList], 0
0x14003c697  mov     r14, rdx
0x14003c69a  lea     r8, [rbp+40h+EcpList]; EcpList
0x14003c69e  mov     r13, rcx
0x14003c6a1  xor     eax, eax
0x14003c6a3  mov     rcx, cs:Globals; Filter
0x14003c6aa  xor     edx, edx; Flags
0x14003c6ac  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x14003c6b0  mov     r15d, r9d
0x14003c6b3  mov     word ptr [rbp+40h+var_90], ax
0x14003c6b7  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x14003c6bb  movups  xmmword ptr [rbp+40h+var_B0.Size], xmm0
0x14003c6bf  movups  xmmword ptr [rbp+40h+var_B0.DeviceObjectHint], xmm0
0x14003c6c3  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x14003c6c7  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm0
0x14003c6cb  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14003c6d2  nop     dword ptr [rax+rax+00h]
0x14003c6d7  mov     edi, eax
0x14003c6d9  test    eax, eax
0x14003c6db  jns     loc_14003C783
0x14003c6e1  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003c6e7  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003c6ee  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003c6f5  setnz   r8b
0x14003c6f9  and     dl, 20h
0x14003c6fc  jnz     short loc_14003C703
0x14003c6fe  test    r8b, r8b
0x14003c701  jz      short loc_14003C750
0x14003c703  mov     [rsp+140h+CreateDisposition], eax
0x14003c707  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003c70e  mov     [rsp+140h+ShareAccess], 8F8h
0x14003c716  mov     qword ptr [rsp+140h+FileAttributes], rax
0x14003c71b  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003c722  mov     [rsp+140h+AllocationSize], rax
0x14003c727  mov     word ptr [rsp+140h+EcpContext], 37h ; '7'
0x14003c72e  mov     r9, cs:WPP_GLOBAL_Control
0x14003c735  mov     ecx, 205h
0x14003c73a  mov     dword ptr [rsp+140h+LookasideList], 5
0x14003c742  mov     byte ptr [rsp+140h+CleanupCallback], 2
0x14003c747  mov     r9, [r9+40h]
0x14003c74b  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003c750  mov     rdx, [rbp+40h+EcpList]; EcpList
0x14003c754  test    rdx, rdx
0x14003c757  jz      short loc_14003C76C
0x14003c759  mov     rcx, cs:Globals; Filter
0x14003c760  call    cs:__imp_FltFreeExtraCreateParameterList
0x14003c767  nop     dword ptr [rax+rax+00h]
0x14003c76c  mov     eax, edi
0x14003c76e  add     rsp, 108h
0x14003c775  pop     r15
0x14003c777  pop     r14
0x14003c779  pop     r13
0x14003c77b  pop     r12
0x14003c77d  pop     rdi
0x14003c77e  pop     rsi
0x14003c77f  pop     rbx
0x14003c780  pop     rbp
0x14003c781  retn
0x14003c783  mov     rcx, cs:Globals; Filter
0x14003c78a  lea     rax, [rbp+40h+var_C0]
0x14003c78e  mov     [rsp+140h+EcpContext], rax; EcpContext
0x14003c793  lea     rdx, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x14003c79a  xor     r9d, r9d; Flags
0x14003c79d  lea     rax, qword_14001A640
0x14003c7a4  mov     [rsp+140h+LookasideList], rax; LookasideList
0x14003c7a9  mov     [rsp+140h+CleanupCallback], 0; CleanupCallback
0x14003c7b2  lea     r8d, [r9+10h]; SizeOfContext
0x14003c7b6  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x14003c7bd  nop     dword ptr [rax+rax+00h]
0x14003c7c2  mov     edi, eax
0x14003c7c4  test    eax, eax
0x14003c7c6  jns     short loc_14003C81E
0x14003c7c8  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003c7ce  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003c7d5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003c7dc  setnz   r8b
0x14003c7e0  and     dl, 20h
0x14003c7e3  jnz     short loc_14003C7EE
0x14003c7e5  test    r8b, r8b
0x14003c7e8  jz      loc_14003C750
0x14003c7ee  mov     [rsp+140h+CreateDisposition], eax
0x14003c7f2  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003c7f9  mov     [rsp+140h+ShareAccess], 906h
0x14003c801  mov     qword ptr [rsp+140h+FileAttributes], rax
0x14003c806  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003c80d  mov     [rsp+140h+AllocationSize], rax
0x14003c812  mov     word ptr [rsp+140h+EcpContext], 38h ; '8'
0x14003c819  jmp     loc_14003C72E
0x14003c81e  mov     rax, [rbp+40h+var_C0]
0x14003c822  xor     esi, esi
0x14003c824  mov     rbx, [rbp+40h+arg_30]
0x14003c82b  mov     [rax+8], rax
0x14003c82f  mov     [rax], rax
0x14003c832  mov     rax, [rbx]
0x14003c835  cmp     rax, rbx
0x14003c838  jz      short loc_14003C885
0x14003c83a  cmp     [rax+8], rbx
0x14003c83e  jnz     loc_14003CA95
0x14003c844  mov     rcx, [rax]
0x14003c847  cmp     [rcx+8], rax
0x14003c84b  jnz     loc_14003CA95
0x14003c851  mov     [rbx], rcx
0x14003c854  mov     [rcx+8], rbx
0x14003c858  mov     rcx, [rbp+40h+var_C0]
0x14003c85c  mov     rdx, [rcx+8]
0x14003c860  cmp     [rdx], rcx
0x14003c863  jnz     loc_14003CA95
0x14003c869  mov     [rax], rcx
0x14003c86c  mov     [rax+8], rdx
0x14003c870  mov     [rdx], rax
0x14003c873  mov     [rcx+8], rax
0x14003c877  cmp     dword ptr [rax+10h], 0A0000022h
0x14003c87e  jnz     short loc_14003C832
0x14003c880  mov     rsi, rax
0x14003c883  jmp     short loc_14003C832
0x14003c885  mov     r8, [rbp+40h+var_C0]; EcpContext
0x14003c889  mov     rdx, [rbp+40h+EcpList]; EcpList
0x14003c88d  mov     rcx, cs:Globals; Filter
0x14003c894  call    cs:__imp_FltInsertExtraCreateParameter
0x14003c89b  nop     dword ptr [rax+rax+00h]
0x14003c8a0  xor     edi, edi
0x14003c8a2  test    eax, eax
0x14003c8a4  jns     short loc_14003C8AB
0x14003c8a6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003c8ab  mov     r9, [rbp+40h+FileObject]; FileObject
0x14003c8b2  mov     eax, 28h ; '('
0x14003c8b7  mov     r8, [rbp+40h+FileHandle]; FileHandle
0x14003c8be  xorps   xmm0, xmm0
0x14003c8c1  mov     [rbp+40h+var_B0.Size], ax
0x14003c8c5  mov     rdx, r13; Instance
0x14003c8c8  mov     dword ptr [rbp+40h+var_B0+2], edi
0x14003c8cb  lea     ecx, [rax-27h]
0x14003c8ce  mov     word ptr [rbp+40h+var_B0+6], di
0x14003c8d2  mov     rax, [rbp+40h+EcpList]
0x14003c8d6  mov     [rbp+40h+var_B0.ExtraCreateParameter], rax
0x14003c8da  lea     rax, [rbp+40h+var_B0]
0x14003c8de  mov     [rsp+140h+DriverContext], rax; DriverContext
0x14003c8e3  mov     eax, [rbp+40h+arg_20]
0x14003c8e6  mov     [rsp+140h+Flags], edi; Flags
0x14003c8ea  mov     [rsp+140h+EaLength], edi; EaLength
0x14003c8ee  mov     [rsp+140h+EaBuffer], rdi; EaBuffer
0x14003c8f3  mov     [rsp+140h+CreateOptions], eax; CreateOptions
0x14003c8f7  lea     rax, [rbp+40h+IoStatusBlock]
0x14003c8fb  mov     [rsp+140h+CreateDisposition], ecx; CreateDisposition
0x14003c8ff  mov     [rsp+140h+ShareAccess], 7; ShareAccess
0x14003c907  mov     [rsp+140h+FileAttributes], edi; FileAttributes
0x14003c90b  mov     [rsp+140h+AllocationSize], rdi; AllocationSize
0x14003c910  mov     [rsp+140h+EcpContext], rax; IoStatusBlock
0x14003c915  lea     rax, [rbp+40h+ObjectAttributes]
0x14003c919  mov     [rbp+40h+var_90], rcx
0x14003c91d  mov     rcx, cs:Globals; Filter
0x14003c924  mov     [rsp+140h+LookasideList], rax; ObjectAttributes
0x14003c929  mov     dword ptr [rsp+140h+CleanupCallback], r15d; DesiredAccess
0x14003c92e  movdqu  xmmword ptr [rbp+40h+var_B0.DeviceObjectHint], xmm0
0x14003c933  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x14003c93a  mov     [rbp+40h+ObjectAttributes.RootDirectory], r12
0x14003c93e  mov     [rbp+40h+ObjectAttributes.Attributes], 240h
0x14003c945  mov     [rbp+40h+ObjectAttributes.ObjectName], r14
0x14003c949  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003c94e  call    cs:__imp_FltCreateFileEx2
0x14003c955  nop     dword ptr [rax+rax+00h]
0x14003c95a  mov     edi, eax
0x14003c95c  test    eax, eax
0x14003c95e  jns     loc_14003CA56
0x14003c964  mov     r9d, 0C0000279h
0x14003c96a  cmp     eax, r9d
0x14003c96d  jnz     loc_14003C750
0x14003c973  test    rsi, rsi
0x14003c976  jz      loc_14003CA08
0x14003c97c  mov     eax, [rsi+14h]
0x14003c97f  test    al, 1
0x14003c981  jz      loc_14003CA08
0x14003c987  lea     edi, [r9+8]
0x14003c98b  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x14003c991  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003c998  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003c99f  setnz   r8b
0x14003c9a3  and     dl, 4
0x14003c9a6  jnz     short loc_14003C9B1
0x14003c9a8  test    r8b, r8b
0x14003c9ab  jz      loc_14003C750
0x14003c9b1  mov     r9, cs:WPP_GLOBAL_Control
0x14003c9b8  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003c9bf  mov     qword ptr [rsp+140h+CreateOptions], r14
0x14003c9c4  mov     ecx, 40Ah
0x14003c9c9  mov     [rsp+140h+CreateDisposition], edi
0x14003c9cd  mov     [rsp+140h+ShareAccess], 95Bh
0x14003c9d5  mov     r9, [r9+40h]
0x14003c9d9  mov     qword ptr [rsp+140h+FileAttributes], rax
0x14003c9de  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003c9e5  mov     [rsp+140h+AllocationSize], rax
0x14003c9ea  mov     word ptr [rsp+140h+EcpContext], 39h ; '9'
0x14003c9f1  mov     dword ptr [rsp+140h+LookasideList], 0Ah
0x14003c9f9  mov     byte ptr [rsp+140h+CleanupCallback], 4
0x14003c9fe  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x14003ca03  jmp     loc_14003C750
0x14003ca08  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003ca0e  lea     rcx, WPP_RECORDER_INITIALIZED
0x14003ca15  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003ca1c  setnz   r8b
0x14003ca20  and     dl, 4
0x14003ca23  jnz     short loc_14003CA2E
0x14003ca25  test    r8b, r8b
0x14003ca28  jz      loc_14003C750
0x14003ca2e  mov     rax, [rbp+40h+IoStatusBlock.Information]
0x14003ca32  mov     [rsp+140h+EaBuffer], rax
0x14003ca37  mov     qword ptr [rsp+140h+CreateOptions], r14
0x14003ca3c  mov     [rsp+140h+CreateDisposition], r9d
0x14003ca41  mov     r9, cs:WPP_GLOBAL_Control
0x14003ca48  mov     r9, [r9+40h]
0x14003ca4c  call    WPP_RECORDER_AND_TRACE_SF_sDdZP
0x14003ca51  jmp     loc_14003C750
0x14003ca56  mov     rcx, [rbp+40h+var_C0]
0x14003ca5a  mov     rax, [rcx]
0x14003ca5d  cmp     rax, rcx
0x14003ca60  jz      loc_14003C750
0x14003ca66  cmp     [rax+8], rcx
0x14003ca6a  jnz     short loc_14003CA95
0x14003ca6c  mov     rdx, [rax]
0x14003ca6f  cmp     [rdx+8], rax
0x14003ca73  jnz     short loc_14003CA95
0x14003ca75  mov     [rcx], rdx
0x14003ca78  mov     [rdx+8], rcx
0x14003ca7c  mov     rcx, [rbx+8]
0x14003ca80  cmp     [rcx], rbx
0x14003ca83  jnz     short loc_14003CA95
0x14003ca85  mov     [rax], rbx
0x14003ca88  mov     [rax+8], rcx
0x14003ca8c  mov     [rcx], rax
0x14003ca8f  mov     [rbx+8], rax
0x14003ca93  jmp     short loc_14003CA56
0x14003ca95  mov     ecx, 3
0x14003ca9a  int     29h; Win8: RtlFailFast(ecx)
```
