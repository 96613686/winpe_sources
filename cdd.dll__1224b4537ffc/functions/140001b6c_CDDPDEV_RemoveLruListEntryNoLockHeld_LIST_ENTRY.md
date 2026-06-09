# CDDPDEV::RemoveLruListEntryNoLockHeld(_LIST_ENTRY *)

- ea: `0x140001b6c`
- end: `0x140001cad`
- name: `?RemoveLruListEntryNoLockHeld@CDDPDEV@@QEAAEPEAU_LIST_ENTRY@@@Z`
- size: `321`
- prototype: `unsigned __int8 __fastcall(CDDPDEV *__hidden this, struct _LIST_ENTRY *)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400015e0`
- `0x140001a5c`
- `0x140001b14`
- `0x140003840`
- `0x14002799c`
- `0x140030f74`
- `0x1400314a0`

## callees

- `0x140001b6c`
- `0x1400023c0`
- `0x140002420`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140001bc2`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140001c2d`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140001bc2`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140001c2d`
- `watchdog!WdLogSingleEntry0` at `0x140001bac`
- `watchdog!WdLogSingleEntry0` at `0x140001c16`
- `watchdog!WdLogSingleEntry0` at `0x140001bac`
- `watchdog!WdLogSingleEntry0` at `0x140001c16`

## pseudocode

```c
char __fastcall CDDPDEV::RemoveLruListEntryNoLockHeld(CDDPDEV *this, struct _LIST_ENTRY *a2)
{
  char v2; // si
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  _QWORD *v10; // rax
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *Blink; // rcx

  v2 = 0;
  if ( *((_BYTE *)this + 12716) )
  {
    if ( *(struct _KTHREAD **)(*((_QWORD *)this + 1600) + 8LL) == KeGetCurrentThread() )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 638;
      v7 = (_QWORD *)WdLogNewEntry5_WdAssertion(v6, v5);
      v7[3] = gCddImageInfo;
      v7[4] = (unsigned int)dword_14003E570;
      v7[5] = 215857758;
      WdLogGlobalForLineNumber = 638;
    }
    CDDPDEV::AcquireResidencyLock(this);
    if ( a2->Flink )
    {
      if ( !a2->Blink )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 644;
        v10 = (_QWORD *)WdLogNewEntry5_WdAssertion(v9, v8);
        v10[3] = gCddImageInfo;
        v10[4] = (unsigned int)dword_14003E570;
        v10[5] = 215857758;
        WdLogGlobalForLineNumber = 644;
      }
      Flink = a2->Flink;
      if ( a2->Flink->Blink != a2 || (Blink = a2->Blink, Blink->Flink != a2) )
        __fastfail(3u);
      Blink->Flink = Flink;
      v2 = 1;
      Flink->Blink = Blink;
      a2->Flink = 0;
      a2->Blink = 0;
    }
    CDDPDEV::ReleaseResidencyLock(this);
  }
  return v2;
}

```

## disassembly

```asm
0x140001b6c  mov     [rsp+arg_0], rbx
0x140001b71  mov     [rsp+arg_8], rsi
0x140001b76  push    rdi
0x140001b77  sub     rsp, 20h
0x140001b7b  xor     sil, sil
0x140001b7e  mov     rbx, rdx
0x140001b81  mov     rdi, rcx
0x140001b84  cmp     [rcx+31ACh], sil
0x140001b8b  jz      loc_140001C92
0x140001b91  mov     r8, gs:188h
0x140001b9a  mov     rax, [rcx+3200h]
0x140001ba1  cmp     [rax+8], r8
0x140001ba5  jnz     short loc_140001BF8
0x140001ba7  mov     ecx, 1
0x140001bac  call    cs:__imp_WdLogSingleEntry0
0x140001bb3  nop     dword ptr [rax+rax+00h]
0x140001bb8  mov     cs:WdLogGlobalForLineNumber, 27Eh
0x140001bc2  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140001bc9  nop     dword ptr [rax+rax+00h]
0x140001bce  mov     rcx, rax
0x140001bd1  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140001bd8  mov     [rcx+18h], rax
0x140001bdc  mov     eax, cs:dword_14003E570
0x140001be2  mov     [rcx+20h], rax
0x140001be6  mov     qword ptr [rcx+28h], 0CDDBA5Eh
0x140001bee  mov     cs:WdLogGlobalForLineNumber, 27Eh
0x140001bf8  mov     rcx, rdi; this
0x140001bfb  call    ?AcquireResidencyLock@CDDPDEV@@QEAAXXZ; CDDPDEV::AcquireResidencyLock(void)
0x140001c00  cmp     qword ptr [rbx], 0
0x140001c04  jz      loc_140001C8A
0x140001c0a  cmp     qword ptr [rbx+8], 0
0x140001c0f  jnz     short loc_140001C5F
0x140001c11  mov     ecx, 1
0x140001c16  call    cs:__imp_WdLogSingleEntry0
0x140001c1d  nop     dword ptr [rax+rax+00h]
0x140001c22  mov     esi, 284h
0x140001c27  mov     cs:WdLogGlobalForLineNumber, esi
0x140001c2d  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140001c34  nop     dword ptr [rax+rax+00h]
0x140001c39  mov     rcx, rax
0x140001c3c  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140001c43  mov     [rcx+18h], rax
0x140001c47  mov     eax, cs:dword_14003E570
0x140001c4d  mov     [rcx+20h], rax
0x140001c51  mov     qword ptr [rcx+28h], 0CDDBA5Eh
0x140001c59  mov     cs:WdLogGlobalForLineNumber, esi
0x140001c5f  mov     rax, [rbx]
0x140001c62  cmp     [rax+8], rbx
0x140001c66  jnz     short loc_140001CA6
0x140001c68  mov     rcx, [rbx+8]
0x140001c6c  cmp     [rcx], rbx
0x140001c6f  jnz     short loc_140001CA6
0x140001c71  mov     [rcx], rax
0x140001c74  mov     sil, 1
0x140001c77  mov     [rax+8], rcx
0x140001c7b  mov     qword ptr [rbx], 0
0x140001c82  mov     qword ptr [rbx+8], 0
0x140001c8a  mov     rcx, rdi; this
0x140001c8d  call    ?ReleaseResidencyLock@CDDPDEV@@QEAAXXZ; CDDPDEV::ReleaseResidencyLock(void)
0x140001c92  mov     rbx, [rsp+28h+arg_0]
0x140001c97  mov     al, sil
0x140001c9a  mov     rsi, [rsp+28h+arg_8]
0x140001c9f  add     rsp, 20h
0x140001ca3  pop     rdi
0x140001ca4  retn
0x140001ca6  mov     ecx, 3
0x140001cab  int     29h; Win8: RtlFailFast(ecx)
```
