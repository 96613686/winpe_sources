# SockSanHandleImportFailure

- ea: `0x1800248fc`
- end: `0x180024dcb`
- name: `SockSanHandleImportFailure`
- size: `1231`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x18003d540`

## callees

- `0x1800052a0`
- `0x180008250`
- `0x18000b3a0`
- `0x18000ca20`
- `0x18000db30`
- `0x18000ea70`
- `0x18000f4c8`
- `0x18000fa40`
- `0x180022bd2`
- `0x1800248fc`
- `0x180038104`
- `0x180038118`
- `0x18003ae8c`
- `0x180053010`

## import_xrefs

- `ntdll!NtClose` at `0x180024d54`
- `ntdll!NtClose` at `0x180024d6c`
- `ntdll!NtClose` at `0x180024d54`
- `ntdll!NtClose` at `0x180024d6c`
- `ntdll!RtlInitUnicodeString` at `0x180024941`
- `ntdll!RtlInitUnicodeString` at `0x180024941`
- `ntdll!RtlFreeHeap` at `0x180024ce5`
- `ntdll!RtlFreeHeap` at `0x180024d84`
- `ntdll!RtlFreeHeap` at `0x180024ce5`
- `ntdll!RtlFreeHeap` at `0x180024d84`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024d3c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024d3c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180024bdf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180024bdf`
- `WS2_32!WahInsertHandleContext` at `0x180024c30`
- `WS2_32!WahInsertHandleContext` at `0x180024c30`

## pseudocode

