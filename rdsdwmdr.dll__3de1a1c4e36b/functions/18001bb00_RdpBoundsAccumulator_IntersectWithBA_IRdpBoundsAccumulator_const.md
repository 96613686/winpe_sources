# RdpBoundsAccumulator::IntersectWithBA(IRdpBoundsAccumulator const *)

- ea: `0x18001bb00`
- end: `0x18001bcab`
- name: `?IntersectWithBA@RdpBoundsAccumulator@@UEAAJPEBVIRdpBoundsAccumulator@@@Z`
- size: `427`
- prototype: `__int64 __fastcall(RdpBoundsAccumulator *this, const struct IRdpBoundsAccumulator *, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18001bb00`
- `0x18001c9d0`
- `0x18001d098`
- `0x18001d114`
- `0x18001db30`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x18001bbcc`: `Source BA implementation is not compatible with target BA`

## pseudocode

```c
__int64 __fastcall RdpBoundsAccumulator::IntersectWithBA(
        RdpBoundsAccumulator *this,
        const struct IRdpBoundsAccumulator *a2,
        __int64 a3)
{
  __int64 v3; // r9
  int ActivityIdPrefix; // eax
  int v6; // ebx
  int v7; // eax
  int v8; // edx
  const char *v9; // rcx
  __int64 v10; // r11
  __int64 *v11; // rdx
  __int64 *v12; // r10
  __int64 v13; // rcx
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  v15 = 0;
  v3 = (__int64)a2;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, 0, a3, 0);
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
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
    v8 = 20;
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
  v3 = 1;
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
                         1) )
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
    v8 = 21;
    v9 = "TsIntersectRegionWithRegion failed";
    goto LABEL_24;
  }
LABEL_25:
  TCntPtr<CTSThread>::SafeRelease(&v15, a2, a3, v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001bb00  mov     [rsp+arg_0], rbx
0x18001bb05  push    rdi
0x18001bb06  sub     rsp, 30h
0x18001bb0a  mov     [rsp+38h+arg_8], 0
0x18001bb13  mov     r9, rdx
0x18001bb16  mov     rdi, rcx
0x18001bb19  test    rdx, rdx
0x18001bb1c  jnz     short loc_18001BB77
0x18001bb1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb25  lea     rax, WPP_GLOBAL_Control
0x18001bb2c  cmp     rcx, rax
0x18001bb2f  jz      short loc_18001BB6D
0x18001bb31  test    byte ptr [rcx+1Ch], 8
0x18001bb35  jz      short loc_18001BB6D
0x18001bb37  cmp     byte ptr [rcx+19h], 2
0x18001bb3b  jb      short loc_18001BB6D
0x18001bb3d  call    RdpX_GetActivityIdPrefix
0x18001bb42  lea     rcx, aPsource; "pSource"
0x18001bb49  mov     edx, 13h
0x18001bb4e  mov     [rsp+38h+var_18], rcx
0x18001bb53  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001bb5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb61  mov     r9d, eax
0x18001bb64  mov     rcx, [rcx+10h]
0x18001bb68  call    WPP_SF_Ds
0x18001bb6d  mov     ebx, 80004003h
0x18001bb72  jmp     loc_18001BC94
0x18001bb77  mov     rax, [rdx]
0x18001bb7a  lea     r8, [rsp+38h+arg_8]
0x18001bb7f  lea     rdx, qword_180034248
0x18001bb86  mov     rcx, r9
0x18001bb89  mov     rax, [rax]
0x18001bb8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb91  mov     ebx, eax
0x18001bb93  test    eax, eax
0x18001bb95  jns     short loc_18001BBD8
0x18001bb97  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb9e  lea     rax, WPP_GLOBAL_Control
0x18001bba5  cmp     rcx, rax
0x18001bba8  jz      loc_18001BC94
0x18001bbae  test    byte ptr [rcx+1Ch], 8
0x18001bbb2  jz      loc_18001BC94
0x18001bbb8  cmp     byte ptr [rcx+19h], 2
0x18001bbbc  jb      loc_18001BC94
0x18001bbc2  call    RdpX_GetActivityIdPrefix
0x18001bbc7  mov     edx, 14h
0x18001bbcc  lea     rcx, aSourceBaImplem; "Source BA implementation is not compati"...
0x18001bbd3  jmp     loc_18001BC71
0x18001bbd8  mov     r11, [rdi+38h]
0x18001bbdc  mov     r9d, 1; int
0x18001bbe2  mov     [rdi+40h], r9d
0x18001bbe6  test    r11, r11
0x18001bbe9  jz      short loc_18001BC3C
0x18001bbeb  mov     ecx, 0F00Dh
0x18001bbf0  cmp     [r11], ecx
0x18001bbf3  jnz     short loc_18001BC3C
0x18001bbf5  mov     rax, [rsp+38h+arg_8]
0x18001bbfa  mov     r8, [rax+38h]
0x18001bbfe  test    r8, r8
0x18001bc01  jz      short loc_18001BC3C
0x18001bc03  cmp     [r8], ecx
0x18001bc06  jnz     short loc_18001BC3C
0x18001bc08  mov     rdx, [r11+10h]
0x18001bc0c  mov     r10, [r11+8]
0x18001bc10  mov     rax, [rdx]
0x18001bc13  mov     rcx, [r10]
0x18001bc16  mov     [r10], rax
0x18001bc19  mov     [rdx], rcx
0x18001bc1c  mov     r8, [r8+8]; struct RGNOBJ *
0x18001bc20  mov     rdx, [r11+10h]; struct RGNOBJ *
0x18001bc24  mov     rcx, [r11+8]; this
0x18001bc28  call    ?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z; RGNOBJ::iCombine(RGNOBJ &,RGNOBJ &,long)
0x18001bc2d  test    eax, eax
0x18001bc2f  jnz     short loc_18001BC38
0x18001bc31  mov     ebx, 83451900h
0x18001bc36  jmp     short loc_18001BC41
0x18001bc38  xor     ebx, ebx
0x18001bc3a  jmp     short loc_18001BC94
0x18001bc3c  mov     ebx, 80004003h
0x18001bc41  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc48  lea     rax, WPP_GLOBAL_Control
0x18001bc4f  cmp     rcx, rax
0x18001bc52  jz      short loc_18001BC94
0x18001bc54  test    byte ptr [rcx+1Ch], 8
0x18001bc58  jz      short loc_18001BC94
0x18001bc5a  cmp     byte ptr [rcx+19h], 2
0x18001bc5e  jb      short loc_18001BC94
0x18001bc60  call    RdpX_GetActivityIdPrefix
0x18001bc65  mov     edx, 15h
0x18001bc6a  lea     rcx, aTsintersectreg; "TsIntersectRegionWithRegion failed"
0x18001bc71  mov     [rsp+38h+var_10], ebx
0x18001bc75  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001bc7c  mov     [rsp+38h+var_18], rcx
0x18001bc81  mov     r9d, eax
0x18001bc84  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc8b  mov     rcx, [rcx+10h]
0x18001bc8f  call    WPP_SF_DsD
0x18001bc94  lea     rcx, [rsp+38h+arg_8]
0x18001bc99  call    ?SafeRelease@?$TCntPtr@VCTSThread@@@@AEAAXXZ; TCntPtr<CTSThread>::SafeRelease(void)
0x18001bc9e  mov     eax, ebx
0x18001bca0  mov     rbx, [rsp+38h+arg_0]
0x18001bca5  add     rsp, 30h
0x18001bca9  pop     rdi
0x18001bcaa  retn
```
