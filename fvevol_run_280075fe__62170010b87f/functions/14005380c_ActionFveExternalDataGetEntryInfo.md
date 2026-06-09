# ActionFveExternalDataGetEntryInfo

- ea: `0x14005380c`
- end: `0x140053c77`
- name: `ActionFveExternalDataGetEntryInfo`
- size: `1131`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14008964c`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000aef4`
- `0x14000b920`
- `0x140014c68`
- `0x1400218c0`
- `0x140021d00`
- `0x14005380c`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140053a49`
- `ntoskrnl!ProbeForWrite` at `0x140053a60`
- `ntoskrnl!ProbeForWrite` at `0x140053a81`
- `ntoskrnl!ProbeForWrite` at `0x140053a49`
- `ntoskrnl!ProbeForWrite` at `0x140053a60`
- `ntoskrnl!ProbeForWrite` at `0x140053a81`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140053991`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140053991`
- `ntoskrnl!KeStackAttachProcess` at `0x140053a2a`
- `ntoskrnl!KeStackAttachProcess` at `0x140053a2a`

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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 161, WPP_db10fbeca6e03e7325aab39114461952_Traceguids);
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 162, WPP_db10fbeca6e03e7325aab39114461952_Traceguids, *a3);
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
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 163, WPP_db10fbeca6e03e7325aab39114461952_Traceguids, a3[1], v8);
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
          164,
          WPP_db10fbeca6e03e7325aab39114461952_Traceguids,
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
          167,
          WPP_db10fbeca6e03e7325aab39114461952_Traceguids,
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
        165,
        WPP_db10fbeca6e03e7325aab39114461952_Traceguids,
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
      168,
      WPP_db10fbeca6e03e7325aab39114461952_Traceguids,
      (unsigned int)EntryInfo);
  }
  return (unsigned int)EntryInfo;
}

```

## disassembly

