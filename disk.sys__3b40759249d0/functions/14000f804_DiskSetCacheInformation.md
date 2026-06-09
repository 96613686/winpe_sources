# DiskSetCacheInformation

- ea: `0x14000f804`
- end: `0x14000fb4a`
- name: `DiskSetCacheInformation`
- size: `838`
- prototype: `__int64 __fastcall(__int64, _BYTE *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000e2a0`
- `0x14000ef98`
- `0x140011bc0`

## callees

- `0x140003f78`
- `0x140004078`
- `0x14000f804`
- `0x140015760`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f97b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fb2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f97b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fb2c`
- `ntoskrnl!ExAllocatePool2` at `0x14000f829`
- `ntoskrnl!ExAllocatePool2` at `0x14000f829`
- `CLASSPNP!ClassFindModePage` at `0x14000f913`
- `CLASSPNP!ClassFindModePage` at `0x14000f913`
- `CLASSPNP!ClassModeSense` at `0x14000f888`
- `CLASSPNP!ClassModeSense` at `0x14000f8a8`
- `CLASSPNP!ClassModeSense` at `0x14000f888`
- `CLASSPNP!ClassModeSense` at `0x14000f8a8`

## pseudocode

```c
__int64 __fastcall DiskSetCacheInformation(__int64 a1, _BYTE *a2)
{
  CHAR *Pool2; // rax
  CHAR *v5; // r14
  ULONG v7; // ecx
  unsigned int v8; // ebx
  ULONG v9; // ebp
  unsigned __int8 *ModePage; // rax
  int v11; // edx
  int v12; // r9d
  unsigned __int8 *v13; // rsi
  int v14; // ebp
  unsigned __int8 v15; // cl
  int v16; // r8d
  unsigned __int8 v17; // al
  int v18; // ecx
  unsigned __int8 v19; // cl
  int v20; // eax
  unsigned int i; // r15d
  __int16 v22; // ax
  __int16 v23; // ax

  Pool2 = (CHAR *)ExAllocatePool2(72, 192, 1128555347);
  v5 = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return 3221225626LL;
  }
  v7 = ClassModeSense(*(PDEVICE_OBJECT *)(a1 + 8), Pool2, 0xC0u, 8u);
  if ( v7 < 4 )
  {
    v7 = ClassModeSense(*(PDEVICE_OBJECT *)(a1 + 8), v5, 0xC0u, 8u);
    if ( v7 < 4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
      }
      v8 = -1073741435;
      goto LABEL_24;
    }
  }
  v9 = (unsigned __int8)*v5 + 1;
  if ( v7 <= v9 )
    v9 = v7;
  ModePage = (unsigned __int8 *)ClassFindModePage(v5, v9, 8u, 1u);
  v13 = ModePage;
  if ( !ModePage )
  {
    v8 = -1073741637;
LABEL_24:
    ExFreePoolWithTag(v5, 0);
    return v8;
  }
  if ( ModePage + 12 > (unsigned __int8 *)&v5[v9] )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    v8 = -1073741823;
    goto LABEL_24;
  }
  *ModePage &= ~0x80u;
  v14 = 0;
  v15 = ModePage[2] & 0xFE | (a2[1] == 0);
  v16 = 15;
  ModePage[2] = v15;
  v17 = v15 ^ (v15 ^ (2 * a2[14])) & 2;
  v13[2] = v17;
  LOBYTE(v11) = v17 ^ (v17 ^ (4 * a2[2])) & 4;
  v13[2] = v11;
  v18 = *((_DWORD *)a2 + 2);
  if ( v18 == 15 )
  {
    v18 = 2;
  }
  else if ( v18 == 2 )
  {
    v18 = 15;
  }
  v19 = v13[3] ^ (v13[3] ^ v18) & 0xF;
  v13[3] = v19;
  v20 = *((_DWORD *)a2 + 1);
  if ( v20 == 15 )
  {
    LOBYTE(v20) = 2;
  }
  else if ( v20 == 2 )
  {
    LOBYTE(v20) = 15;
  }
  LOBYTE(v18) = v19 & 0xF;
  v13[3] = v18 | (16 * v20);
  v13[4] = a2[13];
  v13[5] = a2[12];
  v13[6] = a2[17];
  v13[7] = a2[16];
  v13[8] = a2[19];
  v13[9] = a2[18];
  if ( (v11 & 2) != 0 )
  {
    v13[10] = a2[21];
    v13[11] = a2[20];
  }
  for ( i = 0; i < 2; ++i )
  {
    v14 = DiskModeSelect(*(PDEVICE_OBJECT *)(a1 + 8), v13, (unsigned int)v13[1] + 2);
    if ( v14 >= 0 )
    {
      v22 = *(_WORD *)(a1 + 640);
      if ( a2[2] )
      {
        v23 = v22 | 1;
      }
      else
      {
        v18 = 65534;
        v23 = v22 & 0xFFFE;
      }
      *(_WORD *)(a1 + 640) = v23;
      *(_BYTE *)(a1 + 643) = (*(_WORD *)(a1 + 640) & 1) != 0
                          && (*(_WORD *)(a1 + 640) & 0x10) == 0
                          && (*(_DWORD *)(a1 + 876) & 0x80u) == 0;
      goto LABEL_48;
    }
  }
  if ( v14 < 0 )
  {
    *(_DWORD *)(a1 + 876) |= 0x40u;
    goto LABEL_51;
  }
