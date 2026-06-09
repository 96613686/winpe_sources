# DoSendResponseStatusAndHeaders(IHttpContext *,IHttpCompletionInfo *,IHttpEventProvider *)

- ea: `0x180002ab0`
- end: `0x180002eae`
- name: `?DoSendResponseStatusAndHeaders@@YA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpCompletionInfo@@PEAVIHttpEventProvider@@@Z`
- size: `1022`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001020`
- `0x180002aa0`

## callees

- `0x180002ab0`
- `0x180002ec0`
- `0x180003080`
- `0x180005520`
- `0x180005860`
- `0x180008010`

## import_xrefs

- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002b7d`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002b87`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002bae`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002bbb`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002bc8`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002bd5`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002be2`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002b7d`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002b87`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002bae`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002bbb`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002bc8`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002bd5`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180002be2`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x180002b94`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x180002ba1`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x180002b94`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x180002ba1`
- `iisutil!PuDbgPrint` at `0x180002d20`
- `iisutil!PuDbgPrint` at `0x180002d20`

## string_xrefs

- `0x180002d19`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\requestfiltering.cxx`
- `0x180002cfc`: `Failed to create config object - error 0x%08x.\n`

## pseudocode

```c
__int64 __fastcall DoSendResponseStatusAndHeaders(struct IHttpContext *a1)
{
  struct RFLT_URL_STATE *v2; // rbp
  int v3; // eax
  __int64 v4; // rax
  __int64 v5; // r14
  _QWORD *v6; // rbx
  int v7; // esi
  __int64 v8; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rax
  struct RFLT_URL_STATE *v15; // [rsp+40h] [rbp-38h] BYREF
  struct INativeSectionException *v16; // [rsp+88h] [rbp+10h] BYREF
  __int64 v17; // [rsp+90h] [rbp+18h] BYREF
  unsigned __int16 *v18; // [rsp+98h] [rbp+20h] BYREF

  v15 = 0;
  v18 = 0;
  v16 = 0;
  v17 = 0;
  if ( (int)RFLT_URL_STATE::GetUrlState(a1, &v15) < 0 )
    return 0;
  v2 = v15;
  v3 = *((_DWORD *)v15 + 4);
  if ( v3 == -1 )
  {
    v4 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 160LL))(a1);
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4);
    v6 = (_QWORD *)(**(__int64 (__fastcall ***)(__int64, void *))v5)(v5, g_pModuleContext);
    if ( !v6 )
    {
      v6 = operator new(0x250u);
      if ( !v6 )
      {
        v7 = -2147024888;
        goto LABEL_14;
      }
      *v6 = &REQUEST_FILTER_CONFIG::`vftable';
      MULTISZ::MULTISZ((MULTISZ *)(v6 + 7));
      MULTISZ::MULTISZ((MULTISZ *)(v6 + 14));
      MULTISZA::MULTISZA((MULTISZA *)(v6 + 21));
      MULTISZA::MULTISZA((MULTISZA *)(v6 + 28));
      MULTISZ::MULTISZ((MULTISZ *)(v6 + 35));
      MULTISZ::MULTISZ((MULTISZ *)(v6 + 42));
      MULTISZ::MULTISZ((MULTISZ *)(v6 + 49));
      MULTISZ::MULTISZ((MULTISZ *)(v6 + 56));
      MULTISZ::MULTISZ((MULTISZ *)(v6 + 63));
      v6[70] = 0;
      *((_DWORD *)v6 + 142) = 0;
      v6[72] = 0;
      *((_DWORD *)v6 + 146) = 0;
      REQUEST_FILTER_CONFIG::Reset((REQUEST_FILTER_CONFIG *)v6);
      v7 = REQUEST_FILTER_CONFIG::Create((REQUEST_FILTER_CONFIG *)v6, a1, &v16, (const unsigned __int16 **)&v18);
      if ( v7 < 0 )
      {
        (*(void (__fastcall **)(_QWORD *))*v6)(v6);
LABEL_14:
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\requestfiltering.cxx",
            754,
            "DoSendResponseStatusAndHeaders",
            "Failed to create config object - error 0x%08x.\r\n",
            v7);
        if ( v16 )
        {
          (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v16)(
            v16,
            &IID_IAppHostConfigException,
            &v17);
          v10 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
          (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v10 + 24LL))(
            v10,
            500,
            "Internal Server Error",
            19,
            v7,
            v17,
            0);
          if ( v17 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            v17 = 0;
          }
          (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v16 + 16LL))(v16);
        }
        else
        {
          v11 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
          (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v11 + 24LL))(
            v11,
            500,
            "Internal Server Error",
            0,
            v7,
            0,
            0);
          if ( v18 )
          {
            v12 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
            v13 = -1;
            do
              ++v13;
            while ( v18[v13] );
            (*(void (__fastcall **)(__int64, unsigned __int16 *, __int64, __int64))(*(_QWORD *)v12 + 192LL))(
              v12,
              v18,
              v13,
              1);
          }
        }
        return 0;
      }
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD *, void *))(*(_QWORD *)v5 + 8LL))(v5, v6, g_pModuleContext);
      if ( v7 < 0 )
      {
        (*(void (__fastcall **)(_QWORD *))*v6)(v6);
        if ( v7 != -2147024811 )
          goto LABEL_14;
        v6 = (_QWORD *)(**(__int64 (__fastcall ***)(__int64, void *))v5)(v5, g_pModuleContext);
      }
    }
    if ( *((_DWORD *)v6 + 4) )
    {
      *((_DWORD *)v2 + 4) = 1;
      v8 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
      (*(void (__fastcall **)(__int64, const char *))(*(_QWORD *)v8 + 56LL))(v8, "Server");
    }
    else
    {
      *((_DWORD *)v2 + 4) = 0;
    }
    return 0;
  }
  if ( v3 != 1 )
    return 0;
  v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
  (*(void (__fastcall **)(__int64, const char *))(*(_QWORD *)v14 + 56LL))(v14, "Server");
  return 0;
}

