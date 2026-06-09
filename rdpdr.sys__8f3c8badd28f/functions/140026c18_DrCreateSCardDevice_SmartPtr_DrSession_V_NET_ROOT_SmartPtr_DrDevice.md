# DrCreateSCardDevice(SmartPtr<DrSession> &,_V_NET_ROOT *,SmartPtr<DrDevice> &)

- ea: `0x140026c18`
- end: `0x140026f8a`
- name: `?DrCreateSCardDevice@@YAJAEAV?$SmartPtr@VDrSession@@@@PEAU_V_NET_ROOT@@AEAV?$SmartPtr@VDrDevice@@@@@Z`
- size: `882`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `14`
- tags: ``

## callers

- `0x140001350`
- `0x140025c40`
- `0x140026380`

## callees

- `0x140001310`
- `0x140001660`
- `0x140001830`
- `0x140001890`
- `0x140002c60`
- `0x14000324c`
- `0x14000327c`
- `0x1400036c0`
- `0x140003940`
- `0x14000594c`
- `0x140006560`
- `0x1400268e0`
- `0x140026c18`
- `0x140029c90`

## pseudocode

```c
__int64 __fastcall DrCreateSCardDevice(_QWORD *a1, unsigned __int64 a2, RefCount **a3)
{
  __int64 v6; // r15
  char *v7; // rax
  int v8; // r8d
  char *v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // rax
  const char *v12; // r9
  __int64 v13; // rdx
  _BYTE *v14; // rcx
  _BYTE *v15; // rax
  __int64 v16; // rax
  int v17; // ebx

  v6 = 0;
  if ( a2 )
    v6 = *(_QWORD *)(a2 + 32);
  v7 = (char *)TopObj::operator new(0xF0u, a2);
  v9 = v7;
  if ( v7 )
  {
    v7[8] = 1;
    *(_QWORD *)(v7 + 12) = 0;
    *(_QWORD *)v7 = &DrDevice::`vftable'{for `RefCount'};
    *((_QWORD *)v7 + 3) = &DrParallelPort::`vftable'{for `IExchangeUser'};
    *((_QWORD *)v7 + 4) = 0;
    v10 = -1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_qqdds(
        WPP_GLOBAL_Control->AttachedDevice,
        (unsigned int)"SCARD",
        v8,
        (_DWORD)v7,
        *a1,
        32,
        -1,
        (__int64)"SCARD");
    SmartPtr<VirtualChannel>::operator=(v9 + 32, *a1);
    v11 = 2147483646;
    *((_DWORD *)v9 + 11) = 32;
    v12 = "SCARD";
    *((_DWORD *)v9 + 10) = -1;
    v13 = 8;
    *((_DWORD *)v9 + 14) = 0;
    v14 = v9 + 48;
    do
    {
      if ( !v11 )
        break;
      if ( !*v12 )
        break;
      *v14++ = *v12++;
      --v11;
      --v13;
    }
    while ( v13 );
    v15 = v14 - 1;
    if ( v13 )
      v15 = v14;
    *v15 = 0;
    do
      ++v10;
    while ( v9[v10 + 48] );
    if ( (_DWORD)v10 )
    {
      v16 = (unsigned int)(v10 - 1);
      if ( v9[v16 + 48] == 58 )
        v9[v16 + 48] = 0;
    }
    *((_DWORD *)v9 + 15) = 0;
    *(_QWORD *)v9 = &DrSmartCard::`vftable'{for `RefCount'};
    *((_QWORD *)v9 + 3) = &DrParallelPort::`vftable'{for `IExchangeUser'};
    v9[88] = 1;
    *((_QWORD *)v9 + 10) = &DoubleList::`vftable';
    *((_DWORD *)v9 + 23) = 0;
    KernelResource::KernelResource((KernelResource *)(v9 + 112), "MidList");
    *((_QWORD *)v9 + 13) = v9 + 96;
    *((_QWORD *)v9 + 12) = v9 + 96;
    *(_QWORD *)(v9 + 68) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids, v9);
  }
  else
  {
    v9 = 0;
  }
  if ( *a3 )
    RefCount::Release(*a3);
  *a3 = (RefCount *)v9;
  if ( v9 )
    RefCount::AddRef((RefCount *)v9);
  if ( *a3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids);
    v17 = (*(__int64 (__fastcall **)(RefCount *, _QWORD, _QWORD, __int64))(*(_QWORD *)*a3 + 48LL))(*a3, 0, 0, 2);
    if ( v17 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids);
      SmartPtr<DrDevice>::operator=(a3, 0);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids);
      *((_DWORD *)*a3 + 14) = 0;
      if ( (unsigned int)DrDeviceManager::AddDevice(*a1 + 912LL, a3) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids);
        goto LABEL_38;
      }
      SmartPtr<DrDevice>::operator=(a3, 0);
      if ( (unsigned int)DrDeviceManager::FindDeviceByDosName(*a1 + 912LL, "SCARD", a3) )
      {
LABEL_38:
        if ( a2 )
        {
          RefCount::AddRef(*a3);
          *(_QWORD *)(a2 + 40) = *a3;
          *(_DWORD *)(v6 + 80) = 7;
          *(_BYTE *)(v6 + 77) = 0;
        }
        return 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids);
      return (unsigned int)-1073741620;
    }
  }
  else
  {
    v17 = -1073741620;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids, 3221225676LL);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140026c18  push    rbx
0x140026c1a  push    rbp
0x140026c1b  push    rsi
0x140026c1c  push    rdi
0x140026c1d  push    r12
0x140026c1f  push    r13
0x140026c21  push    r14
0x140026c23  push    r15
0x140026c25  sub     rsp, 48h
0x140026c29  xor     r13d, r13d
0x140026c2c  mov     rsi, r8
0x140026c2f  mov     rbp, rdx
0x140026c32  mov     r12, rcx
0x140026c35  mov     r15d, r13d
0x140026c38  test    rdx, rdx
0x140026c3b  jz      short loc_140026C41
0x140026c3d  mov     r15, [rdx+20h]
0x140026c41  mov     ecx, 0F0h; unsigned __int64
0x140026c46  call    ??2TopObj@@SAPEAX_K0@Z; TopObj::operator new(unsigned __int64,unsigned __int64)
0x140026c4b  lea     r14, WPP_GLOBAL_Control
0x140026c52  mov     rbx, rax
0x140026c55  lea     rdx, Str1; "SCARD"
0x140026c5c  test    rax, rax
0x140026c5f  jz      loc_140026DC5
0x140026c65  mov     byte ptr [rax+8], 1
0x140026c69  mov     [rax+0Ch], r13
0x140026c6d  lea     rax, ??_7DrDevice@@6BRefCount@@@; const DrDevice::`vftable'{for `RefCount'}
0x140026c74  mov     [rbx], rax
0x140026c77  lea     rax, ??_7DrParallelPort@@6BIExchangeUser@@@; const DrParallelPort::`vftable'{for `IExchangeUser'}
0x140026c7e  mov     [rbx+18h], rax
0x140026c82  mov     [rbx+20h], r13
0x140026c86  mov     rcx, cs:WPP_GLOBAL_Control
0x140026c8d  lea     rax, WPP_GLOBAL_Control
0x140026c94  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140026c98  cmp     rcx, rax
0x140026c9b  jz      short loc_140026CC9
0x140026c9d  cmp     byte ptr [rcx+29h], 4
0x140026ca1  jb      short loc_140026CC9
0x140026ca3  mov     rax, [r12]
0x140026ca7  mov     r9, rbx
0x140026caa  mov     rcx, [rcx+18h]
0x140026cae  mov     [rsp+88h+var_50], rdx
0x140026cb3  mov     [rsp+88h+var_58], edi
0x140026cb7  mov     [rsp+88h+var_60], 20h ; ' '
0x140026cbf  mov     [rsp+88h+var_68], rax
0x140026cc4  call    WPP_SF_qqdds
0x140026cc9  mov     rdx, [r12]
0x140026ccd  lea     rcx, [rbx+20h]
0x140026cd1  call    ??4?$SmartPtr@VVirtualChannel@@@@QEAAAEAV0@PEAVVirtualChannel@@@Z; SmartPtr<VirtualChannel>::operator=(VirtualChannel *)
0x140026cd6  mov     eax, 7FFFFFFEh
0x140026cdb  mov     dword ptr [rbx+2Ch], 20h ; ' '
0x140026ce2  lea     r9, Str1; "SCARD"
0x140026ce9  mov     dword ptr [rbx+28h], 0FFFFFFFFh
0x140026cf0  mov     edx, 8
0x140026cf5  mov     [rbx+38h], r13d
0x140026cf9  lea     rcx, [rbx+30h]
0x140026cfd  test    rax, rax
0x140026d00  jz      short loc_140026D1C
0x140026d02  mov     r8b, [r9]
0x140026d05  test    r8b, r8b
0x140026d08  jz      short loc_140026D1C
0x140026d0a  mov     [rcx], r8b
0x140026d0d  inc     r9
0x140026d10  inc     rcx
0x140026d13  dec     rax
0x140026d16  sub     rdx, 1
0x140026d1a  jnz     short loc_140026CFD
0x140026d1c  test    rdx, rdx
0x140026d1f  lea     rax, [rcx-1]
0x140026d23  cmovnz  rax, rcx
0x140026d27  mov     [rax], r13b
0x140026d2a  inc     rdi
0x140026d2d  cmp     [rbx+rdi+30h], r13b
0x140026d32  jnz     short loc_140026D2A
0x140026d34  test    edi, edi
0x140026d36  jz      short loc_140026D47
0x140026d38  lea     eax, [rdi-1]
0x140026d3b  cmp     byte ptr [rax+rbx+30h], 3Ah ; ':'
0x140026d40  jnz     short loc_140026D47
0x140026d42  mov     [rax+rbx+30h], r13b
0x140026d47  mov     [rbx+3Ch], r13d
0x140026d4b  lea     rax, ??_7DrSmartCard@@6BRefCount@@@; const DrSmartCard::`vftable'{for `RefCount'}
0x140026d52  mov     [rbx], rax
0x140026d55  lea     rcx, [rbx+70h]; this
0x140026d59  lea     rax, ??_7DrParallelPort@@6BIExchangeUser@@@; const DrParallelPort::`vftable'{for `IExchangeUser'}
0x140026d60  mov     [rbx+18h], rax
0x140026d64  lea     rdx, aMidlist; "MidList"
0x140026d6b  lea     rax, ??_7DoubleList@@6B@; const DoubleList::`vftable'
0x140026d72  mov     byte ptr [rbx+58h], 1
0x140026d76  mov     [rbx+50h], rax
0x140026d7a  mov     [rbx+5Ch], r13d
0x140026d7e  call    ??0KernelResource@@QEAA@PEBD@Z; KernelResource::KernelResource(char const *)
0x140026d83  lea     rax, [rbx+60h]
0x140026d87  mov     [rax+8], rax
0x140026d8b  mov     [rax], rax
0x140026d8e  mov     [rbx+44h], r13
0x140026d92  mov     rcx, cs:WPP_GLOBAL_Control
0x140026d99  lea     r14, WPP_GLOBAL_Control
0x140026da0  cmp     rcx, r14
0x140026da3  jz      short loc_140026DC8
0x140026da5  cmp     byte ptr [rcx+29h], 4
0x140026da9  jb      short loc_140026DC8
0x140026dab  mov     rcx, [rcx+18h]
0x140026daf  lea     r8, WPP_25868b0bbdc333c7b90438191bab8343_Traceguids
0x140026db6  mov     edx, 0Ah
0x140026dbb  mov     r9, rbx
0x140026dbe  call    WPP_SF_q
0x140026dc3  jmp     short loc_140026DC8
0x140026dc5  mov     rbx, r13
0x140026dc8  mov     rcx, [rsi]; this
0x140026dcb  test    rcx, rcx
0x140026dce  jz      short loc_140026DD5
0x140026dd0  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140026dd5  mov     [rsi], rbx
0x140026dd8  test    rbx, rbx
0x140026ddb  jz      short loc_140026DE5
0x140026ddd  mov     rcx, rbx; this
0x140026de0  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140026de5  cmp     [rsi], r13
0x140026de8  jz      loc_140026F44
0x140026dee  mov     rcx, cs:WPP_GLOBAL_Control
0x140026df5  lea     rdi, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids
0x140026dfc  cmp     rcx, r14
0x140026dff  jz      short loc_140026E18
0x140026e01  cmp     byte ptr [rcx+29h], 5
0x140026e05  jb      short loc_140026E18
0x140026e07  mov     rcx, [rcx+18h]
0x140026e0b  mov     edx, 11h
0x140026e10  mov     r8, rdi
0x140026e13  call    WPP_SF_
0x140026e18  mov     rcx, [rsi]
0x140026e1b  mov     r9d, 2
0x140026e21  xor     r8d, r8d
0x140026e24  xor     edx, edx
0x140026e26  mov     rax, [rcx]
0x140026e29  mov     rax, [rax+30h]
0x140026e2d  call    _guard_dispatch_icall
0x140026e32  mov     ebx, eax
0x140026e34  test    eax, eax
0x140026e36  js      loc_140026F15
0x140026e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140026e43  cmp     rcx, r14
0x140026e46  jz      short loc_140026E5F
0x140026e48  cmp     byte ptr [rcx+29h], 5
0x140026e4c  jb      short loc_140026E5F
0x140026e4e  mov     rcx, [rcx+18h]
0x140026e52  mov     edx, 12h
0x140026e57  mov     r8, rdi
0x140026e5a  call    WPP_SF_
0x140026e5f  mov     rax, [rsi]
0x140026e62  mov     ebx, 390h
0x140026e67  mov     rdx, rsi
0x140026e6a  mov     [rax+38h], r13d
0x140026e6e  mov     rcx, [r12]
0x140026e72  add     rcx, rbx
0x140026e75  call    ?AddDevice@DrDeviceManager@@QEAAHAEAV?$SmartPtr@VDrDevice@@@@@Z; DrDeviceManager::AddDevice(SmartPtr<DrDevice> &)
0x140026e7a  test    eax, eax
0x140026e7c  jz      short loc_140026EC9
0x140026e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140026e85  cmp     rcx, r14
0x140026e88  jz      short loc_140026EA1
0x140026e8a  cmp     byte ptr [rcx+29h], 5
0x140026e8e  jb      short loc_140026EA1
0x140026e90  mov     rcx, [rcx+18h]
0x140026e94  mov     edx, 13h
0x140026e99  mov     r8, rdi
0x140026e9c  call    WPP_SF_
0x140026ea1  test    rbp, rbp
0x140026ea4  jz      short loc_140026EC1
0x140026ea6  mov     rcx, [rsi]; this
0x140026ea9  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140026eae  mov     rax, [rsi]
0x140026eb1  mov     [rbp+28h], rax
0x140026eb5  mov     dword ptr [r15+50h], 7
0x140026ebd  mov     [r15+4Dh], r13b
0x140026ec1  mov     ebx, r13d
0x140026ec4  jmp     loc_140026F76
0x140026ec9  xor     edx, edx
0x140026ecb  mov     rcx, rsi
0x140026ece  call    ??4?$SmartPtr@VDrDevice@@@@QEAAAEAV0@PEAVDrDevice@@@Z; SmartPtr<DrDevice>::operator=(DrDevice *)
0x140026ed3  mov     rcx, [r12]
0x140026ed7  lea     rdx, Str1; "SCARD"
0x140026ede  add     rcx, rbx
0x140026ee1  mov     r8, rsi
0x140026ee4  call    ?FindDeviceByDosName@DrDeviceManager@@QEAAHPEAEAEAV?$SmartPtr@VDrDevice@@@@H@Z; DrDeviceManager::FindDeviceByDosName(uchar *,SmartPtr<DrDevice> &,int)
0x140026ee9  test    eax, eax
0x140026eeb  jnz     short loc_140026EA1
0x140026eed  mov     rcx, cs:WPP_GLOBAL_Control
0x140026ef4  cmp     rcx, r14
0x140026ef7  jz      short loc_140026F0E
0x140026ef9  cmp     byte ptr [rcx+29h], 2
0x140026efd  jb      short loc_140026F0E
0x140026eff  mov     rcx, [rcx+18h]
0x140026f03  lea     edx, [rax+14h]
0x140026f06  mov     r8, rdi
0x140026f09  call    WPP_SF_
0x140026f0e  mov     ebx, 0C00000CCh
0x140026f13  jmp     short loc_140026F76
0x140026f15  mov     rcx, cs:WPP_GLOBAL_Control
0x140026f1c  cmp     rcx, r14
0x140026f1f  jz      short loc_140026F38
0x140026f21  cmp     byte ptr [rcx+29h], 2
0x140026f25  jb      short loc_140026F38
0x140026f27  mov     rcx, [rcx+18h]
0x140026f2b  mov     edx, 15h
0x140026f30  mov     r8, rdi
0x140026f33  call    WPP_SF_
0x140026f38  xor     edx, edx
0x140026f3a  mov     rcx, rsi
0x140026f3d  call    ??4?$SmartPtr@VDrDevice@@@@QEAAAEAV0@PEAVDrDevice@@@Z; SmartPtr<DrDevice>::operator=(DrDevice *)
0x140026f42  jmp     short loc_140026F76
0x140026f44  mov     rcx, cs:WPP_GLOBAL_Control
0x140026f4b  mov     ebx, 0C00000CCh
0x140026f50  cmp     rcx, r14
0x140026f53  jz      short loc_140026F76
0x140026f55  cmp     byte ptr [rcx+29h], 2
0x140026f59  jb      short loc_140026F76
0x140026f5b  mov     rcx, [rcx+18h]
0x140026f5f  lea     r8, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids
0x140026f66  mov     edx, 16h
0x140026f6b  mov     r9d, 0C00000CCh
0x140026f71  call    WPP_SF_d
0x140026f76  mov     eax, ebx
0x140026f78  add     rsp, 48h
0x140026f7c  pop     r15
0x140026f7e  pop     r14
0x140026f80  pop     r13
0x140026f82  pop     r12
0x140026f84  pop     rdi
0x140026f85  pop     rsi
0x140026f86  pop     rbp
0x140026f87  pop     rbx
0x140026f88  retn
```
