# CDockInterface::DeviceInstancePathToDockProfile(ushort const *,_DOCK_PROFILE *)

- ea: `0x18001abac`
- end: `0x18001ad58`
- name: `?DeviceInstancePathToDockProfile@CDockInterface@@AEAAJPEBGPEAU_DOCK_PROFILE@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(DockingProviders **this, const unsigned __int16 *, struct _DOCK_PROFILE *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x18001a9e0`
- `0x18001aad0`
- `0x18001afd0`

## callees

- `0x18000c308`
- `0x1800104e4`
- `0x1800151b8`
- `0x18001abac`
- `0x18001ad60`
- `0x18001b994`
- `0x18001c6fc`
- `0x18001ca3e`
- `0x18001ca70`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18001abfe`
- `msvcrt!wcsnlen` at `0x18001abfe`

## pseudocode

```c
__int64 __fastcall CDockInterface::DeviceInstancePathToDockProfile(
        DockingProviders **this,
        const unsigned __int16 *a2,
        struct _DOCK_PROFILE *a3)
{
  size_t v6; // rax
  __int64 result; // rax
  int v8; // edx
  int v9; // r8d
  int DockProfile; // ebx
  int v11[4]; // [rsp+30h] [rbp-4B8h] BYREF
  _BYTE v12[528]; // [rsp+40h] [rbp-4A8h] BYREF
  int v13; // [rsp+250h] [rbp-298h] BYREF
  __int16 v14; // [rsp+254h] [rbp-294h]

  if ( a2 && a3 )
  {
    memset_0(v12, 0, 0x480u);
    v6 = wcsnlen(a2, 0x208u);
    result = CDockInterface::DeviceInstancePathToVisibleDock(this, v6, a2, (struct _VISIBLE_DOCK *)v12);
    if ( (int)result < 0 )
      return result;
    v11[0] = 0;
    if ( CDockInterface::QueryConnectedDockProfile((CDockInterface *)this, a3, v11) >= 0
      && v11[0] == 1
      && *((_DWORD *)a3 + 132) == v13
      && *((_WORD *)a3 + 266) == v14 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q_MAC_S(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, (_DWORD)this, (__int64)&v13, (__int64)a3);
      }
      return 0;
    }
    DockProfile = DockingProviders::FindDockProfile(this[2], (const struct _VISIBLE_DOCK *)v12, a3);
    if ( DockProfile >= 0 )
      return 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qdS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        (unsigned int)&WPP_b415491bb2933ebae3e7436051291308_Traceguids,
        (_DWORD)this,
        DockProfile,
        (__int64)a2);
    }
    return (unsigned int)DockProfile;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_b415491bb2933ebae3e7436051291308_Traceguids, this);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18001abac  push    rbx
