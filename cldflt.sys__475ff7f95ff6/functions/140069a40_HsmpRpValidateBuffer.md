# HsmpRpValidateBuffer

- ea: `0x140069a40`
- end: `0x14006a253`
- name: `HsmpRpValidateBuffer`
- size: `2067`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140059768`
- `0x140067e24`

## callees

- `0x140003c50`
- `0x14000d908`
- `0x14000d95c`
- `0x14000db8c`
- `0x140069a40`
- `0x14006a25c`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x140069aac`
- `ntoskrnl!RtlComputeCrc32` at `0x140069aac`

## pseudocode

```c
__int64 __fastcall HsmpRpValidateBuffer(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  int v3; // ebp
  unsigned int v4; // eax
  __int64 v5; // rbx
  unsigned __int64 v6; // r8
  __int64 v7; // r10
  unsigned __int64 v8; // r11
  int v9; // r15d
  __int64 i; // r9
  unsigned int v11; // eax
  unsigned __int64 v12; // rax
  unsigned int v13; // ecx
  unsigned int IsReparseBufferSupported; // edi
  unsigned __int16 v16; // dx
  unsigned __int64 v17; // rcx
  unsigned int v18; // eax
  __int64 v19; // rbp
  unsigned int v20; // r14d
  int v21; // edi
  unsigned int v22; // eax
  unsigned int v23; // edx
  __int64 v24; // rax
  unsigned __int16 v25; // r9
  unsigned __int64 v26; // r8
  unsigned int v27; // eax
  int v28; // edi
  unsigned int v29; // r8d
  __int64 v30; // rax
  unsigned __int16 v31; // r9
  unsigned __int64 v32; // rdx
  unsigned int v33; // eax
  int v34; // edi
  PDEVICE_OBJECT v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // r9
  unsigned int v38; // edx
  __int64 v39; // rax
  unsigned __int16 v40; // r9
  unsigned __int64 v41; // r8
  unsigned int v42; // eax
  unsigned int v43; // edx
  __int64 v44; // rax
  unsigned __int16 v45; // r9
  unsigned __int64 v46; // r8
  unsigned int v47; // eax
  unsigned int v48; // edx
  __int64 v49; // rax
  unsigned __int16 v50; // r9
  unsigned __int64 v51; // r8

  v2 = a2 - 4;
  LOBYTE(v3) = 0;
  if ( a2 <= 4 )
    v2 = 0;
  v4 = *(_DWORD *)a1 & 0xF;
  if ( v4 )
  {
    if ( v4 <= 1 )
    {
      if ( v2 < 0x18 )
        goto LABEL_21;
      v5 = a1 + 4;
      if ( *(_DWORD *)(a1 + 4) != 1884448070
        || (*(_BYTE *)(a1 + 16) & 2) != 0 && *(_DWORD *)(a1 + 8) != RtlComputeCrc32(0, (PUCHAR)(a1 + 12), v2 - 8) )
      {
        goto LABEL_21;
      }
      v6 = *(unsigned int *)(v5 + 8);
      if ( v2 < (unsigned int)v6 )
        goto LABEL_21;
      v7 = *(unsigned __int16 *)(v5 + 14);
      if ( !(_WORD)v7 )
        goto LABEL_21;
      v8 = 8 * v7 + 16;
      if ( v8 >= v6 )
        goto LABEL_21;
      v9 = 0x10000;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v11 = *(unsigned __int16 *)(v5 + 14);
        if ( (unsigned int)v7 >= 0xA )
          v11 = 10;
        if ( (unsigned int)i >= v11 )
          break;
        if ( *(_WORD *)(v5 + 8 * i + 16) >= 0x12u )
          goto LABEL_21;
        v12 = *(unsigned int *)(v5 + 8 * i + 20);
        if ( (_DWORD)v12 )
        {
          if ( v12 < v8 )
            goto LABEL_21;
        }
        if ( (unsigned int)v12 > (unsigned int)v6 )
          goto LABEL_21;
        v13 = *(unsigned __int16 *)(v5 + 8 * i + 18);
        if ( v13 > (unsigned int)v6
          || v13 + (unsigned int)v12 > (unsigned int)v6
          || v13 + (unsigned int)v12 < (unsigned int)v12 )
        {
          goto LABEL_21;
        }
        ++v9;
      }
      if ( (unsigned int)v6 < 0x18
        || (v16 = *(_WORD *)(v5 + 16), v16 >= 0x12u)
        || (v17 = *(unsigned int *)(v5 + 20), (_DWORD)v17) && (v17 < v8 || (unsigned int)v17 > (unsigned int)v6)
        || (v18 = *(unsigned __int16 *)(v5 + 18), v18 > (unsigned int)v6)
        || v18 + (unsigned int)v17 > (unsigned int)v6
        || v18 + (unsigned int)v17 < (unsigned int)v17
        || v16 != 7
        || v18 != 1
        || *(_BYTE *)(v17 + v5) > 1u )
      {
LABEL_21:
        HsmDbgBreakOnCorruption();
        IsReparseBufferSupported = -1073688830;
        HsmDbgBreakOnStatus(-1073688830);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids);
        }
        return IsReparseBufferSupported;
      }
      v38 = *(_DWORD *)(v5 + 8);
      v39 = *(unsigned __int16 *)(v5 + 14);
      if ( (unsigned __int16)v39 > 1u
        && (unsigned int)v6 >= 0x20
        && (v40 = *(_WORD *)(v5 + 24), v40 < 0x12u)
        && ((v41 = *(unsigned int *)(v5 + 28), !(_DWORD)v41) || v41 >= 8 * v39 + 16 && (unsigned int)v41 <= v38)
        && (v42 = *(unsigned __int16 *)(v5 + 26), v42 <= v38)
        && v42 + (unsigned int)v41 <= v38
        && v42 + (unsigned int)v41 >= (unsigned int)v41
        && v40 == 10
        && v42 == 4 )
      {
        v3 = *(_DWORD *)(v41 + v5);
        IsReparseBufferSupported = 0;
      }
      else
      {
        IsReparseBufferSupported = -1073741275;
      }
      HsmDbgBreakOnStatus(IsReparseBufferSupported);
      if ( (IsReparseBufferSupported & 0x80000000) != 0 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          return IsReparseBufferSupported;
        }
        v36 = 24;
        v37 = IsReparseBufferSupported;
        goto LABEL_115;
      }
      if ( (v3 & 0x10) != 0 )
        return IsReparseBufferSupported;
      v43 = *(_DWORD *)(v5 + 8);
      if ( v43 < 0x18 )
      {
        IsReparseBufferSupported = -1073741275;
        HsmDbgBreakOnStatus(-1073741275);
      }
      else
      {
        v44 = *(unsigned __int16 *)(v5 + 14);
        if ( (unsigned __int16)v44 > 2u
          && v43 >= 0x28
          && (v45 = *(_WORD *)(v5 + 32), v45 < 0x12u)
          && ((v46 = *(unsigned int *)(v5 + 36), !(_DWORD)v46) || v46 >= 8 * v44 + 16 && (unsigned int)v46 <= v43)
          && (v47 = *(unsigned __int16 *)(v5 + 34), v47 <= v43)
          && v47 + (unsigned int)v46 <= v43
          && v47 + (unsigned int)v46 >= (unsigned int)v46
          && v45 == 6
          && v47 == 8 )
        {
          IsReparseBufferSupported = 0;
        }
        else
        {
          IsReparseBufferSupported = -1073741275;
        }
        HsmDbgBreakOnStatus(IsReparseBufferSupported);
        if ( (IsReparseBufferSupported & 0x80000000) == 0 )
        {
          v48 = *(_DWORD *)(v5 + 8);
          v19 = 0;
          v20 = 0;
          if ( v48 < 0x18 )
          {
            HsmDbgBreakOnStatus(-1073741275);
          }
          else
          {
            v49 = *(unsigned __int16 *)(v5 + 14);
            if ( (unsigned __int16)v49 <= 4u
              || v48 < 0x38
              || (v50 = *(_WORD *)(v5 + 48), v50 >= 0x12u)
              || (v51 = *(unsigned int *)(v5 + 52), (_DWORD)v51) && (v51 < 8 * v49 + 16 || (unsigned int)v51 > v48)
              || (v22 = *(unsigned __int16 *)(v5 + 50), v22 > v48)
              || v22 + (unsigned int)v51 > v48
              || v50 != 17
              || v22 + (unsigned int)v51 < (unsigned int)v51 )
            {
              v21 = -1073741275;
            }
            else
            {
              if ( (_DWORD)v51 && (_WORD)v22 )
                v19 = v5 + v51;
              v20 = *(unsigned __int16 *)(v5 + 50);
              v21 = 0;
            }
            if ( v21 < 0 )
              v20 = 0;
            HsmDbgBreakOnStatus(v21);
            if ( v21 >= 0 )
            {
              IsReparseBufferSupported = HsmpBitmapIsReparseBufferSupported(v19, v20);
              HsmDbgBreakOnStatus(IsReparseBufferSupported);
              if ( (IsReparseBufferSupported & 0x80000000) != 0 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  return IsReparseBufferSupported;
                }
                v36 = 26;
                goto LABEL_114;
              }
            }
          }
          v23 = *(_DWORD *)(v5 + 8);
          if ( v23 < 0x18 )
          {
            HsmDbgBreakOnStatus(-1073741275);
          }
          else
          {
            v24 = *(unsigned __int16 *)(v5 + 14);
            if ( (unsigned __int16)v24 <= 5u
              || v23 < 0x40
              || (v25 = *(_WORD *)(v5 + 56), v25 >= 0x12u)
              || (v26 = *(unsigned int *)(v5 + 60), (_DWORD)v26) && (v26 < 8 * v24 + 16 || (unsigned int)v26 > v23)
              || (v27 = *(unsigned __int16 *)(v5 + 58), v27 > v23)
              || v27 + (unsigned int)v26 > v23
              || v25 != 17
              || v27 + (unsigned int)v26 < (unsigned int)v26 )
            {
              v28 = -1073741275;
            }
            else
            {
              if ( (_DWORD)v26 && (_WORD)v27 )
                v19 = v5 + v26;
              else
                v19 = 0;
              v28 = 0;
              v20 = *(unsigned __int16 *)(v5 + 58);
            }
            HsmDbgBreakOnStatus(v28);
            if ( v28 >= 0 )
            {
              IsReparseBufferSupported = HsmpBitmapIsReparseBufferSupported(v19, v20);
              HsmDbgBreakOnStatus(IsReparseBufferSupported);
              if ( (IsReparseBufferSupported & 0x80000000) != 0 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  return IsReparseBufferSupported;
                }
                v36 = 27;
                goto LABEL_114;
              }
            }
          }
          v29 = *(_DWORD *)(v5 + 8);
          if ( v29 < 0x18 )
          {
            HsmDbgBreakOnStatus(-1073741275);
            return 0;
          }
          v30 = *(unsigned __int16 *)(v5 + 14);
          if ( (unsigned __int16)v30 <= 6u
            || v29 < 0x48
            || (v31 = *(_WORD *)(v5 + 64), v31 >= 0x12u)
            || (v32 = *(unsigned int *)(v5 + 68), (_DWORD)v32) && (v32 < 8 * v30 + 16 || (unsigned int)v32 > v29)
            || (v33 = *(unsigned __int16 *)(v5 + 66), v33 > v29)
            || v33 + (unsigned int)v32 > v29
            || v31 != 17
            || v33 + (unsigned int)v32 < (unsigned int)v32 )
          {
            v34 = -1073741275;
          }
          else
          {
            if ( (_DWORD)v32 && (_WORD)v33 )
              v19 = v5 + v32;
            else
              v19 = 0;
            v34 = 0;
            v20 = *(unsigned __int16 *)(v5 + 66);
          }
          HsmDbgBreakOnStatus(v34);
          if ( v34 < 0 )
            return 0;
          IsReparseBufferSupported = HsmpBitmapIsReparseBufferSupported(v19, v20);
          HsmDbgBreakOnStatus(IsReparseBufferSupported);
          if ( (IsReparseBufferSupported & 0x80000000) == 0 )
            return IsReparseBufferSupported;
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            return IsReparseBufferSupported;
          }
          v36 = 28;
          goto LABEL_114;
        }
      }
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return IsReparseBufferSupported;
      }
      v36 = 25;
LABEL_114:
      v37 = IsReparseBufferSupported;
LABEL_115:
      WPP_SF_d(v35->AttachedDevice, v36, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids, v37);
      return IsReparseBufferSupported;
    }
    IsReparseBufferSupported = -1073741735;
    HsmDbgBreakOnStatus(-1073741735);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return IsReparseBufferSupported;
    }
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids);
    return 3221225561LL;
  }
  else
  {
    HsmDbgBreakOnCorruption();
    IsReparseBufferSupported = -1073741736;
    HsmDbgBreakOnStatus(-1073741736);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return IsReparseBufferSupported;
    }
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids);
    return 3221225560LL;
  }
}

```

