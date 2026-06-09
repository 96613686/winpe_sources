# CNestedImpersonation::~CNestedImpersonation(void)

- ea: `0x180008b70`
- end: `0x180008cb3`
- name: `??1CNestedImpersonation@@QEAA@XZ`
- size: `323`
- prototype: `void __fastcall(CNestedImpersonation *__hidden this)`
- caller_count: `102`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006b40`
- `0x18000815c`
- `0x1800084a0`
- `0x180009ac0`
- `0x180009e70`
- `0x18000bca0`
- `0x18000c920`
- `0x180016ee0`
- `0x18001a6fc`
- `0x18001c9c4`
- `0x18001e96c`
- `0x180027d18`
- `0x180029a84`
- `0x18002ac74`
- `0x1800302e8`
- `0x180030480`
- `0x18003b140`
- `0x18004b9e0`
- `0x1800507a0`
- `0x1800523e8`
- `0x18005352c`
- `0x1800548e4`
- `0x1800590e0`
- `0x180059860`
- `0x180061000`
- `0x180062f88`
- `0x180068880`
- `0x18006e460`
- `0x180076344`
- `0x18007d050`
- `0x18007d8d4`
- `0x18008a9a0`
- `0x18008abdc`
- `0x18008b030`
- `0x18008b230`
- `0x18008b6b0`
- `0x18008b9cc`
- `0x18008bd40`
- `0x18008c040`
- `0x18008c480`
- `0x18009651c`
- `0x180097c58`
- `0x18009ea08`
- `0x1800a1930`
- `0x1800bf570`
- `0x1800bf8d8`
- `0x1800c0c7c`
- `0x1800c365c`
- `0x1800c6d3c`
- `0x1800cbe68`

## callees

- `0x180008b70`
- `0x1800a3444`
- `0x1800acacc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008b90`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008c00`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008b90`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008c00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c65`

## pseudocode

```c
void __fastcall CNestedImpersonation::~CNestedImpersonation(void ***this)
{
  void **v2; // rcx
  void **v3; // rdx
  char *v4; // rcx
  char *v5; // rcx

  if ( *((_BYTE *)this + 8) )
  {
    SetThreadToken(0, **this);
    *((_BYTE *)this + 8) = 0;
  }
  v2 = this[6];
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v2 + 2, 0xFFFFFFFF) == 1 )
      operator delete(this[6], 0x10u);
    this[6] = 0;
  }
  v3 = this[5];
  if ( v3 )
    std::default_delete<AppPackageInfo>::operator()(v2, v3);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this[4], 0xFFFFFFFF) == 1 )
  {
    operator delete(this[4], 4u);
    operator delete(this[3], 0);
    this[4] = 0;
    this[3] = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this[2] + 2, 0xFFFFFFFF) == 1 )
  {
    v4 = (char *)*this[2];
    if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v4);
      *this[2] = 0;
    }
    operator delete(this[2], 0x10u);
    this[2] = 0;
  }
  SetThreadToken(0, **this);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)*this + 2, 0xFFFFFFFF) == 1 )
  {
    v5 = (char *)**this;
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v5);
      **this = 0;
    }
    operator delete(*this, 0x10u);
    *this = 0;
  }
}

```

## disassembly

