# CClfsBaseFile::GetSymbol(long,ulong,_CLFS_CONTAINER_CONTEXT * *)

- ea: `0x140061e00`
- end: `0x140061f2e`
- name: `?GetSymbol@CClfsBaseFile@@QEAAJJKPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(CClfsBaseFile *__hidden this, int, unsigned int, struct _CLFS_CONTAINER_CONTEXT **)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1400394e4`
- `0x140039784`
- `0x140039a00`
- `0x14005ed70`
- `0x140060a70`
- `0x1400616cc`
- `0x140061950`
- `0x140061c00`
- `0x140061d00`
- `0x140063dcc`

## callees

- `0x140061e00`

## import_xrefs

- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140061f04`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14007a620`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140061f04`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14007a620`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140061e3a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140061e3a`

## pseudocode

```c
__int64 __fastcall CClfsBaseFile::GetSymbol(
        PERESOURCE *this,
        unsigned int a2,
        int a3,
        struct _CLFS_CONTAINER_CONTEXT **a4)
{
  __int64 v6; // rdi
  unsigned int v8; // ebx
  BOOLEAN v9; // r11
  PERESOURCE v10; // r8
  ERESOURCE_THREAD OwnerThread; // rdx
  __int64 v12; // rcx
  unsigned int v13; // r9d
  unsigned int v14; // r10d
  unsigned int TableSize; // eax
  __int64 v16; // r8
  __int64 v17; // rax
  int v18; // ecx

  v6 = a2;
  if ( a2 < 0x1368 )
    return 3222929421LL;
  v8 = 0;
  *a4 = 0;
  v9 = ExAcquireResourceSharedLite(this[4], 1u);
  v10 = this[6];
  OwnerThread = v10->OwnerEntry.OwnerThread;
  if ( !OwnerThread )
    goto LABEL_11;
  v12 = *(unsigned int *)(OwnerThread + 40);
  v13 = v12 + v6 + 47;
  if ( v13 < (int)v6 + 47 )
    goto LABEL_11;
  v14 = *(unsigned __int16 *)(OwnerThread + 4) << 9;
  if ( v13 >= v14 )
    goto LABEL_11;
  if ( *((_WORD *)this + 20)
    && (TableSize = v10->OwnerEntry.TableSize, (unsigned int)v12 < TableSize)
    && (unsigned int)v12 >= 0x70
    && TableSize - (unsigned int)v12 >= 0x1338 )
  {
    v16 = OwnerThread + v12;
  }
  else
  {
    v16 = 0;
  }
  if ( (int)v12 + (int)v6 < (unsigned int)v6 )
    goto LABEL_11;
  if ( !v16 )
    goto LABEL_11;
  if ( (int)v12 + (int)v6 >= v14 )
    goto LABEL_11;
  v17 = v16 + v6;
  if ( !(v16 + v6) )
    goto LABEL_11;
  v18 = *(_DWORD *)(v17 - 12);
  if ( v18 != (_DWORD)v6 )
  {
    v8 = -1073741816;
    goto LABEL_24;
  }
  if ( *(_DWORD *)(v17 - 16) == (unsigned __int64)(unsigned int)(v18 + 48)
    && *(_DWORD *)v17 == -1040322552
    && *(_DWORD *)(v17 + 4) == 48
    && *(_DWORD *)(v17 + 16) == a3 )
  {
    *a4 = (struct _CLFS_CONTAINER_CONTEXT *)v17;
  }
  else
  {
LABEL_11:
    v8 = -1072037875;
  }
LABEL_24:
  if ( v9 )
    ExReleaseResourceForThreadLite(this[4], (ERESOURCE_THREAD)KeGetCurrentThread());
  return v8;
}

