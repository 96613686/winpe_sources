# LuafvInstanceSetup

- ea: `0x140021e90`
- end: `0x1400220a4`
- name: `LuafvInstanceSetup`
- size: `532`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140005f30`
- `0x140006380`
- `0x140015b34`
- `0x140015e28`
- `0x14001dd90`
- `0x140021e90`
- `0x140022c64`
- `0x140024cfc`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x140021fdd`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140021fdd`
- `ntoskrnl!EtwWrite` at `0x140022093`
- `ntoskrnl!EtwWrite` at `0x140022093`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140021fb7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140021fb7`
- `FLTMGR!FltSetInstanceContext` at `0x140021ff8`
- `FLTMGR!FltSetInstanceContext` at `0x140021ff8`
- `FLTMGR!FltAllocateContext` at `0x140021f62`
- `FLTMGR!FltAllocateContext` at `0x140021f62`
- `FLTMGR!FltReleaseContext` at `0x140022024`
- `FLTMGR!FltReleaseContext` at `0x140022024`

## pseudocode

```c
__int64 __fastcall LuafvInstanceSetup(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  NTSTATUS VolumeProperties; // ebx
  _DWORD *v7; // rdi
  ULONGLONG Ptr; // rcx
  LONG v9; // eax
  PFLT_CONTEXT NewContext; // [rsp+30h] [rbp-30h] BYREF
  _DWORD *v11; // [rsp+38h] [rbp-28h] BYREF
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
  if ( *v11 != 8 || (v11[1] & 0x5F) != 0 || !(unsigned __int8)LuafvIsIncludedVolume(v11 + 14, &UserData) )
  {
    VolumeProperties = -1071906801;
LABEL_13:
    if ( VolumeProperties != -1071906801 )
    {
      UserData.Ptr = (ULONGLONG)&v11;
      LODWORD(v11) = VolumeProperties;
      *(_QWORD *)&UserData.Size = 4;
      EtwWrite(qword_14000F120, &LuafvInstanceSetupFailed, 0, 1u, &UserData);
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
  v9 = RtlCompareUnicodeString(&stru_14000F128, (PCUNICODE_STRING)(v7 + 14), 0);
  *((_BYTE *)NewContext + 848) = v9 == 0;
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)NewContext + 105);
  VolumeProperties = FltSetInstanceContext(*(PFLT_INSTANCE *)(a1 + 24), FLT_SET_CONTEXT_KEEP_IF_EXISTS, NewContext, 0);
  if ( VolumeProperties >= 0 )
  {
    LuafvInitializeFileTableForVolume(NewContext);
    VolumeProperties = LuafvInitializeUsn((char *)NewContext);
  }
  FltReleaseContext(NewContext);
  if ( VolumeProperties < 0 )
    goto LABEL_13;
  return (unsigned int)VolumeProperties;
}

```

## disassembly

