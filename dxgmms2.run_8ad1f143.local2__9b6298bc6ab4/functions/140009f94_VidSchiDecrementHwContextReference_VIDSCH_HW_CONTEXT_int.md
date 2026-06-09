# VidSchiDecrementHwContextReference(VIDSCH_HW_CONTEXT *,int)

- ea: `0x140009f94`
- end: `0x14000a1a5`
- name: `?VidSchiDecrementHwContextReference@@YAXPEAUVIDSCH_HW_CONTEXT@@H@Z`
- size: `529`
- prototype: `void __fastcall(PVOID P, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140009790`
- `0x1400099e4`
- `0x140054dec`

## callees

- `0x140009f94`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009fce`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009fce`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009ff0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009ff0`
- `ntoskrnl!RtlAvlRemoveNode` at `0x14000a091`
- `ntoskrnl!RtlAvlRemoveNode` at `0x14000a0ab`
- `ntoskrnl!RtlAvlRemoveNode` at `0x14000a091`
- `ntoskrnl!RtlAvlRemoveNode` at `0x14000a0ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a0f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a171`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a194`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a0f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a171`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a194`
- `watchdog!WdLogSingleEntry5` at `0x14000a135`
- `watchdog!WdLogSingleEntry5` at `0x14000a135`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14000a104`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VidSchiDecrementHwContextReference(char *P, int a2)
{
  __int64 v2; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx
  char **v7; // rdx
  __int64 v8; // rdx
  char **v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rdx
  _QWORD *v12; // r8
  void *v13; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-38h] BYREF
  __int128 v15; // [rsp+48h] [rbp-20h]
  __int64 v16; // [rsp+58h] [rbp-10h]

  v2 = *((_QWORD *)P + 2);
  v5 = *(_QWORD *)(v2 + 24);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !a2 )
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 2096), &LockHandle);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 10, 0xFFFFFFFF) == 1 )
  {
    if ( *((char **)P + 37) != P + 296 || *((_DWORD *)P + 79) )
    {
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 281, 12288);
      WdLogGlobalForLineNumber = 921;
    }
    else
    {
      v6 = *((_QWORD *)P + 33);
      if ( *(char **)(v6 + 8) == P + 264 )
      {
        v7 = (char **)*((_QWORD *)P + 34);
        if ( *v7 == P + 264 )
        {
          *v7 = (char *)v6;
          *(_QWORD *)(v6 + 8) = v7;
          v8 = *((_QWORD *)P + 35);
          if ( *(char **)(v8 + 8) == P + 280 )
          {
            v9 = (char **)*((_QWORD *)P + 36);
            if ( *v9 == P + 280 )
            {
              *v9 = (char *)v8;
              *(_QWORD *)(v8 + 8) = v9;
              if ( P[151] )
              {
                RtlAvlRemoveNode(v2 + 1760, P + 160);
                RtlAvlRemoveNode(v2 + 1768, P + 184);
                P[151] = 0;
              }
              v10 = *((_QWORD *)P + 1);
              v16 = 0;
              v15 = 0;
              if ( _InterlockedExchangeAdd64((volatile signed __int64 *)(v10 + 32), 0xFFFFFFFFFFFFFFFFuLL) != 1 )
                goto LABEL_16;
              v11 = *(_QWORD *)(v10 + 112);
              if ( *(_QWORD *)(v11 + 8) == v10 + 112 )
              {
                v12 = *(_QWORD **)(v10 + 120);
                if ( *v12 == v10 + 112 )
                {
                  *v12 = v11;
                  *(_QWORD *)(v11 + 8) = v12;
                  ExFreePoolWithTag((PVOID)v10, 0);
LABEL_16:
                  if ( P[150] )
                  {
                    v13 = (void *)*((_QWORD *)P + 4);
                    if ( v13 )
                      ExFreePoolWithTag(v13, 0x4B677844u);
                  }
                  ExFreePoolWithTag(P, 0);
                  goto LABEL_4;
                }
              }
            }
          }
        }
      }
    }
    __fastfail(3u);
  }
LABEL_4:
  if ( !a2 )
    KeReleaseInStackQueuedSpinLock(&LockHandle);
}

```

## disassembly

