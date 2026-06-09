# MRxSmbCompleteBufferingStateChangeRequest

- ea: `0x140034700`
- end: `0x14003487d`
- name: `MRxSmbCompleteBufferingStateChangeRequest`
- size: `381`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e01c`
- `0x140034700`
- `0x140046120`
- `0x14004d7f0`
- `0x14004dd50`

## import_xrefs

- `rdbss!RxLockEnumerator` at `0x140034808`

## pseudocode

```c
__int64 __fastcall MRxSmbCompleteBufferingStateChangeRequest(_QWORD *a1)
{
  __int64 v1; // rax
  __int64 v2; // rbx
  __int64 v4; // rdi
  __int64 v5; // r14
  __int64 v6; // rbp
  unsigned int OrdinaryExchange; // edi
  unsigned __int8 *v9; // rdi
  unsigned __int8 *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // [rsp+20h] [rbp-38h]
  PVOID pContext; // [rsp+60h] [rbp+8h] BYREF

  v1 = a1[7];
  v2 = a1[9];
  v4 = a1[56];
  v5 = 0;
  if ( v1 )
    v5 = *(_QWORD *)(v1 + 136);
  v6 = 0;
  if ( v2 )
    v6 = *(_QWORD *)(v2 + 48);
  pContext = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      26,
      WPP_3ee8049ed8753e4c0026596278bef2b5_Traceguids,
      *(unsigned __int8 *)(v6 + 10),
      (unsigned __int16)v4);
  if ( !(_WORD)v4 )
    *(_DWORD *)(v2 + 72) |= 1u;
  *(_WORD *)(v5 + 14) = v4;
  if ( *(_BYTE *)(v6 + 10) == 3 && !(_WORD)v4 )
    return 0;
  *(_BYTE *)(v6 + 10) = v4;
  OrdinaryExchange = _SmbPseCreateOrdinaryExchange(
                       (__int64)a1,
                       *(_QWORD *)(v2 + 40),
                       7,
                       (__int64)SmbPseExchangeStart_Locks,
                       v12,
                       (__int64 *)&pContext);
  if ( OrdinaryExchange )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_3ee8049ed8753e4c0026596278bef2b5_Traceguids);
    return OrdinaryExchange;
  }
  else
  {
    v9 = (unsigned __int8 *)pContext;
    v10 = (unsigned __int8 *)pContext;
    *((_QWORD *)pContext + 61) = RxLockEnumerator;
    *((_QWORD *)v10 + 60) = v2;
    v11 = SmbCeInitiateExchange(v10);
    if ( v11 != 259 )
      SmbPseFinalizeOrdinaryExchange(v9);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_3ee8049ed8753e4c0026596278bef2b5_Traceguids, v11);
    return v11;
  }
}