```c
volatile signed __int32 *__fastcall SockSanHandleImportFailure(__int64 a1, __int64 *a2)
{
  char v3; // r15
  char v4; // r14
  __int64 v5; // rsi
  unsigned int TdiName; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  volatile signed __int32 *v9; // rbx
  __int64 v10; // rdx
  size_t v11; // r12
  volatile signed __int32 *v12; // rax
  char v13; // r8
  char v14; // cl
  char v15; // al
  char v16; // cl
  char v17; // dl
  char v18; // cl
  char v19; // al
  unsigned __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r8
  volatile signed __int32 *inserted; // rsi
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  void *v28; // rcx
  void *v29; // rcx
  int v31; // [rsp+50h] [rbp-78h] BYREF
  int v32; // [rsp+54h] [rbp-74h] BYREF
  int v33; // [rsp+58h] [rbp-70h] BYREF
  __int64 v34; // [rsp+60h] [rbp-68h] BYREF
  _QWORD v35[2]; // [rsp+68h] [rbp-60h] BYREF
  struct _UNICODE_STRING v36[5]; // [rsp+78h] [rbp-50h] BYREF
  int v38; // [rsp+E8h] [rbp+20h] BYREF

  v36[0] = 0;
  v35[0] = 0;
  v38 = 0;
  v33 = 0;
  v31 = 0;
  v32 = 0;
  v34 = 0;
  v3 = 0;
  v4 = 0;
  RtlInitUnicodeString(v36, 0);
  v5 = *a2;
  v33 = *(_DWORD *)(*a2 + 28);
  v31 = *(_DWORD *)(v5 + 32);
  v32 = *(_DWORD *)(v5 + 36);
  TdiName = SockGetTdiName(
              (unsigned int)&v33,
              (unsigned int)&v31,
              (unsigned int)&v32,
              (int)v5 + 128,
              0,
              0,
              (__int64)v36,
              (__int64)v35,
              (__int64)&v34,
              (__int64)&v38);
  if ( TdiName )
  {
    v9 = 0;
    if ( SBYTE2(xmmword_180063D60) < 0 )
    {
      v10 = 23;
LABEL_4:
      WPP_SF_d(1047, v10, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, TdiName);
    }
  }
  else
  {
    v11 = 2 * ((*(_DWORD *)(v34 + 36) + 7) & 0xFFFFFFF8) + 280;
    v12 = (volatile signed __int32 *)((__int64 (__fastcall *)(HANDLE, _QWORD, size_t))SockAllocateHeapRoutine)(
                                       SockPrivateHeap,
                                       0,
                                       v11);
    v9 = v12;
    v35[1] = v12;
    if ( v12 )
    {
      memset_0((void *)v12, 0, v11);
      *((_DWORD *)v9 + 6) = 3;
      *((_DWORD *)v9 + 7) = *(_DWORD *)(v5 + 28);
      *((_DWORD *)v9 + 8) = *(_DWORD *)(v5 + 32);
      *((_DWORD *)v9 + 9) = *(_DWORD *)(v5 + 36);
      *((_OWORD *)v9 + 8) = *(_OWORD *)(v5 + 128);
      v4 = 1;
      v13 = *((_BYTE *)v9 + 69) & 0xFB | (*(_DWORD *)(v34 + 48) <= 0 ? 0 : 4);
      *((_BYTE *)v9 + 69) = v13;
      *((_DWORD *)v9 + 18) = *(_DWORD *)(v5 + 72);
      *((_DWORD *)v9 + 19) = *(_DWORD *)(v5 + 76);
      *((_DWORD *)v9 + 20) = *(_DWORD *)(v5 + 80);
      *((_DWORD *)v9 + 21) = *(_DWORD *)(v5 + 84);
      *((_DWORD *)v9 + 12) = *(_DWORD *)(v5 + 48);
      *((_DWORD *)v9 + 15) = *(_DWORD *)(v5 + 60);
      *((_DWORD *)v9 + 16) = *(_DWORD *)(v5 + 64);
      v14 = *((_BYTE *)v9 + 68) ^ (*(_BYTE *)(v5 + 68) ^ *((_BYTE *)v9 + 68)) & 2;
      *((_BYTE *)v9 + 68) = v14;
      v15 = v14 ^ (*(_BYTE *)(v5 + 68) ^ v14) & 4;
      *((_BYTE *)v9 + 68) = v15;
      v16 = v15 ^ (*(_BYTE *)(v5 + 68) ^ v15) & 8;
      *((_BYTE *)v9 + 68) = v16;
      v17 = v16 ^ (*(_BYTE *)(v5 + 68) ^ v16) & 0x10;
      *((_BYTE *)v9 + 68) = v17;
      *((_DWORD *)v9 + 13) = *(_DWORD *)(v5 + 52);
      *((_DWORD *)v9 + 14) = *(_DWORD *)(v5 + 56);
      *((_BYTE *)v9 + 68) = v17 ^ (*(_BYTE *)(v5 + 68) ^ v17) & 0x40;
      v18 = v13 ^ (*(_BYTE *)(v5 + 69) ^ v13) & 0x40;
      *((_BYTE *)v9 + 69) = v18;
      v19 = *(_BYTE *)(v5 + 69);
      *((_QWORD *)v9 + 33) = 0;
      *((_QWORD *)v9 + 34) = 0;
      *((_BYTE *)v9 + 69) = (v19 ^ (v19 ^ v18) & 0x77) & 0xF7;
      *((_QWORD *)v9 + 20) = v35[0];
      *((_QWORD *)v9 + 19) = v34;
      *((_DWORD *)v9 + 36) = v38;
      v20 = ((unsigned __int64)v9 + 287) & 0xFFFFFFFFFFFFFFF8uLL;
      *((_QWORD *)v9 + 21) = v20;
      *((_DWORD *)v9 + 10) = *(_DWORD *)(v34 + 36);
      *((_QWORD *)v9 + 22) = (v20 + *(int *)(v34 + 36) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
      *((_DWORD *)v9 + 11) = *(_DWORD *)(v34 + 36);
      InitializeCriticalSection((LPCRITICAL_SECTION)(v9 + 56));
      *((_QWORD *)v9 + 1) = a1;
      *v9 = 2;
      TdiName = SockGetTdiHandles(v9, v21, v22);
      if ( TdiName )
      {
        if ( (SBYTE2(xmmword_180063D60) & 0x80u) == 0 )
          goto LABEL_22;
        v10 = 25;
        goto LABEL_4;
      }
      SockAcquireRwLockExclusive();
      inserted = (volatile signed __int32 *)WahInsertHandleContext(SockContextTable, v9);
      SockReleaseRwLockExclusive(v25, v24, v26, v27);
      if ( inserted )
      {
        if ( inserted != v9 )
        {
          if ( SBYTE2(xmmword_180063D60) < 0 )
            WPP_SF_q(1047, 27, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, *((_QWORD *)v9 + 1));
          if ( _InterlockedExchangeAdd(inserted, 0xFFFFFFFF) == 1 )
            SockDestroySocket((__int64)inserted, v7, v8);
        }
        v3 = 1;
      }
      else if ( SBYTE2(xmmword_180063D60) < 0 )
      {
        WPP_SF_(1047, 26, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
      }
    }
    else
    {
      if ( SBYTE2(xmmword_180063D60) < 0 )
        WPP_SF_(1047, 24, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
      if ( (v38 & 0x80u) != 0 )
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int))(v34 + 104))(v35[0], -1, 0, 0, 128);
    }
  }
LABEL_22:
  if ( v36[0].Buffer && v31 == 3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v36[0].Buffer);
  if ( v3 )
  {
    if ( SBYTE2(xmmword_180063D60) < 0 )
      WPP_SF_(1047, 28, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
  }
  else
  {
    if ( v9 )
    {
      SockNotifyHelperDll(v9, 128, v8);
      if ( v4 )
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 56));
      v28 = (void *)*((_QWORD *)v9 + 23);
      if ( v28 )
        NtClose(v28);
      v29 = (void *)*((_QWORD *)v9 + 24);
      if ( v29 )
        NtClose(v29);
      RtlFreeHeap(SockPrivateHeap, 0, (PVOID)v9);
      v9 = 0;
    }
    if ( v34 && _InterlockedExchangeAdd((volatile signed __int32 *)(v34 + 16), 0xFFFFFFFF) == 1 )
      SockFreeHelperDll(v34, v7, v8);
  }
  return v9;
}

```

