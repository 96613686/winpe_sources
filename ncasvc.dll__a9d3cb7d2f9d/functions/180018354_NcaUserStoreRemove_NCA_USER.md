# NcaUserStoreRemove(NCA_USER_ *)

- ea: `0x180018354`
- end: `0x1800184cb`
- name: `?NcaUserStoreRemove@@YAXPEAUNCA_USER_@@@Z`
- size: `375`
- prototype: `void __fastcall(struct NCA_USER_ ***lpMem)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180007738`
- `0x180017708`

## callees

- `0x1800043bc`
- `0x180004f04`
- `0x180004f34`
- `0x1800175c8`
- `0x180018354`
- `0x1800184d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001847b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001847b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018396`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018396`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800183bb`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800183bb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180018463`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180018463`

## pseudocode

```c
void __fastcall NcaUserStoreRemove(struct NCA_USER_ ***lpMem)
{
  DWORD v2; // eax
  struct _tag_NCA_CANCELABLE_LOCK *v3; // rcx
  struct NCA_USER_ **v4; // rax
  struct NCA_USER_ **v5; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_f6fba97516d23319eaec26e747470e80_Traceguids);
  EnterCriticalSection(&gNcaUserStore);
  _InterlockedIncrement(&dword_180028AE8);
  v2 = WaitForMultipleObjects(2u, &gNcaMain, 0, 0xFFFFFFFF);
  if ( !v2 )
  {
    NcaReleaseCancelableLock(v3);
LABEL_7:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_f6fba97516d23319eaec26e747470e80_Traceguids, 1115);
    goto LABEL_18;
  }
  if ( v2 != 1 )
    goto LABEL_7;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpMem + 18, 0xFFFFFFFF) == 1 )
  {
    v4 = *lpMem;
    if ( (*lpMem)[1] != (struct NCA_USER_ *)lpMem || (v5 = lpMem[1], *v5 != (struct NCA_USER_ *)lpMem) )
      __fastfail(3u);
    *v5 = (struct NCA_USER_ *)v4;
    v4[1] = (struct NCA_USER_ *)v5;
    if ( *((_DWORD *)lpMem + 13) == 1 )
      qword_180029588 = 0;
    if ( (unsigned int)NcaUserStoreTransferOwnership((struct NCA_USER_ *)lpMem) )
    {
      ++dword_180029584;
      SubmitThreadpoolWork((PTP_WORK)lpMem[5]);
    }
    else
    {
      NcaUserStoreClose((struct NCA_USER_ *)lpMem);
    }
  }
  NcaReleaseCancelableLock(v3);
LABEL_18:
  LeaveCriticalSection(&gNcaUserStore);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_f6fba97516d23319eaec26e747470e80_Traceguids);
}

```

## disassembly

