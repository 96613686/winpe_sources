# DfscCreateNetUseConnection

- ea: `0x14001338c`
- end: `0x1400136e9`
- name: `DfscCreateNetUseConnection`
- size: `861`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, int, int, char, __int64)`
- caller_count: `2`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x140014520`
- `0x140029160`

## callees

- `0x1400027f8`
- `0x140002aa0`
- `0x140011a34`
- `0x140011a54`
- `0x14001338c`
- `0x1400136f0`
- `0x140013908`
- `0x140013a00`
- `0x140013cbc`
- `0x1400140bc`
- `0x140017458`
- `0x140025918`
- `0x140025d4c`
- `0x140025d6c`
- `0x140025efc`
- `0x1400264e0`
- `0x140026f60`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400133d9`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400133d9`
- `ntoskrnl!PsRevertToSelf` at `0x14001367f`
- `ntoskrnl!PsRevertToSelf` at `0x14001367f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013696`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013696`

## pseudocode

```c
__int64 __fastcall DfscCreateNetUseConnection(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        char a8,
        __int64 a9)
{
  unsigned int EffectiveRequestorSessionId; // ebx
  const wchar_t *v14; // r8
  char v15; // r14
  unsigned int v16; // eax
  size_t v18; // rdx
  const wchar_t *v19; // r8
  __int64 v20; // rdi
  __int64 DriveLetterNetUseTable; // rax
  __int64 v22; // rcx
  __int64 DevicelessNetUseTable; // rax
  __int64 v24; // rcx
  struct _RTL_AVL_TABLE *CredTable; // rax
  char v27; // [rsp+50h] [rbp-31h] BYREF
  _BYTE v28[3]; // [rsp+51h] [rbp-30h] BYREF
  unsigned int v29; // [rsp+54h] [rbp-2Dh] BYREF
  __int64 v30; // [rsp+58h] [rbp-29h] BYREF
  struct _LUID AuthenticationId; // [rsp+60h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-19h] BYREF

  v29 = 0;
  v30 = 0;
  AuthenticationId = 0;
  v27 = 0;
  DestinationString = 0;
  v28[0] = 0;
  RtlInitUnicodeStringEx(&DestinationString, 0);
  EffectiveRequestorSessionId = DfscGetEffectiveRequestorSessionId(a2, &v29);
  if ( EffectiveRequestorSessionId
    || (EffectiveRequestorSessionId = DfscGetLogonId(&AuthenticationId)) != 0
    || (EffectiveRequestorSessionId = DfscCreateTreeConnectName(a4 + 80, a3, v29, &DestinationString)) != 0 )
  {
LABEL_31:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids,
        EffectiveRequestorSessionId);
    }
    goto LABEL_34;
  }
  v15 = 0;
  if ( !a3 )
    goto LABEL_15;
  if ( !a8 )
  {
    v16 = DfscImpersonateCaller(a2, v28);
    EffectiveRequestorSessionId = v16;
    if ( v16 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids, v16);
      }
      goto LABEL_31;
    }
  }
  EffectiveRequestorSessionId = DfscCreateSymbolicLink(**(_WORD **)(a3 + 8), &DestinationString, v14);
  if ( EffectiveRequestorSessionId )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids,
        &DestinationString);
    }
    goto LABEL_31;
  }
  v15 = 1;
  while ( 1 )
  {
LABEL_15:
    EffectiveRequestorSessionId = DfscCreateNetUseTreeConnection(
                                    (unsigned int)&DestinationString,
                                    a5,
                                    a6,
                                    a7,
                                    a9,
                                    (__int64)&v30);
    if ( EffectiveRequestorSessionId )
      goto LABEL_29;
    if ( a6 != 2 )
      break;
    DfscReleaseTreeConnectionHandle(v30);
    v30 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        EffectiveRequestorSessionId + 12,
        WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids,
        &DestinationString);
    }
    a6 = 1;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_Z(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids,
      &DestinationString);
  v20 = v30;
  EffectiveRequestorSessionId = DfscNetUseAdd(a1, v29, &AuthenticationId, a4, v30, a3, a5, a7, a9, &v27);
  if ( v27 != 1 )
  {
    DfscReleaseTreeConnectionHandle(v20);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids,
        &DestinationString);
    }
  }
  if ( EffectiveRequestorSessionId )
  {
LABEL_29:
    if ( v15 )
      DfscDeleteSymbolicLink(**(_WORD **)(a3 + 8), v18, v19);
    goto LABEL_31;
  }
