# DockingProvider::CompletePairWithDock(unsigned __int64,ushort,uchar *,_DOCK_PROFILE *)

- ea: `0x1800144a8`
- end: `0x1800145c6`
- name: `?CompletePairWithDock@DockingProvider@@QEAAJ_KGPEAEPEAU_DOCK_PROFILE@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(DockingProvider *this, __int64, unsigned __int16, unsigned __int8 *, struct _DOCK_PROFILE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800145cc`

## callees

- `0x18000c308`
- `0x1800144a8`
- `0x180017854`
- `0x180017af4`
- `0x18001ca3e`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall DockingProvider::CompletePairWithDock(
        DockingProvider *this,
        __int64 a2,
        unsigned __int16 a3,
        unsigned __int8 *a4,
        struct _DOCK_PROFILE *a5)
{
  int v6; // ebx
  __int64 v9; // r8
  int v11; // eax
  __int64 v12; // r8
  int v13; // ebx

  v6 = a3;
  memset_0(a5, 0, 0x488u);
  if ( *((_QWORD *)this + 16) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qID(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v9, this, a2, v6);
    }
    v11 = (*((__int64 (__fastcall **)(__int64, _QWORD, unsigned __int8 *, struct _DOCK_PROFILE *))this + 16))(
            a2,
            (unsigned __int16)v6,
            a4,
            a5);
    v13 = v11;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v12, this, v11, a5);
    }
    if ( v13 > 0 )
      return (unsigned __int16)v13 | 0x80070000;
    return (unsigned int)v13;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, this);
    }
    return 5023;
  }
}

```

## disassembly

```asm
0x1800144a8  push    rbx
0x1800144aa  push    rbp
0x1800144ab  push    rsi
0x1800144ac  push    rdi
0x1800144ad  push    r14
0x1800144af  push    r15
0x1800144b1  sub     rsp, 38h
0x1800144b5  mov     rbp, [rsp+68h+arg_20]
0x1800144bd  mov     r14, rdx
0x1800144c0  movzx   ebx, r8w
0x1800144c4  mov     rsi, rcx
0x1800144c7  mov     rcx, rbp; void *
0x1800144ca  xor     edx, edx; Val
0x1800144cc  mov     r8d, 488h; Size
0x1800144d2  mov     r15, r9
0x1800144d5  call    memset_0
0x1800144da  cmp     qword ptr [rsi+80h], 0
0x1800144e2  jnz     short loc_180014525
0x1800144e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144eb  lea     rdi, WPP_GLOBAL_Control
0x1800144f2  cmp     rcx, rdi
0x1800144f5  jz      short loc_18001451B
0x1800144f7  cmp     byte ptr [rcx+19h], 1
0x1800144fb  jb      short loc_18001451B
0x1800144fd  test    byte ptr [rcx+1Ch], 1
0x180014501  jz      short loc_18001451B
0x180014503  mov     rcx, [rcx+10h]
0x180014507  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x18001450e  mov     edx, 1Ah
0x180014513  mov     r9, rsi
0x180014516  call    WPP_SF_q
0x18001451b  mov     eax, 139Fh
0x180014520  jmp     loc_1800145B9
0x180014525  mov     rcx, cs:WPP_GLOBAL_Control
0x18001452c  lea     rdi, WPP_GLOBAL_Control
0x180014533  cmp     rcx, rdi
0x180014536  jz      short loc_18001455E
0x180014538  cmp     byte ptr [rcx+19h], 4
0x18001453c  jb      short loc_18001455E
0x18001453e  test    byte ptr [rcx+1Ch], 1
0x180014542  jz      short loc_18001455E
0x180014544  mov     rcx, [rcx+10h]
0x180014548  mov     edx, 1Bh
0x18001454d  mov     dword ptr [rsp+68h+var_40], ebx
0x180014551  mov     r9, rsi
0x180014554  mov     [rsp+68h+var_48], r14
0x180014559  call    WPP_SF_qID
0x18001455e  mov     rax, [rsi+80h]
0x180014565  mov     r9, rbp
0x180014568  mov     r8, r15
0x18001456b  movzx   edx, bx
0x18001456e  mov     rcx, r14
0x180014571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014576  mov     ebx, eax
0x180014578  mov     rcx, cs:WPP_GLOBAL_Control
0x18001457f  cmp     rcx, rdi
0x180014582  jz      short loc_1800145AA
0x180014584  cmp     byte ptr [rcx+19h], 4
0x180014588  jb      short loc_1800145AA
0x18001458a  test    byte ptr [rcx+1Ch], 1
0x18001458e  jz      short loc_1800145AA
0x180014590  mov     rcx, [rcx+10h]
0x180014594  mov     edx, 1Ch
0x180014599  mov     [rsp+68h+var_40], rbp
0x18001459e  mov     r9, rsi
0x1800145a1  mov     dword ptr [rsp+68h+var_48], eax
0x1800145a5  call    WPP_SF_qDq
0x1800145aa  test    ebx, ebx
0x1800145ac  jle     short loc_1800145B7
0x1800145ae  movzx   ebx, bx
0x1800145b1  or      ebx, 80070000h
0x1800145b7  mov     eax, ebx
0x1800145b9  add     rsp, 38h
0x1800145bd  pop     r15
0x1800145bf  pop     r14
0x1800145c1  pop     rdi
0x1800145c2  pop     rsi
0x1800145c3  pop     rbp
0x1800145c4  pop     rbx
0x1800145c5  retn
```
