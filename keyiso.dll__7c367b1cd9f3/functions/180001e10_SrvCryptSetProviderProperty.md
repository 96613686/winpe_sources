# SrvCryptSetProviderProperty

- ea: `0x180001e10`
- end: `0x180002044`
- name: `SrvCryptSetProviderProperty`
- size: `564`
- prototype: `__int64 __fastcall(__int64, __int64, const wchar_t *, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180001e10`
- `0x1800025b0`
- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180005510`
- `0x180018904`
- `0x180019010`

## string_xrefs

- `0x180001e50`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180001f41`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180001fdd`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000202c`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptSetProviderProperty(__int64 a1, __int64 a2, const wchar_t *a3, __int64 a4, unsigned int a5)
{
  unsigned int v7; // ebx
  int v9; // edx
  __int64 v10; // rdi
  int v11; // r8d
  int v12; // edx
  int v13; // r8d
  __int64 v14; // rcx
  const wchar_t *v15; // rax
  __int64 v16; // r9
  __int64 v17; // rcx
  int v18; // edx
  unsigned int v19; // ebx
  int v20; // r8d
  int v21; // eax

  if ( !a1 )
  {
    v7 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        130);
    return v7;
  }
  v10 = SrvLookupAndReferenceProvider(a1, a2, 0);
  if ( v10 )
  {
    if ( a3 )
    {
      if ( wcscmp_0(a3, L"MSSP/Client Process ID") )
      {
        v14 = 64;
        v15 = a3;
        while ( *v15 )
        {
          ++v15;
          if ( !--v14 )
          {
            v16 = 3236;
            goto LABEL_13;
          }
        }
        if ( a4 && a5 <= 0x7FFFFFFF )
        {
          v19 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(v10 + 88))(*(_QWORD *)(v10 + 296), a3, a4);
          if ( v19 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v18,
                v20,
                (unsigned int)"Status",
                v19,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
                188);
            v7 = NormalizeNteStatus(v19);
          }
          else
          {
            v7 = 0;
          }
        }
        else
        {
          v7 = -2146893785;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v12,
              v13,
              (unsigned int)"Status",
              39,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
              171);
        }
        goto LABEL_21;
      }
      v7 = -2146893808;
      v16 = 3229;
      v17 = 2148073488LL;
    }
    else
    {
      v16 = 3218;
LABEL_13:
      v7 = -2146893785;
      v17 = 2148073511LL;
    }
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v16);
LABEL_21:
    v21 = SrvDereferenceProvider(v10);
    if ( v21 < 0 && (v7 & 0x80000000) == 0 )
      return (unsigned int)v21;
    return v7;
  }
  v7 = -2146893786;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v11,
      (unsigned int)"Status",
      38,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
      139);
  return v7;
}

