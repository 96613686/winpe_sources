# DepFSDismountDependenciesOnVolume

- ea: `0x18000a874`
- end: `0x18000aa40`
- name: `DepFSDismountDependenciesOnVolume`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000c940`

## callees

- `0x180001020`
- `0x18000a874`
- `0x18000aa48`
- `0x18000eac0`
- `0x18000f73c`
- `0x18000f91c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000a8fb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000aa28`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000a8fb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000aa28`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000aa09`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000aa09`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000a8ef`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000aa1c`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000a8ef`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000aa1c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000a89c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000a9b2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000a89c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000a9b2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000a887`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000a99d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000a887`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000a99d`

## pseudocode

```c
__int64 __fastcall DepFSDismountDependenciesOnVolume(__int64 a1)
{
  unsigned int v1; // ebp
  int v3; // eax
  _WORD *v4; // rbx
  int v5; // esi
  __int16 v6; // ax
  _DWORD *v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rax
  __int16 v10; // dx
  _DWORD *v11; // rcx
  char v13; // [rsp+20h] [rbp-38h]
  PVOID P; // [rsp+60h] [rbp+8h] BYREF

  v1 = 0;
  P = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  v3 = *(_DWORD *)(a1 + 56);
  if ( (v3 & 1) != 0 || (*(_DWORD *)(a1 + 56) = v3 | 1, *(_QWORD *)(a1 + 8) == a1 + 8) )
  {
LABEL_23:
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    return v1;
  }
  v13 = 1;
  v1 = DepFSGenerateDependencyList(0, a1, 0, &P, v13, 256);
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
  if ( (v1 & 0x80000000) != 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids, v1);
  }
  v4 = P;
  if ( P )
  {
    v5 = 0;
    if ( *((_DWORD *)P + 1) )
    {
      while ( 1 )
      {
        v6 = v4[8 * v5 + 4];
        if ( (v6 & 1) != 0 )
          break;
        if ( (v6 & 2) != 0 )
        {
          v1 = DepFSDismountDependency(*(char **)&v4[8 * v5 + 8]);
          goto LABEL_14;
        }
LABEL_15:
        if ( (unsigned int)++v5 >= *((_DWORD *)v4 + 1) )
          goto LABEL_16;
      }
      DereferenceVolumeContext(*(_QWORD *)&v4[8 * v5 + 8]);
      *(_QWORD *)&v4[8 * v5 + 8] = 0;
LABEL_14:
      v4 = P;
      goto LABEL_15;
    }
LABEL_16:
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    v7 = P;
    v8 = 0;
    if ( *((_DWORD *)P + 1) )
    {
      do
      {
        v9 = 4LL * v8;
        v10 = v7[v9 + 2];
        if ( (v10 & 2) != 0 )
        {
          v11 = &v7[v9];
          if ( (v10 & 0x100) != 0 )
            _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)v11 + 2) + 96LL));
          DereferenceDependencyContext(*((PVOID *)v11 + 2));
          v7 = P;
        }
        ++v8;
      }
      while ( v8 < v7[1] );
    }
    ExFreePoolWithTag(v7, 0x6C447044u);
    goto LABEL_23;
  }
  return v1;
}

```

## disassembly

