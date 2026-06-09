# CompareSecurityContexts

- ea: `0x14000418c`
- end: `0x14000444b`
- name: `CompareSecurityContexts`
- size: `703`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003480`

## callees

- `0x140002390`
- `0x14000418c`
- `0x140009e00`
- `0x140046734`
- `0x140077fa0`

## import_xrefs

- `ntoskrnl!SeAccessCheckFromStateEx` at `0x140004365`
- `ntoskrnl!SeAccessCheckFromStateEx` at `0x140004365`
- `NDIS!NdisAcquireRWLockRead` at `0x140004244`
- `NDIS!NdisAcquireRWLockRead` at `0x140004244`
- `NDIS!NdisReleaseRWLock` at `0x1400042c3`
- `NDIS!NdisReleaseRWLock` at `0x14000443a`
- `NDIS!NdisReleaseRWLock` at `0x1400042c3`
- `NDIS!NdisReleaseRWLock` at `0x14000443a`

## string_xrefs

- `0x140004411`: `CompareSecurityContexts`

## pseudocode

```c
__int64 __fastcall CompareSecurityContexts(int *a1, __int64 a2)
{
  __int64 v2; // rax
  unsigned int *v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 v7; // r8
  unsigned __int64 v8; // rax
  int v9; // r9d
  char v10; // [rsp+50h] [rbp+7h] BYREF
  struct _LOCK_STATE_EX LockState[2]; // [rsp+51h] [rbp+8h] BYREF
  __int64 v12; // [rsp+58h] [rbp+Fh] BYREF
  __int128 v13; // [rsp+60h] [rbp+17h] BYREF
  int v14; // [rsp+70h] [rbp+27h]
  int v15; // [rsp+74h] [rbp+2Bh]
  __int64 v16; // [rsp+78h] [rbp+2Fh]
  __int64 v17; // [rsp+80h] [rbp+37h] BYREF
  _DWORD v18[4]; // [rsp+88h] [rbp+3Fh] BYREF

  v12 = 0;
  *(_WORD *)&LockState[1].OldIrql = 0;
  LockState[1].Flags = 0;
  v18[0] = 131073;
  v18[3] = 131073;
  v15 = 0;
  v18[1] = 0x20000;
  v18[2] = 0x20000;
  v14 = *a1;
  v2 = *((_QWORD *)a1 + 1);
  v3 = *(unsigned int **)(a2 + 8);
  v13 = 0;
  v16 = v2;
  v10 = 0;
  v4 = *((_QWORD *)v3 + 1);
  LockState[0].OldIrql = 0;
  LockState[0].LockState = 1;
  v17 = 0;
  if ( *(_DWORD *)(v4 - 224) != 1399155777 )
  {
    WfpReportSysErrorAsNtStatus(v3, "CompareSecurityContexts", 3221225485LL, 1);
    return 2;
  }
  *(_QWORD *)((char *)&v13 + 4) = *(_QWORD *)(v4 - 204);
  v5 = *v3;
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState[1], 1u);
  if ( FindCacheMatch((int)gWfpGlobal + 1120, 0, 0, (unsigned int)&v12, (__int64)&v17, (__int64)&v10) )
    goto LABEL_15;
  if ( v10 )
  {
    LODWORD(v13) = *(_DWORD *)(v17 + 72);
    BYTE4(v12) = *(_BYTE *)(v17 + 68);
    LODWORD(v12) = *(_DWORD *)(v17 + 64);
    _InterlockedIncrement64((volatile signed __int64 *)&gWfpGlobal[9].L.ListHead.Region);
    goto LABEL_5;
  }
  if ( (*(_DWORD *)(v4 - 196) & 4) != 0 )
  {
    v7 = 0;
    v8 = v4 + ((v5 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  else
  {
    v7 = v4 + ((v5 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
    v8 = *(_QWORD *)(v4 - 40) + ((*(unsigned int *)(*(_QWORD *)(v4 - 40) + 72LL) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL) + 224;
  }
  BYTE4(v12) = SeAccessCheckFromStateEx(v16, v8, v7, 1, 0, 0, v18, 1, &v13, &v12);
  _InterlockedIncrement64((volatile signed __int64 *)&gWfpGlobal[9].L.Depth);
  if ( ProcessCacheMiss(
         (int)gWfpGlobal + 1120,
         0,
         0,
         v9,
         0,
         (__int64)&v12,
         &LockState[1],
         (__int64)LockState,
         (__int64)&LockState[0].LockState) )
  {
LABEL_15:
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState[1]);
    return 2;
  }
  if ( LockState[0].OldIrql == 1 )
    _InterlockedIncrement64((volatile signed __int64 *)&gWfpGlobal[9].L.AllocateMisses);
LABEL_5:
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState[1]);
  if ( !BYTE4(v12) )
    return 2;
  return ~(2 * (_BYTE)v13) & 2;
}

```

## disassembly

```asm
0x14000418c  mov     [rsp-8+arg_10], rbx
0x140004191  mov     [rsp-8+arg_18], rdi
0x140004196  push    rbp
0x140004197  lea     rbp, [rsp-57h]
0x14000419c  sub     rsp, 0A0h
0x1400041a3  mov     rax, cs:__security_cookie
0x1400041aa  xor     rax, rsp
0x1400041ad  mov     [rbp+57h+var_8], rax
0x1400041b1  xor     eax, eax
0x1400041b3  mov     [rbp+57h+var_48], 0
0x1400041bb  mov     word ptr [rbp+57h+var_4F.OldIrql+3], ax
0x1400041bf  mov     r8d, 20001h
0x1400041c5  mov     [rbp+57h+var_4F.Flags+3], al
0x1400041c8  xorps   xmm0, xmm0
0x1400041cb  mov     [rbp+57h+var_18], r8d
0x1400041cf  mov     [rbp+57h+var_C], r8d
0x1400041d3  lea     eax, [r8-1]
0x1400041d7  mov     [rbp+57h+var_2C], 0
0x1400041de  mov     [rbp+57h+var_14], eax
0x1400041e1  mov     [rbp+57h+var_10], eax
0x1400041e4  mov     eax, [rcx]
0x1400041e6  mov     [rbp+57h+var_30], eax
0x1400041e9  mov     rax, [rcx+8]
0x1400041ed  mov     rcx, [rdx+8]
0x1400041f1  movdqu  [rbp+57h+var_40], xmm0
0x1400041f6  mov     [rbp+57h+var_28], rax
0x1400041fa  mov     [rbp+57h+var_50], 0
0x1400041fe  mov     rbx, [rcx+8]
0x140004202  mov     [rbp+57h+var_4F.OldIrql], 0
0x140004206  mov     [rbp+57h+var_4F.LockState], 1
0x14000420a  mov     [rbp+57h+var_20], 0
0x140004212  cmp     dword ptr [rbx-0E0h], 53656C41h
0x14000421c  jnz     loc_14000440B
0x140004222  mov     rax, [rbx-0CCh]
0x140004229  lea     rdx, [rbp+57h+var_4F.OldIrql+3]; LockState
0x14000422d  mov     qword ptr [rbp+57h+var_40+4], rax
0x140004231  mov     r8b, 1; Flags
0x140004234  mov     edi, [rcx]
0x140004236  mov     rcx, cs:gWfpGlobal
0x14000423d  mov     rcx, [rcx+6C0h]; Lock
0x140004244  call    cs:__imp_NdisAcquireRWLockRead
0x14000424b  nop     dword ptr [rax+rax+00h]
0x140004250  mov     rcx, cs:gWfpGlobal
0x140004257  lea     rax, [rbp+57h+var_50]
0x14000425b  mov     [rsp+0A0h+var_78], rax
0x140004260  lea     r9, [rbp+57h+var_48]
0x140004264  lea     rax, [rbp+57h+var_20]
0x140004268  add     rcx, 460h
0x14000426f  xor     r8d, r8d
0x140004272  mov     [rsp+0A0h+var_80], rax
0x140004277  xor     edx, edx
0x140004279  call    FindCacheMatch
0x14000427e  test    rax, rax
0x140004281  jnz     loc_140004428
0x140004287  cmp     [rbp+57h+var_50], al
0x14000428a  jz      short loc_140004308
0x14000428c  mov     rcx, [rbp+57h+var_20]
0x140004290  mov     eax, [rcx+48h]
0x140004293  mov     dword ptr [rbp+57h+var_40], eax
0x140004296  mov     al, [rcx+44h]
0x140004299  mov     byte ptr [rbp+57h+var_48+4], al
0x14000429c  mov     eax, [rcx+40h]
0x14000429f  mov     dword ptr [rbp+57h+var_48], eax
0x1400042a2  mov     rax, cs:gWfpGlobal
0x1400042a9  lock inc qword ptr [rax+488h]
0x1400042b1  mov     rcx, cs:gWfpGlobal
0x1400042b8  lea     rdx, [rbp+57h+var_4F.OldIrql+3]; LockState
0x1400042bc  mov     rcx, [rcx+6C0h]; Lock
0x1400042c3  call    cs:__imp_NdisReleaseRWLock
0x1400042ca  nop     dword ptr [rax+rax+00h]
0x1400042cf  cmp     byte ptr [rbp+57h+var_48+4], 0
0x1400042d3  jnz     short loc_1400042FC
0x1400042d5  mov     eax, 2
0x1400042da  mov     rcx, [rbp+57h+var_8]
0x1400042de  xor     rcx, rsp; StackCookie
0x1400042e1  call    __security_check_cookie
0x1400042e6  lea     r11, [rsp+0A0h+var_s0]
0x1400042ee  mov     rbx, [r11+20h]
0x1400042f2  mov     rdi, [r11+28h]
0x1400042f6  mov     rsp, r11
0x1400042f9  pop     rbp
0x1400042fa  retn
0x1400042fc  mov     eax, dword ptr [rbp+57h+var_40]
0x1400042ff  add     eax, eax
0x140004301  not     eax
0x140004303  and     eax, 2
0x140004306  jmp     short loc_1400042DA
0x140004308  mov     eax, [rbx-0C4h]
0x14000430e  lea     rdx, [rdi+7]
0x140004312  and     rdx, 0FFFFFFFFFFFFFFF8h
0x140004316  add     rdx, rbx
0x140004319  test    al, 4
0x14000431b  jz      loc_1400043EB
0x140004321  xor     r8d, r8d
0x140004324  mov     rax, rdx
0x140004327  lea     rcx, [rbp+57h+var_48]
0x14000432b  mov     r9d, 1
0x140004331  mov     [rsp+0A0h+var_58], rcx
0x140004336  mov     rdx, rax
0x140004339  lea     rcx, [rbp+57h+var_40]
0x14000433d  mov     [rsp+0A0h+var_60], rcx
0x140004342  lea     rcx, [rbp+57h+var_18]
0x140004346  mov     byte ptr [rsp+0A0h+var_68], 1
0x14000434b  mov     [rsp+0A0h+LockState], rcx
0x140004350  mov     rcx, [rbp+57h+var_28]
0x140004354  mov     [rsp+0A0h+var_78], 0
0x14000435d  mov     dword ptr [rsp+0A0h+var_80], 0
0x140004365  call    cs:__imp_SeAccessCheckFromStateEx
0x14000436c  nop     dword ptr [rax+rax+00h]
0x140004371  mov     byte ptr [rbp+57h+var_48+4], al
0x140004374  mov     rax, cs:gWfpGlobal
0x14000437b  lock inc qword ptr [rax+490h]
0x140004383  mov     rcx, cs:gWfpGlobal
0x14000438a  lea     rax, [rbp+57h+var_4F.LockState]
0x14000438e  mov     [rsp+0A0h+var_60], rax; __int64
0x140004393  add     rcx, 460h; int
0x14000439a  lea     rax, [rbp+57h+var_4F]
0x14000439e  xor     r8d, r8d; int
0x1400043a1  mov     [rsp+0A0h+var_68], rax; __int64
0x1400043a6  xor     edx, edx; int
0x1400043a8  lea     rax, [rbp+57h+var_4F.OldIrql+3]
0x1400043ac  mov     [rsp+0A0h+LockState], rax; LockState
0x1400043b1  lea     rax, [rbp+57h+var_48]
0x1400043b5  mov     [rsp+0A0h+var_78], rax; __int64
0x1400043ba  mov     [rsp+0A0h+var_80], 0; __int64
0x1400043c3  call    ProcessCacheMiss
0x1400043c8  test    rax, rax
0x1400043cb  jnz     short loc_140004428
0x1400043cd  cmp     [rbp+57h+var_4F.OldIrql], 1
0x1400043d1  jnz     loc_1400042B1
0x1400043d7  mov     rax, cs:gWfpGlobal
0x1400043de  lock inc qword ptr [rax+498h]
0x1400043e6  jmp     loc_1400042B1
0x1400043eb  mov     rcx, [rbx-28h]
0x1400043ef  mov     r8, rdx
0x1400043f2  mov     eax, [rcx+48h]
0x1400043f5  add     rax, 7
0x1400043f9  and     rax, 0FFFFFFFFFFFFFFF8h
0x1400043fd  add     rax, 0E0h
0x140004403  add     rax, rcx
0x140004406  jmp     loc_140004327
0x14000440b  mov     r9d, 1
0x140004411  lea     rdx, aComparesecurit; "CompareSecurityContexts"
0x140004418  mov     r8d, 0C000000Dh
0x14000441e  call    WfpReportSysErrorAsNtStatus
0x140004423  jmp     loc_1400042D5
0x140004428  mov     rcx, cs:gWfpGlobal
0x14000442f  lea     rdx, [rbp+57h+var_4F.OldIrql+3]; LockState
0x140004433  mov     rcx, [rcx+6C0h]; Lock
0x14000443a  call    cs:__imp_NdisReleaseRWLock
0x140004441  nop     dword ptr [rax+rax+00h]
0x140004446  jmp     loc_1400042D5
```