```

## disassembly

```asm
0x180002ab0  mov     rax, rsp
0x180002ab3  mov     [rax+18h], r8
0x180002ab7  mov     [rax+10h], rdx
0x180002abb  push    rdi
0x180002abc  push    r15
0x180002abe  sub     rsp, 68h
0x180002ac2  xor     r15d, r15d
0x180002ac5  lea     rdx, [rax-38h]; struct RFLT_URL_STATE **
0x180002ac9  mov     [rax-38h], r15
0x180002acd  mov     rdi, rcx
0x180002ad0  mov     [rax+20h], r15
0x180002ad4  mov     [rax+10h], r15
0x180002ad8  mov     [rax+18h], r15
0x180002adc  call    ?GetUrlState@RFLT_URL_STATE@@SAJPEAVIHttpContext@@PEAPEAV1@@Z; RFLT_URL_STATE::GetUrlState(IHttpContext *,RFLT_URL_STATE * *)
0x180002ae1  test    eax, eax
0x180002ae3  js      loc_180002CDD
0x180002ae9  mov     [rsp+78h+var_18], rbp
0x180002aee  mov     rbp, [rsp+78h+var_38]
0x180002af3  mov     eax, [rbp+10h]
0x180002af6  cmp     eax, 0FFFFFFFFh
0x180002af9  jnz     loc_180002E6E
0x180002aff  mov     rax, [rdi]
0x180002b02  mov     rcx, rdi
0x180002b05  mov     [rsp+78h+arg_0], rbx
0x180002b0d  mov     [rsp+78h+var_28], r14
0x180002b12  mov     [rsp+78h+var_20], rsi
0x180002b17  mov     rax, [rax+0A0h]
0x180002b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b23  mov     rdx, rax
0x180002b26  mov     rcx, [rax]
0x180002b29  mov     rax, [rcx+18h]
0x180002b2d  mov     rcx, rdx
0x180002b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b35  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x180002b3c  mov     r14, rax
0x180002b3f  mov     rcx, [rax]
0x180002b42  mov     rax, [rcx]
0x180002b45  mov     rcx, r14
0x180002b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b4d  mov     rbx, rax
0x180002b50  test    rax, rax
0x180002b53  jnz     loc_180002C8D
0x180002b59  mov     ecx, 250h; Size
0x180002b5e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002b63  mov     rbx, rax
0x180002b66  test    rax, rax
0x180002b69  jz      loc_180002CE7
0x180002b6f  lea     rax, ??_7REQUEST_FILTER_CONFIG@@6B@; const REQUEST_FILTER_CONFIG::`vftable'
0x180002b76  lea     rcx, [rbx+38h]
0x180002b7a  mov     [rbx], rax
0x180002b7d  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180002b83  lea     rcx, [rbx+70h]
0x180002b87  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180002b8d  lea     rcx, [rbx+0A8h]
0x180002b94  call    cs:__imp_??0MULTISZA@@QEAA@XZ; MULTISZA::MULTISZA(void)
0x180002b9a  lea     rcx, [rbx+0E0h]
0x180002ba1  call    cs:__imp_??0MULTISZA@@QEAA@XZ; MULTISZA::MULTISZA(void)
0x180002ba7  lea     rcx, [rbx+118h]
0x180002bae  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180002bb4  lea     rcx, [rbx+150h]
0x180002bbb  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180002bc1  lea     rcx, [rbx+188h]
0x180002bc8  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180002bce  lea     rcx, [rbx+1C0h]
0x180002bd5  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180002bdb  lea     rcx, [rbx+1F8h]
0x180002be2  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180002be8  mov     rcx, rbx; this
0x180002beb  mov     [rbx+230h], r15
0x180002bf2  mov     [rbx+238h], r15d
0x180002bf9  mov     [rbx+240h], r15
0x180002c00  mov     [rbx+248h], r15d
0x180002c07  call    ?Reset@REQUEST_FILTER_CONFIG@@AEAAXXZ; REQUEST_FILTER_CONFIG::Reset(void)
0x180002c0c  lea     r9, [rsp+78h+arg_18]; unsigned __int16 **
0x180002c14  mov     rdx, rdi; struct IHttpContext *
0x180002c17  lea     r8, [rsp+78h+arg_8]; struct INativeSectionException **
0x180002c1f  mov     rcx, rbx; this
0x180002c22  call    ?Create@REQUEST_FILTER_CONFIG@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@PEAPEBG@Z; REQUEST_FILTER_CONFIG::Create(IHttpContext *,INativeSectionException * *,ushort const * *)
0x180002c27  mov     esi, eax
0x180002c29  test    eax, eax
0x180002c2b  jns     short loc_180002C40
0x180002c2d  mov     rcx, [rbx]
0x180002c30  mov     rax, [rcx]
0x180002c33  mov     rcx, rbx
0x180002c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c3b  jmp     loc_180002CEC
0x180002c40  mov     rax, [r14]
0x180002c43  mov     rdx, rbx
0x180002c46  mov     r8, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x180002c4d  mov     rcx, r14
0x180002c50  mov     rax, [rax+8]
0x180002c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c59  mov     esi, eax
0x180002c5b  test    eax, eax
0x180002c5d  jns     short loc_180002C8D
0x180002c5f  mov     rax, [rbx]
0x180002c62  mov     rcx, rbx
0x180002c65  mov     rax, [rax]
0x180002c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c6d  cmp     esi, 80070055h
0x180002c73  jnz     short loc_180002CEC
0x180002c75  mov     rax, [r14]
0x180002c78  mov     rcx, r14
0x180002c7b  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x180002c82  mov     rax, [rax]
0x180002c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c8a  mov     rbx, rax
0x180002c8d  cmp     [rbx+10h], r15d
0x180002c91  jz      loc_180002E65
0x180002c97  mov     dword ptr [rbp+10h], 1
0x180002c9e  mov     rcx, rdi
0x180002ca1  mov     rax, [rdi]
0x180002ca4  mov     rax, [rax+20h]
0x180002ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cad  mov     r8, rax
0x180002cb0  lea     rdx, aServer; "Server"
0x180002cb7  mov     rcx, [rax]
0x180002cba  mov     rax, [rcx+38h]
0x180002cbe  mov     rcx, r8
0x180002cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc6  mov     rsi, [rsp+78h+var_20]
0x180002ccb  mov     rbx, [rsp+78h+arg_0]
0x180002cd3  mov     r14, [rsp+78h+var_28]
0x180002cd8  mov     rbp, [rsp+78h+var_18]
0x180002cdd  xor     eax, eax
0x180002cdf  add     rsp, 68h
0x180002ce3  pop     r15
0x180002ce5  pop     rdi
0x180002ce6  retn
0x180002ce7  mov     esi, 80070008h
0x180002cec  test    byte ptr cs:g_dwDebugFlags, 3
0x180002cf3  jz      short loc_180002D26
0x180002cf5  mov     rcx, cs:g_pDebug
0x180002cfc  lea     rax, aFailedToCreate; "Failed to create config object - error "...
0x180002d03  mov     dword ptr [rsp+78h+var_50], esi
0x180002d07  lea     r9, aDosendresponse; "DoSendResponseStatusAndHeaders"
0x180002d0e  mov     r8d, 2F2h
0x180002d14  mov     [rsp+78h+var_58], rax
0x180002d19  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180002d20  call    cs:__imp_PuDbgPrint
0x180002d26  mov     rcx, [rsp+78h+arg_8]
0x180002d2e  test    rcx, rcx
0x180002d31  jz      loc_180002DD4
0x180002d37  mov     rax, [rcx]
0x180002d3a  lea     r8, [rsp+78h+arg_10]
0x180002d42  lea     rdx, IID_IAppHostConfigException
0x180002d49  mov     rax, [rax]
0x180002d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d51  mov     rax, [rdi]
0x180002d54  mov     rcx, rdi
0x180002d57  mov     rax, [rax+20h]
0x180002d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d60  mov     r10, rax
0x180002d63  mov     [rsp+78h+var_48], r15d
0x180002d68  mov     edx, 1F4h
0x180002d6d  lea     r8, aInternalServer; "Internal Server Error"
0x180002d74  mov     r9d, 13h
0x180002d7a  mov     rcx, [rax]
0x180002d7d  mov     rax, [rcx+18h]
0x180002d81  mov     rcx, [rsp+78h+arg_10]
0x180002d89  mov     [rsp+78h+var_50], rcx
0x180002d8e  mov     rcx, r10
0x180002d91  mov     dword ptr [rsp+78h+var_58], esi
0x180002d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d9a  mov     rcx, [rsp+78h+arg_10]
0x180002da2  test    rcx, rcx
0x180002da5  jz      short loc_180002DBB
0x180002da7  mov     rax, [rcx]
0x180002daa  mov     rax, [rax+10h]
0x180002dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002db3  mov     [rsp+78h+arg_10], r15
0x180002dbb  mov     rcx, [rsp+78h+arg_8]
0x180002dc3  mov     rax, [rcx]
0x180002dc6  mov     rax, [rax+10h]
0x180002dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dcf  jmp     loc_180002CC6
0x180002dd4  mov     rax, [rdi]
0x180002dd7  mov     rcx, rdi
0x180002dda  mov     rax, [rax+20h]
0x180002dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de3  mov     r10, rax
0x180002de6  mov     [rsp+78h+var_48], r15d
0x180002deb  xor     r9d, r9d
0x180002dee  mov     [rsp+78h+var_50], r15
0x180002df3  mov     edx, 1F4h
0x180002df8  mov     dword ptr [rsp+78h+var_58], esi
0x180002dfc  mov     rcx, [rax]
0x180002dff  lea     r8, aInternalServer; "Internal Server Error"
0x180002e06  mov     rax, [rcx+18h]
0x180002e0a  mov     rcx, r10
0x180002e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e12  cmp     [rsp+78h+arg_18], r15
0x180002e1a  jz      loc_180002CC6
0x180002e20  mov     rax, [rdi]
0x180002e23  mov     rcx, rdi
0x180002e26  mov     rax, [rax+20h]
0x180002e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e2f  mov     rdx, [rsp+78h+arg_18]
0x180002e37  mov     rcx, rax
0x180002e3a  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180002e41  inc     r8
0x180002e44  cmp     [rdx+r8*2], r15w
0x180002e49  jnz     short loc_180002E41
0x180002e4b  mov     rax, [rax]
0x180002e4e  mov     r9d, 1
0x180002e54  mov     rax, [rax+0C0h]
0x180002e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e60  jmp     loc_180002CC6
0x180002e65  mov     [rbp+10h], r15d
0x180002e69  jmp     loc_180002CC6
0x180002e6e  cmp     eax, 1
0x180002e71  jnz     loc_180002CD8
0x180002e77  mov     rax, [rdi]
0x180002e7a  mov     rcx, rdi
0x180002e7d  mov     rax, [rax+20h]
0x180002e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e86  mov     r8, rax
0x180002e89  lea     rdx, aServer; "Server"
0x180002e90  mov     rcx, [rax]
0x180002e93  mov     rax, [rcx+38h]
0x180002e97  mov     rcx, r8
0x180002e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e9f  mov     rbp, [rsp+78h+var_18]
0x180002ea4  xor     eax, eax
0x180002ea6  add     rsp, 68h
0x180002eaa  pop     r15
0x180002eac  pop     rdi
0x180002ead  retn
```
