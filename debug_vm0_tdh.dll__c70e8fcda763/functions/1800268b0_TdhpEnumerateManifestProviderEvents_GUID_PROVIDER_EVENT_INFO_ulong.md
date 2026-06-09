# TdhpEnumerateManifestProviderEvents(_GUID *,_PROVIDER_EVENT_INFO *,ulong *)

- ea: `0x1800268b0`
- end: `0x180026adc`
- name: `?TdhpEnumerateManifestProviderEvents@@YAKPEAU_GUID@@PEAU_PROVIDER_EVENT_INFO@@PEAK@Z`
- size: `556`
- prototype: `__int64 __fastcall(struct _GUID *, struct _PROVIDER_EVENT_INFO *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800247a0`

## callees

- `0x1800064d0`
- `0x1800076e0`
- `0x180018198`
- `0x1800268b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002690a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800269e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002690a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800269e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002692b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180026ab4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002692b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180026ab4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026934`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026934`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800269da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800269da`

## pseudocode

```c
__int64 __fastcall TdhpEnumerateManifestProviderEvents(
        struct _GUID *a1,
        struct _PROVIDER_EVENT_INFO *a2,
        unsigned int *a3)
{
  __int64 v3; // rsi
  RTL_SRWLOCK *v4; // rax
  RTL_SRWLOCK *v5; // rbx
  unsigned int TraceEventInfoArray; // edi
  ULONG v8; // ebp
  char v9; // r15
  unsigned int v10; // r13d
  __int64 v11; // r9
  int v12; // edx
  unsigned int v13; // esi
  ULONG v14; // r8d
  __int64 v15; // r9
  __int64 v16; // r11
  bool v17; // zf
  __int64 v18; // rdx
  __int64 v19; // rax
  int v20; // [rsp+50h] [rbp-58h] BYREF
  void *v21; // [rsp+58h] [rbp-50h] BYREF
  int v25; // [rsp+C8h] [rbp+20h] BYREF

  v3 = 0;
  v25 = 0;
  v21 = 0;
  v20 = 0;
  v4 = (RTL_SRWLOCK *)TdhpCacheLockEntry(g_TdhCache, a1);
  v5 = v4;
  if ( !v4 )
    return 8;
  TraceEventInfoArray = 1168;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  AcquireSRWLockShared(v4);
  do
  {
    if ( v5[3 * v3 + 3].Ptr )
    {
      v8 += LODWORD(v5[3 * v3 + 4].Ptr);
      v10 = v3;
      TraceEventInfoArray = 0;
      goto LABEL_17;
    }
    ReleaseSRWLockShared(v5);
    AcquireSRWLockExclusive(v5);
    if ( !v5[3 * v3 + 3].Ptr )
    {
      LOBYTE(v11) = v3;
      TraceEventInfoArray = TdhpAllocAndGetTraceEventInfoArray(0, 0, a1, v11, 0, &v25, &v21, &v20, 0, 0);
      switch ( TraceEventInfoArray )
      {
        case 0u:
          v10 = v3;
          v12 = v25;
          v8 += v25;
          v5[3 * v3 + 3].Ptr = v21;
          HIDWORD(v5[3 * v3 + 4].Ptr) = v20;
          LODWORD(v5[3 * v3 + 4].Ptr) = v12;
          goto LABEL_14;
        case 0xC007FF01:
          TraceEventInfoArray = 4306;
          if ( (unsigned int)v3 <= v10 + 10 )
            goto LABEL_14;
          break;
        case 0xC007FF00:
          TraceEventInfoArray = 1168;
          break;
      }
      v9 = 1;
    }
LABEL_14:
    ReleaseSRWLockExclusive(v5);
    AcquireSRWLockShared(v5);
    if ( v9 )
      break;
LABEL_17:
    v3 = (unsigned int)(v3 + 1);
  }
  while ( (unsigned int)v3 < 0x100 );
  if ( (TraceEventInfoArray == 1168 || TraceEventInfoArray == 4306) && v8 )
  {
    TraceEventInfoArray = 0;
    goto LABEL_23;
  }
  if ( !TraceEventInfoArray )
  {
LABEL_23:
    v13 = 16 * v8 + 8;
    if ( v13 > *a3 )
    {
      TraceEventInfoArray = 122;
    }
    else
    {
      v14 = 0;
      a2->Reserved = 0;
      v15 = 0;
      do
      {
        if ( v5[3 * v15 + 3].Ptr )
        {
          v16 = 0;
          if ( LODWORD(v5[3 * v15 + 4].Ptr) )
          {
            while ( 1 )
            {
              v17 = v14 == v8;
              if ( v14 >= v8 )
                break;
              v18 = *((_QWORD *)v5[3 * v15 + 3].Ptr + v16);
              v16 = (unsigned int)(v16 + 1);
              v19 = v14++;
              a2->EventDescriptorsArray[v19] = *(EVENT_DESCRIPTOR *)(v18 + 32);
              if ( (unsigned int)v16 >= LODWORD(v5[3 * v15 + 4].Ptr) )
                goto LABEL_29;
            }
          }
          else
          {
LABEL_29:
            v17 = v14 == v8;
          }
          if ( v17 )
            break;
        }
        v15 = (unsigned int)(v15 + 1);
      }
      while ( (unsigned int)v15 <= v10 );
      a2->NumberOfEvents = v14;
    }
    *a3 = v13;
  }
  ReleaseSRWLockShared(v5);
  TdhpCacheFreeEntry(g_TdhCache, v5);
  return TraceEventInfoArray;
}

```

