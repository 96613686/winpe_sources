# RdpBoundsAccumulator::RemoveBA(IRdpBoundsAccumulator const *)

- ea: `0x18001c730`
- end: `0x18001c8de`
- name: `?RemoveBA@RdpBoundsAccumulator@@UEAAJPEBVIRdpBoundsAccumulator@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(RdpBoundsAccumulator *__hidden this, const struct IRdpBoundsAccumulator *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18001c730`
- `0x18001c9d0`
- `0x18001d098`
- `0x18001d114`
- `0x18001db30`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x18001c7fc`: `Source BA implementation is not compatible with target BA`

## pseudocode

```c
__int64 __fastcall RdpBoundsAccumulator::RemoveBA(
        RdpBoundsAccumulator *this,
        const struct IRdpBoundsAccumulator *a2,
        __int64 a3)
{
  const struct IRdpBoundsAccumulator *v3; // r9
  int ActivityIdPrefix; // eax
  int v6; // ebx
  int v7; // eax
  int v8; // edx
  const char *v9; // rcx
  __int64 v10; // r10
  __int64 *v11; // rdx
  __int64 *v12; // r9
  __int64 v13; // rcx
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  v15 = 0;
  v3 = a2;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, 0, a3, 0);
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids,
        ActivityIdPrefix,
        (__int64)"pSource");
    }
    v6 = -2147467261;
    goto LABEL_25;
  }
  v6 = (**(__int64 (__fastcall ***)(const struct IRdpBoundsAccumulator *, __int64 *, __int64 *))a2)(
         a2,
         &qword_180034248,
         &v15);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    v7 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, a2, a3, v3);
    v8 = 17;
    v9 = "Source BA implementation is not compatible with target BA";
LABEL_24:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids,
      v7,
      (__int64)v9,
      v6);
    goto LABEL_25;
  }
  v10 = *((_QWORD *)this + 7);
  *((_DWORD *)this + 16) = 1;
  if ( v10 && *(_DWORD *)v10 == 61453 && (a3 = *(_QWORD *)(v15 + 56)) != 0 && *(_DWORD *)a3 == 61453 )
  {
    v11 = *(__int64 **)(v10 + 16);
    v12 = *(__int64 **)(v10 + 8);
    v13 = *v12;
    *v12 = *v11;
    *v11 = v13;
    if ( (unsigned int)RGNOBJ::iCombine(
                         *(unsigned int ***)(v10 + 8),
                         *(struct RGNOBJ **)(v10 + 16),
                         *(struct RGNOBJ **)(a3 + 8),
                         4) )
    {
      v6 = 0;
      goto LABEL_25;
    }
    v6 = -2092623616;
  }
  else
  {
    v6 = -2147467261;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, a2, a3, v3);
    v8 = 18;
    v9 = "TsSubtractRegionFromRegion failed";
    goto LABEL_24;
  }
