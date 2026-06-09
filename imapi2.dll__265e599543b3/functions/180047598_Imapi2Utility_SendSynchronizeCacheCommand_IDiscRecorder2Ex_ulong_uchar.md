# Imapi2Utility::SendSynchronizeCacheCommand(IDiscRecorder2Ex *,ulong,uchar)

- ea: `0x180047598`
- end: `0x180047721`
- name: `?SendSynchronizeCacheCommand@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@KE@Z`
- size: `393`
- prototype: `__int64 __fastcall(Imapi2Utility *__hidden this, struct IDiscRecorder2Ex *, unsigned int, unsigned __int8)`
- caller_count: `11`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180018908`
- `0x180018aec`
- `0x180018cd0`
- `0x180018e80`
- `0x1800190f8`
- `0x180019490`
- `0x180019728`
- `0x18001dd30`
- `0x180025508`
- `0x1800306c0`
- `0x1800369e0`

## callees

- `0x18000ae3c`
- `0x1800140f4`
- `0x180047598`
- `0x180048fdc`
- `0x180049880`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::SendSynchronizeCacheCommand(
        Imapi2Utility *this,
        struct IDiscRecorder2Ex *a2,
        unsigned __int8 a3)
{
  int v3; // edi
  __int64 v4; // rax
  __int64 (__fastcall *v5)(Imapi2Utility *, __int128 *, __int64, union _CDB *, int); // rax
  int *v6; // r9
  unsigned int v7; // ebx
  unsigned __int8 v8; // al
  struct _SENSE_DATA v10; // [rsp+50h] [rbp+7h] BYREF
  int v11; // [rsp+62h] [rbp+19h]
  __int16 v12; // [rsp+66h] [rbp+1Dh]
  union _CDB *v13; // [rsp+68h] [rbp+1Fh]
  union _CDB v14; // [rsp+70h] [rbp+27h] BYREF
  __int16 v15; // [rsp+80h] [rbp+37h]
  __int128 v16; // [rsp+88h] [rbp+3Fh] BYREF

  v3 = a3;
  v15 = 0;
  v4 = *(_QWORD *)this;
  v16 = 0;
  v5 = *(__int64 (__fastcall **)(Imapi2Utility *, __int128 *, __int64, union _CDB *, int))(v4 + 24);
  BYTE1(v16) = a3 != 0 ? 2 : 0;
  v14 = 0;
  LOBYTE(v16) = 53;
  *(_DWORD *)&v10 = v5(this, &v16, 10, &v14, 260);
  v7 = (unsigned int)v10;
  if ( *(_DWORD *)&v10 == 11141632 )
  {
    v8 = Imapi2Utility::TranslateSenseInfoToHResult((Imapi2Utility *)&v16, &v14, &v10, v6);
    v7 = (unsigned int)v10;
    if ( !v8 )
      v7 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      *(_WORD *)&v10.SenseKeySpecific[1] = 18;
      v13 = &v14;
      v11 = 0;
      v12 = 0;
      WPP_SF_ddDDDd_HEX_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        v14.CDB16.TransferLength[2],
        v3,
        260,
        v14.CDB6GENERIC.CommandUniqueBytes[0] & 0xF,
        v14.CDB16.TransferLength[2],
        v14.CDB16.TransferLength[3],
        v7,
        (__int64)&v10.SenseKeySpecific[1]);
    }
  }
  else if ( *(_DWORD *)&v10 < 0
         && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, *(_DWORD *)&v10);
  }
  return v7;
}

```

## disassembly