```asm
0x180018354  mov     [rsp+arg_0], rbx
0x180018359  push    rdi
0x18001835a  sub     rsp, 20h
0x18001835e  mov     rbx, rcx
0x180018361  mov     rcx, cs:WPP_GLOBAL_Control
0x180018368  lea     rdi, WPP_GLOBAL_Control
0x18001836f  cmp     rcx, rdi
0x180018372  jz      short loc_18001838F
0x180018374  test    byte ptr [rcx+1Ch], 8
0x180018378  jz      short loc_18001838F
0x18001837a  mov     rcx, [rcx+10h]
0x18001837e  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x180018385  mov     edx, 1Eh
0x18001838a  call    WPP_SF_
0x18001838f  lea     rcx, ?gNcaUserStore@@3UNCA_USER_STORE_COMPONENT_@@A; lpCriticalSection
0x180018396  call    cs:__imp_EnterCriticalSection
0x18001839d  nop     dword ptr [rax+rax+00h]
0x1800183a2  lock inc cs:dword_180028AE8
0x1800183a9  xor     r8d, r8d; bWaitAll
0x1800183ac  lea     rdx, ?gNcaMain@@3UNCA_MAIN_COMPONENT_@@A; lpHandles
0x1800183b3  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800183b7  lea     ecx, [r8+2]; nCount
0x1800183bb  call    cs:__imp_WaitForMultipleObjects
0x1800183c2  nop     dword ptr [rax+rax+00h]
0x1800183c7  test    eax, eax
0x1800183c9  jnz     short loc_1800183D2
0x1800183cb  call    ?NcaReleaseCancelableLock@@YAXPEAU_tag_NCA_CANCELABLE_LOCK@@@Z; NcaReleaseCancelableLock(_tag_NCA_CANCELABLE_LOCK *)
0x1800183d0  jmp     short loc_1800183D7
0x1800183d2  cmp     eax, 1
0x1800183d5  jz      short loc_18001840E
0x1800183d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183de  cmp     rcx, rdi
0x1800183e1  jz      loc_180018474
0x1800183e7  test    byte ptr [rcx+1Ch], 1
0x1800183eb  jz      loc_180018474
0x1800183f1  mov     rcx, [rcx+10h]
0x1800183f5  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x1800183fc  mov     edx, 1Fh
0x180018401  mov     r9d, 45Bh
0x180018407  call    WPP_SF_d
0x18001840c  jmp     short loc_180018474
0x18001840e  or      eax, 0FFFFFFFFh
0x180018411  lock xadd [rbx+48h], eax
0x180018416  cmp     eax, 1
0x180018419  jnz     short loc_18001846F
0x18001841b  mov     rax, [rbx]
0x18001841e  cmp     [rax+8], rbx
0x180018422  jnz     loc_1800184C4
0x180018428  mov     rcx, [rbx+8]
0x18001842c  cmp     [rcx], rbx
0x18001842f  jnz     loc_1800184C4
0x180018435  mov     [rcx], rax
0x180018438  mov     [rax+8], rcx
0x18001843c  cmp     dword ptr [rbx+34h], 1
0x180018440  jnz     short loc_18001844D
0x180018442  mov     cs:qword_180029588, 0
0x18001844d  mov     rcx, rbx; struct NCA_USER_ *
0x180018450  call    ?NcaUserStoreTransferOwnership@@YAHPEAUNCA_USER_@@@Z; NcaUserStoreTransferOwnership(NCA_USER_ *)
0x180018455  test    eax, eax
0x180018457  jz      short loc_1800184BA
0x180018459  inc     cs:dword_180029584
0x18001845f  mov     rcx, [rbx+28h]; pwk
0x180018463  call    cs:__imp_SubmitThreadpoolWork
0x18001846a  nop     dword ptr [rax+rax+00h]
0x18001846f  call    ?NcaReleaseCancelableLock@@YAXPEAU_tag_NCA_CANCELABLE_LOCK@@@Z; NcaReleaseCancelableLock(_tag_NCA_CANCELABLE_LOCK *)
0x180018474  lea     rcx, ?gNcaUserStore@@3UNCA_USER_STORE_COMPONENT_@@A; lpCriticalSection
0x18001847b  call    cs:__imp_LeaveCriticalSection
0x180018482  nop     dword ptr [rax+rax+00h]
0x180018487  mov     rcx, cs:WPP_GLOBAL_Control
0x18001848e  cmp     rcx, rdi
0x180018491  jz      short loc_1800184AE
0x180018493  test    byte ptr [rcx+1Ch], 8
0x180018497  jz      short loc_1800184AE
0x180018499  mov     rcx, [rcx+10h]
0x18001849d  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x1800184a4  mov     edx, 20h ; ' '
0x1800184a9  call    WPP_SF_
0x1800184ae  mov     rbx, [rsp+28h+arg_0]
0x1800184b3  add     rsp, 20h
0x1800184b7  pop     rdi
0x1800184b8  retn
0x1800184ba  mov     rcx, rbx; lpMem
0x1800184bd  call    ?NcaUserStoreClose@@YAXPEAUNCA_USER_@@@Z; NcaUserStoreClose(NCA_USER_ *)
0x1800184c2  jmp     short loc_18001846F
0x1800184c4  mov     ecx, 3
0x1800184c9  int     29h; Win8: RtlFailFast(ecx)
```
