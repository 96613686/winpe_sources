# CFveApiBase::GetLinkedOsVolumeRootForWinReFromBcd(ushort *,ulong)

- ea: `0x180078adc`
- end: `0x180078d98`
- name: `?GetLinkedOsVolumeRootForWinReFromBcd@CFveApiBase@@QEAAJPEAGK@Z`
- size: `700`
- prototype: `int(CFveApiBase *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1800a0988`
- `0x1800b9a84`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x18000aae0`
- `0x18000ba30`
- `0x180018b10`
- `0x180078adc`
- `0x18009ba80`
- `0x18009befc`
- `0x18011f010`

## import_xrefs

- `bcd!BcdCloseObject` at `0x180078d1f`
- `bcd!BcdCloseObject` at `0x180123057`
- `bcd!BcdCloseObject` at `0x180078d1f`
- `bcd!BcdCloseObject` at `0x180123057`
- `bcd!BcdOpenObject` at `0x180078c27`
- `bcd!BcdOpenObject` at `0x180078c27`
- `bcd!BcdCloseStore` at `0x180078d3f`
- `bcd!BcdCloseStore` at `0x18012306d`
- `bcd!BcdCloseStore` at `0x180078d3f`
- `bcd!BcdCloseStore` at `0x18012306d`
- `bcd!BcdOpenSystemStore` at `0x180078b9a`
- `bcd!BcdOpenSystemStore` at `0x180078b9a`

## pseudocode

```c
__int64 __fastcall CFveApiBase::GetLinkedOsVolumeRootForWinReFromBcd(CFveApiBase *this, unsigned __int16 *a2)
{
  PVOID *v3; // rcx
  unsigned int v4; // ebx
  int v5; // eax
  int AssociatedOs; // eax
  __int64 v7; // rdx
  int v8; // eax
  void *lpMem; // [rsp+28h] [rbp-40h] BYREF
  unsigned int v11; // [rsp+30h] [rbp-38h] BYREF
  void *v12; // [rsp+38h] [rbp-30h] BYREF
  void *v13; // [rsp+40h] [rbp-28h] BYREF
  struct _GUID v14; // [rsp+48h] [rbp-20h] BYREF

  v14 = 0;
  v12 = 0;
  v13 = 0;
  lpMem = 0;
  v11 = 0;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, &WPP_232a563e2194333b5335056010c74b6d_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    v4 = -2147467261;
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 )
    {
      WPP_SF_(v3[2], 118, &WPP_232a563e2194333b5335056010c74b6d_Traceguids);
LABEL_29:
      v3 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  v5 = BcdOpenSystemStore(&v12, a2);
  AssociatedOs = FromNtStatus(v5);
  v4 = AssociatedOs;
  if ( AssociatedOs < 0 )
  {
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_30;
    v7 = 119;
    goto LABEL_28;
  }
  AssociatedOs = CFveApiBase::GetAssociatedOs(v12, &v14);
  v4 = AssociatedOs;
  if ( AssociatedOs < 0 )
  {
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_30;
    v7 = 120;
    goto LABEL_28;
  }
  v8 = BcdOpenObject(v12, &v14, &v13);
  AssociatedOs = FromNtStatus(v8);
  v4 = AssociatedOs;
  if ( AssociatedOs < 0 )
  {
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_30;
    v7 = 121;
    goto LABEL_28;
  }
  AssociatedOs = CFveApiBase::GetBcdElementData(v13, 0x21000001u, &lpMem, &v11);
  v4 = AssociatedOs;
  if ( AssociatedOs < 0 )
  {
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_30;
    v7 = 122;
LABEL_28:
    WPP_SF_d(v3[2], v7, &WPP_232a563e2194333b5335056010c74b6d_Traceguids, (unsigned int)AssociatedOs);
    goto LABEL_29;
  }
  AssociatedOs = StringCchPrintfW(a2, 0x105u, L"\\\\?\\GLOBALROOT%s", (char *)lpMem + 20, AssociatedOs);
  v4 = AssociatedOs;
  if ( AssociatedOs >= 0 )
    goto LABEL_29;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v7 = 123;
    goto LABEL_28;
  }
