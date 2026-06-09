# MouHid_PowerCompletion

- ea: `0x140002370`
- end: `0x1400025c2`
- name: `MouHid_PowerCompletion`
- size: `594`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001464`
- `0x14000171c`
- `0x140002370`
- `0x1400026d0`
- `0x14000292c`
- `0x140002d28`
- `0x1400047a0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000254d`
- `ntoskrnl!KeSetEvent` at `0x14000254d`
- `ntoskrnl!KeResetEvent` at `0x14000249f`
- `ntoskrnl!KeResetEvent` at `0x14000249f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140002572`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140002572`

## pseudocode

```c
__int64 __fastcall MouHid_PowerCompletion(__int64 a1, __int64 a2, int a3)
{
  __int64 *v5; // rdx
  __int64 v6; // rax
  int v7; // r14d
  __int64 v8; // rbx
  int v9; // edi
  signed __int32 v10; // eax
  signed __int32 v11; // edi
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  int v15; // eax
  int v16; // edx
  int v17; // edx
  int v19; // [rsp+20h] [rbp-58h]

  v5 = WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v5) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v5,
      4,
      23,
      (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids);
    v5 = WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids;
  }
  v6 = *(_QWORD *)(a2 + 184);
  v7 = *(_DWORD *)(a2 + 48);
  v8 = *(_QWORD *)(a1 + 64);
  if ( *(_BYTE *)(v6 + 1) == 2 )
  {
    v9 = *(_DWORD *)(v6 + 16);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 4;
      WPP_RECORDER_SF_qqd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v5,
        4,
        24,
        (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids,
        a1,
        a2,
        *(_DWORD *)(v6 + 24) - 1);
    }
    if ( v9 == 1 && *(_DWORD *)(v8 + 40) == 1 && v7 >= 0 && *(_QWORD *)(v8 + 128) )
    {
      v10 = _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 56), 3, 3);
      v11 = v10;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qL(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)v5, a3, 25, v19, a1, v10);
      if ( v11 == 3 )
      {
        KeResetEvent((PRKEVENT)(v8 + 192));
        if ( _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 136), 2, 1) == 1 )
        {
          v15 = MouHid_SetResolutionMultipliers(v8);
          _InterlockedExchange((volatile __int32 *)(v8 + 56), (v15 != -1073741637) + 1);
          _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 136), 1, 2);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v16) = 4;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v16,
              4,
              26,
              (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids,
              v15);
          }
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_L(WPP_GLOBAL_Control->DeviceExtension, v12, v13, v14, v19, 3);
        }
        KeSetEvent((PRKEVENT)(v8 + 192), 0, 0);
      }
    }
  }
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v8 + 240), (PVOID)a2, 0x20u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v17) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      4,
      28,
      (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140002370  push    rbx
0x140002372  push    rbp
0x140002373  push    rsi
0x140002374  push    rdi
0x140002375  push    r12
0x140002377  push    r14
0x140002379  push    r15
0x14000237b  sub     rsp, 40h
0x14000237f  mov     rsi, rdx
0x140002382  mov     rbp, rcx
0x140002385  lea     r12, WPP_RECORDER_INITIALIZED
0x14000238c  xor     r15d, r15d
0x14000238f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002396  lea     rdx, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x14000239d  jz      short loc_1400023CC
0x14000239f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023a6  cmp     [rcx+48h], r15w
0x1400023ab  jz      short loc_1400023CC
0x1400023ad  mov     rcx, [rcx+40h]
0x1400023b1  lea     r9d, [r15+17h]
0x1400023b5  mov     [rsp+78h+var_58], rdx
0x1400023ba  lea     r8d, [r15+4]
0x1400023be  mov     dl, 5
0x1400023c0  call    WPP_RECORDER_SF_
0x1400023c5  lea     rdx, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x1400023cc  mov     rax, [rsi+0B8h]
0x1400023d3  mov     r14d, [rsi+30h]
0x1400023d7  mov     rbx, [rbp+40h]
0x1400023db  cmp     byte ptr [rax+1], 2
0x1400023df  jnz     loc_14000255B
0x1400023e5  mov     edi, [rax+10h]
0x1400023e8  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400023ef  mov     ecx, 1
0x1400023f4  jz      short loc_14000242E
0x1400023f6  mov     eax, [rax+18h]
0x1400023f9  lea     r8d, [rcx+3]
0x1400023fd  sub     eax, ecx
0x1400023ff  lea     r9d, [rcx+17h]
0x140002403  mov     rcx, cs:WPP_GLOBAL_Control
0x14000240a  mov     [rsp+78h+var_40], eax
0x14000240e  mov     [rsp+78h+var_48], rsi
0x140002413  mov     [rsp+78h+var_50], rbp
0x140002418  mov     rcx, [rcx+40h]
0x14000241c  mov     [rsp+78h+var_58], rdx
0x140002421  mov     dl, r8b
0x140002424  call    WPP_RECORDER_SF_qqd
0x140002429  mov     ecx, 1
0x14000242e  cmp     edi, 1
0x140002431  jnz     loc_14000255B
0x140002437  cmp     [rbx+28h], ecx
0x14000243a  jnz     loc_14000255B
0x140002440  test    r14d, r14d
0x140002443  js      loc_14000255B
0x140002449  cmp     [rbx+80h], r15
0x140002450  jz      loc_14000255B
0x140002456  lea     ecx, [rdi+2]
0x140002459  mov     eax, ecx
0x14000245b  lock cmpxchg [rbx+38h], ecx
0x140002460  mov     edi, eax
0x140002462  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140002469  jz      short loc_14000248D
0x14000246b  lea     r9d, [rcx+16h]
0x14000246f  mov     dword ptr [rsp+78h+var_48], eax
0x140002473  mov     rcx, cs:WPP_GLOBAL_Control
0x14000247a  mov     [rsp+78h+var_50], rbp
0x14000247f  mov     rcx, [rcx+40h]
0x140002483  call    WPP_RECORDER_SF_qL
0x140002488  mov     ecx, 3
0x14000248d  cmp     edi, ecx
0x14000248f  jnz     loc_14000255B
0x140002495  lea     rdi, [rbx+0C0h]
0x14000249c  mov     rcx, rdi; Event
0x14000249f  call    cs:__imp_KeResetEvent
0x1400024a6  nop     dword ptr [rax+rax+00h]
0x1400024ab  mov     ebp, 1
0x1400024b0  mov     eax, ebp
0x1400024b2  lea     ecx, [rbp+1]
0x1400024b5  lock cmpxchg [rbx+88h], ecx
0x1400024bd  jnz     short loc_14000251D
0x1400024bf  mov     rcx, rbx
0x1400024c2  call    MouHid_SetResolutionMultipliers
0x1400024c7  mov     ecx, eax
0x1400024c9  mov     eax, r15d
0x1400024cc  cmp     ecx, 0C00000BBh
0x1400024d2  setnz   al
0x1400024d5  add     eax, ebp
0x1400024d7  xchg    eax, [rbx+38h]
0x1400024da  lea     eax, [rbp+1]
0x1400024dd  lock cmpxchg [rbx+88h], ebp
0x1400024e5  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400024ec  lea     rbp, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x1400024f3  jz      short loc_140002545
0x1400024f5  mov     dword ptr [rsp+78h+var_50], ecx
0x1400024f9  mov     r9d, 1Ah
0x1400024ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140002506  mov     [rsp+78h+var_58], rbp
0x14000250b  lea     r8d, [r9-16h]
0x14000250f  mov     rcx, [rcx+40h]
0x140002513  mov     dl, r8b
0x140002516  call    WPP_RECORDER_SF_d
0x14000251b  jmp     short loc_140002545
0x14000251d  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140002524  jz      short loc_14000253E
0x140002526  mov     rcx, cs:WPP_GLOBAL_Control
0x14000252d  mov     dword ptr [rsp+78h+var_50], 3
0x140002535  mov     rcx, [rcx+40h]
0x140002539  call    WPP_RECORDER_SF_L
0x14000253e  lea     rbp, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x140002545  xor     r8d, r8d; Wait
0x140002548  xor     edx, edx; Increment
0x14000254a  mov     rcx, rdi; Event
0x14000254d  call    cs:__imp_KeSetEvent
0x140002554  nop     dword ptr [rax+rax+00h]
0x140002559  jmp     short loc_140002562
0x14000255b  lea     rbp, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x140002562  lea     rcx, [rbx+0F0h]; RemoveLock
0x140002569  mov     r8d, 20h ; ' '; RemlockSize
0x14000256f  mov     rdx, rsi; Tag
0x140002572  call    cs:__imp_IoReleaseRemoveLockEx
0x140002579  nop     dword ptr [rax+rax+00h]
0x14000257e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002585  jz      short loc_1400025AF
0x140002587  mov     rcx, cs:WPP_GLOBAL_Control
0x14000258e  cmp     [rcx+48h], r15w
0x140002593  jz      short loc_1400025AF
0x140002595  mov     rcx, [rcx+40h]
0x140002599  mov     r9d, 1Ch
0x14000259f  mov     dl, 5
0x1400025a1  mov     [rsp+78h+var_58], rbp
0x1400025a6  lea     r8d, [r9-18h]
0x1400025aa  call    WPP_RECORDER_SF_
0x1400025af  mov     eax, r14d
0x1400025b2  add     rsp, 40h
0x1400025b6  pop     r15
0x1400025b8  pop     r14
0x1400025ba  pop     r12
0x1400025bc  pop     rdi
0x1400025bd  pop     rsi
0x1400025be  pop     rbp
0x1400025bf  pop     rbx
0x1400025c0  retn
```
