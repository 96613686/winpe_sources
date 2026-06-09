# CSwitchSecurityContext::CSwitchSecurityContext(void)

- ea: `0x18008b404`
- end: `0x18008b4d6`
- name: `??0CSwitchSecurityContext@@QEAA@XZ`
- size: `210`
- prototype: `CSwitchSecurityContext *__fastcall(CSwitchSecurityContext *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180088910`
- `0x180089280`
- `0x180089980`
- `0x180089d10`
- `0x18008d170`
- `0x18008dc60`
- `0x18008dd10`
- `0x18008dde0`

## callees

- `0x18008b404`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b4a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b4a8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18008b49e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18008b49e`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x18008b48b`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x18008b4b6`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x18008b48b`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x18008b4b6`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18008b43c`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18008b43c`

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
0x18008b404  mov     rax, rsp
0x18008b407  mov     [rax+18h], rbx
0x18008b40b  push    rdi
0x18008b40c  sub     rsp, 20h
0x18008b410  lea     rdi, [rcx+8]
0x18008b414  mov     byte ptr [rcx], 0
0x18008b417  mov     rbx, rcx
0x18008b41a  mov     qword ptr [rdi], 0
0x18008b421  lea     rcx, IID_IServerSecurity; riid
0x18008b428  mov     qword ptr [rax+10h], 0
0x18008b430  lea     rdx, [rax+8]; ppInterface
0x18008b434  mov     qword ptr [rax+8], 0
0x18008b43c  call    cs:__imp_CoGetCallContext
0x18008b442  test    eax, eax
0x18008b444  js      short loc_18008B486
0x18008b446  mov     rcx, [rsp+28h+arg_0]
0x18008b44b  mov     rax, [rcx]
0x18008b44e  mov     rax, [rax+30h]
0x18008b452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b457  test    eax, eax
0x18008b459  jz      short loc_18008B46C
0x18008b45b  mov     rcx, [rsp+28h+arg_0]
0x18008b460  mov     rax, [rcx]
0x18008b463  mov     rax, [rax+28h]
0x18008b467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b46c  mov     rcx, [rsp+28h+arg_0]
0x18008b471  mov     rax, [rcx]
0x18008b474  mov     rax, [rax+10h]
0x18008b478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b47d  mov     [rsp+28h+arg_0], 0
0x18008b486  mov     rdx, rdi; ppOldObject
0x18008b489  xor     ecx, ecx; pNewObject
0x18008b48b  call    cs:__imp_CoSwitchCallContext
0x18008b491  test    eax, eax
0x18008b493  js      short loc_18008B4C8
0x18008b495  mov     rdx, cs:?m_hImpersonationToken@CSwitchSecurityContext@@0PEAXEA; Token
0x18008b49c  xor     ecx, ecx; Thread
0x18008b49e  call    cs:__imp_SetThreadToken
0x18008b4a4  test    eax, eax
0x18008b4a6  jnz     short loc_18008B4C5
0x18008b4a8  call    cs:__imp_GetLastError
0x18008b4ae  mov     rcx, [rdi]; pNewObject
0x18008b4b1  lea     rdx, [rsp+28h+ppOldObject]; ppOldObject
0x18008b4b6  call    cs:__imp_CoSwitchCallContext
0x18008b4bc  mov     qword ptr [rdi], 0
0x18008b4c3  jmp     short loc_18008B4C8
0x18008b4c5  mov     byte ptr [rbx], 1
0x18008b4c8  mov     rax, rbx
0x18008b4cb  mov     rbx, [rsp+28h+arg_10]
0x18008b4d0  add     rsp, 20h
0x18008b4d4  pop     rdi
0x18008b4d5  retn
```
