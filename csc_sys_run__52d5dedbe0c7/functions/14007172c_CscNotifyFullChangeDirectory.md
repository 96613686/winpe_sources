# CscNotifyFullChangeDirectory

- ea: `0x14007172c`
- end: `0x140071988`
- name: `CscNotifyFullChangeDirectory`
- size: `604`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14006e380`
- `0x140070c70`
- `0x1400837e0`

## callees

- `0x14000e100`
- `0x1400190ec`
- `0x140020abc`
- `0x140020b78`
- `0x14007172c`

## import_xrefs

- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1400718eb`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectory` at `0x1400718eb`
- `rdbss!RxAttachIrpToRxContext` at `0x14007191c`
- `rdbss!RxAttachIrpToRxContext` at `0x14007191c`
- `rdbss!RxDetachIrpFromRxContext` at `0x14007183c`
- `rdbss!RxDetachIrpFromRxContext` at `0x14007183c`
- `rdbss!RxFcbTableNameFromFcb` at `0x140071815`
- `rdbss!RxFcbTableNameFromFcb` at `0x140071815`

## pseudocode

```c
__int64 __fastcall CscNotifyFullChangeDirectory(__int64 a1, BOOLEAN a2, ULONG a3, char a4)
{
  __int64 v5; // rdi
  int v6; // esi
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // r9d
  char v11; // r10
  __int64 v12; // r11
  __int64 v13; // rcx
  __int64 v14; // rbp
  __int64 v15; // rbx
  char v16; // r13
  int v17; // ebx
  int v18; // ebp
  struct _STRING *v19; // r15
  __int64 v20; // rdi
  int v21; // edx
  IRP *NotifyIrp; // rax
  __int64 v24; // [rsp+60h] [rbp-68h] BYREF
  __int128 v25; // [rsp+70h] [rbp-58h]
  PVOID FsContext; // [rsp+D0h] [rbp+8h]

  v5 = *(_QWORD *)(a1 + 56);
  FsContext = *(PVOID *)(a1 + 64);
  v6 = a4 == 0 ? 0x103 : 0;
  v25 = 0;
  CscGetContexts((_QWORD *)a1, &v24);
  v14 = *(_QWORD *)(v13 + 264);
  v15 = *((_QWORD *)&v25 + 1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    LOBYTE(v8) = v11 != 0 ? 89 : 78;
    WPP_SF_qqcDD(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      v9,
      v5,
      v12,
      (_BYTE)v8,
      v10,
      *(_DWORD *)(*((_QWORD *)&v25 + 1) + 4LL));
  }
  if ( !v15 || (*(_DWORD *)(v15 + 4) & 0x80u) == 0 )
    return 3221225626LL;
  v16 = 0;
  if ( a4 )
  {
    v20 = 0;
    v19 = 0;
LABEL_13:
    v18 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      v21 = 0;
      if ( !a4 )
        v21 = v20;
      LOBYTE(v10) = a4 != 0 ? 89 : 78;
      WPP_SF_cZq(WPP_GLOBAL_Control->AttachedDevice, v21, v9, v10, (__int64)v19, v21);
    }
    NotifyIrp = 0;
    if ( !a4 )
      NotifyIrp = (IRP *)v20;
    FsRtlNotifyFilterChangeDirectory(
      *(PNOTIFY_SYNC *)(v15 + 32),
      (PLIST_ENTRY)(v15 + 16),
      FsContext,
      v19,
      a2,
      0,
      a3,
      NotifyIrp,
      0,
      0,
      0);
    if ( a4 )
    {
      v17 = v6;
    }
    else
    {
      v17 = *(_DWORD *)(a1 + 176);
      if ( v17 < 0 || (v17 = v6, v6 != 259) )
      {
        if ( v16 )
          RxAttachIrpToRxContext(a1, v20);
      }
    }
    goto LABEL_26;
  }
  if ( (*(_DWORD *)(v5 + 156) & 1) == 0 )
  {
    v19 = (struct _STRING *)RxFcbTableNameFromFcb(v5);
    if ( !v14 || (v20 = *(_QWORD *)(v14 + 24)) == 0 )
    {
      v20 = *(_QWORD *)(a1 + 40);
      RxDetachIrpFromRxContext(a1, v20);
      v16 = 1;
      _InterlockedExchange64((volatile __int64 *)(v20 + 104), 0);
    }
    goto LABEL_13;
  }
  v17 = -1073741738;
  v18 = 813;
