# DiscpSetInitiatorSharedSecret

- ea: `0x18001026c`
- end: `0x1800103fd`
- name: `DiscpSetInitiatorSharedSecret`
- size: `401`
- prototype: `__int64 __fastcall(size_t Size, void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003c70`
- `0x18001302c`

## callees

- `0x180006998`
- `0x18001026c`
- `0x180010404`
- `0x18001d38c`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x1800102ab`
- `ISCSIUM!DiscpAllocMemory` at `0x18001035b`
- `ISCSIUM!DiscpAllocMemory` at `0x1800102ab`
- `ISCSIUM!DiscpAllocMemory` at `0x18001035b`
- `ISCSIUM!DiscpSetRegistryValue` at `0x1800102f6`
- `ISCSIUM!DiscpSetRegistryValue` at `0x1800102f6`
- `ISCSIUM!DiscpFreeMemory` at `0x18001030e`
- `ISCSIUM!DiscpFreeMemory` at `0x1800103bd`
- `ISCSIUM!DiscpFreeMemory` at `0x1800103cc`
- `ISCSIUM!DiscpFreeMemory` at `0x1800103dc`
- `ISCSIUM!DiscpFreeMemory` at `0x18001030e`
- `ISCSIUM!DiscpFreeMemory` at `0x1800103bd`
- `ISCSIUM!DiscpFreeMemory` at `0x1800103cc`
- `ISCSIUM!DiscpFreeMemory` at `0x1800103dc`
- `ntdll!RtlLeaveCriticalSection` at `0x180010328`
- `ntdll!RtlLeaveCriticalSection` at `0x180010328`
- `ntdll!RtlEnterCriticalSection` at `0x18001029e`
- `ntdll!RtlEnterCriticalSection` at `0x18001029e`

## pseudocode

```c
__int64 __fastcall DiscpSetInitiatorSharedSecret(size_t Size, void *Src)
{
  size_t v2; // rdi
  void *v4; // rax
  void *v5; // rbp
  unsigned int InitiatorInstanceList; // ebx
  unsigned int v7; // r12d
  _DWORD *v8; // rax
  __int64 v9; // r15
  _DWORD *v10; // r14
  unsigned int v11; // esi
  __int64 i; // rdi
  __int64 v13; // rbp
  unsigned int v15; // [rsp+78h] [rbp+10h] BYREF
  __int64 v16; // [rsp+80h] [rbp+18h] BYREF

  v2 = (unsigned int)Size;
  v15 = 0;
  v16 = 0;
  RtlEnterCriticalSection(&DiscpCritSection);
  if ( Src )
  {
    v4 = (void *)DiscpAllocMemory((unsigned int)v2);
    v5 = v4;
    if ( !v4 )
    {
      InitiatorInstanceList = 8;
      goto LABEL_10;
    }
    memcpy_0(v4, Src, (unsigned int)v2);
  }
  else
  {
    v5 = 0;
  }
  InitiatorInstanceList = DiscpSetRegistryValue(
                            0,
                            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery",
                            L"InitiatorCHAPSecret",
                            3,
                            Src,
                            v2,
                            1);
  if ( !InitiatorInstanceList )
  {
    if ( DiscpInitiatorSharedSecret )
      DiscpFreeMemory(DiscpInitiatorSharedSecret);
    DiscpInitiatorSharedSecret = v5;
    LODWORD(DiscpInitiatorSharedSecretLength) = v2;
  }
LABEL_10:
  RtlLeaveCriticalSection(&DiscpCritSection);
  if ( !InitiatorInstanceList )
  {
    InitiatorInstanceList = DiscpGetInitiatorInstanceList(0, &v15, &v16);
    if ( !InitiatorInstanceList )
    {
      v7 = v2 + 4;
      v8 = (_DWORD *)DiscpAllocMemory((unsigned int)(v2 + 4));
      v9 = v16;
      v10 = v8;
      if ( v8 )
      {
        *v8 = v2;
        if ( Src )
          memcpy_0(v8 + 1, Src, v2);
        v11 = v15;
        for ( i = 0; (unsigned int)i < v11; i = (unsigned int)(i + 1) )
        {
          v13 = *(_QWORD *)(v9 + 8 * i);
          if ( (unsigned int)DiscpSetInitiatorSharedSecretForAdapter(v13, v10, v7) )
            InitiatorInstanceList = -1342242770;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 16), 0xFFFFFFFF) == 1 )
            DiscpFreeMemory(v13);
        }
        DiscpFreeMemory(v10);
      }
      else
      {
        InitiatorInstanceList = 8;
      }
      DiscpFreeMemory(v9);
    }
  }
  return InitiatorInstanceList;
}

