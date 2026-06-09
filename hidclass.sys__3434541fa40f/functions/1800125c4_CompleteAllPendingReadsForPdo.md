# CompleteAllPendingReadsForPdo

- ea: `0x1800125c4`
- end: `0x1800127c9`
- name: `CompleteAllPendingReadsForPdo`
- size: `517`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a1cc`
- `0x18003e5b0`

## callees

- `0x18000ebb0`
- `0x1800125c4`
- `0x1800127d0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180012795`
- `ntoskrnl!IofCompleteRequest` at `0x180012795`
- `ntoskrnl!KeReleaseSpinLock` at `0x180012688`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800126a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x180012688`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800126a5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180012611`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180012630`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180012611`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180012630`

## pseudocode

```c
__int64 __fastcall CompleteAllPendingReadsForPdo(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v3; // rdi
  __int64 v4; // rdi
  KIRQL v5; // al
  _QWORD *v6; // rbx
  KIRQL v7; // r10
  _QWORD *v8; // rdx
  _QWORD *v9; // rax
  __int64 Irp; // rax
  int v11; // r8d
  __int64 result; // rax
  __int64 v13; // rcx
  __int128 *v14; // rdx
  IRP *v15; // rbx
  __int64 v16; // [rsp+60h] [rbp-20h]
  __int128 v17; // [rsp+70h] [rbp-10h] BYREF
  KIRQL v18; // [rsp+C0h] [rbp+40h]

  v1 = *(_QWORD *)(a1 + 64);
  v3 = 424LL * *(unsigned int *)(a1 + 12);
  v17 = 0;
  v4 = *(_QWORD *)(v1 + 184) + v3;
  *((_QWORD *)&v17 + 1) = &v17;
  *(_QWORD *)&v17 = &v17;
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 40));
  v18 = v5;
  v6 = *(_QWORD **)(v4 + 24);
  if ( v6 != (_QWORD *)(v4 + 24) )
  {
    do
    {
      v7 = KeAcquireSpinLockRaiseToDpc(v6 + 2);
      if ( *(v6 - 5) == a1 )
      {
        while ( 1 )
        {
          Irp = DequeueInterruptReadIrp(v4, v6 - 7);
          if ( !Irp )
            break;
          v8 = (_QWORD *)*((_QWORD *)&v17 + 1);
          if ( **((__int128 ***)&v17 + 1) != &v17 )
LABEL_22:
            __fastfail(3u);
          v9 = (_QWORD *)(Irp + 168);
          *v9 = &v17;
          v9[1] = v8;
          *v8 = v9;
          *((_QWORD *)&v17 + 1) = v9;
        }
      }
      KeReleaseSpinLock(v6 + 2, v7);
      v6 = (_QWORD *)*v6;
    }
    while ( v6 != (_QWORD *)(v4 + 24) );
    v5 = v18;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 40), v5);
  while ( 1 )
  {
    result = v17;
    if ( (__int128 *)v17 == &v17 )
      return result;
    if ( *(__int128 **)(v17 + 8) != &v17 )
      goto LABEL_22;
    v13 = *(_QWORD *)v17;
    if ( *(_QWORD *)(*(_QWORD *)v17 + 8LL) != (_QWORD)v17 )
      goto LABEL_22;
    *(_QWORD *)&v17 = *(_QWORD *)v17;
    v14 = &v17;
    v15 = (IRP *)(result - 168);
    *(_QWORD *)(v13 + 8) = &v17;
    *(_DWORD *)(result - 168 + 48) = -1073741667;
    LOBYTE(v14) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v16) = -1073741667;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v14,
        v11,
        *(_QWORD *)(v1 + 704),
        4,
        5,
        12,
        (__int64)WPP_d3422704dcd235ea7c23ca0d62a7cccc_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a1 + 64) + 32LL),
        *(_DWORD *)(a1 + 8),
        *(_QWORD *)(a1 + 48),
        result + 88,
        v16);
    }
    IofCompleteRequest(v15, 0);
  }
}

```

## disassembly

