# RdpBoundsAccumulator::IntersectsBA(IRdpBoundsAccumulator const *,int *)

- ea: `0x18001bcc0`
- end: `0x18001be65`
- name: `?IntersectsBA@RdpBoundsAccumulator@@UEBAJPEBVIRdpBoundsAccumulator@@PEAH@Z`
- size: `421`
- prototype: `__int64 __fastcall(RdpBoundsAccumulator *this, const struct IRdpBoundsAccumulator *, int *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18001bcc0`
- `0x18001cc98`
- `0x18001d098`
- `0x18001d114`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x18001bda6`: `UpdateRectsIter failed`

## pseudocode

```c
__int64 __fastcall RdpBoundsAccumulator::IntersectsBA(
        RdpBoundsAccumulator *this,
        const struct IRdpBoundsAccumulator *a2,
        int *a3,
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
  int v15; // edx
  const char *v16; // rcx
  unsigned int i; // esi
  __int64 v18; // rax
  __int128 v19; // xmm0
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  _OWORD v25[3]; // [rsp+30h] [rbp-38h] BYREF

  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467261;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, 0, a3, a4);
    v8 = 38;
    v9 = "pSource";
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
    v8 = 39;
    v9 = "pResult";
    goto LABEL_6;
  }
  updated = RdpBoundsAccumulator::UpdateRectsIter(this);
  if ( updated >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= *((_DWORD *)this + 20) )
      {
        *a3 = 0;
        return (unsigned int)updated;
      }
      v18 = *((_QWORD *)this + 9);
      v25[0] = 0;
      v19 = *(_OWORD *)(v18 + 16LL * i);
      v20 = *(_QWORD *)a2;
      v25[0] = v19;
      updated = (*(__int64 (__fastcall **)(const struct IRdpBoundsAccumulator *, _OWORD *, int *))(v20 + 96))(
                  a2,
                  v25,
                  a3);
      if ( updated < 0 )
        break;
      if ( *a3 )
        return (unsigned int)updated;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v21, v22, v23);
      v15 = 41;
      v16 = "IntersectsRect failed";
      goto LABEL_18;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v11, v12, v13);
    v15 = 40;
    v16 = "UpdateRectsIter failed";
LABEL_18:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      (unsigned int)WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids,
      v14,
      (__int64)v16,
      updated);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18001bcc0  push    rbx