```

## disassembly

```asm
0x18001026c  mov     rax, rsp
0x18001026f  mov     [rax+8], rbx
0x180010273  mov     [rax+20h], rbp
0x180010277  push    rsi
0x180010278  push    rdi
0x180010279  push    r12
0x18001027b  push    r14
0x18001027d  push    r15
0x18001027f  sub     rsp, 40h
0x180010283  mov     edi, ecx
0x180010285  mov     rsi, rdx
0x180010288  lea     rcx, DiscpCritSection; CriticalSection
0x18001028f  mov     dword ptr [rax+10h], 0
0x180010296  mov     qword ptr [rax+18h], 0
0x18001029e  call    cs:__imp_RtlEnterCriticalSection
0x1800102a4  test    rsi, rsi
0x1800102a7  jz      short loc_1800102D0
0x1800102a9  mov     ecx, edi
0x1800102ab  call    cs:__imp_DiscpAllocMemory
0x1800102b1  mov     rbp, rax
0x1800102b4  test    rax, rax
0x1800102b7  jz      short loc_1800102C9
0x1800102b9  mov     r8d, edi; Size
0x1800102bc  mov     rdx, rsi; Src
0x1800102bf  mov     rcx, rax; void *
0x1800102c2  call    memcpy_0
0x1800102c7  jmp     short loc_1800102D2
0x1800102c9  mov     ebx, 8
0x1800102ce  jmp     short loc_180010321
0x1800102d0  xor     ebp, ebp
0x1800102d2  mov     [rsp+68h+var_38], 1
0x1800102d7  lea     r8, aInitiatorchaps; "InitiatorCHAPSecret"
0x1800102de  mov     [rsp+68h+var_40], edi
0x1800102e2  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800102e9  mov     r9d, 3
0x1800102ef  mov     [rsp+68h+var_48], rsi
0x1800102f4  xor     ecx, ecx
0x1800102f6  call    cs:__imp_DiscpSetRegistryValue
0x1800102fc  mov     ebx, eax
0x1800102fe  test    eax, eax
0x180010300  jnz     short loc_180010321
0x180010302  mov     rcx, cs:DiscpInitiatorSharedSecret
0x180010309  test    rcx, rcx
0x18001030c  jz      short loc_180010314
0x18001030e  call    cs:__imp_DiscpFreeMemory
0x180010314  mov     cs:DiscpInitiatorSharedSecret, rbp
0x18001031b  mov     cs:DiscpInitiatorSharedSecretLength, edi
0x180010321  lea     rcx, DiscpCritSection; CriticalSection
0x180010328  call    cs:__imp_RtlLeaveCriticalSection
0x18001032e  test    ebx, ebx
0x180010330  jnz     loc_1800103E2
0x180010336  lea     r8, [rsp+68h+arg_10]
0x18001033e  xor     ecx, ecx
0x180010340  lea     rdx, [rsp+68h+arg_8]
0x180010345  call    DiscpGetInitiatorInstanceList
0x18001034a  mov     ebx, eax
0x18001034c  test    eax, eax
0x18001034e  jnz     loc_1800103E2
0x180010354  lea     r12d, [rdi+4]
0x180010358  mov     ecx, r12d
0x18001035b  call    cs:__imp_DiscpAllocMemory
0x180010361  mov     r15, [rsp+68h+arg_10]
0x180010369  mov     r14, rax
0x18001036c  test    rax, rax
0x18001036f  jz      short loc_1800103D4
0x180010371  mov     [rax], edi
0x180010373  test    rsi, rsi
0x180010376  jz      short loc_180010387
0x180010378  mov     r8, rdi; Size
0x18001037b  lea     rcx, [rax+4]; void *
0x18001037f  mov     rdx, rsi; Src
0x180010382  call    memcpy_0
0x180010387  mov     esi, [rsp+68h+arg_8]
0x18001038b  xor     edi, edi
0x18001038d  test    esi, esi
0x18001038f  jz      short loc_1800103C9
0x180010391  mov     rbp, [r15+rdi*8]
0x180010395  mov     r8d, r12d
0x180010398  mov     rcx, rbp
0x18001039b  mov     rdx, r14
0x18001039e  call    DiscpSetInitiatorSharedSecretForAdapter
0x1800103a3  test    eax, eax
0x1800103a5  mov     ecx, 0AFFF002Eh
0x1800103aa  cmovnz  ebx, ecx
0x1800103ad  or      eax, 0FFFFFFFFh
0x1800103b0  lock xadd [rbp+10h], eax
0x1800103b5  cmp     eax, 1
0x1800103b8  jnz     short loc_1800103C3
0x1800103ba  mov     rcx, rbp
0x1800103bd  call    cs:__imp_DiscpFreeMemory
0x1800103c3  inc     edi
0x1800103c5  cmp     edi, esi
0x1800103c7  jb      short loc_180010391
0x1800103c9  mov     rcx, r14
0x1800103cc  call    cs:__imp_DiscpFreeMemory
0x1800103d2  jmp     short loc_1800103D9
0x1800103d4  mov     ebx, 8
0x1800103d9  mov     rcx, r15
0x1800103dc  call    cs:__imp_DiscpFreeMemory
0x1800103e2  lea     r11, [rsp+68h+var_28]
0x1800103e7  mov     eax, ebx
0x1800103e9  mov     rbx, [r11+30h]
0x1800103ed  mov     rbp, [r11+48h]
0x1800103f1  mov     rsp, r11
0x1800103f4  pop     r15
0x1800103f6  pop     r14
0x1800103f8  pop     r12
0x1800103fa  pop     rdi
0x1800103fb  pop     rsi
0x1800103fc  retn
```
