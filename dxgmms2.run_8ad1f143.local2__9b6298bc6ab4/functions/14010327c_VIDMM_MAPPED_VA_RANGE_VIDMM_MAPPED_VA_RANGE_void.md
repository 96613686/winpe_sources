# VIDMM_MAPPED_VA_RANGE::~VIDMM_MAPPED_VA_RANGE(void)

- ea: `0x14010327c`
- end: `0x1401033aa`
- name: `??1VIDMM_MAPPED_VA_RANGE@@AEAA@XZ`
- size: `302`
- prototype: `void __fastcall(VIDMM_MAPPED_VA_RANGE *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14003180c`
- `0x140032908`

## callees

- `0x1400311ac`
- `0x14010327c`

## import_xrefs

- `ntoskrnl!RtlAvlRemoveNode` at `0x140103386`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140103386`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401032f8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401032f8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140103309`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140103309`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010334f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14010334f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010335b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14010335b`

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
0x14010327c  mov     [rsp+arg_0], rbx
0x140103281  push    rdi
0x140103282  sub     rsp, 20h
0x140103286  lea     rax, [rcx+20h]
0x14010328a  mov     rdi, rcx
0x14010328d  mov     rcx, [rax]
0x140103290  test    rcx, rcx
0x140103293  jz      short loc_1401032B2
0x140103295  cmp     [rcx+8], rax
0x140103299  jnz     short loc_1401032DE
0x14010329b  mov     rdx, [rax+8]
0x14010329f  cmp     [rdx], rax
0x1401032a2  jnz     short loc_1401032DE
0x1401032a4  mov     [rdx], rcx
0x1401032a7  mov     [rcx+8], rdx
0x1401032ab  mov     qword ptr [rax], 0
0x1401032b2  mov     eax, [rdi+48h]
0x1401032b5  bt      eax, 0Eh
0x1401032b9  jb      loc_14010336C
0x1401032bf  mov     ecx, [rdi+48h]
0x1401032c2  bt      ecx, 0Dh
0x1401032c6  jb      short loc_1401032D2
0x1401032c8  lea     rbx, [rdi+30h]
0x1401032cc  cmp     qword ptr [rbx], 0
0x1401032d0  jnz     short loc_1401032E5
0x1401032d2  mov     rbx, [rsp+28h+arg_0]
0x1401032d7  add     rsp, 20h
0x1401032db  pop     rdi
0x1401032dc  retn
0x1401032de  mov     ecx, 3
0x1401032e3  int     29h; Win8: RtlFailFast(ecx)
0x1401032e5  mov     rdx, [rdi+40h]
0x1401032e9  and     ecx, 0Fh
0x1401032ec  call    ?GetVidMmGlobalAllocFromOwner@@YAPEAUVIDMM_GLOBAL_ALLOC@@W4VIDMM_VAD_OWNER_TYPE@@PEAX@Z; GetVidMmGlobalAllocFromOwner(VIDMM_VAD_OWNER_TYPE,void *)
0x1401032f1  lea     rdi, [rax+0C0h]
0x1401032f8  call    cs:__imp_KeEnterCriticalRegion
0x1401032ff  nop     dword ptr [rax+rax+00h]
0x140103304  xor     edx, edx
0x140103306  mov     rcx, rdi
0x140103309  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140103310  nop     dword ptr [rax+rax+00h]
0x140103315  mov     rax, gs:188h
0x14010331e  mov     [rdi+8], rax
0x140103322  mov     rcx, [rbx]
0x140103325  cmp     [rcx+8], rbx
0x140103329  jnz     short loc_1401032DE
0x14010332b  mov     rax, [rbx+8]
0x14010332f  cmp     [rax], rbx
0x140103332  jnz     short loc_1401032DE
0x140103334  mov     [rax], rcx
0x140103337  xor     edx, edx
0x140103339  mov     [rcx+8], rax
0x14010333d  mov     rcx, rdi
0x140103340  mov     qword ptr [rbx], 0
0x140103347  mov     qword ptr [rdi+8], 0
0x14010334f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140103356  nop     dword ptr [rax+rax+00h]
0x14010335b  call    cs:__imp_KeLeaveCriticalRegion
0x140103362  nop     dword ptr [rax+rax+00h]
0x140103367  jmp     loc_1401032D2
0x14010336c  shr     rax, 4
0x140103370  lea     rdx, [rdi+8]
0x140103374  and     eax, 3Fh
0x140103377  add     rax, 4
0x14010337b  lea     rcx, [rax+rax*2]
0x14010337f  mov     rax, [rdi]
0x140103382  lea     rcx, [rax+rcx*8]
0x140103386  call    cs:__imp_RtlAvlRemoveNode
0x14010338d  nop     dword ptr [rax+rax+00h]
0x140103392  xor     eax, eax
0x140103394  xorps   xmm0, xmm0
0x140103397  movups  xmmword ptr [rdi+8], xmm0
0x14010339b  mov     [rdi+18h], rax
0x14010339f  mov     rax, [rdi]
0x1401033a2  dec     dword ptr [rax+4Ch]
0x1401033a5  jmp     loc_1401032BF
```
