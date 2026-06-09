# RxCreateNetFobx

- ea: `0x14005d6d0`
- end: `0x14005dab6`
- name: `RxCreateNetFobx`
- size: `998`
- prototype: `PMRX_FOBX __stdcall(PRX_CONTEXT RxContext, PMRX_SRV_OPEN MrxSrvOpen)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x14000a0a0`
- `0x140012840`
- `0x140016e20`
- `0x140016e70`
- `0x140059660`
- `0x14005c6c0`
- `0x14005d6d0`
- `0x14005f110`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005d84c`
- `ntoskrnl!ExAllocatePool2` at `0x14005d84c`
- `ntoskrnl!IoGetRequestorProcess` at `0x14005d7f8`
- `ntoskrnl!IoGetRequestorProcess` at `0x14005d7f8`

## pseudocode

```c
PMRX_FOBX __stdcall RxCreateNetFobx(PRX_CONTEXT RxContext, PMRX_SRV_OPEN MrxSrvOpen)
{
  POOL_TYPE v4; // r8d
  char v5; // r12
  _DWORD *Context2; // r14
  int v7; // eax
  struct _MRX_FOBX_ *AlreadyAllocatedObject; // rdi
  int v9; // r9d
  char v10; // r15
  PSZ FileName; // r8
  int v12; // eax
  int v13; // eax
  PSZ v14; // rax
  int v15; // ebp
  PEPROCESS RequestorProcess; // rax
  int v17; // eax
  NODE_TYPE_CODE *Pool2; // rax
  PMRX_SRV_OPEN *Key; // rdx
  struct _RDBSS_DEVICE_OBJECT *NonPagedFcb; // rcx
  int v21; // eax
  int v22; // eax
  ULONG *p_Flags; // rax
  int v25; // eax

  if ( !RxContext->pFobx )
  {
    v4 = 64;
    v5 = 0;
    Context2 = MrxSrvOpen->Context2;
    v7 = Context2[39];
    if ( (v7 & 4) == 0 )
      v4 = 256;
    if ( (v7 & 0x40000000) != 0 || MrxSrvOpen != *((PMRX_SRV_OPEN *)Context2 + 51) )
    {
      NonPagedFcb = (struct _RDBSS_DEVICE_OBJECT *)RxContext->NonPagedFcb;
      v10 = 0;
      if ( ((__int64)MrxSrvOpen->Key & 0x20000) != 0 )
      {
        AlreadyAllocatedObject = (struct _MRX_FOBX_ *)RxAllocateFcbObject(NonPagedFcb, 0xEC30u, v4, 0, 0);
        v9 = 0;
      }
      else
      {
        AlreadyAllocatedObject = *(struct _MRX_FOBX_ **)&MrxSrvOpen[1].DesiredAccess;
        RxAllocateFcbObject(NonPagedFcb, 0xEC30u, v4, 0, AlreadyAllocatedObject);
        LODWORD(MrxSrvOpen->Key) |= 0x20000u;
        v9 = 0x4000000;
        v5 = 1;
      }
    }
    else
    {
      AlreadyAllocatedObject = (struct _MRX_FOBX_ *)*((_QWORD *)Context2 + 52);
      RxAllocateFcbObject((PRDBSS_DEVICE_OBJECT)RxContext->NonPagedFcb, 0xEC30u, v4, 0, AlreadyAllocatedObject);
      Context2[39] |= 0x40000000u;
      v9 = 0x4000000;
      v10 = 1;
    }
    if ( AlreadyAllocatedObject )
    {
      FileName = RxContext->TrackerHistory[0].FileName;
      if ( FileName )
      {
        v12 = *((_DWORD *)FileName + 20);
        if ( v12 == 7 )
        {
          v13 = *((_DWORD *)FileName + 29);
          if ( v13 )
          {
            *(_QWORD *)&AlreadyAllocatedObject[2].Flags = (unsigned int)(10000 * v13);
            v25 = *((_DWORD *)FileName + 30) / *((_DWORD *)FileName + 29);
            LODWORD(AlreadyAllocatedObject[2].Context2) = 0;
            HIDWORD(AlreadyAllocatedObject[2].Context2) = v25;
          }
        }
        else if ( v12 == 17 )
        {
          v21 = *((_DWORD *)FileName + 27);
          if ( v21 )
          {
            AlreadyAllocatedObject[2].UnicodeQueryTemplate.Buffer = (wchar_t *)(unsigned int)(10000 * v21);
            v22 = *((_DWORD *)FileName + 28) / *((_DWORD *)FileName + 27);
            *(_DWORD *)&AlreadyAllocatedObject[2].UnicodeQueryTemplate.Length = 0;
            HIDWORD(AlreadyAllocatedObject[2].PipeHandleInformation) = v22;
          }
          if ( *((int *)&RxContext->9 + 38) <= 1 )
            BYTE4(AlreadyAllocatedObject[2].AssociatedFileObject) = 1;
        }
      }
      if ( (BYTE2(RxContext->TrackerHistory[4].FileName) & 1) != 0 )
        v9 |= 0x2000000u;
      v14 = RxContext->TrackerHistory[1].FileName;
      v15 = v9 | 4;
      if ( (*((_DWORD *)&RxContext->9 + 35) & 0x4000) == 0 )
        v15 = v9;
      if ( v14 && *((int *)v14 + 3) < 0 )
        v15 |= 8u;
      *(_DWORD *)&AlreadyAllocatedObject[1].NodeTypeCode = v15;
      AlreadyAllocatedObject->NodeReferenceCount = 1;
      AlreadyAllocatedObject[2].NodeByteSize = 0;
      AlreadyAllocatedObject[3].Context2 = (PVOID)*((_QWORD *)Context2 + 50);
      RequestorProcess = IoGetRequestorProcess(RxContext->CurrentIrp);
      *(_QWORD *)&AlreadyAllocatedObject->Flags = Context2;
      *(_QWORD *)&AlreadyAllocatedObject[3].Flags = RequestorProcess;
      *(_QWORD *)&AlreadyAllocatedObject[1].OffsetOfNextEaToReturn = (char *)AlreadyAllocatedObject + 128;
      AlreadyAllocatedObject[1].UnicodeQueryTemplate.Buffer = (wchar_t *)(&AlreadyAllocatedObject[1].PipeHandleInformation
                                                                        + 1);
      AlreadyAllocatedObject->Context = &AlreadyAllocatedObject->AssociatedFileObject;
      AlreadyAllocatedObject->AssociatedFileObject = (PFILE_OBJECT)&AlreadyAllocatedObject->AssociatedFileObject;
      v17 = RxInitailizeFobxPowerState(AlreadyAllocatedObject);
      if ( v17 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            71,
            WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
            (unsigned int)v17);
        }
        if ( (v15 & 0x4000000) != 0 )
        {
          if ( v10 )
            Context2[39] &= ~0x40000000u;
          if ( v5 )
            LODWORD(MrxSrvOpen->Key) &= ~0x20000u;
          goto LABEL_59;
        }
      }
      else
      {
        Pool2 = (NODE_TYPE_CODE *)ExAllocatePool2(64, 16, 1061124178);
        AlreadyAllocatedObject[1].Context2 = Pool2;
        if ( Pool2 )
        {
          *Pool2 = AlreadyAllocatedObject->NodeTypeCode;
          *((_WORD *)AlreadyAllocatedObject[1].Context2 + 1) = 16;
          RfsInitializeRundownProtection((char *)AlreadyAllocatedObject[1].Context2 + 8);
LABEL_22:
          RxContext->pFobx = AlreadyAllocatedObject;
          goto LABEL_23;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            72,
            WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
            3221225626LL);
        }
        if ( (v15 & 0x4000000) != 0 )
        {
          if ( v10 )
            Context2[39] &= ~0x40000000u;
          if ( v5 )
            LODWORD(MrxSrvOpen->Key) &= ~0x20000u;
          goto LABEL_59;
        }
      }
      RxFreeFcbObject(AlreadyAllocatedObject);
