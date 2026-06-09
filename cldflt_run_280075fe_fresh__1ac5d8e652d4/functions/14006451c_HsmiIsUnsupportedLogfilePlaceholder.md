# HsmiIsUnsupportedLogfilePlaceholder

- ea: `0x14006451c`
- end: `0x140064745`
- name: `HsmiIsUnsupportedLogfilePlaceholder`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140063dd8`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14001e140`
- `0x14006451c`
- `0x140083da4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140064610`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400646d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064610`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400646d6`
- `ntoskrnl!ExAllocatePool2` at `0x140064629`
- `ntoskrnl!ExAllocatePool2` at `0x140064629`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14006457f`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14006457f`
- `FLTMGR!FltFindExtraCreateParameter` at `0x1400645e0`
- `FLTMGR!FltFindExtraCreateParameter` at `0x1400645e0`

## pseudocode

```c
__int64 __fastcall HsmiIsUnsupportedLogfilePlaceholder(__int64 a1, struct _FLT_CALLBACK_DATA *a2, int a3, bool *a4)
{
  NTSTATUS EcpListFromCallbackData; // ebx
  struct _ECP_LIST *v8; // rdx
  unsigned int i; // ebx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  unsigned int v12; // ebx
  _DWORD *Pool2; // rdi
  PFILE_OBJECT TargetFileObject; // rsi
  int v15; // [rsp+30h] [rbp-68h] BYREF
  PECP_LIST EcpList; // [rsp+38h] [rbp-60h] BYREF
  _OWORD v17[2]; // [rsp+40h] [rbp-58h] BYREF

  EcpListFromCallbackData = 0;
  *a4 = 0;
  v17[0] = ECP_TYPE_CLFS_OPEN_CONTAINER;
  EcpList = 0;
  v17[1] = ECP_TYPE_CLFS_CREATE_CONTAINER;
  if ( (a3 & 0xFFFF0FFF) == dword_140029670 )
  {
    EcpListFromCallbackData = FltGetEcpListFromCallbackData(Filter, a2, &EcpList);
    if ( EcpListFromCallbackData >= 0 )
    {
      v8 = EcpList;
      if ( EcpList )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= 2 )
            return 0;
          if ( FltFindExtraCreateParameter(Filter, v8, (LPCGUID)&v17[i], 0, 0) >= 0 )
            break;
          v8 = EcpList;
        }
        Iopb = a2->Iopb;
        v12 = 1320;
        Pool2 = 0;
        v15 = 1320;
        TargetFileObject = Iopb->TargetFileObject;
        while ( 1 )
        {
          if ( Pool2 )
            ExFreePoolWithTag(Pool2, 0x69527348u);
          Pool2 = (_DWORD *)ExAllocatePool2(256, v12, 1767011144);
          if ( !Pool2 )
            break;
          EcpListFromCallbackData = HsmpCldGetSyncRootStandardInfo(
                                      a1,
                                      0,
                                      (_DWORD)TargetFileObject,
                                      (_DWORD)Pool2,
                                      v12,
                                      (__int64)&v15);
          if ( EcpListFromCallbackData != -2147483643 )
          {
            if ( EcpListFromCallbackData >= 0 )
            {
              *a4 = (Pool2[2] & 0x20000) != 0;
            }
            else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qqd(
                WPP_GLOBAL_Control->AttachedDevice,
                11,
                WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids,
                a1,
                TargetFileObject,
                EcpListFromCallbackData);
            }
            ExFreePoolWithTag(Pool2, 0x69527348u);
            return (unsigned int)EcpListFromCallbackData;
          }
          v12 = v15;
        }
        EcpListFromCallbackData = -1073741670;
        HsmDbgBreakOnStatus(3221225626LL);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqd(
            WPP_GLOBAL_Control->AttachedDevice,
            10,
            WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids,
            a1,
            TargetFileObject,
            -1073741670);
        }
      }
    }
  }
  return (unsigned int)EcpListFromCallbackData;
}

```

## disassembly

