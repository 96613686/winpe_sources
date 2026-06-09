# NtfsIsReparseRequired

- ea: `0x1401b8ec0`
- end: `0x1401b9305`
- name: `NtfsIsReparseRequired`
- size: `1093`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x14019f350`

## callees

- `0x140007ea0`
- `0x1401b8ec0`
- `0x1401ba674`

## import_xrefs

- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1401b8f66`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1401b8f66`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401b8f8f`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401b8f8f`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1401b8fe0`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1401b8fe0`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b90c4`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b91b5`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b90c4`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b91b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b9114`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b918d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b9205`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b9248`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b9114`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b918d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b9205`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b9248`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b90e6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b9140`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b91d7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b90e6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b9140`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b91d7`

## pseudocode

```c
bool __fastcall NtfsIsReparseRequired(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  BOOL v7; // r14d
  __int64 v8; // rcx
  int v9; // esi
  __int64 v11; // rsi
  __int64 v12; // rcx
  int v13; // ebx
  NTSTATUS v14; // eax
  _DWORD *i; // rax
  bool v16; // cl
  bool v17; // al
  __int64 v18; // rdx
  int v19; // r12d
  struct _ERESOURCE *v20; // rcx
  BOOL v21; // r13d
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 *v24; // rax
  __int64 *v25; // rcx
  __int16 v26; // dx
  int v27; // ebx
  __int64 v28; // r12
  __int64 v29; // rcx
  int v30; // ecx
  __int64 v31; // rdx
  __int64 v32; // rax
  struct _ECP_LIST *ExtraCreateParameter; // [rsp+68h] [rbp+10h] BYREF
  PVOID EcpContext; // [rsp+78h] [rbp+20h] BYREF

  v3 = *(_QWORD *)(a2 + 96);
  v7 = 1;
  v8 = *(_QWORD *)(v3 + 328);
  if ( v8 )
  {
    v19 = 0;
    v20 = *(struct _ERESOURCE **)(v8 + 136);
    v21 = 1;
    ExtraCreateParameter = *(struct _ECP_LIST **)(a2 + 184);
    if ( !ExIsResourceAcquiredSharedLite(v20) )
    {
      ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(v3 + 328) + 136LL), 1u);
      v19 = 1;
    }
    v22 = *(_QWORD *)(v3 + 328);
    if ( (*(_DWORD *)(v22 + 4) & 1) != 0 )
    {
      v31 = *(_QWORD *)(v22 + 24);
      if ( v31 )
        v21 = ExtraCreateParameter == *(struct _ECP_LIST **)(v31 + 232);
    }
    if ( v19 == 1 )
      ExReleaseResourceLite(*(PERESOURCE *)(v22 + 136));
    if ( !v21 )
    {
      ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(v3 + 328) + 136LL), 1u);
      v23 = *(_QWORD *)(v3 + 328);
      v24 = *(__int64 **)(v23 + 88);
      v25 = (__int64 *)(v23 + 88);
      if ( v24 != (__int64 *)(v23 + 88) )
      {
        while ( 1 )
        {
          v26 = *((_WORD *)v24 + 39);
          if ( (v26 & 1) != 0 && (v26 & 8) == 0 )
            break;
          v24 = (__int64 *)*v24;
          if ( v24 == v25 )
            goto LABEL_54;
        }
        if ( v24 != v25 )
        {
          v9 = *((_DWORD *)v24 + 16);
          ExReleaseResourceLite(*(PERESOURCE *)(v23 + 136));
          goto LABEL_3;
        }
      }
LABEL_54:
      ExReleaseResourceLite(*(PERESOURCE *)(v23 + 136));
    }
  }
  v9 = *(_DWORD *)(v3 + 176);
