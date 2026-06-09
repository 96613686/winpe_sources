# FveHwAccelCreateConfiguration

- ea: `0x1400cb21c`
- end: `0x1400cb53b`
- name: `FveHwAccelCreateConfiguration`
- size: `799`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400cca48`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140014464`
- `0x1400cb21c`
- `0x1400cb544`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400cb2ba`
- `ntoskrnl!ExAllocatePool2` at `0x1400cb350`
- `ntoskrnl!ExAllocatePool2` at `0x1400cb2ba`
- `ntoskrnl!ExAllocatePool2` at `0x1400cb350`
- `ext-ms-win-accel-api-km-l1-1-1!AccelConfigureWorkspaceCryptoCapability` at `0x1400cb46d`
- `ext-ms-win-accel-api-km-l1-1-1!AccelConfigureWorkspaceCryptoCapability` at `0x1400cb46d`
- `ext-ms-win-accel-api-km-l1-1-1!AccelInitializeCryptoWorkspace` at `0x1400cb3d6`
- `ext-ms-win-accel-api-km-l1-1-1!AccelInitializeCryptoWorkspace` at `0x1400cb3d6`

## pseudocode

```c
__int64 __fastcall FveHwAccelCreateConfiguration(__int64 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  __int64 v4; // r14
  __int64 Pool2; // rax
  __int64 v10; // rdi
  __int64 v11; // r9
  unsigned int v12; // ebx
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  unsigned __int16 Size; // ax
  __int64 v16; // rax
  int v17; // eax
  __int128 v19; // [rsp+20h] [rbp-58h] BYREF
  __int128 v20; // [rsp+30h] [rbp-48h] BYREF
  __int128 v21; // [rsp+40h] [rbp-38h]
  __int128 v22; // [rsp+50h] [rbp-28h]
  __int64 v23; // [rsp+60h] [rbp-18h]

  v4 = *(_QWORD *)(a1 + 8);
  v19 = 0;
  v23 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids);
  }
  if ( *(int *)(a2 + 28) < 0 || !*(_BYTE *)(a2 + 24) )
  {
    v10 = 0;
    v12 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids, 3221225485LL);
    }
    goto LABEL_35;
  }
  Pool2 = ExAllocatePool2(64, 40, 809850438);
  v10 = Pool2;
  if ( !Pool2 )
  {
    v11 = 3221225626LL;
    v12 = -1073741670;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v14 = 65;
LABEL_12:
      WPP_SF_d(v13->AttachedDevice, v14, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids, v11);
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  *(_OWORD *)Pool2 = 0;
  *(_OWORD *)(Pool2 + 16) = 0;
  *(_QWORD *)(Pool2 + 32) = 0;
  *(_DWORD *)Pool2 = *(_DWORD *)(a2 + 16);
  *(_DWORD *)(Pool2 + 8) = 1;
  Size = FveDatumKeyGetSize(a3);
  *(_DWORD *)(v10 + 24) = Size;
  v16 = ExAllocatePool2(64, Size, 1701736270);
  *(_QWORD *)(v10 + 16) = v16;
  if ( v16 )
  {
    v12 = 0;
    if ( (*(_DWORD *)(v4 + 9680) & 0x800000) == 0 )
    {
      v19 = 0;
      LODWORD(v19) = 1048577;
      *((_QWORD *)&v19 + 1) = *(_QWORD *)(v4 + 10472);
      v17 = AccelInitializeCryptoWorkspace(&v19, v10 + 32);
      v12 = v17;
      if ( v17 < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u)
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_35;
        }
        v14 = 67;
        goto LABEL_24;
      }
      v23 = 0;
      v20 = 0;
      LODWORD(v20) = 3670017;
      v21 = 0;
      v22 = 0;
      *((_QWORD *)&v20 + 1) = *(_QWORD *)(v10 + 32);
      LODWORD(v21) = *(_DWORD *)(a2 + 16);
      DWORD2(v21) = 1;
      *(_QWORD *)&v22 = *(_QWORD *)(v10 + 16);
      DWORD2(v22) = *(_DWORD *)(v10 + 24);
      LODWORD(v23) = *(_DWORD *)(a1 + 1308);
      v17 = AccelConfigureWorkspaceCryptoCapability(&v20);
      v12 = v17;
      if ( v17 < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u)
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_35;
        }
        v14 = 68;
