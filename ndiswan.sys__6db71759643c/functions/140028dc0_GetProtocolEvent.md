# GetProtocolEvent

- ea: `0x140028dc0`
- end: `0x140028f54`
- name: `GetProtocolEvent`
- size: `404`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000a290`
- `0x14000a5f4`
- `0x140016700`
- `0x140028dc0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140028f36`
- `ntoskrnl!KeReleaseSpinLock` at `0x140028f36`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028e24`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028e24`

## pseudocode

```c
__int64 __fastcall GetProtocolEvent(__int64 a1, unsigned int a2, _DWORD *a3, unsigned int a4, _DWORD *a5)
{
  PKSPIN_LOCK v8; // rbx
  KSPIN_LOCK *v9; // rcx
  unsigned int v10; // ebp
  PKSPIN_LOCK v11; // rbx
  unsigned int v12; // r14d
  KSPIN_LOCK v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // r9d
  int v16; // eax
  __int64 v17; // rcx
  bool v18; // zf

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 105, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
  }
  v8 = ProtocolInfoTable;
  v9 = ProtocolInfoTable;
  *a5 = 0;
  *((_BYTE *)v8 + 8) = KeAcquireSpinLockRaiseToDpc(v9);
  if ( a4 >= 0x104 )
  {
    v11 = ProtocolInfoTable;
    v10 = 0;
    v12 = *((_DWORD *)ProtocolInfoTable + 5);
    *a5 = 260;
    memset(a3, 0, 0x104u);
    v13 = v11[5];
    v14 = 0;
    v15 = 0;
    if ( !v12 )
    {
LABEL_20:
      *((_DWORD *)ProtocolInfoTable + 6) &= 0xFFFFFFE7;
      goto LABEL_21;
    }
    while ( (*(_DWORD *)(v13 + 4) & 8) == 0 )
    {
LABEL_19:
      ++v15;
      v13 += 20LL;
      if ( v15 >= v12 )
        goto LABEL_20;
    }
    LOWORD(a3[2 * v14 + 1]) = *(_WORD *)v13;
    v16 = *(_DWORD *)(v13 + 4);
    v17 = (unsigned int)v14;
    v14 = (unsigned int)(v14 + 1);
    if ( (v16 & 4) != 0 )
    {
      *(_DWORD *)(v13 + 4) = v16 & 0xFFFFFFF3;
      a3[2 * v17 + 2] = 2;
      ++*a3;
      v18 = (_DWORD)v14 == 32;
      if ( (unsigned int)v14 >= 0x20 )
        goto LABEL_18;
      LOWORD(a3[2 * v14 + 1]) = *(_WORD *)v13;
      a3[2 * v14 + 2] = 1;
      ++*a3;
      v14 = (unsigned int)(v14 + 1);
    }
    else
    {
      a3[2 * v17 + 2] = 2 - ((v16 & 2) != 0);
      *(_DWORD *)(v13 + 4) &= ~8u;
      ++*a3;
    }
    v18 = (_DWORD)v14 == 32;
LABEL_18:
    if ( v18 )
      goto LABEL_20;
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, a2, 260);
  }
  *a5 = 260;
  v10 = -1073741820;
LABEL_21:
  KeReleaseSpinLock(ProtocolInfoTable, *((_BYTE *)ProtocolInfoTable + 8));
  return v10;
}

