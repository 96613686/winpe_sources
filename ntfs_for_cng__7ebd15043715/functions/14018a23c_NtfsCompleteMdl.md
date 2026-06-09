# NtfsCompleteMdl

- ea: `0x14018a23c`
- end: `0x14018a847`
- name: `NtfsCompleteMdl`
- size: `1547`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140015540`
- `0x140016850`

## callees

- `0x1400082b0`
- `0x140009af0`
- `0x140021590`
- `0x140030a80`
- `0x140039038`
- `0x1400c65ec`
- `0x140188ce4`
- `0x140188ee0`
- `0x14018a23c`
- `0x14018a850`
- `0x1401be398`
- `0x1401c00e0`

## import_xrefs

- `ntoskrnl!CcMdlWriteComplete` at `0x14018a76b`
- `ntoskrnl!CcMdlWriteComplete` at `0x14018a76b`
- `ntoskrnl!KeBugCheckEx` at `0x1402caa11`
- `ntoskrnl!KeBugCheckEx` at `0x1402caa11`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14018a5e4`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14018a5e4`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14018a594`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14018a594`
- `ntoskrnl!KeWaitForSingleObject` at `0x14018a6fc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14018a6fc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14018a360`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14018a536`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14018a360`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14018a536`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a452`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a619`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a653`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a6d8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a452`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a619`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a653`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a6d8`
- `ntoskrnl!CcMdlReadComplete` at `0x14018a7e2`
- `ntoskrnl!CcMdlReadComplete` at `0x14018a7e2`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14018a6bb`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14018a6bb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14018a3c8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14018a3c8`

## pseudocode

```c
__int64 __fastcall NtfsCompleteMdl(__int64 a1, IRP *a2)
{
  IRP *v2; // r15
  int v4; // r13d
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r9
  struct _FILE_OBJECT *FileObject; // rdi
  __int64 v7; // r8
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 FsContext; // rsi
  union _LARGE_INTEGER *p_ByteOffset; // rdx
  PMDL *p_MdlAddress; // r12
  PMDL v13; // rcx
  __int64 QuadPart; // rdx
  __int64 v15; // r13
  BOOLEAN v16; // r15
  __int64 v17; // rdi
  __int64 v18; // rdx
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rcx
  __int64 v20; // rdi
  __int64 v21; // rcx
  __int64 v22; // rdi
  __int64 v23; // r13
  __int64 v24; // r15
  __int64 v25; // r15
  char v26; // al
  __int64 v27; // r12
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rcx
  int v32; // [rsp+50h] [rbp-A8h]
  int v33; // [rsp+54h] [rbp-A4h]
  __int64 v34; // [rsp+60h] [rbp-98h] BYREF
  unsigned int v35; // [rsp+68h] [rbp-90h]
  __int64 v36; // [rsp+70h] [rbp-88h]
  __int64 v37; // [rsp+78h] [rbp-80h]
  __int64 v38; // [rsp+80h] [rbp-78h]
  PMDL *v39; // [rsp+88h] [rbp-70h]
  __int64 v40; // [rsp+90h] [rbp-68h]
  signed __int64 v41; // [rsp+98h] [rbp-60h]
  struct _FILE_OBJECT *v42; // [rsp+A0h] [rbp-58h]
  __int64 v43; // [rsp+A8h] [rbp-50h]
  __int64 v44; // [rsp+B0h] [rbp-48h]
  union _LARGE_INTEGER *v45; // [rsp+B8h] [rbp-40h]
  char v47; // [rsp+110h] [rbp+18h] BYREF
  struct _FILE_OBJECT *v48; // [rsp+118h] [rbp+20h]

  v2 = a2;
  v34 = 0;
  v4 = 0;
  v33 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  v48 = FileObject;
  v42 = FileObject;
  v7 = *(unsigned __int8 *)(a1 + 32);
  v8 = (unsigned int)*(unsigned __int8 *)(a1 + 32) - 3;
  if ( (_DWORD)v8 )
  {
    if ( (_DWORD)v8 != 1 )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x800) != 0 )
      {
        McTemplateU0q_EtwWriteTransfer(v8, (const EVENT_DESCRIPTOR *)cachesup_c1885, v7);
      }
      KeBugCheckEx(0x24u, 0xAC00050762uLL, *(unsigned __int8 *)(a1 + 32), 0, 0);
    }
    v9 = 0;
    v35 = 0;
    v47 = 0;
    v40 = 0;
    FsContext = (__int64)FileObject->FsContext;
    v43 = FsContext;
    p_ByteOffset = &CurrentStackLocation->Parameters.Read.ByteOffset;
    v45 = &CurrentStackLocation->Parameters.Read.ByteOffset;
    p_MdlAddress = &v2->MdlAddress;
    if ( *(_QWORD *)(FsContext + 16) )
    {
      v39 = &v2->MdlAddress;
      v13 = *p_MdlAddress;
      QuadPart = p_ByteOffset->QuadPart;
      v37 = QuadPart;
      v44 = QuadPart;
      while ( v13 )
      {
        v9 += v13->ByteCount;
        v35 = v9;
        v13 = v13->Next;
      }
      v15 = v9;
      v41 = (v9 + QuadPart + 4095) & 0xFFFFFFFFFFFFF000uLL;
      if ( *(_BYTE *)(FsContext + 460) )
      {
        v16 = 0;
        if ( *(_WORD *)FsContext == 1794 )
        {
          v17 = FsContext;
        }
        else
        {
          v17 = 0;
          if ( *(_QWORD *)(FsContext + 16) )
            v17 = *(_QWORD *)(FsContext + 184);
        }
        do
        {
          if ( (*(_DWORD *)(v17 + 16) & 0x200) == 0
            || a1
            && ((*(_DWORD *)(a1 + 16) & 0x40000000) != 0 || (*(_DWORD *)(*(_QWORD *)(a1 + 144) + 16LL) & 0x40000000) != 0)
            || ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(v17 + 96) + 2160LL)) )
          {
            if ( v16 )
              break;
          }
          else
          {
            if ( v16 )
              ExReleaseResourceLite(*(PERESOURCE *)(v17 + 112));
            KeWaitForSingleObject(*(PVOID *)(*(_QWORD *)(v17 + 96) + 1432LL), Executive, 0, 0, 0);
          }
          v16 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v17 + 112), 1u);
        }
        while ( v16 );
        FileObject = v48;
        v2 = a2;
      }
      else
      {
        LOBYTE(v7) = 1;
        NtfsAcquirePagingShared(a1, FsContext, v7, 0);
        if ( *(_BYTE *)(FsContext + 460) )
        {
          NtfsReleasePagingResourcePriv(v28, FsContext);
          LOBYTE(v29) = 1;
          NtfsAcquirePagingResourceExclusive(a1, FsContext, v29);
        }
      }
      v18 = *(_QWORD *)(FsContext + 528);
      if ( v18 )
      {
        if ( *(_DWORD *)(FsContext + 256) == 128 )
        {
          SectionObjectPointer = FileObject->SectionObjectPointer;
          if ( SectionObjectPointer == (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(FsContext + 288) + 16LL)
            || SectionObjectPointer[1].ImageSectionObject )
          {
            ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(v18 + 64) + 136LL), 1u);
            v20 = *(_QWORD *)(FsContext + 528);
            v21 = *(_QWORD *)(v20 + 64);
            if ( *(_QWORD *)(v21 + 24) )
            {
              v36 = 0;
              if ( v20 )
              {
                v22 = *(_QWORD *)(v20 + 56);
                v36 = v22;
                while ( v22 )
                {
                  if ( !*(_WORD *)(v22 + 304) || (*(_DWORD *)(v22 + 8) & 0x2000) == 0 )
                  {
                    if ( (*(_DWORD *)(v22 + 8) & 0x2001) != 0 )
                      v22 = 0;
                    v36 = v22;
                    if ( v22 )
                      _InterlockedIncrement((volatile signed __int32 *)(v22 + 4));
                    break;
                  }
                  v22 = *(_QWORD *)(v22 + 32);
                  v36 = v22;
                }
                v38 = v22;
              }
              else
              {
                v22 = 0;
                v38 = 0;
              }
              v40 = v22;
              ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(FsContext + 528) + 64LL) + 136LL));
              v33 = 1;
              v32 = TxfLogPriorToWrite(a1, (__int64)v48, v22, v37, v15, (__int64)v2, 1, 0);
              if ( v22 )
              {
                v23 = v22;
                v24 = *(_QWORD *)(v22 + 16);
                if ( v24 )
                  v25 = *(_QWORD *)(v24 + 64);
                else
                  v25 = 0;
                v26 = 0;
                do
                {
                  v27 = 0;
                  if ( v25 && !v26 )
                  {
                    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v25 + 136), 1u);
                    v26 = 1;
                  }
                  _InterlockedDecrement((volatile signed __int32 *)(v23 + 4));
                  if ( !*(_DWORD *)(v23 + 4) )
                  {
                    v27 = *(_QWORD *)(v23 + 40);
                    TxfDeleteTxfVscb((char *)v23);
                    v26 = 0;
                  }
                  v23 = v27;
                }
                while ( v27 );
                if ( v26 && v25 )
                  ExReleaseResourceLite(*(PERESOURCE *)(v25 + 136));
              }
              if ( v32 )
                *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v22 + 16) + 64LL) + 4LL) |= 0x2000u;
              p_MdlAddress = v39;
            }
            else
            {
              ExReleaseResourceLite(*(PERESOURCE *)(v21 + 136));
            }
          }
        }
      }
      FsRtlAcquireHeaderMutex(FsContext + 120, FsContext + 160);
      if ( v41 > *(_QWORD *)(FsContext + 40) )
        NtfsGetIoAtEof(a1, FsContext, v37, v41 - v37, 1, &v47);
      FsRtlReleaseHeaderMutex(FsContext + 120, FsContext + 160);
      v2 = a2;
      FileObject = v48;
      v4 = v33;
      p_ByteOffset = v45;
    }
    CcMdlWriteComplete(FileObject, p_ByteOffset, *p_MdlAddress);
    if ( *(_QWORD *)(FsContext + 16) )
      NtfsReleasePagingResourcePriv(v30, FsContext);
    if ( v4 && v34 )
      TxfDereferenceTransaction(&v34, 1);
  }
  else
  {
    p_MdlAddress = &a2->MdlAddress;
    CcMdlReadComplete(FileObject, a2->MdlAddress);
  }
  *(_DWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 4) &= ~0x100u;
  *p_MdlAddress = 0;
  NtfsExtendedCompleteRequestInternal(a1, v2, 0, v2 != 0, 1);
  return 0;
}

