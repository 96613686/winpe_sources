# RebuildHidDeviceList

- ea: `0x180006460`
- end: `0x180006744`
- name: `RebuildHidDeviceList`
- size: `740`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002e40`

## callees

- `0x1800025b8`
- `0x1800025e0`
- `0x1800053a0`
- `0x180005680`
- `0x180005708`
- `0x180006460`
- `0x18000674c`
- `0x180006978`
- `0x1800070f0`
- `0x180008450`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000665a`
- `KERNEL32!GetLastError` at `0x18000665a`
- `HID!HidD_GetHidGuid` at `0x1800064d0`
- `HID!HidD_GetHidGuid` at `0x1800064d0`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180006720`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180006720`
- `DEVOBJ!DevObjCreateClassDeviceInfoList` at `0x1800064ec`
- `DEVOBJ!DevObjCreateClassDeviceInfoList` at `0x1800064ec`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18000664c`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18000664c`

## pseudocode

```c
__int64 __fastcall RebuildHidDeviceList(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rsi
  __int64 v5; // r9
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rax
  __int64 i; // r9
  LPVOID v11; // r8
  __int64 *v12; // rcx
  __int64 *v13; // rdx
  DWORD LastError; // eax
  __int64 v15; // r9
  _QWORD *v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rdi
  LPVOID lpParameter; // [rsp+30h] [rbp-48h] BYREF
  GUID HidGuid; // [rsp+38h] [rbp-40h] BYREF
  _OWORD v21[2]; // [rsp+48h] [rbp-30h] BYREF

  lpParameter = 0;
  memset(v21, 0, sizeof(v21));
  HidGuid = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, a4);
  }
  HidD_GetHidGuid(&HidGuid);
  v4 = DevObjCreateClassDeviceInfoList(&HidGuid, 0, 18);
  if ( v4 == -1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, v5);
    }
    return 0;
  }
  v7 = 0;
  LODWORD(v21[0]) = 32;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, v5);
    v8 = WPP_GLOBAL_Control;
  }
  v9 = HidDeviceList;
  if ( HidDeviceList )
  {
    do
    {
      *(_DWORD *)(v9 + 104) = 0;
      v9 = *(_QWORD *)v9;
    }
    while ( v9 );
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 4u )
    WPP_SF_(v8[2], 13, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, v5);
  for ( i = 0; (unsigned int)DevObjEnumDeviceInterfaces(v4, 0, &HidGuid, i, v21); i = v7 )
  {
    if ( (unsigned int)OpenHidDevice(v4, (__int64)v21, &lpParameter) )
    {
      if ( (unsigned int)StartHidDevice(lpParameter) )
      {
        v11 = lpParameter;
        *(_QWORD *)lpParameter = 0;
        v12 = (__int64 *)HidDeviceList;
        if ( HidDeviceList )
        {
          do
          {
            v13 = v12;
            v12 = (__int64 *)*v12;
          }
          while ( v12 );
        }
        else
        {
          v13 = &HidDeviceList;
        }
        *v13 = (__int64)v11;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids,
            lpParameter);
        }
        FreeHidDevice(lpParameter);
      }
    }
    ++v7;
  }
  LastError = GetLastError();
  if ( LastError == 259 )
    goto LABEL_42;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_43:
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 2) != 0 && *((_BYTE *)v16 + 25) >= 4u )
      {
        WPP_SF_(v16[2], 16, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, v15);
        v16 = WPP_GLOBAL_Control;
      }
      goto LABEL_47;
    }
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, LastError);
LABEL_42:
    v16 = WPP_GLOBAL_Control;
    goto LABEL_43;
  }
LABEL_47:
  v17 = HidDeviceList;
  if ( HidDeviceList )
  {
    do
    {
      v18 = *(_QWORD *)v17;
      if ( !*(_DWORD *)(v17 + 104) )
      {
        if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 2) != 0 && *((_BYTE *)v16 + 25) >= 4u )
          WPP_SF_D(v16[2], 17, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, *(unsigned int *)(v17 + 100));
        RemoveEntryFromList(v16, v17);
        StopHidDevice(v17);
        v16 = WPP_GLOBAL_Control;
      }
      v17 = v18;
    }
    while ( v18 );
  }
  DevObjDestroyDeviceInfoList(v4);
  return 1;
}

```

## disassembly

