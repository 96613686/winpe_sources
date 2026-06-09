# RxFindOrInitializeNetworkCreateEcp

- ea: `0x14000ce60`
- end: `0x14000d10c`
- name: `RxFindOrInitializeNetworkCreateEcp`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140065830`

## callees

- `0x14000ce60`
- `0x140014ec0`

## import_xrefs

- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14000ced6`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14000ced6`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x14000ceaf`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x14000ceaf`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14000cfd3`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14000cfd3`
- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x14000cff0`
- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x14000cff0`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14000d016`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14000d016`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14000cf22`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14000cf22`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14000cf8d`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14000cf8d`

## pseudocode

```c
__int64 __fastcall RxFindOrInitializeNetworkCreateEcp(__int64 a1)
{
  __int64 v1; // r14
  int v3; // r15d
  struct _ECP_LIST *v4; // rax
  NTSTATUS ExtraCreateParameter; // ebx
  char *v6; // rax
  PVOID v7; // rax
  ULONG EcpContextSize; // [rsp+70h] [rbp+40h] BYREF
  PVOID EcpContext; // [rsp+78h] [rbp+48h] BYREF
  PECP_LIST EcpList; // [rsp+80h] [rbp+50h] BYREF

  v1 = *(_QWORD *)(a1 + 40);
  EcpList = 0;
  EcpContext = 0;
  v3 = 0;
  EcpContextSize = 0;
  if ( **(_BYTE **)(v1 + 184) )
  {
    if ( (*(_BYTE *)(a1 + 749) & 0x20) == 0 )
      goto LABEL_8;
  }
  else if ( (*(_BYTE *)(a1 + 749) & 0x20) == 0 )
  {
    FsRtlGetEcpListFromIrp((PIRP)v1, &EcpList);
    v4 = EcpList;
    goto LABEL_4;
  }
  v4 = *(struct _ECP_LIST **)(a1 + 480);
  EcpList = v4;
LABEL_4:
  if ( v4 )
  {
    ExtraCreateParameter = FsRtlFindExtraCreateParameter(
                             v4,
                             &GUID_ECP_NETWORK_OPEN_CONTEXT,
                             &EcpContext,
                             &EcpContextSize);
    if ( !ExtraCreateParameter )
    {
      if ( EcpContextSize < 0x1C
        || (v7 = EcpContext, *(_WORD *)EcpContext != 28)
        || *((_WORD *)EcpContext + 1)
        || *((int *)EcpContext + 1) > 2
        || *((int *)EcpContext + 2) > 4 )
      {
        v7 = 0;
        ExtraCreateParameter = -1073741811;
        EcpContext = 0;
        v3 = 128;
      }
LABEL_12:
      *(_QWORD *)(a1 + 672) = v7;
      if ( ExtraCreateParameter >= 0 )
        return (unsigned int)ExtraCreateParameter;
      goto LABEL_19;
    }
    v4 = EcpList;
  }
  EcpContext = 0;
  if ( !v4 && (*(_BYTE *)(a1 + 749) & 0x20) == 0 )
  {
    ExtraCreateParameter = FsRtlAllocateExtraCreateParameterList(0, &EcpList);
    if ( ExtraCreateParameter < 0 )
    {
      v3 = 150;
      *(_QWORD *)(a1 + 672) = EcpContext;
      goto LABEL_19;
    }
    ExtraCreateParameter = FsRtlSetEcpListIntoIrp((PIRP)v1, EcpList);
    if ( ExtraCreateParameter < 0 )
    {
      FsRtlFreeExtraCreateParameterList(EcpList);
      v3 = 160;
      *(_QWORD *)(a1 + 672) = EcpContext;
      EcpList = 0;
      goto LABEL_19;
    }
    *(_QWORD *)(a1 + 688) = EcpList;
  }
LABEL_8:
  ExtraCreateParameter = FsRtlAllocateExtraCreateParameter(
                           &GUID_ECP_NETWORK_OPEN_CONTEXT,
                           0x1Cu,
                           0,
                           0,
                           0x63457852u,
                           &EcpContext);
  v6 = (char *)EcpContext;
  if ( ExtraCreateParameter >= 0 )
  {
    *(_OWORD *)EcpContext = 0;
    *(_OWORD *)(v6 + 12) = 0;
    *(_WORD *)EcpContext = 28;
    *((_WORD *)EcpContext + 1) = 0;
    *((_DWORD *)EcpContext + 1) = dbgInitialNetworkOpenLocation;
    *((_DWORD *)EcpContext + 2) = dbgInitialNetworkOpenIntegrity;
    *((_DWORD *)EcpContext + 4) = 0;
    *((_DWORD *)EcpContext + 5) = 0;
    if ( EcpList )
      ExtraCreateParameter = FsRtlInsertExtraCreateParameter(EcpList, EcpContext);
    v7 = EcpContext;
    goto LABEL_12;
  }
  v3 = 183;
  *(_QWORD *)(a1 + 672) = EcpContext;
LABEL_19:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      WPP_a28743743bb83892c11d9270eb466b78_Traceguids,
      a1,
      ExtraCreateParameter,
      v3);
  }
  return (unsigned int)ExtraCreateParameter;
}

