# MRxSmbCloseSrvOpen

- ea: `0x1400367d0`
- end: `0x140036b4a`
- name: `MRxSmbCloseSrvOpen`
- size: `890`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x140010768`
- `0x140010a74`
- `0x1400283f8`
- `0x1400367d0`
- `0x1400381a0`
- `0x140046120`
- `0x14004d7f0`
- `0x14004dd50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140036893`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400368b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036893`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400368b7`

## pseudocode

```c
__int64 __fastcall MRxSmbCloseSrvOpen(__int64 a1)
{
  __int64 v1; // rax
  unsigned int OrdinaryExchange; // ebp
  __int16 *v3; // r12
  __int64 v5; // rsi
  __int16 v6; // r15
  __int64 v7; // rbx
  __int64 v8; // rdi
  bool v9; // r14
  __int64 v10; // rax
  void *v11; // rcx
  void *v12; // rcx
  PDEVICE_OBJECT *v13; // r8
  int v14; // ecx
  int v15; // edx
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r14
  int v19; // edi
  __int64 v21; // [rsp+20h] [rbp-58h]
  __int64 v22; // [rsp+80h] [rbp+8h]
  PVOID pContext; // [rsp+88h] [rbp+10h] BYREF

  v1 = *(_QWORD *)(a1 + 64);
  OrdinaryExchange = 0;
  v3 = *(__int16 **)(a1 + 56);
  v5 = *(_QWORD *)(v1 + 32);
  v6 = *v3;
  if ( v5 )
    v7 = *(_QWORD *)(v5 + 48);
  else
    v7 = 0;
  v8 = *(_QWORD *)(v1 + 56);
  v9 = 0;
  v10 = *(_QWORD *)(v5 + 40);
  pContext = 0;
  v22 = *(_QWORD *)(*(_QWORD *)(v10 + 40) + 88LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  if ( v6 == -5087 )
  {
    if ( v8 )
    {
      v9 = (*(_BYTE *)(v8 + 52) & 2) != 0;
      MRxSmbDeallocateSideBuffer(a1, v8, (__int64)"Cleanup");
      v11 = *(void **)(v8 + 8);
      if ( v11 )
      {
        ExFreePoolWithTag(v11, 0);
        *(_QWORD *)(v8 + 8) = 0;
      }
    }
  }
  if ( *(_BYTE *)(v7 + 133) )
    goto LABEL_16;
  v12 = *(void **)(v7 + 16);
  if ( !v12 )
    goto LABEL_16;
  ExFreePoolWithTag(v12, 0);
  *(_QWORD *)(v7 + 16) = 0;
  v13 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_Zq(
      WPP_GLOBAL_Control->AttachedDevice,
      77,
      (unsigned int)WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
      *(_QWORD *)(a1 + 56) + 360,
      v7);
LABEL_16:
    v13 = &WPP_GLOBAL_Control;
  }
  v14 = *((_DWORD *)v3 + 39);
  if ( (v14 & 0x80u) != 0 || *(_BYTE *)(*((_QWORD *)v3 + 15) + 77LL) == 1 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 )
      goto LABEL_48;
    v17 = 78;
    goto LABEL_47;
  }
  v15 = *(_DWORD *)(v5 + 72);
  if ( (v15 & 0x30) != 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 )
      goto LABEL_48;
    v17 = 79;
    goto LABEL_47;
  }
  if ( *(_WORD *)(v7 + 8) == 0xFFFF || (*(_DWORD *)v7 & 0x600) != 0 )
    goto LABEL_48;
  if ( ((v14 & 1) == 0 || *((_DWORD *)v3 + 48)) && !v9 && (v15 & 0x100000) != 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 )
      goto LABEL_48;
    v17 = 80;
