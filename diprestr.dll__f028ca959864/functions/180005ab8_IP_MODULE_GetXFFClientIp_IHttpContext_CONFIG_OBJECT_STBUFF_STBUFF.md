# IP_MODULE::GetXFFClientIp(IHttpContext *,CONFIG_OBJECT *,STBUFF *,STBUFF *)

- ea: `0x180005ab8`
- end: `0x180005d6b`
- name: `?GetXFFClientIp@IP_MODULE@@CAJPEAVIHttpContext@@PEAVCONFIG_OBJECT@@PEAVSTBUFF@@2@Z`
- size: `691`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct CONFIG_OBJECT *, struct STBUFF *, struct STBUFF *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800047a4`

## callees

- `0x180001948`
- `0x180001a2c`
- `0x180001af4`
- `0x180001dc8`
- `0x180002510`
- `0x180005ab8`
- `0x1800067c0`
- `0x180007010`

## import_xrefs

- `msvcrt!strrchr` at `0x180005b60`
- `msvcrt!strrchr` at `0x180005b60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005d15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005d43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005d15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005d43`
- `iisutil!PuDbgPrint` at `0x180005cb0`
- `iisutil!PuDbgPrint` at `0x180005cb0`

## string_xrefs

- `0x180005c76`: `servercommon\inetsrv\iis\iisrearc\iis70\dynamiciprestriction\dipmodule.cpp`

## pseudocode

```c
__int64 __fastcall IP_MODULE::GetXFFClientIp(
        struct IHttpContext *a1,
        struct CONFIG_OBJECT *a2,
        struct STBUFF *a3,
        struct STBUFF *a4)
{
  int v7; // edx
  int appended; // edi
  int v9; // r15d
  char *v10; // rax
  char *v11; // rbx
  ALLOW_LIST *v12; // rcx
  _WORD *v13; // r14
  char *v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // r8d
  __int64 v17; // r8
  __int64 v18; // rax
  void **v21; // [rsp+50h] [rbp-B0h] BYREF
  char *Str; // [rsp+58h] [rbp-A8h]
  int v23; // [rsp+60h] [rbp-A0h]
  int v24; // [rsp+64h] [rbp-9Ch]
  _BYTE v25[68]; // [rsp+6Ch] [rbp-94h] BYREF
  void **v26; // [rsp+B0h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+B8h] [rbp-48h]
  char v28; // [rsp+CCh] [rbp-34h] BYREF

  STBUFF::STBUFF((STBUFF *)&v26, (int)a2);
  STBUFF::STBUFF((STBUFF *)&v21, v7);
  appended = PopulateXFFHeader(a1, (struct STBUFF *)&v21);
  if ( appended >= 0 && v23 )
  {
    v9 = 0;
    for ( Str[v23] = 0; ; Str[v23] = 0 )
    {
      Str[v23 + 1] = 0;
      v14 = Str;
      if ( !Str || v9 )
        break;
      Str[v23] = 0;
      Str[v23 + 1] = 0;
      v10 = strrchr(Str, 44);
      if ( v10 )
      {
        *v10 = 0;
        v11 = v10 + 1;
      }
      else
      {
        v9 = 1;
        Str[v23] = 0;
        Str[v23 + 1] = 0;
        v11 = Str;
      }
      appended = IpToSockAddr(v11, (struct STBUFF *)&v26);
      if ( appended < 0 )
      {
        v18 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
        (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v18 + 24LL))(
          v18,
          400,
          "Bad Request",
          10,
          appended,
          0,
          0);
        goto LABEL_25;
      }
      v12 = (ALLOW_LIST *)*((_QWORD *)a2 + 25);
      v13 = hMem;
      if ( !v12 || !(unsigned int)ALLOW_LIST::QueryIpAllowed(v12, (struct sockaddr *)hMem) )
      {
        v15 = 4;
        if ( *v13 != 23 )
          v15 = 2;
        v16 = 16;
        if ( *v13 != 23 )
          v16 = 4;
        appended = STBUFF::AppendData(a3, &v13[v15], v16, 0);
        if ( appended >= 0 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v11[v17] );
          appended = STBUFF::AppendData(a4, v11, v17, 0);
          if ( appended >= 0 && (g_dwDebugFlags & 3) != 0 )
          {
            *(_BYTE *)(*((unsigned int *)a4 + 4) + *((_QWORD *)a4 + 1)) = 0;
            *(_BYTE *)((unsigned int)(*((_DWORD *)a4 + 4) + 1) + *((_QWORD *)a4 + 1)) = 0;
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\dynamiciprestriction\\dipmodule.cpp",
              1387,
              "IP_MODULE::GetXFFClientIp",
              "Using this IP for checks %s.\n",
              *((const char **)a4 + 1));
          }
        }
        goto LABEL_25;
      }
    }
  }
  else
  {
LABEL_25:
    v14 = Str;
  }
  v21 = &STBUFF::`vftable';
  if ( v14 != v25 )
  {
    LocalFree(v14);
    v24 = 64;
    Str = v25;
  }
  v26 = &STBUFF::`vftable';
  v23 = 0;
  if ( hMem != &v28 )
    LocalFree(hMem);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180005ab8  push    rbp
