# CClfsBaseFile::GetSymbol(long,uchar,_CLFS_CLIENT_CONTEXT * *)

- ea: `0x140062ad8`
- end: `0x140062c0f`
- name: `?GetSymbol@CClfsBaseFile@@QEAAJJEPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(CClfsBaseFile *__hidden this, int, unsigned __int8, struct _CLFS_CLIENT_CONTEXT **)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14005ed70`
- `0x140060c54`
- `0x140062980`
- `0x140062a30`
- `0x140063c24`

## callees

- `0x14000b6b0`
- `0x140062ad8`
- `0x140062c20`

## import_xrefs

- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140062be5`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140062be5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140062b12`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140062b12`

## pseudocode

```c
__int64 __fastcall CClfsBaseFile::GetSymbol(
        PERESOURCE *this,
        unsigned int a2,
        char a3,
        struct _CLFS_CLIENT_CONTEXT **a4)
{
  __int64 v6; // rdi
  unsigned int v8; // ebx
  BOOLEAN v9; // r11
  ERESOURCE_THREAD OwnerThread; // r9
  __int64 v12; // r9
  struct _CLFS_BASE_RECORD_HEADER *BaseLogRecord; // r10
  unsigned int v14; // ecx
  unsigned int v15; // edx
  int v16; // eax
  char *v17; // rdx

  v6 = a2;
  if ( a2 < 0x1368 )
    return 3222929421LL;
  v8 = 0;
  *a4 = 0;
  v9 = ExAcquireResourceSharedLite(this[4], 1u);
  OwnerThread = this[6]->OwnerEntry.OwnerThread;
  if ( !(OwnerThread
      && (v15 = *(_DWORD *)(OwnerThread + 40) + v6 + 135, v15 >= (int)v6 + 135)
      && v15 < *(unsigned __int16 *)(OwnerThread + 4) << 9) )
    goto LABEL_7;
  BaseLogRecord = CClfsBaseFile::GetBaseLogRecord((CClfsBaseFile *)this);
  if ( !v12 )
    goto LABEL_7;
  v14 = *(_DWORD *)(v12 + 40) + v6;
  if ( v14 < (unsigned int)v6 )
    goto LABEL_7;
  v17 = BaseLogRecord && v14 < *(unsigned __int16 *)(v12 + 4) << 9 ? (char *)BaseLogRecord + v6 : 0LL;
  if ( !v17 )
    goto LABEL_7;
  v16 = *((_DWORD *)v17 - 3);
  if ( v16 != (_DWORD)v6 )
  {
    v8 = -1073741816;
    goto LABEL_22;
  }
  if ( *((_DWORD *)v17 - 4) == (unsigned __int64)(unsigned int)(v16 + 136)
    && *(_DWORD *)v17 == -1040322553
    && *((_DWORD *)v17 + 1) == 136
    && v17[8] == a3 )
  {
    *a4 = (struct _CLFS_CLIENT_CONTEXT *)v17;
  }
  else
  {
LABEL_7:
    v8 = -1072037875;
  }
LABEL_22:
  if ( v9 )
    ExReleaseResourceForThreadLite(this[4], (ERESOURCE_THREAD)KeGetCurrentThread());
  return v8;
}

