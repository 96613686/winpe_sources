# CMSDiscMasterObj::IsCallLegal(ulong)

- ea: `0x18000c69c`
- end: `0x18000c983`
- name: `?IsCallLegal@CMSDiscMasterObj@@AEAAJK@Z`
- size: `743`
- prototype: `__int64 __fastcall(CMSDiscMasterObj *this, __int16)`
- caller_count: `25`
- callee_count: `2`
- tags: ``

## callers

- `0x180004a40`
- `0x180006430`
- `0x1800064e0`
- `0x180006c20`
- `0x180006d30`
- `0x180007420`
- `0x18000a0c0`
- `0x18000a220`
- `0x18000a430`
- `0x18000a570`
- `0x18000a620`
- `0x18000a6e0`
- `0x18000a7a0`
- `0x18000a860`
- `0x18000b650`
- `0x18000bc60`
- `0x18000be80`
- `0x18000c0f0`
- `0x18000c200`
- `0x18000ce60`
- `0x18000d4d0`
- `0x18000d660`
- `0x18000d830`
- `0x18000e2b0`
- `0x18000e3f0`

## callees

- `0x180007bac`
- `0x18000c69c`

## pseudocode

```c
__int64 __fastcall CMSDiscMasterObj::IsCallLegal(CMSDiscMasterObj *this, __int16 a2)
{
  _BYTE *v2; // rax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  __int64 v7; // rdx

  v2 = (char *)this + 353;
  if ( (a2 & 1) != 0 && !*v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 79, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids);
    return 2147746315LL;
  }
  if ( (a2 & 2) != 0 && *v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 80, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids);
    return 2147746338LL;
  }
  if ( (a2 & 4) != 0
    && *(_QWORD *)((char *)this + 356) == *(_QWORD *)&GUID_NULL.Data1
    && *(_QWORD *)((char *)this + 364) == *(_QWORD *)GUID_NULL.Data4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 81, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids);
    return 2147746335LL;
  }
  if ( (a2 & 8) != 0 && !*((_QWORD *)this + 59) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      return 2147746336LL;
    v5 = 82;
LABEL_44:
    WPP_SF_(v4[7], v5, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids);
    return 2147746336LL;
  }
  if ( (a2 & 0x10) != 0
    && (*(_QWORD *)((char *)this + 356) != *(_QWORD *)&IID_IRedbookDiscMaster.Data1
     || *(_QWORD *)((char *)this + 364) != *(_QWORD *)IID_IRedbookDiscMaster.Data4) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      return 2147746337LL;
    v7 = 83;
LABEL_37:
    WPP_SF_(v6[7], v7, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids);
    return 2147746337LL;
  }
  if ( (a2 & 0x20) != 0
    && (*(_QWORD *)((char *)this + 356) != *(_QWORD *)&IID_IJolietDiscMaster.Data1
     || *(_QWORD *)((char *)this + 364) != *(_QWORD *)IID_IJolietDiscMaster.Data4) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      return 2147746337LL;
    v7 = 84;
    goto LABEL_37;
  }
  if ( (a2 & 0x80u) != 0 && !*((_QWORD *)this + 59) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      return 2147746336LL;
    v5 = 85;
    goto LABEL_44;
  }
  if ( (a2 & 0x100) == 0 || *((_BYTE *)this + 568) )
  {
    if ( (a2 & 0x200) != 0 && *((_BYTE *)this + 568) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 87, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids);
      return 2147746331LL;
    }
    else if ( (a2 & 0x400) != 0 && *((_BYTE *)this + 354) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 88, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids);
      return 262656;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 86, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids);
    return 2147746330LL;
  }
}

```

## disassembly

