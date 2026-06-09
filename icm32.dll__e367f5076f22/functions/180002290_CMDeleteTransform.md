# CMDeleteTransform

- ea: `0x180002290`
- end: `0x18000233b`
- name: `CMDeleteTransform`
- size: `171`
- prototype: `BOOL __stdcall(HCMTRANSFORM hcmTransform)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002290`
- `0x180002344`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002305`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d101`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002305`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d101`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022b3`

## pseudocode

```c
BOOL __stdcall CMDeleteTransform(HCMTRANSFORM hcmTransform)
{
  int v1; // r14d
  int v2; // edi
  __int64 v3; // rbx
  BOOL v4; // esi
  __int64 v5; // rcx

  v1 = (int)hcmTransform;
  v2 = (_DWORD)hcmTransform - 256;
  v3 = 0;
  v4 = 0;
  EnterCriticalSection(&GlobalCriticalSection);
  if ( v2 < IndexTransform && v2 >= 0 )
  {
    _mm_lfence();
    v3 = TheTransform[v1 - 256];
    TheTransform[v1 - 256] = 0;
    if ( v2 == IndexTransform - 1 )
      --IndexTransform;
    v4 = 1;
  }
  LeaveCriticalSection(&GlobalCriticalSection);
  if ( v3 )
    v5 = *(_QWORD *)(v3 + 376);
  else
    v5 = 0;
  if ( v5 )
    LHColorWorldClose(v5);
  LHColorWorldClose(v3);
  return v4;
}

```

## disassembly

```asm
0x180002290  push    rbx
0x180002292  push    rsi
0x180002293  push    rdi
0x180002294  push    r14
0x180002296  sub     rsp, 38h
0x18000229a  mov     r14, rcx
0x18000229d  lea     edi, [rcx-100h]
0x1800022a3  xor     ebx, ebx
0x1800022a5  mov     [rsp+58h+var_38], rbx
0x1800022aa  xor     esi, esi
0x1800022ac  lea     rcx, GlobalCriticalSection; lpCriticalSection
0x1800022b3  call    cs:__imp_EnterCriticalSection
0x1800022b9  cmp     edi, cs:IndexTransform
0x1800022bf  jge     short loc_1800022FE
0x1800022c1  test    edi, edi
0x1800022c3  js      short loc_1800022FE
0x1800022c5  lfence
0x1800022c8  movsxd  rax, r14d
0x1800022cb  lea     rcx, TheTransform
0x1800022d2  mov     rbx, [rcx+rax*8-800h]
0x1800022da  mov     [rsp+58h+var_38], rbx
0x1800022df  mov     [rcx+rax*8-800h], rsi
0x1800022e7  mov     eax, cs:IndexTransform
0x1800022ed  dec     eax
0x1800022ef  cmp     edi, eax
0x1800022f1  jnz     short loc_1800022F9
0x1800022f3  mov     cs:IndexTransform, eax
0x1800022f9  mov     esi, 1
0x1800022fe  lea     rcx, GlobalCriticalSection; lpCriticalSection
0x180002305  call    cs:__imp_LeaveCriticalSection
0x18000230b  test    rbx, rbx
0x18000230e  jz      short loc_180002330
0x180002310  mov     rcx, [rbx+178h]
0x180002317  test    rcx, rcx
0x18000231a  jnz     short loc_180002334
0x18000231c  mov     rcx, rbx
0x18000231f  call    LHColorWorldClose
0x180002324  mov     eax, esi
0x180002326  add     rsp, 38h
0x18000232a  pop     r14
0x18000232c  pop     rdi
0x18000232d  pop     rsi
0x18000232e  pop     rbx
0x18000232f  retn
0x180002330  xor     ecx, ecx
0x180002332  jmp     short loc_180002317
0x180002334  call    LHColorWorldClose
0x180002339  jmp     short loc_18000231C
0x18003d0f0  push    rbx
0x18003d0f2  push    rbp
0x18003d0f3  sub     rsp, 28h
0x18003d0f7  mov     rbp, rdx
0x18003d0fa  lea     rcx, GlobalCriticalSection; lpCriticalSection
0x18003d101  call    cs:__imp_LeaveCriticalSection
0x18003d107  mov     rbx, [rbp+20h]
0x18003d10b  test    rbx, rbx
0x18003d10e  jz      short loc_18003D119
0x18003d110  mov     rcx, [rbx+178h]
0x18003d117  jmp     short loc_18003D11B
0x18003d119  xor     ecx, ecx
0x18003d11b  test    rcx, rcx
0x18003d11e  jz      short loc_18003D126
0x18003d120  call    LHColorWorldClose
0x18003d125  nop
0x18003d126  mov     rcx, rbx
0x18003d129  add     rsp, 28h
0x18003d12d  pop     rbp
0x18003d12e  pop     rbx
0x18003d12f  jmp     LHColorWorldClose
```
