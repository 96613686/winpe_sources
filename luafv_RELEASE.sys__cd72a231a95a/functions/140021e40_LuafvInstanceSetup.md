# LuafvInstanceSetup

- ea: `0x140021e40`
- end: `0x140022054`
- name: `LuafvInstanceSetup`
- size: `532`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140005bb0`
- `0x140006000`
- `0x140015b34`
- `0x140015e28`
- `0x14001dd40`
- `0x140021e40`
- `0x140022c14`
- `0x140024cac`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x140021f8d`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140021f8d`
- `ntoskrnl!EtwWrite` at `0x140022043`
- `ntoskrnl!EtwWrite` at `0x140022043`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140021f67`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140021f67`
- `FLTMGR!FltSetInstanceContext` at `0x140021fa8`
- `FLTMGR!FltSetInstanceContext` at `0x140021fa8`
- `FLTMGR!FltAllocateContext` at `0x140021f12`
- `FLTMGR!FltAllocateContext` at `0x140021f12`
- `FLTMGR!FltReleaseContext` at `0x140021fd4`
- `FLTMGR!FltReleaseContext` at `0x140021fd4`

## pseudocode

```c
__int64 __fastcall LuafvInstanceSetup(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  NTSTATUS VolumeProperties; // ebx
  __int64 v7; // rdi
  ULONGLONG Ptr; // rcx
  LONG v9; // eax
  PFLT_CONTEXT NewContext; // [rsp+30h] [rbp-30h] BYREF
  __int64 v11; // [rsp+38h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-20h] BYREF

  v11 = 0;
  UserData.Ptr = 0;
  VolumeProperties = -1071906801;
  NewContext = 0;
  if ( a4 != 2 )
    return (unsigned int)VolumeProperties;
  VolumeProperties = LuafvGetVolumeProperties(*(PFLT_VOLUME *)(a1 + 16));
  if ( VolumeProperties < 0 )
    goto LABEL_13;
  v7 = v11;
  if ( *(_DWORD *)v11 != 8
    || (*(_DWORD *)(v11 + 4) & 0x5F) != 0
    || !LuafvIsIncludedVolume((_WORD *)(v11 + 56), &UserData) )
  {
    VolumeProperties = -1071906801;
LABEL_13:
    if ( VolumeProperties != -1071906801 )
    {
      UserData.Ptr = (ULONGLONG)&v11;
      LODWORD(v11) = VolumeProperties;
      *(_QWORD *)&UserData.Size = 4;
      EtwWrite(qword_14000EAE0, &LuafvInstanceSetupFailed, 0, 1u, &UserData);
    }
    return (unsigned int)VolumeProperties;
  }
  VolumeProperties = FltAllocateContext(LuafvDriverData, 2u, 0x358u, (POOL_TYPE)512, &NewContext);
  if ( VolumeProperties < 0 )
    goto LABEL_13;
  memset(NewContext, 0, 0x358u);
  *((_QWORD *)NewContext + 2) = *(_QWORD *)(a1 + 24);
  Ptr = UserData.Ptr;
  *((_QWORD *)NewContext + 3) = v7;
  *((_QWORD *)NewContext + 4) = Ptr;
  v9 = RtlCompareUnicodeString(&stru_14000EAE8, (PCUNICODE_STRING)(v7 + 56), 0);
  *((_BYTE *)NewContext + 848) = v9 == 0;
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)NewContext + 105);
  VolumeProperties = FltSetInstanceContext(*(PFLT_INSTANCE *)(a1 + 24), FLT_SET_CONTEXT_KEEP_IF_EXISTS, NewContext, 0);
  if ( VolumeProperties >= 0 )
  {
    LuafvInitializeFileTableForVolume(NewContext);
    VolumeProperties = LuafvInitializeUsn(NewContext);
  }
  FltReleaseContext(NewContext);
  if ( VolumeProperties < 0 )
    goto LABEL_13;
  return (unsigned int)VolumeProperties;
}

