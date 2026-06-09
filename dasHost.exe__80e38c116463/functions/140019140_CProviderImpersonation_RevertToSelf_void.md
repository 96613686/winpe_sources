# CProviderImpersonation::RevertToSelf(void)

- ea: `0x140019140`
- end: `0x140019173`
- name: `?RevertToSelf@CProviderImpersonation@@UEAAJXZ`
- size: `51`
- prototype: `__int64 __fastcall(CProviderImpersonation *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140019140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019156`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019156`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14001914c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14001914c`

## pseudocode

```c
__int64 __fastcall CProviderImpersonation::RevertToSelf(CProviderImpersonation *this)
{
  unsigned int v1; // ebx
  signed int LastError; // eax

  v1 = 0;
  if ( !SetThreadToken(0, 0) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v1;
}

```

## disassembly

```asm
0x140019140  push    rbx
0x140019142  sub     rsp, 20h
0x140019146  xor     edx, edx; Token
0x140019148  xor     ecx, ecx; Thread
0x14001914a  xor     ebx, ebx
0x14001914c  call    cs:__imp_SetThreadToken
0x140019152  test    eax, eax
0x140019154  jnz     short loc_14001916B
0x140019156  call    cs:__imp_GetLastError
0x14001915c  mov     ebx, eax
0x14001915e  test    eax, eax
0x140019160  jle     short loc_14001916B
0x140019162  movzx   ebx, ax
0x140019165  or      ebx, 80070000h
0x14001916b  mov     eax, ebx
0x14001916d  add     rsp, 20h
0x140019171  pop     rbx
0x140019172  retn
```