LABEL_34:
  if ( v28[0] )
    PsRevertToSelf();
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  DriveLetterNetUseTable = DfscGetDriveLetterNetUseTable(a1);
  DfscNetUseTableDump(v22, DriveLetterNetUseTable);
  DevicelessNetUseTable = DfscGetDevicelessNetUseTable(a1);
  DfscNetUseTableDump(v24, DevicelessNetUseTable);
  CredTable = (struct _RTL_AVL_TABLE *)DfscGetCredTable(a1);
  DfscCredTableDump(CredTable);
  return EffectiveRequestorSessionId;
}

```

## disassembly

```asm
0x14001338c  mov     [rsp-8+arg_18], r9
0x140013391  push    rbp
0x140013392  push    rbx
0x140013393  push    rsi
0x140013394  push    rdi
0x140013395  push    r12
0x140013397  push    r13
0x140013399  push    r14
0x14001339b  push    r15
0x14001339d  lea     rbp, [rsp-7]
0x1400133a2  sub     rsp, 88h
0x1400133a9  xor     r12d, r12d
0x1400133ac  mov     rdi, rdx
0x1400133af  mov     r15, rcx
0x1400133b2  mov     [rbp+3Fh+var_6C], r12d
0x1400133b6  xorps   xmm0, xmm0
0x1400133b9  mov     [rbp+3Fh+var_68], r12
0x1400133bd  xor     edx, edx; SourceString
0x1400133bf  mov     qword ptr [rbp+3Fh+AuthenticationId.LowPart], r12
0x1400133c3  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x1400133c7  mov     [rbp+3Fh+var_70], r12b
0x1400133cb  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x1400133cf  mov     [rbp+3Fh+var_6F], r12b
0x1400133d3  mov     r14, r9
0x1400133d6  mov     rsi, r8
0x1400133d9  call    cs:__imp_RtlInitUnicodeStringEx
0x1400133e0  nop     dword ptr [rax+rax+00h]
0x1400133e5  lea     rdx, [rbp+3Fh+var_6C]
0x1400133e9  mov     rcx, rdi
0x1400133ec  call    DfscGetEffectiveRequestorSessionId
0x1400133f1  lea     r13, WPP_GLOBAL_Control
0x1400133f8  mov     ebx, eax
0x1400133fa  test    eax, eax
0x1400133fc  jnz     loc_14001364C
0x140013402  lea     rcx, [rbp+3Fh+AuthenticationId]; AuthenticationId
0x140013406  call    DfscGetLogonId
0x14001340b  mov     ebx, eax
0x14001340d  test    eax, eax
0x14001340f  jnz     loc_14001364C
0x140013415  mov     r8d, [rbp+3Fh+var_6C]
0x140013419  lea     rcx, [r14+50h]
0x14001341d  lea     r9, [rbp+3Fh+DestinationString]
0x140013421  mov     rdx, rsi
0x140013424  call    DfscCreateTreeConnectName
0x140013429  mov     ebx, eax
0x14001342b  test    eax, eax
0x14001342d  jnz     loc_14001364C
0x140013433  mov     r14b, r12b
0x140013436  test    rsi, rsi
0x140013439  jz      loc_1400134E8
0x14001343f  cmp     [rbp+3Fh+arg_38], r12b
0x140013446  jnz     short loc_140013494
0x140013448  lea     rdx, [rbp+3Fh+var_6F]
0x14001344c  mov     rcx, rdi
0x14001344f  call    DfscImpersonateCaller
0x140013454  mov     ebx, eax
0x140013456  test    eax, eax
0x140013458  jz      short loc_140013494
0x14001345a  mov     rcx, cs:WPP_GLOBAL_Control
0x140013461  cmp     rcx, r13
0x140013464  jz      loc_14001364C
0x14001346a  test    dword ptr [rcx+2Ch], 400000h
0x140013471  jz      loc_14001364C
0x140013477  mov     rcx, [rcx+18h]
0x14001347b  lea     edx, [r12+0Ah]
0x140013480  mov     r9d, eax
0x140013483  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x14001348a  call    WPP_SF_D
0x14001348f  jmp     loc_14001364C
0x140013494  mov     rcx, [rsi+8]
0x140013498  lea     rdx, [rbp+3Fh+DestinationString]
0x14001349c  movzx   ecx, word ptr [rcx]
0x14001349f  call    DfscCreateSymbolicLink
0x1400134a4  mov     ebx, eax
0x1400134a6  test    eax, eax
0x1400134a8  jz      short loc_1400134E5
0x1400134aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400134b1  cmp     rcx, r13
0x1400134b4  jz      loc_14001364C
0x1400134ba  test    dword ptr [rcx+2Ch], 400000h
0x1400134c1  jz      loc_14001364C
0x1400134c7  mov     rcx, [rcx+18h]
0x1400134cb  lea     r9, [rbp+3Fh+DestinationString]
0x1400134cf  mov     edx, 0Bh
0x1400134d4  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x1400134db  call    WPP_SF_Z
0x1400134e0  jmp     loc_14001364C
0x1400134e5  mov     r14b, 1
0x1400134e8  mov     r12, [rbp+3Fh+arg_40]
0x1400134ef  mov     r13d, [rbp+3Fh+arg_30]
0x1400134f3  mov     edi, [rbp+3Fh+arg_28]
0x1400134f6  mov     rdx, [rbp+3Fh+arg_20]
0x1400134fa  lea     rax, [rbp+3Fh+var_68]
0x1400134fe  mov     [rsp+0C0h+var_98], rax
0x140013503  lea     rcx, [rbp+3Fh+DestinationString]
0x140013507  mov     r9d, r13d
0x14001350a  mov     [rsp+0C0h+var_A0], r12
0x14001350f  mov     r8d, edi
0x140013512  call    DfscCreateNetUseTreeConnection
0x140013517  mov     ebx, eax
0x140013519  test    eax, eax
0x14001351b  jnz     loc_140013631
0x140013521  cmp     edi, 2
0x140013524  jnz     short loc_140013571
0x140013526  mov     rcx, [rbp+3Fh+var_68]
0x14001352a  call    DfscReleaseTreeConnectionHandle
0x14001352f  mov     [rbp+3Fh+var_68], 0
0x140013537  mov     rcx, cs:WPP_GLOBAL_Control
0x14001353e  lea     rax, WPP_GLOBAL_Control
0x140013545  cmp     rcx, rax
0x140013548  jz      short loc_14001356A
0x14001354a  test    dword ptr [rcx+2Ch], 400000h
0x140013551  jz      short loc_14001356A
0x140013553  mov     rcx, [rcx+18h]
0x140013557  lea     edx, [rbx+0Ch]
0x14001355a  lea     r9, [rbp+3Fh+DestinationString]
0x14001355e  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x140013565  call    WPP_SF_Z
0x14001356a  mov     edi, 1
0x14001356f  jmp     short loc_1400134F6
0x140013571  mov     rcx, cs:WPP_GLOBAL_Control
0x140013578  lea     rax, WPP_GLOBAL_Control
0x14001357f  cmp     rcx, rax
0x140013582  jz      short loc_1400135A6
0x140013584  test    dword ptr [rcx+2Ch], 400000h
0x14001358b  jz      short loc_1400135A6
0x14001358d  mov     rcx, [rcx+18h]
0x140013591  lea     r9, [rbp+3Fh+DestinationString]
0x140013595  mov     edx, 0Dh
0x14001359a  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x1400135a1  call    WPP_SF_Z
0x1400135a6  mov     rdi, [rbp+3Fh+var_68]
0x1400135aa  lea     rax, [rbp+3Fh+var_70]
0x1400135ae  mov     r9, [rbp+3Fh+arg_18]
0x1400135b2  lea     r8, [rbp+3Fh+AuthenticationId]
0x1400135b6  mov     edx, [rbp+3Fh+var_6C]
0x1400135b9  mov     rcx, r15
0x1400135bc  mov     [rsp+0C0h+var_78], rax
0x1400135c1  mov     rax, [rbp+3Fh+arg_20]
0x1400135c5  mov     [rsp+0C0h+var_80], r12
0x1400135ca  mov     [rsp+0C0h+var_88], r13d
0x1400135cf  mov     [rsp+0C0h+var_90], rax
0x1400135d4  mov     [rsp+0C0h+var_98], rsi
0x1400135d9  mov     [rsp+0C0h+var_A0], rdi
0x1400135de  call    DfscNetUseAdd
0x1400135e3  cmp     [rbp+3Fh+var_70], 1
0x1400135e7  mov     ebx, eax
0x1400135e9  jz      short loc_140013628
0x1400135eb  mov     rcx, rdi
0x1400135ee  call    DfscReleaseTreeConnectionHandle
0x1400135f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400135fa  lea     rax, WPP_GLOBAL_Control
0x140013601  cmp     rcx, rax
0x140013604  jz      short loc_140013628
0x140013606  test    dword ptr [rcx+2Ch], 400000h
0x14001360d  jz      short loc_140013628
0x14001360f  mov     rcx, [rcx+18h]
0x140013613  lea     r9, [rbp+3Fh+DestinationString]
0x140013617  mov     edx, 0Eh
0x14001361c  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x140013623  call    WPP_SF_Z
0x140013628  xor     r12d, r12d
0x14001362b  test    ebx, ebx
0x14001362d  jz      short loc_140013679
0x14001362f  jmp     short loc_140013634
0x140013631  xor     r12d, r12d
0x140013634  test    r14b, r14b
0x140013637  jz      short loc_140013645
0x140013639  mov     rcx, [rsi+8]
0x14001363d  movzx   ecx, word ptr [rcx]
0x140013640  call    DfscDeleteSymbolicLink
0x140013645  lea     r13, WPP_GLOBAL_Control
0x14001364c  mov     rcx, cs:WPP_GLOBAL_Control
0x140013653  cmp     rcx, r13
0x140013656  jz      short loc_140013679
0x140013658  test    dword ptr [rcx+2Ch], 400000h
0x14001365f  jz      short loc_140013679
0x140013661  mov     rcx, [rcx+18h]
0x140013665  lea     r8, WPP_c327d774323a32c9dfd0b2a33532fcc9_Traceguids
0x14001366c  mov     edx, 0Fh
0x140013671  mov     r9d, ebx
0x140013674  call    WPP_SF_D
0x140013679  cmp     [rbp+3Fh+var_6F], r12b
0x14001367d  jz      short loc_14001368B
0x14001367f  call    cs:__imp_PsRevertToSelf
0x140013686  nop     dword ptr [rax+rax+00h]
0x14001368b  mov     rcx, [rbp+3Fh+DestinationString.Buffer]; P
0x14001368f  test    rcx, rcx
0x140013692  jz      short loc_1400136A2
0x140013694  xor     edx, edx; Tag
0x140013696  call    cs:__imp_ExFreePoolWithTag
0x14001369d  nop     dword ptr [rax+rax+00h]
0x1400136a2  mov     rcx, r15
0x1400136a5  call    DfscGetDriveLetterNetUseTable
0x1400136aa  mov     rdx, rax
0x1400136ad  call    DfscNetUseTableDump
0x1400136b2  mov     rcx, r15
0x1400136b5  call    DfscGetDevicelessNetUseTable
0x1400136ba  mov     rdx, rax
0x1400136bd  call    DfscNetUseTableDump
0x1400136c2  mov     rcx, r15
0x1400136c5  call    DfscGetCredTable
0x1400136ca  mov     rcx, rax; Table
0x1400136cd  call    DfscCredTableDump
0x1400136d2  mov     eax, ebx
0x1400136d4  add     rsp, 88h
0x1400136db  pop     r15
0x1400136dd  pop     r14
0x1400136df  pop     r13
0x1400136e1  pop     r12
0x1400136e3  pop     rdi
0x1400136e4  pop     rsi
0x1400136e5  pop     rbx
0x1400136e6  pop     rbp
0x1400136e7  retn
```
