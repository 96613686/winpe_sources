# CompleteAppSendsUponClose

- ea: `0x18003ec84`
- end: `0x18003ef29`
- name: `CompleteAppSendsUponClose`
- size: `677`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003c7cc`

## callees

- `0x180008250`
- `0x180024dd4`
- `0x18003ec84`
- `0x18003f28c`
- `0x18003f2e0`
- `0x1800462b0`
- `0x1800496e4`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003eec4`
- `ntdll!RtlFreeHeap` at `0x18003eec4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ecd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ed5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003eefe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ecd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ed5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003eefe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ecaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ecf3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003eda6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ecaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ecf3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003eda6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003ece4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003ece4`

## pseudocode

```c
void __fastcall CompleteAppSendsUponClose(__int64 a1, char a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  _QWORD **v5; // r14
  _QWORD *i; // rcx
  _QWORD *v7; // r15
  _QWORD *v8; // rbx
  __int64 v9; // rsi
  __int64 v10; // rdx
  __int64 v11; // r8
  _QWORD *v12; // rdx
  _QWORD *v13; // rdx
  _QWORD *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  unsigned int *v17; // rsi
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  _QWORD *v20; // rax
  int v21; // [rsp+70h] [rbp+18h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 48);
  v21 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v5 = (_QWORD **)(a1 + 400);
LABEL_2:
  for ( i = *v5; i != v5; i = v7 )
  {
    if ( *(_DWORD *)(a1 + 464) )
    {
      LeaveCriticalSection(v2);
      Sleep(0);
      EnterCriticalSection(v2);
      goto LABEL_2;
    }
    v7 = (_QWORD *)*i;
    v8 = i - 2;
    if ( (!a2 || !*((_BYTE *)v8 + 129)) && *((_DWORD *)v8 + 21) < *((_DWORD *)v8 + 20) && !*((_DWORD *)v8 + 24) )
    {
      if ( *((char *)v8 + 92) >= 0 )
      {
        *(_QWORD *)((char *)v8 + 92) = 0;
        v13 = (_QWORD *)*i;
        if ( *(_QWORD **)(*i + 8LL) != i )
          goto LABEL_33;
        v14 = (_QWORD *)i[1];
        if ( (_QWORD *)*v14 != i )
          goto LABEL_33;
        *v14 = v13;
        v13[1] = v14;
        if ( !*((_DWORD *)v8 + 9) )
        {
          v15 = v8[17];
          if ( v15 )
          {
            IndicateRedirError(a1, v15, 3221225997LL);
          }
          else
          {
            v16 = v8[1];
            if ( v16 )
              CompleteOverlappedIO(
                *(_QWORD *)(*(_QWORD *)a1 + 8LL),
                v16,
                (void *)v8[8],
                (void *)v8[9],
                a2 != 0 ? 995 : 10054,
                *((_DWORD *)v8 + 10));
          }
        }
        if ( !*((_DWORD *)v8 + 22) )
        {
          if ( *((_BYTE *)v8 + 129) )
          {
            v17 = (unsigned int *)v8[6];
            if ( (unsigned int)UseRdma(*v17) )
            {
              v18 = (_QWORD *)(a1 + 896);
              v19 = *(_QWORD *)(a1 + 896);
              if ( *(_QWORD *)(v19 + 8) != a1 + 896 )
                goto LABEL_33;
              v20 = (_QWORD *)(*((_QWORD *)v17 + 1) - 24LL);
              v20[1] = v18;
              *v20 = v19;
              *(_QWORD *)(v19 + 8) = v20;
              *v18 = v20;
            }
            else
            {
              RtlFreeHeap(SockPrivateHeap, 0, *((PVOID *)v17 + 1));
            }
            *(_DWORD *)(a1 + 128) -= *v17;
          }
          ReleaseWsaBufArray(a1, v8[6]);
          ReleaseApplicationBuffer(a1, v8);
        }
      }
      else if ( (*(_BYTE *)(a1 + 801) & 8) != 0 )
      {
        v9 = v8[15];
        v8[15] = 0;
        *((_DWORD *)v8 + 23) = 0;
        LeaveCriticalSection(v2);
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(*(_QWORD *)(a1 + 16) + 328LL))(
          *(_QWORD *)(a1 + 104),
          *(_QWORD *)(v9 + 96),
          *(unsigned int *)(*(_QWORD *)(a1 + 16) + 20LL),
          &v21);
        if ( _InterlockedExchangeAdd(*(volatile signed __int32 **)(a1 + 8), 0xFFFFFFFF) == 1 )
          SockDestroySocket(*(_QWORD *)(a1 + 8), v10, v11);
        EnterCriticalSection(v2);
        *(_DWORD *)v9 = 1145324612;
        v12 = *(_QWORD **)(a1 + 776);
        if ( *v12 != a1 + 768 )
LABEL_33:
          __fastfail(3u);
        *(_QWORD *)(v9 + 40) = a1 + 768;
        *(_QWORD *)(v9 + 48) = v12;
        *v12 = v9 + 40;
        *(_QWORD *)(a1 + 776) = v9 + 40;
        goto LABEL_2;
      }
    }
  }
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x18003ec84  mov     [rsp+arg_8], rbx
0x18003ec89  mov     [rsp+arg_18], rbp
0x18003ec8e  push    rsi
0x18003ec8f  push    rdi
0x18003ec90  push    r12
0x18003ec92  push    r14
0x18003ec94  push    r15
0x18003ec96  sub     rsp, 30h
0x18003ec9a  lea     rbp, [rcx+30h]
0x18003ec9e  mov     [rsp+58h+arg_10], 0
0x18003eca6  mov     rdi, rcx
0x18003eca9  mov     r12b, dl
0x18003ecac  mov     rcx, rbp; lpCriticalSection
0x18003ecaf  call    cs:__imp_EnterCriticalSection
0x18003ecb6  nop     dword ptr [rax+rax+00h]
0x18003ecbb  lea     r14, [rdi+190h]
0x18003ecc2  mov     rcx, [r14]
0x18003ecc5  jmp     loc_18003EEF2
0x18003ecca  cmp     dword ptr [rdi+1D0h], 0
0x18003ecd1  jz      short loc_18003ED01
0x18003ecd3  mov     rcx, rbp; lpCriticalSection
0x18003ecd6  call    cs:__imp_LeaveCriticalSection
0x18003ecdd  nop     dword ptr [rax+rax+00h]
0x18003ece2  xor     ecx, ecx; dwMilliseconds
0x18003ece4  call    cs:__imp_Sleep
0x18003eceb  nop     dword ptr [rax+rax+00h]
0x18003ecf0  mov     rcx, rbp; lpCriticalSection
0x18003ecf3  call    cs:__imp_EnterCriticalSection
0x18003ecfa  nop     dword ptr [rax+rax+00h]
0x18003ecff  jmp     short loc_18003ECC2
0x18003ed01  mov     r15, [rcx]
0x18003ed04  lea     rbx, [rcx-10h]
0x18003ed08  test    r12b, r12b
0x18003ed0b  jz      short loc_18003ED1A
0x18003ed0d  cmp     byte ptr [rbx+81h], 0
0x18003ed14  jnz     loc_18003EEEF
0x18003ed1a  mov     eax, [rbx+50h]
0x18003ed1d  cmp     [rbx+54h], eax
0x18003ed20  jge     loc_18003EEEF
0x18003ed26  cmp     dword ptr [rbx+60h], 0
0x18003ed2a  jnz     loc_18003EEEF
0x18003ed30  test    byte ptr [rbx+5Ch], 80h
0x18003ed34  jz      loc_18003EDE3
0x18003ed3a  test    byte ptr [rdi+321h], 8
0x18003ed41  jz      loc_18003EEEF
0x18003ed47  mov     rsi, [rbx+78h]
0x18003ed4b  mov     rcx, rbp; lpCriticalSection
0x18003ed4e  mov     qword ptr [rbx+78h], 0
0x18003ed56  mov     dword ptr [rbx+5Ch], 0
0x18003ed5d  call    cs:__imp_LeaveCriticalSection
0x18003ed64  nop     dword ptr [rax+rax+00h]
0x18003ed69  mov     r8, [rdi+10h]
0x18003ed6d  lea     r9, [rsp+58h+arg_10]
0x18003ed72  mov     rdx, [rsi+60h]
0x18003ed76  mov     rcx, [rdi+68h]
0x18003ed7a  mov     rax, [r8+148h]
0x18003ed81  mov     r8d, [r8+14h]
0x18003ed85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed8a  mov     rax, [rdi+8]
0x18003ed8e  or      ecx, 0FFFFFFFFh
0x18003ed91  lock xadd [rax], ecx
0x18003ed95  cmp     ecx, 1
0x18003ed98  jnz     short loc_18003EDA3
0x18003ed9a  mov     rcx, [rdi+8]
0x18003ed9e  call    SockDestroySocket
0x18003eda3  mov     rcx, rbp; lpCriticalSection
0x18003eda6  call    cs:__imp_EnterCriticalSection
0x18003edad  nop     dword ptr [rax+rax+00h]
0x18003edb2  lea     rcx, [rdi+300h]
0x18003edb9  mov     dword ptr [rsi], 44444444h
0x18003edbf  mov     rdx, [rcx+8]
0x18003edc3  cmp     [rdx], rcx
0x18003edc6  jnz     loc_18003EF22
0x18003edcc  lea     rax, [rsi+28h]
0x18003edd0  mov     [rax], rcx
0x18003edd3  mov     [rax+8], rdx
0x18003edd7  mov     [rdx], rax
0x18003edda  mov     [rcx+8], rax
0x18003edde  jmp     loc_18003ECC2
0x18003ede3  mov     qword ptr [rbx+5Ch], 0
0x18003edeb  mov     rdx, [rcx]
0x18003edee  cmp     [rdx+8], rcx
0x18003edf2  jnz     loc_18003EF22
0x18003edf8  mov     rax, [rcx+8]
0x18003edfc  cmp     [rax], rcx
0x18003edff  jnz     loc_18003EF22
0x18003ee05  mov     [rax], rdx
0x18003ee08  mov     [rdx+8], rax
0x18003ee0c  cmp     dword ptr [rbx+24h], 0
0x18003ee10  jnz     short loc_18003EE6D
0x18003ee12  mov     rdx, [rbx+88h]
0x18003ee19  test    rdx, rdx
0x18003ee1c  jz      short loc_18003EE2E
0x18003ee1e  mov     r8d, 0C000020Dh
0x18003ee24  mov     rcx, rdi
0x18003ee27  call    IndicateRedirError
0x18003ee2c  jmp     short loc_18003EE6D
0x18003ee2e  mov     rdx, [rbx+8]
0x18003ee32  test    rdx, rdx
0x18003ee35  jz      short loc_18003EE6D
0x18003ee37  mov     rcx, [rdi]
0x18003ee3a  mov     al, r12b
0x18003ee3d  mov     r9, [rbx+48h]
0x18003ee41  neg     al
0x18003ee43  mov     eax, [rbx+28h]
0x18003ee46  sbb     r8d, r8d
0x18003ee49  mov     [rsp+58h+var_30], eax
0x18003ee4d  mov     rcx, [rcx+8]
0x18003ee51  and     r8d, 0FFFFDC9Dh
0x18003ee58  add     r8d, 2746h
0x18003ee5f  mov     [rsp+58h+var_38], r8d
0x18003ee64  mov     r8, [rbx+40h]
0x18003ee68  call    CompleteOverlappedIO
0x18003ee6d  cmp     dword ptr [rbx+58h], 0
0x18003ee71  jnz     short loc_18003EEEF
0x18003ee73  cmp     byte ptr [rbx+81h], 0
0x18003ee7a  jz      short loc_18003EED8
0x18003ee7c  mov     rsi, [rbx+30h]
0x18003ee80  mov     ecx, [rsi]
0x18003ee82  call    UseRdma
0x18003ee87  test    eax, eax
0x18003ee89  jz      short loc_18003EEB7
0x18003ee8b  lea     rcx, [rdi+380h]
0x18003ee92  mov     rdx, [rcx]
0x18003ee95  cmp     [rdx+8], rcx
0x18003ee99  jnz     loc_18003EF22
0x18003ee9f  mov     rax, [rsi+8]
0x18003eea3  add     rax, 0FFFFFFFFFFFFFFE8h
0x18003eea7  mov     [rax+8], rcx
0x18003eeab  mov     [rax], rdx
0x18003eeae  mov     [rdx+8], rax
0x18003eeb2  mov     [rcx], rax
0x18003eeb5  jmp     short loc_18003EED0
0x18003eeb7  mov     r8, [rsi+8]; P
0x18003eebb  xor     edx, edx; Flags
0x18003eebd  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18003eec4  call    cs:__imp_RtlFreeHeap
0x18003eecb  nop     dword ptr [rax+rax+00h]
0x18003eed0  mov     eax, [rsi]
0x18003eed2  sub     [rdi+80h], eax
0x18003eed8  mov     rdx, [rbx+30h]
0x18003eedc  mov     rcx, rdi
0x18003eedf  call    ReleaseWsaBufArray
0x18003eee4  mov     rdx, rbx
0x18003eee7  mov     rcx, rdi
0x18003eeea  call    ReleaseApplicationBuffer
0x18003eeef  mov     rcx, r15
0x18003eef2  cmp     rcx, r14
0x18003eef5  jnz     loc_18003ECCA
0x18003eefb  mov     rcx, rbp; lpCriticalSection
0x18003eefe  call    cs:__imp_LeaveCriticalSection
0x18003ef05  nop     dword ptr [rax+rax+00h]
0x18003ef0a  mov     rbx, [rsp+58h+arg_8]
0x18003ef0f  mov     rbp, [rsp+58h+arg_18]
0x18003ef14  add     rsp, 30h
0x18003ef18  pop     r15
0x18003ef1a  pop     r14
0x18003ef1c  pop     r12
0x18003ef1e  pop     rdi
0x18003ef1f  pop     rsi
0x18003ef20  retn
0x18003ef22  mov     ecx, 3
0x18003ef27  int     29h; Win8: RtlFailFast(ecx)
```
