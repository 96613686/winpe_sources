# SockFindHelperDllForAddressFamily

- ea: `0x180010680`
- end: `0x180010974`
- name: `SockFindHelperDllForAddressFamily`
- size: `756`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010440`
- `0x180010570`

## callees

- `0x18000c8c0`
- `0x18000ca20`
- `0x18000db30`
- `0x18000f9f0`
- `0x180010680`
- `0x18001097c`
- `0x180010e00`
- `0x180010e2c`
- `0x180010f4c`
- `0x1800222f0`
- `0x180038570`
- `0x180038fb4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001083e`
- `ntdll!RtlFreeHeap` at `0x1800108b7`
- `ntdll!RtlFreeHeap` at `0x18001083e`
- `ntdll!RtlFreeHeap` at `0x1800108b7`
- `ntdll!NtSetEvent` at `0x1800108ed`
- `ntdll!NtSetEvent` at `0x1800108ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800107b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800107b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010785`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010785`

## pseudocode

```c
__int64 *__fastcall SockFindHelperDllForAddressFamily(unsigned int a1)
{
  char v2; // bp
  int v3; // ebx
  __int64 v4; // rcx
  signed __int32 v5; // esi
  __int64 *v6; // rbx
  __int64 *v7; // r10
  unsigned int *v8; // r9
  unsigned int v9; // eax
  __int64 v10; // r8
  int v11; // eax
  int v12; // edx
  signed __int32 v13; // edx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  PVOID v19; // rbp
  WCHAR *v20; // rbx
  int v21; // eax
  PVOID v22; // rsi
  __int64 v23; // rax
  LSTATUS ProviderId; // eax
  int v26; // ecx
  __int64 *v27; // [rsp+30h] [rbp-58h] BYREF
  PVOID P; // [rsp+38h] [rbp-50h] BYREF
  PVOID v29[2]; // [rsp+40h] [rbp-48h] BYREF

  v27 = 0;
  v2 = 1;
  v29[0] = 0;
  P = 0;
  do
  {
    v3 = SocketGlobalLock;
    if ( SocketGlobalLock < 0 )
    {
      EnterCriticalSection(&CriticalSection);
      v3 = SocketGlobalLock;
      v5 = _InterlockedCompareExchange(
             &SocketGlobalLock,
             ((SocketGlobalLock >> 31) & 0xFFFFFFFE) + SocketGlobalLock + 1,
             SocketGlobalLock);
      LeaveCriticalSection(&CriticalSection);
    }
    else
    {
      v4 = (unsigned int)(SocketGlobalLock + 1);
      v5 = _InterlockedCompareExchange(&SocketGlobalLock, v4, SocketGlobalLock);
    }
  }
  while ( v5 != v3 );
  while ( 1 )
  {
    v6 = (__int64 *)SockHelperDllListHead;
LABEL_6:
    if ( v6 != &SockHelperDllListHead )
    {
      v7 = v6;
      v27 = v6;
      if ( (xmmword_180063D60 & 2) != 0 )
      {
        WPP_SF_ql(v4, 10, WPP_6cc0c9a94cfa36ebabe8e0189c9f9edd_Traceguids, v6, a1);
        v7 = v27;
      }
      v8 = (unsigned int *)v7[7];
      v9 = 0;
      v10 = *v8;
      while ( 1 )
      {
        if ( v9 >= (unsigned int)v10 )
        {
          v6 = (__int64 *)*v6;
          goto LABEL_6;
        }
        v4 = v9;
        if ( v8[3 * v9 + 2] == a1 )
          break;
        ++v9;
      }
      _InterlockedIncrement((volatile signed __int32 *)v7 + 4);
      if ( v2 )
      {
        do
        {
          v11 = SocketGlobalLock;
          v12 = -1;
          if ( SocketGlobalLock <= 0 )
            v12 = 1;
          v13 = SocketGlobalLock + v12;
        }
        while ( v11 != _InterlockedCompareExchange(&SocketGlobalLock, v13, SocketGlobalLock) );
        if ( v13 == -1 )
          NtSetEvent(Handle, 0);
      }
      else
      {
        SockReleaseRwLockExclusive(v9, 3LL * v9, v10, v8);
      }
      return v27;
    }
    if ( !v2 )
      break;
    SockReleaseRwLockShared();
    SockAcquireRwLockExclusive();
    v2 = 0;
  }
  if ( !SockLoadTransportList(v29) )
  {
    v19 = v29[0];
    v20 = (WCHAR *)v29[0];
    v27 = 0;
    while ( *v20 )
    {
      v21 = SockLoadTransportMapping(v20, &P);
      if ( v21 )
      {
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_Sd(v16, 11, (unsigned int)WPP_6cc0c9a94cfa36ebabe8e0189c9f9edd_Traceguids, (_DWORD)v20, v21);
      }
      else
      {
        v22 = P;
        if ( (unsigned int)SockIsAddressFamilySupported(P, a1) )
        {
          *(_OWORD *)v29 = 0;
          ProviderId = SockGetProviderId(v20, (LPBYTE)v29);
          if ( ProviderId )
          {
            if ( (xmmword_180063D60 & 2) != 0 )
              WPP_SF_Sd(v26, 12, (unsigned int)WPP_6cc0c9a94cfa36ebabe8e0189c9f9edd_Traceguids, (_DWORD)v20, ProviderId);
          }
          else if ( !(unsigned int)SockLoadHelperDll(v20, (__int128 *)v29, (__int64)v22, &v27) )
          {
            _InterlockedIncrement((volatile signed __int32 *)v27 + 4);
            break;
          }
        }
        RtlFreeHeap(SockPrivateHeap, 0, v22);
      }
      v23 = -1;
      while ( v20[++v23] != 0 )
        ;
      v20 += v23 + 1;
    }
    SockReleaseRwLockExclusive(v16, v15, v17, v18);
    RtlFreeHeap(SockPrivateHeap, 0, v19);
    return v27;
  }
  SockReleaseRwLockExclusive(v16, v15, v17, v18);
  return 0;
}

```

