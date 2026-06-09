# RefsFsdSetInformation

- ea: `0x1c0001010`
- end: `0x1c000125f`
- name: `RefsFsdSetInformation`
- size: `591`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1c0001010`
- `0x1c0005564`
- `0x1c0005650`
- `0x1c000f480`
- `0x1c00588cc`
- `0x1c0062ce0`
- `0x1c0068960`
- `0x1c014d9fc`
- `0x1c01a3f68`
- `0x1c01cd29c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1c0001081`
- `ntoskrnl!KeInitializeEvent` at `0x1c0001081`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0001130`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0001130`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c000108d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c000108d`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c00010a9`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c00010a9`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c006c68e`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c006c68e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0001223`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0001223`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c00010f0`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c00010f0`

## pseudocode

```c
__int64 __fastcall RefsFsdSetInformation(__int64 a1, IRP *a2)
{
  BOOL v3; // r12d
  __int64 v4; // r13
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rcx
  _DWORD *v8; // rbx
  _QWORD *v9; // rbx
  unsigned int v10; // ebx
  PVOID Context; // [rsp+20h] [rbp-B8h] BYREF
  int v13; // [rsp+28h] [rbp-B0h]
  unsigned int v14; // [rsp+2Ch] [rbp-ACh]
  BOOL v15; // [rsp+30h] [rbp-A8h]
  IRP *v16; // [rsp+38h] [rbp-A0h]
  _QWORD v17[3]; // [rsp+40h] [rbp-98h] BYREF
  struct _KEVENT Event; // [rsp+58h] [rbp-80h] BYREF
  _OWORD v19[2]; // [rsp+70h] [rbp-68h] BYREF
  __int64 v20; // [rsp+90h] [rbp-48h]
  __int128 v21; // [rsp+98h] [rbp-40h] BYREF

  v16 = a2;
  memset(v19, 0, sizeof(v19));
  v20 = 0;
  Context = 0;
  v13 = 0;
  memset(&Event, 0, sizeof(Event));
  v21 = 0;
  v17[0] = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  KeEnterCriticalRegion();
  v3 = (int)IoPropagateActivityIdToThread(a2, &v21, v17) >= 0;
  v15 = v3;
  v4 = RefsInitializeTopLevelIrp(v19, 0, 0);
  v17[1] = v4;
  while ( 1 )
  {
    if ( !Context )
    {
      LOBYTE(v5) = IoIsOperationSynchronous(a2);
      LOBYTE(v6) = 1;
      RefsInitializeIrpContext(a2, v5, v6, &Context);
      v7 = *(_QWORD *)(v4 + 32);
      if ( !v7 )
      {
        *(_DWORD *)(v4 + 4) = 1397140410;
        v8 = Context;
        *(_QWORD *)(v4 + 32) = Context;
        v8[2] |= 0x100000u;
        IoSetTopLevelIrp((PIRP)v4);
        v7 = *(_QWORD *)(v4 + 32);
      }
      *((_QWORD *)Context + 13) = v7;
    }
    v9 = Context;
    RefsPreRequestProcessingExtend(Context);
    v9[19] = &Event;
    v10 = RefsCommonSetInformation(v9);
    v14 = v10;
    if ( v10 != 871 )
      break;
    a2->Tail.Overlay.CurrentStackLocation->Control &= ~1u;
    RefsWaitForOplockCompletionEvent(a2, &Event);
  }
  if ( v3 )
    IoClearActivityIdThread(v17[0]);
  KeLeaveCriticalRegion();
  return v10;
}