```asm
0x14005380c  mov     r11, rsp
0x14005380f  push    rbx
0x140053810  push    rsi
0x140053811  push    rdi
0x140053812  push    r12
0x140053814  push    r13
0x140053816  push    r14
0x140053818  push    r15
0x14005381a  sub     rsp, 130h
0x140053821  mov     rax, cs:__security_cookie
0x140053828  xor     rax, rsp
0x14005382b  mov     [rsp+168h+var_48], rax
0x140053833  mov     rsi, r8
0x140053836  mov     r13, rdx
0x140053839  mov     rbx, rcx
0x14005383c  mov     [rsp+168h+var_110], rcx
0x140053841  xorps   xmm0, xmm0
0x140053844  movups  xmmword ptr [r11-78h], xmm0
0x140053849  movups  xmmword ptr [r11-68h], xmm0
0x14005384e  movups  xmmword ptr [r11-58h], xmm0
0x140053853  xor     r14d, r14d
0x140053856  mov     [rsp+168h+var_11C], r14d
0x14005385b  mov     [rsp+168h+var_124], r14w
0x140053861  xor     edx, edx; Val
0x140053863  mov     r8d, 90h; Size
0x140053869  lea     rcx, [rsp+168h+var_108]; void *
0x14005386e  call    memset
0x140053873  lea     r15, WPP_GLOBAL_Control
0x14005387a  mov     rcx, cs:WPP_GLOBAL_Control
0x140053881  lea     edi, [r14+1]
0x140053885  cmp     rcx, r15
0x140053888  jz      short loc_1400538AD
0x14005388a  mov     eax, [rcx+2Ch]
0x14005388d  test    dil, al
0x140053890  jz      short loc_1400538AD
0x140053892  cmp     byte ptr [rcx+29h], 5
0x140053896  jb      short loc_1400538AD
0x140053898  mov     edx, 0A1h
0x14005389d  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x1400538a4  mov     rcx, [rcx+18h]
0x1400538a8  call    WPP_SF_
0x1400538ad  mov     [rsp+168h+var_11C], r14d
0x1400538b2  mov     [rsp+168h+var_124], r14w
0x1400538b8  mov     r12b, r14b
0x1400538bb  movzx   edx, word ptr [rsi]
0x1400538be  cmp     edx, 50h ; 'P'
0x1400538c1  jnb     short loc_1400538FC
0x1400538c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400538ca  cmp     rcx, r15
0x1400538cd  jz      short loc_1400538F5
0x1400538cf  mov     eax, [rcx+2Ch]
0x1400538d2  test    dil, al
0x1400538d5  jz      short loc_1400538F5
0x1400538d7  cmp     byte ptr [rcx+29h], 2
0x1400538db  jb      short loc_1400538F5
0x1400538dd  mov     r9d, edx
0x1400538e0  mov     edx, 0A2h
0x1400538e5  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x1400538ec  mov     rcx, [rcx+18h]
0x1400538f0  call    WPP_SF_d
0x1400538f5  mov     ebx, 0C000000Dh
0x1400538fa  jmp     short loc_140053973
0x1400538fc  mov     r8d, [rsi+4]
0x140053900  cmp     r8d, 1Dh
0x140053904  jnz     loc_140053C1D
0x14005390a  cmp     [rsi+2], di
0x14005390e  jnz     loc_140053C1D
0x140053914  mov     r12, [r13+78h]
0x140053918  cmp     [r13+40h], r14b
0x14005391c  jz      loc_1400539FA
0x140053922  mov     r8d, edi
0x140053925  mov     rdx, r13
0x140053928  mov     rcx, rbx
0x14005392b  call    FveCheckAdminAccess
0x140053930  mov     ebx, eax
0x140053932  test    eax, eax
0x140053934  jns     loc_1400539F5
0x14005393a  mov     rcx, cs:WPP_GLOBAL_Control
0x140053941  cmp     rcx, r15
0x140053944  jz      short loc_140053970
0x140053946  mov     edx, [rcx+2Ch]
0x140053949  test    dil, dl
0x14005394c  jz      short loc_140053970
0x14005394e  cmp     byte ptr [rcx+29h], 2
0x140053952  jb      loc_140053C6C
0x140053958  mov     edx, 0A4h
0x14005395d  mov     r9d, eax
0x140053960  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x140053967  mov     rcx, [rcx+18h]
0x14005396b  call    WPP_SF_d
0x140053970  mov     r12b, r14b
0x140053973  mov     al, r14b
0x140053976  test    al, al
0x140053978  jz      short loc_140053984
0x14005397a  lea     rcx, [rsp+168h+var_108]
0x14005397f  call    FvepReleaseDevFveLock
0x140053984  test    r12b, r12b
0x140053987  jz      short loc_14005399D
0x140053989  lea     rcx, [rsp+168h+ApcState]; ApcState
0x140053991  call    cs:__imp_KeUnstackDetachProcess
0x140053998  nop     dword ptr [rax+rax+00h]
0x14005399d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400539a4  cmp     rcx, r15
0x1400539a7  jz      short loc_1400539CF
0x1400539a9  mov     eax, [rcx+2Ch]
0x1400539ac  test    dil, al
0x1400539af  jz      short loc_1400539CF
0x1400539b1  cmp     byte ptr [rcx+29h], 5
0x1400539b5  jb      short loc_1400539CF
0x1400539b7  mov     edx, 0A8h
0x1400539bc  mov     r9d, ebx
0x1400539bf  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x1400539c6  mov     rcx, [rcx+18h]
0x1400539ca  call    WPP_SF_d
0x1400539cf  mov     eax, ebx
0x1400539d1  mov     rcx, [rsp+168h+var_48]
0x1400539d9  xor     rcx, rsp; StackCookie
0x1400539dc  call    __security_check_cookie
0x1400539e1  add     rsp, 130h
0x1400539e8  pop     r15
0x1400539ea  pop     r14
0x1400539ec  pop     r13
0x1400539ee  pop     r12
0x1400539f0  pop     rdi
0x1400539f1  pop     rsi
0x1400539f2  pop     rbx
0x1400539f3  retn
0x1400539f5  mov     rbx, [rsp+168h+var_110]
0x1400539fa  xor     r8d, r8d
0x1400539fd  lea     rdx, [rsp+168h+var_108]
0x140053a02  mov     rcx, rbx
0x140053a05  call    FvepAcquireDevFveLock
0x140053a0a  mov     al, dil
0x140053a0d  mov     [rsp+168h+var_128], al
0x140053a11  mov     [rsp+168h+var_120], al
0x140053a15  cmp     [r13+40h], r14b
0x140053a19  jz      loc_140053B84
0x140053a1f  lea     rdx, [rsp+168h+ApcState]; ApcState
0x140053a27  mov     rcx, r12; PROCESS
0x140053a2a  call    cs:__imp_KeStackAttachProcess
0x140053a31  nop     dword ptr [rax+rax+00h]
0x140053a36  mov     r12b, dil
0x140053a39  mov     r13d, 4
0x140053a3f  mov     r8d, r13d; Alignment
0x140053a42  mov     edx, r13d; Length
0x140053a45  mov     rcx, [rsi+38h]; Address
0x140053a49  call    cs:__imp_ProbeForWrite
0x140053a50  nop     dword ptr [rax+rax+00h]
0x140053a55  mov     r8d, r13d; Alignment
0x140053a58  lea     edx, [r13-2]; Length
0x140053a5c  mov     rcx, [rsi+40h]; Address
0x140053a60  call    cs:__imp_ProbeForWrite
0x140053a67  nop     dword ptr [rax+rax+00h]
0x140053a6c  mov     eax, [rsi+34h]
0x140053a6f  test    eax, eax
0x140053a71  jz      short loc_140053A8D
0x140053a73  mov     rcx, [rsi+48h]; Address
0x140053a77  test    rcx, rcx
0x140053a7a  jz      short loc_140053A8D
0x140053a7c  mov     edx, eax; Length
0x140053a7e  mov     r8d, edi; Alignment
0x140053a81  call    cs:__imp_ProbeForWrite
0x140053a88  nop     dword ptr [rax+rax+00h]
0x140053a8d  lea     rdx, [rsi+8]
0x140053a91  mov     rcx, [rbx+3D8h]
0x140053a98  add     rcx, 40h ; '@'; char
0x140053a9c  mov     rax, [rsi+48h]
0x140053aa0  mov     [rsp+168h+var_138], rax; void *
0x140053aa5  lea     rax, [rsp+168h+var_124]
0x140053aaa  mov     qword ptr [rsp+168h+pusResult], rax; pusResult
0x140053aaf  lea     rax, [rsp+168h+var_11C]
0x140053ab4  mov     [rsp+168h+var_148], rax; __int64
0x140053ab9  mov     r9d, [rsi+34h]
0x140053abd  movzx   r8d, word ptr [rsi+30h]
0x140053ac2  call    FveDataSetExternalDataGetEntryInfo
0x140053ac7  mov     ebx, eax
0x140053ac9  mov     [rsp+168h+var_11C+4], eax
0x140053acd  test    eax, eax
0x140053acf  jns     short loc_140053B0C
0x140053ad1  mov     rcx, cs:WPP_GLOBAL_Control
0x140053ad8  cmp     rcx, r15
0x140053adb  jz      short loc_140053B03
0x140053add  mov     eax, [rcx+2Ch]
0x140053ae0  test    dil, al
0x140053ae3  jz      short loc_140053B03
0x140053ae5  cmp     byte ptr [rcx+29h], 2
0x140053ae9  jb      short loc_140053B03
0x140053aeb  mov     edx, 0A5h
0x140053af0  mov     r9d, ebx
0x140053af3  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x140053afa  mov     rcx, [rcx+18h]
0x140053afe  call    WPP_SF_d
0x140053b03  mov     al, [rsp+168h+var_128]
0x140053b07  jmp     loc_140053976
0x140053b0c  mov     rcx, [rsi+38h]
0x140053b10  mov     eax, [rsp+168h+var_11C]
0x140053b14  mov     [rcx], eax
0x140053b16  mov     rcx, [rsi+40h]
0x140053b1a  movzx   eax, [rsp+168h+var_124]
0x140053b1f  mov     [rcx], ax
0x140053b22  mov     al, [rsp+168h+var_128]
0x140053b26  jmp     loc_140053976
0x140053b2b  mov     ebx, 0C000000Dh
0x140053b30  mov     [rsp+168h+var_11C+4], ebx
0x140053b34  lea     rax, WPP_GLOBAL_Control
0x140053b3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140053b42  cmp     rcx, rax
0x140053b45  jz      short loc_140053B6C
0x140053b47  mov     eax, [rcx+2Ch]
0x140053b4a  test    al, 1
0x140053b4c  jz      short loc_140053B6C
0x140053b4e  cmp     byte ptr [rcx+29h], 2
0x140053b52  jb      short loc_140053B6C
0x140053b54  mov     edx, 0A6h
0x140053b59  mov     r9d, ebx
0x140053b5c  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x140053b63  mov     rcx, [rcx+18h]
0x140053b67  call    WPP_SF_d
0x140053b6c  lea     r15, WPP_GLOBAL_Control
0x140053b73  mov     edi, 1
0x140053b78  mov     al, [rsp+168h+var_120]
0x140053b7c  mov     r12b, al
0x140053b7f  jmp     loc_140053976
0x140053b84  lea     rdx, [rsi+8]
0x140053b88  mov     rcx, [rbx+3D8h]
0x140053b8f  add     rcx, 40h ; '@'; char
0x140053b93  mov     rax, [rsi+48h]
0x140053b97  mov     [rsp+168h+var_138], rax; void *
0x140053b9c  lea     rax, [rsp+168h+var_124]
0x140053ba1  mov     qword ptr [rsp+168h+pusResult], rax; pusResult
0x140053ba6  lea     rax, [rsp+168h+var_11C]
0x140053bab  mov     [rsp+168h+var_148], rax; __int64
0x140053bb0  mov     r9d, [rsi+34h]
0x140053bb4  movzx   r8d, word ptr [rsi+30h]
0x140053bb9  call    FveDataSetExternalDataGetEntryInfo
0x140053bbe  mov     ebx, eax
0x140053bc0  test    eax, eax
0x140053bc2  jns     short loc_140053C05
0x140053bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140053bcb  cmp     rcx, r15
0x140053bce  jz      short loc_140053BFA
0x140053bd0  mov     eax, [rcx+2Ch]
0x140053bd3  test    dil, al
0x140053bd6  jz      loc_140053C67
0x140053bdc  cmp     byte ptr [rcx+29h], 2
0x140053be0  jb      short loc_140053BFA
0x140053be2  mov     edx, 0A7h
0x140053be7  mov     r9d, ebx
0x140053bea  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x140053bf1  mov     rcx, [rcx+18h]
0x140053bf5  call    WPP_SF_d
0x140053bfa  mov     r12b, r14b
0x140053bfd  mov     al, dil
0x140053c00  jmp     loc_140053976
0x140053c05  mov     rcx, [rsi+38h]
0x140053c09  mov     eax, [rsp+168h+var_11C]
0x140053c0d  mov     [rcx], eax
0x140053c0f  mov     rcx, [rsi+40h]
0x140053c13  movzx   eax, [rsp+168h+var_124]
0x140053c18  mov     [rcx], ax
0x140053c1b  jmp     short loc_140053BFA
0x140053c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140053c24  cmp     rcx, r15
0x140053c27  jz      loc_1400538F5
0x140053c2d  mov     eax, [rcx+2Ch]
0x140053c30  test    dil, al
0x140053c33  jz      loc_1400538F5
0x140053c39  cmp     byte ptr [rcx+29h], 2
0x140053c3d  jb      loc_1400538F5
0x140053c43  movzx   r9d, word ptr [rsi+2]
0x140053c48  mov     edx, 0A3h
0x140053c4d  mov     dword ptr [rsp+168h+var_148], r8d
0x140053c52  lea     r8, WPP_db10fbeca6e03e7325aab39114461952_Traceguids
0x140053c59  mov     rcx, [rcx+18h]
0x140053c5d  call    WPP_SF_Dd
0x140053c62  jmp     loc_1400538F5
0x140053c67  mov     al, dil
0x140053c6a  jmp     short loc_140053C6F
0x140053c6c  mov     al, r14b
0x140053c6f  mov     r12b, r14b
0x140053c72  jmp     loc_140053976
```