```

## disassembly

```asm
0x140061e00  mov     [rsp+arg_10], rbx
0x140061e05  mov     [rsp+arg_18], rsi
0x140061e0a  mov     [rsp+arg_0], rcx
0x140061e0f  push    rdi
0x140061e10  push    r14
0x140061e12  push    r15
0x140061e14  sub     rsp, 20h
0x140061e18  mov     r14, r9
0x140061e1b  mov     r15d, r8d
0x140061e1e  mov     edi, edx
0x140061e20  mov     rsi, rcx
0x140061e23  cmp     edx, 1368h
0x140061e29  jb      loc_140061F27
0x140061e2f  xor     ebx, ebx
0x140061e31  mov     [r9], rbx
0x140061e34  mov     dl, 1; Wait
0x140061e36  mov     rcx, [rcx+20h]; Resource
0x140061e3a  call    cs:__imp_ExAcquireResourceSharedLite
0x140061e41  nop     dword ptr [rax+rax+00h]
0x140061e46  movzx   r11d, al
0x140061e4a  mov     [rsp+38h+arg_8], al
0x140061e4e  mov     r8, [rsi+30h]
0x140061e52  mov     rdx, [r8+30h]
0x140061e56  test    rdx, rdx
0x140061e59  jz      short loc_140061EA0
0x140061e5b  lea     eax, [rdi+2Fh]
0x140061e5e  mov     ecx, [rdx+28h]
0x140061e61  lea     r9d, [rcx+rax]
0x140061e65  cmp     r9d, eax
0x140061e68  jb      short loc_140061EA0
0x140061e6a  movzx   r10d, word ptr [rdx+4]
0x140061e6f  shl     r10d, 9
0x140061e73  cmp     r9d, r10d
0x140061e76  jnb     short loc_140061EA0
0x140061e78  xor     eax, eax
0x140061e7a  cmp     ax, [rsi+28h]
0x140061e7e  jz      short loc_140061E96
0x140061e80  mov     eax, [r8+38h]
0x140061e84  cmp     ecx, eax
0x140061e86  jnb     short loc_140061E96
0x140061e88  cmp     ecx, 70h ; 'p'
0x140061e8b  jb      short loc_140061E96
0x140061e8d  sub     eax, ecx
0x140061e8f  cmp     eax, 1338h
0x140061e94  jnb     short loc_140061EDB
0x140061e96  xor     r8d, r8d
0x140061e99  lea     eax, [rcx+rdi]
0x140061e9c  cmp     eax, edi
0x140061e9e  jnb     short loc_140061EE1
0x140061ea0  mov     ebx, 0C01A000Dh
0x140061ea5  jmp     short loc_140061EF2
0x140061ea7  mov     rax, rdi
0x140061eaa  add     rax, r8
0x140061ead  jz      short loc_140061EA0
0x140061eaf  mov     ecx, [rax-0Ch]
0x140061eb2  cmp     ecx, edi
0x140061eb4  jnz     short loc_140061EED
0x140061eb6  lea     edx, [rcx+30h]
0x140061eb9  movsxd  rcx, dword ptr [rax-10h]
0x140061ebd  cmp     rcx, rdx
0x140061ec0  jnz     short loc_140061EA0
0x140061ec2  cmp     dword ptr [rax], 0C1FDF008h
0x140061ec8  jnz     short loc_140061EA0
0x140061eca  cmp     dword ptr [rax+4], 30h ; '0'
0x140061ece  jnz     short loc_140061EA0
0x140061ed0  cmp     [rax+10h], r15d
0x140061ed4  jnz     short loc_140061EA0
0x140061ed6  mov     [r14], rax
0x140061ed9  jmp     short loc_140061EF2
0x140061edb  lea     r8, [rdx+rcx]
0x140061edf  jmp     short loc_140061E99
0x140061ee1  test    r8, r8
0x140061ee4  jz      short loc_140061EA0
0x140061ee6  cmp     eax, r10d
0x140061ee9  jnb     short loc_140061EA0
0x140061eeb  jmp     short loc_140061EA7
0x140061eed  mov     ebx, 0C0000008h
0x140061ef2  test    r11b, r11b
0x140061ef5  jz      short loc_140061F10
0x140061ef7  mov     rdx, gs:188h; ResourceThreadId
0x140061f00  mov     rcx, [rsi+20h]; Resource
0x140061f04  call    cs:__imp_ExReleaseResourceForThreadLite
0x140061f0b  nop     dword ptr [rax+rax+00h]
0x140061f10  mov     eax, ebx
0x140061f12  mov     rbx, [rsp+38h+arg_10]
0x140061f17  mov     rsi, [rsp+38h+arg_18]
0x140061f1c  add     rsp, 20h
0x140061f20  pop     r15
0x140061f22  pop     r14
0x140061f24  pop     rdi
0x140061f25  retn
0x140061f27  mov     eax, 0C01A000Dh
0x140061f2c  jmp     short loc_140061F12
0x14007a600  push    rbp
0x14007a602  sub     rsp, 20h
0x14007a606  mov     rbp, rdx
0x14007a609  cmp     byte ptr [rbp+48h], 0
0x14007a60d  jz      short loc_14007A62D
0x14007a60f  mov     rdx, gs:188h; ResourceThreadId
0x14007a618  mov     rcx, [rbp+40h]
0x14007a61c  mov     rcx, [rcx+20h]; Resource
0x14007a620  call    cs:__imp_ExReleaseResourceForThreadLite
0x14007a627  nop     dword ptr [rax+rax+00h]
0x14007a62c  nop
0x14007a62d  add     rsp, 20h
0x14007a631  pop     rbp
0x14007a632  retn
```
