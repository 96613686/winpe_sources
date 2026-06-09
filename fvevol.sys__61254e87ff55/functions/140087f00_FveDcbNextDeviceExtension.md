# FveDcbNextDeviceExtension

- ea: `0x140087f00`
- end: `0x1400884f0`
- name: `FveDcbNextDeviceExtension`
- size: `1520`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140027db8`
- `0x14002ae98`
- `0x14002e950`
- `0x140072bb0`
- `0x140072f2c`
- `0x140087b90`

## callees

- `0x140008e80`
- `0x14000a210`
- `0x14001046c`
- `0x14002e2bc`
- `0x140087f00`
- `0x1400889e8`
- `0x140088d8c`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140088020`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140088020`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140088083`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14008816d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140088491`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140088083`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14008816d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140088491`

## pseudocode

```c
__int64 __fastcall FveDcbNextDeviceExtension(_QWORD *a1, __int64 a2, int a3)
{
  __int64 v3; // r12
  __int64 v4; // rbp
  __int64 v5; // rsi
  __int64 v7; // rbx
  __int64 v9; // r8
  __int64 v10; // r13
  __int64 v11; // rcx
  __int64 v12; // r15
  __int64 v13; // rax
  __int64 i; // rax
  __int64 v15; // r8
  _QWORD *v16; // rbx
  __int64 v18; // rcx
  __int64 ChildDcb; // rax
  __int64 v20; // rcx
  __int64 v21; // r8

  v3 = 0;
  v4 = 0;
  v5 = 0;
  v7 = a2;
  LOBYTE(a2) = 5;
  v9 = 1024;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qqL(WPP_GLOBAL_Control->AttachedDevice, a2, 1024, a1, v7, a3);
    v9 = 1024;
  }
  if ( !a1 || v7 && *(_QWORD **)(v7 + 8) != a1 || a3 >= 3 )
    goto LABEL_25;
  v10 = 0;
  if ( !v7 )
  {
    v12 = 0;
    if ( a3 )
    {
      if ( a3 == 1 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
        }
        v18 = a1[3];
      }
      else
      {
        if ( a3 != 2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
          }
          v20 = a1[3];
          if ( !v20 )
            goto LABEL_34;
          ChildDcb = BlNextChildDcb(*(_QWORD *)(v20 + 8), 0, v9);
LABEL_33:
          v5 = ChildDcb;
LABEL_34:
          v13 = 0;
          goto LABEL_13;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
        }
        v18 = a1[4];
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
      }
      v18 = a1[2];
    }
    ChildDcb = BlDcbRef(v18);
    goto LABEL_33;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
  }
  v11 = *(_QWORD *)(v7 + 24);
  v12 = *(_QWORD *)(v11 + 200);
  if ( v12 )
    v10 = BlDcbRef(v11);
  v5 = BlDcbRef(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 8LL));
  v13 = BlDcbRef(*(_QWORD *)(v7 + 24));
LABEL_13:
  for ( i = BlNextChildDcb(v5, v13, v9); ; i = BlNextChildDcb(v5, v4, v15) )
  {
    v4 = i;
    if ( !v5
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
    }
    if ( !v4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
      }
      if ( !v5 || a3 != -1 || !*(_QWORD *)(v5 + 8) )
        goto LABEL_40;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 86, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
      }
      v5 = BlNextChildDcb(*(_QWORD *)(v5 + 8), v5, v15);
      v4 = BlNextChildDcb(v5, 0, v21);
      if ( !v5
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
      }
      if ( !v4 )
        break;
    }
    v16 = *(_QWORD **)(v4 + 200);
    if ( *v16 && IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v16 + 1), v16, File, 1u, 0x20u) >= 0 )
    {
      if ( (*(_DWORD *)(*(_QWORD *)*v16 + 48LL) & 0x80u) == 0 )
      {
        v3 = *v16;
        if ( !*v16 )
          IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v16 + 1), v16, 0x20u);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids, v3);
        }
        goto LABEL_23;
      }
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v16 + 1), v16, 0x20u);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 90, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids, *v16);
    }
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_23;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
LABEL_40:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 89, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
  }
LABEL_23:
  if ( v12 )
  {
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v12 + 8), (PVOID)v12, 0x20u);
    BlDcbDeref(v10);
  }
LABEL_25:
  BlDcbDeref(v4);
  BlDcbDeref(v5);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x140087f00  push    rbx