LABEL_30:
  if ( lpMem )
  {
    CFveApiBase::FastFree(lpMem);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 )
  {
    BcdCloseObject(v13);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 )
  {
    BcdCloseStore(v12, a2);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x20) != 0 )
    WPP_SF_d(v3[2], 124, &WPP_232a563e2194333b5335056010c74b6d_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180078adc  mov     r11, rsp
0x180078adf  mov     [r11+8], rbx
0x180078ae3  mov     [r11+18h], rsi
0x180078ae7  push    r15
0x180078ae9  sub     rsp, 60h
0x180078aed  mov     rax, cs:__security_cookie
0x180078af4  xor     rax, rsp
0x180078af7  mov     [rsp+68h+var_10], rax
0x180078afc  mov     rsi, rdx
0x180078aff  xorps   xmm0, xmm0
0x180078b02  movups  xmmword ptr [rsp+68h+var_20.Data1], xmm0
0x180078b07  mov     qword ptr [r11-30h], 0
0x180078b0f  mov     qword ptr [r11-28h], 0
0x180078b17  mov     qword ptr [r11-40h], 0
0x180078b1f  mov     [rsp+68h+var_38], 0
0x180078b27  lea     r15, WPP_GLOBAL_Control
0x180078b2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180078b35  cmp     rcx, r15
0x180078b38  jz      short loc_180078B5C
0x180078b3a  test    byte ptr [rcx+1Ch], 20h
0x180078b3e  jz      short loc_180078B5C
0x180078b40  mov     edx, 75h ; 'u'
0x180078b45  lea     r8, WPP_232a563e2194333b5335056010c74b6d_Traceguids
0x180078b4c  mov     rcx, [rcx+10h]
0x180078b50  call    WPP_SF_
0x180078b55  mov     rcx, cs:WPP_GLOBAL_Control
0x180078b5c  test    rsi, rsi
0x180078b5f  jnz     short loc_180078B95
0x180078b61  mov     ebx, 80004003h
0x180078b66  mov     [rsp+68h+var_48], ebx
0x180078b6a  cmp     rcx, r15
0x180078b6d  jz      loc_180078CF9
0x180078b73  test    byte ptr [rcx+1Ch], 2
0x180078b77  jz      loc_180078CF9
0x180078b7d  lea     edx, [rsi+76h]
0x180078b80  lea     r8, WPP_232a563e2194333b5335056010c74b6d_Traceguids
0x180078b87  mov     rcx, [rcx+10h]
0x180078b8b  call    WPP_SF_
0x180078b90  jmp     loc_180078CF2
0x180078b95  lea     rcx, [rsp+68h+var_30]
0x180078b9a  call    cs:__imp_BcdOpenSystemStore
0x180078ba1  nop     dword ptr [rax+rax+00h]
0x180078ba6  mov     ecx, eax; int
0x180078ba8  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180078bad  mov     ebx, eax
0x180078baf  mov     [rsp+68h+var_48], eax
0x180078bb3  test    eax, eax
0x180078bb5  jns     short loc_180078BDB
0x180078bb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180078bbe  cmp     rcx, r15
0x180078bc1  jz      loc_180078CF9
0x180078bc7  test    byte ptr [rcx+1Ch], 2
0x180078bcb  jz      loc_180078CF9
0x180078bd1  mov     edx, 77h ; 'w'
0x180078bd6  jmp     loc_180078CDF
0x180078bdb  lea     rdx, [rsp+68h+var_20]; struct _GUID *
0x180078be0  mov     rcx, [rsp+68h+var_30]; void *
0x180078be5  call    ?GetAssociatedOs@CFveApiBase@@KAJPEAXPEAU_GUID@@@Z; CFveApiBase::GetAssociatedOs(void *,_GUID *)
0x180078bea  mov     ebx, eax
0x180078bec  mov     [rsp+68h+var_48], eax
0x180078bf0  test    eax, eax
0x180078bf2  jns     short loc_180078C18
0x180078bf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180078bfb  cmp     rcx, r15
0x180078bfe  jz      loc_180078CF9
0x180078c04  test    byte ptr [rcx+1Ch], 2
0x180078c08  jz      loc_180078CF9
0x180078c0e  mov     edx, 78h ; 'x'
0x180078c13  jmp     loc_180078CDF
0x180078c18  lea     r8, [rsp+68h+var_28]
0x180078c1d  lea     rdx, [rsp+68h+var_20]
0x180078c22  mov     rcx, [rsp+68h+var_30]
0x180078c27  call    cs:__imp_BcdOpenObject
0x180078c2e  nop     dword ptr [rax+rax+00h]
0x180078c33  mov     ecx, eax; int
0x180078c35  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180078c3a  mov     ebx, eax
0x180078c3c  mov     [rsp+68h+var_48], eax
0x180078c40  test    eax, eax
0x180078c42  jns     short loc_180078C65
0x180078c44  mov     rcx, cs:WPP_GLOBAL_Control
0x180078c4b  cmp     rcx, r15
0x180078c4e  jz      loc_180078CF9
0x180078c54  test    byte ptr [rcx+1Ch], 2
0x180078c58  jz      loc_180078CF9
0x180078c5e  mov     edx, 79h ; 'y'
0x180078c63  jmp     short loc_180078CDF
0x180078c65  lea     r9, [rsp+68h+var_38]; unsigned int *
0x180078c6a  lea     r8, [rsp+68h+lpMem]; void **
0x180078c6f  mov     edx, 21000001h; unsigned int
0x180078c74  mov     rcx, [rsp+68h+var_28]; void *
0x180078c79  call    ?GetBcdElementData@CFveApiBase@@SAJPEAXKPEAPEAXPEAK@Z; CFveApiBase::GetBcdElementData(void *,ulong,void * *,ulong *)
0x180078c7e  mov     ebx, eax
0x180078c80  mov     [rsp+68h+var_48], eax
0x180078c84  test    eax, eax
0x180078c86  jns     short loc_180078CA1
0x180078c88  mov     rcx, cs:WPP_GLOBAL_Control
0x180078c8f  cmp     rcx, r15
0x180078c92  jz      short loc_180078CF9
0x180078c94  test    byte ptr [rcx+1Ch], 2
0x180078c98  jz      short loc_180078CF9
0x180078c9a  mov     edx, 7Ah ; 'z'
0x180078c9f  jmp     short loc_180078CDF
0x180078ca1  mov     r9, [rsp+68h+lpMem]
0x180078ca6  add     r9, 14h
0x180078caa  lea     r8, aGlobalrootS; "\\\\?\\GLOBALROOT%s"
0x180078cb1  mov     edx, 105h; unsigned __int64
0x180078cb6  mov     rcx, rsi; unsigned __int16 *
0x180078cb9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180078cbe  mov     ebx, eax
0x180078cc0  mov     [rsp+68h+var_48], eax
0x180078cc4  test    eax, eax
0x180078cc6  jns     short loc_180078CF2
0x180078cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180078ccf  cmp     rcx, r15
0x180078cd2  jz      short loc_180078CF9
0x180078cd4  test    byte ptr [rcx+1Ch], 2
0x180078cd8  jz      short loc_180078CF9
0x180078cda  mov     edx, 7Bh ; '{'
0x180078cdf  mov     r9d, eax
0x180078ce2  lea     r8, WPP_232a563e2194333b5335056010c74b6d_Traceguids
0x180078ce9  mov     rcx, [rcx+10h]
0x180078ced  call    WPP_SF_d
0x180078cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180078cf9  mov     rax, [rsp+68h+lpMem]
0x180078cfe  test    rax, rax
0x180078d01  jz      short loc_180078D12
0x180078d03  mov     rcx, rax; lpMem
0x180078d06  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180078d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180078d12  mov     rax, [rsp+68h+var_28]
0x180078d17  test    rax, rax
0x180078d1a  jz      short loc_180078D32
0x180078d1c  mov     rcx, rax
0x180078d1f  call    cs:__imp_BcdCloseObject
0x180078d26  nop     dword ptr [rax+rax+00h]
0x180078d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180078d32  mov     rax, [rsp+68h+var_30]
0x180078d37  test    rax, rax
0x180078d3a  jz      short loc_180078D52
0x180078d3c  mov     rcx, rax
0x180078d3f  call    cs:__imp_BcdCloseStore
0x180078d46  nop     dword ptr [rax+rax+00h]
0x180078d4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180078d52  cmp     rcx, r15
0x180078d55  jz      short loc_180078D75
0x180078d57  test    byte ptr [rcx+1Ch], 20h
0x180078d5b  jz      short loc_180078D75
0x180078d5d  mov     edx, 7Ch ; '|'
0x180078d62  mov     r9d, ebx
0x180078d65  lea     r8, WPP_232a563e2194333b5335056010c74b6d_Traceguids
0x180078d6c  mov     rcx, [rcx+10h]
0x180078d70  call    WPP_SF_d
0x180078d75  mov     eax, ebx
0x180078d77  mov     rcx, [rsp+68h+var_10]
0x180078d7c  xor     rcx, rsp; StackCookie
0x180078d7f  call    __security_check_cookie
0x180078d84  lea     r11, [rsp+68h+var_8]
0x180078d89  mov     rbx, [r11+10h]
0x180078d8d  mov     rsi, [r11+20h]
0x180078d91  mov     rsp, r11
0x180078d94  pop     r15
0x180078d96  retn
0x180123036  push    rbp
0x180123038  sub     rsp, 20h
0x18012303c  mov     rbp, rdx
0x18012303f  mov     rcx, [rbp+28h]; lpMem
0x180123043  test    rcx, rcx
0x180123046  jz      short loc_18012304E
0x180123048  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18012304d  nop
0x18012304e  mov     rcx, [rbp+40h]
0x180123052  test    rcx, rcx
0x180123055  jz      short loc_180123064
0x180123057  call    cs:__imp_BcdCloseObject
0x18012305e  nop     dword ptr [rax+rax+00h]
0x180123063  nop
0x180123064  mov     rcx, [rbp+38h]
0x180123068  test    rcx, rcx
0x18012306b  jz      short loc_18012307A
0x18012306d  call    cs:__imp_BcdCloseStore
0x180123074  nop     dword ptr [rax+rax+00h]
0x180123079  nop
0x18012307a  add     rsp, 20h
0x18012307e  pop     rbp
0x18012307f  retn
```
