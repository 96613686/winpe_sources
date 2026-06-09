# OUTPUT_CACHE::ScavengerCallback(void *,uchar)

- ea: `0x180003fe0`
- end: `0x1800040e2`
- name: `?ScavengerCallback@OUTPUT_CACHE@@CAXPEAXE@Z`
- size: `258`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180003fe0`
- `0x18000653c`
- `0x180008bbe`
- `0x180008bf0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18000405f`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18000405f`

## pseudocode

```c
void __fastcall OUTPUT_CACHE::ScavengerCallback(_QWORD *a1)
{
  void (__fastcall ***v2)(_QWORD, __int64, __int64); // rax
  DWORDLONG ullAvailVirtual; // rcx
  unsigned int v4; // eax
  unsigned __int64 v5; // r8
  struct _MEMORYSTATUSEX Buffer; // [rsp+20h] [rbp-58h] BYREF

  if ( !_InterlockedCompareExchange(&OUTPUT_CACHE::sm_fScavengerFired, 1, 0) )
  {
    v2 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
    (**v2)(v2, 20, 1);
    if ( !a1[12] )
    {
      memset_0(&Buffer, 0, sizeof(Buffer));
      Buffer.dwLength = 64;
      GlobalMemoryStatusEx(&Buffer);
      ullAvailVirtual = Buffer.ullAvailVirtual;
      if ( Buffer.ullAvailPhys < Buffer.ullAvailVirtual )
        ullAvailVirtual = Buffer.ullAvailPhys;
      a1[11] = (ullAvailVirtual + a1[13]) >> 1;
    }
    if ( *((_DWORD *)a1 + 29) )
    {
      v4 = *((_DWORD *)a1 + 30);
      v5 = 2LL * a1[11];
      *((_DWORD *)a1 + 30) = v4 >> 1;
      CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::DeleteIf(
        (CLKRHashTable *)a1,
        (__int64)OUTPUT_CACHE::CacheFlushByHitCount,
        (unsigned int)(a1[13] * (unsigned __int64)(v4 / *((_DWORD *)a1 + 29)) / v5));
    }
    OUTPUT_CACHE::sm_fScavengerFired = 0;
  }
}

```

## disassembly

```asm
0x180003fe0  mov     [rsp+arg_8], rbx
0x180003fe5  push    rdi
0x180003fe6  sub     rsp, 70h
0x180003fea  mov     rax, cs:__security_cookie
0x180003ff1  xor     rax, rsp
0x180003ff4  mov     [rsp+78h+var_18], rax
0x180003ff9  mov     rbx, rcx
0x180003ffc  mov     edi, 1
0x180004001  xor     eax, eax
0x180004003  lock cmpxchg cs:?sm_fScavengerFired@OUTPUT_CACHE@@0HA, edi; int OUTPUT_CACHE::sm_fScavengerFired
0x18000400b  jnz     loc_180004093
0x180004011  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180004018  mov     rax, [rcx]
0x18000401b  mov     rax, [rax+60h]
0x18000401f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004024  mov     r9, rax
0x180004027  lea     edx, [rdi+13h]
0x18000402a  mov     r8d, edi
0x18000402d  mov     rcx, [rax]
0x180004030  mov     rax, [rcx]
0x180004033  mov     rcx, r9
0x180004036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000403b  cmp     qword ptr [rbx+60h], 0
0x180004040  jnz     short loc_180004083
0x180004042  mov     edi, 40h ; '@'
0x180004047  lea     rcx, [rsp+78h+Buffer]; void *
0x18000404c  mov     r8d, edi; Size
0x18000404f  xor     edx, edx; Val
0x180004051  call    memset_0
0x180004056  lea     rcx, [rsp+78h+Buffer]; lpBuffer
0x18000405b  mov     [rsp+78h+Buffer.dwLength], edi
0x18000405f  call    cs:__imp_GlobalMemoryStatusEx
0x180004065  mov     rcx, [rsp+78h+Buffer.ullAvailVirtual]
0x18000406a  cmp     [rsp+78h+Buffer.ullAvailPhys], rcx
0x18000406f  mov     rax, [rbx+68h]
0x180004073  cmovb   rcx, [rsp+78h+Buffer.ullAvailPhys]
0x180004079  add     rax, rcx
0x18000407c  shr     rax, 1
0x18000407f  mov     [rbx+58h], rax
0x180004083  cmp     dword ptr [rbx+74h], 0
0x180004087  jnz     short loc_1800040AE
0x180004089  mov     cs:?sm_fScavengerFired@OUTPUT_CACHE@@0HA, 0; int OUTPUT_CACHE::sm_fScavengerFired
0x180004093  mov     rcx, [rsp+78h+var_18]
0x180004098  xor     rcx, rsp; StackCookie
0x18000409b  call    __security_check_cookie
0x1800040a0  mov     rbx, [rsp+78h+arg_8]
0x1800040a8  add     rsp, 70h
0x1800040ac  pop     rdi
0x1800040ad  retn
0x1800040ae  mov     eax, [rbx+78h]
0x1800040b1  mov     rcx, rbx
0x1800040b4  mov     r8, [rbx+58h]
0x1800040b8  mov     edx, eax
0x1800040ba  shr     edx, 1
0x1800040bc  add     r8, r8
0x1800040bf  mov     [rbx+78h], edx
0x1800040c2  xor     edx, edx
0x1800040c4  div     dword ptr [rbx+74h]
0x1800040c7  xor     edx, edx
0x1800040c9  imul    rax, [rbx+68h]
0x1800040ce  div     r8
0x1800040d1  lea     rdx, ?CacheFlushByHitCount@OUTPUT_CACHE@@CA?AW4LK_PREDICATE@@PEAVOUTPUT_ENTRY@@PEAX@Z; OUTPUT_CACHE::CacheFlushByHitCount(OUTPUT_ENTRY *,void *)
0x1800040d8  mov     r8d, eax
0x1800040db  call    ?DeleteIf@?$CTypedHashTable@VUL_RESPONSE_CACHE@@VUL_RESPONSE_CACHE_ENTRY@@PEAVUL_RESPONSE_CACHE_KEY@@VCLKRHashTable@@@@QEAAKP6A?AW4LK_PREDICATE@@PEAVUL_RESPONSE_CACHE_ENTRY@@PEAX@Z1@Z; CTypedHashTable<UL_RESPONSE_CACHE,UL_RESPONSE_CACHE_ENTRY,UL_RESPONSE_CACHE_KEY *,CLKRHashTable>::DeleteIf(LK_PREDICATE (*)(UL_RESPONSE_CACHE_ENTRY *,void *),void *)
0x1800040e0  jmp     short loc_180004089
```
