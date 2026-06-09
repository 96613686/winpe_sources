# DockingProvider::DeleteProfile(_DOCK_PROFILE *)

- ea: `0x180014a78`
- end: `0x180014b2d`
- name: `?DeleteProfile@DockingProvider@@QEAAJPEAU_DOCK_PROFILE@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(__int64 (__fastcall **this)(struct _DOCK_PROFILE *), struct _DOCK_PROFILE *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a810`

## callees

- `0x18000c348`
- `0x180010664`
- `0x180014a78`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall DockingProvider::DeleteProfile(
        __int64 (__fastcall **this)(struct _DOCK_PROFILE *),
        struct _DOCK_PROFILE *a2)
{
  int v4; // eax
  int v5; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, this, a2);
  }
  v4 = this[26](a2);
  v5 = v4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, this, v4);
  }
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180014a78  mov     [rsp+arg_0], rbx
0x180014a7d  mov     [rsp+arg_8], rsi
0x180014a82  push    rdi
0x180014a83  sub     rsp, 30h
0x180014a87  mov     rbx, rdx
0x180014a8a  mov     rdi, rcx
0x180014a8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a94  lea     rsi, WPP_GLOBAL_Control
0x180014a9b  cmp     rcx, rsi
0x180014a9e  jz      short loc_180014AC9
0x180014aa0  cmp     byte ptr [rcx+19h], 4
0x180014aa4  jb      short loc_180014AC9
0x180014aa6  test    byte ptr [rcx+1Ch], 1
0x180014aaa  jz      short loc_180014AC9
0x180014aac  mov     rcx, [rcx+10h]
0x180014ab0  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180014ab7  mov     edx, 26h ; '&'
0x180014abc  mov     [rsp+38h+var_18], rbx
0x180014ac1  mov     r9, rdi
0x180014ac4  call    WPP_SF_qq
0x180014ac9  mov     rax, [rdi+0D0h]
0x180014ad0  mov     rcx, rbx
0x180014ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ad8  mov     ebx, eax
0x180014ada  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ae1  cmp     rcx, rsi
0x180014ae4  jz      short loc_180014B0E
0x180014ae6  cmp     byte ptr [rcx+19h], 4
0x180014aea  jb      short loc_180014B0E
0x180014aec  test    byte ptr [rcx+1Ch], 1
0x180014af0  jz      short loc_180014B0E
0x180014af2  mov     rcx, [rcx+10h]
0x180014af6  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180014afd  mov     edx, 27h ; '''
0x180014b02  mov     dword ptr [rsp+38h+var_18], eax
0x180014b06  mov     r9, rdi
0x180014b09  call    WPP_SF_qD
0x180014b0e  test    ebx, ebx
0x180014b10  jle     short loc_180014B1B
0x180014b12  movzx   ebx, bx
0x180014b15  or      ebx, 80070000h
0x180014b1b  mov     rsi, [rsp+38h+arg_8]
0x180014b20  mov     eax, ebx
0x180014b22  mov     rbx, [rsp+38h+arg_0]
0x180014b27  add     rsp, 30h
0x180014b2b  pop     rdi
0x180014b2c  retn
```