```asm
0x1800125c4  mov     [rsp-38h+arg_10], rbx
0x1800125c9  push    rbp
0x1800125ca  push    rsi
0x1800125cb  push    rdi
0x1800125cc  push    r12
0x1800125ce  push    r13
0x1800125d0  push    r14
0x1800125d2  push    r15
0x1800125d4  mov     rbp, rsp
0x1800125d7  sub     rsp, 80h
0x1800125de  mov     eax, [rcx+0Ch]
0x1800125e1  xorps   xmm0, xmm0
0x1800125e4  mov     rsi, [rcx+40h]
0x1800125e8  mov     r13, rcx
0x1800125eb  imul    rdi, rax, 1A8h
0x1800125f2  movups  [rbp+var_10], xmm0
0x1800125f6  lea     rax, [rbp+var_10]
0x1800125fa  add     rdi, [rsi+0B8h]
0x180012601  mov     qword ptr [rbp+var_10+8], rax
0x180012605  lea     rax, [rbp+var_10]
0x180012609  mov     qword ptr [rbp+var_10], rax
0x18001260d  lea     rcx, [rdi+28h]; SpinLock
0x180012611  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180012618  nop     dword ptr [rax+rax+00h]
0x18001261d  lea     r15, [rdi+18h]
0x180012621  mov     [rbp+arg_0], al
0x180012624  mov     rbx, [r15]
0x180012627  cmp     rbx, r15
0x18001262a  jz      short loc_18001269F
0x18001262c  lea     rcx, [rbx+10h]; SpinLock
0x180012630  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180012637  nop     dword ptr [rax+rax+00h]
0x18001263c  mov     r10b, al
0x18001263f  cmp     [rbx-28h], r13
0x180012643  jz      short loc_180012670
0x180012645  jmp     short loc_180012681
0x180012647  mov     rdx, qword ptr [rbp+var_10+8]
0x18001264b  lea     rcx, [rbp+var_10]
0x18001264f  cmp     [rdx], rcx
0x180012652  jnz     loc_1800127A6
0x180012658  add     rax, 0A8h
0x18001265e  lea     rcx, [rbp+var_10]
0x180012662  mov     [rax], rcx
0x180012665  mov     [rax+8], rdx
0x180012669  mov     [rdx], rax
0x18001266c  mov     qword ptr [rbp+var_10+8], rax
0x180012670  lea     rdx, [rbx-38h]
0x180012674  mov     rcx, rdi
0x180012677  call    DequeueInterruptReadIrp
0x18001267c  test    rax, rax
0x18001267f  jnz     short loc_180012647
0x180012681  mov     dl, r10b; NewIrql
0x180012684  lea     rcx, [rbx+10h]; SpinLock
0x180012688  call    cs:__imp_KeReleaseSpinLock
0x18001268f  nop     dword ptr [rax+rax+00h]
0x180012694  mov     rbx, [rbx]
0x180012697  cmp     rbx, r15
0x18001269a  jnz     short loc_18001262C
0x18001269c  mov     al, [rbp+arg_0]
0x18001269f  mov     dl, al; NewIrql
0x1800126a1  lea     rcx, [rdi+28h]; SpinLock
0x1800126a5  call    cs:__imp_KeReleaseSpinLock
0x1800126ac  nop     dword ptr [rax+rax+00h]
0x1800126b1  mov     edi, 0C000009Dh
0x1800126b6  mov     rax, qword ptr [rbp+var_10]
0x1800126ba  lea     rcx, [rbp+var_10]
0x1800126be  cmp     rax, rcx
0x1800126c1  jz      loc_1800127AD
0x1800126c7  lea     rcx, [rbp+var_10]
0x1800126cb  cmp     [rax+8], rcx
0x1800126cf  jnz     loc_1800127A6
0x1800126d5  mov     rcx, [rax]
0x1800126d8  cmp     [rcx+8], rax
0x1800126dc  jnz     loc_1800127A6
0x1800126e2  mov     qword ptr [rbp+var_10], rcx
0x1800126e6  lea     rdx, [rbp+var_10]
0x1800126ea  lea     rbx, [rax-0A8h]
0x1800126f1  mov     [rcx+8], rdx
0x1800126f5  mov     [rbx+30h], edi
0x1800126f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126ff  lea     rax, WPP_GLOBAL_Control
0x180012706  cmp     rcx, rax
0x180012709  jz      short loc_18001271C
0x18001270b  mov     eax, [rcx+2Ch]
0x18001270e  test    al, 10h
0x180012710  jz      short loc_18001271C
0x180012712  cmp     byte ptr [rcx+29h], 4
0x180012716  jb      short loc_18001271C
0x180012718  mov     dl, 1
0x18001271a  jmp     short loc_18001271E
0x18001271c  xor     dl, dl
0x18001271e  lea     rax, WPP_RECORDER_INITIALIZED
0x180012725  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001272c  setnz   r8b
0x180012730  test    dl, dl
0x180012732  jnz     short loc_180012739
0x180012734  test    r8b, r8b
0x180012737  jz      short loc_180012790
0x180012739  mov     rax, [r13+30h]
0x18001273d  mov     r9, [r13+40h]
0x180012741  mov     rcx, [rcx+18h]
0x180012745  mov     [rsp+80h+var_20], edi
0x180012749  mov     [rsp+80h+var_28], rbx
0x18001274e  mov     [rsp+80h+var_30], rax
0x180012753  mov     eax, [r13+8]
0x180012757  mov     [rsp+80h+var_38], eax
0x18001275b  mov     rax, [r9+20h]
0x18001275f  mov     r9, [rsi+2C0h]
0x180012766  mov     [rsp+80h+var_40], rax
0x18001276b  lea     rax, WPP_d3422704dcd235ea7c23ca0d62a7cccc_Traceguids
0x180012772  mov     [rsp+80h+var_48], rax
0x180012777  mov     [rsp+80h+var_50], 0Ch
0x18001277e  mov     [rsp+80h+var_58], 5
0x180012786  mov     [rsp+80h+var_60], 4
0x18001278b  call    WPP_RECORDER_AND_TRACE_SF_qdqqd
0x180012790  xor     edx, edx; PriorityBoost
0x180012792  mov     rcx, rbx; Irp
0x180012795  call    cs:__imp_IofCompleteRequest
0x18001279c  nop     dword ptr [rax+rax+00h]
0x1800127a1  jmp     loc_1800126B6
0x1800127a6  mov     ecx, 3
0x1800127ab  int     29h; Win8: RtlFailFast(ecx)
0x1800127ad  mov     rbx, [rsp+80h+arg_10]
0x1800127b5  add     rsp, 80h
0x1800127bc  pop     r15
0x1800127be  pop     r14
0x1800127c0  pop     r13
0x1800127c2  pop     r12
0x1800127c4  pop     rdi
0x1800127c5  pop     rsi
0x1800127c6  pop     rbp
0x1800127c7  retn
```
