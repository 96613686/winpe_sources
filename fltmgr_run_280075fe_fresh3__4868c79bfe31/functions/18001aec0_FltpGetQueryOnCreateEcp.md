# FltpGetQueryOnCreateEcp

- ea: `0x18001aec0`
- end: `0x18001b035`
- name: `FltpGetQueryOnCreateEcp`
- size: `373`
- prototype: `__int64 __fastcall(PFLT_FILTER Filter, PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1800502e0`
- `0x180070140`

## callees

- `0x180009f20`
- `0x18001aec0`
- `0x180024c00`
- `0x180064df0`
- `0x180065420`
- `0x1800659e0`
- `0x18006b930`

## import_xrefs

- `ntoskrnl!FsRtlAllocateExtraCreateParameterFromLookasideList` at `0x18001af99`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterFromLookasideList` at `0x18001af99`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18001afde`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18001afde`

## pseudocode

```c
__int64 __fastcall FltpGetQueryOnCreateEcp(PFLT_FILTER Filter, PFLT_CALLBACK_DATA CallbackData, _QWORD *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  UCHAR MajorFunction; // cl
  unsigned int v8; // ebp
  PVOID v10; // rax
  unsigned int v11; // ebx
  PVOID EcpContext; // [rsp+58h] [rbp+10h] BYREF
  PECP_LIST EcpList; // [rsp+68h] [rbp+20h] BYREF

  Iopb = CallbackData->Iopb;
  EcpList = 0;
  EcpContext = 0;
  MajorFunction = Iopb->MajorFunction;
  if ( !MajorFunction || MajorFunction == 0xF2 || MajorFunction == 0xF9 )
  {
    FltGetEcpListFromCallbackData(Filter, CallbackData, &EcpList);
    if ( EcpList )
    {
      FltFindExtraCreateParameter(Filter, EcpList, &GUID_ECP_QUERY_ON_CREATE, &EcpContext, 0);
    }
    else
    {
      v8 = FltAllocateExtraCreateParameterList(Filter, 0, &EcpList);
      if ( (int)FltpDbgStatus(v8, "minkernel\\fs\\filtermgr\\filter\\ecpsup.c", 1588, 0) < 0 )
        return v8;
      FltSetEcpListIntoCallbackData(Filter, CallbackData, EcpList);
    }
    v10 = EcpContext;
    if ( !EcpContext )
    {
      v11 = FsRtlAllocateExtraCreateParameterFromLookasideList(
              &GUID_ECP_QUERY_ON_CREATE,
              0xC8u,
              0,
              FltpQocEcpCleanupCallback,
              qword_18003F3C0,
              &EcpContext);
      if ( (int)FltpDbgStatus(v11, "minkernel\\fs\\filtermgr\\filter\\ecpsup.c", 1629, 0) < 0 )
        return v11;
      memset(EcpContext, 0, 0xC8u);
      FsRtlInsertExtraCreateParameter(EcpList, EcpContext);
      v10 = EcpContext;
    }
    *a3 = v10;
    return 0;
  }
  return 3221225712LL;
}

