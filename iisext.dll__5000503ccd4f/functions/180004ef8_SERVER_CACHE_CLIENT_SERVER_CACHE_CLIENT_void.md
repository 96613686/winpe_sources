# SERVER_CACHE_CLIENT::SERVER_CACHE_CLIENT(void)

- ea: `0x180004ef8`
- end: `0x180004f91`
- name: `??0SERVER_CACHE_CLIENT@@QEAA@XZ`
- size: `153`
- prototype: `SERVER_CACHE_CLIENT *__fastcall(SERVER_CACHE_CLIENT *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180005310`
- `0x1800065a0`
- `0x1800072a0`
- `0x1800080d0`
- `0x180008834`
- `0x180009c20`
- `0x18000a5b0`

## callees

- `0x180001008`
- `0x1800048dc`
- `0x180004ef8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180004f14`
- `KERNEL32!EnterCriticalSection` at `0x180004f14`
- `KERNEL32!LeaveCriticalSection` at `0x180004f7d`
- `KERNEL32!LeaveCriticalSection` at `0x180004f7d`

## string_xrefs

- `0x180004f67`: `\n\n==========================================\niisext!sm_pServerCache=%p\n\n`

## pseudocode

```c
SERVER_CACHE_CLIENT *__fastcall SERVER_CACHE_CLIENT::SERVER_CACHE_CLIENT(SERVER_CACHE_CLIENT *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  SERVER_CACHE *v3; // rax
  SERVER_CACHE *v4; // rdx
  char *v5; // rax

  v1 = g_pGlobalLock;
  if ( g_pGlobalLock )
  {
    EnterCriticalSection(g_pGlobalLock);
    ++SERVER_CACHE::sm_cRefs;
    if ( !SERVER_CACHE::sm_pServerCache )
    {
      v3 = (SERVER_CACHE *)operator new(0x40u);
      v4 = v3;
      if ( v3 )
      {
        *((_QWORD *)v3 + 2) = 0;
        *((_QWORD *)v3 + 1) = 5;
        v5 = (char *)v3 + 24;
        *(_QWORD *)v4 = v5;
        *(_OWORD *)v5 = 0;
        *((_OWORD *)v5 + 1) = 0;
        *((_QWORD *)v5 + 4) = 0;
      }
      else
      {
        v4 = 0;
      }
      SERVER_CACHE::sm_pServerCache = v4;
      AdsiTrace(L"\n\n==========================================\niisext!sm_pServerCache=%p\n\n");
    }
    LeaveCriticalSection(v1);
  }
  return this;
}

```

## disassembly

```asm
0x180004ef8  mov     [rsp+arg_0], rbx
0x180004efd  push    rdi
0x180004efe  sub     rsp, 20h
0x180004f02  mov     rbx, cs:?g_pGlobalLock@@3PEAVWIN32_CRITSEC@@EA; WIN32_CRITSEC * g_pGlobalLock
0x180004f09  mov     rdi, rcx
0x180004f0c  test    rbx, rbx
0x180004f0f  jz      short loc_180004F83
0x180004f11  mov     rcx, rbx; lpCriticalSection
0x180004f14  call    cs:__imp_EnterCriticalSection
0x180004f1a  inc     cs:?sm_cRefs@SERVER_CACHE@@1JA; long SERVER_CACHE::sm_cRefs
0x180004f20  cmp     cs:?sm_pServerCache@SERVER_CACHE@@1PEAV1@EA, 0; SERVER_CACHE * SERVER_CACHE::sm_pServerCache
0x180004f28  jnz     short loc_180004F7A
0x180004f2a  mov     ecx, 40h ; '@'; Size
0x180004f2f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004f34  mov     rdx, rax
0x180004f37  test    rax, rax
0x180004f3a  jz      short loc_180004F65
0x180004f3c  mov     qword ptr [rax+10h], 0
0x180004f44  xorps   xmm0, xmm0
0x180004f47  mov     qword ptr [rax+8], 5
0x180004f4f  add     rax, 18h
0x180004f53  mov     [rdx], rax
0x180004f56  xor     ecx, ecx
0x180004f58  movups  xmmword ptr [rax], xmm0
0x180004f5b  movups  xmmword ptr [rax+10h], xmm0
0x180004f5f  mov     [rax+20h], rcx
0x180004f63  jmp     short loc_180004F67
0x180004f65  xor     edx, edx
0x180004f67  lea     rcx, aIisextSmPserve; "\n\n==================================="...
0x180004f6e  mov     cs:?sm_pServerCache@SERVER_CACHE@@1PEAV1@EA, rdx; SERVER_CACHE * SERVER_CACHE::sm_pServerCache
0x180004f75  call    ?AdsiTrace@@YAXPEBGZZ; AdsiTrace(ushort const *,...)
0x180004f7a  mov     rcx, rbx; lpCriticalSection
0x180004f7d  call    cs:__imp_LeaveCriticalSection
0x180004f83  mov     rbx, [rsp+28h+arg_0]
0x180004f88  mov     rax, rdi
0x180004f8b  add     rsp, 20h
0x180004f8f  pop     rdi
0x180004f90  retn
```