LABEL_59:
      AlreadyAllocatedObject = 0;
      goto LABEL_22;
    }
  }
LABEL_23:
  if ( RxContext->pFobx )
  {
    RxReference(MrxSrvOpen);
    _InterlockedIncrement((volatile signed __int32 *)&MrxSrvOpen->ShadowContext[1].LockKey);
    BYTE2(MrxSrvOpen->ShadowContext[4].UnderlyingDeviceObject) = 0;
    *(_QWORD *)&RxContext->pFobx->Flags = RxContext->pFcb;
    Key = (PMRX_SRV_OPEN *)MrxSrvOpen[1].Key;
    if ( *Key != (PMRX_SRV_OPEN)&MrxSrvOpen[1].UncleanFobxCount )
      __fastfail(3u);
    p_Flags = &RxContext->pFobx[1].Flags;
    *(_QWORD *)p_Flags = (char *)MrxSrvOpen + 184;
    *((_QWORD *)p_Flags + 1) = Key;
    *Key = (PMRX_SRV_OPEN)p_Flags;
    MrxSrvOpen[1].Key = p_Flags;
    RxContext->pFobx->Context2 = MrxSrvOpen;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids, RxContext->pFobx);
  }
  return RxContext->pFobx;
}

```

## disassembly

```asm
0x14005d6d0  push    rbx
0x14005d6d2  push    rsi
0x14005d6d3  push    rdi
0x14005d6d4  push    r13
0x14005d6d6  sub     rsp, 38h
0x14005d6da  cmp     qword ptr [rcx+40h], 0
0x14005d6df  lea     r13, WPP_GLOBAL_Control
0x14005d6e6  mov     rsi, rdx
0x14005d6e9  mov     rbx, rcx
0x14005d6ec  mov     edi, 100h
0x14005d6f1  jnz     loc_14005D8A8
0x14005d6f7  mov     [rsp+58h+arg_8], r12
0x14005d6fc  mov     r8d, 40h ; '@'
0x14005d702  mov     [rsp+58h+arg_10], r14
0x14005d707  xor     r12b, r12b
0x14005d70a  mov     r14, [rdx+20h]
0x14005d70e  mov     [rsp+58h+var_28], r15
0x14005d713  mov     eax, [r14+9Ch]
0x14005d71a  test    al, 4
0x14005d71c  cmovz   r8d, edi; PoolType
0x14005d720  bt      eax, 1Eh
0x14005d724  jb      loc_14005D8F5
0x14005d72a  cmp     rdx, [r14+198h]
0x14005d731  jnz     loc_14005D8F5
0x14005d737  mov     rdi, [r14+1A0h]
0x14005d73e  mov     edx, 0EC30h; NodeType
0x14005d743  mov     rcx, [rcx+50h]; RxDeviceObject
0x14005d747  xor     r9d, r9d; NameSize
0x14005d74a  mov     [rsp+58h+AlreadyAllocatedObject], rdi; AlreadyAllocatedObject
0x14005d74f  call    RxAllocateFcbObject
0x14005d754  or      dword ptr [r14+9Ch], 40000000h
0x14005d75f  mov     r9d, 4000000h
0x14005d765  mov     r15b, 1
0x14005d768  test    rdi, rdi
0x14005d76b  jz      loc_14005D894
0x14005d771  mov     r8, [rbx+288h]
0x14005d778  mov     [rsp+58h+arg_0], rbp
0x14005d77d  test    r8, r8
0x14005d780  jz      short loc_14005D79B
0x14005d782  mov     eax, [r8+50h]
0x14005d786  cmp     eax, 7
0x14005d789  jnz     loc_14005D933
0x14005d78f  mov     eax, [r8+74h]
0x14005d793  test    eax, eax
0x14005d795  jnz     loc_14005D9F1
0x14005d79b  test    byte ptr [rbx+2EAh], 1
0x14005d7a2  jz      short loc_14005D7A9
0x14005d7a4  bts     r9d, 19h
0x14005d7a9  mov     rax, [rbx+2A0h]
0x14005d7b0  mov     ebp, r9d
0x14005d7b3  or      ebp, 4
0x14005d7b6  test    dword ptr [rbx+21Ch], 4000h
0x14005d7c0  cmovz   ebp, r9d
0x14005d7c4  test    rax, rax
0x14005d7c7  jz      short loc_14005D7D3
0x14005d7c9  cmp     dword ptr [rax+0Ch], 0
0x14005d7cd  jl      loc_14005DA1D
0x14005d7d3  mov     [rdi+48h], ebp
0x14005d7d6  mov     dword ptr [rdi+4], 1
0x14005d7dd  mov     word ptr [rdi+92h], 0
0x14005d7e6  mov     rax, [r14+190h]
0x14005d7ed  mov     [rdi+0F8h], rax
0x14005d7f4  mov     rcx, [rbx+28h]; Irp
0x14005d7f8  call    cs:__imp_IoGetRequestorProcess
0x14005d7ff  nop     dword ptr [rax+rax+00h]
0x14005d804  mov     [rdi+28h], r14
0x14005d808  mov     rcx, rdi
0x14005d80b  mov     [rdi+100h], rax
0x14005d812  lea     rax, [rdi+80h]
0x14005d819  mov     [rax+8], rax
0x14005d81d  mov     [rax], rax
0x14005d820  lea     rax, [rdi+10h]
0x14005d824  mov     [rax+8], rax
0x14005d828  mov     [rax], rax
0x14005d82b  call    RxInitailizeFobxPowerState
0x14005d830  test    eax, eax
0x14005d832  js      loc_14005DA25
0x14005d838  mov     r13d, 10h
0x14005d83e  mov     r8d, 3F3F7852h
0x14005d844  mov     edx, r13d
0x14005d847  mov     ecx, 40h ; '@'
0x14005d84c  call    cs:__imp_ExAllocatePool2
0x14005d853  nop     dword ptr [rax+rax+00h]
0x14005d858  mov     [rdi+68h], rax
0x14005d85c  mov     rcx, rax
0x14005d85f  test    rax, rax
0x14005d862  jz      loc_14005DA69
0x14005d868  movzx   eax, word ptr [rdi]
0x14005d86b  mov     [rcx], ax
0x14005d86e  mov     rax, [rdi+68h]
0x14005d872  mov     [rax+2], r13w
0x14005d877  mov     rcx, [rdi+68h]
0x14005d87b  add     rcx, 8
0x14005d87f  call    RfsInitializeRundownProtection
0x14005d884  lea     r13, WPP_GLOBAL_Control
0x14005d88b  mov     rbp, [rsp+58h+arg_0]
0x14005d890  mov     [rbx+40h], rdi
0x14005d894  mov     r15, [rsp+58h+var_28]
0x14005d899  mov     edi, 100h
0x14005d89e  mov     r12, [rsp+58h+arg_8]
0x14005d8a3  mov     r14, [rsp+58h+arg_10]
0x14005d8a8  cmp     qword ptr [rbx+40h], 0
0x14005d8ad  jz      loc_14005D9B0
0x14005d8b3  mov     rcx, rsi; Instance
0x14005d8b6  call    RxReference
0x14005d8bb  mov     rax, [rsi+28h]
0x14005d8bf  lock inc dword ptr [rax+40h]
0x14005d8c3  mov     rax, [rsi+28h]
0x14005d8c7  mov     byte ptr [rax+0CAh], 0
0x14005d8ce  mov     rcx, [rbx+40h]
0x14005d8d2  mov     rax, [rbx+38h]
0x14005d8d6  mov     [rcx+28h], rax
0x14005d8da  lea     rcx, [rsi+0B8h]
0x14005d8e1  mov     rdx, [rcx+8]
0x14005d8e5  cmp     [rdx], rcx
0x14005d8e8  jz      loc_14005D992
0x14005d8ee  mov     ecx, 3
0x14005d8f3  int     29h; Win8: RtlFailFast(ecx)
0x14005d8f5  mov     rcx, [rcx+50h]; RxDeviceObject
0x14005d8f9  xor     r15b, r15b
0x14005d8fc  xor     r9d, r9d; NameSize
0x14005d8ff  test    dword ptr [rdx+48h], 20000h
0x14005d906  jnz     short loc_14005D974
0x14005d908  mov     rdi, [rdx+0C8h]
0x14005d90f  mov     edx, 0EC30h; NodeType
0x14005d914  mov     [rsp+58h+AlreadyAllocatedObject], rdi; AlreadyAllocatedObject
0x14005d919  call    RxAllocateFcbObject
0x14005d91e  or      dword ptr [rsi+48h], 20000h
0x14005d925  mov     r9d, 4000000h
0x14005d92b  mov     r12b, 1
0x14005d92e  jmp     loc_14005D768
0x14005d933  cmp     eax, 11h
0x14005d936  jnz     loc_14005D79B
0x14005d93c  mov     eax, [r8+6Ch]
0x14005d940  test    eax, eax
0x14005d942  jz      loc_14007D206
0x14005d948  imul    ecx, eax, 2710h
0x14005d94e  xor     edx, edx
0x14005d950  mov     [rdi+0C8h], rcx
0x14005d957  mov     eax, [r8+70h]
0x14005d95b  div     dword ptr [r8+6Ch]
0x14005d95f  mov     dword ptr [rdi+0C0h], 0
0x14005d969  mov     [rdi+0C4h], eax
0x14005d96f  jmp     loc_14007D206
0x14005d974  mov     edx, 0EC30h; NodeType
0x14005d979  mov     [rsp+58h+AlreadyAllocatedObject], 0; AlreadyAllocatedObject
0x14005d982  call    RxAllocateFcbObject
0x14005d987  mov     rdi, rax
0x14005d98a  xor     r9d, r9d
0x14005d98d  jmp     loc_14005D768
0x14005d992  mov     rax, [rbx+40h]
0x14005d996  add     rax, 70h ; 'p'
0x14005d99a  mov     [rax], rcx
0x14005d99d  mov     [rax+8], rdx
0x14005d9a1  mov     [rdx], rax
0x14005d9a4  mov     [rcx+8], rax
0x14005d9a8  mov     rax, [rbx+40h]
0x14005d9ac  mov     [rax+20h], rsi
0x14005d9b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d9b7  cmp     rcx, r13
0x14005d9ba  jnz     short loc_14005D9CB
0x14005d9bc  mov     rax, [rbx+40h]
0x14005d9c0  add     rsp, 38h
0x14005d9c4  pop     r13
0x14005d9c6  pop     rdi
0x14005d9c7  pop     rsi
0x14005d9c8  pop     rbx
0x14005d9c9  retn
0x14005d9cb  test    [rcx+2Ch], edi
0x14005d9ce  jz      short loc_14005D9BC
0x14005d9d0  cmp     byte ptr [rcx+29h], 4
0x14005d9d4  jb      short loc_14005D9BC
0x14005d9d6  mov     r9, [rbx+40h]
0x14005d9da  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x14005d9e1  mov     rcx, [rcx+18h]
0x14005d9e5  mov     edx, 49h ; 'I'
0x14005d9ea  call    WPP_SF_q
0x14005d9ef  jmp     short loc_14005D9BC
0x14005d9f1  imul    ecx, eax, 2710h
0x14005d9f7  xor     edx, edx
0x14005d9f9  mov     [rdi+0B8h], rcx
0x14005da00  mov     eax, [r8+78h]
0x14005da04  div     dword ptr [r8+74h]
0x14005da08  mov     dword ptr [rdi+0B0h], 0
0x14005da12  mov     [rdi+0B4h], eax
0x14005da18  jmp     loc_14005D79B
0x14005da1d  or      ebp, 8
0x14005da20  jmp     loc_14005D7D3
0x14005da25  mov     rcx, cs:WPP_GLOBAL_Control
0x14005da2c  cmp     rcx, r13
0x14005da2f  jz      loc_14007D21F
0x14005da35  mov     edx, [rcx+2Ch]
0x14005da38  test    dl, 1
0x14005da3b  jz      loc_14007D21F
0x14005da41  cmp     byte ptr [rcx+29h], 1
0x14005da45  jb      loc_14007D21F
0x14005da4b  mov     rcx, [rcx+18h]
0x14005da4f  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x14005da56  mov     edx, 47h ; 'G'
0x14005da5b  mov     r9d, eax
0x14005da5e  call    WPP_SF_d
0x14005da63  nop
0x14005da64  jmp     loc_14007D21F
0x14005da69  mov     rcx, cs:WPP_GLOBAL_Control
0x14005da70  lea     r13, WPP_GLOBAL_Control
0x14005da77  cmp     rcx, r13
0x14005da7a  jz      loc_14007D243
0x14005da80  mov     eax, [rcx+2Ch]
0x14005da83  test    al, 1
0x14005da85  jz      loc_14007D243
0x14005da8b  cmp     byte ptr [rcx+29h], 1
0x14005da8f  jb      loc_14007D243
0x14005da95  mov     rcx, [rcx+18h]
0x14005da99  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x14005daa0  mov     edx, 48h ; 'H'
0x14005daa5  mov     r9d, 0C000009Ah
0x14005daab  call    WPP_SF_d
0x14005dab0  nop
0x14005dab1  jmp     loc_14007D243
0x14007d206  cmp     dword ptr [rbx+228h], 1
0x14007d20d  jg      loc_14005D79B
0x14007d213  mov     byte ptr [rdi+0A4h], 1
0x14007d21a  jmp     loc_14005D79B
0x14007d21f  bt      ebp, 1Ah
0x14007d223  jnb     short loc_14007D267
0x14007d225  test    r15b, r15b
0x14007d228  jz      short loc_14007D235
0x14007d22a  and     dword ptr [r14+9Ch], 0BFFFFFFFh
0x14007d235  test    r12b, r12b
0x14007d238  jz      short loc_14007D26F
0x14007d23a  and     dword ptr [rsi+48h], 0FFFDFFFFh
0x14007d241  jmp     short loc_14007D26F
0x14007d243  bt      ebp, 1Ah
0x14007d247  jnb     short loc_14007D267
0x14007d249  test    r15b, r15b
0x14007d24c  jz      short loc_14007D259
0x14007d24e  and     dword ptr [r14+9Ch], 0BFFFFFFFh
0x14007d259  test    r12b, r12b
0x14007d25c  jz      short loc_14007D26F
0x14007d25e  and     dword ptr [rsi+48h], 0FFFDFFFFh
0x14007d265  jmp     short loc_14007D26F
0x14007d267  mov     rcx, rdi; Object
0x14007d26a  call    RxFreeFcbObject
0x14007d26f  xor     edi, edi
0x14007d271  jmp     loc_14005D88B
```
