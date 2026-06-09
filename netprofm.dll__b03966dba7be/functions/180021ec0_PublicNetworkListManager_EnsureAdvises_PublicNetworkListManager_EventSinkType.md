# PublicNetworkListManager::EnsureAdvises(PublicNetworkListManager::EventSinkType)

- ea: `0x180021ec0`
- end: `0x1800220c1`
- name: `?EnsureAdvises@PublicNetworkListManager@@AEAAJW4EventSinkType@1@@Z`
- size: `513`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `6`
- callee_count: `8`
- tags: ``

## callers

- `0x18001f8d0`
- `0x180027630`
- `0x180027900`
- `0x180027bd0`
- `0x180027f80`
- `0x180028250`

## callees

- `0x180006770`
- `0x180006810`
- `0x180009d28`
- `0x180021ec0`
- `0x18002dc9c`
- `0x18002de04`
- `0x18002df6c`
- `0x18002e0d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800220ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800220ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021f0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021f0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PublicNetworkListManager::EnsureAdvises(__int64 a1, int a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // eax
  unsigned int v7; // ebx
  PVOID *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 616));
  v5 = *(unsigned int *)(a1 + 656);
  if ( ((unsigned int)v5 & a2) != 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v7 = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_39;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_36;
    v10 = 80;
    goto LABEL_34;
  }
  switch ( a2 )
  {
    case 0:
      goto LABEL_30;
    case 1:
      v6 = PublicNetworkListManager::PrivateNetworkEventSync::AdviseNotifyNetworkListManagerEvents(*(PublicNetworkListManager::PrivateNetworkEventSync **)(a1 + 216));
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_39;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_36;
        v9 = 78;
        goto LABEL_14;
      }
      goto LABEL_27;
    case 2:
      v6 = PublicNetworkListManager::PrivateNetworkEventSync::AdviseNotifyNetworkEvents(*(PublicNetworkListManager::PrivateNetworkEventSync **)(a1 + 216));
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_39;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_36;
        v9 = 75;
        goto LABEL_14;
      }
      goto LABEL_27;
    case 4:
      v6 = PublicNetworkListManager::PrivateNetworkEventSync::AdviseNotifyNetworkInterfaceEvents(*(PublicNetworkListManager::PrivateNetworkEventSync **)(a1 + 216));
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_39;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_36;
        v9 = 77;
        goto LABEL_14;
      }
      goto LABEL_27;
  }
  if ( a2 != 8 )
  {
LABEL_30:
    v7 = -2147024809;
    goto LABEL_35;
  }
  v6 = PublicNetworkListManager::PrivateNetworkEventSync::AdviseNotifyNetworkGlobalCostEvents(*(PublicNetworkListManager::PrivateNetworkEventSync **)(a1 + 216));
  v7 = v6;
  if ( v6 >= 0 )
  {
LABEL_27:
    *(_DWORD *)(a1 + 656) |= a2;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_39;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_36;
    v5 = *(unsigned int *)(a1 + 656);
    v10 = 79;
LABEL_34:
    WPP_SF_DD(v8[2], v10, v4, v5, a2);
    goto LABEL_35;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_39;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 76;
LABEL_14:
    WPP_SF_d(v8[2], v9, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, (unsigned int)v6);
LABEL_35:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_36:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    WPP_SF_d(v8[2], 81, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids, v7);
LABEL_39:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 616));
  return v7;
}

```

## disassembly