```asm
0x180008b70  mov     [rsp+arg_8], rbx
0x180008b75  mov     [rsp+arg_10], rsi
0x180008b7a  push    rdi
0x180008b7b  sub     rsp, 20h
0x180008b7f  cmp     byte ptr [rcx+8], 0
0x180008b83  mov     rbx, rcx
0x180008b86  jz      short loc_180008B9A
0x180008b88  mov     rdx, [rcx]
0x180008b8b  xor     ecx, ecx; Thread
0x180008b8d  mov     rdx, [rdx]; Token
0x180008b90  call    cs:__imp_SetThreadToken
0x180008b96  mov     byte ptr [rbx+8], 0
0x180008b9a  mov     rcx, [rbx+30h]
0x180008b9e  xor     esi, esi
0x180008ba0  mov     edi, 0FFFFFFFFh
0x180008ba5  test    rcx, rcx
0x180008ba8  jz      short loc_180008BC8
0x180008baa  mov     eax, edi
0x180008bac  lock xadd [rcx+8], eax
0x180008bb1  cmp     eax, 1
0x180008bb4  jnz     short loc_180008BC4
0x180008bb6  mov     rcx, [rbx+30h]; void *
0x180008bba  mov     edx, 10h; unsigned __int64
0x180008bbf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008bc4  mov     [rbx+30h], rsi
0x180008bc8  mov     rdx, [rbx+28h]
0x180008bcc  test    rdx, rdx
0x180008bcf  jnz     loc_180008CA9
0x180008bd5  mov     rax, [rbx+20h]
0x180008bd9  mov     ecx, edi
0x180008bdb  lock xadd [rax], ecx
0x180008bdf  cmp     ecx, 1
0x180008be2  jz      loc_180008C83
0x180008be8  mov     rcx, [rbx+10h]
0x180008bec  mov     eax, edi
0x180008bee  lock xadd [rcx+8], eax
0x180008bf3  cmp     eax, 1
0x180008bf6  jz      short loc_180008C23
0x180008bf8  mov     rdx, [rbx]
0x180008bfb  xor     ecx, ecx; Thread
0x180008bfd  mov     rdx, [rdx]; Token
0x180008c00  call    cs:__imp_SetThreadToken
0x180008c06  mov     rax, [rbx]
0x180008c09  lock xadd [rax+8], edi
0x180008c0e  cmp     edi, 1
0x180008c11  jz      short loc_180008C55
0x180008c13  mov     rbx, [rsp+28h+arg_8]
0x180008c18  mov     rsi, [rsp+28h+arg_10]
0x180008c1d  add     rsp, 20h
0x180008c21  pop     rdi
0x180008c22  retn
0x180008c23  mov     rax, [rbx+10h]
0x180008c27  mov     rcx, [rax]; hObject
0x180008c2a  lea     rax, [rcx-1]
0x180008c2e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008c32  ja      short loc_180008C41
0x180008c34  call    cs:__imp_CloseHandle
0x180008c3a  mov     rax, [rbx+10h]
0x180008c3e  mov     [rax], rsi
0x180008c41  mov     rcx, [rbx+10h]; void *
0x180008c45  mov     edx, 10h; unsigned __int64
0x180008c4a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008c4f  mov     [rbx+10h], rsi
0x180008c53  jmp     short loc_180008BF8
0x180008c55  mov     rax, [rbx]
0x180008c58  mov     rcx, [rax]; hObject
0x180008c5b  lea     rax, [rcx-1]
0x180008c5f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008c63  ja      short loc_180008C71
0x180008c65  call    cs:__imp_CloseHandle
0x180008c6b  mov     rax, [rbx]
0x180008c6e  mov     [rax], rsi
0x180008c71  mov     rcx, [rbx]; void *
0x180008c74  mov     edx, 10h; unsigned __int64
0x180008c79  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008c7e  mov     [rbx], rsi
0x180008c81  jmp     short loc_180008C13
0x180008c83  mov     rcx, [rbx+20h]; void *
0x180008c87  mov     edx, 4; unsigned __int64
0x180008c8c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008c91  mov     rcx, [rbx+18h]; void *
0x180008c95  xor     edx, edx; unsigned __int64
0x180008c97  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008c9c  mov     [rbx+20h], rsi
0x180008ca0  mov     [rbx+18h], rsi
0x180008ca4  jmp     loc_180008BE8
0x180008ca9  call    ??R?$default_delete@UAppPackageInfo@@@std@@QEBAXPEAUAppPackageInfo@@@Z; std::default_delete<AppPackageInfo>::operator()(AppPackageInfo *)
0x180008cae  jmp     loc_180008BD5
```
