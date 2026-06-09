# SmbExtSecuritySessionSetupExchangeStart

- ea: `0x140052700`
- end: `0x140052895`
- name: `SmbExtSecuritySessionSetupExchangeStart`
- size: `405`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000dfd8`
- `0x14000e52c`
- `0x140016640`
- `0x14004e5b0`
- `0x140052700`

## pseudocode

```c
__int64 __fastcall SmbExtSecuritySessionSetupExchangeStart(_QWORD *pContext)
{
  __int64 v1; // rsi
  __int64 v4; // r14
  __int16 v5; // cx
  __int64 v6; // rdi
  bool v7; // zf
  unsigned int v8; // esi
  unsigned int v9; // eax
  int v10; // [rsp+70h] [rbp+8h] BYREF

  v1 = pContext[11];
  v10 = 0;
  if ( v1 )
    v1 = *(_QWORD *)(v1 + 96);
  if ( !*((_BYTE *)pContext + 360) )
    return *(_DWORD *)(v1 + 12) != 0 ? 0xC0000203 : 0;
  v4 = pContext[10];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_43394d5f7d713bd5b3e6605c91e75025_Traceguids, pContext[50], v1);
  v5 = -14333;
  v6 = pContext[47];
  v7 = MRxSmbSecuritySignaturesEnabled == 0;
  v10 = *((_DWORD *)pContext + 98) - 32;
  *(_DWORD *)v6 = 1112364031;
  *(_BYTE *)(v6 + 9) = 24;
  *(_WORD *)(v6 + 10) = -14333;
  *(_WORD *)(v6 + 26) = -257;
  *(_WORD *)(v6 + 28) = *(_WORD *)(v1 + 132);
  *(_WORD *)(v6 + 24) = -1;
  *(_DWORD *)(v6 + 5) = 0;
  *(_BYTE *)(v6 + 4) = 115;
  if ( !v7 )
  {
    v5 = -14329;
    *(_WORD *)(v6 + 10) = -14329;
  }
  if ( MRxSmbSecuritySignaturesRequired || (*(_BYTE *)(v4 + 673) & 1) != 0 )
    *(_WORD *)(v6 + 10) = v5 | 0x10;
  v8 = (**(__int64 (__fastcall ***)(_QWORD *, __int64, int *))(v4 + 408))(pContext, v6 + 32, &v10);
  if ( !v8 )
  {
    *(_DWORD *)(v6 + 33) = 255;
    if ( (*(_BYTE *)(v4 + 672) & 0x18) == 0x10 )
      *(_QWORD *)(v6 + 14) = *(_QWORD *)InitialSecuritySignature;
    v9 = SmbCeTranceive((char *)pContext, 805306368, pContext[48], *((_DWORD *)pContext + 98) - v10);
    v8 = v9;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_43394d5f7d713bd5b3e6605c91e75025_Traceguids, v9);
  }
  return v8;
}

