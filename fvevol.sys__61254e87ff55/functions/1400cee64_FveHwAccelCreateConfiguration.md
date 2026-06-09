# FveHwAccelCreateConfiguration

- ea: `0x1400cee64`
- end: `0x1400cf158`
- name: `FveHwAccelCreateConfiguration`
- size: `756`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400d1490`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x140014e1c`
- `0x140022d40`
- `0x1400cee64`
- `0x1400cf160`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400ceeeb`
- `ntoskrnl!ExAllocatePool2` at `0x1400cef8d`
- `ntoskrnl!ExAllocatePool2` at `0x1400ceeeb`
- `ntoskrnl!ExAllocatePool2` at `0x1400cef8d`
- `ext-ms-win-accel-api-km-l1-1-1!AccelConfigureWorkspaceCryptoCapability` at `0x1400cf0be`
- `ext-ms-win-accel-api-km-l1-1-1!AccelConfigureWorkspaceCryptoCapability` at `0x1400cf0be`
- `ext-ms-win-accel-api-km-l1-1-1!AccelInitializeCryptoWorkspace` at `0x1400cf028`
- `ext-ms-win-accel-api-km-l1-1-1!AccelInitializeCryptoWorkspace` at `0x1400cf028`

## pseudocode

```c
__int64 __fastcall FveHwAccelCreateConfiguration(__int64 a1, _DWORD *a2, __int64 a3, __int64 *a4)
{
  __int64 v4; // rsi
  __int64 Pool2; // rax
  __int64 v10; // rdi
  __int64 v11; // r9
  unsigned int v12; // ebx
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  unsigned __int16 Size; // ax
  void *v16; // rax
  int v17; // eax
  __int128 v19; // [rsp+20h] [rbp-58h] BYREF
  __int128 v20; // [rsp+30h] [rbp-48h] BYREF
  __int128 v21; // [rsp+40h] [rbp-38h]
  __int128 v22; // [rsp+50h] [rbp-28h]
  __int64 v23; // [rsp+60h] [rbp-18h]

  v4 = *(_QWORD *)(a1 + 8);
  v19 = 0;
  v23 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids);
  }
  Pool2 = ExAllocatePool2(64, 48, 1749374534);
  v10 = Pool2;
  if ( !Pool2 )
  {
    v11 = 3221225626LL;
    v12 = -1073741670;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v14 = 95;
LABEL_10:
      WPP_SF_d(v13->AttachedDevice, v14, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, v11);
      goto LABEL_29;
    }
    goto LABEL_29;
  }
  *(_OWORD *)Pool2 = 0;
  *(_OWORD *)(Pool2 + 16) = 0;
  *(_OWORD *)(Pool2 + 32) = 0;
  *(_DWORD *)Pool2 = *a2;
  *(_DWORD *)(Pool2 + 4) = a2[4];
  *(_DWORD *)(Pool2 + 8) = a2[5];
  *(_DWORD *)(Pool2 + 16) = 1;
  Size = FveDatumKeyGetSize(a3);
  *(_DWORD *)(v10 + 32) = Size;
  v16 = (void *)ExAllocatePool2(64, Size, 1701736270);
  *(_QWORD *)(v10 + 24) = v16;
  if ( v16 )
  {
    v12 = 0;
    memmove(v16, (const void *)(a3 + 12), *(unsigned int *)(v10 + 32));
    if ( (*(_DWORD *)(v4 + 9928) & 0x800000) == 0 )
    {
      v19 = 0;
      LODWORD(v19) = 1048577;
      *((_QWORD *)&v19 + 1) = *(_QWORD *)(v4 + 10736);
      v17 = AccelInitializeCryptoWorkspace(&v19, v10 + 40);
      v12 = v17;
      if ( v17 < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_29;
        }
        v14 = 97;
        goto LABEL_22;
      }
      v23 = 0;
      v20 = 0;
      LODWORD(v20) = 3670017;
      v21 = 0;
      v22 = 0;
      *((_QWORD *)&v20 + 1) = *(_QWORD *)(v10 + 40);
      LODWORD(v21) = *a2;
      DWORD2(v21) = 1;
      *(_QWORD *)&v22 = *(_QWORD *)(v10 + 24);
      DWORD2(v22) = *(_DWORD *)(v10 + 32);
      LODWORD(v23) = *(_DWORD *)(a1 + 1308);
      v17 = AccelConfigureWorkspaceCryptoCapability(&v20);
      v12 = v17;
      if ( v17 < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_29;
        }
        v14 = 98;
LABEL_22:
        v11 = (unsigned int)v17;
        goto LABEL_10;
      }
    }
    *a4 = v10;
    v10 = 0;
    goto LABEL_29;
  }
  v11 = 3221225626LL;
  v12 = -1073741670;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v14 = 96;
    goto LABEL_10;
  }
LABEL_29:
  FveHwAccelDestroyConfiguration((PVOID)v10);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x1400cee64  push    rbp
