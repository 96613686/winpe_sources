# RxpInitializeCreateContext

- ea: `0x14000a830`
- end: `0x14000abe9`
- name: `RxpInitializeCreateContext`
- size: `953`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140053400`

## callees

- `0x14000a830`
- `0x14000abf0`
- `0x14000b0d0`
- `0x140017280`
- `0x140017370`
- `0x140025d80`
- `0x1400265a0`

## import_xrefs

- `ntoskrnl!IoIsFileObjectIgnoringSharing` at `0x14000a8b9`
- `ntoskrnl!IoIsFileObjectIgnoringSharing` at `0x14000a8b9`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x14000aa30`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x14000aa30`
- `ntoskrnl!PsIsHostSilo` at `0x14000aa42`
- `ntoskrnl!PsIsHostSilo` at `0x14000aa42`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14000aa64`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14000aa64`
- `ntoskrnl!IoGetSiloParameters` at `0x14000a88a`
- `ntoskrnl!IoGetSiloParameters` at `0x14000a88a`

## pseudocode

```c
__int64 __fastcall RxpInitializeCreateContext(__int64 a1)
{
  __int64 v2; // rsi
  char v3; // bp
  __int64 v4; // rdi
  __int64 v5; // rax
  __int64 SiloParameters; // rax
  __int64 v7; // rax
  int v8; // eax
  __int64 result; // rax
  __int64 v10; // rcx
  int v11; // esi
  unsigned int *v12; // rdi
  _DWORD *v13; // r14
  int v14; // r15d
  __int64 v15; // rax
  int v16; // esi
  unsigned int *v17; // rdi
  _DWORD *v18; // r15
  int v19; // r14d
  __int64 v20; // rax
  int v21; // esi
  unsigned int *v22; // rdi
  _DWORD *v23; // r15
  int v24; // r14d
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 EffectiveServerSilo; // r14
  __int64 v28; // rax
  int v29; // ecx
  int v30; // esi
  int v31; // esi
  __int64 v32; // [rsp+60h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 40);
  v3 = 0;
  v4 = *(_QWORD *)(v2 + 184);
  RxpCopyCreateParameters(a1);
  v5 = *(_QWORD *)(a1 + 80);
  *(_QWORD *)(a1 + 600) = 0;
  if ( (*(_DWORD *)(v5 + 336) & 0x2000) != 0 )
  {
    SiloParameters = IoGetSiloParameters(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 184LL) + 48LL));
    v32 = 0;
    if ( SiloParameters
      && (v26 = *(_QWORD *)(SiloParameters + 8)) != 0
      && (EffectiveServerSilo = PsGetEffectiveServerSilo(v26), !(unsigned __int8)PsIsHostSilo(EffectiveServerSilo))
      && (int)PsGetPermanentSiloContext(EffectiveServerSilo, (unsigned int)g_RxSiloContextSlot, &v32) >= 0 )
    {
      v28 = v32;
      *(_QWORD *)(a1 + 840) = v32;
      if ( v28 )
      {
        v7 = *(_QWORD *)(v28 + 40);
        goto LABEL_5;
      }
    }
    else
    {
      *(_QWORD *)(a1 + 840) = 0;
    }
    v7 = 0;
LABEL_5:
    *(_QWORD *)(a1 + 624) = v7;
  }
  if ( IoIsFileObjectIgnoringSharing(*(PFILE_OBJECT *)(v4 + 48)) )
    *(_WORD *)(a1 + 746) |= 0x20u;
  v8 = *(_DWORD *)(v4 + 32);
  *(_DWORD *)(a1 + 712) = v8;
  *(_QWORD *)(a1 + 696) = 0;
  if ( v8 )
  {
    *(_QWORD *)(a1 + 696) = *(_QWORD *)(v2 + 24);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
        *(_QWORD *)(v2 + 24));
    }
    v11 = *(_DWORD *)(a1 + 712);
    if ( v11 )
    {
      v12 = *(unsigned int **)(a1 + 696);
      v13 = 0;
      v14 = 0;
      while ( *((_BYTE *)v12 + 5) != 28 || memcmp(v12 + 2, "ClusteredApplicationInstance", 0x1Cu) )
      {
        v15 = *v12;
        if ( !(_DWORD)v15 )
          goto LABEL_23;
        v14 += v15;
        v13 = v12;
        v12 = (unsigned int *)((char *)v12 + v15);
      }
      if ( *v12 )
      {
        v30 = v11 - *v12;
        *(_DWORD *)(a1 + 712) = v30;
        memmove(v12, (char *)v12 + *v12, (unsigned int)(v30 - v14));
      }
      else
      {
        *(_DWORD *)(a1 + 712) = v14;
        if ( v13 )
          *v13 = 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids);
      }
    }