LABEL_47:
    WPP_SF_(v16->AttachedDevice, v17, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
LABEL_48:
    v18 = v22;
    goto LABEL_49;
  }
  v18 = v22;
  if ( *(_DWORD *)(v7 + 4) == *(_DWORD *)(v22 + 400) )
  {
    v19 = 0;
    while ( 1 )
    {
      OrdinaryExchange = _SmbPseCreateOrdinaryExchange(
                           a1,
                           *(_QWORD *)(v5 + 40),
                           9,
                           (__int64)SmbPseExchangeStart_Close,
                           v21,
                           (__int64 *)&pContext);
      if ( OrdinaryExchange )
        break;
      OrdinaryExchange = SmbCeInitiateExchange((unsigned __int8 *)pContext);
      SmbPseFinalizeOrdinaryExchange((unsigned __int8 *)pContext);
      if ( OrdinaryExchange != -1069481983 )
        goto LABEL_35;
      if ( ++v19 >= 3 )
      {
        OrdinaryExchange = -1073741595;
        goto LABEL_35;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  }
  else
  {
LABEL_35:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        82,
        WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
        OrdinaryExchange);
  }
LABEL_49:
  if ( (*(_DWORD *)v7 & 0x600) == 0 && (*(_DWORD *)(v5 + 72) & 0x100000) == 0 && v18 )
    MRxSmbDecrementSrvOpenCount(v18, *(unsigned int *)(v7 + 4), v5);
  *(_DWORD *)v7 |= 0x400u;
  if ( OrdinaryExchange
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
  {
    WPP_SF_qqqL(WPP_GLOBAL_Control->AttachedDevice, 83, v13, a1, v5, v3, OrdinaryExchange);
  }
  return 0;
}

```

## disassembly

```asm
0x1400367d0  mov     [rsp+arg_10], rbx
0x1400367d5  push    rbp
0x1400367d6  push    rsi
0x1400367d7  push    rdi
0x1400367d8  push    r12
0x1400367da  push    r13
0x1400367dc  push    r14
0x1400367de  push    r15
0x1400367e0  sub     rsp, 40h
0x1400367e4  mov     rax, [rcx+40h]
0x1400367e8  xor     ebp, ebp
0x1400367ea  mov     r12, [rcx+38h]
0x1400367ee  mov     r13, rcx
0x1400367f1  mov     rsi, [rax+20h]
0x1400367f5  movzx   r15d, word ptr [r12]
0x1400367fa  test    rsi, rsi
0x1400367fd  jnz     short loc_140036803
0x1400367ff  xor     ebx, ebx
0x140036801  jmp     short loc_140036807
0x140036803  mov     rbx, [rsi+30h]
0x140036807  mov     rdi, [rax+38h]
0x14003680b  xor     r14b, r14b
0x14003680e  mov     rax, [rsi+28h]
0x140036812  mov     [rsp+78h+pContext], rbp
0x14003681a  mov     rcx, [rax+28h]
0x14003681e  mov     rax, [rcx+58h]
0x140036822  mov     [rsp+78h+arg_0], rax
0x14003682a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140036831  lea     rax, WPP_GLOBAL_Control
0x140036838  cmp     rcx, rax
0x14003683b  jz      short loc_14003685B
0x14003683d  test    dword ptr [rcx+2Ch], 400h
0x140036844  jz      short loc_14003685B
0x140036846  mov     rcx, [rcx+18h]
0x14003684a  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140036851  mov     edx, 4Ch ; 'L'
0x140036856  call    WPP_SF_
0x14003685b  mov     eax, 0EC21h
0x140036860  cmp     r15w, ax
0x140036864  jnz     short loc_1400368A3
0x140036866  test    rdi, rdi
0x140036869  jz      short loc_1400368A3
0x14003686b  mov     r14b, [rdi+34h]
0x14003686f  lea     r8, aCleanup; "Cleanup"
0x140036876  shr     r14b, 1
0x140036879  mov     rdx, rdi
0x14003687c  mov     rcx, r13
0x14003687f  and     r14b, 1
0x140036883  call    MRxSmbDeallocateSideBuffer
0x140036888  mov     rcx, [rdi+8]; P
0x14003688c  test    rcx, rcx
0x14003688f  jz      short loc_1400368A3
0x140036891  xor     edx, edx; Tag
0x140036893  call    cs:__imp_ExFreePoolWithTag
0x14003689a  nop     dword ptr [rax+rax+00h]
0x14003689f  mov     [rdi+8], rbp
0x1400368a3  cmp     [rbx+85h], bpl
0x1400368aa  jnz     short loc_14003690D
0x1400368ac  mov     rcx, [rbx+10h]; P
0x1400368b0  test    rcx, rcx
0x1400368b3  jz      short loc_14003690D
0x1400368b5  xor     edx, edx; Tag
0x1400368b7  call    cs:__imp_ExFreePoolWithTag
0x1400368be  nop     dword ptr [rax+rax+00h]
0x1400368c3  mov     [rbx+10h], rbp
0x1400368c7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400368ce  lea     r8, WPP_GLOBAL_Control
0x1400368d5  mov     r15d, 400h
0x1400368db  cmp     rcx, r8
0x1400368de  jz      short loc_14003691A
0x1400368e0  test    [rcx+2Ch], r15d
0x1400368e4  jz      short loc_14003691A
0x1400368e6  mov     r9, [r13+38h]
0x1400368ea  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x1400368f1  mov     rcx, [rcx+18h]
0x1400368f5  add     r9, 168h
0x1400368fc  mov     edx, 4Dh ; 'M'
0x140036901  mov     [rsp+78h+var_58], rbx
0x140036906  call    WPP_SF_Zq
0x14003690b  jmp     short loc_140036913
0x14003690d  mov     r15d, 400h
0x140036913  lea     r8, WPP_GLOBAL_Control
0x14003691a  mov     ecx, [r12+9Ch]
0x140036922  test    cl, cl
0x140036924  js      loc_140036A94
0x14003692a  mov     rax, [r12+78h]
0x14003692f  cmp     byte ptr [rax+4Dh], 1
0x140036933  jz      loc_140036A94
0x140036939  mov     edx, [rsi+48h]
0x14003693c  test    dl, 30h
0x14003693f  jnz     loc_140036A7B
0x140036945  mov     eax, 0FFFFh
0x14003694a  cmp     [rbx+8], ax
0x14003694e  jz      loc_140036ABB
0x140036954  test    dword ptr [rbx], 600h
0x14003695a  jnz     loc_140036ABB
0x140036960  test    cl, 1
0x140036963  jz      short loc_14003696F
0x140036965  cmp     [r12+0C0h], ebp
0x14003696d  jz      short loc_14003699E
0x14003696f  test    r14b, r14b
0x140036972  jnz     short loc_14003699E
0x140036974  bt      edx, 14h
0x140036978  jnb     short loc_14003699E
0x14003697a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140036981  cmp     rcx, r8
0x140036984  jz      loc_140036ABB
0x14003698a  test    [rcx+2Ch], r15d
0x14003698e  jz      loc_140036ABB
0x140036994  mov     edx, 50h ; 'P'
0x140036999  jmp     loc_140036AAB
0x14003699e  mov     r14, [rsp+78h+arg_0]
0x1400369a6  mov     eax, [r14+190h]
0x1400369ad  cmp     [rbx+4], eax
0x1400369b0  jnz     short loc_140036A10
0x1400369b2  xor     edi, edi
0x1400369b4  mov     rdx, [rsi+28h]
0x1400369b8  lea     rax, [rsp+78h+pContext]
0x1400369c0  lea     r9, SmbPseExchangeStart_Close
0x1400369c7  mov     [rsp+78h+var_50], rax
0x1400369cc  mov     r8d, 9
0x1400369d2  mov     rcx, r13
0x1400369d5  call    __SmbPseCreateOrdinaryExchange
0x1400369da  mov     ebp, eax
0x1400369dc  test    eax, eax
0x1400369de  jnz     short loc_140036A4B
0x1400369e0  mov     rcx, [rsp+78h+pContext]
0x1400369e8  call    SmbCeInitiateExchange
0x1400369ed  mov     rcx, [rsp+78h+pContext]; pContext
0x1400369f5  mov     ebp, eax
0x1400369f7  call    SmbPseFinalizeOrdinaryExchange
0x1400369fc  cmp     ebp, 0C0410001h
0x140036a02  jnz     short loc_140036A10
0x140036a04  inc     edi
0x140036a06  cmp     edi, 3
0x140036a09  jl      short loc_1400369B4
0x140036a0b  mov     ebp, 0C00000E5h
0x140036a10  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140036a17  lea     rdi, WPP_GLOBAL_Control
0x140036a1e  cmp     rcx, rdi
0x140036a21  jz      loc_140036ACA
0x140036a27  test    [rcx+2Ch], r15d
0x140036a2b  jz      loc_140036ACA
0x140036a31  mov     rcx, [rcx+18h]
0x140036a35  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140036a3c  mov     edx, 52h ; 'R'
0x140036a41  mov     r9d, ebp
0x140036a44  call    WPP_SF_d
0x140036a49  jmp     short loc_140036ACA
0x140036a4b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140036a52  lea     rdi, WPP_GLOBAL_Control
0x140036a59  cmp     rcx, rdi
0x140036a5c  jz      short loc_140036ACA
0x140036a5e  test    [rcx+2Ch], r15d
0x140036a62  jz      short loc_140036ACA
0x140036a64  mov     rcx, [rcx+18h]
0x140036a68  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140036a6f  mov     edx, 51h ; 'Q'
0x140036a74  call    WPP_SF_
0x140036a79  jmp     short loc_140036ACA
0x140036a7b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140036a82  cmp     rcx, r8
0x140036a85  jz      short loc_140036ABB
0x140036a87  test    [rcx+2Ch], r15d
0x140036a8b  jz      short loc_140036ABB
0x140036a8d  mov     edx, 4Fh ; 'O'
0x140036a92  jmp     short loc_140036AAB
0x140036a94  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140036a9b  cmp     rcx, r8
0x140036a9e  jz      short loc_140036ABB
0x140036aa0  test    [rcx+2Ch], r15d
0x140036aa4  jz      short loc_140036ABB
0x140036aa6  mov     edx, 4Eh ; 'N'
0x140036aab  mov     rcx, [rcx+18h]
0x140036aaf  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140036ab6  call    WPP_SF_
0x140036abb  mov     r14, [rsp+78h+arg_0]
0x140036ac3  lea     rdi, WPP_GLOBAL_Control
0x140036aca  test    dword ptr [rbx], 600h
0x140036ad0  setz    dl
0x140036ad3  test    dword ptr [rsi+48h], 100000h
0x140036ada  setz    al
0x140036add  test    al, dl
0x140036adf  jz      short loc_140036AF4
0x140036ae1  test    r14, r14
0x140036ae4  jz      short loc_140036AF4
0x140036ae6  mov     edx, [rbx+4]
0x140036ae9  mov     r8, rsi
0x140036aec  mov     rcx, r14
0x140036aef  call    MRxSmbDecrementSrvOpenCount
0x140036af4  or      [rbx], r15d
0x140036af7  test    ebp, ebp
0x140036af9  jz      short loc_140036B2F
0x140036afb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140036b02  cmp     rcx, rdi
0x140036b05  jz      short loc_140036B2F
0x140036b07  test    dword ptr [rcx+2Ch], 100h
0x140036b0e  jz      short loc_140036B2F
0x140036b10  mov     rcx, [rcx+18h]
0x140036b14  mov     edx, 53h ; 'S'
0x140036b19  mov     [rsp+78h+var_48], ebp
0x140036b1d  mov     r9, r13
0x140036b20  mov     [rsp+78h+var_50], r12
0x140036b25  mov     [rsp+78h+var_58], rsi
0x140036b2a  call    WPP_SF_qqqL
0x140036b2f  mov     rbx, [rsp+78h+arg_10]
0x140036b37  xor     eax, eax
0x140036b39  add     rsp, 40h
0x140036b3d  pop     r15
0x140036b3f  pop     r14
0x140036b41  pop     r13
0x140036b43  pop     r12
0x140036b45  pop     rdi
0x140036b46  pop     rsi
0x140036b47  pop     rbp
0x140036b48  retn
```