```asm
0x14006451c  push    rbx
0x14006451e  push    rbp
0x14006451f  push    rsi
0x140064520  push    rdi
0x140064521  push    r14
0x140064523  sub     rsp, 70h
0x140064527  mov     rax, cs:__security_cookie
0x14006452e  xor     rax, rsp
0x140064531  mov     [rsp+98h+var_38], rax
0x140064536  movups  xmm0, cs:ECP_TYPE_CLFS_OPEN_CONTAINER
0x14006453d  xor     ebx, ebx
0x14006453f  and     r8d, 0FFFF0FFFh
0x140064546  movups  xmm1, xmmword ptr cs:ECP_TYPE_CLFS_CREATE_CONTAINER.Data1
0x14006454d  mov     [r9], bl
0x140064550  mov     r14, r9
0x140064553  cmp     r8d, cs:dword_140029670
0x14006455a  mov     rsi, rdx
0x14006455d  movdqu  [rsp+98h+var_58], xmm0
0x140064563  mov     rbp, rcx
0x140064566  mov     [rsp+98h+EcpList], rbx
0x14006456b  movdqu  [rsp+98h+var_48], xmm1
0x140064571  jnz     short loc_1400645A4
0x140064573  mov     rcx, cs:Filter; Filter
0x14006457a  lea     r8, [rsp+98h+EcpList]; EcpList
0x14006457f  call    cs:__imp_FltGetEcpListFromCallbackData
0x140064586  nop     dword ptr [rax+rax+00h]
0x14006458b  mov     ebx, eax
0x14006458d  test    eax, eax
0x14006458f  js      short loc_1400645A4
0x140064591  mov     rdx, [rsp+98h+EcpList]; EcpList
0x140064596  test    rdx, rdx
0x140064599  jz      short loc_1400645A4
0x14006459b  xor     ebx, ebx
0x14006459d  cmp     ebx, 2
0x1400645a0  jb      short loc_1400645BF
0x1400645a2  xor     ebx, ebx
0x1400645a4  mov     eax, ebx
0x1400645a6  mov     rcx, [rsp+98h+var_38]
0x1400645ab  xor     rcx, rsp; StackCookie
0x1400645ae  call    __security_check_cookie
0x1400645b3  add     rsp, 70h
0x1400645b7  pop     r14
0x1400645b9  pop     rdi
0x1400645ba  pop     rsi
0x1400645bb  pop     rbp
0x1400645bc  pop     rbx
0x1400645bd  retn
0x1400645bf  mov     rcx, cs:Filter; Filter
0x1400645c6  lea     r8, [rsp+98h+var_58]
0x1400645cb  mov     eax, ebx
0x1400645cd  xor     r9d, r9d; EcpContext
0x1400645d0  shl     rax, 4
0x1400645d4  add     r8, rax; EcpType
0x1400645d7  mov     [rsp+98h+EcpContextSize], 0; EcpContextSize
0x1400645e0  call    cs:__imp_FltFindExtraCreateParameter
0x1400645e7  nop     dword ptr [rax+rax+00h]
0x1400645ec  test    eax, eax
0x1400645ee  js      short loc_14006466E
0x1400645f0  mov     rax, [rsi+10h]
0x1400645f4  mov     ebx, 528h
0x1400645f9  xor     edi, edi
0x1400645fb  mov     [rsp+98h+var_68], ebx
0x1400645ff  mov     rsi, [rax+8]
0x140064603  test    rdi, rdi
0x140064606  jz      short loc_14006461C
0x140064608  mov     edx, 69527348h; Tag
0x14006460d  mov     rcx, rdi; P
0x140064610  call    cs:__imp_ExFreePoolWithTag
0x140064617  nop     dword ptr [rax+rax+00h]
0x14006461c  mov     edx, ebx
0x14006461e  mov     ecx, 100h
0x140064623  mov     r8d, 69527348h
0x140064629  call    cs:__imp_ExAllocatePool2
0x140064630  nop     dword ptr [rax+rax+00h]
0x140064635  mov     rdi, rax
0x140064638  test    rax, rax
0x14006463b  jz      loc_1400646E7
0x140064641  lea     rax, [rsp+98h+var_68]
0x140064646  mov     r9, rdi
0x140064649  mov     [rsp+98h+var_70], rax
0x14006464e  mov     r8, rsi
0x140064651  xor     edx, edx
0x140064653  mov     dword ptr [rsp+98h+EcpContextSize], ebx
0x140064657  mov     rcx, rbp
0x14006465a  call    HsmpCldGetSyncRootStandardInfo
0x14006465f  mov     ebx, eax
0x140064661  cmp     eax, 80000005h
0x140064666  jnz     short loc_14006467A
0x140064668  mov     ebx, [rsp+98h+var_68]
0x14006466c  jmp     short loc_140064603
0x14006466e  mov     rdx, [rsp+98h+EcpList]
0x140064673  inc     ebx
0x140064675  jmp     loc_14006459D
0x14006467a  test    ebx, ebx
0x14006467c  jns     short loc_1400646C1
0x14006467e  mov     rcx, cs:WPP_GLOBAL_Control
0x140064685  lea     rax, WPP_GLOBAL_Control
0x14006468c  cmp     rcx, rax
0x14006468f  jz      short loc_1400646CE
0x140064691  mov     eax, [rcx+2Ch]
0x140064694  test    al, 1
0x140064696  jz      short loc_1400646CE
0x140064698  cmp     byte ptr [rcx+29h], 2
0x14006469c  jb      short loc_1400646CE
0x14006469e  mov     rcx, [rcx+18h]
0x1400646a2  lea     r8, WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids
0x1400646a9  mov     edx, 0Bh
0x1400646ae  mov     dword ptr [rsp+98h+var_70], ebx
0x1400646b2  mov     r9, rbp
0x1400646b5  mov     [rsp+98h+EcpContextSize], rsi
0x1400646ba  call    WPP_SF_qqd
0x1400646bf  jmp     short loc_1400646CE
0x1400646c1  test    dword ptr [rdi+8], 20000h
0x1400646c8  setnbe  al
0x1400646cb  mov     [r14], al
0x1400646ce  mov     edx, 69527348h; Tag
0x1400646d3  mov     rcx, rdi; P
0x1400646d6  call    cs:__imp_ExFreePoolWithTag
0x1400646dd  nop     dword ptr [rax+rax+00h]
0x1400646e2  jmp     loc_1400645A4
0x1400646e7  mov     ebx, 0C000009Ah
0x1400646ec  mov     ecx, ebx
0x1400646ee  call    HsmDbgBreakOnStatus
0x1400646f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400646fa  lea     rax, WPP_GLOBAL_Control
0x140064701  cmp     rcx, rax
0x140064704  jz      loc_1400645A4
0x14006470a  mov     eax, [rcx+2Ch]
0x14006470d  test    al, 1
0x14006470f  jz      loc_1400645A4
0x140064715  cmp     byte ptr [rcx+29h], 2
0x140064719  jb      loc_1400645A4
0x14006471f  mov     rcx, [rcx+18h]
0x140064723  lea     r8, WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids
0x14006472a  mov     edx, 0Ah
0x14006472f  mov     dword ptr [rsp+98h+var_70], ebx
0x140064733  mov     r9, rbp
0x140064736  mov     [rsp+98h+EcpContextSize], rsi
0x14006473b  call    WPP_SF_qqd
0x140064740  jmp     loc_1400645A4
```