```asm
0x140009f94  mov     r11, rsp
0x140009f97  mov     [r11+8], rbx
0x140009f9b  mov     [r11+10h], rsi
0x140009f9f  push    rdi
0x140009fa0  sub     rsp, 60h
0x140009fa4  mov     rdi, [rcx+10h]
0x140009fa8  xor     eax, eax
0x140009faa  mov     rbx, rcx
0x140009fad  xorps   xmm0, xmm0
0x140009fb0  mov     esi, edx
0x140009fb2  mov     rcx, [rdi+18h]
0x140009fb6  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x140009fbb  mov     [r11-28h], rax
0x140009fbf  test    edx, edx
0x140009fc1  jnz     short loc_140009FDA
0x140009fc3  add     rcx, 830h; SpinLock
0x140009fca  lea     rdx, [r11-38h]; LockHandle
0x140009fce  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140009fd5  nop     dword ptr [rax+rax+00h]
0x140009fda  or      eax, 0FFFFFFFFh
0x140009fdd  lock xadd [rbx+28h], eax
0x140009fe2  cmp     eax, 1
0x140009fe5  jz      short loc_14000A00D
0x140009fe7  test    esi, esi
0x140009fe9  jnz     short loc_140009FFC
0x140009feb  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x140009ff0  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140009ff7  nop     dword ptr [rax+rax+00h]
0x140009ffc  mov     rbx, [rsp+68h+arg_0]
0x14000a001  mov     rsi, [rsp+68h+arg_8]
0x14000a006  add     rsp, 60h
0x14000a00a  pop     rdi
0x14000a00b  retn
0x14000a00d  lea     rax, [rbx+128h]
0x14000a014  cmp     [rax], rax
0x14000a017  jnz     loc_14000A104
0x14000a01d  cmp     dword ptr [rbx+13Ch], 0
0x14000a024  jnz     loc_14000A104
0x14000a02a  lea     rax, [rbx+108h]
0x14000a031  mov     rcx, [rax]
0x14000a034  cmp     [rcx+8], rax
0x14000a038  jnz     loc_14000A14B
0x14000a03e  mov     rdx, [rax+8]
0x14000a042  cmp     [rdx], rax
0x14000a045  jnz     loc_14000A14B
0x14000a04b  mov     [rdx], rcx
0x14000a04e  lea     rax, [rbx+118h]
0x14000a055  mov     [rcx+8], rdx
0x14000a059  mov     rdx, [rax]
0x14000a05c  cmp     [rdx+8], rax
0x14000a060  jnz     loc_14000A14B
0x14000a066  mov     rcx, [rax+8]
0x14000a06a  cmp     [rcx], rax
0x14000a06d  jnz     loc_14000A14B
0x14000a073  mov     [rcx], rdx
0x14000a076  mov     [rdx+8], rcx
0x14000a07a  cmp     byte ptr [rbx+97h], 0
0x14000a081  jz      short loc_14000A0BE
0x14000a083  lea     rdx, [rbx+0A0h]
0x14000a08a  lea     rcx, [rdi+6E0h]
0x14000a091  call    cs:__imp_RtlAvlRemoveNode
0x14000a098  nop     dword ptr [rax+rax+00h]
0x14000a09d  lea     rdx, [rbx+0B8h]
0x14000a0a4  lea     rcx, [rdi+6E8h]
0x14000a0ab  call    cs:__imp_RtlAvlRemoveNode
0x14000a0b2  nop     dword ptr [rax+rax+00h]
0x14000a0b7  mov     byte ptr [rbx+97h], 0
0x14000a0be  mov     rcx, [rbx+8]; P
0x14000a0c2  xor     eax, eax
0x14000a0c4  xorps   xmm0, xmm0
0x14000a0c7  mov     [rsp+68h+var_10], rax
0x14000a0cc  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000a0d0  movups  [rsp+68h+var_20], xmm0
0x14000a0d5  lock xadd [rcx+20h], rax
0x14000a0db  cmp     rax, 1
0x14000a0df  jz      short loc_14000A152
0x14000a0e1  cmp     byte ptr [rbx+96h], 0
0x14000a0e8  jnz     loc_14000A182
0x14000a0ee  xor     edx, edx; Tag
0x14000a0f0  mov     rcx, rbx; P
0x14000a0f3  call    cs:__imp_ExFreePoolWithTag
0x14000a0fa  nop     dword ptr [rax+rax+00h]
0x14000a0ff  jmp     loc_140009FE7
0x14000a104  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x14000a10b  mov     ecx, [rbx+13Ch]
0x14000a111  mov     dword ptr [rax], 1
0x14000a117  mov     [rsp+68h+var_40], 0
0x14000a120  mov     r9, rbx
0x14000a123  mov     [rsp+68h+var_48], rcx
0x14000a128  mov     edx, 119h
0x14000a12d  xor     ecx, ecx
0x14000a12f  mov     r8d, 3000h
0x14000a135  call    cs:__imp_WdLogSingleEntry5
0x14000a13c  nop     dword ptr [rax+rax+00h]
0x14000a141  mov     cs:WdLogGlobalForLineNumber, 399h
0x14000a14b  mov     ecx, 3
0x14000a150  int     29h; Win8: RtlFailFast(ecx)
0x14000a152  lea     rax, [rcx+70h]
0x14000a156  mov     rdx, [rax]
0x14000a159  cmp     [rdx+8], rax
0x14000a15d  jnz     short loc_14000A14B
0x14000a15f  mov     r8, [rax+8]
0x14000a163  cmp     [r8], rax
0x14000a166  jnz     short loc_14000A14B
0x14000a168  mov     [r8], rdx
0x14000a16b  mov     [rdx+8], r8
0x14000a16f  xor     edx, edx; Tag
0x14000a171  call    cs:__imp_ExFreePoolWithTag
0x14000a178  nop     dword ptr [rax+rax+00h]
0x14000a17d  jmp     loc_14000A0E1
0x14000a182  mov     rcx, [rbx+20h]; P
0x14000a186  test    rcx, rcx
0x14000a189  jz      loc_14000A0EE
0x14000a18f  mov     edx, 4B677844h; Tag
0x14000a194  call    cs:__imp_ExFreePoolWithTag
0x14000a19b  nop     dword ptr [rax+rax+00h]
0x14000a1a0  jmp     loc_14000A0EE
```
