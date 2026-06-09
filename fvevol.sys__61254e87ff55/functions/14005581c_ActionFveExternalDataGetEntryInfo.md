# ActionFveExternalDataGetEntryInfo

- ea: `0x14005581c`
- end: `0x140055c87`
- name: `ActionFveExternalDataGetEntryInfo`
- size: `1131`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14008b6ec`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000afb4`
- `0x14000ba48`
- `0x140015620`
- `0x140022bf0`
- `0x140023040`
- `0x14005581c`
- `0x1400dce00`
- `0x1400dd144`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140055a59`
- `ntoskrnl!ProbeForWrite` at `0x140055a70`
- `ntoskrnl!ProbeForWrite` at `0x140055a91`
- `ntoskrnl!ProbeForWrite` at `0x140055a59`
- `ntoskrnl!ProbeForWrite` at `0x140055a70`
- `ntoskrnl!ProbeForWrite` at `0x140055a91`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400559a1`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400559a1`
- `ntoskrnl!KeStackAttachProcess` at `0x140055a3a`
- `ntoskrnl!KeStackAttachProcess` at `0x140055a3a`

## pseudocode

```c
__int64 __fastcall ActionFveExternalDataGetEntryInfo(__int64 a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v5; // rbx
  char v6; // r12
  int EntryInfo; // ebx
  int v8; // r8d
  struct _KPROCESS *v9; // r12
  int v10; // eax
  char v11; // al
  unsigned int v13; // eax
  volatile void *v14; // rcx
  USHORT v15[2]; // [rsp+44h] [rbp-124h] BYREF
  char v16; // [rsp+48h] [rbp-120h]
  _DWORD v17[3]; // [rsp+4Ch] [rbp-11Ch] BYREF
  __int64 v18; // [rsp+58h] [rbp-110h]
  _BYTE v19[144]; // [rsp+60h] [rbp-108h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+F0h] [rbp-78h] BYREF

  v5 = a1;
  v18 = a1;
  memset(&ApcState, 0, sizeof(ApcState));
  v17[0] = 0;
  v15[0] = 0;
  memset(v19, 0, sizeof(v19));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 162, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids);
  }
  v17[0] = 0;
  v15[0] = 0;
  v6 = 0;
  if ( *a3 < 0x50u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 163, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids, *a3);
    }
LABEL_10:
    EntryInfo = -1073741811;
LABEL_20:
    v11 = 0;
    goto LABEL_21;
  }
  v8 = *((_DWORD *)a3 + 1);
  if ( v8 != 29 || a3[1] != 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 164, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids, a3[1], v8);
    }
    goto LABEL_10;
  }
  v9 = *(struct _KPROCESS **)(a2 + 120);
  if ( *(_BYTE *)(a2 + 64) )
  {
    v10 = FveCheckAdminAccess(v5, a2, 1);
    EntryInfo = v10;
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_19;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          165,
          WPP_314c37a8eeb93938f289173f56a197f3_Traceguids,
          (unsigned int)v10);
