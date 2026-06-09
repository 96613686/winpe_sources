# DiskGetCacheInformation

- ea: `0x140012ca0`
- end: `0x140013095`
- name: `DiskGetCacheInformation`
- size: `1013`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000e2a0`
- `0x140011bc0`
- `0x140012b30`

## callees

- `0x140003f78`
- `0x140004078`
- `0x140012ca0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140012e3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012eb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013001`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012e3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012eb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013001`
- `ntoskrnl!ExAllocatePool2` at `0x140012cc1`
- `ntoskrnl!ExAllocatePool2` at `0x140012cc1`
- `CLASSPNP!ClassFindModePage` at `0x140012d1d`
- `CLASSPNP!ClassFindModePage` at `0x140012d1d`
- `CLASSPNP!ClassModeSense` at `0x140012ce9`
- `CLASSPNP!ClassModeSense` at `0x140012e81`
- `CLASSPNP!ClassModeSense` at `0x140012ce9`
- `CLASSPNP!ClassModeSense` at `0x140012e81`

## pseudocode

```c
__int64 __fastcall DiskGetCacheInformation(__int64 a1, __int64 a2)
{
  CHAR *Pool2; // rax
  CHAR *v5; // rbx
  ULONG v6; // ecx
  ULONG v7; // ebp
  _BYTE *ModePage; // rax
  int v9; // edx
  int v10; // r9d
  bool v11; // r11
  char v12; // bp
  unsigned int v13; // ecx
  int v14; // r10d
  int v15; // ecx
  __int16 v16; // r14
  __int16 v17; // r15
  __int16 v18; // r12

  Pool2 = (CHAR *)ExAllocatePool2(72, 192, 1128555347);
  v5 = Pool2;
  if ( Pool2 )
  {
    v6 = ClassModeSense(*(PDEVICE_OBJECT *)(a1 + 8), Pool2, 0xC0u, 8u);
    if ( v6 >= 4 || (v6 = ClassModeSense(*(PDEVICE_OBJECT *)(a1 + 8), v5, 0xC0u, 8u), v6 >= 4) )
    {
      v7 = (unsigned __int8)*v5 + 1;
      if ( v6 <= v7 )
        v7 = v6;
      ModePage = ClassFindModePage(v5, v7, 8u, 1u);
      if ( ModePage )
      {
        if ( ModePage + 12 > &v5[v7] )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
          }
          ExFreePoolWithTag(v5, 0);
          return 3221225473LL;
        }
        else
        {
          *(_OWORD *)a2 = 0;
          *(_QWORD *)(a2 + 16) = 0;
          v10 = 2;
          *(_BYTE *)a2 = *ModePage >> 7;
          v11 = (ModePage[2] & 1) == 0;
          *(_BYTE *)(a2 + 1) = v11;
          v12 = (ModePage[2] & 4) != 0;
          *(_BYTE *)(a2 + 2) = v12;
          v13 = (unsigned __int8)ModePage[3];
          if ( (unsigned __int8)v13 >> 4 == 15 )
          {
            v14 = 2;
          }
          else if ( (unsigned __int8)v13 >> 4 == 2 )
          {
            v14 = 15;
          }
          else
          {
            v14 = v13 >> 4;
          }
          *(_DWORD *)(a2 + 4) = v14;
          v15 = (unsigned __int8)ModePage[3];
          if ( (v15 & 0xF) != 0xF )
          {
            if ( (v15 & 0xF) == 2 )
              v10 = 15;
            else
              v10 = v15 & 0xF;
          }
          *(_DWORD *)(a2 + 8) = v10;
          v16 = (unsigned __int8)ModePage[5] + ((unsigned __int8)ModePage[4] << 8);
          *(_WORD *)(a2 + 12) = v16;
          v17 = (unsigned __int8)ModePage[7] + ((unsigned __int8)ModePage[6] << 8);
          *(_WORD *)(a2 + 16) = v17;
          v18 = (unsigned __int8)ModePage[9] + ((unsigned __int8)ModePage[8] << 8);
          *(_WORD *)(a2 + 18) = v18;
          if ( (ModePage[2] & 2) != 0 )
          {
            *(_BYTE *)(a2 + 14) = 1;
            v9 = (unsigned __int8)ModePage[10] << 8;
            LOWORD(v9) = (unsigned __int8)ModePage[11] + ((unsigned __int8)ModePage[10] << 8);
            *(_WORD *)(a2 + 20) = v9;
          }
          if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
            McTemplateK0uuuuuhhhhq_EtwWriteTransfer(
              v15,
              v9,
              (_DWORD)ModePage,
              v11,
              v12,
              v14,
              v10,
              *(_BYTE *)(a2 + 14),
              v16,
              v17,
              v18,
              *(_WORD *)(a2 + 20),
              *(_DWORD *)(a1 + 588));
          ExFreePoolWithTag(v5, 0);
          return 0;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
        }
        ExFreePoolWithTag(v5, 0);
        return 3221225659LL;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
      }
      ExFreePoolWithTag(v5, 0);
      return 3221225861LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140012ca0  push    rbx
0x140012ca2  push    rsi
0x140012ca3  push    rdi
0x140012ca4  sub     rsp, 80h
0x140012cab  mov     rsi, rdx
0x140012cae  mov     rdi, rcx
0x140012cb1  mov     edx, 0C0h
0x140012cb6  mov     ecx, 48h ; 'H'
0x140012cbb  mov     r8d, 43446353h
0x140012cc1  call    cs:__imp_ExAllocatePool2
0x140012cc8  nop     dword ptr [rax+rax+00h]
0x140012ccd  mov     rbx, rax
0x140012cd0  test    rax, rax
0x140012cd3  jz      loc_140012EFB
0x140012cd9  mov     rcx, [rdi+8]; DeviceObject
0x140012cdd  mov     r9b, 8; PageMode
0x140012ce0  mov     r8d, 0C0h; Length
0x140012ce6  mov     rdx, rax; ModeSenseBuffer
0x140012ce9  call    cs:__imp_ClassModeSense
0x140012cf0  nop     dword ptr [rax+rax+00h]
0x140012cf5  mov     ecx, eax
0x140012cf7  cmp     eax, 4
0x140012cfa  jb      loc_140012E71
0x140012d00  mov     [rsp+98h+arg_0], rbp
0x140012d08  mov     r9b, 1; Use6Byte
0x140012d0b  movzx   ebp, byte ptr [rbx]
0x140012d0e  mov     r8b, 8; PageMode
0x140012d11  inc     ebp
0x140012d13  cmp     ecx, ebp
0x140012d15  cmovbe  ebp, ecx
0x140012d18  mov     rcx, rbx; ModeSenseBuffer
0x140012d1b  mov     edx, ebp; Length
0x140012d1d  call    cs:__imp_ClassFindModePage
0x140012d24  nop     dword ptr [rax+rax+00h]
0x140012d29  mov     r8, rax
0x140012d2c  test    rax, rax
0x140012d2f  jz      loc_140012F1F
0x140012d35  mov     ecx, ebp
0x140012d37  add     rax, 0Ch
0x140012d3b  add     rcx, rbx
0x140012d3e  cmp     rax, rcx
0x140012d41  ja      loc_140012FC7
0x140012d47  xor     eax, eax
0x140012d49  mov     [rsp+98h+arg_8], r12
0x140012d51  mov     [rsp+98h+arg_10], r13
0x140012d59  xorps   xmm0, xmm0
0x140012d5c  movups  xmmword ptr [rsi], xmm0
0x140012d5f  mov     [rsi+10h], rax
0x140012d63  mov     r9d, 2
0x140012d69  movzx   eax, byte ptr [r8]
0x140012d6d  shr     al, 7
0x140012d70  mov     [rsi], al
0x140012d72  movzx   r11d, byte ptr [r8+2]
0x140012d77  not     r11b
0x140012d7a  mov     [rsp+98h+var_20], r14
0x140012d7f  and     r11b, 1
0x140012d83  mov     [rsp+98h+var_28], r15
0x140012d88  mov     [rsi+1], r11b
0x140012d8c  movzx   ebp, byte ptr [r8+2]
0x140012d91  shr     bpl, 2
0x140012d95  and     bpl, 1
0x140012d99  mov     [rsi+2], bpl
0x140012d9d  movzx   ecx, byte ptr [r8+3]
0x140012da2  movzx   eax, cl
0x140012da5  shr     al, 4
0x140012da8  cmp     al, 0Fh
0x140012daa  jnz     loc_140012EE6
0x140012db0  mov     r10d, r9d
0x140012db3  mov     [rsi+4], r10d
0x140012db7  movzx   ecx, byte ptr [r8+3]
0x140012dbc  movzx   eax, cl
0x140012dbf  and     al, 0Fh
0x140012dc1  cmp     al, 0Fh
0x140012dc3  jnz     loc_140012ED1
0x140012dc9  mov     [rsi+8], r9d
0x140012dcd  mov     r13d, 100h
0x140012dd3  movzx   eax, byte ptr [r8+5]
0x140012dd8  movzx   r14d, byte ptr [r8+4]
0x140012ddd  imul    r14d, r13d
0x140012de1  add     r14w, ax
0x140012de5  mov     [rsi+0Ch], r14w
0x140012dea  movzx   eax, byte ptr [r8+7]
0x140012def  movzx   r15d, byte ptr [r8+6]
0x140012df4  imul    r15d, r13d
0x140012df8  add     r15w, ax
0x140012dfc  mov     [rsi+10h], r15w
0x140012e01  movzx   r12d, byte ptr [r8+8]
0x140012e06  movzx   eax, byte ptr [r8+9]
0x140012e0b  imul    r12d, r13d
0x140012e0f  add     r12w, ax
0x140012e13  mov     [rsi+12h], r12w
0x140012e18  test    byte ptr [r8+2], 2
0x140012e1d  jnz     loc_14001302D
0x140012e23  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 1
0x140012e2a  mov     r13, [rsp+98h+arg_10]
0x140012e32  jnz     loc_14001304B
0x140012e38  xor     edx, edx; Tag
0x140012e3a  mov     rcx, rbx; P
0x140012e3d  call    cs:__imp_ExFreePoolWithTag
0x140012e44  nop     dword ptr [rax+rax+00h]
0x140012e49  mov     r15, [rsp+98h+var_28]
0x140012e4e  xor     eax, eax
0x140012e50  mov     r14, [rsp+98h+var_20]
0x140012e55  mov     r12, [rsp+98h+arg_8]
0x140012e5d  mov     rbp, [rsp+98h+arg_0]
0x140012e65  add     rsp, 80h
0x140012e6c  pop     rdi
0x140012e6d  pop     rsi
0x140012e6e  pop     rbx
0x140012e6f  retn
0x140012e71  mov     rcx, [rdi+8]; DeviceObject
0x140012e75  mov     r9b, 8; PageMode
0x140012e78  mov     r8d, 0C0h; Length
0x140012e7e  mov     rdx, rbx; ModeSenseBuffer
0x140012e81  call    cs:__imp_ClassModeSense
0x140012e88  nop     dword ptr [rax+rax+00h]
0x140012e8d  mov     ecx, eax
0x140012e8f  cmp     eax, 4
0x140012e92  jnb     loc_140012D00
0x140012e98  mov     rcx, cs:WPP_GLOBAL_Control
0x140012e9f  lea     rax, WPP_GLOBAL_Control
0x140012ea6  cmp     rcx, rax
0x140012ea9  jnz     loc_140012F71
0x140012eaf  xor     edx, edx; Tag
0x140012eb1  mov     rcx, rbx; P
0x140012eb4  call    cs:__imp_ExFreePoolWithTag
0x140012ebb  nop     dword ptr [rax+rax+00h]
0x140012ec0  mov     eax, 0C0000185h
0x140012ec5  add     rsp, 80h
0x140012ecc  pop     rdi
0x140012ecd  pop     rsi
0x140012ece  pop     rbx
0x140012ecf  retn
0x140012ed1  cmp     al, r9b
0x140012ed4  jz      loc_140013022
0x140012eda  mov     r9d, ecx
0x140012edd  and     r9d, 0Fh
0x140012ee1  jmp     loc_140012DC9
0x140012ee6  cmp     al, r9b
0x140012ee9  jz      loc_140013017
0x140012eef  mov     r10d, ecx
0x140012ef2  shr     r10d, 4
0x140012ef6  jmp     loc_140012DB3
0x140012efb  mov     rcx, cs:WPP_GLOBAL_Control
0x140012f02  lea     rax, WPP_GLOBAL_Control
0x140012f09  cmp     rcx, rax
0x140012f0c  jnz     short loc_140012F4D
0x140012f0e  mov     eax, 0C000009Ah
0x140012f13  add     rsp, 80h
0x140012f1a  pop     rdi
0x140012f1b  pop     rsi
0x140012f1c  pop     rbx
0x140012f1d  retn
0x140012f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140012f26  lea     rax, WPP_GLOBAL_Control
0x140012f2d  cmp     rcx, rax
0x140012f30  jnz     short loc_140012FA0
0x140012f32  xor     edx, edx; Tag
0x140012f34  mov     rcx, rbx; P
0x140012f37  call    cs:__imp_ExFreePoolWithTag
0x140012f3e  nop     dword ptr [rax+rax+00h]
0x140012f43  mov     eax, 0C00000BBh
0x140012f48  jmp     loc_140012E5D
0x140012f4d  mov     eax, [rcx+2Ch]
0x140012f50  test    al, 10h
0x140012f52  jz      short loc_140012F0E
0x140012f54  cmp     byte ptr [rcx+29h], 2
0x140012f58  jb      short loc_140012F0E
0x140012f5a  mov     rcx, [rcx+18h]
0x140012f5e  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140012f65  mov     edx, 32h ; '2'
0x140012f6a  call    WPP_SF_
0x140012f6f  jmp     short loc_140012F0E
0x140012f71  mov     eax, [rcx+2Ch]
0x140012f74  test    al, 10h
0x140012f76  jz      loc_140012EAF
0x140012f7c  cmp     byte ptr [rcx+29h], 2
0x140012f80  jb      loc_140012EAF
0x140012f86  mov     rcx, [rcx+18h]
0x140012f8a  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140012f91  mov     edx, 33h ; '3'
0x140012f96  call    WPP_SF_
0x140012f9b  jmp     loc_140012EAF
0x140012fa0  mov     eax, [rcx+2Ch]
0x140012fa3  test    al, 10h
0x140012fa5  jz      short loc_140012F32
0x140012fa7  cmp     byte ptr [rcx+29h], 2
0x140012fab  jb      short loc_140012F32
0x140012fad  mov     rcx, [rcx+18h]
0x140012fb1  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140012fb8  mov     edx, 34h ; '4'
0x140012fbd  call    WPP_SF_
0x140012fc2  jmp     loc_140012F32
0x140012fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x140012fce  lea     rax, WPP_GLOBAL_Control
0x140012fd5  cmp     rcx, rax
0x140012fd8  jz      short loc_140012FFC
0x140012fda  mov     eax, [rcx+2Ch]
0x140012fdd  test    al, 10h
0x140012fdf  jz      short loc_140012FFC
0x140012fe1  cmp     byte ptr [rcx+29h], 2
0x140012fe5  jb      short loc_140012FFC
0x140012fe7  mov     rcx, [rcx+18h]
0x140012feb  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140012ff2  mov     edx, 35h ; '5'
0x140012ff7  call    WPP_SF_
0x140012ffc  xor     edx, edx; Tag
0x140012ffe  mov     rcx, rbx; P
0x140013001  call    cs:__imp_ExFreePoolWithTag
0x140013008  nop     dword ptr [rax+rax+00h]
0x14001300d  mov     eax, 0C0000001h
0x140013012  jmp     loc_140012E5D
0x140013017  mov     r10d, 0Fh
0x14001301d  jmp     loc_140012DB3
0x140013022  mov     r9d, 0Fh
0x140013028  jmp     loc_140012DC9
0x14001302d  mov     byte ptr [rsi+0Eh], 1
0x140013031  movzx   edx, byte ptr [r8+0Ah]
0x140013036  movzx   eax, byte ptr [r8+0Bh]
0x14001303b  imul    edx, r13d
0x14001303f  add     dx, ax
0x140013042  mov     [rsi+14h], dx
0x140013046  jmp     loc_140012E23
0x14001304b  mov     eax, [rdi+24Ch]
0x140013051  mov     [rsp+98h+var_38], eax
0x140013055  movzx   eax, word ptr [rsi+14h]
0x140013059  mov     [rsp+98h+var_40], ax
0x14001305e  movzx   eax, byte ptr [rsi+0Eh]
0x140013062  mov     [rsp+98h+var_48], r12w
0x140013068  mov     [rsp+98h+var_50], r15w
0x14001306e  mov     [rsp+98h+var_58], r14w
0x140013074  mov     [rsp+98h+var_60], al
0x140013078  mov     [rsp+98h+var_68], r9b
0x14001307d  movzx   r9d, r11b
0x140013081  mov     [rsp+98h+var_70], r10b
0x140013086  mov     [rsp+98h+var_78], bpl
0x14001308b  call    McTemplateK0uuuuuhhhhq_EtwWriteTransfer
0x140013090  jmp     loc_140012E38
```
