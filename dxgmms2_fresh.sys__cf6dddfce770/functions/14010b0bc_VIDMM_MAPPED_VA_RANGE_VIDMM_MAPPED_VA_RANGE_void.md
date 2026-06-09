# VIDMM_MAPPED_VA_RANGE::~VIDMM_MAPPED_VA_RANGE(void)

- ea: `0x14010b0bc`
- end: `0x14010b1ea`
- name: `??1VIDMM_MAPPED_VA_RANGE@@AEAA@XZ`
- size: `302`
- prototype: `void __fastcall(VIDMM_MAPPED_VA_RANGE *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002f6a8`
- `0x140030758`

## callees

- `0x14002eebc`
- `0x14010b0bc`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14010b138`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14010b138`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010b149`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14010b149`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010b18f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010b18f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010b19b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010b19b`
- `ntoskrnl!RtlAvlRemoveNode` at `0x14010b1c6`
- `ntoskrnl!RtlAvlRemoveNode` at `0x14010b1c6`

## pseudocode

```c
void __fastcall VIDMM_MAPPED_VA_RANGE::~VIDMM_MAPPED_VA_RANGE(VIDMM_MAPPED_VA_RANGE *this)
{
  _QWORD *v1; // rax
  __int64 v3; // rcx
  _QWORD *v4; // rdx
  unsigned __int64 v5; // rax
  int v6; // ecx
  _QWORD *v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // rcx
  _QWORD *v10; // rax

  v1 = (_QWORD *)((char *)this + 32);
  v3 = *((_QWORD *)this + 4);
  if ( v3 )
  {
    if ( *(_QWORD **)(v3 + 8) != v1 )
      goto LABEL_10;
    v4 = (_QWORD *)v1[1];
    if ( (_QWORD *)*v4 != v1 )
      goto LABEL_10;
    *v4 = v3;
    *(_QWORD *)(v3 + 8) = v4;
    *v1 = 0;
  }
  v5 = *((unsigned int *)this + 18);
  if ( (v5 & 0x4000) != 0 )
  {
    RtlAvlRemoveNode(*(_QWORD *)this + 24 * (((v5 >> 4) & 0x3F) + 4), (char *)this + 8);
    *(_OWORD *)((char *)this + 8) = 0;
    *((_QWORD *)this + 3) = 0;
    --*(_DWORD *)(*(_QWORD *)this + 76LL);
  }
  v6 = *((_DWORD *)this + 18);
  if ( (v6 & 0x2000) == 0 )
  {
    v7 = (_QWORD *)((char *)this + 48);
    if ( *((_QWORD *)this + 6) )
    {
      v8 = GetVidMmGlobalAllocFromOwner(v6 & 0xF, *((_QWORD *)this + 8)) + 192;
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v8, 0);
      *(_QWORD *)(v8 + 8) = KeGetCurrentThread();
      v9 = *v7;
      if ( *(_QWORD **)(*v7 + 8LL) == v7 )
      {
        v10 = (_QWORD *)v7[1];
        if ( (_QWORD *)*v10 == v7 )
        {
          *v10 = v9;
          *(_QWORD *)(v9 + 8) = v10;
          *v7 = 0;
          *(_QWORD *)(v8 + 8) = 0;
          ExReleasePushLockExclusiveEx(v8, 0);
          KeLeaveCriticalRegion();
          return;
        }
      }
LABEL_10:
      __fastfail(3u);
    }
  }
}

