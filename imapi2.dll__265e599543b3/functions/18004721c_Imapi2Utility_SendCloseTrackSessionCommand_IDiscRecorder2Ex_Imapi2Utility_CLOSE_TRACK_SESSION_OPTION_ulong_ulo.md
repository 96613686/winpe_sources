# Imapi2Utility::SendCloseTrackSessionCommand(IDiscRecorder2Ex *,Imapi2Utility::_CLOSE_TRACK_SESSION_OPTION,ulong,ulong,uchar)

- ea: `0x18004721c`
- end: `0x1800473ff`
- name: `?SendCloseTrackSessionCommand@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@W4_CLOSE_TRACK_SESSION_OPTION@1@KKE@Z`
- size: `483`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180018908`
- `0x180018aec`
- `0x180018cd0`
- `0x1800190f8`
- `0x180019490`
- `0x180019728`
- `0x1800369e0`
- `0x180039320`

## callees

- `0x18000ae3c`
- `0x1800140f4`
- `0x180023790`
- `0x18004721c`
- `0x180048df0`
- `0x180049880`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::SendCloseTrackSessionCommand(__int64 *a1, int a2, unsigned int a3, int a4, char a5)
{
  unsigned int v5; // ebx
  int v6; // eax
  int v9; // ecx
  __int64 v10; // rax
  int v11; // eax
  int *v12; // r9
  PVOID *v13; // rcx
  PVOID v14; // rcx
  struct _SENSE_DATA v16; // [rsp+40h] [rbp-11h] BYREF
  int v17; // [rsp+52h] [rbp+1h]
  __int16 v18; // [rsp+56h] [rbp+5h]
  union _CDB *v19; // [rsp+58h] [rbp+7h]
  __int128 v20; // [rsp+60h] [rbp+Fh] BYREF
  union _CDB v21; // [rsp+70h] [rbp+1Fh] BYREF
  __int16 v22; // [rsp+80h] [rbp+2Fh]

  v5 = 0;
  v6 = 0;
  v9 = -2147024809;
  if ( a2 != 1 && a2 != 2 && a2 != 3 && a2 != 4 && a2 != 5 && a2 != 6 )
  {
    v5 = -2147024809;
    v6 = -2147024809;
  }
  if ( a3 == -1 || a3 <= 0xFFFF )
    v9 = v6;
  else
    v5 = -2147024809;
  if ( v9 >= 0 )
  {
    v22 = 0;
    v20 = 0;
    BYTE5(v20) = a3;
    BYTE1(v20) = a5 != 0;
    LOBYTE(v20) = 91;
    BYTE4(v20) = BYTE1(a3);
    BYTE2(v20) = a2 & 7;
    v10 = *a1;
    v21 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64, union _CDB *, int))(v10 + 24))(
            a1,
            &v20,
            10,
            &v21,
            a4);
    *(_DWORD *)&v16 = v11;
    v5 = v11;
    if ( v11 == 11141632 )
    {
      Imapi2Utility::TranslateSenseInfoToHResult((Imapi2Utility *)&v20, &v21, &v16, v12);
      v13 = (PVOID *)WPP_GLOBAL_Control;
      v5 = (unsigned int)v16;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_DDDLd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            59,
            v21.CDB16.TransferLength[2],
            v21.CDB6GENERIC.CommandUniqueBytes[0] & 0xF,
            v21.CDB16.TransferLength[2],
            v21.CDB16.TransferLength[3],
            a2,
            *(_DWORD *)&v16);
          v13 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 4) != 0 && *((_BYTE *)v13 + 25) >= 3u )
        {
          v14 = v13[2];
          v17 = 0;
          *(_WORD *)&v16.SenseKeySpecific[1] = 18;
          v18 = 0;
          v19 = &v21;
          WPP_SF__HEX_(v14, 60, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, &v16.SenseKeySpecific[1]);
        }
      }
    }
    else if ( v11 < 0
           && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
        (unsigned int)v11);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18004721c  mov     [rsp-8+arg_8], rbx
0x180047221  push    rbp
0x180047222  push    rsi
0x180047223  push    rdi
0x180047224  lea     rbp, [rsp-3Fh]
0x180047229  sub     rsp, 90h
0x180047230  mov     rax, cs:__security_cookie
0x180047237  xor     rax, rsp
0x18004723a  mov     [rbp+4Fh+var_18], rax
0x18004723e  xor     ebx, ebx
0x180047240  xor     eax, eax
0x180047242  mov     r10, rcx
0x180047245  mov     edi, edx
0x180047247  mov     ecx, 80070057h
0x18004724c  cmp     edx, 1
0x18004724f  jz      short loc_18004726E
0x180047251  cmp     edx, 2
0x180047254  jz      short loc_18004726E
0x180047256  cmp     edx, 3
0x180047259  jz      short loc_18004726E
0x18004725b  cmp     edx, 4
0x18004725e  jz      short loc_18004726E
0x180047260  cmp     edx, 5
0x180047263  jz      short loc_18004726E
0x180047265  cmp     edx, 6
0x180047268  jz      short loc_18004726E
0x18004726a  mov     ebx, ecx
0x18004726c  mov     eax, ecx
0x18004726e  cmp     r8d, 0FFFFFFFFh
0x180047272  jz      short loc_180047281
0x180047274  cmp     r8d, 0FFFFh
0x18004727b  jbe     short loc_180047281
0x18004727d  mov     ebx, ecx
0x18004727f  jmp     short loc_180047283
0x180047281  mov     ecx, eax
0x180047283  test    ecx, ecx
0x180047285  js      loc_1800473DE
0x18004728b  xor     eax, eax
0x18004728d  mov     [rsp+0A0h+var_80], r9d
0x180047292  cmp     [rbp+4Fh+arg_20], al
0x180047295  lea     r9, [rbp+4Fh+var_30]
0x180047299  mov     [rbp+4Fh+var_20], ax
0x18004729d  lea     rdx, [rbp+4Fh+var_40]
0x1800472a1  mov     eax, r8d
0x1800472a4  xorps   xmm0, xmm0
0x1800472a7  movups  [rbp+4Fh+var_40], xmm0
0x1800472ab  mov     byte ptr [rbp+4Fh+var_40+5], r8b
0x1800472af  mov     r8d, 0Ah
0x1800472b5  setnz   byte ptr [rbp+4Fh+var_40+1]
0x1800472b9  mov     byte ptr [rbp+4Fh+var_40], 5Bh ; '['
0x1800472bd  shr     eax, 8
0x1800472c0  mov     rcx, r10
0x1800472c3  mov     byte ptr [rbp+4Fh+var_40+4], al
0x1800472c6  mov     al, dil
0x1800472c9  and     al, 7
0x1800472cb  mov     byte ptr [rbp+4Fh+var_40+2], al
0x1800472ce  mov     rax, [r10]
0x1800472d1  movups  xmmword ptr [rbp+4Fh+var_30], xmm0
0x1800472d5  mov     rax, [rax+18h]
0x1800472d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472de  mov     dword ptr [rbp+4Fh+var_60.ErrorCode], eax
0x1800472e1  mov     ebx, eax
0x1800472e3  cmp     eax, 0AA0200h
0x1800472e8  jnz     loc_1800473A3
0x1800472ee  lea     r8, [rbp+4Fh+var_60]; struct _SENSE_DATA *
0x1800472f2  lea     rdx, [rbp+4Fh+var_30]; union _CDB *
0x1800472f6  lea     rcx, [rbp+4Fh+var_40]; this
0x1800472fa  call    ?TranslateSenseInfoToHResult@Imapi2Utility@@YA?BEPEBT_CDB@@PEBU_SENSE_DATA@@PEAJ@Z; Imapi2Utility::TranslateSenseInfoToHResult(_CDB const *,_SENSE_DATA const *,long *)
0x1800472ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180047306  lea     rsi, WPP_GLOBAL_Control
0x18004730d  mov     ebx, dword ptr [rbp+4Fh+var_60.ErrorCode]
0x180047310  cmp     rcx, rsi
0x180047313  jz      loc_1800473DE
0x180047319  test    byte ptr [rcx+1Ch], 4
0x18004731d  jz      short loc_18004735D
0x18004731f  cmp     byte ptr [rcx+19h], 3
0x180047323  jb      short loc_18004735D
0x180047325  movzx   eax, byte ptr [rbp+4Fh+var_30+0Dh]
0x180047329  mov     edx, 3Bh ; ';'
0x18004732e  movzx   r9d, byte ptr [rbp+4Fh+var_30+2]
0x180047333  movzx   r8d, byte ptr [rbp+4Fh+var_30+0Ch]
0x180047338  and     r9d, 0Fh
0x18004733c  mov     rcx, [rcx+10h]
0x180047340  mov     [rsp+0A0h+var_68], ebx
0x180047344  mov     [rsp+0A0h+var_70], edi
0x180047348  mov     [rsp+0A0h+var_78], eax
0x18004734c  mov     [rsp+0A0h+var_80], r8d
0x180047351  call    WPP_SF_DDDLd
0x180047356  mov     rcx, cs:WPP_GLOBAL_Control
0x18004735d  cmp     rcx, rsi
0x180047360  jz      short loc_1800473DE
0x180047362  test    byte ptr [rcx+1Ch], 4
0x180047366  jz      short loc_1800473DE
0x180047368  cmp     byte ptr [rcx+19h], 3
0x18004736c  jb      short loc_1800473DE
0x18004736e  mov     rcx, [rcx+10h]
0x180047372  lea     r9, [rbp+4Fh+var_60.SenseKeySpecific+1]
0x180047376  xor     edx, edx
0x180047378  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18004737f  mov     eax, 12h
0x180047384  mov     [rbp+4Fh+var_4E], edx
0x180047387  mov     word ptr [rbp+4Fh+var_60.SenseKeySpecific+1], ax
0x18004738b  lea     rax, [rbp+4Fh+var_30]
0x18004738f  mov     [rbp+4Fh+var_4A], dx
0x180047393  mov     edx, 3Ch ; '<'
0x180047398  mov     [rbp+4Fh+var_48], rax
0x18004739c  call    WPP_SF__HEX_
0x1800473a1  jmp     short loc_1800473DE
0x1800473a3  test    eax, eax
0x1800473a5  jns     short loc_1800473DE
0x1800473a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800473ae  lea     rsi, WPP_GLOBAL_Control
0x1800473b5  cmp     rcx, rsi
0x1800473b8  jz      short loc_1800473DE
0x1800473ba  test    byte ptr [rcx+1Ch], 4
0x1800473be  jz      short loc_1800473DE
0x1800473c0  cmp     byte ptr [rcx+19h], 3
0x1800473c4  jb      short loc_1800473DE
0x1800473c6  mov     rcx, [rcx+10h]
0x1800473ca  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x1800473d1  mov     edx, 3Dh ; '='
0x1800473d6  mov     r9d, eax
0x1800473d9  call    WPP_SF_d
0x1800473de  mov     eax, ebx
0x1800473e0  mov     rcx, [rbp+4Fh+var_18]
0x1800473e4  xor     rcx, rsp; StackCookie
0x1800473e7  call    __security_check_cookie
0x1800473ec  mov     rbx, [rsp+0A0h+arg_8]
0x1800473f4  add     rsp, 90h
0x1800473fb  pop     rdi
0x1800473fc  pop     rsi
0x1800473fd  pop     rbp
0x1800473fe  retn
```