LABEL_19:
        v6 = 0;
        goto LABEL_20;
      }
      v11 = 0;
      goto LABEL_55;
    }
    v5 = v18;
  }
  FvepAcquireDevFveLock(v5, v19, 0);
  v16 = 1;
  if ( !*(_BYTE *)(a2 + 64) )
  {
    EntryInfo = FveDataSetExternalDataGetEntryInfo(
                  (unsigned __int8)*(_QWORD *)(v5 + 984) + 64,
                  (__int64)v17,
                  (USHORT)v15,
                  *((void **)a3 + 9));
    if ( EntryInfo >= 0 )
    {
      **((_DWORD **)a3 + 7) = v17[0];
      **((_WORD **)a3 + 8) = v15[0];
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      {
        v11 = 1;
LABEL_55:
        v6 = 0;
        goto LABEL_21;
      }
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          168,
          WPP_314c37a8eeb93938f289173f56a197f3_Traceguids,
          (unsigned int)EntryInfo);
    }
    v6 = 0;
    v11 = 1;
    goto LABEL_21;
  }
  KeStackAttachProcess(v9, &ApcState);
  v6 = 1;
  ProbeForWrite(*((volatile void **)a3 + 7), 4u, 4u);
  ProbeForWrite(*((volatile void **)a3 + 8), 2u, 4u);
  v13 = *((_DWORD *)a3 + 13);
  if ( v13 )
  {
    v14 = (volatile void *)*((_QWORD *)a3 + 9);
    if ( v14 )
      ProbeForWrite(v14, v13, 1u);
  }
  EntryInfo = FveDataSetExternalDataGetEntryInfo(
                (unsigned __int8)*(_QWORD *)(v5 + 984) + 64,
                (__int64)v17,
                (USHORT)v15,
                *((void **)a3 + 9));
  v17[1] = EntryInfo;
  if ( EntryInfo >= 0 )
  {
    **((_DWORD **)a3 + 7) = v17[0];
    **((_WORD **)a3 + 8) = v15[0];
    v11 = 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        166,
        WPP_314c37a8eeb93938f289173f56a197f3_Traceguids,
        (unsigned int)EntryInfo);
    }
    v11 = 1;
  }
LABEL_21:
  if ( v11 )
    FvepReleaseDevFveLock(v19);
  if ( v6 )
    KeUnstackDetachProcess(&ApcState);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      169,
      WPP_314c37a8eeb93938f289173f56a197f3_Traceguids,
      (unsigned int)EntryInfo);
  }
  return (unsigned int)EntryInfo;
}

