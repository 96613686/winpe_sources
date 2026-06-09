# NfsReadDirectoryEntry

- ea: `0x140013dc0`
- end: `0x1400142f6`
- name: `NfsReadDirectoryEntry`
- size: `1334`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x140003510`
- `0x140005de0`
- `0x1400070a0`
- `0x1400372e8`

## callees

- `0x140003440`
- `0x140008140`
- `0x140008e10`
- `0x14000d4cc`
- `0x140012c40`
- `0x140013dc0`
- `0x1400159cc`
- `0x1400159fc`
- `0x1400196a8`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400140c0`
- `ntoskrnl!KeReleaseMutex` at `0x1400140c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014298`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014298`
- `ntoskrnl!ExAllocatePool2` at `0x140013e86`
- `ntoskrnl!ExAllocatePool2` at `0x140013e86`
- `rpcxdr!OncRpcDestroy` at `0x1400140f8`
- `rpcxdr!OncRpcDestroy` at `0x140014275`
- `rpcxdr!OncRpcDestroy` at `0x1400140f8`
- `rpcxdr!OncRpcDestroy` at `0x140014275`

## pseudocode

```c
__int64 __fastcall NfsReadDirectoryEntry(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        void **a4,
        char a5,
        _QWORD *a6,
        _QWORD *a7,
        _DWORD *a8,
        _QWORD *a9,
        _QWORD *a10)
{
  __int64 v12; // r8
  __int64 v13; // r14
  __int64 v15; // rbx
  _QWORD *v16; // r12
  _QWORD *v17; // r13
  _DWORD *v18; // r15
  __int64 Pool2; // rax
  int DirBuffer; // ebx
  int v21; // ecx
  int DirEntry; // eax
  struct _KMUTANT *v23; // rcx
  bool v25; // zf
  __int64 v26; // rcx
  int v27; // [rsp+20h] [rbp-78h]
  __int64 v28; // [rsp+50h] [rbp-48h]
  int v29; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v30; // [rsp+B8h] [rbp+20h] BYREF

  v12 = 0;
  v13 = a2;
  v30 = 0;
  v29 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 198, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  v15 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 32LL);
  if ( !v15 )
    return 3221225662LL;
  v28 = *(_QWORD *)(a1 + 40);
  if ( !v28 )
    return 3221225662LL;
  v16 = a9;
  v17 = a10;
  v18 = *a4;
  if ( *a4 )
    goto LABEL_19;
  if ( !a5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 200, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    DirBuffer = -1073741811;
    goto LABEL_67;
  }
  Pool2 = ExAllocatePool2(258, 528, 1381131854);
  v18 = (_DWORD *)Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 199, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    DirBuffer = -1073741670;
    goto LABEL_67;
  }
  if ( *(_DWORD *)(v15 + 88) == 2 )
  {
    a2 = 1;
  }
  else if ( !v16 || (a2 = 3, !v17) )
  {
    a2 = 2;
  }
  v21 = *(_DWORD *)(v28 + 24);
  *a4 = (void *)Pool2;
  *(_QWORD *)(Pool2 + 256) = Pool2 + 264;
  *(_DWORD *)(Pool2 + 88) = 0;
  *(_DWORD *)Pool2 = a2;
  *(_DWORD *)(Pool2 + 20) = -1;
  *(_WORD *)(Pool2 + 16) = -1;
  *(_QWORD *)(Pool2 + 24) = 0;
  *(_QWORD *)(Pool2 + 32) = 0;
  *(_DWORD *)(Pool2 + 4) = v21;
  *(_QWORD *)(Pool2 + 8) = 0;
  *(_QWORD *)(Pool2 + 80) = 0;
  *(_QWORD *)(Pool2 + 64) = 0;
  *(_DWORD *)(Pool2 + 48) = 7;
  *(_QWORD *)(Pool2 + 56) = 0;
  while ( 1 )
  {
LABEL_19:
    if ( (v18[12] & 2) == 0 )
      goto LABEL_37;
    v27 = 1;
    DirBuffer = NfsFillReadDirBuffer(a1, v13, a3, (__int64)v18);
    if ( DirBuffer < 0 )
      break;
    v18[12] &= ~2u;
    if ( (unsigned __int8)HacIsEntryFake(a3) )
      return NfsFakeReadDirectoryEntry(a1, a3, a4, a5, a6, a7, a8, v16, v17);
    if ( (unsigned int)(*v18 - 1) <= 1 )
    {
      v12 = 0;
      if ( v16 )
        *v16 = 0;
      if ( v17 )
        *v17 = 0;
    }
    else if ( !v16 || !v17 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 202, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
      DirBuffer = -1073741811;
LABEL_62:
      v26 = *((_QWORD *)v18 + 1);
      if ( v26 )
      {
        OncRpcDestroy(v26);
        *((_QWORD *)v18 + 1) = 0;
      }
      goto LABEL_64;
    }
LABEL_37:
    if ( (v18[12] & 1) != 0 )
    {
      HacAcquireLock(a3, a2, v12);
      DirEntry = GetDirEntry(a1, a3, v18, &v30, v27);
      v23 = *(struct _KMUTANT **)(a3 + 40);
      DirBuffer = DirEntry;
      v30 = 0;
      KeReleaseMutex(v23, 0);
    }
    else
    {
      *((_QWORD *)v18 + 32) = v18 + 66;
      DirBuffer = NfsUnPackAnEntry(a1, (_DWORD)v18, (int)v18 + 72, (int)v18 + 256, (__int64)&v29, 1);
    }
    a2 = (__int64)(v18 + 64);
    if ( DirBuffer != 261 )
    {
      if ( !DirBuffer )
      {
        v25 = *v18 == 3;
        *a6 = *((_QWORD *)v18 + 9);
        *a7 = *(_QWORD *)a2;
        *a8 = v18[22];
        if ( v25 )
        {
          if ( v17 )
          {
            if ( v18[41] )
              *v17 = v18 + 42;
            else
              *v17 = 0;
          }
          if ( v16 )
          {
            if ( v18[23] )
              *v16 = v18 + 24;
            else
              *v16 = 0;
          }
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 203, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
        }
        return 0;
      }
      goto LABEL_62;
    }
    v18[12] |= 2u;
    if ( (v18[12] & 1) == 0 )
    {
      OncRpcDestroy(*((_QWORD *)v18 + 1));
      *((_QWORD *)v18 + 1) = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 201, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
LABEL_64:
  if ( a5 )
    ExFreePoolWithTag(v18, 0);
  *a4 = 0;
  if ( DirBuffer == -2147483642 )
    return (unsigned int)DirBuffer;
LABEL_67:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 204, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  return (unsigned int)DirBuffer;
}

```

## disassembly

```asm
0x140013dc0  mov     rax, rsp
0x140013dc3  push    rbx
0x140013dc4  push    rbp
0x140013dc5  push    rsi
0x140013dc6  push    rdi
0x140013dc7  push    r14
0x140013dc9  sub     rsp, 70h
0x140013dcd  mov     rbp, r8
0x140013dd0  mov     rsi, r9
0x140013dd3  xor     r8d, r8d
0x140013dd6  mov     r14, rdx
0x140013dd9  mov     [rax+20h], r8
0x140013ddd  mov     rdi, rcx
0x140013de0  mov     [rax+8], r8d
0x140013de4  mov     rcx, cs:WPP_GLOBAL_Control
0x140013deb  lea     rax, WPP_GLOBAL_Control
0x140013df2  cmp     rcx, rax
0x140013df5  jz      short loc_140013E13
0x140013df7  mov     eax, [rcx+2Ch]
0x140013dfa  test    al, 40h
0x140013dfc  jz      short loc_140013E13
0x140013dfe  mov     rcx, [rcx+18h]
0x140013e02  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140013e09  mov     edx, 0C6h
0x140013e0e  call    WPP_SF_
0x140013e13  mov     rax, [rdi+20h]
0x140013e17  mov     rbx, [rax+20h]
0x140013e1b  mov     rbx, [rbx+20h]
0x140013e1f  test    rbx, rbx
0x140013e22  jz      loc_1400142E5
0x140013e28  mov     rax, [rdi+28h]
0x140013e2c  mov     [rsp+98h+var_48], rax
0x140013e31  test    rax, rax
0x140013e34  jz      loc_1400142E5
0x140013e3a  mov     [rsp+98h+arg_8], r12
0x140013e42  mov     r12, [rsp+98h+arg_40]
0x140013e4a  mov     [rsp+98h+var_30], r13
0x140013e4f  mov     r13, [rsp+98h+arg_48]
0x140013e57  mov     [rsp+98h+var_38], r15
0x140013e5c  mov     r15, [rsi]
0x140013e5f  test    r15, r15
0x140013e62  jnz     loc_140013F62
0x140013e68  cmp     [rsp+98h+arg_20], r15b
0x140013e70  jz      loc_140013FFB
0x140013e76  mov     edx, 210h
0x140013e7b  mov     ecx, 102h
0x140013e80  mov     r8d, 5252664Eh
0x140013e86  call    cs:__imp_ExAllocatePool2
0x140013e8d  nop     dword ptr [rax+rax+00h]
0x140013e92  mov     r15, rax
0x140013e95  test    rax, rax
0x140013e98  jnz     short loc_140013ED3
0x140013e9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140013ea1  lea     rdi, WPP_GLOBAL_Control
0x140013ea8  cmp     rcx, rdi
0x140013eab  jz      short loc_140013EC9
0x140013ead  mov     eax, [rcx+2Ch]
0x140013eb0  test    al, 1
0x140013eb2  jz      short loc_140013EC9
0x140013eb4  mov     rcx, [rcx+18h]
0x140013eb8  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140013ebf  mov     edx, 0C7h
0x140013ec4  call    WPP_SF_
0x140013ec9  mov     ebx, 0C000009Ah
0x140013ece  jmp     loc_1400142B3
0x140013ed3  cmp     dword ptr [rbx+58h], 2
0x140013ed7  jnz     short loc_140013EE0
0x140013ed9  mov     edx, 1
0x140013ede  jmp     short loc_140013EF4
0x140013ee0  test    r12, r12
0x140013ee3  jz      short loc_140013EEF
0x140013ee5  mov     edx, 3
0x140013eea  test    r13, r13
0x140013eed  jnz     short loc_140013EF4
0x140013eef  mov     edx, 2
0x140013ef4  mov     rcx, [rsp+98h+var_48]
0x140013ef9  add     rax, 108h
0x140013eff  mov     ecx, [rcx+18h]
0x140013f02  mov     [rsi], r15
0x140013f05  mov     [r15+100h], rax
0x140013f0c  mov     dword ptr [r15+58h], 0
0x140013f14  mov     [r15], edx
0x140013f17  mov     dword ptr [r15+14h], 0FFFFFFFFh
0x140013f1f  mov     word ptr [r15+10h], 0FFFFh
0x140013f26  mov     qword ptr [r15+18h], 0
0x140013f2e  mov     qword ptr [r15+20h], 0
0x140013f36  mov     [r15+4], ecx
0x140013f3a  mov     qword ptr [r15+8], 0
0x140013f42  mov     qword ptr [r15+50h], 0
0x140013f4a  mov     qword ptr [r15+40h], 0
0x140013f52  mov     dword ptr [r15+30h], 7
0x140013f5a  mov     qword ptr [r15+38h], 0
0x140013f62  mov     eax, [r15+30h]
0x140013f66  test    al, 2
0x140013f68  jz      loc_140014049
0x140013f6e  mov     r9, r15
0x140013f71  mov     dword ptr [rsp+98h+var_78], 1
0x140013f79  mov     r8, rbp
0x140013f7c  mov     rdx, r14
0x140013f7f  mov     rcx, rdi
0x140013f82  call    NfsFillReadDirBuffer
0x140013f87  mov     ebx, eax
0x140013f89  test    eax, eax
0x140013f8b  js      loc_140014177
0x140013f91  and     dword ptr [r15+30h], 0FFFFFFFDh
0x140013f96  mov     rcx, rbp
0x140013f99  call    HacIsEntryFake
0x140013f9e  test    al, al
0x140013fa0  jnz     loc_140014111
0x140013fa6  mov     eax, [r15]
0x140013fa9  dec     eax
0x140013fab  cmp     eax, 1
0x140013fae  jbe     loc_140014034
0x140013fb4  test    r12, r12
0x140013fb7  jz      short loc_140013FC2
0x140013fb9  test    r13, r13
0x140013fbc  jnz     loc_140014049
0x140013fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140013fc9  lea     rdi, WPP_GLOBAL_Control
0x140013fd0  cmp     rcx, rdi
0x140013fd3  jz      short loc_140013FF1
0x140013fd5  mov     eax, [rcx+2Ch]
0x140013fd8  test    al, 1
0x140013fda  jz      short loc_140013FF1
0x140013fdc  mov     rcx, [rcx+18h]
0x140013fe0  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140013fe7  mov     edx, 0CAh
0x140013fec  call    WPP_SF_
0x140013ff1  mov     ebx, 0C000000Dh
0x140013ff6  jmp     loc_14001426C
0x140013ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x140014002  lea     rdi, WPP_GLOBAL_Control
0x140014009  cmp     rcx, rdi
0x14001400c  jz      short loc_14001402A
0x14001400e  mov     eax, [rcx+2Ch]
0x140014011  test    al, 1
0x140014013  jz      short loc_14001402A
0x140014015  mov     rcx, [rcx+18h]
0x140014019  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140014020  mov     edx, 0C8h
0x140014025  call    WPP_SF_
0x14001402a  mov     ebx, 0C000000Dh
0x14001402f  jmp     loc_1400142B3
0x140014034  xor     r8d, r8d
0x140014037  test    r12, r12
0x14001403a  jz      short loc_140014040
0x14001403c  mov     [r12], r8
0x140014040  test    r13, r13
0x140014043  jz      short loc_140014049
0x140014045  mov     [r13+0], r8
0x140014049  mov     eax, [r15+30h]
0x14001404d  test    al, 1
0x14001404f  jnz     short loc_14001408E
0x140014051  lea     rax, [r15+108h]
0x140014058  mov     dword ptr [rsp+98h+var_70], 1
0x140014060  mov     [r15+100h], rax
0x140014067  lea     r8, [r15+48h]
0x14001406b  lea     rax, [rsp+98h+arg_0]
0x140014073  mov     rdx, r15
0x140014076  lea     r9, [r15+100h]
0x14001407d  mov     [rsp+98h+var_78], rax
0x140014082  mov     rcx, rdi
0x140014085  call    NfsUnPackAnEntry
0x14001408a  mov     ebx, eax
0x14001408c  jmp     short loc_1400140CC
0x14001408e  mov     rcx, rbp
0x140014091  call    HacAcquireLock
0x140014096  lea     r9, [rsp+98h+arg_18]
0x14001409e  mov     r8, r15
0x1400140a1  mov     rdx, rbp
0x1400140a4  mov     rcx, rdi
0x1400140a7  call    GetDirEntry
0x1400140ac  mov     rcx, [rbp+28h]; Mutex
0x1400140b0  xor     edx, edx; Wait
0x1400140b2  mov     ebx, eax
0x1400140b4  mov     [rsp+98h+arg_18], 0
0x1400140c0  call    cs:__imp_KeReleaseMutex
0x1400140c7  nop     dword ptr [rax+rax+00h]
0x1400140cc  lea     rdx, [r15+100h]
0x1400140d3  lea     rax, [r15+48h]
0x1400140d7  cmp     ebx, 105h
0x1400140dd  jnz     loc_1400141B6
0x1400140e3  or      dword ptr [r15+30h], 2
0x1400140e8  mov     eax, [r15+30h]
0x1400140ec  test    al, 1
0x1400140ee  jnz     loc_140013F62
0x1400140f4  mov     rcx, [r15+8]
0x1400140f8  call    cs:__imp_OncRpcDestroy
0x1400140ff  nop     dword ptr [rax+rax+00h]
0x140014104  mov     qword ptr [r15+8], 0
0x14001410c  jmp     loc_140013F62
0x140014111  mov     rax, [rsp+98h+arg_38]
0x140014119  mov     r8, rsi
0x14001411c  movzx   r9d, [rsp+98h+arg_20]
0x140014125  mov     rdx, rbp
0x140014128  mov     [rsp+98h+var_58], r13
0x14001412d  mov     rcx, rdi
0x140014130  mov     [rsp+98h+var_60], r12
0x140014135  mov     [rsp+98h+var_68], rax
0x14001413a  mov     rax, [rsp+98h+arg_30]
0x140014142  mov     [rsp+98h+var_70], rax
0x140014147  mov     rax, [rsp+98h+arg_28]
0x14001414f  mov     [rsp+98h+var_78], rax
0x140014154  call    NfsFakeReadDirectoryEntry
0x140014159  mov     r13, [rsp+98h+var_30]
0x14001415e  mov     r12, [rsp+98h+arg_8]
0x140014166  mov     r15, [rsp+98h+var_38]
0x14001416b  add     rsp, 70h
0x14001416f  pop     r14
0x140014171  pop     rdi
0x140014172  pop     rsi
0x140014173  pop     rbp
0x140014174  pop     rbx
0x140014175  retn
0x140014177  mov     rcx, cs:WPP_GLOBAL_Control
0x14001417e  lea     rdi, WPP_GLOBAL_Control
0x140014185  cmp     rcx, rdi
0x140014188  jz      loc_140014289
0x14001418e  mov     eax, [rcx+2Ch]
0x140014191  test    al, 1
0x140014193  jz      loc_140014289
0x140014199  mov     rcx, [rcx+18h]
0x14001419d  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x1400141a4  mov     edx, 0C9h
0x1400141a9  mov     r9d, ebx
0x1400141ac  call    WPP_SF_d
0x1400141b1  jmp     loc_140014289
0x1400141b6  test    ebx, ebx
0x1400141b8  jnz     loc_140014265
0x1400141be  cmp     dword ptr [r15], 3
0x1400141c2  mov     rcx, [rax]
0x1400141c5  mov     rax, [rsp+98h+arg_28]
0x1400141cd  mov     [rax], rcx
0x1400141d0  mov     rax, [rsp+98h+arg_30]
0x1400141d8  mov     rcx, [rdx]
0x1400141db  mov     [rax], rcx
0x1400141de  mov     rax, [rsp+98h+arg_38]
0x1400141e6  mov     ecx, [r15+58h]
0x1400141ea  mov     [rax], ecx
0x1400141ec  jnz     short loc_14001422F
0x1400141ee  test    r13, r13
0x1400141f1  jz      short loc_140014211
0x1400141f3  cmp     [r15+0A4h], ebx
0x1400141fa  jz      short loc_140014209
0x1400141fc  lea     rax, [r15+0A8h]
0x140014203  mov     [r13+0], rax
0x140014207  jmp     short loc_140014211
0x140014209  mov     qword ptr [r13+0], 0
0x140014211  test    r12, r12
0x140014214  jz      short loc_14001422F
0x140014216  cmp     dword ptr [r15+5Ch], 0
0x14001421b  jz      short loc_140014227
0x14001421d  lea     rax, [r15+60h]
0x140014221  mov     [r12], rax
0x140014225  jmp     short loc_14001422F
0x140014227  mov     qword ptr [r12], 0
0x14001422f  mov     rcx, cs:WPP_GLOBAL_Control
0x140014236  lea     rdi, WPP_GLOBAL_Control
0x14001423d  cmp     rcx, rdi
0x140014240  jz      short loc_14001425E
0x140014242  mov     eax, [rcx+2Ch]
0x140014245  test    al, 40h
0x140014247  jz      short loc_14001425E
0x140014249  mov     rcx, [rcx+18h]
0x14001424d  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140014254  mov     edx, 0CBh
0x140014259  call    WPP_SF_
0x14001425e  xor     eax, eax
0x140014260  jmp     loc_140014159
0x140014265  lea     rdi, WPP_GLOBAL_Control
0x14001426c  mov     rcx, [r15+8]
0x140014270  test    rcx, rcx
0x140014273  jz      short loc_140014289
0x140014275  call    cs:__imp_OncRpcDestroy
0x14001427c  nop     dword ptr [rax+rax+00h]
0x140014281  mov     qword ptr [r15+8], 0
0x140014289  cmp     [rsp+98h+arg_20], 0
0x140014291  jz      short loc_1400142A4
0x140014293  xor     edx, edx; Tag
0x140014295  mov     rcx, r15; P
0x140014298  call    cs:__imp_ExFreePoolWithTag
0x14001429f  nop     dword ptr [rax+rax+00h]
0x1400142a4  mov     qword ptr [rsi], 0
0x1400142ab  cmp     ebx, 80000006h
0x1400142b1  jz      short loc_1400142DE
0x1400142b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400142ba  cmp     rcx, rdi
0x1400142bd  jz      short loc_1400142DE
0x1400142bf  mov     eax, [rcx+2Ch]
0x1400142c2  test    al, 1
0x1400142c4  jz      short loc_1400142DE
0x1400142c6  mov     rcx, [rcx+18h]
0x1400142ca  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x1400142d1  mov     edx, 0CCh
0x1400142d6  mov     r9d, ebx
0x1400142d9  call    WPP_SF_d
0x1400142de  mov     eax, ebx
0x1400142e0  jmp     loc_140014159
0x1400142e5  mov     eax, 0C00000BEh
0x1400142ea  add     rsp, 70h
  ... truncated ...
```
