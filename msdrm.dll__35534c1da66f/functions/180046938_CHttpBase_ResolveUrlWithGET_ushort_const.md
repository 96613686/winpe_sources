# CHttpBase::ResolveUrlWithGET(ushort const *)

- ea: `0x180046938`
- end: `0x180046c76`
- name: `?ResolveUrlWithGET@CHttpBase@@SAJPEBG@Z`
- size: `830`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180044088`

## callees

- `0x180001284`
- `0x180001290`
- `0x180004654`
- `0x1800046c8`
- `0x180015438`
- `0x180042640`
- `0x180042704`
- `0x180043bc0`
- `0x180045980`
- `0x180046938`
- `0x1800472d4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800469c4`
- `msvcrt!_wcsicmp` at `0x1800469c4`

## string_xrefs

- `0x180046ac5`: `[msdrm]:Using Cache ServerNotResolvable Url=%S`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CHttpBase::ResolveUrlWithGET(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  CHttpBase *v3; // rcx
  signed int ServerAndObjectPath; // ebx
  const unsigned __int16 *v5; // r9
  wchar_t *v6; // rsi
  int v7; // ebx
  unsigned int v8; // ecx
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rdi
  unsigned int v11; // r11d
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  const unsigned __int16 *v14; // rax
  unsigned __int64 v15; // rdx
  signed __int64 v16; // r15
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int16 **v20; // rax
  _BYTE v22[120]; // [rsp+40h] [rbp-D8h] BYREF
  int v23; // [rsp+B8h] [rbp-60h]
  int v24; // [rsp+CCh] [rbp-4Ch]
  int v25; // [rsp+E8h] [rbp-30h]
  wchar_t *String1; // [rsp+130h] [rbp+18h] BYREF

  CHttpBase::CHttpBase((CHttpBase *)v22, a2);
  String1 = 0;
  ServerAndObjectPath = CHttpBase::GetServerAndObjectPath(v3, a1, &String1, 0, 0, 0);
  v6 = String1;
  if ( ServerAndObjectPath >= 0 )
  {
    v7 = 0;
    if ( g_cServerNotResolvable )
    {
      while ( _wcsicmp(v6, (const wchar_t *)(&g_pwszServerNotResolvable)[v7]) )
      {
        if ( ++v7 >= g_cServerNotResolvable )
          goto LABEL_5;
      }
      v10 = -1;
      do
        ++v10;
      while ( v6[v10] );
      if ( v10 < 0x3E8 )
        _RTLTRACE("[msdrm]:Using Cache ServerNotResolvable Url=%S", v6);
      goto LABEL_19;
    }
LABEL_5:
    v25 = 1;
    v24 = 0;
    ServerAndObjectPath = CHttpBase::SetServerInfo((CHttpBase *)v22, a1, 0x12u, v5);
    if ( ServerAndObjectPath >= 0 )
    {
      ServerAndObjectPath = CHttpBase::DispatchRequest((CHttpBase *)v22, 0, 0);
      if ( ServerAndObjectPath >= 0 )
      {
        v11 = g_cUrlResolvable;
        if ( g_cUrlResolvable == 255 )
        {
          g_cUrlResolvable = 254;
          operator delete(qword_1800856A0);
          v11 = g_cUrlResolvable;
          (&g_pwszUrlResolvable)[g_cUrlResolvable] = 0;
        }
        v12 = -1;
        do
          ++v12;
        while ( a1[v12] );
        if ( v12 < 0x3E8 )
        {
          _RTLTRACE("[msdrm]:Caching Resolvable Url=%S", a1);
          v11 = g_cUrlResolvable;
        }
        if ( !a1 )
        {
          ServerAndObjectPath = -2147024809;
          goto LABEL_39;
        }
        v13 = 0x7FFFFFFF;
        v14 = a1;
        do
        {
          if ( !*v14 )
            break;
          ++v14;
          --v13;
        }
        while ( v13 );
        ServerAndObjectPath = v13 == 0 ? 0x80070057 : 0;
        v15 = (0x7FFFFFFF - v13) & ((unsigned __int128)-(__int128)(unsigned __int64)v13 >> 64);
        if ( v13 )
        {
          v16 = v15 + 1;
          if ( v15 + 1 < v15 )
            SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v13);
          v17 = HIDWORD(v16);
          if ( v16 < 0 )
            SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v17);
          v18 = 2LL * (unsigned int)v16;
          v19 = v17 << 33;
          if ( v19 + v18 < v18 )
            SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v19);
          if ( v19 + v18 )
          {
            v20 = (unsigned __int16 **)operator new[](saturated_mul(v16, 2u));
            (&g_pwszUrlResolvable)[g_cUrlResolvable] = v20;
            if ( !v20 )
            {
              ServerAndObjectPath = -2147024882;
              goto LABEL_39;
            }
            ServerAndObjectPath = StringCchCopyW((unsigned __int16 *)v20, v16, a1);
            if ( ServerAndObjectPath < 0 )
              goto LABEL_39;
          }
          g_cUrlResolvable = v11 + 1;
        }
      }
      else if ( v23 == 12007 )
      {
        v8 = g_cServerNotResolvable;
        if ( g_cServerNotResolvable == 255 )
        {
          g_cServerNotResolvable = 254;
          operator delete(qword_180086AB0);
          v8 = g_cServerNotResolvable;
          (&g_pwszServerNotResolvable)[g_cServerNotResolvable] = 0;
        }
        v9 = -1;
        do
          ++v9;
        while ( v6[v9] );
        if ( v9 < 0x3E8 )
        {
          _RTLTRACE("[msdrm]:Caching ServerNotResolvable Url=%S", v6);
          v8 = g_cServerNotResolvable;
        }
        (&g_pwszServerNotResolvable)[v8] = (unsigned __int16 * near *)v6;
        v6 = 0;
        g_cServerNotResolvable = v8 + 1;
LABEL_19:
        ServerAndObjectPath = -2147168438;
      }
    }
  }
LABEL_39:
  operator delete(v6);
  CHttpBase::~CHttpBase((CHttpBase *)v22);
  return (unsigned int)ServerAndObjectPath;
}

```

