# SmbCeSwitchConnectionObjectTransport

- ea: `0x14001ca80`
- end: `0x14001cd95`
- name: `SmbCeSwitchConnectionObjectTransport`
- size: `789`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14001ca80`
- `0x140037fa4`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001cc7d`
- `ntoskrnl!KeBugCheckEx` at `0x14001cca3`
- `ntoskrnl!KeBugCheckEx` at `0x14001cd0b`
- `ntoskrnl!KeBugCheckEx` at `0x14001cc7d`
- `ntoskrnl!KeBugCheckEx` at `0x14001cca3`
- `ntoskrnl!KeBugCheckEx` at `0x14001cd0b`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001cc3e`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001cc3e`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14001cab8`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14001cab8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001cac7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001cac7`

## pseudocode

```c
void __fastcall SmbCeSwitchConnectionObjectTransport(__int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // r14
  __int64 v4; // rbx
  KIRQL v5; // bp
  __int64 v6; // rcx
  __int64 v7; // rcx
  int *v8; // rax
  _QWORD *v9; // rdx
  ULONG_PTR v10; // rbx
  int **v11; // r8
  __int64 v12; // rax
  __int64 v13; // rdx
  int **v14; // rax
  int *v15; // rcx
  int ***v16; // r8
  int *v17; // rdx
  int *v18; // rsi
  unsigned int v19; // r8d
  unsigned int v20; // r9d
  __int64 v21; // rcx
  int **v22; // r8

  v1 = *(unsigned __int16 *)(a1 + 2);
  if ( (_WORD)v1 )
    v3 = a1 + v1;
  else
    v3 = 0;
  v4 = *(_QWORD *)(a1 + 24);
  v5 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v4 + 1920));
  *(_DWORD *)(v4 + 2352) = (unsigned int)PsGetCurrentThreadId();
  v6 = *(unsigned __int16 *)(a1 + 2);
  if ( (_WORD)v6 )
  {
    v7 = a1 + v6 + 8;
    if ( !v7 )
      goto LABEL_45;
  }
  else
  {
    v7 = 8;
  }
  v8 = *(int **)v7;
  if ( !*(_QWORD *)v7 || (v9 = *(_QWORD **)(v7 + 8)) == 0 || *((_QWORD *)v8 + 1) != v7 || *v9 != v7 )
LABEL_45:
    __fastfail(3u);
  while ( 1 )
  {
    v10 = 0;
    if ( v8 == (int *)v7 )
      break;
    if ( !v8 )
      goto LABEL_45;
    if ( !*(_QWORD *)v8 )
      goto LABEL_45;
    v11 = (int **)*((_QWORD *)v8 + 1);
    if ( !v11 || *(int **)(*(_QWORD *)v8 + 8LL) != v8 || *v11 != v8 )
      goto LABEL_45;
    v10 = (ULONG_PTR)(v8 - 100);
    if ( *(v8 - 98) < 0 )
      KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)(v8 - 100), *(v8 - 98), 0);
    if ( *(_WORD *)v10 != 0xE2FF )
      break;
    v8 = *(int **)v8;
  }
  if ( v10 )
  {
    while ( 1 )
    {
      v12 = *(unsigned __int16 *)(a1 + 2);
      if ( (_WORD)v12 )
        v13 = a1 + v12;
      else
        v13 = 0;
      if ( *(int *)(v10 + 8) < 0 )
        KeBugCheckEx(0x27u, 0xA0001u, v10, *(int *)(v10 + 8), 0);
      v14 = (int **)(v10 + 400);
      if ( v10 == -400 )
        goto LABEL_45;
      v15 = *v14;
      if ( !*v14 )
        goto LABEL_45;
      v16 = *(int ****)(v10 + 408);
      if ( !v16 || *((int ***)v15 + 1) != v14 || *v16 != v14 )
        goto LABEL_45;
      v17 = (int *)(v13 + 8);
      while ( 1 )
      {
        v18 = 0;
        if ( v15 == v17 )
          break;
        if ( !v15 )
          goto LABEL_45;
        if ( !*(_QWORD *)v15 )
          goto LABEL_45;
        v22 = (int **)*((_QWORD *)v15 + 1);
        if ( !v22 || *(int **)(*(_QWORD *)v15 + 8LL) != v15 || *v22 != v15 )
          goto LABEL_45;
        v18 = v15 - 100;
        if ( *(v15 - 98) < 0 )
          KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)(v15 - 100), *(v15 - 98), 0);
        if ( *(_WORD *)v18 != 0xE2FF )
          break;
        v15 = *(int **)v15;
      }
      v19 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 2408LL) + 120LL);
      v20 = *(_DWORD *)(*(_QWORD *)(v10 + 392) + 472LL);
      if ( v20 > v19 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qDD(
            WPP_GLOBAL_Control->AttachedDevice,
            11,
            &WPP_2088f4a0286237c2def3368796e0c3b6_Traceguids,
            v10,
            v20,
            v19);
        }
        (*(void (__fastcall **)(__int64, ULONG_PTR, __int64))(*(_QWORD *)v3 + 16LL))(a1, v10, 3221225996LL);
      }
      if ( !v18 )
        break;
      v10 = (ULONG_PTR)v18;
    }
  }
  v21 = *(_QWORD *)(a1 + 24);
  *(_DWORD *)(v21 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v21 + 1920), v5);
}

```