0x18001bcc2  push    rbp
0x18001bcc3  push    rsi
0x18001bcc4  push    rdi
0x18001bcc5  push    r14
0x18001bcc7  sub     rsp, 40h
0x18001bccb  mov     rdi, r8
0x18001bcce  mov     r14, rdx
0x18001bcd1  mov     rbp, rcx
0x18001bcd4  test    rdx, rdx
0x18001bcd7  jnz     short loc_18001BD31
0x18001bcd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bce0  lea     rax, WPP_GLOBAL_Control
0x18001bce7  cmp     rcx, rax
0x18001bcea  jz      short loc_18001BD27
0x18001bcec  test    byte ptr [rcx+1Ch], 8
0x18001bcf0  jz      short loc_18001BD27
0x18001bcf2  cmp     byte ptr [rcx+19h], 2
0x18001bcf6  jb      short loc_18001BD27
0x18001bcf8  call    RdpX_GetActivityIdPrefix
0x18001bcfd  lea     edx, [r14+26h]
0x18001bd01  lea     rcx, aPsource; "pSource"
0x18001bd08  mov     [rsp+68h+var_48], rcx
0x18001bd0d  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001bd14  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd1b  mov     r9d, eax
0x18001bd1e  mov     rcx, [rcx+10h]
0x18001bd22  call    WPP_SF_Ds
0x18001bd27  mov     ebx, 80004003h
0x18001bd2c  jmp     loc_18001BE58
0x18001bd31  test    rdi, rdi
0x18001bd34  jnz     short loc_18001BD66
0x18001bd36  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd3d  lea     rax, WPP_GLOBAL_Control
0x18001bd44  cmp     rcx, rax
0x18001bd47  jz      short loc_18001BD27
0x18001bd49  test    byte ptr [rcx+1Ch], 8
0x18001bd4d  jz      short loc_18001BD27
0x18001bd4f  cmp     byte ptr [rcx+19h], 2
0x18001bd53  jb      short loc_18001BD27
0x18001bd55  call    RdpX_GetActivityIdPrefix
0x18001bd5a  lea     edx, [rdi+27h]
0x18001bd5d  lea     rcx, aPresult; "pResult"
0x18001bd64  jmp     short loc_18001BD08
0x18001bd66  call    ?UpdateRectsIter@RdpBoundsAccumulator@@AEBAJXZ; RdpBoundsAccumulator::UpdateRectsIter(void)
0x18001bd6b  mov     ebx, eax
0x18001bd6d  test    eax, eax
0x18001bd6f  jns     short loc_18001BDD5
0x18001bd71  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd78  lea     rax, WPP_GLOBAL_Control
0x18001bd7f  cmp     rcx, rax
0x18001bd82  jz      loc_18001BE58
0x18001bd88  test    byte ptr [rcx+1Ch], 8
0x18001bd8c  jz      loc_18001BE58
0x18001bd92  cmp     byte ptr [rcx+19h], 2
0x18001bd96  jb      loc_18001BE58
0x18001bd9c  call    RdpX_GetActivityIdPrefix
0x18001bda1  mov     edx, 28h ; '('
0x18001bda6  lea     rcx, aUpdaterectsite; "UpdateRectsIter failed"
0x18001bdad  mov     [rsp+68h+var_40], ebx
0x18001bdb1  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001bdb8  mov     [rsp+68h+var_48], rcx
0x18001bdbd  mov     r9d, eax
0x18001bdc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bdc7  mov     rcx, [rcx+10h]
0x18001bdcb  call    WPP_SF_DsD
0x18001bdd0  jmp     loc_18001BE58
0x18001bdd5  xor     esi, esi
0x18001bdd7  cmp     esi, [rbp+50h]
0x18001bdda  jnb     short loc_18001BE52
0x18001bddc  mov     rax, [rbp+48h]
0x18001bde0  lea     rdx, [rsp+68h+var_38]
0x18001bde5  xorps   xmm0, xmm0
0x18001bde8  mov     ecx, esi
0x18001bdea  add     rcx, rcx
0x18001bded  mov     r8, rdi
0x18001bdf0  movups  [rsp+68h+var_38], xmm0
0x18001bdf5  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18001bdf9  mov     rax, [r14]
0x18001bdfc  mov     rcx, r14
0x18001bdff  movdqu  [rsp+68h+var_38], xmm0
0x18001be05  mov     rax, [rax+60h]
0x18001be09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be0e  mov     ebx, eax
0x18001be10  test    eax, eax
0x18001be12  js      short loc_18001BE1D
0x18001be14  cmp     dword ptr [rdi], 0
0x18001be17  jnz     short loc_18001BE58
0x18001be19  inc     esi
0x18001be1b  jmp     short loc_18001BDD7
0x18001be1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be24  lea     rax, WPP_GLOBAL_Control
0x18001be2b  cmp     rcx, rax
0x18001be2e  jz      short loc_18001BE58
0x18001be30  test    byte ptr [rcx+1Ch], 8
0x18001be34  jz      short loc_18001BE58
0x18001be36  cmp     byte ptr [rcx+19h], 2
0x18001be3a  jb      short loc_18001BE58
0x18001be3c  call    RdpX_GetActivityIdPrefix
0x18001be41  mov     edx, 29h ; ')'
0x18001be46  lea     rcx, aIntersectsrect; "IntersectsRect failed"
0x18001be4d  jmp     loc_18001BDAD
0x18001be52  mov     dword ptr [rdi], 0
0x18001be58  mov     eax, ebx
0x18001be5a  add     rsp, 40h
0x18001be5e  pop     r14
0x18001be60  pop     rdi
0x18001be61  pop     rsi
0x18001be62  pop     rbp
0x18001be63  pop     rbx
0x18001be64  retn
```