```

## disassembly

```asm
0x14018a23c  mov     r11, rsp
0x14018a23f  mov     [r11+10h], rdx
0x14018a243  mov     [r11+8], rcx
0x14018a247  push    rbx
0x14018a248  push    rsi
0x14018a249  push    rdi
0x14018a24a  push    r12
0x14018a24c  push    r13
0x14018a24e  push    r14
0x14018a250  push    r15
0x14018a252  sub     rsp, 0C0h
0x14018a259  mov     r15, rdx
0x14018a25c  mov     r14, rcx
0x14018a25f  xor     ebx, ebx
0x14018a261  mov     [rsp+0F8h+var_A0], rbx
0x14018a266  mov     [rsp+0F8h+var_98], rbx
0x14018a26b  mov     r13d, ebx
0x14018a26e  mov     [rsp+0F8h+var_A4], ebx
0x14018a272  mov     r9, [rdx+0B8h]
0x14018a279  mov     rdi, [r9+30h]
0x14018a27d  mov     [rsp+0F8h+arg_18], rdi
0x14018a285  mov     [rsp+0F8h+var_58], rdi
0x14018a28d  movzx   r8d, byte ptr [rcx+20h]
0x14018a292  mov     ecx, r8d
0x14018a295  sub     ecx, 3
0x14018a298  jz      loc_14018A7D7
0x14018a29e  cmp     ecx, 1
0x14018a2a1  jnz     loc_14018A7F0
0x14018a2a7  mov     eax, ebx
0x14018a2a9  mov     [rsp+0F8h+var_90], ebx
0x14018a2ad  mov     [r11+18h], bl
0x14018a2b1  mov     [r11-68h], rbx
0x14018a2b5  mov     [rsp+0F8h+var_A8], 0C0000001h
0x14018a2bd  mov     rsi, [rdi+18h]
0x14018a2c1  mov     [rsp+0F8h+var_50], rsi
0x14018a2c9  mov     [rsp+0F8h+var_A0], rsi
0x14018a2ce  lea     rdx, [r9+18h]; FileOffset
0x14018a2d2  mov     [rsp+0F8h+var_40], rdx
0x14018a2da  lea     r12, [r15+8]
0x14018a2de  cmp     [rsi+10h], rbx
0x14018a2e2  jz      loc_14018A764
0x14018a2e8  mov     [rsp+0F8h+var_70], r12
0x14018a2f0  mov     rcx, [r12]
0x14018a2f4  mov     rdx, [rdx]
0x14018a2f7  mov     [rsp+0F8h+var_80], rdx
0x14018a2fc  mov     [rsp+0F8h+var_48], rdx
0x14018a304  test    rcx, rcx
0x14018a307  jnz     loc_14018A70D
0x14018a30d  mov     r13d, eax
0x14018a310  lea     rax, [rdx+0FFFh]
0x14018a317  add     rax, r13
0x14018a31a  and     rax, 0FFFFFFFFFFFFF000h
0x14018a320  mov     [rsp+0F8h+var_60], rax
0x14018a328  cmp     [rsi+1CCh], cl
0x14018a32e  jz      loc_14018A71C
0x14018a334  mov     r15b, bl
0x14018a337  mov     eax, 702h
0x14018a33c  cmp     ax, [rsi]
0x14018a33f  jnz     loc_14018A62A
0x14018a345  mov     rdi, rsi
0x14018a348  test    dword ptr [rdi+10h], 200h
0x14018a34f  jnz     loc_14018A687
0x14018a355  test    r15b, r15b
0x14018a358  jnz     short loc_14018A373
0x14018a35a  mov     dl, 1; Wait
0x14018a35c  mov     rcx, [rdi+70h]; Resource
0x14018a360  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14018a367  nop     dword ptr [rax+rax+00h]
0x14018a36c  mov     r15b, al
0x14018a36f  test    al, al
0x14018a371  jnz     short loc_14018A348
0x14018a373  mov     rdi, [rsp+0F8h+arg_18]
0x14018a37b  mov     r15, [rsp+0F8h+arg_8]
0x14018a383  mov     rdx, [rsi+210h]
0x14018a38a  test    rdx, rdx
0x14018a38d  jz      loc_14018A586
0x14018a393  cmp     dword ptr [rsi+100h], 80h
0x14018a39d  jnz     loc_14018A586
0x14018a3a3  mov     rcx, [rdi+28h]
0x14018a3a7  mov     rax, [rsi+120h]
0x14018a3ae  add     rax, 10h
0x14018a3b2  cmp     rcx, rax
0x14018a3b5  jnz     loc_14018A755
0x14018a3bb  mov     rcx, [rdx+40h]
0x14018a3bf  mov     dl, 1; Wait
0x14018a3c1  mov     rcx, [rcx+88h]; Resource
0x14018a3c8  call    cs:__imp_ExAcquireResourceSharedLite
0x14018a3cf  nop     dword ptr [rax+rax+00h]
0x14018a3d4  mov     rdi, [rsi+210h]
0x14018a3db  mov     rcx, [rdi+40h]
0x14018a3df  cmp     [rcx+18h], rbx
0x14018a3e3  jz      loc_14018A612
0x14018a3e9  mov     [rsp+0F8h+var_88], rbx
0x14018a3ee  test    rdi, rdi
0x14018a3f1  jz      loc_14018A4EE
0x14018a3f7  mov     rdi, [rdi+38h]
0x14018a3fb  mov     [rsp+0F8h+var_88], rdi
0x14018a400  test    rdi, rdi
0x14018a403  jz      short loc_14018A430
0x14018a405  cmp     [rdi+130h], bx
0x14018a40c  jnz     loc_14018A4D3
0x14018a412  test    rdi, rdi
0x14018a415  jz      short loc_14018A430
0x14018a417  test    dword ptr [rdi+8], 2001h
0x14018a41e  cmovnz  rdi, rbx
0x14018a422  mov     [rsp+0F8h+var_88], rdi
0x14018a427  test    rdi, rdi
0x14018a42a  jz      short loc_14018A430
0x14018a42c  lock inc dword ptr [rdi+4]
0x14018a430  mov     [rsp+0F8h+var_78], rdi
0x14018a438  mov     [rsp+0F8h+var_68], rdi
0x14018a440  mov     rax, [rsi+210h]
0x14018a447  mov     rcx, [rax+40h]
0x14018a44b  mov     rcx, [rcx+88h]; Resource
0x14018a452  call    cs:__imp_ExReleaseResourceLite
0x14018a459  nop     dword ptr [rax+rax+00h]
0x14018a45e  mov     [rsp+0F8h+var_A4], 1
0x14018a466  mov     [rsp+0F8h+var_C0], ebx
0x14018a46a  mov     [rsp+0F8h+var_C8], 1
0x14018a472  mov     [rsp+0F8h+var_D0], r15
0x14018a477  mov     [rsp+0F8h+Timeout], r13
0x14018a47c  mov     r9, [rsp+0F8h+var_80]
0x14018a481  mov     r8, rdi
0x14018a484  mov     rdx, [rsp+0F8h+arg_18]
0x14018a48c  mov     rcx, r14
0x14018a48f  call    TxfLogPriorToWrite
0x14018a494  mov     [rsp+0F8h+var_A8], eax
0x14018a498  jmp     short loc_14018A4FE
0x14018a49a  xor     ebx, ebx
0x14018a49c  mov     r14, [rsp+0F8h+arg_0]
0x14018a4a4  mov     rdx, [rsp+0F8h+var_58]
0x14018a4ac  mov     [rsp+0F8h+arg_18], rdx
0x14018a4b4  mov     rsi, [rsp+0F8h+var_50]
0x14018a4bc  mov     rax, [rsp+0F8h+var_48]
0x14018a4c4  mov     [rsp+0F8h+var_80], rax
0x14018a4c9  mov     rdi, [rsp+0F8h+var_78]
0x14018a4d1  jmp     short loc_14018A4FE
0x14018a4d3  test    dword ptr [rdi+8], 2000h
0x14018a4da  jz      loc_14018A412
0x14018a4e0  mov     rdi, [rdi+20h]
0x14018a4e4  mov     [rsp+0F8h+var_88], rdi
0x14018a4e9  jmp     loc_14018A400
0x14018a4ee  mov     rdi, rbx
0x14018a4f1  mov     [rsp+0F8h+var_78], rbx
0x14018a4f9  jmp     loc_14018A438
0x14018a4fe  test    rdi, rdi
0x14018a501  jz      short loc_14018A567
0x14018a503  mov     [rsp+0F8h+var_B0], bl
0x14018a507  mov     r13, rdi
0x14018a50a  mov     r15, [rdi+10h]
0x14018a50e  test    r15, r15
0x14018a511  jz      loc_14018A67F
0x14018a517  mov     r15, [r15+40h]
0x14018a51b  mov     al, bl
0x14018a51d  mov     [rsp+0F8h+var_B8], bl
0x14018a521  mov     r12, rbx
0x14018a524  test    r15, r15
0x14018a527  jz      short loc_14018A548
0x14018a529  test    al, al
0x14018a52b  jnz     short loc_14018A548
0x14018a52d  mov     dl, 1; Wait
0x14018a52f  mov     rcx, [r15+88h]; Resource
0x14018a536  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14018a53d  nop     dword ptr [rax+rax+00h]
0x14018a542  mov     al, 1
0x14018a544  mov     [rsp+0F8h+var_B8], al
0x14018a548  lock dec dword ptr [r13+4]
0x14018a54d  cmp     [r13+4], ebx
0x14018a551  jz      loc_14018A664
0x14018a557  mov     r13, r12
0x14018a55a  test    r12, r12
0x14018a55d  jnz     short loc_14018A521
0x14018a55f  test    al, al
0x14018a561  jnz     loc_14018A643
0x14018a567  cmp     [rsp+0F8h+var_A8], ebx
0x14018a56b  jz      short loc_14018A57A
0x14018a56d  mov     rax, [rdi+10h]
0x14018a571  mov     rcx, [rax+40h]
0x14018a575  bts     dword ptr [rcx+4], 0Dh
0x14018a57a  mov     r12, [rsp+0F8h+var_70]
0x14018a582  mov     [rsp+0F8h+var_A8], ebx
0x14018a586  lea     rdi, [rsi+0A0h]
0x14018a58d  mov     rdx, rdi
0x14018a590  lea     rcx, [rsi+78h]
0x14018a594  call    cs:__imp_FsRtlAcquireHeaderMutex
0x14018a59b  nop     dword ptr [rax+rax+00h]
0x14018a5a0  mov     rax, [rsp+0F8h+var_60]
0x14018a5a8  mov     rcx, [rsp+0F8h+var_A0]
0x14018a5ad  cmp     rax, [rcx+28h]
0x14018a5b1  jle     short loc_14018A5DD
0x14018a5b3  sub     rax, [rsp+0F8h+var_80]
0x14018a5b8  lea     rdx, [rsp+0F8h+arg_10]
0x14018a5c0  mov     [rsp+0F8h+var_D0], rdx
0x14018a5c5  mov     byte ptr [rsp+0F8h+Timeout], 1
0x14018a5ca  mov     r9, rax
0x14018a5cd  mov     r8, [rsp+0F8h+var_80]
0x14018a5d2  mov     rdx, rsi
0x14018a5d5  mov     rcx, r14
0x14018a5d8  call    NtfsGetIoAtEof
0x14018a5dd  mov     rdx, rdi
0x14018a5e0  lea     rcx, [rsi+78h]
0x14018a5e4  call    cs:__imp_FsRtlReleaseHeaderMutex
0x14018a5eb  nop     dword ptr [rax+rax+00h]
0x14018a5f0  mov     r15, [rsp+0F8h+arg_8]
0x14018a5f8  mov     rdi, [rsp+0F8h+arg_18]
0x14018a600  mov     r13d, [rsp+0F8h+var_A4]
0x14018a605  mov     rdx, [rsp+0F8h+var_40]
0x14018a60d  jmp     loc_14018A764
0x14018a612  mov     rcx, [rcx+88h]; Resource
0x14018a619  call    cs:__imp_ExReleaseResourceLite
0x14018a620  nop     dword ptr [rax+rax+00h]
0x14018a625  jmp     loc_14018A582
0x14018a62a  mov     rdi, rbx
0x14018a62d  cmp     [rsi+10h], rbx
0x14018a631  jz      loc_14018A348
0x14018a637  mov     rdi, [rsi+0B8h]
0x14018a63e  jmp     loc_14018A348
0x14018a643  test    r15, r15
0x14018a646  jz      loc_14018A567
0x14018a64c  mov     rcx, [r15+88h]; Resource
0x14018a653  call    cs:__imp_ExReleaseResourceLite
0x14018a65a  nop     dword ptr [rax+rax+00h]
0x14018a65f  jmp     loc_14018A567
0x14018a664  mov     r12, [r13+28h]
0x14018a668  mov     rcx, r13; Entry
0x14018a66b  call    TxfDeleteTxfVscb
0x14018a670  mov     al, bl
0x14018a672  mov     [rsp+0F8h+var_B8], bl
0x14018a676  mov     [rsp+0F8h+var_B0], bl
0x14018a67a  jmp     loc_14018A557
0x14018a67f  mov     r15, rbx
0x14018a682  jmp     loc_14018A51B
0x14018a687  test    r14, r14
0x14018a68a  jz      short loc_14018A6B0
0x14018a68c  mov     eax, [r14+10h]
0x14018a690  bt      rax, 1Eh
0x14018a695  jb      loc_14018A355
0x14018a69b  mov     rax, [r14+90h]
0x14018a6a2  mov     ecx, [rax+10h]
0x14018a6a5  bt      rcx, 1Eh
0x14018a6aa  jb      loc_14018A355
0x14018a6b0  mov     rcx, [rdi+60h]
0x14018a6b4  add     rcx, 870h; Resource
0x14018a6bb  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14018a6c2  nop     dword ptr [rax+rax+00h]
0x14018a6c7  test    al, al
0x14018a6c9  jnz     loc_14018A355
0x14018a6cf  test    r15b, r15b
0x14018a6d2  jz      short loc_14018A6E4
0x14018a6d4  mov     rcx, [rdi+70h]; Resource
0x14018a6d8  call    cs:__imp_ExReleaseResourceLite
0x14018a6df  nop     dword ptr [rax+rax+00h]
0x14018a6e4  mov     rcx, [rdi+60h]
0x14018a6e8  mov     [rsp+0F8h+Timeout], rbx; Timeout
0x14018a6ed  xor     r9d, r9d; Alertable
0x14018a6f0  xor     r8d, r8d; WaitMode
0x14018a6f3  xor     edx, edx; WaitReason
0x14018a6f5  mov     rcx, [rcx+598h]; Object
0x14018a6fc  call    cs:__imp_KeWaitForSingleObject
0x14018a703  nop     dword ptr [rax+rax+00h]
0x14018a708  jmp     loc_14018A35A
0x14018a70d  add     eax, [rcx+28h]
0x14018a710  mov     [rsp+0F8h+var_90], eax
0x14018a714  mov     rcx, [rcx]
0x14018a717  jmp     loc_14018A304
0x14018a71c  xor     r9d, r9d
0x14018a71f  mov     r8b, 1
0x14018a722  mov     rdx, rsi
0x14018a725  mov     rcx, r14
0x14018a728  call    NtfsAcquirePagingShared
0x14018a72d  cmp     byte ptr [rsi+1CCh], 0
0x14018a734  jz      loc_14018A383
0x14018a73a  mov     rdx, rsi
0x14018a73d  call    NtfsReleasePagingResourcePriv
0x14018a742  mov     r8b, 1
0x14018a745  mov     rdx, rsi
0x14018a748  mov     rcx, r14
0x14018a74b  call    NtfsAcquirePagingResourceExclusive
0x14018a750  jmp     loc_14018A383
0x14018a755  cmp     [rcx+28h], rbx
0x14018a759  jz      loc_14018A586
0x14018a75f  jmp     loc_14018A3BB
0x14018a764  mov     r8, [r12]; MdlChain
0x14018a768  mov     rcx, rdi; FileObject
0x14018a76b  call    cs:__imp_CcMdlWriteComplete
0x14018a772  nop     dword ptr [rax+rax+00h]
0x14018a777  nop
0x14018a778  mov     rax, [rsp+0F8h+var_A0]
0x14018a77d  cmp     [rax+10h], rbx
0x14018a781  jnz     loc_14018A81E
0x14018a787  test    r13d, r13d
0x14018a78a  jnz     loc_14018A82B
0x14018a790  mov     [r14+18h], ebx
0x14018a794  btr     dword ptr [r14+4], 8
0x14018a79a  mov     [r12], rbx
0x14018a79e  mov     al, cs:NtfsStatusDebugFlags
0x14018a7a4  test    r15, r15
0x14018a7a7  setnz   r9b
0x14018a7ab  mov     dword ptr [rsp+0F8h+Timeout], 1
0x14018a7b3  xor     r8d, r8d
  ... truncated ...
```
