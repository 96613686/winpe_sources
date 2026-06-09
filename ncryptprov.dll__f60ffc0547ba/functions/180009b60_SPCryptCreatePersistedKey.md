# SPCryptCreatePersistedKey

- ea: `0x180009b60`
- end: `0x180009f5a`
- name: `SPCryptCreatePersistedKey`
- size: `1018`
- prototype: `__int64 __fastcall(__int64, unsigned int **, char *, void *, int, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006e80`
- `0x180009b60`
- `0x180009f60`
- `0x18000af80`
- `0x18000b250`
- `0x18000dab0`
- `0x180017580`
- `0x180063010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180009c88`
- `ntdll!RtlReleaseResource` at `0x180009c88`
- `ntdll!RtlAcquireResourceShared` at `0x180009cbc`
- `ntdll!RtlAcquireResourceShared` at `0x180009cbc`

## string_xrefs

- `0x180009d4d`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x180009e08`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x180009e54`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x180009eab`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x180009ede`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x180009f06`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x180009f38`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`

## pseudocode

```c
__int64 __fastcall SPCryptCreatePersistedKey(__int64 a1, unsigned int **a2, char *a3, void *a4, int a5, int a6)
{
  int UserStorageArea; // ebx
  int NewKeyObject; // eax
  __int64 v12; // rdx
  int v13; // r8d
  unsigned int *v14; // rdi
  int v15; // ecx
  int v16; // r8d
  int v18; // edx
  char *v19; // r8
  char v20; // bp
  unsigned __int64 i; // r9
  char *v22; // rax
  wchar_t **v23; // r10
  int v24; // ecx
  int v25; // edx
  int v26; // r8d
  unsigned int v27; // eax
  void *v28; // [rsp+60h] [rbp+8h] BYREF

  v28 = 0;
  if ( a1 && *(_DWORD *)a1 >= 0xA0u && *(_DWORD *)(a1 + 4) == 1263751248 )
  {
    RtlAcquireResourceShared((PRTL_RESOURCE)(a1 + 64), 1u);
    if ( a2 )
    {
      v20 = a6;
      if ( (a6 & 0xFFF8BF1F) != 0 )
      {
        UserStorageArea = -2146893815;
        DebugTraceError(2148073481LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 2438);
      }
      else if ( *(_DWORD *)(a1 + 48) && (a6 & 0x20) != 0 )
      {
        UserStorageArea = -2146893808;
        DebugTraceError(2148073488LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 2447);
      }
      else
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= 0x18 )
          {
            UserStorageArea = -2146893783;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v18,
                (_DWORD)v19,
                (unsigned int)"Status",
                41,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
                151);
            goto LABEL_18;
          }
          v22 = a3;
          v23 = &(&off_180064030)[13 * i];
          v19 = (char *)((char *)*v23 - a3);
          do
          {
            v24 = *(unsigned __int16 *)&v19[(_QWORD)v22];
            v18 = *(unsigned __int16 *)v22 - v24;
            if ( v18 )
              break;
            v22 += 2;
          }
          while ( v24 );
          if ( !v18 )
            break;
        }
        if ( a5 && !*((_DWORD *)v23 + 14) && (unsigned int)(a5 - 1) > 1 )
        {
          UserStorageArea = -2146893785;
          goto LABEL_18;
        }
        NewKeyObject = CreateNewKeyObject(a4, a6, (__int64)&v28);
        v14 = (unsigned int *)v28;
        UserStorageArea = NewKeyObject;
        if ( NewKeyObject )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v12,
              v13,
              (unsigned int)"Status",
              NewKeyObject,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
              189);
        }
        else
        {
          v15 = *(_DWORD *)(*((_QWORD *)v28 + 8) + 8LL);
          if ( v15 != 1 && v15 != 7 )
          {
            UserStorageArea = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, _QWORD))(*((_QWORD *)v28 + 21) + 72LL))(
                                *((_QWORD *)v28 + 19),
                                (char *)v28 + 112,
                                *((unsigned int *)v28 + 7),
                                0);
            if ( UserStorageArea < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v12,
                  v16,
                  (unsigned int)"Status",
                  UserStorageArea,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
                  214);
              goto LABEL_16;
            }
          }
          if ( !a4 )
          {
LABEL_21:
            *a2 = v14;
            UserStorageArea = 0;
            goto LABEL_18;
          }
          UserStorageArea = GetUserStorageArea(v14[8], v12, v14[132], *(_QWORD *)(a1 + 40), v14 + 18);
          if ( !UserStorageArea )
          {
            if ( v20 >= 0 )
            {
              v27 = KspCheckKeyDoesNotExist(v14);
              UserStorageArea = v27;
              if ( v27 )
              {
                DebugTraceError(v27, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 2552);
                goto LABEL_16;
              }
            }
            goto LABEL_21;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v25,
              v26,
              (unsigned int)"Status",
              UserStorageArea,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
              233);
        }
