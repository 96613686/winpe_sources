# NtfsIsReparseRequired

- ea: `0x1401b8e70`
- end: `0x1401b92b5`
- name: `NtfsIsReparseRequired`
- size: `1093`
- prototype: `bool __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x14019f300`

## callees

- `0x140007ea0`
- `0x1401b8e70`
- `0x1401ba624`

## import_xrefs

- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1401b8f16`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1401b8f16`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401b8f3f`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401b8f3f`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1401b8f90`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1401b8f90`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b9074`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b9165`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b9074`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401b9165`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b90c4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b913d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b91b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b91f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b90c4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b913d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b91b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401b91f8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b9096`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b90f0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b9187`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b9096`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b90f0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401b9187`

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
            NtfsStatusTraceAndDebugInternal(0, v14, 0xA0980u);
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
0x1401b8e70  push    rbx
0x1401b8e72  push    rbp
0x1401b8e73  push    rsi
0x1401b8e74  push    rdi
0x1401b8e75  push    r12
0x1401b8e77  push    r14
0x1401b8e79  push    r15
0x1401b8e7b  sub     rsp, 20h
0x1401b8e7f  mov     rsi, [rdx+60h]
0x1401b8e83  mov     r15, rcx
0x1401b8e86  mov     rbp, r8
0x1401b8e89  mov     rdi, rdx
0x1401b8e8c  mov     r14d, 1
0x1401b8e92  mov     rcx, [rsi+148h]
0x1401b8e99  test    rcx, rcx
0x1401b8e9c  jnz     loc_1401B9056
0x1401b8ea2  mov     esi, [rsi+0B0h]
0x1401b8ea8  bt      esi, 0Ah
0x1401b8eac  jb      short loc_1401B8EC0
0x1401b8eae  xor     al, al
0x1401b8eb0  add     rsp, 20h
0x1401b8eb4  pop     r15
0x1401b8eb6  pop     r14
0x1401b8eb8  pop     r12
0x1401b8eba  pop     rdi
0x1401b8ebb  pop     rsi
0x1401b8ebc  pop     rbp
0x1401b8ebd  pop     rbx
0x1401b8ebe  retn
0x1401b8ec0  mov     rsi, [rdi+60h]
0x1401b8ec4  mov     dword ptr [rsp+58h+ExtraCreateParameter], 0
0x1401b8ecc  mov     rcx, [rsi+148h]
0x1401b8ed3  test    rcx, rcx
0x1401b8ed6  jnz     loc_1401B9155
0x1401b8edc  mov     ebx, [rsi+0B4h]
0x1401b8ee2  mov     [rsp+58h+ExtraCreateParameter], 0
0x1401b8eeb  mov     [rsp+58h+EcpContext], 0
0x1401b8ef4  cmp     [rdi+0C8h], ebx
0x1401b8efa  jz      short loc_1401B8F76
0x1401b8efc  mov     [rdi+0C8h], ebx
0x1401b8f02  lea     rdx, [rsp+58h+ExtraCreateParameter]; ExtraCreateParameter
0x1401b8f07  mov     qword ptr [rdi+0D8h], 0
0x1401b8f12  mov     rcx, [r15+70h]; Irp
0x1401b8f16  call    cs:__imp_IoGetIrpExtraCreateParameter
0x1401b8f1d  nop     dword ptr [rax+rax+00h]
0x1401b8f22  test    eax, eax
0x1401b8f24  js      short loc_1401B8F76
0x1401b8f26  mov     rcx, [rsp+58h+ExtraCreateParameter]; EcpList
0x1401b8f2b  test    rcx, rcx
0x1401b8f2e  jz      short loc_1401B8F76
0x1401b8f30  xor     r9d, r9d; EcpContextSize
0x1401b8f33  lea     r8, [rsp+58h+EcpContext]; EcpContext
0x1401b8f38  lea     rdx, ECP_TYPE_OPEN_REPARSE_GUID; EcpType
0x1401b8f3f  call    cs:__imp_FsRtlFindExtraCreateParameter
0x1401b8f46  nop     dword ptr [rax+rax+00h]
0x1401b8f4b  mov     edx, eax
0x1401b8f4d  test    eax, eax
0x1401b8f4f  js      loc_1401B8FF3
0x1401b8f55  mov     rcx, [rsp+58h+EcpContext]
0x1401b8f5a  mov     rax, [rcx]
0x1401b8f5d  nop     dword ptr [rax]
0x1401b8f60  cmp     rax, rcx
0x1401b8f63  jz      short loc_1401B8F76
0x1401b8f65  cmp     [rax+10h], ebx
0x1401b8f68  jz      short loc_1401B8F6F
0x1401b8f6a  mov     rax, [rax]
0x1401b8f6d  jmp     short loc_1401B8F60
0x1401b8f6f  mov     [rdi+0D8h], rax
0x1401b8f76  mov     rax, [rdi+60h]
0x1401b8f7a  test    dword ptr [rax+0B0h], 10000000h
0x1401b8f84  jz      loc_1401B914E
0x1401b8f8a  mov     ecx, [rdi+0C8h]
0x1401b8f90  call    cs:__imp_FsRtlIsNonEmptyDirectoryReparsePointAllowed
0x1401b8f97  nop     dword ptr [rax+rax+00h]
0x1401b8f9c  test    al, al
0x1401b8f9e  jz      loc_1401B914E
0x1401b8fa4  mov     cl, 1
0x1401b8fa6  cmp     word ptr [rbp+0], 0
0x1401b8fab  jz      loc_1401B904F
0x1401b8fb1  mov     rax, [rbp+8]
0x1401b8fb5  cmp     word ptr [rax], 3Ah ; ':'
0x1401b8fb9  jz      loc_1401B904F
0x1401b8fbf  xor     al, al
0x1401b8fc1  test    cl, cl
0x1401b8fc3  jnz     loc_1401B8EAE
0x1401b8fc9  mov     rdx, [rdi+0D8h]
0x1401b8fd0  test    al, al
0x1401b8fd2  jnz     loc_1401B9219
0x1401b8fd8  test    rdx, rdx
0x1401b8fdb  jnz     loc_1401B9209
0x1401b8fe1  mov     al, 1
0x1401b8fe3  add     rsp, 20h
0x1401b8fe7  pop     r15
0x1401b8fe9  pop     r14
0x1401b8feb  pop     r12
0x1401b8fed  pop     rdi
0x1401b8fee  pop     rsi
0x1401b8fef  pop     rbp
0x1401b8ff0  pop     rbx
0x1401b8ff1  retn
0x1401b8ff3  movzx   ecx, cs:NtfsStatusDebugFlags
0x1401b8ffa  test    cl, cl
0x1401b8ffc  jz      loc_1401B8F76
0x1401b9002  cmp     edx, 0FFFFFFEDh
0x1401b9005  jnb     loc_1401B8F76
0x1401b900b  cmp     edx, 0C0000016h
0x1401b9011  jz      loc_1401B8F76
0x1401b9017  cmp     edx, 0C0000011h
0x1401b901d  jz      loc_1401B8F76
0x1401b9023  add     eax, 7FFFFFFBh
0x1401b9028  cmp     eax, 1
0x1401b902b  jbe     loc_1401B8F76
0x1401b9031  cmp     edx, 0C00000D8h
0x1401b9037  jz      loc_1401B8F76
0x1401b903d  xor     ecx, ecx
0x1401b903f  mov     r8d, 0A0980h
0x1401b9045  call    NtfsStatusTraceAndDebugInternal
0x1401b904a  jmp     loc_1401B8F76
0x1401b904f  mov     al, 1
0x1401b9051  jmp     loc_1401B8FC1
0x1401b9056  mov     rax, [rdx+0B8h]
0x1401b905d  xor     r12d, r12d
0x1401b9060  mov     rcx, [rcx+88h]; Resource
0x1401b9067  mov     [rsp+58h+arg_0], r13
0x1401b906c  mov     r13d, r14d
0x1401b906f  mov     [rsp+58h+ExtraCreateParameter], rax
0x1401b9074  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1401b907b  nop     dword ptr [rax+rax+00h]
0x1401b9080  test    eax, eax
0x1401b9082  jnz     short loc_1401B90A5
0x1401b9084  mov     rcx, [rsi+148h]
0x1401b908b  movzx   edx, r13b; Wait
0x1401b908f  mov     rcx, [rcx+88h]; Resource
0x1401b9096  call    cs:__imp_ExAcquireResourceSharedLite
0x1401b909d  nop     dword ptr [rax+rax+00h]
0x1401b90a2  mov     r12d, r14d
0x1401b90a5  mov     rcx, [rsi+148h]
0x1401b90ac  mov     eax, [rcx+4]
0x1401b90af  test    r13b, al
0x1401b90b2  jnz     loc_1401B9270
0x1401b90b8  cmp     r12d, r14d
0x1401b90bb  jnz     short loc_1401B90D0
0x1401b90bd  mov     rcx, [rcx+88h]; Resource
0x1401b90c4  call    cs:__imp_ExReleaseResourceLite
0x1401b90cb  nop     dword ptr [rax+rax+00h]
0x1401b90d0  test    r13d, r13d
0x1401b90d3  mov     r13, [rsp+58h+arg_0]
0x1401b90d8  jnz     loc_1401B8EA2
0x1401b90de  mov     rcx, [rsi+148h]
0x1401b90e5  movzx   edx, r14b; Wait
0x1401b90e9  mov     rcx, [rcx+88h]; Resource
0x1401b90f0  call    cs:__imp_ExAcquireResourceSharedLite
0x1401b90f7  nop     dword ptr [rax+rax+00h]
0x1401b90fc  mov     r8, [rsi+148h]
0x1401b9103  mov     rax, [r8+58h]
0x1401b9107  lea     rcx, [r8+58h]
0x1401b910b  cmp     rax, rcx
0x1401b910e  jz      loc_1401B91F1
0x1401b9114  movzx   edx, word ptr [rax+4Eh]
0x1401b9118  test    r14b, dl
0x1401b911b  jz      loc_1401B91E5
0x1401b9121  test    dl, 8
0x1401b9124  jnz     loc_1401B91E5
0x1401b912a  cmp     rax, rcx
0x1401b912d  jz      loc_1401B91F1
0x1401b9133  mov     rcx, [r8+88h]; Resource
0x1401b913a  mov     esi, [rax+40h]
0x1401b913d  call    cs:__imp_ExReleaseResourceLite
0x1401b9144  nop     dword ptr [rax+rax+00h]
0x1401b9149  jmp     loc_1401B8EA8
0x1401b914e  xor     cl, cl
0x1401b9150  jmp     loc_1401B8FA6
0x1401b9155  mov     rcx, [rcx+88h]; Resource
0x1401b915c  xor     ebx, ebx
0x1401b915e  mov     r12, [rdi+0B8h]
0x1401b9165  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1401b916c  nop     dword ptr [rax+rax+00h]
0x1401b9171  test    eax, eax
0x1401b9173  jnz     short loc_1401B9196
0x1401b9175  mov     rcx, [rsi+148h]
0x1401b917c  movzx   edx, r14b; Wait
0x1401b9180  mov     rcx, [rcx+88h]; Resource
0x1401b9187  call    cs:__imp_ExAcquireResourceSharedLite
0x1401b918e  nop     dword ptr [rax+rax+00h]
0x1401b9193  mov     ebx, r14d
0x1401b9196  mov     rcx, [rsi+148h]
0x1401b919d  mov     eax, [rcx+4]
0x1401b91a0  test    r14b, al
0x1401b91a3  jnz     loc_1401B9295
0x1401b91a9  cmp     ebx, 1
0x1401b91ac  jnz     short loc_1401B91C1
0x1401b91ae  mov     rcx, [rcx+88h]; Resource
0x1401b91b5  call    cs:__imp_ExReleaseResourceLite
0x1401b91bc  nop     dword ptr [rax+rax+00h]
0x1401b91c1  test    r14d, r14d
0x1401b91c4  jnz     loc_1401B8EDC
0x1401b91ca  lea     r8, [rsp+58h+ExtraCreateParameter]
0x1401b91cf  mov     rcx, rsi
0x1401b91d2  lea     rdx, [rsp+58h+EcpContext]
0x1401b91d7  call    TxfGetTransFileInfo
0x1401b91dc  mov     ebx, dword ptr [rsp+58h+ExtraCreateParameter]
0x1401b91e0  jmp     loc_1401B8EE2
0x1401b91e5  mov     rax, [rax]
0x1401b91e8  cmp     rax, rcx
0x1401b91eb  jnz     loc_1401B9114
0x1401b91f1  mov     rcx, [r8+88h]; Resource
0x1401b91f8  call    cs:__imp_ExReleaseResourceLite
0x1401b91ff  nop     dword ptr [rax+rax+00h]
0x1401b9204  jmp     loc_1401B8EA2
0x1401b9209  mov     eax, [rdx+14h]
0x1401b920c  test    al, 10h
0x1401b920e  jz      loc_1401B8EAE
0x1401b9214  jmp     loc_1401B8FE1
0x1401b9219  mov     rax, [rdi+0B0h]
0x1401b9220  mov     ecx, [rax+10h]
0x1401b9223  and     ecx, 200000h
0x1401b9229  test    rdx, rdx
0x1401b922c  jnz     short loc_1401B9243
0x1401b922e  test    ecx, ecx
0x1401b9230  setz    al
0x1401b9233  add     rsp, 20h
0x1401b9237  pop     r15
0x1401b9239  pop     r14
0x1401b923b  pop     r12
0x1401b923d  pop     rdi
0x1401b923e  pop     rsi
0x1401b923f  pop     rbp
0x1401b9240  pop     rbx
0x1401b9241  retn
0x1401b9243  test    ecx, ecx
0x1401b9245  jz      short loc_1401B9253
0x1401b9247  mov     ecx, [rdx+14h]
0x1401b924a  test    cl, 40h
0x1401b924d  jz      loc_1401B8EAE
0x1401b9253  mov     eax, [rdx+14h]
0x1401b9256  test    al, 20h
0x1401b9258  jz      loc_1401B8EAE
0x1401b925e  mov     al, 1
0x1401b9260  add     rsp, 20h
0x1401b9264  pop     r15
0x1401b9266  pop     r14
0x1401b9268  pop     r12
0x1401b926a  pop     rdi
0x1401b926b  pop     rsi
0x1401b926c  pop     rbp
0x1401b926d  pop     rbx
0x1401b926e  retn
0x1401b9270  mov     rdx, [rcx+18h]
0x1401b9274  test    rdx, rdx
0x1401b9277  jz      loc_1401B90B8
0x1401b927d  mov     rax, [rsp+58h+ExtraCreateParameter]
0x1401b9282  xor     r13d, r13d
0x1401b9285  cmp     rax, [rdx+0E8h]
0x1401b928c  setz    r13b
0x1401b9290  jmp     loc_1401B90B8
0x1401b9295  mov     rax, [rcx+18h]
0x1401b9299  test    rax, rax
0x1401b929c  jz      loc_1401B91A9
0x1401b92a2  xor     r14d, r14d
0x1401b92a5  cmp     r12, [rax+0E8h]
0x1401b92ac  setz    r14b
0x1401b92b0  jmp     loc_1401B91A9
```
