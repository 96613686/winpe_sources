# CSwitchSecurityContext::CSwitchSecurityContext(void)

- ea: `0x180092408`
- end: `0x1800924f9`
- name: `??0CSwitchSecurityContext@@QEAA@XZ`
- size: `241`
- prototype: `CSwitchSecurityContext *__fastcall(CSwitchSecurityContext *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008f5d0`
- `0x18008ffe0`
- `0x1800907a0`
- `0x180090b60`
- `0x180094240`
- `0x180094df0`
- `0x180094ea0`
- `0x180094f80`

## callees

- `0x180092408`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800924be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800924be`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800924ae`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800924ae`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180092495`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800924d2`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x180092495`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800924d2`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180092440`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180092440`

## pseudocode

```c
CSwitchSecurityContext *__fastcall CSwitchSecurityContext::CSwitchSecurityContext(CSwitchSecurityContext *this)
{
  IUnknown **v1; // rdi
  void *v4; // [rsp+30h] [rbp+8h] BYREF
  IUnknown *ppOldObject; // [rsp+38h] [rbp+10h] BYREF

  v1 = (IUnknown **)((char *)this + 8);
  *(_BYTE *)this = 0;
  *((_QWORD *)this + 1) = 0;
  ppOldObject = 0;
  v4 = 0;
  if ( CoGetCallContext(&IID_IServerSecurity, &v4) >= 0 )
  {
    if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v4 + 48LL))(v4) )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 40LL))(v4);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
    v4 = 0;
  }
  if ( CoSwitchCallContext(0, v1) >= 0 )
  {
    if ( SetThreadToken(0, CSwitchSecurityContext::m_hImpersonationToken) )
    {
      *(_BYTE *)this = 1;
    }
    else
    {
      GetLastError();
      CoSwitchCallContext(*v1, &ppOldObject);
      *v1 = 0;
    }
  }
  return this;
}

```

## disassembly

```asm
0x180092408  mov     rax, rsp
0x18009240b  mov     [rax+18h], rbx
0x18009240f  push    rdi
0x180092410  sub     rsp, 20h
0x180092414  lea     rdi, [rcx+8]
0x180092418  mov     byte ptr [rcx], 0
0x18009241b  mov     rbx, rcx
0x18009241e  mov     qword ptr [rdi], 0
0x180092425  lea     rcx, IID_IServerSecurity; riid
0x18009242c  mov     qword ptr [rax+10h], 0
0x180092434  lea     rdx, [rax+8]; ppInterface
0x180092438  mov     qword ptr [rax+8], 0
0x180092440  call    cs:__imp_CoGetCallContext
0x180092447  nop     dword ptr [rax+rax+00h]
0x18009244c  test    eax, eax
0x18009244e  js      short loc_180092490
0x180092450  mov     rcx, [rsp+28h+arg_0]
0x180092455  mov     rax, [rcx]
0x180092458  mov     rax, [rax+30h]
0x18009245c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092461  test    eax, eax
0x180092463  jz      short loc_180092476
0x180092465  mov     rcx, [rsp+28h+arg_0]
0x18009246a  mov     rax, [rcx]
0x18009246d  mov     rax, [rax+28h]
0x180092471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092476  mov     rcx, [rsp+28h+arg_0]
0x18009247b  mov     rax, [rcx]
0x18009247e  mov     rax, [rax+10h]
0x180092482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092487  mov     [rsp+28h+arg_0], 0
0x180092490  mov     rdx, rdi; ppOldObject
0x180092493  xor     ecx, ecx; pNewObject
0x180092495  call    cs:__imp_CoSwitchCallContext
0x18009249c  nop     dword ptr [rax+rax+00h]
0x1800924a1  test    eax, eax
0x1800924a3  js      short loc_1800924EA
0x1800924a5  mov     rdx, cs:?m_hImpersonationToken@CSwitchSecurityContext@@0PEAXEA; Token
0x1800924ac  xor     ecx, ecx; Thread
0x1800924ae  call    cs:__imp_SetThreadToken
0x1800924b5  nop     dword ptr [rax+rax+00h]
0x1800924ba  test    eax, eax
0x1800924bc  jnz     short loc_1800924E7
0x1800924be  call    cs:__imp_GetLastError
0x1800924c5  nop     dword ptr [rax+rax+00h]
0x1800924ca  mov     rcx, [rdi]; pNewObject
0x1800924cd  lea     rdx, [rsp+28h+ppOldObject]; ppOldObject
0x1800924d2  call    cs:__imp_CoSwitchCallContext
0x1800924d9  nop     dword ptr [rax+rax+00h]
0x1800924de  mov     qword ptr [rdi], 0
0x1800924e5  jmp     short loc_1800924EA
0x1800924e7  mov     byte ptr [rbx], 1
0x1800924ea  mov     rax, rbx
0x1800924ed  mov     rbx, [rsp+28h+arg_10]
0x1800924f2  add     rsp, 20h
0x1800924f6  pop     rdi
0x1800924f7  retn
```