## disassembly

```asm
0x14001ca80  push    rbx
0x14001ca82  push    rbp
0x14001ca83  push    rdi
0x14001ca84  push    r14
0x14001ca86  sub     rsp, 38h
0x14001ca8a  movzx   eax, word ptr [rcx+2]
0x14001ca8e  mov     rdi, rcx
0x14001ca91  test    ax, ax
0x14001ca94  jz      loc_14001CD18
0x14001ca9a  lea     r14, [rcx+rax]
0x14001ca9e  mov     rbx, [rcx+18h]
0x14001caa2  mov     [rsp+58h+arg_8], rsi
0x14001caa7  mov     [rsp+58h+arg_10], r12
0x14001caac  mov     [rsp+58h+var_28], r15
0x14001cab1  lea     rcx, [rbx+780h]; SpinLock
0x14001cab8  call    cs:__imp_ExAcquireSpinLockExclusive
0x14001cabf  nop     dword ptr [rax+rax+00h]
0x14001cac4  movzx   ebp, al
0x14001cac7  call    cs:__imp_PsGetCurrentThreadId
0x14001cace  nop     dword ptr [rax+rax+00h]
0x14001cad3  mov     [rbx+930h], eax
0x14001cad9  movzx   ecx, word ptr [rdi+2]
0x14001cadd  test    cx, cx
0x14001cae0  jz      loc_14001CD20
0x14001cae6  add     rcx, 8
0x14001caea  add     rcx, rdi
0x14001caed  jz      loc_14001CD31
0x14001caf3  mov     rax, [rcx]
0x14001caf6  test    rax, rax
0x14001caf9  jz      loc_14001CD31
0x14001caff  mov     rdx, [rcx+8]
0x14001cb03  test    rdx, rdx
0x14001cb06  jz      loc_14001CD31
0x14001cb0c  cmp     [rax+8], rcx
0x14001cb10  jnz     loc_14001CD31
0x14001cb16  cmp     [rdx], rcx
0x14001cb19  jnz     loc_14001CD31
0x14001cb1f  mov     r15d, 0E2FFh
0x14001cb25  xor     ebx, ebx
0x14001cb27  cmp     rax, rcx
0x14001cb2a  jz      short loc_14001CB7E
0x14001cb2c  test    rax, rax
0x14001cb2f  jz      loc_14001CD31
0x14001cb35  mov     rdx, [rax]
0x14001cb38  test    rdx, rdx
0x14001cb3b  jz      loc_14001CD31
0x14001cb41  mov     r8, [rax+8]
0x14001cb45  test    r8, r8
0x14001cb48  jz      loc_14001CD31
0x14001cb4e  cmp     [rdx+8], rax
0x14001cb52  jnz     loc_14001CD31
0x14001cb58  cmp     [r8], rax
0x14001cb5b  jnz     loc_14001CD31
0x14001cb61  lea     rbx, [rax-190h]
0x14001cb68  movsxd  rdx, dword ptr [rbx+8]
0x14001cb6c  test    edx, edx
0x14001cb6e  js      loc_14001CC64
0x14001cb74  cmp     [rbx], r15w
0x14001cb78  jz      loc_14001CD38
0x14001cb7e  test    rbx, rbx
0x14001cb81  jz      loc_14001CC25
0x14001cb87  lea     r12, WPP_GLOBAL_Control
0x14001cb8e  movzx   eax, word ptr [rdi+2]
0x14001cb92  test    ax, ax
0x14001cb95  jz      loc_14001CD2A
0x14001cb9b  lea     rdx, [rdi+rax]
0x14001cb9f  movsxd  rax, dword ptr [rbx+8]
0x14001cba3  test    eax, eax
0x14001cba5  js      loc_14001CC8A
0x14001cbab  lea     rax, [rbx+190h]
0x14001cbb2  test    rax, rax
0x14001cbb5  jz      loc_14001CD31
0x14001cbbb  mov     rcx, [rax]
0x14001cbbe  test    rcx, rcx
0x14001cbc1  jz      loc_14001CD31
0x14001cbc7  mov     r8, [rax+8]
0x14001cbcb  test    r8, r8
0x14001cbce  jz      loc_14001CD31
0x14001cbd4  cmp     [rcx+8], rax
0x14001cbd8  jnz     loc_14001CD31
0x14001cbde  cmp     [r8], rax
0x14001cbe1  jnz     loc_14001CD31
0x14001cbe7  add     rdx, 8
0x14001cbeb  xor     esi, esi
0x14001cbed  cmp     rcx, rdx
0x14001cbf0  jnz     loc_14001CCB0
0x14001cbf6  mov     rax, [rdi+18h]
0x14001cbfa  mov     rcx, [rax+968h]
0x14001cc01  mov     rax, [rbx+188h]
0x14001cc08  mov     r8d, [rcx+78h]
0x14001cc0c  mov     r9d, [rax+1D8h]
0x14001cc13  cmp     r9d, r8d
0x14001cc16  ja      loc_14001CD40
0x14001cc1c  test    rsi, rsi
0x14001cc1f  jnz     loc_14001CD8D
0x14001cc25  mov     rcx, [rdi+18h]
0x14001cc29  movzx   edx, bpl; OldIrql
0x14001cc2d  mov     dword ptr [rcx+930h], 0FFFFFFFFh
0x14001cc37  add     rcx, 780h; SpinLock
0x14001cc3e  call    cs:__imp_ExReleaseSpinLockExclusive
0x14001cc45  nop     dword ptr [rax+rax+00h]
0x14001cc4a  mov     r15, [rsp+58h+var_28]
0x14001cc4f  mov     r12, [rsp+58h+arg_10]
0x14001cc54  mov     rsi, [rsp+58h+arg_8]
0x14001cc59  add     rsp, 38h
0x14001cc5d  pop     r14
0x14001cc5f  pop     rdi
0x14001cc60  pop     rbp
0x14001cc61  pop     rbx
0x14001cc62  retn
0x14001cc64  mov     r9, rdx; BugCheckParameter3
0x14001cc67  mov     [rsp+58h+BugCheckParameter4], 0; BugCheckParameter4
0x14001cc70  mov     edx, 0A0001h; BugCheckParameter1
0x14001cc75  mov     r8, rbx; BugCheckParameter2
0x14001cc78  mov     ecx, 27h ; '''; BugCheckCode
0x14001cc7d  call    cs:__imp_KeBugCheckEx
0x14001cc8a  mov     r9, rax; BugCheckParameter3
0x14001cc8d  mov     [rsp+58h+BugCheckParameter4], 0; BugCheckParameter4
0x14001cc96  mov     r8, rbx; BugCheckParameter2
0x14001cc99  mov     edx, 0A0001h; BugCheckParameter1
0x14001cc9e  mov     ecx, 27h ; '''; BugCheckCode
0x14001cca3  call    cs:__imp_KeBugCheckEx
0x14001ccb0  test    rcx, rcx
0x14001ccb3  jz      short loc_14001CD31
0x14001ccb5  mov     rax, [rcx]
0x14001ccb8  test    rax, rax
0x14001ccbb  jz      short loc_14001CD31
0x14001ccbd  mov     r8, [rcx+8]
0x14001ccc1  test    r8, r8
0x14001ccc4  jz      short loc_14001CD31
0x14001ccc6  cmp     [rax+8], rcx
0x14001ccca  jnz     short loc_14001CD31
0x14001cccc  cmp     [r8], rcx
0x14001cccf  jnz     short loc_14001CD31
0x14001ccd1  lea     rsi, [rcx-190h]
0x14001ccd8  movsxd  rax, dword ptr [rsi+8]
0x14001ccdc  test    eax, eax
0x14001ccde  js      short loc_14001CCF2
0x14001cce0  cmp     [rsi], r15w
0x14001cce4  jnz     loc_14001CBF6
0x14001ccea  mov     rcx, [rcx]
0x14001cced  jmp     loc_14001CBEB
0x14001ccf2  mov     r9, rax; BugCheckParameter3
0x14001ccf5  mov     [rsp+58h+BugCheckParameter4], 0; BugCheckParameter4
0x14001ccfe  mov     r8, rsi; BugCheckParameter2
0x14001cd01  mov     edx, 0A0001h; BugCheckParameter1
0x14001cd06  mov     ecx, 27h ; '''; BugCheckCode
0x14001cd0b  call    cs:__imp_KeBugCheckEx
0x14001cd18  xor     r14d, r14d
0x14001cd1b  jmp     loc_14001CA9E
0x14001cd20  mov     ecx, 8
0x14001cd25  jmp     loc_14001CAF3
0x14001cd2a  xor     edx, edx
0x14001cd2c  jmp     loc_14001CB9F
0x14001cd31  mov     ecx, 3
0x14001cd36  int     29h; Win8: RtlFailFast(ecx)
0x14001cd38  mov     rax, [rax]
0x14001cd3b  jmp     loc_14001CB25
0x14001cd40  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd47  cmp     rcx, r12
0x14001cd4a  jz      loc_14005E524
0x14001cd50  mov     eax, [rcx+2Ch]
0x14001cd53  test    al, 1
0x14001cd55  jz      loc_14005E524
0x14001cd5b  cmp     byte ptr [rcx+29h], 1
0x14001cd5f  jb      loc_14005E524
0x14001cd65  mov     rcx, [rcx+18h]
0x14001cd69  mov     edx, 0Bh
0x14001cd6e  mov     [rsp+58h+var_30], r8d
0x14001cd73  lea     r8, WPP_2088f4a0286237c2def3368796e0c3b6_Traceguids
0x14001cd7a  mov     dword ptr [rsp+58h+BugCheckParameter4], r9d
0x14001cd7f  mov     r9, rbx
0x14001cd82  call    WPP_SF_qDD
0x14001cd87  nop
0x14001cd88  jmp     loc_14005E524
0x14001cd8d  mov     rbx, rsi
0x14001cd90  jmp     loc_14001CB8E
0x14005e524  mov     rax, [r14]
0x14005e527  mov     rdx, rbx
0x14005e52a  mov     dword ptr [rsp+58h+arg_0], 0C000020Ch
0x14005e532  mov     rcx, rdi
0x14005e535  mov     dword ptr [rsp+58h+arg_0+4], 0
0x14005e53d  mov     r8, [rsp+58h+arg_0]
0x14005e542  mov     rax, [rax+10h]
0x14005e546  call    _guard_dispatch_icall
0x14005e54b  nop
0x14005e54c  jmp     loc_14001CC1C
```