```asm
0x140021e90  mov     [rsp-18h+arg_8], rbx
0x140021e95  mov     [rsp-18h+arg_10], rsi
0x140021e9a  push    rbp
0x140021e9b  push    rdi
0x140021e9c  push    r14
0x140021e9e  mov     rbp, rsp
0x140021ea1  sub     rsp, 60h
0x140021ea5  mov     rax, cs:__security_cookie
0x140021eac  xor     rax, rsp
0x140021eaf  mov     [rbp+var_10], rax
0x140021eb3  mov     [rbp+var_28], 0
0x140021ebb  mov     rsi, rcx
0x140021ebe  mov     [rbp+UserData.Ptr], 0
0x140021ec6  mov     ebx, 0C01C000Fh
0x140021ecb  mov     [rbp+NewContext], 0
0x140021ed3  cmp     r9d, 2
0x140021ed7  jz      short loc_140021EFD
0x140021ed9  mov     eax, ebx
0x140021edb  mov     rcx, [rbp+var_10]
0x140021edf  xor     rcx, rsp; StackCookie
0x140021ee2  call    __security_check_cookie
0x140021ee7  lea     r11, [rsp+60h+var_s0]
0x140021eec  mov     rbx, [r11+28h]
0x140021ef0  mov     rsi, [r11+30h]
0x140021ef4  mov     rsp, r11
0x140021ef7  pop     r14
0x140021ef9  pop     rdi
0x140021efa  pop     rbp
0x140021efb  retn
0x140021efd  mov     rcx, [rcx+10h]; Volume
0x140021f01  lea     rdx, [rbp+var_28]
0x140021f05  call    LuafvGetVolumeProperties
0x140021f0a  mov     ebx, eax
0x140021f0c  test    eax, eax
0x140021f0e  js      loc_140022054
0x140021f14  mov     rdi, [rbp+var_28]
0x140021f18  cmp     dword ptr [rdi], 8
0x140021f1b  jnz     loc_14002203A
0x140021f21  mov     eax, [rdi+4]
0x140021f24  test    al, 5Fh
0x140021f26  jnz     loc_14002203A
0x140021f2c  lea     rdx, [rbp+UserData]
0x140021f30  lea     rcx, [rdi+38h]
0x140021f34  call    LuafvIsIncludedVolume
0x140021f39  test    al, al
0x140021f3b  jz      loc_14002203A
0x140021f41  mov     rcx, cs:LuafvDriverData; Filter
0x140021f48  lea     rax, [rbp+NewContext]
0x140021f4c  mov     edx, 2; ContextType
0x140021f51  mov     [rsp+60h+ReturnedContext], rax; ReturnedContext
0x140021f56  mov     r9d, 200h; PoolType
0x140021f5c  mov     r8d, 358h; ContextSize
0x140021f62  call    cs:__imp_FltAllocateContext
0x140021f69  nop     dword ptr [rax+rax+00h]
0x140021f6e  mov     ebx, eax
0x140021f70  test    eax, eax
0x140021f72  js      loc_14002203F
0x140021f78  mov     rcx, [rbp+NewContext]; void *
0x140021f7c  xor     edx, edx; Val
0x140021f7e  mov     r8d, 358h; Size
0x140021f84  call    memset
0x140021f89  mov     rax, [rbp+NewContext]
0x140021f8d  lea     rdx, [rdi+38h]; String2
0x140021f91  mov     rcx, [rsi+18h]
0x140021f95  xor     r8d, r8d; CaseInSensitive
0x140021f98  mov     [rax+10h], rcx
0x140021f9c  mov     rax, [rbp+NewContext]
0x140021fa0  mov     rcx, [rbp+UserData.Ptr]
0x140021fa4  mov     [rax+18h], rdi
0x140021fa8  mov     rax, [rbp+NewContext]
0x140021fac  mov     [rax+20h], rcx
0x140021fb0  lea     rcx, stru_14000F128; String1
0x140021fb7  call    cs:__imp_RtlCompareUnicodeString
0x140021fbe  nop     dword ptr [rax+rax+00h]
0x140021fc3  test    eax, eax
0x140021fc5  mov     rax, [rbp+NewContext]
0x140021fc9  setz    cl
0x140021fcc  mov     [rax+350h], cl
0x140021fd2  mov     rcx, [rbp+NewContext]
0x140021fd6  add     rcx, 348h; RunRef
0x140021fdd  call    cs:__imp_ExInitializeRundownProtection
0x140021fe4  nop     dword ptr [rax+rax+00h]
0x140021fe9  mov     r8, [rbp+NewContext]; NewContext
0x140021fed  xor     r9d, r9d; OldContext
0x140021ff0  mov     rcx, [rsi+18h]; Instance
0x140021ff4  lea     edx, [r9+1]; Operation
0x140021ff8  call    cs:__imp_FltSetInstanceContext
0x140021fff  nop     dword ptr [rax+rax+00h]
0x140022004  mov     ebx, eax
0x140022006  test    eax, eax
0x140022008  js      short loc_140022020
0x14002200a  mov     rcx, [rbp+NewContext]
0x14002200e  xor     edi, edi
0x140022010  call    LuafvInitializeFileTableForVolume
0x140022015  mov     rcx, [rbp+NewContext]; StartContext
0x140022019  call    LuafvInitializeUsn
0x14002201e  mov     ebx, eax
0x140022020  mov     rcx, [rbp+NewContext]; Context
0x140022024  call    cs:__imp_FltReleaseContext
0x14002202b  nop     dword ptr [rax+rax+00h]
0x140022030  test    ebx, ebx
0x140022032  jns     loc_140021ED9
0x140022038  jmp     short loc_14002203F
0x14002203a  mov     ebx, 0C01C000Fh
0x14002203f  test    rdi, rdi
0x140022042  jz      short loc_140022054
0x140022044  mov     rcx, rdi
0x140022047  call    LuafvFreePool
0x14002204c  test    ebx, ebx
0x14002204e  jns     loc_140021ED9
0x140022054  cmp     ebx, 0C01C000Fh
0x14002205a  jz      loc_140021ED9
0x140022060  mov     rcx, cs:qword_14000F120; RegHandle
0x140022067  lea     rax, [rbp+var_28]
0x14002206b  mov     [rbp+UserData.Ptr], rax
0x14002206f  lea     rdx, LuafvInstanceSetupFailed; EventDescriptor
0x140022076  lea     rax, [rbp+UserData]
0x14002207a  mov     dword ptr [rbp+var_28], ebx
0x14002207d  mov     r9d, 1; UserDataCount
0x140022083  mov     [rsp+60h+ReturnedContext], rax; UserData
0x140022088  xor     r8d, r8d; ActivityId
0x14002208b  mov     qword ptr [rbp+UserData.Size], 4
0x140022093  call    cs:__imp_EtwWrite
0x14002209a  nop     dword ptr [rax+rax+00h]
0x14002209f  jmp     loc_140021ED9
```
