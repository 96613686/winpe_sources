# Imapi2Utility::SendStartStopUnitCommand(IDiscRecorder2Ex *,Imapi2Utility::_START_STOP_OPTION)

- ea: `0x180047408`
- end: `0x18004758f`
- name: `?SendStartStopUnitCommand@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@W4_START_STOP_OPTION@1@@Z`
- size: `391`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001dd30`
- `0x180025dd0`
- `0x1800306c0`

## callees

- `0x18000ae3c`
- `0x1800140f4`
- `0x180023790`
- `0x180047408`
- `0x180048df0`
- `0x180049880`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::SendStartStopUnitCommand(__int64 *a1)
{
  __int64 v1; // rax
  __int64 (__fastcall *v2)(__int64 *, __int128 *, __int64, union _CDB *, int); // rax
  int v3; // eax
  int *v4; // r9
  unsigned int v5; // ebx
  PVOID *v6; // rcx
  PVOID v7; // rcx
  struct _SENSE_DATA v9; // [rsp+40h] [rbp+7h] BYREF
  int v10; // [rsp+52h] [rbp+19h]
  __int16 v11; // [rsp+56h] [rbp+1Dh]
  union _CDB *v12; // [rsp+58h] [rbp+1Fh]
  union _CDB v13; // [rsp+60h] [rbp+27h] BYREF
  __int16 v14; // [rsp+70h] [rbp+37h]
  __int128 v15; // [rsp+78h] [rbp+3Fh] BYREF

  v14 = 0;
  v1 = *a1;
  v15 = 0;
  LOBYTE(v15) = 27;
  v2 = *(__int64 (__fastcall **)(__int64 *, __int128 *, __int64, union _CDB *, int))(v1 + 24);
  v13 = 0;
  BYTE4(v15) = 1;
  v3 = v2(a1, &v15, 6, &v13, 60);
  *(_DWORD *)&v9 = v3;
  v5 = v3;
  if ( v3 == 11141632 )
  {
    Imapi2Utility::TranslateSenseInfoToHResult((Imapi2Utility *)&v15, &v13, &v9, v4);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v5 = (unsigned int)v9;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_DDDLd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          v13.CDB16.TransferLength[2],
          v13.CDB6GENERIC.CommandUniqueBytes[0] & 0xF,
          v13.CDB16.TransferLength[2],
          v13.CDB16.TransferLength[3],
          1,
          *(_DWORD *)&v9);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 && *((_BYTE *)v6 + 25) >= 3u )
      {
        v7 = v6[2];
        v10 = 0;
        *(_WORD *)&v9.SenseKeySpecific[1] = 18;
        v11 = 0;
        v12 = &v13;
        WPP_SF__HEX_(v7, 38, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, &v9.SenseKeySpecific[1]);
      }
    }
  }
  else if ( v3 < 0
         && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
      (unsigned int)v3);
  }
  return v5;
}

```

## disassembly

