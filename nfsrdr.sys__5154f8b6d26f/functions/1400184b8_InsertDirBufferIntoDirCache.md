# InsertDirBufferIntoDirCache

- ea: `0x1400184b8`
- end: `0x1400186a3`
- name: `InsertDirBufferIntoDirCache`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140012c40`

## callees

- `0x140008140`
- `0x1400159cc`
- `0x14001837c`
- `0x1400184b8`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140018582`
- `ntoskrnl!KeReleaseMutex` at `0x14001861d`
- `ntoskrnl!KeReleaseMutex` at `0x140018582`
- `ntoskrnl!KeReleaseMutex` at `0x14001861d`
- `ntoskrnl!ExAllocatePool2` at `0x140018565`
- `ntoskrnl!ExAllocatePool2` at `0x140018565`

## pseudocode

```c
__int64 __fastcall InsertDirBufferIntoDirCache(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4, __int64 a5)
{
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 Pool2; // rax
  unsigned int v13; // edi
  bool v14; // zf

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids);
  if ( !a2 || !a3 || !a4 )
  {
    v13 = -1073741811;
    goto LABEL_23;
  }
  HacAcquireLock(a2, a2, a3);
  v9 = *(_QWORD *)(a2 + 32);
  if ( v9 )
  {
    v10 = *(_QWORD *)(a4 + 80);
    if ( !v10 || v10 != *(_QWORD *)(*(_QWORD *)(v9 + 8) + 32LL) )
      DeleteDirCache(a1, a2);
  }
  v11 = *(_QWORD *)(a2 + 32);
  if ( v11 )
  {
    *a3 = **(_QWORD **)(v11 + 8);
    **(_QWORD **)(v11 + 8) = a3;
    *(_QWORD *)(v11 + 8) = a3;
  }
  else
  {
    Pool2 = ExAllocatePool2(258, 48, 1246914126);
    v11 = Pool2;
    if ( !Pool2 )
    {
      v13 = -1073741670;
      KeReleaseMutex(*(PRKMUTEX *)(a2 + 40), 0);
LABEL_23:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids);
      return v13;
    }
    *(_QWORD *)(Pool2 + 16) = 48;
    *(_WORD *)(Pool2 + 4) = *(_WORD *)a4;
    *(_DWORD *)(Pool2 + 32) = *(_DWORD *)(a2 + 136);
    *(_QWORD *)(Pool2 + 36) = *(_QWORD *)(a2 + 200);
    *(_QWORD *)(Pool2 + 8) = a3;
    *(_DWORD *)Pool2 = _InterlockedIncrement(&GlobalDirCacheCounter);
    v14 = *(_DWORD *)Pool2 == -1;
    *(_QWORD *)(Pool2 + 24) = MEMORY[0xFFFFF78000000014];
    if ( v14 )
      *(_DWORD *)Pool2 = _InterlockedIncrement(&GlobalDirCacheCounter);
    *(_QWORD *)(a2 + 32) = Pool2;
  }
  *(_QWORD *)(v11 + 16) += a5;
  *(_DWORD *)(a4 + 20) = **(_DWORD **)(a2 + 32);
  KeReleaseMutex(*(PRKMUTEX *)(a2 + 40), 0);
  *(_QWORD *)(a4 + 24) = a3;
  *(_WORD *)(a4 + 16) = 0;
  *(_QWORD *)(a4 + 32) = a3 + 5;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1400184b8  push    rbx
0x1400184ba  push    rbp
0x1400184bb  push    rsi
0x1400184bc  push    rdi
0x1400184bd  push    r12
0x1400184bf  sub     rsp, 20h
0x1400184c3  mov     rsi, r9
0x1400184c6  mov     rdi, r8
0x1400184c9  mov     rbx, rdx
0x1400184cc  mov     rbp, rcx
0x1400184cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400184d6  lea     r12, WPP_GLOBAL_Control
0x1400184dd  cmp     rcx, r12
0x1400184e0  jz      short loc_1400184FE
0x1400184e2  mov     eax, [rcx+2Ch]
0x1400184e5  test    al, 40h
0x1400184e7  jz      short loc_1400184FE
0x1400184e9  mov     rcx, [rcx+18h]
0x1400184ed  lea     r8, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids
0x1400184f4  mov     edx, 1Eh
0x1400184f9  call    WPP_SF_
0x1400184fe  test    rbx, rbx
0x140018501  jz      loc_140018667
0x140018507  test    rdi, rdi
0x14001850a  jz      loc_140018667
0x140018510  test    rsi, rsi
0x140018513  jz      loc_140018667
0x140018519  mov     rcx, rbx
0x14001851c  call    HacAcquireLock
0x140018521  mov     rax, [rbx+20h]
0x140018525  test    rax, rax
0x140018528  jz      short loc_140018548
0x14001852a  mov     rcx, [rsi+50h]
0x14001852e  test    rcx, rcx
0x140018531  jz      short loc_14001853D
0x140018533  mov     rax, [rax+8]
0x140018537  cmp     rcx, [rax+20h]
0x14001853b  jz      short loc_140018548
0x14001853d  mov     rdx, rbx
0x140018540  mov     rcx, rbp
0x140018543  call    DeleteDirCache
0x140018548  mov     rdx, [rbx+20h]
0x14001854c  test    rdx, rdx
0x14001854f  jnz     loc_1400185F0
0x140018555  lea     ebp, [rdx+30h]
0x140018558  mov     r8d, 4A52664Eh
0x14001855e  mov     edx, ebp
0x140018560  mov     ecx, 102h
0x140018565  call    cs:__imp_ExAllocatePool2
0x14001856c  nop     dword ptr [rax+rax+00h]
0x140018571  mov     rdx, rax; Wait
0x140018574  test    rax, rax
0x140018577  jnz     short loc_140018593
0x140018579  mov     edi, 0C000009Ah
0x14001857e  mov     rcx, [rbx+28h]; Mutex
0x140018582  call    cs:__imp_KeReleaseMutex
0x140018589  nop     dword ptr [rax+rax+00h]
0x14001858e  jmp     loc_14001866C
0x140018593  mov     [rax+10h], rbp
0x140018597  mov     ecx, 1
0x14001859c  movzx   eax, word ptr [rsi]
0x14001859f  mov     [rdx+4], ax
0x1400185a3  mov     eax, [rbx+88h]
0x1400185a9  mov     [rdx+20h], eax
0x1400185ac  mov     rax, [rbx+0C8h]
0x1400185b3  mov     [rdx+24h], rax
0x1400185b7  mov     eax, ecx
0x1400185b9  mov     [rdx+8], rdi
0x1400185bd  lock xadd cs:GlobalDirCacheCounter, eax
0x1400185c5  add     eax, ecx
0x1400185c7  mov     [rdx], eax
0x1400185c9  mov     rax, ds:0FFFFF78000000014h
0x1400185d3  cmp     dword ptr [rdx], 0FFFFFFFFh
0x1400185d6  mov     [rdx+18h], rax
0x1400185da  jnz     short loc_1400185EA
0x1400185dc  mov     eax, ecx
0x1400185de  lock xadd cs:GlobalDirCacheCounter, eax
0x1400185e6  add     eax, ecx
0x1400185e8  mov     [rdx], eax
0x1400185ea  mov     [rbx+20h], rdx
0x1400185ee  jmp     short loc_140018605
0x1400185f0  mov     rax, [rdx+8]
0x1400185f4  mov     rcx, [rax]
0x1400185f7  mov     [rdi], rcx
0x1400185fa  mov     rax, [rdx+8]
0x1400185fe  mov     [rax], rdi
0x140018601  mov     [rdx+8], rdi
0x140018605  mov     rax, [rsp+48h+arg_20]
0x14001860a  add     [rdx+10h], rax
0x14001860e  xor     edx, edx; Wait
0x140018610  mov     rax, [rbx+20h]
0x140018614  mov     ecx, [rax]
0x140018616  mov     [rsi+14h], ecx
0x140018619  mov     rcx, [rbx+28h]; Mutex
0x14001861d  call    cs:__imp_KeReleaseMutex
0x140018624  nop     dword ptr [rax+rax+00h]
0x140018629  xor     eax, eax
0x14001862b  mov     [rsi+18h], rdi
0x14001862f  mov     [rsi+10h], ax
0x140018633  lea     rax, [rdi+28h]
0x140018637  mov     [rsi+20h], rax
0x14001863b  mov     rcx, cs:WPP_GLOBAL_Control
0x140018642  cmp     rcx, r12
0x140018645  jz      short loc_140018663
0x140018647  mov     eax, [rcx+2Ch]
0x14001864a  test    al, 40h
0x14001864c  jz      short loc_140018663
0x14001864e  mov     rcx, [rcx+18h]
0x140018652  lea     r8, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids
0x140018659  mov     edx, 1Fh
0x14001865e  call    WPP_SF_
0x140018663  xor     eax, eax
0x140018665  jmp     short loc_140018697
0x140018667  mov     edi, 0C000000Dh
0x14001866c  mov     rcx, cs:WPP_GLOBAL_Control
0x140018673  cmp     rcx, r12
0x140018676  jz      short loc_140018695
0x140018678  mov     edx, [rcx+2Ch]
0x14001867b  test    dl, 40h
0x14001867e  jz      short loc_140018695
0x140018680  mov     rcx, [rcx+18h]
0x140018684  lea     r8, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids
0x14001868b  mov     edx, 20h ; ' '
0x140018690  call    WPP_SF_
0x140018695  mov     eax, edi
0x140018697  add     rsp, 20h
0x14001869b  pop     r12
0x14001869d  pop     rdi
0x14001869e  pop     rsi
0x14001869f  pop     rbp
0x1400186a0  pop     rbx
0x1400186a1  retn
```