LABEL_3:
  if ( (v9 & 0x400) == 0 )
    return 0;
  v11 = *(_QWORD *)(a2 + 96);
  LODWORD(ExtraCreateParameter) = 0;
  v12 = *(_QWORD *)(v11 + 328);
  if ( !v12 )
    goto LABEL_6;
  v27 = 0;
  v28 = *(_QWORD *)(a2 + 184);
  if ( !ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(v12 + 136)) )
  {
    ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(v11 + 328) + 136LL), 1u);
    v27 = 1;
  }
  v29 = *(_QWORD *)(v11 + 328);
  if ( (*(_DWORD *)(v29 + 4) & 1) != 0 )
  {
    v32 = *(_QWORD *)(v29 + 24);
    if ( v32 )
      v7 = v28 == *(_QWORD *)(v32 + 232);
  }
  if ( v27 == 1 )
    ExReleaseResourceLite(*(PERESOURCE *)(v29 + 136));
  if ( v7 )
  {
LABEL_6:
    v13 = *(_DWORD *)(v11 + 180);
  }
  else
  {
    TxfGetTransFileInfo(v11, &EcpContext, &ExtraCreateParameter);
    v13 = (int)ExtraCreateParameter;
  }
  ExtraCreateParameter = 0;
  EcpContext = 0;
  if ( *(_DWORD *)(a2 + 200) != v13 )
  {
    *(_DWORD *)(a2 + 200) = v13;
    *(_QWORD *)(a2 + 216) = 0;
    if ( IoGetIrpExtraCreateParameter(*(PIRP *)(a1 + 112), &ExtraCreateParameter) >= 0 )
    {
      if ( ExtraCreateParameter )
      {
        v14 = FsRtlFindExtraCreateParameter(ExtraCreateParameter, &ECP_TYPE_OPEN_REPARSE_GUID, &EcpContext, 0);
        if ( v14 < 0 )
        {
          if ( NtfsStatusDebugFlags
            && (unsigned int)v14 < 0xFFFFFFED
            && v14 != -1073741802
            && v14 != -1073741807
            && (unsigned int)(v14 + 2147483643) > 1
            && v14 != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(0, (unsigned int)v14, 657792);
          }
        }
        else
        {
          for ( i = *(_DWORD **)EcpContext; i != EcpContext; i = *(_DWORD **)i )
          {
            if ( i[4] == v13 )
            {
              *(_QWORD *)(a2 + 216) = i;
              break;
            }
          }
        }
      }
    }
  }
  v16 = (*(_DWORD *)(*(_QWORD *)(a2 + 96) + 176LL) & 0x10000000) != 0
     && (unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(*(unsigned int *)(a2 + 200));
  v17 = !*(_WORD *)a3 || **(_WORD **)(a3 + 8) == 58;
  if ( v16 )
    return 0;
  v18 = *(_QWORD *)(a2 + 216);
  if ( !v17 )
    return !v18 || (*(_DWORD *)(v18 + 20) & 0x10) != 0;
  v30 = *(_DWORD *)(*(_QWORD *)(a2 + 176) + 16LL) & 0x200000;
  if ( !v18 )
    return v30 == 0;
  return (!v30 || (*(_DWORD *)(v18 + 20) & 0x40) != 0) && (*(_DWORD *)(v18 + 20) & 0x20) != 0;
}

