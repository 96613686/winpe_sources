# RdpBoundsAccumulator::ContainsPoint(int,int,int *)

- ea: `0x18001b090`
- end: `0x18001b1ab`
- name: `?ContainsPoint@RdpBoundsAccumulator@@UEBAJHHPEAH@Z`
- size: `283`
- prototype: `__int64 __fastcall(RdpBoundsAccumulator *this, __int64, __int64, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x18001b090`
- `0x18001cc98`
- `0x18001d098`
- `0x18001d114`
- `0x18002a1c4`

## string_xrefs

- `0x18001b132`: `UpdateRectsIter failed`

## pseudocode

```c
__int64 __fastcall RdpBoundsAccumulator::ContainsPoint(RdpBoundsAccumulator *this, __int64 a2, __int64 a3, int *a4)
{
  int v5; // ebp
  int v6; // r14d
  int v8; // eax
  int updated; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  int ActivityIdPrefix; // eax
  unsigned int i; // ecx
  __int64 v14; // rdx

  v5 = a3;
  v6 = a2;
  if ( a4 )
  {
    updated = RdpBoundsAccumulator::UpdateRectsIter(this);
    if ( updated >= 0 )
    {
      for ( i = 0; i < *((_DWORD *)this + 20); ++i )
      {
        v14 = *((_QWORD *)this + 9);
        if ( *(_DWORD *)(v14 + 16LL * i) <= v6
          && *(_DWORD *)(v14 + 16LL * i + 4) <= v5
          && *(_DWORD *)(v14 + 16LL * i + 8) > v6
          && *(_DWORD *)(v14 + 16LL * i + 12) > v5 )
        {
          *a4 = 1;
          return (unsigned int)updated;
        }
      }
      *a4 = 0;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, WPP_GLOBAL_Control, v10, v11);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        (unsigned int)WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids,
        ActivityIdPrefix,
        (__int64)"UpdateRectsIter failed",
        updated);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, a2, a3, 0);
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        (unsigned int)WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids,
        v8,
        (__int64)"pResult");
    }
    return (unsigned int)-2147467261;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18001b090  push    rbx
0x18001b092  push    rbp
0x18001b093  push    rsi
0x18001b094  push    rdi
0x18001b095  push    r14
0x18001b097  sub     rsp, 30h
0x18001b09b  mov     rdi, r9
0x18001b09e  mov     ebp, r8d
0x18001b0a1  mov     r14d, edx
0x18001b0a4  mov     rsi, rcx
0x18001b0a7  test    r9, r9
0x18001b0aa  jnz     short loc_18001B103
0x18001b0ac  mov     rax, cs:WPP_GLOBAL_Control
0x18001b0b3  lea     rcx, WPP_GLOBAL_Control
0x18001b0ba  cmp     rax, rcx
0x18001b0bd  jz      short loc_18001B0F9
0x18001b0bf  test    byte ptr [rax+1Ch], 8
0x18001b0c3  jz      short loc_18001B0F9
0x18001b0c5  cmp     byte ptr [rax+19h], 2
0x18001b0c9  jb      short loc_18001B0F9
0x18001b0cb  call    RdpX_GetActivityIdPrefix
0x18001b0d0  lea     rcx, aPresult; "pResult"
0x18001b0d7  mov     r9d, eax
0x18001b0da  mov     [rsp+58h+var_38], rcx
0x18001b0df  lea     edx, [rdi+2Ch]
0x18001b0e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0e9  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001b0f0  mov     rcx, [rcx+10h]
0x18001b0f4  call    WPP_SF_Ds
0x18001b0f9  mov     ebx, 80004003h
0x18001b0fe  jmp     loc_18001B19E
0x18001b103  call    ?UpdateRectsIter@RdpBoundsAccumulator@@AEBAJXZ; RdpBoundsAccumulator::UpdateRectsIter(void)
0x18001b108  mov     ebx, eax
0x18001b10a  test    eax, eax
0x18001b10c  jns     short loc_18001B163
0x18001b10e  mov     rdx, cs:WPP_GLOBAL_Control
0x18001b115  lea     rcx, WPP_GLOBAL_Control
0x18001b11c  cmp     rdx, rcx
0x18001b11f  jz      short loc_18001B19E
0x18001b121  test    byte ptr [rdx+1Ch], 8
0x18001b125  jz      short loc_18001B19E
0x18001b127  cmp     byte ptr [rdx+19h], 2
0x18001b12b  jb      short loc_18001B19E
0x18001b12d  call    RdpX_GetActivityIdPrefix
0x18001b132  lea     rcx, aUpdaterectsite; "UpdateRectsIter failed"
0x18001b139  mov     [rsp+58h+var_30], ebx
0x18001b13d  mov     [rsp+58h+var_38], rcx
0x18001b142  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001b149  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b150  mov     edx, 2Dh ; '-'
0x18001b155  mov     r9d, eax
0x18001b158  mov     rcx, [rcx+10h]
0x18001b15c  call    WPP_SF_DsD
0x18001b161  jmp     short loc_18001B19E
0x18001b163  xor     ecx, ecx
0x18001b165  cmp     ecx, [rsi+50h]
0x18001b168  jnb     short loc_18001B198
0x18001b16a  mov     rdx, [rsi+48h]
0x18001b16e  mov     eax, ecx
0x18001b170  add     rax, rax
0x18001b173  cmp     [rdx+rax*8], r14d
0x18001b177  jg      short loc_18001B18C
0x18001b179  cmp     [rdx+rax*8+4], ebp
0x18001b17d  jg      short loc_18001B18C
0x18001b17f  cmp     [rdx+rax*8+8], r14d
0x18001b184  jle     short loc_18001B18C
0x18001b186  cmp     [rdx+rax*8+0Ch], ebp
0x18001b18a  jg      short loc_18001B190
0x18001b18c  inc     ecx
0x18001b18e  jmp     short loc_18001B165
0x18001b190  mov     dword ptr [rdi], 1
0x18001b196  jmp     short loc_18001B19E
0x18001b198  mov     dword ptr [rdi], 0
0x18001b19e  mov     eax, ebx
0x18001b1a0  add     rsp, 30h
0x18001b1a4  pop     r14
0x18001b1a6  pop     rdi
0x18001b1a7  pop     rsi
0x18001b1a8  pop     rbp
0x18001b1a9  pop     rbx
0x18001b1aa  retn
```