```

## disassembly

```asm
0x18001aec0  mov     [rsp+arg_0], rbx
0x18001aec5  push    rbp
0x18001aec6  push    rsi
0x18001aec7  push    rdi
0x18001aec8  sub     rsp, 30h
0x18001aecc  mov     rax, [rdx+10h]
0x18001aed0  xor     ebp, ebp
0x18001aed2  mov     rdi, rcx
0x18001aed5  mov     [rsp+48h+EcpList], rbp
0x18001aeda  mov     [rsp+48h+EcpContext], rbp
0x18001aedf  mov     rsi, r8
0x18001aee2  mov     rbx, rdx
0x18001aee5  movzx   ecx, byte ptr [rax+4]
0x18001aee9  test    cl, cl
0x18001aeeb  jnz     loc_18001B019
0x18001aef1  lea     r8, [rsp+48h+EcpList]; EcpList
0x18001aef6  mov     rcx, rdi; Filter
0x18001aef9  call    FltGetEcpListFromCallbackData
0x18001aefe  mov     rdx, [rsp+48h+EcpList]; EcpList
0x18001af03  mov     rcx, rdi; Filter
0x18001af06  test    rdx, rdx
0x18001af09  jnz     short loc_18001AF46
0x18001af0b  lea     r8, [rsp+48h+EcpList]; EcpList
0x18001af10  call    FltAllocateExtraCreateParameterList
0x18001af15  mov     r8d, 634h
0x18001af1b  lea     rdx, aMinkernelFsFil_14; "minkernel\\fs\\filtermgr\\filter\\ecpsu"...
0x18001af22  xor     r9d, r9d
0x18001af25  mov     ecx, eax
0x18001af27  mov     ebp, eax
0x18001af29  call    FltpDbgStatus
0x18001af2e  test    eax, eax
0x18001af30  jns     loc_18001AFF4
0x18001af36  mov     eax, ebp
0x18001af38  mov     rbx, [rsp+48h+arg_0]
0x18001af3d  add     rsp, 30h
0x18001af41  pop     rdi
0x18001af42  pop     rsi
0x18001af43  pop     rbp
0x18001af44  retn
0x18001af46  lea     r9, [rsp+48h+EcpContext]; EcpContext
0x18001af4b  mov     [rsp+48h+EcpContextSize], rbp; EcpContextSize
0x18001af50  lea     r8, GUID_ECP_QUERY_ON_CREATE; EcpType
0x18001af57  call    FltFindExtraCreateParameter
0x18001af5c  mov     rax, [rsp+48h+EcpContext]
0x18001af61  test    rax, rax
0x18001af64  jz      short loc_18001AF6D
0x18001af66  mov     [rsi], rax
0x18001af69  xor     eax, eax
0x18001af6b  jmp     short loc_18001AF38
0x18001af6d  lea     rax, [rsp+48h+EcpContext]
0x18001af72  xor     r8d, r8d; Flags
0x18001af75  mov     [rsp+48h+var_20], rax; EcpContext
0x18001af7a  lea     r9, FltpQocEcpCleanupCallback; CleanupCallback
0x18001af81  lea     rax, qword_18003F3C0
0x18001af88  mov     edx, 0C8h; SizeOfContext
0x18001af8d  lea     rcx, GUID_ECP_QUERY_ON_CREATE; EcpType
0x18001af94  mov     [rsp+48h+EcpContextSize], rax; LookasideList
0x18001af99  call    cs:__imp_FsRtlAllocateExtraCreateParameterFromLookasideList
0x18001afa0  nop     dword ptr [rax+rax+00h]
0x18001afa5  mov     r8d, 65Dh
0x18001afab  lea     rdx, aMinkernelFsFil_14; "minkernel\\fs\\filtermgr\\filter\\ecpsu"...
0x18001afb2  mov     ecx, eax
0x18001afb4  xor     r9d, r9d
0x18001afb7  mov     ebx, eax
0x18001afb9  call    FltpDbgStatus
0x18001afbe  test    eax, eax
0x18001afc0  js      short loc_18001B009
0x18001afc2  mov     rcx, [rsp+48h+EcpContext]; void *
0x18001afc7  xor     edx, edx; Val
0x18001afc9  mov     r8d, 0C8h; Size
0x18001afcf  call    memset
0x18001afd4  mov     rdx, [rsp+48h+EcpContext]; EcpContext
0x18001afd9  mov     rcx, [rsp+48h+EcpList]; EcpList
0x18001afde  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x18001afe5  nop     dword ptr [rax+rax+00h]
0x18001afea  mov     rax, [rsp+48h+EcpContext]
0x18001afef  jmp     loc_18001AF66
0x18001aff4  mov     r8, [rsp+48h+EcpList]; EcpList
0x18001aff9  mov     rdx, rbx; CallbackData
0x18001affc  mov     rcx, rdi; Filter
0x18001afff  call    FltSetEcpListIntoCallbackData
0x18001b004  jmp     loc_18001AF5C
0x18001b009  mov     eax, ebx
0x18001b00b  mov     rbx, [rsp+48h+arg_0]
0x18001b010  add     rsp, 30h
0x18001b014  pop     rdi
0x18001b015  pop     rsi
0x18001b016  pop     rbp
0x18001b017  retn
0x18001b019  cmp     cl, 0F2h
0x18001b01c  jz      loc_18001AEF1
0x18001b022  cmp     cl, 0F9h
0x18001b025  jz      loc_18001AEF1
0x18001b02b  mov     eax, 0C00000F0h
0x18001b030  jmp     loc_18001AF38
```