```

## disassembly

```asm
0x140028dc0  push    rbx
0x140028dc2  push    rbp
0x140028dc3  push    rsi
0x140028dc4  push    rdi
0x140028dc5  push    r12
0x140028dc7  push    r14
0x140028dc9  push    r15
0x140028dcb  sub     rsp, 30h
0x140028dcf  mov     r14d, r9d
0x140028dd2  mov     rdi, r8
0x140028dd5  mov     ebp, edx
0x140028dd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140028dde  lea     r12, WPP_GLOBAL_Control
0x140028de5  cmp     rcx, r12
0x140028de8  jz      short loc_140028E0C
0x140028dea  mov     eax, [rcx+2Ch]
0x140028ded  test    al, 20h
0x140028def  jz      short loc_140028E0C
0x140028df1  cmp     byte ptr [rcx+29h], 5
0x140028df5  jb      short loc_140028E0C
0x140028df7  mov     rcx, [rcx+18h]
0x140028dfb  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140028e02  mov     edx, 69h ; 'i'
0x140028e07  call    WPP_SF_
0x140028e0c  mov     rbx, cs:ProtocolInfoTable
0x140028e13  mov     rsi, [rsp+68h+arg_20]
0x140028e1b  mov     rcx, rbx; SpinLock
0x140028e1e  mov     dword ptr [rsi], 0
0x140028e24  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140028e2b  nop     dword ptr [rax+rax+00h]
0x140028e30  mov     r15d, 104h
0x140028e36  mov     [rbx+8], al
0x140028e39  cmp     r14d, r15d
0x140028e3c  jnb     short loc_140028E81
0x140028e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140028e45  cmp     rcx, r12
0x140028e48  jz      short loc_140028E74
0x140028e4a  mov     eax, [rcx+2Ch]
0x140028e4d  test    al, 20h
0x140028e4f  jz      short loc_140028E74
0x140028e51  cmp     byte ptr [rcx+29h], 3
0x140028e55  jb      short loc_140028E74
0x140028e57  mov     rcx, [rcx+18h]
0x140028e5b  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140028e62  mov     edx, 6Ah ; 'j'
0x140028e67  mov     [rsp+68h+var_48], r15d
0x140028e6c  mov     r9d, ebp
0x140028e6f  call    WPP_SF_dd
0x140028e74  mov     [rsi], r15d
0x140028e77  mov     ebp, 0C0000004h
0x140028e7c  jmp     loc_140028F2C
0x140028e81  mov     rbx, cs:ProtocolInfoTable
0x140028e88  mov     r8, r15; Size
0x140028e8b  xor     edx, edx; Val
0x140028e8d  mov     rcx, rdi; void *
0x140028e90  xor     ebp, ebp
0x140028e92  mov     r14d, [rbx+14h]
0x140028e96  mov     [rsi], r15d
0x140028e99  call    memset
0x140028e9e  mov     rdx, [rbx+28h]
0x140028ea2  xor     r8d, r8d
0x140028ea5  xor     r9d, r9d
0x140028ea8  test    r14d, r14d
0x140028eab  jz      short loc_140028F21
0x140028ead  lea     r10d, [rbp+1]
0x140028eb1  mov     eax, [rdx+4]
0x140028eb4  test    al, 8
0x140028eb6  jz      short loc_140028F15
0x140028eb8  movzx   eax, word ptr [rdx]
0x140028ebb  mov     [rdi+r8*8+4], ax
0x140028ec1  mov     eax, [rdx+4]
0x140028ec4  mov     ecx, r8d
0x140028ec7  inc     r8d
0x140028eca  test    al, 4
0x140028ecc  jz      short loc_140028EFB
0x140028ece  and     eax, 0FFFFFFF3h
0x140028ed1  mov     [rdx+4], eax
0x140028ed4  mov     dword ptr [rdi+rcx*8+8], 2
0x140028edc  add     [rdi], r10d
0x140028edf  cmp     r8d, 20h ; ' '
0x140028ee3  jnb     short loc_140028F13
0x140028ee5  movzx   eax, word ptr [rdx]
0x140028ee8  mov     [rdi+r8*8+4], ax
0x140028eee  mov     [rdi+r8*8+8], r10d
0x140028ef3  add     [rdi], r10d
0x140028ef6  inc     r8d
0x140028ef9  jmp     short loc_140028F0F
0x140028efb  and     al, 2
0x140028efd  neg     al
0x140028eff  sbb     eax, eax
0x140028f01  add     eax, 2
0x140028f04  mov     [rdi+rcx*8+8], eax
0x140028f08  and     dword ptr [rdx+4], 0FFFFFFF7h
0x140028f0c  add     [rdi], r10d
0x140028f0f  cmp     r8d, 20h ; ' '
0x140028f13  jz      short loc_140028F21
0x140028f15  add     r9d, r10d
0x140028f18  add     rdx, 14h
0x140028f1c  cmp     r9d, r14d
0x140028f1f  jb      short loc_140028EB1
0x140028f21  mov     rcx, cs:ProtocolInfoTable
0x140028f28  and     dword ptr [rcx+18h], 0FFFFFFE7h
0x140028f2c  mov     rcx, cs:ProtocolInfoTable; SpinLock
0x140028f33  mov     dl, [rcx+8]; NewIrql
0x140028f36  call    cs:__imp_KeReleaseSpinLock
0x140028f3d  nop     dword ptr [rax+rax+00h]
0x140028f42  mov     eax, ebp
0x140028f44  add     rsp, 30h
0x140028f48  pop     r15
0x140028f4a  pop     r14
0x140028f4c  pop     r12
0x140028f4e  pop     rdi
0x140028f4f  pop     rsi
0x140028f50  pop     rbp
0x140028f51  pop     rbx
0x140028f52  retn
```
