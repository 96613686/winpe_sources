# MRxDAVPrecompleteUserModeRefreshTheServerLockRequest

- ea: `0x140005030`
- end: `0x140005293`
- name: `MRxDAVPrecompleteUserModeRefreshTheServerLockRequest`
- size: `611`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x140005030`
- `0x140027a20`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14000506f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400050a7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400050f3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000514f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400051a5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400051fb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000525f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000506f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400050a7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400050f3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000514f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400051a5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400051fb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000525f`

## pseudocode

```c
__int64 __fastcall MRxDAVPrecompleteUserModeRefreshTheServerLockRequest(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  __int64 v8; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v10; // rbx
  HANDLE v11; // rax
  __int64 v12; // rbx
  HANDLE v13; // rax
  int v14; // ebp
  __int64 v15; // rbx
  HANDLE v16; // rax
  int v17; // ebp
  __int64 v18; // rbx
  HANDLE v19; // rax
  int v20; // esi
  __int64 v21; // rbx
  HANDLE v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rbx
  HANDLE v25; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v8, 50, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v11 = PsGetCurrentThreadId();
      WPP_SF_qqq(v10, 51, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v11, a1, a2);
    }
  }
  if ( a5
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v13 = PsGetCurrentThreadId();
    WPP_SF_qqq(v12, 52, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v13, a1, a2);
  }
  if ( *(_QWORD *)(a3 + 632) )
  {
    v14 = UMRxFreeSecondaryBuffer(a1);
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v16 = PsGetCurrentThreadId();
        WPP_SF_qD(v15, 53, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v16, v14);
      }
    }
  }
  if ( *(_QWORD *)(a3 + 640) )
  {
    v17 = UMRxFreeSecondaryBuffer(a1);
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v19 = PsGetCurrentThreadId();
        WPP_SF_qD(v18, 54, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v19, v17);
      }
    }
  }
  if ( *(_QWORD *)(a3 + 648) )
  {
    v20 = UMRxFreeSecondaryBuffer(a1);
    if ( v20 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v21 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v22 = PsGetCurrentThreadId();
        WPP_SF_qD(v21, 55, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v22, v20);
      }
    }
  }
  if ( !a5 )
  {
    v23 = *(_QWORD *)(a2 + 216);
    *(_DWORD *)(v23 + 64) = *(_DWORD *)(a3 + 2312);
    *(_QWORD *)(v23 + 72) = MEMORY[0xFFFFF78000000320];
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v24 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v25 = PsGetCurrentThreadId();
    WPP_SF_q(v24, 56, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, v25);
  }
  return 1;
}

```

## disassembly

