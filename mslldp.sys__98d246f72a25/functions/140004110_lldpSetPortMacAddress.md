# lldpSetPortMacAddress

- ea: `0x140004110`
- end: `0x1400041f4`
- name: `lldpSetPortMacAddress`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001ae0`
- `0x140012000`

## callees

- `0x140004110`
- `0x140005b20`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x14000416c`
- `NDIS!NdisReleaseRWLock` at `0x14000416c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000413a`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000413a`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall lldpSetPortMacAddress(__int64 a1, unsigned __int8 *a2)
{
  struct _NDIS_RW_LOCK_EX *v4; // rcx
  struct _NDIS_RW_LOCK_EX *v5; // rcx
  PDEVICE_OBJECT *result; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+70h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  v4 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 976);
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(v4, &LockState, 0);
  v5 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 976);
  *(_DWORD *)(a1 + 144) = *(_DWORD *)a2;
  *(_WORD *)(a1 + 148) = *((_WORD *)a2 + 2);
  *(_BYTE *)(a1 + 151) = 1;
  NdisReleaseRWLock(v5, &LockState);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    return (PDEVICE_OBJECT *)WPP_SF_DDDDDDDD(
                               WPP_GLOBAL_Control->AttachedDevice,
                               a2[4],
                               a2[3],
                               HIWORD(*(_QWORD *)(a1 + 120)),
                               (*(_QWORD *)(a1 + 120) >> 24) & 0xFFFFFF,
                               *a2,
                               a2[1],
                               a2[2],
                               a2[3],
                               a2[4],
                               a2[5]);
  return result;
}

```

## disassembly

```asm
0x140004110  mov     [rsp+arg_8], rbx
0x140004115  push    rdi
0x140004116  sub     rsp, 60h
0x14000411a  xor     eax, eax
0x14000411c  mov     rdi, rdx
0x14000411f  mov     rbx, rcx
0x140004122  mov     word ptr [rsp+68h+LockState.OldIrql], ax
0x140004127  mov     rcx, [rcx+3D0h]; Lock
0x14000412e  lea     rdx, [rsp+68h+LockState]; LockState
0x140004133  xor     r8d, r8d; Flags
0x140004136  mov     [rsp+68h+LockState.Flags], al
0x14000413a  call    cs:__imp_NdisAcquireRWLockWrite
0x140004141  nop     dword ptr [rax+rax+00h]
0x140004146  mov     eax, [rdi]
0x140004148  lea     rdx, [rsp+68h+LockState]; LockState
0x14000414d  mov     rcx, [rbx+3D0h]; Lock
0x140004154  mov     [rbx+90h], eax
0x14000415a  movzx   eax, word ptr [rdi+4]
0x14000415e  mov     [rbx+94h], ax
0x140004165  mov     byte ptr [rbx+97h], 1
0x14000416c  call    cs:__imp_NdisReleaseRWLock
0x140004173  nop     dword ptr [rax+rax+00h]
0x140004178  mov     rcx, cs:WPP_GLOBAL_Control
0x14000417f  lea     rax, WPP_GLOBAL_Control
0x140004186  cmp     rcx, rax
0x140004189  jz      short loc_1400041E8
0x14000418b  cmp     byte ptr [rcx+29h], 4
0x14000418f  jb      short loc_1400041E8
0x140004191  movzx   eax, byte ptr [rdi+5]
0x140004195  movzx   edx, byte ptr [rdi+4]
0x140004199  movzx   r8d, byte ptr [rdi+3]
0x14000419e  movzx   r10d, byte ptr [rdi+2]
0x1400041a3  movzx   r11d, byte ptr [rdi+1]
0x1400041a8  mov     r9, [rbx+78h]
0x1400041ac  movzx   ebx, byte ptr [rdi]
0x1400041af  mov     rdi, r9
0x1400041b2  mov     rcx, [rcx+18h]
0x1400041b6  mov     [rsp+68h+var_18], eax
0x1400041ba  mov     [rsp+68h+var_20], edx
0x1400041be  mov     [rsp+68h+var_28], r8d
0x1400041c3  mov     [rsp+68h+var_30], r10d
0x1400041c8  mov     [rsp+68h+var_38], r11d
0x1400041cd  shr     rdi, 18h
0x1400041d1  and     edi, 0FFFFFFh
0x1400041d7  mov     [rsp+68h+var_40], ebx
0x1400041db  shr     r9, 30h
0x1400041df  mov     [rsp+68h+var_48], edi
0x1400041e3  call    WPP_SF_DDDDDDDD
0x1400041e8  mov     rbx, [rsp+68h+arg_8]
0x1400041ed  add     rsp, 60h
0x1400041f1  pop     rdi
0x1400041f2  retn
```