LABEL_16:
        if ( v14 )
          DeleteKeyObject(v14);
      }
    }
    else
    {
      UserStorageArea = -2146893785;
      DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 2424);
    }
LABEL_18:
    RtlReleaseResource((PRTL_RESOURCE)(a1 + 64));
  }
  else
  {
    UserStorageArea = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        113);
  }
  return (unsigned int)UserStorageArea;
}

```

## disassembly

```asm
0x180009b60  mov     [rsp+arg_18], rbx
0x180009b65  push    rsi
0x180009b66  push    r14
0x180009b68  push    r15
0x180009b6a  sub     rsp, 40h
0x180009b6e  mov     [rsp+58h+arg_0], 0
0x180009b77  mov     r15, r9
0x180009b7a  mov     rbx, r8
0x180009b7d  mov     r14, rdx
0x180009b80  mov     rsi, rcx
0x180009b83  test    rcx, rcx
0x180009b86  jz      short loc_180009B9D
0x180009b88  cmp     dword ptr [rcx], 0A0h
0x180009b8e  jb      short loc_180009B9D
0x180009b90  cmp     dword ptr [rcx+4], 4B535050h
0x180009b97  jz      loc_180009CB6
0x180009b9d  xor     esi, esi
0x180009b9f  mov     ebx, 80090026h
0x180009ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bab  lea     rax, WPP_GLOBAL_Control
0x180009bb2  cmp     rcx, rax
0x180009bb5  jz      loc_180009C94
0x180009bbb  test    byte ptr [rcx+1Ch], 1
0x180009bbf  jnz     loc_180009E50
0x180009bc5  test    rsi, rsi
0x180009bc8  jz      loc_180009C94
0x180009bce  jmp     loc_180009C84
0x180009bd3  mov     r9d, [rsp+58h+arg_20]
0x180009bdb  mov     eax, [r10+38h]
0x180009bdf  test    r9d, r9d
0x180009be2  jnz     loc_180009D6E
0x180009be8  mov     r9d, eax
0x180009beb  lea     rax, [rsp+58h+arg_0]
0x180009bf0  mov     [rsp+58h+arg_10], rdi
0x180009bf5  mov     [rsp+58h+var_30], rax; __int64
0x180009bfa  mov     r8, r10
0x180009bfd  mov     rdx, rsi
0x180009c00  mov     [rsp+58h+var_38], ebp; int
0x180009c04  mov     rcx, r15; Src
0x180009c07  call    CreateNewKeyObject
0x180009c0c  mov     rdi, [rsp+58h+arg_0]
0x180009c11  mov     ebx, eax
0x180009c13  test    eax, eax
0x180009c15  jnz     loc_180009D9A
0x180009c1b  mov     rax, [rdi+40h]
0x180009c1f  mov     ecx, [rax+8]
0x180009c22  cmp     ecx, 1
0x180009c25  jz      short loc_180009CA6
0x180009c27  cmp     ecx, 7
0x180009c2a  jz      short loc_180009CA6
0x180009c2c  mov     rax, [rdi+0A8h]
0x180009c33  lea     rdx, [rdi+70h]
0x180009c37  mov     r8d, [rdi+1Ch]
0x180009c3b  xor     r9d, r9d
0x180009c3e  mov     rcx, [rdi+98h]
0x180009c45  mov     rax, [rax+48h]
0x180009c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c4e  mov     ebx, eax
0x180009c50  test    eax, eax
0x180009c52  jns     short loc_180009CA6
0x180009c54  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c5b  lea     rax, WPP_GLOBAL_Control
0x180009c62  cmp     rcx, rax
0x180009c65  jz      short loc_180009C71
0x180009c67  test    byte ptr [rcx+1Ch], 1
0x180009c6b  jnz     loc_180009D41
0x180009c71  test    rdi, rdi
0x180009c74  jnz     loc_180009D8D
0x180009c7a  mov     rdi, [rsp+58h+arg_10]
0x180009c7f  mov     rbp, [rsp+58h+arg_8]
0x180009c84  lea     rcx, [rsi+40h]; Resource
0x180009c88  call    cs:__imp_RtlReleaseResource
0x180009c8f  nop     dword ptr [rax+rax+00h]
0x180009c94  mov     eax, ebx
0x180009c96  mov     rbx, [rsp+58h+arg_18]
0x180009c9b  add     rsp, 40h
0x180009c9f  pop     r15
0x180009ca1  pop     r14
0x180009ca3  pop     rsi
0x180009ca4  retn
0x180009ca6  test    r15, r15
0x180009ca9  jnz     loc_180009DC5
0x180009caf  mov     [r14], rdi
0x180009cb2  xor     ebx, ebx
0x180009cb4  jmp     short loc_180009C7A
0x180009cb6  add     rcx, 40h ; '@'; Resource
0x180009cba  mov     dl, 1; Wait
0x180009cbc  call    cs:__imp_RtlAcquireResourceShared
0x180009cc3  nop     dword ptr [rax+rax+00h]
0x180009cc8  test    r14, r14
0x180009ccb  jz      loc_180009ED8
0x180009cd1  mov     [rsp+58h+arg_8], rbp
0x180009cd6  mov     ebp, [rsp+58h+arg_28]
0x180009cdd  test    ebp, 0FFF8BF1Fh
0x180009ce3  jnz     loc_180009F00
0x180009ce9  cmp     dword ptr [rsi+30h], 0
0x180009ced  jnz     loc_180009F28
0x180009cf3  xor     r9d, r9d
0x180009cf6  lea     r11, off_180064030; "RSA"
0x180009cfd  nop     dword ptr [rax]
0x180009d00  cmp     r9, 18h
0x180009d04  jnb     loc_180009E81
0x180009d0a  imul    r10, r9, 68h ; 'h'
0x180009d0e  mov     rax, rbx
0x180009d11  add     r10, r11
0x180009d14  mov     r8, [r10]
0x180009d17  sub     r8, rbx
0x180009d1a  nop     word ptr [rax+rax+00h]
0x180009d20  movzx   edx, word ptr [rax]
0x180009d23  movzx   ecx, word ptr [rax+r8]
0x180009d28  sub     edx, ecx
0x180009d2a  jnz     short loc_180009D34
0x180009d2c  add     rax, 2
0x180009d30  test    ecx, ecx
0x180009d32  jnz     short loc_180009D20
0x180009d34  test    edx, edx
0x180009d36  jz      loc_180009BD3
0x180009d3c  inc     r9
0x180009d3f  jmp     short loc_180009D00
0x180009d41  mov     [rsp+58h+var_28], 9D6h
0x180009d49  mov     rcx, [rcx+10h]
0x180009d4d  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009d54  mov     [rsp+58h+var_30], rax
0x180009d59  lea     r9, aStatus; "Status"
0x180009d60  mov     [rsp+58h+var_38], ebx
0x180009d64  call    WPP_SF_sDsd
0x180009d69  jmp     loc_180009C71
0x180009d6e  test    eax, eax
0x180009d70  jnz     loc_180009BEB
0x180009d76  lea     eax, [r9-1]
0x180009d7a  cmp     eax, 1
0x180009d7d  jbe     loc_180009BEB
0x180009d83  mov     ebx, 80090027h
0x180009d88  jmp     loc_180009C7F
0x180009d8d  mov     rcx, rdi; void *
0x180009d90  call    DeleteKeyObject
0x180009d95  jmp     loc_180009C7A
0x180009d9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009da1  lea     rax, WPP_GLOBAL_Control
0x180009da8  cmp     rcx, rax
0x180009dab  jz      loc_180009C71
0x180009db1  test    byte ptr [rcx+1Ch], 1
0x180009db5  jz      loc_180009C71
0x180009dbb  mov     [rsp+58h+var_28], 9BDh
0x180009dc3  jmp     short loc_180009D49
0x180009dc5  mov     r9, [rsi+28h]
0x180009dc9  lea     rax, [rdi+48h]
0x180009dcd  mov     r8d, [rdi+210h]
0x180009dd4  mov     ecx, [rdi+20h]
0x180009dd7  mov     qword ptr [rsp+58h+var_38], rax
0x180009ddc  call    GetUserStorageArea
0x180009de1  mov     ebx, eax
0x180009de3  test    eax, eax
0x180009de5  jnz     short loc_180009E22
0x180009de7  test    bpl, bpl
0x180009dea  js      loc_180009CAF
0x180009df0  mov     rcx, rdi
0x180009df3  call    KspCheckKeyDoesNotExist
0x180009df8  mov     ebx, eax
0x180009dfa  test    eax, eax
0x180009dfc  jz      loc_180009CAF
0x180009e02  mov     r9d, 9F8h
0x180009e08  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009e0f  lea     rdx, aStatus; "Status"
0x180009e16  mov     ecx, eax
0x180009e18  call    DebugTraceError
0x180009e1d  jmp     loc_180009C71
0x180009e22  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e29  lea     rax, WPP_GLOBAL_Control
0x180009e30  cmp     rcx, rax
0x180009e33  jz      loc_180009C71
0x180009e39  test    byte ptr [rcx+1Ch], 1
0x180009e3d  jz      loc_180009C71
0x180009e43  mov     [rsp+58h+var_28], 9E9h
0x180009e4b  jmp     loc_180009D49
0x180009e50  mov     rcx, [rcx+10h]
0x180009e54  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009e5b  mov     [rsp+58h+var_28], 971h
0x180009e63  lea     r9, aStatus; "Status"
0x180009e6a  mov     [rsp+58h+var_30], rax
0x180009e6f  mov     [rsp+58h+var_38], 80090026h
0x180009e77  call    WPP_SF_sDsd
0x180009e7c  jmp     loc_180009BC5
0x180009e81  mov     ebx, 80090029h
0x180009e86  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e8d  lea     rax, WPP_GLOBAL_Control
0x180009e94  cmp     rcx, rax
0x180009e97  jz      loc_180009C7F
0x180009e9d  test    byte ptr [rcx+1Ch], 1
0x180009ea1  jz      loc_180009C7F
0x180009ea7  mov     rcx, [rcx+10h]
0x180009eab  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009eb2  mov     [rsp+58h+var_28], 997h
0x180009eba  lea     r9, aStatus; "Status"
0x180009ec1  mov     [rsp+58h+var_30], rax
0x180009ec6  mov     [rsp+58h+var_38], 80090029h
0x180009ece  call    WPP_SF_sDsd
0x180009ed3  jmp     loc_180009C7F
0x180009ed8  mov     r9d, 978h
0x180009ede  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009ee5  lea     rdx, aStatus; "Status"
0x180009eec  mov     ecx, 80090027h
0x180009ef1  mov     ebx, 80090027h
0x180009ef6  call    DebugTraceError
0x180009efb  jmp     loc_180009C84
0x180009f00  mov     r9d, 986h
0x180009f06  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009f0d  lea     rdx, aStatus; "Status"
0x180009f14  mov     ecx, 80090009h
0x180009f19  mov     ebx, 80090009h
0x180009f1e  call    DebugTraceError
0x180009f23  jmp     loc_180009C7F
0x180009f28  test    bpl, 20h
0x180009f2c  jz      loc_180009CF3
0x180009f32  mov     r9d, 98Fh
0x180009f38  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009f3f  lea     rdx, aStatus; "Status"
0x180009f46  mov     ecx, 80090010h
0x180009f4b  mov     ebx, 80090010h
0x180009f50  call    DebugTraceError
0x180009f55  jmp     loc_180009C7F
```