```

## disassembly

```asm
0x140052700  push    rbx
0x140052702  push    rbp
0x140052703  push    rsi
0x140052704  push    rdi
0x140052705  push    r12
0x140052707  push    r14
0x140052709  sub     rsp, 38h
0x14005270d  mov     rsi, [rcx+58h]
0x140052711  mov     rbx, rcx
0x140052714  mov     [rsp+68h+arg_0], 0
0x14005271c  test    rsi, rsi
0x14005271f  jz      short loc_140052725
0x140052721  mov     rsi, [rsi+60h]
0x140052725  cmp     byte ptr [rcx+168h], 0
0x14005272c  jnz     short loc_14005273F
0x14005272e  mov     eax, [rsi+0Ch]
0x140052731  neg     eax
0x140052733  sbb     eax, eax
0x140052735  and     eax, 0C0000203h
0x14005273a  jmp     loc_140052887
0x14005273f  mov     r14, [rcx+50h]; __annotation("TMF:",
0x140052743  lea     r12, WPP_GLOBAL_Control
0x14005274a  mov     rcx, cs:WPP_GLOBAL_Control
0x140052751  cmp     rcx, r12
0x140052754  jz      short loc_140052780
0x140052756  test    dword ptr [rcx+2Ch], 200h
0x14005275d  jz      short loc_140052780
0x14005275f  mov     r9, [rbx+190h]
0x140052766  lea     r8, WPP_43394d5f7d713bd5b3e6605c91e75025_Traceguids
0x14005276d  mov     rcx, [rcx+18h]
0x140052771  mov     edx, 0Bh
0x140052776  mov     [rsp+68h+var_48], rsi
0x14005277b  call    WPP_SF_qq
0x140052780  mov     eax, [rbx+188h]
0x140052786  mov     ecx, 0C803h
0x14005278b  mov     rdi, [rbx+178h]
0x140052792  sub     eax, 20h ; ' '
0x140052795  cmp     cs:MRxSmbSecuritySignaturesEnabled, 0
0x14005279c  mov     [rsp+68h+arg_0], eax
0x1400527a0  mov     dword ptr [rdi], 424D53FFh
0x1400527a6  mov     byte ptr [rdi+9], 18h
0x1400527aa  mov     [rdi+0Ah], cx
0x1400527ae  mov     word ptr [rdi+1Ah], 0FEFFh
0x1400527b4  movzx   eax, word ptr [rsi+84h]
0x1400527bb  mov     [rdi+1Ch], ax
0x1400527bf  mov     word ptr [rdi+18h], 0FFFFh
0x1400527c5  mov     dword ptr [rdi+5], 0
0x1400527cc  mov     byte ptr [rdi+4], 73h ; 's'
0x1400527d0  jz      short loc_1400527DB
0x1400527d2  mov     ecx, 0C807h
0x1400527d7  mov     [rdi+0Ah], cx
0x1400527db  cmp     cs:MRxSmbSecuritySignaturesRequired, 0
0x1400527e2  jnz     short loc_1400527EE
0x1400527e4  test    byte ptr [r14+2A1h], 1
0x1400527ec  jz      short loc_1400527F6
0x1400527ee  or      cx, 10h
0x1400527f2  mov     [rdi+0Ah], cx
0x1400527f6  mov     rax, [r14+198h]
0x1400527fd  lea     r8, [rsp+68h+arg_0]
0x140052802  lea     rdx, [rdi+20h]
0x140052806  mov     rcx, rbx
0x140052809  mov     rax, [rax]
0x14005280c  call    _guard_dispatch_icall
0x140052811  mov     esi, eax
0x140052813  test    eax, eax
0x140052815  jnz     short loc_140052885
0x140052817  mov     dword ptr [rdi+21h], 0FFh
0x14005281e  mov     al, [r14+2A0h]
0x140052825  and     al, 18h
0x140052827  cmp     al, 10h
0x140052829  jnz     short loc_140052836
0x14005282b  mov     rax, qword ptr cs:InitialSecuritySignature; "BSRSPYL "
0x140052832  mov     [rdi+0Eh], rax
0x140052836  mov     r9d, [rbx+188h]
0x14005283d  mov     edx, 30000000h
0x140052842  sub     r9d, [rsp+68h+arg_0]
0x140052847  mov     rcx, rbx; pContext
0x14005284a  mov     r8, [rbx+180h]
0x140052851  call    SmbCeTranceive
0x140052856  mov     esi, eax
0x140052858  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005285f  cmp     rcx, r12
0x140052862  jz      short loc_140052885
0x140052864  test    dword ptr [rcx+2Ch], 400h
0x14005286b  jz      short loc_140052885
0x14005286d  mov     rcx, [rcx+18h]
0x140052871  lea     r8, WPP_43394d5f7d713bd5b3e6605c91e75025_Traceguids
0x140052878  mov     edx, 0Ch
0x14005287d  mov     r9d, eax
0x140052880  call    WPP_SF_d
0x140052885  mov     eax, esi
0x140052887  add     rsp, 38h
0x14005288b  pop     r14
0x14005288d  pop     r12
0x14005288f  pop     rdi
0x140052890  pop     rsi
0x140052891  pop     rbp
0x140052892  pop     rbx
0x140052893  retn
```
