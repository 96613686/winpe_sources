# FveDcbNextDeviceExtension

- ea: `0x140085e60`
- end: `0x140086450`
- name: `FveDcbNextDeviceExtension`
- size: `1520`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140026db8`
- `0x140029e98`
- `0x14002d950`
- `0x140070bd0`
- `0x140070f4c`
- `0x140085af0`

## callees

- `0x140008dc0`
- `0x14000a150`
- `0x140010070`
- `0x14002d2bc`
- `0x140085e60`
- `0x140086948`
- `0x140086cec`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140085f80`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140085f80`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140085fe3`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400860cd`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400863f1`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140085fe3`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400860cd`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400863f1`

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
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 i; // rax
  __int64 v17; // r8
  _QWORD *v18; // rbx
  __int64 v20; // rcx
  __int64 ChildDcb; // rax
  __int64 v22; // rcx
  __int64 v23; // r8

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
    LOBYTE(a2) = 5;
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
        v20 = a1[3];
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
          v22 = a1[3];
          if ( !v22 )
            goto LABEL_34;
          ChildDcb = BlNextChildDcb(*(_QWORD *)(v22 + 8), 0, v9);
LABEL_33:
          v5 = ChildDcb;
LABEL_34:
          v15 = 0;
          goto LABEL_13;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
        }
        v20 = a1[4];
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
      v20 = a1[2];
    }
    ChildDcb = BlDcbRef(v20, a2, v9);
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
    v10 = BlDcbRef(v11, a2, v9);
  v5 = BlDcbRef(*(_QWORD *)(*(_QWORD *)(v7 + 24) + 8LL), a2, v9);
  v15 = BlDcbRef(*(_QWORD *)(v7 + 24), v13, v14);
LABEL_13:
  for ( i = BlNextChildDcb(v5, v15, v9); ; i = BlNextChildDcb(v5, v4, v17) )
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
      v5 = BlNextChildDcb(*(_QWORD *)(v5 + 8), v5, v17);
      v4 = BlNextChildDcb(v5, 0, v23);
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
    v18 = *(_QWORD **)(v4 + 200);
    if ( *v18 && IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v18 + 1), v18, File, 1u, 0x20u) >= 0 )
    {
      if ( (*(_DWORD *)(*(_QWORD *)*v18 + 48LL) & 0x80u) == 0 )
      {
        v3 = *v18;
        if ( !*v18 )
          IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v18 + 1), v18, 0x20u);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids, v3);
        }
        goto LABEL_23;
      }
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v18 + 1), v18, 0x20u);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 90, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids, *v18);
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
0x140085e60  push    rbx
0x140085e62  push    rbp
0x140085e63  push    rsi
0x140085e64  push    rdi
0x140085e65  push    r12
0x140085e67  push    r13
0x140085e69  push    r14
0x140085e6b  push    r15
0x140085e6d  sub     rsp, 38h
0x140085e71  xor     r12d, r12d
0x140085e74  xor     ebp, ebp
0x140085e76  xor     esi, esi
0x140085e78  mov     r14d, r8d
0x140085e7b  mov     rbx, rdx
0x140085e7e  mov     rdi, rcx
0x140085e81  mov     rcx, cs:WPP_GLOBAL_Control
0x140085e88  lea     r9, WPP_GLOBAL_Control
0x140085e8f  mov     dl, 5
0x140085e91  mov     r8d, 400h
0x140085e97  cmp     rcx, r9
0x140085e9a  jz      short loc_140085EA6
0x140085e9c  test    [rcx+2Ch], r8d
0x140085ea0  jnz     loc_140086225
0x140085ea6  lea     r10, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140085ead  test    rdi, rdi
0x140085eb0  jz      loc_140086070
0x140085eb6  test    rbx, rbx
0x140085eb9  jz      short loc_140085EC5
0x140085ebb  cmp     [rbx+8], rdi
0x140085ebf  jnz     loc_140086070
0x140085ec5  cmp     r14d, 3
0x140085ec9  jge     loc_140086070
0x140085ecf  xor     r13d, r13d
0x140085ed2  test    rbx, rbx
0x140085ed5  jz      loc_140086035
0x140085edb  mov     rcx, cs:WPP_GLOBAL_Control
0x140085ee2  cmp     rcx, r9
0x140085ee5  jz      short loc_140085EF1
0x140085ee7  test    [rcx+2Ch], r8d
0x140085eeb  jnz     loc_1400862A7
0x140085ef1  mov     rcx, [rbx+18h]
0x140085ef5  mov     r15, [rcx+0C8h]
0x140085efc  test    r15, r15
0x140085eff  jz      short loc_140085F09
0x140085f01  call    BlDcbRef
0x140085f06  mov     r13, rax
0x140085f09  mov     rcx, [rbx+18h]
0x140085f0d  mov     rcx, [rcx+8]
0x140085f11  call    BlDcbRef
0x140085f16  mov     rcx, [rbx+18h]
0x140085f1a  mov     rsi, rax
0x140085f1d  call    BlDcbRef
0x140085f22  mov     rdx, rax
0x140085f25  mov     rcx, rsi
0x140085f28  call    BlNextChildDcb
0x140085f2d  lea     rdi, WPP_GLOBAL_Control
0x140085f34  mov     rbp, rax
0x140085f37  test    rsi, rsi
0x140085f3a  jz      loc_1400862C6
0x140085f40  mov     ebx, 400h
0x140085f45  test    rbp, rbp
0x140085f48  jz      loc_14008607C
0x140085f4e  mov     rbx, [rbp+0C8h]
0x140085f55  mov     rax, [rbx]
0x140085f58  test    rax, rax
0x140085f5b  jz      loc_1400860E0
0x140085f61  lea     rdi, [rbx+8]
0x140085f65  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x140085f6d  mov     rcx, rdi; RemoveLock
0x140085f70  lea     r8, File; File
0x140085f77  mov     r9d, 1; Line
0x140085f7d  mov     rdx, rbx; Tag
0x140085f80  call    cs:__imp_IoAcquireRemoveLockEx
0x140085f87  nop     dword ptr [rax+rax+00h]
0x140085f8c  test    eax, eax
0x140085f8e  js      loc_1400860D9
0x140085f94  mov     rax, [rbx]
0x140085f97  mov     rdx, [rax]
0x140085f9a  mov     eax, [rdx+30h]
0x140085f9d  test    al, al
0x140085f9f  js      loc_1400860C1
0x140085fa5  mov     r12, [rbx]
0x140085fa8  test    r12, r12
0x140085fab  jz      loc_1400863E5
0x140085fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140085fb8  lea     rbx, WPP_GLOBAL_Control
0x140085fbf  cmp     rcx, rbx
0x140085fc2  jz      short loc_140085FD1
0x140085fc4  test    dword ptr [rcx+2Ch], 400h
0x140085fcb  jnz     loc_140086402
0x140085fd1  test    r15, r15
0x140085fd4  jz      short loc_140085FF7
0x140085fd6  lea     rcx, [r15+8]; RemoveLock
0x140085fda  mov     r8d, 20h ; ' '; RemlockSize
0x140085fe0  mov     rdx, r15; Tag
0x140085fe3  call    cs:__imp_IoReleaseRemoveLockEx
0x140085fea  nop     dword ptr [rax+rax+00h]
0x140085fef  mov     rcx, r13
0x140085ff2  call    BlDcbDeref
0x140085ff7  mov     rcx, rbp
0x140085ffa  call    BlDcbDeref
0x140085fff  mov     rcx, rsi
0x140086002  call    BlDcbDeref
0x140086007  mov     rcx, cs:WPP_GLOBAL_Control
0x14008600e  cmp     rcx, rbx
0x140086011  jz      short loc_140086020
0x140086013  test    dword ptr [rcx+2Ch], 400h
0x14008601a  jnz     loc_140086429
0x140086020  mov     rax, r12
0x140086023  add     rsp, 38h
0x140086027  pop     r15
0x140086029  pop     r14
0x14008602b  pop     r13
0x14008602d  pop     r12
0x14008602f  pop     rdi
0x140086030  pop     rsi
0x140086031  pop     rbp
0x140086032  pop     rbx
0x140086033  retn
0x140086035  xor     r15d, r15d
0x140086038  mov     ecx, r14d
0x14008603b  test    r14d, r14d
0x14008603e  jz      loc_140086276
0x140086044  sub     ecx, 1
0x140086047  jnz     loc_140086129
0x14008604d  mov     rcx, cs:WPP_GLOBAL_Control
0x140086054  cmp     rcx, r9
0x140086057  jnz     loc_140086100
0x14008605d  mov     rcx, [rdi+18h]
0x140086061  call    BlDcbRef
0x140086066  mov     rsi, rax
0x140086069  xor     eax, eax
0x14008606b  jmp     loc_140085F22
0x140086070  lea     rbx, WPP_GLOBAL_Control
0x140086077  jmp     loc_140085FF7
0x14008607c  mov     rcx, cs:WPP_GLOBAL_Control
0x140086083  cmp     rcx, rdi
0x140086086  jz      short loc_140086091
0x140086088  test    [rcx+2Ch], ebx
0x14008608b  jnz     loc_140086308
0x140086091  test    rsi, rsi
0x140086094  jz      short loc_1400860A0
0x140086096  cmp     r14d, 0FFFFFFFFh
0x14008609a  jz      loc_14008615F
0x1400860a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400860a7  cmp     rcx, rdi
0x1400860aa  jz      short loc_1400860B5
0x1400860ac  test    [rcx+2Ch], ebx
0x1400860af  jnz     loc_1400863C1
0x1400860b5  lea     rbx, WPP_GLOBAL_Control
0x1400860bc  jmp     loc_140085FD1
0x1400860c1  mov     r8d, 20h ; ' '; RemlockSize
0x1400860c7  mov     rdx, rbx; Tag
0x1400860ca  mov     rcx, rdi; RemoveLock
0x1400860cd  call    cs:__imp_IoReleaseRemoveLockEx
0x1400860d4  nop     dword ptr [rax+rax+00h]
0x1400860d9  lea     rdi, WPP_GLOBAL_Control
0x1400860e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400860e7  cmp     rcx, rdi
0x1400860ea  jnz     loc_14008638D
0x1400860f0  mov     rdx, rbp
0x1400860f3  mov     rcx, rsi
0x1400860f6  call    BlNextChildDcb
0x1400860fb  jmp     loc_140085F34
0x140086100  test    [rcx+2Ch], r8d
0x140086104  jz      loc_14008605D
0x14008610a  cmp     [rcx+29h], dl
0x14008610d  jb      loc_14008605D
0x140086113  mov     rcx, [rcx+18h]
0x140086117  mov     edx, 50h ; 'P'
0x14008611c  mov     r8, r10
0x14008611f  call    WPP_SF_
0x140086124  jmp     loc_14008605D
0x140086129  cmp     ecx, 1
0x14008612c  jz      loc_140086210
0x140086132  mov     rcx, cs:WPP_GLOBAL_Control
0x140086139  cmp     rcx, r9
0x14008613c  jnz     loc_1400861E7
0x140086142  mov     rcx, [rdi+18h]
0x140086146  test    rcx, rcx
0x140086149  jz      loc_140086069
0x14008614f  mov     rcx, [rcx+8]
0x140086153  xor     edx, edx
0x140086155  call    BlNextChildDcb
0x14008615a  jmp     loc_140086066
0x14008615f  cmp     [rsi+8], r12
0x140086163  jz      loc_1400860A0
0x140086169  mov     rcx, cs:WPP_GLOBAL_Control
0x140086170  cmp     rcx, rdi
0x140086173  jz      short loc_14008617E
0x140086175  test    [rcx+2Ch], ebx
0x140086178  jnz     loc_14008632C
0x14008617e  mov     rcx, [rsi+8]
0x140086182  mov     rdx, rsi
0x140086185  call    BlNextChildDcb
0x14008618a  xor     edx, edx
0x14008618c  mov     rcx, rax
0x14008618f  mov     rsi, rax
0x140086192  call    BlNextChildDcb
0x140086197  mov     rbp, rax
0x14008619a  test    rsi, rsi
0x14008619d  jz      loc_140086350
0x1400861a3  test    rbp, rbp
0x1400861a6  jnz     loc_140085F4E
0x1400861ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400861b3  cmp     rcx, rdi
0x1400861b6  jz      loc_1400860B5
0x1400861bc  test    [rcx+2Ch], ebx
0x1400861bf  jz      loc_1400860A0
0x1400861c5  cmp     byte ptr [rcx+29h], 5
0x1400861c9  jb      loc_1400860A0
0x1400861cf  mov     rcx, [rcx+18h]
0x1400861d3  lea     edx, [rbp+58h]
0x1400861d6  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x1400861dd  call    WPP_SF_
0x1400861e2  jmp     loc_1400860A0
0x1400861e7  test    [rcx+2Ch], r8d
0x1400861eb  jz      loc_140086142
0x1400861f1  cmp     [rcx+29h], dl
0x1400861f4  jb      loc_140086142
0x1400861fa  mov     rcx, [rcx+18h]
0x1400861fe  mov     edx, 52h ; 'R'
0x140086203  mov     r8, r10
0x140086206  call    WPP_SF_
0x14008620b  jmp     loc_140086142
0x140086210  mov     rcx, cs:WPP_GLOBAL_Control
0x140086217  cmp     rcx, r9
0x14008621a  jnz     short loc_140086258
0x14008621c  mov     rcx, [rdi+20h]
0x140086220  jmp     loc_140086061
0x140086225  cmp     [rcx+29h], dl
0x140086228  jb      loc_140085EA6
0x14008622e  mov     rcx, [rcx+18h]
0x140086232  mov     r9, rdi
0x140086235  mov     [rsp+78h+var_50], r14d
0x14008623a  mov     qword ptr [rsp+78h+RemlockSize], rbx
0x14008623f  call    WPP_SF_qqL
0x140086244  mov     dl, 5
0x140086246  lea     r9, WPP_GLOBAL_Control
0x14008624d  mov     r8d, 400h
0x140086253  jmp     loc_140085EA6
0x140086258  test    [rcx+2Ch], r8d
0x14008625c  jz      short loc_14008621C
0x14008625e  cmp     [rcx+29h], dl
0x140086261  jb      short loc_14008621C
0x140086263  mov     rcx, [rcx+18h]
0x140086267  mov     edx, 51h ; 'Q'
0x14008626c  mov     r8, r10
0x14008626f  call    WPP_SF_
0x140086274  jmp     short loc_14008621C
0x140086276  mov     rcx, cs:WPP_GLOBAL_Control
0x14008627d  cmp     rcx, r9
0x140086280  jz      short loc_14008629E
0x140086282  test    [rcx+2Ch], r8d
0x140086286  jz      short loc_14008629E
0x140086288  cmp     [rcx+29h], dl
0x14008628b  jb      short loc_14008629E
0x14008628d  mov     rcx, [rcx+18h]
0x140086291  mov     edx, 4Fh ; 'O'
0x140086296  mov     r8, r10
0x140086299  call    WPP_SF_
0x14008629e  mov     rcx, [rdi+10h]
0x1400862a2  jmp     loc_140086061
0x1400862a7  cmp     [rcx+29h], dl
0x1400862aa  jb      loc_140085EF1
0x1400862b0  mov     rcx, [rcx+18h]
0x1400862b4  mov     edx, 53h ; 'S'
0x1400862b9  mov     r8, r10
0x1400862bc  call    WPP_SF_
0x1400862c1  jmp     loc_140085EF1
0x1400862c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400862cd  mov     ebx, 400h
0x1400862d2  cmp     rcx, rdi
0x1400862d5  jz      loc_140085F45
0x1400862db  test    [rcx+2Ch], ebx
0x1400862de  jz      loc_140085F45
0x1400862e4  cmp     byte ptr [rcx+29h], 5
0x1400862e8  jb      loc_140085F45
0x1400862ee  mov     rcx, [rcx+18h]
0x1400862f2  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x1400862f9  mov     edx, 54h ; 'T'
0x1400862fe  call    WPP_SF_
0x140086303  jmp     loc_140085F45
0x140086308  cmp     byte ptr [rcx+29h], 5
0x14008630c  jb      loc_140086091
0x140086312  mov     rcx, [rcx+18h]
0x140086316  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008631d  mov     edx, 55h ; 'U'
0x140086322  call    WPP_SF_
0x140086327  jmp     loc_140086091
0x14008632c  cmp     byte ptr [rcx+29h], 5
0x140086330  jb      loc_14008617E
0x140086336  mov     rcx, [rcx+18h]
0x14008633a  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140086341  mov     edx, 56h ; 'V'
0x140086346  call    WPP_SF_
0x14008634b  jmp     loc_14008617E
0x140086350  mov     rcx, cs:WPP_GLOBAL_Control
0x140086357  cmp     rcx, rdi
0x14008635a  jz      loc_1400861A3
  ... truncated ...
```