```asm
0x140005030  push    rbx
0x140005032  push    rbp
0x140005033  push    rsi
0x140005034  push    rdi
0x140005035  push    r12
0x140005037  push    r13
0x140005039  push    r15
0x14000503b  sub     rsp, 30h
0x14000503f  mov     rdi, r8
0x140005042  mov     r15, rdx
0x140005045  mov     rsi, rcx
0x140005048  mov     rbx, cs:WPP_GLOBAL_Control
0x14000504f  lea     r12, WPP_GLOBAL_Control
0x140005056  lea     r13, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x14000505d  cmp     rbx, r12
0x140005060  jz      short loc_1400050D0
0x140005062  test    dword ptr [rbx+2Ch], 4000h
0x140005069  jz      short loc_14000508E
0x14000506b  mov     rbx, [rbx+18h]
0x14000506f  call    cs:__imp_PsGetCurrentThreadId
0x140005076  nop     dword ptr [rax+rax+00h]
0x14000507b  mov     edx, 32h ; '2'
0x140005080  mov     r8, r13
0x140005083  mov     r9, rax
0x140005086  mov     rcx, rbx
0x140005089  call    WPP_SF_q
0x14000508e  mov     rbx, cs:WPP_GLOBAL_Control
0x140005095  cmp     rbx, r12
0x140005098  jz      short loc_1400050D0
0x14000509a  test    dword ptr [rbx+2Ch], 4000h
0x1400050a1  jz      short loc_1400050D0
0x1400050a3  mov     rbx, [rbx+18h]
0x1400050a7  call    cs:__imp_PsGetCurrentThreadId
0x1400050ae  nop     dword ptr [rax+rax+00h]
0x1400050b3  mov     edx, 33h ; '3'
0x1400050b8  mov     [rsp+68h+var_40], r15
0x1400050bd  mov     r9, rax
0x1400050c0  mov     [rsp+68h+var_48], rsi
0x1400050c5  mov     r8, r13
0x1400050c8  mov     rcx, rbx
0x1400050cb  call    WPP_SF_qqq
0x1400050d0  cmp     [rsp+68h+arg_20], 0
0x1400050d8  jz      short loc_14000511C
0x1400050da  mov     rbx, cs:WPP_GLOBAL_Control
0x1400050e1  cmp     rbx, r12
0x1400050e4  jz      short loc_14000511C
0x1400050e6  test    dword ptr [rbx+2Ch], 2000h
0x1400050ed  jz      short loc_14000511C
0x1400050ef  mov     rbx, [rbx+18h]
0x1400050f3  call    cs:__imp_PsGetCurrentThreadId
0x1400050fa  nop     dword ptr [rax+rax+00h]
0x1400050ff  mov     edx, 34h ; '4'
0x140005104  mov     [rsp+68h+var_40], r15
0x140005109  mov     r9, rax
0x14000510c  mov     [rsp+68h+var_48], rsi
0x140005111  mov     r8, r13
0x140005114  mov     rcx, rbx
0x140005117  call    WPP_SF_qqq
0x14000511c  mov     rdx, [rdi+278h]
0x140005123  test    rdx, rdx
0x140005126  jz      short loc_140005172
0x140005128  mov     rcx, rsi
0x14000512b  call    UMRxFreeSecondaryBuffer
0x140005130  mov     ebp, eax
0x140005132  test    eax, eax
0x140005134  jz      short loc_140005172
0x140005136  mov     rbx, cs:WPP_GLOBAL_Control
0x14000513d  cmp     rbx, r12
0x140005140  jz      short loc_140005172
0x140005142  test    dword ptr [rbx+2Ch], 2000h
0x140005149  jz      short loc_140005172
0x14000514b  mov     rbx, [rbx+18h]
0x14000514f  call    cs:__imp_PsGetCurrentThreadId
0x140005156  nop     dword ptr [rax+rax+00h]
0x14000515b  mov     edx, 35h ; '5'
0x140005160  mov     dword ptr [rsp+68h+var_48], ebp
0x140005164  mov     r9, rax
0x140005167  mov     r8, r13
0x14000516a  mov     rcx, rbx
0x14000516d  call    WPP_SF_qD
0x140005172  mov     rdx, [rdi+280h]
0x140005179  test    rdx, rdx
0x14000517c  jz      short loc_1400051C8
0x14000517e  mov     rcx, rsi
0x140005181  call    UMRxFreeSecondaryBuffer
0x140005186  mov     ebp, eax
0x140005188  test    eax, eax
0x14000518a  jz      short loc_1400051C8
0x14000518c  mov     rbx, cs:WPP_GLOBAL_Control
0x140005193  cmp     rbx, r12
0x140005196  jz      short loc_1400051C8
0x140005198  test    dword ptr [rbx+2Ch], 2000h
0x14000519f  jz      short loc_1400051C8
0x1400051a1  mov     rbx, [rbx+18h]
0x1400051a5  call    cs:__imp_PsGetCurrentThreadId
0x1400051ac  nop     dword ptr [rax+rax+00h]
0x1400051b1  mov     edx, 36h ; '6'
0x1400051b6  mov     dword ptr [rsp+68h+var_48], ebp
0x1400051ba  mov     r9, rax
0x1400051bd  mov     r8, r13
0x1400051c0  mov     rcx, rbx
0x1400051c3  call    WPP_SF_qD
0x1400051c8  mov     rdx, [rdi+288h]
0x1400051cf  test    rdx, rdx
0x1400051d2  jz      short loc_14000521E
0x1400051d4  mov     rcx, rsi
0x1400051d7  call    UMRxFreeSecondaryBuffer
0x1400051dc  mov     esi, eax
0x1400051de  test    eax, eax
0x1400051e0  jz      short loc_14000521E
0x1400051e2  mov     rbx, cs:WPP_GLOBAL_Control
0x1400051e9  cmp     rbx, r12
0x1400051ec  jz      short loc_14000521E
0x1400051ee  test    dword ptr [rbx+2Ch], 2000h
0x1400051f5  jz      short loc_14000521E
0x1400051f7  mov     rbx, [rbx+18h]
0x1400051fb  call    cs:__imp_PsGetCurrentThreadId
0x140005202  nop     dword ptr [rax+rax+00h]
0x140005207  mov     edx, 37h ; '7'
0x14000520c  mov     dword ptr [rsp+68h+var_48], esi
0x140005210  mov     r9, rax
0x140005213  mov     r8, r13
0x140005216  mov     rcx, rbx
0x140005219  call    WPP_SF_qD
0x14000521e  cmp     [rsp+68h+arg_20], 0
0x140005226  jnz     short loc_140005246
0x140005228  mov     eax, [rdi+908h]
0x14000522e  mov     rcx, [r15+0D8h]
0x140005235  mov     [rcx+40h], eax
0x140005238  mov     rax, ds:0FFFFF78000000320h
0x140005242  mov     [rcx+48h], rax
0x140005246  mov     rbx, cs:WPP_GLOBAL_Control
0x14000524d  cmp     rbx, r12
0x140005250  jz      short loc_14000527E
0x140005252  test    dword ptr [rbx+2Ch], 4000h
0x140005259  jz      short loc_14000527E
0x14000525b  mov     rbx, [rbx+18h]
0x14000525f  call    cs:__imp_PsGetCurrentThreadId
0x140005266  nop     dword ptr [rax+rax+00h]
0x14000526b  mov     edx, 38h ; '8'
0x140005270  mov     r8, r13
0x140005273  mov     r9, rax
0x140005276  mov     rcx, rbx
0x140005279  call    WPP_SF_q
0x14000527e  mov     eax, 1
0x140005283  add     rsp, 30h
0x140005287  pop     r15
0x140005289  pop     r13
0x14000528b  pop     r12
0x14000528d  pop     rdi
0x14000528e  pop     rsi
0x14000528f  pop     rbp
0x140005290  pop     rbx
0x140005291  retn
```