0x180005aba  push    rbx
0x180005abb  push    rsi
0x180005abc  push    rdi
0x180005abd  push    r12
0x180005abf  push    r13
0x180005ac1  push    r14
0x180005ac3  push    r15
0x180005ac5  lea     rbp, [rsp-28h]
0x180005aca  sub     rsp, 128h
0x180005ad1  mov     rax, cs:__security_cookie
0x180005ad8  xor     rax, rsp
0x180005adb  mov     [rbp+60h+var_50], rax
0x180005adf  mov     r12, rcx
0x180005ae2  mov     [rsp+160h+var_120], r8
0x180005ae7  lea     rcx, [rbp+60h+var_B0]; this
0x180005aeb  mov     rsi, r9
0x180005aee  mov     r13, rdx
0x180005af1  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180005af6  lea     rcx, [rsp+160h+var_110]; this
0x180005afb  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180005b00  lea     rdx, [rsp+160h+var_110]; struct STBUFF *
0x180005b05  mov     rcx, r12; struct IHttpContext *
0x180005b08  call    ?PopulateXFFHeader@@YAJPEAVIHttpContext@@PEAVSTBUFF@@@Z; PopulateXFFHeader(IHttpContext *,STBUFF *)
0x180005b0d  xor     r14d, r14d
0x180005b10  mov     edi, eax
0x180005b12  test    eax, eax
0x180005b14  js      loc_180005CFA
0x180005b1a  mov     eax, [rsp+160h+var_100]
0x180005b1e  test    eax, eax
0x180005b20  jz      loc_180005CFA
0x180005b26  mov     rcx, [rsp+160h+Str]
0x180005b2b  mov     r15d, r14d
0x180005b2e  mov     [rax+rcx], r14b
0x180005b32  jmp     loc_180005BDF
0x180005b37  test    r15d, r15d
0x180005b3a  jnz     loc_180005CFF
0x180005b40  mov     eax, [rsp+160h+var_100]
0x180005b44  lea     edx, [r15+2Ch]; Ch
0x180005b48  mov     [rax+rcx], r14b
0x180005b4c  mov     ecx, [rsp+160h+var_100]
0x180005b50  mov     rax, [rsp+160h+Str]
0x180005b55  inc     ecx
0x180005b57  mov     [rcx+rax], r14b
0x180005b5b  mov     rcx, [rsp+160h+Str]; Str
0x180005b60  call    cs:__imp_strrchr
0x180005b66  mov     rbx, rax
0x180005b69  test    rax, rax
0x180005b6c  jnz     short loc_180005B97
0x180005b6e  mov     ecx, [rsp+160h+var_100]
0x180005b72  mov     r15d, 1
0x180005b78  mov     rax, [rsp+160h+Str]
0x180005b7d  mov     [rcx+rax], r14b
0x180005b81  mov     ecx, [rsp+160h+var_100]
0x180005b85  mov     rax, [rsp+160h+Str]
0x180005b8a  inc     ecx
0x180005b8c  mov     [rcx+rax], r14b
0x180005b90  mov     rbx, [rsp+160h+Str]
0x180005b95  jmp     short loc_180005B9D
0x180005b97  mov     [rax], r14b
0x180005b9a  inc     rbx
0x180005b9d  lea     rdx, [rbp+60h+var_B0]; this
0x180005ba1  mov     rcx, rbx; char *
0x180005ba4  call    ?IpToSockAddr@@YAJPEADPEAVSTBUFF@@@Z; IpToSockAddr(char *,STBUFF *)
0x180005ba9  mov     edi, eax
0x180005bab  test    eax, eax
0x180005bad  js      loc_180005CB8
0x180005bb3  mov     rcx, [r13+0C8h]; this
0x180005bba  mov     r14, [rbp+60h+hMem]
0x180005bbe  test    rcx, rcx
0x180005bc1  jz      short loc_180005C01
0x180005bc3  mov     rdx, r14; struct sockaddr *
0x180005bc6  call    ?QueryIpAllowed@ALLOW_LIST@@QEAAHPEAUsockaddr@@@Z; ALLOW_LIST::QueryIpAllowed(sockaddr *)
0x180005bcb  test    eax, eax
0x180005bcd  jz      short loc_180005C01
0x180005bcf  mov     ecx, [rsp+160h+var_100]
0x180005bd3  xor     r14d, r14d
0x180005bd6  mov     rax, [rsp+160h+Str]
0x180005bdb  mov     [rcx+rax], r14b
0x180005bdf  mov     ecx, [rsp+160h+var_100]
0x180005be3  mov     rax, [rsp+160h+Str]
0x180005be8  inc     ecx
0x180005bea  mov     [rcx+rax], r14b
0x180005bee  mov     rcx, [rsp+160h+Str]
0x180005bf3  test    rcx, rcx
0x180005bf6  jnz     loc_180005B37
0x180005bfc  jmp     loc_180005CFF
0x180005c01  cmp     word ptr [r14], 17h
0x180005c06  mov     eax, 4
0x180005c0b  mov     rcx, [rsp+160h+var_120]; this
0x180005c10  lea     edx, [rax+4]
0x180005c13  cmovnz  edx, eax
0x180005c16  lea     r8d, [rax+0Ch]
0x180005c1a  cmovnz  r8d, eax; unsigned int
0x180005c1e  add     rdx, r14; void *
0x180005c21  xor     r9d, r9d; unsigned int
0x180005c24  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x180005c29  xor     r14d, r14d
0x180005c2c  mov     edi, eax
0x180005c2e  test    eax, eax
0x180005c30  js      loc_180005CFA
0x180005c36  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005c3a  inc     r8; unsigned int
0x180005c3d  cmp     [rbx+r8], r14b
0x180005c41  jnz     short loc_180005C3A
0x180005c43  xor     r9d, r9d; unsigned int
0x180005c46  mov     rdx, rbx; void *
0x180005c49  mov     rcx, rsi; this
0x180005c4c  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x180005c51  mov     edi, eax
0x180005c53  test    eax, eax
0x180005c55  js      loc_180005CFA
0x180005c5b  test    byte ptr cs:g_dwDebugFlags, 3
0x180005c62  jz      loc_180005CFA
0x180005c68  mov     ecx, [rsi+10h]
0x180005c6b  lea     r9, aIpModuleGetxff; "IP_MODULE::GetXFFClientIp"
0x180005c72  mov     rax, [rsi+8]
0x180005c76  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005c7d  mov     r8d, 56Bh
0x180005c83  mov     [rcx+rax], r14b
0x180005c87  mov     ecx, [rsi+10h]
0x180005c8a  mov     rax, [rsi+8]
0x180005c8e  inc     ecx
0x180005c90  mov     [rcx+rax], r14b
0x180005c94  mov     rax, [rsi+8]
0x180005c98  mov     rcx, cs:g_pDebug
0x180005c9f  mov     [rsp+160h+var_138], rax
0x180005ca4  lea     rax, aUsingThisIpFor; "Using this IP for checks %s.\n"
0x180005cab  mov     [rsp+160h+var_140], rax
0x180005cb0  call    cs:__imp_PuDbgPrint
0x180005cb6  jmp     short loc_180005CFA
0x180005cb8  mov     rax, [r12]
0x180005cbc  mov     rcx, r12
0x180005cbf  mov     rax, [rax+20h]
0x180005cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cc8  mov     r10, rax
0x180005ccb  mov     [rsp+160h+var_130], r14d
0x180005cd0  mov     edx, 190h
0x180005cd5  mov     [rsp+160h+var_138], r14
0x180005cda  mov     r9d, 0Ah
0x180005ce0  mov     dword ptr [rsp+160h+var_140], edi
0x180005ce4  mov     rcx, [rax]
0x180005ce7  lea     r8, aBadRequest; "Bad Request"
0x180005cee  mov     rax, [rcx+18h]
0x180005cf2  mov     rcx, r10
0x180005cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cfa  mov     rcx, [rsp+160h+Str]; hMem
0x180005cff  lea     rax, [rsp+160h+var_F4]
0x180005d04  lea     rbx, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180005d0b  mov     [rsp+160h+var_110], rbx
0x180005d10  cmp     rcx, rax
0x180005d13  jz      short loc_180005D2D
0x180005d15  call    cs:__imp_LocalFree
0x180005d1b  lea     rax, [rsp+160h+var_F4]
0x180005d20  mov     [rsp+160h+var_FC], 40h ; '@'
0x180005d28  mov     [rsp+160h+Str], rax
0x180005d2d  mov     rcx, [rbp+60h+hMem]; hMem
0x180005d31  lea     rax, [rbp+60h+var_94]
0x180005d35  mov     [rbp+60h+var_B0], rbx
0x180005d39  mov     [rsp+160h+var_100], r14d
0x180005d3e  cmp     rcx, rax
0x180005d41  jz      short loc_180005D49
0x180005d43  call    cs:__imp_LocalFree
0x180005d49  mov     eax, edi
0x180005d4b  mov     rcx, [rbp+60h+var_50]
0x180005d4f  xor     rcx, rsp; StackCookie
0x180005d52  call    __security_check_cookie
0x180005d57  add     rsp, 128h
0x180005d5e  pop     r15
0x180005d60  pop     r14
0x180005d62  pop     r13
0x180005d64  pop     r12
0x180005d66  pop     rdi
0x180005d67  pop     rsi
0x180005d68  pop     rbx
0x180005d69  pop     rbp
0x180005d6a  retn
```
