# PendCall(_DAC_CLIENT_CONTEXT *,int *)

- ea: `0x180002c50`
- end: `0x180002c9b`
- name: `?PendCall@@YAJPEAU_DAC_CLIENT_CONTEXT@@PEAH@Z`
- size: `75`
- prototype: `__int64 __fastcall(struct _DAC_CLIENT_CONTEXT *, int *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002168`
- `0x180008b40`
- `0x180008fc0`

## callees

- `0x180002c50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c68`

## pseudocode

```c
__int64 __fastcall PendCall(struct _DAC_CLIENT_CONTEXT *a1, int *a2)
{
  unsigned int v3; // ebx

  v3 = 0;
  *a2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
  if ( *((_DWORD *)a1 + 16) )
  {
    v3 = -2147483638;
  }
  else
  {
    *((_DWORD *)a1 + 16) = 1;
    *a2 = 1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
  return v3;
}

```

## disassembly

```asm
0x180002c50  push    rbx
0x180002c52  push    rsi
0x180002c53  push    rdi
0x180002c54  push    r14
0x180002c56  sub     rsp, 28h
0x180002c5a  mov     rdi, rcx
0x180002c5d  xor     ebx, ebx
0x180002c5f  add     rcx, 10h; lpCriticalSection
0x180002c63  mov     [rdx], ebx
0x180002c65  mov     r14, rdx
0x180002c68  call    cs:__imp_EnterCriticalSection
0x180002c6e  cmp     [rdi+40h], ebx
0x180002c71  jz      short loc_180002C7A
0x180002c73  mov     ebx, 8000000Ah
0x180002c78  jmp     short loc_180002C85
0x180002c7a  mov     eax, 1
0x180002c7f  mov     [rdi+40h], eax
0x180002c82  mov     [r14], eax
0x180002c85  lea     rcx, [rdi+10h]; lpCriticalSection
0x180002c89  call    cs:__imp_LeaveCriticalSection
0x180002c8f  mov     eax, ebx
0x180002c91  add     rsp, 28h
0x180002c95  pop     r14
0x180002c97  pop     rdi
0x180002c98  pop     rsi
0x180002c99  pop     rbx
0x180002c9a  retn
```
