# CscEcpGetTypeValue

- ea: `0x140076f00`
- end: `0x1400770cc`
- name: `CscEcpGetTypeValue`
- size: `460`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140008610`
- `0x14004a4f4`
- `0x140062b70`
- `0x140075770`

## callees

- `0x140018d7c`
- `0x140018fd0`
- `0x1400224f4`
- `0x140076f00`

## import_xrefs

- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x140076f79`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x140076f79`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x140076f3c`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x140076f3c`

## pseudocode

```c
__int64 __fastcall CscEcpGetTypeValue(IRP *a1, unsigned int a2)
{
  unsigned __int8 v4; // si
  const GUID *v5; // rdi
  NTSTATUS IrpExtraCreateParameter; // ebx
  int v7; // ebp
  __int64 v8; // r8
  char v9; // di
  __int64 Timer_high; // rdx
  char v12; // al
  int v13; // [rsp+20h] [rbp-58h]
  int v14; // [rsp+28h] [rbp-50h]
  ULONG EcpContextSize; // [rsp+88h] [rbp+10h] BYREF
  PECP_LIST EcpList; // [rsp+90h] [rbp+18h] BYREF
  PVOID EcpContext; // [rsp+98h] [rbp+20h] BYREF

  EcpContextSize = 0;
  v4 = 0;
  v5 = (const GUID *)off_140031000[a2];
  EcpContext = 0;
  EcpList = 0;
  IrpExtraCreateParameter = IoGetIrpExtraCreateParameter(a1, &EcpList);
  if ( IrpExtraCreateParameter < 0 )
  {
    v7 = 337;
  }
  else if ( EcpList )
  {
    v7 = 0;
    IrpExtraCreateParameter = FsRtlFindExtraCreateParameter(EcpList, v5, &EcpContext, &EcpContextSize);
    if ( IrpExtraCreateParameter < 0 )
      v7 = 360;
  }
  else
  {
    IrpExtraCreateParameter = -1073741275;
    v7 = 349;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      WPP_f74abd63425539499d784964bfbadaaa_Traceguids,
      a1,
      IrpExtraCreateParameter,
      v7);
  if ( IrpExtraCreateParameter >= 0 )
  {
    if ( EcpContextSize == 1 )
    {
      v8 = 0;
      v4 = *(_BYTE *)EcpContext;
    }
    else
    {
      IrpExtraCreateParameter = -1073741811;
      v8 = 484;
    }
  }
  else
  {
    v8 = 478;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    v9 = 89;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      v12 = 89;
      if ( !v4 )
        v12 = 78;
      LOBYTE(v13) = v12;
      WPP_SF_qcDD(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_f74abd63425539499d784964bfbadaaa_Traceguids,
        a1,
        v13,
        IrpExtraCreateParameter,
        v8);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 0x40) != 0 )
      {
        if ( !v4 )
          v9 = 78;
        LOBYTE(v14) = v9;
        WPP_SF_DqcD(WPP_GLOBAL_Control->AttachedDevice, Timer_high, v8, a2, a1, v14, IrpExtraCreateParameter);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140076f00  mov     rax, rsp
0x140076f03  push    rbx
0x140076f04  push    rbp
0x140076f05  push    rsi
0x140076f06  push    rdi
0x140076f07  push    r12
0x140076f09  push    r14
0x140076f0b  push    r15
0x140076f0d  sub     rsp, 40h
0x140076f11  movsxd  r15, edx
0x140076f14  lea     rdi, off_140031000
0x140076f1b  mov     [rax+8], r13
0x140076f1f  lea     rdx, [rax+18h]; ExtraCreateParameter
0x140076f23  xor     r13d, r13d
0x140076f26  mov     r14, rcx
0x140076f29  mov     [rax+10h], r13d
0x140076f2d  xor     sil, sil
0x140076f30  mov     rdi, [rdi+r15*8]
0x140076f34  mov     [rax+20h], r13
0x140076f38  mov     [rax+18h], r13
0x140076f3c  call    cs:__imp_IoGetIrpExtraCreateParameter
0x140076f43  nop     dword ptr [rax+rax+00h]
0x140076f48  mov     ebx, eax
0x140076f4a  test    eax, eax
0x140076f4c  js      loc_14007703E
0x140076f52  mov     rcx, [rsp+78h+EcpList]; EcpList
0x140076f5a  test    rcx, rcx
0x140076f5d  jz      loc_14007700D
0x140076f63  lea     r9, [rsp+78h+EcpContextSize]; EcpContextSize
0x140076f6b  mov     rdx, rdi; EcpType
0x140076f6e  lea     r8, [rsp+78h+EcpContext]; EcpContext
0x140076f76  mov     ebp, r13d
0x140076f79  call    cs:__imp_FsRtlFindExtraCreateParameter
0x140076f80  nop     dword ptr [rax+rax+00h]
0x140076f85  mov     ebx, eax
0x140076f87  test    eax, eax
0x140076f89  jns     short loc_140076F90
0x140076f8b  mov     ebp, 168h
0x140076f90  mov     rcx, cs:WPP_GLOBAL_Control
0x140076f97  lea     r12, WPP_GLOBAL_Control
0x140076f9e  cmp     rcx, r12
0x140076fa1  jz      short loc_140076FAE
0x140076fa3  mov     eax, [rcx+2Ch]
0x140076fa6  test    al, 40h
0x140076fa8  jnz     loc_140077048
0x140076fae  test    ebx, ebx
0x140076fb0  jns     loc_14007706D
0x140076fb6  mov     r8d, 1DEh
0x140076fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140076fc3  mov     r13, [rsp+78h+arg_0]
0x140076fcb  cmp     rcx, r12
0x140076fce  jz      short loc_140076FF9
0x140076fd0  mov     eax, [rcx+2Ch]
0x140076fd3  mov     edi, 59h ; 'Y'
0x140076fd8  mov     ebp, 4Eh ; 'N'
0x140076fdd  test    al, 40h
0x140076fdf  jnz     loc_14007709A
0x140076fe5  mov     rcx, cs:WPP_GLOBAL_Control
0x140076fec  cmp     rcx, r12
0x140076fef  jz      short loc_140076FF9
0x140076ff1  mov     edx, [rcx+2Ch]
0x140076ff4  test    dl, 40h
0x140076ff7  jnz     short loc_14007701C
0x140076ff9  movzx   eax, sil
0x140076ffd  add     rsp, 40h
0x140077001  pop     r15
0x140077003  pop     r14
0x140077005  pop     r12
0x140077007  pop     rdi
0x140077008  pop     rsi
0x140077009  pop     rbp
0x14007700a  pop     rbx
0x14007700b  retn
0x14007700d  mov     ebx, 0C0000225h
0x140077012  mov     ebp, 15Dh
0x140077017  jmp     loc_140076F90
0x14007701c  mov     rcx, [rcx+18h]
0x140077020  test    sil, sil
0x140077023  mov     [rsp+78h+var_48], ebx
0x140077027  mov     r9d, r15d
0x14007702a  cmovz   edi, ebp
0x14007702d  mov     byte ptr [rsp+78h+var_50], dil
0x140077032  mov     [rsp+78h+var_58], r14
0x140077037  call    WPP_SF_DqcD
0x14007703c  jmp     short loc_140076FF9
0x14007703e  mov     ebp, 151h
0x140077043  jmp     loc_140076F90
0x140077048  mov     rcx, [rcx+18h]
0x14007704c  lea     r8, WPP_f74abd63425539499d784964bfbadaaa_Traceguids
0x140077053  mov     edx, 0Bh
0x140077058  mov     [rsp+78h+var_50], ebp
0x14007705c  mov     r9, r14
0x14007705f  mov     dword ptr [rsp+78h+var_58], ebx
0x140077063  call    WPP_SF_qDD
0x140077068  jmp     loc_140076FAE
0x14007706d  cmp     [rsp+78h+EcpContextSize], 1
0x140077075  jz      short loc_140077087
0x140077077  mov     ebx, 0C000000Dh
0x14007707c  mov     r8d, 1E4h
0x140077082  jmp     loc_140076FBC
0x140077087  mov     rax, [rsp+78h+EcpContext]
0x14007708f  mov     r8d, r13d
0x140077092  movzx   esi, byte ptr [rax]
0x140077095  jmp     loc_140076FBC
0x14007709a  mov     rcx, [rcx+18h]
0x14007709e  test    sil, sil
0x1400770a1  mov     [rsp+78h+var_48], r8d
0x1400770a6  mov     eax, edi
0x1400770a8  cmovz   eax, ebp
0x1400770ab  mov     [rsp+78h+var_50], ebx
0x1400770af  mov     edx, 0Dh
0x1400770b4  mov     byte ptr [rsp+78h+var_58], al
0x1400770b8  mov     r9, r14
0x1400770bb  lea     r8, WPP_f74abd63425539499d784964bfbadaaa_Traceguids
0x1400770c2  call    WPP_SF_qcDD
0x1400770c7  jmp     loc_140076FE5
```
