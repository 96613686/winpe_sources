# DockingProvider::ConfigureAutoConnect(_DOCK_PROFILE *,int)

- ea: `0x18001471c`
- end: `0x1800147cd`
- name: `?ConfigureAutoConnect@DockingProvider@@QEAAJPEAU_DOCK_PROFILE@@H@Z`
- size: `177`
- prototype: `__int64 __fastcall(DockingProvider *this, struct _DOCK_PROFILE *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a810`
- `0x18001a9e0`

## callees

- `0x18000c348`
- `0x180013b24`
- `0x18001471c`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall DockingProvider::ConfigureAutoConnect(
        DockingProvider *this,
        struct _DOCK_PROFILE *a2,
        unsigned int a3)
{
  int v6; // eax
  int v7; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, this, a2, a3);
  }
  v6 = (*((__int64 (__fastcall **)(struct _DOCK_PROFILE *, _QWORD))this + 22))(a2, a3);
  v7 = v6;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, this, v6);
  }
  if ( v7 > 0 )
    return (unsigned __int16)v7 | 0x80070000;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001471c  push    rbx
0x18001471e  push    rbp
0x18001471f  push    rsi
0x180014720  push    rdi
0x180014721  sub     rsp, 38h
0x180014725  mov     ebx, r8d
0x180014728  mov     rsi, rdx
0x18001472b  mov     rdi, rcx
0x18001472e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014735  lea     rbp, WPP_GLOBAL_Control
0x18001473c  cmp     rcx, rbp
0x18001473f  jz      short loc_18001476E
0x180014741  cmp     byte ptr [rcx+19h], 4
0x180014745  jb      short loc_18001476E
0x180014747  test    byte ptr [rcx+1Ch], 1
0x18001474b  jz      short loc_18001476E
0x18001474d  mov     rcx, [rcx+10h]
0x180014751  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180014758  mov     edx, 24h ; '$'
0x18001475d  mov     [rsp+58h+var_30], ebx
0x180014761  mov     r9, rdi
0x180014764  mov     [rsp+58h+var_38], rsi
0x180014769  call    WPP_SF_qqd
0x18001476e  mov     rax, [rdi+0B0h]
0x180014775  mov     edx, ebx
0x180014777  mov     rcx, rsi
0x18001477a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001477f  mov     ebx, eax
0x180014781  mov     rcx, cs:WPP_GLOBAL_Control
0x180014788  cmp     rcx, rbp
0x18001478b  jz      short loc_1800147B5
0x18001478d  cmp     byte ptr [rcx+19h], 4
0x180014791  jb      short loc_1800147B5
0x180014793  test    byte ptr [rcx+1Ch], 1
0x180014797  jz      short loc_1800147B5
0x180014799  mov     rcx, [rcx+10h]
0x18001479d  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x1800147a4  mov     edx, 25h ; '%'
0x1800147a9  mov     dword ptr [rsp+58h+var_38], eax
0x1800147ad  mov     r9, rdi
0x1800147b0  call    WPP_SF_qD
0x1800147b5  test    ebx, ebx
0x1800147b7  jle     short loc_1800147C2
0x1800147b9  movzx   ebx, bx
0x1800147bc  or      ebx, 80070000h
0x1800147c2  mov     eax, ebx
0x1800147c4  add     rsp, 38h
0x1800147c8  pop     rdi
0x1800147c9  pop     rsi
0x1800147ca  pop     rbp
0x1800147cb  pop     rbx
0x1800147cc  retn
```
