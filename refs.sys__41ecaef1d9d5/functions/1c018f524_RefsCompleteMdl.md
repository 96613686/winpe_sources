# RefsCompleteMdl

- ea: `0x1c018f524`
- end: `0x1c018f6f3`
- name: `RefsCompleteMdl`
- size: `463`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1c00098f0`
- `0x1c000d400`

## callees

- `0x1c000f770`
- `0x1c0013f90`
- `0x1c005c650`
- `0x1c0068168`
- `0x1c01634c8`
- `0x1c018f524`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c018f640`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c018f6df`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c018f640`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c018f6df`
- `ntoskrnl!CcMdlWriteComplete` at `0x1c018f60a`
- `ntoskrnl!CcMdlWriteComplete` at `0x1c018f60a`
- `ntoskrnl!CcMdlReadComplete` at `0x1c018f655`
- `ntoskrnl!CcMdlReadComplete` at `0x1c018f655`
- `ntoskrnl!KeBugCheckEx` at `0x1c018f5bd`
- `ntoskrnl!KeBugCheckEx` at `0x1c018f5bd`

## string_xrefs

- `0x1c018f67f`: `CacheSup.c`

## pseudocode

```c
__int64 __fastcall RefsCompleteMdl(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // r15
  struct _FILE_OBJECT *v6; // r14
  __int64 v7; // r9
  int v8; // ecx
  unsigned __int8 v9; // cl
  __int64 v10; // rcx
  PERESOURCE *FsContext; // rbx
  __int64 *i; // rax

  v5 = *(_QWORD *)(a2 + 184);
  v6 = *(struct _FILE_OBJECT **)(v5 + 48);
  v7 = *(unsigned __int8 *)(a1 + 40);
  v8 = *(unsigned __int8 *)(a1 + 40) - 3;
  if ( v8 )
  {
    if ( v8 != 1 )
    {
      v9 = v7;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_34beff5d47f330610d64a67e096d2140_Traceguids, v7);
        v9 = *(_BYTE *)(a1 + 40);
      }
      KeBugCheckEx(0x149u, 0x50440u, v9, 0, 0);
    }
    v10 = 0;
    FsContext = (PERESOURCE *)v6->FsContext;
    if ( FsContext[2] )
    {
      for ( i = *(__int64 **)(a2 + 8); i; i = (__int64 *)*i )
        v10 = (unsigned int)(*((_DWORD *)i + 10) + v10);
      LOBYTE(a3) = 1;
      RefsAcquirePagingResourceShared(v10, FsContext, a3);
    }
    CcMdlWriteComplete(v6, (PLARGE_INTEGER)(v5 + 24), *(PMDL *)(a2 + 8));
    *(_QWORD *)(a2 + 8) = 0;
    RefsFlushForWriteThrough(a1, FsContext);
    if ( FsContext[2] )
    {
      if ( *(_WORD *)FsContext != 2050 )
        FsContext = (PERESOURCE *)FsContext[15];
      ExReleaseResourceLite(FsContext[13]);
    }
  }
  else
  {
    CcMdlReadComplete(*(PFILE_OBJECT *)(v5 + 48), *(PMDL *)(a2 + 8));
  }
  *(_DWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 4) &= ~0x100u;
  *(_QWORD *)(a2 + 8) = 0;
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(0);
  RefsExtendedCompleteRequestInternal(a1, a2, 0);
  return 0;
}

