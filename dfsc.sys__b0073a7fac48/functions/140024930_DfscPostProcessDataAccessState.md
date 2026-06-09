# DfscPostProcessDataAccessState

- ea: `0x140024930`
- end: `0x140024c48`
- name: `DfscPostProcessDataAccessState`
- size: `792`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x1400239b0`

## callees

- `0x14000136c`
- `0x140002340`
- `0x1400025f4`
- `0x140024930`
- `0x140024db4`

## import_xrefs

- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1400249ca`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1400249ca`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x1400249f3`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x1400249f3`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140024a08`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140024a08`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002497b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002497b`

## pseudocode

```c
__int64 __fastcall DfscPostProcessDataAccessState(__int64 a1)
{
  int v1; // edi
  IRP *v3; // r13
  int v4; // r15d
  void *v5; // rcx
  __int64 *v6; // r14
  unsigned int v7; // ebp
  __int64 v9; // r12
  int v10; // edx
  int v11; // r9d
  int v12; // ecx
  int v13; // eax
  struct _ECP_LIST *ExtraCreateParameter; // [rsp+70h] [rbp+8h] BYREF
  PVOID EcpContext; // [rsp+78h] [rbp+10h] BYREF

  v1 = *(_DWORD *)(a1 + 316);
  v3 = *(IRP **)(a1 + 336);
  v4 = v1;
  if ( v1 < 0 || v1 == 260 )
  {
    v6 = (__int64 *)(a1 + 272);
    v9 = *(_QWORD *)(a1 + 272);
    DfscReplaceFileObjectInformation(a1, v3->Tail.Overlay.CurrentStackLocation->FileObject);
    switch ( v1 )
    {
      case -1073741788:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_437e7fbce0fd321920764c6a18cc1998_Traceguids, a1);
        }
        v7 = 8;
        v1 = 0;
        goto LABEL_7;
      case -1073741225:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            12,
            WPP_437e7fbce0fd321920764c6a18cc1998_Traceguids,
            a1,
            -1073741225);
        }
        v7 = 7;
        v1 = 0;
        goto LABEL_7;
      case -1073741766:
        if ( *(_WORD *)(a1 + 208) <= 2u )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_437e7fbce0fd321920764c6a18cc1998_Traceguids, a1);
          }
LABEL_30:
          v7 = 5;
          *(_BYTE *)(*(_QWORD *)(v9 + 16) + 14LL) = 0;
          goto LABEL_13;
        }
        break;
      default:
        if ( v1 >= 0 )
        {
LABEL_25:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
          {
            WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_437e7fbce0fd321920764c6a18cc1998_Traceguids, a1, v1);
          }
          v1 = 0;
          goto LABEL_6;
        }
        break;
    }
    v10 = 0;
    v11 = 29;
    while ( 1 )
    {
      v12 = (v11 + v10) / 2;
      if ( *((_DWORD *)DfscFailoverErrorList + v12) == v1 )
        break;
      v13 = v12 - 1;
      if ( *((_DWORD *)DfscFailoverErrorList + v12) <= v1 )
        v13 = v11;
      v11 = v13;
      if ( *((_DWORD *)DfscFailoverErrorList + v12) <= v1 )
        v10 = v12 + 1;
      if ( v10 > v13 )
        goto LABEL_25;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_437e7fbce0fd321920764c6a18cc1998_Traceguids, a1, v1);
      v7 = 5;
      *(_BYTE *)(*(_QWORD *)(v9 + 16) + 14LL) = 0;
      goto LABEL_13;
    }
    goto LABEL_30;
  }
  v5 = *(void **)(a1 + 352);
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0);
    *(_QWORD *)(a1 + 352) = 0;
    *(_DWORD *)(a1 + 344) = 0;
  }
  v6 = (__int64 *)(a1 + 272);
LABEL_6:
  v7 = 9;
LABEL_7:
  *(_WORD *)(*(_QWORD *)(*v6 + 16) + 26LL) = *(_WORD *)(*v6 + 32);
  if ( (*(_BYTE *)(a1 + 288) & 4) != 0 )
  {
    EcpContext = 0;
    ExtraCreateParameter = 0;
    if ( !IoGetIrpExtraCreateParameter(v3, &ExtraCreateParameter)
      && ExtraCreateParameter
      && !FsRtlRemoveExtraCreateParameter(ExtraCreateParameter, &GUID_ECP_DOMAIN_SERVICE_NAME_CONTEXT, &EcpContext, 0) )
    {
      FsRtlFreeExtraCreateParameter(EcpContext);
    }
    *(_WORD *)(a1 + 288) &= ~4u;
  }
LABEL_13:
  DfscReferralSetCurrentAccessStatus(*v6, v1);
  *(_DWORD *)(a1 + 316) = v4;
  return v7;
}

```

## disassembly

