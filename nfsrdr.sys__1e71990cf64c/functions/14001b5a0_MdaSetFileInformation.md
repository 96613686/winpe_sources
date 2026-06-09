# MdaSetFileInformation

- ea: `0x14001b5a0`
- end: `0x14001b9d1`
- name: `MdaSetFileInformation`
- size: `1073`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1400159cc`
- `0x1400159fc`
- `0x14001add0`
- `0x14001b1c4`
- `0x14001b5a0`
- `0x14001bbbc`
- `0x14001c694`
- `0x14001d6b0`

## pseudocode

```c
__int64 __fastcall MdaSetFileInformation(__int64 a1)
{
  int v1; // eax
  __int64 v3; // rsi
  __int64 v4; // rbp
  int v5; // edi
  __int64 v6; // r14
  unsigned int v7; // r15d
  int v8; // r9d
  unsigned int v9; // eax
  int v11; // r9d
  int v12; // r9d
  unsigned int v13; // ebx
  char v14; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_DWORD *)(a1 + 120);
  v14 = 0;
  if ( (v1 & 0x1000) != 0 )
  {
    if ( (v1 & 2) == 0 )
    {
      *(_BYTE *)(a1 + 35) = 1;
      return 3225485315LL;
    }
    *(_DWORD *)(a1 + 120) = v1 & 0xFFFFEFFF;
  }
  v3 = *(_QWORD *)(a1 + 56);
  v4 = *(_QWORD *)(a1 + 64);
  v5 = *(_DWORD *)(a1 + 448);
  v6 = *(_QWORD *)(a1 + 456);
  v7 = *(_DWORD *)(a1 + 472);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          25,
          WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids,
          (unsigned int)v5);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, v7);
    }
  }
  if ( v5 > 23 )
  {
    if ( v5 == 24 || v5 == 25 || v5 == 29 || v5 == 31 )
      goto LABEL_68;
    if ( v5 == 64 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
      v11 = 64;
      goto LABEL_64;
    }
    if ( v5 != 65 )
      goto LABEL_68;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
    v12 = 65;
LABEL_43:
    v9 = MdaSetRenameInformation((_QWORD *)a1, v3, v4, v12, v6, v7, (__int64)&v14);
    goto LABEL_65;
  }
  if ( v5 == 23 )
    goto LABEL_68;
  if ( v5 != 4 )
  {
    if ( v5 != 10 )
    {
      if ( v5 == 11 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
        v9 = MdaSetLinkInformation((_QWORD *)a1, v3, v4, v6, v7, (__int64)&v14);
        goto LABEL_65;
      }
      if ( v5 != 13 )
      {
        if ( v5 == 19 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
          }
          v8 = 19;
          goto LABEL_25;
        }
        if ( v5 == 20 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
          }
          v8 = 20;
LABEL_25:
          v9 = MdaSetSizeInformation(a1, v3, v4, v8, v6);
LABEL_65:
          v13 = v9;
          goto LABEL_66;
        }
LABEL_68:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            36,
            WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids,
            (unsigned int)v5);
        v13 = -1073741811;
        goto LABEL_72;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
      v11 = 13;
LABEL_64:
      v9 = MdaSetDispositionInformation(a1, v3, v4, v11, v6);
      goto LABEL_65;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
    v12 = 10;
    goto LABEL_43;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
  v13 = MdaSetBasicInformation(a1, v3, v4, v6);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, v13);
LABEL_66:
  if ( (v13 & 0x80000000) == 0 )
  {
LABEL_75:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
    return v13;
  }
LABEL_72:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids, v13);
    goto LABEL_75;
  }
  return v13;
}

