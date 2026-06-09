# FREB_SITE_META_STORED_CONTEXT::Initialize(ulong,INativeSectionException * *)

- ea: `0x180006ce0`
- end: `0x180006f90`
- name: `?Initialize@FREB_SITE_META_STORED_CONTEXT@@AEAAJKPEAPEAVINativeSectionException@@@Z`
- size: `688`
- prototype: `__int64 __fastcall(FREB_SITE_META_STORED_CONTEXT *__hidden this, unsigned int, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180006aec`

## callees

- `0x180006ce0`
- `0x180007518`
- `0x18000b010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006dd0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006dd0`

## string_xrefs

- `0x180006e42`: `directory`

## pseudocode

```c
__int64 __fastcall FREB_SITE_META_STORED_CONTEXT::Initialize(
        FREB_SITE_META_STORED_CONTEXT *this,
        unsigned int a2,
        struct INativeSectionException **a3)
{
  struct IHttpServer *v4; // rcx
  __int64 v7; // rax
  __int64 (__fastcall *v8)(struct IHttpServer *); // rax
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rax
  int v10; // ebx
  __int64 v12; // [rsp+30h] [rbp-20h] BYREF
  __int64 v13; // [rsp+38h] [rbp-18h] BYREF
  const unsigned __int16 *v14; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v15; // [rsp+48h] [rbp-8h] BYREF
  __int64 v16; // [rsp+90h] [rbp+40h] BYREF
  __int64 v17; // [rsp+98h] [rbp+48h] BYREF

  v4 = g_pGlobalInfo;
  *a3 = 0;
  v13 = 0;
  v12 = 0;
  v7 = *(_QWORD *)v4;
  v16 = 0;
  v17 = 0;
  v14 = 0;
  v8 = *(__int64 (__fastcall **)(struct IHttpServer *))(v7 + 56);
  v15 = 0;
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v8(v4);
  v10 = (**v9)(v9, &IID_INativeConfigurationSystem, &v13);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 56LL))(v13, &v12);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, struct INativeSectionException **))(*(_QWORD *)v12 + 32LL))(
              v12,
              a2,
              &v17,
              a3);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
                v17,
                L"name",
                &v14,
                0,
                0);
        if ( v10 >= 0 )
        {
          v10 = STRU::Copy((FREB_SITE_META_STORED_CONTEXT *)((char *)this + 88), v14);
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v17 + 32LL))(
                    v17,
                    L"traceFailedRequestsLogging",
                    &v16);
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v16 + 72LL))(
                      v16,
                      L"enabled",
                      (char *)this + 12,
                      0,
                      0);
              if ( v10 >= 0 )
              {
                v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v16 + 64LL))(
                        v16,
                        L"directory",
                        &v15,
                        0,
                        0);
                if ( v10 >= 0 )
                {
                  if ( v15 )
                  {
                    v10 = FREB_SITE_META_STORED_CONTEXT::SetDirectory(this, v15, a2);
                    if ( v10 < 0 )
                      goto LABEL_17;
                  }
                  else
                  {
                    *((_DWORD *)this + 3) = 0;
                  }
                  v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v16 + 48LL))(
                          v16,
                          L"maxLogFiles",
                          (char *)this + 72,
                          0,
                          0);
                  if ( v10 >= 0 )
                  {
                    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v16 + 72LL))(
                            v16,
                            L"customActionsEnabled",
                            (char *)this + 76,
                            0,
                            0);
                    if ( v10 >= 0 )
                    {
                      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v16 + 48LL))(
                              v16,
                              L"maxLogFileSizeKB",
                              (char *)this + 80,
                              0,
                              0);
                      if ( v10 >= 0 )
                      {
                        *((_DWORD *)this + 20) <<= 10;
                        *((_DWORD *)this + 190) = *((_DWORD *)this + 18);
                        *((_DWORD *)this + 21) = a2;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_17:
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180006ce0  mov     [rsp-28h+arg_0], rbx
0x180006ce5  mov     [rsp-28h+arg_8], rsi
0x180006cea  push    rbp
0x180006ceb  push    rdi
0x180006cec  push    r12
0x180006cee  push    r14
0x180006cf0  push    r15
0x180006cf2  mov     rbp, rsp
0x180006cf5  sub     rsp, 50h
0x180006cf9  xor     r12d, r12d
0x180006cfc  mov     rdi, rcx
0x180006cff  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180006d06  mov     rsi, r8
0x180006d09  mov     [r8], r12
0x180006d0c  mov     r15d, edx
0x180006d0f  mov     [rbp+var_18], r12
0x180006d13  mov     [rbp+var_20], r12
0x180006d17  mov     rax, [rcx]
0x180006d1a  mov     [rbp+arg_10], r12
0x180006d1e  mov     [rbp+arg_18], r12
0x180006d22  mov     [rbp+var_10], r12
0x180006d26  mov     rax, [rax+38h]
0x180006d2a  mov     [rbp+var_8], r12
0x180006d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d33  mov     r9, rax
0x180006d36  lea     r8, [rbp+var_18]
0x180006d3a  lea     rdx, IID_INativeConfigurationSystem
0x180006d41  mov     rcx, [rax]
0x180006d44  mov     rax, [rcx]
0x180006d47  mov     rcx, r9
0x180006d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d4f  mov     ebx, eax
0x180006d51  test    eax, eax
0x180006d53  js      loc_180006F15
0x180006d59  mov     rcx, [rbp+var_18]
0x180006d5d  lea     rdx, [rbp+var_20]
0x180006d61  mov     rax, [rcx]
0x180006d64  mov     rax, [rax+38h]
0x180006d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d6d  mov     ebx, eax
0x180006d6f  test    eax, eax
0x180006d71  js      loc_180006F15
0x180006d77  mov     rcx, [rbp+var_20]
0x180006d7b  lea     r8, [rbp+arg_18]
0x180006d7f  mov     r9, rsi
0x180006d82  mov     edx, r15d
0x180006d85  mov     rax, [rcx]
0x180006d88  mov     rax, [rax+20h]
0x180006d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d91  mov     ebx, eax
0x180006d93  test    eax, eax
0x180006d95  js      loc_180006F15
0x180006d9b  mov     rcx, [rbp+arg_18]
0x180006d9f  lea     r8, [rbp+var_10]
0x180006da3  xor     r9d, r9d
0x180006da6  mov     [rsp+50h+var_30], r12
0x180006dab  lea     rdx, aName; "name"
0x180006db2  mov     rax, [rcx]
0x180006db5  mov     rax, [rax+40h]
0x180006db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dbe  mov     ebx, eax
0x180006dc0  test    eax, eax
0x180006dc2  js      loc_180006F15
0x180006dc8  mov     rdx, [rbp+var_10]
0x180006dcc  lea     rcx, [rdi+58h]
0x180006dd0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180006dd6  mov     ebx, eax
0x180006dd8  test    eax, eax
0x180006dda  js      loc_180006F15
0x180006de0  mov     rcx, [rbp+arg_18]
0x180006de4  lea     r8, [rbp+arg_10]
0x180006de8  lea     rdx, aTracefailedreq; "traceFailedRequestsLogging"
0x180006def  mov     rax, [rcx]
0x180006df2  mov     rax, [rax+20h]
0x180006df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dfb  mov     ebx, eax
0x180006dfd  test    eax, eax
0x180006dff  js      loc_180006F15
0x180006e05  mov     rcx, [rbp+arg_10]
0x180006e09  lea     r8, [rdi+0Ch]
0x180006e0d  xor     r9d, r9d
0x180006e10  mov     [rsp+50h+var_30], r12
0x180006e15  lea     rdx, aEnabled; "enabled"
0x180006e1c  mov     rax, [rcx]
0x180006e1f  mov     rax, [rax+48h]
0x180006e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e28  mov     ebx, eax
0x180006e2a  test    eax, eax
0x180006e2c  js      loc_180006F15
0x180006e32  mov     rcx, [rbp+arg_10]
0x180006e36  lea     r8, [rbp+var_8]
0x180006e3a  xor     r9d, r9d
0x180006e3d  mov     [rsp+50h+var_30], r12
0x180006e42  lea     rdx, aDirectory; "directory"
0x180006e49  mov     rax, [rcx]
0x180006e4c  mov     rax, [rax+40h]
0x180006e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e55  mov     ebx, eax
0x180006e57  test    eax, eax
0x180006e59  js      loc_180006F15
0x180006e5f  mov     rdx, [rbp+var_8]; unsigned __int16 *
0x180006e63  test    rdx, rdx
0x180006e66  jz      short loc_180006E7F
0x180006e68  mov     r8d, r15d; unsigned int
0x180006e6b  mov     rcx, rdi; this
0x180006e6e  call    ?SetDirectory@FREB_SITE_META_STORED_CONTEXT@@QEAAJPEBGK@Z; FREB_SITE_META_STORED_CONTEXT::SetDirectory(ushort const *,ulong)
0x180006e73  mov     ebx, eax
0x180006e75  test    eax, eax
0x180006e77  js      loc_180006F15
0x180006e7d  jmp     short loc_180006E83
0x180006e7f  mov     [rdi+0Ch], r12d
0x180006e83  mov     rcx, [rbp+arg_10]
0x180006e87  lea     r8, [rdi+48h]
0x180006e8b  xor     r9d, r9d
0x180006e8e  mov     [rsp+50h+var_30], r12
0x180006e93  lea     rdx, aMaxlogfiles; "maxLogFiles"
0x180006e9a  mov     rax, [rcx]
0x180006e9d  mov     rax, [rax+30h]
0x180006ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea6  mov     ebx, eax
0x180006ea8  test    eax, eax
0x180006eaa  js      short loc_180006F15
0x180006eac  mov     rcx, [rbp+arg_10]
0x180006eb0  lea     r8, [rdi+4Ch]
0x180006eb4  xor     r9d, r9d
0x180006eb7  mov     [rsp+50h+var_30], r12
0x180006ebc  lea     rdx, aCustomactionse; "customActionsEnabled"
0x180006ec3  mov     rax, [rcx]
0x180006ec6  mov     rax, [rax+48h]
0x180006eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ecf  mov     ebx, eax
0x180006ed1  test    eax, eax
0x180006ed3  js      short loc_180006F15
0x180006ed5  mov     rcx, [rbp+arg_10]
0x180006ed9  lea     rsi, [rdi+50h]
0x180006edd  xor     r9d, r9d
0x180006ee0  mov     [rsp+50h+var_30], r12
0x180006ee5  mov     r8, rsi
0x180006ee8  lea     rdx, aMaxlogfilesize; "maxLogFileSizeKB"
0x180006eef  mov     rax, [rcx]
0x180006ef2  mov     rax, [rax+30h]
0x180006ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006efb  mov     ebx, eax
0x180006efd  test    eax, eax
0x180006eff  js      short loc_180006F15
0x180006f01  mov     eax, [rsi]
0x180006f03  shl     eax, 0Ah
0x180006f06  mov     [rsi], eax
0x180006f08  mov     eax, [rdi+48h]
0x180006f0b  mov     [rdi+2F8h], eax
0x180006f11  mov     [rdi+54h], r15d
0x180006f15  mov     rcx, [rbp+arg_10]
0x180006f19  test    rcx, rcx
0x180006f1c  jz      short loc_180006F2E
0x180006f1e  mov     rax, [rcx]
0x180006f21  mov     rax, [rax+10h]
0x180006f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f2a  mov     [rbp+arg_10], r12
0x180006f2e  mov     rcx, [rbp+arg_18]
0x180006f32  test    rcx, rcx
0x180006f35  jz      short loc_180006F47
0x180006f37  mov     rax, [rcx]
0x180006f3a  mov     rax, [rax+10h]
0x180006f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f43  mov     [rbp+arg_18], r12
0x180006f47  mov     rcx, [rbp+var_20]
0x180006f4b  test    rcx, rcx
0x180006f4e  jz      short loc_180006F60
0x180006f50  mov     rax, [rcx]
0x180006f53  mov     rax, [rax+10h]
0x180006f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f5c  mov     [rbp+var_20], r12
0x180006f60  mov     rcx, [rbp+var_18]
0x180006f64  test    rcx, rcx
0x180006f67  jz      short loc_180006F75
0x180006f69  mov     rax, [rcx]
0x180006f6c  mov     rax, [rax+10h]
0x180006f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f75  lea     r11, [rsp+50h+var_s0]
0x180006f7a  mov     eax, ebx
0x180006f7c  mov     rbx, [r11+30h]
0x180006f80  mov     rsi, [r11+38h]
0x180006f84  mov     rsp, r11
0x180006f87  pop     r15
0x180006f89  pop     r14
0x180006f8b  pop     r12
0x180006f8d  pop     rdi
0x180006f8e  pop     rbp
0x180006f8f  retn
```