```asm
0x18000a874  push    rbx
0x18000a876  push    rbp
0x18000a877  push    rsi
0x18000a878  push    rdi
0x18000a879  sub     rsp, 38h
0x18000a87d  xor     ebp, ebp
0x18000a87f  mov     rbx, rcx
0x18000a882  mov     [rsp+58h+P], rbp
0x18000a887  call    cs:__imp_KeEnterCriticalRegion
0x18000a88e  nop     dword ptr [rax+rax+00h]
0x18000a893  mov     dl, 1; Wait
0x18000a895  lea     rcx, Resource; Resource
0x18000a89c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000a8a3  nop     dword ptr [rax+rax+00h]
0x18000a8a8  mov     eax, [rbx+38h]
0x18000a8ab  test    al, 1
0x18000a8ad  jnz     loc_18000AA15
0x18000a8b3  or      eax, 1
0x18000a8b6  mov     [rbx+38h], eax
0x18000a8b9  lea     rax, [rbx+8]
0x18000a8bd  cmp     [rax], rax
0x18000a8c0  jz      loc_18000AA15
0x18000a8c6  mov     edi, 100h
0x18000a8cb  lea     r9, [rsp+58h+P]
0x18000a8d0  mov     [rsp+58h+var_30], edi
0x18000a8d4  xor     r8d, r8d
0x18000a8d7  mov     rdx, rbx
0x18000a8da  mov     [rsp+58h+var_38], 1
0x18000a8df  xor     ecx, ecx
0x18000a8e1  call    DepFSGenerateDependencyList
0x18000a8e6  lea     rcx, Resource; Resource
0x18000a8ed  mov     ebp, eax
0x18000a8ef  call    cs:__imp_ExReleaseResourceLite
0x18000a8f6  nop     dword ptr [rax+rax+00h]
0x18000a8fb  call    cs:__imp_KeLeaveCriticalRegion
0x18000a902  nop     dword ptr [rax+rax+00h]
0x18000a907  test    ebp, ebp
0x18000a909  jns     short loc_18000A944
0x18000a90b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a912  lea     rax, WPP_GLOBAL_Control
0x18000a919  cmp     rcx, rax
0x18000a91c  jz      short loc_18000A944
0x18000a91e  mov     edx, [rcx+2Ch]
0x18000a921  test    dl, 1
0x18000a924  jz      short loc_18000A944
0x18000a926  cmp     byte ptr [rcx+29h], 2
0x18000a92a  jb      short loc_18000A944
0x18000a92c  mov     rcx, [rcx+18h]
0x18000a930  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000a937  mov     edx, 1Ah
0x18000a93c  mov     r9d, ebp
0x18000a93f  call    WPP_SF_D
0x18000a944  mov     rbx, [rsp+58h+P]
0x18000a949  test    rbx, rbx
0x18000a94c  jz      loc_18000AA34
0x18000a952  xor     esi, esi
0x18000a954  cmp     [rbx+4], esi
0x18000a957  jbe     short loc_18000A99D
0x18000a959  mov     edi, esi
0x18000a95b  add     rdi, rdi
0x18000a95e  movzx   eax, word ptr [rbx+rdi*8+8]
0x18000a963  test    al, 1
0x18000a965  jz      short loc_18000A97C
0x18000a967  mov     rcx, [rbx+rdi*8+10h]
0x18000a96c  call    DereferenceVolumeContext
0x18000a971  mov     qword ptr [rbx+rdi*8+10h], 0
0x18000a97a  jmp     short loc_18000A98C
0x18000a97c  test    al, 2
0x18000a97e  jz      short loc_18000A991
0x18000a980  mov     rcx, [rbx+rdi*8+10h]; P
0x18000a985  call    DepFSDismountDependency
0x18000a98a  mov     ebp, eax
0x18000a98c  mov     rbx, [rsp+58h+P]
0x18000a991  inc     esi
0x18000a993  cmp     esi, [rbx+4]
0x18000a996  jb      short loc_18000A959
0x18000a998  mov     edi, 100h
0x18000a99d  call    cs:__imp_KeEnterCriticalRegion
0x18000a9a4  nop     dword ptr [rax+rax+00h]
0x18000a9a9  mov     dl, 1; Wait
0x18000a9ab  lea     rcx, Resource; Resource
0x18000a9b2  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000a9b9  nop     dword ptr [rax+rax+00h]
0x18000a9be  mov     rcx, [rsp+58h+P]
0x18000a9c3  xor     ebx, ebx
0x18000a9c5  cmp     [rcx+4], ebx
0x18000a9c8  jbe     short loc_18000AA04
0x18000a9ca  mov     eax, ebx
0x18000a9cc  shl     rax, 4
0x18000a9d0  movzx   edx, word ptr [rax+rcx+8]
0x18000a9d5  test    dl, 2
0x18000a9d8  jz      short loc_18000A9FD
0x18000a9da  add     rcx, rax
0x18000a9dd  test    di, dx
0x18000a9e0  jz      short loc_18000A9EA
0x18000a9e2  mov     rax, [rcx+10h]
0x18000a9e6  lock dec dword ptr [rax+60h]
0x18000a9ea  mov     rcx, [rcx+10h]; P
0x18000a9ee  xor     r8d, r8d
0x18000a9f1  mov     dl, 1
0x18000a9f3  call    DereferenceDependencyContext
0x18000a9f8  mov     rcx, [rsp+58h+P]; P
0x18000a9fd  inc     ebx
0x18000a9ff  cmp     ebx, [rcx+4]
0x18000aa02  jb      short loc_18000A9CA
0x18000aa04  mov     edx, 6C447044h; Tag
0x18000aa09  call    cs:__imp_ExFreePoolWithTag
0x18000aa10  nop     dword ptr [rax+rax+00h]
0x18000aa15  lea     rcx, Resource; Resource
0x18000aa1c  call    cs:__imp_ExReleaseResourceLite
0x18000aa23  nop     dword ptr [rax+rax+00h]
0x18000aa28  call    cs:__imp_KeLeaveCriticalRegion
0x18000aa2f  nop     dword ptr [rax+rax+00h]
0x18000aa34  mov     eax, ebp
0x18000aa36  add     rsp, 38h
0x18000aa3a  pop     rdi
0x18000aa3b  pop     rsi
0x18000aa3c  pop     rbp
0x18000aa3d  pop     rbx
0x18000aa3e  retn
```