LABEL_23:
    v16 = *(_DWORD *)(a1 + 712);
    if ( v16 )
    {
      v17 = *(unsigned int **)(a1 + 696);
      v18 = 0;
      v19 = 0;
      while ( *((_BYTE *)v17 + 5) != 22 || memcmp(v17 + 2, "ApplicationTrafficType", 0x16u) )
      {
        v20 = *v17;
        if ( !(_DWORD)v20 )
          goto LABEL_27;
        v19 += v20;
        v18 = v17;
        v17 = (unsigned int *)((char *)v17 + v20);
      }
      if ( *v17 )
      {
        v31 = v16 - *v17;
        *(_DWORD *)(a1 + 712) = v31;
        memmove(v17, (char *)v17 + *v17, (unsigned int)(v31 - v19));
      }
      else
      {
        *(_DWORD *)(a1 + 712) = v19;
        if ( v18 )
          *v18 = 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids);
      }
    }
LABEL_27:
    v21 = *(_DWORD *)(a1 + 712);
    if ( v21 )
    {
      v22 = *(unsigned int **)(a1 + 696);
      v23 = 0;
      v24 = 0;
      while ( *((_BYTE *)v22 + 5) != 26 || memcmp(v22 + 2, "SmbDisableHandleDurability", 0x1Au) )
      {
        v25 = *v22;
        if ( !(_DWORD)v25 )
          goto LABEL_9;
        v24 += v25;
        v23 = v22;
        v22 = (unsigned int *)((char *)v22 + v25);
      }
      v29 = *v22;
      if ( *v22 )
      {
        *(_DWORD *)(a1 + 712) = v21 - v29;
        memmove(v22, (char *)v22 + *v22, (unsigned int)(v21 - v29 - v24));
      }
      else
      {
        *(_DWORD *)(a1 + 712) = v24;
        if ( v23 )
          *v23 = 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids);
      }
      v3 = 1;
    }
  }
