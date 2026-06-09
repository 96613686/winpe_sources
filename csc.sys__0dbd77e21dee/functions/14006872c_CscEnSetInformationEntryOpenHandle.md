# CscEnSetInformationEntryOpenHandle

- ea: `0x14006872c`
- end: `0x1400689e5`
- name: `CscEnSetInformationEntryOpenHandle`
- size: `697`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140001ed0`
- `0x140019548`

## callees

- `0x140005390`
- `0x140007420`
- `0x14001a494`
- `0x140028578`
- `0x14006872c`
- `0x1400691f8`
- `0x14007dc34`

## import_xrefs

- `ntoskrnl!RtlAssert` at `0x140068911`
- `ntoskrnl!RtlAssert` at `0x140068911`

## pseudocode

```c
__int64 __fastcall CscEnSetInformationEntryOpenHandle(
        __int64 a1,
        unsigned __int8 a2,
        int a3,
        int a4,
        __int64 a5,
        int *a6)
{
  int v6; // ebx
  int v7; // r15d
  __int64 v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // esi
  int v15; // r14d
  int v16; // edx
  int v17; // ebx
  int v18; // ebp
  int v20[4]; // [rsp+50h] [rbp-38h] BYREF
  char v21; // [rsp+A0h] [rbp+18h] BYREF

  v6 = 0;
  v7 = a2;
  v20[0] = 0;
  v21 = 0;
  v11 = a5;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
  {
    if ( a1 )
    {
      v12 = *(_QWORD *)(a1 + 8);
      v13 = *(unsigned int *)(a1 + 16);
    }
    else
    {
      v12 = 0;
      v13 = 0;
    }
    WPP_SF_qqDDdDq(WPP_GLOBAL_Control->AttachedDevice, v12, v13, a1, v12, v13, v7, a3, a4, a5);
  }
  if ( a3 != 4 && (unsigned int)(a3 - 19) >= 2 )
  {
    v14 = 2635;
    v15 = -1073741811;
    goto LABEL_39;
  }
  CscEnpMainAcquireExclusive(*(_QWORD *)(a1 + 8));
  if ( a3 == 4
    && !*(_DWORD *)(v11 + 32)
    && (unsigned __int64)(*(_QWORD *)v11 + 1LL) <= 1
    && (unsigned __int64)(*(_QWORD *)(v11 + 8) + 1LL) <= 1
    && (unsigned __int64)(*(_QWORD *)(v11 + 16) + 1LL) <= 1
    && (unsigned __int64)(*(_QWORD *)(v11 + 24) + 1LL) <= 1 )
  {
    v15 = 0;
LABEL_17:
    if ( *(_QWORD *)(v11 + 16) )
      *(_DWORD *)(a1 + 16) |= 0x20u;
    if ( *(_QWORD *)(v11 + 24) )
      *(_DWORD *)(a1 + 16) |= 0x10u;
    if ( *(_DWORD *)(v11 + 32)
      || (unsigned __int64)(*(_QWORD *)v11 + 1LL) > 1
      || (unsigned __int64)(*(_QWORD *)(v11 + 8) + 1LL) > 1
      || (unsigned __int64)(*(_QWORD *)(v11 + 16) + 1LL) > 1
      || (unsigned __int64)(*(_QWORD *)(v11 + 24) + 1LL) > 1 )
    {
      *(_DWORD *)(a1 + 16) |= 1u;
      if ( *(_QWORD *)(v11 + 16) )
        v17 = v6 | 0x30;
      else
        v17 = v6 | 0x20;
      CscEnpImplicitTimeUpdate(a1, v7, v20);
      v6 = v20[0] | v17;
    }
LABEL_37:
    v14 = 0;
    goto LABEL_38;
  }
  LOBYTE(v16) = v7;
  v15 = CscEnpSetLocalInformationEntryEx(*(_QWORD *)(a1 + 8), v16, a3, a4, v11, 3, (__int64)&v21, (__int64)v20);
  if ( v15 >= 0 )
  {
    v6 = v20[0];
    v18 = a3 - 4;
    if ( !v18 )
      goto LABEL_17;
    if ( (unsigned int)(v18 - 15) < 2 )
    {
      if ( !v21 )
      {
        *(_DWORD *)(a1 + 16) |= 3u;
        v20[0] = 0;
        CscEnpImplicitTimeUpdate(a1, v7, v20);
        v6 |= v20[0] | 0x38;
      }
      goto LABEL_37;
    }
    RtlAssert("0", "base\\fs\\remotefs\\rdr\\csc\\newdb\\entry_qsinfo.c", 0xAA5u, 0);
    v14 = 2727;
    v15 = -1073741811;
  }
  else
  {
    v14 = 2662;
  }
LABEL_38:
  CscEnpMainRelease(*(_QWORD *)(a1 + 8));
LABEL_39:
  if ( a6 )
    *a6 = v6;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_DDd(
      WPP_GLOBAL_Control->AttachedDevice,
      56,
      WPP_c7a60c7e3f883d3ed947201bd17678e0_Traceguids,
      *(unsigned int *)(a1 + 16),
      v15,
      v14);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14006872c  mov     rax, rsp
0x14006872f  mov     [rax+8], rbx
0x140068733  mov     [rax+10h], rbp
0x140068737  push    rsi
0x140068738  push    rdi
0x140068739  push    r13
0x14006873b  push    r14
0x14006873d  push    r15
0x14006873f  sub     rsp, 60h
0x140068743  xor     ebx, ebx
0x140068745  movzx   r15d, dl
0x140068749  mov     [rax-38h], ebx
0x14006874c  mov     r14d, r9d
0x14006874f  mov     ebp, r8d
0x140068752  mov     byte ptr [rax+18h], 0
0x140068756  mov     rdi, rcx
0x140068759  mov     rcx, cs:WPP_GLOBAL_Control
0x140068760  lea     r13, WPP_GLOBAL_Control
0x140068767  mov     rsi, [rsp+88h+arg_20]
0x14006876f  cmp     rcx, r13
0x140068772  jz      short loc_1400687BA
0x140068774  test    dword ptr [rcx+2Ch], 20000h
0x14006877b  jz      short loc_1400687BA
0x14006877d  test    rdi, rdi
0x140068780  jz      short loc_14006878C
0x140068782  mov     rdx, [rdi+8]
0x140068786  mov     r8d, [rdi+10h]
0x14006878a  jmp     short loc_140068791
0x14006878c  xor     edx, edx
0x14006878e  xor     r8d, r8d
0x140068791  mov     rcx, [rcx+18h]
0x140068795  mov     r9, rdi
0x140068798  mov     [rsp+88h+var_40], rsi
0x14006879d  mov     [rsp+88h+var_48], r14d
0x1400687a2  mov     dword ptr [rsp+88h+var_50], ebp
0x1400687a6  mov     dword ptr [rsp+88h+var_58], r15d
0x1400687ab  mov     [rsp+88h+var_60], r8d
0x1400687b0  mov     [rsp+88h+var_68], rdx
0x1400687b5  call    WPP_SF_qqDDdDq
0x1400687ba  mov     ecx, ebp
0x1400687bc  sub     ecx, 4
0x1400687bf  jz      short loc_1400687DB
0x1400687c1  sub     ecx, 0Fh
0x1400687c4  jz      short loc_1400687DB
0x1400687c6  cmp     ecx, 1
0x1400687c9  jz      short loc_1400687DB
0x1400687cb  mov     esi, 0A4Bh
0x1400687d0  mov     r14d, 0C000000Dh
0x1400687d6  jmp     loc_140068982
0x1400687db  mov     rcx, [rdi+8]
0x1400687df  call    CscEnpMainAcquireExclusive
0x1400687e4  mov     r13d, 1
0x1400687ea  cmp     ebp, 4
0x1400687ed  jnz     loc_14006889C
0x1400687f3  cmp     [rsi+20h], ebx
0x1400687f6  jnz     loc_14006889C
0x1400687fc  mov     rax, [rsi]
0x1400687ff  add     rax, r13
0x140068802  cmp     rax, r13
0x140068805  ja      loc_14006889C
0x14006880b  mov     rax, [rsi+8]
0x14006880f  add     rax, r13
0x140068812  cmp     rax, r13
0x140068815  ja      loc_14006889C
0x14006881b  mov     rax, [rsi+10h]
0x14006881f  add     rax, r13
0x140068822  cmp     rax, r13
0x140068825  ja      short loc_14006889C
0x140068827  mov     rax, [rsi+18h]
0x14006882b  add     rax, r13
0x14006882e  cmp     rax, r13
0x140068831  ja      short loc_14006889C
0x140068833  xor     r14d, r14d
0x140068836  cmp     qword ptr [rsi+10h], 0
0x14006883b  jz      short loc_140068841
0x14006883d  or      dword ptr [rdi+10h], 20h
0x140068841  cmp     qword ptr [rsi+18h], 0
0x140068846  jz      short loc_14006884C
0x140068848  or      dword ptr [rdi+10h], 10h
0x14006884c  cmp     dword ptr [rsi+20h], 0
0x140068850  jnz     short loc_140068885
0x140068852  mov     rax, [rsi]
0x140068855  add     rax, r13
0x140068858  cmp     rax, r13
0x14006885b  ja      short loc_140068885
0x14006885d  mov     rax, [rsi+8]
0x140068861  add     rax, r13
0x140068864  cmp     rax, r13
0x140068867  ja      short loc_140068885
0x140068869  mov     rax, [rsi+10h]
0x14006886d  add     rax, r13
0x140068870  cmp     rax, r13
0x140068873  ja      short loc_140068885
0x140068875  mov     rax, [rsi+18h]
0x140068879  add     rax, r13
0x14006887c  cmp     rax, r13
0x14006887f  jbe     loc_140068970
0x140068885  or      [rdi+10h], r13d
0x140068889  cmp     qword ptr [rsi+10h], 0
0x14006888e  jz      loc_140068959
0x140068894  or      ebx, 30h
0x140068897  jmp     loc_14006895C
0x14006889c  mov     rcx, [rdi+8]
0x1400688a0  lea     rax, [rsp+88h+var_38]
0x1400688a5  mov     [rsp+88h+var_50], rax
0x1400688aa  mov     r9d, r14d
0x1400688ad  lea     rax, [rsp+88h+arg_10]
0x1400688b5  mov     r8d, ebp
0x1400688b8  mov     [rsp+88h+var_58], rax
0x1400688bd  mov     dl, r15b
0x1400688c0  mov     [rsp+88h+var_60], 3
0x1400688c8  mov     [rsp+88h+var_68], rsi
0x1400688cd  call    CscEnpSetLocalInformationEntryEx
0x1400688d2  mov     r14d, eax
0x1400688d5  test    eax, eax
0x1400688d7  jns     short loc_1400688E3
0x1400688d9  mov     esi, 0A66h
0x1400688de  jmp     loc_140068972
0x1400688e3  mov     ebx, [rsp+88h+var_38]
0x1400688e7  sub     ebp, 4
0x1400688ea  jz      loc_140068836
0x1400688f0  sub     ebp, 0Fh
0x1400688f3  jz      short loc_14006892A
0x1400688f5  cmp     ebp, r13d
0x1400688f8  jz      short loc_14006892A
0x1400688fa  xor     r9d, r9d; MutableMessage
0x1400688fd  lea     rdx, aBaseFsRemotefs_4; "base\\fs\\remotefs\\rdr\\csc\\newdb\\en"...
0x140068904  mov     r8d, 0AA5h; LineNumber
0x14006890a  lea     rcx, a0; "0"
0x140068911  call    cs:__imp_RtlAssert
0x140068918  nop     dword ptr [rax+rax+00h]
0x14006891d  mov     esi, 0AA7h
0x140068922  mov     r14d, 0C000000Dh
0x140068928  jmp     short loc_140068972
0x14006892a  cmp     [rsp+88h+arg_10], 0
0x140068932  jnz     short loc_140068970
0x140068934  or      dword ptr [rdi+10h], 3
0x140068938  lea     r8, [rsp+88h+var_38]
0x14006893d  mov     dl, r15b
0x140068940  mov     [rsp+88h+var_38], 0
0x140068948  mov     rcx, rdi
0x14006894b  call    CscEnpImplicitTimeUpdate
0x140068950  or      ebx, [rsp+88h+var_38]
0x140068954  or      ebx, 38h
0x140068957  jmp     short loc_140068970
0x140068959  or      ebx, 20h
0x14006895c  lea     r8, [rsp+88h+var_38]
0x140068961  mov     dl, r15b
0x140068964  mov     rcx, rdi
0x140068967  call    CscEnpImplicitTimeUpdate
0x14006896c  or      ebx, [rsp+88h+var_38]
0x140068970  xor     esi, esi
0x140068972  mov     rcx, [rdi+8]
0x140068976  call    CscEnpMainRelease
0x14006897b  lea     r13, WPP_GLOBAL_Control
0x140068982  mov     rax, [rsp+88h+arg_28]
0x14006898a  test    rax, rax
0x14006898d  jz      short loc_140068991
0x14006898f  mov     [rax], ebx
0x140068991  mov     rcx, cs:WPP_GLOBAL_Control
0x140068998  cmp     rcx, r13
0x14006899b  jz      short loc_1400689C8
0x14006899d  test    dword ptr [rcx+2Ch], 20000h
0x1400689a4  jz      short loc_1400689C8
0x1400689a6  mov     r9d, [rdi+10h]
0x1400689aa  lea     r8, WPP_c7a60c7e3f883d3ed947201bd17678e0_Traceguids
0x1400689b1  mov     rcx, [rcx+18h]
0x1400689b5  mov     edx, 38h ; '8'
0x1400689ba  mov     [rsp+88h+var_60], esi
0x1400689be  mov     dword ptr [rsp+88h+var_68], r14d
0x1400689c3  call    WPP_SF_DDd
0x1400689c8  lea     r11, [rsp+88h+var_28]
0x1400689cd  mov     eax, r14d
0x1400689d0  mov     rbx, [r11+30h]
0x1400689d4  mov     rbp, [r11+38h]
0x1400689d8  mov     rsp, r11
0x1400689db  pop     r15
0x1400689dd  pop     r14
0x1400689df  pop     r13
0x1400689e1  pop     rdi
0x1400689e2  pop     rsi
0x1400689e3  retn
```
