# CDplServiceImpl::MakeAppHash(ushort const *,ushort const *,uchar *,uchar *)

- ea: `0x180094bb0`
- end: `0x1800950c1`
- name: `?MakeAppHash@CDplServiceImpl@@AEAAJPEBG0PEAE1@Z`
- size: `1297`
- prototype: `int(CDplServiceImpl *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180090228`

## callees

- `0x1800124d8`
- `0x18001312c`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180094bb0`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x180094f51`
- `bcrypt!BCryptDestroyHash` at `0x180095063`
- `bcrypt!BCryptDestroyHash` at `0x180094f51`
- `bcrypt!BCryptDestroyHash` at `0x180095063`
- `bcrypt!BCryptFinishHash` at `0x180094f27`
- `bcrypt!BCryptFinishHash` at `0x18009501d`
- `bcrypt!BCryptFinishHash` at `0x180094f27`
- `bcrypt!BCryptFinishHash` at `0x18009501d`
- `bcrypt!BCryptHashData` at `0x180094ef0`
- `bcrypt!BCryptHashData` at `0x180094fbc`
- `bcrypt!BCryptHashData` at `0x180094fed`
- `bcrypt!BCryptHashData` at `0x180094ef0`
- `bcrypt!BCryptHashData` at `0x180094fbc`
- `bcrypt!BCryptHashData` at `0x180094fed`
- `bcrypt!BCryptCreateHash` at `0x180094ebc`
- `bcrypt!BCryptCreateHash` at `0x180094f89`
- `bcrypt!BCryptCreateHash` at `0x180094ebc`
- `bcrypt!BCryptCreateHash` at `0x180094f89`

## pseudocode

```c
__int64 __fastcall CDplServiceImpl::MakeAppHash(
        BCRYPT_ALG_HANDLE *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int8 *a4,
        PUCHAR pbOutput)
{
  int v9; // ecx
  unsigned int v10; // ebx
  int v11; // r8d
  unsigned __int8 *v12; // rsi
  int v13; // ecx
  int v14; // ecx
  __int64 *v15; // rdx
  int v16; // ecx
  NTSTATUS v17; // eax
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  BCRYPT_ALG_HANDLE v20; // rcx
  NTSTATUS v21; // eax
  NTSTATUS v22; // eax
  NTSTATUS v23; // eax
  NTSTATUS v24; // eax
  char pbSecret; // [rsp+20h] [rbp-40h]
  ULONG v27; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v29; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int64 v30; // [rsp+58h] [rbp-8h] BYREF
  ULONG cbInput; // [rsp+98h] [rbp+38h] BYREF

  phHash = 0;
  v30 = 0;
  v27 = 0;
  v29 = 0;
  cbInput = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 37, 129);
  if ( !a2 )
  {
    pbSecret = -125;
LABEL_3:
    v10 = -2147024809;
    v11 = -2147024809;
LABEL_55:
    v15 = EFS_TRACE_ERROR;
    goto LABEL_56;
  }
  if ( !a3 )
  {
    pbSecret = -124;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v10 = -2147467261;
    pbSecret = -123;
    v11 = -2147467261;
    goto LABEL_55;
  }
  v12 = pbOutput;
  if ( !pbOutput )
  {
    v10 = -2147467261;
    pbSecret = -122;
    v11 = -2147467261;
    goto LABEL_55;
  }
  *(_OWORD *)a4 = 0;
  *((_OWORD *)a4 + 1) = 0;
  *(_OWORD *)v12 = 0;
  *((_OWORD *)v12 + 1) = 0;
  fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 139);
  v10 = StringCbLengthW(a2, 0xFFFFFFFE, &v29);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v10,
              37,
              139) >= 0 )
  {
    fnEfsLogTrace1Strings(v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 140);
    v10 = ULongLongToULong(v29, &cbInput);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v10,
                37,
                140) >= 0 )
    {
      if ( cbInput < 2 )
      {
        pbSecret = -113;
        goto LABEL_14;
      }
      fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 147);
      v10 = StringCbLengthW(a3, 0xFFFFFFFE, &v30);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  v10,
                  37,
                  147) >= 0 )
      {
        fnEfsLogTrace1Strings(v16, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 148);
        v10 = ULongLongToULong(v30, &v27);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    v10,
                    37,
                    148) >= 0 )
        {
          if ( v27 >= 2 )
          {
            v17 = BCryptCreateHash(this[30], &phHash, 0, 0, 0, 0, 0);
            if ( v17 )
            {
              if ( v17 > 0 )
                v10 = (unsigned __int16)v17 | 0x80070000;
              else
                v10 = v17;
              pbSecret = -99;
            }
            else
            {
              v18 = BCryptHashData(phHash, (PUCHAR)a2, cbInput, 0);
              if ( v18 )
              {
                if ( v18 > 0 )
                  v10 = (unsigned __int16)v18 | 0x80070000;
                else
                  v10 = v18;
                pbSecret = -94;
              }
              else
              {
                v19 = BCryptFinishHash(phHash, a4, 0x20u, 0);
                if ( v19 )
                {
                  if ( v19 > 0 )
                    v10 = (unsigned __int16)v19 | 0x80070000;
                  else
                    v10 = v19;
                  pbSecret = -89;
                }
                else
                {
                  BCryptDestroyHash(phHash);
                  v20 = this[30];
                  phHash = 0;
                  v21 = BCryptCreateHash(v20, &phHash, 0, 0, 0, 0, 0);
                  if ( v21 )
                  {
                    if ( v21 > 0 )
                      v10 = (unsigned __int16)v21 | 0x80070000;
                    else
                      v10 = v21;
                    pbSecret = -81;
                  }
                  else
                  {
                    v22 = BCryptHashData(phHash, a4, 0x20u, 0);
                    if ( v22 )
                    {
                      if ( v22 > 0 )
                        v10 = (unsigned __int16)v22 | 0x80070000;
                      else
                        v10 = v22;
                      pbSecret = -76;
                    }
                    else
                    {
                      v23 = BCryptHashData(phHash, (PUCHAR)a3, v27, 0);
                      if ( v23 )
                      {
                        if ( v23 > 0 )
                          v10 = (unsigned __int16)v23 | 0x80070000;
                        else
                          v10 = v23;
                        pbSecret = -71;
                      }
                      else
                      {
                        v24 = BCryptFinishHash(phHash, v12, 0x20u, 0);
                        if ( !v24 )
                          goto LABEL_57;
                        if ( v24 > 0 )
                          v10 = (unsigned __int16)v24 | 0x80070000;
                        else
                          v10 = v24;
                        pbSecret = -66;
                      }
                    }
                  }
                }
              }
            }
            v11 = v10;
            goto LABEL_55;
          }
          pbSecret = -105;
LABEL_14:
          v11 = 1;
          v15 = EFS_TRACE_STATUS;
          v10 = 1;
LABEL_56:
          fnEfsLogTrace1(g_hPublisher, (_DWORD)v15, v11, 37, pbSecret);
        }
      }
    }
  }
LABEL_57:
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v10,
    37,
    200);
  return v10;
}

```

