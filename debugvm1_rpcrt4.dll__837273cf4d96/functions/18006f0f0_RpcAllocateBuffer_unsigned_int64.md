# RpcAllocateBuffer(unsigned __int64)

- ea: `0x18006f0f0`
- end: `0x18006f430`
- name: `?RpcAllocateBuffer@@YAPEAX_K@Z`
- size: `832`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001ed04`
- `0x180021ce0`
- `0x180021e18`
- `0x180021e70`
- `0x18006f0f0`
- `0x1800ca140`

## import_xrefs

- `ntdll!RtlGetCurrentProcessorNumber` at `0x18006f1f0`
- `ntdll!RtlGetCurrentProcessorNumber` at `0x18006f1f0`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18006f219`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18006f219`

## pseudocode

```c
struct _SLIST_ENTRY *__fastcall RpcAllocateBuffer(unsigned __int64 a1)
{
  unsigned __int64 v1; // rdi
  __int64 v2; // r14
  unsigned int i; // ebx
  PSLIST_ENTRY v4; // rax
  PSLIST_ENTRY v5; // rbx
  struct BCACHE *v7; // r15
  ULONG CurrentProcessorNumber; // eax
  union _SLIST_HEADER *v9; // rcx
  PSLIST_ENTRY v10; // rax
  __int64 v11; // r8
  PSLIST_ENTRY v12; // r15
  unsigned int j; // ecx
  SIZE_T v14; // rsi
  _DWORD *v15; // rax
  __int64 v16; // r8
  _DWORD *v17; // rdi
  unsigned int k; // ecx
  int v19; // [rsp+30h] [rbp-81h]
  int v20; // [rsp+38h] [rbp-79h]
  char v21; // [rsp+48h] [rbp-69h] BYREF
  char v22; // [rsp+50h] [rbp-61h] BYREF
  SIZE_T v23; // [rsp+58h] [rbp-59h] BYREF
  __int64 v24; // [rsp+60h] [rbp-51h] BYREF
  _QWORD v25[2]; // [rsp+68h] [rbp-49h] BYREF
  _BYTE v26[16]; // [rsp+78h] [rbp-39h] BYREF
  char *v27; // [rsp+88h] [rbp-29h]
  __int64 v28; // [rsp+90h] [rbp-21h]
  char *v29; // [rsp+98h] [rbp-19h]
  __int64 v30; // [rsp+A0h] [rbp-11h]
  SIZE_T *v31; // [rsp+A8h] [rbp-9h]
  __int64 v32; // [rsp+B0h] [rbp-1h]
  __int64 *v33; // [rsp+B8h] [rbp+7h]
  __int64 v34; // [rsp+C0h] [rbp+Fh]
  SIZE_T *v35; // [rsp+C8h] [rbp+17h]
  __int64 v36; // [rsp+D0h] [rbp+1Fh]

