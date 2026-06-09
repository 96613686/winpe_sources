# FIStreamLog

- ea: `0x140013fb0`
- end: `0x1400142c8`
- name: `FIStreamLog`
- size: `792`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e5a0`
- `0x14001334c`
- `0x140013560`
- `0x140013d70`
- `0x140016ea0`

## callees

- `0x140003920`
- `0x140003a00`
- `0x140013fb0`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14001426d`
- `ntoskrnl!EtwWrite` at `0x14001426d`
- `ntoskrnl!PfFileInfoNotify` at `0x1400140d8`
- `ntoskrnl!PfFileInfoNotify` at `0x140014100`
- `ntoskrnl!PfFileInfoNotify` at `0x1400140d8`
- `ntoskrnl!PfFileInfoNotify` at `0x140014100`

## pseudocode

```c
__int64 __fastcall FIStreamLog(__int64 a1)
{
  __int64 v1; // r10
  __int128 *v3; // r9
  __int64 *v4; // r8
  bool v5; // zf
  __int64 v6; // rdx
  __int64 v7; // rax
  void (__fastcall *v8)(_QWORD, _QWORD, __int128 *, __int64, int, __int16); // r10
  __int64 v10; // r9
  __int16 v11; // r8
  int v12; // ecx
  const EVENT_DESCRIPTOR *v13; // rdx
  int v14; // ecx
  __int16 v15; // [rsp+40h] [rbp-49h] BYREF
  __int128 v16; // [rsp+48h] [rbp-41h] BYREF
  __int128 *v17; // [rsp+58h] [rbp-31h]
  __int128 v18; // [rsp+60h] [rbp-29h] BYREF
  __int128 v19; // [rsp+70h] [rbp-19h] BYREF
  __int128 v20; // [rsp+80h] [rbp-9h]
  __int128 v21; // [rsp+90h] [rbp+7h]
  __int64 v22; // [rsp+A0h] [rbp+17h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A8h] [rbp+1Fh] BYREF
  __int16 *v24; // [rsp+B8h] [rbp+2Fh]
  __int64 v25; // [rsp+C0h] [rbp+37h]
  __int64 v26; // [rsp+C8h] [rbp+3Fh]
  int v27; // [rsp+D0h] [rbp+47h]
  int v28; // [rsp+D4h] [rbp+4Bh]

  v1 = *(_QWORD *)(a1 + 16);
  v19 = 0;
  v22 = 0;
  v20 = 0;
  v17 = 0;
  v21 = 0;
  v15 = 0;
  v16 = 0;
  v18 = 0;
  if ( *(_QWORD *)(v1 + 24) )
  {
    v3 = &v19;
    v4 = *(__int64 **)(a1 + 32);
    DWORD1(v16) = *(_DWORD *)(a1 + 24);
    LODWORD(v16) = 15;
    v5 = (*(_BYTE *)a1 & *(_BYTE *)(*(_QWORD *)(v1 + 24) + 132LL) & 1) == 0;
    v17 = &v19;
    DWORD2(v16) = !v5;
    *(_QWORD *)&v20 = *(_QWORD *)(v1 + 32);
    *((_QWORD *)&v19 + 1) = *(_QWORD *)(*(_QWORD *)(v1 + 24) + 72LL);
    DWORD1(v21) = (*((_DWORD *)v4 + 2) >> 2) & 1;
    DWORD1(v21) |= (*((_DWORD *)v4 + 2) >> 3) & 2;
    DWORD1(v21) |= (*((_DWORD *)v4 + 2) >> 2) & 8;
    DWORD1(v21) |= (*((_DWORD *)v4 + 2) >> 2) & 0x10;
    DWORD2(v21) = *((_DWORD *)v4 + 3);
    LODWORD(v22) = *(_DWORD *)(*(_QWORD *)(v1 + 24) + 120LL);
    HIDWORD(v21) = *((_DWORD *)v4 + 4);
    v6 = *v4;
    if ( *v4 )
    {
      *((_QWORD *)&v20 + 1) = *(_QWORD *)(v6 + 16);
      LODWORD(v21) = (*(_WORD *)(v6 + 8) & 0xFFFE) << 15;
      LODWORD(v21) = v21 | (*(unsigned __int16 *)(v6 + 24) >> 1);
    }
    else
    {
      LODWORD(v21) = 720896;
      *((_QWORD *)&v20 + 1) = FIUnknown;
    }
    if ( !v5 )
    {
      PfFileInfoNotify(&v16);
      v3 = v17;
    }
    if ( (*(_DWORD *)a1 & 8) != 0 )
    {
      v7 = *(_QWORD *)(a1 + 40);
      DWORD2(v16) = 4;
      *(_QWORD *)v3 = v7;
      PfFileInfoNotify(&v16);
      v3 = v17;
    }
    if ( (*(_DWORD *)a1 & 4) != 0 && qword_140009A28 )
    {
      switch ( DWORD1(v16) )
      {
        case 2:
          v13 = &FiEvt_FileNameCreate_Info;
LABEL_25:
          v14 = *((unsigned __int16 *)v3 + 17);
          UserData.Ptr = (ULONGLONG)(v3 + 1);
          v15 = v14;
          v24 = &v15;
          *(_QWORD *)&UserData.Size = 8;
          v25 = 2;
          v26 = *((_QWORD *)v3 + 3);
          v28 = 0;
          v27 = 2 * v14;
          EtwWrite(qword_140009A28, v13, 0, 3u, &UserData);
          break;
        case 3:
          v13 = (const EVENT_DESCRIPTOR *)FiEvt_FileNameDelete_Info;
          goto LABEL_25;
        case 6:
          v13 = (const EVENT_DESCRIPTOR *)FiEvt_FileNameRundown_Info;
          goto LABEL_25;
      }
    }
    if ( DWORD1(v16) == 6 )
      v8 = *(void (__fastcall **)(_QWORD, _QWORD, __int128 *, __int64, int, __int16))qword_140009A00;
    else
      v8 = *(void (__fastcall **)(_QWORD, _QWORD, __int128 *, __int64, int, __int16))(qword_140009A00 + 8);
    if ( (*(_DWORD *)a1 & 2) == 0 || !v8 )
      return 0;
    if ( DWORD1(v16) == 6 )
    {
      v10 = *(_QWORD *)(a1 + 8);
      v11 = 1060;
      v12 = *(_DWORD *)(a1 + 4);
    }
    else
    {
      if ( DWORD1(v16) != 2 )
      {
        if ( DWORD1(v16) == 3 )
        {
          LOWORD(v18) = 2 * *((_WORD *)v17 + 17);
          WORD1(v18) = v18;
          *((_QWORD *)&v18 + 1) = *((_QWORD *)v17 + 3);
          v8(*(_QWORD *)(a1 + 40), *((_QWORD *)v17 + 2), &v18, 0, 0, 1059);
        }
        return 0;
      }
      v10 = 0;
      v11 = 1056;
      v12 = 0;
    }
    LOWORD(v18) = 2 * *((_WORD *)v17 + 17);
    WORD1(v18) = v18;
    *((_QWORD *)&v18 + 1) = *((_QWORD *)v17 + 3);
    v8(*(_QWORD *)(a1 + 40), *((_QWORD *)v17 + 2), &v18, v10, v12, v11);
    return 0;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140013fb0  mov     [rsp-8+arg_8], rbx
0x140013fb5  push    rbp
0x140013fb6  lea     rbp, [rsp-57h]
0x140013fbb  sub     rsp, 0E0h
0x140013fc2  mov     rax, cs:__security_cookie
0x140013fc9  xor     rax, rsp
0x140013fcc  mov     [rbp+57h+var_8], rax
0x140013fd0  mov     r10, [rcx+10h]
0x140013fd4  xorps   xmm0, xmm0
0x140013fd7  xor     eax, eax
0x140013fd9  mov     rbx, rcx
0x140013fdc  movups  [rbp+57h+var_70], xmm0
0x140013fe0  mov     [rbp+57h+var_40], rax
0x140013fe4  movups  [rbp+57h+var_60], xmm0
0x140013fe8  mov     [rbp+57h+var_88], rax
0x140013fec  movups  [rbp+57h+var_50], xmm0
0x140013ff0  mov     [rbp+57h+var_A0], ax
0x140013ff4  movups  [rbp+57h+var_98], xmm0
0x140013ff8  movups  [rbp+57h+var_80], xmm0
0x140013ffc  cmp     [r10+18h], rax
0x140014000  jz      loc_1400141F0
0x140014006  mov     eax, [rcx+18h]
0x140014009  lea     r9, [rbp+57h+var_70]
0x14001400d  mov     r8, [rbx+20h]
0x140014011  xor     r11d, r11d
0x140014014  mov     dword ptr [rbp+57h+var_98+4], eax
0x140014017  mov     dword ptr [rbp+57h+var_98], 0Fh
0x14001401e  mov     rax, [r10+18h]
0x140014022  mov     ecx, [rax+84h]
0x140014028  mov     eax, 1
0x14001402d  and     ecx, [rbx]
0x14001402f  test    al, cl
0x140014031  mov     [rbp+57h+var_88], r9
0x140014035  cmovnz  r11d, eax
0x140014039  mov     dword ptr [rbp+57h+var_98+8], r11d
0x14001403d  mov     rax, [r10+20h]
0x140014041  mov     qword ptr [rbp+57h+var_60], rax
0x140014045  mov     rax, [r10+18h]
0x140014049  mov     rcx, [rax+48h]
0x14001404d  mov     qword ptr [rbp+57h+var_70+8], rcx
0x140014051  mov     eax, [r8+8]
0x140014055  shr     eax, 2
0x140014058  and     eax, 1
0x14001405b  mov     dword ptr [rbp+57h+var_50+4], eax
0x14001405e  mov     ecx, [r8+8]
0x140014062  shr     ecx, 3
0x140014065  and     ecx, 2
0x140014068  or      ecx, eax
0x14001406a  mov     dword ptr [rbp+57h+var_50+4], ecx
0x14001406d  mov     edx, [r8+8]
0x140014071  shr     edx, 2
0x140014074  and     edx, 8
0x140014077  or      edx, ecx
0x140014079  mov     dword ptr [rbp+57h+var_50+4], edx
0x14001407c  mov     eax, [r8+8]
0x140014080  shr     eax, 2
0x140014083  and     eax, 10h
0x140014086  or      eax, edx
0x140014088  mov     dword ptr [rbp+57h+var_50+4], eax
0x14001408b  mov     eax, [r8+0Ch]
0x14001408f  mov     dword ptr [rbp+57h+var_50+8], eax
0x140014092  mov     rax, [r10+18h]
0x140014096  mov     ecx, [rax+78h]
0x140014099  mov     dword ptr [rbp+57h+var_40], ecx
0x14001409c  mov     eax, [r8+10h]
0x1400140a0  mov     dword ptr [rbp+57h+var_50+0Ch], eax
0x1400140a3  mov     rdx, [r8]
0x1400140a6  test    rdx, rdx
0x1400140a9  jz      loc_14001428C
0x1400140af  mov     rax, [rdx+10h]
0x1400140b3  mov     qword ptr [rbp+57h+var_60+8], rax
0x1400140b7  movzx   ecx, word ptr [rdx+8]
0x1400140bb  and     ecx, 0FFFFFFFEh
0x1400140be  shl     ecx, 0Fh
0x1400140c1  mov     dword ptr [rbp+57h+var_50], ecx
0x1400140c4  movzx   eax, word ptr [rdx+18h]
0x1400140c8  shr     eax, 1
0x1400140ca  or      eax, ecx
0x1400140cc  mov     dword ptr [rbp+57h+var_50], eax
0x1400140cf  test    r11d, r11d
0x1400140d2  jz      short loc_1400140E8
0x1400140d4  lea     rcx, [rbp+57h+var_98]
0x1400140d8  call    cs:__imp_PfFileInfoNotify
0x1400140df  nop     dword ptr [rax+rax+00h]
0x1400140e4  mov     r9, [rbp+57h+var_88]
0x1400140e8  mov     eax, [rbx]
0x1400140ea  test    al, 8
0x1400140ec  jz      short loc_140014110
0x1400140ee  mov     rax, [rbx+28h]
0x1400140f2  lea     rcx, [rbp+57h+var_98]
0x1400140f6  mov     dword ptr [rbp+57h+var_98+8], 4
0x1400140fd  mov     [r9], rax
0x140014100  call    cs:__imp_PfFileInfoNotify
0x140014107  nop     dword ptr [rax+rax+00h]
0x14001410c  mov     r9, [rbp+57h+var_88]
0x140014110  mov     eax, [rbx]
0x140014112  test    al, 4
0x140014114  jnz     loc_1400141FA
0x14001411a  cmp     dword ptr [rbp+57h+var_98+4], 6
0x14001411e  mov     rax, cs:qword_140009A00
0x140014125  jz      short loc_1400141A6
0x140014127  mov     r10, [rax+8]
0x14001412b  mov     eax, [rbx]
0x14001412d  test    al, 2
0x14001412f  jz      short loc_140014136
0x140014131  test    r10, r10
0x140014134  jnz     short loc_140014156
0x140014136  xor     eax, eax
0x140014138  mov     rcx, [rbp+57h+var_8]
0x14001413c  xor     rcx, rsp; StackCookie
0x14001413f  call    __security_check_cookie
0x140014144  mov     rbx, [rsp+0E0h+arg_8]
0x14001414c  add     rsp, 0E0h
0x140014153  pop     rbp
0x140014154  retn
0x140014156  mov     ecx, dword ptr [rbp+57h+var_98+4]
0x140014159  cmp     ecx, 6
0x14001415c  jnz     short loc_1400141AB
0x14001415e  mov     r9, [rbx+8]
0x140014162  mov     r8d, 424h
0x140014168  mov     ecx, [rbx+4]
0x14001416b  mov     rdx, [rbp+57h+var_88]
0x14001416f  mov     [rsp+0E0h+var_B8], r8w
0x140014175  mov     dword ptr [rsp+0E0h+UserData], ecx
0x140014179  movzx   eax, word ptr [rdx+22h]
0x14001417d  add     ax, ax
0x140014180  mov     word ptr [rbp+57h+var_80], ax
0x140014184  mov     word ptr [rbp+57h+var_80+2], ax
0x140014188  mov     rax, [rdx+18h]
0x14001418c  mov     qword ptr [rbp+57h+var_80+8], rax
0x140014190  mov     rdx, [rdx+10h]
0x140014194  lea     r8, [rbp+57h+var_80]
0x140014198  mov     rcx, [rbx+28h]
0x14001419c  mov     rax, r10
0x14001419f  call    _guard_dispatch_icall
0x1400141a4  jmp     short loc_140014136
0x1400141a6  mov     r10, [rax]
0x1400141a9  jmp     short loc_14001412B
0x1400141ab  sub     ecx, 2
0x1400141ae  jz      loc_1400142B8
0x1400141b4  cmp     ecx, 1
0x1400141b7  jnz     loc_140014136
0x1400141bd  mov     rdx, [rbp+57h+var_88]
0x1400141c1  mov     [rsp+0E0h+var_B8], 423h
0x1400141c8  mov     dword ptr [rsp+0E0h+UserData], 0
0x1400141d0  movzx   r8d, word ptr [rdx+22h]
0x1400141d5  add     r8w, r8w
0x1400141d9  mov     word ptr [rbp+57h+var_80], r8w
0x1400141de  xor     r9d, r9d
0x1400141e1  mov     word ptr [rbp+57h+var_80+2], r8w
0x1400141e6  mov     r8, [rdx+18h]
0x1400141ea  mov     qword ptr [rbp+57h+var_80+8], r8
0x1400141ee  jmp     short loc_140014190
0x1400141f0  mov     eax, 0C000000Dh
0x1400141f5  jmp     loc_140014138
0x1400141fa  mov     r10, cs:qword_140009A28
0x140014201  test    r10, r10
0x140014204  jz      loc_14001411A
0x14001420a  mov     eax, dword ptr [rbp+57h+var_98+4]
0x14001420d  cmp     eax, 2
0x140014210  jnz     short loc_14001427E
0x140014212  lea     rdx, FiEvt_FileNameCreate_Info; EventDescriptor
0x140014219  movzx   ecx, word ptr [r9+22h]
0x14001421e  lea     rax, [r9+10h]
0x140014222  mov     [rbp+57h+var_38.Ptr], rax
0x140014226  xor     r8d, r8d; ActivityId
0x140014229  mov     [rbp+57h+var_A0], cx
0x14001422d  lea     rax, [rbp+57h+var_A0]
0x140014231  mov     [rbp+57h+var_28], rax
0x140014235  mov     qword ptr [rbp+57h+var_38.Size], 8
0x14001423d  mov     [rbp+57h+var_20], 2
0x140014245  mov     rax, [r9+18h]
0x140014249  mov     r9d, 3; UserDataCount
0x14001424f  mov     [rbp+57h+var_18], rax
0x140014253  mov     eax, ecx
0x140014255  add     eax, eax
0x140014257  mov     [rbp+57h+var_C], 0
0x14001425e  mov     [rbp+57h+var_10], eax
0x140014261  mov     rcx, r10; RegHandle
0x140014264  lea     rax, [rbp+57h+var_38]
0x140014268  mov     [rsp+0E0h+UserData], rax; UserData
0x14001426d  call    cs:__imp_EtwWrite
0x140014274  nop     dword ptr [rax+rax+00h]
0x140014279  jmp     loc_14001411A
0x14001427e  cmp     eax, 3
0x140014281  jnz     short loc_1400142A3
0x140014283  lea     rdx, FiEvt_FileNameDelete_Info
0x14001428a  jmp     short loc_140014219
0x14001428c  lea     rax, FIUnknown; "\\FI_UNKNOWN"
0x140014293  mov     dword ptr [rbp+57h+var_50], 0B0000h
0x14001429a  mov     qword ptr [rbp+57h+var_60+8], rax
0x14001429e  jmp     loc_1400140CF
0x1400142a3  cmp     eax, 6
0x1400142a6  jnz     loc_14001411A
0x1400142ac  lea     rdx, FiEvt_FileNameRundown_Info
0x1400142b3  jmp     loc_140014219
0x1400142b8  xor     r9d, r9d
0x1400142bb  mov     r8d, 420h
0x1400142c1  xor     ecx, ecx
0x1400142c3  jmp     loc_14001416B
```
