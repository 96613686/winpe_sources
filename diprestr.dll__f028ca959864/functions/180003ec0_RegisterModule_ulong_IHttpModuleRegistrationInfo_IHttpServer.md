# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180003ec0`
- end: `0x1800040ca`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `522`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180001948`
- `0x180003244`
- `0x180003ec0`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003f14`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003f14`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180003f40`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180003f40`
- `iisutil!PuCreateDebugPrintsObject` at `0x180003efb`
- `iisutil!PuCreateDebugPrintsObject` at `0x180003efb`

## string_xrefs

- `0x180003f0d`: `Unable to Create Debug Print Object \n`
- `0x180003f39`: `System\CurrentControlSet\Services\W3SVC\Parameters\dynamicIpRestrictions`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  __int64 v3; // rax
  __int64 DebugPrintsObject; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  _DWORD *v8; // rdi
  int (*v9)(struct STBUFF *, struct STBUFF *); // r9
  int v10; // edi
  _QWORD *v11; // rax

  v3 = *(_QWORD *)a2;
  g_pGlobalInfo = a3;
  g_pModuleID = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(v3 + 8))(a2);
  DebugPrintsObject = PuCreateDebugPrintsObject("dynamicIpRestrictions", 1);
  g_pDebug = DebugPrintsObject;
  if ( DebugPrintsObject
    || (OutputDebugStringA("Unable to Create Debug Print Object \n"), (DebugPrintsObject = g_pDebug) != 0) )
  {
    if ( *(_DWORD *)(DebugPrintsObject + 640) )
    {
      g_dwDebugFlags = PuLoadDebugFlagsFromRegStr(
                         "System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\dynamicIpRestrictions",
                         0);
      v6 = operator new(0x10u);
      v7 = v6;
      if ( v6 )
      {
        *v6 = &IP_MODULE::`vftable'{for `CGlobalModule'};
        v6[1] = &IP_MODULE::`vftable'{for `CHttpModule'};
        v8 = operator new(0xB8u);
        if ( v8 )
        {
          *(_QWORD *)v8 = &STTABLE::`vftable';
          STBUFF::STBUFF((STBUFF *)(v8 + 2));
          v8[26] = 0;
          v8[28] = 0;
          *((_QWORD *)v8 + 22) = 0;
          g_pSiteHashTable = (STTABLE *)v8;
          v10 = STTABLE::Initialize((STTABLE *)v8, 0x61u, (unsigned int (*)(struct STBUFF *))KeyToHashString, v9);
          if ( v10 < 0 )
            goto LABEL_15;
          v10 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 24LL))(
                  a2,
                  v7,
                  256);
          if ( v10 < 0 )
            goto LABEL_15;
          v11 = operator new(8u);
          if ( v11 )
          {
            *v11 = &IP_FACTORY::`vftable';
            v10 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
                    a2,
                    v11,
                    536872960,
                    0);
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, __int64, const wchar_t *))(*(_QWORD *)a2 + 32LL))(
                      a2,
                      0x20000000,
                      L"FIRST");
              if ( v10 >= 0 )
                return (unsigned int)v10;
            }
LABEL_15:
            if ( g_pSiteHashTable )
            {
              (**(void (__fastcall ***)(STTABLE *, __int64))g_pSiteHashTable)(g_pSiteHashTable, 1);
              g_pSiteHashTable = 0;
            }
            if ( v7 )
              (*(void (__fastcall **)(_QWORD *, __int64))(v7[1] + 240LL))(v7 + 1, 1);
            return (unsigned int)v10;
          }
        }
        else
        {
          g_pSiteHashTable = 0;
        }
      }
      else
      {
        v7 = 0;
      }
      v10 = -2147024882;
      goto LABEL_15;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180003ec0  mov     [rsp+arg_0], rbx
