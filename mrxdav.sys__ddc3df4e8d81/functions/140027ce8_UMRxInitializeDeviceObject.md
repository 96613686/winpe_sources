# UMRxInitializeDeviceObject

- ea: `0x140027ce8`
- end: `0x140027f15`
- name: `UMRxInitializeDeviceObject`
- size: `557`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140016d2c`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140027ce8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140027d1b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027d54`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027dac`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027edd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027d1b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027d54`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027dac`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027edd`
- `ntoskrnl!KeInitializeEvent` at `0x140027e22`
- `ntoskrnl!KeInitializeEvent` at `0x140027e95`
- `ntoskrnl!KeInitializeEvent` at `0x140027e22`
- `ntoskrnl!KeInitializeEvent` at `0x140027e95`
- `ntoskrnl!ExInitializeResourceLite` at `0x140027e4a`
- `ntoskrnl!ExInitializeResourceLite` at `0x140027e72`
- `ntoskrnl!ExInitializeResourceLite` at `0x140027e4a`
- `ntoskrnl!ExInitializeResourceLite` at `0x140027e72`
- `ntoskrnl!KeInitializeQueue` at `0x140027e5f`
- `ntoskrnl!KeInitializeQueue` at `0x140027e5f`
- `rdbss!RxCreateMidAtlas` at `0x140027d84`
- `rdbss!RxCreateMidAtlas` at `0x140027d84`

## pseudocode