## disassembly

```asm
0x180094bb0  mov     [rsp-28h+arg_0], rbx
0x180094bb5  mov     [rsp-28h+arg_10], rsi
0x180094bba  push    rbp
0x180094bbb  push    rdi
0x180094bbc  push    r13
0x180094bbe  push    r14
0x180094bc0  push    r15
0x180094bc2  mov     rbp, rsp
0x180094bc5  sub     rsp, 60h
0x180094bc9  mov     rdi, r9
0x180094bcc  mov     [rbp+phHash], 0
0x180094bd4  mov     r14, r8
0x180094bd7  mov     [rbp+var_8], 0
0x180094bdf  mov     r15, rdx
0x180094be2  mov     [rbp+var_20], 0
0x180094be9  mov     r9d, 25h ; '%'
0x180094bef  mov     [rbp+var_10], 0
0x180094bf7  lea     r8, sourceString
0x180094bfe  mov     [rbp+cbInput], 0
0x180094c05  lea     rdx, EFS_TRACE_ENTER_EVENT
0x180094c0c  mov     dword ptr [rsp+60h+pbSecret], 1A81h
0x180094c14  mov     r13, rcx
0x180094c17  call    fnEfsLogTrace1Strings
0x180094c1c  test    r15, r15
0x180094c1f  jnz     short loc_180094C39
0x180094c21  mov     dword ptr [rsp+60h+pbSecret], 1A83h
0x180094c29  mov     ebx, 80070057h
0x180094c2e  mov     r8d, 80070057h
0x180094c34  jmp     loc_180095041
0x180094c39  test    r14, r14
0x180094c3c  jnz     short loc_180094C48
0x180094c3e  mov     dword ptr [rsp+60h+pbSecret], 1A84h
0x180094c46  jmp     short loc_180094C29
0x180094c48  test    rdi, rdi
0x180094c4b  jnz     short loc_180094C65
0x180094c4d  mov     ebx, 80004003h
0x180094c52  mov     dword ptr [rsp+60h+pbSecret], 1A85h
0x180094c5a  mov     r8d, 80004003h
0x180094c60  jmp     loc_180095041
0x180094c65  mov     rsi, [rbp+pbOutput]
0x180094c69  mov     r9d, 25h ; '%'
0x180094c6f  test    rsi, rsi
0x180094c72  jnz     short loc_180094C8C
0x180094c74  mov     ebx, 80004003h
0x180094c79  mov     dword ptr [rsp+60h+pbSecret], 1A86h
0x180094c81  mov     r8d, 80004003h
0x180094c87  jmp     loc_180095047
0x180094c8c  xorps   xmm0, xmm0
0x180094c8f  mov     dword ptr [rsp+60h+pbSecret], 1A8Bh
0x180094c97  movups  xmmword ptr [rdi], xmm0
0x180094c9a  lea     r8, sourceString
0x180094ca1  xorps   xmm1, xmm1
0x180094ca4  lea     rdx, EFS_TRACE_START_EVENT
0x180094cab  movups  xmmword ptr [rdi+10h], xmm0
0x180094caf  movups  xmmword ptr [rsi], xmm1
0x180094cb2  movups  xmmword ptr [rsi+10h], xmm1
0x180094cb6  call    fnEfsLogTrace1Strings
0x180094cbb  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180094cbf  mov     edx, 0FFFFFFFEh; unsigned __int64
0x180094cc4  mov     rcx, r15; unsigned __int16 *
0x180094cc7  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180094ccc  mov     rcx, cs:g_hPublisher
0x180094cd3  lea     r9, sourceString
0x180094cda  mov     [rsp+60h+dwFlags], 1A8Bh
0x180094ce2  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180094ce9  mov     [rsp+60h+cbSecret], 25h ; '%'
0x180094cf1  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180094cf8  mov     dword ptr [rsp+60h+pbSecret], eax
0x180094cfc  mov     ebx, eax
0x180094cfe  call    fnEfsLogTrace1String1Dword
0x180094d03  test    eax, eax
0x180094d05  js      loc_18009505A
0x180094d0b  mov     r9d, 25h ; '%'
0x180094d11  mov     dword ptr [rsp+60h+pbSecret], 1A8Ch
0x180094d19  lea     r8, sourceString
0x180094d20  lea     rdx, EFS_TRACE_START_EVENT
0x180094d27  call    fnEfsLogTrace1Strings
0x180094d2c  mov     rcx, [rbp+var_10]; unsigned __int64
0x180094d30  lea     rdx, [rbp+cbInput]; unsigned int *
0x180094d34  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180094d39  mov     rcx, cs:g_hPublisher
0x180094d40  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180094d47  mov     [rsp+60h+dwFlags], 1A8Ch
0x180094d4f  lea     r9, sourceString
0x180094d56  mov     [rsp+60h+cbSecret], 25h ; '%'
0x180094d5e  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180094d65  mov     dword ptr [rsp+60h+pbSecret], eax
0x180094d69  mov     ebx, eax
0x180094d6b  call    fnEfsLogTrace1String1Dword
0x180094d70  test    eax, eax
0x180094d72  js      loc_18009505A
0x180094d78  cmp     [rbp+cbInput], 2
0x180094d7c  mov     r9d, 25h ; '%'
0x180094d82  jnb     short loc_180094DA1
0x180094d84  mov     dword ptr [rsp+60h+pbSecret], 1A8Fh
0x180094d8c  mov     r8d, 1
0x180094d92  lea     rdx, EFS_TRACE_STATUS
0x180094d99  mov     ebx, r8d
0x180094d9c  jmp     loc_18009504E
0x180094da1  lea     r8, sourceString
0x180094da8  mov     dword ptr [rsp+60h+pbSecret], 1A93h
0x180094db0  lea     rdx, EFS_TRACE_START_EVENT
0x180094db7  call    fnEfsLogTrace1Strings
0x180094dbc  lea     r8, [rbp+var_8]; unsigned __int64 *
0x180094dc0  mov     edx, 0FFFFFFFEh; unsigned __int64
0x180094dc5  mov     rcx, r14; unsigned __int16 *
0x180094dc8  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180094dcd  mov     rcx, cs:g_hPublisher
0x180094dd4  lea     r9, sourceString
0x180094ddb  mov     [rsp+60h+dwFlags], 1A93h
0x180094de3  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180094dea  mov     [rsp+60h+cbSecret], 25h ; '%'
0x180094df2  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180094df9  mov     dword ptr [rsp+60h+pbSecret], eax
0x180094dfd  mov     ebx, eax
0x180094dff  call    fnEfsLogTrace1String1Dword
0x180094e04  test    eax, eax
0x180094e06  js      loc_18009505A
0x180094e0c  mov     r9d, 25h ; '%'
0x180094e12  mov     dword ptr [rsp+60h+pbSecret], 1A94h
0x180094e1a  lea     r8, sourceString
0x180094e21  lea     rdx, EFS_TRACE_START_EVENT
0x180094e28  call    fnEfsLogTrace1Strings
0x180094e2d  mov     rcx, [rbp+var_8]; unsigned __int64
0x180094e31  lea     rdx, [rbp+var_20]; unsigned int *
0x180094e35  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180094e3a  mov     rcx, cs:g_hPublisher
0x180094e41  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180094e48  mov     [rsp+60h+dwFlags], 1A94h
0x180094e50  lea     r9, sourceString
0x180094e57  mov     [rsp+60h+cbSecret], 25h ; '%'
0x180094e5f  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180094e66  mov     dword ptr [rsp+60h+pbSecret], eax
0x180094e6a  mov     ebx, eax
0x180094e6c  call    fnEfsLogTrace1String1Dword
0x180094e71  test    eax, eax
0x180094e73  js      loc_18009505A
0x180094e79  cmp     [rbp+var_20], 2
0x180094e7d  jnb     short loc_180094E92
0x180094e7f  mov     dword ptr [rsp+60h+pbSecret], 1A97h
0x180094e87  mov     r9d, 25h ; '%'
0x180094e8d  jmp     loc_180094D8C
0x180094e92  mov     rcx, [r13+0F0h]; hAlgorithm
0x180094e99  lea     rdx, [rbp+phHash]; phHash
0x180094e9d  mov     [rsp+60h+dwFlags], 0; dwFlags
0x180094ea5  xor     r9d, r9d; cbHashObject
0x180094ea8  mov     [rsp+60h+cbSecret], 0; cbSecret
0x180094eb0  xor     r8d, r8d; pbHashObject
0x180094eb3  mov     [rsp+60h+pbSecret], 0; pbSecret
0x180094ebc  call    cs:__imp_BCryptCreateHash
0x180094ec2  test    eax, eax
0x180094ec4  jz      short loc_180094EE2
0x180094ec6  jg      short loc_180094ECC
0x180094ec8  mov     ebx, eax
0x180094eca  jmp     short loc_180094ED5
0x180094ecc  movzx   ebx, ax
0x180094ecf  or      ebx, 80070000h
0x180094ed5  mov     dword ptr [rsp+60h+pbSecret], 1A9Dh
0x180094edd  jmp     loc_18009503E
0x180094ee2  mov     r8d, [rbp+cbInput]; cbInput
0x180094ee6  xor     r9d, r9d; dwFlags
0x180094ee9  mov     rcx, [rbp+phHash]; hHash
0x180094eed  mov     rdx, r15; pbInput
0x180094ef0  call    cs:__imp_BCryptHashData
0x180094ef6  test    eax, eax
0x180094ef8  jz      short loc_180094F16
0x180094efa  jg      short loc_180094F00
0x180094efc  mov     ebx, eax
0x180094efe  jmp     short loc_180094F09
0x180094f00  movzx   ebx, ax
0x180094f03  or      ebx, 80070000h
0x180094f09  mov     dword ptr [rsp+60h+pbSecret], 1AA2h
0x180094f11  jmp     loc_18009503E
0x180094f16  mov     rcx, [rbp+phHash]; hHash
0x180094f1a  xor     r9d, r9d; dwFlags
0x180094f1d  mov     rdx, rdi; pbOutput
0x180094f20  lea     r15d, [r9+20h]
0x180094f24  mov     r8d, r15d; cbOutput
0x180094f27  call    cs:__imp_BCryptFinishHash
0x180094f2d  test    eax, eax
0x180094f2f  jz      short loc_180094F4D
0x180094f31  jg      short loc_180094F37
0x180094f33  mov     ebx, eax
0x180094f35  jmp     short loc_180094F40
0x180094f37  movzx   ebx, ax
0x180094f3a  or      ebx, 80070000h
0x180094f40  mov     dword ptr [rsp+60h+pbSecret], 1AA7h
0x180094f48  jmp     loc_18009503E
0x180094f4d  mov     rcx, [rbp+phHash]; hHash
0x180094f51  call    cs:__imp_BCryptDestroyHash
0x180094f57  mov     rcx, [r13+0F0h]; hAlgorithm
0x180094f5e  lea     rdx, [rbp+phHash]; phHash
0x180094f62  mov     [rsp+60h+dwFlags], 0; dwFlags
0x180094f6a  xor     r9d, r9d; cbHashObject
0x180094f6d  mov     [rsp+60h+cbSecret], 0; cbSecret
0x180094f75  xor     r8d, r8d; pbHashObject
0x180094f78  mov     [rsp+60h+pbSecret], 0; pbSecret
0x180094f81  mov     [rbp+phHash], 0
0x180094f89  call    cs:__imp_BCryptCreateHash
0x180094f8f  test    eax, eax
0x180094f91  jz      short loc_180094FAF
0x180094f93  jg      short loc_180094F99
0x180094f95  mov     ebx, eax
0x180094f97  jmp     short loc_180094FA2
0x180094f99  movzx   ebx, ax
0x180094f9c  or      ebx, 80070000h
0x180094fa2  mov     dword ptr [rsp+60h+pbSecret], 1AAFh
0x180094faa  jmp     loc_18009503E
0x180094faf  mov     rcx, [rbp+phHash]; hHash
0x180094fb3  xor     r9d, r9d; dwFlags
0x180094fb6  mov     r8d, r15d; cbInput
0x180094fb9  mov     rdx, rdi; pbInput
0x180094fbc  call    cs:__imp_BCryptHashData
0x180094fc2  test    eax, eax
0x180094fc4  jz      short loc_180094FDF
0x180094fc6  jg      short loc_180094FCC
0x180094fc8  mov     ebx, eax
0x180094fca  jmp     short loc_180094FD5
0x180094fcc  movzx   ebx, ax
0x180094fcf  or      ebx, 80070000h
0x180094fd5  mov     dword ptr [rsp+60h+pbSecret], 1AB4h
0x180094fdd  jmp     short loc_18009503E
0x180094fdf  mov     r8d, [rbp+var_20]; cbInput
0x180094fe3  xor     r9d, r9d; dwFlags
0x180094fe6  mov     rcx, [rbp+phHash]; hHash
0x180094fea  mov     rdx, r14; pbInput
0x180094fed  call    cs:__imp_BCryptHashData
0x180094ff3  test    eax, eax
0x180094ff5  jz      short loc_180095010
0x180094ff7  jg      short loc_180094FFD
0x180094ff9  mov     ebx, eax
0x180094ffb  jmp     short loc_180095006
0x180094ffd  movzx   ebx, ax
0x180095000  or      ebx, 80070000h
0x180095006  mov     dword ptr [rsp+60h+pbSecret], 1AB9h
0x18009500e  jmp     short loc_18009503E
0x180095010  mov     rcx, [rbp+phHash]; hHash
0x180095014  xor     r9d, r9d; dwFlags
0x180095017  mov     r8d, r15d; cbOutput
0x18009501a  mov     rdx, rsi; pbOutput
0x18009501d  call    cs:__imp_BCryptFinishHash
0x180095023  test    eax, eax
0x180095025  jz      short loc_18009505A
0x180095027  jg      short loc_18009502D
0x180095029  mov     ebx, eax
0x18009502b  jmp     short loc_180095036
0x18009502d  movzx   ebx, ax
0x180095030  or      ebx, 80070000h
0x180095036  mov     dword ptr [rsp+60h+pbSecret], 1ABEh
0x18009503e  mov     r8d, ebx
0x180095041  mov     r9d, 25h ; '%'
0x180095047  lea     rdx, EFS_TRACE_ERROR
0x18009504e  mov     rcx, cs:g_hPublisher
0x180095055  call    fnEfsLogTrace1
0x18009505a  mov     rcx, [rbp+phHash]; hHash
0x18009505e  test    rcx, rcx
0x180095061  jz      short loc_180095071
0x180095063  call    cs:__imp_BCryptDestroyHash
0x180095069  mov     [rbp+phHash], 0
0x180095071  mov     rcx, cs:g_hPublisher
0x180095078  lea     r9, sourceString
0x18009507f  mov     [rsp+60h+dwFlags], 1AC8h
0x180095087  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x18009508e  mov     [rsp+60h+cbSecret], 25h ; '%'
0x180095096  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x18009509d  mov     dword ptr [rsp+60h+pbSecret], ebx
0x1800950a1  call    fnEfsLogTrace1String1Dword
0x1800950a6  lea     r11, [rsp+60h+var_s0]
0x1800950ab  mov     eax, ebx
0x1800950ad  mov     rbx, [r11+30h]
0x1800950b1  mov     rsi, [r11+40h]
0x1800950b5  mov     rsp, r11
0x1800950b8  pop     r15
0x1800950ba  pop     r14
0x1800950bc  pop     r13
0x1800950be  pop     rdi
0x1800950bf  pop     rbp
0x1800950c0  retn
```