LABEL_24:
        v11 = (unsigned int)v17;
        goto LABEL_12;
      }
    }
    *a4 = v10;
    v10 = 0;
    goto LABEL_35;
  }
  v11 = 3221225626LL;
  v12 = -1073741670;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v14 = 66;
    goto LABEL_12;
  }
LABEL_35:
  FveHwAccelDestroyConfiguration((PVOID)v10);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x1400cb21c  push    rbp
0x1400cb21e  push    rbx
0x1400cb21f  push    rsi
0x1400cb220  push    rdi
0x1400cb221  push    r12
0x1400cb223  push    r13
0x1400cb225  push    r14
0x1400cb227  push    r15
0x1400cb229  mov     rbp, rsp
0x1400cb22c  sub     rsp, 78h
0x1400cb230  mov     r14, [rcx+8]
0x1400cb234  xorps   xmm1, xmm1
0x1400cb237  xorps   xmm0, xmm0
0x1400cb23a  xor     eax, eax
0x1400cb23c  movups  [rbp+var_58], xmm0
0x1400cb240  mov     [rbp+var_18], rax
0x1400cb244  mov     r12, r9
0x1400cb247  movups  [rbp+var_48], xmm1
0x1400cb24b  mov     rbx, r8
0x1400cb24e  mov     rsi, rdx
0x1400cb251  movups  [rbp+var_38], xmm1
0x1400cb255  mov     r15, rcx
0x1400cb258  movups  [rbp+var_28], xmm1
0x1400cb25c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb263  lea     rax, WPP_GLOBAL_Control
0x1400cb26a  cmp     rcx, rax
0x1400cb26d  jz      short loc_1400CB298
0x1400cb26f  bt      dword ptr [rcx+2Ch], 16h
0x1400cb274  jnb     short loc_1400CB291
0x1400cb276  cmp     byte ptr [rcx+29h], 5
0x1400cb27a  jb      short loc_1400CB291
0x1400cb27c  mov     rcx, [rcx+18h]
0x1400cb280  lea     r8, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids
0x1400cb287  mov     edx, 3Fh ; '?'
0x1400cb28c  call    WPP_SF_
0x1400cb291  lea     rax, WPP_GLOBAL_Control
0x1400cb298  cmp     dword ptr [rsi+1Ch], 0
0x1400cb29c  jl      loc_1400CB4B1
0x1400cb2a2  cmp     byte ptr [rsi+18h], 0
0x1400cb2a6  jz      loc_1400CB4B1
0x1400cb2ac  mov     edx, 28h ; '('
0x1400cb2b1  mov     r8d, 30455646h
0x1400cb2b7  lea     ecx, [rdx+18h]
0x1400cb2ba  call    cs:__imp_ExAllocatePool2
0x1400cb2c1  nop     dword ptr [rax+rax+00h]
0x1400cb2c6  mov     rdi, rax
0x1400cb2c9  test    rax, rax
0x1400cb2cc  jnz     short loc_1400CB31B
0x1400cb2ce  mov     r9d, 0C000009Ah
0x1400cb2d4  mov     ebx, r9d
0x1400cb2d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb2de  lea     rsi, WPP_GLOBAL_Control
0x1400cb2e5  cmp     rcx, rsi
0x1400cb2e8  jz      loc_1400CB4EE
0x1400cb2ee  bt      dword ptr [rcx+2Ch], 16h
0x1400cb2f3  jnb     loc_1400CB4EE
0x1400cb2f9  cmp     byte ptr [rcx+29h], 2
0x1400cb2fd  jb      loc_1400CB4EE
0x1400cb303  lea     edx, [rax+41h]
0x1400cb306  mov     rcx, [rcx+18h]
0x1400cb30a  lea     r8, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids
0x1400cb311  call    WPP_SF_d
0x1400cb316  jmp     loc_1400CB4EE
0x1400cb31b  xor     eax, eax
0x1400cb31d  xorps   xmm0, xmm0
0x1400cb320  movups  xmmword ptr [rdi], xmm0
0x1400cb323  mov     rcx, rbx
0x1400cb326  movups  xmmword ptr [rdi+10h], xmm0
0x1400cb32a  mov     [rdi+20h], rax
0x1400cb32e  mov     eax, [rsi+10h]
0x1400cb331  mov     [rdi], eax
0x1400cb333  mov     dword ptr [rdi+8], 1
0x1400cb33a  call    FveDatumKeyGetSize
0x1400cb33f  movzx   edx, ax
0x1400cb342  mov     ecx, 40h ; '@'
0x1400cb347  mov     r8d, 656E6F4Eh
0x1400cb34d  mov     [rdi+18h], edx
0x1400cb350  call    cs:__imp_ExAllocatePool2
0x1400cb357  nop     dword ptr [rax+rax+00h]
0x1400cb35c  mov     [rdi+10h], rax
0x1400cb360  test    rax, rax
0x1400cb363  jnz     short loc_1400CB3A2
0x1400cb365  mov     r9d, 0C000009Ah
0x1400cb36b  mov     ebx, r9d
0x1400cb36e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb375  lea     rsi, WPP_GLOBAL_Control
0x1400cb37c  cmp     rcx, rsi
0x1400cb37f  jz      loc_1400CB4EE
0x1400cb385  bt      dword ptr [rcx+2Ch], 16h
0x1400cb38a  jnb     loc_1400CB4EE
0x1400cb390  cmp     byte ptr [rcx+29h], 2
0x1400cb394  jb      loc_1400CB4EE
0x1400cb39a  lea     edx, [rax+42h]
0x1400cb39d  jmp     loc_1400CB306
0x1400cb3a2  xor     ebx, ebx
0x1400cb3a4  test    dword ptr [r14+25D0h], 800000h
0x1400cb3af  jnz     loc_1400CB4A9
0x1400cb3b5  xorps   xmm0, xmm0
0x1400cb3b8  lea     rdx, [rdi+20h]
0x1400cb3bc  movups  [rbp+var_58], xmm0
0x1400cb3c0  mov     dword ptr [rbp+var_58], 100001h
0x1400cb3c7  lea     rcx, [rbp+var_58]
0x1400cb3cb  mov     rax, [r14+28E8h]
0x1400cb3d2  mov     qword ptr [rbp+var_58+8], rax
0x1400cb3d6  call    cs:__imp_AccelInitializeCryptoWorkspace
0x1400cb3dd  nop     dword ptr [rax+rax+00h]
0x1400cb3e2  mov     ebx, eax
0x1400cb3e4  test    eax, eax
0x1400cb3e6  jns     short loc_1400CB421
0x1400cb3e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb3ef  lea     rsi, WPP_GLOBAL_Control
0x1400cb3f6  cmp     rcx, rsi
0x1400cb3f9  jz      loc_1400CB4EE
0x1400cb3ff  bt      dword ptr [rcx+2Ch], 16h
0x1400cb404  jnb     loc_1400CB4EE
0x1400cb40a  cmp     byte ptr [rcx+29h], 2
0x1400cb40e  jb      loc_1400CB4EE
0x1400cb414  mov     edx, 43h ; 'C'
0x1400cb419  mov     r9d, eax
0x1400cb41c  jmp     loc_1400CB306
0x1400cb421  xor     eax, eax
0x1400cb423  xorps   xmm0, xmm0
0x1400cb426  mov     [rbp+var_18], rax
0x1400cb42a  movups  [rbp+var_48], xmm0
0x1400cb42e  mov     dword ptr [rbp+var_48], 380001h
0x1400cb435  lea     ecx, [rax+1]
0x1400cb438  movups  [rbp+var_38], xmm0
0x1400cb43c  movups  [rbp+var_28], xmm0
0x1400cb440  mov     rax, [rdi+20h]
0x1400cb444  mov     qword ptr [rbp+var_48+8], rax
0x1400cb448  mov     eax, [rsi+10h]
0x1400cb44b  mov     dword ptr [rbp+var_38], eax
0x1400cb44e  mov     dword ptr [rbp+var_38+8], ecx
0x1400cb451  lea     rcx, [rbp+var_48]
0x1400cb455  mov     rax, [rdi+10h]
0x1400cb459  mov     qword ptr [rbp+var_28], rax
0x1400cb45d  mov     eax, [rdi+18h]
0x1400cb460  mov     dword ptr [rbp+var_28+8], eax
0x1400cb463  mov     eax, [r15+51Ch]
0x1400cb46a  mov     dword ptr [rbp+var_18], eax
0x1400cb46d  call    cs:__imp_AccelConfigureWorkspaceCryptoCapability
0x1400cb474  nop     dword ptr [rax+rax+00h]
0x1400cb479  mov     ebx, eax
0x1400cb47b  test    eax, eax
0x1400cb47d  jns     short loc_1400CB4A9
0x1400cb47f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb486  lea     rsi, WPP_GLOBAL_Control
0x1400cb48d  cmp     rcx, rsi
0x1400cb490  jz      short loc_1400CB4EE
0x1400cb492  bt      dword ptr [rcx+2Ch], 16h
0x1400cb497  jnb     short loc_1400CB4EE
0x1400cb499  cmp     byte ptr [rcx+29h], 2
0x1400cb49d  jb      short loc_1400CB4EE
0x1400cb49f  mov     edx, 44h ; 'D'
0x1400cb4a4  jmp     loc_1400CB419
0x1400cb4a9  mov     [r12], rdi
0x1400cb4ad  xor     edi, edi
0x1400cb4af  jmp     short loc_1400CB4E7
0x1400cb4b1  xor     edi, edi
0x1400cb4b3  mov     ebx, 0C000000Dh
0x1400cb4b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb4bf  cmp     rcx, rax
0x1400cb4c2  jz      short loc_1400CB4E7
0x1400cb4c4  bt      dword ptr [rcx+2Ch], 16h
0x1400cb4c9  jnb     short loc_1400CB4E7
0x1400cb4cb  cmp     byte ptr [rcx+29h], 2
0x1400cb4cf  jb      short loc_1400CB4E7
0x1400cb4d1  mov     rcx, [rcx+18h]
0x1400cb4d5  lea     edx, [rdi+40h]
0x1400cb4d8  mov     r9d, ebx
0x1400cb4db  lea     r8, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids
0x1400cb4e2  call    WPP_SF_d
0x1400cb4e7  lea     rsi, WPP_GLOBAL_Control
0x1400cb4ee  mov     rcx, rdi; P
0x1400cb4f1  call    FveHwAccelDestroyConfiguration
0x1400cb4f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cb4fd  cmp     rcx, rsi
0x1400cb500  jz      short loc_1400CB527
0x1400cb502  bt      dword ptr [rcx+2Ch], 16h
0x1400cb507  jnb     short loc_1400CB527
0x1400cb509  cmp     byte ptr [rcx+29h], 5
0x1400cb50d  jb      short loc_1400CB527
0x1400cb50f  mov     rcx, [rcx+18h]
0x1400cb513  lea     r8, WPP_fa53f08b4f2d315e4871dfc305e80bc2_Traceguids
0x1400cb51a  mov     edx, 45h ; 'E'
0x1400cb51f  mov     r9d, ebx
0x1400cb522  call    WPP_SF_d
0x1400cb527  mov     eax, ebx
0x1400cb529  add     rsp, 78h
0x1400cb52d  pop     r15
0x1400cb52f  pop     r14
0x1400cb531  pop     r13
0x1400cb533  pop     r12
0x1400cb535  pop     rdi
0x1400cb536  pop     rsi
0x1400cb537  pop     rbx
0x1400cb538  pop     rbp
0x1400cb539  retn
```
