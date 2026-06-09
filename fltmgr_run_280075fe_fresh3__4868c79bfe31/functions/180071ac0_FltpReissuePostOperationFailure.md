# FltpReissuePostOperationFailure

- ea: `0x180071ac0`
- end: `0x180071ec1`
- name: `FltpReissuePostOperationFailure`
- size: `1025`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180017fc0`

## callees

- `0x1800044e0`
- `0x180009f20`
- `0x180009f80`
- `0x18000a340`
- `0x18000f5b0`
- `0x18001de80`
- `0x180071ac0`
- `0x180071ed0`
- `0x1800722e0`
- `0x180072360`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180071dca`
- `ntoskrnl!ObfDereferenceObject` at `0x180071dca`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x180071c94`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x180071c94`
- `ntoskrnl!IoReplaceFileObjectName` at `0x180071d67`
- `ntoskrnl!IoReplaceFileObjectName` at `0x180071d67`

## pseudocode

```c
__int64 __fastcall FltpReissuePostOperationFailure(PVOID *a1)
{
  unsigned int IrpCtrl; // edi
  __int64 *v2; // rbx
  char v3; // bp
  __int64 v5; // rdx
  char v6; // r13
  char v7; // r15
  unsigned int StreamListCtrl; // eax
  __int64 v10; // rsi
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // r12
  char v15; // al
  __int64 v16; // r14
  WCHAR *v17; // rdx
  __int64 v18; // r12
  unsigned int v19; // esi
  int v20; // eax
  char v21; // al
  int v22; // ecx
  int v23; // ecx
  __int128 Parameter; // [rsp+30h] [rbp-58h] BYREF
  __int64 v25; // [rsp+40h] [rbp-48h]
  PVOID Object; // [rsp+98h] [rbp+10h] BYREF

  IrpCtrl = 0;
  v2 = (__int64 *)(a1 + 2);
  Object = 0;
  v3 = 0;
  Parameter = 0;
  v25 = 0;
  if ( !a1[2] )
  {
    IrpCtrl = FltpAllocateIrpCtrl(*((_QWORD *)*a1 + 8), 1, a1[1], a1 + 2);
    if ( (int)FltpDbgStatus(IrpCtrl, "minkernel\\fs\\filtermgr\\filter\\sectionsup.c", 1525, 0) < 0 )
      return IrpCtrl;
    v3 = 1;
    *(_DWORD *)(*v2 + 4) |= 0x400u;
    IrpCtrl = 0;
  }
  v5 = *v2;
  v6 = 1;
  v7 = 0;
  if ( (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*(_BYTE *)(*v2 + 12) + 22)) & 2) == 0 )
  {
    StreamListCtrl = FltpGetStreamListCtrl(*a1);
    v10 = 0;
    if ( (int)FltpDbgStatus(StreamListCtrl, "minkernel\\fs\\filtermgr\\filter\\sectionsup.c", 1637, 0) < 0 )
      goto LABEL_22;
    goto LABEL_9;
  }
  if ( v5 && (*(_DWORD *)(v5 + 4) & 0x800) != 0 )
  {
    v10 = *(_QWORD *)(v5 + 168);
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 68));
    goto LABEL_9;
  }
  IrpCtrl = FltpOpenFileForFailedSupersede((const UNICODE_STRING **)a1, &Object);
  if ( (int)FltpDbgStatus(IrpCtrl, "minkernel\\fs\\filtermgr\\filter\\sectionsup.c", 1570, 0) >= 0 )
  {
    v19 = FltpGetStreamListCtrl(*a1);
    ObfDereferenceObject(Object);
    v20 = FltpDbgStatus(v19, "minkernel\\fs\\filtermgr\\filter\\sectionsup.c", 1581, 0);
    v10 = 0;
    if ( v20 < 0 )
    {
      IrpCtrl = 0;
      goto LABEL_22;
    }
    v6 = 0;
    IrpCtrl = 0;
    *(_QWORD *)(*v2 + 168) = 0;
LABEL_9:
    v11 = *v2;
    if ( (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*(_BYTE *)(*v2 + 12) + 22)) & 2) != 0 )
    {
      v17 = *(WCHAR **)(v11 + 184);
      if ( v17 )
      {
        v18 = (unsigned int)IoReplaceFileObjectName(*(PFILE_OBJECT *)(v11 + 112), v17, *(_WORD *)(v11 + 176));
        if ( (int)FltpDbgStatus(v18, "minkernel\\fs\\filtermgr\\filter\\sectionsup.c", 1671, 0) < 0 )
        {
          if ( (_DWORD)v18 == -1073741670 )
            IrpCtrl = -1073741670;
          goto LABEL_22;
        }
      }
    }
    v12 = *v2;
    if ( !*v2
      || (*(_DWORD *)(v12 + 4) & 0x800) == 0
      || (v21 = *(_BYTE *)(v12 + 12)) == 0
      || v21 == 6 && ((v22 = *(_DWORD *)(*(_QWORD *)(v12 + 248) + 32LL), v22 == 13) || v22 == 64) )
    {
      v13 = FltpReferenceStreamForSectionConflict(v10);
      if ( (int)FltpDbgStatus(v13, "minkernel\\fs\\filtermgr\\filter\\sectionsup.c", 1710, 0) < 0 )
        goto LABEL_22;
      v7 = 1;
    }
    v14 = (unsigned int)FltpSynchronizeWithDatascan(*v2, v10);
    if ( (int)FltpDbgStatus(v14, "minkernel\\fs\\filtermgr\\filter\\sectionsup.c", 1730, 0) < 0 )
    {
      if ( (_DWORD)v14 != -1073741275 )
        IrpCtrl = v14;
    }
    else
    {
      v15 = *(_BYTE *)(*v2 + 12);
      if ( !v15 || v15 == 6 && ((v23 = *(_DWORD *)(*(_QWORD *)(*v2 + 248) + 32LL), v23 == 13) || v23 == 64) )
      {
        FltpReleaseStreamForSectionConflict(v10);
        v7 = 0;
      }
      *(_QWORD *)&Parameter = a1;
      v16 = (unsigned int)KeExpandKernelStackAndCalloutEx(
                            FltpReissuePostOperationFailureCallout,
                            &Parameter,
                            0x6000u,
                            0,
                            0);
      if ( (int)FltpDbgStatus(v16, "minkernel\\fs\\filtermgr\\filter\\sectionsup.c", 1794, 0) < 0 )
      {
        if ( (_DWORD)v16 == -1073741801 )
          IrpCtrl = -1073741801;
      }
      else
      {
        IrpCtrl = v25;
        v7 = 0;
        if ( !v6 )
          goto LABEL_6;
      }
    }
LABEL_22:
    if ( v10 )
    {
      if ( v7 )
        FltpReleaseStreamForSectionConflict(v10);
      FltpReleaseStreamListCtrl((char *)v10);
    }
  }
LABEL_6:
  if ( v3 && IrpCtrl != -1073741802 )
  {
    FltpFreeIrpCtrl(*v2);
    *v2 = 0;
  }
  return IrpCtrl;
}

```