## disassembly

```asm
0x1800248fc  mov     rax, rsp
0x1800248ff  mov     [rax+8], rcx
0x180024903  push    rbx
0x180024904  push    rsi
0x180024905  push    rdi
0x180024906  push    r12
0x180024908  push    r13
0x18002490a  push    r14
0x18002490c  push    r15
0x18002490e  sub     rsp, 90h
0x180024915  mov     rbx, rdx
0x180024918  xorps   xmm0, xmm0
0x18002491b  movups  xmmword ptr [rax-50h], xmm0
0x18002491f  xor     edi, edi
0x180024921  mov     [rax-60h], rdi
0x180024925  mov     [rax+20h], edi
0x180024928  mov     [rax-70h], edi
0x18002492b  mov     [rax-78h], edi
0x18002492e  mov     [rax-74h], edi
0x180024931  mov     [rax-68h], rdi
0x180024935  mov     r15b, dil
0x180024938  mov     r14b, dil
0x18002493b  xor     edx, edx; SourceString
0x18002493d  lea     rcx, [rax-50h]; DestinationString
0x180024941  call    cs:__imp_RtlInitUnicodeString
0x180024948  nop     dword ptr [rax+rax+00h]
0x18002494d  mov     rsi, [rbx]
0x180024950  mov     eax, [rsi+1Ch]
0x180024953  mov     [rsp+0C8h+var_70], eax
0x180024957  mov     eax, [rsi+20h]
0x18002495a  mov     [rsp+0C8h+var_78], eax
0x18002495e  mov     eax, [rsi+24h]
0x180024961  mov     [rsp+0C8h+var_74], eax
0x180024965  lea     r13, [rsi+80h]
0x18002496c  lea     rax, [rsp+0C8h+arg_18]
0x180024974  mov     [rsp+0C8h+var_80], rax
0x180024979  lea     rax, [rsp+0C8h+var_68]
0x18002497e  mov     [rsp+0C8h+var_88], rax
0x180024983  lea     rax, [rsp+0C8h+var_60]
0x180024988  mov     [rsp+0C8h+var_90], rax
0x18002498d  lea     rax, [rsp+0C8h+var_50]
0x180024992  mov     [rsp+0C8h+var_98], rax
0x180024997  mov     [rsp+0C8h+var_A0], edi
0x18002499b  mov     [rsp+0C8h+var_A8], edi
0x18002499f  mov     r9, r13
0x1800249a2  lea     r8, [rsp+0C8h+var_74]
0x1800249a7  lea     rdx, [rsp+0C8h+var_78]
0x1800249ac  lea     rcx, [rsp+0C8h+var_70]
0x1800249b1  call    SockGetTdiName
0x1800249b6  test    eax, eax
0x1800249b8  jz      short loc_1800249E5
0x1800249ba  mov     ebx, edi
0x1800249bc  cmp     byte ptr cs:xmmword_180063D60+2, dil
0x1800249c3  jge     loc_180024CBD
0x1800249c9  lea     edx, [rdi+17h]
0x1800249cc  mov     ecx, 417h
0x1800249d1  mov     r9d, eax
0x1800249d4  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x1800249db  call    WPP_SF_d
0x1800249e0  jmp     loc_180024CBD
0x1800249e5  mov     rax, [rsp+0C8h+var_68]
0x1800249ea  mov     eax, [rax+24h]
0x1800249ed  add     eax, 7
0x1800249f0  and     eax, 0FFFFFFF8h
0x1800249f3  lea     eax, ds:118h[rax*2]
0x1800249fa  mov     r12d, eax
0x1800249fd  mov     r8d, eax
0x180024a00  xor     edx, edx
0x180024a02  mov     rcx, cs:SockPrivateHeap
0x180024a09  mov     rax, cs:SockAllocateHeapRoutine
0x180024a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a15  mov     rbx, rax
0x180024a18  mov     [rsp+0C8h+var_58], rax
0x180024a1d  test    rax, rax
0x180024a20  jnz     short loc_180024A77
0x180024a22  cmp     byte ptr cs:xmmword_180063D60+2, dil
0x180024a29  jge     short loc_180024A3F
0x180024a2b  lea     edx, [rax+18h]
0x180024a2e  mov     ecx, 417h
0x180024a33  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180024a3a  call    WPP_SF_
0x180024a3f  test    byte ptr [rsp+0C8h+arg_18], 80h
0x180024a47  jz      loc_180024CBD
0x180024a4d  mov     rax, [rsp+0C8h+var_68]
0x180024a52  mov     [rsp+0C8h+var_A8], 80h
0x180024a5a  xor     r9d, r9d
0x180024a5d  xor     r8d, r8d
0x180024a60  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180024a64  mov     rcx, [rsp+0C8h+var_60]
0x180024a69  mov     rax, [rax+68h]
0x180024a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a72  jmp     loc_180024CBD
0x180024a77  mov     r8, r12; Size
0x180024a7a  xor     edx, edx; Val
0x180024a7c  mov     rcx, rbx; void *
0x180024a7f  call    memset_0
0x180024a84  mov     dword ptr [rbx+18h], 3
0x180024a8b  mov     eax, [rsi+1Ch]
0x180024a8e  mov     [rbx+1Ch], eax
0x180024a91  mov     eax, [rsi+20h]
0x180024a94  mov     [rbx+20h], eax
0x180024a97  mov     eax, [rsi+24h]
0x180024a9a  mov     [rbx+24h], eax
0x180024a9d  movups  xmm0, xmmword ptr [r13+0]
0x180024aa2  movdqu  xmmword ptr [rbx+80h], xmm0
0x180024aaa  mov     rax, [rsp+0C8h+var_68]
0x180024aaf  cmp     [rax+30h], edi
0x180024ab2  setle   r8b
0x180024ab6  mov     r14b, 1
0x180024ab9  sub     r8b, r14b
0x180024abc  and     r8b, 4
0x180024ac0  mov     al, [rbx+45h]
0x180024ac3  and     al, 0FBh
0x180024ac5  or      r8b, al
0x180024ac8  mov     [rbx+45h], r8b
0x180024acc  mov     eax, [rsi+48h]
0x180024acf  mov     [rbx+48h], eax
0x180024ad2  mov     eax, [rsi+4Ch]
0x180024ad5  mov     [rbx+4Ch], eax
0x180024ad8  mov     eax, [rsi+50h]
0x180024adb  mov     [rbx+50h], eax
0x180024ade  mov     eax, [rsi+54h]
0x180024ae1  mov     [rbx+54h], eax
0x180024ae4  mov     eax, [rsi+30h]
0x180024ae7  mov     [rbx+30h], eax
0x180024aea  mov     eax, [rsi+3Ch]
0x180024aed  mov     [rbx+3Ch], eax
0x180024af0  mov     eax, [rsi+40h]
0x180024af3  mov     [rbx+40h], eax
0x180024af6  mov     cl, [rbx+44h]
0x180024af9  xor     cl, [rsi+44h]
0x180024afc  and     cl, 2
0x180024aff  xor     cl, [rbx+44h]
0x180024b02  mov     [rbx+44h], cl
0x180024b05  mov     al, cl
0x180024b07  xor     al, [rsi+44h]
0x180024b0a  and     al, 4
0x180024b0c  xor     al, cl
0x180024b0e  mov     [rbx+44h], al
0x180024b11  mov     cl, al
0x180024b13  xor     cl, [rsi+44h]
0x180024b16  and     cl, 8
0x180024b19  xor     cl, al
0x180024b1b  mov     [rbx+44h], cl
0x180024b1e  mov     dl, cl
0x180024b20  xor     dl, [rsi+44h]
0x180024b23  and     dl, 10h
0x180024b26  xor     dl, cl
0x180024b28  mov     [rbx+44h], dl
0x180024b2b  mov     eax, [rsi+34h]
0x180024b2e  mov     [rbx+34h], eax
0x180024b31  mov     eax, [rsi+38h]
0x180024b34  mov     [rbx+38h], eax
0x180024b37  mov     al, dl
0x180024b39  xor     al, [rsi+44h]
0x180024b3c  and     al, 40h
0x180024b3e  xor     al, dl
0x180024b40  mov     [rbx+44h], al
0x180024b43  mov     cl, r8b
0x180024b46  xor     cl, [rsi+45h]
0x180024b49  and     cl, 40h
0x180024b4c  xor     cl, r8b
0x180024b4f  mov     [rbx+45h], cl
0x180024b52  mov     al, [rsi+45h]
0x180024b55  mov     [rbx+108h], rdi
0x180024b5c  mov     [rbx+110h], rdi
0x180024b63  xor     cl, al
0x180024b65  and     cl, 77h
0x180024b68  xor     cl, al
0x180024b6a  and     cl, 0F7h
0x180024b6d  mov     [rbx+45h], cl
0x180024b70  mov     rax, [rsp+0C8h+var_60]
0x180024b75  mov     [rbx+0A0h], rax
0x180024b7c  mov     rax, [rsp+0C8h+var_68]
0x180024b81  mov     [rbx+98h], rax
0x180024b88  mov     eax, [rsp+0C8h+arg_18]
0x180024b8f  mov     [rbx+90h], eax
0x180024b95  lea     rdx, [rbx+11Fh]
0x180024b9c  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180024ba0  mov     [rbx+0A8h], rdx
0x180024ba7  mov     rax, [rsp+0C8h+var_68]
0x180024bac  mov     ecx, [rax+24h]
0x180024baf  mov     [rbx+28h], ecx
0x180024bb2  mov     rax, [rsp+0C8h+var_68]
0x180024bb7  movsxd  rax, dword ptr [rax+24h]
0x180024bbb  add     rax, 7
0x180024bbf  add     rax, rdx
0x180024bc2  and     rax, 0FFFFFFFFFFFFFFF8h
0x180024bc6  mov     [rbx+0B0h], rax
0x180024bcd  mov     rax, [rsp+0C8h+var_68]
0x180024bd2  mov     ecx, [rax+24h]
0x180024bd5  mov     [rbx+2Ch], ecx
0x180024bd8  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180024bdf  call    cs:__imp_InitializeCriticalSection
0x180024be6  nop     dword ptr [rax+rax+00h]
0x180024beb  nop
0x180024bec  mov     rax, [rsp+0C8h+arg_0]
0x180024bf4  mov     [rbx+8], rax
0x180024bf8  mov     dword ptr [rbx], 2
0x180024bfe  mov     rcx, rbx
0x180024c01  call    SockGetTdiHandles
0x180024c06  test    eax, eax
0x180024c08  jz      short loc_180024C21
0x180024c0a  cmp     byte ptr cs:xmmword_180063D60+2, dil
0x180024c11  jge     loc_180024CBD
0x180024c17  mov     edx, 19h
0x180024c1c  jmp     loc_1800249CC
0x180024c21  call    SockAcquireRwLockExclusive
0x180024c26  mov     rdx, rbx
0x180024c29  mov     rcx, cs:SockContextTable
0x180024c30  call    cs:__imp_WahInsertHandleContext
0x180024c37  nop     dword ptr [rax+rax+00h]
0x180024c3c  mov     rsi, rax
0x180024c3f  call    SockReleaseRwLockExclusive
0x180024c44  test    rsi, rsi
0x180024c47  jnz     short loc_180024C68
0x180024c49  cmp     byte ptr cs:xmmword_180063D60+2, dil
0x180024c50  jge     short loc_180024CBD
0x180024c52  lea     edx, [rsi+1Ah]
0x180024c55  mov     ecx, 417h
0x180024c5a  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180024c61  call    WPP_SF_
0x180024c66  jmp     short loc_180024CBD
0x180024c68  cmp     rsi, rbx
0x180024c6b  jz      short loc_180024CA4
0x180024c6d  cmp     byte ptr cs:xmmword_180063D60+2, dil
0x180024c74  jge     short loc_180024C90
0x180024c76  mov     edx, 1Bh
0x180024c7b  mov     ecx, 417h
0x180024c80  mov     r9, [rbx+8]
0x180024c84  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180024c8b  call    WPP_SF_q
0x180024c90  or      eax, 0FFFFFFFFh
0x180024c93  lock xadd [rsi], eax
0x180024c97  cmp     eax, 1
0x180024c9a  jnz     short loc_180024CA4
0x180024c9c  mov     rcx, rsi
0x180024c9f  call    SockDestroySocket
0x180024ca4  mov     r15b, r14b
0x180024ca7  jmp     short loc_180024CBD
0x180024ca9  mov     ecx, eax
0x180024cab  call    NtStatusToSocketError
0x180024cb0  xor     edi, edi
0x180024cb2  mov     rbx, [rsp+0C8h+var_58]
0x180024cb7  mov     r15b, dil
0x180024cba  mov     r14b, dil
0x180024cbd  cmp     [rsp+0C8h+P], rdi
0x180024cc5  jz      short loc_180024CF1
0x180024cc7  cmp     [rsp+0C8h+var_78], 3
0x180024ccc  jnz     short loc_180024CF1
0x180024cce  mov     rcx, gs:60h
0x180024cd7  mov     r8, [rsp+0C8h+P]; P
0x180024cdf  xor     edx, edx; Flags
0x180024ce1  mov     rcx, [rcx+30h]; HeapHandle
0x180024ce5  call    cs:__imp_RtlFreeHeap
0x180024cec  nop     dword ptr [rax+rax+00h]
0x180024cf1  test    r15b, r15b
0x180024cf4  jz      short loc_180024D1E
0x180024cf6  cmp     byte ptr cs:xmmword_180063D60+2, dil
0x180024cfd  jge     loc_180024DB4
0x180024d03  mov     edx, 1Ch
0x180024d08  mov     ecx, 417h
0x180024d0d  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180024d14  call    WPP_SF_
0x180024d19  jmp     loc_180024DB4
0x180024d1e  test    rbx, rbx
0x180024d21  jz      short loc_180024D93
0x180024d23  mov     edx, 80h
0x180024d28  mov     rcx, rbx
0x180024d2b  call    SockNotifyHelperDll
0x180024d30  test    r14b, r14b
0x180024d33  jz      short loc_180024D48
0x180024d35  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180024d3c  call    cs:__imp_DeleteCriticalSection
0x180024d43  nop     dword ptr [rax+rax+00h]
0x180024d48  mov     rcx, [rbx+0B8h]; Handle
0x180024d4f  test    rcx, rcx
0x180024d52  jz      short loc_180024D60
0x180024d54  call    cs:__imp_NtClose
0x180024d5b  nop     dword ptr [rax+rax+00h]
0x180024d60  mov     rcx, [rbx+0C0h]; Handle
0x180024d67  test    rcx, rcx
0x180024d6a  jz      short loc_180024D78
0x180024d6c  call    cs:__imp_NtClose
0x180024d73  nop     dword ptr [rax+rax+00h]
0x180024d78  mov     r8, rbx; P
0x180024d7b  xor     edx, edx; Flags
0x180024d7d  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180024d84  call    cs:__imp_RtlFreeHeap
0x180024d8b  nop     dword ptr [rax+rax+00h]
0x180024d90  mov     rbx, rdi
0x180024d93  mov     rcx, [rsp+0C8h+var_68]
0x180024d98  test    rcx, rcx
0x180024d9b  jz      short loc_180024DB4
0x180024d9d  or      eax, 0FFFFFFFFh
0x180024da0  lock xadd [rcx+10h], eax
0x180024da5  cmp     eax, 1
0x180024da8  jnz     short loc_180024DB4
0x180024daa  mov     rcx, [rsp+0C8h+var_68]
0x180024daf  call    SockFreeHelperDll
  ... truncated ...
```