```

## disassembly

```asm
0x1c0001010  mov     r11, rsp
0x1c0001013  mov     [r11+8], rbx
0x1c0001017  mov     [r11+18h], rsi
0x1c000101b  push    rdi
0x1c000101c  push    r12
0x1c000101e  push    r13
0x1c0001020  push    r14
0x1c0001022  push    r15
0x1c0001024  sub     rsp, 0B0h
0x1c000102b  mov     rax, cs:__security_cookie
0x1c0001032  xor     rax, rsp
0x1c0001035  mov     [rsp+0D8h+var_30], rax
0x1c000103d  mov     rdi, rdx
0x1c0001040  mov     [rsp+0D8h+var_A0], rdx
0x1c0001045  xorps   xmm0, xmm0
0x1c0001048  xor     eax, eax
0x1c000104a  movups  [rsp+0D8h+var_68], xmm0
0x1c000104f  movups  xmmword ptr [r11-58h], xmm0
0x1c0001054  mov     [r11-48h], rax
0x1c0001058  xor     ebx, ebx
0x1c000105a  and     [rsp+0D8h+Context], rax
0x1c000105f  xor     esi, esi
0x1c0001061  mov     [rsp+0D8h+var_B0], esi
0x1c0001065  movups  xmmword ptr [rsp+0D8h+Event.Header], xmm0
0x1c000106a  mov     [r11-70h], rax
0x1c000106e  movups  xmmword ptr [r11-40h], xmm0
0x1c0001073  and     [rsp+0D8h+var_98], rax
0x1c0001078  xor     r8d, r8d; State
0x1c000107b  xor     edx, edx; Type
0x1c000107d  lea     rcx, [r11-80h]; Event
0x1c0001081  call    cs:__imp_KeInitializeEvent
0x1c0001088  nop     dword ptr [rax+rax+00h]
0x1c000108d  call    cs:__imp_KeEnterCriticalRegion
0x1c0001094  nop     dword ptr [rax+rax+00h]
0x1c0001099  lea     r8, [rsp+0D8h+var_98]
0x1c000109e  lea     rdx, [rsp+0D8h+var_40]
0x1c00010a6  mov     rcx, rdi
0x1c00010a9  call    cs:__imp_IoPropagateActivityIdToThread
0x1c00010b0  nop     dword ptr [rax+rax+00h]
0x1c00010b5  xor     r12d, r12d
0x1c00010b8  lea     r15d, [rbx+1]
0x1c00010bc  test    eax, eax
0x1c00010be  cmovns  r12d, r15d
0x1c00010c2  mov     [rsp+0D8h+var_A8], r12d
0x1c00010c7  xor     r8d, r8d
0x1c00010ca  xor     edx, edx
0x1c00010cc  lea     rcx, [rsp+0D8h+var_68]
0x1c00010d1  call    RefsInitializeTopLevelIrp
0x1c00010d6  mov     r13, rax
0x1c00010d9  mov     r14, rax
0x1c00010dc  mov     [rsp+0D8h+var_90], rax
0x1c00010e1  cmp     [rsp+0D8h+Context], 0
0x1c00010e7  jnz     loc_1C000117C
0x1c00010ed  mov     rcx, rdi; Irp
0x1c00010f0  call    cs:__imp_IoIsOperationSynchronous
0x1c00010f7  nop     dword ptr [rax+rax+00h]
0x1c00010fc  mov     dl, al
0x1c00010fe  lea     r9, [rsp+0D8h+Context]
0x1c0001103  mov     r8b, r15b
0x1c0001106  mov     rcx, rdi
0x1c0001109  call    RefsInitializeIrpContext
0x1c000110e  mov     rcx, [r14+20h]
0x1c0001112  test    rcx, rcx
0x1c0001115  jnz     short loc_1C0001140
0x1c0001117  mov     dword ptr [r14+4], 5346ABBAh
0x1c000111f  mov     rbx, [rsp+0D8h+Context]
0x1c0001124  mov     [r14+20h], rbx
0x1c0001128  bts     dword ptr [rbx+8], 14h
0x1c000112d  mov     rcx, r14; Irp
0x1c0001130  call    cs:__imp_IoSetTopLevelIrp
0x1c0001137  nop     dword ptr [rax+rax+00h]
0x1c000113c  mov     rcx, [r13+20h]
0x1c0001140  mov     rax, [rsp+0D8h+Context]
0x1c0001145  mov     [rax+68h], rcx
0x1c0001149  mov     rbx, [rsp+0D8h+Context]
0x1c000114e  mov     rcx, rbx
0x1c0001151  call    RefsPreRequestProcessingExtend
0x1c0001156  lea     rax, [rsp+0D8h+Event]
0x1c000115b  mov     [rbx+98h], rax
0x1c0001162  mov     rdx, rdi
0x1c0001165  mov     rcx, rbx; Context
0x1c0001168  call    RefsCommonSetInformation
0x1c000116d  mov     ebx, eax
0x1c000116f  mov     [rsp+0D8h+var_AC], eax
0x1c0001173  cmp     eax, 367h
0x1c0001178  jz      short loc_1C00011A3
0x1c000117a  jmp     short loc_1C00011C1
0x1c000117c  cmp     ebx, 0C0000188h
0x1c0001182  jnz     short loc_1C0001149
0x1c0001184  mov     rbx, [rsp+0D8h+Context]
0x1c0001189  mov     rcx, rbx
0x1c000118c  call    RefsCheckpointForLogFileFull
0x1c0001191  add     esi, r15d
0x1c0001194  mov     [rsp+0D8h+var_B0], esi
0x1c0001198  cmp     esi, 2
0x1c000119b  jb      short loc_1C0001149
0x1c000119d  or      dword ptr [rbx+4], 10h
0x1c00011a1  jmp     short loc_1C0001149
0x1c00011a3  mov     rcx, [rdi+0B8h]
0x1c00011aa  and     byte ptr [rcx+3], 0FEh
0x1c00011ae  lea     rdx, [rsp+0D8h+Event]; Event
0x1c00011b3  mov     rcx, rdi; Irp
0x1c00011b6  call    RefsWaitForOplockCompletionEvent
0x1c00011bb  nop
0x1c00011bc  jmp     loc_1C006C654
0x1c00011c1  jmp     short loc_1C000121A
0x1c00011c3  mov     r8d, eax
0x1c00011c6  mov     rdi, [rsp+0D8h+var_A0]
0x1c00011cb  cmp     eax, 0C0000123h
0x1c00011d0  jnz     short loc_1C00011EB
0x1c00011d2  mov     rax, [rdi+0B8h]
0x1c00011d9  cmp     dword ptr [rax+10h], 14h
0x1c00011dd  jnz     short loc_1C00011EB
0x1c00011df  xor     r8d, r8d
0x1c00011e2  mov     rax, [rsp+0D8h+Context]
0x1c00011e7  and     [rax+10h], r8d
0x1c00011eb  mov     rdx, rdi
0x1c00011ee  mov     rcx, [rsp+0D8h+Context]
0x1c00011f3  call    RefsProcessException
0x1c00011f8  mov     ebx, eax
0x1c00011fa  mov     [rsp+0D8h+var_AC], eax
0x1c00011fe  mov     r15d, 1
0x1c0001204  mov     r14, [rsp+0D8h+var_90]
0x1c0001209  mov     esi, [rsp+0D8h+var_B0]
0x1c000120d  mov     r13, r14
0x1c0001210  mov     r12d, [rsp+0D8h+var_A8]
0x1c0001215  jmp     loc_1C006C654
0x1c000121a  test    r12d, r12d
0x1c000121d  jnz     loc_1C006C689
0x1c0001223  call    cs:__imp_KeLeaveCriticalRegion
0x1c000122a  nop     dword ptr [rax+rax+00h]
0x1c000122f  mov     eax, ebx
0x1c0001231  mov     rcx, [rsp+0D8h+var_30]
0x1c0001239  xor     rcx, rsp; StackCookie
0x1c000123c  call    __security_check_cookie
0x1c0001241  lea     r11, [rsp+0D8h+var_28]
0x1c0001249  mov     rbx, [r11+30h]
0x1c000124d  mov     rsi, [r11+40h]
0x1c0001251  mov     rsp, r11
0x1c0001254  pop     r15
0x1c0001256  pop     r14
0x1c0001258  pop     r13
0x1c000125a  pop     r12
0x1c000125c  pop     rdi
0x1c000125d  retn
0x1c006b4d0  push    rbp
0x1c006b4d2  sub     rsp, 20h
0x1c006b4d6  mov     rbp, rdx
0x1c006b4d9  mov     rdx, rcx
0x1c006b4dc  mov     rcx, [rbp+20h]
0x1c006b4e0  call    RefsExceptionFilter
0x1c006b4e5  nop
0x1c006b4e6  add     rsp, 20h
0x1c006b4ea  pop     rbp
0x1c006b4eb  retn
0x1c006c654  cmp     ebx, 0C00000D8h
0x1c006c65a  jz      loc_1C00010E1
0x1c006c660  cmp     ebx, 0C00001A8h
0x1c006c666  jz      loc_1C00010E1
0x1c006c66c  cmp     ebx, 0C0000188h
0x1c006c672  jz      loc_1C00010E1
0x1c006c678  cmp     ebx, 367h
0x1c006c67e  jz      loc_1C00010E1
0x1c006c684  jmp     loc_1C000121A
0x1c006c689  mov     rcx, [rsp+0D8h+var_98]
0x1c006c68e  call    cs:__imp_IoClearActivityIdThread
0x1c006c695  nop     dword ptr [rax+rax+00h]
0x1c006c69a  nop
0x1c006c69b  jmp     loc_1C0001223
```
