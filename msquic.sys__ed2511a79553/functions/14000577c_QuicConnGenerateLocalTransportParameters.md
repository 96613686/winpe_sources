# QuicConnGenerateLocalTransportParameters

- ea: `0x14000577c`
- end: `0x140005a9b`
- name: `QuicConnGenerateLocalTransportParameters`
- size: `799`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000524c`
- `0x140043368`

## callees

- `0x14000577c`
- `0x140028658`
- `0x14002a180`
- `0x14002ab40`
- `0x1400337e4`
- `0x1400351a8`
- `0x14003cb00`
- `0x14003fdf8`

## string_xrefs

- `0x14000579c`: `Connection->Configuration != ((void *)0)`
- `0x1400059c5`: `QuicLibraryGenerateStatelessResetToken`

## pseudocode

```c
__int64 __fastcall QuicConnGenerateLocalTransportParameters(__int64 a1, __int64 a2)
{
  __int64 *v4; // r14
  __int64 v5; // rax
  int v6; // ecx
  char *v7; // rsi
  __int64 v8; // rax
  int v9; // eax
  int v10; // ecx
  int StatelessResetToken; // esi
  __int64 v13; // rdx
  int v14; // [rsp+50h] [rbp+8h] BYREF

  if ( !*(_QWORD *)(a1 + 88) )
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\connection.c", 2284, "Connection->Configuration != ((void *)0)");
  v4 = *(__int64 **)(a1 + 1280);
  *(_QWORD *)(a2 + 40) = *(_QWORD *)(a1 + 3448);
  *(_QWORD *)(a2 + 16) = *(unsigned int *)(a1 + 156);
  *(_QWORD *)(a2 + 24) = *(unsigned int *)(a1 + 160);
  *(_QWORD *)(a2 + 32) = *(unsigned int *)(a1 + 164);
  *(_QWORD *)(a2 + 64) = (unsigned __int16)(CxPlatSocketGetLocalMtu(*(_QWORD *)(*(_QWORD *)(a1 + 360) + 32LL), a1 + 368)
                                          - 28);
  *(_QWORD *)(a2 + 80) = QuicConnGetAckDelay(a1);
  if ( P && *((_DWORD *)P + 1) )
    v5 = 0;
  else
    v5 = 1000 * (unsigned int)(unsigned __int8)byte_14005C560;
  v6 = 1069135;
  *(_QWORD *)(a2 + 88) = v5;
  *(_DWORD *)a2 = 1069135;
  *(_QWORD *)(a2 + 96) = 4;
  if ( *(_QWORD *)(a1 + 128) )
  {
    v6 = 1071183;
    *(_DWORD *)a2 = 1071183;
    *(_QWORD *)(a2 + 8) = *(_QWORD *)(a1 + 128);
  }
  if ( *(_BYTE *)(a1 + 279) != 3 )
  {
    v6 |= 0x80u;
    *(_DWORD *)a2 = v6;
    *(_QWORD *)(a2 + 72) = *(unsigned __int8 *)(a1 + 279);
  }
  *(_DWORD *)a2 = v6 | 0x10000;
  *(_BYTE *)(a2 + 132) = *((_BYTE *)v4 + 17);
  memmove((void *)(a2 + 112), v4 + 4, *((unsigned __int8 *)v4 + 17));
  if ( (*(_BYTE *)(a1 + 235) & 8) != 0 )
  {
    *(_DWORD *)a2 |= 0x8000u;
    v7 = (char *)(a1 + 235);
    *(_QWORD *)(a2 + 104) = 0xFFFF;
  }
  else
  {
    v7 = (char *)(a1 + 235);
  }
  if ( (*(_BYTE *)(a1 + 249) & 0x10) != 0 )
    *(_DWORD *)a2 |= 0x40000u;
  else
    v7 = (char *)(a1 + 235);
  if ( *(_BYTE *)(a1 + 1312) )
  {
    *(_DWORD *)a2 |= 0x200000u;
    *(_QWORD *)(a2 + 136) = *(unsigned __int8 *)(a1 + 1312);
    *(_QWORD *)(a2 + 144) = *(unsigned __int8 *)(a1 + 1313);
  }
  if ( (*v7 & 0x40) != 0 )
  {
    v14 = 0;
    v8 = QuicVersionNegotiationExtEncodeVersionInfo(a1, &v14);
    *(_QWORD *)(a2 + 248) = v8;
    if ( v8 )
    {
      v9 = v14;
      *(_DWORD *)a2 |= 0x80000u;
      *(_DWORD *)(a2 + 240) = v9;
    }
    else
    {
      *(_DWORD *)(a2 + 240) = 0;
    }
  }
  if ( *v7 < 0 )
    *(_DWORD *)a2 |= 0x400000u;
  if ( (*(_BYTE *)(a1 + 236) & 8) != 0 )
    *(_DWORD *)a2 |= 0x800000u;
  if ( (*(_BYTE *)(a1 + 236) & 0x10) != 0 )
    *(_DWORD *)a2 |= 0x3000000u;
  if ( *(_DWORD *)a1 != 4 )
  {
    if ( *(_QWORD *)(a1 + 2056) )
    {
      *(_DWORD *)a2 |= 0x10u;
      *(_QWORD *)(a2 + 48) = *(_QWORD *)(a1 + 2056);
    }
    if ( *(_QWORD *)(a1 + 2104) )
    {
      *(_DWORD *)a2 |= 0x20u;
      *(_QWORD *)(a2 + 56) = *(_QWORD *)(a1 + 2104);
    }
    return 0;
  }
  if ( *(_QWORD *)(a1 + 2032) )
  {
    *(_DWORD *)a2 |= 0x10u;
    *(_QWORD *)(a2 + 48) = *(_QWORD *)(a1 + 2032);
  }
  if ( *(_QWORD *)(a1 + 2080) )
  {
    *(_DWORD *)a2 |= 0x20u;
    *(_QWORD *)(a2 + 56) = *(_QWORD *)(a1 + 2080);
  }
  if ( (*(_BYTE *)(a1 + 235) & 4) == 0 )
    *(_DWORD *)a2 |= 0x400u;
  *(_DWORD *)a2 |= 0x100u;
  StatelessResetToken = QuicLibraryGenerateStatelessResetToken(*(_QWORD *)(a1 + 72), v4 + 4, a2 + 152);
  if ( StatelessResetToken >= 0 )
  {
    if ( *(_QWORD *)(a1 + 1304) )
    {
      *(_DWORD *)a2 |= 0x2000u;
      *(_BYTE *)(a2 + 216) = *(_BYTE *)(*(_QWORD *)(a1 + 1304) + 1LL);
      memmove(
        (void *)(a2 + 196),
        (const void *)(*(_QWORD *)(a1 + 1304) + 16LL),
        *(unsigned __int8 *)(*(_QWORD *)(a1 + 1304) + 1LL));
      if ( (*(_BYTE *)(a1 + 250) & 1) != 0 )
      {
        v13 = *v4;
        *(_DWORD *)a2 |= 0x20000u;
        *(_BYTE *)(a2 + 237) = *(_BYTE *)(v13 + 17);
        memmove((void *)(a2 + 217), (const void *)(v13 + 32), *(unsigned __int8 *)(v13 + 17));
      }
    }
    return 0;
  }
  if ( (byte_14005C48B & 4) != 0 )
    McTemplateU0pqs_EtwWriteTransfer(
      v10,
      (unsigned int)QuicConnErrorStatus,
      a1,
      StatelessResetToken,
      (__int64)"QuicLibraryGenerateStatelessResetToken");
  return (unsigned int)StatelessResetToken;
}

