# DisplayDriverBlockBalloon(DEVICE_COLLECTION *)

- ea: `0x180006a68`
- end: `0x180006bca`
- name: `?DisplayDriverBlockBalloon@@YAXPEAUDEVICE_COLLECTION@@@Z`
- size: `354`
- prototype: `void __fastcall(struct DEVICE_COLLECTION **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004e60`

## callees

- `0x180006a68`
- `0x180008760`

## import_xrefs

- `apphelp!SdbCloseDatabase` at `0x180006b41`
- `apphelp!SdbCloseDatabase` at `0x180006b41`
- `apphelp!SdbGetStandardDatabaseGUID` at `0x180006ae0`
- `apphelp!SdbGetStandardDatabaseGUID` at `0x180006ae0`
- `apphelp!SdbFindFirstGUIDIndexedTag` at `0x180006ba4`
- `apphelp!SdbFindFirstGUIDIndexedTag` at `0x180006ba4`
- `apphelp!SdbOpenDatabase` at `0x180006b1a`
- `apphelp!SdbOpenDatabase` at `0x180006b1a`
- `apphelp!SdbResolveDatabase` at `0x180006b07`
- `apphelp!SdbResolveDatabase` at `0x180006b07`
- `apphelp!SdbInitDatabase` at `0x180006acb`
- `apphelp!SdbInitDatabase` at `0x180006acb`
- `apphelp!SdbApphelpNotify` at `0x180006bbf`
- `apphelp!SdbApphelpNotify` at `0x180006bbf`
- `apphelp!SdbReleaseDatabase` at `0x180006b4a`
- `apphelp!SdbReleaseDatabase` at `0x180006b4a`

## pseudocode

```c
void __fastcall DisplayDriverBlockBalloon(struct DEVICE_COLLECTION **a1)
{
  __int64 inited; // rsi
  int v3; // r14d
  __int64 v4; // rbx
  struct DEVICE_COLLECTION *v5; // rcx
  __int64 v6; // rdx
  unsigned int FirstGUIDIndexedTag; // eax
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v9[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v10; // [rsp+58h] [rbp-A8h]
  __int128 v11; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v12; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v13[528]; // [rsp+80h] [rbp-80h] BYREF

  v8 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  memset(v9, 0, sizeof(v9));
  inited = SdbInitDatabase(2147745792LL, 0);
  if ( inited )
  {
    if ( (unsigned int)SdbGetStandardDatabaseGUID(2147745792LL, &v11) )
    {
      v8 = -2147221504;
      if ( (unsigned int)SdbResolveDatabase(inited, &v11, &v8, v13, 260) )
      {
        v3 = 0;
        v4 = SdbOpenDatabase(v13, 0);
        if ( v4 )
        {
LABEL_5:
          v5 = *a1;
          v6 = 0;
          while ( v5 != (struct DEVICE_COLLECTION *)a1 )
          {
            if ( (_DWORD)v6 == v3 )
            {
              v12 = *(_OWORD *)((char *)v5 + 436);
              ++v3;
              FirstGUIDIndexedTag = SdbFindFirstGUIDIndexedTag(v4, 28679, 36868, &v12, v9);
              if ( FirstGUIDIndexedTag )
                SdbApphelpNotify(0, &v11, FirstGUIDIndexedTag, 0);
              goto LABEL_5;
            }
            v5 = *(struct DEVICE_COLLECTION **)v5;
            v6 = (unsigned int)(v6 + 1);
          }
          SdbCloseDatabase(v4, v6);
        }
      }
    }
    SdbReleaseDatabase(inited);
  }
}

```

## disassembly