```

## disassembly

```asm
0x140034700  mov     [rsp+arg_8], rbx
0x140034705  mov     [rsp+arg_10], rbp
0x14003470a  push    rsi
0x14003470b  push    rdi
0x14003470c  push    r12
0x14003470e  push    r14
0x140034710  push    r15
0x140034712  sub     rsp, 30h
0x140034716  mov     rax, [rcx+38h]
0x14003471a  xor     r15d, r15d
0x14003471d  mov     rbx, [rcx+48h]
0x140034721  mov     rsi, rcx
0x140034724  mov     rdi, [rcx+1C0h]
0x14003472b  mov     r14d, r15d
0x14003472e  test    rax, rax
0x140034731  jz      short loc_14003473A
0x140034733  mov     r14, [rax+88h]
0x14003473a  mov     rbp, r15
0x14003473d  test    rbx, rbx
0x140034740  jz      short loc_140034746
0x140034742  mov     rbp, [rbx+30h]
0x140034746  mov     [rsp+58h+pContext], r15
0x14003474b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140034752  lea     r12, WPP_GLOBAL_Control
0x140034759  cmp     rcx, r12
0x14003475c  jz      short loc_140034788
0x14003475e  test    dword ptr [rcx+2Ch], 200h
0x140034765  jz      short loc_140034788
0x140034767  movzx   r9d, byte ptr [rbp+0Ah]
0x14003476c  lea     r8, WPP_3ee8049ed8753e4c0026596278bef2b5_Traceguids
0x140034773  mov     rcx, [rcx+18h]
0x140034777  mov     edx, 1Ah
0x14003477c  movzx   eax, di
0x14003477f  mov     dword ptr [rsp+58h+var_38], eax
0x140034783  call    WPP_SF_Dd
0x140034788  test    di, di
0x14003478b  jnz     short loc_140034791
0x14003478d  or      dword ptr [rbx+48h], 1
0x140034791  mov     [r14+0Eh], di
0x140034796  cmp     byte ptr [rbp+0Ah], 3
0x14003479a  jnz     short loc_1400347A8
0x14003479c  test    di, di
0x14003479f  jnz     short loc_1400347A8
0x1400347a1  xor     eax, eax
0x1400347a3  jmp     loc_140034865
0x1400347a8  mov     [rbp+0Ah], dil
0x1400347ac  lea     rax, [rsp+58h+pContext]
0x1400347b1  mov     rdx, [rbx+28h]
0x1400347b5  lea     r9, SmbPseExchangeStart_Locks
0x1400347bc  mov     r8d, 7
0x1400347c2  mov     [rsp+58h+var_30], rax
0x1400347c7  mov     rcx, rsi
0x1400347ca  call    __SmbPseCreateOrdinaryExchange
0x1400347cf  mov     edi, eax
0x1400347d1  test    eax, eax
0x1400347d3  jz      short loc_140034803
0x1400347d5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400347dc  cmp     rcx, r12
0x1400347df  jz      short loc_1400347FF
0x1400347e1  test    dword ptr [rcx+2Ch], 400h
0x1400347e8  jz      short loc_1400347FF
0x1400347ea  mov     rcx, [rcx+18h]
0x1400347ee  lea     r8, WPP_3ee8049ed8753e4c0026596278bef2b5_Traceguids
0x1400347f5  mov     edx, 1Bh
0x1400347fa  call    WPP_SF_
0x1400347ff  mov     eax, edi
0x140034801  jmp     short loc_140034865
0x140034803  mov     rdi, [rsp+58h+pContext]
0x140034808  mov     rax, cs:__imp_RxLockEnumerator
0x14003480f  mov     rcx, rdi
0x140034812  mov     [rdi+1E8h], rax
0x140034819  mov     [rdi+1E0h], rbx
0x140034820  call    SmbCeInitiateExchange
0x140034825  mov     ebx, eax
0x140034827  cmp     eax, 103h
0x14003482c  jz      short loc_140034836
0x14003482e  mov     rcx, rdi; pContext
0x140034831  call    SmbPseFinalizeOrdinaryExchange
0x140034836  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003483d  cmp     rcx, r12
0x140034840  jz      short loc_140034863
0x140034842  test    dword ptr [rcx+2Ch], 400h
0x140034849  jz      short loc_140034863
0x14003484b  mov     rcx, [rcx+18h]
0x14003484f  lea     r8, WPP_3ee8049ed8753e4c0026596278bef2b5_Traceguids
0x140034856  mov     edx, 1Ch
0x14003485b  mov     r9d, ebx
0x14003485e  call    WPP_SF_d
0x140034863  mov     eax, ebx
0x140034865  mov     rbx, [rsp+58h+arg_8]
0x14003486a  mov     rbp, [rsp+58h+arg_10]
0x14003486f  add     rsp, 30h
0x140034873  pop     r15
0x140034875  pop     r14
0x140034877  pop     r12
0x140034879  pop     rdi
0x14003487a  pop     rsi
0x14003487b  retn
```