```

## disassembly

```asm
0x14001b5a0  mov     [rsp+arg_8], rbx
0x14001b5a5  mov     [rsp+arg_10], rbp
0x14001b5aa  push    rsi
0x14001b5ab  push    rdi
0x14001b5ac  push    r13
0x14001b5ae  push    r14
0x14001b5b0  push    r15
0x14001b5b2  sub     rsp, 40h
0x14001b5b6  mov     eax, [rcx+78h]
0x14001b5b9  mov     rbx, rcx
0x14001b5bc  mov     [rsp+68h+arg_0], 0
0x14001b5c1  bt      eax, 0Ch
0x14001b5c5  jnb     short loc_14001B5D6
0x14001b5c7  test    al, 2
0x14001b5c9  jz      loc_14001B700
0x14001b5cf  btr     eax, 0Ch
0x14001b5d3  mov     [rcx+78h], eax
0x14001b5d6  mov     rsi, [rcx+38h]
0x14001b5da  lea     r13, WPP_GLOBAL_Control
0x14001b5e1  mov     rbp, [rcx+40h]
0x14001b5e5  mov     edi, [rcx+1C0h]
0x14001b5eb  mov     r14, [rcx+1C8h]
0x14001b5f2  mov     r15d, [rcx+1D8h]
0x14001b5f9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b600  cmp     rcx, r13
0x14001b603  jz      short loc_14001B677
0x14001b605  mov     eax, [rcx+2Ch]
0x14001b608  test    al, 8
0x14001b60a  jz      short loc_14001B621
0x14001b60c  mov     rcx, [rcx+18h]
0x14001b610  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001b617  mov     edx, 18h
0x14001b61c  call    WPP_SF_
0x14001b621  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b628  cmp     rcx, r13
0x14001b62b  jz      short loc_14001B677
0x14001b62d  mov     eax, [rcx+2Ch]
0x14001b630  test    al, 4
0x14001b632  jz      short loc_14001B64C
0x14001b634  mov     rcx, [rcx+18h]
0x14001b638  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001b63f  mov     edx, 19h
0x14001b644  mov     r9d, edi
0x14001b647  call    WPP_SF_d
0x14001b64c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b653  cmp     rcx, r13
0x14001b656  jz      short loc_14001B677
0x14001b658  mov     eax, [rcx+2Ch]
0x14001b65b  test    al, 4
0x14001b65d  jz      short loc_14001B677
0x14001b65f  mov     rcx, [rcx+18h]
0x14001b663  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001b66a  mov     edx, 1Ah
0x14001b66f  mov     r9d, r15d
0x14001b672  call    WPP_SF_d
0x14001b677  cmp     edi, 17h
0x14001b67a  jg      loc_14001B886
0x14001b680  jz      loc_14001B932
0x14001b686  mov     ecx, edi
0x14001b688  sub     ecx, 4
0x14001b68b  jz      loc_14001B813
0x14001b691  sub     ecx, 6
0x14001b694  jz      loc_14001B7BE
0x14001b69a  sub     ecx, 1
0x14001b69d  jz      loc_14001B771
0x14001b6a3  sub     ecx, 2
0x14001b6a6  jz      loc_14001B73E
0x14001b6ac  sub     ecx, 6
0x14001b6af  jz      short loc_14001B70E
0x14001b6b1  cmp     ecx, 1
0x14001b6b4  jnz     loc_14001B932
0x14001b6ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b6c1  cmp     rcx, r13
0x14001b6c4  jz      short loc_14001B6E2
0x14001b6c6  mov     eax, [rcx+2Ch]
0x14001b6c9  test    al, 4
0x14001b6cb  jz      short loc_14001B6E2
0x14001b6cd  mov     rcx, [rcx+18h]
0x14001b6d1  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001b6d8  mov     edx, 20h ; ' '
0x14001b6dd  call    WPP_SF_
0x14001b6e2  mov     r9d, 14h
0x14001b6e8  mov     r8, rbp
0x14001b6eb  mov     [rsp+68h+var_48], r14
0x14001b6f0  mov     rdx, rsi
0x14001b6f3  mov     rcx, rbx
0x14001b6f6  call    MdaSetSizeInformation
0x14001b6fb  jmp     loc_14001B92A
0x14001b700  mov     byte ptr [rcx+23h], 1
0x14001b704  mov     eax, 0C0410003h
0x14001b709  jmp     loc_14001B9B7
0x14001b70e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b715  cmp     rcx, r13
0x14001b718  jz      short loc_14001B736
0x14001b71a  mov     eax, [rcx+2Ch]
0x14001b71d  test    al, 4
0x14001b71f  jz      short loc_14001B736
0x14001b721  mov     rcx, [rcx+18h]
0x14001b725  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001b72c  mov     edx, 1Fh
0x14001b731  call    WPP_SF_
0x14001b736  mov     r9d, 13h
0x14001b73c  jmp     short loc_14001B6E8
0x14001b73e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b745  cmp     rcx, r13
0x14001b748  jz      short loc_14001B766
0x14001b74a  mov     eax, [rcx+2Ch]
0x14001b74d  test    al, 4
0x14001b74f  jz      short loc_14001B766
0x14001b751  mov     rcx, [rcx+18h]
0x14001b755  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001b75c  mov     edx, 1Dh
0x14001b761  call    WPP_SF_
0x14001b766  mov     r9d, 0Dh
0x14001b76c  jmp     loc_14001B917
0x14001b771  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b778  cmp     rcx, r13
0x14001b77b  jz      short loc_14001B799
0x14001b77d  mov     eax, [rcx+2Ch]
0x14001b780  test    al, 4
0x14001b782  jz      short loc_14001B799
0x14001b784  mov     rcx, [rcx+18h]
0x14001b788  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001b78f  mov     edx, 23h ; '#'
0x14001b794  call    WPP_SF_
0x14001b799  lea     rax, [rsp+68h+arg_0]
0x14001b79e  mov     r9, r14
0x14001b7a1  mov     [rsp+68h+var_40], rax
0x14001b7a6  mov     r8, rbp
0x14001b7a9  mov     rdx, rsi
0x14001b7ac  mov     dword ptr [rsp+68h+var_48], r15d
0x14001b7b1  mov     rcx, rbx
0x14001b7b4  call    MdaSetLinkInformation
0x14001b7b9  jmp     loc_14001B92A
0x14001b7be  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b7c5  cmp     rcx, r13
0x14001b7c8  jz      short loc_14001B7E6
0x14001b7ca  mov     eax, [rcx+2Ch]
0x14001b7cd  test    al, 4
0x14001b7cf  jz      short loc_14001B7E6
0x14001b7d1  mov     rcx, [rcx+18h]
0x14001b7d5  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001b7dc  mov     edx, 21h ; '!'
0x14001b7e1  call    WPP_SF_
0x14001b7e6  mov     r9d, 0Ah
0x14001b7ec  lea     rax, [rsp+68h+arg_0]
0x14001b7f1  mov     r8, rbp
0x14001b7f4  mov     [rsp+68h+var_38], rax
0x14001b7f9  mov     rdx, rsi
0x14001b7fc  mov     dword ptr [rsp+68h+var_40], r15d
0x14001b801  mov     rcx, rbx
0x14001b804  mov     [rsp+68h+var_48], r14
0x14001b809  call    MdaSetRenameInformation
0x14001b80e  jmp     loc_14001B92A
0x14001b813  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b81a  cmp     rcx, r13
0x14001b81d  jz      short loc_14001B83B
0x14001b81f  mov     eax, [rcx+2Ch]
0x14001b822  test    al, 4
0x14001b824  jz      short loc_14001B83B
0x14001b826  mov     rcx, [rcx+18h]
0x14001b82a  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001b831  mov     edx, 1Bh
0x14001b836  call    WPP_SF_
0x14001b83b  mov     r9, r14
0x14001b83e  mov     r8, rbp
0x14001b841  mov     rdx, rsi
0x14001b844  mov     rcx, rbx
0x14001b847  call    MdaSetBasicInformation
0x14001b84c  mov     ebx, eax
0x14001b84e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b855  cmp     rcx, r13
0x14001b858  jz      loc_14001B92C
0x14001b85e  mov     eax, [rcx+2Ch]
0x14001b861  test    al, 4
0x14001b863  jz      loc_14001B92C
0x14001b869  mov     rcx, [rcx+18h]
0x14001b86d  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001b874  mov     edx, 1Ch
0x14001b879  mov     r9d, ebx
0x14001b87c  call    WPP_SF_d
0x14001b881  jmp     loc_14001B92C
0x14001b886  mov     ecx, edi
0x14001b888  sub     ecx, 18h
0x14001b88b  jz      loc_14001B932
0x14001b891  sub     ecx, 1
0x14001b894  jz      loc_14001B932
0x14001b89a  sub     ecx, 4
0x14001b89d  jz      loc_14001B932
0x14001b8a3  sub     ecx, 2
0x14001b8a6  jz      loc_14001B932
0x14001b8ac  sub     ecx, 21h ; '!'
0x14001b8af  jz      short loc_14001B8E9
0x14001b8b1  cmp     ecx, 1
0x14001b8b4  jnz     short loc_14001B932
0x14001b8b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b8bd  cmp     rcx, r13
0x14001b8c0  jz      short loc_14001B8DE
0x14001b8c2  mov     eax, [rcx+2Ch]
0x14001b8c5  test    al, 4
0x14001b8c7  jz      short loc_14001B8DE
0x14001b8c9  mov     rcx, [rcx+18h]
0x14001b8cd  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001b8d4  mov     edx, 22h ; '"'
0x14001b8d9  call    WPP_SF_
0x14001b8de  mov     r9d, 41h ; 'A'
0x14001b8e4  jmp     loc_14001B7EC
0x14001b8e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b8f0  cmp     rcx, r13
0x14001b8f3  jz      short loc_14001B911
0x14001b8f5  mov     eax, [rcx+2Ch]
0x14001b8f8  test    al, 4
0x14001b8fa  jz      short loc_14001B911
0x14001b8fc  mov     rcx, [rcx+18h]
0x14001b900  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001b907  mov     edx, 1Eh
0x14001b90c  call    WPP_SF_
0x14001b911  mov     r9d, 40h ; '@'
0x14001b917  mov     r8, rbp
0x14001b91a  mov     [rsp+68h+var_48], r14
0x14001b91f  mov     rdx, rsi
0x14001b922  mov     rcx, rbx
0x14001b925  call    MdaSetDispositionInformation
0x14001b92a  mov     ebx, eax
0x14001b92c  test    ebx, ebx
0x14001b92e  jns     short loc_14001B98D
0x14001b930  jmp     short loc_14001B962
0x14001b932  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b939  cmp     rcx, r13
0x14001b93c  jz      short loc_14001B95D
0x14001b93e  mov     eax, [rcx+2Ch]
0x14001b941  test    al, 8
0x14001b943  jz      short loc_14001B95D
0x14001b945  mov     rcx, [rcx+18h]
0x14001b949  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001b950  mov     edx, 24h ; '$'
0x14001b955  mov     r9d, edi
0x14001b958  call    WPP_SF_d
0x14001b95d  mov     ebx, 0C000000Dh
0x14001b962  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b969  cmp     rcx, r13
0x14001b96c  jz      short loc_14001B9B5
0x14001b96e  mov     eax, [rcx+2Ch]
0x14001b971  test    al, 1
0x14001b973  jz      short loc_14001B98D
0x14001b975  mov     rcx, [rcx+18h]
0x14001b979  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001b980  mov     edx, 25h ; '%'
0x14001b985  mov     r9d, ebx
0x14001b988  call    WPP_SF_d
0x14001b98d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b994  cmp     rcx, r13
0x14001b997  jz      short loc_14001B9B5
0x14001b999  mov     eax, [rcx+2Ch]
0x14001b99c  test    al, 8
0x14001b99e  jz      short loc_14001B9B5
0x14001b9a0  mov     rcx, [rcx+18h]
0x14001b9a4  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x14001b9ab  mov     edx, 26h ; '&'
0x14001b9b0  call    WPP_SF_
0x14001b9b5  mov     eax, ebx
0x14001b9b7  lea     r11, [rsp+68h+var_28]
0x14001b9bc  mov     rbx, [r11+38h]
0x14001b9c0  mov     rbp, [r11+40h]
0x14001b9c4  mov     rsp, r11
0x14001b9c7  pop     r15
0x14001b9c9  pop     r14
0x14001b9cb  pop     r13
0x14001b9cd  pop     rdi
0x14001b9ce  pop     rsi
0x14001b9cf  retn
```