```

## disassembly

```asm
0x180001e10  push    rbx
0x180001e12  push    rbp
0x180001e13  push    rsi
0x180001e14  push    rdi
0x180001e15  sub     rsp, 48h
0x180001e19  xor     ebp, ebp
0x180001e1b  mov     rsi, r9
0x180001e1e  mov     rbx, r8
0x180001e21  test    rcx, rcx
0x180001e24  jnz     short loc_180001E7B
0x180001e26  mov     ebx, 80090026h
0x180001e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e32  lea     rax, WPP_GLOBAL_Control
0x180001e39  cmp     rcx, rax
0x180001e3c  jz      short loc_180001E70
0x180001e3e  test    byte ptr [rcx+1Ch], 1
0x180001e42  jz      short loc_180001E70
0x180001e44  mov     [rsp+68h+var_38], 0C82h
0x180001e4c  mov     rcx, [rcx+10h]
0x180001e50  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001e57  mov     [rsp+68h+var_40], rax
0x180001e5c  lea     r9, aStatus; "Status"
0x180001e63  mov     [rsp+68h+var_48], 80090026h
0x180001e6b  call    WPP_SF_sDsd
0x180001e70  mov     eax, ebx
0x180001e72  add     rsp, 48h
0x180001e76  pop     rdi
0x180001e77  pop     rsi
0x180001e78  pop     rbp
0x180001e79  pop     rbx
0x180001e7a  retn
0x180001e7b  xor     r8d, r8d
0x180001e7e  call    SrvLookupAndReferenceProvider
0x180001e83  mov     rdi, rax
0x180001e86  test    rax, rax
0x180001e89  jz      loc_180001F88
0x180001e8f  test    rbx, rbx
0x180001e92  jz      loc_18000200A
0x180001e98  lea     rdx, aMsspClientProc; "MSSP/Client Process ID"
0x180001e9f  mov     rcx, rbx; String1
0x180001ea2  call    wcscmp_0
0x180001ea7  test    eax, eax
0x180001ea9  jz      loc_180002015
0x180001eaf  mov     ecx, 40h ; '@'
0x180001eb4  mov     rax, rbx
0x180001eb7  cmp     [rax], bp
0x180001eba  jz      short loc_180001EDB
0x180001ebc  add     rax, 2
0x180001ec0  sub     rcx, 1
0x180001ec4  jnz     short loc_180001EB7
0x180001ec6  mov     r9d, 0CA4h
0x180001ecc  mov     ebx, 80090027h
0x180001ed1  mov     ecx, 80090027h
0x180001ed6  jmp     loc_180002025
0x180001edb  test    rsi, rsi
0x180001ede  jz      loc_180001FBB
0x180001ee4  mov     r9d, [rsp+68h+arg_20]
0x180001eec  cmp     r9d, 7FFFFFFFh
0x180001ef3  ja      loc_180001FBB
0x180001ef9  mov     eax, [rsp+68h+arg_28]
0x180001f00  mov     r8, rsi
0x180001f03  mov     rcx, [rdi+128h]
0x180001f0a  mov     rdx, rbx
0x180001f0d  mov     [rsp+68h+var_48], eax
0x180001f11  mov     rax, [rdi+58h]
0x180001f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f1a  mov     ebx, eax
0x180001f1c  test    eax, eax
0x180001f1e  jz      loc_18000203D
0x180001f24  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f2b  lea     rax, WPP_GLOBAL_Control
0x180001f32  cmp     rcx, rax
0x180001f35  jz      short loc_180001F65
0x180001f37  test    byte ptr [rcx+1Ch], 1
0x180001f3b  jz      short loc_180001F65
0x180001f3d  mov     rcx, [rcx+10h]
0x180001f41  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001f48  mov     [rsp+68h+var_38], 0CBCh
0x180001f50  lea     r9, aStatus; "Status"
0x180001f57  mov     [rsp+68h+var_40], rax
0x180001f5c  mov     [rsp+68h+var_48], ebx
0x180001f60  call    WPP_SF_sDsd
0x180001f65  mov     ecx, ebx
0x180001f67  call    NormalizeNteStatus
0x180001f6c  mov     ebx, eax
0x180001f6e  mov     rcx, rdi
0x180001f71  call    SrvDereferenceProvider
0x180001f76  test    eax, eax
0x180001f78  jns     loc_180001E70
0x180001f7e  test    ebx, ebx
0x180001f80  cmovns  ebx, eax
0x180001f83  jmp     loc_180001E70
0x180001f88  mov     ebx, 80090026h
0x180001f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f94  lea     rax, WPP_GLOBAL_Control
0x180001f9b  cmp     rcx, rax
0x180001f9e  jz      loc_180001E70
0x180001fa4  test    byte ptr [rcx+1Ch], 1
0x180001fa8  jz      loc_180001E70
0x180001fae  mov     [rsp+68h+var_38], 0C8Bh
0x180001fb6  jmp     loc_180001E4C
0x180001fbb  mov     ebx, 80090027h
0x180001fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180001fc7  lea     rax, WPP_GLOBAL_Control
0x180001fce  cmp     rcx, rax
0x180001fd1  jz      short loc_180001F6E
0x180001fd3  test    byte ptr [rcx+1Ch], 1
0x180001fd7  jz      short loc_180001F6E
0x180001fd9  mov     rcx, [rcx+10h]
0x180001fdd  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001fe4  mov     [rsp+68h+var_38], 0CABh
0x180001fec  lea     r9, aStatus; "Status"
0x180001ff3  mov     [rsp+68h+var_40], rax
0x180001ff8  mov     [rsp+68h+var_48], 80090027h
0x180002000  call    WPP_SF_sDsd
0x180002005  jmp     loc_180001F6E
0x18000200a  mov     r9d, 0C92h
0x180002010  jmp     loc_180001ECC
0x180002015  mov     ebx, 80090010h
0x18000201a  mov     r9d, 0C9Dh
0x180002020  mov     ecx, 80090010h
0x180002025  lea     rdx, aStatus; "Status"
0x18000202c  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002033  call    DebugTraceError
0x180002038  jmp     loc_180001F6E
0x18000203d  mov     ebx, ebp
0x18000203f  jmp     loc_180001F6E
```