LABEL_9:
  result = RxProcessEcps(a1);
  if ( (int)result >= 0 )
  {
    if ( v3 )
      *(_DWORD *)(*(_QWORD *)(a1 + 672) + 12LL) |= 2u;
    if ( Fcb )
    {
      v10 = *(_QWORD *)(a1 + 672);
      if ( *(_DWORD *)(v10 + 8) > 1u || (*(_DWORD *)(v10 + 12) & 8) != 0 )
        *(_BYTE *)(a1 + 750) |= 4u;
      return (unsigned int)result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000a830  push    rbx
0x14000a832  push    rbp
0x14000a833  sub     rsp, 48h
0x14000a837  mov     [rsp+58h+arg_8], rsi
0x14000a83c  mov     rbx, rcx
0x14000a83f  mov     rsi, [rcx+28h]
0x14000a843  xor     bpl, bpl
0x14000a846  mov     [rsp+58h+arg_10], rdi
0x14000a84b  mov     [rsp+58h+arg_18], r12
0x14000a850  mov     [rsp+58h+var_20], r14
0x14000a855  mov     rdi, [rsi+0B8h]
0x14000a85c  call    RxpCopyCreateParameters
0x14000a861  mov     rax, [rbx+50h]
0x14000a865  xor     r12d, r12d
0x14000a868  mov     [rbx+258h], r12
0x14000a86f  test    dword ptr [rax+150h], 2000h
0x14000a879  jz      short loc_14000A8B5
0x14000a87b  mov     rax, [rbx+28h]
0x14000a87f  mov     rcx, [rax+0B8h]
0x14000a886  mov     rcx, [rcx+30h]
0x14000a88a  call    cs:__imp_IoGetSiloParameters
0x14000a891  nop     dword ptr [rax+rax+00h]
0x14000a896  mov     [rsp+58h+arg_0], r12
0x14000a89b  test    rax, rax
0x14000a89e  jnz     loc_14000AA23
0x14000a8a4  mov     [rbx+348h], r12
0x14000a8ab  mov     rax, r12
0x14000a8ae  mov     [rbx+270h], rax
0x14000a8b5  mov     rcx, [rdi+30h]; FileObject
0x14000a8b9  call    cs:__imp_IoIsFileObjectIgnoringSharing
0x14000a8c0  nop     dword ptr [rax+rax+00h]
0x14000a8c5  test    al, al
0x14000a8c7  jnz     loc_14000AA96
0x14000a8cd  mov     eax, [rdi+20h]
0x14000a8d0  mov     [rbx+2C8h], eax
0x14000a8d6  mov     [rbx+2B8h], r12
0x14000a8dd  test    eax, eax
0x14000a8df  jnz     short loc_14000A93C
0x14000a8e1  mov     rcx, rbx
0x14000a8e4  call    RxProcessEcps
0x14000a8e9  mov     r14, [rsp+58h+var_20]
0x14000a8ee  mov     edx, eax
0x14000a8f0  mov     r12, [rsp+58h+arg_18]
0x14000a8f5  mov     rdi, [rsp+58h+arg_10]
0x14000a8fa  mov     rsi, [rsp+58h+arg_8]
0x14000a8ff  test    eax, eax
0x14000a901  js      short loc_14000A934
0x14000a903  test    bpl, bpl
0x14000a906  jnz     loc_14000ABD9
0x14000a90c  cmp     cs:Fcb, 0
0x14000a914  jz      short loc_14000A934
0x14000a916  mov     rcx, [rbx+2A0h]
0x14000a91d  cmp     dword ptr [rcx+8], 1
0x14000a921  ja      loc_14000A9F3
0x14000a927  mov     eax, [rcx+0Ch]
0x14000a92a  test    al, 8
0x14000a92c  jnz     loc_14000A9F3
0x14000a932  mov     eax, edx
0x14000a934  add     rsp, 48h
0x14000a938  pop     rbp
0x14000a939  pop     rbx
0x14000a93a  retn
0x14000a93c  mov     rax, [rsi+18h]
0x14000a940  mov     [rbx+2B8h], rax
0x14000a947  mov     [rsp+58h+var_18], r13
0x14000a94c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a953  lea     r13, WPP_GLOBAL_Control
0x14000a95a  cmp     rcx, r13
0x14000a95d  jz      short loc_14000A96A
0x14000a95f  mov     eax, [rcx+2Ch]
0x14000a962  test    al, 8
0x14000a964  jnz     loc_14000AABB
0x14000a96a  mov     esi, [rbx+2C8h]
0x14000a970  mov     [rsp+58h+var_28], r15
0x14000a975  test    esi, esi
0x14000a977  jz      short loc_14000A996
0x14000a979  mov     rdi, [rbx+2B8h]
0x14000a980  mov     r14, r12
0x14000a983  mov     r15d, r12d
0x14000a986  cmp     byte ptr [rdi+5], 1Ch
0x14000a98a  jz      loc_14000AAEA
0x14000a990  mov     eax, [rdi]
0x14000a992  test    eax, eax
0x14000a994  jnz     short loc_14000A9FF
0x14000a996  mov     esi, [rbx+2C8h]
0x14000a99c  test    esi, esi
0x14000a99e  jz      short loc_14000A9BD
0x14000a9a0  mov     rdi, [rbx+2B8h]
0x14000a9a7  mov     r15, r12
0x14000a9aa  mov     r14d, r12d
0x14000a9ad  cmp     byte ptr [rdi+5], 16h
0x14000a9b1  jz      loc_14000AB2A
0x14000a9b7  mov     eax, [rdi]
0x14000a9b9  test    eax, eax
0x14000a9bb  jnz     short loc_14000AA0D
0x14000a9bd  mov     esi, [rbx+2C8h]
0x14000a9c3  test    esi, esi
0x14000a9c5  jz      short loc_14000A9E4
0x14000a9c7  mov     rdi, [rbx+2B8h]
0x14000a9ce  mov     r15, r12
0x14000a9d1  mov     r14d, r12d
0x14000a9d4  cmp     byte ptr [rdi+5], 1Ah
0x14000a9d8  jz      loc_14000AB6A
0x14000a9de  mov     eax, [rdi]
0x14000a9e0  test    eax, eax
0x14000a9e2  jnz     short loc_14000AA18
0x14000a9e4  mov     r15, [rsp+58h+var_28]
0x14000a9e9  mov     r13, [rsp+58h+var_18]
0x14000a9ee  jmp     loc_14000A8E1
0x14000a9f3  or      byte ptr [rbx+2EEh], 4
0x14000a9fa  jmp     loc_14000A932
0x14000a9ff  add     r15d, eax
0x14000aa02  mov     r14, rdi
0x14000aa05  add     rdi, rax
0x14000aa08  jmp     loc_14000A986
0x14000aa0d  add     r14d, eax
0x14000aa10  mov     r15, rdi
0x14000aa13  add     rdi, rax
0x14000aa16  jmp     short loc_14000A9AD
0x14000aa18  add     r14d, eax
0x14000aa1b  mov     r15, rdi
0x14000aa1e  add     rdi, rax
0x14000aa21  jmp     short loc_14000A9D4
0x14000aa23  mov     rcx, [rax+8]
0x14000aa27  test    rcx, rcx
0x14000aa2a  jz      loc_14000A8A4
0x14000aa30  call    cs:__imp_PsGetEffectiveServerSilo
0x14000aa37  nop     dword ptr [rax+rax+00h]
0x14000aa3c  mov     rcx, rax
0x14000aa3f  mov     r14, rax
0x14000aa42  call    cs:__imp_PsIsHostSilo
0x14000aa49  nop     dword ptr [rax+rax+00h]
0x14000aa4e  test    al, al
0x14000aa50  jnz     loc_14000A8A4
0x14000aa56  mov     edx, cs:g_RxSiloContextSlot
0x14000aa5c  lea     r8, [rsp+58h+arg_0]
0x14000aa61  mov     rcx, r14
0x14000aa64  call    cs:__imp_PsGetPermanentSiloContext
0x14000aa6b  nop     dword ptr [rax+rax+00h]
0x14000aa70  test    eax, eax
0x14000aa72  js      loc_14000A8A4
0x14000aa78  mov     rax, [rsp+58h+arg_0]
0x14000aa7d  mov     [rbx+348h], rax
0x14000aa84  test    rax, rax
0x14000aa87  jz      loc_14000A8AB
0x14000aa8d  mov     rax, [rax+28h]
0x14000aa91  jmp     loc_14000A8AE
0x14000aa96  or      word ptr [rbx+2EAh], 20h
0x14000aa9e  jmp     loc_14000A8CD
0x14000aaa3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aaaa  cmp     rcx, r13
0x14000aaad  jnz     loc_14000ABAA
0x14000aab3  mov     bpl, 1
0x14000aab6  jmp     loc_14000A9E4
0x14000aabb  cmp     byte ptr [rcx+29h], 4
0x14000aabf  jb      loc_14000A96A
0x14000aac5  mov     eax, [rdi+20h]
0x14000aac8  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x14000aacf  mov     r9, [rsi+18h]
0x14000aad3  mov     edx, 0Ah
0x14000aad8  mov     rcx, [rcx+18h]
0x14000aadc  mov     [rsp+58h+var_38], eax
0x14000aae0  call    WPP_SF_qD
0x14000aae5  jmp     loc_14000A96A
0x14000aaea  lea     rcx, [rdi+8]; Buf1
0x14000aaee  mov     r8d, 1Ch; Size
0x14000aaf4  lea     rdx, aClusteredappli; "ClusteredApplicationInstance"
0x14000aafb  call    memcmp
0x14000ab00  test    eax, eax
0x14000ab02  jnz     loc_14000A990
0x14000ab08  mov     eax, [rdi]
0x14000ab0a  test    eax, eax
0x14000ab0c  jnz     loc_140027386
0x14000ab12  mov     [rbx+2C8h], r15d
0x14000ab19  test    r14, r14
0x14000ab1c  jz      loc_1400273A1
0x14000ab22  mov     [r14], r12d
0x14000ab25  jmp     loc_1400273A1
0x14000ab2a  lea     rcx, [rdi+8]; Buf1
0x14000ab2e  mov     r8d, 16h; Size
0x14000ab34  lea     rdx, aApplicationtra; "ApplicationTrafficType"
0x14000ab3b  call    memcmp
0x14000ab40  test    eax, eax
0x14000ab42  jnz     loc_14000A9B7
0x14000ab48  mov     eax, [rdi]
0x14000ab4a  test    eax, eax
0x14000ab4c  jnz     loc_1400273E1
0x14000ab52  mov     [rbx+2C8h], r14d
0x14000ab59  test    r15, r15
0x14000ab5c  jz      loc_1400273FC
0x14000ab62  mov     [r15], r12d
0x14000ab65  jmp     loc_1400273FC
0x14000ab6a  lea     rcx, [rdi+8]; Buf1
0x14000ab6e  mov     r8d, 1Ah; Size
0x14000ab74  lea     rdx, aSmbdisablehand; "SmbDisableHandleDurability"
0x14000ab7b  call    memcmp
0x14000ab80  test    eax, eax
0x14000ab82  jnz     loc_14000A9DE
0x14000ab88  mov     ecx, [rdi]
0x14000ab8a  test    ecx, ecx
0x14000ab8c  jnz     loc_14002743C
0x14000ab92  mov     [rbx+2C8h], r14d
0x14000ab99  test    r15, r15
0x14000ab9c  jz      loc_14000AAA3
0x14000aba2  mov     [r15], r12d
0x14000aba5  jmp     loc_14000AAA3
0x14000abaa  mov     eax, [rcx+2Ch]
0x14000abad  test    al, 8
0x14000abaf  jz      loc_14000AAB3
0x14000abb5  cmp     byte ptr [rcx+29h], 2
0x14000abb9  jb      loc_14000AAB3
0x14000abbf  mov     rcx, [rcx+18h]
0x14000abc3  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x14000abca  mov     edx, 0Dh
0x14000abcf  call    WPP_SF_
0x14000abd4  jmp     loc_14000AAB3
0x14000abd9  mov     rcx, [rbx+2A0h]
0x14000abe0  or      dword ptr [rcx+0Ch], 2
0x14000abe4  jmp     loc_14000A90C
0x140027386  sub     esi, eax
0x140027388  mov     rcx, rdi; void *
0x14002738b  mov     [rbx+2C8h], esi
0x140027391  sub     esi, r15d
0x140027394  mov     edx, [rdi]
0x140027396  mov     r8d, esi; Size
0x140027399  add     rdx, rdi; Src
0x14002739c  call    memmove
0x1400273a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400273a8  cmp     rcx, r13
0x1400273ab  jz      loc_14000A996
0x1400273b1  mov     eax, [rcx+2Ch]
0x1400273b4  test    al, 8
0x1400273b6  jz      loc_14000A996
0x1400273bc  cmp     byte ptr [rcx+29h], 2
0x1400273c0  jb      loc_14000A996
0x1400273c6  mov     rcx, [rcx+18h]
0x1400273ca  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x1400273d1  mov     edx, 0Bh
0x1400273d6  call    WPP_SF_
0x1400273db  nop
0x1400273dc  jmp     loc_14000A996
0x1400273e1  sub     esi, eax
0x1400273e3  mov     rcx, rdi; void *
0x1400273e6  mov     [rbx+2C8h], esi
0x1400273ec  sub     esi, r14d
0x1400273ef  mov     edx, [rdi]
0x1400273f1  mov     r8d, esi; Size
0x1400273f4  add     rdx, rdi; Src
0x1400273f7  call    memmove
0x1400273fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140027403  cmp     rcx, r13
0x140027406  jz      loc_14000A9BD
0x14002740c  mov     eax, [rcx+2Ch]
0x14002740f  test    al, 8
0x140027411  jz      loc_14000A9BD
0x140027417  cmp     byte ptr [rcx+29h], 2
0x14002741b  jb      loc_14000A9BD
0x140027421  mov     rcx, [rcx+18h]
0x140027425  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x14002742c  mov     edx, 0Ch
0x140027431  call    WPP_SF_
0x140027436  nop
0x140027437  jmp     loc_14000A9BD
0x14002743c  mov     eax, esi
0x14002743e  sub     esi, ecx
0x140027440  sub     eax, ecx
0x140027442  sub     esi, r14d
0x140027445  mov     [rbx+2C8h], eax
0x14002744b  mov     rcx, rdi; void *
0x14002744e  mov     edx, [rdi]
0x140027450  add     rdx, rdi; Src
0x140027453  mov     r8d, esi; Size
0x140027456  call    memmove
0x14002745b  nop
0x14002745c  jmp     loc_14000AAA3
```
