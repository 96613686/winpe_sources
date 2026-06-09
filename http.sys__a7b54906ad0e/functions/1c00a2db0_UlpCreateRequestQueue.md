# UlpCreateRequestQueue

- ea: `0x1c00a2db0`
- end: `0x1c00a2ffa`
- name: `UlpCreateRequestQueue`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c00a2ccc`

## callees

- `0x1c00021bc`
- `0x1c008f570`
- `0x1c0090288`
- `0x1c0090974`
- `0x1c00a2db0`
- `0x1c00a3000`
- `0x1c00a309c`
- `0x1c00a47b4`
- `0x1c00a4a34`
- `0x1c00a81b8`
- `0x1c00a931c`
- `0x1c00a93f4`
- `0x1c0102a4c`
- `0x1c0103af4`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x1c00a2f4b`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1c00a2f4b`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00a2f1a`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00ddfe9`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00a2f1a`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00ddfe9`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c00a2ef6`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c00ddfbf`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c00a2ef6`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c00ddfbf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00a2fa3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00a2fa3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00a2e4a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00a2e4a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a2f26`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a2faf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ddff5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a2f26`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a2faf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ddff5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a2e32`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a2ee3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00ddfac`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a2e32`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a2ee3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00ddfac`

## pseudocode

```c
__int64 __fastcall UlpCreateRequestQueue(
        struct _RTL_DYNAMIC_HASH_TABLE *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        HANDLE Handle,
        _QWORD *a8)
{
  _QWORD *v8; // rsi
  PVOID *p_Directory; // rsi
  int Consumer; // edi
  _QWORD *v14; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE *v15; // r13
  struct _RTL_DYNAMIC_HASH_TABLE **v16; // rax
  struct _RTL_DYNAMIC_HASH_TABLE **v17; // rcx
  PVOID v18; // rdx
  void *v20; // rbx
  PVOID P; // [rsp+68h] [rbp-18h] BYREF
  PVOID v22[2]; // [rsp+70h] [rbp-10h] BYREF

  v8 = 0;
  v22[0] = 0;
  P = 0;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
  {
    WPP_SF_qllSqqLqq(
      HIWORD(a2),
      a2,
      (_DWORD)a1,
      (unsigned __int16)a2,
      SBYTE2(a2),
      *(_QWORD *)(a3 + 8),
      a4,
      a5,
      a6,
      (char)Handle,
      (char)a8);
    v8 = P;
  }
  *a8 = 0;
  if ( a6 - 1 > 1 )
    goto LABEL_21;
  if ( !*(_QWORD *)(a3 + 8) )
  {
    if ( a6 == 1 )
    {
LABEL_6:
      KeEnterCriticalRegion();
      p_Directory = &a1[98].Directory;
      ExAcquirePushLockExclusiveEx(&a1[98].Directory, 0);
      if ( *(_QWORD *)(a3 + 8) && UlpFindRequestQueue(a1, a3, 1) )
      {
        Consumer = -1073741771;
      }
      else
      {
        Consumer = UlListenerObjectAccessCheck(a5, L"RequestQueue");
        if ( Consumer >= 0 )
        {
          Consumer = UlpAllocateRequestQueue(a1, a2, a3, a4, &P);
          if ( Consumer >= 0 )
          {
            Consumer = UlpAllocateConsumer(a5, a6, v22);
            if ( Consumer >= 0 )
            {
              v14 = P;
              if ( *((_BYTE *)P + 136) )
              {
                Consumer = UlCreateAutoServerSession(Handle);
                if ( Consumer < 0 )
                  goto LABEL_16;
                v14 = P;
              }
              KeEnterCriticalRegion();
              ExAcquireCacheAwarePushLockExclusive(v14[35]);
              UlpAttachConsumerToRequestQueue(P, v22[0]);
              ExReleaseCacheAwarePushLockExclusive(*((_QWORD *)P + 35));
              KeLeaveCriticalRegion();
              RtlInsertEntryHashTable(a1 + 99, (PRTL_DYNAMIC_HASH_TABLE_ENTRY)P + 7, 1u, 0);
              v15 = a1 + 100;
              v16 = (struct _RTL_DYNAMIC_HASH_TABLE **)((char *)P + 192);
              v17 = *(struct _RTL_DYNAMIC_HASH_TABLE ***)&v15->TableSize;
              if ( *v17 != v15 )
                __fastfail(3u);
              *v16 = v15;
              v16[1] = (struct _RTL_DYNAMIC_HASH_TABLE *)v17;
              *v17 = (struct _RTL_DYNAMIC_HASH_TABLE *)v16;
              v18 = v22[0];
              *(_QWORD *)&v15->TableSize = v16;
              *a8 = v18;
              if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x200000) != 0 )
                WPP_SF_qZqL(71, (_DWORD)v18, (_DWORD)P, (_DWORD)P + 152, (char)v18, a6);
            }
          }
        }
      }
LABEL_16:
      ExReleasePushLockExclusiveEx(p_Directory, 0);
      KeLeaveCriticalRegion();
      if ( Consumer >= 0 )
        goto LABEL_17;
      goto LABEL_20;
    }
LABEL_21:
    Consumer = -1073741811;
    goto LABEL_22;
  }
  Consumer = UlpValidateRequestQueueName((PCUNICODE_STRING)a3);
  if ( Consumer >= 0 )
    goto LABEL_6;
LABEL_20:
  v8 = P;
LABEL_22:
  if ( v8 )
  {
    KeEnterCriticalRegion();
    ExAcquireCacheAwarePushLockExclusive(v8[35]);
    v20 = (void *)*((_QWORD *)P + 16);
    *((_QWORD *)P + 16) = 0;
    ExReleaseCacheAwarePushLockExclusive(*((_QWORD *)P + 35));
    KeLeaveCriticalRegion();
    if ( v20 )
      UlDeleteAutoServerSession(v20);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)P, 0xFFFFFFFF) == 1 )
      UlFreeRequestQueue(P);
  }
  if ( v22[0] )
  {
    _InterlockedDecrement((volatile signed __int32 *)v22[0]);
    UlpFreeConsumer(v22[0]);
  }
LABEL_17:
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qD(72, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, *a8, (unsigned int)Consumer);
  return (unsigned int)Consumer;
}

```