0x140087f02  push    rbp
0x140087f03  push    rsi
0x140087f04  push    rdi
0x140087f05  push    r12
0x140087f07  push    r13
0x140087f09  push    r14
0x140087f0b  push    r15
0x140087f0d  sub     rsp, 38h
0x140087f11  xor     r12d, r12d
0x140087f14  xor     ebp, ebp
0x140087f16  xor     esi, esi
0x140087f18  mov     r14d, r8d
0x140087f1b  mov     rbx, rdx
0x140087f1e  mov     rdi, rcx
0x140087f21  mov     rcx, cs:WPP_GLOBAL_Control
0x140087f28  lea     r9, WPP_GLOBAL_Control
0x140087f2f  mov     dl, 5
0x140087f31  mov     r8d, 400h
0x140087f37  cmp     rcx, r9
0x140087f3a  jz      short loc_140087F46
0x140087f3c  test    [rcx+2Ch], r8d
0x140087f40  jnz     loc_1400882C5
0x140087f46  lea     r10, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140087f4d  test    rdi, rdi
0x140087f50  jz      loc_140088110
0x140087f56  test    rbx, rbx
0x140087f59  jz      short loc_140087F65
0x140087f5b  cmp     [rbx+8], rdi
0x140087f5f  jnz     loc_140088110
0x140087f65  cmp     r14d, 3
0x140087f69  jge     loc_140088110
0x140087f6f  xor     r13d, r13d
0x140087f72  test    rbx, rbx
0x140087f75  jz      loc_1400880D5
0x140087f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140087f82  cmp     rcx, r9
0x140087f85  jz      short loc_140087F91
0x140087f87  test    [rcx+2Ch], r8d
0x140087f8b  jnz     loc_140088347
0x140087f91  mov     rcx, [rbx+18h]
0x140087f95  mov     r15, [rcx+0C8h]
0x140087f9c  test    r15, r15
0x140087f9f  jz      short loc_140087FA9
0x140087fa1  call    BlDcbRef
0x140087fa6  mov     r13, rax
0x140087fa9  mov     rcx, [rbx+18h]
0x140087fad  mov     rcx, [rcx+8]
0x140087fb1  call    BlDcbRef
0x140087fb6  mov     rcx, [rbx+18h]
0x140087fba  mov     rsi, rax
0x140087fbd  call    BlDcbRef
0x140087fc2  mov     rdx, rax
0x140087fc5  mov     rcx, rsi
0x140087fc8  call    BlNextChildDcb
0x140087fcd  lea     rdi, WPP_GLOBAL_Control
0x140087fd4  mov     rbp, rax
0x140087fd7  test    rsi, rsi
0x140087fda  jz      loc_140088366
0x140087fe0  mov     ebx, 400h
0x140087fe5  test    rbp, rbp
0x140087fe8  jz      loc_14008811C
0x140087fee  mov     rbx, [rbp+0C8h]
0x140087ff5  mov     rax, [rbx]
0x140087ff8  test    rax, rax
0x140087ffb  jz      loc_140088180
0x140088001  lea     rdi, [rbx+8]
0x140088005  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x14008800d  mov     rcx, rdi; RemoveLock
0x140088010  lea     r8, File; File
0x140088017  mov     r9d, 1; Line
0x14008801d  mov     rdx, rbx; Tag
0x140088020  call    cs:__imp_IoAcquireRemoveLockEx
0x140088027  nop     dword ptr [rax+rax+00h]
0x14008802c  test    eax, eax
0x14008802e  js      loc_140088179
0x140088034  mov     rax, [rbx]
0x140088037  mov     rdx, [rax]
0x14008803a  mov     eax, [rdx+30h]
0x14008803d  test    al, al
0x14008803f  js      loc_140088161
0x140088045  mov     r12, [rbx]
0x140088048  test    r12, r12
0x14008804b  jz      loc_140088485
0x140088051  mov     rcx, cs:WPP_GLOBAL_Control
0x140088058  lea     rbx, WPP_GLOBAL_Control
0x14008805f  cmp     rcx, rbx
0x140088062  jz      short loc_140088071
0x140088064  test    dword ptr [rcx+2Ch], 400h
0x14008806b  jnz     loc_1400884A2
0x140088071  test    r15, r15
0x140088074  jz      short loc_140088097
0x140088076  lea     rcx, [r15+8]; RemoveLock
0x14008807a  mov     r8d, 20h ; ' '; RemlockSize
0x140088080  mov     rdx, r15; Tag
0x140088083  call    cs:__imp_IoReleaseRemoveLockEx
0x14008808a  nop     dword ptr [rax+rax+00h]
0x14008808f  mov     rcx, r13
0x140088092  call    BlDcbDeref
0x140088097  mov     rcx, rbp
0x14008809a  call    BlDcbDeref
0x14008809f  mov     rcx, rsi
0x1400880a2  call    BlDcbDeref
0x1400880a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400880ae  cmp     rcx, rbx
0x1400880b1  jz      short loc_1400880C0
0x1400880b3  test    dword ptr [rcx+2Ch], 400h
0x1400880ba  jnz     loc_1400884C9
0x1400880c0  mov     rax, r12
0x1400880c3  add     rsp, 38h
0x1400880c7  pop     r15
0x1400880c9  pop     r14
0x1400880cb  pop     r13
0x1400880cd  pop     r12
0x1400880cf  pop     rdi
0x1400880d0  pop     rsi
0x1400880d1  pop     rbp
0x1400880d2  pop     rbx
0x1400880d3  retn
0x1400880d5  xor     r15d, r15d
0x1400880d8  mov     ecx, r14d
0x1400880db  test    r14d, r14d
0x1400880de  jz      loc_140088316
0x1400880e4  sub     ecx, 1
0x1400880e7  jnz     loc_1400881C9
0x1400880ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400880f4  cmp     rcx, r9
0x1400880f7  jnz     loc_1400881A0
0x1400880fd  mov     rcx, [rdi+18h]
0x140088101  call    BlDcbRef
0x140088106  mov     rsi, rax
0x140088109  xor     eax, eax
0x14008810b  jmp     loc_140087FC2
0x140088110  lea     rbx, WPP_GLOBAL_Control
0x140088117  jmp     loc_140088097
0x14008811c  mov     rcx, cs:WPP_GLOBAL_Control
0x140088123  cmp     rcx, rdi
0x140088126  jz      short loc_140088131
0x140088128  test    [rcx+2Ch], ebx
0x14008812b  jnz     loc_1400883A8
0x140088131  test    rsi, rsi
0x140088134  jz      short loc_140088140
0x140088136  cmp     r14d, 0FFFFFFFFh
0x14008813a  jz      loc_1400881FF
0x140088140  mov     rcx, cs:WPP_GLOBAL_Control
0x140088147  cmp     rcx, rdi
0x14008814a  jz      short loc_140088155
0x14008814c  test    [rcx+2Ch], ebx
0x14008814f  jnz     loc_140088461
0x140088155  lea     rbx, WPP_GLOBAL_Control
0x14008815c  jmp     loc_140088071
0x140088161  mov     r8d, 20h ; ' '; RemlockSize
0x140088167  mov     rdx, rbx; Tag
0x14008816a  mov     rcx, rdi; RemoveLock
0x14008816d  call    cs:__imp_IoReleaseRemoveLockEx
0x140088174  nop     dword ptr [rax+rax+00h]
0x140088179  lea     rdi, WPP_GLOBAL_Control
0x140088180  mov     rcx, cs:WPP_GLOBAL_Control
0x140088187  cmp     rcx, rdi
0x14008818a  jnz     loc_14008842D
0x140088190  mov     rdx, rbp
0x140088193  mov     rcx, rsi
0x140088196  call    BlNextChildDcb
0x14008819b  jmp     loc_140087FD4
0x1400881a0  test    [rcx+2Ch], r8d
0x1400881a4  jz      loc_1400880FD
0x1400881aa  cmp     [rcx+29h], dl
0x1400881ad  jb      loc_1400880FD
0x1400881b3  mov     rcx, [rcx+18h]
0x1400881b7  mov     edx, 50h ; 'P'
0x1400881bc  mov     r8, r10
0x1400881bf  call    WPP_SF_
0x1400881c4  jmp     loc_1400880FD
0x1400881c9  cmp     ecx, 1
0x1400881cc  jz      loc_1400882B0
0x1400881d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400881d9  cmp     rcx, r9
0x1400881dc  jnz     loc_140088287
0x1400881e2  mov     rcx, [rdi+18h]
0x1400881e6  test    rcx, rcx
0x1400881e9  jz      loc_140088109
0x1400881ef  mov     rcx, [rcx+8]
0x1400881f3  xor     edx, edx
0x1400881f5  call    BlNextChildDcb
0x1400881fa  jmp     loc_140088106
0x1400881ff  cmp     [rsi+8], r12
0x140088203  jz      loc_140088140
0x140088209  mov     rcx, cs:WPP_GLOBAL_Control
0x140088210  cmp     rcx, rdi
0x140088213  jz      short loc_14008821E
0x140088215  test    [rcx+2Ch], ebx
0x140088218  jnz     loc_1400883CC
0x14008821e  mov     rcx, [rsi+8]
0x140088222  mov     rdx, rsi
0x140088225  call    BlNextChildDcb
0x14008822a  xor     edx, edx
0x14008822c  mov     rcx, rax
0x14008822f  mov     rsi, rax
0x140088232  call    BlNextChildDcb
0x140088237  mov     rbp, rax
0x14008823a  test    rsi, rsi
0x14008823d  jz      loc_1400883F0
0x140088243  test    rbp, rbp
0x140088246  jnz     loc_140087FEE
0x14008824c  mov     rcx, cs:WPP_GLOBAL_Control
0x140088253  cmp     rcx, rdi
0x140088256  jz      loc_140088155
0x14008825c  test    [rcx+2Ch], ebx
0x14008825f  jz      loc_140088140
0x140088265  cmp     byte ptr [rcx+29h], 5
0x140088269  jb      loc_140088140
0x14008826f  mov     rcx, [rcx+18h]
0x140088273  lea     edx, [rbp+58h]
0x140088276  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008827d  call    WPP_SF_
0x140088282  jmp     loc_140088140
0x140088287  test    [rcx+2Ch], r8d
0x14008828b  jz      loc_1400881E2
0x140088291  cmp     [rcx+29h], dl
0x140088294  jb      loc_1400881E2
0x14008829a  mov     rcx, [rcx+18h]
0x14008829e  mov     edx, 52h ; 'R'
0x1400882a3  mov     r8, r10
0x1400882a6  call    WPP_SF_
0x1400882ab  jmp     loc_1400881E2
0x1400882b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400882b7  cmp     rcx, r9
0x1400882ba  jnz     short loc_1400882F8
0x1400882bc  mov     rcx, [rdi+20h]
0x1400882c0  jmp     loc_140088101
0x1400882c5  cmp     [rcx+29h], dl
0x1400882c8  jb      loc_140087F46
0x1400882ce  mov     rcx, [rcx+18h]
0x1400882d2  mov     r9, rdi
0x1400882d5  mov     [rsp+78h+var_50], r14d
0x1400882da  mov     qword ptr [rsp+78h+RemlockSize], rbx
0x1400882df  call    WPP_SF_qqL
0x1400882e4  mov     dl, 5
0x1400882e6  lea     r9, WPP_GLOBAL_Control
0x1400882ed  mov     r8d, 400h
0x1400882f3  jmp     loc_140087F46
0x1400882f8  test    [rcx+2Ch], r8d
0x1400882fc  jz      short loc_1400882BC
0x1400882fe  cmp     [rcx+29h], dl
0x140088301  jb      short loc_1400882BC
0x140088303  mov     rcx, [rcx+18h]
0x140088307  mov     edx, 51h ; 'Q'
0x14008830c  mov     r8, r10
0x14008830f  call    WPP_SF_
0x140088314  jmp     short loc_1400882BC
0x140088316  mov     rcx, cs:WPP_GLOBAL_Control
0x14008831d  cmp     rcx, r9
0x140088320  jz      short loc_14008833E
0x140088322  test    [rcx+2Ch], r8d
0x140088326  jz      short loc_14008833E
0x140088328  cmp     [rcx+29h], dl
0x14008832b  jb      short loc_14008833E
0x14008832d  mov     rcx, [rcx+18h]
0x140088331  mov     edx, 4Fh ; 'O'
0x140088336  mov     r8, r10
0x140088339  call    WPP_SF_
0x14008833e  mov     rcx, [rdi+10h]
0x140088342  jmp     loc_140088101
0x140088347  cmp     [rcx+29h], dl
0x14008834a  jb      loc_140087F91
0x140088350  mov     rcx, [rcx+18h]
0x140088354  mov     edx, 53h ; 'S'
0x140088359  mov     r8, r10
0x14008835c  call    WPP_SF_
0x140088361  jmp     loc_140087F91
0x140088366  mov     rcx, cs:WPP_GLOBAL_Control
0x14008836d  mov     ebx, 400h
0x140088372  cmp     rcx, rdi
0x140088375  jz      loc_140087FE5
0x14008837b  test    [rcx+2Ch], ebx
0x14008837e  jz      loc_140087FE5
0x140088384  cmp     byte ptr [rcx+29h], 5
0x140088388  jb      loc_140087FE5
0x14008838e  mov     rcx, [rcx+18h]
0x140088392  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140088399  mov     edx, 54h ; 'T'
0x14008839e  call    WPP_SF_
0x1400883a3  jmp     loc_140087FE5
0x1400883a8  cmp     byte ptr [rcx+29h], 5
0x1400883ac  jb      loc_140088131
0x1400883b2  mov     rcx, [rcx+18h]
0x1400883b6  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x1400883bd  mov     edx, 55h ; 'U'
0x1400883c2  call    WPP_SF_
0x1400883c7  jmp     loc_140088131
0x1400883cc  cmp     byte ptr [rcx+29h], 5
0x1400883d0  jb      loc_14008821E
0x1400883d6  mov     rcx, [rcx+18h]
0x1400883da  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x1400883e1  mov     edx, 56h ; 'V'
0x1400883e6  call    WPP_SF_
0x1400883eb  jmp     loc_14008821E
0x1400883f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400883f7  cmp     rcx, rdi
0x1400883fa  jz      loc_140088243
  ... truncated ...
```
