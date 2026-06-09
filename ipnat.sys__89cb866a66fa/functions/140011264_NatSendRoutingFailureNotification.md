# NatSendRoutingFailureNotification

- ea: `0x140011264`
- end: `0x140011505`
- name: `NatSendRoutingFailureNotification`
- size: `673`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140029850`
- `0x140029ce0`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x140002200`
- `0x140011264`
- `0x140011624`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400114be`
- `ntoskrnl!IofCompleteRequest` at `0x1400114be`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011387`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001142d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011387`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001142d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400112bb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400112bb`

## pseudocode

```c
void __fastcall NatSendRoutingFailureNotification(unsigned int a1, unsigned int a2)
{
  KIRQL v4; // di
  __int64 v5; // rcx
  __int64 *v6; // rdx
  __int64 v7; // rbx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  __int64 **v10; // rax
  unsigned int *v11; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids, a1, a2);
  }
  v4 = KeAcquireSpinLockRaiseToDpc(&NotificationLock);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids, 0);
  }
  v5 = NotificationList;
  if ( (__int64 *)NotificationList == &NotificationList )
  {
LABEL_12:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids);
    }
  }
  else
  {
    while ( 1 )
    {
      v6 = *(__int64 **)v5;
      v7 = v5 - 168;
      if ( !**(_DWORD **)(v5 - 168 + 24) )
        break;
      v5 = *(_QWORD *)v5;
      if ( v6 == &NotificationList )
        goto LABEL_12;
    }
    if ( v6[1] != v5 || (v10 = *(__int64 ***)(v5 + 8), *v10 != (__int64 *)v5) )
      __fastfail(3u);
    *v10 = v6;
    v6[1] = (__int64)v10;
    *(_QWORD *)(v5 + 8) = v5;
    *(_QWORD *)v5 = v5;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids);
    }
    if ( v7 )
    {
      KeReleaseSpinLock(&NotificationLock, v4);
      if ( _InterlockedExchange64((volatile __int64 *)(v7 + 104), 0) )
      {
        v11 = *(unsigned int **)(v7 + 24);
        *v11 = a1;
        v11[1] = a2;
        *(_DWORD *)(v7 + 48) = 0;
        *(_QWORD *)(v7 + 56) = 8;
        IofCompleteRequest((PIRP)v7, 0);
        ReleaseComponentReference();
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          v9 = 33;
          goto LABEL_24;
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          v9 = 32;
          goto LABEL_24;
        }
      }
      return;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids);
  }
  KeReleaseSpinLock(&NotificationLock, v4);
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    v9 = 30;
LABEL_24:
    WPP_SF_(v8->AttachedDevice, v9, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids);
  }
}

```

## disassembly

