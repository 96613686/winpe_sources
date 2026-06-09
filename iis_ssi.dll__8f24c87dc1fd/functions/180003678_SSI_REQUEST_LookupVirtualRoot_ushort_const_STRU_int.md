# SSI_REQUEST::LookupVirtualRoot(ushort const *,STRU *,int)

- ea: `0x180003678`
- end: `0x180003955`
- name: `?LookupVirtualRoot@SSI_REQUEST@@QEAAJPEBGPEAVSTRU@@H@Z`
- size: `733`
- prototype: `__int64 __fastcall(SSI_REQUEST *__hidden this, const unsigned __int16 *, struct STRU *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000474c`

## callees

- `0x180003678`
- `0x18000574a`
- `0x180005780`
- `0x180006010`

## import_xrefs

- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003757`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003757`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003714`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003714`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800037a2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800037ba`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800037a2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800037ba`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003927`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003927`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800036d0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800036d0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003769`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003769`

## string_xrefs

- `0x18000388d`: `accessPolicy`

## pseudocode

```c
__int64 __fastcall SSI_REQUEST::LookupVirtualRoot(
        SSI_REQUEST *this,
        const unsigned __int16 *a2,
        struct STRU *a3,
        int a4)
{
  __int64 v8; // rcx
  __int64 v9; // r8
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rax
  const unsigned __int16 *v15; // rax
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // rax
  __int64 v17; // rax
  unsigned int v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v23[32]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h]
  unsigned __int16 v25[256]; // [rsp+90h] [rbp-70h] BYREF

  memset_0(v25, 0, sizeof(v25));
  STRU::STRU((STRU *)v23, v25, 0x100u);
  v8 = *((_QWORD *)this + 1);
  v9 = *((_QWORD *)a3 + 4);
  v19 = *((_DWORD *)a3 + 10);
  v10 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, unsigned int *))(*(_QWORD *)v8 + 216LL))(
          v8,
          a2,
          v9,
          &v19);
  v11 = v10;
  if ( v10 >= 0
    || v10 == -2147024774
    && (v11 = STRU::Resize(a3, v19), v11 >= 0)
    && (v12 = *((_QWORD *)this + 1),
        v13 = *((_QWORD *)a3 + 4),
        v19 = *((_DWORD *)a3 + 10),
        v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, unsigned int *))(*(_QWORD *)v12 + 216LL))(
                v12,
                a2,
                v13,
                &v19),
        v11 >= 0) )
  {
    STRU::SyncWithBuffer(a3);
    v11 = STRU::Copy((STRU *)v23, L"MACHINE/WEBROOT/APPHOST/");
    if ( v11 >= 0 )
    {
      v14 = (***((__int64 (__fastcall ****)(_QWORD))this + 1))(*((_QWORD *)this + 1));
      v15 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      v11 = STRU::Append((STRU *)v23, v15);
      if ( v11 >= 0 )
      {
        v11 = STRU::Append((STRU *)v23, a2);
        if ( v11 >= 0 )
        {
          v21 = 0;
          v22 = 0;
          v20 = 0;
          v16 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 56LL))(s_pGlobalInfo);
          v11 = (**v16)(v16, &IID_INativeConfigurationSystem, &v21);
          if ( v11 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v21 + 24LL))(
                    v21,
                    L"system.webServer/handlers",
                    v24,
                    &v22,
                    0,
                    0);
            if ( v11 >= 0 )
            {
              v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v22 + 48LL))(
                      v22,
                      L"accessPolicy",
                      &v20,
                      0,
                      0);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
              v22 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              v21 = 0;
              if ( v11 >= 0 )
              {
                if ( !a4
                  || (v20 & 1) != 0
                  && ((v20 & 8) == 0
                   || (v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 24LL))(*((_QWORD *)this + 1)),
                       *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17) + 840))) )
                {
                  v11 = 0;
                }
                else
                {
                  v11 = -2147024891;
                }
              }
            }
            else
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              v21 = 0;
            }
          }
        }
      }
    }
  }
  STRU::~STRU((STRU *)v23);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180003678  mov     [rsp-8+arg_18], rbx
0x18000367d  push    rbp
0x18000367e  push    rsi
0x18000367f  push    rdi
0x180003680  push    r14
0x180003682  push    r15
0x180003684  lea     rbp, [rsp-1A0h]
0x18000368c  sub     rsp, 2A0h
0x180003693  mov     rax, cs:__security_cookie
0x18000369a  xor     rax, rsp
0x18000369d  mov     [rbp+1C0h+var_30], rax
0x1800036a4  mov     rdi, r8
0x1800036a7  mov     rsi, rdx
0x1800036aa  mov     r14, rcx
0x1800036ad  xor     edx, edx; Val
0x1800036af  mov     r8d, 200h; Size
0x1800036b5  lea     rcx, [rbp+1C0h+var_230]; void *
0x1800036b9  mov     r15d, r9d
0x1800036bc  call    memset_0
0x1800036c1  mov     r8d, 100h
0x1800036c7  lea     rdx, [rbp+1C0h+var_230]
0x1800036cb  lea     rcx, [rsp+2C0h+var_268]
0x1800036d0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800036d6  mov     eax, [rdi+28h]
0x1800036d9  lea     r9, [rsp+2C0h+var_280]
0x1800036de  mov     rcx, [r14+8]
0x1800036e2  mov     rdx, rsi
0x1800036e5  mov     r8, [rdi+20h]
0x1800036e9  mov     [rsp+2C0h+var_280], eax
0x1800036ed  mov     rax, [rcx]
0x1800036f0  mov     rax, [rax+0D8h]
0x1800036f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036fc  mov     ebx, eax
0x1800036fe  test    eax, eax
0x180003700  jns     short loc_180003754
0x180003702  cmp     eax, 8007007Ah
0x180003707  jnz     loc_180003922
0x18000370d  mov     edx, [rsp+2C0h+var_280]
0x180003711  mov     rcx, rdi
0x180003714  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18000371a  mov     ebx, eax
0x18000371c  test    eax, eax
0x18000371e  js      loc_180003922
0x180003724  mov     eax, [rdi+28h]
0x180003727  lea     r9, [rsp+2C0h+var_280]
0x18000372c  mov     rcx, [r14+8]
0x180003730  mov     rdx, rsi
0x180003733  mov     r8, [rdi+20h]
0x180003737  mov     [rsp+2C0h+var_280], eax
0x18000373b  mov     rax, [rcx]
0x18000373e  mov     rax, [rax+0D8h]
0x180003745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000374a  mov     ebx, eax
0x18000374c  test    eax, eax
0x18000374e  js      loc_180003922
0x180003754  mov     rcx, rdi
0x180003757  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18000375d  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST/"
0x180003764  lea     rcx, [rsp+2C0h+var_268]
0x180003769  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000376f  mov     ebx, eax
0x180003771  test    eax, eax
0x180003773  js      loc_180003922
0x180003779  mov     rcx, [r14+8]
0x18000377d  mov     rax, [rcx]
0x180003780  mov     rax, [rax]
0x180003783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003788  mov     r8, rax
0x18000378b  mov     rcx, [rax]
0x18000378e  mov     rax, [rcx+8]
0x180003792  mov     rcx, r8
0x180003795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000379a  mov     rdx, rax
0x18000379d  lea     rcx, [rsp+2C0h+var_268]
0x1800037a2  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800037a8  mov     ebx, eax
0x1800037aa  test    eax, eax
0x1800037ac  js      loc_180003922
0x1800037b2  mov     rdx, rsi
0x1800037b5  lea     rcx, [rsp+2C0h+var_268]
0x1800037ba  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800037c0  mov     ebx, eax
0x1800037c2  test    eax, eax
0x1800037c4  js      loc_180003922
0x1800037ca  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x1800037d1  mov     [rsp+2C0h+var_278], 0
0x1800037da  mov     [rsp+2C0h+var_270], 0
0x1800037e3  mov     [rsp+2C0h+var_27C], 0
0x1800037eb  mov     rax, [rcx]
0x1800037ee  mov     rax, [rax+38h]
0x1800037f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037f7  mov     r9, rax
0x1800037fa  lea     r8, [rsp+2C0h+var_278]
0x1800037ff  lea     rdx, IID_INativeConfigurationSystem
0x180003806  mov     rcx, [rax]
0x180003809  mov     rax, [rcx]
0x18000380c  mov     rcx, r9
0x18000380f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003814  mov     ebx, eax
0x180003816  test    eax, eax
0x180003818  js      loc_180003922
0x18000381e  mov     rcx, [rsp+2C0h+var_278]
0x180003823  lea     r9, [rsp+2C0h+var_270]
0x180003828  mov     r8, [rsp+2C0h+var_248]
0x18000382d  lea     rdx, aSystemWebserve_0; "system.webServer/handlers"
0x180003834  mov     [rsp+2C0h+var_298], 0
0x18000383d  mov     [rsp+2C0h+var_2A0], 0
0x180003846  mov     rax, [rcx]
0x180003849  mov     rax, [rax+18h]
0x18000384d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003852  mov     ebx, eax
0x180003854  test    eax, eax
0x180003856  jns     short loc_180003877
0x180003858  mov     rcx, [rsp+2C0h+var_278]
0x18000385d  mov     rax, [rcx]
0x180003860  mov     rax, [rax+10h]
0x180003864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003869  mov     [rsp+2C0h+var_278], 0
0x180003872  jmp     loc_180003922
0x180003877  mov     rcx, [rsp+2C0h+var_270]
0x18000387c  lea     r8, [rsp+2C0h+var_27C]
0x180003881  xor     r9d, r9d
0x180003884  mov     [rsp+2C0h+var_2A0], 0
0x18000388d  lea     rdx, aAccesspolicy; "accessPolicy"
0x180003894  mov     rax, [rcx]
0x180003897  mov     rax, [rax+30h]
0x18000389b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038a0  mov     rcx, [rsp+2C0h+var_270]
0x1800038a5  mov     ebx, eax
0x1800038a7  mov     rax, [rcx]
0x1800038aa  mov     rax, [rax+10h]
0x1800038ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038b3  mov     rcx, [rsp+2C0h+var_278]
0x1800038b8  mov     [rsp+2C0h+var_270], 0
0x1800038c1  mov     rax, [rcx]
0x1800038c4  mov     rax, [rax+10h]
0x1800038c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038cd  mov     [rsp+2C0h+var_278], 0
0x1800038d6  test    ebx, ebx
0x1800038d8  js      short loc_180003922
0x1800038da  test    r15d, r15d
0x1800038dd  jz      short loc_180003920
0x1800038df  test    byte ptr [rsp+2C0h+var_27C], 1
0x1800038e4  jz      short loc_180003919
0x1800038e6  test    byte ptr [rsp+2C0h+var_27C], 8
0x1800038eb  jz      short loc_180003920
0x1800038ed  mov     rcx, [r14+8]
0x1800038f1  mov     rax, [rcx]
0x1800038f4  mov     rax, [rax+18h]
0x1800038f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038fd  mov     rdx, rax
0x180003900  mov     rcx, [rax]
0x180003903  mov     rax, [rcx+8]
0x180003907  mov     rcx, rdx
0x18000390a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000390f  cmp     qword ptr [rax+348h], 0
0x180003917  jnz     short loc_180003920
0x180003919  mov     ebx, 80070005h
0x18000391e  jmp     short loc_180003922
0x180003920  xor     ebx, ebx
0x180003922  lea     rcx, [rsp+2C0h+var_268]
0x180003927  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000392d  mov     eax, ebx
0x18000392f  mov     rcx, [rbp+1C0h+var_30]
0x180003936  xor     rcx, rsp; StackCookie
0x180003939  call    __security_check_cookie
0x18000393e  mov     rbx, [rsp+2C0h+arg_18]
0x180003946  add     rsp, 2A0h
0x18000394d  pop     r15
0x18000394f  pop     r14
0x180003951  pop     rdi
0x180003952  pop     rsi
0x180003953  pop     rbp
0x180003954  retn
```