```

## disassembly

```asm
0x1401b8ec0  push    rbx
0x1401b8ec2  push    rbp
0x1401b8ec3  push    rsi
0x1401b8ec4  push    rdi
0x1401b8ec5  push    r12
0x1401b8ec7  push    r14
0x1401b8ec9  push    r15
0x1401b8ecb  sub     rsp, 20h
0x1401b8ecf  mov     rsi, [rdx+60h]
0x1401b8ed3  mov     r15, rcx
0x1401b8ed6  mov     rbp, r8
0x1401b8ed9  mov     rdi, rdx
0x1401b8edc  mov     r14d, 1
0x1401b8ee2  mov     rcx, [rsi+148h]
0x1401b8ee9  test    rcx, rcx
0x1401b8eec  jnz     loc_1401B90A6
0x1401b8ef2  mov     esi, [rsi+0B0h]
0x1401b8ef8  bt      esi, 0Ah
0x1401b8efc  jb      short loc_1401B8F10
0x1401b8efe  xor     al, al
0x1401b8f00  add     rsp, 20h
0x1401b8f04  pop     r15
0x1401b8f06  pop     r14
0x1401b8f08  pop     r12
0x1401b8f0a  pop     rdi
0x1401b8f0b  pop     rsi
0x1401b8f0c  pop     rbp
0x1401b8f0d  pop     rbx
0x1401b8f0e  retn
0x1401b8f10  mov     rsi, [rdi+60h]
0x1401b8f14  mov     dword ptr [rsp+58h+ExtraCreateParameter], 0
0x1401b8f1c  mov     rcx, [rsi+148h]
0x1401b8f23  test    rcx, rcx
0x1401b8f26  jnz     loc_1401B91A5
0x1401b8f2c  mov     ebx, [rsi+0B4h]
0x1401b8f32  mov     [rsp+58h+ExtraCreateParameter], 0
0x1401b8f3b  mov     [rsp+58h+EcpContext], 0
0x1401b8f44  cmp     [rdi+0C8h], ebx
0x1401b8f4a  jz      short loc_1401B8FC6
0x1401b8f4c  mov     [rdi+0C8h], ebx
0x1401b8f52  lea     rdx, [rsp+58h+ExtraCreateParameter]; ExtraCreateParameter
0x1401b8f57  mov     qword ptr [rdi+0D8h], 0
0x1401b8f62  mov     rcx, [r15+70h]; Irp
0x1401b8f66  call    cs:__imp_IoGetIrpExtraCreateParameter
0x1401b8f6d  nop     dword ptr [rax+rax+00h]
0x1401b8f72  test    eax, eax
0x1401b8f74  js      short loc_1401B8FC6
0x1401b8f76  mov     rcx, [rsp+58h+ExtraCreateParameter]; EcpList
0x1401b8f7b  test    rcx, rcx
0x1401b8f7e  jz      short loc_1401B8FC6
0x1401b8f80  xor     r9d, r9d; EcpContextSize
0x1401b8f83  lea     r8, [rsp+58h+EcpContext]; EcpContext
0x1401b8f88  lea     rdx, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x1401b8f8f  call    cs:__imp_FsRtlFindExtraCreateParameter
0x1401b8f96  nop     dword ptr [rax+rax+00h]
0x1401b8f9b  mov     edx, eax
0x1401b8f9d  test    eax, eax
0x1401b8f9f  js      loc_1401B9043
0x1401b8fa5  mov     rcx, [rsp+58h+EcpContext]
0x1401b8faa  mov     rax, [rcx]
0x1401b8fad  nop     dword ptr [rax]
0x1401b8fb0  cmp     rax, rcx
0x1401b8fb3  jz      short loc_1401B8FC6
0x1401b8fb5  cmp     [rax+10h], ebx
0x1401b8fb8  jz      short loc_1401B8FBF
0x1401b8fba  mov     rax, [rax]
0x1401b8fbd  jmp     short loc_1401B8FB0
0x1401b8fbf  mov     [rdi+0D8h], rax
0x1401b8fc6  mov     rax, [rdi+60h]
0x1401b8fca  test    dword ptr [rax+0B0h], 10000000h
0x1401b8fd4  jz      loc_1401B919E
0x1401b8fda  mov     ecx, [rdi+0C8h]
0x1401b8fe0  call    cs:__imp_FsRtlIsNonEmptyDirectoryReparsePointAllowed
0x1401b8fe7  nop     dword ptr [rax+rax+00h]
0x1401b8fec  test    al, al
0x1401b8fee  jz      loc_1401B919E
0x1401b8ff4  mov     cl, 1
0x1401b8ff6  cmp     word ptr [rbp+0], 0
0x1401b8ffb  jz      loc_1401B909F
0x1401b9001  mov     rax, [rbp+8]
0x1401b9005  cmp     word ptr [rax], 3Ah ; ':'
0x1401b9009  jz      loc_1401B909F
0x1401b900f  xor     al, al
0x1401b9011  test    cl, cl
0x1401b9013  jnz     loc_1401B8EFE
0x1401b9019  mov     rdx, [rdi+0D8h]
0x1401b9020  test    al, al
0x1401b9022  jnz     loc_1401B9269
0x1401b9028  test    rdx, rdx
0x1401b902b  jnz     loc_1401B9259
0x1401b9031  mov     al, 1
0x1401b9033  add     rsp, 20h
0x1401b9037  pop     r15
0x1401b9039  pop     r14
0x1401b903b  pop     r12
0x1401b903d  pop     rdi
0x1401b903e  pop     rsi
0x1401b903f  pop     rbp
0x1401b9040  pop     rbx
0x1401b9041  retn
0x1401b9043  movzx   ecx, cs:NtfsStatusDebugFlags
0x1401b904a  test    cl, cl
0x1401b904c  jz      loc_1401B8FC6
0x1401b9052  cmp     edx, 0FFFFFFEDh
0x1401b9055  jnb     loc_1401B8FC6
0x1401b905b  cmp     edx, 0C0000016h
0x1401b9061  jz      loc_1401B8FC6
0x1401b9067  cmp     edx, 0C0000011h
0x1401b906d  jz      loc_1401B8FC6
0x1401b9073  add     eax, 7FFFFFFBh
0x1401b9078  cmp     eax, 1
0x1401b907b  jbe     loc_1401B8FC6
0x1401b9081  cmp     edx, 0C00000D8h
0x1401b9087  jz      loc_1401B8FC6
0x1401b908d  xor     ecx, ecx
0x1401b908f  mov     r8d, 0A0980h
0x1401b9095  call    NtfsStatusTraceAndDebugInternal
0x1401b909a  jmp     loc_1401B8FC6
0x1401b909f  mov     al, 1
0x1401b90a1  jmp     loc_1401B9011
0x1401b90a6  mov     rax, [rdx+0B8h]
0x1401b90ad  xor     r12d, r12d
0x1401b90b0  mov     rcx, [rcx+88h]; Resource
0x1401b90b7  mov     [rsp+58h+arg_0], r13
0x1401b90bc  mov     r13d, r14d
0x1401b90bf  mov     [rsp+58h+ExtraCreateParameter], rax
0x1401b90c4  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1401b90cb  nop     dword ptr [rax+rax+00h]
0x1401b90d0  test    eax, eax
0x1401b90d2  jnz     short loc_1401B90F5
0x1401b90d4  mov     rcx, [rsi+148h]
0x1401b90db  movzx   edx, r13b; Wait
0x1401b90df  mov     rcx, [rcx+88h]; Resource
0x1401b90e6  call    cs:__imp_ExAcquireResourceSharedLite
0x1401b90ed  nop     dword ptr [rax+rax+00h]
0x1401b90f2  mov     r12d, r14d
0x1401b90f5  mov     rcx, [rsi+148h]
0x1401b90fc  mov     eax, [rcx+4]
0x1401b90ff  test    r13b, al
0x1401b9102  jnz     loc_1401B92C0
0x1401b9108  cmp     r12d, r14d
0x1401b910b  jnz     short loc_1401B9120
0x1401b910d  mov     rcx, [rcx+88h]; Resource
0x1401b9114  call    cs:__imp_ExReleaseResourceLite
0x1401b911b  nop     dword ptr [rax+rax+00h]
0x1401b9120  test    r13d, r13d
0x1401b9123  mov     r13, [rsp+58h+arg_0]
0x1401b9128  jnz     loc_1401B8EF2
0x1401b912e  mov     rcx, [rsi+148h]
0x1401b9135  movzx   edx, r14b; Wait
0x1401b9139  mov     rcx, [rcx+88h]; Resource
0x1401b9140  call    cs:__imp_ExAcquireResourceSharedLite
0x1401b9147  nop     dword ptr [rax+rax+00h]
0x1401b914c  mov     r8, [rsi+148h]
0x1401b9153  mov     rax, [r8+58h]
0x1401b9157  lea     rcx, [r8+58h]
0x1401b915b  cmp     rax, rcx
0x1401b915e  jz      loc_1401B9241
0x1401b9164  movzx   edx, word ptr [rax+4Eh]
0x1401b9168  test    r14b, dl
0x1401b916b  jz      loc_1401B9235
0x1401b9171  test    dl, 8
0x1401b9174  jnz     loc_1401B9235
0x1401b917a  cmp     rax, rcx
0x1401b917d  jz      loc_1401B9241
0x1401b9183  mov     rcx, [r8+88h]; Resource
0x1401b918a  mov     esi, [rax+40h]
0x1401b918d  call    cs:__imp_ExReleaseResourceLite
0x1401b9194  nop     dword ptr [rax+rax+00h]
0x1401b9199  jmp     loc_1401B8EF8
0x1401b919e  xor     cl, cl
0x1401b91a0  jmp     loc_1401B8FF6
0x1401b91a5  mov     rcx, [rcx+88h]; Resource
0x1401b91ac  xor     ebx, ebx
0x1401b91ae  mov     r12, [rdi+0B8h]
0x1401b91b5  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1401b91bc  nop     dword ptr [rax+rax+00h]
0x1401b91c1  test    eax, eax
0x1401b91c3  jnz     short loc_1401B91E6
0x1401b91c5  mov     rcx, [rsi+148h]
0x1401b91cc  movzx   edx, r14b; Wait
0x1401b91d0  mov     rcx, [rcx+88h]; Resource
0x1401b91d7  call    cs:__imp_ExAcquireResourceSharedLite
0x1401b91de  nop     dword ptr [rax+rax+00h]
0x1401b91e3  mov     ebx, r14d
0x1401b91e6  mov     rcx, [rsi+148h]
0x1401b91ed  mov     eax, [rcx+4]
0x1401b91f0  test    r14b, al
0x1401b91f3  jnz     loc_1401B92E5
0x1401b91f9  cmp     ebx, 1
0x1401b91fc  jnz     short loc_1401B9211
0x1401b91fe  mov     rcx, [rcx+88h]; Resource
0x1401b9205  call    cs:__imp_ExReleaseResourceLite
0x1401b920c  nop     dword ptr [rax+rax+00h]
0x1401b9211  test    r14d, r14d
0x1401b9214  jnz     loc_1401B8F2C
0x1401b921a  lea     r8, [rsp+58h+ExtraCreateParameter]
0x1401b921f  mov     rcx, rsi
0x1401b9222  lea     rdx, [rsp+58h+EcpContext]
0x1401b9227  call    TxfGetTransFileInfo
0x1401b922c  mov     ebx, dword ptr [rsp+58h+ExtraCreateParameter]
0x1401b9230  jmp     loc_1401B8F32
0x1401b9235  mov     rax, [rax]
0x1401b9238  cmp     rax, rcx
0x1401b923b  jnz     loc_1401B9164
0x1401b9241  mov     rcx, [r8+88h]; Resource
0x1401b9248  call    cs:__imp_ExReleaseResourceLite
0x1401b924f  nop     dword ptr [rax+rax+00h]
0x1401b9254  jmp     loc_1401B8EF2
0x1401b9259  mov     eax, [rdx+14h]
0x1401b925c  test    al, 10h
0x1401b925e  jz      loc_1401B8EFE
0x1401b9264  jmp     loc_1401B9031
0x1401b9269  mov     rax, [rdi+0B0h]
0x1401b9270  mov     ecx, [rax+10h]
0x1401b9273  and     ecx, 200000h
0x1401b9279  test    rdx, rdx
0x1401b927c  jnz     short loc_1401B9293
0x1401b927e  test    ecx, ecx
0x1401b9280  setz    al
0x1401b9283  add     rsp, 20h
0x1401b9287  pop     r15
0x1401b9289  pop     r14
0x1401b928b  pop     r12
0x1401b928d  pop     rdi
0x1401b928e  pop     rsi
0x1401b928f  pop     rbp
0x1401b9290  pop     rbx
0x1401b9291  retn
0x1401b9293  test    ecx, ecx
0x1401b9295  jz      short loc_1401B92A3
0x1401b9297  mov     ecx, [rdx+14h]
0x1401b929a  test    cl, 40h
0x1401b929d  jz      loc_1401B8EFE
0x1401b92a3  mov     eax, [rdx+14h]
0x1401b92a6  test    al, 20h
0x1401b92a8  jz      loc_1401B8EFE
0x1401b92ae  mov     al, 1
0x1401b92b0  add     rsp, 20h
0x1401b92b4  pop     r15
0x1401b92b6  pop     r14
0x1401b92b8  pop     r12
0x1401b92ba  pop     rdi
0x1401b92bb  pop     rsi
0x1401b92bc  pop     rbp
0x1401b92bd  pop     rbx
0x1401b92be  retn
0x1401b92c0  mov     rdx, [rcx+18h]
0x1401b92c4  test    rdx, rdx
0x1401b92c7  jz      loc_1401B9108
0x1401b92cd  mov     rax, [rsp+58h+ExtraCreateParameter]
0x1401b92d2  xor     r13d, r13d
0x1401b92d5  cmp     rax, [rdx+0E8h]
0x1401b92dc  setz    r13b
0x1401b92e0  jmp     loc_1401B9108
0x1401b92e5  mov     rax, [rcx+18h]
0x1401b92e9  test    rax, rax
0x1401b92ec  jz      loc_1401B91F9
0x1401b92f2  xor     r14d, r14d
0x1401b92f5  cmp     r12, [rax+0E8h]
0x1401b92fc  setz    r14b
0x1401b9300  jmp     loc_1401B91F9
```