```asm
0x140011264  push    rbx
0x140011266  push    rbp
0x140011267  push    rsi
0x140011268  push    rdi
0x140011269  push    r12
0x14001126b  push    r15
0x14001126d  sub     rsp, 38h
0x140011271  mov     esi, edx
0x140011273  mov     ebp, ecx
0x140011275  mov     rcx, cs:WPP_GLOBAL_Control
0x14001127c  lea     r12, WPP_GLOBAL_Control
0x140011283  lea     r15, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids
0x14001128a  cmp     rcx, r12
0x14001128d  jz      short loc_1400112B4
0x14001128f  mov     eax, [rcx+2Ch]
0x140011292  test    al, 1
0x140011294  jz      short loc_1400112B4
0x140011296  cmp     byte ptr [rcx+29h], 6
0x14001129a  jb      short loc_1400112B4
0x14001129c  mov     rcx, [rcx+18h]
0x1400112a0  mov     edx, 1Ch
0x1400112a5  mov     r9d, ebp
0x1400112a8  mov     [rsp+68h+var_48], esi
0x1400112ac  mov     r8, r15
0x1400112af  call    WPP_SF_dd
0x1400112b4  lea     rcx, NotificationLock; SpinLock
0x1400112bb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400112c2  nop     dword ptr [rax+rax+00h]
0x1400112c7  mov     dil, al
0x1400112ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400112d1  cmp     rcx, r12
0x1400112d4  jz      short loc_1400112F7
0x1400112d6  mov     eax, [rcx+2Ch]
0x1400112d9  test    al, 1
0x1400112db  jz      short loc_1400112F7
0x1400112dd  cmp     byte ptr [rcx+29h], 6
0x1400112e1  jb      short loc_1400112F7
0x1400112e3  mov     rcx, [rcx+18h]
0x1400112e7  mov     edx, 0Eh
0x1400112ec  xor     r9d, r9d
0x1400112ef  mov     r8, r15
0x1400112f2  call    WPP_SF_d
0x1400112f7  mov     rcx, cs:NotificationList
0x1400112fe  lea     r8, NotificationList
0x140011305  cmp     rcx, r8
0x140011308  jz      short loc_140011329
0x14001130a  mov     rdx, [rcx]
0x14001130d  lea     rbx, [rcx-0A8h]
0x140011314  mov     rax, [rbx+18h]
0x140011318  cmp     dword ptr [rax], 0
0x14001131b  jz      loc_1400113CB
0x140011321  mov     rcx, rdx
0x140011324  cmp     rdx, r8
0x140011327  jnz     short loc_14001130A
0x140011329  mov     rcx, cs:WPP_GLOBAL_Control
0x140011330  cmp     rcx, r12
0x140011333  jz      short loc_140011353
0x140011335  mov     eax, [rcx+2Ch]
0x140011338  test    al, 1
0x14001133a  jz      short loc_140011353
0x14001133c  cmp     byte ptr [rcx+29h], 6
0x140011340  jb      short loc_140011353
0x140011342  mov     rcx, [rcx+18h]
0x140011346  mov     edx, 10h
0x14001134b  mov     r8, r15
0x14001134e  call    WPP_SF_
0x140011353  mov     rcx, cs:WPP_GLOBAL_Control
0x14001135a  cmp     rcx, r12
0x14001135d  jz      short loc_14001137D
0x14001135f  mov     eax, [rcx+2Ch]
0x140011362  test    al, 1
0x140011364  jz      short loc_14001137D
0x140011366  cmp     byte ptr [rcx+29h], 2
0x14001136a  jb      short loc_14001137D
0x14001136c  mov     rcx, [rcx+18h]
0x140011370  mov     edx, 1Dh
0x140011375  mov     r8, r15
0x140011378  call    WPP_SF_
0x14001137d  mov     dl, dil; NewIrql
0x140011380  lea     rcx, NotificationLock; SpinLock
0x140011387  call    cs:__imp_KeReleaseSpinLock
0x14001138e  nop     dword ptr [rax+rax+00h]
0x140011393  mov     rcx, cs:WPP_GLOBAL_Control
0x14001139a  cmp     rcx, r12
0x14001139d  jz      short loc_1400113BD
0x14001139f  mov     eax, [rcx+2Ch]
0x1400113a2  test    al, 1
0x1400113a4  jz      short loc_1400113BD
0x1400113a6  cmp     byte ptr [rcx+29h], 6
0x1400113aa  jb      short loc_1400113BD
0x1400113ac  mov     edx, 1Eh
0x1400113b1  mov     rcx, [rcx+18h]
0x1400113b5  mov     r8, r15
0x1400113b8  call    WPP_SF_
0x1400113bd  add     rsp, 38h
0x1400113c1  pop     r15
0x1400113c3  pop     r12
0x1400113c5  pop     rdi
0x1400113c6  pop     rsi
0x1400113c7  pop     rbp
0x1400113c8  pop     rbx
0x1400113c9  retn
0x1400113cb  cmp     [rdx+8], rcx
0x1400113cf  jnz     loc_1400114FE
0x1400113d5  mov     rax, [rcx+8]
0x1400113d9  cmp     [rax], rcx
0x1400113dc  jnz     loc_1400114FE
0x1400113e2  mov     [rax], rdx
0x1400113e5  mov     [rdx+8], rax
0x1400113e9  mov     [rcx+8], rcx
0x1400113ed  mov     [rcx], rcx
0x1400113f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400113f7  cmp     rcx, r12
0x1400113fa  jz      short loc_14001141A
0x1400113fc  mov     eax, [rcx+2Ch]
0x1400113ff  test    al, 1
0x140011401  jz      short loc_14001141A
0x140011403  cmp     byte ptr [rcx+29h], 6
0x140011407  jb      short loc_14001141A
0x140011409  mov     rcx, [rcx+18h]
0x14001140d  mov     edx, 0Fh
0x140011412  mov     r8, r15
0x140011415  call    WPP_SF_
0x14001141a  test    rbx, rbx
0x14001141d  jz      loc_140011353
0x140011423  mov     dl, dil; NewIrql
0x140011426  lea     rcx, NotificationLock; SpinLock
0x14001142d  call    cs:__imp_KeReleaseSpinLock
0x140011434  nop     dword ptr [rax+rax+00h]
0x140011439  xor     eax, eax
0x14001143b  xchg    rax, [rbx+68h]
0x14001143f  test    rax, rax
0x140011442  jnz     short loc_1400114A1
0x140011444  mov     rcx, cs:WPP_GLOBAL_Control
0x14001144b  cmp     rcx, r12
0x14001144e  jz      loc_1400113BD
0x140011454  mov     eax, [rcx+2Ch]
0x140011457  test    al, 1
0x140011459  jz      short loc_140011472
0x14001145b  cmp     byte ptr [rcx+29h], 2
0x14001145f  jb      short loc_140011472
0x140011461  mov     rcx, [rcx+18h]
0x140011465  mov     edx, 1Fh
0x14001146a  mov     r8, r15
0x14001146d  call    WPP_SF_
0x140011472  mov     rcx, cs:WPP_GLOBAL_Control
0x140011479  cmp     rcx, r12
0x14001147c  jz      loc_1400113BD
0x140011482  mov     eax, [rcx+2Ch]
0x140011485  test    al, 1
0x140011487  jz      loc_1400113BD
0x14001148d  cmp     byte ptr [rcx+29h], 6
0x140011491  jb      loc_1400113BD
0x140011497  mov     edx, 20h ; ' '
0x14001149c  jmp     loc_1400113B1
0x1400114a1  mov     rax, [rbx+18h]
0x1400114a5  xor     edx, edx; PriorityBoost
0x1400114a7  mov     rcx, rbx; Irp
0x1400114aa  mov     [rax], ebp
0x1400114ac  mov     [rax+4], esi
0x1400114af  mov     dword ptr [rbx+30h], 0
0x1400114b6  mov     qword ptr [rbx+38h], 8
0x1400114be  call    cs:__imp_IofCompleteRequest
0x1400114c5  nop     dword ptr [rax+rax+00h]
0x1400114ca  call    ReleaseComponentReference
0x1400114cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400114d6  cmp     rcx, r12
0x1400114d9  jz      loc_1400113BD
0x1400114df  mov     eax, [rcx+2Ch]
0x1400114e2  test    al, 1
0x1400114e4  jz      loc_1400113BD
0x1400114ea  cmp     byte ptr [rcx+29h], 6
0x1400114ee  jb      loc_1400113BD
0x1400114f4  mov     edx, 21h ; '!'
0x1400114f9  jmp     loc_1400113B1
0x1400114fe  mov     ecx, 3
0x140011503  int     29h; Win8: RtlFailFast(ecx)
```
