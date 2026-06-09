# CClfsLogFcbCommon::CreateCcb(uchar,_FILE_OBJECT *,_FILE_OBJECT *,CClfsLogCcb * &)

- ea: `0x140007200`
- end: `0x14000728e`
- name: `?CreateCcb@CClfsLogFcbCommon@@QEAAJEPEAU_FILE_OBJECT@@0AEAPEAVCClfsLogCcb@@@Z`
- size: `142`
- prototype: `int(CClfsLogFcbCommon *__hidden this, unsigned __int8, struct _FILE_OBJECT *, struct _FILE_OBJECT *, struct CClfsLogCcb **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400011c0`
- `0x140007f2c`

## callees

- `0x140007180`
- `0x140007200`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x140007280`
- `ntoskrnl!ObfReferenceObject` at `0x140007280`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140007225`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140007225`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbCommon::CreateCcb(
        CClfsLogFcbCommon *this,
        char a2,
        struct _FILE_OBJECT *a3,
        struct _FILE_OBJECT *a4,
        struct CClfsLogCcb **a5)
{
  CClfsLogCcb *v8; // rax
  volatile signed __int32 *v9; // rax
  __int64 v10; // rbx

  *a5 = 0;
  v8 = (CClfsLogCcb *)ExAllocateFromNPagedLookasideList(&CClfsLogCcb::m_laList);
  if ( !v8 )
  {
    *a5 = 0;
    return 3221225626LL;
  }
  v9 = (volatile signed __int32 *)CClfsLogCcb::CClfsLogCcb(v8);
  *a5 = (struct CClfsLogCcb *)v9;
  if ( !v9 )
    return 3221225626LL;
  _InterlockedIncrement(v9 + 6);
  v10 = (__int64)*a5;
  *(_BYTE *)(v10 + 64) = a2;
  *(_QWORD *)(v10 + 72) = a3;
  if ( a4 )
  {
    *(_QWORD *)(v10 + 80) = a4;
    ObfReferenceObject(a4);
  }
  _InterlockedOr((volatile signed __int32 *)(v10 + 28), 1u);
  return 0;
}

```

## disassembly

```asm
0x140007200  push    rbx
0x140007202  push    rbp
0x140007203  push    rsi
0x140007204  push    rdi
0x140007205  sub     rsp, 28h
0x140007209  mov     rbx, [rsp+48h+arg_20]
0x14000720e  lea     rcx, ?m_laList@CClfsLogCcb@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140007215  mov     rdi, r9
0x140007218  mov     rsi, r8
0x14000721b  mov     bpl, dl
0x14000721e  mov     qword ptr [rbx], 0
0x140007225  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000722c  nop     dword ptr [rax+rax+00h]
0x140007231  test    rax, rax
0x140007234  jz      short loc_14000726B
0x140007236  mov     rcx, rax; this
0x140007239  call    ??0CClfsLogCcb@@QEAA@XZ; CClfsLogCcb::CClfsLogCcb(void)
0x14000723e  mov     [rbx], rax
0x140007241  test    rax, rax
0x140007244  jz      short loc_140007272
0x140007246  lock inc dword ptr [rax+18h]
0x14000724a  mov     rbx, [rbx]
0x14000724d  mov     [rbx+40h], bpl
0x140007251  mov     [rbx+48h], rsi
0x140007255  test    rdi, rdi
0x140007258  jnz     short loc_140007279
0x14000725a  lock or dword ptr [rbx+1Ch], 1
0x14000725f  xor     eax, eax
0x140007261  add     rsp, 28h
0x140007265  pop     rdi
0x140007266  pop     rsi
0x140007267  pop     rbp
0x140007268  pop     rbx
0x140007269  retn
0x14000726b  mov     qword ptr [rbx], 0
0x140007272  mov     eax, 0C000009Ah
0x140007277  jmp     short loc_140007261
0x140007279  mov     rcx, rdi; Object
0x14000727c  mov     [rbx+50h], rdi
0x140007280  call    cs:__imp_ObfReferenceObject
0x140007287  nop     dword ptr [rax+rax+00h]
0x14000728c  jmp     short loc_14000725A
```