```asm
0x180006460  push    rbp
0x180006462  push    rbx
0x180006463  push    rsi
0x180006464  push    rdi
0x180006465  push    r12
0x180006467  push    r13
0x180006469  mov     rbp, rsp
0x18000646c  sub     rsp, 78h
0x180006470  mov     rax, cs:__security_cookie
0x180006477  xor     rax, rsp
0x18000647a  mov     [rbp+var_10], rax
0x18000647e  xorps   xmm0, xmm0
0x180006481  mov     [rbp+lpParameter], 0
0x180006489  movups  [rbp+var_30], xmm0
0x18000648d  movups  [rbp+var_20], xmm0
0x180006491  movups  xmmword ptr [rbp+HidGuid.Data1], xmm0
0x180006495  mov     rcx, cs:WPP_GLOBAL_Control
0x18000649c  lea     r12, WPP_GLOBAL_Control
0x1800064a3  lea     r13, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids
0x1800064aa  cmp     rcx, r12
0x1800064ad  jz      short loc_1800064CC
0x1800064af  test    byte ptr [rcx+1Ch], 2
0x1800064b3  jz      short loc_1800064CC
0x1800064b5  cmp     byte ptr [rcx+19h], 5
0x1800064b9  jb      short loc_1800064CC
0x1800064bb  mov     rcx, [rcx+10h]
0x1800064bf  mov     edx, 0Ah
0x1800064c4  mov     r8, r13
0x1800064c7  call    WPP_SF_
0x1800064cc  lea     rcx, [rbp+HidGuid]; HidGuid
0x1800064d0  call    cs:__imp_HidD_GetHidGuid
0x1800064d6  xor     r9d, r9d
0x1800064d9  mov     [rsp+78h+var_58], 0
0x1800064e2  xor     edx, edx
0x1800064e4  lea     rcx, [rbp+HidGuid]
0x1800064e8  lea     r8d, [r9+12h]
0x1800064ec  call    cs:__imp_DevObjCreateClassDeviceInfoList
0x1800064f2  mov     rsi, rax
0x1800064f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800064f9  jnz     short loc_180006529
0x1800064fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006502  cmp     rcx, r12
0x180006505  jz      short loc_180006522
0x180006507  test    byte ptr [rcx+1Ch], 2
0x18000650b  jz      short loc_180006522
0x18000650d  cmp     byte ptr [rcx+19h], 2
0x180006511  jb      short loc_180006522
0x180006513  mov     rcx, [rcx+10h]
0x180006517  lea     edx, [rax+0Ch]
0x18000651a  mov     r8, r13
0x18000651d  call    WPP_SF_
0x180006522  xor     eax, eax
0x180006524  jmp     loc_18000672B
0x180006529  xor     ebx, ebx
0x18000652b  mov     dword ptr [rbp+var_30], 20h ; ' '
0x180006532  mov     rcx, cs:WPP_GLOBAL_Control
0x180006539  mov     dil, 4
0x18000653c  cmp     rcx, r12
0x18000653f  jz      short loc_180006563
0x180006541  test    byte ptr [rcx+1Ch], 2
0x180006545  jz      short loc_180006563
0x180006547  cmp     [rcx+19h], dil
0x18000654b  jb      short loc_180006563
0x18000654d  mov     rcx, [rcx+10h]
0x180006551  lea     edx, [rbx+0Ch]
0x180006554  mov     r8, r13
0x180006557  call    WPP_SF_
0x18000655c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006563  mov     rax, cs:HidDeviceList
0x18000656a  test    rax, rax
0x18000656d  jz      short loc_180006581
0x18000656f  mov     [rax+68h], ebx
0x180006572  mov     rax, [rax]
0x180006575  test    rax, rax
0x180006578  jnz     short loc_18000656F
0x18000657a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006581  cmp     rcx, r12
0x180006584  jz      short loc_1800065A3
0x180006586  test    byte ptr [rcx+1Ch], 2
0x18000658a  jz      short loc_1800065A3
0x18000658c  cmp     [rcx+19h], dil
0x180006590  jb      short loc_1800065A3
0x180006592  mov     rcx, [rcx+10h]
0x180006596  mov     edx, 0Dh
0x18000659b  mov     r8, r13
0x18000659e  call    WPP_SF_
0x1800065a3  xor     r9d, r9d
0x1800065a6  jmp     loc_18000663A
0x1800065ab  lea     r8, [rbp+lpParameter]
0x1800065af  mov     rcx, rsi
0x1800065b2  lea     rdx, [rbp+var_30]
0x1800065b6  call    OpenHidDevice
0x1800065bb  test    eax, eax
0x1800065bd  jz      short loc_180006635
0x1800065bf  mov     rcx, [rbp+lpParameter]; lpParameter
0x1800065c3  call    StartHidDevice
0x1800065c8  test    eax, eax
0x1800065ca  jz      short loc_1800065FF
0x1800065cc  mov     r8, [rbp+lpParameter]
0x1800065d0  mov     qword ptr [r8], 0
0x1800065d7  mov     rcx, cs:HidDeviceList
0x1800065de  test    rcx, rcx
0x1800065e1  jz      short loc_1800065F3
0x1800065e3  mov     rax, [rcx]
0x1800065e6  mov     rdx, rcx
0x1800065e9  mov     rcx, rax
0x1800065ec  test    rax, rax
0x1800065ef  jnz     short loc_1800065E3
0x1800065f1  jmp     short loc_1800065FA
0x1800065f3  lea     rdx, HidDeviceList
0x1800065fa  mov     [rdx], r8
0x1800065fd  jmp     short loc_180006635
0x1800065ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180006606  cmp     rcx, r12
0x180006609  jz      short loc_18000662C
0x18000660b  test    byte ptr [rcx+1Ch], 2
0x18000660f  jz      short loc_18000662C
0x180006611  cmp     byte ptr [rcx+19h], 2
0x180006615  jb      short loc_18000662C
0x180006617  mov     r9, [rbp+lpParameter]
0x18000661b  mov     edx, 0Eh
0x180006620  mov     rcx, [rcx+10h]
0x180006624  mov     r8, r13
0x180006627  call    WPP_SF_q
0x18000662c  mov     rcx, [rbp+lpParameter]
0x180006630  call    FreeHidDevice
0x180006635  inc     ebx
0x180006637  mov     r9d, ebx
0x18000663a  lea     rax, [rbp+var_30]
0x18000663e  xor     edx, edx
0x180006640  lea     r8, [rbp+HidGuid]
0x180006644  mov     [rsp+78h+var_58], rax
0x180006649  mov     rcx, rsi
0x18000664c  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180006652  test    eax, eax
0x180006654  jnz     loc_1800065AB
0x18000665a  call    cs:__imp_GetLastError
0x180006660  cmp     eax, 103h
0x180006665  jz      short loc_180006693
0x180006667  mov     rcx, cs:WPP_GLOBAL_Control
0x18000666e  cmp     rcx, r12
0x180006671  jz      short loc_1800066C3
0x180006673  test    byte ptr [rcx+1Ch], 2
0x180006677  jz      short loc_18000669A
0x180006679  cmp     byte ptr [rcx+19h], 2
0x18000667d  jb      short loc_18000669A
0x18000667f  mov     rcx, [rcx+10h]
0x180006683  mov     edx, 0Fh
0x180006688  mov     r9d, eax
0x18000668b  mov     r8, r13
0x18000668e  call    WPP_SF_D
0x180006693  mov     rcx, cs:WPP_GLOBAL_Control
0x18000669a  cmp     rcx, r12
0x18000669d  jz      short loc_1800066C3
0x18000669f  test    byte ptr [rcx+1Ch], 2
0x1800066a3  jz      short loc_1800066C3
0x1800066a5  cmp     [rcx+19h], dil
0x1800066a9  jb      short loc_1800066C3
0x1800066ab  mov     rcx, [rcx+10h]
0x1800066af  mov     edx, 10h
0x1800066b4  mov     r8, r13
0x1800066b7  call    WPP_SF_
0x1800066bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066c3  mov     rbx, cs:HidDeviceList
0x1800066ca  test    rbx, rbx
0x1800066cd  jz      short loc_18000671D
0x1800066cf  cmp     dword ptr [rbx+68h], 0
0x1800066d3  mov     rdi, [rbx]
0x1800066d6  jnz     short loc_180006715
0x1800066d8  cmp     rcx, r12
0x1800066db  jz      short loc_1800066FE
0x1800066dd  test    byte ptr [rcx+1Ch], 2
0x1800066e1  jz      short loc_1800066FE
0x1800066e3  cmp     byte ptr [rcx+19h], 4
0x1800066e7  jb      short loc_1800066FE
0x1800066e9  mov     r9d, [rbx+64h]
0x1800066ed  mov     edx, 11h
0x1800066f2  mov     rcx, [rcx+10h]
0x1800066f6  mov     r8, r13
0x1800066f9  call    WPP_SF_D
0x1800066fe  mov     rdx, rbx
0x180006701  call    RemoveEntryFromList
0x180006706  mov     rcx, rbx
0x180006709  call    StopHidDevice
0x18000670e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006715  mov     rbx, rdi
0x180006718  test    rdi, rdi
0x18000671b  jnz     short loc_1800066CF
0x18000671d  mov     rcx, rsi
0x180006720  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180006726  mov     eax, 1
0x18000672b  mov     rcx, [rbp+var_10]
0x18000672f  xor     rcx, rsp; StackCookie
0x180006732  call    __security_check_cookie
0x180006737  add     rsp, 78h
0x18000673b  pop     r13
0x18000673d  pop     r12
0x18000673f  pop     rdi
0x180006740  pop     rsi
0x180006741  pop     rbx
0x180006742  pop     rbp
0x180006743  retn
```