## disassembly

```asm
0x180046938  mov     rax, rsp
0x18004693b  push    rdi
0x18004693c  push    r12
0x18004693e  push    r13
0x180046940  push    r14
0x180046942  push    r15
0x180046944  sub     rsp, 0F0h
0x18004694b  mov     [rsp+118h+var_E8], 0FFFFFFFFFFFFFFFEh
0x180046954  mov     [rax+8], rbx
0x180046958  mov     [rax+20h], rsi
0x18004695c  mov     r14, rcx
0x18004695f  lea     rcx, [rsp+118h+var_D8]; this
0x180046964  call    ??0CHttpBase@@QEAA@PEBG@Z; CHttpBase::CHttpBase(ushort const *)
0x180046969  nop
0x18004696a  xor     r13d, r13d
0x18004696d  mov     [rsp+118h+String1], r13
0x180046975  mov     [rsp+118h+var_F0], r13; unsigned __int16 *
0x18004697a  mov     [rsp+118h+var_F8], r13; int *
0x18004697f  xor     r9d, r9d; unsigned __int16 **
0x180046982  lea     r8, [rsp+118h+String1]; unsigned __int16 **
0x18004698a  mov     rdx, r14; unsigned __int16 *
0x18004698d  call    ?GetServerAndObjectPath@CHttpBase@@AEAAJPEBGPEAPEAG1PEAHPEAG@Z; CHttpBase::GetServerAndObjectPath(ushort const *,ushort * *,ushort * *,int *,ushort *)
0x180046992  mov     ebx, eax
0x180046994  mov     rsi, [rsp+118h+String1]
0x18004699c  test    eax, eax
0x18004699e  js      loc_180046C32
0x1800469a4  mov     ebx, r13d
0x1800469a7  lea     r12, __ImageBase
0x1800469ae  cmp     cs:?g_cServerNotResolvable@@3IA, r13d; uint g_cServerNotResolvable
0x1800469b5  jbe     short loc_1800469DC
0x1800469b7  mov     edx, ebx
0x1800469b9  mov     rdx, rva ?g_pwszServerNotResolvable@@3PAPEAGA[r12+rdx*8]; String2
0x1800469c1  mov     rcx, rsi; String1
0x1800469c4  call    cs:__imp__wcsicmp
0x1800469ca  test    eax, eax
0x1800469cc  jz      loc_180046AAB
0x1800469d2  inc     ebx
0x1800469d4  cmp     ebx, cs:?g_cServerNotResolvable@@3IA; uint g_cServerNotResolvable
0x1800469da  jb      short loc_1800469B7
0x1800469dc  mov     [rsp+118h+var_30], 1
0x1800469e7  mov     [rsp+118h+var_4C], r13d
0x1800469ef  mov     r8d, 12h; unsigned int
0x1800469f5  mov     rdx, r14; unsigned __int16 *
0x1800469f8  lea     rcx, [rsp+118h+var_D8]; this
0x1800469fd  call    ?SetServerInfo@CHttpBase@@QEAAJPEBGI0@Z; CHttpBase::SetServerInfo(ushort const *,uint,ushort const *)
0x180046a02  mov     ebx, eax
0x180046a04  test    eax, eax
0x180046a06  js      loc_180046C32
0x180046a0c  xor     r8d, r8d; unsigned int
0x180046a0f  xor     edx, edx; unsigned __int8 *
0x180046a11  lea     rcx, [rsp+118h+var_D8]; this
0x180046a16  call    ?DispatchRequest@CHttpBase@@UEAAJPEAEI@Z; CHttpBase::DispatchRequest(uchar *,uint)
0x180046a1b  mov     ebx, eax
0x180046a1d  test    eax, eax
0x180046a1f  jns     loc_180046ADB
0x180046a25  cmp     [rsp+118h+var_60], 2EE7h
0x180046a30  jnz     loc_180046C32
0x180046a36  mov     ecx, cs:?g_cServerNotResolvable@@3IA; uint g_cServerNotResolvable
0x180046a3c  cmp     ecx, 0FFh
0x180046a42  jnz     short loc_180046A68
0x180046a44  mov     cs:?g_cServerNotResolvable@@3IA, 0FEh; uint g_cServerNotResolvable
0x180046a4e  mov     rcx, cs:qword_180086AB0; Block
0x180046a55  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180046a5a  mov     ecx, cs:?g_cServerNotResolvable@@3IA; uint g_cServerNotResolvable
0x180046a60  mov     rva ?g_pwszServerNotResolvable@@3PAPEAGA[r12+rcx*8], r13; ushort * near * g_pwszServerNotResolvable ...
0x180046a68  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180046a6c  inc     rdi
0x180046a6f  cmp     [rsi+rdi*2], r13w
0x180046a74  jnz     short loc_180046A6C
0x180046a76  cmp     rdi, 3E8h
0x180046a7d  jnb     short loc_180046A94
0x180046a7f  mov     rdx, rsi
0x180046a82  lea     rcx, aMsdrmCachingSe; "[msdrm]:Caching ServerNotResolvable Url"...
0x180046a89  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180046a8e  mov     ecx, cs:?g_cServerNotResolvable@@3IA; uint g_cServerNotResolvable
0x180046a94  mov     eax, ecx
0x180046a96  mov     rva ?g_pwszServerNotResolvable@@3PAPEAGA[r12+rax*8], rsi; ushort * near * g_pwszServerNotResolvable ...
0x180046a9e  mov     rsi, r13
0x180046aa1  inc     ecx
0x180046aa3  mov     cs:?g_cServerNotResolvable@@3IA, ecx; uint g_cServerNotResolvable
0x180046aa9  jmp     short loc_180046AD1
0x180046aab  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180046aaf  inc     rdi
0x180046ab2  cmp     [rsi+rdi*2], r13w
0x180046ab7  jnz     short loc_180046AAF
0x180046ab9  cmp     rdi, 3E8h
0x180046ac0  jnb     short loc_180046AD1
0x180046ac2  mov     rdx, rsi
0x180046ac5  lea     rcx, aMsdrmUsingCach_0; "[msdrm]:Using Cache ServerNotResolvable"...
0x180046acc  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180046ad1  mov     ebx, 8004CF4Ah
0x180046ad6  jmp     loc_180046C32
0x180046adb  mov     r11d, cs:?g_cUrlResolvable@@3IA; uint g_cUrlResolvable
0x180046ae2  cmp     r11d, 0FFh
0x180046ae9  jnz     short loc_180046B10
0x180046aeb  mov     cs:?g_cUrlResolvable@@3IA, 0FEh; uint g_cUrlResolvable
0x180046af5  mov     rcx, cs:qword_1800856A0; Block
0x180046afc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180046b01  mov     r11d, cs:?g_cUrlResolvable@@3IA; uint g_cUrlResolvable
0x180046b08  mov     rva ?g_pwszUrlResolvable@@3PAPEAGA[r12+r11*8], r13; ushort * near * g_pwszUrlResolvable ...
0x180046b10  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180046b14  mov     rax, rdi
0x180046b17  inc     rax
0x180046b1a  cmp     [r14+rax*2], r13w
0x180046b1f  jnz     short loc_180046B17
0x180046b21  cmp     rax, 3E8h
0x180046b27  jnb     short loc_180046B3F
0x180046b29  mov     rdx, r14
0x180046b2c  lea     rcx, aMsdrmCachingRe; "[msdrm]:Caching Resolvable Url=%S"
0x180046b33  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180046b38  mov     r11d, cs:?g_cUrlResolvable@@3IA; uint g_cUrlResolvable
0x180046b3f  test    r14, r14
0x180046b42  jz      loc_180046C1C
0x180046b48  mov     r8d, 7FFFFFFFh
0x180046b4e  mov     ecx, r8d
0x180046b51  mov     rax, r14
0x180046b54  cmp     [rax], r13w
0x180046b58  jz      short loc_180046B64
0x180046b5a  add     rax, 2
0x180046b5e  sub     rcx, 1
0x180046b62  jnz     short loc_180046B54
0x180046b64  mov     rax, rcx
0x180046b67  neg     rax
0x180046b6a  sbb     ebx, ebx
0x180046b6c  not     ebx
0x180046b6e  and     ebx, 80070057h
0x180046b74  mov     rax, rcx
0x180046b77  sub     r8, rcx
0x180046b7a  neg     rax
0x180046b7d  sbb     rdx, rdx
0x180046b80  and     rdx, r8
0x180046b83  test    rcx, rcx
0x180046b86  jz      loc_180046C21
0x180046b8c  lea     r15, [rdx+1]
0x180046b90  cmp     r15, rdx
0x180046b93  jb      loc_180046C64
0x180046b99  mov     rcx, r15
0x180046b9c  shr     rcx, 20h
0x180046ba0  mov     rax, rcx
0x180046ba3  shr     rax, 1Fh
0x180046ba7  test    eax, eax
0x180046ba9  jnz     loc_180046C6A
0x180046baf  mov     eax, r15d
0x180046bb2  add     rax, rax
0x180046bb5  shl     rcx, 21h
0x180046bb9  lea     rdx, [rcx+rax]
0x180046bbd  cmp     rdx, rax
0x180046bc0  jb      loc_180046C6F
0x180046bc6  test    rdx, rdx
0x180046bc9  jz      short loc_180046C10
0x180046bcb  mov     eax, 2
0x180046bd0  mul     r15
0x180046bd3  cmovb   rax, rdi
0x180046bd7  mov     rcx, rax; unsigned __int64
0x180046bda  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180046bdf  mov     r11d, cs:?g_cUrlResolvable@@3IA; uint g_cUrlResolvable
0x180046be6  mov     rva ?g_pwszUrlResolvable@@3PAPEAGA[r12+r11*8], rax; ushort * near * g_pwszUrlResolvable ...
0x180046bee  test    rax, rax
0x180046bf1  jnz     short loc_180046BFA
0x180046bf3  mov     ebx, 8007000Eh
0x180046bf8  jmp     short loc_180046C32
0x180046bfa  mov     r8, r14; unsigned __int16 *
0x180046bfd  mov     rdx, r15; unsigned __int64
0x180046c00  mov     rcx, rax; unsigned __int16 *
0x180046c03  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180046c08  mov     ebx, eax
0x180046c0a  test    eax, eax
0x180046c0c  jns     short loc_180046C10
0x180046c0e  jmp     short loc_180046C32
0x180046c10  inc     r11d
0x180046c13  mov     cs:?g_cUrlResolvable@@3IA, r11d; uint g_cUrlResolvable
0x180046c1a  jmp     short loc_180046C32
0x180046c1c  mov     ebx, 80070057h
0x180046c21  jmp     short loc_180046C32
0x180046c23  mov     ebx, [rsp+118h+arg_8]
0x180046c2a  mov     rsi, [rsp+118h+String1]
0x180046c32  mov     rcx, rsi; Block
0x180046c35  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180046c3a  nop
0x180046c3b  lea     rcx, [rsp+118h+var_D8]; this
0x180046c40  call    ??1CHttpBase@@UEAA@XZ; CHttpBase::~CHttpBase(void)
0x180046c45  mov     eax, ebx
0x180046c47  lea     r11, [rsp+118h+var_28]
0x180046c4f  mov     rbx, [r11+30h]
0x180046c53  mov     rsi, [r11+48h]
0x180046c57  mov     rsp, r11
0x180046c5a  pop     r15
0x180046c5c  pop     r14
0x180046c5e  pop     r13
0x180046c60  pop     r12
0x180046c62  pop     rdi
0x180046c63  retn
0x180046c64  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180046c6a  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180046c6f  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
