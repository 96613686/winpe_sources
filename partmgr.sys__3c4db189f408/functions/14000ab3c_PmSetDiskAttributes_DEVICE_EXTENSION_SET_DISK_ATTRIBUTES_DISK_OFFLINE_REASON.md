# PmSetDiskAttributes(_DEVICE_EXTENSION *,_SET_DISK_ATTRIBUTES *,_DISK_OFFLINE_REASON)

- ea: `0x14000ab3c`
- end: `0x14000ad97`
- name: `?PmSetDiskAttributes@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SET_DISK_ATTRIBUTES@@W4_DISK_OFFLINE_REASON@@@Z`
- size: `603`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x14000bbe0`
- `0x14001c0e0`
- `0x14001ccb4`
- `0x14002184c`
- `0x14002589c`
- `0x140025ab8`

## callees

- `0x14000a014`
- `0x14000ab3c`
- `0x14000bfa0`
- `0x14002032c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000ad72`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ad72`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000ac81`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000aca9`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000ac81`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14000aca9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000acee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000acee`

## pseudocode

```c
__int64 __fastcall PmSetDiskAttributes(__int64 a1, __int64 a2, int a3)
{
  GUID *v6; // rcx
  __int64 v7; // rax
  GUID *v8; // rbp
  int v9; // edi
  __int64 v10; // r15
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r15
  GUID v14; // xmm0
  int *v15; // rsi
  __int64 v16; // rax
  __int64 v17; // rbp
  KIRQL v18; // bp
  int v19; // r8d
  unsigned __int8 v20; // dl

  if ( (*(_DWORD *)(a1 + 516) & 1) != 0 && (*(_DWORD *)(a1 + 516) & 0x4000) != 0 )
    return (unsigned int)-1073741790;
  v6 = (GUID *)(a1 + 544);
  v7 = *(_QWORD *)&v6->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&v6->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v7 = *(_QWORD *)v6->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( !v7 )
  {
    v8 = v6;
    goto LABEL_10;
  }
  if ( *(_QWORD *)&v6->Data1 != *(_QWORD *)(a2 + 24) || *(_QWORD *)v6->Data4 != *(_QWORD *)(a2 + 32) )
    return (unsigned int)-1073741790;
  v8 = (GUID *)(a1 + 544);
LABEL_10:
  v9 = 0;
  if ( *(_BYTE *)(a2 + 4) )
  {
    v10 = *(_QWORD *)(a2 + 16) & *(_QWORD *)(a2 + 8) | *(_QWORD *)(a1 + 536) & ~*(_QWORD *)(a2 + 16);
    v9 = PmSetDeviceParameter((struct _DEVICE_EXTENSION *)a1, (unsigned __int16 *)a2, v10);
    if ( v9 < 0 )
      return (unsigned int)v9;
    *(_QWORD *)(a1 + 536) = v10;
  }
  else
  {
    v8 = v6;
  }
  v11 = *(_QWORD *)(a2 + 8) & *(_QWORD *)(a2 + 16) | *(_QWORD *)(a1 + 528) & ~*(_QWORD *)(a2 + 16);
  v12 = *(_QWORD *)(a1 + 528);
  *(_QWORD *)(a1 + 528) = v11;
  v13 = v12 ^ v11;
  if ( *(_BYTE *)(a2 + 5) )
    v14 = GUID_NULL;
  else
    v14 = *(GUID *)(a2 + 24);
  v15 = (int *)(a1 + 512);
  *v8 = v14;
  if ( (v13 & 4) != 0 || *v15 == 2 )
  {
    v16 = *v15;
    v17 = (*(_QWORD *)(a1 + 528) >> 2) & 1LL;
    if ( (_DWORD)v16 != 2 )
    {
      v9 = IoSetDeviceInterfaceState((PUNICODE_STRING)(a1 + 16 * (v16 + 30)), 0);
      if ( v9 < 0 )
        return (unsigned int)v9;
      *v15 = 2;
    }
    v9 = IoSetDeviceInterfaceState((PUNICODE_STRING)(a1 + 16 * ((unsigned int)v17 + 30LL)), 1u);
    if ( v9 < 0 )
      return (unsigned int)v9;
    *v15 = v17;
  }
  if ( v13 )
  {
    if ( (v13 & 2) != 0 )
      _InterlockedExchange((volatile __int32 *)(a1 + 524), (*(_QWORD *)(a1 + 528) & 2) == 0);
    v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 112));
    if ( (v13 & 1) != 0 )
    {
      if ( (*(_QWORD *)(a1 + 528) & 1) != 0 )
      {
        v20 = 1;
        *(_DWORD *)(a1 + 516) |= 0x10u;
        *(_DWORD *)(a1 + 520) = a3;
      }
      else
      {
        *(_QWORD *)(a1 + 516) = *(_DWORD *)(a1 + 516) & 0xFFFFFFEF;
        v20 = 0;
      }
      PmUpdateOffline((struct _DEVICE_EXTENSION *)a1, v20);
    }
    *(_DWORD *)(a1 + 516) |= 0x100000u;
    PmQueueNotificationWorkItem((struct _DEVICE_EXTENSION *)a1, "PmSetDiskAttributes", v19);
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 112), v18);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000ab3c  push    rbx
0x14000ab3e  push    rbp
0x14000ab3f  push    rsi
0x14000ab40  push    rdi
0x14000ab41  push    r12
0x14000ab43  push    r14
0x14000ab45  push    r15
0x14000ab47  sub     rsp, 20h
0x14000ab4b  mov     eax, [rcx+204h]
0x14000ab51  mov     r12d, r8d
0x14000ab54  mov     r14, rdx
0x14000ab57  mov     rbx, rcx
0x14000ab5a  test    al, 1
0x14000ab5c  jz      short loc_14000AB6E
0x14000ab5e  mov     eax, [rcx+204h]
0x14000ab64  bt      eax, 0Eh
0x14000ab68  jb      loc_14000AD80
0x14000ab6e  add     rcx, 220h
0x14000ab75  mov     rax, [rcx]
0x14000ab78  sub     rax, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x14000ab7f  jnz     short loc_14000AB8C
0x14000ab81  mov     rax, [rcx+8]
0x14000ab85  sub     rax, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data4; _GUID const GUID_NULL ...
0x14000ab8c  test    rax, rax
0x14000ab8f  jnz     short loc_14000AB96
0x14000ab91  mov     rbp, rcx
0x14000ab94  jmp     short loc_14000ABB8
0x14000ab96  mov     rax, [rcx]
0x14000ab99  cmp     rax, [rdx+18h]
0x14000ab9d  jnz     loc_14000AD80
0x14000aba3  mov     rax, [rcx+8]
0x14000aba7  cmp     rax, [rdx+20h]
0x14000abab  jnz     loc_14000AD80
0x14000abb1  lea     rbp, [rbx+220h]
0x14000abb8  xor     edi, edi
0x14000abba  cmp     [rdx+4], dil
0x14000abbe  jz      short loc_14000ABF9
0x14000abc0  mov     rcx, [rdx+10h]
0x14000abc4  mov     rax, [rdx+8]
0x14000abc8  mov     r15, rcx
0x14000abcb  and     rax, rcx
0x14000abce  not     r15
0x14000abd1  and     r15, [rbx+218h]
0x14000abd8  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x14000abdb  or      r15, rax
0x14000abde  mov     r8, r15; unsigned __int64
0x14000abe1  call    ?PmSetDeviceParameter@@YAJPEAU_DEVICE_EXTENSION@@PEAG_K@Z; PmSetDeviceParameter(_DEVICE_EXTENSION *,ushort *,unsigned __int64)
0x14000abe6  mov     edi, eax
0x14000abe8  test    eax, eax
0x14000abea  js      loc_14000AD85
0x14000abf0  mov     [rbx+218h], r15
0x14000abf7  jmp     short loc_14000ABFC
0x14000abf9  mov     rbp, rcx
0x14000abfc  mov     rax, [rbx+210h]
0x14000ac03  mov     rcx, [r14+10h]
0x14000ac07  not     rcx
0x14000ac0a  and     rcx, rax
0x14000ac0d  mov     rax, [r14+10h]
0x14000ac11  and     rax, [r14+8]
0x14000ac15  or      rcx, rax
0x14000ac18  mov     rax, [rbx+210h]
0x14000ac1f  mov     r15, rcx
0x14000ac22  mov     [rbx+210h], rcx
0x14000ac29  xor     r15, rax
0x14000ac2c  cmp     byte ptr [r14+5], 0
0x14000ac31  jz      short loc_14000AC3C
0x14000ac33  movups  xmm0, xmmword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x14000ac3a  jmp     short loc_14000AC41
0x14000ac3c  movups  xmm0, xmmword ptr [r14+18h]
0x14000ac41  lea     rsi, [rbx+200h]
0x14000ac48  mov     r14d, 2
0x14000ac4e  movdqu  xmmword ptr [rbp+0], xmm0
0x14000ac53  test    r15b, 4
0x14000ac57  jnz     short loc_14000AC5E
0x14000ac59  cmp     [rsi], r14d
0x14000ac5c  jnz     short loc_14000ACC1
0x14000ac5e  mov     rbp, [rbx+210h]
0x14000ac65  movsxd  rax, dword ptr [rsi]
0x14000ac68  shr     rbp, 2
0x14000ac6c  and     ebp, 1
0x14000ac6f  cmp     eax, r14d
0x14000ac72  jz      short loc_14000AC9A
0x14000ac74  lea     rcx, [rax+1Eh]
0x14000ac78  xor     edx, edx; Enable
0x14000ac7a  shl     rcx, 4
0x14000ac7e  add     rcx, rbx; SymbolicLinkName
0x14000ac81  call    cs:__imp_IoSetDeviceInterfaceState
0x14000ac88  nop     dword ptr [rax+rax+00h]
0x14000ac8d  mov     edi, eax
0x14000ac8f  test    eax, eax
0x14000ac91  js      loc_14000AD85
0x14000ac97  mov     [rsi], r14d
0x14000ac9a  mov     ecx, ebp
0x14000ac9c  mov     dl, 1; Enable
0x14000ac9e  add     rcx, 1Eh
0x14000aca2  shl     rcx, 4
0x14000aca6  add     rcx, rbx; SymbolicLinkName
0x14000aca9  call    cs:__imp_IoSetDeviceInterfaceState
0x14000acb0  nop     dword ptr [rax+rax+00h]
0x14000acb5  mov     edi, eax
0x14000acb7  test    eax, eax
0x14000acb9  js      loc_14000AD85
0x14000acbf  mov     [rsi], ebp
0x14000acc1  test    r15, r15
0x14000acc4  jz      loc_14000AD85
0x14000acca  test    r14b, r15b
0x14000accd  jz      short loc_14000ACEA
0x14000accf  mov     rax, [rbx+210h]
0x14000acd6  test    r14b, al
0x14000acd9  jz      short loc_14000ACDF
0x14000acdb  xor     eax, eax
0x14000acdd  jmp     short loc_14000ACE4
0x14000acdf  mov     eax, 1
0x14000ace4  xchg    eax, [rbx+20Ch]
0x14000acea  lea     rcx, [rbx+70h]; SpinLock
0x14000acee  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000acf5  nop     dword ptr [rax+rax+00h]
0x14000acfa  mov     bpl, al
0x14000acfd  test    r15b, 1
0x14000ad01  jz      short loc_14000AD4C
0x14000ad03  mov     rcx, [rbx+210h]
0x14000ad0a  test    cl, 1
0x14000ad0d  jz      short loc_14000AD29
0x14000ad0f  mov     ecx, [rbx+204h]
0x14000ad15  mov     dl, 1
0x14000ad17  or      ecx, 10h
0x14000ad1a  mov     [rbx+204h], ecx
0x14000ad20  mov     [rbx+208h], r12d
0x14000ad27  jmp     short loc_14000AD44
0x14000ad29  mov     eax, [rbx+204h]
0x14000ad2f  and     eax, 0FFFFFFEFh
0x14000ad32  mov     dword ptr [rbx+208h], 0
0x14000ad3c  mov     [rbx+204h], eax
0x14000ad42  xor     edx, edx; unsigned __int8
0x14000ad44  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x14000ad47  call    ?PmUpdateOffline@@YAXPEAU_DEVICE_EXTENSION@@E@Z; PmUpdateOffline(_DEVICE_EXTENSION *,uchar)
0x14000ad4c  mov     eax, [rbx+204h]
0x14000ad52  lea     rdx, aPmsetdiskattri; "PmSetDiskAttributes"
0x14000ad59  bts     eax, 14h
0x14000ad5d  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x14000ad60  mov     [rbx+204h], eax
0x14000ad66  call    ?PmQueueNotificationWorkItem@@YAJPEAU_DEVICE_EXTENSION@@PEBD@Z; PmQueueNotificationWorkItem(_DEVICE_EXTENSION *,char const *)
0x14000ad6b  mov     dl, bpl; NewIrql
0x14000ad6e  lea     rcx, [rbx+70h]; SpinLock
0x14000ad72  call    cs:__imp_KeReleaseSpinLock
0x14000ad79  nop     dword ptr [rax+rax+00h]
0x14000ad7e  jmp     short loc_14000AD85
0x14000ad80  mov     edi, 0C0000022h
0x14000ad85  mov     eax, edi
0x14000ad87  add     rsp, 20h
0x14000ad8b  pop     r15
0x14000ad8d  pop     r14
0x14000ad8f  pop     r12
0x14000ad91  pop     rdi
0x14000ad92  pop     rsi
0x14000ad93  pop     rbp
0x14000ad94  pop     rbx
0x14000ad95  retn
```