## disassembly

```asm
0x180071ac0  mov     r11, rsp
0x180071ac3  push    rbx
0x180071ac4  push    rbp
0x180071ac5  push    rdi
0x180071ac6  push    r14
0x180071ac8  sub     rsp, 68h
0x180071acc  xor     edi, edi
0x180071ace  lea     rbx, [rcx+10h]
0x180071ad2  xor     eax, eax
0x180071ad4  mov     [r11+10h], rdi
0x180071ad8  xorps   xmm0, xmm0
0x180071adb  mov     [r11+8], rdi
0x180071adf  xor     bpl, bpl
0x180071ae2  mov     r14, rcx
0x180071ae5  movups  [rsp+88h+Parameter], xmm0
0x180071aea  mov     [r11-48h], rax
0x180071aee  cmp     [rbx], rax
0x180071af1  jz      loc_180071CFE
0x180071af7  mov     rdx, [rbx]
0x180071afa  mov     [rsp+88h+arg_10], rsi
0x180071b02  mov     [rsp+88h+var_28], r12
0x180071b07  lea     r12, FltpOperationFlags
0x180071b0e  mov     [rsp+88h+var_30], r13
0x180071b13  mov     r13b, 1
0x180071b16  movzx   eax, byte ptr [rdx+0Ch]
0x180071b1a  add     al, 16h
0x180071b1c  mov     [rsp+88h+var_38], r15
0x180071b21  movzx   eax, al
0x180071b24  xor     r15b, r15b
0x180071b27  test    byte ptr [rax+r12], 2
0x180071b2c  jz      short loc_180071B9E
0x180071b2e  test    rdx, rdx
0x180071b31  jz      short loc_180071B40
0x180071b33  test    dword ptr [rdx+4], 800h
0x180071b3a  jnz     loc_180071E00
0x180071b40  lea     rdx, [rsp+88h+Object]
0x180071b48  mov     rcx, r14
0x180071b4b  call    FltpOpenFileForFailedSupersede
0x180071b50  mov     r8d, 622h
0x180071b56  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x180071b5d  xor     r9d, r9d
0x180071b60  mov     ecx, eax
0x180071b62  mov     edi, eax
0x180071b64  call    FltpDbgStatus
0x180071b69  test    eax, eax
0x180071b6b  jns     loc_180071DA5
0x180071b71  mov     r15, [rsp+88h+var_38]
0x180071b76  mov     r13, [rsp+88h+var_30]
0x180071b7b  mov     r12, [rsp+88h+var_28]
0x180071b80  mov     rsi, [rsp+88h+arg_10]
0x180071b88  test    bpl, bpl
0x180071b8b  jnz     loc_180071E9F
0x180071b91  mov     eax, edi
0x180071b93  add     rsp, 68h
0x180071b97  pop     r14
0x180071b99  pop     rdi
0x180071b9a  pop     rbp
0x180071b9b  pop     rbx
0x180071b9c  retn
0x180071b9e  mov     rdx, [rdx+70h]
0x180071ba2  lea     r9, [rsp+88h+Entry]
0x180071baa  mov     rcx, [r14]; OwnerId
0x180071bad  xor     r8d, r8d
0x180071bb0  call    FltpGetStreamListCtrl
0x180071bb5  mov     r8d, 665h
0x180071bbb  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x180071bc2  xor     r9d, r9d
0x180071bc5  mov     ecx, eax
0x180071bc7  call    FltpDbgStatus
0x180071bcc  mov     rsi, [rsp+88h+Entry]
0x180071bd4  test    eax, eax
0x180071bd6  js      loc_180071CDF
0x180071bdc  mov     rcx, [rbx]
0x180071bdf  movzx   eax, byte ptr [rcx+0Ch]
0x180071be3  add     al, 16h
0x180071be5  movzx   eax, al
0x180071be8  test    byte ptr [rax+r12], 2
0x180071bed  jnz     loc_180071D4B
0x180071bf3  mov     rcx, [rbx]
0x180071bf6  test    rcx, rcx
0x180071bf9  jz      short loc_180071C08
0x180071bfb  test    dword ptr [rcx+4], 800h
0x180071c02  jnz     loc_180071E24
0x180071c08  mov     rcx, rsi
0x180071c0b  call    FltpReferenceStreamForSectionConflict
0x180071c10  mov     r8d, 6AEh
0x180071c16  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x180071c1d  xor     r9d, r9d
0x180071c20  mov     ecx, eax
0x180071c22  call    FltpDbgStatus
0x180071c27  test    eax, eax
0x180071c29  js      loc_180071CDF
0x180071c2f  mov     r15b, 1
0x180071c32  mov     rcx, [rbx]
0x180071c35  mov     rdx, rsi
0x180071c38  call    FltpSynchronizeWithDatascan
0x180071c3d  mov     r8d, 6C2h
0x180071c43  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x180071c4a  xor     r9d, r9d
0x180071c4d  mov     ecx, eax
0x180071c4f  mov     r12d, eax
0x180071c52  call    FltpDbgStatus
0x180071c57  test    eax, eax
0x180071c59  js      short loc_180071CD4
0x180071c5b  mov     rcx, [rbx]
0x180071c5e  movzx   eax, byte ptr [rcx+0Ch]
0x180071c62  test    al, al
0x180071c64  jnz     loc_180071E59
0x180071c6a  mov     rcx, rsi
0x180071c6d  call    FltpReleaseStreamForSectionConflict
0x180071c72  xor     r15b, r15b
0x180071c75  xor     r9d, r9d; Wait
0x180071c78  mov     qword ptr [rsp+88h+Parameter], r14
0x180071c7d  mov     r8d, 6000h; Size
0x180071c83  mov     [rsp+88h+Context], rdi; Context
0x180071c88  lea     rdx, [rsp+88h+Parameter]; Parameter
0x180071c8d  lea     rcx, FltpReissuePostOperationFailureCallout; Callout
0x180071c94  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x180071c9b  nop     dword ptr [rax+rax+00h]
0x180071ca0  mov     r8d, 702h
0x180071ca6  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x180071cad  mov     ecx, eax
0x180071caf  xor     r9d, r9d
0x180071cb2  mov     r14d, eax
0x180071cb5  call    FltpDbgStatus
0x180071cba  test    eax, eax
0x180071cbc  js      loc_180071E82
0x180071cc2  mov     edi, dword ptr [rsp+88h+var_48]
0x180071cc6  xor     r15b, r15b
0x180071cc9  test    r13b, r13b
0x180071ccc  jz      loc_180071B71
0x180071cd2  jmp     short loc_180071CDF
0x180071cd4  cmp     r12d, 0C0000225h
0x180071cdb  cmovnz  edi, r12d
0x180071cdf  test    rsi, rsi
0x180071ce2  jz      loc_180071B71
0x180071ce8  test    r15b, r15b
0x180071ceb  jnz     loc_180071E92
0x180071cf1  mov     rcx, rsi; Entry
0x180071cf4  call    FltpReleaseStreamListCtrl
0x180071cf9  jmp     loc_180071B71
0x180071cfe  mov     rcx, [rcx]
0x180071d01  mov     r9, rbx
0x180071d04  mov     r8, [r14+8]
0x180071d08  mov     edx, 1
0x180071d0d  mov     rcx, [rcx+40h]
0x180071d11  call    FltpAllocateIrpCtrl
0x180071d16  mov     r8d, 5F5h
0x180071d1c  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x180071d23  xor     r9d, r9d
0x180071d26  mov     ecx, eax
0x180071d28  mov     edi, eax
0x180071d2a  call    FltpDbgStatus
0x180071d2f  test    eax, eax
0x180071d31  js      loc_180071B91
0x180071d37  mov     rax, [rbx]
0x180071d3a  mov     bpl, 1
0x180071d3d  or      dword ptr [rax+4], 400h
0x180071d44  xor     edi, edi
0x180071d46  jmp     loc_180071AF7
0x180071d4b  mov     rdx, [rcx+0B8h]; NewFileName
0x180071d52  test    rdx, rdx
0x180071d55  jz      loc_180071BF3
0x180071d5b  movzx   r8d, word ptr [rcx+0B0h]; FileNameLength
0x180071d63  mov     rcx, [rcx+70h]; FileObject
0x180071d67  call    cs:__imp_IoReplaceFileObjectName
0x180071d6e  nop     dword ptr [rax+rax+00h]
0x180071d73  mov     r8d, 687h
0x180071d79  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x180071d80  mov     ecx, eax
0x180071d82  xor     r9d, r9d
0x180071d85  mov     r12d, eax
0x180071d88  call    FltpDbgStatus
0x180071d8d  test    eax, eax
0x180071d8f  jns     loc_180071BF3
0x180071d95  cmp     r12d, 0C000009Ah
0x180071d9c  cmovz   edi, r12d
0x180071da0  jmp     loc_180071CDF
0x180071da5  mov     rdx, [rsp+88h+Object]
0x180071dad  lea     r9, [rsp+88h+Entry]
0x180071db5  mov     rcx, [r14]; OwnerId
0x180071db8  xor     r8d, r8d
0x180071dbb  call    FltpGetStreamListCtrl
0x180071dc0  mov     rcx, [rsp+88h+Object]; Object
0x180071dc8  mov     esi, eax
0x180071dca  call    cs:__imp_ObfDereferenceObject
0x180071dd1  nop     dword ptr [rax+rax+00h]
0x180071dd6  mov     r8d, 62Dh
0x180071ddc  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x180071de3  xor     r9d, r9d
0x180071de6  mov     ecx, esi
0x180071de8  call    FltpDbgStatus
0x180071ded  mov     rsi, [rsp+88h+Entry]
0x180071df5  test    eax, eax
0x180071df7  jns     short loc_180071E10
0x180071df9  xor     edi, edi
0x180071dfb  jmp     loc_180071CDF
0x180071e00  mov     rsi, [rdx+0A8h]
0x180071e07  lock inc dword ptr [rsi+44h]
0x180071e0b  jmp     loc_180071BDC
0x180071e10  mov     rax, [rbx]
0x180071e13  xor     r13b, r13b
0x180071e16  xor     edi, edi
0x180071e18  mov     [rax+0A8h], rsi
0x180071e1f  jmp     loc_180071BDC
0x180071e24  movzx   eax, byte ptr [rcx+0Ch]
0x180071e28  test    al, al
0x180071e2a  jz      loc_180071C08
0x180071e30  cmp     al, 6
0x180071e32  jnz     loc_180071C32
0x180071e38  mov     rax, [rcx+0F8h]
0x180071e3f  mov     ecx, [rax+20h]
0x180071e42  cmp     ecx, 0Dh
0x180071e45  jz      loc_180071C08
0x180071e4b  cmp     ecx, 40h ; '@'
0x180071e4e  jnz     loc_180071C32
0x180071e54  jmp     loc_180071C08
0x180071e59  cmp     al, 6
0x180071e5b  jnz     loc_180071C75
0x180071e61  mov     rax, [rcx+0F8h]
0x180071e68  mov     ecx, [rax+20h]
0x180071e6b  cmp     ecx, 0Dh
0x180071e6e  jz      loc_180071C6A
0x180071e74  cmp     ecx, 40h ; '@'
0x180071e77  jnz     loc_180071C75
0x180071e7d  jmp     loc_180071C6A
0x180071e82  cmp     r14d, 0C0000017h
0x180071e89  cmovz   edi, r14d
0x180071e8d  jmp     loc_180071CDF
0x180071e92  mov     rcx, rsi
0x180071e95  call    FltpReleaseStreamForSectionConflict
0x180071e9a  jmp     loc_180071CF1
0x180071e9f  cmp     edi, 0C0000016h
0x180071ea5  jz      loc_180071B91
0x180071eab  mov     rcx, [rbx]; BugCheckParameter3
0x180071eae  xor     edx, edx
0x180071eb0  call    FltpFreeIrpCtrl
0x180071eb5  mov     qword ptr [rbx], 0
0x180071ebc  jmp     loc_180071B91
```
