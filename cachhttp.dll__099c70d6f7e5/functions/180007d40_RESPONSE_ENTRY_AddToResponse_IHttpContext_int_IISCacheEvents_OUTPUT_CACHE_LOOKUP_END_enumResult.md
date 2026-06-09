# RESPONSE_ENTRY::AddToResponse(IHttpContext *,int *,IISCacheEvents::OUTPUT_CACHE_LOOKUP_END::enumResult *)

- ea: `0x180007d40`
- end: `0x18000809f`
- name: `?AddToResponse@RESPONSE_ENTRY@@QEAAJPEAVIHttpContext@@PEAHPEAW4enumResult@OUTPUT_CACHE_LOOKUP_END@IISCacheEvents@@@Z`
- size: `863`
- prototype: `__int64 __fastcall(RESPONSE_ENTRY *__hidden this, struct IHttpContext *, int *, enum IISCacheEvents::OUTPUT_CACHE_LOOKUP_END::enumResult *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002f20`

## callees

- `0x180004d90`
- `0x1800065c8`
- `0x180007d40`
- `0x180009010`

## import_xrefs

- `msvcrt!strstr` at `0x180007e22`
- `msvcrt!strstr` at `0x180007e22`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007eb9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007eb9`
- `iisutil!StringTimeToFileTime` at `0x180007e84`
- `iisutil!StringTimeToFileTime` at `0x180007e99`
- `iisutil!StringTimeToFileTime` at `0x180007e84`
- `iisutil!StringTimeToFileTime` at `0x180007e99`

## pseudocode

```c
__int64 __fastcall RESPONSE_ENTRY::AddToResponse(
        RESPONSE_ENTRY *this,
        struct IHttpContext *a2,
        int *a3,
        enum IISCacheEvents::OUTPUT_CACHE_LOOKUP_END::enumResult *a4)
{
  int v5; // r13d
  int v8; // r15d
  __int64 v9; // rsi
  const char *v10; // rax
  const char *v11; // rcx
  int v12; // r12d
  const char *v13; // rax
  __int64 v14; // rdx
  const char *v15; // rax
  const char *v16; // rdx
  const char *v17; // r12
  __int64 v18; // rax
  int *v19; // rax
  _BYTE *v20; // r13
  _BYTE *v21; // r12
  _BYTE *v22; // rax
  __int64 v23; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  _OWORD *v28; // rcx
  _OWORD *v29; // rax
  __int128 v30; // xmm1
  int *v31; // rax
  union _LARGE_INTEGER v32; // [rsp+40h] [rbp-10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-8h] BYREF
  unsigned __int16 v34; // [rsp+90h] [rbp+40h] BYREF
  union _LARGE_INTEGER v35; // [rsp+98h] [rbp+48h] BYREF
  int *v36; // [rsp+A0h] [rbp+50h]

  v36 = a3;
  v5 = 0;
  v8 = 0;
  v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v34 = 0;
  v10 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v9 + 16LL))(
                        v9,
                        20,
                        &v34);
  if ( v10 )
  {
    if ( *v10 )
    {
      v11 = (const char *)*((_QWORD *)this + 34);
      if ( v11 )
      {
        if ( *v11 )
        {
          v35.LowPart = 0;
          v8 = IsAcceptable(v11, v10, v34, (int *)&v35);
          if ( v8 < 0 )
          {
LABEL_33:
            RESPONSE_ENTRY::DereferenceResponseEntry(this);
            return (unsigned int)v8;
          }
          if ( !v35.LowPart )
          {
            *(_DWORD *)a4 = 2;
            goto LABEL_33;
          }
        }
      }
    }
  }
  v12 = 1;
  v13 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v9 + 16LL))(v9, 31, 0);
  if ( v13 )
  {
    v14 = *((_QWORD *)this + 54);
    if ( !v14 || *(_BYTE *)v14 == 87 && *(_BYTE *)(v14 + 1) == 47 || !strstr(v13, (const char *)v14) )
      v5 = 1;
    else
      v12 = 0;
  }
  v15 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 16LL))(v9, 30);
  if ( v5 || !v15 )
  {
    if ( !v12 )
    {
LABEL_23:
      v18 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
      (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v18 + 24LL))(
        v18,
        304,
        "Not Modified",
        0,
        0,
        0,
        0);
      v19 = v36;
      *(_DWORD *)a4 = 1;
      *v19 = 1;
      RESPONSE_ENTRY::DereferenceResponseEntry(this);
      return 0;
    }
  }
  else
  {
    v16 = (const char *)*((_QWORD *)this + 48);
    v17 = byte_18000B9AD;
    v32.QuadPart = 0;
    v35.QuadPart = 0;
    if ( v16 )
      v17 = v16;
    if ( StringTimeToFileTime(v15, &v35) )
    {
      if ( StringTimeToFileTime(v17, &v32) )
      {
        if ( v32.QuadPart <= v35.QuadPart )
        {
          SystemTimeAsFileTime = 0;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          if ( *(_QWORD *)&SystemTimeAsFileTime >= v35.QuadPart )
            goto LABEL_23;
        }
      }
    }
  }
  v20 = (_BYTE *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 16LL))(v9, 37);
  v21 = (_BYTE *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 16LL))(v9, 29);
  v22 = (_BYTE *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 16LL))(v9, 33);
  if ( v20 && *v20 || v21 && *v21 || v22 && *v22 )
  {
    *(_DWORD *)a4 = 5;
    goto LABEL_33;
  }
  v23 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 56LL))(a2);
  v8 = (*(__int64 (__fastcall **)(__int64, RESPONSE_ENTRY *, void *))(*(_QWORD *)v23 + 8LL))(v23, this, g_pModuleId);
  if ( v8 < 0 )
    goto LABEL_33;
  v25 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
  v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
  v27 = 4;
  v28 = (_OWORD *)v26;
  v29 = (_OWORD *)((char *)this + 16);
  do
  {
    *v28 = *v29;
    v28[1] = v29[1];
    v28[2] = v29[2];
    v28[3] = v29[3];
    v28[4] = v29[4];
    v28[5] = v29[5];
    v28[6] = v29[6];
    v30 = v29[7];
    v29 += 8;
    v28[7] = v30;
    v28 += 8;
    --v27;
  }
  while ( v27 );
  *v28 = *v29;
  v28[1] = v29[1];
  v28[2] = v29[2];
  *((_QWORD *)v28 + 6) = *((_QWORD *)v29 + 6);
  v31 = v36;
  *(_DWORD *)a4 = 1;
  *v31 = 1;
  return 0;
}