```asm
0x180047408  mov     [rsp-8+arg_8], rbx
0x18004740d  mov     [rsp-8+arg_10], rdi
0x180047412  push    rbp
0x180047413  lea     rbp, [rsp-57h]
0x180047418  sub     rsp, 90h
0x18004741f  mov     rax, cs:__security_cookie
0x180047426  xor     rax, rsp
0x180047429  mov     [rbp+57h+var_8], rax
0x18004742d  xor     eax, eax
0x18004742f  mov     [rsp+90h+var_70], 3Ch ; '<'
0x180047437  mov     [rbp+57h+var_20], ax
0x18004743b  lea     r9, [rbp+57h+var_30]
0x18004743f  mov     rax, [rcx]
0x180047442  lea     rdx, [rbp+57h+var_18]
0x180047446  xorps   xmm0, xmm0
0x180047449  mov     r8d, 6
0x18004744f  movups  [rbp+57h+var_18], xmm0
0x180047453  mov     byte ptr [rbp+57h+var_18], 1Bh
0x180047457  mov     rax, [rax+18h]
0x18004745b  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x18004745f  mov     byte ptr [rbp+57h+var_18+4], 1
0x180047463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047468  mov     dword ptr [rbp+57h+var_50.ErrorCode], eax
0x18004746b  mov     ebx, eax
0x18004746d  cmp     eax, 0AA0200h
0x180047472  jnz     loc_180047531
0x180047478  lea     r8, [rbp+57h+var_50]; struct _SENSE_DATA *
0x18004747c  lea     rdx, [rbp+57h+var_30]; union _CDB *
0x180047480  lea     rcx, [rbp+57h+var_18]; this
0x180047484  call    ?TranslateSenseInfoToHResult@Imapi2Utility@@YA?BEPEBT_CDB@@PEBU_SENSE_DATA@@PEAJ@Z; Imapi2Utility::TranslateSenseInfoToHResult(_CDB const *,_SENSE_DATA const *,long *)
0x180047489  mov     rcx, cs:WPP_GLOBAL_Control
0x180047490  lea     rdi, WPP_GLOBAL_Control
0x180047497  mov     ebx, dword ptr [rbp+57h+var_50.ErrorCode]
0x18004749a  cmp     rcx, rdi
0x18004749d  jz      loc_18004756C
0x1800474a3  test    byte ptr [rcx+1Ch], 4
0x1800474a7  jz      short loc_1800474EB
0x1800474a9  cmp     byte ptr [rcx+19h], 3
0x1800474ad  jb      short loc_1800474EB
0x1800474af  movzx   eax, byte ptr [rbp+57h+var_30+0Dh]
0x1800474b3  mov     edx, 25h ; '%'
0x1800474b8  movzx   r9d, byte ptr [rbp+57h+var_30+2]
0x1800474bd  movzx   r8d, byte ptr [rbp+57h+var_30+0Ch]
0x1800474c2  and     r9d, 0Fh
0x1800474c6  mov     rcx, [rcx+10h]
0x1800474ca  mov     [rsp+90h+var_58], ebx
0x1800474ce  mov     [rsp+90h+var_60], 1
0x1800474d6  mov     [rsp+90h+var_68], eax
0x1800474da  mov     [rsp+90h+var_70], r8d
0x1800474df  call    WPP_SF_DDDLd
0x1800474e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800474eb  cmp     rcx, rdi
0x1800474ee  jz      short loc_18004756C
0x1800474f0  test    byte ptr [rcx+1Ch], 4
0x1800474f4  jz      short loc_18004756C
0x1800474f6  cmp     byte ptr [rcx+19h], 3
0x1800474fa  jb      short loc_18004756C
0x1800474fc  mov     rcx, [rcx+10h]
0x180047500  lea     r9, [rbp+57h+var_50.SenseKeySpecific+1]
0x180047504  xor     edx, edx
0x180047506  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18004750d  mov     eax, 12h
0x180047512  mov     [rbp+57h+var_3E], edx
0x180047515  mov     word ptr [rbp+57h+var_50.SenseKeySpecific+1], ax
0x180047519  lea     rax, [rbp+57h+var_30]
0x18004751d  mov     [rbp+57h+var_3A], dx
0x180047521  mov     edx, 26h ; '&'
0x180047526  mov     [rbp+57h+var_38], rax
0x18004752a  call    WPP_SF__HEX_
0x18004752f  jmp     short loc_18004756C
0x180047531  test    eax, eax
0x180047533  jns     short loc_18004756C
0x180047535  mov     rcx, cs:WPP_GLOBAL_Control
0x18004753c  lea     rdi, WPP_GLOBAL_Control
0x180047543  cmp     rcx, rdi
0x180047546  jz      short loc_18004756C
0x180047548  test    byte ptr [rcx+1Ch], 4
0x18004754c  jz      short loc_18004756C
0x18004754e  cmp     byte ptr [rcx+19h], 3
0x180047552  jb      short loc_18004756C
0x180047554  mov     rcx, [rcx+10h]
0x180047558  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18004755f  mov     edx, 27h ; '''
0x180047564  mov     r9d, eax
0x180047567  call    WPP_SF_d
0x18004756c  mov     eax, ebx
0x18004756e  mov     rcx, [rbp+57h+var_8]
0x180047572  xor     rcx, rsp; StackCookie
0x180047575  call    __security_check_cookie
0x18004757a  lea     r11, [rsp+90h+var_s0]
0x180047582  mov     rbx, [r11+18h]
0x180047586  mov     rdi, [r11+20h]
0x18004758a  mov     rsp, r11
0x18004758d  pop     rbp
0x18004758e  retn
```