0x1400cee66  push    rbx
0x1400cee67  push    rsi
0x1400cee68  push    rdi
0x1400cee69  push    r12
0x1400cee6b  push    r13
0x1400cee6d  push    r14
0x1400cee6f  push    r15
0x1400cee71  mov     rbp, rsp
0x1400cee74  sub     rsp, 78h
0x1400cee78  mov     rsi, [rcx+8]
0x1400cee7c  xorps   xmm1, xmm1
0x1400cee7f  xorps   xmm0, xmm0
0x1400cee82  xor     eax, eax
0x1400cee84  movups  [rbp+var_58], xmm0
0x1400cee88  mov     [rbp+var_18], rax
0x1400cee8c  mov     r12, r9
0x1400cee8f  movups  [rbp+var_48], xmm1
0x1400cee93  mov     r14, r8
0x1400cee96  mov     r15, rdx
0x1400cee99  movups  [rbp+var_38], xmm1
0x1400cee9d  mov     r13, rcx
0x1400ceea0  movups  [rbp+var_28], xmm1
0x1400ceea4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ceeab  lea     rax, WPP_GLOBAL_Control
0x1400ceeb2  cmp     rcx, rax
0x1400ceeb5  jz      short loc_1400CEEDB
0x1400ceeb7  test    dword ptr [rcx+2Ch], 400000h
0x1400ceebe  jz      short loc_1400CEEDB
0x1400ceec0  cmp     byte ptr [rcx+29h], 5
0x1400ceec4  jb      short loc_1400CEEDB
0x1400ceec6  mov     rcx, [rcx+18h]
0x1400ceeca  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400ceed1  mov     edx, 5Eh ; '^'
0x1400ceed6  call    WPP_SF_
0x1400ceedb  mov     edx, 30h ; '0'
0x1400ceee0  mov     r8d, 68455646h
0x1400ceee6  lea     ebx, [rdx+10h]
0x1400ceee9  mov     ecx, ebx
0x1400ceeeb  call    cs:__imp_ExAllocatePool2
0x1400ceef2  nop     dword ptr [rax+rax+00h]
0x1400ceef7  mov     rdi, rax
0x1400ceefa  test    rax, rax
0x1400ceefd  jnz     short loc_1400CEF4E
0x1400ceeff  mov     r9d, 0C000009Ah
0x1400cef05  mov     ebx, r9d
0x1400cef08  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cef0f  lea     rsi, WPP_GLOBAL_Control
0x1400cef16  cmp     rcx, rsi
0x1400cef19  jz      loc_1400CF109
0x1400cef1f  test    dword ptr [rcx+2Ch], 400000h
0x1400cef26  jz      loc_1400CF109
0x1400cef2c  cmp     byte ptr [rcx+29h], 2
0x1400cef30  jb      loc_1400CF109
0x1400cef36  lea     edx, [rax+5Fh]
0x1400cef39  mov     rcx, [rcx+18h]
0x1400cef3d  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400cef44  call    WPP_SF_d
0x1400cef49  jmp     loc_1400CF109
0x1400cef4e  xorps   xmm0, xmm0
0x1400cef51  mov     rcx, r14
0x1400cef54  movups  xmmword ptr [rax], xmm0
0x1400cef57  movups  xmmword ptr [rax+10h], xmm0
0x1400cef5b  movups  xmmword ptr [rax+20h], xmm0
0x1400cef5f  mov     eax, [r15]
0x1400cef62  mov     [rdi], eax
0x1400cef64  mov     eax, [r15+10h]
0x1400cef68  mov     [rdi+4], eax
0x1400cef6b  mov     eax, [r15+14h]
0x1400cef6f  mov     [rdi+8], eax
0x1400cef72  mov     dword ptr [rdi+10h], 1
0x1400cef79  call    FveDatumKeyGetSize
0x1400cef7e  movzx   edx, ax
0x1400cef81  mov     r8d, 656E6F4Eh
0x1400cef87  mov     rcx, rbx
0x1400cef8a  mov     [rdi+20h], edx
0x1400cef8d  call    cs:__imp_ExAllocatePool2
0x1400cef94  nop     dword ptr [rax+rax+00h]
0x1400cef99  mov     [rdi+18h], rax
0x1400cef9d  test    rax, rax
0x1400cefa0  jnz     short loc_1400CEFE1
0x1400cefa2  mov     r9d, 0C000009Ah
0x1400cefa8  mov     ebx, r9d
0x1400cefab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cefb2  lea     rsi, WPP_GLOBAL_Control
0x1400cefb9  cmp     rcx, rsi
0x1400cefbc  jz      loc_1400CF109
0x1400cefc2  test    dword ptr [rcx+2Ch], 400000h
0x1400cefc9  jz      loc_1400CF109
0x1400cefcf  cmp     byte ptr [rcx+29h], 2
0x1400cefd3  jb      loc_1400CF109
0x1400cefd9  lea     edx, [rax+60h]
0x1400cefdc  jmp     loc_1400CEF39
0x1400cefe1  mov     r8d, [rdi+20h]; Size
0x1400cefe5  lea     rdx, [r14+0Ch]; Src
0x1400cefe9  mov     rcx, rax; void *
0x1400cefec  xor     ebx, ebx
0x1400cefee  call    memmove
0x1400ceff3  test    dword ptr [rsi+26C8h], 800000h
0x1400ceffd  jnz     loc_1400CF0FC
0x1400cf003  xorps   xmm0, xmm0
0x1400cf006  lea     rdx, [rdi+28h]
0x1400cf00a  movups  [rbp+var_58], xmm0
0x1400cf00e  mov     dword ptr [rbp+var_58], 100001h
0x1400cf015  lea     rcx, [rbp+var_58]
0x1400cf019  mov     rax, [rsi+29F0h]
0x1400cf020  lea     r14d, [rbx+1]
0x1400cf024  mov     qword ptr [rbp+var_58+8], rax
0x1400cf028  call    cs:__imp_AccelInitializeCryptoWorkspace
0x1400cf02f  nop     dword ptr [rax+rax+00h]
0x1400cf034  mov     ebx, eax
0x1400cf036  test    eax, eax
0x1400cf038  jns     short loc_1400CF074
0x1400cf03a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cf041  lea     rsi, WPP_GLOBAL_Control
0x1400cf048  cmp     rcx, rsi
0x1400cf04b  jz      loc_1400CF109
0x1400cf051  test    dword ptr [rcx+2Ch], 400000h
0x1400cf058  jz      loc_1400CF109
0x1400cf05e  cmp     byte ptr [rcx+29h], 2
0x1400cf062  jb      loc_1400CF109
0x1400cf068  lea     edx, [r14+60h]
0x1400cf06c  mov     r9d, eax
0x1400cf06f  jmp     loc_1400CEF39
0x1400cf074  xor     eax, eax
0x1400cf076  lea     rcx, [rbp+var_48]
0x1400cf07a  mov     [rbp+var_18], rax
0x1400cf07e  xorps   xmm0, xmm0
0x1400cf081  movups  [rbp+var_48], xmm0
0x1400cf085  mov     dword ptr [rbp+var_48], 380001h
0x1400cf08c  movups  [rbp+var_38], xmm0
0x1400cf090  movups  [rbp+var_28], xmm0
0x1400cf094  mov     rax, [rdi+28h]
0x1400cf098  mov     qword ptr [rbp+var_48+8], rax
0x1400cf09c  mov     eax, [r15]
0x1400cf09f  mov     dword ptr [rbp+var_38], eax
0x1400cf0a2  mov     dword ptr [rbp+var_38+8], r14d
0x1400cf0a6  mov     rax, [rdi+18h]
0x1400cf0aa  mov     qword ptr [rbp+var_28], rax
0x1400cf0ae  mov     eax, [rdi+20h]
0x1400cf0b1  mov     dword ptr [rbp+var_28+8], eax
0x1400cf0b4  mov     eax, [r13+51Ch]
0x1400cf0bb  mov     dword ptr [rbp+var_18], eax
0x1400cf0be  call    cs:__imp_AccelConfigureWorkspaceCryptoCapability
0x1400cf0c5  nop     dword ptr [rax+rax+00h]
0x1400cf0ca  mov     ebx, eax
0x1400cf0cc  test    eax, eax
0x1400cf0ce  jns     short loc_1400CF0FC
0x1400cf0d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cf0d7  lea     rsi, WPP_GLOBAL_Control
0x1400cf0de  cmp     rcx, rsi
0x1400cf0e1  jz      short loc_1400CF109
0x1400cf0e3  test    dword ptr [rcx+2Ch], 400000h
0x1400cf0ea  jz      short loc_1400CF109
0x1400cf0ec  cmp     byte ptr [rcx+29h], 2
0x1400cf0f0  jb      short loc_1400CF109
0x1400cf0f2  mov     edx, 62h ; 'b'
0x1400cf0f7  jmp     loc_1400CF06C
0x1400cf0fc  mov     [r12], rdi
0x1400cf100  lea     rsi, WPP_GLOBAL_Control
0x1400cf107  xor     edi, edi
0x1400cf109  mov     rcx, rdi; P
0x1400cf10c  call    FveHwAccelDestroyConfiguration
0x1400cf111  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cf118  cmp     rcx, rsi
0x1400cf11b  jz      short loc_1400CF144
0x1400cf11d  test    dword ptr [rcx+2Ch], 400000h
0x1400cf124  jz      short loc_1400CF144
0x1400cf126  cmp     byte ptr [rcx+29h], 5
0x1400cf12a  jb      short loc_1400CF144
0x1400cf12c  mov     rcx, [rcx+18h]
0x1400cf130  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400cf137  mov     edx, 63h ; 'c'
0x1400cf13c  mov     r9d, ebx
0x1400cf13f  call    WPP_SF_d
0x1400cf144  mov     eax, ebx
0x1400cf146  add     rsp, 78h
0x1400cf14a  pop     r15
0x1400cf14c  pop     r14
0x1400cf14e  pop     r13
0x1400cf150  pop     r12
0x1400cf152  pop     rdi
0x1400cf153  pop     rsi
0x1400cf154  pop     rbx
0x1400cf155  pop     rbp
0x1400cf156  retn
```
