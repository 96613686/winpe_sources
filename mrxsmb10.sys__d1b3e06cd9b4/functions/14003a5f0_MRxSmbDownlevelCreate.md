# MRxSmbDownlevelCreate

- ea: `0x14003a5f0`
- end: `0x14003ad2b`
- name: `MRxSmbDownlevelCreate`
- size: `1851`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops`

## callers

- `0x140047fb0`

## callees

- `0x14000dc44`
- `0x14000dfd8`
- `0x14000ebd8`
- `0x14000eed8`
- `0x140039b9c`
- `0x14003a028`
- `0x14003a120`
- `0x14003a204`
- `0x14003a394`
- `0x14003a494`
- `0x14003a5f0`
- `0x14003b07c`
- `0x14003b2d4`
- `0x14003b320`
- `0x14003b370`
- `0x14003b3a4`
- `0x14003b4c8`
- `0x140047dc0`
- `0x140049870`
- `0x14004a4a4`
- `0x1400526a4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003a84a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a84a`

## pseudocode

```c
__int64 __fastcall MRxSmbDownlevelCreate(unsigned int *pContext, __int64 a2)
{
  __int64 v2; // rbx
  char v3; // r15
  __int64 v4; // r13
  __int64 v7; // r14
  unsigned int v8; // esi
  int v9; // r12d
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned __int16 v12; // ax
  unsigned __int16 v13; // r10
  unsigned __int16 v14; // r11
  int FileAttributes; // ebx
  int v16; // r12d
  __int64 v17; // rax
  __int64 v18; // rcx
  char v19; // r13
  int v20; // r14d
  bool v21; // r13
  int v22; // eax
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // r14d
  char v26; // r15
  int v27; // eax
  int Directory; // eax
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  unsigned __int16 v31; // ax
  __int64 v33; // [rsp+40h] [rbp-58h]
  unsigned __int16 v34; // [rsp+A0h] [rbp+8h]
  unsigned __int16 v35; // [rsp+A8h] [rbp+10h]
  unsigned __int16 v36; // [rsp+B0h] [rbp+18h]
  unsigned __int16 v37; // [rsp+B8h] [rbp+20h]

  v2 = *(_QWORD *)(a2 + 72);
  v3 = 0;
  v4 = *(_QWORD *)(a2 + 56);
  v7 = 0;
  if ( v2 )
    v7 = *(_QWORD *)(v2 + 48);
  v8 = *(_DWORD *)(a2 + 536);
  v9 = *(_DWORD *)(a2 + 540);
  v34 = MRxSmbMapDisposition(v8);
  v36 = MRxSmbMapShareAccess(*(unsigned __int16 *)(v10 + 532));
  v35 = MRxSmbMapFileAttributes(*(unsigned int *)(v11 + 528));
  v12 = MRxSmbMapDesiredAccess(*(unsigned int *)(a2 + 512));
  v33 = *(_QWORD *)(a2 + 520);
  v37 = v12;
  if ( (v9 & 1) != 0 || (*(_BYTE *)(a2 + 746) & 2) != 0 )
    v3 = 1;
  if ( v12 == 3 )
    v37 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids, pContext);
      v13 = v34;
      v14 = v35;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_LLLL(
        WPP_GLOBAL_Control->AttachedDevice,
        30,
        WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids,
        v14,
        v36,
        v13,
        v37);
  }
  if ( *((_BYTE *)pContext + 564) )
  {
    FileAttributes = -1073741637;
    goto LABEL_127;
  }
  if ( HIDWORD(v33) )
  {
LABEL_17:
    FileAttributes = -1073741811;
    goto LABEL_127;
  }
  v16 = v9 & 0x40;
  v17 = v4 + 360;
  v18 = 0;
  if ( v2 )
    v18 = *(_QWORD *)(v2 + 48);
  *((_QWORD *)pContext + 68) = v18;
  *((_QWORD *)pContext + 108) = v17;
  if ( !*(_WORD *)v17 || (v19 = 0, *(_WORD *)v17 == 2) && **(_WORD **)(v17 + 8) == 92 )
  {
    if ( v16 )
    {
      FileAttributes = -1073741638;
      goto LABEL_127;
    }
    if ( ((v8 - 1) & 0xFFFFFFFD) == 0 )
    {
      Directory = MRxSmbPseudoOpenTailFromFakeGFAResponse(pContext, 1);
      goto LABEL_126;
    }
    v3 = 1;
    v19 = 1;
LABEL_40:
    if ( v37 != 0xFFFF && v8 && (FileAttributes = -1073741822, v16) )
    {
      v21 = 0;
    }
    else
    {
      FileAttributes = MRxSmbGetFileAttributes(pContext);
      if ( !FileAttributes && v3 && !*((_BYTE *)pContext + 533) )
      {
        FileAttributes = -1073741565;
        goto LABEL_127;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          31,
          WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids,
          (unsigned int)FileAttributes);
      }
      if ( FileAttributes < 0 )
      {
        if ( FileAttributes != -1073741809 && FileAttributes != -1073741766 )
          goto LABEL_127;
        if ( v8 > 5 || (v22 = 45, !_bittest(&v22, v8)) )
        {
          if ( !v19 )
            goto LABEL_127;
          Directory = MRxSmbPseudoOpenTailFromFakeGFAResponse(pContext, 1);
          *(_DWORD *)v7 |= 4u;
          goto LABEL_126;
        }
        v21 = 0;
      }
      else
      {
        v20 = pContext[126] & 0x10;
        v21 = v20 != 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            32,
            WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids,
            pContext[126]);
        }
        if ( v8 == 2 )
        {
          FileAttributes = -1073741771;
          goto LABEL_127;
        }
        if ( v3 && !v20 && v8 )
        {
          FileAttributes = -1073741771;
          goto LABEL_60;
        }
        if ( v16 && v20 )
        {
          if ( v8 )
          {
            FileAttributes = -1073741638;
LABEL_60:
            if ( v8 != 1 )
              FileAttributes = -1073741788;
            goto LABEL_127;
          }
        }
        else if ( ((v8 - 1) & 0xFFFFFFFD) == 0 )
        {
          MRxSmbPseudoOpenTailFromGFAResponse(pContext);
          goto LABEL_127;
        }
      }
    }
    *(_QWORD *)(pContext + 27) = 0;
    pContext[18] &= ~8u;
    pContext[26] = 0;
    pContext[29] = 0;
    pContext[12] = 0;
    pContext[10] = 0;
    if ( FileAttributes >= 0 && !v8 )
    {
      FileAttributes = MRxSmbCoreDeleteForSupercedeOrClose(pContext);
      if ( FileAttributes < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return (unsigned int)FileAttributes;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 )
          goto LABEL_127;
        v24 = 33;
LABEL_81:
        WPP_SF_d(
          v23->AttachedDevice,
          v24,
          WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids,
          (unsigned int)FileAttributes);
        goto LABEL_127;
      }
      pContext[18] &= ~8u;
      *(_QWORD *)(pContext + 27) = 0;
      pContext[26] = 0;
      pContext[29] = 0;
      pContext[12] = 0;
      pContext[10] = 0;
    }
    if ( !v3 && (!v21 || v8) )
    {
      v25 = 0;
      v26 = 0;
      switch ( v8 )
      {
        case 0u:
          goto LABEL_96;
        case 1u:
          goto LABEL_133;
        case 2u:
          goto LABEL_96;
        case 3u:
LABEL_133:
          while ( 1 )
          {
LABEL_92:
            FileAttributes = MRxSmbCoreOpen(pContext);
            if ( ((v8 - 3) & 0xFFFFFFFD) != 0 || FileAttributes != -1073741809 )
            {
              if ( FileAttributes >= 0 && v26 && !*((_BYTE *)pContext + 580) && pContext[144] )
              {
                Directory = MRxSmbCoreTruncate(pContext);
                goto LABEL_126;
              }
              goto LABEL_127;
            }
            if ( v25 > 6 )
              goto LABEL_127;
            pContext[18] &= ~8u;
            *(_QWORD *)(pContext + 27) = 0;
            pContext[26] = 0;
            pContext[29] = 0;
            pContext[12] = 0;
            pContext[10] = 0;
LABEL_96:
            v27 = MRxSmbCoreCreate(pContext);
            FileAttributes = v27;
            if ( v27 < 0 )
              break;
            v27 = MRxSmbCloseAfterCoreCreate(pContext);
            FileAttributes = v27;
            if ( v27 < 0 )
            {
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
              {
                v30 = 37;
                goto LABEL_110;
              }
              goto LABEL_127;
            }
            v8 = 3;
            ++v25;
          }
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            v30 = 36;
            goto LABEL_110;
          }
          goto LABEL_127;
      }
      if ( v8 - 4 <= 1 )
      {
        v26 = 1;
        goto LABEL_92;
      }
      goto LABEL_17;
    }
    FileAttributes = MRxSmbCoreCreateDirectory(pContext);
    if ( FileAttributes < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return (unsigned int)FileAttributes;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 )
        goto LABEL_127;
      v24 = 34;
      goto LABEL_81;
    }
    v31 = v35;
    if ( (v35 & 0x27) != 0 )
    {
      v27 = MRxSmbSetFileAttributes(pContext);
      FileAttributes = v27;
      if ( v27 < 0 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          v30 = 35;
LABEL_110:
          WPP_SF_d(v29->AttachedDevice, v30, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids, (unsigned int)v27);
        }
        goto LABEL_127;
      }
      v31 = v35;
    }
    if ( FileAttributes )
      goto LABEL_127;
    Directory = MRxSmbPseudoOpenTailFromCoreCreateDirectory(pContext, v31);
