# RdpBoundsAccumulator::AddBA(IRdpBoundsAccumulator const *)

- ea: `0x18001ab50`
- end: `0x18001acfe`
- name: `?AddBA@RdpBoundsAccumulator@@UEAAJPEBVIRdpBoundsAccumulator@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(RdpBoundsAccumulator *this, const struct IRdpBoundsAccumulator *, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18001ab50`
- `0x18001c9d0`
- `0x18001d098`
- `0x18001d114`
- `0x18001db30`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x18001ac1c`: `Source BA implementation is not compatible with target BA`

## pseudocode

```c
__int64 __fastcall RdpBoundsAccumulator::AddBA(
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
        13,
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
    v7 = ((__int64 (*)(void))RdpX_GetActivityIdPrefix)();
    v8 = 14;
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
                         *(RGNOBJ **)(v10 + 8),
                         *(struct RGNOBJ **)(v10 + 16),
                         *(struct RGNOBJ **)(a3 + 8),
                         2) )
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
    v7 = ((__int64 (*)(void))RdpX_GetActivityIdPrefix)();
    v8 = 15;
    v9 = "TsAddRegionToRegion failed";
    goto LABEL_24;
  }
LABEL_25:
  TCntPtr<CTSThread>::SafeRelease(&v15, a2, a3, v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001ab50  mov     [rsp+arg_0], rbx
0x18001ab55  push    rdi
0x18001ab56  sub     rsp, 30h
0x18001ab5a  mov     [rsp+38h+arg_8], 0
0x18001ab63  mov     r9, rdx
0x18001ab66  mov     rdi, rcx
0x18001ab69  test    rdx, rdx
0x18001ab6c  jnz     short loc_18001ABC7
0x18001ab6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab75  lea     rax, WPP_GLOBAL_Control
0x18001ab7c  cmp     rcx, rax
0x18001ab7f  jz      short loc_18001ABBD
0x18001ab81  test    byte ptr [rcx+1Ch], 8
0x18001ab85  jz      short loc_18001ABBD
0x18001ab87  cmp     byte ptr [rcx+19h], 2
0x18001ab8b  jb      short loc_18001ABBD
0x18001ab8d  call    RdpX_GetActivityIdPrefix
0x18001ab92  lea     rcx, aPsource; "pSource"
0x18001ab99  mov     edx, 0Dh
0x18001ab9e  mov     [rsp+38h+var_18], rcx
0x18001aba3  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001abaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abb1  mov     r9d, eax
0x18001abb4  mov     rcx, [rcx+10h]
0x18001abb8  call    WPP_SF_Ds
0x18001abbd  mov     ebx, 80004003h
0x18001abc2  jmp     loc_18001ACE7
0x18001abc7  mov     rax, [rdx]
0x18001abca  lea     r8, [rsp+38h+arg_8]
0x18001abcf  lea     rdx, qword_180034248
0x18001abd6  mov     rcx, r9
0x18001abd9  mov     rax, [rax]
0x18001abdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abe1  mov     ebx, eax
0x18001abe3  test    eax, eax
0x18001abe5  jns     short loc_18001AC28
0x18001abe7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abee  lea     rax, WPP_GLOBAL_Control
0x18001abf5  cmp     rcx, rax
0x18001abf8  jz      loc_18001ACE7
0x18001abfe  test    byte ptr [rcx+1Ch], 8
0x18001ac02  jz      loc_18001ACE7
0x18001ac08  cmp     byte ptr [rcx+19h], 2
0x18001ac0c  jb      loc_18001ACE7
0x18001ac12  call    RdpX_GetActivityIdPrefix
0x18001ac17  mov     edx, 0Eh
0x18001ac1c  lea     rcx, aSourceBaImplem; "Source BA implementation is not compati"...
0x18001ac23  jmp     loc_18001ACC4
0x18001ac28  mov     r10, [rdi+38h]
0x18001ac2c  mov     dword ptr [rdi+40h], 1
0x18001ac33  test    r10, r10
0x18001ac36  jz      short loc_18001AC8F
0x18001ac38  mov     ecx, 0F00Dh
0x18001ac3d  cmp     [r10], ecx
0x18001ac40  jnz     short loc_18001AC8F
0x18001ac42  mov     rax, [rsp+38h+arg_8]
0x18001ac47  mov     r8, [rax+38h]
0x18001ac4b  test    r8, r8
0x18001ac4e  jz      short loc_18001AC8F
0x18001ac50  cmp     [r8], ecx
0x18001ac53  jnz     short loc_18001AC8F
0x18001ac55  mov     rdx, [r10+10h]
0x18001ac59  mov     r9, [r10+8]
0x18001ac5d  mov     rax, [rdx]
0x18001ac60  mov     rcx, [r9]
0x18001ac63  mov     [r9], rax
0x18001ac66  mov     r9d, 2; int
0x18001ac6c  mov     [rdx], rcx
0x18001ac6f  mov     r8, [r8+8]; struct RGNOBJ *
0x18001ac73  mov     rdx, [r10+10h]; struct RGNOBJ *
0x18001ac77  mov     rcx, [r10+8]; this
0x18001ac7b  call    ?iCombine@RGNOBJ@@QEAAJAEAV1@0J@Z; RGNOBJ::iCombine(RGNOBJ &,RGNOBJ &,long)
0x18001ac80  test    eax, eax
0x18001ac82  jnz     short loc_18001AC8B
0x18001ac84  mov     ebx, 83451900h
0x18001ac89  jmp     short loc_18001AC94
0x18001ac8b  xor     ebx, ebx
0x18001ac8d  jmp     short loc_18001ACE7
0x18001ac8f  mov     ebx, 80004003h
0x18001ac94  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac9b  lea     rax, WPP_GLOBAL_Control
0x18001aca2  cmp     rcx, rax
0x18001aca5  jz      short loc_18001ACE7
0x18001aca7  test    byte ptr [rcx+1Ch], 8
0x18001acab  jz      short loc_18001ACE7
0x18001acad  cmp     byte ptr [rcx+19h], 2
0x18001acb1  jb      short loc_18001ACE7
0x18001acb3  call    RdpX_GetActivityIdPrefix
0x18001acb8  mov     edx, 0Fh
0x18001acbd  lea     rcx, aTsaddregiontor; "TsAddRegionToRegion failed"
0x18001acc4  mov     [rsp+38h+var_10], ebx
0x18001acc8  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001accf  mov     [rsp+38h+var_18], rcx
0x18001acd4  mov     r9d, eax
0x18001acd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001acde  mov     rcx, [rcx+10h]
0x18001ace2  call    WPP_SF_DsD
0x18001ace7  lea     rcx, [rsp+38h+arg_8]
0x18001acec  call    ?SafeRelease@?$TCntPtr@VCTSThread@@@@AEAAXXZ; TCntPtr<CTSThread>::SafeRelease(void)
0x18001acf1  mov     eax, ebx
0x18001acf3  mov     rbx, [rsp+38h+arg_0]
0x18001acf8  add     rsp, 30h
0x18001acfc  pop     rdi
0x18001acfd  retn
```