```

## disassembly

```asm
0x14000ce60  push    rbp
0x14000ce62  push    rbx
0x14000ce63  push    rsi
0x14000ce64  push    rdi
0x14000ce65  push    r12
0x14000ce67  push    r14
0x14000ce69  push    r15
0x14000ce6b  mov     rbp, rsp
0x14000ce6e  sub     rsp, 30h
0x14000ce72  mov     r14, [rcx+28h]
0x14000ce76  xor     r12d, r12d
0x14000ce79  mov     [rbp+EcpList], r12
0x14000ce7d  mov     rsi, rcx
0x14000ce80  mov     [rbp+EcpContext], r12
0x14000ce84  mov     r15d, r12d
0x14000ce87  mov     [rbp+EcpContextSize], r12d
0x14000ce8b  mov     rax, [r14+0B8h]
0x14000ce92  cmp     [rax], r12b
0x14000ce95  jnz     loc_14000D089
0x14000ce9b  test    byte ptr [rcx+2EDh], 20h
0x14000cea2  jnz     loc_14000D096
0x14000cea8  lea     rdx, [rbp+EcpList]; EcpList
0x14000ceac  mov     rcx, r14; Irp
0x14000ceaf  call    cs:__imp_FsRtlGetEcpListFromIrp
0x14000ceb6  nop     dword ptr [rax+rax+00h]
0x14000cebb  mov     rax, [rbp+EcpList]
0x14000cebf  test    rax, rax
0x14000cec2  jz      short loc_14000CEF0
0x14000cec4  lea     r9, [rbp+EcpContextSize]; EcpContextSize
0x14000cec8  mov     rcx, rax; EcpList
0x14000cecb  lea     r8, [rbp+EcpContext]; EcpContext
0x14000cecf  lea     rdx, GUID_ECP_NETWORK_OPEN_CONTEXT; EcpType
0x14000ced6  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14000cedd  nop     dword ptr [rax+rax+00h]
0x14000cee2  mov     ebx, eax
0x14000cee4  test    eax, eax
0x14000cee6  jz      loc_14000D0A6
0x14000ceec  mov     rax, [rbp+EcpList]
0x14000cef0  mov     [rbp+EcpContext], r12
0x14000cef4  test    rax, rax
0x14000cef7  jz      loc_14000CFC0
0x14000cefd  lea     rax, [rbp+EcpContext]
0x14000cf01  mov     edi, 1Ch
0x14000cf06  mov     [rsp+30h+var_8], rax; EcpContext
0x14000cf0b  lea     rcx, GUID_ECP_NETWORK_OPEN_CONTEXT; EcpType
0x14000cf12  mov     edx, edi; SizeOfContext
0x14000cf14  mov     [rsp+30h+PoolTag], 63457852h; PoolTag
0x14000cf1c  xor     r9d, r9d; CleanupCallback
0x14000cf1f  xor     r8d, r8d; Flags
0x14000cf22  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x14000cf29  nop     dword ptr [rax+rax+00h]
0x14000cf2e  mov     ebx, eax
0x14000cf30  test    eax, eax
0x14000cf32  mov     rax, [rbp+EcpContext]
0x14000cf36  js      loc_14000D0FA
0x14000cf3c  xorps   xmm0, xmm0
0x14000cf3f  movups  xmmword ptr [rax], xmm0
0x14000cf42  movups  xmmword ptr [rax+0Ch], xmm0
0x14000cf46  mov     rax, [rbp+EcpContext]
0x14000cf4a  mov     [rax], di
0x14000cf4d  mov     rax, [rbp+EcpContext]
0x14000cf51  mov     [rax+2], r12w
0x14000cf56  mov     eax, cs:dbgInitialNetworkOpenLocation
0x14000cf5c  mov     rcx, [rbp+EcpContext]
0x14000cf60  mov     [rcx+4], eax
0x14000cf63  mov     eax, cs:dbgInitialNetworkOpenIntegrity
0x14000cf69  mov     rcx, [rbp+EcpContext]
0x14000cf6d  mov     [rcx+8], eax
0x14000cf70  mov     rax, [rbp+EcpContext]
0x14000cf74  mov     [rax+10h], r12d
0x14000cf78  mov     rax, [rbp+EcpContext]
0x14000cf7c  mov     [rax+14h], r12d
0x14000cf80  mov     rcx, [rbp+EcpList]; EcpList
0x14000cf84  test    rcx, rcx
0x14000cf87  jz      short loc_14000CF9B
0x14000cf89  mov     rdx, [rbp+EcpContext]; EcpContext
0x14000cf8d  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x14000cf94  nop     dword ptr [rax+rax+00h]
0x14000cf99  mov     ebx, eax
0x14000cf9b  mov     rax, [rbp+EcpContext]
0x14000cf9f  mov     [rsi+2A0h], rax
0x14000cfa6  test    ebx, ebx
0x14000cfa8  js      loc_14000D037
0x14000cfae  mov     eax, ebx
0x14000cfb0  add     rsp, 30h
0x14000cfb4  pop     r15
0x14000cfb6  pop     r14
0x14000cfb8  pop     r12
0x14000cfba  pop     rdi
0x14000cfbb  pop     rsi
0x14000cfbc  pop     rbx
0x14000cfbd  pop     rbp
0x14000cfbe  retn
0x14000cfc0  test    byte ptr [rsi+2EDh], 20h
0x14000cfc7  jnz     loc_14000CEFD
0x14000cfcd  lea     rdx, [rbp+EcpList]; EcpList
0x14000cfd1  xor     ecx, ecx; Flags
0x14000cfd3  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x14000cfda  nop     dword ptr [rax+rax+00h]
0x14000cfdf  mov     ebx, eax
0x14000cfe1  test    eax, eax
0x14000cfe3  js      loc_14000D0E4
0x14000cfe9  mov     rdx, [rbp+EcpList]; EcpList
0x14000cfed  mov     rcx, r14; Irp
0x14000cff0  call    cs:__imp_FsRtlSetEcpListIntoIrp
0x14000cff7  nop     dword ptr [rax+rax+00h]
0x14000cffc  mov     ebx, eax
0x14000cffe  test    eax, eax
0x14000d000  js      short loc_14000D012
0x14000d002  mov     rax, [rbp+EcpList]
0x14000d006  mov     [rsi+2B0h], rax
0x14000d00d  jmp     loc_14000CEFD
0x14000d012  mov     rcx, [rbp+EcpList]; EcpList
0x14000d016  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x14000d01d  nop     dword ptr [rax+rax+00h]
0x14000d022  mov     rax, [rbp+EcpContext]
0x14000d026  mov     r15d, 0A0h
0x14000d02c  mov     [rsi+2A0h], rax
0x14000d033  mov     [rbp+EcpList], r12
0x14000d037  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d03e  lea     rax, WPP_GLOBAL_Control
0x14000d045  cmp     rcx, rax
0x14000d048  jz      loc_14000CFAE
0x14000d04e  mov     eax, [rcx+2Ch]
0x14000d051  test    al, 1
0x14000d053  jz      loc_14000CFAE
0x14000d059  cmp     byte ptr [rcx+29h], 1
0x14000d05d  jb      loc_14000CFAE
0x14000d063  mov     rcx, [rcx+18h]
0x14000d067  lea     r8, WPP_a28743743bb83892c11d9270eb466b78_Traceguids
0x14000d06e  mov     edx, 0Bh
0x14000d073  mov     dword ptr [rsp+30h+var_8], r15d
0x14000d078  mov     r9, rsi
0x14000d07b  mov     [rsp+30h+PoolTag], ebx
0x14000d07f  call    WPP_SF_qDD
0x14000d084  jmp     loc_14000CFAE
0x14000d089  test    byte ptr [rcx+2EDh], 20h
0x14000d090  jz      loc_14000CEFD
0x14000d096  mov     rax, [rcx+1E0h]
0x14000d09d  mov     [rbp+EcpList], rax
0x14000d0a1  jmp     loc_14000CEBF
0x14000d0a6  cmp     [rbp+EcpContextSize], 1Ch
0x14000d0aa  jb      short loc_14000D0CD
0x14000d0ac  mov     rax, [rbp+EcpContext]
0x14000d0b0  cmp     word ptr [rax], 1Ch
0x14000d0b4  jnz     short loc_14000D0CD
0x14000d0b6  cmp     [rax+2], r12w
0x14000d0bb  jnz     short loc_14000D0CD
0x14000d0bd  cmp     dword ptr [rax+4], 2
0x14000d0c1  jg      short loc_14000D0CD
0x14000d0c3  cmp     dword ptr [rax+8], 4
0x14000d0c7  jle     loc_14000CF9F
0x14000d0cd  mov     rax, r12
0x14000d0d0  mov     ebx, 0C000000Dh
0x14000d0d5  mov     [rbp+EcpContext], rax
0x14000d0d9  mov     r15d, 80h
0x14000d0df  jmp     loc_14000CF9F
0x14000d0e4  mov     rax, [rbp+EcpContext]
0x14000d0e8  mov     r15d, 96h
0x14000d0ee  mov     [rsi+2A0h], rax
0x14000d0f5  jmp     loc_14000D037
0x14000d0fa  mov     r15d, 0B7h
0x14000d100  mov     [rsi+2A0h], rax
0x14000d107  jmp     loc_14000D037
```