```asm
0x140024930  mov     [rsp+arg_10], rbx
0x140024935  push    rbp
0x140024936  push    rsi
0x140024937  push    rdi
0x140024938  push    r12
0x14002493a  push    r13
0x14002493c  push    r14
0x14002493e  push    r15
0x140024940  sub     rsp, 30h
0x140024944  mov     edi, [rcx+13Ch]
0x14002494a  mov     rbx, rcx
0x14002494d  mov     r13, [rcx+150h]
0x140024954  mov     r15d, edi
0x140024957  test    edi, edi
0x140024959  js      loc_140024A4C
0x14002495f  cmp     edi, 104h
0x140024965  jz      loc_140024A4C
0x14002496b  mov     rcx, [rcx+160h]; P
0x140024972  xor     esi, esi
0x140024974  test    rcx, rcx
0x140024977  jz      short loc_140024994
0x140024979  xor     edx, edx; Tag
0x14002497b  call    cs:__imp_ExFreePoolWithTag
0x140024982  nop     dword ptr [rax+rax+00h]
0x140024987  mov     [rbx+160h], rsi
0x14002498e  mov     [rbx+158h], esi
0x140024994  lea     r14, [rbx+110h]
0x14002499b  mov     ebp, 9
0x1400249a0  mov     rax, [r14]
0x1400249a3  mov     rdx, [rax+10h]
0x1400249a7  movzx   eax, word ptr [rax+20h]
0x1400249ab  mov     [rdx+1Ah], ax
0x1400249af  test    byte ptr [rbx+120h], 4
0x1400249b6  jz      short loc_140024A20
0x1400249b8  lea     rdx, [rsp+68h+ExtraCreateParameter]; ExtraCreateParameter
0x1400249bd  mov     [rsp+68h+EcpContext], rsi
0x1400249c2  mov     rcx, r13; Irp
0x1400249c5  mov     [rsp+68h+ExtraCreateParameter], rsi
0x1400249ca  call    cs:__imp_IoGetIrpExtraCreateParameter
0x1400249d1  nop     dword ptr [rax+rax+00h]
0x1400249d6  test    eax, eax
0x1400249d8  jnz     short loc_140024A14
0x1400249da  mov     rcx, [rsp+68h+ExtraCreateParameter]; EcpList
0x1400249df  test    rcx, rcx
0x1400249e2  jz      short loc_140024A14
0x1400249e4  xor     r9d, r9d; EcpContextSize
0x1400249e7  lea     r8, [rsp+68h+EcpContext]; EcpContext
0x1400249ec  lea     rdx, GUID_ECP_DOMAIN_SERVICE_NAME_CONTEXT; EcpType
0x1400249f3  call    cs:__imp_FsRtlRemoveExtraCreateParameter
0x1400249fa  nop     dword ptr [rax+rax+00h]
0x1400249ff  test    eax, eax
0x140024a01  jnz     short loc_140024A14
0x140024a03  mov     rcx, [rsp+68h+EcpContext]; EcpContext
0x140024a08  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x140024a0f  nop     dword ptr [rax+rax+00h]
0x140024a14  mov     eax, 0FFFBh
0x140024a19  and     [rbx+120h], ax
0x140024a20  mov     rcx, [r14]
0x140024a23  mov     edx, edi
0x140024a25  call    DfscReferralSetCurrentAccessStatus
0x140024a2a  mov     [rbx+13Ch], r15d
0x140024a31  mov     eax, ebp
0x140024a33  mov     rbx, [rsp+68h+arg_10]
0x140024a3b  add     rsp, 30h
0x140024a3f  pop     r15
0x140024a41  pop     r14
0x140024a43  pop     r13
0x140024a45  pop     r12
0x140024a47  pop     rdi
0x140024a48  pop     rsi
0x140024a49  pop     rbp
0x140024a4a  retn
0x140024a4c  mov     rdx, [r13+0B8h]
0x140024a53  lea     r14, [rcx+110h]
0x140024a5a  mov     r12, [r14]
0x140024a5d  mov     rdx, [rdx+30h]
0x140024a61  call    DfscReplaceFileObjectInformation
0x140024a66  cmp     edi, 0C0000024h
0x140024a6c  jz      loc_140024B5F
0x140024a72  cmp     edi, 0C0000257h
0x140024a78  jz      loc_140024BA1
0x140024a7e  xor     esi, esi
0x140024a80  cmp     edi, 0C000003Ah
0x140024a86  jz      loc_140024B1B
0x140024a8c  test    edi, edi
0x140024a8e  jns     short loc_140024ACA
0x140024a90  mov     edx, esi
0x140024a92  lea     r10, DfscFailoverErrorList
0x140024a99  mov     r9d, 1Dh
0x140024a9f  nop
0x140024aa0  lea     ecx, [r9+rdx]
0x140024aa4  test    ecx, ecx
0x140024aa6  jns     short loc_140024AAA
0x140024aa8  inc     ecx
0x140024aaa  sar     ecx, 1
0x140024aac  movsxd  rax, ecx
0x140024aaf  cmp     [r10+rax*4], edi
0x140024ab3  jz      short loc_140024AF1
0x140024ab5  lea     eax, [rcx-1]
0x140024ab8  cmovle  eax, r9d
0x140024abc  mov     r9d, eax
0x140024abf  lea     eax, [rcx+1]
0x140024ac2  cmovle  edx, eax
0x140024ac5  cmp     edx, r9d
0x140024ac8  jle     short loc_140024AA0
0x140024aca  mov     rcx, cs:WPP_GLOBAL_Control
0x140024ad1  lea     rax, WPP_GLOBAL_Control
0x140024ad8  cmp     rcx, rax
0x140024adb  jz      short loc_140024AEA
0x140024add  test    dword ptr [rcx+2Ch], 200000h
0x140024ae4  jnz     loc_140024C27
0x140024aea  mov     edi, esi
0x140024aec  jmp     loc_14002499B
0x140024af1  mov     rcx, cs:WPP_GLOBAL_Control
0x140024af8  lea     rax, WPP_GLOBAL_Control
0x140024aff  cmp     rcx, rax
0x140024b02  jnz     loc_140024BEB
0x140024b08  mov     rax, [r12+10h]
0x140024b0d  mov     ebp, 5
0x140024b12  mov     [rax+0Eh], sil
0x140024b16  jmp     loc_140024A20
0x140024b1b  cmp     word ptr [rbx+0D0h], 2
0x140024b23  ja      loc_140024A90
0x140024b29  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b30  lea     rax, WPP_GLOBAL_Control
0x140024b37  cmp     rcx, rax
0x140024b3a  jz      short loc_140024B08
0x140024b3c  test    dword ptr [rcx+2Ch], 200000h
0x140024b43  jz      short loc_140024B08
0x140024b45  mov     rcx, [rcx+18h]
0x140024b49  lea     r8, WPP_437e7fbce0fd321920764c6a18cc1998_Traceguids
0x140024b50  mov     edx, 0Dh
0x140024b55  mov     r9, rbx
0x140024b58  call    WPP_SF_q
0x140024b5d  jmp     short loc_140024B08
0x140024b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b66  lea     rax, WPP_GLOBAL_Control
0x140024b6d  cmp     rcx, rax
0x140024b70  jz      short loc_140024B93
0x140024b72  test    dword ptr [rcx+2Ch], 200000h
0x140024b79  jz      short loc_140024B93
0x140024b7b  mov     rcx, [rcx+18h]
0x140024b7f  lea     r8, WPP_437e7fbce0fd321920764c6a18cc1998_Traceguids
0x140024b86  mov     edx, 0Bh
0x140024b8b  mov     r9, rbx
0x140024b8e  call    WPP_SF_q
0x140024b93  xor     esi, esi
0x140024b95  mov     ebp, 8
0x140024b9a  mov     edi, esi
0x140024b9c  jmp     loc_1400249A0
0x140024ba1  mov     rcx, cs:WPP_GLOBAL_Control
0x140024ba8  lea     rax, WPP_GLOBAL_Control
0x140024baf  cmp     rcx, rax
0x140024bb2  jz      short loc_140024BDD
0x140024bb4  test    dword ptr [rcx+2Ch], 200000h
0x140024bbb  jz      short loc_140024BDD
0x140024bbd  mov     rcx, [rcx+18h]
0x140024bc1  lea     r8, WPP_437e7fbce0fd321920764c6a18cc1998_Traceguids
0x140024bc8  mov     edx, 0Ch
0x140024bcd  mov     [rsp+68h+var_48], 0C0000257h
0x140024bd5  mov     r9, rbx
0x140024bd8  call    WPP_SF_qD
0x140024bdd  xor     esi, esi
0x140024bdf  mov     ebp, 7
0x140024be4  mov     edi, esi
0x140024be6  jmp     loc_1400249A0
0x140024beb  test    dword ptr [rcx+2Ch], 200000h
0x140024bf2  jz      loc_140024B08
0x140024bf8  mov     rcx, [rcx+18h]
0x140024bfc  lea     r8, WPP_437e7fbce0fd321920764c6a18cc1998_Traceguids
0x140024c03  mov     edx, 0Eh
0x140024c08  mov     [rsp+68h+var_48], edi
0x140024c0c  mov     r9, rbx
0x140024c0f  call    WPP_SF_qD
0x140024c14  mov     rax, [r12+10h]
0x140024c19  mov     ebp, 5
0x140024c1e  mov     [rax+0Eh], sil
0x140024c22  jmp     loc_140024A20
0x140024c27  mov     rcx, [rcx+18h]
0x140024c2b  lea     r8, WPP_437e7fbce0fd321920764c6a18cc1998_Traceguids
0x140024c32  mov     edx, 0Fh
0x140024c37  mov     [rsp+68h+var_48], edi
0x140024c3b  mov     r9, rbx
0x140024c3e  call    WPP_SF_qD
0x140024c43  jmp     loc_140024AEA
```
