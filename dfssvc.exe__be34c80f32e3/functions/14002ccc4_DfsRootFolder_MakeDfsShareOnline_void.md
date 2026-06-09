# DfsRootFolder::MakeDfsShareOnline(void)

- ea: `0x14002ccc4`
- end: `0x14002ced4`
- name: `?MakeDfsShareOnline@DfsRootFolder@@QEAAKXZ`
- size: `528`
- prototype: `unsigned int __fastcall(DfsRootFolder *__hidden this)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000b040`
- `0x14000c2bc`
- `0x140021460`
- `0x140021e40`
- `0x140044df0`
- `0x140045478`

## callees

- `0x140006bf0`
- `0x1400097f8`
- `0x14000b934`
- `0x140015f64`
- `0x1400162c8`
- `0x14002ccc4`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x14002cdec`
- `ntdll!RtlCompareUnicodeString` at `0x14002cdec`

## pseudocode

```c
__int64 __fastcall DfsRootFolder::MakeDfsShareOnline(unsigned __int64 this, __int64 a2, unsigned __int8 a3)
{
  UNICODE_STRING *v3; // rbp
  struct _UNICODE_STRING *v4; // r14
  DfsRootFolder *v5; // rbx
  int v6; // eax
  unsigned int v7; // edi
  struct _UNICODE_STRING *v9; // r15
  struct _UNICODE_STRING *v10; // rcx
  unsigned __int8 v11; // r8
  unsigned int v12; // r9d
  unsigned int v13; // ecx
  unsigned __int16 *v14[5]; // [rsp+30h] [rbp-28h] BYREF

  v3 = (UNICODE_STRING *)(this + 152);
  v14[1] = 0;
  v4 = (struct _UNICODE_STRING *)(this + 296);
  v5 = (DfsRootFolder *)this;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    this = (unsigned __int64)pWppControl;
    if ( pWppControl )
    {
      if ( (pWppControl[7] & 0x20) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
        WPP_SF_qZ(
          *((_QWORD *)pWppControl + 2),
          35,
          (unsigned int)WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids,
          (_DWORD)v5,
          (__int64)v3);
    }
  }
  v6 = *((_DWORD *)v5 + 68);
  if ( (v6 & 0x20) != 0 )
  {
    if ( (v6 & 0x40) != 0 )
      return 0;
    v9 = (struct _UNICODE_STRING *)((char *)v5 + 280);
    v10 = (struct _UNICODE_STRING *)((char *)v5 + 280);
    if ( *((_BYTE *)v5 + 216) != 1 )
      v10 = 0;
    v7 = DfsSetDfsNamespaceState(v10, v3, a3);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( pWppControl )
      {
        this = -v7;
        if ( (((1 << (v7 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
          WPP_SF_qZD(
            *((_QWORD *)pWppControl + 2),
            36,
            (unsigned int)WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids,
            (_DWORD)v5,
            (__int64)v3,
            v7);
      }
    }
    if ( !v7 )
    {
      if ( !RtlCompareUnicodeString(v3, v4, 1u) )
        goto LABEL_27;
      if ( *((_BYTE *)v5 + 216) != 1 )
        v9 = 0;
      v7 = DfsSetDfsNamespaceState(v9, v4, v11);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        this = (unsigned __int64)pWppControl;
        if ( pWppControl )
        {
          if ( (((1 << (v7 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
            WPP_SF_qZD(
              *((_QWORD *)pWppControl + 2),
              37,
              (unsigned int)WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids,
              (_DWORD)v5,
              (__int64)v4,
              v7);
        }
      }
      if ( !v7 )
LABEL_27:
        *((_DWORD *)v5 + 68) |= 0x40u;
    }
  }
  else
  {
    v7 = *((_DWORD *)v5 + 61);
  }
  v14[0] = *((unsigned __int16 **)v5 + 20);
  if ( v7 )
  {
    v12 = v7;
    v13 = -2147469095;
LABEL_32:
    DfsLogDfsEvent(v13, 1u, (const unsigned __int16 **const)v14, v12);
    return v7;
  }
  if ( *((_DWORD *)CConfigurationSettings::_GetInstance((unsigned int *)this) + 3) )
  {
    v12 = 0;
    v13 = 1073756378;
    goto LABEL_32;
  }
  return v7;
}

```

## disassembly

```asm
0x14002ccc4  mov     r11, rsp
0x14002ccc7  mov     [r11+8], rbx
0x14002cccb  mov     [r11+10h], rbp
0x14002cccf  mov     [r11+18h], rsi
0x14002ccd3  mov     [r11+20h], rdi
0x14002ccd7  push    r12
0x14002ccd9  push    r14
0x14002ccdb  push    r15
0x14002ccdd  sub     rsp, 40h
0x14002cce1  xor     r12d, r12d
0x14002cce4  lea     rbp, [rcx+98h]
0x14002cceb  mov     [r11-20h], r12
0x14002ccef  lea     r14, [rcx+128h]
0x14002ccf6  mov     rbx, rcx
0x14002ccf9  lea     rax, WPP_GLOBAL_Control
0x14002cd00  cmp     cs:WPP_GLOBAL_Control, rax
0x14002cd07  lea     esi, [r12+20h]
0x14002cd0c  jz      short loc_14002CD40
0x14002cd0e  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002cd15  test    rcx, rcx
0x14002cd18  jz      short loc_14002CD40
0x14002cd1a  test    [rcx+1Ch], sil
0x14002cd1e  jz      short loc_14002CD40
0x14002cd20  cmp     byte ptr [rcx+19h], 3
0x14002cd24  jb      short loc_14002CD40
0x14002cd26  mov     rcx, [rcx+10h]
0x14002cd2a  lea     edx, [rsi+3]
0x14002cd2d  mov     r9, rbx
0x14002cd30  mov     [r11-38h], rbp
0x14002cd34  lea     r8, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids
0x14002cd3b  call    WPP_SF_qZ
0x14002cd40  mov     eax, [rbx+110h]
0x14002cd46  test    sil, al
0x14002cd49  jnz     short loc_14002CD56
0x14002cd4b  mov     edi, [rbx+0F4h]
0x14002cd51  jmp     loc_14002CE76
0x14002cd56  test    al, 40h
0x14002cd58  jz      short loc_14002CD61
0x14002cd5a  xor     eax, eax
0x14002cd5c  jmp     loc_14002CEB4
0x14002cd61  cmp     byte ptr [rbx+0D8h], 1
0x14002cd68  lea     r15, [rbx+118h]
0x14002cd6f  mov     rcx, r15
0x14002cd72  mov     rdx, rbp; struct _UNICODE_STRING *
0x14002cd75  cmovnz  rcx, r12; struct _UNICODE_STRING *
0x14002cd79  call    ?DfsSetDfsNamespaceState@@YAKPEAU_UNICODE_STRING@@0E@Z; DfsSetDfsNamespaceState(_UNICODE_STRING *,_UNICODE_STRING *,uchar)
0x14002cd7e  mov     edi, eax
0x14002cd80  lea     rax, WPP_GLOBAL_Control
0x14002cd87  cmp     cs:WPP_GLOBAL_Control, rax
0x14002cd8e  jz      short loc_14002CDDB
0x14002cd90  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002cd97  test    r10, r10
0x14002cd9a  jz      short loc_14002CDDB
0x14002cd9c  mov     ecx, edi
0x14002cd9e  mov     eax, esi
0x14002cda0  neg     ecx
0x14002cda2  sbb     edx, edx
0x14002cda4  and     edx, 0FFFFFFECh
0x14002cda7  add     edx, 1Fh
0x14002cdaa  bts     eax, edx
0x14002cdad  test    [r10+1Ch], eax
0x14002cdb1  jz      short loc_14002CDDB
0x14002cdb3  cmp     byte ptr [r10+19h], 3
0x14002cdb8  jb      short loc_14002CDDB
0x14002cdba  mov     rcx, [r10+10h]
0x14002cdbe  lea     r8, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids
0x14002cdc5  mov     edx, 24h ; '$'
0x14002cdca  mov     [rsp+58h+var_30], edi
0x14002cdce  mov     r9, rbx
0x14002cdd1  mov     [rsp+58h+var_38], rbp
0x14002cdd6  call    WPP_SF_qZD
0x14002cddb  test    edi, edi
0x14002cddd  jnz     loc_14002CE76
0x14002cde3  mov     r8b, 1; CaseInsensitive
0x14002cde6  mov     rdx, r14; String2
0x14002cde9  mov     rcx, rbp; String1
0x14002cdec  call    cs:__imp_RtlCompareUnicodeString
0x14002cdf3  nop     dword ptr [rax+rax+00h]
0x14002cdf8  test    eax, eax
0x14002cdfa  jz      short loc_14002CE6F
0x14002cdfc  cmp     byte ptr [rbx+0D8h], 1
0x14002ce03  mov     rdx, r14; struct _UNICODE_STRING *
0x14002ce06  cmovnz  r15, r12
0x14002ce0a  mov     rcx, r15; struct _UNICODE_STRING *
0x14002ce0d  call    ?DfsSetDfsNamespaceState@@YAKPEAU_UNICODE_STRING@@0E@Z; DfsSetDfsNamespaceState(_UNICODE_STRING *,_UNICODE_STRING *,uchar)
0x14002ce12  mov     edi, eax
0x14002ce14  lea     rax, WPP_GLOBAL_Control
0x14002ce1b  cmp     cs:WPP_GLOBAL_Control, rax
0x14002ce22  jz      short loc_14002CE6B
0x14002ce24  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002ce2b  test    rcx, rcx
0x14002ce2e  jz      short loc_14002CE6B
0x14002ce30  mov     eax, edi
0x14002ce32  neg     eax
0x14002ce34  sbb     edx, edx
0x14002ce36  and     edx, 0FFFFFFECh
0x14002ce39  add     edx, 1Fh
0x14002ce3c  bts     esi, edx
0x14002ce3f  test    [rcx+1Ch], esi
0x14002ce42  jz      short loc_14002CE6B
0x14002ce44  cmp     byte ptr [rcx+19h], 3
0x14002ce48  jb      short loc_14002CE6B
0x14002ce4a  mov     rcx, [rcx+10h]
0x14002ce4e  lea     r8, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids
0x14002ce55  mov     edx, 25h ; '%'
0x14002ce5a  mov     [rsp+58h+var_30], edi
0x14002ce5e  mov     r9, rbx
0x14002ce61  mov     [rsp+58h+var_38], r14
0x14002ce66  call    WPP_SF_qZD
0x14002ce6b  test    edi, edi
0x14002ce6d  jnz     short loc_14002CE76
0x14002ce6f  or      dword ptr [rbx+110h], 40h
0x14002ce76  mov     rax, [rbx+0A0h]
0x14002ce7d  mov     [rsp+58h+var_28], rax
0x14002ce82  test    edi, edi
0x14002ce84  jz      short loc_14002CE90
0x14002ce86  mov     r9d, edi
0x14002ce89  mov     ecx, 800038D9h
0x14002ce8e  jmp     short loc_14002CEA3
0x14002ce90  call    ?_GetInstance@CConfigurationSettings@@SAPEAV1@PEAK@Z; CConfigurationSettings::_GetInstance(ulong *)
0x14002ce95  cmp     [rax+0Ch], r12d
0x14002ce99  jz      short loc_14002CEB2
0x14002ce9b  xor     r9d, r9d; unsigned int
0x14002ce9e  mov     ecx, 400038DAh; unsigned int
0x14002cea3  lea     r8, [rsp+58h+var_28]; unsigned __int16 **
0x14002cea8  mov     edx, 1; unsigned __int16
0x14002cead  call    ?DfsLogDfsEvent@@YAKKGQEAPEBGK@Z; DfsLogDfsEvent(ulong,ushort,ushort const * * const,ulong)
0x14002ceb2  mov     eax, edi
0x14002ceb4  mov     rbx, [rsp+58h+arg_0]
0x14002ceb9  mov     rbp, [rsp+58h+arg_8]
0x14002cebe  mov     rsi, [rsp+58h+arg_10]
0x14002cec3  mov     rdi, [rsp+58h+arg_18]
0x14002cec8  add     rsp, 40h
0x14002cecc  pop     r15
0x14002cece  pop     r14
0x14002ced0  pop     r12
0x14002ced2  retn
```