```

## disassembly

```asm
0x14005581c  mov     r11, rsp
0x14005581f  push    rbx
0x140055820  push    rsi
0x140055821  push    rdi
0x140055822  push    r12
0x140055824  push    r13
0x140055826  push    r14
0x140055828  push    r15
0x14005582a  sub     rsp, 130h
0x140055831  mov     rax, cs:__security_cookie
0x140055838  xor     rax, rsp
0x14005583b  mov     [rsp+168h+var_48], rax
0x140055843  mov     rsi, r8
0x140055846  mov     r13, rdx
0x140055849  mov     rbx, rcx
0x14005584c  mov     [rsp+168h+var_110], rcx
0x140055851  xorps   xmm0, xmm0
0x140055854  movups  xmmword ptr [r11-78h], xmm0
0x140055859  movups  xmmword ptr [r11-68h], xmm0
0x14005585e  movups  xmmword ptr [r11-58h], xmm0
0x140055863  xor     r14d, r14d
0x140055866  mov     [rsp+168h+var_11C], r14d
0x14005586b  mov     [rsp+168h+var_124], r14w
0x140055871  xor     edx, edx; Val
0x140055873  mov     r8d, 90h; Size
0x140055879  lea     rcx, [rsp+168h+var_108]; void *
0x14005587e  call    memset
0x140055883  lea     r15, WPP_GLOBAL_Control
0x14005588a  mov     rcx, cs:WPP_GLOBAL_Control
0x140055891  lea     edi, [r14+1]
0x140055895  cmp     rcx, r15
0x140055898  jz      short loc_1400558BD
0x14005589a  mov     eax, [rcx+2Ch]
0x14005589d  test    dil, al
0x1400558a0  jz      short loc_1400558BD
0x1400558a2  cmp     byte ptr [rcx+29h], 5
0x1400558a6  jb      short loc_1400558BD
0x1400558a8  mov     edx, 0A2h
0x1400558ad  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x1400558b4  mov     rcx, [rcx+18h]
0x1400558b8  call    WPP_SF_
0x1400558bd  mov     [rsp+168h+var_11C], r14d
0x1400558c2  mov     [rsp+168h+var_124], r14w
0x1400558c8  mov     r12b, r14b
0x1400558cb  movzx   edx, word ptr [rsi]
0x1400558ce  cmp     edx, 50h ; 'P'
0x1400558d1  jnb     short loc_14005590C
0x1400558d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400558da  cmp     rcx, r15
0x1400558dd  jz      short loc_140055905
0x1400558df  mov     eax, [rcx+2Ch]
0x1400558e2  test    dil, al
0x1400558e5  jz      short loc_140055905
0x1400558e7  cmp     byte ptr [rcx+29h], 2
0x1400558eb  jb      short loc_140055905
0x1400558ed  mov     r9d, edx
0x1400558f0  mov     edx, 0A3h
0x1400558f5  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x1400558fc  mov     rcx, [rcx+18h]
0x140055900  call    WPP_SF_d
0x140055905  mov     ebx, 0C000000Dh
0x14005590a  jmp     short loc_140055983
0x14005590c  mov     r8d, [rsi+4]
0x140055910  cmp     r8d, 1Dh
0x140055914  jnz     loc_140055C2D
0x14005591a  cmp     [rsi+2], di
0x14005591e  jnz     loc_140055C2D
0x140055924  mov     r12, [r13+78h]
0x140055928  cmp     [r13+40h], r14b
0x14005592c  jz      loc_140055A0A
0x140055932  mov     r8d, edi
0x140055935  mov     rdx, r13
0x140055938  mov     rcx, rbx
0x14005593b  call    FveCheckAdminAccess
0x140055940  mov     ebx, eax
0x140055942  test    eax, eax
0x140055944  jns     loc_140055A05
0x14005594a  mov     rcx, cs:WPP_GLOBAL_Control
0x140055951  cmp     rcx, r15
0x140055954  jz      short loc_140055980
0x140055956  mov     edx, [rcx+2Ch]
0x140055959  test    dil, dl
0x14005595c  jz      short loc_140055980
0x14005595e  cmp     byte ptr [rcx+29h], 2
0x140055962  jb      loc_140055C7C
0x140055968  mov     edx, 0A5h
0x14005596d  mov     r9d, eax
0x140055970  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x140055977  mov     rcx, [rcx+18h]
0x14005597b  call    WPP_SF_d
0x140055980  mov     r12b, r14b
0x140055983  mov     al, r14b
0x140055986  test    al, al
0x140055988  jz      short loc_140055994
0x14005598a  lea     rcx, [rsp+168h+var_108]
0x14005598f  call    FvepReleaseDevFveLock
0x140055994  test    r12b, r12b
0x140055997  jz      short loc_1400559AD
0x140055999  lea     rcx, [rsp+168h+ApcState]; ApcState
0x1400559a1  call    cs:__imp_KeUnstackDetachProcess
0x1400559a8  nop     dword ptr [rax+rax+00h]
0x1400559ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400559b4  cmp     rcx, r15
0x1400559b7  jz      short loc_1400559DF
0x1400559b9  mov     eax, [rcx+2Ch]
0x1400559bc  test    dil, al
0x1400559bf  jz      short loc_1400559DF
0x1400559c1  cmp     byte ptr [rcx+29h], 5
0x1400559c5  jb      short loc_1400559DF
0x1400559c7  mov     edx, 0A9h
0x1400559cc  mov     r9d, ebx
0x1400559cf  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x1400559d6  mov     rcx, [rcx+18h]
0x1400559da  call    WPP_SF_d
0x1400559df  mov     eax, ebx
0x1400559e1  mov     rcx, [rsp+168h+var_48]
0x1400559e9  xor     rcx, rsp; StackCookie
0x1400559ec  call    __security_check_cookie
0x1400559f1  add     rsp, 130h
0x1400559f8  pop     r15
0x1400559fa  pop     r14
0x1400559fc  pop     r13
0x1400559fe  pop     r12
0x140055a00  pop     rdi
0x140055a01  pop     rsi
0x140055a02  pop     rbx
0x140055a03  retn
0x140055a05  mov     rbx, [rsp+168h+var_110]
0x140055a0a  xor     r8d, r8d
0x140055a0d  lea     rdx, [rsp+168h+var_108]
0x140055a12  mov     rcx, rbx
0x140055a15  call    FvepAcquireDevFveLock
0x140055a1a  mov     al, dil
0x140055a1d  mov     [rsp+168h+var_128], al
0x140055a21  mov     [rsp+168h+var_120], al
0x140055a25  cmp     [r13+40h], r14b
0x140055a29  jz      loc_140055B94
0x140055a2f  lea     rdx, [rsp+168h+ApcState]; ApcState
0x140055a37  mov     rcx, r12; PROCESS
0x140055a3a  call    cs:__imp_KeStackAttachProcess
0x140055a41  nop     dword ptr [rax+rax+00h]
0x140055a46  mov     r12b, dil
0x140055a49  mov     r13d, 4
0x140055a4f  mov     r8d, r13d; Alignment
0x140055a52  mov     edx, r13d; Length
0x140055a55  mov     rcx, [rsi+38h]; Address
0x140055a59  call    cs:__imp_ProbeForWrite
0x140055a60  nop     dword ptr [rax+rax+00h]
0x140055a65  mov     r8d, r13d; Alignment
0x140055a68  lea     edx, [r13-2]; Length
0x140055a6c  mov     rcx, [rsi+40h]; Address
0x140055a70  call    cs:__imp_ProbeForWrite
0x140055a77  nop     dword ptr [rax+rax+00h]
0x140055a7c  mov     eax, [rsi+34h]
0x140055a7f  test    eax, eax
0x140055a81  jz      short loc_140055A9D
0x140055a83  mov     rcx, [rsi+48h]; Address
0x140055a87  test    rcx, rcx
0x140055a8a  jz      short loc_140055A9D
0x140055a8c  mov     edx, eax; Length
0x140055a8e  mov     r8d, edi; Alignment
0x140055a91  call    cs:__imp_ProbeForWrite
0x140055a98  nop     dword ptr [rax+rax+00h]
0x140055a9d  lea     rdx, [rsi+8]
0x140055aa1  mov     rcx, [rbx+3D8h]
0x140055aa8  add     rcx, 40h ; '@'; char
0x140055aac  mov     rax, [rsi+48h]
0x140055ab0  mov     [rsp+168h+var_138], rax; void *
0x140055ab5  lea     rax, [rsp+168h+var_124]
0x140055aba  mov     qword ptr [rsp+168h+pusResult], rax; pusResult
0x140055abf  lea     rax, [rsp+168h+var_11C]
0x140055ac4  mov     [rsp+168h+var_148], rax; __int64
0x140055ac9  mov     r9d, [rsi+34h]
0x140055acd  movzx   r8d, word ptr [rsi+30h]
0x140055ad2  call    FveDataSetExternalDataGetEntryInfo
0x140055ad7  mov     ebx, eax
0x140055ad9  mov     [rsp+168h+var_11C+4], eax
0x140055add  test    eax, eax
0x140055adf  jns     short loc_140055B1C
0x140055ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x140055ae8  cmp     rcx, r15
0x140055aeb  jz      short loc_140055B13
0x140055aed  mov     eax, [rcx+2Ch]
0x140055af0  test    dil, al
0x140055af3  jz      short loc_140055B13
0x140055af5  cmp     byte ptr [rcx+29h], 2
0x140055af9  jb      short loc_140055B13
0x140055afb  mov     edx, 0A6h
0x140055b00  mov     r9d, ebx
0x140055b03  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x140055b0a  mov     rcx, [rcx+18h]
0x140055b0e  call    WPP_SF_d
0x140055b13  mov     al, [rsp+168h+var_128]
0x140055b17  jmp     loc_140055986
0x140055b1c  mov     rcx, [rsi+38h]
0x140055b20  mov     eax, [rsp+168h+var_11C]
0x140055b24  mov     [rcx], eax
0x140055b26  mov     rcx, [rsi+40h]
0x140055b2a  movzx   eax, [rsp+168h+var_124]
0x140055b2f  mov     [rcx], ax
0x140055b32  mov     al, [rsp+168h+var_128]
0x140055b36  jmp     loc_140055986
0x140055b3b  mov     ebx, 0C000000Dh
0x140055b40  mov     [rsp+168h+var_11C+4], ebx
0x140055b44  lea     rax, WPP_GLOBAL_Control
0x140055b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140055b52  cmp     rcx, rax
0x140055b55  jz      short loc_140055B7C
0x140055b57  mov     eax, [rcx+2Ch]
0x140055b5a  test    al, 1
0x140055b5c  jz      short loc_140055B7C
0x140055b5e  cmp     byte ptr [rcx+29h], 2
0x140055b62  jb      short loc_140055B7C
0x140055b64  mov     edx, 0A7h
0x140055b69  mov     r9d, ebx
0x140055b6c  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x140055b73  mov     rcx, [rcx+18h]
0x140055b77  call    WPP_SF_d
0x140055b7c  lea     r15, WPP_GLOBAL_Control
0x140055b83  mov     edi, 1
0x140055b88  mov     al, [rsp+168h+var_120]
0x140055b8c  mov     r12b, al
0x140055b8f  jmp     loc_140055986
0x140055b94  lea     rdx, [rsi+8]
0x140055b98  mov     rcx, [rbx+3D8h]
0x140055b9f  add     rcx, 40h ; '@'; char
0x140055ba3  mov     rax, [rsi+48h]
0x140055ba7  mov     [rsp+168h+var_138], rax; void *
0x140055bac  lea     rax, [rsp+168h+var_124]
0x140055bb1  mov     qword ptr [rsp+168h+pusResult], rax; pusResult
0x140055bb6  lea     rax, [rsp+168h+var_11C]
0x140055bbb  mov     [rsp+168h+var_148], rax; __int64
0x140055bc0  mov     r9d, [rsi+34h]
0x140055bc4  movzx   r8d, word ptr [rsi+30h]
0x140055bc9  call    FveDataSetExternalDataGetEntryInfo
0x140055bce  mov     ebx, eax
0x140055bd0  test    eax, eax
0x140055bd2  jns     short loc_140055C15
0x140055bd4  mov     rcx, cs:WPP_GLOBAL_Control
0x140055bdb  cmp     rcx, r15
0x140055bde  jz      short loc_140055C0A
0x140055be0  mov     eax, [rcx+2Ch]
0x140055be3  test    dil, al
0x140055be6  jz      loc_140055C77
0x140055bec  cmp     byte ptr [rcx+29h], 2
0x140055bf0  jb      short loc_140055C0A
0x140055bf2  mov     edx, 0A8h
0x140055bf7  mov     r9d, ebx
0x140055bfa  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x140055c01  mov     rcx, [rcx+18h]
0x140055c05  call    WPP_SF_d
0x140055c0a  mov     r12b, r14b
0x140055c0d  mov     al, dil
0x140055c10  jmp     loc_140055986
0x140055c15  mov     rcx, [rsi+38h]
0x140055c19  mov     eax, [rsp+168h+var_11C]
0x140055c1d  mov     [rcx], eax
0x140055c1f  mov     rcx, [rsi+40h]
0x140055c23  movzx   eax, [rsp+168h+var_124]
0x140055c28  mov     [rcx], ax
0x140055c2b  jmp     short loc_140055C0A
0x140055c2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140055c34  cmp     rcx, r15
0x140055c37  jz      loc_140055905
0x140055c3d  mov     eax, [rcx+2Ch]
0x140055c40  test    dil, al
0x140055c43  jz      loc_140055905
0x140055c49  cmp     byte ptr [rcx+29h], 2
0x140055c4d  jb      loc_140055905
0x140055c53  movzx   r9d, word ptr [rsi+2]
0x140055c58  mov     edx, 0A4h
0x140055c5d  mov     dword ptr [rsp+168h+var_148], r8d
0x140055c62  lea     r8, WPP_314c37a8eeb93938f289173f56a197f3_Traceguids
0x140055c69  mov     rcx, [rcx+18h]
0x140055c6d  call    WPP_SF_Dd
0x140055c72  jmp     loc_140055905
0x140055c77  mov     al, dil
0x140055c7a  jmp     short loc_140055C7F
0x140055c7c  mov     al, r14b
0x140055c7f  mov     r12b, r14b
0x140055c82  jmp     loc_140055986
```
