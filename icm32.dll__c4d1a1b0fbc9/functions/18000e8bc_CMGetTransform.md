# CMGetTransform

- ea: `0x18000e8bc`
- end: `0x18000e921`
- name: `CMGetTransform`
- size: `101`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e690`
- `0x18000e930`
- `0x18001d470`
- `0x18001d4f0`

## callees

- `0x18000e8bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e908`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e908`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d173`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e8dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e8dd`

## pseudocode

```c
__int64 __fastcall CMGetTransform(int a1)
{
  int v2; // edi
  __int64 v3; // rbx

  v2 = a1 - 256;
  v3 = 0;
  EnterCriticalSection(&GlobalCriticalSection);
  if ( v2 < IndexTransform && v2 >= 0 )
    v3 = TheTransform[a1 - 256];
  LeaveCriticalSection(&GlobalCriticalSection);
  return v3;
}

```

## disassembly

```asm
0x18000e8bc  mov     [rsp+arg_0], rbx
0x18000e8c1  mov     [rsp+arg_8], rsi
0x18000e8c6  push    rdi
0x18000e8c7  sub     rsp, 20h
0x18000e8cb  mov     rsi, rcx
0x18000e8ce  lea     edi, [rcx-100h]
0x18000e8d4  xor     ebx, ebx
0x18000e8d6  lea     rcx, GlobalCriticalSection; lpCriticalSection
0x18000e8dd  call    cs:__imp_EnterCriticalSection
0x18000e8e3  cmp     edi, cs:IndexTransform
0x18000e8e9  jge     short loc_18000E901
0x18000e8eb  test    edi, edi
0x18000e8ed  js      short loc_18000E901
0x18000e8ef  movsxd  rax, esi
0x18000e8f2  lea     rbx, TheTransform
0x18000e8f9  mov     rbx, [rbx+rax*8-800h]
0x18000e901  lea     rcx, GlobalCriticalSection; lpCriticalSection
0x18000e908  call    cs:__imp_LeaveCriticalSection
0x18000e90e  mov     rax, rbx
0x18000e911  mov     rbx, [rsp+28h+arg_0]
0x18000e916  mov     rsi, [rsp+28h+arg_8]
0x18000e91b  add     rsp, 20h
0x18000e91f  pop     rdi
0x18000e920  retn
0x18003d15e  push    rbp
0x18003d160  sub     rsp, 20h
0x18003d164  mov     rbp, rdx
0x18003d167  lea     rcx, GlobalCriticalSection
0x18003d16e  add     rsp, 20h
0x18003d172  pop     rbp
0x18003d173  jmp     cs:__imp_LeaveCriticalSection
```
