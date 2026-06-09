# IP_MODULE::GetSiteConfig(IHttpSite *,CONFIG_OBJECT * *)

- ea: `0x1800055f0`
- end: `0x1800057c3`
- name: `?GetSiteConfig@IP_MODULE@@CAJPEAVIHttpSite@@PEAPEAVCONFIG_OBJECT@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(struct IHttpSite *, struct CONFIG_OBJECT **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800062b0`

## callees

- `0x180001008`
- `0x180001948`
- `0x180002604`
- `0x180005598`
- `0x1800055f0`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800056cd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800056cd`

## pseudocode

```c
__int64 __fastcall IP_MODULE::GetSiteConfig(struct IHttpSite *a1, struct CONFIG_OBJECT **a2)
{
  int ReferencedConfigFromIHttpSite; // edi
  unsigned __int16 *v5; // rdi
  char *v6; // rbx
  __int64 v7; // rax
  int v8; // eax
  __int64 (__fastcall ***v9)(_QWORD, void *); // rax
  volatile signed __int32 *v10; // rax
  struct CONFIG_OBJECT *v12; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  v12 = 0;
  ReferencedConfigFromIHttpSite = IP_MODULE::GetReferencedConfigFromIHttpSite(a1, &v12);
  if ( ReferencedConfigFromIHttpSite < 0 )
  {
    v5 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpSite *))(*(_QWORD *)a1 + 8LL))(a1);
    if ( v5 )
    {
      v6 = (char *)operator new(0x138u);
      if ( v6 )
      {
        *((_QWORD *)v6 + 1) = 0;
        *(_QWORD *)v6 = &CONFIG_OBJECT::`vftable';
        *((_QWORD *)v6 + 2) = 1;
        *(_QWORD *)(v6 + 28) = 0;
        *((_DWORD *)v6 + 9) = 0;
        *((_QWORD *)v6 + 5) = 300000;
        *((_QWORD *)v6 + 6) = 0;
        *((_DWORD *)v6 + 24) = 0;
        STBUFF::STBUFF((STBUFF *)(v6 + 104));
        *((_QWORD *)v6 + 25) = 0;
        STBUFF::STBUFF((STBUFF *)(v6 + 208));
        InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v6 + 56), 0x64u);
        *((_DWORD *)v6 + 24) = 1;
        ReferencedConfigFromIHttpSite = CONFIG_OBJECT::ReadConfig((CONFIG_OBJECT *)v6, v5);
        if ( ReferencedConfigFromIHttpSite < 0 )
          goto LABEL_16;
        v7 = (*(__int64 (__fastcall **)(struct IHttpSite *))(*(_QWORD *)a1 + 16LL))(a1);
        v8 = (*(__int64 (__fastcall **)(__int64, char *, void *))(*(_QWORD *)v7 + 8LL))(v7, v6, g_pModuleID);
        ReferencedConfigFromIHttpSite = v8;
        if ( v8 >= 0 )
        {
          v10 = (volatile signed __int32 *)v6;
        }
        else if ( v8 == -2147024811 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 4, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 1);
          v6 = 0;
          v9 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpSite *))(*(_QWORD *)a1 + 16LL))(a1);
          v10 = (volatile signed __int32 *)(**v9)(v9, g_pModuleID);
          ReferencedConfigFromIHttpSite = 0;
        }
        else
        {
          v10 = (volatile signed __int32 *)v12;
        }
        _InterlockedIncrement(v10 + 4);
        *a2 = (struct CONFIG_OBJECT *)v10;
        if ( ReferencedConfigFromIHttpSite < 0 )
        {
          if ( v6 )
          {
LABEL_16:
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 4, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 1);
          }
        }
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    *a2 = v12;
  }
  return (unsigned int)ReferencedConfigFromIHttpSite;
}

```

## disassembly

```asm
0x1800055f0  push    rbx
0x1800055f2  push    rsi
0x1800055f3  push    rdi
0x1800055f4  push    r14
0x1800055f6  sub     rsp, 28h
0x1800055fa  mov     r14, rdx
0x1800055fd  mov     qword ptr [rdx], 0
0x180005604  lea     rdx, [rsp+48h+arg_8]; struct CONFIG_OBJECT **
0x180005609  mov     [rsp+48h+arg_8], 0
0x180005612  mov     rsi, rcx
0x180005615  call    ?GetReferencedConfigFromIHttpSite@IP_MODULE@@CAJPEAVIHttpSite@@PEAPEAVCONFIG_OBJECT@@@Z; IP_MODULE::GetReferencedConfigFromIHttpSite(IHttpSite *,CONFIG_OBJECT * *)
0x18000561a  mov     edi, eax
0x18000561c  test    eax, eax
0x18000561e  js      short loc_18000562D
0x180005620  mov     rcx, [rsp+48h+arg_8]
0x180005625  mov     [r14], rcx
0x180005628  jmp     loc_1800057B7
0x18000562d  mov     rax, [rsi]
0x180005630  mov     rcx, rsi
0x180005633  mov     rax, [rax+8]
0x180005637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000563c  mov     rdi, rax
0x18000563f  test    rax, rax
0x180005642  jnz     short loc_18000564E
0x180005644  mov     edi, 80070057h
0x180005649  jmp     loc_1800057B7
0x18000564e  mov     ecx, 138h; Size
0x180005653  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005658  mov     rbx, rax
0x18000565b  test    rax, rax
0x18000565e  jz      loc_1800057B2
0x180005664  lea     rax, ??_7CONFIG_OBJECT@@6B@; const CONFIG_OBJECT::`vftable'
0x18000566b  mov     qword ptr [rbx+8], 0
0x180005673  lea     rcx, [rbx+68h]; this
0x180005677  mov     [rbx], rax
0x18000567a  mov     qword ptr [rbx+10h], 1
0x180005682  mov     qword ptr [rbx+1Ch], 0
0x18000568a  mov     dword ptr [rbx+24h], 0
0x180005691  mov     qword ptr [rbx+28h], 493E0h
0x180005699  mov     qword ptr [rbx+30h], 0
0x1800056a1  mov     dword ptr [rbx+60h], 0
0x1800056a8  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x1800056ad  lea     rcx, [rbx+0D0h]; this
0x1800056b4  mov     qword ptr [rbx+0C8h], 0
0x1800056bf  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x1800056c4  lea     rcx, [rbx+38h]; lpCriticalSection
0x1800056c8  mov     edx, 64h ; 'd'; dwSpinCount
0x1800056cd  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800056d3  mov     dword ptr [rbx+60h], 1
0x1800056da  mov     rdx, rdi; unsigned __int16 *
0x1800056dd  mov     rcx, rbx; this
0x1800056e0  call    ?ReadConfig@CONFIG_OBJECT@@AEAAJPEBG@Z; CONFIG_OBJECT::ReadConfig(ushort const *)
0x1800056e5  mov     edi, eax
0x1800056e7  test    eax, eax
0x1800056e9  js      loc_18000578F
0x1800056ef  mov     rax, [rsi]
0x1800056f2  mov     rcx, rsi
0x1800056f5  mov     rax, [rax+10h]
0x1800056f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056fe  mov     r8, cs:?g_pModuleID@@3PEAXEA; void * g_pModuleID
0x180005705  mov     r9, rax
0x180005708  mov     rdx, rbx
0x18000570b  mov     rcx, [rax]
0x18000570e  mov     rax, [rcx+8]
0x180005712  mov     rcx, r9
0x180005715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000571a  mov     edi, eax
0x18000571c  test    eax, eax
0x18000571e  jns     short loc_18000577C
0x180005720  cmp     eax, 80070055h
0x180005725  jnz     short loc_180005775
0x180005727  or      eax, 0FFFFFFFFh
0x18000572a  lock xadd [rbx+10h], eax
0x18000572f  cmp     eax, 1
0x180005732  jnz     short loc_180005748
0x180005734  mov     rax, [rbx]
0x180005737  mov     edx, 1
0x18000573c  mov     rcx, rbx
0x18000573f  mov     rax, [rax+8]
0x180005743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005748  mov     rax, [rsi]
0x18000574b  mov     rcx, rsi
0x18000574e  xor     ebx, ebx
0x180005750  mov     rax, [rax+10h]
0x180005754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005759  mov     rdx, cs:?g_pModuleID@@3PEAXEA; void * g_pModuleID
0x180005760  mov     r8, rax
0x180005763  mov     rcx, [rax]
0x180005766  mov     rax, [rcx]
0x180005769  mov     rcx, r8
0x18000576c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005771  xor     edi, edi
0x180005773  jmp     short loc_18000577F
0x180005775  mov     rax, [rsp+48h+arg_8]
0x18000577a  jmp     short loc_18000577F
0x18000577c  mov     rax, rbx
0x18000577f  lock inc dword ptr [rax+10h]
0x180005783  mov     [r14], rax
0x180005786  test    edi, edi
0x180005788  jns     short loc_1800057B7
0x18000578a  test    rbx, rbx
0x18000578d  jz      short loc_1800057B7
0x18000578f  or      eax, 0FFFFFFFFh
0x180005792  lock xadd [rbx+10h], eax
0x180005797  cmp     eax, 1
0x18000579a  jnz     short loc_1800057B7
0x18000579c  mov     rax, [rbx]
0x18000579f  mov     edx, 1
0x1800057a4  mov     rcx, rbx
0x1800057a7  mov     rax, [rax+8]
0x1800057ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057b0  jmp     short loc_1800057B7
0x1800057b2  mov     edi, 8007000Eh
0x1800057b7  mov     eax, edi
0x1800057b9  add     rsp, 28h
0x1800057bd  pop     r14
0x1800057bf  pop     rdi
0x1800057c0  pop     rsi
0x1800057c1  pop     rbx
0x1800057c2  retn
```