LABEL_126:
    FileAttributes = Directory;
    goto LABEL_127;
  }
  if ( v8 != 1 || !v3 && (*(_DWORD *)(a2 + 512) & 0xFFEEFF7F) != 0 )
    goto LABEL_40;
  FileAttributes = MRxSmbPseudoOpenTailFromFakeGFAResponse(pContext, 2 - (unsigned int)(v3 != 0));
  if ( !FileAttributes )
  {
    FileAttributes = MRxSmbQueryFileInformationFromPseudoOpen(pContext, a2, 4);
    if ( !FileAttributes )
    {
      if ( v3 && !*((_BYTE *)pContext + 533) )
        FileAttributes = -1073741565;
      if ( v16 && *((_BYTE *)pContext + 533) )
      {
        FileAttributes = -1073741638;
      }
      else if ( !FileAttributes )
      {
        goto LABEL_127;
      }
    }
    ExFreePoolWithTag(*(PVOID *)(v7 + 16), 0);
    *(_QWORD *)(v7 + 16) = 0;
  }
LABEL_127:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      38,
      WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids,
      pContext,
      FileAttributes);
  return (unsigned int)FileAttributes;
}

```

## disassembly

```asm
0x14003a5f0  push    rbx
0x14003a5f2  push    rbp
0x14003a5f3  push    rsi
0x14003a5f4  push    rdi
0x14003a5f5  push    r12
0x14003a5f7  push    r13
0x14003a5f9  push    r14
0x14003a5fb  push    r15
0x14003a5fd  sub     rsp, 58h
0x14003a601  mov     rbx, [rdx+48h]
0x14003a605  xor     r15d, r15d
0x14003a608  mov     r13, [rdx+38h]
0x14003a60c  mov     rbp, rdx
0x14003a60f  mov     rdi, rcx
0x14003a612  mov     r14d, r15d
0x14003a615  test    rbx, rbx
0x14003a618  jz      short loc_14003A61E
0x14003a61a  mov     r14, [rbx+30h]
0x14003a61e  mov     esi, [rdx+218h]
0x14003a624  mov     ecx, esi
0x14003a626  mov     r12d, [rdx+21Ch]
0x14003a62d  call    MRxSmbMapDisposition
0x14003a632  movzx   ecx, word ptr [rdx+214h]
0x14003a639  movzx   r10d, ax
0x14003a63d  mov     [rsp+98h+arg_0], ax
0x14003a645  call    MRxSmbMapShareAccess
0x14003a64a  mov     ecx, [rdx+210h]
0x14003a650  mov     [rsp+98h+arg_10], ax
0x14003a658  call    MRxSmbMapFileAttributes
0x14003a65d  mov     ecx, [rbp+200h]
0x14003a663  movzx   r11d, ax
0x14003a667  mov     [rsp+98h+arg_8], ax
0x14003a66f  call    MRxSmbMapDesiredAccess
0x14003a674  mov     rcx, [rbp+208h]
0x14003a67b  mov     [rsp+98h+var_58], rcx
0x14003a680  mov     [rsp+98h+arg_18], eax
0x14003a687  test    r12b, 1
0x14003a68b  jnz     short loc_14003A696
0x14003a68d  test    byte ptr [rbp+2EAh], 2
0x14003a694  jz      short loc_14003A699
0x14003a696  mov     r15b, 1
0x14003a699  mov     ecx, 3
0x14003a69e  cmp     ax, cx
0x14003a6a1  jnz     short loc_14003A6AE
0x14003a6a3  mov     [rsp+98h+arg_18], 0
0x14003a6ae  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003a6b5  lea     rax, WPP_GLOBAL_Control
0x14003a6bc  cmp     rcx, rax
0x14003a6bf  jz      loc_14003A750
0x14003a6c5  test    dword ptr [rcx+2Ch], 400h
0x14003a6cc  jz      short loc_14003A6F8
0x14003a6ce  mov     rcx, [rcx+18h]
0x14003a6d2  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003a6d9  mov     edx, 1Dh
0x14003a6de  mov     r9, rdi
0x14003a6e1  call    WPP_SF_q
0x14003a6e6  movzx   r10d, [rsp+98h+arg_0]
0x14003a6ef  movzx   r11d, [rsp+98h+arg_8]
0x14003a6f8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003a6ff  lea     rax, WPP_GLOBAL_Control
0x14003a706  cmp     rcx, rax
0x14003a709  jz      short loc_14003A750
0x14003a70b  test    dword ptr [rcx+2Ch], 400h
0x14003a712  jz      short loc_14003A750
0x14003a714  movzx   eax, word ptr [rsp+98h+arg_18]
0x14003a71c  mov     edx, 1Eh
0x14003a721  mov     rcx, [rcx+18h]
0x14003a725  movzx   r8d, r10w
0x14003a729  movzx   r10d, [rsp+98h+arg_10]
0x14003a732  mov     [rsp+98h+var_68], eax
0x14003a736  mov     [rsp+98h+var_70], r8d
0x14003a73b  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003a742  movzx   r9d, r11w
0x14003a746  mov     [rsp+98h+var_78], r10d
0x14003a74b  call    WPP_SF_LLLL
0x14003a750  xor     edx, edx
0x14003a752  cmp     [rdi+234h], dl
0x14003a758  jz      short loc_14003A764
0x14003a75a  mov     ebx, 0C00000BBh
0x14003a75f  jmp     loc_14003ACDF
0x14003a764  cmp     dword ptr [rsp+98h+var_58+4], edx
0x14003a768  jz      short loc_14003A774
0x14003a76a  mov     ebx, 0C000000Dh
0x14003a76f  jmp     loc_14003ACDF
0x14003a774  and     r12d, 40h
0x14003a778  lea     rax, [r13+168h]
0x14003a77f  mov     rcx, rdx
0x14003a782  test    rbx, rbx
0x14003a785  jz      short loc_14003A78B
0x14003a787  mov     rcx, [rbx+30h]
0x14003a78b  mov     [rdi+220h], rcx
0x14003a792  mov     [rdi+360h], rax
0x14003a799  movzx   ecx, word ptr [rax]
0x14003a79c  test    cx, cx
0x14003a79f  jz      loc_14003A85F
0x14003a7a5  mov     r8d, 2
0x14003a7ab  mov     r13b, dl
0x14003a7ae  cmp     cx, r8w
0x14003a7b2  jnz     short loc_14003A7C2
0x14003a7b4  mov     rax, [rax+8]
0x14003a7b8  cmp     word ptr [rax], 5Ch ; '\'
0x14003a7bc  jz      loc_14003A85F
0x14003a7c2  cmp     esi, 1
0x14003a7c5  jnz     loc_14003A882
0x14003a7cb  test    r15b, r15b
0x14003a7ce  jnz     short loc_14003A7E0
0x14003a7d0  test    dword ptr [rbp+200h], 0FFEEFF7Fh
0x14003a7da  jnz     loc_14003A882
0x14003a7e0  mov     al, r15b
0x14003a7e3  mov     rcx, rdi
0x14003a7e6  neg     al
0x14003a7e8  sbb     edx, edx
0x14003a7ea  add     edx, r8d
0x14003a7ed  call    MRxSmbPseudoOpenTailFromFakeGFAResponse
0x14003a7f2  xor     esi, esi
0x14003a7f4  mov     ebx, eax
0x14003a7f6  test    eax, eax
0x14003a7f8  jnz     loc_14003ACDF
0x14003a7fe  lea     r8d, [rax+4]
0x14003a802  mov     rdx, rbp
0x14003a805  mov     rcx, rdi
0x14003a808  call    MRxSmbQueryFileInformationFromPseudoOpen
0x14003a80d  mov     ebx, eax
0x14003a80f  test    eax, eax
0x14003a811  jnz     short loc_14003A844
0x14003a813  test    r15b, r15b
0x14003a816  jz      short loc_14003A827
0x14003a818  cmp     [rdi+215h], sil
0x14003a81f  mov     eax, 0C0000103h
0x14003a824  cmovz   ebx, eax
0x14003a827  test    r12d, r12d
0x14003a82a  jz      short loc_14003A83C
0x14003a82c  cmp     [rdi+215h], sil
0x14003a833  jz      short loc_14003A83C
0x14003a835  mov     ebx, 0C00000BAh
0x14003a83a  jmp     short loc_14003A844
0x14003a83c  test    ebx, ebx
0x14003a83e  jz      loc_14003ACDF
0x14003a844  mov     rcx, [r14+10h]; P
0x14003a848  xor     edx, edx; Tag
0x14003a84a  call    cs:__imp_ExFreePoolWithTag
0x14003a851  nop     dword ptr [rax+rax+00h]
0x14003a856  mov     [r14+10h], rsi
0x14003a85a  jmp     loc_14003ACDF
0x14003a85f  test    r12d, r12d
0x14003a862  jz      short loc_14003A86E
0x14003a864  mov     ebx, 0C00000BAh
0x14003a869  jmp     loc_14003ACDF
0x14003a86e  lea     eax, [rsi-1]
0x14003a871  test    eax, 0FFFFFFFDh
0x14003a876  jz      loc_14003ACD0
0x14003a87c  mov     r15b, 1
0x14003a87f  mov     r13b, r15b
0x14003a882  mov     eax, 0FFFFh
0x14003a887  mov     byte ptr [rsp+98h+arg_0], dl
0x14003a88e  cmp     word ptr [rsp+98h+arg_18], ax
0x14003a896  jz      short loc_14003A8AA
0x14003a898  test    esi, esi
0x14003a89a  jz      short loc_14003A8AA
0x14003a89c  mov     ebx, 0C0000002h
0x14003a8a1  test    r12d, r12d
0x14003a8a4  jnz     loc_14003A9EA
0x14003a8aa  mov     rdx, rbp
0x14003a8ad  mov     rcx, rdi; pContext
0x14003a8b0  call    MRxSmbGetFileAttributes
0x14003a8b5  xor     edx, edx
0x14003a8b7  mov     ebx, eax
0x14003a8b9  test    eax, eax
0x14003a8bb  jnz     short loc_14003A8D4
0x14003a8bd  test    r15b, r15b
0x14003a8c0  jz      short loc_14003A8D4
0x14003a8c2  cmp     [rdi+215h], dl
0x14003a8c8  jnz     short loc_14003A8D4
0x14003a8ca  mov     ebx, 0C0000103h
0x14003a8cf  jmp     loc_14003ACDF
0x14003a8d4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003a8db  lea     rax, WPP_GLOBAL_Control
0x14003a8e2  cmp     rcx, rax
0x14003a8e5  jz      short loc_14003A911
0x14003a8e7  test    dword ptr [rcx+2Ch], 400h
0x14003a8ee  jz      short loc_14003A90A
0x14003a8f0  mov     rcx, [rcx+18h]
0x14003a8f4  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003a8fb  mov     edx, 1Fh
0x14003a900  mov     r9d, ebx
0x14003a903  call    WPP_SF_d
0x14003a908  xor     edx, edx
0x14003a90a  lea     rax, WPP_GLOBAL_Control
0x14003a911  test    ebx, ebx
0x14003a913  js      loc_14003A9B5
0x14003a919  mov     r9d, [rdi+1F8h]
0x14003a920  mov     r14d, r9d
0x14003a923  and     r14d, 10h
0x14003a927  setnz   r13b
0x14003a92b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003a932  cmp     rcx, rax
0x14003a935  jz      short loc_14003A957
0x14003a937  test    dword ptr [rcx+2Ch], 400h
0x14003a93e  jz      short loc_14003A957
0x14003a940  mov     rcx, [rcx+18h]
0x14003a944  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003a94b  mov     edx, 20h ; ' '
0x14003a950  call    WPP_SF_d
0x14003a955  xor     edx, edx
0x14003a957  cmp     esi, 2
0x14003a95a  jnz     short loc_14003A966
0x14003a95c  mov     ebx, 0C0000035h
0x14003a961  jmp     loc_14003ACDF
0x14003a966  test    r15b, r15b
0x14003a969  jz      short loc_14003A989
0x14003a96b  test    r14d, r14d
0x14003a96e  jnz     short loc_14003A989
0x14003a970  test    esi, esi
0x14003a972  jz      short loc_14003A989
0x14003a974  mov     ebx, 0C0000035h
0x14003a979  cmp     esi, 1
0x14003a97c  mov     eax, 0C0000024h
0x14003a981  cmovnz  ebx, eax
0x14003a984  jmp     loc_14003ACDF
0x14003a989  test    r12d, r12d
0x14003a98c  jz      short loc_14003A99E
0x14003a98e  test    r14d, r14d
0x14003a991  jz      short loc_14003A99E
0x14003a993  test    esi, esi
0x14003a995  jz      short loc_14003A9ED
0x14003a997  mov     ebx, 0C00000BAh
0x14003a99c  jmp     short loc_14003A979
0x14003a99e  lea     eax, [rsi-1]
0x14003a9a1  test    eax, 0FFFFFFFDh
0x14003a9a6  jnz     short loc_14003A9ED
0x14003a9a8  mov     rcx, rdi
0x14003a9ab  call    MRxSmbPseudoOpenTailFromGFAResponse
0x14003a9b0  jmp     loc_14003ACDF
0x14003a9b5  cmp     ebx, 0C000000Fh
0x14003a9bb  jz      short loc_14003A9C9
0x14003a9bd  cmp     ebx, 0C000003Ah
0x14003a9c3  jnz     loc_14003ACDF
0x14003a9c9  cmp     esi, 5
0x14003a9cc  ja      loc_14003ACB8
0x14003a9d2  mov     eax, 2Dh ; '-'
0x14003a9d7  bt      eax, esi
0x14003a9da  jnb     loc_14003ACB8
0x14003a9e0  mov     r13b, byte ptr [rsp+98h+arg_0]
0x14003a9e8  jmp     short loc_14003A9ED
0x14003a9ea  mov     r13b, dl
0x14003a9ed  mov     r14d, 0FFFFFFF7h
0x14003a9f3  mov     qword ptr [rdi+6Ch], 0
0x14003a9fb  and     [rdi+48h], r14d
0x14003a9ff  mov     [rdi+68h], edx
0x14003aa02  mov     [rdi+74h], edx
0x14003aa05  mov     [rdi+30h], edx
0x14003aa08  mov     [rdi+28h], edx
0x14003aa0b  test    ebx, ebx
0x14003aa0d  js      short loc_14003AA80
0x14003aa0f  test    esi, esi
0x14003aa11  jnz     short loc_14003AA80
0x14003aa13  mov     r8b, [rdi+215h]
0x14003aa1a  mov     rdx, rbp
0x14003aa1d  mov     rcx, rdi; pContext
0x14003aa20  call    MRxSmbCoreDeleteForSupercedeOrClose
0x14003aa25  xor     edx, edx
0x14003aa27  mov     ebx, eax
0x14003aa29  test    eax, eax
0x14003aa2b  jns     short loc_14003AA6C
0x14003aa2d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003aa34  lea     rax, WPP_GLOBAL_Control
0x14003aa3b  cmp     rcx, rax
0x14003aa3e  jz      loc_14003AD17
0x14003aa44  test    dword ptr [rcx+2Ch], 400h
0x14003aa4b  jz      loc_14003ACDF
0x14003aa51  lea     edx, [rsi+21h]
0x14003aa54  mov     rcx, [rcx+18h]
0x14003aa58  lea     r8, WPP_6b9e4f57e45e32add9588aaf92b3ae93_Traceguids
0x14003aa5f  mov     r9d, ebx
0x14003aa62  call    WPP_SF_d
0x14003aa67  jmp     loc_14003ACDF
0x14003aa6c  and     [rdi+48h], r14d
0x14003aa70  mov     [rdi+6Ch], rdx
0x14003aa74  mov     [rdi+68h], edx
0x14003aa77  mov     [rdi+74h], edx
0x14003aa7a  mov     [rdi+30h], edx
0x14003aa7d  mov     [rdi+28h], edx
0x14003aa80  test    r15b, r15b
0x14003aa83  jnz     loc_14003AC1A
0x14003aa89  test    r13b, r13b
0x14003aa8c  jz      short loc_14003AA96
0x14003aa8e  test    esi, esi
0x14003aa90  jz      loc_14003AC1A
0x14003aa96  movzx   r12d, [rsp+98h+arg_8]
0x14003aa9f  mov     r14d, edx
0x14003aaa2  mov     r15b, dl
0x14003aaa5  mov     eax, esi
0x14003aaa7  test    esi, esi
0x14003aaa9  jz      loc_14003AB30
0x14003aaaf  sub     eax, 1
0x14003aab2  jz      short loc_14003AACF
0x14003aab4  sub     eax, 1
0x14003aab7  jz      short loc_14003AB30
0x14003aab9  sub     eax, 1
0x14003aabc  jz      short loc_14003AACF
  ... truncated ...
```