```asm
0x180047598  mov     [rsp-8+arg_8], rbx
0x18004759d  mov     [rsp-8+arg_18], rdi
0x1800475a2  push    rbp
0x1800475a3  lea     rbp, [rsp-57h]
0x1800475a8  sub     rsp, 0A0h
0x1800475af  mov     rax, cs:__security_cookie
0x1800475b6  xor     rax, rsp
0x1800475b9  mov     [rbp+57h+var_8], rax
0x1800475bd  xor     eax, eax
0x1800475bf  movzx   edi, r8b
0x1800475c3  mov     [rbp+57h+var_20], ax
0x1800475c7  lea     r9, [rbp+57h+var_30]
0x1800475cb  mov     al, dil
0x1800475ce  mov     [rsp+0A0h+var_80], 104h
0x1800475d6  neg     al
0x1800475d8  xorps   xmm0, xmm0
0x1800475db  mov     rax, [rcx]
0x1800475de  xorps   xmm1, xmm1
0x1800475e1  sbb     dl, dl
0x1800475e3  mov     r8d, 0Ah
0x1800475e9  and     dl, 2
0x1800475ec  movups  [rbp+57h+var_18], xmm0
0x1800475f0  mov     rax, [rax+18h]
0x1800475f4  mov     byte ptr [rbp+57h+var_18+1], dl
0x1800475f7  lea     rdx, [rbp+57h+var_18]
0x1800475fb  movups  xmmword ptr [rbp+57h+var_30], xmm1
0x1800475ff  mov     byte ptr [rbp+57h+var_18], 35h ; '5'
0x180047603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047608  mov     dword ptr [rbp+57h+var_50.ErrorCode], eax
0x18004760b  mov     ebx, eax
0x18004760d  cmp     eax, 0AA0200h
0x180047612  jnz     loc_1800476C3
0x180047618  lea     r8, [rbp+57h+var_50]; struct _SENSE_DATA *
0x18004761c  lea     rdx, [rbp+57h+var_30]; union _CDB *
0x180047620  lea     rcx, [rbp+57h+var_18]; this
0x180047624  call    ?TranslateSenseInfoToHResult@Imapi2Utility@@YA?BEPEBT_CDB@@PEBU_SENSE_DATA@@PEAJ@Z; Imapi2Utility::TranslateSenseInfoToHResult(_CDB const *,_SENSE_DATA const *,long *)
0x180047629  mov     ebx, dword ptr [rbp+57h+var_50.ErrorCode]
0x18004762c  test    al, al
0x18004762e  mov     ecx, 80004005h
0x180047633  cmovz   ebx, ecx
0x180047636  mov     rcx, cs:WPP_GLOBAL_Control
0x18004763d  lea     rax, WPP_GLOBAL_Control
0x180047644  cmp     rcx, rax
0x180047647  jz      loc_1800476FE
0x18004764d  test    byte ptr [rcx+1Ch], 4
0x180047651  jz      loc_1800476FE
0x180047657  cmp     byte ptr [rcx+19h], 3
0x18004765b  jb      loc_1800476FE
0x180047661  movzx   r10d, byte ptr [rbp+57h+var_30+2]
0x180047666  lea     r11, [rbp+57h+var_50.SenseKeySpecific+1]
0x18004766a  movzx   r8d, byte ptr [rbp+57h+var_30+0Ch]
0x18004766f  xor     edx, edx
0x180047671  mov     [rsp+0A0h+var_58], r11
0x180047676  mov     eax, 12h
0x18004767b  mov     word ptr [rbp+57h+var_50.SenseKeySpecific+1], ax
0x18004767f  and     r10d, 0Fh
0x180047683  mov     [rsp+0A0h+var_60], ebx
0x180047687  lea     rax, [rbp+57h+var_30]
0x18004768b  mov     [rbp+57h+var_38], rax
0x18004768f  mov     r9d, edi
0x180047692  movzx   eax, byte ptr [rbp+57h+var_30+0Dh]
0x180047696  mov     [rsp+0A0h+var_68], eax
0x18004769a  mov     [rsp+0A0h+var_70], r8d
0x18004769f  mov     [rbp+57h+var_3E], edx
0x1800476a2  mov     [rbp+57h+var_3A], dx
0x1800476a6  mov     edx, 28h ; '('
0x1800476ab  mov     rcx, [rcx+10h]
0x1800476af  mov     [rsp+0A0h+var_78], r10d
0x1800476b4  mov     [rsp+0A0h+var_80], 104h
0x1800476bc  call    WPP_SF_ddDDDd_HEX_
0x1800476c1  jmp     short loc_1800476FE
0x1800476c3  test    ebx, ebx
0x1800476c5  jns     short loc_1800476FE
0x1800476c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800476ce  lea     rax, WPP_GLOBAL_Control
0x1800476d5  cmp     rcx, rax
0x1800476d8  jz      short loc_1800476FE
0x1800476da  test    byte ptr [rcx+1Ch], 4
0x1800476de  jz      short loc_1800476FE
0x1800476e0  cmp     byte ptr [rcx+19h], 3
0x1800476e4  jb      short loc_1800476FE
0x1800476e6  mov     rcx, [rcx+10h]
0x1800476ea  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x1800476f1  mov     edx, 29h ; ')'
0x1800476f6  mov     r9d, ebx
0x1800476f9  call    WPP_SF_d
0x1800476fe  mov     eax, ebx
0x180047700  mov     rcx, [rbp+57h+var_8]
0x180047704  xor     rcx, rsp; StackCookie
0x180047707  call    __security_check_cookie
0x18004770c  lea     r11, [rsp+0A0h+var_s0]
0x180047714  mov     rbx, [r11+18h]
0x180047718  mov     rdi, [r11+28h]
0x18004771c  mov     rsp, r11
0x18004771f  pop     rbp
0x180047720  retn
```
