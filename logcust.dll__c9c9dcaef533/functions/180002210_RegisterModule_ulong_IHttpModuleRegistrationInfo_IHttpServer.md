# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180002210`
- end: `0x180002372`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(__int64, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001008`
- `0x180002210`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExA` at `0x18000230a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExA` at `0x18000230a`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  __int64 v5; // rax
  __int64 result; // rax
  int v7; // ebx
  _QWORD *v8; // rax
  CHAR *v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rax
  const char *v12; // rcx
  CHAR *v13; // rax
  unsigned int v14; // ecx
  DWORD nSize; // [rsp+48h] [rbp+10h] BYREF
  __int64 v16; // [rsp+50h] [rbp+18h] BYREF

  g_pLoggingModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  v5 = *(_QWORD *)a3;
  g_pGlobalInfo = a3;
  v16 = 0;
  result = (*(__int64 (__fastcall **)(struct IHttpServer *, __int64 *))(v5 + 160))(a3, &v16);
  if ( (int)result >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v16 + 40LL))(v16, 0, &g_fDoCentralBinaryLogging);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
    v16 = 0;
    if ( v7 >= 0 )
    {
      v8 = operator new(0x10u);
      if ( v8 )
      {
        *v8 = &CIISModuleFactory::`vftable';
        v8[1] = &CIISHttpModule::`vftable';
        result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
                   a2,
                   v8,
                   1024,
                   0);
        if ( (int)result >= 0 )
        {
          v9 = g_pszComputerName;
          v10 = 256;
          nSize = 256;
          if ( GetComputerNameExA(ComputerNameDnsHostname, g_pszComputerName, &nSize) )
            return 0;
          v11 = 2147483646;
          v12 = "<Server>";
          do
          {
            if ( !v11 )
              break;
            if ( !*v12 )
              break;
            *v9++ = *v12++;
            --v11;
            --v10;
          }
          while ( v10 );
          v13 = v9 - 1;
          v14 = v10 == 0 ? 0x8007007A : 0;
          if ( v10 )
            v13 = v9;
          *v13 = 0;
          if ( v10 )
            return 0;
          return v14;
        }
      }
      else
      {
        return 2147942408LL;
      }
    }
    else
    {
      return (unsigned int)v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002210  mov     [rsp+arg_0], rbx
0x180002215  push    rdi
0x180002216  sub     rsp, 30h
0x18000221a  mov     rax, [rdx]
0x18000221d  mov     rcx, rdx
0x180002220  mov     rbx, r8
0x180002223  mov     rdi, rdx
0x180002226  mov     rax, [rax+8]
0x18000222a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000222f  mov     cs:?g_pLoggingModuleContext@@3PEAXEA, rax; void * g_pLoggingModuleContext
0x180002236  lea     rdx, [rsp+38h+arg_10]
0x18000223b  mov     rax, [rbx]
0x18000223e  mov     rcx, rbx
0x180002241  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * g_pGlobalInfo
0x180002248  mov     [rsp+38h+arg_10], 0
0x180002251  mov     rax, [rax+0A0h]
0x180002258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000225d  test    eax, eax
0x18000225f  js      loc_180002367
0x180002265  mov     rcx, [rsp+38h+arg_10]
0x18000226a  lea     r8, ?g_fDoCentralBinaryLogging@@3HA; int g_fDoCentralBinaryLogging
0x180002271  xor     edx, edx
0x180002273  mov     rax, [rcx]
0x180002276  mov     rax, [rax+28h]
0x18000227a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000227f  mov     rcx, [rsp+38h+arg_10]
0x180002284  mov     ebx, eax
0x180002286  mov     rdx, [rcx]
0x180002289  mov     rax, [rdx+8]
0x18000228d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002292  mov     [rsp+38h+arg_10], 0
0x18000229b  test    ebx, ebx
0x18000229d  jns     short loc_1800022A6
0x18000229f  mov     eax, ebx
0x1800022a1  jmp     loc_180002367
0x1800022a6  mov     ecx, 10h; Size
0x1800022ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800022b0  mov     rdx, rax
0x1800022b3  test    rax, rax
0x1800022b6  jz      loc_180002362
0x1800022bc  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x1800022c3  xor     r9d, r9d
0x1800022c6  mov     [rdx], rax
0x1800022c9  mov     r8d, 400h
0x1800022cf  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x1800022d6  mov     [rdx+8], rax
0x1800022da  mov     rcx, [rdi]
0x1800022dd  mov     rax, [rcx+10h]
0x1800022e1  mov     rcx, rdi
0x1800022e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022e9  test    eax, eax
0x1800022eb  js      short loc_180002367
0x1800022ed  lea     rdi, ?g_pszComputerName@@3PADA; char near * g_pszComputerName
0x1800022f4  mov     ebx, 100h
0x1800022f9  mov     rdx, rdi; lpBuffer
0x1800022fc  mov     [rsp+38h+nSize], ebx
0x180002300  lea     r8, [rsp+38h+nSize]; nSize
0x180002305  mov     ecx, 1; NameType
0x18000230a  call    cs:__imp_GetComputerNameExA
0x180002310  test    eax, eax
0x180002312  jnz     short loc_18000235C
0x180002314  mov     eax, 7FFFFFFEh
0x180002319  lea     rcx, aServer; "<Server>"
0x180002320  test    rax, rax
0x180002323  jz      short loc_18000233C
0x180002325  mov     dl, [rcx]
0x180002327  test    dl, dl
0x180002329  jz      short loc_18000233C
0x18000232b  mov     [rdi], dl
0x18000232d  inc     rcx
0x180002330  inc     rdi
0x180002333  dec     rax
0x180002336  sub     rbx, 1
0x18000233a  jnz     short loc_180002320
0x18000233c  mov     rax, rbx
0x18000233f  neg     rax
0x180002342  lea     rax, [rdi-1]
0x180002346  sbb     ecx, ecx
0x180002348  not     ecx
0x18000234a  and     ecx, 8007007Ah
0x180002350  test    rbx, rbx
0x180002353  cmovnz  rax, rdi
0x180002357  mov     byte ptr [rax], 0
0x18000235a  jz      short loc_18000235E
0x18000235c  xor     ecx, ecx
0x18000235e  mov     eax, ecx
0x180002360  jmp     short loc_180002367
0x180002362  mov     eax, 80070008h
0x180002367  mov     rbx, [rsp+38h+arg_0]
0x18000236c  add     rsp, 30h
0x180002370  pop     rdi
0x180002371  retn
```
