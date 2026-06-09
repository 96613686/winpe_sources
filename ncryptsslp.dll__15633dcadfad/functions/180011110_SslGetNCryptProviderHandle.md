# SslGetNCryptProviderHandle

- ea: `0x180011110`
- end: `0x18001122b`
- name: `SslGetNCryptProviderHandle`
- size: `283`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800105e0`
- `0x180013b80`
- `0x180021a74`

## callees

- `0x18000b654`
- `0x180011110`
- `0x180011240`
- `0x180023ac4`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800111a8`
- `ntdll!RtlReleaseResource` at `0x1800111a8`
- `ntdll!RtlAcquireResourceShared` at `0x180011161`
- `ntdll!RtlAcquireResourceShared` at `0x180011161`

## string_xrefs

- `0x1800111d6`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsncryptprovider.c`
- `0x18001120b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsncryptprovider.c`

## pseudocode

```c
__int64 __fastcall SslGetNCryptProviderHandle(unsigned __int16 *a1, __int64 *a2, int a3)
{
  int IsAppContainer; // eax
  unsigned int v6; // ebx
  __int64 *v7; // rsi
  __int64 v8; // rbx
  _QWORD *v9; // r9
  unsigned __int16 *v10; // rax
  int v11; // ecx
  int v12; // edx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // [rsp+50h] [rbp+18h] BYREF

  LOBYTE(v16) = 0;
  IsAppContainer = SslIsAppContainer((bool *)&v16, (__int64)a2, a3);
  v6 = IsAppContainer;
  if ( IsAppContainer < 0 )
  {
    DebugTraceError(
      (unsigned int)IsAppContainer,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsncryptprovider.c",
      241);
    return v6;
  }
  v7 = qword_18003F3E0;
  if ( !(_BYTE)v16 )
    v7 = qword_18003F460;
  v8 = 0;
  RtlAcquireResourceShared((PRTL_RESOURCE)(v7 + 3), 1u);
  v9 = (_QWORD *)*v7;
  if ( *v7 )
  {
    do
    {
      if ( v8 )
        break;
      v10 = a1;
      do
      {
        v11 = *(unsigned __int16 *)((char *)v10 + v9[1] - (_QWORD)a1);
        v12 = *v10 - v11;
        if ( v12 )
          break;
        ++v10;
      }
      while ( v11 );
      if ( !v12 )
        v8 = v9[2];
      v9 = (_QWORD *)*v9;
    }
    while ( v9 );
  }
  RtlReleaseResource((PRTL_RESOURCE)(v7 + 3));
  v16 = v8;
  if ( !v8 )
  {
    v14 = SslOpenAndCacheNCryptProv((__int64)v7, a1, &v16);
    v15 = v14;
    if ( v14 < 0 )
    {
      DebugTraceError(
        (unsigned int)v14,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsncryptprovider.c",
        255);
      return v15;
    }
    v8 = v16;
  }
  *a2 = v8;
  return 0;
}

```

## disassembly

```asm
0x180011110  push    rbx
0x180011112  push    rdi
0x180011113  push    r14
0x180011115  sub     rsp, 20h
0x180011119  mov     rdi, rcx
0x18001111c  mov     byte ptr [rsp+38h+arg_10], 0
0x180011121  lea     rcx, [rsp+38h+arg_10]
0x180011126  mov     r14, rdx
0x180011129  call    SslIsAppContainer
0x18001112e  mov     ebx, eax
0x180011130  test    eax, eax
0x180011132  js      loc_1800111D0
0x180011138  cmp     byte ptr [rsp+38h+arg_10], 0
0x18001113d  lea     rax, qword_18003F460
0x180011144  mov     [rsp+38h+arg_0], rbp
0x180011149  mov     dl, 1; Wait
0x18001114b  mov     [rsp+38h+arg_8], rsi
0x180011150  lea     rsi, qword_18003F3E0
0x180011157  cmovz   rsi, rax
0x18001115b  xor     ebx, ebx
0x18001115d  lea     rcx, [rsi+18h]; Resource
0x180011161  call    cs:__imp_RtlAcquireResourceShared
0x180011167  mov     r9, [rsi]
0x18001116a  test    r9, r9
0x18001116d  jz      short loc_1800111A4
0x18001116f  test    rbx, rbx
0x180011172  jnz     short loc_1800111A4
0x180011174  mov     r8, [r9+8]
0x180011178  mov     rax, rdi
0x18001117b  sub     r8, rdi
0x18001117e  xchg    ax, ax
0x180011180  movzx   edx, word ptr [rax]
0x180011183  movzx   ecx, word ptr [rax+r8]
0x180011188  sub     edx, ecx
0x18001118a  jnz     short loc_180011194
0x18001118c  add     rax, 2
0x180011190  test    ecx, ecx
0x180011192  jnz     short loc_180011180
0x180011194  test    edx, edx
0x180011196  jnz     short loc_18001119C
0x180011198  mov     rbx, [r9+10h]
0x18001119c  mov     r9, [r9]
0x18001119f  test    r9, r9
0x1800111a2  jnz     short loc_18001116F
0x1800111a4  lea     rcx, [rsi+18h]; Resource
0x1800111a8  call    cs:__imp_RtlReleaseResource
0x1800111ae  mov     rbp, [rsp+38h+arg_0]
0x1800111b3  mov     [rsp+38h+arg_10], rbx
0x1800111b8  test    rbx, rbx
0x1800111bb  jz      short loc_1800111EF
0x1800111bd  mov     [r14], rbx
0x1800111c0  xor     eax, eax
0x1800111c2  mov     rsi, [rsp+38h+arg_8]
0x1800111c7  add     rsp, 20h
0x1800111cb  pop     r14
0x1800111cd  pop     rdi
0x1800111ce  pop     rbx
0x1800111cf  retn
0x1800111d0  mov     r9d, 0F1h
0x1800111d6  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800111dd  lea     rdx, aStatus; "Status"
0x1800111e4  mov     ecx, ebx
0x1800111e6  call    DebugTraceError
0x1800111eb  mov     eax, ebx
0x1800111ed  jmp     short loc_1800111C7
0x1800111ef  lea     r8, [rsp+38h+arg_10]
0x1800111f4  mov     rdx, rdi
0x1800111f7  mov     rcx, rsi
0x1800111fa  call    SslOpenAndCacheNCryptProv
0x1800111ff  mov     ebx, eax
0x180011201  test    eax, eax
0x180011203  jns     short loc_180011224
0x180011205  mov     r9d, 0FFh
0x18001120b  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011212  lea     rdx, aStatus; "Status"
0x180011219  mov     ecx, eax
0x18001121b  call    DebugTraceError
0x180011220  mov     eax, ebx
0x180011222  jmp     short loc_1800111C2
0x180011224  mov     rbx, [rsp+38h+arg_10]
0x180011229  jmp     short loc_1800111BD
```