0x180003ec5  mov     [rsp+arg_8], rsi
0x180003eca  push    rdi
0x180003ecb  sub     rsp, 30h
0x180003ecf  mov     rax, [rdx]
0x180003ed2  mov     rcx, rdx
0x180003ed5  mov     rsi, rdx
0x180003ed8  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, r8; IHttpServer * g_pGlobalInfo
0x180003edf  mov     rax, [rax+8]
0x180003ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ee8  mov     edx, 1
0x180003eed  mov     cs:?g_pModuleID@@3PEAXEA, rax; void * g_pModuleID
0x180003ef4  lea     rcx, aDynamiciprestr; "dynamicIpRestrictions"
0x180003efb  call    cs:__imp_PuCreateDebugPrintsObject
0x180003f01  mov     cs:g_pDebug, rax
0x180003f08  test    rax, rax
0x180003f0b  jnz     short loc_180003F2A
0x180003f0d  lea     rcx, aUnableToCreate; "Unable to Create Debug Print Object \n"
0x180003f14  call    cs:__imp_OutputDebugStringA
0x180003f1a  mov     rax, cs:g_pDebug
0x180003f21  test    rax, rax
0x180003f24  jz      loc_1800040B5
0x180003f2a  cmp     dword ptr [rax+280h], 0
0x180003f31  jz      loc_1800040B5
0x180003f37  xor     edx, edx
0x180003f39  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x180003f40  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x180003f46  mov     ecx, 10h; Size
0x180003f4b  mov     cs:g_dwDebugFlags, eax
0x180003f51  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003f56  mov     rbx, rax
0x180003f59  test    rax, rax
0x180003f5c  jz      loc_180004066
0x180003f62  lea     rax, ??_7IP_MODULE@@6BCGlobalModule@@@; const IP_MODULE::`vftable'{for `CGlobalModule'}
0x180003f69  mov     ecx, 0B8h; Size
0x180003f6e  mov     [rbx], rax
0x180003f71  lea     rax, ??_7IP_MODULE@@6BCHttpModule@@@; const IP_MODULE::`vftable'{for `CHttpModule'}
0x180003f78  mov     [rbx+8], rax
0x180003f7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003f81  mov     rdi, rax
0x180003f84  test    rax, rax
0x180003f87  jz      loc_180004059
0x180003f8d  lea     rax, ??_7STTABLE@@6B@; const STTABLE::`vftable'
0x180003f94  lea     rcx, [rdi+8]; this
0x180003f98  mov     [rdi], rax
0x180003f9b  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180003fa0  lea     r8, ?KeyToHashString@@YAKPEAVSTBUFF@@@Z; unsigned int (*)(struct STBUFF *)
0x180003fa7  mov     dword ptr [rdi+68h], 0
0x180003fae  mov     edx, 61h ; 'a'; unsigned int
0x180003fb3  mov     dword ptr [rdi+70h], 0
0x180003fba  mov     rcx, rdi; this
0x180003fbd  mov     qword ptr [rdi+0B0h], 0
0x180003fc8  mov     cs:?g_pSiteHashTable@@3PEAVSTTABLE@@EA, rdi; STTABLE * g_pSiteHashTable
0x180003fcf  call    ?Initialize@STTABLE@@QEAAJKP6AKPEAVSTBUFF@@@ZP6AH00@Z@Z; STTABLE::Initialize(ulong,ulong (*)(STBUFF *),int (*)(STBUFF *,STBUFF *))
0x180003fd4  mov     edi, eax
0x180003fd6  test    eax, eax
0x180003fd8  js      loc_18000406D
0x180003fde  mov     rax, [rsi]
0x180003fe1  mov     r8d, 100h
0x180003fe7  mov     rdx, rbx
0x180003fea  mov     rcx, rsi
0x180003fed  mov     rax, [rax+18h]
0x180003ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ff6  mov     edi, eax
0x180003ff8  test    eax, eax
0x180003ffa  js      short loc_18000406D
0x180003ffc  mov     ecx, 8; Size
0x180004001  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004006  mov     rdx, rax
0x180004009  test    rax, rax
0x18000400c  jz      short loc_180004068
0x18000400e  lea     rax, ??_7IP_FACTORY@@6B@; const IP_FACTORY::`vftable'
0x180004015  xor     r9d, r9d
0x180004018  mov     [rdx], rax
0x18000401b  mov     r8d, 20000800h
0x180004021  mov     rcx, [rsi]
0x180004024  mov     rax, [rcx+10h]
0x180004028  mov     rcx, rsi
0x18000402b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004030  mov     edi, eax
0x180004032  test    eax, eax
0x180004034  js      short loc_18000406D
0x180004036  mov     rax, [rsi]
0x180004039  lea     r8, aFirst; "FIRST"
0x180004040  mov     edx, 20000000h
0x180004045  mov     rcx, rsi
0x180004048  mov     rax, [rax+20h]
0x18000404c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004051  mov     edi, eax
0x180004053  test    eax, eax
0x180004055  jns     short loc_1800040B1
0x180004057  jmp     short loc_18000406D
0x180004059  mov     cs:?g_pSiteHashTable@@3PEAVSTTABLE@@EA, 0; STTABLE * g_pSiteHashTable
0x180004064  jmp     short loc_180004068
0x180004066  xor     ebx, ebx
0x180004068  mov     edi, 8007000Eh
0x18000406d  mov     rcx, cs:?g_pSiteHashTable@@3PEAVSTTABLE@@EA; STTABLE * g_pSiteHashTable
0x180004074  test    rcx, rcx
0x180004077  jz      short loc_180004094
0x180004079  mov     rax, [rcx]
0x18000407c  mov     edx, 1
0x180004081  mov     rax, [rax]
0x180004084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004089  mov     cs:?g_pSiteHashTable@@3PEAVSTTABLE@@EA, 0; STTABLE * g_pSiteHashTable
0x180004094  test    rbx, rbx
0x180004097  jz      short loc_1800040B1
0x180004099  lea     rcx, [rbx+8]
0x18000409d  mov     edx, 1
0x1800040a2  mov     rax, [rcx]
0x1800040a5  mov     rax, [rax+0F0h]
0x1800040ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040b1  mov     eax, edi
0x1800040b3  jmp     short loc_1800040BA
0x1800040b5  mov     eax, 80004005h
0x1800040ba  mov     rbx, [rsp+38h+arg_0]
0x1800040bf  mov     rsi, [rsp+38h+arg_8]
0x1800040c4  add     rsp, 30h
0x1800040c8  pop     rdi
0x1800040c9  retn
```