```

## disassembly

```asm
0x140062ad8  mov     [rsp+arg_10], rbx
0x140062add  mov     [rsp+arg_18], rsi
0x140062ae2  mov     [rsp+arg_0], rcx
0x140062ae7  push    rdi
0x140062ae8  push    r14
0x140062aea  push    r15
0x140062aec  sub     rsp, 20h
0x140062af0  mov     r14, r9
0x140062af3  mov     r15b, r8b
0x140062af6  mov     edi, edx
0x140062af8  mov     rsi, rcx
0x140062afb  cmp     edx, 1368h
0x140062b01  jb      loc_140062C08
0x140062b07  xor     ebx, ebx
0x140062b09  mov     [r9], rbx
0x140062b0c  mov     dl, 1; Wait
0x140062b0e  mov     rcx, [rcx+20h]; Resource
0x140062b12  call    cs:__imp_ExAcquireResourceSharedLite
0x140062b19  nop     dword ptr [rax+rax+00h]
0x140062b1e  mov     r11b, al
0x140062b21  mov     [rsp+38h+arg_8], al
0x140062b25  mov     rax, [rsi+30h]
0x140062b29  mov     r9, [rax+30h]
0x140062b2d  test    r9, r9
0x140062b30  jnz     short loc_140062B5A
0x140062b32  xor     al, al
0x140062b34  test    al, al
0x140062b36  jz      short loc_140062B53
0x140062b38  mov     rcx, rsi; this
0x140062b3b  call    ?GetBaseLogRecord@CClfsBaseFile@@IEAAPEAU_CLFS_BASE_RECORD_HEADER@@XZ; CClfsBaseFile::GetBaseLogRecord(void)
0x140062b40  mov     r10, rax
0x140062b43  test    r9, r9
0x140062b46  jz      short loc_140062B53
0x140062b48  mov     eax, [r9+28h]
0x140062b4c  lea     ecx, [rax+rdi]
0x140062b4f  cmp     ecx, edi
0x140062b51  jnb     short loc_140062BB8
0x140062b53  mov     ebx, 0C01A000Dh
0x140062b58  jmp     short loc_140062BD3
0x140062b5a  lea     ecx, [rdi+87h]
0x140062b60  mov     eax, [r9+28h]
0x140062b64  lea     edx, [rax+rcx]
0x140062b67  cmp     edx, ecx
0x140062b69  jb      short loc_140062B32
0x140062b6b  movzx   eax, word ptr [r9+4]
0x140062b70  shl     eax, 9
0x140062b73  cmp     edx, eax
0x140062b75  setb    al
0x140062b78  jmp     short loc_140062B34
0x140062b7a  test    rdx, rdx
0x140062b7d  jz      short loc_140062B53
0x140062b7f  mov     eax, [rdx-0Ch]
0x140062b82  cmp     eax, edi
0x140062b84  jnz     short loc_140062BB1
0x140062b86  lea     ecx, [rax+88h]
0x140062b8c  movsxd  rax, dword ptr [rdx-10h]
0x140062b90  cmp     rax, rcx
0x140062b93  jnz     short loc_140062B53
0x140062b95  cmp     dword ptr [rdx], 0C1FDF007h
0x140062b9b  jnz     short loc_140062B53
0x140062b9d  cmp     dword ptr [rdx+4], 88h
0x140062ba4  jnz     short loc_140062B53
0x140062ba6  cmp     [rdx+8], r15b
0x140062baa  jnz     short loc_140062B53
0x140062bac  mov     [r14], rdx
0x140062baf  jmp     short loc_140062BD3
0x140062bb1  mov     ebx, 0C0000008h
0x140062bb6  jmp     short loc_140062BD3
0x140062bb8  test    r10, r10
0x140062bbb  jz      short loc_140062BCF
0x140062bbd  movzx   eax, word ptr [r9+4]
0x140062bc2  shl     eax, 9
0x140062bc5  cmp     ecx, eax
0x140062bc7  jnb     short loc_140062BCF
0x140062bc9  lea     rdx, [r10+rdi]
0x140062bcd  jmp     short loc_140062B7A
0x140062bcf  xor     edx, edx
0x140062bd1  jmp     short loc_140062B7A
0x140062bd3  test    r11b, r11b
0x140062bd6  jz      short loc_140062BF1
0x140062bd8  mov     rdx, gs:188h; ResourceThreadId
0x140062be1  mov     rcx, [rsi+20h]; Resource
0x140062be5  call    cs:__imp_ExReleaseResourceForThreadLite
0x140062bec  nop     dword ptr [rax+rax+00h]
0x140062bf1  mov     eax, ebx
0x140062bf3  mov     rbx, [rsp+38h+arg_10]
0x140062bf8  mov     rsi, [rsp+38h+arg_18]
0x140062bfd  add     rsp, 20h
0x140062c01  pop     r15
0x140062c03  pop     r14
0x140062c05  pop     rdi
0x140062c06  retn
0x140062c08  mov     eax, 0C01A000Dh
0x140062c0d  jmp     short loc_140062BF3
0x14007a803  push    rbp
0x14007a805  sub     rsp, 20h
0x14007a809  mov     rbp, rdx
0x14007a80c  cmp     byte ptr [rbp+48h], 0
0x14007a810  jz      short loc_14007A81C
0x14007a812  mov     rcx, [rbp+40h]; this
0x14007a816  call    ?UnlockImage@CClfsBaseFile@@QEAAXXZ; CClfsBaseFile::UnlockImage(void)
0x14007a81b  nop
0x14007a81c  add     rsp, 20h
0x14007a820  pop     rbp
0x14007a821  retn
```
