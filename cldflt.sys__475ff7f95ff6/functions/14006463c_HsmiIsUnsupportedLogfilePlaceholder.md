# HsmiIsUnsupportedLogfilePlaceholder

- ea: `0x14006463c`
- end: `0x140064865`
- name: `HsmiIsUnsupportedLogfilePlaceholder`
- size: `553`
- prototype: `__int64 __fastcall(__int64, struct _FLT_CALLBACK_DATA *, int, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140063ef8`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14001e1c0`
- `0x14006463c`
- `0x140083f64`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140064730`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400647f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064730`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400647f6`
- `ntoskrnl!ExAllocatePool2` at `0x140064749`
- `ntoskrnl!ExAllocatePool2` at `0x140064749`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14006469f`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14006469f`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140064700`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140064700`

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
        HsmDbgBreakOnStatus(-1073741670);
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
0x14006463c  push    rbx
0x14006463e  push    rbp
0x14006463f  push    rsi
0x140064640  push    rdi
0x140064641  push    r14
0x140064643  sub     rsp, 70h
0x140064647  mov     rax, cs:__security_cookie
0x14006464e  xor     rax, rsp
0x140064651  mov     [rsp+98h+var_38], rax
0x140064656  movups  xmm0, cs:ECP_TYPE_CLFS_OPEN_CONTAINER
0x14006465d  xor     ebx, ebx
0x14006465f  and     r8d, 0FFFF0FFFh
0x140064666  movups  xmm1, xmmword ptr cs:ECP_TYPE_CLFS_CREATE_CONTAINER.Data1
0x14006466d  mov     [r9], bl
0x140064670  mov     r14, r9
0x140064673  cmp     r8d, cs:dword_140029670
0x14006467a  mov     rsi, rdx
0x14006467d  movdqu  [rsp+98h+var_58], xmm0
0x140064683  mov     rbp, rcx
0x140064686  mov     [rsp+98h+EcpList], rbx
0x14006468b  movdqu  [rsp+98h+var_48], xmm1
0x140064691  jnz     short loc_1400646C4
0x140064693  mov     rcx, cs:Filter; Filter
0x14006469a  lea     r8, [rsp+98h+EcpList]; EcpList
0x14006469f  call    cs:__imp_FltGetEcpListFromCallbackData
0x1400646a6  nop     dword ptr [rax+rax+00h]
0x1400646ab  mov     ebx, eax
0x1400646ad  test    eax, eax
0x1400646af  js      short loc_1400646C4
0x1400646b1  mov     rdx, [rsp+98h+EcpList]; EcpList
0x1400646b6  test    rdx, rdx
0x1400646b9  jz      short loc_1400646C4
0x1400646bb  xor     ebx, ebx
0x1400646bd  cmp     ebx, 2
0x1400646c0  jb      short loc_1400646DF
0x1400646c2  xor     ebx, ebx
0x1400646c4  mov     eax, ebx
0x1400646c6  mov     rcx, [rsp+98h+var_38]
0x1400646cb  xor     rcx, rsp; StackCookie
0x1400646ce  call    __security_check_cookie
0x1400646d3  add     rsp, 70h
0x1400646d7  pop     r14
0x1400646d9  pop     rdi
0x1400646da  pop     rsi
0x1400646db  pop     rbp
0x1400646dc  pop     rbx
0x1400646dd  retn
0x1400646df  mov     rcx, cs:Filter; Filter
0x1400646e6  lea     r8, [rsp+98h+var_58]
0x1400646eb  mov     eax, ebx
0x1400646ed  xor     r9d, r9d; EcpContext
0x1400646f0  shl     rax, 4
0x1400646f4  add     r8, rax; EcpType
0x1400646f7  mov     [rsp+98h+EcpContextSize], 0; EcpContextSize
0x140064700  call    cs:__imp_FltFindExtraCreateParameter
0x140064707  nop     dword ptr [rax+rax+00h]
0x14006470c  test    eax, eax
0x14006470e  js      short loc_14006478E
0x140064710  mov     rax, [rsi+10h]
0x140064714  mov     ebx, 528h
0x140064719  xor     edi, edi
0x14006471b  mov     [rsp+98h+var_68], ebx
0x14006471f  mov     rsi, [rax+8]
0x140064723  test    rdi, rdi
0x140064726  jz      short loc_14006473C
0x140064728  mov     edx, 69527348h; Tag
0x14006472d  mov     rcx, rdi; P
0x140064730  call    cs:__imp_ExFreePoolWithTag
0x140064737  nop     dword ptr [rax+rax+00h]
0x14006473c  mov     edx, ebx
0x14006473e  mov     ecx, 100h
0x140064743  mov     r8d, 69527348h
0x140064749  call    cs:__imp_ExAllocatePool2
0x140064750  nop     dword ptr [rax+rax+00h]
0x140064755  mov     rdi, rax
0x140064758  test    rax, rax
0x14006475b  jz      loc_140064807
0x140064761  lea     rax, [rsp+98h+var_68]
0x140064766  mov     r9, rdi
0x140064769  mov     [rsp+98h+var_70], rax
0x14006476e  mov     r8, rsi
0x140064771  xor     edx, edx
0x140064773  mov     dword ptr [rsp+98h+EcpContextSize], ebx
0x140064777  mov     rcx, rbp
0x14006477a  call    HsmpCldGetSyncRootStandardInfo
0x14006477f  mov     ebx, eax
0x140064781  cmp     eax, 80000005h
0x140064786  jnz     short loc_14006479A
0x140064788  mov     ebx, [rsp+98h+var_68]
0x14006478c  jmp     short loc_140064723
0x14006478e  mov     rdx, [rsp+98h+EcpList]
0x140064793  inc     ebx
0x140064795  jmp     loc_1400646BD
0x14006479a  test    ebx, ebx
0x14006479c  jns     short loc_1400647E1
0x14006479e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400647a5  lea     rax, WPP_GLOBAL_Control
0x1400647ac  cmp     rcx, rax
0x1400647af  jz      short loc_1400647EE
0x1400647b1  mov     eax, [rcx+2Ch]
0x1400647b4  test    al, 1
0x1400647b6  jz      short loc_1400647EE
0x1400647b8  cmp     byte ptr [rcx+29h], 2
0x1400647bc  jb      short loc_1400647EE
0x1400647be  mov     rcx, [rcx+18h]
0x1400647c2  lea     r8, WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids
0x1400647c9  mov     edx, 0Bh
0x1400647ce  mov     dword ptr [rsp+98h+var_70], ebx
0x1400647d2  mov     r9, rbp
0x1400647d5  mov     [rsp+98h+EcpContextSize], rsi
0x1400647da  call    WPP_SF_qqd
0x1400647df  jmp     short loc_1400647EE
0x1400647e1  test    dword ptr [rdi+8], 20000h
0x1400647e8  setnbe  al
0x1400647eb  mov     [r14], al
0x1400647ee  mov     edx, 69527348h; Tag
0x1400647f3  mov     rcx, rdi; P
0x1400647f6  call    cs:__imp_ExFreePoolWithTag
0x1400647fd  nop     dword ptr [rax+rax+00h]
0x140064802  jmp     loc_1400646C4
0x140064807  mov     ebx, 0C000009Ah
0x14006480c  mov     ecx, ebx
0x14006480e  call    HsmDbgBreakOnStatus
0x140064813  mov     rcx, cs:WPP_GLOBAL_Control
0x14006481a  lea     rax, WPP_GLOBAL_Control
0x140064821  cmp     rcx, rax
0x140064824  jz      loc_1400646C4
0x14006482a  mov     eax, [rcx+2Ch]
0x14006482d  test    al, 1
0x14006482f  jz      loc_1400646C4
0x140064835  cmp     byte ptr [rcx+29h], 2
0x140064839  jb      loc_1400646C4
0x14006483f  mov     rcx, [rcx+18h]
0x140064843  lea     r8, WPP_666dd97b4df534fdc194a0db3f3e286d_Traceguids
0x14006484a  mov     edx, 0Ah
0x14006484f  mov     dword ptr [rsp+98h+var_70], ebx
0x140064853  mov     r9, rbp
0x140064856  mov     [rsp+98h+EcpContextSize], rsi
0x14006485b  call    WPP_SF_qqd
0x140064860  jmp     loc_1400646C4
```