```asm
0x18000c69c  sub     rsp, 28h
0x18000c6a0  xor     r9d, r9d
0x18000c6a3  lea     rax, [rcx+161h]
0x18000c6aa  mov     r8b, 1
0x18000c6ad  test    r8b, dl
0x18000c6b0  jz      short loc_18000C6EE
0x18000c6b2  cmp     [rax], r9b
0x18000c6b5  jnz     short loc_18000C6EE
0x18000c6b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6be  lea     rax, WPP_GLOBAL_Control
0x18000c6c5  cmp     rcx, rax
0x18000c6c8  jz      short loc_18000C6E4
0x18000c6ca  test    [rcx+44h], r8b
0x18000c6ce  jz      short loc_18000C6E4
0x18000c6d0  mov     rcx, [rcx+38h]
0x18000c6d4  lea     edx, [r9+4Fh]
0x18000c6d8  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000c6df  call    WPP_SF_
0x18000c6e4  mov     eax, 8004020Bh
0x18000c6e9  jmp     loc_18000C97E
0x18000c6ee  test    dl, 2
0x18000c6f1  jz      short loc_18000C730
0x18000c6f3  cmp     [rax], r9b
0x18000c6f6  jz      short loc_18000C730
0x18000c6f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6ff  lea     rax, WPP_GLOBAL_Control
0x18000c706  cmp     rcx, rax
0x18000c709  jz      short loc_18000C726
0x18000c70b  test    [rcx+44h], r8b
0x18000c70f  jz      short loc_18000C726
0x18000c711  mov     rcx, [rcx+38h]
0x18000c715  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000c71c  mov     edx, 50h ; 'P'
0x18000c721  call    WPP_SF_
0x18000c726  mov     eax, 80040222h
0x18000c72b  jmp     loc_18000C97E
0x18000c730  test    dl, 4
0x18000c733  jz      short loc_18000C78D
0x18000c735  mov     rax, [rcx+164h]
0x18000c73c  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18000c743  jnz     short loc_18000C78D
0x18000c745  mov     rax, [rcx+16Ch]
0x18000c74c  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18000c753  jnz     short loc_18000C78D
0x18000c755  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c75c  lea     rax, WPP_GLOBAL_Control
0x18000c763  cmp     rcx, rax
0x18000c766  jz      short loc_18000C783
0x18000c768  test    [rcx+44h], r8b
0x18000c76c  jz      short loc_18000C783
0x18000c76e  mov     rcx, [rcx+38h]
0x18000c772  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000c779  mov     edx, 51h ; 'Q'
0x18000c77e  call    WPP_SF_
0x18000c783  mov     eax, 8004021Fh
0x18000c788  jmp     loc_18000C97E
0x18000c78d  test    dl, 8
0x18000c790  jz      short loc_18000C7C6
0x18000c792  cmp     [rcx+1D8h], r9
0x18000c799  jnz     short loc_18000C7C6
0x18000c79b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7a2  lea     rax, WPP_GLOBAL_Control
0x18000c7a9  cmp     rcx, rax
0x18000c7ac  jz      loc_18000C8A3
0x18000c7b2  test    [rcx+44h], r8b
0x18000c7b6  jz      loc_18000C8A3
0x18000c7bc  mov     edx, 52h ; 'R'
0x18000c7c1  jmp     loc_18000C893
0x18000c7c6  test    dl, 10h
0x18000c7c9  jz      short loc_18000C80B
0x18000c7cb  mov     rax, [rcx+164h]
0x18000c7d2  cmp     rax, qword ptr cs:IID_IRedbookDiscMaster.Data1
0x18000c7d9  jnz     short loc_18000C7EB
0x18000c7db  mov     rax, [rcx+16Ch]
0x18000c7e2  cmp     rax, qword ptr cs:IID_IRedbookDiscMaster.Data4
0x18000c7e9  jz      short loc_18000C80B
0x18000c7eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7f2  lea     rax, WPP_GLOBAL_Control
0x18000c7f9  cmp     rcx, rax
0x18000c7fc  jz      short loc_18000C85E
0x18000c7fe  test    [rcx+44h], r8b
0x18000c802  jz      short loc_18000C85E
0x18000c804  mov     edx, 53h ; 'S'
0x18000c809  jmp     short loc_18000C84E
0x18000c80b  test    dl, 20h
0x18000c80e  jz      short loc_18000C868
0x18000c810  mov     rax, [rcx+164h]
0x18000c817  cmp     rax, qword ptr cs:IID_IJolietDiscMaster.Data1
0x18000c81e  jnz     short loc_18000C830
0x18000c820  mov     rax, [rcx+16Ch]
0x18000c827  cmp     rax, qword ptr cs:IID_IJolietDiscMaster.Data4
0x18000c82e  jz      short loc_18000C868
0x18000c830  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c837  lea     rax, WPP_GLOBAL_Control
0x18000c83e  cmp     rcx, rax
0x18000c841  jz      short loc_18000C85E
0x18000c843  test    [rcx+44h], r8b
0x18000c847  jz      short loc_18000C85E
0x18000c849  mov     edx, 54h ; 'T'
0x18000c84e  mov     rcx, [rcx+38h]
0x18000c852  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000c859  call    WPP_SF_
0x18000c85e  mov     eax, 80040221h
0x18000c863  jmp     loc_18000C97E
0x18000c868  test    dl, dl
0x18000c86a  jns     short loc_18000C8AD
0x18000c86c  cmp     [rcx+1D8h], r9
0x18000c873  jnz     short loc_18000C8AD
0x18000c875  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c87c  lea     rax, WPP_GLOBAL_Control
0x18000c883  cmp     rcx, rax
0x18000c886  jz      short loc_18000C8A3
0x18000c888  test    [rcx+44h], r8b
0x18000c88c  jz      short loc_18000C8A3
0x18000c88e  mov     edx, 55h ; 'U'
0x18000c893  mov     rcx, [rcx+38h]
0x18000c897  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000c89e  call    WPP_SF_
0x18000c8a3  mov     eax, 80040220h
0x18000c8a8  jmp     loc_18000C97E
0x18000c8ad  bt      edx, 8
0x18000c8b1  jnb     short loc_18000C8F4
0x18000c8b3  cmp     [rcx+238h], r9b
0x18000c8ba  jnz     short loc_18000C8F4
0x18000c8bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8c3  lea     rax, WPP_GLOBAL_Control
0x18000c8ca  cmp     rcx, rax
0x18000c8cd  jz      short loc_18000C8EA
0x18000c8cf  test    [rcx+44h], r8b
0x18000c8d3  jz      short loc_18000C8EA
0x18000c8d5  mov     rcx, [rcx+38h]
0x18000c8d9  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000c8e0  mov     edx, 56h ; 'V'
0x18000c8e5  call    WPP_SF_
0x18000c8ea  mov     eax, 8004021Ah
0x18000c8ef  jmp     loc_18000C97E
0x18000c8f4  bt      edx, 9
0x18000c8f8  jnb     short loc_18000C938
0x18000c8fa  cmp     [rcx+238h], r9b
0x18000c901  jz      short loc_18000C938
0x18000c903  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c90a  lea     rax, WPP_GLOBAL_Control
0x18000c911  cmp     rcx, rax
0x18000c914  jz      short loc_18000C931
0x18000c916  test    [rcx+44h], r8b
0x18000c91a  jz      short loc_18000C931
0x18000c91c  mov     rcx, [rcx+38h]
0x18000c920  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000c927  mov     edx, 57h ; 'W'
0x18000c92c  call    WPP_SF_
0x18000c931  mov     eax, 8004021Bh
0x18000c936  jmp     short loc_18000C97E
0x18000c938  bt      edx, 0Ah
0x18000c93c  jnb     short loc_18000C97C
0x18000c93e  cmp     [rcx+162h], r9b
0x18000c945  jz      short loc_18000C97C
0x18000c947  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c94e  lea     rax, WPP_GLOBAL_Control
0x18000c955  cmp     rcx, rax
0x18000c958  jz      short loc_18000C975
0x18000c95a  test    [rcx+44h], r8b
0x18000c95e  jz      short loc_18000C975
0x18000c960  mov     rcx, [rcx+38h]
0x18000c964  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000c96b  mov     edx, 58h ; 'X'
0x18000c970  call    WPP_SF_
0x18000c975  mov     eax, 40200h
0x18000c97a  jmp     short loc_18000C97E
0x18000c97c  xor     eax, eax
0x18000c97e  add     rsp, 28h
0x18000c982  retn
```
