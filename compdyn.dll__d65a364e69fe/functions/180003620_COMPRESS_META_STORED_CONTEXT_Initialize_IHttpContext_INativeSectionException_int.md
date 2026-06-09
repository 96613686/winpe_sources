# COMPRESS_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *,int)

- ea: `0x180003620`
- end: `0x18000383e`
- name: `?Initialize@COMPRESS_META_STORED_CONTEXT@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@H@Z`
- size: `542`
- prototype: `__int64 __fastcall(COMPRESS_META_STORED_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001a60`

## callees

- `0x180003620`
- `0x180003850`
- `0x180008010`

## string_xrefs

- `0x18000371b`: `doStaticCompression`
- `0x1800036ee`: `doDynamicCompression`
- `0x180003748`: `dynamicCompressionBeforeCache`
- `0x1800036b9`: `system.webServer/urlCompression`
- `0x18000379c`: `system.webServer/httpCompression`
- `0x18000586a`: `system.webServer/httpCompression`

## pseudocode

```c
__int64 __fastcall COMPRESS_META_STORED_CONTEXT::Initialize(
        COMPRESS_META_STORED_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct IHttpContext *); // rax
  __int64 (__fastcall ***v7)(_QWORD); // rax
  __int64 v8; // r12
  __int64 (__fastcall ***v9)(_QWORD, GUID *, _QWORD *); // rax
  int v10; // ebx
  __int64 v12; // [rsp+40h] [rbp-28h] BYREF
  __int64 v13; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v14[3]; // [rsp+50h] [rbp-18h] BYREF
  __int64 v15; // [rsp+B8h] [rbp+50h] BYREF

  v3 = *(_QWORD *)a2;
  v14[0] = 0;
  v12 = 0;
  v15 = 0;
  v6 = *(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160);
  v13 = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD))v6(a2);
  v8 = (**v7)(v7);
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  v10 = (**v9)(v9, &IID_INativeConfigurationSystem, v14);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v14[0] + 24LL))(
            v14[0],
            L"system.webServer/urlCompression",
            v8,
            &v12,
            a3,
            0);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v12 + 72LL))(
              v12,
              L"doDynamicCompression",
              (char *)this + 12,
              0,
              0);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v12 + 72LL))(
                v12,
                L"doStaticCompression",
                (char *)this + 8,
                0,
                0);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v12 + 72LL))(
                  v12,
                  L"dynamicCompressionBeforeCache",
                  (char *)this + 20,
                  0,
                  0);
          if ( v10 >= 0 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            v12 = 0;
            if ( !*((_DWORD *)this + 2) && !*((_DWORD *)this + 3) )
              goto LABEL_13;
            if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, __int64 *))(*(_QWORD *)v14[0] + 24LL))(
                   v14[0],
                   L"system.webServer/httpCompression",
                   v8,
                   &v15,
                   a3,
                   &v13) >= 0 )
              goto LABEL_32;
            if ( v13 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
              v13 = 0;
            }
            if ( *a3 )
            {
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
              *a3 = 0;
            }
            v10 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64 *, struct INativeSectionException **, __int64 *))(*(_QWORD *)v14[0] + 24LL))(
                    v14[0],
                    L"system.webServer/httpCompression",
                    L"MACHINE/WEBROOT/APPHOST",
                    &v15,
                    a3,
                    &v13);
            if ( v10 >= 0 )
            {
LABEL_32:
              if ( !*((_DWORD *)this + 2)
                || (v10 = InitializeMimeTypes(v15, L"staticTypes", (char *)this + 24, (char *)this + 40), v10 >= 0) )
              {
                if ( !*((_DWORD *)this + 3)
                  || (v10 = InitializeMimeTypes(v15, L"dynamicTypes", (char *)this + 48, (char *)this + 64), v10 >= 0) )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
                  v15 = 0;
LABEL_13:
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14[0] + 16LL))(v14[0]);
                  return 0;
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v14[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14[0] + 16LL))(v14[0]);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180003620  push    rbp
0x180003622  push    rbx
0x180003623  push    rsi
0x180003624  push    rdi
0x180003625  push    r12
0x180003627  push    r13
0x180003629  push    r14
0x18000362b  push    r15
0x18000362d  mov     rbp, rsp
0x180003630  sub     rsp, 68h
0x180003634  mov     rax, [rdx]
0x180003637  xor     r13d, r13d
0x18000363a  mov     rdi, rcx
0x18000363d  mov     [rbp+var_18], r13
0x180003641  mov     rcx, rdx
0x180003644  mov     [rbp+var_28], r13
0x180003648  mov     r15, r8
0x18000364b  mov     [rbp+arg_8], r13
0x18000364f  mov     rax, [rax+0A0h]
0x180003656  mov     [rbp+var_20], r13
0x18000365a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000365f  mov     rdx, rax
0x180003662  mov     rcx, [rax]
0x180003665  mov     rax, [rcx]
0x180003668  mov     rcx, rdx
0x18000366b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003670  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180003677  mov     r12, rax
0x18000367a  mov     rdx, [rcx]
0x18000367d  mov     rax, [rdx+38h]
0x180003681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003686  mov     r9, rax
0x180003689  lea     r8, [rbp+var_18]
0x18000368d  lea     rdx, IID_INativeConfigurationSystem
0x180003694  mov     rcx, [rax]
0x180003697  mov     rax, [rcx]
0x18000369a  mov     rcx, r9
0x18000369d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036a2  mov     ebx, eax
0x1800036a4  test    eax, eax
0x1800036a6  js      loc_180005887
0x1800036ac  mov     rcx, [rbp+var_18]
0x1800036b0  lea     r9, [rbp+var_28]
0x1800036b4  mov     [rsp+68h+var_40], r13
0x1800036b9  lea     rdx, aSystemWebserve; "system.webServer/urlCompression"
0x1800036c0  mov     r8, r12
0x1800036c3  mov     [rsp+68h+var_48], r15
0x1800036c8  mov     rax, [rcx]
0x1800036cb  mov     rax, [rax+18h]
0x1800036cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036d4  mov     ebx, eax
0x1800036d6  test    eax, eax
0x1800036d8  js      loc_180005887
0x1800036de  mov     rcx, [rbp+var_28]
0x1800036e2  lea     r8, [rdi+0Ch]
0x1800036e6  xor     r9d, r9d
0x1800036e9  mov     [rsp+68h+var_48], r13
0x1800036ee  lea     rdx, aDodynamiccompr; "doDynamicCompression"
0x1800036f5  mov     rax, [rcx]
0x1800036f8  mov     rax, [rax+48h]
0x1800036fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003701  mov     ebx, eax
0x180003703  test    eax, eax
0x180003705  js      loc_180005887
0x18000370b  mov     rcx, [rbp+var_28]
0x18000370f  lea     r8, [rdi+8]
0x180003713  xor     r9d, r9d
0x180003716  mov     [rsp+68h+var_48], r13
0x18000371b  lea     rdx, aDostaticcompre; "doStaticCompression"
0x180003722  mov     rax, [rcx]
0x180003725  mov     rax, [rax+48h]
0x180003729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000372e  mov     ebx, eax
0x180003730  test    eax, eax
0x180003732  js      loc_180005887
0x180003738  mov     rcx, [rbp+var_28]
0x18000373c  lea     r8, [rdi+14h]
0x180003740  xor     r9d, r9d
0x180003743  mov     [rsp+68h+var_48], r13
0x180003748  lea     rdx, aDynamiccompres_3; "dynamicCompressionBeforeCache"
0x18000374f  mov     rax, [rcx]
0x180003752  mov     rax, [rax+48h]
0x180003756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000375b  mov     ebx, eax
0x18000375d  test    eax, eax
0x18000375f  js      loc_180005887
0x180003765  mov     rcx, [rbp+var_28]
0x180003769  mov     rax, [rcx]
0x18000376c  mov     rax, [rax+10h]
0x180003770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003775  mov     [rbp+var_28], r13
0x180003779  cmp     [rdi+8], r13d
0x18000377d  jz      loc_18000580E
0x180003783  mov     rcx, [rbp+var_18]
0x180003787  lea     rdx, [rbp+var_20]
0x18000378b  mov     [rsp+68h+var_40], rdx
0x180003790  lea     r9, [rbp+arg_8]
0x180003794  mov     r8, r12
0x180003797  mov     [rsp+68h+var_48], r15
0x18000379c  lea     rdx, aSystemWebserve_0; "system.webServer/httpCompression"
0x1800037a3  mov     rax, [rcx]
0x1800037a6  mov     rax, [rax+18h]
0x1800037aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037af  test    eax, eax
0x1800037b1  js      loc_18000581D
0x1800037b7  cmp     [rdi+8], r13d
0x1800037bb  jz      short loc_1800037DF
0x1800037bd  mov     rcx, [rbp+arg_8]
0x1800037c1  lea     r9, [rdi+28h]
0x1800037c5  lea     r8, [rdi+18h]
0x1800037c9  lea     rdx, aStatictypes; "staticTypes"
0x1800037d0  call    InitializeMimeTypes
0x1800037d5  mov     ebx, eax
0x1800037d7  test    eax, eax
0x1800037d9  js      loc_180005887
0x1800037df  cmp     [rdi+0Ch], r13d
0x1800037e3  jz      short loc_180003807
0x1800037e5  mov     rcx, [rbp+arg_8]
0x1800037e9  lea     r9, [rdi+40h]
0x1800037ed  lea     r8, [rdi+30h]
0x1800037f1  lea     rdx, aDynamictypes; "dynamicTypes"
0x1800037f8  call    InitializeMimeTypes
0x1800037fd  mov     ebx, eax
0x1800037ff  test    eax, eax
0x180003801  js      loc_180005887
0x180003807  mov     rcx, [rbp+arg_8]
0x18000380b  mov     rax, [rcx]
0x18000380e  mov     rax, [rax+10h]
0x180003812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003817  mov     [rbp+arg_8], r13
0x18000381b  mov     rcx, [rbp+var_18]
0x18000381f  mov     rax, [rcx]
0x180003822  mov     rax, [rax+10h]
0x180003826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000382b  xor     eax, eax
0x18000382d  add     rsp, 68h
0x180003831  pop     r15
0x180003833  pop     r14
0x180003835  pop     r13
0x180003837  pop     r12
0x180003839  pop     rdi
0x18000383a  pop     rsi
0x18000383b  pop     rbx
0x18000383c  pop     rbp
0x18000383d  retn
0x18000580e  cmp     [rdi+0Ch], r13d
0x180005812  jz      loc_18000381B
0x180005818  jmp     loc_180003783
0x18000581d  mov     rcx, [rbp+var_20]
0x180005821  test    rcx, rcx
0x180005824  jz      short loc_180005836
0x180005826  mov     rax, [rcx]
0x180005829  mov     rax, [rax+10h]
0x18000582d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005832  mov     [rbp+var_20], r13
0x180005836  mov     rcx, [r15]
0x180005839  test    rcx, rcx
0x18000583c  jz      short loc_18000584D
0x18000583e  mov     rax, [rcx]
0x180005841  mov     rax, [rax+10h]
0x180005845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000584a  mov     [r15], r13
0x18000584d  mov     rcx, [rbp+var_18]
0x180005851  lea     r8, [rbp+var_20]
0x180005855  mov     [rsp+68h+var_40], r8
0x18000585a  lea     r9, [rbp+arg_8]
0x18000585e  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180005865  mov     [rsp+68h+var_48], r15
0x18000586a  lea     rdx, aSystemWebserve_0; "system.webServer/httpCompression"
0x180005871  mov     rax, [rcx]
0x180005874  mov     rax, [rax+18h]
0x180005878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000587d  mov     ebx, eax
0x18000587f  test    eax, eax
0x180005881  jns     loc_1800037B7
0x180005887  mov     rcx, [rbp+var_20]
0x18000588b  test    rcx, rcx
0x18000588e  jz      short loc_1800058A0
0x180005890  mov     rax, [rcx]
0x180005893  mov     rax, [rax+10h]
0x180005897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000589c  mov     [rbp+var_20], r13
0x1800058a0  mov     rcx, [rbp+arg_8]
0x1800058a4  test    rcx, rcx
0x1800058a7  jz      short loc_1800058B9
0x1800058a9  mov     rax, [rcx]
0x1800058ac  mov     rax, [rax+10h]
0x1800058b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058b5  mov     [rbp+arg_8], r13
0x1800058b9  mov     rcx, [rbp+var_28]
0x1800058bd  test    rcx, rcx
0x1800058c0  jz      short loc_1800058D2
0x1800058c2  mov     rax, [rcx]
0x1800058c5  mov     rax, [rax+10h]
0x1800058c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058ce  mov     [rbp+var_28], r13
0x1800058d2  mov     rcx, [rbp+var_18]
0x1800058d6  test    rcx, rcx
0x1800058d9  jz      short loc_1800058E7
0x1800058db  mov     rax, [rcx]
0x1800058de  mov     rax, [rax+10h]
0x1800058e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058e7  mov     eax, ebx
0x1800058e9  jmp     loc_18000382D
```
