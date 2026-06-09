# CWriteEngineSectionResources::Init(CMsftWriteEngine2 *,CWriteEngineStaticDriveInformation *,ulong,void *,void *)

- ea: `0x180035580`
- end: `0x180035981`
- name: `?Init@CWriteEngineSectionResources@@QEAAJPEAVCMsftWriteEngine2@@PEAVCWriteEngineStaticDriveInformation@@KPEAX2@Z`
- size: `1025`
- prototype: `__int64 __fastcall(CWriteEngineSectionResources *this, struct CMsftWriteEngine2 *, struct CWriteEngineStaticDriveInformation *, __int64, void *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180033b60`

## callees

- `0x18000908c`
- `0x180014134`
- `0x180016778`
- `0x1800236b4`
- `0x180035580`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x180035968`
- `KERNEL32!VirtualFree` at `0x180035968`
- `KERNEL32!LocalAlloc` at `0x18003570e`
- `KERNEL32!LocalAlloc` at `0x18003571b`
- `KERNEL32!LocalAlloc` at `0x18003570e`
- `KERNEL32!LocalAlloc` at `0x18003571b`
- `KERNEL32!LocalFree` at `0x1800358dc`
- `KERNEL32!LocalFree` at `0x1800358fe`
- `KERNEL32!LocalFree` at `0x1800358dc`
- `KERNEL32!LocalFree` at `0x1800358fe`
- `KERNEL32!VirtualAlloc` at `0x1800356aa`
- `KERNEL32!VirtualAlloc` at `0x1800356aa`
- `KERNEL32!CreateEventW` at `0x180035741`
- `KERNEL32!CreateEventW` at `0x1800357b8`
- `KERNEL32!CreateEventW` at `0x1800357cc`
- `KERNEL32!CreateEventW` at `0x180035741`
- `KERNEL32!CreateEventW` at `0x1800357b8`
- `KERNEL32!CreateEventW` at `0x1800357cc`

## pseudocode

```c
__int64 __fastcall CWriteEngineSectionResources::Init(
        CWriteEngineSectionResources *this,
        struct CMsftWriteEngine2 *a2,
        struct CWriteEngineStaticDriveInformation *a3,
        __int64 a4,
        void *a5,
        void *a6)
{
  unsigned int v6; // ebp
  PVOID *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned __int64 v12; // rax
  void *v13; // r12
  int v14; // edi
  char *v15; // r15
  char *v16; // rax
  char *v17; // r14
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r13
  HANDLE EventW; // rax
  __int64 i; // rbx
  __int64 j; // rbx
  HANDLE v25[11]; // [rsp+40h] [rbp-58h] BYREF

  v6 = *((_DWORD *)a3 + 5);
  v25[0] = 0;
  if ( v6 > 0x10000 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
    {
      goto LABEL_7;
    }
    v10 = 12;
    goto LABEL_6;
  }
  if ( v6 >= 0x10000 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_14;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 2u )
  {
    v10 = 13;
LABEL_6:
    WPP_SF_Dd(v9[27], v10, &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids, v6, 0x10000);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_7:
  v6 = 0x10000;
LABEL_14:
  if ( *((_DWORD *)a3 + 7) > 8u
    && v9 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v9 + 228) & 4) != 0
    && *((_BYTE *)v9 + 225) >= 3u )
  {
    WPP_SF_DDDd(v9[27], 14, &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v11 = 0xFFFFFFFFLL;
  v12 = 8LL * v6;
  if ( v12 > 0xFFFFFFFF )
  {
    v13 = 0;
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 228) & 4) != 0 && *((_BYTE *)v9 + 225) >= 3u )
      WPP_SF_DDDd(v9[27], 15, &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids);
    v14 = -2147024882;
    goto LABEL_61;
  }
  v13 = VirtualAlloc(0, (unsigned int)v12, 0x3000u, 4u);
  if ( !v13 )
  {
    v14 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        16,
        &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids,
        8 * v6,
        8 * v6);
    }
LABEL_61:
    Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)v25, (void **)v11);
    if ( v13 )
      VirtualFree(v13, 0, 0x8000u);
    return (unsigned int)v14;
  }
  v15 = (char *)LocalAlloc(0x40u, 0x40u);
  v16 = (char *)LocalAlloc(0x40u, 0x40u);
  v17 = v16;
  if ( !v15 || !v16 )
  {
    v14 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 27), 17, &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids, 8, 8);
    }
    if ( !v17 )
      goto LABEL_52;
    goto LABEL_49;
  }
  v25[0] = CreateEventW(0, 1, 0, 0);
  if ( !v25[0] )
  {
    v14 = -2147024882;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
    {
      v19 = 18;
LABEL_32:
      WPP_SF_(v18[27], v19, &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids);
    }
LABEL_49:
    for ( i = 0; i != 8; ++i )
      Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)&v17[8 * i], (void **)v11);
    LocalFree(v17);
