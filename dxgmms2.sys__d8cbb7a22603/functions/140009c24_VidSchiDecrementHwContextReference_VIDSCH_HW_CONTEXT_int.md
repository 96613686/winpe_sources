# VidSchiDecrementHwContextReference(VIDSCH_HW_CONTEXT *,int)

- ea: `0x140009c24`
- end: `0x140009e35`
- name: `?VidSchiDecrementHwContextReference@@YAXPEAUVIDSCH_HW_CONTEXT@@H@Z`
- size: `529`
- prototype: `void __fastcall(PVOID P, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140009420`
- `0x140009674`
- `0x1400556c4`

## callees

- `0x140009c24`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009c5e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009c5e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009c80`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009c80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009d83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009e01`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009e24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009d83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009e01`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009e24`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140009d21`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140009d3b`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140009d21`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140009d3b`
- `watchdog!WdLogSingleEntry5` at `0x140009dc5`
- `watchdog!WdLogSingleEntry5` at `0x140009dc5`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140009d94`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VidSchiDecrementHwContextReference(unsigned int *P, int a2)
{
  __int64 v2; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned int **v7; // rdx
  __int64 v8; // rdx
  unsigned int **v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rdx
  _QWORD *v13; // r8
  void *v14; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-38h] BYREF
  __int128 v16; // [rsp+48h] [rbp-20h]
  __int64 v17; // [rsp+58h] [rbp-10h]

  v2 = *((_QWORD *)P + 2);
  v5 = *(_QWORD *)(v2 + 24);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !a2 )
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v5 + 2096), &LockHandle);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 10, 0xFFFFFFFF) == 1 )
  {
    if ( *((unsigned int **)P + 37) != P + 74 || P[79] )
    {
      v11 = P[79];
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 281, 12288, P, v11, 0);
      WdLogGlobalForLineNumber = 926;
    }
    else
    {
      v6 = *((_QWORD *)P + 33);
      if ( *(unsigned int **)(v6 + 8) == P + 66 )
      {
        v7 = (unsigned int **)*((_QWORD *)P + 34);
        if ( *v7 == P + 66 )
        {
          *v7 = (unsigned int *)v6;
          *(_QWORD *)(v6 + 8) = v7;
          v8 = *((_QWORD *)P + 35);
          if ( *(unsigned int **)(v8 + 8) == P + 70 )
          {
            v9 = (unsigned int **)*((_QWORD *)P + 36);
            if ( *v9 == P + 70 )
            {
              *v9 = (unsigned int *)v8;
              *(_QWORD *)(v8 + 8) = v9;
              if ( *((_BYTE *)P + 151) )
              {
                RtlAvlRemoveNode(v2 + 1760, P + 40);
                RtlAvlRemoveNode(v2 + 1768, P + 46);
                *((_BYTE *)P + 151) = 0;
              }
              v10 = *((_QWORD *)P + 1);
              v17 = 0;
              v16 = 0;
              if ( _InterlockedExchangeAdd64((volatile signed __int64 *)(v10 + 32), 0xFFFFFFFFFFFFFFFFuLL) != 1 )
                goto LABEL_16;
              v12 = *(_QWORD *)(v10 + 112);
              if ( *(_QWORD *)(v12 + 8) == v10 + 112 )
              {
                v13 = *(_QWORD **)(v10 + 120);
                if ( *v13 == v10 + 112 )
                {
                  *v13 = v12;
                  *(_QWORD *)(v12 + 8) = v13;
                  ExFreePoolWithTag((PVOID)v10, 0);
LABEL_16:
                  if ( *((_BYTE *)P + 150) )
                  {
                    v14 = (void *)*((_QWORD *)P + 4);
                    if ( v14 )
                      ExFreePoolWithTag(v14, 0x4B677844u);
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
0x140009c24  mov     r11, rsp
0x140009c27  mov     [r11+8], rbx
0x140009c2b  mov     [r11+10h], rsi
0x140009c2f  push    rdi
0x140009c30  sub     rsp, 60h
0x140009c34  mov     rdi, [rcx+10h]
0x140009c38  xor     eax, eax
0x140009c3a  mov     rbx, rcx
0x140009c3d  xorps   xmm0, xmm0
0x140009c40  mov     esi, edx
0x140009c42  mov     rcx, [rdi+18h]
0x140009c46  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x140009c4b  mov     [r11-28h], rax
0x140009c4f  test    edx, edx
0x140009c51  jnz     short loc_140009C6A
0x140009c53  add     rcx, 830h; SpinLock
0x140009c5a  lea     rdx, [r11-38h]; LockHandle
0x140009c5e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140009c65  nop     dword ptr [rax+rax+00h]
0x140009c6a  or      eax, 0FFFFFFFFh
0x140009c6d  lock xadd [rbx+28h], eax
0x140009c72  cmp     eax, 1
0x140009c75  jz      short loc_140009C9D
0x140009c77  test    esi, esi
0x140009c79  jnz     short loc_140009C8C
0x140009c7b  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x140009c80  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140009c87  nop     dword ptr [rax+rax+00h]
0x140009c8c  mov     rbx, [rsp+68h+arg_0]
0x140009c91  mov     rsi, [rsp+68h+arg_8]
0x140009c96  add     rsp, 60h
0x140009c9a  pop     rdi
0x140009c9b  retn
0x140009c9d  lea     rax, [rbx+128h]
0x140009ca4  cmp     [rax], rax
0x140009ca7  jnz     loc_140009D94
0x140009cad  cmp     dword ptr [rbx+13Ch], 0
0x140009cb4  jnz     loc_140009D94
0x140009cba  lea     rax, [rbx+108h]
0x140009cc1  mov     rcx, [rax]
0x140009cc4  cmp     [rcx+8], rax
0x140009cc8  jnz     loc_140009DDB
0x140009cce  mov     rdx, [rax+8]
0x140009cd2  cmp     [rdx], rax
0x140009cd5  jnz     loc_140009DDB
0x140009cdb  mov     [rdx], rcx
0x140009cde  lea     rax, [rbx+118h]
0x140009ce5  mov     [rcx+8], rdx
0x140009ce9  mov     rdx, [rax]
0x140009cec  cmp     [rdx+8], rax
0x140009cf0  jnz     loc_140009DDB
0x140009cf6  mov     rcx, [rax+8]
0x140009cfa  cmp     [rcx], rax
0x140009cfd  jnz     loc_140009DDB
0x140009d03  mov     [rcx], rdx
0x140009d06  mov     [rdx+8], rcx
0x140009d0a  cmp     byte ptr [rbx+97h], 0
0x140009d11  jz      short loc_140009D4E
0x140009d13  lea     rdx, [rbx+0A0h]
0x140009d1a  lea     rcx, [rdi+6E0h]
0x140009d21  call    cs:__imp_RtlAvlRemoveNode
0x140009d28  nop     dword ptr [rax+rax+00h]
0x140009d2d  lea     rdx, [rbx+0B8h]
0x140009d34  lea     rcx, [rdi+6E8h]
0x140009d3b  call    cs:__imp_RtlAvlRemoveNode
0x140009d42  nop     dword ptr [rax+rax+00h]
0x140009d47  mov     byte ptr [rbx+97h], 0
0x140009d4e  mov     rcx, [rbx+8]; P
0x140009d52  xor     eax, eax
0x140009d54  xorps   xmm0, xmm0
0x140009d57  mov     [rsp+68h+var_10], rax
0x140009d5c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009d60  movups  [rsp+68h+var_20], xmm0
0x140009d65  lock xadd [rcx+20h], rax
0x140009d6b  cmp     rax, 1
0x140009d6f  jz      short loc_140009DE2
0x140009d71  cmp     byte ptr [rbx+96h], 0
0x140009d78  jnz     loc_140009E12
0x140009d7e  xor     edx, edx; Tag
0x140009d80  mov     rcx, rbx; P
0x140009d83  call    cs:__imp_ExFreePoolWithTag
0x140009d8a  nop     dword ptr [rax+rax+00h]
0x140009d8f  jmp     loc_140009C77
0x140009d94  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x140009d9b  mov     ecx, [rbx+13Ch]
0x140009da1  mov     dword ptr [rax], 1
0x140009da7  mov     [rsp+68h+var_40], 0
0x140009db0  mov     r9, rbx
0x140009db3  mov     [rsp+68h+var_48], rcx
0x140009db8  mov     edx, 119h
0x140009dbd  xor     ecx, ecx
0x140009dbf  mov     r8d, 3000h
0x140009dc5  call    cs:__imp_WdLogSingleEntry5
0x140009dcc  nop     dword ptr [rax+rax+00h]
0x140009dd1  mov     cs:WdLogGlobalForLineNumber, 39Eh
0x140009ddb  mov     ecx, 3
0x140009de0  int     29h; Win8: RtlFailFast(ecx)
0x140009de2  lea     rax, [rcx+70h]
0x140009de6  mov     rdx, [rax]
0x140009de9  cmp     [rdx+8], rax
0x140009ded  jnz     short loc_140009DDB
0x140009def  mov     r8, [rax+8]
0x140009df3  cmp     [r8], rax
0x140009df6  jnz     short loc_140009DDB
0x140009df8  mov     [r8], rdx
0x140009dfb  mov     [rdx+8], r8
0x140009dff  xor     edx, edx; Tag
0x140009e01  call    cs:__imp_ExFreePoolWithTag
0x140009e08  nop     dword ptr [rax+rax+00h]
0x140009e0d  jmp     loc_140009D71
0x140009e12  mov     rcx, [rbx+20h]; P
0x140009e16  test    rcx, rcx
0x140009e19  jz      loc_140009D7E
0x140009e1f  mov     edx, 4B677844h; Tag
0x140009e24  call    cs:__imp_ExFreePoolWithTag
0x140009e2b  nop     dword ptr [rax+rax+00h]
0x140009e30  jmp     loc_140009D7E
```