```c
__int64 __fastcall UMRxInitializeDeviceObject(__int64 a1)
{
  __int64 v2; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v4; // rbx
  HANDLE v5; // rax
  PRX_MID_ATLAS MidAtlas; // rax
  __int64 v7; // rbx
  HANDLE v8; // rax
  __int64 v10; // rbx
  HANDLE v11; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v2 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v2, 115, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v5 = PsGetCurrentThreadId();
      WPP_SF_qq(v4, 116, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v5, a1);
    }
  }
  MidAtlas = RxCreateMidAtlas(0x400u, 0x200u);
  if ( MidAtlas )
  {
    *(_QWORD *)(a1 + 1312) = MidAtlas;
    *(_QWORD *)(a1 + 1328) = 0;
    *(_QWORD *)(a1 + 1384) = a1 + 1376;
    *(_QWORD *)(a1 + 1376) = a1 + 1376;
    *(_DWORD *)(a1 + 1320) = 1;
    *(_DWORD *)(a1 + 1336) = 0;
    KeInitializeEvent((PRKEVENT)(a1 + 1344), SynchronizationEvent, 0);
    qword_14000B198 = (__int64)&UMRxAsyncEngineContextList;
    UMRxAsyncEngineContextList = (__int64)&UMRxAsyncEngineContextList;
    ExInitializeResourceLite(&UMRxAsyncEngineContextListLock);
    KeInitializeQueue((PRKQUEUE)(a1 + 1392), 0);
    ExInitializeResourceLite((PERESOURCE)(a1 + 1456));
    *(_QWORD *)(a1 + 1560) = -100000000;
    KeInitializeEvent((PRKEVENT)(a1 + 1584), NotificationEvent, 0);
    *(_QWORD *)(a1 + 1608) = 0;
    *(_BYTE *)(a1 + 1616) = 1;
    *(_DWORD *)(a1 + 1620) = 9176;
    *(_WORD *)(a1 + 304) = 512;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v11 = PsGetCurrentThreadId();
      WPP_SF_qD(v10, 118, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v11, 0);
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v8 = PsGetCurrentThreadId();
      WPP_SF_qD(v7, 117, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v8, -1073741670);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140027ce8  push    rbx
0x140027cea  push    rbp
0x140027ceb  push    rdi
0x140027cec  push    r15
0x140027cee  sub     rsp, 38h
0x140027cf2  mov     rdi, rcx
0x140027cf5  mov     rbx, cs:WPP_GLOBAL_Control
0x140027cfc  lea     rbp, WPP_GLOBAL_Control
0x140027d03  mov     r15d, 200h
0x140027d09  cmp     rbx, rbp
0x140027d0c  jz      short loc_140027D7C
0x140027d0e  test    dword ptr [rbx+2Ch], 800h
0x140027d15  jz      short loc_140027D3E
0x140027d17  mov     rbx, [rbx+18h]
0x140027d1b  call    cs:__imp_PsGetCurrentThreadId
0x140027d22  nop     dword ptr [rax+rax+00h]
0x140027d27  mov     edx, 73h ; 's'
0x140027d2c  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027d33  mov     r9, rax
0x140027d36  mov     rcx, rbx
0x140027d39  call    WPP_SF_q
0x140027d3e  mov     rbx, cs:WPP_GLOBAL_Control
0x140027d45  cmp     rbx, rbp
0x140027d48  jz      short loc_140027D7C
0x140027d4a  test    [rbx+2Ch], r15d
0x140027d4e  jz      short loc_140027D7C
0x140027d50  mov     rbx, [rbx+18h]
0x140027d54  call    cs:__imp_PsGetCurrentThreadId
0x140027d5b  nop     dword ptr [rax+rax+00h]
0x140027d60  mov     edx, 74h ; 't'
0x140027d65  mov     [rsp+58h+var_38], rdi
0x140027d6a  mov     r9, rax
0x140027d6d  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027d74  mov     rcx, rbx
0x140027d77  call    WPP_SF_qq
0x140027d7c  mov     edx, r15d; InitialAllocation
0x140027d7f  mov     ecx, 400h; MaximumNumberOfEntries
0x140027d84  call    cs:__imp_RxCreateMidAtlas
0x140027d8b  nop     dword ptr [rax+rax+00h]
0x140027d90  test    rax, rax
0x140027d93  jnz     short loc_140027DE1
0x140027d95  mov     rbx, cs:WPP_GLOBAL_Control
0x140027d9c  cmp     rbx, rbp
0x140027d9f  jz      short loc_140027DD7
0x140027da1  mov     eax, [rbx+2Ch]
0x140027da4  test    al, al
0x140027da6  jns     short loc_140027DD7
0x140027da8  mov     rbx, [rbx+18h]
0x140027dac  call    cs:__imp_PsGetCurrentThreadId
0x140027db3  nop     dword ptr [rax+rax+00h]
0x140027db8  mov     edx, 75h ; 'u'
0x140027dbd  mov     dword ptr [rsp+58h+var_38], 0C000009Ah
0x140027dc5  mov     r9, rax
0x140027dc8  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027dcf  mov     rcx, rbx
0x140027dd2  call    WPP_SF_qD
0x140027dd7  mov     eax, 0C000009Ah
0x140027ddc  jmp     loc_140027F0A
0x140027de1  mov     [rdi+520h], rax
0x140027de8  lea     rcx, [rdi+540h]; Event
0x140027def  lea     rax, [rdi+560h]
0x140027df6  mov     qword ptr [rdi+530h], 0
0x140027e01  mov     ebx, 1
0x140027e06  mov     [rax+8], rax
0x140027e0a  mov     edx, ebx; Type
0x140027e0c  mov     [rax], rax
0x140027e0f  xor     r8d, r8d; State
0x140027e12  mov     [rdi+528h], ebx
0x140027e18  mov     dword ptr [rdi+538h], 0
0x140027e22  call    cs:__imp_KeInitializeEvent
0x140027e29  nop     dword ptr [rax+rax+00h]
0x140027e2e  lea     rax, UMRxAsyncEngineContextList
0x140027e35  lea     rcx, UMRxAsyncEngineContextListLock; Resource
0x140027e3c  mov     cs:qword_14000B198, rax
0x140027e43  mov     cs:UMRxAsyncEngineContextList, rax
0x140027e4a  call    cs:__imp_ExInitializeResourceLite
0x140027e51  nop     dword ptr [rax+rax+00h]
0x140027e56  lea     rcx, [rdi+570h]; Queue
0x140027e5d  xor     edx, edx; Count
0x140027e5f  call    cs:__imp_KeInitializeQueue
0x140027e66  nop     dword ptr [rax+rax+00h]
0x140027e6b  lea     rcx, [rdi+5B0h]; Resource
0x140027e72  call    cs:__imp_ExInitializeResourceLite
0x140027e79  nop     dword ptr [rax+rax+00h]
0x140027e7e  lea     rcx, [rdi+630h]; Event
0x140027e85  mov     qword ptr [rdi+618h], 0FFFFFFFFFA0A1F00h
0x140027e90  xor     r8d, r8d; State
0x140027e93  xor     edx, edx; Type
0x140027e95  call    cs:__imp_KeInitializeEvent
0x140027e9c  nop     dword ptr [rax+rax+00h]
0x140027ea1  mov     qword ptr [rdi+648h], 0
0x140027eac  mov     [rdi+650h], bl
0x140027eb2  mov     dword ptr [rdi+654h], 23D8h
0x140027ebc  mov     [rdi+130h], r15w
0x140027ec4  mov     rbx, cs:WPP_GLOBAL_Control
0x140027ecb  cmp     rbx, rbp
0x140027ece  jz      short loc_140027F08
0x140027ed0  test    dword ptr [rbx+2Ch], 800h
0x140027ed7  jz      short loc_140027F08
0x140027ed9  mov     rbx, [rbx+18h]
0x140027edd  call    cs:__imp_PsGetCurrentThreadId
0x140027ee4  nop     dword ptr [rax+rax+00h]
0x140027ee9  mov     edx, 76h ; 'v'
0x140027eee  mov     dword ptr [rsp+58h+var_38], 0
0x140027ef6  mov     r9, rax
0x140027ef9  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027f00  mov     rcx, rbx
0x140027f03  call    WPP_SF_qD
0x140027f08  xor     eax, eax
0x140027f0a  add     rsp, 38h
0x140027f0e  pop     r15
0x140027f10  pop     rdi
0x140027f11  pop     rbp
0x140027f12  pop     rbx
0x140027f13  retn
```