LABEL_52:
    if ( v15 )
    {
      for ( j = 0; j != 8; ++j )
        Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)&v15[8 * j], (void **)v11);
      LocalFree(v15);
    }
    goto LABEL_61;
  }
  v14 = 0;
  v20 = 0;
  while ( (unsigned int)v20 < 8 )
  {
    *(_QWORD *)&v17[8 * v20] = CreateEventW(0, 0, 1, 0);
    EventW = CreateEventW(0, 0, 0, 0);
    *(_QWORD *)&v15[8 * v20] = EventW;
    if ( !*(_QWORD *)&v17[8 * v20] || !EventW )
    {
      v14 = -2147024882;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
      {
        v19 = 19;
        goto LABEL_32;
      }
    }
    v20 = (unsigned int)(v20 + 1);
    if ( v14 < 0 )
      goto LABEL_49;
  }
  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 2) = a5;
  *((_QWORD *)this + 3) = a6;
  *((HANDLE *)this + 7) = v25[0];
  *((_DWORD *)this + 8) = 8;
  *((_QWORD *)this + 5) = v17;
  *((_QWORD *)this + 6) = v15;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = v6;
  *((_QWORD *)this + 10) = v13;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180035580  mov     [rsp+arg_8], rdx
0x180035585  push    rbx
0x180035586  push    rbp
0x180035587  push    rsi
0x180035588  push    rdi
0x180035589  push    r12
0x18003558b  push    r13
0x18003558d  push    r14
0x18003558f  push    r15
0x180035591  sub     rsp, 58h
0x180035595  mov     ebp, [r8+14h]
0x180035599  lea     r14, WPP_GLOBAL_Control
0x1800355a0  mov     edi, 10000h
0x1800355a5  mov     [rsp+98h+var_58], 0
0x1800355ae  lea     r15, WPP_d9598978672c34cd509ac261b9388a6f_Traceguids
0x1800355b5  mov     rbx, r8
0x1800355b8  mov     rsi, rcx
0x1800355bb  mov     r13d, 4
0x1800355c1  cmp     ebp, edi
0x1800355c3  jbe     short loc_180035608
0x1800355c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800355cc  cmp     rcx, r14
0x1800355cf  jz      short loc_180035604
0x1800355d1  test    [rcx+0E4h], r13b
0x1800355d8  jz      short loc_180035604
0x1800355da  cmp     byte ptr [rcx+0E1h], 3
0x1800355e1  jb      short loc_180035604
0x1800355e3  lea     edx, [r13+8]
0x1800355e7  mov     rcx, [rcx+0D8h]
0x1800355ee  mov     r9d, ebp
0x1800355f1  mov     r8, r15
0x1800355f4  mov     [rsp+98h+var_78], edi
0x1800355f8  call    WPP_SF_Dd
0x1800355fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180035604  mov     ebp, edi
0x180035606  jmp     short loc_180035636
0x180035608  jnb     short loc_18003562F
0x18003560a  mov     rcx, cs:WPP_GLOBAL_Control
0x180035611  cmp     rcx, r14
0x180035614  jz      short loc_180035604
0x180035616  test    [rcx+0E4h], r13b
0x18003561d  jz      short loc_180035604
0x18003561f  cmp     byte ptr [rcx+0E1h], 2
0x180035626  jb      short loc_180035604
0x180035628  mov     edx, 0Dh
0x18003562d  jmp     short loc_1800355E7
0x18003562f  mov     rcx, cs:WPP_GLOBAL_Control
0x180035636  mov     r9d, [rbx+1Ch]
0x18003563a  cmp     r9d, 8
0x18003563e  jbe     short loc_180035687
0x180035640  cmp     rcx, r14
0x180035643  jz      short loc_180035687
0x180035645  test    [rcx+0E4h], r13b
0x18003564c  jz      short loc_180035687
0x18003564e  cmp     byte ptr [rcx+0E1h], 3
0x180035655  jb      short loc_180035687
0x180035657  mov     rcx, [rcx+0D8h]
0x18003565e  mov     edx, 0Eh
0x180035663  mov     [rsp+98h+var_68], 8
0x18003566b  mov     r8, r15
0x18003566e  mov     [rsp+98h+var_70], 8
0x180035676  mov     [rsp+98h+var_78], r9d
0x18003567b  call    WPP_SF_DDDd
0x180035680  mov     rcx, cs:WPP_GLOBAL_Control
0x180035687  mov     eax, ebp
0x180035689  mov     edx, 0FFFFFFFFh
0x18003568e  shl     rax, 3
0x180035692  cmp     rax, rdx
0x180035695  ja      loc_180035906
0x18003569b  mov     edx, eax; dwSize
0x18003569d  mov     r9d, r13d; flProtect
0x1800356a0  xor     ecx, ecx; lpAddress
0x1800356a2  mov     ebx, eax
0x1800356a4  mov     r8d, 3000h; flAllocationType
0x1800356aa  call    cs:__imp_VirtualAlloc
0x1800356b0  mov     r12, rax
0x1800356b3  test    rax, rax
0x1800356b6  jnz     short loc_180035705
0x1800356b8  mov     edi, 8007000Eh
0x1800356bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800356c4  cmp     rcx, r14
0x1800356c7  jz      loc_18003594E
0x1800356cd  test    [rcx+0E4h], r13b
0x1800356d4  jz      loc_18003594E
0x1800356da  cmp     byte ptr [rcx+0E1h], 3
0x1800356e1  jb      loc_18003594E
0x1800356e7  mov     rcx, [rcx+0D8h]
0x1800356ee  lea     edx, [rax+10h]
0x1800356f1  mov     r9d, ebx
0x1800356f4  mov     [rsp+98h+var_78], ebx
0x1800356f8  mov     r8, r15
0x1800356fb  call    WPP_SF_Dd
0x180035700  jmp     loc_18003594E
0x180035705  mov     ebx, 40h ; '@'
0x18003570a  mov     edx, ebx; uBytes
0x18003570c  mov     ecx, ebx; uFlags
0x18003570e  call    cs:__imp_LocalAlloc
0x180035714  mov     edx, ebx; uBytes
0x180035716  mov     ecx, ebx; uFlags
0x180035718  mov     r15, rax
0x18003571b  call    cs:__imp_LocalAlloc
0x180035721  mov     r14, rax
0x180035724  test    r15, r15
0x180035727  jz      loc_180035872
0x18003572d  test    rax, rax
0x180035730  jz      loc_180035872
0x180035736  xor     r9d, r9d; lpName
0x180035739  lea     edx, [rbx-3Fh]; bManualReset
0x18003573c  xor     r8d, r8d; bInitialState
0x18003573f  xor     ecx, ecx; lpEventAttributes
0x180035741  call    cs:__imp_CreateEventW
0x180035747  mov     [rsp+98h+var_58], rax
0x18003574c  test    rax, rax
0x18003574f  jnz     short loc_1800357A2
0x180035751  mov     edi, 8007000Eh
0x180035756  mov     rcx, cs:WPP_GLOBAL_Control
0x18003575d  lea     rax, WPP_GLOBAL_Control
0x180035764  cmp     rcx, rax
0x180035767  jz      loc_1800358C5
0x18003576d  test    [rcx+0E4h], r13b
0x180035774  jz      loc_1800358C5
0x18003577a  cmp     byte ptr [rcx+0E1h], 3
0x180035781  jb      loc_1800358C5
0x180035787  lea     edx, [rbx-2Eh]
0x18003578a  mov     rcx, [rcx+0D8h]
0x180035791  lea     r8, WPP_d9598978672c34cd509ac261b9388a6f_Traceguids
0x180035798  call    WPP_SF_
0x18003579d  jmp     loc_1800358C5
0x1800357a2  xor     edi, edi
0x1800357a4  xor     r13d, r13d
0x1800357a7  cmp     r13d, 8
0x1800357ab  jnb     short loc_180035822
0x1800357ad  xor     r9d, r9d; lpName
0x1800357b0  xor     edx, edx; bManualReset
0x1800357b2  xor     ecx, ecx; lpEventAttributes
0x1800357b4  lea     r8d, [r9+1]; bInitialState
0x1800357b8  call    cs:__imp_CreateEventW
0x1800357be  xor     r9d, r9d; lpName
0x1800357c1  xor     r8d, r8d; bInitialState
0x1800357c4  xor     edx, edx; bManualReset
0x1800357c6  mov     [r14+r13*8], rax
0x1800357ca  xor     ecx, ecx; lpEventAttributes
0x1800357cc  call    cs:__imp_CreateEventW
0x1800357d2  mov     [r15+r13*8], rax
0x1800357d6  cmp     qword ptr [r14+r13*8], 0
0x1800357db  jz      short loc_1800357E2
0x1800357dd  test    rax, rax
0x1800357e0  jnz     short loc_18003580C
0x1800357e2  mov     edi, 8007000Eh
0x1800357e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800357ee  lea     rax, WPP_GLOBAL_Control
0x1800357f5  cmp     rcx, rax
0x1800357f8  jz      short loc_18003580C
0x1800357fa  test    byte ptr [rcx+0E4h], 4
0x180035801  jz      short loc_18003580C
0x180035803  cmp     byte ptr [rcx+0E1h], 3
0x18003580a  jnb     short loc_180035818
0x18003580c  inc     r13d
0x18003580f  test    edi, edi
0x180035811  jns     short loc_1800357A7
0x180035813  jmp     loc_1800358C5
0x180035818  mov     edx, 13h
0x18003581d  jmp     loc_18003578A
0x180035822  mov     rax, [rsp+98h+arg_8]
0x18003582a  mov     [rsi+8], rax
0x18003582e  mov     rax, [rsp+98h+arg_20]
0x180035836  mov     [rsi+10h], rax
0x18003583a  mov     rax, [rsp+98h+arg_28]
0x180035842  mov     [rsi+18h], rax
0x180035846  mov     rax, [rsp+98h+var_58]
0x18003584b  mov     [rsi+38h], rax
0x18003584f  mov     dword ptr [rsi+20h], 8
0x180035856  mov     [rsi+28h], r14
0x18003585a  mov     [rsi+30h], r15
0x18003585e  mov     qword ptr [rsi+40h], 0
0x180035866  mov     [rsi+48h], ebp
0x180035869  mov     [rsi+50h], r12
0x18003586d  jmp     loc_18003596E
0x180035872  mov     edi, 8007000Eh
0x180035877  mov     rcx, cs:WPP_GLOBAL_Control
0x18003587e  lea     rax, WPP_GLOBAL_Control
0x180035885  cmp     rcx, rax
0x180035888  jz      short loc_1800358C0
0x18003588a  test    [rcx+0E4h], r13b
0x180035891  jz      short loc_1800358C0
0x180035893  cmp     byte ptr [rcx+0E1h], 3
0x18003589a  jb      short loc_1800358C0
0x18003589c  mov     rcx, [rcx+0D8h]
0x1800358a3  lea     r8, WPP_d9598978672c34cd509ac261b9388a6f_Traceguids
0x1800358aa  mov     edx, 11h
0x1800358af  mov     [rsp+98h+var_78], 8
0x1800358b7  lea     r9d, [rdx-9]
0x1800358bb  call    WPP_SF_Dd
0x1800358c0  test    r14, r14
0x1800358c3  jz      short loc_1800358E2
0x1800358c5  xor     ebx, ebx
0x1800358c7  lea     rcx, [r14+rbx*8]; this
0x1800358cb  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x1800358d0  inc     rbx
0x1800358d3  cmp     rbx, 8
0x1800358d7  jnz     short loc_1800358C7
0x1800358d9  mov     rcx, r14; hMem
0x1800358dc  call    cs:__imp_LocalFree
0x1800358e2  test    r15, r15
0x1800358e5  jz      short loc_18003594E
0x1800358e7  xor     ebx, ebx
0x1800358e9  lea     rcx, [r15+rbx*8]; this
0x1800358ed  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x1800358f2  inc     rbx
0x1800358f5  cmp     rbx, 8
0x1800358f9  jnz     short loc_1800358E9
0x1800358fb  mov     rcx, r15; hMem
0x1800358fe  call    cs:__imp_LocalFree
0x180035904  jmp     short loc_18003594E
0x180035906  xor     r12d, r12d
0x180035909  cmp     rcx, r14
0x18003590c  jz      short loc_180035949
0x18003590e  test    [rcx+0E4h], r13b
0x180035915  jz      short loc_180035949
0x180035917  cmp     byte ptr [rcx+0E1h], 3
0x18003591e  jb      short loc_180035949
0x180035920  mov     rcx, [rcx+0D8h]
0x180035927  lea     edx, [r12+0Fh]
0x18003592c  mov     [rsp+98h+var_68], ebp
0x180035930  lea     r9d, [r12+8]
0x180035935  mov     [rsp+98h+var_70], ebp
0x180035939  mov     r8, r15
0x18003593c  mov     [rsp+98h+var_78], 8
0x180035944  call    WPP_SF_DDDd
0x180035949  mov     edi, 8007000Eh
0x18003594e  lea     rcx, [rsp+98h+var_58]; this
0x180035953  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x180035958  test    r12, r12
0x18003595b  jz      short loc_18003596E
0x18003595d  xor     edx, edx; dwSize
0x18003595f  mov     r8d, 8000h; dwFreeType
0x180035965  mov     rcx, r12; lpAddress
0x180035968  call    cs:__imp_VirtualFree
0x18003596e  mov     eax, edi
0x180035970  add     rsp, 58h
0x180035974  pop     r15
0x180035976  pop     r14
0x180035978  pop     r13
0x18003597a  pop     r12
0x18003597c  pop     rdi
0x18003597d  pop     rsi
0x18003597e  pop     rbp
0x18003597f  pop     rbx
0x180035980  retn
```