LABEL_26:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      24,
      WPP_463ea68f65b43533505b8fb2e756adbc_Traceguids,
      (unsigned int)v17,
      v18);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14007172c  mov     [rsp+arg_18], rbx
0x140071731  mov     [rsp+arg_10], r8d
0x140071736  mov     [rsp+arg_8], dl
0x14007173a  push    rbp
0x14007173b  push    rsi
0x14007173c  push    rdi
0x14007173d  push    r12
0x14007173f  push    r13
0x140071741  push    r14
0x140071743  push    r15
0x140071745  sub     rsp, 90h
0x14007174c  mov     r11, [rcx+40h]
0x140071750  mov     r12b, r9b
0x140071753  mov     rdi, [rcx+38h]
0x140071757  mov     al, r12b
0x14007175a  neg     al
0x14007175c  mov     [rsp+0C8h+FsContext], r11
0x140071764  mov     r10b, dl
0x140071767  xorps   xmm0, xmm0
0x14007176a  sbb     esi, esi
0x14007176c  lea     rdx, [rsp+0C8h+var_68]
0x140071771  not     esi
0x140071773  mov     r9d, r8d
0x140071776  and     esi, 103h
0x14007177c  mov     r14, rcx
0x14007177f  movups  [rsp+0C8h+var_58], xmm0
0x140071784  call    CscGetContexts
0x140071789  mov     rbp, [rcx+108h]
0x140071790  mov     rcx, cs:WPP_GLOBAL_Control
0x140071797  lea     rax, WPP_GLOBAL_Control
0x14007179e  mov     rbx, qword ptr [rsp+0C8h+var_58+8]
0x1400717a3  cmp     rcx, rax
0x1400717a6  jz      short loc_1400717DD
0x1400717a8  mov     eax, [rcx+2Ch]
0x1400717ab  test    al, 20h
0x1400717ad  jz      short loc_1400717DD
0x1400717af  mov     rcx, [rcx+18h]
0x1400717b3  mov     al, r10b
0x1400717b6  neg     al
0x1400717b8  mov     eax, [rbx+4]
0x1400717bb  mov     dword ptr [rsp+0C8h+NotifyIrp], eax
0x1400717bf  sbb     dl, dl
0x1400717c1  mov     [rsp+0C8h+CompletionFilter], r9d
0x1400717c6  and     dl, 0Bh
0x1400717c9  add     dl, 4Eh ; 'N'
0x1400717cc  mov     r9, rdi
0x1400717cf  mov     [rsp+0C8h+IgnoreBuffer], dl
0x1400717d3  mov     qword ptr [rsp+0C8h+WatchTree], r11
0x1400717d8  call    WPP_SF_qqcDD
0x1400717dd  test    rbx, rbx
0x1400717e0  jz      loc_140071967
0x1400717e6  mov     eax, [rbx+4]
0x1400717e9  test    al, al
0x1400717eb  jns     loc_140071967
0x1400717f1  xor     r13b, r13b
0x1400717f4  test    r12b, r12b
0x1400717f7  jnz     short loc_140071853
0x1400717f9  mov     eax, [rdi+9Ch]
0x1400717ff  test    al, 1
0x140071801  jz      short loc_140071812
0x140071803  mov     ebx, 0C0000056h
0x140071808  mov     ebp, 32Dh
0x14007180d  jmp     loc_14007192C
0x140071812  mov     rcx, rdi
0x140071815  call    cs:__imp_RxFcbTableNameFromFcb
0x14007181c  nop     dword ptr [rax+rax+00h]
0x140071821  mov     r15, rax
0x140071824  test    rbp, rbp
0x140071827  jz      short loc_140071832
0x140071829  mov     rdi, [rbp+18h]
0x14007182d  test    rdi, rdi
0x140071830  jnz     short loc_140071858
0x140071832  mov     rdi, [r14+28h]
0x140071836  mov     rcx, r14
0x140071839  mov     rdx, rdi
0x14007183c  call    cs:__imp_RxDetachIrpFromRxContext
0x140071843  nop     dword ptr [rax+rax+00h]
0x140071848  xor     eax, eax
0x14007184a  mov     r13b, 1
0x14007184d  xchg    rax, [rdi+68h]
0x140071851  jmp     short loc_140071858
0x140071853  xor     edi, edi
0x140071855  xor     r15d, r15d
0x140071858  mov     rcx, cs:WPP_GLOBAL_Control
0x14007185f  lea     rax, WPP_GLOBAL_Control
0x140071866  xor     ebp, ebp
0x140071868  cmp     rcx, rax
0x14007186b  jz      short loc_1400718A0
0x14007186d  mov     eax, [rcx+2Ch]
0x140071870  test    al, 40h
0x140071872  jz      short loc_1400718A0
0x140071874  mov     rcx, [rcx+18h]
0x140071878  xor     edx, edx
0x14007187a  test    r12b, r12b
0x14007187d  mov     al, r12b
0x140071880  cmovz   rdx, rdi
0x140071884  neg     al
0x140071886  mov     qword ptr [rsp+0C8h+IgnoreBuffer], rdx
0x14007188b  sbb     r9b, r9b
0x14007188e  mov     qword ptr [rsp+0C8h+WatchTree], r15
0x140071893  and     r9b, 0Bh
0x140071897  add     r9b, 4Eh ; 'N'
0x14007189b  call    WPP_SF_cZq
0x1400718a0  mov     r8, [rsp+0C8h+FsContext]; FsContext
0x1400718a8  lea     rdx, [rbx+10h]; NotifyList
0x1400718ac  mov     rcx, [rbx+20h]; NotifySync
0x1400718b0  xor     eax, eax
0x1400718b2  mov     [rsp+0C8h+FilterCallback], rbp; FilterCallback
0x1400718b7  test    r12b, r12b
0x1400718ba  mov     [rsp+0C8h+SubjectContext], rbp; SubjectContext
0x1400718bf  mov     r9, r15; FullDirectoryName
0x1400718c2  cmovz   rax, rdi
0x1400718c6  mov     [rsp+0C8h+TraverseCallback], rbp; TraverseCallback
0x1400718cb  mov     [rsp+0C8h+NotifyIrp], rax; NotifyIrp
0x1400718d0  mov     eax, [rsp+0C8h+arg_10]
0x1400718d7  mov     [rsp+0C8h+CompletionFilter], eax; CompletionFilter
0x1400718db  mov     al, [rsp+0C8h+arg_8]
0x1400718e2  mov     [rsp+0C8h+IgnoreBuffer], bpl; IgnoreBuffer
0x1400718e7  mov     [rsp+0C8h+WatchTree], al; WatchTree
0x1400718eb  call    cs:__imp_FsRtlNotifyFilterChangeDirectory
0x1400718f2  nop     dword ptr [rax+rax+00h]
0x1400718f7  test    r12b, r12b
0x1400718fa  jnz     short loc_14007192A
0x1400718fc  mov     ebx, [r14+0B0h]
0x140071903  test    ebx, ebx
0x140071905  js      short loc_140071911
0x140071907  mov     ebx, esi
0x140071909  cmp     esi, 103h
0x14007190f  jz      short loc_14007192C
0x140071911  test    r13b, r13b
0x140071914  jz      short loc_14007192C
0x140071916  mov     rdx, rdi
0x140071919  mov     rcx, r14
0x14007191c  call    cs:__imp_RxAttachIrpToRxContext
0x140071923  nop     dword ptr [rax+rax+00h]
0x140071928  jmp     short loc_14007192C
0x14007192a  mov     ebx, esi
0x14007192c  mov     rcx, cs:WPP_GLOBAL_Control
0x140071933  lea     rax, WPP_GLOBAL_Control
0x14007193a  cmp     rcx, rax
0x14007193d  jz      short loc_140071963
0x14007193f  mov     edx, [rcx+2Ch]
0x140071942  test    dl, 20h
0x140071945  jz      short loc_140071963
0x140071947  mov     rcx, [rcx+18h]
0x14007194b  lea     r8, WPP_463ea68f65b43533505b8fb2e756adbc_Traceguids
0x140071952  mov     edx, 18h
0x140071957  mov     dword ptr [rsp+0C8h+WatchTree], ebp
0x14007195b  mov     r9d, ebx
0x14007195e  call    WPP_SF_Dd
0x140071963  mov     eax, ebx
0x140071965  jmp     short loc_14007196C
0x140071967  mov     eax, 0C000009Ah
0x14007196c  mov     rbx, [rsp+0C8h+arg_18]
0x140071974  add     rsp, 90h
0x14007197b  pop     r15
0x14007197d  pop     r14
0x14007197f  pop     r13
0x140071981  pop     r12
0x140071983  pop     rdi
0x140071984  pop     rsi
0x140071985  pop     rbp
0x140071986  retn
```