```asm
0x180021ec0  push    rbx
0x180021ec2  push    rbp
0x180021ec3  push    rsi
0x180021ec4  push    rdi
0x180021ec5  push    r14
0x180021ec7  push    r15
0x180021ec9  sub     rsp, 38h
0x180021ecd  mov     esi, edx
0x180021ecf  mov     rdi, rcx
0x180021ed2  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ed9  lea     r14, WPP_GLOBAL_Control
0x180021ee0  lea     r15, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180021ee7  cmp     rcx, r14
0x180021eea  jz      short loc_180021F03
0x180021eec  test    byte ptr [rcx+1Ch], 8
0x180021ef0  jz      short loc_180021F03
0x180021ef2  mov     rcx, [rcx+10h]
0x180021ef6  mov     edx, 4Ah ; 'J'
0x180021efb  mov     r8, r15
0x180021efe  call    WPP_SF_
0x180021f03  lea     rbp, [rdi+268h]
0x180021f0a  mov     rcx, rbp; lpCriticalSection
0x180021f0d  call    cs:__imp_EnterCriticalSection
0x180021f13  mov     r9d, [rdi+290h]
0x180021f1a  test    esi, r9d
0x180021f1d  jnz     loc_18002205F
0x180021f23  mov     ecx, esi
0x180021f25  test    esi, esi
0x180021f27  jz      loc_180022058
0x180021f2d  sub     ecx, 1
0x180021f30  jz      loc_180022000
0x180021f36  sub     ecx, 1
0x180021f39  jz      loc_180021FCD
0x180021f3f  sub     ecx, 2
0x180021f42  jz      short loc_180021F96
0x180021f44  cmp     ecx, 4
0x180021f47  jnz     loc_180022058
0x180021f4d  mov     rcx, [rdi+0D8h]; this
0x180021f54  call    ?AdviseNotifyNetworkGlobalCostEvents@PrivateNetworkEventSync@PublicNetworkListManager@@QEAAJXZ; PublicNetworkListManager::PrivateNetworkEventSync::AdviseNotifyNetworkGlobalCostEvents(void)
0x180021f59  mov     ebx, eax
0x180021f5b  test    eax, eax
0x180021f5d  jns     loc_180022032
0x180021f63  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f6a  cmp     rcx, r14
0x180021f6d  jz      loc_1800220A9
0x180021f73  test    byte ptr [rcx+1Ch], 1
0x180021f77  jz      loc_18002208A
0x180021f7d  mov     edx, 4Ch ; 'L'
0x180021f82  mov     rcx, [rcx+10h]
0x180021f86  mov     r9d, eax
0x180021f89  mov     r8, r15
0x180021f8c  call    WPP_SF_d
0x180021f91  jmp     loc_180022083
0x180021f96  mov     rcx, [rdi+0D8h]; this
0x180021f9d  call    ?AdviseNotifyNetworkInterfaceEvents@PrivateNetworkEventSync@PublicNetworkListManager@@QEAAJXZ; PublicNetworkListManager::PrivateNetworkEventSync::AdviseNotifyNetworkInterfaceEvents(void)
0x180021fa2  mov     ebx, eax
0x180021fa4  test    eax, eax
0x180021fa6  jns     loc_180022032
0x180021fac  mov     rcx, cs:WPP_GLOBAL_Control
0x180021fb3  cmp     rcx, r14
0x180021fb6  jz      loc_1800220A9
0x180021fbc  test    byte ptr [rcx+1Ch], 1
0x180021fc0  jz      loc_18002208A
0x180021fc6  mov     edx, 4Dh ; 'M'
0x180021fcb  jmp     short loc_180021F82
0x180021fcd  mov     rcx, [rdi+0D8h]; this
0x180021fd4  call    ?AdviseNotifyNetworkEvents@PrivateNetworkEventSync@PublicNetworkListManager@@QEAAJXZ; PublicNetworkListManager::PrivateNetworkEventSync::AdviseNotifyNetworkEvents(void)
0x180021fd9  mov     ebx, eax
0x180021fdb  test    eax, eax
0x180021fdd  jns     short loc_180022032
0x180021fdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180021fe6  cmp     rcx, r14
0x180021fe9  jz      loc_1800220A9
0x180021fef  test    byte ptr [rcx+1Ch], 1
0x180021ff3  jz      loc_18002208A
0x180021ff9  mov     edx, 4Bh ; 'K'
0x180021ffe  jmp     short loc_180021F82
0x180022000  mov     rcx, [rdi+0D8h]; this
0x180022007  call    ?AdviseNotifyNetworkListManagerEvents@PrivateNetworkEventSync@PublicNetworkListManager@@QEAAJXZ; PublicNetworkListManager::PrivateNetworkEventSync::AdviseNotifyNetworkListManagerEvents(void)
0x18002200c  mov     ebx, eax
0x18002200e  test    eax, eax
0x180022010  jns     short loc_180022032
0x180022012  mov     rcx, cs:WPP_GLOBAL_Control
0x180022019  cmp     rcx, r14
0x18002201c  jz      loc_1800220A9
0x180022022  test    byte ptr [rcx+1Ch], 1
0x180022026  jz      short loc_18002208A
0x180022028  mov     edx, 4Eh ; 'N'
0x18002202d  jmp     loc_180021F82
0x180022032  or      [rdi+290h], esi
0x180022038  mov     rcx, cs:WPP_GLOBAL_Control
0x18002203f  cmp     rcx, r14
0x180022042  jz      short loc_1800220A9
0x180022044  test    byte ptr [rcx+1Ch], 8
0x180022048  jz      short loc_18002208A
0x18002204a  mov     r9d, [rdi+290h]
0x180022051  mov     edx, 4Fh ; 'O'
0x180022056  jmp     short loc_180022076
0x180022058  mov     ebx, 80070057h
0x18002205d  jmp     short loc_180022083
0x18002205f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022066  xor     ebx, ebx
0x180022068  cmp     rcx, r14
0x18002206b  jz      short loc_1800220A9
0x18002206d  test    byte ptr [rcx+1Ch], 8
0x180022071  jz      short loc_18002208A
0x180022073  lea     edx, [rbx+50h]
0x180022076  mov     rcx, [rcx+10h]
0x18002207a  mov     [rsp+68h+var_48], esi
0x18002207e  call    WPP_SF_DD
0x180022083  mov     rcx, cs:WPP_GLOBAL_Control
0x18002208a  cmp     rcx, r14
0x18002208d  jz      short loc_1800220A9
0x18002208f  test    byte ptr [rcx+1Ch], 8
0x180022093  jz      short loc_1800220A9
0x180022095  mov     rcx, [rcx+10h]
0x180022099  mov     edx, 51h ; 'Q'
0x18002209e  mov     r9d, ebx
0x1800220a1  mov     r8, r15
0x1800220a4  call    WPP_SF_d
0x1800220a9  mov     rcx, rbp; lpCriticalSection
0x1800220ac  call    cs:__imp_LeaveCriticalSection
0x1800220b2  mov     eax, ebx
0x1800220b4  add     rsp, 38h
0x1800220b8  pop     r15
0x1800220ba  pop     r14
0x1800220bc  pop     rdi
0x1800220bd  pop     rsi
0x1800220be  pop     rbp
0x1800220bf  pop     rbx
0x1800220c0  retn
```
