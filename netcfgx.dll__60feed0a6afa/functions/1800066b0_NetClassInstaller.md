# NetClassInstaller

- ea: `0x1800066b0`
- end: `0x18000677b`
- name: `NetClassInstaller`
- size: `203`
- prototype: `__int64 __fastcall(unsigned int, void *, struct _SP_DEVINFO_DATA *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800066b0`
- `0x1800068a0`
- `0x1800068e4`
- `0x180006ac4`

## pseudocode

```c
__int64 __fastcall NetClassInstaller(unsigned int a1, void *a2, struct _SP_DEVINFO_DATA *a3)
{
  int v6; // eax
  __int64 v7; // r8
  unsigned __int16 v8; // cx
  int v9; // eax
  unsigned int v10; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 9u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_791ea57c360e3e7f6c080c026470c4c9_Traceguids, a1);
  }
  try
  {
    v6 = _HrNetClassInstaller(a1, a2, a3);
    v8 = v6;
    if ( v6 >= 0 )
    {
      v10 = 0;
    }
    else
    {
      v9 = v6 & 0x1FFF0000;
      if ( v9 == 983040 )
      {
        v10 = v8 | 0xE0000000;
      }
      else if ( v9 == 458752 )
      {
        v10 = v8;
      }
      else
      {
        v10 = 31;
      }
    }
  }
  catch ( std::bad_alloc )
  {
    v10 = 8;
  }
  v6 = _HrNetClassInstaller(a1, a2, a3);
  v8 = v6;
}

```

## disassembly

```asm
0x1800066b0  push    rbx
0x1800066b2  push    rsi
0x1800066b3  push    rdi
0x1800066b4  push    r14
0x1800066b6  sub     rsp, 28h
0x1800066ba  mov     rsi, r8
0x1800066bd  mov     r14, rdx
0x1800066c0  mov     ebx, ecx
0x1800066c2  lea     rdi, WPP_GLOBAL_Control
0x1800066c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066d0  cmp     rcx, rdi
0x1800066d3  jz      short loc_1800066FA
0x1800066d5  cmp     byte ptr [rcx+19h], 9
0x1800066d9  jb      short loc_1800066FA
0x1800066db  test    byte ptr [rcx+1Ch], 40h
0x1800066df  jz      short loc_1800066FA
0x1800066e1  mov     edx, 0Ah
0x1800066e6  mov     r9d, ebx
0x1800066e9  lea     r8, WPP_791ea57c360e3e7f6c080c026470c4c9_Traceguids
0x1800066f0  mov     rcx, [rcx+10h]
0x1800066f4  call    WPP_SF_d
0x1800066f9  nop
0x1800066fa  mov     r8, rsi; struct _SP_DEVINFO_DATA *
0x1800066fd  mov     rdx, r14; void *
0x180006700  mov     ecx, ebx; unsigned int
0x180006702  call    ?_HrNetClassInstaller@@YAJIPEAXPEAU_SP_DEVINFO_DATA@@@Z; _HrNetClassInstaller(uint,void *,_SP_DEVINFO_DATA *)
0x180006707  mov     ecx, eax
0x180006709  test    eax, eax
0x18000670b  jns     short loc_180006737
0x18000670d  and     eax, 1FFF0000h
0x180006712  cmp     eax, 0F0000h
0x180006717  jz      short loc_18000672C
0x180006719  cmp     eax, 70000h
0x18000671e  jz      short loc_180006727
0x180006720  mov     ebx, 1Fh
0x180006725  jmp     short loc_180006739
0x180006727  movzx   ebx, cx
0x18000672a  jmp     short loc_180006739
0x18000672c  movzx   ebx, cx
0x18000672f  or      ebx, 0E0000000h
0x180006735  jmp     short loc_180006739
0x180006737  xor     ebx, ebx
0x180006739  jmp     short loc_180006746
0x18000673b  lea     rdi, WPP_GLOBAL_Control
0x180006742  mov     ebx, [rsp+48h+arg_18]
0x180006746  mov     rcx, cs:WPP_GLOBAL_Control
0x18000674d  cmp     rcx, rdi
0x180006750  jz      short loc_18000676F
0x180006752  cmp     byte ptr [rcx+19h], 9
0x180006756  jb      short loc_18000676F
0x180006758  test    byte ptr [rcx+1Ch], 40h
0x18000675c  jz      short loc_18000676F
0x18000675e  mov     edx, 0Bh
0x180006763  mov     r9d, ebx
0x180006766  mov     rcx, [rcx+10h]
0x18000676a  call    WPP_SF_D
0x18000676f  mov     eax, ebx
0x180006771  add     rsp, 28h
0x180006775  pop     r14
0x180006777  pop     rdi
0x180006778  pop     rsi
0x180006779  pop     rbx
0x18000677a  retn
```