```

## disassembly

```asm
0x1c018f524  mov     rax, rsp
0x1c018f527  mov     [rax+8], rbx
0x1c018f52b  mov     [rax+10h], rsi
0x1c018f52f  mov     [rax+18h], rdi
0x1c018f533  mov     [rax+20h], r14
0x1c018f537  push    r15
0x1c018f539  sub     rsp, 40h
0x1c018f53d  mov     rsi, rdx
0x1c018f540  mov     rdi, rcx
0x1c018f543  and     qword ptr [rax-10h], 0
0x1c018f548  mov     r15, [rdx+0B8h]
0x1c018f54f  mov     r14, [r15+30h]
0x1c018f553  movzx   r9d, byte ptr [rcx+28h]
0x1c018f558  mov     ecx, r9d
0x1c018f55b  sub     ecx, 3
0x1c018f55e  jz      loc_1C018F64E
0x1c018f564  cmp     ecx, 1
0x1c018f567  jz      short loc_1C018F5CA
0x1c018f569  mov     cl, r9b
0x1c018f56c  lea     rax, WPP_GLOBAL_Control
0x1c018f573  mov     r10, cs:WPP_GLOBAL_Control
0x1c018f57a  cmp     r10, rax
0x1c018f57d  jz      short loc_1C018F5A6
0x1c018f57f  mov     eax, [r10+2Ch]
0x1c018f583  test    al, 1
0x1c018f585  jz      short loc_1C018F5A6
0x1c018f587  cmp     byte ptr [r10+29h], 2
0x1c018f58c  jb      short loc_1C018F5A6
0x1c018f58e  mov     edx, 12h
0x1c018f593  lea     r8, WPP_34beff5d47f330610d64a67e096d2140_Traceguids
0x1c018f59a  mov     rcx, [r10+18h]
0x1c018f59e  call    WPP_SF_D
0x1c018f5a3  mov     cl, [rdi+28h]
0x1c018f5a6  movzx   r8d, cl; BugCheckParameter2
0x1c018f5aa  and     [rsp+48h+var_28], 0
0x1c018f5b0  xor     r9d, r9d; BugCheckParameter3
0x1c018f5b3  mov     edx, 50440h; BugCheckParameter1
0x1c018f5b8  mov     ecx, 149h; BugCheckCode
0x1c018f5bd  call    cs:__imp_KeBugCheckEx
0x1c018f5ca  xor     ecx, ecx
0x1c018f5cc  mov     [rsp+48h+var_18], ecx
0x1c018f5d0  mov     rbx, [r14+18h]
0x1c018f5d4  mov     [rsp+48h+var_10], rbx
0x1c018f5d9  cmp     [rbx+10h], rcx
0x1c018f5dd  jz      short loc_1C018F5FF
0x1c018f5df  mov     rax, [rdx+8]
0x1c018f5e3  test    rax, rax
0x1c018f5e6  jz      short loc_1C018F5F4
0x1c018f5e8  add     ecx, [rax+28h]
0x1c018f5eb  mov     [rsp+48h+var_18], ecx
0x1c018f5ef  mov     rax, [rax]
0x1c018f5f2  jmp     short loc_1C018F5E3
0x1c018f5f4  mov     r8b, 1
0x1c018f5f7  mov     rdx, rbx
0x1c018f5fa  call    RefsAcquirePagingResourceShared
0x1c018f5ff  lea     rdx, [r15+18h]; FileOffset
0x1c018f603  mov     r8, [rsi+8]; MdlChain
0x1c018f607  mov     rcx, r14; FileObject
0x1c018f60a  call    cs:__imp_CcMdlWriteComplete
0x1c018f611  nop     dword ptr [rax+rax+00h]
0x1c018f616  and     qword ptr [rsi+8], 0
0x1c018f61b  mov     rdx, rbx
0x1c018f61e  mov     rcx, rdi
0x1c018f621  call    RefsFlushForWriteThrough
0x1c018f626  nop
0x1c018f627  cmp     qword ptr [rbx+10h], 0
0x1c018f62c  jz      short loc_1C018F661
0x1c018f62e  mov     eax, 802h
0x1c018f633  cmp     ax, [rbx]
0x1c018f636  jz      short loc_1C018F63C
0x1c018f638  mov     rbx, [rbx+78h]
0x1c018f63c  mov     rcx, [rbx+68h]; Resource
0x1c018f640  call    cs:__imp_ExReleaseResourceLite
0x1c018f647  nop     dword ptr [rax+rax+00h]
0x1c018f64c  jmp     short loc_1C018F661
0x1c018f64e  mov     rdx, [rdx+8]; MdlChain
0x1c018f652  mov     rcx, r14; FileObject
0x1c018f655  call    cs:__imp_CcMdlReadComplete
0x1c018f65c  nop     dword ptr [rax+rax+00h]
0x1c018f661  and     dword ptr [rdi+10h], 0
0x1c018f665  btr     dword ptr [rdi+4], 8
0x1c018f66a  and     qword ptr [rsi+8], 0
0x1c018f66f  mov     al, cs:RefsStatusDebugEnabled
0x1c018f675  test    al, al
0x1c018f677  jz      short loc_1C018F68D
0x1c018f679  mov     r8d, 456h
0x1c018f67f  lea     rdx, aCachesupC; "CacheSup.c"
0x1c018f686  xor     ecx, ecx; Status
0x1c018f688  call    RefsStatusDebug
0x1c018f68d  xor     r8d, r8d
0x1c018f690  mov     rdx, rsi
0x1c018f693  mov     rcx, rdi
0x1c018f696  call    RefsExtendedCompleteRequestInternal
0x1c018f69b  xor     eax, eax
0x1c018f69d  mov     rbx, [rsp+48h+arg_0]
0x1c018f6a2  mov     rsi, [rsp+48h+arg_8]
0x1c018f6a7  mov     rdi, [rsp+48h+arg_10]
0x1c018f6ac  mov     r14, [rsp+48h+arg_18]
0x1c018f6b1  add     rsp, 40h
0x1c018f6b5  pop     r15
0x1c018f6b7  retn
0x1c018f6b9  push    rbp
0x1c018f6bb  sub     rsp, 30h
0x1c018f6bf  mov     rbp, rdx
0x1c018f6c2  mov     rcx, [rbp+38h]
0x1c018f6c6  cmp     qword ptr [rcx+10h], 0
0x1c018f6cb  jz      short loc_1C018F6EC
0x1c018f6cd  mov     eax, 802h
0x1c018f6d2  cmp     ax, [rcx]
0x1c018f6d5  jz      short loc_1C018F6DB
0x1c018f6d7  mov     rcx, [rcx+78h]
0x1c018f6db  mov     rcx, [rcx+68h]; Resource
0x1c018f6df  call    cs:__imp_ExReleaseResourceLite
0x1c018f6e6  nop     dword ptr [rax+rax+00h]
0x1c018f6eb  nop
0x1c018f6ec  add     rsp, 30h
0x1c018f6f0  pop     rbp
0x1c018f6f1  retn
```