```

## disassembly

```asm
0x14010b0bc  mov     [rsp+arg_0], rbx
0x14010b0c1  push    rdi
0x14010b0c2  sub     rsp, 20h
0x14010b0c6  lea     rax, [rcx+20h]
0x14010b0ca  mov     rdi, rcx
0x14010b0cd  mov     rcx, [rax]
0x14010b0d0  test    rcx, rcx
0x14010b0d3  jz      short loc_14010B0F2
0x14010b0d5  cmp     [rcx+8], rax
0x14010b0d9  jnz     short loc_14010B11E
0x14010b0db  mov     rdx, [rax+8]
0x14010b0df  cmp     [rdx], rax
0x14010b0e2  jnz     short loc_14010B11E
0x14010b0e4  mov     [rdx], rcx
0x14010b0e7  mov     [rcx+8], rdx
0x14010b0eb  mov     qword ptr [rax], 0
0x14010b0f2  mov     eax, [rdi+48h]
0x14010b0f5  bt      eax, 0Eh
0x14010b0f9  jb      loc_14010B1AC
0x14010b0ff  mov     ecx, [rdi+48h]
0x14010b102  bt      ecx, 0Dh
0x14010b106  jb      short loc_14010B112
0x14010b108  lea     rbx, [rdi+30h]
0x14010b10c  cmp     qword ptr [rbx], 0
0x14010b110  jnz     short loc_14010B125
0x14010b112  mov     rbx, [rsp+28h+arg_0]
0x14010b117  add     rsp, 20h
0x14010b11b  pop     rdi
0x14010b11c  retn
0x14010b11e  mov     ecx, 3
0x14010b123  int     29h; Win8: RtlFailFast(ecx)
0x14010b125  mov     rdx, [rdi+40h]
0x14010b129  and     ecx, 0Fh
0x14010b12c  call    ?GetVidMmGlobalAllocFromOwner@@YAPEAUVIDMM_GLOBAL_ALLOC@@W4VIDMM_VAD_OWNER_TYPE@@PEAX@Z; GetVidMmGlobalAllocFromOwner(VIDMM_VAD_OWNER_TYPE,void *)
0x14010b131  lea     rdi, [rax+0C0h]
0x14010b138  call    cs:__imp_KeEnterCriticalRegion
0x14010b13f  nop     dword ptr [rax+rax+00h]
0x14010b144  xor     edx, edx
0x14010b146  mov     rcx, rdi
0x14010b149  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14010b150  nop     dword ptr [rax+rax+00h]
0x14010b155  mov     rax, gs:188h
0x14010b15e  mov     [rdi+8], rax
0x14010b162  mov     rcx, [rbx]
0x14010b165  cmp     [rcx+8], rbx
0x14010b169  jnz     short loc_14010B11E
0x14010b16b  mov     rax, [rbx+8]
0x14010b16f  cmp     [rax], rbx
0x14010b172  jnz     short loc_14010B11E
0x14010b174  mov     [rax], rcx
0x14010b177  xor     edx, edx
0x14010b179  mov     [rcx+8], rax
0x14010b17d  mov     rcx, rdi
0x14010b180  mov     qword ptr [rbx], 0
0x14010b187  mov     qword ptr [rdi+8], 0
0x14010b18f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14010b196  nop     dword ptr [rax+rax+00h]
0x14010b19b  call    cs:__imp_KeLeaveCriticalRegion
0x14010b1a2  nop     dword ptr [rax+rax+00h]
0x14010b1a7  jmp     loc_14010B112
0x14010b1ac  shr     rax, 4
0x14010b1b0  lea     rdx, [rdi+8]
0x14010b1b4  and     eax, 3Fh
0x14010b1b7  add     rax, 4
0x14010b1bb  lea     rcx, [rax+rax*2]
0x14010b1bf  mov     rax, [rdi]
0x14010b1c2  lea     rcx, [rax+rcx*8]
0x14010b1c6  call    cs:__imp_RtlAvlRemoveNode
0x14010b1cd  nop     dword ptr [rax+rax+00h]
0x14010b1d2  xor     eax, eax
0x14010b1d4  xorps   xmm0, xmm0
0x14010b1d7  movups  xmmword ptr [rdi+8], xmm0
0x14010b1db  mov     [rdi+18h], rax
0x14010b1df  mov     rax, [rdi]
0x14010b1e2  dec     dword ptr [rax+4Ch]
0x14010b1e5  jmp     loc_14010B0FF
```
