# RdpBoundsAccumulator::IntersectsRect(RdpRect const *,uint *)

- ea: `0x18001c200`
- end: `0x18001c370`
- name: `?IntersectsRect@RdpBoundsAccumulator@@UEBAJPEBURdpRect@@PEAI@Z`
- size: `368`
- prototype: `__int64 __fastcall(RdpBoundsAccumulator *this, const struct RdpRect *, unsigned int *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18001baa0`
- `0x18001c200`
- `0x18001cc98`
- `0x18001d098`
- `0x18001d114`
- `0x18002a1c4`

## string_xrefs

- `0x18001c2e5`: `UpdateRectsIter failed`

## pseudocode

```c
__int64 __fastcall RdpBoundsAccumulator::IntersectsRect(
        RdpBoundsAccumulator *this,
        const struct RdpRect *a2,
        unsigned int *a3,
        __int64 a4)
{
  int ActivityIdPrefix; // eax
  int v8; // edx
  const char *v9; // rcx
  int updated; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // eax
  unsigned int i; // r10d
  int v16; // r10d
  int v17; // r11d
  __int128 v19; // [rsp+30h] [rbp-38h] BYREF

  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467261;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, 0, a3, a4);
    v8 = 35;
    v9 = "pRect";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids,
      ActivityIdPrefix,
      (__int64)v9);
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467261;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, a2, 0, a4);
    v8 = 36;
    v9 = "pIntersectionArea";
    goto LABEL_6;
  }
  *a3 = 0;
  updated = RdpBoundsAccumulator::UpdateRectsIter(this);
  if ( updated >= 0 )
  {
    for ( i = 0; i < *((_DWORD *)this + 20); *a3 = (DWORD2(v19) - v19) * (HIDWORD(v19) - DWORD1(v19)) + v17 )
    {
      v19 = *(_OWORD *)(*((_QWORD *)this + 9) + 16LL * i);
      RdpRect::Intersect((RdpRect *)&v19, a2);
      i = v16 + 1;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v11, v12, v13);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      (unsigned int)WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids,
      v14,
      (__int64)"UpdateRectsIter failed",
      updated);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18001c200  push    rbx
0x18001c202  push    rbp
0x18001c203  push    rsi
0x18001c204  push    rdi
0x18001c205  sub     rsp, 48h
0x18001c209  mov     rdi, r8
0x18001c20c  mov     rbp, rdx
0x18001c20f  mov     rsi, rcx
0x18001c212  test    rdx, rdx
0x18001c215  jnz     short loc_18001C26E
0x18001c217  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c21e  lea     rax, WPP_GLOBAL_Control
0x18001c225  cmp     rcx, rax
0x18001c228  jz      short loc_18001C264
0x18001c22a  test    byte ptr [rcx+1Ch], 8
0x18001c22e  jz      short loc_18001C264
0x18001c230  cmp     byte ptr [rcx+19h], 2
0x18001c234  jb      short loc_18001C264
0x18001c236  call    RdpX_GetActivityIdPrefix
0x18001c23b  lea     edx, [rbp+23h]
0x18001c23e  lea     rcx, aPrect; "pRect"
0x18001c245  mov     [rsp+68h+var_48], rcx
0x18001c24a  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001c251  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c258  mov     r9d, eax
0x18001c25b  mov     rcx, [rcx+10h]
0x18001c25f  call    WPP_SF_Ds
0x18001c264  mov     ebx, 80004003h
0x18001c269  jmp     loc_18001C365
0x18001c26e  test    rdi, rdi
0x18001c271  jnz     short loc_18001C2A3
0x18001c273  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c27a  lea     rax, WPP_GLOBAL_Control
0x18001c281  cmp     rcx, rax
0x18001c284  jz      short loc_18001C264
0x18001c286  test    byte ptr [rcx+1Ch], 8
0x18001c28a  jz      short loc_18001C264
0x18001c28c  cmp     byte ptr [rcx+19h], 2
0x18001c290  jb      short loc_18001C264
0x18001c292  call    RdpX_GetActivityIdPrefix
0x18001c297  lea     edx, [rdi+24h]
0x18001c29a  lea     rcx, aPintersectiona; "pIntersectionArea"
0x18001c2a1  jmp     short loc_18001C245
0x18001c2a3  mov     dword ptr [r8], 0
0x18001c2aa  call    ?UpdateRectsIter@RdpBoundsAccumulator@@AEBAJXZ; RdpBoundsAccumulator::UpdateRectsIter(void)
0x18001c2af  mov     ebx, eax
0x18001c2b1  test    eax, eax
0x18001c2b3  jns     short loc_18001C316
0x18001c2b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2bc  lea     rax, WPP_GLOBAL_Control
0x18001c2c3  cmp     rcx, rax
0x18001c2c6  jz      loc_18001C365
0x18001c2cc  test    byte ptr [rcx+1Ch], 8
0x18001c2d0  jz      loc_18001C365
0x18001c2d6  cmp     byte ptr [rcx+19h], 2
0x18001c2da  jb      loc_18001C365
0x18001c2e0  call    RdpX_GetActivityIdPrefix
0x18001c2e5  lea     rcx, aUpdaterectsite; "UpdateRectsIter failed"
0x18001c2ec  mov     [rsp+68h+var_40], ebx
0x18001c2f0  mov     [rsp+68h+var_48], rcx
0x18001c2f5  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001c2fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c303  mov     edx, 25h ; '%'
0x18001c308  mov     r9d, eax
0x18001c30b  mov     rcx, [rcx+10h]
0x18001c30f  call    WPP_SF_DsD
0x18001c314  jmp     short loc_18001C365
0x18001c316  xor     r10d, r10d
0x18001c319  cmp     [rsi+50h], r10d
0x18001c31d  jbe     short loc_18001C365
0x18001c31f  mov     r11d, [rdi]
0x18001c322  mov     rax, [rsi+48h]
0x18001c326  mov     rdx, rbp; struct RdpRect *
0x18001c329  mov     ecx, r10d
0x18001c32c  add     rcx, rcx
0x18001c32f  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18001c333  lea     rcx, [rsp+68h+var_38]; this
0x18001c338  movdqu  [rsp+68h+var_38], xmm0
0x18001c33e  call    ?Intersect@RdpRect@@QEAA_NAEBU1@@Z; RdpRect::Intersect(RdpRect const &)
0x18001c343  mov     eax, dword ptr [rsp+68h+var_38+8]
0x18001c347  inc     r10d
0x18001c34a  sub     eax, dword ptr [rsp+68h+var_38]
0x18001c34e  mov     ecx, dword ptr [rsp+68h+var_38+0Ch]
0x18001c352  sub     ecx, dword ptr [rsp+68h+var_38+4]
0x18001c356  imul    ecx, eax
0x18001c359  add     r11d, ecx
0x18001c35c  mov     [rdi], r11d
0x18001c35f  cmp     r10d, [rsi+50h]
0x18001c363  jb      short loc_18001C322
0x18001c365  mov     eax, ebx
0x18001c367  add     rsp, 48h
0x18001c36b  pop     rdi
0x18001c36c  pop     rsi
0x18001c36d  pop     rbp
0x18001c36e  pop     rbx
0x18001c36f  retn
```
