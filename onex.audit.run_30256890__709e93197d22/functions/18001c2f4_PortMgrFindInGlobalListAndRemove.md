# PortMgrFindInGlobalListAndRemove

- ea: `0x18001c2f4`
- end: `0x18001c46d`
- name: `PortMgrFindInGlobalListAndRemove`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001fb58`

## callees

- `0x180005440`
- `0x18001c2f4`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18001c41a`
- `MobileNetworking!ReleaseWriteLock` at `0x18001c41a`
- `MobileNetworking!AcquireWriteLock` at `0x18001c390`
- `MobileNetworking!AcquireWriteLock` at `0x18001c390`

## string_xrefs

- `0x18001c375`: `PortMgrFindInGlobalListAndRemove`
- `0x18001c405`: `PortMgrFindInGlobalListAndRemove`

## pseudocode

```c
__int64 __fastcall PortMgrFindInGlobalListAndRemove(__int64 *a1, int a2)
{
  _QWORD *v4; // rcx
  unsigned int v5; // ebx
  char v6; // di
  __int64 *i; // rax
  __int64 v8; // rcx
  __int64 **v9; // rdx
  __int64 **v10; // rcx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 36, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v6 = 0;
    AcquireWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrFindInGlobalListAndRemove", 310);
    for ( i = (__int64 *)qword_18003DD68; i != &qword_18003DD68; i = (__int64 *)*i )
    {
      if ( a1 == i )
      {
        if ( a2 )
        {
          v8 = *i;
          if ( *(__int64 **)(*i + 8) != i
            || (v9 = (__int64 **)i[1], *v9 != i)
            || (*v9 = (__int64 *)v8,
                *(_QWORD *)(v8 + 8) = v9,
                v10 = (__int64 **)qword_18003DD80,
                *(__int64 **)qword_18003DD80 != &qword_18003DD78) )
          {
            __fastfail(3u);
          }
          *i = (__int64)&qword_18003DD78;
          i[1] = (__int64)v10;
          *v10 = i;
          qword_18003DD80 = (__int64)i;
        }
        v6 = 1;
        break;
      }
    }
    ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrFindInGlobalListAndRemove", 339);
    v5 = v6 == 0 ? 6 : 0;
    goto LABEL_19;
  }
  v5 = 6;
  if ( v4 == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)v4 + 68) & 1) != 0 )
  {
    WPP_SF_(v4[7], 37, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
LABEL_19:
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x800) != 0 )
    WPP_SF_D(v4[7], 38, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18001c2f4  push    rbx
0x18001c2f6  push    rbp
0x18001c2f7  push    rsi
0x18001c2f8  push    rdi
0x18001c2f9  sub     rsp, 28h
0x18001c2fd  mov     esi, edx
0x18001c2ff  mov     rbx, rcx
0x18001c302  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c309  lea     rbp, WPP_GLOBAL_Control
0x18001c310  cmp     rcx, rbp
0x18001c313  jz      short loc_18001C33A
0x18001c315  test    dword ptr [rcx+44h], 800h
0x18001c31c  jz      short loc_18001C33A
0x18001c31e  mov     rcx, [rcx+38h]
0x18001c322  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18001c329  mov     edx, 24h ; '$'
0x18001c32e  call    WPP_SF_
0x18001c333  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c33a  test    rbx, rbx
0x18001c33d  jnz     short loc_18001C372
0x18001c33f  mov     ebx, 6
0x18001c344  cmp     rcx, rbp
0x18001c347  jz      loc_18001C45B
0x18001c34d  mov     dil, 1
0x18001c350  test    [rcx+44h], dil
0x18001c354  jz      loc_18001C435
0x18001c35a  mov     rcx, [rcx+38h]
0x18001c35e  lea     edx, [rbx+1Fh]
0x18001c361  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18001c368  call    WPP_SF_
0x18001c36d  jmp     loc_18001C42E
0x18001c372  xor     dil, dil
0x18001c375  lea     r8, aPortmgrfinding; "PortMgrFindInGlobalListAndRemove"
0x18001c37c  mov     r9d, 136h
0x18001c382  lea     rdx, qword_18003DD98
0x18001c389  lea     rcx, g_OneXInfo
0x18001c390  call    cs:__imp_AcquireWriteLock
0x18001c396  mov     rax, cs:qword_18003DD68
0x18001c39d  lea     rcx, qword_18003DD68
0x18001c3a4  cmp     rax, rcx
0x18001c3a7  jz      short loc_18001C3FF
0x18001c3a9  cmp     rbx, rax
0x18001c3ac  jz      short loc_18001C3B3
0x18001c3ae  mov     rax, [rax]
0x18001c3b1  jmp     short loc_18001C39D
0x18001c3b3  test    esi, esi
0x18001c3b5  jz      short loc_18001C3FC
0x18001c3b7  mov     rcx, [rax]
0x18001c3ba  cmp     [rcx+8], rax
0x18001c3be  jnz     loc_18001C466
0x18001c3c4  mov     rdx, [rax+8]
0x18001c3c8  cmp     [rdx], rax
0x18001c3cb  jnz     loc_18001C466
0x18001c3d1  mov     [rdx], rcx
0x18001c3d4  mov     [rcx+8], rdx
0x18001c3d8  lea     rdx, qword_18003DD78
0x18001c3df  mov     rcx, cs:qword_18003DD80
0x18001c3e6  cmp     [rcx], rdx
0x18001c3e9  jnz     short loc_18001C466
0x18001c3eb  mov     [rax], rdx
0x18001c3ee  mov     [rax+8], rcx
0x18001c3f2  mov     [rcx], rax
0x18001c3f5  mov     cs:qword_18003DD80, rax
0x18001c3fc  mov     dil, 1
0x18001c3ff  mov     r9d, 153h
0x18001c405  lea     r8, aPortmgrfinding; "PortMgrFindInGlobalListAndRemove"
0x18001c40c  lea     rdx, qword_18003DD98
0x18001c413  lea     rcx, g_OneXInfo
0x18001c41a  call    cs:__imp_ReleaseWriteLock
0x18001c420  neg     dil
0x18001c423  mov     ebx, 6
0x18001c428  sbb     eax, eax
0x18001c42a  not     eax
0x18001c42c  and     ebx, eax
0x18001c42e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c435  cmp     rcx, rbp
0x18001c438  jz      short loc_18001C45B
0x18001c43a  test    dword ptr [rcx+44h], 800h
0x18001c441  jz      short loc_18001C45B
0x18001c443  mov     rcx, [rcx+38h]
0x18001c447  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18001c44e  mov     edx, 26h ; '&'
0x18001c453  mov     r9d, ebx
0x18001c456  call    WPP_SF_D
0x18001c45b  mov     eax, ebx
0x18001c45d  add     rsp, 28h
0x18001c461  pop     rdi
0x18001c462  pop     rsi
0x18001c463  pop     rbp
0x18001c464  pop     rbx
0x18001c465  retn
0x18001c466  mov     ecx, 3
0x18001c46b  int     29h; Win8: RtlFailFast(ecx)
```