## disassembly

```asm
0x1c00a2db0  mov     rax, rsp
0x1c00a2db3  mov     [rax+8], rbx
0x1c00a2db7  mov     [rax+10h], rsi
0x1c00a2dbb  mov     [rax+18h], rdi
0x1c00a2dbf  mov     [rax+20h], r9
0x1c00a2dc3  push    rbp
0x1c00a2dc4  push    r12
0x1c00a2dc6  push    r13
0x1c00a2dc8  push    r14
0x1c00a2dca  push    r15
0x1c00a2dcc  mov     rbp, rsp
0x1c00a2dcf  sub     rsp, 80h
0x1c00a2dd6  xor     esi, esi
0x1c00a2dd8  mov     dword ptr [rbp+Signature], 1
0x1c00a2ddf  and     [rbp+var_10], rsi
0x1c00a2de3  mov     r10, r9
0x1c00a2de6  mov     [rbp+P], rsi
0x1c00a2dea  mov     r14, r8
0x1c00a2ded  mov     ebx, edx
0x1c00a2def  mov     r13, rcx
0x1c00a2df2  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a2df8  mov     r15d, [rbp+arg_28]
0x1c00a2dfc  mov     r12, [rbp+arg_20]
0x1c00a2e00  mov     rdi, [rbp+arg_38]
0x1c00a2e04  test    al, al
0x1c00a2e06  js      loc_1C00DDF5E
0x1c00a2e0c  and     qword ptr [rdi], 0
0x1c00a2e10  lea     eax, [r15-1]
0x1c00a2e14  cmp     eax, 1
0x1c00a2e17  ja      loc_1C00DDFA2
0x1c00a2e1d  cmp     qword ptr [r14+8], 0
0x1c00a2e22  jnz     loc_1C00DE046
0x1c00a2e28  cmp     r15d, 1
0x1c00a2e2c  jnz     loc_1C00DDFA2
0x1c00a2e32  call    cs:__imp_KeEnterCriticalRegion
0x1c00a2e39  nop     dword ptr [rax+rax+00h]
0x1c00a2e3e  lea     rsi, [r13+0F70h]
0x1c00a2e45  xor     edx, edx
0x1c00a2e47  mov     rcx, rsi
0x1c00a2e4a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00a2e51  nop     dword ptr [rax+rax+00h]
0x1c00a2e56  cmp     qword ptr [r14+8], 0
0x1c00a2e5b  jnz     loc_1C00DE061
0x1c00a2e61  lea     rdx, aRequestqueue; "RequestQueue"
0x1c00a2e68  mov     rcx, r12
0x1c00a2e6b  call    UlListenerObjectAccessCheck
0x1c00a2e70  mov     edi, eax
0x1c00a2e72  test    eax, eax
0x1c00a2e74  js      loc_1C00A2F9E
0x1c00a2e7a  mov     r9, [rbp+arg_18]
0x1c00a2e7e  lea     rax, [rbp+P]
0x1c00a2e82  mov     r8, r14
0x1c00a2e85  mov     [rsp+80h+var_60], rax
0x1c00a2e8a  mov     edx, ebx
0x1c00a2e8c  mov     rcx, r13
0x1c00a2e8f  call    UlpAllocateRequestQueue
0x1c00a2e94  mov     edi, eax
0x1c00a2e96  test    eax, eax
0x1c00a2e98  js      loc_1C00A2F9E
0x1c00a2e9e  lea     r8, [rbp+var_10]
0x1c00a2ea2  mov     edx, r15d
0x1c00a2ea5  mov     rcx, r12
0x1c00a2ea8  call    UlpAllocateConsumer
0x1c00a2ead  mov     edi, eax
0x1c00a2eaf  test    eax, eax
0x1c00a2eb1  js      loc_1C00A2F9E
0x1c00a2eb7  mov     rbx, [rbp+P]
0x1c00a2ebb  cmp     byte ptr [rbx+88h], 0
0x1c00a2ec2  jz      short loc_1C00A2EE3
0x1c00a2ec4  mov     dl, [r12+40h]
0x1c00a2ec9  mov     r8, rbx
0x1c00a2ecc  mov     rcx, [rbp+Handle]; Handle
0x1c00a2ed0  call    UlCreateAutoServerSession
0x1c00a2ed5  mov     edi, eax
0x1c00a2ed7  test    eax, eax
0x1c00a2ed9  js      loc_1C00A2F9E
0x1c00a2edf  mov     rbx, [rbp+P]
0x1c00a2ee3  call    cs:__imp_KeEnterCriticalRegion
0x1c00a2eea  nop     dword ptr [rax+rax+00h]
0x1c00a2eef  mov     rcx, [rbx+118h]
0x1c00a2ef6  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c00a2efd  nop     dword ptr [rax+rax+00h]
0x1c00a2f02  mov     rdx, [rbp+var_10]
0x1c00a2f06  mov     rcx, [rbp+P]
0x1c00a2f0a  call    UlpAttachConsumerToRequestQueue
0x1c00a2f0f  mov     rcx, [rbp+P]
0x1c00a2f13  mov     rcx, [rcx+118h]
0x1c00a2f1a  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c00a2f21  nop     dword ptr [rax+rax+00h]
0x1c00a2f26  call    cs:__imp_KeLeaveCriticalRegion
0x1c00a2f2d  nop     dword ptr [rax+rax+00h]
0x1c00a2f32  mov     rdx, [rbp+P]
0x1c00a2f36  lea     rcx, [r13+0F78h]; HashTable
0x1c00a2f3d  mov     r8d, dword ptr [rbp+Signature]; Signature
0x1c00a2f41  add     rdx, 0A8h; Entry
0x1c00a2f48  xor     r9d, r9d; Context
0x1c00a2f4b  call    cs:__imp_RtlInsertEntryHashTable
0x1c00a2f52  nop     dword ptr [rax+rax+00h]
0x1c00a2f57  mov     rax, [rbp+P]
0x1c00a2f5b  add     r13, 0FA0h
0x1c00a2f62  add     rax, 0C0h
0x1c00a2f68  mov     rcx, [r13+8]
0x1c00a2f6c  cmp     [rcx], r13
0x1c00a2f6f  jnz     loc_1C00DE083
0x1c00a2f75  mov     [rax], r13
0x1c00a2f78  mov     [rax+8], rcx
0x1c00a2f7c  mov     [rcx], rax
0x1c00a2f7f  mov     rdx, [rbp+var_10]
0x1c00a2f83  mov     [r13+8], rax
0x1c00a2f87  mov     rax, [rbp+arg_38]
0x1c00a2f8b  mov     [rax], rdx
0x1c00a2f8e  test    dword ptr cs:WPP_MAIN_CB.Queue, 200000h
0x1c00a2f98  jnz     loc_1C00DE08A
0x1c00a2f9e  xor     edx, edx
0x1c00a2fa0  mov     rcx, rsi
0x1c00a2fa3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00a2faa  nop     dword ptr [rax+rax+00h]
0x1c00a2faf  call    cs:__imp_KeLeaveCriticalRegion
0x1c00a2fb6  nop     dword ptr [rax+rax+00h]
0x1c00a2fbb  test    edi, edi
0x1c00a2fbd  js      short loc_1C00A2FF1
0x1c00a2fbf  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a2fc5  test    al, al
0x1c00a2fc7  js      loc_1C00DE0AF
0x1c00a2fcd  lea     r11, [rsp+80h+var_s0]
0x1c00a2fd5  mov     eax, edi
0x1c00a2fd7  mov     rbx, [r11+30h]
0x1c00a2fdb  mov     rsi, [r11+38h]
0x1c00a2fdf  mov     rdi, [r11+40h]
0x1c00a2fe3  mov     rsp, r11
0x1c00a2fe6  pop     r15
0x1c00a2fe8  pop     r14
0x1c00a2fea  pop     r13
0x1c00a2fec  pop     r12
0x1c00a2fee  pop     rbp
0x1c00a2fef  retn
0x1c00a2ff1  mov     rsi, [rbp+P]
0x1c00a2ff5  jmp     loc_1C00DDFA7
0x1c00ddf5e  mov     rax, [rbp+Handle]
0x1c00ddf62  mov     ecx, ebx
0x1c00ddf64  mov     [rsp+80h+var_30], rdi
0x1c00ddf69  mov     [rsp+80h+var_38], rax
0x1c00ddf6e  mov     rax, [r8+8]
0x1c00ddf72  mov     r8, r13
0x1c00ddf75  mov     [rsp+80h+var_40], r15d
0x1c00ddf7a  mov     [rsp+80h+var_48], r12
0x1c00ddf7f  mov     [rsp+80h+var_50], r10
0x1c00ddf84  shr     ecx, 10h
0x1c00ddf87  mov     [rsp+80h+var_58], rax
0x1c00ddf8c  movzx   r9d, bx
0x1c00ddf90  mov     dword ptr [rsp+80h+var_60], ecx
0x1c00ddf94  call    WPP_SF_qllSqqLqq
0x1c00ddf99  mov     rsi, [rbp+P]
0x1c00ddf9d  jmp     loc_1C00A2E0C
0x1c00ddfa2  mov     edi, 0C000000Dh
0x1c00ddfa7  test    rsi, rsi
0x1c00ddfaa  jz      short loc_1C00DE027
0x1c00ddfac  call    cs:__imp_KeEnterCriticalRegion
0x1c00ddfb3  nop     dword ptr [rax+rax+00h]
0x1c00ddfb8  mov     rcx, [rsi+118h]
0x1c00ddfbf  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c00ddfc6  nop     dword ptr [rax+rax+00h]
0x1c00ddfcb  mov     rax, [rbp+P]
0x1c00ddfcf  mov     rbx, [rax+80h]
0x1c00ddfd6  and     qword ptr [rax+80h], 0
0x1c00ddfde  mov     rcx, [rbp+P]
0x1c00ddfe2  mov     rcx, [rcx+118h]
0x1c00ddfe9  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c00ddff0  nop     dword ptr [rax+rax+00h]
0x1c00ddff5  call    cs:__imp_KeLeaveCriticalRegion
0x1c00ddffc  nop     dword ptr [rax+rax+00h]
0x1c00de001  test    rbx, rbx
0x1c00de004  jz      short loc_1C00DE00E
0x1c00de006  mov     rcx, rbx
0x1c00de009  call    UlDeleteAutoServerSession
0x1c00de00e  mov     rax, [rbp+P]
0x1c00de012  or      ecx, 0FFFFFFFFh
0x1c00de015  lock xadd [rax], ecx
0x1c00de019  cmp     ecx, 1
0x1c00de01c  jnz     short loc_1C00DE027
0x1c00de01e  mov     rcx, [rbp+P]; P
0x1c00de022  call    UlFreeRequestQueue
0x1c00de027  mov     rax, [rbp+var_10]
0x1c00de02b  test    rax, rax
0x1c00de02e  jz      loc_1C00A2FBF
0x1c00de034  lock dec dword ptr [rax]
0x1c00de037  mov     rcx, [rbp+var_10]; P
0x1c00de03b  call    UlpFreeConsumer
0x1c00de040  nop
0x1c00de041  jmp     loc_1C00A2FBF
0x1c00de046  lea     rdx, [rbp+Signature]
0x1c00de04a  mov     rcx, r14; String
0x1c00de04d  call    UlpValidateRequestQueueName
0x1c00de052  mov     edi, eax
0x1c00de054  test    eax, eax
0x1c00de056  js      loc_1C00A2FF1
0x1c00de05c  jmp     loc_1C00A2E32
0x1c00de061  mov     r8d, dword ptr [rbp+Signature]
0x1c00de065  mov     rdx, r14
0x1c00de068  mov     rcx, r13
0x1c00de06b  call    UlpFindRequestQueue
0x1c00de070  test    rax, rax
0x1c00de073  jz      loc_1C00A2E61
0x1c00de079  mov     edi, 0C0000035h
0x1c00de07e  jmp     loc_1C00A2F9E
0x1c00de083  mov     ecx, 3
0x1c00de088  int     29h; Win8: RtlFailFast(ecx)
0x1c00de08a  mov     r8, [rbp+P]
0x1c00de08e  mov     ecx, 47h ; 'G'
0x1c00de093  mov     dword ptr [rsp+80h+var_58], r15d
0x1c00de098  mov     [rsp+80h+var_60], rdx
0x1c00de09d  lea     r9, [r8+98h]
0x1c00de0a4  call    WPP_SF_qZqL
0x1c00de0a9  nop
0x1c00de0aa  jmp     loc_1C00A2F9E
0x1c00de0af  mov     rax, [rbp+arg_38]
0x1c00de0b3  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00de0ba  mov     ecx, 48h ; 'H'
0x1c00de0bf  mov     r9d, edi
0x1c00de0c2  mov     r8, [rax]
0x1c00de0c5  call    WPP_SF_qD
0x1c00de0ca  nop
0x1c00de0cb  jmp     loc_1C00A2FCD
```