0x18001abae  push    rsi
0x18001abaf  push    rdi
0x18001abb0  sub     rsp, 4D0h
0x18001abb7  mov     rax, cs:__security_cookie
0x18001abbe  xor     rax, rsp
0x18001abc1  mov     [rsp+4E8h+var_28], rax
0x18001abc9  mov     rbx, r8
0x18001abcc  mov     rsi, rdx
0x18001abcf  mov     rdi, rcx
0x18001abd2  test    rdx, rdx
0x18001abd5  jz      loc_18001AD01
0x18001abdb  test    rbx, rbx
0x18001abde  jz      loc_18001AD01
0x18001abe4  xor     edx, edx; Val
0x18001abe6  lea     rcx, [rsp+4E8h+var_4A8]; void *
0x18001abeb  mov     r8d, 480h; Size
0x18001abf1  call    memset_0
0x18001abf6  mov     edx, 208h; MaxCount
0x18001abfb  mov     rcx, rsi; Source
0x18001abfe  call    cs:__imp_wcsnlen
0x18001ac04  lea     r9, [rsp+4E8h+var_4A8]; struct _VISIBLE_DOCK *
0x18001ac09  mov     r8, rsi; unsigned __int16 *
0x18001ac0c  mov     rdx, rax; unsigned __int64
0x18001ac0f  mov     rcx, rdi; this
0x18001ac12  call    ?DeviceInstancePathToVisibleDock@CDockInterface@@AEAAJ_KPEBGPEAU_VISIBLE_DOCK@@@Z; CDockInterface::DeviceInstancePathToVisibleDock(unsigned __int64,ushort const *,_VISIBLE_DOCK *)
0x18001ac17  test    eax, eax
0x18001ac19  js      loc_18001AD3D
0x18001ac1f  lea     r8, [rsp+4E8h+var_4B8]; int *
0x18001ac24  mov     [rsp+4E8h+var_4B8], 0
0x18001ac2c  mov     rdx, rbx; struct _DOCK_PROFILE *
0x18001ac2f  mov     rcx, rdi; this
0x18001ac32  call    ?QueryConnectedDockProfile@CDockInterface@@AEAAJPEAU_DOCK_PROFILE@@PEAH@Z; CDockInterface::QueryConnectedDockProfile(_DOCK_PROFILE *,int *)
0x18001ac37  test    eax, eax
0x18001ac39  js      short loc_18001ACA6
0x18001ac3b  cmp     [rsp+4E8h+var_4B8], 1
0x18001ac40  jnz     short loc_18001ACA6
0x18001ac42  mov     eax, [rbx+210h]
0x18001ac48  cmp     eax, [rsp+4E8h+var_298]
0x18001ac4f  jnz     short loc_18001ACA6
0x18001ac51  movzx   eax, word ptr [rbx+214h]
0x18001ac58  cmp     ax, [rsp+4E8h+var_294]
0x18001ac60  jnz     short loc_18001ACA6
0x18001ac62  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac69  lea     rax, WPP_GLOBAL_Control
0x18001ac70  cmp     rcx, rax
0x18001ac73  jz      short loc_18001AC9F
0x18001ac75  cmp     byte ptr [rcx+19h], 3
0x18001ac79  jb      short loc_18001AC9F
0x18001ac7b  test    byte ptr [rcx+1Ch], 1
0x18001ac7f  jz      short loc_18001AC9F
0x18001ac81  mov     rcx, [rcx+10h]
0x18001ac85  lea     rax, [rsp+4E8h+var_298]
0x18001ac8d  mov     [rsp+4E8h+var_4C0], rbx
0x18001ac92  mov     r9, rdi
0x18001ac95  mov     [rsp+4E8h+var_4C8], rax
0x18001ac9a  call    WPP_SF_q_MAC_S
0x18001ac9f  xor     eax, eax
0x18001aca1  jmp     loc_18001AD3D
0x18001aca6  mov     rcx, [rdi+10h]; this
0x18001acaa  lea     rdx, [rsp+4E8h+var_4A8]; struct _VISIBLE_DOCK *
0x18001acaf  mov     r8, rbx; struct _DOCK_PROFILE *
0x18001acb2  call    ?FindDockProfile@DockingProviders@@QEAAJPEBU_VISIBLE_DOCK@@PEAU_DOCK_PROFILE@@@Z; DockingProviders::FindDockProfile(_VISIBLE_DOCK const *,_DOCK_PROFILE *)
0x18001acb7  mov     ebx, eax
0x18001acb9  test    eax, eax
0x18001acbb  jns     short loc_18001AC9F
0x18001acbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001acc4  lea     rax, WPP_GLOBAL_Control
0x18001accb  cmp     rcx, rax
0x18001acce  jz      short loc_18001ACFD
0x18001acd0  cmp     byte ptr [rcx+19h], 1
0x18001acd4  jb      short loc_18001ACFD
0x18001acd6  test    byte ptr [rcx+1Ch], 1
0x18001acda  jz      short loc_18001ACFD
0x18001acdc  mov     rcx, [rcx+10h]
0x18001ace0  lea     r8, WPP_b415491bb2933ebae3e7436051291308_Traceguids
0x18001ace7  mov     edx, 21h ; '!'
0x18001acec  mov     [rsp+4E8h+var_4C0], rsi
0x18001acf1  mov     r9, rdi
0x18001acf4  mov     dword ptr [rsp+4E8h+var_4C8], ebx
0x18001acf8  call    WPP_SF_qdS
0x18001acfd  mov     eax, ebx
0x18001acff  jmp     short loc_18001AD3D
0x18001ad01  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad08  lea     rax, WPP_GLOBAL_Control
0x18001ad0f  cmp     rcx, rax
0x18001ad12  jz      short loc_18001AD38
0x18001ad14  cmp     byte ptr [rcx+19h], 1
0x18001ad18  jb      short loc_18001AD38
0x18001ad1a  test    byte ptr [rcx+1Ch], 1
0x18001ad1e  jz      short loc_18001AD38
0x18001ad20  mov     rcx, [rcx+10h]
0x18001ad24  lea     r8, WPP_b415491bb2933ebae3e7436051291308_Traceguids
0x18001ad2b  mov     edx, 1Fh
0x18001ad30  mov     r9, rdi
0x18001ad33  call    WPP_SF_q
0x18001ad38  mov     eax, 80070057h
0x18001ad3d  mov     rcx, [rsp+4E8h+var_28]
0x18001ad45  xor     rcx, rsp; StackCookie
0x18001ad48  call    __security_check_cookie
0x18001ad4d  add     rsp, 4D0h
0x18001ad54  pop     rdi
0x18001ad55  pop     rsi
0x18001ad56  pop     rbx
0x18001ad57  retn
```
