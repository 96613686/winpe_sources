# CTSThreadInternal_CreateInstance

- ea: `0x1800290fc`
- end: `0x1800292c6`
- name: `CTSThreadInternal_CreateInstance`
- size: `458`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180025520`

## callees

- `0x1800032d4`
- `0x18000f08c`
- `0x18001d098`
- `0x18001d114`
- `0x1800290fc`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x18002913b`: `CTSThreadInternal`
- `0x180029286`: `CTSThreadInternal`

## pseudocode

```c
__int64 __fastcall CTSThreadInternal_CreateInstance(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  _QWORD *v8; // rbx
  __int64 (__fastcall **v9)(_QWORD *, GUID *, _QWORD); // rax
  int v10; // ebx
  __int64 v11; // r8
  __int64 v12; // r9
  int ActivityIdPrefix; // eax
  int v14; // eax
  _QWORD *v16; // [rsp+48h] [rbp+10h] BYREF

  v16 = 0;
  v4 = operator new(0x60u);
  v8 = v4;
  if ( v4 )
  {
    *v4 = &ITSThreadInternal::`vftable';
    *((_DWORD *)v4 + 8) = -607474739;
    v4[3] = "CTSThreadInternal";
    *((_DWORD *)v4 + 9) = 1;
    v4[1] = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
    v4[2] = &CTSUnknown::`vftable'{for `CTSObject'};
    *((_DWORD *)v4 + 12) = 0;
    v4[5] = v4 + 1;
    *v4 = &CTSThreadInternal::`vftable';
    v4[1] = &CTSThreadInternal::`vftable'{for `INonDelegatingUnknown'};
    v4[2] = &CTSThreadInternal::`vftable'{for `CTSObject'};
    v4[7] = 0;
    v4[8] = 0;
    v4[9] = 0;
    v4[10] = 0;
    *((_DWORD *)v4 + 22) = 0;
    TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v16);
    v9 = (__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD))*v8;
    v16 = v8;
    ((void (__fastcall *)(_QWORD *))v9[1])(v8);
    v10 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64))*v8)(v8, &IID_ITSThreadInternal, a3);
    if ( v10 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, WPP_GLOBAL_Control, v11, v12);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_73b49cc1326e3e16b22d457759b24fb0_Traceguids,
        ActivityIdPrefix,
        (__int64)"Failed to QI",
        v10);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v5, v6, v7);
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_73b49cc1326e3e16b22d457759b24fb0_Traceguids,
        v14,
        (__int64)"CTSThreadInternal");
    }
    v10 = -2147024882;
  }
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v16);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800290fc  mov     [rsp+arg_0], rbx
0x180029101  mov     [rsp+arg_8], rdx
0x180029106  push    rdi
0x180029107  sub     rsp, 30h
0x18002910b  mov     ecx, 60h ; '`'; Size
0x180029110  mov     [rsp+38h+arg_8], 0
0x180029119  mov     rdi, r8
0x18002911c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029121  mov     rbx, rax
0x180029124  test    rax, rax
0x180029127  jz      loc_18002925B
0x18002912d  lea     rcx, [rbx+8]
0x180029131  lea     rax, ??_7ITSThreadInternal@@6B@; const ITSThreadInternal::`vftable'
0x180029138  mov     [rbx], rax
0x18002913b  lea     r8, aCtsthreadinter; "CTSThreadInternal"
0x180029142  mov     dword ptr [rcx+18h], 0DBCAABCDh
0x180029149  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x180029150  mov     [rcx+10h], r8
0x180029154  mov     dword ptr [rcx+1Ch], 1
0x18002915b  mov     [rcx], rax
0x18002915e  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180029165  mov     [rcx+8], rax
0x180029169  lea     rax, ??_7CTSThreadInternal@@6B@; const CTSThreadInternal::`vftable'
0x180029170  mov     dword ptr [rcx+28h], 0
0x180029177  mov     [rcx+20h], rcx
0x18002917b  mov     [rbx], rax
0x18002917e  lea     rax, ??_7CTSThreadInternal@@6BINonDelegatingUnknown@@@; const CTSThreadInternal::`vftable'{for `INonDelegatingUnknown'}
0x180029185  mov     [rcx], rax
0x180029188  lea     rax, ??_7CTSThreadInternal@@6BCTSObject@@@; const CTSThreadInternal::`vftable'{for `CTSObject'}
0x18002918f  lea     rcx, [rsp+38h+arg_8]
0x180029194  mov     [rbx+10h], rax
0x180029198  mov     qword ptr [rbx+38h], 0
0x1800291a0  mov     qword ptr [rbx+40h], 0
0x1800291a8  mov     qword ptr [rbx+48h], 0
0x1800291b0  mov     qword ptr [rbx+50h], 0
0x1800291b8  mov     dword ptr [rbx+58h], 0
0x1800291bf  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800291c4  mov     rax, [rbx]
0x1800291c7  mov     rcx, rbx
0x1800291ca  mov     [rsp+38h+arg_8], rbx
0x1800291cf  mov     rax, [rax+8]
0x1800291d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291d8  mov     rax, [rbx]
0x1800291db  lea     rdx, IID_ITSThreadInternal
0x1800291e2  mov     r8, rdi
0x1800291e5  mov     rcx, rbx
0x1800291e8  mov     rax, [rax]
0x1800291eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291f0  mov     ebx, eax
0x1800291f2  test    eax, eax
0x1800291f4  jns     loc_1800292AF
0x1800291fa  mov     rdx, cs:WPP_GLOBAL_Control
0x180029201  lea     rcx, WPP_GLOBAL_Control
0x180029208  cmp     rdx, rcx
0x18002920b  jz      loc_1800292AF
0x180029211  test    byte ptr [rdx+1Ch], 8
0x180029215  jz      loc_1800292AF
0x18002921b  cmp     byte ptr [rdx+19h], 2
0x18002921f  jb      loc_1800292AF
0x180029225  call    RdpX_GetActivityIdPrefix
0x18002922a  lea     rcx, aFailedToQi; "Failed to QI"
0x180029231  mov     [rsp+38h+var_10], ebx
0x180029235  mov     [rsp+38h+var_18], rcx
0x18002923a  lea     r8, WPP_73b49cc1326e3e16b22d457759b24fb0_Traceguids
0x180029241  mov     rcx, cs:WPP_GLOBAL_Control
0x180029248  mov     edx, 0Ch
0x18002924d  mov     r9d, eax
0x180029250  mov     rcx, [rcx+10h]
0x180029254  call    WPP_SF_DsD
0x180029259  jmp     short loc_1800292AF
0x18002925b  mov     rax, cs:WPP_GLOBAL_Control
0x180029262  lea     rcx, WPP_GLOBAL_Control
0x180029269  cmp     rax, rcx
0x18002926c  jz      short loc_1800292AA
0x18002926e  test    byte ptr [rax+1Ch], 8
0x180029272  jz      short loc_1800292AA
0x180029274  cmp     byte ptr [rax+19h], 2
0x180029278  jb      short loc_1800292AA
0x18002927a  call    RdpX_GetActivityIdPrefix
0x18002927f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029286  lea     r8, aCtsthreadinter; "CTSThreadInternal"
0x18002928d  mov     [rsp+38h+var_18], r8
0x180029292  mov     edx, 0Bh
0x180029297  mov     r9d, eax
0x18002929a  lea     r8, WPP_73b49cc1326e3e16b22d457759b24fb0_Traceguids
0x1800292a1  mov     rcx, [rcx+10h]
0x1800292a5  call    WPP_SF_Ds
0x1800292aa  mov     ebx, 8007000Eh
0x1800292af  lea     rcx, [rsp+38h+arg_8]
0x1800292b4  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800292b9  mov     eax, ebx
0x1800292bb  mov     rbx, [rsp+38h+arg_0]
0x1800292c0  add     rsp, 30h
0x1800292c4  pop     rdi
0x1800292c5  retn
```
