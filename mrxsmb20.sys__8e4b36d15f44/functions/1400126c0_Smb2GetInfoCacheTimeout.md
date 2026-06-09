# Smb2GetInfoCacheTimeout

- ea: `0x1400126c0`
- end: `0x14001288b`
- name: `Smb2GetInfoCacheTimeout`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004b30`

## callees

- `0x140012210`
- `0x1400126c0`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400127f4`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400127f4`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400126e1`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400126e1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400126f1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400126f1`
- `ntoskrnl!KeBugCheckEx` at `0x140012860`
- `ntoskrnl!KeBugCheckEx` at `0x140012860`

## pseudocode

```c
void __fastcall Smb2GetInfoCacheTimeout(__int64 a1, int *a2)
{
  __int64 v2; // rdi
  int v4; // ebx
  __int64 v5; // rsi
  KIRQL v6; // r15
  ULONG_PTR v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  _QWORD *v11; // rax
  _QWORD *v12; // rdx
  _QWORD *v13; // r8
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  __int64 FirstBindingObject; // rax

  v2 = *(_QWORD *)(a1 + 40);
  v4 = 0;
  v5 = *(_QWORD *)(v2 + 24);
  v6 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v5 + 1920));
  *(_DWORD *)(v5 + 2352) = (unsigned int)PsGetCurrentThreadId();
  if ( *(_DWORD *)(v2 + 12) )
    goto LABEL_20;
  v8 = *(_QWORD *)(v2 + 416);
  v9 = *(unsigned __int16 *)(v8 + 2);
  if ( (_WORD)v9 )
  {
    v10 = v9 + v8 + 8;
    if ( !v10 )
      goto LABEL_21;
  }
  else
  {
    v10 = 8;
  }
  v11 = *(_QWORD **)v10;
  if ( !*(_QWORD *)v10 || (v12 = *(_QWORD **)(v10 + 8)) == 0 || v11[1] != v10 || *v12 != v10 )
LABEL_21:
    __fastfail(3u);
  while ( v11 != (_QWORD *)v10 )
  {
    if ( !v11 )
      goto LABEL_21;
    if ( !*v11 )
      goto LABEL_21;
    v13 = (_QWORD *)v11[1];
    if ( !v13 || *(_QWORD **)(*v11 + 8LL) != v11 || (_QWORD *)*v13 != v11 )
      goto LABEL_21;
    v7 = (ULONG_PTR)(v11 - 50);
    v12 = (_QWORD *)*((int *)v11 - 98);
    if ( (int)v12 < 0 )
      KeBugCheckEx(0x27u, 0xA0001u, v7, *((int *)v11 - 98), 0);
    if ( *(_WORD *)v7 != 0xE2FF )
    {
      if ( v11 != (_QWORD *)400 )
      {
        v14 = *(_QWORD *)(v7 + 392);
        if ( v14 )
          goto LABEL_18;
      }
      break;
    }
    v11 = (_QWORD *)*v11;
  }
  FirstBindingObject = SmbCeGetFirstBindingObjectEx(*(_QWORD *)(*(_QWORD *)(v2 + 416) + 384LL), v12, v7, 58111);
  if ( !FirstBindingObject )
    goto LABEL_20;
  v14 = *(_QWORD *)(FirstBindingObject + 392);
  if ( !v14 )
    goto LABEL_20;
LABEL_18:
  v15 = *(_QWORD *)(v14 + 280);
  if ( v15 >= 0xC738 )
  {
    v4 = 60;
    if ( v15 < 0x31128 )
      v4 = 30;
  }
  else
  {
    v4 = 10;
  }
LABEL_20:
  *a2 = v4;
  *(_DWORD *)(v5 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v5 + 1920), v6);
}