LABEL_48:
  if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
  {
    LOBYTE(v12) = a2[1];
    McTemplateK0uuuuuhhhhq_EtwWriteTransfer(
      v18,
      v11,
      v16,
      v12,
      a2[2],
      a2[4],
      a2[8],
      a2[14],
      *((_WORD *)a2 + 6),
      *((_WORD *)a2 + 8),
      *((_WORD *)a2 + 9),
      *((_WORD *)a2 + 10),
      *(_DWORD *)(a1 + 588));
  }
LABEL_51:
  ExFreePoolWithTag(v5, 0);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14000f804  push    rbx
0x14000f806  push    rbp
0x14000f807  push    rsi
0x14000f808  push    rdi
0x14000f809  push    r13
0x14000f80b  push    r14
0x14000f80d  push    r15
0x14000f80f  sub     rsp, 70h
0x14000f813  mov     esi, 0C0h
0x14000f818  mov     rdi, rdx
0x14000f81b  mov     rbx, rcx
0x14000f81e  mov     r8d, 43446353h
0x14000f824  mov     edx, esi
0x14000f826  lea     ecx, [rsi-78h]
0x14000f829  call    cs:__imp_ExAllocatePool2
0x14000f830  nop     dword ptr [rax+rax+00h]
0x14000f835  mov     r14, rax
0x14000f838  test    rax, rax
0x14000f83b  jnz     short loc_14000F87B
0x14000f83d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f844  lea     rax, WPP_GLOBAL_Control
0x14000f84b  cmp     rcx, rax
0x14000f84e  jz      short loc_14000F871
0x14000f850  mov     eax, [rcx+2Ch]
0x14000f853  test    al, 10h
0x14000f855  jz      short loc_14000F871
0x14000f857  cmp     byte ptr [rcx+29h], 2
0x14000f85b  jb      short loc_14000F871
0x14000f85d  mov     rcx, [rcx+18h]
0x14000f861  lea     edx, [r14+36h]
0x14000f865  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000f86c  call    WPP_SF_
0x14000f871  mov     eax, 0C000009Ah
0x14000f876  jmp     loc_14000FB3A
0x14000f87b  mov     rcx, [rbx+8]; DeviceObject
0x14000f87f  mov     r9b, 8; PageMode
0x14000f882  mov     r8d, esi; Length
0x14000f885  mov     rdx, r14; ModeSenseBuffer
0x14000f888  call    cs:__imp_ClassModeSense
0x14000f88f  nop     dword ptr [rax+rax+00h]
0x14000f894  mov     ecx, eax
0x14000f896  cmp     eax, 4
0x14000f899  jnb     short loc_14000F8F7
0x14000f89b  mov     rcx, [rbx+8]; DeviceObject
0x14000f89f  mov     r9b, 8; PageMode
0x14000f8a2  mov     r8d, esi; Length
0x14000f8a5  mov     rdx, r14; ModeSenseBuffer
0x14000f8a8  call    cs:__imp_ClassModeSense
0x14000f8af  nop     dword ptr [rax+rax+00h]
0x14000f8b4  mov     ecx, eax
0x14000f8b6  cmp     eax, 4
0x14000f8b9  jnb     short loc_14000F8F7
0x14000f8bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f8c2  lea     rax, WPP_GLOBAL_Control
0x14000f8c9  cmp     rcx, rax
0x14000f8cc  jz      short loc_14000F8F0
0x14000f8ce  mov     eax, [rcx+2Ch]
0x14000f8d1  test    al, 10h
0x14000f8d3  jz      short loc_14000F8F0
0x14000f8d5  cmp     byte ptr [rcx+29h], 2
0x14000f8d9  jb      short loc_14000F8F0
0x14000f8db  mov     rcx, [rcx+18h]
0x14000f8df  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000f8e6  mov     edx, 37h ; '7'
0x14000f8eb  call    WPP_SF_
0x14000f8f0  mov     ebx, 0C0000185h
0x14000f8f5  jmp     short loc_14000F976
0x14000f8f7  movzx   ebp, byte ptr [r14]
0x14000f8fb  mov     r13d, 1
0x14000f901  inc     ebp
0x14000f903  mov     r9b, r13b; Use6Byte
0x14000f906  cmp     ecx, ebp
0x14000f908  mov     r8b, 8; PageMode
0x14000f90b  cmovbe  ebp, ecx
0x14000f90e  mov     rcx, r14; ModeSenseBuffer
0x14000f911  mov     edx, ebp; Length
0x14000f913  call    cs:__imp_ClassFindModePage
0x14000f91a  nop     dword ptr [rax+rax+00h]
0x14000f91f  mov     rsi, rax
0x14000f922  test    rax, rax
0x14000f925  jnz     short loc_14000F92E
0x14000f927  mov     ebx, 0C00000BBh
0x14000f92c  jmp     short loc_14000F976
0x14000f92e  mov     ecx, ebp
0x14000f930  add     rax, 0Ch
0x14000f934  add     rcx, r14
0x14000f937  cmp     rax, rcx
0x14000f93a  jbe     short loc_14000F98E
0x14000f93c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f943  lea     rax, WPP_GLOBAL_Control
0x14000f94a  cmp     rcx, rax
0x14000f94d  jz      short loc_14000F971
0x14000f94f  mov     eax, [rcx+2Ch]
0x14000f952  test    al, 10h
0x14000f954  jz      short loc_14000F971
0x14000f956  cmp     byte ptr [rcx+29h], 2
0x14000f95a  jb      short loc_14000F971
0x14000f95c  mov     rcx, [rcx+18h]
0x14000f960  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000f967  mov     edx, 38h ; '8'
0x14000f96c  call    WPP_SF_
0x14000f971  mov     ebx, 0C0000001h
0x14000f976  xor     edx, edx; Tag
0x14000f978  mov     rcx, r14; P
0x14000f97b  call    cs:__imp_ExFreePoolWithTag
0x14000f982  nop     dword ptr [rax+rax+00h]
0x14000f987  mov     eax, ebx
0x14000f989  jmp     loc_14000FB3A
0x14000f98e  and     byte ptr [rsi], 7Fh
0x14000f991  xor     ebp, ebp
0x14000f993  cmp     [rdi+1], bpl
0x14000f997  mov     al, [rsi+2]
0x14000f99a  setz    cl
0x14000f99d  and     al, 0FEh
0x14000f99f  or      cl, al
0x14000f9a1  lea     r8d, [rbp+0Fh]
0x14000f9a5  mov     [rsi+2], cl
0x14000f9a8  mov     al, [rdi+0Eh]
0x14000f9ab  add     al, al
0x14000f9ad  xor     al, cl
0x14000f9af  and     al, 2
0x14000f9b1  xor     al, cl
0x14000f9b3  mov     [rsi+2], al
0x14000f9b6  mov     dl, [rdi+2]
0x14000f9b9  shl     dl, 2
0x14000f9bc  xor     dl, al
0x14000f9be  and     dl, 4
0x14000f9c1  xor     dl, al
0x14000f9c3  mov     [rsi+2], dl
0x14000f9c6  mov     ecx, [rdi+8]
0x14000f9c9  cmp     ecx, r8d
0x14000f9cc  jnz     short loc_14000F9D3
0x14000f9ce  lea     ecx, [rbp+2]
0x14000f9d1  jmp     short loc_14000F9DA
0x14000f9d3  cmp     ecx, 2
0x14000f9d6  cmovz   ecx, r8d
0x14000f9da  mov     al, [rsi+3]
0x14000f9dd  xor     cl, al
0x14000f9df  and     cl, r8b
0x14000f9e2  xor     cl, al
0x14000f9e4  mov     [rsi+3], cl
0x14000f9e7  mov     eax, [rdi+4]
0x14000f9ea  cmp     eax, r8d
0x14000f9ed  jnz     short loc_14000F9F6
0x14000f9ef  mov     eax, 2
0x14000f9f4  jmp     short loc_14000F9FD
0x14000f9f6  cmp     eax, 2
0x14000f9f9  cmovz   eax, r8d
0x14000f9fd  shl     al, 4
0x14000fa00  and     cl, r8b
0x14000fa03  or      al, cl
0x14000fa05  mov     [rsi+3], al
0x14000fa08  mov     al, [rdi+0Dh]
0x14000fa0b  mov     [rsi+4], al
0x14000fa0e  mov     al, [rdi+0Ch]
0x14000fa11  mov     [rsi+5], al
0x14000fa14  mov     al, [rdi+11h]
0x14000fa17  mov     [rsi+6], al
0x14000fa1a  mov     al, [rdi+10h]
0x14000fa1d  mov     [rsi+7], al
0x14000fa20  mov     al, [rdi+13h]
0x14000fa23  mov     [rsi+8], al
0x14000fa26  mov     al, [rdi+12h]
0x14000fa29  mov     [rsi+9], al
0x14000fa2c  test    dl, 2
0x14000fa2f  jz      short loc_14000FA3D
0x14000fa31  mov     al, [rdi+15h]
0x14000fa34  mov     [rsi+0Ah], al
0x14000fa37  mov     al, [rdi+14h]
0x14000fa3a  mov     [rsi+0Bh], al
0x14000fa3d  xor     r15d, r15d
0x14000fa40  cmp     r15d, 2
0x14000fa44  jnb     short loc_14000FABE
0x14000fa46  movzx   r8d, byte ptr [rsi+1]
0x14000fa4b  mov     rdx, rsi; Src
0x14000fa4e  mov     r9b, [rdi]
0x14000fa51  add     r8d, 2; Size
0x14000fa55  mov     rcx, [rbx+8]; DeviceObject
0x14000fa59  call    DiskModeSelect
0x14000fa5e  mov     ebp, eax
0x14000fa60  test    eax, eax
0x14000fa62  jns     short loc_14000FA69
0x14000fa64  add     r15d, r13d
0x14000fa67  jmp     short loc_14000FA40
0x14000fa69  cmp     byte ptr [rdi+2], 0
0x14000fa6d  movzx   eax, word ptr [rbx+280h]
0x14000fa74  jz      short loc_14000FA7C
0x14000fa76  or      ax, r13w
0x14000fa7a  jmp     short loc_14000FA84
0x14000fa7c  mov     ecx, 0FFFEh
0x14000fa81  and     ax, cx
0x14000fa84  mov     [rbx+280h], ax
0x14000fa8b  movzx   eax, word ptr [rbx+280h]
0x14000fa92  test    r13b, al
0x14000fa95  jz      short loc_14000FAB5
0x14000fa97  movzx   eax, word ptr [rbx+280h]
0x14000fa9e  test    al, 10h
0x14000faa0  jnz     short loc_14000FAB5
0x14000faa2  mov     eax, [rbx+36Ch]
0x14000faa8  test    al, al
0x14000faaa  js      short loc_14000FAB5
0x14000faac  mov     [rbx+283h], r13b
0x14000fab3  jmp     short loc_14000FAC2
0x14000fab5  mov     byte ptr [rbx+283h], 0
0x14000fabc  jmp     short loc_14000FAC2
0x14000fabe  test    ebp, ebp
0x14000fac0  js      short loc_14000FB20
0x14000fac2  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, r13b
0x14000fac9  jz      short loc_14000FB27
0x14000facb  mov     eax, [rbx+24Ch]
0x14000fad1  mov     r9b, [rdi+1]
0x14000fad5  mov     [rsp+0A8h+var_48], eax
0x14000fad9  movzx   eax, word ptr [rdi+14h]
0x14000fadd  mov     [rsp+0A8h+var_50], ax
0x14000fae2  movzx   eax, word ptr [rdi+12h]
0x14000fae6  mov     [rsp+0A8h+var_58], ax
0x14000faeb  movzx   eax, word ptr [rdi+10h]
0x14000faef  mov     [rsp+0A8h+var_60], ax
0x14000faf4  movzx   eax, word ptr [rdi+0Ch]
0x14000faf8  mov     [rsp+0A8h+var_68], ax
0x14000fafd  mov     al, [rdi+0Eh]
0x14000fb00  mov     [rsp+0A8h+var_70], al
0x14000fb04  mov     al, [rdi+8]
0x14000fb07  mov     [rsp+0A8h+var_78], al
0x14000fb0b  mov     al, [rdi+4]
0x14000fb0e  mov     [rsp+0A8h+var_80], al
0x14000fb12  mov     al, [rdi+2]
0x14000fb15  mov     [rsp+0A8h+var_88], al
0x14000fb19  call    McTemplateK0uuuuuhhhhq_EtwWriteTransfer
0x14000fb1e  jmp     short loc_14000FB27
0x14000fb20  or      dword ptr [rbx+36Ch], 40h
0x14000fb27  xor     edx, edx; Tag
0x14000fb29  mov     rcx, r14; P
0x14000fb2c  call    cs:__imp_ExFreePoolWithTag
0x14000fb33  nop     dword ptr [rax+rax+00h]
0x14000fb38  mov     eax, ebp
0x14000fb3a  add     rsp, 70h
0x14000fb3e  pop     r15
0x14000fb40  pop     r14
0x14000fb42  pop     r13
0x14000fb44  pop     rdi
0x14000fb45  pop     rsi
0x14000fb46  pop     rbp
0x14000fb47  pop     rbx
0x14000fb48  retn
```