```

## disassembly

```asm
0x140021e40  mov     [rsp-18h+arg_8], rbx
0x140021e45  mov     [rsp-18h+arg_10], rsi
0x140021e4a  push    rbp
0x140021e4b  push    rdi
0x140021e4c  push    r14
0x140021e4e  mov     rbp, rsp
0x140021e51  sub     rsp, 60h
0x140021e55  mov     rax, cs:__security_cookie
0x140021e5c  xor     rax, rsp
0x140021e5f  mov     [rbp+var_10], rax
0x140021e63  mov     [rbp+var_28], 0
0x140021e6b  mov     rsi, rcx
0x140021e6e  mov     [rbp+UserData.Ptr], 0
0x140021e76  mov     ebx, 0C01C000Fh
0x140021e7b  mov     [rbp+NewContext], 0
0x140021e83  cmp     r9d, 2
0x140021e87  jz      short loc_140021EAD
0x140021e89  mov     eax, ebx
0x140021e8b  mov     rcx, [rbp+var_10]
0x140021e8f  xor     rcx, rsp; StackCookie
0x140021e92  call    __security_check_cookie
0x140021e97  lea     r11, [rsp+60h+var_s0]
0x140021e9c  mov     rbx, [r11+28h]
0x140021ea0  mov     rsi, [r11+30h]
0x140021ea4  mov     rsp, r11
0x140021ea7  pop     r14
0x140021ea9  pop     rdi
0x140021eaa  pop     rbp
0x140021eab  retn
0x140021ead  mov     rcx, [rcx+10h]; Volume
0x140021eb1  lea     rdx, [rbp+var_28]
0x140021eb5  call    LuafvGetVolumeProperties
0x140021eba  mov     ebx, eax
0x140021ebc  test    eax, eax
0x140021ebe  js      loc_140022004
0x140021ec4  mov     rdi, [rbp+var_28]
0x140021ec8  cmp     dword ptr [rdi], 8
0x140021ecb  jnz     loc_140021FEA
0x140021ed1  mov     eax, [rdi+4]
0x140021ed4  test    al, 5Fh
0x140021ed6  jnz     loc_140021FEA
0x140021edc  lea     rdx, [rbp+UserData]
0x140021ee0  lea     rcx, [rdi+38h]
0x140021ee4  call    LuafvIsIncludedVolume
0x140021ee9  test    al, al
0x140021eeb  jz      loc_140021FEA
0x140021ef1  mov     rcx, cs:LuafvDriverData; Filter
0x140021ef8  lea     rax, [rbp+NewContext]
0x140021efc  mov     edx, 2; ContextType
0x140021f01  mov     [rsp+60h+ReturnedContext], rax; ReturnedContext
0x140021f06  mov     r9d, 200h; PoolType
0x140021f0c  mov     r8d, 358h; ContextSize
0x140021f12  call    cs:__imp_FltAllocateContext
0x140021f19  nop     dword ptr [rax+rax+00h]
0x140021f1e  mov     ebx, eax
0x140021f20  test    eax, eax
0x140021f22  js      loc_140021FEF
0x140021f28  mov     rcx, [rbp+NewContext]; void *
0x140021f2c  xor     edx, edx; Val
0x140021f2e  mov     r8d, 358h; Size
0x140021f34  call    memset
0x140021f39  mov     rax, [rbp+NewContext]
0x140021f3d  lea     rdx, [rdi+38h]; String2
0x140021f41  mov     rcx, [rsi+18h]
0x140021f45  xor     r8d, r8d; CaseInSensitive
0x140021f48  mov     [rax+10h], rcx
0x140021f4c  mov     rax, [rbp+NewContext]
0x140021f50  mov     rcx, [rbp+UserData.Ptr]
0x140021f54  mov     [rax+18h], rdi
0x140021f58  mov     rax, [rbp+NewContext]
0x140021f5c  mov     [rax+20h], rcx
0x140021f60  lea     rcx, stru_14000EAE8; String1
0x140021f67  call    cs:__imp_RtlCompareUnicodeString
0x140021f6e  nop     dword ptr [rax+rax+00h]
0x140021f73  test    eax, eax
0x140021f75  mov     rax, [rbp+NewContext]
0x140021f79  setz    cl
0x140021f7c  mov     [rax+350h], cl
0x140021f82  mov     rcx, [rbp+NewContext]
0x140021f86  add     rcx, 348h; RunRef
0x140021f8d  call    cs:__imp_ExInitializeRundownProtection
0x140021f94  nop     dword ptr [rax+rax+00h]
0x140021f99  mov     r8, [rbp+NewContext]; NewContext
0x140021f9d  xor     r9d, r9d; OldContext
0x140021fa0  mov     rcx, [rsi+18h]; Instance
0x140021fa4  lea     edx, [r9+1]; Operation
0x140021fa8  call    cs:__imp_FltSetInstanceContext
0x140021faf  nop     dword ptr [rax+rax+00h]
0x140021fb4  mov     ebx, eax
0x140021fb6  test    eax, eax
0x140021fb8  js      short loc_140021FD0
0x140021fba  mov     rcx, [rbp+NewContext]
0x140021fbe  xor     edi, edi
0x140021fc0  call    LuafvInitializeFileTableForVolume
0x140021fc5  mov     rcx, [rbp+NewContext]; StartContext
0x140021fc9  call    LuafvInitializeUsn
0x140021fce  mov     ebx, eax
0x140021fd0  mov     rcx, [rbp+NewContext]; Context
0x140021fd4  call    cs:__imp_FltReleaseContext
0x140021fdb  nop     dword ptr [rax+rax+00h]
0x140021fe0  test    ebx, ebx
0x140021fe2  jns     loc_140021E89
0x140021fe8  jmp     short loc_140021FEF
0x140021fea  mov     ebx, 0C01C000Fh
0x140021fef  test    rdi, rdi
0x140021ff2  jz      short loc_140022004
0x140021ff4  mov     rcx, rdi
0x140021ff7  call    LuafvFreePool
0x140021ffc  test    ebx, ebx
0x140021ffe  jns     loc_140021E89
0x140022004  cmp     ebx, 0C01C000Fh
0x14002200a  jz      loc_140021E89
0x140022010  mov     rcx, cs:qword_14000EAE0; RegHandle
0x140022017  lea     rax, [rbp+var_28]
0x14002201b  mov     [rbp+UserData.Ptr], rax
0x14002201f  lea     rdx, LuafvInstanceSetupFailed; EventDescriptor
0x140022026  lea     rax, [rbp+UserData]
0x14002202a  mov     dword ptr [rbp+var_28], ebx
0x14002202d  mov     r9d, 1; UserDataCount
0x140022033  mov     [rsp+60h+ReturnedContext], rax; UserData
0x140022038  xor     r8d, r8d; ActivityId
0x14002203b  mov     qword ptr [rbp+UserData.Size], 4
0x140022043  call    cs:__imp_EtwWrite
0x14002204a  nop     dword ptr [rax+rax+00h]
0x14002204f  jmp     loc_140021E89
```