## disassembly

```asm
0x180010680  push    rbx
0x180010682  push    rbp
0x180010683  push    rsi
0x180010684  push    rdi
0x180010685  push    r14
0x180010687  sub     rsp, 60h
0x18001068b  mov     rax, cs:__security_cookie
0x180010692  xor     rax, rsp
0x180010695  mov     [rsp+88h+var_38], rax
0x18001069a  xor     r14d, r14d
0x18001069d  mov     edi, ecx
0x18001069f  mov     [rsp+88h+var_58], r14
0x1800106a4  mov     bpl, 1
0x1800106a7  mov     [rsp+88h+var_48], r14
0x1800106ac  mov     [rsp+88h+P], r14
0x1800106b1  mov     ebx, cs:SocketGlobalLock
0x1800106b7  test    ebx, ebx
0x1800106b9  js      loc_18001077E
0x1800106bf  lea     ecx, [rbx+1]
0x1800106c2  mov     eax, ebx
0x1800106c4  lock cmpxchg cs:SocketGlobalLock, ecx
0x1800106cc  mov     esi, eax
0x1800106ce  cmp     esi, ebx
0x1800106d0  jnz     short loc_1800106B1
0x1800106d2  lea     rsi, SockHelperDllListHead
0x1800106d9  mov     rbx, cs:SockHelperDllListHead
0x1800106e0  cmp     rbx, rsi
0x1800106e3  jz      loc_1800107C8
0x1800106e9  mov     r10, rbx
0x1800106ec  mov     [rsp+88h+var_58], rbx
0x1800106f1  test    byte ptr cs:xmmword_180063D60, 2
0x1800106f8  jnz     loc_1800108FE
0x1800106fe  mov     r9, [r10+38h]
0x180010702  mov     eax, r14d
0x180010705  mov     r8d, [r9]
0x180010708  cmp     eax, r8d
0x18001070b  jnb     short loc_180010776
0x18001070d  mov     ecx, eax
0x18001070f  lea     rdx, [rcx+rcx*2]
0x180010713  cmp     [r9+rdx*4+8], edi
0x180010718  jz      short loc_18001071E
0x18001071a  inc     eax
0x18001071c  jmp     short loc_180010708
0x18001071e  lock inc dword ptr [r10+10h]
0x180010723  test    bpl, bpl
0x180010726  jz      loc_1800108C8
0x18001072c  mov     r8d, 1
0x180010732  mov     eax, cs:SocketGlobalLock
0x180010738  mov     edx, 0FFFFFFFFh
0x18001073d  test    eax, eax
0x18001073f  cmovle  edx, r8d
0x180010743  add     edx, eax
0x180010745  lock cmpxchg cs:SocketGlobalLock, edx
0x18001074d  jnz     short loc_180010732
0x18001074f  cmp     edx, 0FFFFFFFFh
0x180010752  jz      loc_1800108E4
0x180010758  mov     rax, [rsp+88h+var_58]
0x18001075d  mov     rcx, [rsp+88h+var_38]
0x180010762  xor     rcx, rsp; StackCookie
0x180010765  call    __security_check_cookie
0x18001076a  add     rsp, 60h
0x18001076e  pop     r14
0x180010770  pop     rdi
0x180010771  pop     rsi
0x180010772  pop     rbp
0x180010773  pop     rbx
0x180010774  retn
0x180010776  mov     rbx, [rbx]
0x180010779  jmp     loc_1800106E0
0x18001077e  lea     rcx, CriticalSection; lpCriticalSection
0x180010785  call    cs:__imp_EnterCriticalSection
0x18001078c  nop     dword ptr [rax+rax+00h]
0x180010791  mov     ebx, cs:SocketGlobalLock
0x180010797  mov     eax, ebx
0x180010799  sar     eax, 1Fh
0x18001079c  and     eax, 0FFFFFFFEh
0x18001079f  lea     ecx, [rbx+1]
0x1800107a2  add     ecx, eax
0x1800107a4  mov     eax, ebx
0x1800107a6  lock cmpxchg cs:SocketGlobalLock, ecx
0x1800107ae  lea     rcx, CriticalSection; lpCriticalSection
0x1800107b5  mov     esi, eax
0x1800107b7  call    cs:__imp_LeaveCriticalSection
0x1800107be  nop     dword ptr [rax+rax+00h]
0x1800107c3  jmp     loc_1800106CE
0x1800107c8  test    bpl, bpl
0x1800107cb  jnz     loc_1800108D2
0x1800107d1  lea     rcx, [rsp+88h+var_48]
0x1800107d6  call    SockLoadTransportList
0x1800107db  test    eax, eax
0x1800107dd  jz      short loc_1800107EB
0x1800107df  call    SockReleaseRwLockExclusive
0x1800107e4  xor     eax, eax
0x1800107e6  jmp     loc_18001075D
0x1800107eb  mov     rbp, [rsp+88h+var_48]
0x1800107f0  mov     rbx, rbp
0x1800107f3  mov     [rsp+88h+var_58], r14
0x1800107f8  nop     dword ptr [rax+rax+00000000h]
0x180010800  cmp     [rbx], r14w
0x180010804  jz      loc_1800108A6
0x18001080a  lea     rdx, [rsp+88h+P]
0x18001080f  mov     rcx, rbx
0x180010812  call    SockLoadTransportMapping
0x180010817  test    eax, eax
0x180010819  jnz     loc_180010920
0x18001081f  mov     rsi, [rsp+88h+P]
0x180010824  mov     edx, edi
0x180010826  mov     rcx, rsi
0x180010829  call    SockIsAddressFamilySupported
0x18001082e  test    eax, eax
0x180010830  jnz     short loc_180010867
0x180010832  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180010839  mov     r8, rsi; P
0x18001083c  xor     edx, edx; Flags
0x18001083e  call    cs:__imp_RtlFreeHeap
0x180010845  nop     dword ptr [rax+rax+00h]
0x18001084a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180010851  cmp     [rbx+rax*2+2], r14w
0x180010857  lea     rax, [rax+1]
0x18001085b  jnz     short loc_180010851
0x18001085d  lea     rbx, [rbx+rax*2]
0x180010861  add     rbx, 2
0x180010865  jmp     short loc_180010800
0x180010867  xorps   xmm0, xmm0
0x18001086a  lea     rdx, [rsp+88h+var_48]; lpData
0x18001086f  mov     rcx, rbx; lpSubKey
0x180010872  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x180010877  call    SockGetProviderId
0x18001087c  test    eax, eax
0x18001087e  jnz     loc_18001094A
0x180010884  lea     r9, [rsp+88h+var_58]
0x180010889  mov     r8, rsi
0x18001088c  lea     rdx, [rsp+88h+var_48]
0x180010891  mov     rcx, rbx; pszSrc
0x180010894  call    SockLoadHelperDll
0x180010899  test    eax, eax
0x18001089b  jnz     short loc_180010832
0x18001089d  mov     rax, [rsp+88h+var_58]
0x1800108a2  lock inc dword ptr [rax+10h]
0x1800108a6  call    SockReleaseRwLockExclusive
0x1800108ab  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800108b2  mov     r8, rbp; P
0x1800108b5  xor     edx, edx; Flags
0x1800108b7  call    cs:__imp_RtlFreeHeap
0x1800108be  nop     dword ptr [rax+rax+00h]
0x1800108c3  jmp     loc_180010758
0x1800108c8  call    SockReleaseRwLockExclusive
0x1800108cd  jmp     loc_180010758
0x1800108d2  call    SockReleaseRwLockShared
0x1800108d7  call    SockAcquireRwLockExclusive
0x1800108dc  xor     bpl, bpl
0x1800108df  jmp     loc_1800106D9
0x1800108e4  mov     rcx, cs:Handle; EventHandle
0x1800108eb  xor     edx, edx; PreviousState
0x1800108ed  call    cs:__imp_NtSetEvent
0x1800108f4  nop     dword ptr [rax+rax+00h]
0x1800108f9  jmp     loc_180010758
0x1800108fe  mov     edx, 0Ah
0x180010903  mov     [rsp+88h+var_68], edi
0x180010907  mov     r9, rbx
0x18001090a  lea     r8, WPP_6cc0c9a94cfa36ebabe8e0189c9f9edd_Traceguids
0x180010911  call    WPP_SF_ql
0x180010916  mov     r10, [rsp+88h+var_58]
0x18001091b  jmp     loc_1800106FE
0x180010920  test    byte ptr cs:xmmword_180063D60, 2
0x180010927  jz      loc_18001084A
0x18001092d  mov     edx, 0Bh
0x180010932  mov     [rsp+88h+var_68], eax
0x180010936  mov     r9, rbx
0x180010939  lea     r8, WPP_6cc0c9a94cfa36ebabe8e0189c9f9edd_Traceguids
0x180010940  call    WPP_SF_Sd
0x180010945  jmp     loc_18001084A
0x18001094a  test    byte ptr cs:xmmword_180063D60, 2
0x180010951  jz      loc_180010832
0x180010957  mov     edx, 0Ch
0x18001095c  mov     [rsp+88h+var_68], eax
0x180010960  mov     r9, rbx
0x180010963  lea     r8, WPP_6cc0c9a94cfa36ebabe8e0189c9f9edd_Traceguids
0x18001096a  call    WPP_SF_Sd
0x18001096f  jmp     loc_180010832
```