```

## disassembly

```asm
0x180007d40  mov     [rsp-38h+arg_18], rbx
0x180007d45  mov     [rsp-38h+arg_10], r8
0x180007d4a  push    rbp
0x180007d4b  push    rsi
0x180007d4c  push    rdi
0x180007d4d  push    r12
0x180007d4f  push    r13
0x180007d51  push    r14
0x180007d53  push    r15
0x180007d55  mov     rbp, rsp
0x180007d58  sub     rsp, 50h
0x180007d5c  mov     rax, [rdx]
0x180007d5f  mov     rbx, rcx
0x180007d62  xor     r13d, r13d
0x180007d65  mov     rcx, rdx
0x180007d68  mov     r14, r9
0x180007d6b  mov     rdi, rdx
0x180007d6e  mov     r15d, r13d
0x180007d71  mov     rax, [rax+18h]
0x180007d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d7a  mov     rsi, rax
0x180007d7d  mov     [rbp+arg_0], r13w
0x180007d82  lea     r8, [rbp+arg_0]
0x180007d86  mov     rcx, rsi
0x180007d89  lea     edx, [r13+14h]
0x180007d8d  mov     rax, [rax]
0x180007d90  mov     rax, [rax+10h]
0x180007d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d99  test    rax, rax
0x180007d9c  jz      short loc_180007DE6
0x180007d9e  cmp     [rax], r13b
0x180007da1  jz      short loc_180007DE6
0x180007da3  mov     rcx, [rbx+110h]; Str
0x180007daa  test    rcx, rcx
0x180007dad  jz      short loc_180007DE6
0x180007daf  cmp     [rcx], r13b
0x180007db2  jz      short loc_180007DE6
0x180007db4  movzx   r8d, [rbp+arg_0]; unsigned __int16
0x180007db9  lea     r9, [rbp+arg_8]; int *
0x180007dbd  mov     rdx, rax; char *
0x180007dc0  mov     dword ptr [rbp+arg_8], r13d
0x180007dc4  call    ?IsAcceptable@@YAJPEBD0GPEAH@Z; IsAcceptable(char const *,char const *,ushort,int *)
0x180007dc9  mov     r15d, eax
0x180007dcc  test    eax, eax
0x180007dce  js      loc_180007FD0
0x180007dd4  cmp     dword ptr [rbp+arg_8], r13d
0x180007dd8  jnz     short loc_180007DE6
0x180007dda  mov     dword ptr [r14], 2
0x180007de1  jmp     loc_180007FD0
0x180007de6  mov     rax, [rsi]
0x180007de9  mov     r12d, 1
0x180007def  xor     r8d, r8d
0x180007df2  mov     rcx, rsi
0x180007df5  mov     rax, [rax+10h]
0x180007df9  lea     edx, [r12+1Eh]
0x180007dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e03  test    rax, rax
0x180007e06  jz      short loc_180007E35
0x180007e08  mov     rdx, [rbx+1B0h]; SubStr
0x180007e0f  test    rdx, rdx
0x180007e12  jz      short loc_180007E32
0x180007e14  cmp     byte ptr [rdx], 57h ; 'W'
0x180007e17  jnz     short loc_180007E1F
0x180007e19  cmp     byte ptr [rdx+1], 2Fh ; '/'
0x180007e1d  jz      short loc_180007E32
0x180007e1f  mov     rcx, rax; Str
0x180007e22  call    cs:__imp_strstr
0x180007e28  test    rax, rax
0x180007e2b  jz      short loc_180007E32
0x180007e2d  xor     r12d, r12d
0x180007e30  jmp     short loc_180007E35
0x180007e32  mov     r13d, r12d
0x180007e35  mov     rax, [rsi]
0x180007e38  xor     r8d, r8d
0x180007e3b  mov     rcx, rsi
0x180007e3e  mov     rax, [rax+10h]
0x180007e42  lea     edx, [r8+1Eh]
0x180007e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e4b  test    r13d, r13d
0x180007e4e  jnz     loc_180007F23
0x180007e54  xor     r13d, r13d
0x180007e57  test    rax, rax
0x180007e5a  jz      loc_180007F26
0x180007e60  mov     rdx, [rbx+180h]
0x180007e67  lea     r12, byte_18000B9AD
0x180007e6e  test    rdx, rdx
0x180007e71  mov     [rbp+var_10], r13
0x180007e75  mov     rcx, rax
0x180007e78  mov     [rbp+arg_8], r13
0x180007e7c  cmovnz  r12, rdx
0x180007e80  lea     rdx, [rbp+arg_8]
0x180007e84  call    cs:__imp_?StringTimeToFileTime@@YAHPEBDPEAT_LARGE_INTEGER@@@Z; StringTimeToFileTime(char const *,_LARGE_INTEGER *)
0x180007e8a  test    eax, eax
0x180007e8c  jz      loc_180007F2B
0x180007e92  lea     rdx, [rbp+var_10]
0x180007e96  mov     rcx, r12
0x180007e99  call    cs:__imp_?StringTimeToFileTime@@YAHPEBDPEAT_LARGE_INTEGER@@@Z; StringTimeToFileTime(char const *,_LARGE_INTEGER *)
0x180007e9f  test    eax, eax
0x180007ea1  jz      loc_180007F2B
0x180007ea7  mov     rax, [rbp+arg_8]
0x180007eab  cmp     [rbp+var_10], rax
0x180007eaf  jg      short loc_180007F2B
0x180007eb1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180007eb5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r13
0x180007eb9  call    cs:__imp_GetSystemTimeAsFileTime
0x180007ebf  mov     rax, [rbp+arg_8]
0x180007ec3  cmp     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180007ec7  jl      short loc_180007F2B
0x180007ec9  mov     rax, [rdi]
0x180007ecc  mov     rcx, rdi
0x180007ecf  mov     rax, [rax+20h]
0x180007ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ed8  mov     r10, rax
0x180007edb  mov     [rsp+50h+var_20], r13d
0x180007ee0  xor     r9d, r9d
0x180007ee3  mov     [rsp+50h+var_28], r13
0x180007ee8  mov     edx, 130h
0x180007eed  mov     [rsp+50h+var_30], r13d
0x180007ef2  mov     rcx, [rax]
0x180007ef5  lea     r8, aNotModified; "Not Modified"
0x180007efc  mov     rax, [rcx+18h]
0x180007f00  mov     rcx, r10
0x180007f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f08  mov     rax, [rbp+arg_10]
0x180007f0c  mov     ecx, 1
0x180007f11  mov     [r14], ecx
0x180007f14  mov     [rax], ecx
0x180007f16  mov     rcx, rbx; this
0x180007f19  call    ?DereferenceResponseEntry@RESPONSE_ENTRY@@QEAAXXZ; RESPONSE_ENTRY::DereferenceResponseEntry(void)
0x180007f1e  jmp     loc_180008085
0x180007f23  xor     r13d, r13d
0x180007f26  test    r12d, r12d
0x180007f29  jz      short loc_180007EC9
0x180007f2b  mov     rax, [rsi]
0x180007f2e  xor     r8d, r8d
0x180007f31  mov     rcx, rsi
0x180007f34  mov     rax, [rax+10h]
0x180007f38  lea     edx, [r8+25h]
0x180007f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f41  mov     rcx, [rsi]
0x180007f44  xor     r8d, r8d
0x180007f47  mov     r13, rax
0x180007f4a  mov     rax, [rcx+10h]
0x180007f4e  lea     edx, [r8+1Dh]
0x180007f52  mov     rcx, rsi
0x180007f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f5a  mov     rcx, [rsi]
0x180007f5d  xor     r8d, r8d
0x180007f60  mov     r12, rax
0x180007f63  mov     rax, [rcx+10h]
0x180007f67  lea     edx, [r8+21h]
0x180007f6b  mov     rcx, rsi
0x180007f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f73  xor     esi, esi
0x180007f75  test    r13, r13
0x180007f78  jz      short loc_180007F80
0x180007f7a  cmp     [r13+0], sil
0x180007f7e  jnz     short loc_180007F95
0x180007f80  test    r12, r12
0x180007f83  jz      short loc_180007F8B
0x180007f85  cmp     [r12], sil
0x180007f89  jnz     short loc_180007F95
0x180007f8b  test    rax, rax
0x180007f8e  jz      short loc_180007F9E
0x180007f90  cmp     [rax], sil
0x180007f93  jz      short loc_180007F9E
0x180007f95  mov     dword ptr [r14], 5
0x180007f9c  jmp     short loc_180007FD0
0x180007f9e  mov     rax, [rdi]
0x180007fa1  mov     rcx, rdi
0x180007fa4  mov     rax, [rax+38h]
0x180007fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fad  mov     r8, cs:?g_pModuleId@@3PEAXEA; void * g_pModuleId
0x180007fb4  mov     r9, rax
0x180007fb7  mov     rdx, rbx
0x180007fba  mov     rcx, [rax]
0x180007fbd  mov     rax, [rcx+8]
0x180007fc1  mov     rcx, r9
0x180007fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fc9  mov     r15d, eax
0x180007fcc  test    eax, eax
0x180007fce  jns     short loc_180007FE0
0x180007fd0  mov     rcx, rbx; this
0x180007fd3  call    ?DereferenceResponseEntry@RESPONSE_ENTRY@@QEAAXXZ; RESPONSE_ENTRY::DereferenceResponseEntry(void)
0x180007fd8  mov     eax, r15d
0x180007fdb  jmp     loc_180008087
0x180007fe0  mov     rax, [rdi]
0x180007fe3  mov     rcx, rdi
0x180007fe6  mov     rax, [rax+20h]
0x180007fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fef  mov     rdx, rax
0x180007ff2  mov     rcx, [rax]
0x180007ff5  mov     rax, [rcx+8]
0x180007ff9  mov     rcx, rdx
0x180007ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008001  mov     edx, 4
0x180008006  mov     rcx, rax
0x180008009  lea     rax, [rbx+10h]
0x18000800d  lea     r8d, [rdx+7Ch]
0x180008011  movups  xmm0, xmmword ptr [rax]
0x180008014  movups  xmmword ptr [rcx], xmm0
0x180008017  movups  xmm1, xmmword ptr [rax+10h]
0x18000801b  movups  xmmword ptr [rcx+10h], xmm1
0x18000801f  movups  xmm0, xmmword ptr [rax+20h]
0x180008023  movups  xmmword ptr [rcx+20h], xmm0
0x180008027  movups  xmm1, xmmword ptr [rax+30h]
0x18000802b  movups  xmmword ptr [rcx+30h], xmm1
0x18000802f  movups  xmm0, xmmword ptr [rax+40h]
0x180008033  movups  xmmword ptr [rcx+40h], xmm0
0x180008037  movups  xmm1, xmmword ptr [rax+50h]
0x18000803b  movups  xmmword ptr [rcx+50h], xmm1
0x18000803f  movups  xmm0, xmmword ptr [rax+60h]
0x180008043  movups  xmmword ptr [rcx+60h], xmm0
0x180008047  movups  xmm1, xmmword ptr [rax+70h]
0x18000804b  add     rax, r8
0x18000804e  movups  xmmword ptr [rcx+70h], xmm1
0x180008052  add     rcx, r8
0x180008055  sub     rdx, 1
0x180008059  jnz     short loc_180008011
0x18000805b  movups  xmm0, xmmword ptr [rax]
0x18000805e  movups  xmmword ptr [rcx], xmm0
0x180008061  movups  xmm1, xmmword ptr [rax+10h]
0x180008065  movups  xmmword ptr [rcx+10h], xmm1
0x180008069  movups  xmm0, xmmword ptr [rax+20h]
0x18000806d  movups  xmmword ptr [rcx+20h], xmm0
0x180008071  mov     rax, [rax+30h]
0x180008075  mov     [rcx+30h], rax
0x180008079  lea     ecx, [rdx+1]
0x18000807c  mov     rax, [rbp+arg_10]
0x180008080  mov     [r14], ecx
0x180008083  mov     [rax], ecx
0x180008085  xor     eax, eax
0x180008087  mov     rbx, [rsp+50h+arg_18]
0x18000808f  add     rsp, 50h
0x180008093  pop     r15
0x180008095  pop     r14
0x180008097  pop     r13
0x180008099  pop     r12
0x18000809b  pop     rdi
0x18000809c  pop     rsi
0x18000809d  pop     rbp
0x18000809e  retn
```