```

## disassembly

```asm
0x1400126c0  push    rbx
0x1400126c2  push    rbp
0x1400126c3  push    rsi
0x1400126c4  push    rdi
0x1400126c5  push    r14
0x1400126c7  push    r15
0x1400126c9  sub     rsp, 38h
0x1400126cd  mov     rdi, [rcx+28h]
0x1400126d1  mov     r14, rdx
0x1400126d4  xor     ebx, ebx
0x1400126d6  mov     rsi, [rdi+18h]
0x1400126da  lea     rcx, [rsi+780h]; SpinLock
0x1400126e1  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400126e8  nop     dword ptr [rax+rax+00h]
0x1400126ed  movzx   r15d, al
0x1400126f1  call    cs:__imp_PsGetCurrentThreadId
0x1400126f8  nop     dword ptr [rax+rax+00h]
0x1400126fd  mov     [rsi+930h], eax
0x140012703  cmp     [rdi+0Ch], ebx
0x140012706  jnz     loc_1400127DC
0x14001270c  mov     rcx, [rdi+1A0h]
0x140012713  movzx   edx, word ptr [rcx+2]
0x140012717  test    dx, dx
0x14001271a  jz      loc_140012815
0x140012720  add     rcx, 8
0x140012724  add     rcx, rdx
0x140012727  jz      loc_14001280E
0x14001272d  mov     rax, [rcx]
0x140012730  test    rax, rax
0x140012733  jz      loc_14001280E
0x140012739  mov     rdx, [rcx+8]
0x14001273d  test    rdx, rdx
0x140012740  jz      loc_14001280E
0x140012746  cmp     [rax+8], rcx
0x14001274a  jnz     loc_14001280E
0x140012750  cmp     [rdx], rcx
0x140012753  jnz     loc_14001280E
0x140012759  mov     r9d, 0E2FFh
0x14001275f  cmp     rax, rcx
0x140012762  jz      loc_14001286D
0x140012768  test    rax, rax
0x14001276b  jz      loc_14001280E
0x140012771  mov     rdx, [rax]
0x140012774  test    rdx, rdx
0x140012777  jz      loc_14001280E
0x14001277d  mov     r8, [rax+8]
0x140012781  test    r8, r8
0x140012784  jz      loc_14001280E
0x14001278a  cmp     [rdx+8], rax
0x14001278e  jnz     short loc_14001280E
0x140012790  cmp     [r8], rax
0x140012793  jnz     short loc_14001280E
0x140012795  lea     r8, [rax-190h]; BugCheckParameter2
0x14001279c  movsxd  rdx, dword ptr [r8+8]
0x1400127a0  test    edx, edx
0x1400127a2  js      loc_14001284E
0x1400127a8  cmp     [r8], r9w
0x1400127ac  jz      short loc_14001281F
0x1400127ae  test    r8, r8
0x1400127b1  jz      loc_14001286D
0x1400127b7  mov     rax, [r8+188h]
0x1400127be  test    rax, rax
0x1400127c1  jz      loc_14001286D
0x1400127c7  mov     rcx, [rax+118h]
0x1400127ce  cmp     rcx, 0C738h
0x1400127d5  jnb     short loc_140012827
0x1400127d7  mov     ebx, 0Ah
0x1400127dc  movzx   edx, r15b; OldIrql
0x1400127e0  mov     [r14], ebx
0x1400127e3  lea     rcx, [rsi+780h]; SpinLock
0x1400127ea  mov     dword ptr [rsi+930h], 0FFFFFFFFh
0x1400127f4  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400127fb  nop     dword ptr [rax+rax+00h]
0x140012800  add     rsp, 38h
0x140012804  pop     r15
0x140012806  pop     r14
0x140012808  pop     rdi
0x140012809  pop     rsi
0x14001280a  pop     rbp
0x14001280b  pop     rbx
0x14001280c  retn
0x14001280e  mov     ecx, 3
0x140012813  int     29h; Win8: RtlFailFast(ecx)
0x140012815  mov     ecx, 8
0x14001281a  jmp     loc_14001272D
0x14001281f  mov     rax, [rax]
0x140012822  jmp     loc_14001275F
0x140012827  cmp     rcx, 31128h
0x14001282e  mov     ebx, 3Ch ; '<'
0x140012833  mov     eax, 1Eh
0x140012838  cmovb   ebx, eax
0x14001283b  jmp     short loc_1400127DC
0x14001283d  mov     rax, [rax+188h]
0x140012844  test    rax, rax
0x140012847  jz      short loc_1400127DC
0x140012849  jmp     loc_1400127C7
0x14001284e  mov     r9, rdx; BugCheckParameter3
0x140012851  mov     [rsp+68h+BugCheckParameter4], rbx; BugCheckParameter4
0x140012856  mov     edx, 0A0001h; BugCheckParameter1
0x14001285b  mov     ecx, 27h ; '''; BugCheckCode
0x140012860  call    cs:__imp_KeBugCheckEx
0x14001286d  mov     rcx, [rdi+1A0h]
0x140012874  mov     rcx, [rcx+180h]
0x14001287b  call    SmbCeGetFirstBindingObjectEx
0x140012880  test    rax, rax
0x140012883  jz      loc_1400127DC
0x140012889  jmp     short loc_14001283D
```