## disassembly

```asm
0x1800268b0  mov     rax, rsp
0x1800268b3  mov     [rax+18h], r8
0x1800268b7  mov     [rax+10h], rdx
0x1800268bb  mov     [rax+8], rcx
0x1800268bf  push    rbx
0x1800268c0  push    rbp
0x1800268c1  push    rsi
0x1800268c2  push    rdi
0x1800268c3  push    r12
0x1800268c5  push    r13
0x1800268c7  push    r14
0x1800268c9  push    r15
0x1800268cb  sub     rsp, 68h
0x1800268cf  xor     esi, esi
0x1800268d1  mov     rdx, rcx
0x1800268d4  mov     rcx, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; TDH_CACHE * g_TdhCache
0x1800268db  mov     [rax+20h], esi
0x1800268de  mov     [rax-50h], rsi
0x1800268e2  mov     [rax-58h], esi
0x1800268e5  call    TdhpCacheLockEntry
0x1800268ea  mov     rbx, rax
0x1800268ed  test    rax, rax
0x1800268f0  jnz     short loc_1800268FA
0x1800268f2  lea     eax, [rsi+8]
0x1800268f5  jmp     loc_180026ACB
0x1800268fa  mov     rcx, rbx; SRWLock
0x1800268fd  mov     edi, 490h
0x180026902  mov     ebp, esi
0x180026904  mov     r15b, sil
0x180026907  mov     r13d, esi
0x18002690a  call    cs:__imp_AcquireSRWLockShared
0x180026910  mov     r12, [rsp+0A8h+arg_0]
0x180026918  lea     r14, [rsi+rsi*2]
0x18002691c  cmp     qword ptr [rbx+r14*8+18h], 0
0x180026922  jnz     loc_1800269F0
0x180026928  mov     rcx, rbx; SRWLock
0x18002692b  call    cs:__imp_ReleaseSRWLockShared
0x180026931  mov     rcx, rbx; SRWLock
0x180026934  call    cs:__imp_AcquireSRWLockExclusive
0x18002693a  xor     ecx, ecx
0x18002693c  cmp     [rbx+r14*8+18h], rcx
0x180026941  jnz     loc_1800269D7
0x180026947  mov     [rsp+0A8h+var_60], rcx
0x18002694c  lea     rax, [rsp+0A8h+var_58]
0x180026951  mov     [rsp+0A8h+var_68], rcx
0x180026956  mov     r9b, sil
0x180026959  mov     [rsp+0A8h+var_70], rax
0x18002695e  mov     r8, r12
0x180026961  lea     rax, [rsp+0A8h+var_50]
0x180026966  xor     edx, edx
0x180026968  mov     [rsp+0A8h+var_78], rax
0x18002696d  lea     rax, [rsp+0A8h+arg_18]
0x180026975  mov     [rsp+0A8h+var_80], rax
0x18002697a  mov     [rsp+0A8h+var_88], ecx
0x18002697e  call    TdhpAllocAndGetTraceEventInfoArray
0x180026983  mov     edi, eax
0x180026985  test    eax, eax
0x180026987  jnz     short loc_1800269AF
0x180026989  mov     rcx, [rsp+0A8h+var_50]
0x18002698e  mov     r13d, esi
0x180026991  mov     edx, [rsp+0A8h+arg_18]
0x180026998  add     ebp, edx
0x18002699a  mov     [rbx+r14*8+18h], rcx
0x18002699f  mov     ecx, [rsp+0A8h+var_58]
0x1800269a3  mov     [rbx+r14*8+24h], ecx
0x1800269a8  mov     [rbx+r14*8+20h], edx
0x1800269ad  jmp     short loc_1800269D7
0x1800269af  cmp     edi, 0C007FF01h
0x1800269b5  jnz     short loc_1800269C6
0x1800269b7  lea     eax, [r13+0Ah]
0x1800269bb  mov     edi, 10D2h
0x1800269c0  cmp     esi, eax
0x1800269c2  jbe     short loc_1800269D7
0x1800269c4  jmp     short loc_1800269D4
0x1800269c6  cmp     edi, 0C007FF00h
0x1800269cc  mov     eax, 490h
0x1800269d1  cmovz   edi, eax
0x1800269d4  mov     r15b, 1
0x1800269d7  mov     rcx, rbx; SRWLock
0x1800269da  call    cs:__imp_ReleaseSRWLockExclusive
0x1800269e0  mov     rcx, rbx; SRWLock
0x1800269e3  call    cs:__imp_AcquireSRWLockShared
0x1800269e9  test    r15b, r15b
0x1800269ec  jnz     short loc_180026A08
0x1800269ee  jmp     short loc_1800269FA
0x1800269f0  add     ebp, [rbx+r14*8+20h]
0x1800269f5  mov     r13d, esi
0x1800269f8  xor     edi, edi
0x1800269fa  inc     esi
0x1800269fc  cmp     esi, 100h
0x180026a02  jb      loc_180026918
0x180026a08  mov     r12, [rsp+0A8h+arg_8]
0x180026a10  cmp     edi, 490h
0x180026a16  jz      short loc_180026A20
0x180026a18  cmp     edi, 10D2h
0x180026a1e  jnz     short loc_180026A28
0x180026a20  test    ebp, ebp
0x180026a22  jz      short loc_180026A28
0x180026a24  xor     edi, edi
0x180026a26  jmp     short loc_180026A30
0x180026a28  test    edi, edi
0x180026a2a  jnz     loc_180026AB1
0x180026a30  mov     r14, [rsp+0A8h+arg_10]
0x180026a38  mov     esi, ebp
0x180026a3a  shl     esi, 4
0x180026a3d  add     esi, 8
0x180026a40  cmp     esi, [r14]
0x180026a43  ja      short loc_180026AA9
0x180026a45  xor     r8d, r8d
0x180026a48  mov     dword ptr [r12+4], 0
0x180026a51  xor     r9d, r9d
0x180026a54  lea     r10, [r9+r9*2]
0x180026a58  cmp     qword ptr [rbx+r10*8+18h], 0
0x180026a5e  jz      short loc_180026A9B
0x180026a60  xor     r11d, r11d
0x180026a63  cmp     [rbx+r10*8+20h], r11d
0x180026a68  jbe     short loc_180026A96
0x180026a6a  cmp     r8d, ebp
0x180026a6d  jnb     short loc_180026A99
0x180026a6f  mov     rax, [rbx+r10*8+18h]
0x180026a74  mov     rdx, [rax+r11*8]
0x180026a78  inc     r11d
0x180026a7b  mov     eax, r8d
0x180026a7e  inc     r8d
0x180026a81  add     rax, rax
0x180026a84  movups  xmm0, xmmword ptr [rdx+20h]
0x180026a88  movdqu  xmmword ptr [r12+rax*8+8], xmm0
0x180026a8f  cmp     r11d, [rbx+r10*8+20h]
0x180026a94  jb      short loc_180026A6A
0x180026a96  cmp     r8d, ebp
0x180026a99  jz      short loc_180026AA3
0x180026a9b  inc     r9d
0x180026a9e  cmp     r9d, r13d
0x180026aa1  jbe     short loc_180026A54
0x180026aa3  mov     [r12], r8d
0x180026aa7  jmp     short loc_180026AAE
0x180026aa9  mov     edi, 7Ah ; 'z'
0x180026aae  mov     [r14], esi
0x180026ab1  mov     rcx, rbx; SRWLock
0x180026ab4  call    cs:__imp_ReleaseSRWLockShared
0x180026aba  mov     rcx, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; TDH_CACHE * g_TdhCache
0x180026ac1  mov     rdx, rbx
0x180026ac4  call    TdhpCacheFreeEntry
0x180026ac9  mov     eax, edi
0x180026acb  add     rsp, 68h
0x180026acf  pop     r15
0x180026ad1  pop     r14
0x180026ad3  pop     r13
0x180026ad5  pop     r12
0x180026ad7  pop     rdi
0x180026ad8  pop     rsi
0x180026ad9  pop     rbp
0x180026ada  pop     rbx
0x180026adb  retn
```