## disassembly

```asm
0x140069a40  mov     [rsp+arg_18], rbx
0x140069a45  push    rbp
0x140069a46  push    rsi
0x140069a47  push    rdi
0x140069a48  sub     rsp, 30h
0x140069a4c  xor     eax, eax
0x140069a4e  lea     edi, [rdx-4]
0x140069a51  xor     ebp, ebp
0x140069a53  mov     rbx, rcx
0x140069a56  cmp     edx, 4
0x140069a59  cmovbe  edi, eax
0x140069a5c  mov     eax, [rcx]
0x140069a5e  and     eax, 0Fh
0x140069a61  cmp     eax, 1
0x140069a64  jb      loc_140069C45
0x140069a6a  ja      loc_140069CB2
0x140069a70  mov     [rsp+48h+arg_0], r14
0x140069a75  mov     [rsp+48h+arg_10], r15
0x140069a7a  cmp     edi, 18h
0x140069a7d  jb      loc_14006A24B
0x140069a83  add     rbx, 4
0x140069a87  cmp     dword ptr [rbx], 70526546h
0x140069a8d  jnz     loc_14006A240
0x140069a93  mov     r14d, 2
0x140069a99  test    [rbx+0Ch], r14b
0x140069a9d  jz      short loc_140069ABD
0x140069a9f  lea     r8d, [rdi-8]; Length
0x140069aa3  xor     ecx, ecx; InitialCrc
0x140069aa5  lea     rdx, [rbx+8]; Buffer
0x140069aa9  mov     r15d, r14d
0x140069aac  call    cs:__imp_RtlComputeCrc32
0x140069ab3  nop     dword ptr [rax+rax+00h]
0x140069ab8  cmp     [rbx+4], eax
0x140069abb  jnz     short loc_140069B36
0x140069abd  mov     r8d, [rbx+8]
0x140069ac1  cmp     edi, r8d
0x140069ac4  jb      loc_14006A235
0x140069aca  movzx   r10d, word ptr [rbx+0Eh]
0x140069acf  test    r10w, r10w
0x140069ad3  jz      loc_14006A22A
0x140069ad9  lea     r11, ds:10h[r10*8]
0x140069ae1  cmp     r11, r8
0x140069ae4  jnb     loc_14006A21F
0x140069aea  mov     r15d, 10000h
0x140069af0  xor     r9d, r9d
0x140069af3  mov     eax, r10d
0x140069af6  cmp     r10d, 0Ah
0x140069afa  jb      short loc_140069B01
0x140069afc  mov     eax, 0Ah
0x140069b01  cmp     r9d, eax
0x140069b04  jnb     loc_140069B8E
0x140069b0a  cmp     word ptr [rbx+r9*8+10h], 12h
0x140069b11  jnb     short loc_140069B36
0x140069b13  mov     eax, [rbx+r9*8+14h]
0x140069b18  lea     rdx, [rbx+r9*8]
0x140069b1c  test    eax, eax
0x140069b1e  jnz     short loc_140069B78
0x140069b20  cmp     eax, r8d
0x140069b23  ja      short loc_140069B36
0x140069b25  movzx   ecx, word ptr [rdx+12h]
0x140069b29  cmp     ecx, r8d
0x140069b2c  ja      short loc_140069B36
0x140069b2e  lea     edx, [rcx+rax]
0x140069b31  cmp     edx, r8d
0x140069b34  jbe     short loc_140069B7F
0x140069b36  call    HsmDbgBreakOnCorruption
0x140069b3b  mov     edi, 0C000CF02h
0x140069b40  mov     ecx, edi
0x140069b42  call    HsmDbgBreakOnStatus
0x140069b47  mov     rcx, cs:WPP_GLOBAL_Control
0x140069b4e  lea     rax, WPP_GLOBAL_Control
0x140069b55  cmp     rcx, rax
0x140069b58  jnz     loc_140069C0F
0x140069b5e  mov     r14, [rsp+48h+arg_0]
0x140069b63  mov     r15, [rsp+48h+arg_10]
0x140069b68  mov     eax, edi
0x140069b6a  mov     rbx, [rsp+48h+arg_18]
0x140069b6f  add     rsp, 30h
0x140069b73  pop     rdi
0x140069b74  pop     rsi
0x140069b75  pop     rbp
0x140069b76  retn
0x140069b78  cmp     rax, r11
0x140069b7b  jnb     short loc_140069B20
0x140069b7d  jmp     short loc_140069B36
0x140069b7f  cmp     edx, eax
0x140069b81  jb      short loc_140069B36
0x140069b83  inc     r15d
0x140069b86  inc     r9d
0x140069b89  jmp     loc_140069AF3
0x140069b8e  mov     r15d, 20000h
0x140069b94  cmp     r8d, 18h
0x140069b98  jb      short loc_140069B36
0x140069b9a  xor     eax, eax
0x140069b9c  cmp     ax, r10w
0x140069ba0  jnb     short loc_140069B36
0x140069ba2  movzx   edx, word ptr [rbx+10h]
0x140069ba6  cmp     dx, 12h
0x140069baa  jnb     short loc_140069B36
0x140069bac  mov     ecx, [rbx+14h]
0x140069baf  test    ecx, ecx
0x140069bb1  jz      short loc_140069BC5
0x140069bb3  cmp     rcx, r11
0x140069bb6  jb      loc_140069B36
0x140069bbc  cmp     ecx, r8d
0x140069bbf  ja      loc_140069B36
0x140069bc5  movzx   eax, word ptr [rbx+12h]
0x140069bc9  cmp     eax, r8d
0x140069bcc  ja      loc_140069B36
0x140069bd2  lea     r9d, [rax+rcx]
0x140069bd6  cmp     r9d, r8d
0x140069bd9  ja      loc_140069B36
0x140069bdf  cmp     r9d, ecx
0x140069be2  jb      loc_140069B36
0x140069be8  cmp     dx, 7
0x140069bec  jnz     loc_140069B36
0x140069bf2  cmp     eax, 1
0x140069bf5  jnz     loc_140069B36
0x140069bfb  cmp     [rcx+rbx], al
0x140069bfe  jbe     loc_140069FD5
0x140069c04  mov     r15d, 20001h
0x140069c0a  jmp     loc_140069B36
0x140069c0f  mov     eax, [rcx+2Ch]
0x140069c12  test    al, 1
0x140069c14  jz      loc_140069B5E
0x140069c1a  cmp     byte ptr [rcx+29h], 2
0x140069c1e  jb      loc_140069B5E
0x140069c24  mov     rcx, [rcx+18h]
0x140069c28  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x140069c2f  mov     edx, 17h
0x140069c34  mov     [rsp+48h+var_28], edi
0x140069c38  mov     r9d, r15d
0x140069c3b  call    WPP_SF_Dd
0x140069c40  jmp     loc_140069B5E
0x140069c45  call    HsmDbgBreakOnCorruption
0x140069c4a  mov     edi, 0C0000058h
0x140069c4f  mov     ecx, edi
0x140069c51  call    HsmDbgBreakOnStatus
0x140069c56  mov     rcx, cs:WPP_GLOBAL_Control
0x140069c5d  lea     rax, WPP_GLOBAL_Control
0x140069c64  cmp     rcx, rax
0x140069c67  jz      loc_140069B68
0x140069c6d  mov     eax, [rcx+2Ch]
0x140069c70  test    al, 1
0x140069c72  jz      loc_140069B68
0x140069c78  cmp     byte ptr [rcx+29h], 2
0x140069c7c  jb      loc_140069B68
0x140069c82  mov     r9d, [rbx]
0x140069c85  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x140069c8c  mov     rcx, [rcx+18h]
0x140069c90  and     r9d, 0Fh
0x140069c94  mov     edx, 15h
0x140069c99  mov     [rsp+48h+var_28], edi
0x140069c9d  call    WPP_SF_Dd
0x140069ca2  mov     eax, edi
0x140069ca4  mov     rbx, [rsp+48h+arg_18]
0x140069ca9  add     rsp, 30h
0x140069cad  pop     rdi
0x140069cae  pop     rsi
0x140069caf  pop     rbp
0x140069cb0  retn
0x140069cb2  mov     edi, 0C0000059h
0x140069cb7  mov     ecx, edi
0x140069cb9  call    HsmDbgBreakOnStatus
0x140069cbe  mov     rcx, cs:WPP_GLOBAL_Control
0x140069cc5  lea     rax, WPP_GLOBAL_Control
0x140069ccc  cmp     rcx, rax
0x140069ccf  jz      loc_140069B68
0x140069cd5  mov     eax, [rcx+2Ch]
0x140069cd8  test    al, 1
0x140069cda  jz      loc_140069B68
0x140069ce0  cmp     byte ptr [rcx+29h], 2
0x140069ce4  jb      loc_140069B68
0x140069cea  mov     r9d, [rbx]
0x140069ced  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x140069cf4  mov     rcx, [rcx+18h]
0x140069cf8  and     r9d, 0Fh
0x140069cfc  mov     edx, 16h
0x140069d01  mov     [rsp+48h+var_28], edi
0x140069d05  call    WPP_SF_Dd
0x140069d0a  mov     rbx, [rsp+48h+arg_18]
0x140069d0f  mov     eax, edi
0x140069d11  add     rsp, 30h
0x140069d15  pop     rdi
0x140069d16  pop     rsi
0x140069d17  pop     rbp
0x140069d18  retn
0x140069d1a  cmp     ecx, r8d
0x140069d1d  jb      short loc_140069D5A
0x140069d1f  test    r8d, r8d
0x140069d22  jz      short loc_140069D2D
0x140069d24  test    ax, ax
0x140069d27  jz      short loc_140069D2D
0x140069d29  lea     rbp, [rbx+r8]
0x140069d2d  mov     r14d, eax
0x140069d30  xor     edi, edi
0x140069d32  jmp     short loc_140069D5C
0x140069d34  lea     rcx, ds:10h[rax*8]
0x140069d3c  cmp     r8, rcx
0x140069d3f  jb      short loc_140069D5A
0x140069d41  cmp     r8d, edx
0x140069d44  ja      short loc_140069D5A
0x140069d46  movzx   eax, word ptr [rbx+32h]
0x140069d4a  cmp     eax, edx
0x140069d4c  ja      short loc_140069D5A
0x140069d4e  lea     ecx, [rax+r8]
0x140069d52  cmp     ecx, edx
0x140069d54  jbe     loc_140069E68
0x140069d5a  mov     edi, esi
0x140069d5c  xor     eax, eax
0x140069d5e  mov     ecx, edi
0x140069d60  test    edi, edi
0x140069d62  cmovs   r14d, eax
0x140069d66  call    HsmDbgBreakOnStatus
0x140069d6b  test    edi, edi
0x140069d6d  jns     loc_14006A1FA
0x140069d73  cmp     edi, esi
0x140069d75  jnz     loc_140069F25
0x140069d7b  mov     edx, [rbx+8]
0x140069d7e  cmp     edx, 18h
0x140069d81  jb      loc_14006A213
0x140069d87  movzx   eax, word ptr [rbx+0Eh]
0x140069d8b  mov     r15d, 5
0x140069d91  cmp     r15w, ax
0x140069d95  jnb     short loc_140069DD7
0x140069d97  cmp     edx, 40h ; '@'
0x140069d9a  jb      short loc_140069DD7
0x140069d9c  movzx   r9d, word ptr [rbx+38h]
0x140069da1  cmp     r9w, 12h
0x140069da6  jnb     short loc_140069DD7
0x140069da8  mov     r8d, [rbx+3Ch]
0x140069dac  test    r8d, r8d
0x140069daf  jz      short loc_140069DC3
0x140069db1  lea     rcx, ds:10h[rax*8]
0x140069db9  cmp     r8, rcx
0x140069dbc  jb      short loc_140069DD7
0x140069dbe  cmp     r8d, edx
0x140069dc1  ja      short loc_140069DD7
0x140069dc3  movzx   eax, word ptr [rbx+3Ah]
0x140069dc7  cmp     eax, edx
0x140069dc9  ja      short loc_140069DD7
0x140069dcb  lea     ecx, [rax+r8]
0x140069dcf  cmp     ecx, edx
0x140069dd1  jbe     loc_140069E78
0x140069dd7  mov     edi, esi
0x140069dd9  mov     ecx, edi
0x140069ddb  call    HsmDbgBreakOnStatus
0x140069de0  test    edi, edi
0x140069de2  jns     loc_140069ED6
0x140069de8  cmp     edi, esi
0x140069dea  jnz     loc_140069EEA
0x140069df0  mov     r8d, [rbx+8]
0x140069df4  cmp     r8d, 18h
0x140069df8  jb      loc_140069FC7
0x140069dfe  movzx   eax, word ptr [rbx+0Eh]
0x140069e02  mov     ecx, 6
0x140069e07  cmp     cx, ax
0x140069e0a  jnb     short loc_140069E48
0x140069e0c  cmp     r8d, 48h ; 'H'
0x140069e10  jb      short loc_140069E48
0x140069e12  movzx   r9d, word ptr [rbx+40h]
0x140069e17  cmp     r9w, 12h
0x140069e1c  jnb     short loc_140069E48
0x140069e1e  mov     edx, [rbx+44h]
0x140069e21  test    edx, edx
0x140069e23  jz      short loc_140069E37
0x140069e25  lea     rcx, ds:10h[rax*8]
0x140069e2d  cmp     rdx, rcx
0x140069e30  jb      short loc_140069E48
0x140069e32  cmp     edx, r8d
0x140069e35  ja      short loc_140069E48
0x140069e37  movzx   eax, word ptr [rbx+42h]
0x140069e3b  cmp     eax, r8d
0x140069e3e  ja      short loc_140069E48
0x140069e40  lea     ecx, [rax+rdx]
0x140069e43  cmp     ecx, r8d
0x140069e46  jbe     short loc_140069EAC
0x140069e48  mov     edi, esi
0x140069e4a  mov     ecx, edi
0x140069e4c  call    HsmDbgBreakOnStatus
0x140069e51  test    edi, edi
0x140069e53  jns     loc_140069FA9
0x140069e59  cmp     edi, esi
0x140069e5b  jnz     loc_140069F60
0x140069e61  xor     edi, edi
0x140069e63  jmp     loc_140069B5E
0x140069e68  cmp     r9w, 11h
0x140069e6d  jz      loc_140069D1A
0x140069e73  jmp     loc_140069D5A
0x140069e78  cmp     r9w, 11h
0x140069e7d  jnz     loc_140069DD7
0x140069e83  cmp     ecx, r8d
0x140069e86  jb      loc_140069DD7
0x140069e8c  test    r8d, r8d
0x140069e8f  jz      loc_14006A18C
0x140069e95  test    ax, ax
0x140069e98  jz      loc_14006A18C
0x140069e9e  lea     rbp, [rbx+r8]
0x140069ea2  xor     edi, edi
0x140069ea4  mov     r14d, eax
  ... truncated ...
```