  v1 = ((_DWORD)a1 + 31) & 0xFFFFFFF0;
  v2 = 0;
  if ( v1 < a1 )
    return 0;
  if ( (_DWORD)gBCacheMode != 1 )
  {
    for ( i = 0; i < 5; ++i )
    {
      if ( (unsigned int)dword_1800E2804[2 * i] >= v1 )
      {
        v7 = gBufferCache;
        CurrentProcessorNumber = RtlGetCurrentProcessorNumber();
        if ( *(_QWORD *)v7
          && (v9 = (union _SLIST_HEADER *)(*(_QWORD *)v7
                                         + 16 * ((int)i + 8LL * (CurrentProcessorNumber % *((_DWORD *)v7 + 2))))) != 0
          && (v10 = InterlockedPopEntrySList(v9), (v12 = v10) != 0) )
        {
          LODWORD(v10->Next) = i + 1;
          if ( dword_1800F9624 )
          {
            for ( j = 0; j < 4; ++j )
            {
              if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[j] == 98 )
                return v12 + 2;
            }
            if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
            {
              v25[0] = v1;
              v27 = &v21;
              v24 = 0;
              v29 = &v22;
              v23 = (SIZE_T)v10;
              v31 = &v23;
              v22 = 66;
              v33 = &v24;
              v35 = v25;
              v21 = 98;
              v28 = 1;
              v30 = 1;
              v32 = 8;
              v34 = 8;
              v36 = 8;
              McGenEventWrite_EtwEventWriteTransfer(&RpcEtwGuid_Context, (__int64)RPCLogEvent, v11, 6, (__int64)v26);
            }
          }
          return v12 + 2;
        }
        else
        {
          v14 = (unsigned int)dword_1800E2804[2 * i] + 32LL;
          v15 = AllocWrapper(v14);
          v17 = v15;
          if ( v15 )
          {
            *v15 = i + 1;
            if ( dword_1800F9624 )
            {
              for ( k = 0; k < 4; ++k )
              {
                if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[k] == 98 )
                  return (struct _SLIST_ENTRY *)(v17 + 8);
              }
              if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
              {
                v23 = v14;
                v27 = &v22;
                v24 = 0;
                v29 = &v21;
                v25[0] = v15;
                v31 = v25;
                v21 = 66;
                v33 = &v24;
                v35 = &v23;
                v22 = 98;
                v28 = 1;
                v30 = 1;
                v32 = 8;
                v34 = 8;
                v36 = 8;
                McGenEventWrite_EtwEventWriteTransfer(&RpcEtwGuid_Context, (__int64)RPCLogEvent, v16, 6, (__int64)v26);
              }
            }
            return (struct _SLIST_ENTRY *)(v17 + 8);
          }
          else
          {
            LogEvent(0x62u, 0x58u, 0, 0, v14, v19, v20);
            return 0;
          }
        }
      }
    }
  }
  if ( v1 + 32 >= v1 )
  {
    if ( (_DWORD)gBCacheMode == 1 || !gBufferCache2 )
      v4 = (PSLIST_ENTRY)AllocWrapper(v1 + 32);
    else
      v4 = BCache2::Alloc((BCache2 *)(unsigned int)gBCacheMode, v1 + 32);
    v5 = v4;
    if ( v4 )
    {
      LODWORD(v4->Next) = -1;
      v4[1].Next = (struct _SLIST_ENTRY *)(v1 + 32);
      LogEvent(0x62u, 0x42u, v4, 0, v1, v19, v20);
      return v5 + 2;
    }
    else
    {
      LogEvent(0x62u, 0x58u, 0, 0, v1, v19, v20);
    }
  }
  return (struct _SLIST_ENTRY *)v2;
}

