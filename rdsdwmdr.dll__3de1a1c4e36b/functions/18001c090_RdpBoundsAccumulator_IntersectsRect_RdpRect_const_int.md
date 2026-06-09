# RdpBoundsAccumulator::IntersectsRect(RdpRect const *,int *)

- ea: `0x18001c090`
- end: `0x18001c1ee`
- name: `?IntersectsRect@RdpBoundsAccumulator@@UEBAJPEBURdpRect@@PEAH@Z`
- size: `350`
- prototype: `__int64 __fastcall(RdpBoundsAccumulator *this, const struct RdpRect *, int *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x18001c090`
- `0x18001cc98`
- `0x18001d098`
- `0x18001d114`
- `0x18002a1c4`

## string_xrefs

- `0x18001c16a`: `UpdateRectsIter failed`

## pseudocode

```c
__int64 __fastcall RdpBoundsAccumulator::IntersectsRect(
        RdpBoundsAccumulator *this,
        const struct RdpRect *a2,
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
  unsigned int i; // edx
  __int64 v16; // r8

  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467261;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, 0, a3, a4);
    v8 = 32;
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
    v8 = 33;
    v9 = "pResult";
    goto LABEL_6;
  }
  updated = RdpBoundsAccumulator::UpdateRectsIter(this);
  if ( updated >= 0 )
  {
    for ( i = 0; i < *((_DWORD *)this + 20); ++i )
    {
      v16 = *((_QWORD *)this + 9);
      if ( *(_DWORD *)(v16 + 16LL * i + 8) > *(_DWORD *)a2
        && *(_DWORD *)(v16 + 16LL * i) < *((_DWORD *)a2 + 2)
        && *(_DWORD *)(v16 + 16LL * i + 12) > *((_DWORD *)a2 + 1)
        && *(_DWORD *)(v16 + 16LL * i + 4) < *((_DWORD *)a2 + 3) )
      {
        *a3 = 1;
        return (unsigned int)updated;
      }
    }
    *a3 = 0;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v11, v12, v13);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
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
0x18001c090  push    rbx
0x18001c092  push    rbp
0x18001c093  push    rsi
0x18001c094  push    rdi
0x18001c095  sub     rsp, 38h
0x18001c099  mov     rdi, r8
0x18001c09c  mov     rsi, rdx
0x18001c09f  mov     rbp, rcx
0x18001c0a2  test    rdx, rdx
0x18001c0a5  jnz     short loc_18001C0FE
0x18001c0a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0ae  lea     rax, WPP_GLOBAL_Control
0x18001c0b5  cmp     rcx, rax
0x18001c0b8  jz      short loc_18001C0F4
0x18001c0ba  test    byte ptr [rcx+1Ch], 8
0x18001c0be  jz      short loc_18001C0F4
0x18001c0c0  cmp     byte ptr [rcx+19h], 2
0x18001c0c4  jb      short loc_18001C0F4
0x18001c0c6  call    RdpX_GetActivityIdPrefix
0x18001c0cb  lea     edx, [rsi+20h]
0x18001c0ce  lea     rcx, aPrect; "pRect"
0x18001c0d5  mov     [rsp+58h+var_38], rcx
0x18001c0da  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001c0e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0e8  mov     r9d, eax
0x18001c0eb  mov     rcx, [rcx+10h]
0x18001c0ef  call    WPP_SF_Ds
0x18001c0f4  mov     ebx, 80004003h
0x18001c0f9  jmp     loc_18001C1E3
0x18001c0fe  test    rdi, rdi
0x18001c101  jnz     short loc_18001C133
0x18001c103  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c10a  lea     rax, WPP_GLOBAL_Control
0x18001c111  cmp     rcx, rax
0x18001c114  jz      short loc_18001C0F4
0x18001c116  test    byte ptr [rcx+1Ch], 8
0x18001c11a  jz      short loc_18001C0F4
0x18001c11c  cmp     byte ptr [rcx+19h], 2
0x18001c120  jb      short loc_18001C0F4
0x18001c122  call    RdpX_GetActivityIdPrefix
0x18001c127  lea     edx, [rdi+21h]
0x18001c12a  lea     rcx, aPresult; "pResult"
0x18001c131  jmp     short loc_18001C0D5
0x18001c133  call    ?UpdateRectsIter@RdpBoundsAccumulator@@AEBAJXZ; RdpBoundsAccumulator::UpdateRectsIter(void)
0x18001c138  mov     ebx, eax
0x18001c13a  test    eax, eax
0x18001c13c  jns     short loc_18001C19B
0x18001c13e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c145  lea     rax, WPP_GLOBAL_Control
0x18001c14c  cmp     rcx, rax
0x18001c14f  jz      loc_18001C1E3
0x18001c155  test    byte ptr [rcx+1Ch], 8
0x18001c159  jz      loc_18001C1E3
0x18001c15f  cmp     byte ptr [rcx+19h], 2
0x18001c163  jb      short loc_18001C1E3
0x18001c165  call    RdpX_GetActivityIdPrefix
0x18001c16a  lea     rcx, aUpdaterectsite; "UpdateRectsIter failed"
0x18001c171  mov     [rsp+58h+var_30], ebx
0x18001c175  mov     [rsp+58h+var_38], rcx
0x18001c17a  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001c181  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c188  mov     edx, 22h ; '"'
0x18001c18d  mov     r9d, eax
0x18001c190  mov     rcx, [rcx+10h]
0x18001c194  call    WPP_SF_DsD
0x18001c199  jmp     short loc_18001C1E3
0x18001c19b  xor     edx, edx
0x18001c19d  cmp     edx, [rbp+50h]
0x18001c1a0  jnb     short loc_18001C1DD
0x18001c1a2  mov     r8, [rbp+48h]
0x18001c1a6  mov     eax, [rsi]
0x18001c1a8  mov     ecx, edx
0x18001c1aa  add     rcx, rcx
0x18001c1ad  cmp     [r8+rcx*8+8], eax
0x18001c1b2  jle     short loc_18001C1D1
0x18001c1b4  mov     eax, [rsi+8]
0x18001c1b7  cmp     [r8+rcx*8], eax
0x18001c1bb  jge     short loc_18001C1D1
0x18001c1bd  mov     eax, [rsi+4]
0x18001c1c0  cmp     [r8+rcx*8+0Ch], eax
0x18001c1c5  jle     short loc_18001C1D1
0x18001c1c7  mov     eax, [rsi+0Ch]
0x18001c1ca  cmp     [r8+rcx*8+4], eax
0x18001c1cf  jl      short loc_18001C1D5
0x18001c1d1  inc     edx
0x18001c1d3  jmp     short loc_18001C19D
0x18001c1d5  mov     dword ptr [rdi], 1
0x18001c1db  jmp     short loc_18001C1E3
0x18001c1dd  mov     dword ptr [rdi], 0
0x18001c1e3  mov     eax, ebx
0x18001c1e5  add     rsp, 38h
0x18001c1e9  pop     rdi
0x18001c1ea  pop     rsi
0x18001c1eb  pop     rbp
0x18001c1ec  pop     rbx
0x18001c1ed  retn
```