```

## disassembly

```asm
0x14000577c  mov     [rsp+arg_8], rbx
0x140005781  mov     [rsp+arg_10], rbp
0x140005786  push    rsi
0x140005787  push    rdi
0x140005788  push    r14
0x14000578a  sub     rsp, 30h
0x14000578e  xor     ebp, ebp
0x140005790  mov     rbx, rdx
0x140005793  mov     rdi, rcx
0x140005796  cmp     [rcx+58h], rbp
0x14000579a  jnz     short loc_1400057B4
0x14000579c  lea     r8, aConnectionConf; "Connection->Configuration != ((void *)0"...
0x1400057a3  mov     edx, 8ECh
0x1400057a8  lea     rcx, aCW1SMsquicSrcC_0; "C:\\__w\\1\\s\\msquic\\src\\core\\conne"...
0x1400057af  call    CxPlatLogAssert
0x1400057b4  mov     rax, [rdi+0D78h]
0x1400057bb  lea     rdx, [rdi+170h]
0x1400057c2  mov     r14, [rdi+500h]
0x1400057c9  mov     [rbx+28h], rax
0x1400057cd  mov     eax, [rdi+9Ch]
0x1400057d3  mov     [rbx+10h], rax
0x1400057d7  mov     eax, [rdi+0A0h]
0x1400057dd  mov     [rbx+18h], rax
0x1400057e1  mov     eax, [rdi+0A4h]
0x1400057e7  mov     [rbx+20h], rax
0x1400057eb  mov     rcx, [rdi+168h]
0x1400057f2  mov     rcx, [rcx+20h]
0x1400057f6  call    CxPlatSocketGetLocalMtu
0x1400057fb  sub     ax, 1Ch
0x1400057ff  mov     rcx, rdi
0x140005802  movzx   eax, ax
0x140005805  mov     [rbx+40h], rax
0x140005809  call    QuicConnGetAckDelay
0x14000580e  mov     [rbx+50h], rax
0x140005812  mov     rax, cs:P
0x140005819  test    rax, rax
0x14000581c  jz      short loc_140005827
0x14000581e  cmp     [rax+4], ebp
0x140005821  jz      short loc_140005827
0x140005823  mov     eax, ebp
0x140005825  jmp     short loc_140005834
0x140005827  movzx   eax, cs:byte_14005C560
0x14000582e  imul    eax, 3E8h
0x140005834  mov     ecx, 10504Fh
0x140005839  mov     [rbx+58h], rax
0x14000583d  mov     [rbx], ecx
0x14000583f  mov     qword ptr [rbx+60h], 4
0x140005847  cmp     [rdi+80h], rbp
0x14000584e  jz      short loc_140005862
0x140005850  mov     ecx, 10584Fh
0x140005855  mov     [rbx], ecx
0x140005857  mov     rax, [rdi+80h]
0x14000585e  mov     [rbx+8], rax
0x140005862  cmp     byte ptr [rdi+117h], 3
0x140005869  jz      short loc_14000587C
0x14000586b  bts     ecx, 7
0x14000586f  mov     [rbx], ecx
0x140005871  movzx   eax, byte ptr [rdi+117h]
0x140005878  mov     [rbx+48h], rax
0x14000587c  bts     ecx, 10h
0x140005880  lea     rdx, [r14+20h]; Src
0x140005884  mov     [rbx], ecx
0x140005886  lea     rcx, [rbx+70h]; void *
0x14000588a  mov     al, [r14+11h]
0x14000588e  mov     [rbx+84h], al
0x140005894  movzx   r8d, byte ptr [r14+11h]; Size
0x140005899  call    memmove
0x14000589e  lea     rcx, [rdi+0EBh]
0x1400058a5  test    byte ptr [rcx], 8
0x1400058a8  jz      short loc_1400058BF
0x1400058aa  bts     dword ptr [rbx], 0Fh
0x1400058ae  lea     rsi, [rdi+0EBh]
0x1400058b5  mov     qword ptr [rbx+68h], 0FFFFh
0x1400058bd  jmp     short loc_1400058C2
0x1400058bf  mov     rsi, rcx
0x1400058c2  test    byte ptr [rdi+0F9h], 10h
0x1400058c9  jz      short loc_1400058D1
0x1400058cb  bts     dword ptr [rbx], 12h
0x1400058cf  jmp     short loc_1400058D4
0x1400058d1  mov     rsi, rcx
0x1400058d4  cmp     [rdi+520h], bpl
0x1400058db  jz      short loc_1400058FD
0x1400058dd  bts     dword ptr [rbx], 15h
0x1400058e1  movzx   eax, byte ptr [rdi+520h]
0x1400058e8  mov     [rbx+88h], rax
0x1400058ef  movzx   eax, byte ptr [rdi+521h]
0x1400058f6  mov     [rbx+90h], rax
0x1400058fd  test    byte ptr [rsi], 40h
0x140005900  jz      short loc_140005935
0x140005902  lea     rdx, [rsp+48h+arg_0]
0x140005907  mov     [rsp+48h+arg_0], ebp
0x14000590b  mov     rcx, rdi
0x14000590e  call    QuicVersionNegotiationExtEncodeVersionInfo
0x140005913  mov     [rbx+0F8h], rax
0x14000591a  test    rax, rax
0x14000591d  jz      short loc_14000592F
0x14000591f  mov     eax, [rsp+48h+arg_0]
0x140005923  bts     dword ptr [rbx], 13h
0x140005927  mov     [rbx+0F0h], eax
0x14000592d  jmp     short loc_140005935
0x14000592f  mov     [rbx+0F0h], ebp
0x140005935  cmp     [rsi], bpl
0x140005938  jge     short loc_14000593E
0x14000593a  bts     dword ptr [rbx], 16h
0x14000593e  test    byte ptr [rdi+0ECh], 8
0x140005945  jz      short loc_14000594B
0x140005947  bts     dword ptr [rbx], 17h
0x14000594b  test    byte ptr [rdi+0ECh], 10h
0x140005952  jz      short loc_14000595A
0x140005954  or      dword ptr [rbx], 3000000h
0x14000595a  cmp     dword ptr [rdi], 4
0x14000595d  jnz     loc_140005A57
0x140005963  cmp     [rdi+7F0h], rbp
0x14000596a  jz      short loc_14000597A
0x14000596c  or      dword ptr [rbx], 10h
0x14000596f  mov     rax, [rdi+7F0h]
0x140005976  mov     [rbx+30h], rax
0x14000597a  cmp     [rdi+820h], rbp
0x140005981  jz      short loc_140005991
0x140005983  or      dword ptr [rbx], 20h
0x140005986  mov     rax, [rdi+820h]
0x14000598d  mov     [rbx+38h], rax
0x140005991  test    byte ptr [rdi+0EBh], 4
0x140005998  jnz     short loc_14000599E
0x14000599a  bts     dword ptr [rbx], 0Ah
0x14000599e  bts     dword ptr [rbx], 8
0x1400059a2  lea     r8, [rbx+98h]
0x1400059a9  mov     rcx, [rdi+48h]
0x1400059ad  lea     rdx, [r14+20h]
0x1400059b1  call    QuicLibraryGenerateStatelessResetToken
0x1400059b6  mov     esi, eax
0x1400059b8  test    eax, eax
0x1400059ba  jns     short loc_1400059EA
0x1400059bc  test    cs:byte_14005C48B, 4
0x1400059c3  jz      short loc_1400059E3
0x1400059c5  lea     rax, aQuiclibrarygen; "QuicLibraryGenerateStatelessResetToken"
0x1400059cc  mov     r9d, esi
0x1400059cf  mov     r8, rdi
0x1400059d2  mov     [rsp+48h+var_28], rax
0x1400059d7  lea     rdx, QuicConnErrorStatus
0x1400059de  call    McTemplateU0pqs_EtwWriteTransfer
0x1400059e3  mov     eax, esi
0x1400059e5  jmp     loc_140005A87
0x1400059ea  cmp     [rdi+518h], rbp
0x1400059f1  jz      loc_140005A85
0x1400059f7  bts     dword ptr [rbx], 0Dh
0x1400059fb  mov     rax, [rdi+518h]
0x140005a02  mov     cl, [rax+1]
0x140005a05  mov     [rbx+0D8h], cl
0x140005a0b  lea     rcx, [rbx+0C4h]; void *
0x140005a12  mov     rdx, [rdi+518h]
0x140005a19  movzx   r8d, byte ptr [rdx+1]; Size
0x140005a1e  add     rdx, 10h; Src
0x140005a22  call    memmove
0x140005a27  test    byte ptr [rdi+0FAh], 1
0x140005a2e  jz      short loc_140005A85
0x140005a30  mov     rdx, [r14]
0x140005a33  lea     rcx, [rbx+0D9h]; void *
0x140005a3a  bts     dword ptr [rbx], 11h
0x140005a3e  mov     al, [rdx+11h]
0x140005a41  mov     [rbx+0EDh], al
0x140005a47  movzx   r8d, byte ptr [rdx+11h]; Size
0x140005a4c  add     rdx, 20h ; ' '; Src
0x140005a50  call    memmove
0x140005a55  jmp     short loc_140005A85
0x140005a57  cmp     [rdi+808h], rbp
0x140005a5e  jz      short loc_140005A6E
0x140005a60  or      dword ptr [rbx], 10h
0x140005a63  mov     rax, [rdi+808h]
0x140005a6a  mov     [rbx+30h], rax
0x140005a6e  cmp     [rdi+838h], rbp
0x140005a75  jz      short loc_140005A85
0x140005a77  or      dword ptr [rbx], 20h
0x140005a7a  mov     rax, [rdi+838h]
0x140005a81  mov     [rbx+38h], rax
0x140005a85  xor     eax, eax
0x140005a87  mov     rbx, [rsp+48h+arg_8]
0x140005a8c  mov     rbp, [rsp+48h+arg_10]
0x140005a91  add     rsp, 30h
0x140005a95  pop     r14
0x140005a97  pop     rdi
0x140005a98  pop     rsi
0x140005a99  retn
```