```

## disassembly

```asm
0x18006f0f0  mov     r11, rsp
0x18006f0f3  push    rbp
0x18006f0f4  push    rdi
0x18006f0f5  push    r14
0x18006f0f7  lea     rbp, [r11-5Fh]
0x18006f0fb  sub     rsp, 0F0h
0x18006f102  mov     rax, cs:__security_cookie
0x18006f109  xor     rax, rsp
0x18006f10c  mov     [rbp+57h+var_30], rax
0x18006f110  lea     edi, [rcx+1Fh]
0x18006f113  mov     eax, 0FFFFFFF0h
0x18006f118  and     rdi, rax
0x18006f11b  xor     r14d, r14d
0x18006f11e  cmp     rdi, rcx
0x18006f121  jb      loc_18006F3FD
0x18006f127  mov     ecx, cs:?gBCacheMode@@3W4BCacheMode@@A; this
0x18006f12d  mov     [r11+10h], rbx
0x18006f131  mov     [r11+18h], rsi
0x18006f135  mov     [r11-20h], r12
0x18006f139  cmp     ecx, 1
0x18006f13c  jz      short loc_18006F166
0x18006f13e  mov     ebx, r14d
0x18006f141  lea     r12, __ImageBase
0x18006f148  cmp     ebx, 5
0x18006f14b  jnb     short loc_18006F166
0x18006f14d  movsxd  rsi, ebx
0x18006f150  mov     eax, ds:rva dword_1800E2804[r12+rsi*8]
0x18006f158  cmp     rax, rdi
0x18006f15b  jnb     short loc_18006F161
0x18006f15d  inc     ebx
0x18006f15f  jmp     short loc_18006F148
0x18006f161  cmp     ebx, 0FFFFFFFFh
0x18006f164  jnz     short loc_18006F1E1
0x18006f166  lea     rsi, [rdi+20h]
0x18006f16a  cmp     rsi, rdi
0x18006f16d  jb      short loc_18006F1AE
0x18006f16f  cmp     ecx, 1
0x18006f172  jnz     loc_18006F26C
0x18006f178  mov     rcx, rsi; dwBytes
0x18006f17b  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18006f180  xor     r9d, r9d; void *
0x18006f183  mov     [rsp+20h], rdi; unsigned __int64
0x18006f188  mov     rbx, rax
0x18006f18b  mov     cl, 62h ; 'b'; unsigned __int8
0x18006f18d  test    rax, rax
0x18006f190  jz      loc_18006F421
0x18006f196  mov     r8, rax; void *
0x18006f199  mov     dword ptr [rax], 0FFFFFFFFh
0x18006f19f  mov     dl, 42h ; 'B'; unsigned __int8
0x18006f1a1  mov     [rax+10h], rsi
0x18006f1a5  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x18006f1aa  lea     r14, [rbx+20h]
0x18006f1ae  mov     rax, r14
0x18006f1b1  mov     rsi, [rsp+100h+arg_10]
0x18006f1b9  mov     rbx, [rsp+100h+arg_8]
0x18006f1c1  mov     r12, [rsp+0E8h]
0x18006f1c9  mov     rcx, [rbp+57h+var_30]
0x18006f1cd  xor     rcx, rsp; StackCookie
0x18006f1d0  call    __security_check_cookie
0x18006f1d5  add     rsp, 0F0h
0x18006f1dc  pop     r14
0x18006f1de  pop     rdi
0x18006f1df  pop     rbp
0x18006f1e0  retn
0x18006f1e1  mov     [rsp+100h+var_20], r15
0x18006f1e9  mov     r15, cs:?gBufferCache@@3PEAVBCACHE@@EA; BCACHE * gBufferCache
0x18006f1f0  call    cs:__imp_RtlGetCurrentProcessorNumber
0x18006f1f6  mov     r8, [r15]
0x18006f1f9  test    r8, r8
0x18006f1fc  jz      loc_18006F311
0x18006f202  xor     edx, edx
0x18006f204  div     dword ptr [r15+8]
0x18006f208  lea     rcx, [rsi+rdx*8]
0x18006f20c  shl     rcx, 4
0x18006f210  add     rcx, r8; ListHead
0x18006f213  jz      loc_18006F311
0x18006f219  call    cs:__imp_InterlockedPopEntrySList
0x18006f21f  mov     r15, rax
0x18006f222  test    rax, rax
0x18006f225  jz      loc_18006F311
0x18006f22b  inc     ebx
0x18006f22d  mov     [rax], ebx
0x18006f22f  cmp     cs:dword_1800F9624, r14d
0x18006f236  jz      short loc_18006F25B
0x18006f238  mov     ecx, r14d
0x18006f23b  cmp     ecx, 4
0x18006f23e  jnb     short loc_18006F252
0x18006f240  movsxd  rax, ecx
0x18006f243  cmp     byte ptr [rax+r12+0E1808h], 62h ; 'b'
0x18006f24c  jz      short loc_18006F25B
0x18006f24e  inc     ecx
0x18006f250  jmp     short loc_18006F23B
0x18006f252  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18006f259  jnz     short loc_18006F286
0x18006f25b  lea     rax, [r15+20h]
0x18006f25f  mov     r15, [rsp+100h+var_20]
0x18006f267  jmp     loc_18006F1B1
0x18006f26c  cmp     cs:?gBufferCache2@@3PEAVBCache2@@EA, r14; BCache2 * gBufferCache2
0x18006f273  jz      loc_18006F178
0x18006f279  mov     rdx, rsi; unsigned __int64
0x18006f27c  call    ?Alloc@BCache2@@QEAAPEAX_K@Z; BCache2::Alloc(unsigned __int64)
0x18006f281  jmp     loc_18006F180
0x18006f286  lea     rax, [rbp+57h+var_C0]
0x18006f28a  mov     [rbp+57h+var_A0], rdi
0x18006f28e  mov     [rbp+57h+var_80], rax
0x18006f292  lea     rdx, RPCLogEvent
0x18006f299  lea     rax, [rbp+57h+var_B8]
0x18006f29d  mov     [rbp+57h+var_A8], r14
0x18006f2a1  mov     [rbp+57h+var_70], rax
0x18006f2a5  lea     rcx, RpcEtwGuid_Context
0x18006f2ac  lea     rax, [rbp+57h+var_B0]
0x18006f2b0  mov     [rbp+57h+var_B0], r15
0x18006f2b4  mov     [rbp+57h+var_60], rax
0x18006f2b8  mov     r9d, 6
0x18006f2be  lea     rax, [rbp+57h+var_A8]
0x18006f2c2  mov     [rbp+57h+var_B8], 42h ; 'B'
0x18006f2c6  mov     [rbp+57h+var_50], rax
0x18006f2ca  lea     rax, [rbp+57h+var_A0]
0x18006f2ce  mov     [rbp+57h+var_40], rax
0x18006f2d2  lea     rax, [rbp+57h+var_90]
0x18006f2d6  mov     [rsp+20h], rax
0x18006f2db  mov     [rbp+57h+var_C0], 62h ; 'b'
0x18006f2df  mov     [rbp+57h+var_78], 1
0x18006f2e7  mov     [rbp+57h+var_68], 1
0x18006f2ef  mov     [rbp+57h+var_58], 8
0x18006f2f7  mov     [rbp+57h+var_48], 8
0x18006f2ff  mov     [rbp+57h+var_38], 8
0x18006f307  call    McGenEventWrite_EtwEventWriteTransfer
0x18006f30c  jmp     loc_18006F25B
0x18006f311  mov     esi, ds:rva dword_1800E2804[r12+rsi*8]
0x18006f319  add     rsi, 20h ; ' '
0x18006f31d  mov     rcx, rsi; dwBytes
0x18006f320  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18006f325  mov     rdi, rax
0x18006f328  test    rax, rax
0x18006f32b  jz      loc_18006F405
0x18006f331  inc     ebx
0x18006f333  mov     [rax], ebx
0x18006f335  cmp     cs:dword_1800F9624, r14d
0x18006f33c  jz      short loc_18006F361
0x18006f33e  mov     ecx, r14d
0x18006f341  cmp     ecx, 4
0x18006f344  jnb     short loc_18006F358
0x18006f346  movsxd  rax, ecx
0x18006f349  cmp     byte ptr [rax+r12+0E1808h], 62h ; 'b'
0x18006f352  jz      short loc_18006F361
0x18006f354  inc     ecx
0x18006f356  jmp     short loc_18006F341
0x18006f358  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18006f35f  jnz     short loc_18006F372
0x18006f361  mov     r15, [rsp+100h+var_20]
0x18006f369  lea     rax, [rdi+20h]
0x18006f36d  jmp     loc_18006F1B1
0x18006f372  lea     rax, [rbp+57h+var_B8]
0x18006f376  mov     [rbp+57h+var_B0], rsi
0x18006f37a  mov     [rbp+57h+var_80], rax
0x18006f37e  lea     rdx, RPCLogEvent
0x18006f385  lea     rax, [rbp+57h+var_C0]
0x18006f389  mov     [rbp+57h+var_A8], r14
0x18006f38d  mov     [rbp+57h+var_70], rax
0x18006f391  lea     rcx, RpcEtwGuid_Context
0x18006f398  lea     rax, [rbp+57h+var_A0]
0x18006f39c  mov     [rbp+57h+var_A0], rdi
0x18006f3a0  mov     [rbp+57h+var_60], rax
0x18006f3a4  mov     r9d, 6
0x18006f3aa  lea     rax, [rbp+57h+var_A8]
0x18006f3ae  mov     [rbp+57h+var_C0], 42h ; 'B'
0x18006f3b2  mov     [rbp+57h+var_50], rax
0x18006f3b6  lea     rax, [rbp+57h+var_B0]
0x18006f3ba  mov     [rbp+57h+var_40], rax
0x18006f3be  lea     rax, [rbp+57h+var_90]
0x18006f3c2  mov     [rsp+20h], rax
0x18006f3c7  mov     [rbp+57h+var_B8], 62h ; 'b'
0x18006f3cb  mov     [rbp+57h+var_78], 1
0x18006f3d3  mov     [rbp+57h+var_68], 1
0x18006f3db  mov     [rbp+57h+var_58], 8
0x18006f3e3  mov     [rbp+57h+var_48], 8
0x18006f3eb  mov     [rbp+57h+var_38], 8
0x18006f3f3  call    McGenEventWrite_EtwEventWriteTransfer
0x18006f3f8  jmp     loc_18006F361
0x18006f3fd  mov     rax, r14
0x18006f400  jmp     loc_18006F1C9
0x18006f405  xor     r9d, r9d; void *
0x18006f408  mov     [rsp+20h], rsi; unsigned __int64
0x18006f40d  xor     r8d, r8d; void *
0x18006f410  mov     dl, 58h ; 'X'; unsigned __int8
0x18006f412  mov     cl, 62h ; 'b'; unsigned __int8
0x18006f414  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x18006f419  mov     rax, r14
0x18006f41c  jmp     loc_18006F25F
0x18006f421  xor     r8d, r8d; void *
0x18006f424  mov     dl, 58h ; 'X'; unsigned __int8
0x18006f426  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x18006f42b  jmp     loc_18006F1AE
```