LABEL_25:
  TCntPtr<CTSThread>::SafeRelease(&v15, a2, a3, v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001c730  mov     [rsp+arg_0], rbx
0x18001c735  push    rdi
0x18001c736  sub     rsp, 30h
0x18001c73a  mov     [rsp+38h+arg_8], 0
0x18001c743  mov     r9, rdx
0x18001c746  mov     rdi, rcx
0x18001c749  test    rdx, rdx
0x18001c74c  jnz     short loc_18001C7A7
0x18001c74e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c755  lea     rax, WPP_GLOBAL_Control
0x18001c75c  cmp     rcx, rax
0x18001c75f  jz      short loc_18001C79D
0x18001c761  test    byte ptr [rcx+1Ch], 8
0x18001c765  jz      short loc_18001C79D
0x18001c767  cmp     byte ptr [rcx+19h], 2
0x18001c76b  jb      short loc_18001C79D
0x18001c76d  call    RdpX_GetActivityIdPrefix
0x18001c772  lea     rcx, aPsource; "pSource"
0x18001c779  mov     edx, 10h
0x18001c77e  mov     [rsp+38h+var_18], rcx
0x18001c783  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001c78a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c791  mov     r9d, eax
0x18001c794  mov     rcx, [rcx+10h]
0x18001c798  call    WPP_SF_Ds
0x18001c79d  mov     ebx, 80004003h
0x18001c7a2  jmp     loc_18001C8C7
0x18001c7a7  mov     rax, [rdx]
0x18001c7aa  lea     r8, [rsp+38h+arg_8]
0x18001c7af  lea     rdx, qword_180034248
0x18001c7b6  mov     rcx, r9
0x18001c7b9  mov     rax, [rax]
0x18001c7bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7c1  mov     ebx, eax
0x18001c7c3  test    eax, eax
0x18001c7c5  jns     short loc_18001C808
0x18001c7c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7ce  lea     rax, WPP_GLOBAL_Control
0x18001c7d5  cmp     rcx, rax
0x18001c7d8  jz      loc_18001C8C7
0x18001c7de  test    byte ptr [rcx+1Ch], 8
0x18001c7e2  jz      loc_18001C8C7
0x18001c7e8  cmp     byte ptr [rcx+19h], 2
0x18001c7ec  jb      loc_18001C8C7
0x18001c7f2  call    RdpX_GetActivityIdPrefix
0x18001c7f7  mov     edx, 11h
0x18001c7fc  lea     rcx, aSourceBaImplem; "Source BA implementation is not compati"...
0x18001c803  jmp     loc_18001C8A4
0x18001c808  mov     r10, [rdi+38h]
0x18001c80c  mov     dword ptr [rdi+40h], 1
0x18001c813  test    r10, r10
0x18001c816  jz      short loc_18001C86F
0x18001c818  mov     ecx, 0F00Dh
0x18001c81d  cmp     [r10], ecx
0x18001c820  jnz     short loc_18001C86F
0x18001c822  mov     rax, [rsp+38h+arg_8]
0x18001c827  mov     r8, [rax+38h]
0x18001c82b  test    r8, r8
0x18001c82e  jz      short loc_18001C86F
0x18001c830  cmp     [r8], ecx
0x18001c833  jnz     short loc_18001C86F
0x18001c835  mov     rdx, [r10+10h]
0x18001c839  mov     r9, [r10+8]
0x18001c83d  mov     rax, [rdx]
0x18001c840  mov     rcx, [r9]
0x18001c843  mov     [r9], rax
0x18001c846  mov     r9d, 4; int
0x18001c84c  mov     [rdx], rcx
0x18001c84f  mov     r8, [r8+8]; struct RGNOBJ *
0x18001c853  mov     rdx, [r10+10h]; struct RGNOBJ *
0x18001c857  mov     rcx, [r10+8]; this
0x18001c85b  call    ?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z; RGNOBJ::iCombine(RGNOBJ &,RGNOBJ &,long)
0x18001c860  test    eax, eax
0x18001c862  jnz     short loc_18001C86B
0x18001c864  mov     ebx, 83451900h
0x18001c869  jmp     short loc_18001C874
0x18001c86b  xor     ebx, ebx
0x18001c86d  jmp     short loc_18001C8C7
0x18001c86f  mov     ebx, 80004003h
0x18001c874  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c87b  lea     rax, WPP_GLOBAL_Control
0x18001c882  cmp     rcx, rax
0x18001c885  jz      short loc_18001C8C7
0x18001c887  test    byte ptr [rcx+1Ch], 8
0x18001c88b  jz      short loc_18001C8C7
0x18001c88d  cmp     byte ptr [rcx+19h], 2
0x18001c891  jb      short loc_18001C8C7
0x18001c893  call    RdpX_GetActivityIdPrefix
0x18001c898  mov     edx, 12h
0x18001c89d  lea     rcx, aTssubtractregi; "TsSubtractRegionFromRegion failed"
0x18001c8a4  mov     [rsp+38h+var_10], ebx
0x18001c8a8  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001c8af  mov     [rsp+38h+var_18], rcx
0x18001c8b4  mov     r9d, eax
0x18001c8b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c8be  mov     rcx, [rcx+10h]
0x18001c8c2  call    WPP_SF_DsD
0x18001c8c7  lea     rcx, [rsp+38h+arg_8]
0x18001c8cc  call    ?SafeRelease@?$TCntPtr@VCTSThread@@@@AEAAXXZ; TCntPtr<CTSThread>::SafeRelease(void)
0x18001c8d1  mov     eax, ebx
0x18001c8d3  mov     rbx, [rsp+38h+arg_0]
0x18001c8d8  add     rsp, 30h
0x18001c8dc  pop     rdi
0x18001c8dd  retn
```
