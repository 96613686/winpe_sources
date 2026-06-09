# ThreadSafeHashMap_ForEach

- ea: `0x18003f0e0`
- end: `0x18003f1ce`
- name: `ThreadSafeHashMap_ForEach`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003db90`

## callees

- `0x18003f0e0`
- `0x180043e7c`
- `0x180044464`
- `0x18004449c`
- `0x1800444f4`
- `0x18004462c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f0fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f19f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f0fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f19f`

## pseudocode

```c
__int64 __fastcall ThreadSafeHashMap_ForEach(__int64 **a1, __int64 (__fastcall *a2)(__int64, __int64), __int64 a3)
{
  __int64 **v4; // rdi
  unsigned int v7; // esi
  __int64 v8; // rax
  __int64 *i; // rbx
  __int64 v11; // [rsp+20h] [rbp-38h] BYREF
  __int64 v12; // [rsp+28h] [rbp-30h]

  v4 = a1 + 6;
  v7 = 0;
  if ( a1[11] != (__int64 *)GetCurrentThreadId() && (unsigned int)_Pump_BeginDeferringHelper(v4) )
    _Pump_BeginDeferring(v4);
  v11 = 0;
  if ( a1[1] )
    v12 = **a1;
  else
    v12 = 0;
  while ( 1 )
  {
    v8 = HashMap_Iterate(a1, &v11);
    if ( !v8 )
      break;
    _m_prefetchw((const void *)(v8 + 16));
    if ( *(_QWORD *)(v8 + 16) != 2 )
    {
      v7 = a2(a3, v8);
      if ( v7 )
        goto LABEL_15;
    }
  }
  for ( i = a1[8]; i; i = (__int64 *)*i )
  {
    _m_prefetchw(i + 1);
    if ( !i[1] )
    {
      v7 = ((__int64 (__fastcall *)(__int64))a2)(a3);
      if ( v7 )
        break;
    }
  }
LABEL_15:
  if ( v4[5] != (__int64 *)GetCurrentThreadId() && (unsigned int)_Pump_EndDeferringHelper(v4) )
    _Pump_EndDeferring(v4);
  return v7;
}

```

## disassembly

```asm
0x18003f0e0  push    rbx
0x18003f0e2  push    rbp
0x18003f0e3  push    rsi
0x18003f0e4  push    rdi
0x18003f0e5  push    r14
0x18003f0e7  sub     rsp, 30h
0x18003f0eb  mov     rbp, r8
0x18003f0ee  lea     rdi, [rcx+30h]
0x18003f0f2  mov     r14, rdx
0x18003f0f5  mov     rbx, rcx
0x18003f0f8  xor     esi, esi
0x18003f0fa  call    cs:__imp_GetCurrentThreadId
0x18003f100  mov     eax, eax
0x18003f102  cmp     [rdi+28h], rax
0x18003f106  jz      short loc_18003F11C
0x18003f108  mov     rcx, rdi
0x18003f10b  call    __Pump_BeginDeferringHelper
0x18003f110  test    eax, eax
0x18003f112  jz      short loc_18003F11C
0x18003f114  mov     rcx, rdi
0x18003f117  call    __Pump_BeginDeferring
0x18003f11c  mov     [rsp+58h+var_38], rsi
0x18003f121  cmp     [rbx+8], rsi
0x18003f125  jbe     short loc_18003F134
0x18003f127  mov     rax, [rbx]
0x18003f12a  mov     rcx, [rax]
0x18003f12d  mov     [rsp+58h+var_30], rcx
0x18003f132  jmp     short loc_18003F15D
0x18003f134  mov     [rsp+58h+var_30], rsi
0x18003f139  jmp     short loc_18003F15D
0x18003f13b  prefetchw byte ptr [rax+10h]
0x18003f13f  mov     rcx, [rax+10h]
0x18003f143  cmp     rcx, 2
0x18003f147  jz      short loc_18003F15D
0x18003f149  mov     rdx, rax
0x18003f14c  mov     rcx, rbp
0x18003f14f  mov     rax, r14
0x18003f152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f157  mov     esi, eax
0x18003f159  test    eax, eax
0x18003f15b  jnz     short loc_18003F19F
0x18003f15d  lea     rdx, [rsp+58h+var_38]
0x18003f162  mov     rcx, rbx
0x18003f165  call    HashMap_Iterate
0x18003f16a  test    rax, rax
0x18003f16d  jnz     short loc_18003F13B
0x18003f16f  mov     rbx, [rbx+40h]
0x18003f173  jmp     short loc_18003F19A
0x18003f175  lea     rdx, [rbx-8]
0x18003f179  prefetchw byte ptr [rdx+10h]
0x18003f17d  mov     rax, [rdx+10h]
0x18003f181  test    rax, rax
0x18003f184  jnz     short loc_18003F197
0x18003f186  mov     rcx, rbp
0x18003f189  mov     rax, r14
0x18003f18c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f191  mov     esi, eax
0x18003f193  test    eax, eax
0x18003f195  jnz     short loc_18003F19F
0x18003f197  mov     rbx, [rbx]
0x18003f19a  test    rbx, rbx
0x18003f19d  jnz     short loc_18003F175
0x18003f19f  call    cs:__imp_GetCurrentThreadId
0x18003f1a5  mov     eax, eax
0x18003f1a7  cmp     [rdi+28h], rax
0x18003f1ab  jz      short loc_18003F1C1
0x18003f1ad  mov     rcx, rdi
0x18003f1b0  call    __Pump_EndDeferringHelper
0x18003f1b5  test    eax, eax
0x18003f1b7  jz      short loc_18003F1C1
0x18003f1b9  mov     rcx, rdi
0x18003f1bc  call    __Pump_EndDeferring
0x18003f1c1  mov     eax, esi
0x18003f1c3  add     rsp, 30h
0x18003f1c7  pop     r14
0x18003f1c9  pop     rdi
0x18003f1ca  pop     rsi
0x18003f1cb  pop     rbp
0x18003f1cc  pop     rbx
0x18003f1cd  retn
```
