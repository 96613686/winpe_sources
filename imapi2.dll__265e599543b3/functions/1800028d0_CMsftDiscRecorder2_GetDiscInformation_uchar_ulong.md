# CMsftDiscRecorder2::GetDiscInformation(uchar * *,ulong *)

- ea: `0x1800028d0`
- end: `0x180002d90`
- name: `?GetDiscInformation@CMsftDiscRecorder2@@UEAAJPEAPEAEPEAK@Z`
- size: `1216`
- prototype: `__int64 __fastcall(CMsftDiscRecorder2 *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800028d0`
- `0x180002fc8`
- `0x1800036f0`
- `0x180014134`
- `0x180014180`
- `0x180014250`
- `0x180016778`
- `0x18002d2d8`
- `0x180049832`
- `0x18004984a`
- `0x180049880`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180002940`
- `ole32!CoTaskMemFree` at `0x180002940`
- `ole32!CoTaskMemAlloc` at `0x180002a62`
- `ole32!CoTaskMemAlloc` at `0x180002a62`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::GetDiscInformation(
        CMsftDiscRecorder2 *this,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  signed int v6; // ebx
  PVOID *v7; // rcx
  const struct _GUID *v8; // r8
  size_t v10; // r8
  void *v11; // rcx
  unsigned int v12; // edx
  void *v13; // rdx
  int v14; // eax
  unsigned int v15; // edi
  unsigned __int8 *v16; // rax
  unsigned __int8 *v17; // r14
  unsigned int i; // ecx
  char v19; // al
  char v20; // al
  char v21; // al
  __int64 v22; // r9
  int v23; // r9d
  unsigned __int8 *v24; // [rsp+30h] [rbp-39h]
  unsigned int v25; // [rsp+38h] [rbp-31h]
  unsigned int v26[4]; // [rsp+50h] [rbp-19h] BYREF
  union _CDB v27; // [rsp+60h] [rbp-9h] BYREF
  struct _SENSE_DATA v28; // [rsp+70h] [rbp+7h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    v6 = 0;
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 85, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    v6 = -2147467261;
  }
  if ( !a3 )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 188) & 4) != 0 && *((_BYTE *)v7 + 185) >= 3u )
      WPP_SF_(v7[22], 86, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    v6 = -2147467261;
    goto LABEL_5;
  }
  *a3 = 0;
  if ( v6 < 0 )
  {
LABEL_5:
    CoTaskMemFree(0);
    goto LABEL_6;
  }
  v22 = *((unsigned int *)this + 58);
  if ( (v22 & 2) == 0 )
  {
    v6 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        87,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        v22,
        -2147467259);
    }
    goto LABEL_5;
  }
  v10 = *((unsigned int *)this + 56);
  v11 = (void *)*((_QWORD *)this + 27);
  v26[0] = 0;
  memset_0(v11, 0, v10);
  v12 = *((_DWORD *)this + 56);
  v27 = 0;
  v27.CDB10.TransferBlocksMsb = BYTE1(v12);
  v27.CDB10.TransferBlocksLsb = v12;
  v27.CDB6GENERIC.OperationCode = 81;
  v25 = v12;
  v13 = (void *)*((_QWORD *)this + 10);
  v24 = (unsigned __int8 *)*((_QWORD *)this + 27);
  memset(&v28, 0, sizeof(v28));
  v14 = CMsftDiscRecorder2::SendCommandHelper(
          (CMsftDiscRecorder2 *)((char *)this - 8),
          v13,
          &v27,
          0xAu,
          &v28,
          0xAu,
          v24,
          v25,
          v26,
          1u);
  v6 = v14;
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_ddD(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        88,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        *((unsigned int *)this + 56),
        *((_DWORD *)this + 56),
        v14);
    }
    goto LABEL_5;
  }
  if ( v14 == 11141632 )
  {
    for ( i = 0; i < 0x19; ++i )
    {
      if ( LOBYTE(qword_180057780[i]) == 0xFF || LOBYTE(qword_180057780[i]) == (*((_BYTE *)&v28 + 2) & 0xF) )
      {
        v19 = BYTE1(qword_180057780[i]);
        if ( v19 == v28.AdditionalSenseCode || v19 == -1 )
        {
          v20 = BYTE2(qword_180057780[i]);
          if ( v20 == -1 || v20 == v28.AdditionalSenseCodeQualifier )
          {
            v21 = BYTE3(qword_180057780[i]);
            if ( v21 == -1 || v21 == v27.CDB6GENERIC.OperationCode )
            {
              v6 = HIDWORD(qword_180057780[i]);
              goto LABEL_29;
            }
          }
        }
      }
    }
    v6 = -2147467259;
LABEL_29:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      v23 = *((_DWORD *)this + 56);
      *(_WORD *)&v27.CDB6GENERIC.OperationCode = 18;
      *(ULONG *)((char *)v27.AsUlong + 2) = 0;
      *((_QWORD *)&v27.CDB6FORMAT + 1) = &v28;
      *((_WORD *)&v27.RECEIVE_DIAGNOSTIC + 3) = 0;
      WPP_SF_ddDDDD_HEX_(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        v28.AdditionalSenseCode,
        *((_BYTE *)&v28 + 2) & 0xF,
        v6,
        v23,
        v23,
        *((_BYTE *)&v28 + 2) & 0xF,
        v28.AdditionalSenseCode,
        v28.AdditionalSenseCodeQualifier,
        (__int64)&v27);
    }
    v15 = 0;
    if ( v6 < 0 )
      goto LABEL_5;
  }
  else
  {
    if ( v26[0] < 9 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        WPP_SF_dDdDdD(
          *((_QWORD *)WPP_GLOBAL_Control + 22),
          90,
          &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
          *((unsigned int *)this + 56),
          *((_DWORD *)this + 56),
          v26[0],
          v26[0],
          9,
          9);
      }
      v6 = -2147467259;
      goto LABEL_5;
    }
    v15 = (*(unsigned __int8 *)(*((_QWORD *)this + 27) + 1LL) | (**((unsigned __int8 **)this + 27) << 8)) + 2;
    if ( v15 > *((_DWORD *)this + 56) )
    {
      v6 = -1062599937;
      goto LABEL_5;
    }
  }
  v16 = (unsigned __int8 *)CoTaskMemAlloc(v15);
  v17 = v16;
  if ( !v16 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 22), 91, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, v15, v15);
    }
    v6 = -2147024882;
    goto LABEL_5;
  }
  memcpy_0(v16, *((const void **)this + 27), v15);
  *a2 = v17;
  *a3 = v15;
LABEL_6:
  if ( (v6 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v6, (int)&CLSID_MsftDiscRecorder2, v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800028d0  mov     [rsp-8+arg_18], rbx
0x1800028d5  push    rbp
0x1800028d6  push    rsi
0x1800028d7  push    rdi
0x1800028d8  push    r12
0x1800028da  push    r13
0x1800028dc  push    r14
0x1800028de  push    r15
0x1800028e0  lea     rbp, [rsp-27h]
0x1800028e5  sub     rsp, 90h
0x1800028ec  mov     rax, cs:__security_cookie
0x1800028f3  xor     rax, rsp
0x1800028f6  mov     [rbp+57h+var_38], rax
0x1800028fa  xor     r14d, r14d
0x1800028fd  lea     rax, WPP_GLOBAL_Control
0x180002904  mov     r12, r8
0x180002907  mov     r13, rdx
0x18000290a  mov     rsi, rcx
0x18000290d  mov     r15b, 4
0x180002910  mov     dil, 3
0x180002913  test    rdx, rdx
0x180002916  jz      loc_180002B78
0x18000291c  mov     [rdx], r14
0x18000291f  mov     ebx, r14d
0x180002922  mov     rcx, cs:WPP_GLOBAL_Control
0x180002929  test    r12, r12
0x18000292c  jz      loc_180002BC6
0x180002932  mov     [r12], r14d
0x180002936  test    ebx, ebx
0x180002938  jns     loc_180002B17
0x18000293e  xor     ecx, ecx; pv
0x180002940  call    cs:__imp_CoTaskMemFree
0x180002946  mov     eax, ebx
0x180002948  and     eax, 80FF0000h
0x18000294d  cmp     eax, 80AA0000h
0x180002952  jnz     short loc_180002962
0x180002954  lea     rdx, CLSID_MsftDiscRecorder2; int
0x18000295b  mov     ecx, ebx; dwMessageId
0x18000295d  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x180002962  mov     eax, ebx
0x180002964  mov     rcx, [rbp+57h+var_38]
0x180002968  xor     rcx, rsp; StackCookie
0x18000296b  call    __security_check_cookie
0x180002970  mov     rbx, [rsp+0C0h+arg_18]
0x180002978  add     rsp, 90h
0x18000297f  pop     r15
0x180002981  pop     r14
0x180002983  pop     r13
0x180002985  pop     r12
0x180002987  pop     rdi
0x180002988  pop     rsi
0x180002989  pop     rbp
0x18000298a  retn
0x18000298b  mov     r8d, [rsi+0E0h]; Size
0x180002992  xor     edx, edx; Val
0x180002994  mov     rcx, [rsi+0D8h]; void *
0x18000299b  mov     [rbp+57h+var_70], r14d
0x18000299f  call    memset_0
0x1800029a4  mov     edx, [rsi+0E0h]
0x1800029aa  lea     r8, [rbp+57h+var_60]; union _CDB *
0x1800029ae  xor     eax, eax
0x1800029b0  mov     [rsp+0C0h+var_78], 1; unsigned __int8
0x1800029b5  mov     word ptr [rbp+57h+var_50.SenseKeySpecific+1], ax
0x1800029b9  lea     rcx, [rsi-8]; this
0x1800029bd  mov     eax, edx
0x1800029bf  xorps   xmm0, xmm0
0x1800029c2  shr     eax, 8
0x1800029c5  mov     r9d, 0Ah; unsigned int
0x1800029cb  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800029cf  mov     byte ptr [rbp+57h+var_60+7], al
0x1800029d2  mov     al, dl
0x1800029d4  xorps   xmm1, xmm1
0x1800029d7  mov     byte ptr [rbp+57h+var_60+8], dl
0x1800029da  lea     rax, [rbp+57h+var_70]
0x1800029de  mov     byte ptr [rbp+57h+var_60], 51h ; 'Q'
0x1800029e2  mov     [rsp+0C0h+var_80], rax; unsigned int *
0x1800029e7  mov     rax, [rsi+0D8h]
0x1800029ee  mov     [rsp+0C0h+var_88], edx; unsigned int
0x1800029f2  mov     rdx, [rsi+50h]; void *
0x1800029f6  mov     [rsp+0C0h+var_90], rax; unsigned __int8 *
0x1800029fb  lea     rax, [rbp+57h+var_50]
0x1800029ff  mov     [rsp+0C0h+var_98], r9d; unsigned int
0x180002a04  mov     [rsp+0C0h+var_A0], rax; struct _SENSE_DATA *
0x180002a09  movups  xmmword ptr [rbp+57h+var_50.ErrorCode], xmm1
0x180002a0d  call    ?SendCommandHelper@CMsftDiscRecorder2@@AEAA?BJQEAXPEBT_CDB@@KPEAU_SENSE_DATA@@KPEAEKPEAKE@Z; CMsftDiscRecorder2::SendCommandHelper(void * const,_CDB const *,ulong,_SENSE_DATA *,ulong,uchar *,ulong,ulong *,uchar)
0x180002a12  mov     ebx, eax
0x180002a14  test    eax, eax
0x180002a16  js      loc_180002BFF
0x180002a1c  cmp     eax, 0AA0200h
0x180002a21  jz      short loc_180002A93
0x180002a23  mov     eax, [rbp+57h+var_70]
0x180002a26  mov     r8d, 9
0x180002a2c  cmp     eax, r8d
0x180002a2f  jb      loc_180002CDD
0x180002a35  mov     rax, [rsi+0D8h]
0x180002a3c  movzx   edi, byte ptr [rax]
0x180002a3f  movzx   eax, byte ptr [rax+1]
0x180002a43  shl     edi, 8
0x180002a46  or      edi, eax
0x180002a48  add     edi, 2
0x180002a4b  cmp     edi, [rsi+0E0h]
0x180002a51  jbe     short loc_180002A5D
0x180002a53  mov     ebx, 0C0AA02FFh
0x180002a58  jmp     loc_18000293E
0x180002a5d  mov     ecx, edi; cb
0x180002a5f  mov     r15d, edi
0x180002a62  call    cs:__imp_CoTaskMemAlloc
0x180002a68  mov     r14, rax
0x180002a6b  test    rax, rax
0x180002a6e  jz      loc_180002D42
0x180002a74  mov     rdx, [rsi+0D8h]; Src
0x180002a7b  mov     r8d, r15d; Size
0x180002a7e  mov     rcx, rax; void *
0x180002a81  call    memcpy_0
0x180002a86  mov     [r13+0], r14
0x180002a8a  mov     [r12], edi
0x180002a8e  jmp     loc_180002946
0x180002a93  mov     ecx, r14d
0x180002a96  lea     rdx, qword_180057780
0x180002a9d  mov     r8b, 0FFh
0x180002aa0  cmp     ecx, 19h
0x180002aa3  jnb     short loc_180002AEB
0x180002aa5  mov     ebx, ecx
0x180002aa7  cmp     [rdx+rbx*8], r8b
0x180002aab  jz      short loc_180002AB7
0x180002aad  mov     al, byte ptr [rbp+57h+var_50.SenseKey]
0x180002ab0  and     al, 0Fh
0x180002ab2  cmp     [rdx+rbx*8], al
0x180002ab5  jnz     short loc_180002AC5
0x180002ab7  mov     al, [rdx+rbx*8+1]
0x180002abb  cmp     al, [rbp+57h+var_50.AdditionalSenseCode]
0x180002abe  jz      short loc_180002AC9
0x180002ac0  cmp     al, r8b
0x180002ac3  jz      short loc_180002AC9
0x180002ac5  inc     ecx
0x180002ac7  jmp     short loc_180002AA0
0x180002ac9  mov     al, [rdx+rbx*8+2]
0x180002acd  cmp     al, r8b
0x180002ad0  jz      short loc_180002AD7
0x180002ad2  cmp     al, [rbp+57h+var_50.AdditionalSenseCodeQualifier]
0x180002ad5  jnz     short loc_180002AC5
0x180002ad7  mov     al, [rdx+rbx*8+3]
0x180002adb  cmp     al, r8b
0x180002ade  jz      short loc_180002AE5
0x180002ae0  cmp     al, byte ptr [rbp+57h+var_60]
0x180002ae3  jnz     short loc_180002AC5
0x180002ae5  mov     ebx, [rdx+rbx*8+4]
0x180002ae9  jmp     short loc_180002AF0
0x180002aeb  mov     ebx, 80004005h
0x180002af0  mov     rcx, cs:WPP_GLOBAL_Control
0x180002af7  lea     rdx, WPP_GLOBAL_Control
0x180002afe  cmp     rcx, rdx
0x180002b01  jnz     loc_180002C5D
0x180002b07  mov     edi, r14d
0x180002b0a  test    ebx, ebx
0x180002b0c  js      loc_18000293E
0x180002b12  jmp     loc_180002A5D
0x180002b17  mov     r9d, [rsi+0E8h]
0x180002b1e  test    r9b, 2
0x180002b22  jnz     loc_18000298B
0x180002b28  mov     ebx, 80004005h
0x180002b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b34  cmp     rcx, rax
0x180002b37  jz      loc_18000293E
0x180002b3d  test    [rcx+0BCh], r15b
0x180002b44  jz      loc_18000293E
0x180002b4a  cmp     [rcx+0B9h], dil
0x180002b51  jb      loc_18000293E
0x180002b57  mov     rcx, [rcx+0B0h]
0x180002b5e  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180002b65  mov     edx, 57h ; 'W'
0x180002b6a  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180002b6e  call    WPP_SF_Dd
0x180002b73  jmp     loc_18000293E
0x180002b78  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b7f  cmp     rcx, rax
0x180002b82  jz      short loc_180002BBC
0x180002b84  test    [rcx+0BCh], r15b
0x180002b8b  jz      short loc_180002BBC
0x180002b8d  cmp     [rcx+0B9h], dil
0x180002b94  jb      short loc_180002BBC
0x180002b96  mov     rcx, [rcx+0B0h]
0x180002b9d  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180002ba4  mov     edx, 55h ; 'U'
0x180002ba9  call    WPP_SF_
0x180002bae  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bb5  lea     rax, WPP_GLOBAL_Control
0x180002bbc  mov     ebx, 80004003h
0x180002bc1  jmp     loc_180002929
0x180002bc6  cmp     rcx, rax
0x180002bc9  jz      short loc_180002BF5
0x180002bcb  test    [rcx+0BCh], r15b
0x180002bd2  jz      short loc_180002BF5
0x180002bd4  cmp     [rcx+0B9h], dil
0x180002bdb  jb      short loc_180002BF5
0x180002bdd  mov     rcx, [rcx+0B0h]
0x180002be4  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180002beb  mov     edx, 56h ; 'V'
0x180002bf0  call    WPP_SF_
0x180002bf5  mov     ebx, 80004003h
0x180002bfa  jmp     loc_18000293E
0x180002bff  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c06  lea     rdx, WPP_GLOBAL_Control
0x180002c0d  cmp     rcx, rdx
0x180002c10  jz      loc_18000293E
0x180002c16  test    [rcx+0BCh], r15b
0x180002c1d  jz      loc_18000293E
0x180002c23  cmp     [rcx+0B9h], dil
0x180002c2a  jb      loc_18000293E
0x180002c30  mov     r9d, [rsi+0E0h]
0x180002c37  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180002c3e  mov     rcx, [rcx+0B0h]
0x180002c45  mov     edx, 58h ; 'X'
0x180002c4a  mov     [rsp+0C0h+var_98], eax
0x180002c4e  mov     dword ptr [rsp+0C0h+var_A0], r9d
0x180002c53  call    WPP_SF_ddD
0x180002c58  jmp     loc_18000293E
0x180002c5d  test    [rcx+0BCh], r15b
0x180002c64  jz      loc_180002B07
0x180002c6a  cmp     [rcx+0B9h], dil
0x180002c71  jb      loc_180002B07
0x180002c77  mov     r9d, [rsi+0E0h]
0x180002c7e  lea     r10, [rbp+57h+var_60]
0x180002c82  movzx   r8d, byte ptr [rbp+57h+var_50.SenseKey]
0x180002c87  xor     edx, edx
0x180002c89  mov     qword ptr [rsp+0C0h+var_78], r10
0x180002c8e  mov     eax, 12h
0x180002c93  mov     word ptr [rbp+57h+var_60], ax
0x180002c97  and     r8d, 0Fh
0x180002c9b  lea     rax, [rbp+57h+var_50]
0x180002c9f  mov     dword ptr [rbp+57h+var_60+2], edx
0x180002ca2  mov     qword ptr [rbp+57h+var_60+8], rax
0x180002ca6  movzx   eax, [rbp+57h+var_50.AdditionalSenseCodeQualifier]
0x180002caa  mov     dword ptr [rsp+0C0h+var_80], eax
0x180002cae  mov     word ptr [rbp+57h+var_60+6], dx
0x180002cb2  movzx   edx, [rbp+57h+var_50.AdditionalSenseCode]
0x180002cb6  mov     rcx, [rcx+0B0h]
0x180002cbd  mov     [rsp+0C0h+var_88], edx
0x180002cc1  mov     dword ptr [rsp+0C0h+var_90], r8d
0x180002cc6  mov     [rsp+0C0h+var_98], r9d
0x180002ccb  mov     dword ptr [rsp+0C0h+var_A0], r9d
0x180002cd0  mov     r9d, ebx
0x180002cd3  call    WPP_SF_ddDDDD_HEX_
0x180002cd8  jmp     loc_180002B07
0x180002cdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ce4  lea     rdx, WPP_GLOBAL_Control
0x180002ceb  cmp     rcx, rdx
0x180002cee  jz      short loc_180002D38
0x180002cf0  test    [rcx+0BCh], r15b
0x180002cf7  jz      short loc_180002D38
0x180002cf9  cmp     [rcx+0B9h], dil
0x180002d00  jb      short loc_180002D38
0x180002d02  mov     r9d, [rsi+0E0h]
0x180002d09  mov     edx, 5Ah ; 'Z'
0x180002d0e  mov     rcx, [rcx+0B0h]
0x180002d15  mov     dword ptr [rsp+0C0h+var_80], r8d
0x180002d1a  mov     [rsp+0C0h+var_88], r8d
0x180002d1f  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180002d26  mov     dword ptr [rsp+0C0h+var_90], eax
0x180002d2a  mov     [rsp+0C0h+var_98], eax
0x180002d2e  mov     dword ptr [rsp+0C0h+var_A0], r9d
0x180002d33  call    WPP_SF_dDdDdD
0x180002d38  mov     ebx, 80004005h
0x180002d3d  jmp     loc_18000293E
0x180002d42  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d49  lea     rax, WPP_GLOBAL_Control
0x180002d50  cmp     rcx, rax
0x180002d53  jz      short loc_180002D86
0x180002d55  test    byte ptr [rcx+0BCh], 4
0x180002d5c  jz      short loc_180002D86
0x180002d5e  cmp     byte ptr [rcx+0B9h], 3
0x180002d65  jb      short loc_180002D86
0x180002d67  mov     rcx, [rcx+0B0h]
0x180002d6e  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180002d75  mov     edx, 5Bh ; '['
0x180002d7a  mov     dword ptr [rsp+0C0h+var_A0], edi
0x180002d7e  mov     r9d, edi
0x180002d81  call    WPP_SF_Dd
0x180002d86  mov     ebx, 8007000Eh
0x180002d8b  jmp     loc_18000293E
```