```asm
0x180006a68  mov     [rsp-8+arg_8], rbx
0x180006a6d  mov     [rsp-8+arg_10], rsi
0x180006a72  push    rbp
0x180006a73  push    rdi
0x180006a74  push    r14
0x180006a76  lea     rbp, [rsp-1A0h]
0x180006a7e  sub     rsp, 2A0h
0x180006a85  mov     rax, cs:__security_cookie
0x180006a8c  xor     rax, rsp
0x180006a8f  mov     [rbp+1B0h+var_20], rax
0x180006a96  xorps   xmm0, xmm0
0x180006a99  mov     [rsp+2B0h+var_280], 0
0x180006aa1  mov     rdi, rcx
0x180006aa4  xorps   xmm1, xmm1
0x180006aa7  xor     eax, eax
0x180006aa9  mov     ebx, 80040000h
0x180006aae  mov     ecx, ebx
0x180006ab0  mov     [rsp+2B0h+var_258], rax
0x180006ab5  xor     edx, edx
0x180006ab7  movups  [rsp+2B0h+var_250], xmm0
0x180006abc  movups  [rsp+2B0h+var_240], xmm1
0x180006ac1  movups  [rsp+2B0h+var_278], xmm0
0x180006ac6  movups  [rsp+2B0h+var_268], xmm0
0x180006acb  call    cs:__imp_SdbInitDatabase
0x180006ad1  mov     rsi, rax
0x180006ad4  test    rax, rax
0x180006ad7  jz      short loc_180006B50
0x180006ad9  lea     rdx, [rsp+2B0h+var_250]
0x180006ade  mov     ecx, ebx
0x180006ae0  call    cs:__imp_SdbGetStandardDatabaseGUID
0x180006ae6  test    eax, eax
0x180006ae8  jz      short loc_180006B47
0x180006aea  lea     r9, [rbp+1B0h+var_230]
0x180006aee  mov     [rsp+2B0h+var_280], ebx
0x180006af2  lea     r8, [rsp+2B0h+var_280]
0x180006af7  mov     dword ptr [rsp+2B0h+var_290], 104h
0x180006aff  lea     rdx, [rsp+2B0h+var_250]
0x180006b04  mov     rcx, rsi
0x180006b07  call    cs:__imp_SdbResolveDatabase
0x180006b0d  test    eax, eax
0x180006b0f  jz      short loc_180006B47
0x180006b11  xor     edx, edx
0x180006b13  lea     rcx, [rbp+1B0h+var_230]
0x180006b17  xor     r14d, r14d
0x180006b1a  call    cs:__imp_SdbOpenDatabase
0x180006b20  mov     rbx, rax
0x180006b23  test    rax, rax
0x180006b26  jz      short loc_180006B47
0x180006b28  mov     rcx, [rdi]
0x180006b2b  xor     edx, edx
0x180006b2d  jmp     short loc_180006B39
0x180006b2f  cmp     edx, r14d
0x180006b32  jz      short loc_180006B77
0x180006b34  mov     rcx, [rcx]
0x180006b37  inc     edx
0x180006b39  cmp     rcx, rdi
0x180006b3c  jnz     short loc_180006B2F
0x180006b3e  mov     rcx, rbx
0x180006b41  call    cs:__imp_SdbCloseDatabase
0x180006b47  mov     rcx, rsi
0x180006b4a  call    cs:__imp_SdbReleaseDatabase
0x180006b50  mov     rcx, [rbp+1B0h+var_20]
0x180006b57  xor     rcx, rsp; StackCookie
0x180006b5a  call    __security_check_cookie
0x180006b5f  lea     r11, [rsp+2B0h+var_10]
0x180006b67  mov     rbx, [r11+28h]
0x180006b6b  mov     rsi, [r11+30h]
0x180006b6f  mov     rsp, r11
0x180006b72  pop     r14
0x180006b74  pop     rdi
0x180006b75  pop     rbp
0x180006b76  retn
0x180006b77  movups  xmm0, xmmword ptr [rcx+1B4h]
0x180006b7e  lea     rax, [rsp+2B0h+var_278]
0x180006b83  mov     edx, 7007h
0x180006b88  mov     r8d, 9004h
0x180006b8e  mov     [rsp+2B0h+var_290], rax
0x180006b93  lea     r9, [rsp+2B0h+var_240]
0x180006b98  mov     rcx, rbx
0x180006b9b  movdqu  [rsp+2B0h+var_240], xmm0
0x180006ba1  inc     r14d
0x180006ba4  call    cs:__imp_SdbFindFirstGUIDIndexedTag
0x180006baa  test    eax, eax
0x180006bac  jz      loc_180006B28
0x180006bb2  xor     r9d, r9d
0x180006bb5  lea     rdx, [rsp+2B0h+var_250]
0x180006bba  mov     r8d, eax
0x180006bbd  xor     ecx, ecx
0x180006bbf  call    cs:__imp_SdbApphelpNotify
0x180006bc5  jmp     loc_180006B28
```
