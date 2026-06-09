# DnsNbt_ResolveAddr

- ea: `0x180068b34`
- end: `0x180068e95`
- name: `DnsNbt_ResolveAddr`
- size: `865`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180049998`

## callees

- `0x180024554`
- `0x1800245a0`
- `0x1800249b8`
- `0x18002625c`
- `0x18004a020`
- `0x180068b34`
- `0x18008b5f0`
- `0x1800d3e00`
- `0x1800d3e8c`
- `0x1800d3f30`
- `0x1800d4000`
- `0x1800dc9e0`
- `0x1800e0fc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068c27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068c27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068d34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068d34`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180068d58`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180068d58`
- `ntdll!NtDeviceIoControlFile` at `0x180068cd7`
- `ntdll!NtDeviceIoControlFile` at `0x180068cd7`
- `WS2_32!__imp_ntohl` at `0x180068bf9`
- `WS2_32!__imp_ntohl` at `0x180068bf9`

## pseudocode

```c
__int64 __fastcall DnsNbt_ResolveAddr(__int64 a1, u_long a2, int a3, __int64 a4, int a5, char **a6)
{
  unsigned int v6; // ebx
  char *v7; // rsi
  char *v11; // rax
  __int64 v12; // rdi
  int v13; // r14d
  unsigned int i; // r12d
  HANDLE v15; // rcx
  unsigned int Io; // eax
  NTSTATUS v17; // eax
  int v18; // edx
  int v19; // ecx
  int v20; // r8d
  char v21; // r15
  int v22; // edx
  int v23; // ecx
  int v24; // r8d
  __int64 v25; // rcx
  __m256i v27; // [rsp+58h] [rbp-59h] BYREF
  u_long netlong; // [rsp+80h] [rbp-31h] BYREF

  v6 = 0;
  v7 = 0;
  netlong = a2;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    WPP_SF__IPV4_(a1, 40, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, &netlong);
    a2 = netlong;
  }
  if ( a2 - 1 > 0xFFFFFFFD )
    goto LABEL_22;
  v11 = DnsNbt_Open(a3, a4);
  v7 = v11;
  if ( !v11 )
  {
    v6 = 123;
    goto LABEL_22;
  }
  v12 = (__int64)(v11 + 624);
  AddRefQueryBlobEx(a1, "DnsNbt_ResolveAddr", 1665, 17);
  *((_QWORD *)v7 + 4) = a1;
  *((_DWORD *)v7 + 12) = 0;
  *((_DWORD *)v7 + 141) = netlong;
  *((_QWORD *)v7 + 76) = Query_NetBiosComplete;
  memset((char *)&v27.m256i_u64[1] + 7, 0, 17);
  *(__int64 *)((char *)v27.m256i_i64 + 4) = 0x11001200000001LL;
  v27.m256i_i32[0] = ntohl(netlong);
  v27.m256i_i16[6] = 0;
  v27.m256i_i8[14] = 42;
  EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 568));
  v13 = 0;
  for ( i = 0; i < *((_DWORD *)v7 + 3); ++i )
  {
    v15 = *(HANDLE *)v12;
    if ( *(_QWORD *)v12 )
    {
      *(__m256i *)(v12 + 592) = v27;
      Io = ThreadPool_CreateIo(
             v15,
             (PTP_WIN32_IO_CALLBACK)DnsNbt_IoCompletionCallback,
             (PVOID)v12,
             1,
             (struct _TP_IO **)(v12 + 576));
      v6 = Io;
      if ( Io )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_d(1035, 41, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, Io);
        break;
      }
      AddRefNbtLookupContext(v7);
      v17 = NtDeviceIoControlFile(
              *(HANDLE *)v12,
              0,
              0,
              (PVOID)(v12 + 536),
              (PIO_STATUS_BLOCK)(v12 + 536),
              0x2100AEu,
              (PVOID)(v12 + 592),
              0x20u,
              (PVOID)(v12 + 624),
              0x27Cu);
      v21 = v17;
      if ( v17 < 0 )
      {
        CancelThreadpoolIo(*(PTP_IO *)(v12 + 576));
        DeRefNbtLookupContext(v7);
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF__IPV4_Sd(v23, v22, v24, (unsigned int)&netlong, v12 + 8, v21);
      }
      else
      {
        ++v13;
        _InterlockedOr((volatile signed __int32 *)(v12 + 584), 1u);
        if ( v17 == 259 )
        {
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF__IPV4_Sq(v19, v18, v20, (unsigned int)&netlong, v12 + 8, v12);
        }
        else if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        {
          WPP_SF__IPV4_S(v19, v18, v20, (unsigned int)&netlong, v12 + 8);
        }
      }
    }
    v12 += 1776;
  }
  *((_DWORD *)v7 + 10) = v13;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 568));
  if ( v13 )
  {
    v6 = 9506;
LABEL_27:
    AddRefNbtLookupContext(v7);
    *a6 = v7;
    goto LABEL_22;
  }
  if ( !v6 )
  {
    v6 = 4312;
    goto LABEL_22;
  }
  if ( v6 == 9506 )
    goto LABEL_27;
LABEL_22:
  DeRefNbtLookupContext(v7);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF__IPV4_d(v25, 45, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, &netlong, v6);
  return v6;
}

```

## disassembly

```asm
0x180068b34  mov     rax, rsp
0x180068b37  push    rbp
0x180068b38  push    rbx
0x180068b39  push    rsi
0x180068b3a  push    rdi
0x180068b3b  push    r12
0x180068b3d  push    r13
0x180068b3f  push    r14
0x180068b41  push    r15
0x180068b43  lea     rbp, [rax-4Fh]
0x180068b47  sub     rsp, 0B8h
0x180068b4e  movaps  xmmword ptr [rax-58h], xmm6
0x180068b52  movaps  xmmword ptr [rax-68h], xmm7
0x180068b56  mov     rax, cs:__security_cookie
0x180068b5d  xor     rax, rsp
0x180068b60  mov     [rbp+47h+var_70], rax
0x180068b64  mov     r13, [rbp+47h+arg_28]
0x180068b68  xor     ebx, ebx
0x180068b6a  mov     [rbp+47h+var_80], r13
0x180068b6e  xor     esi, esi
0x180068b70  mov     r14, r9
0x180068b73  mov     [rbp+47h+netlong], edx
0x180068b76  mov     edi, r8d
0x180068b79  mov     r15, rcx
0x180068b7c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180068b83  jnz     loc_180068E20
0x180068b89  lea     eax, [rdx-1]
0x180068b8c  cmp     eax, 0FFFFFFFDh
0x180068b8f  ja      loc_180068D99
0x180068b95  mov     rdx, r14
0x180068b98  mov     ecx, edi
0x180068b9a  call    DnsNbt_Open
0x180068b9f  mov     rsi, rax
0x180068ba2  test    rax, rax
0x180068ba5  jz      loc_180068DDF
0x180068bab  mov     r9d, 11h
0x180068bb1  lea     rdx, aDnsnbtResolvea; "DnsNbt_ResolveAddr"
0x180068bb8  mov     r8d, 681h
0x180068bbe  lea     rdi, [rax+270h]
0x180068bc5  mov     rcx, r15
0x180068bc8  call    AddRefQueryBlobEx
0x180068bcd  mov     [rsi+20h], r15
0x180068bd1  xorps   xmm0, xmm0
0x180068bd4  mov     [rsi+30h], ebx
0x180068bd7  mov     eax, [rbp+47h+netlong]
0x180068bda  mov     [rsi+234h], eax
0x180068be0  lea     rax, Query_NetBiosComplete
0x180068be7  mov     [rsi+260h], rax
0x180068bee  mov     ecx, [rbp+47h+netlong]; netlong
0x180068bf1  movdqu  [rbp+47h+var_A0+0Fh], xmm0
0x180068bf6  mov     [rbp+47h+var_81], bl
0x180068bf9  call    cs:__imp_ntohl
0x180068c00  nop     dword ptr [rax+rax+00h]
0x180068c05  lea     rcx, [rsi+238h]; lpCriticalSection
0x180068c0c  mov     dword ptr [rbp+47h+var_A0+4], 1
0x180068c13  mov     dword ptr [rbp+47h+var_A0], eax
0x180068c16  xor     eax, eax
0x180068c18  mov     word ptr [rbp+47h+var_A0+0Ch], ax
0x180068c1c  mov     byte ptr [rbp+47h+var_A0+0Eh], 2Ah ; '*'
0x180068c20  mov     dword ptr [rbp+47h+var_A0+8], 110012h
0x180068c27  call    cs:__imp_EnterCriticalSection
0x180068c2e  nop     dword ptr [rax+rax+00h]
0x180068c33  movups  xmm6, xmmword ptr [rbp-49h]
0x180068c37  xor     r14d, r14d
0x180068c3a  movups  xmm7, [rbp+47h+var_A0]
0x180068c3e  xor     r12d, r12d
0x180068c41  cmp     r12d, [rsi+0Ch]
0x180068c45  jnb     loc_180068D29
0x180068c4b  mov     rcx, [rdi]; fl
0x180068c4e  test    rcx, rcx
0x180068c51  jz      loc_180068D0D
0x180068c57  lea     r15, [rdi+250h]
0x180068c5e  mov     r9d, 1
0x180068c64  movups  xmmword ptr [r15], xmm7
0x180068c68  lea     r13, [rdi+240h]
0x180068c6f  mov     r8, rdi; pv
0x180068c72  lea     rdx, DnsNbt_IoCompletionCallback; pfnio
0x180068c79  mov     [rsp+0F0h+IoStatusBlock], r13; __int64
0x180068c7e  movups  xmmword ptr [r15+10h], xmm6
0x180068c83  call    ThreadPool_CreateIo
0x180068c88  mov     ebx, eax
0x180068c8a  test    eax, eax
0x180068c8c  jnz     loc_180068D1C
0x180068c92  mov     rcx, rsi
0x180068c95  call    AddRefNbtLookupContext
0x180068c9a  mov     [rsp+0F0h+OutputBufferLength], 27Ch; OutputBufferLength
0x180068ca2  lea     rcx, [rdi+270h]
0x180068ca9  mov     [rsp+0F0h+OutputBuffer], rcx; OutputBuffer
0x180068cae  lea     r9, [rdi+218h]; ApcContext
0x180068cb5  mov     rcx, [rdi]; FileHandle
0x180068cb8  xor     r8d, r8d; ApcRoutine
0x180068cbb  mov     [rsp+0F0h+InputBufferLength], 20h ; ' '; InputBufferLength
0x180068cc3  xor     edx, edx; Event
0x180068cc5  mov     [rsp+0F0h+InputBuffer], r15; InputBuffer
0x180068cca  mov     [rsp+0F0h+IoControlCode], 2100AEh; IoControlCode
0x180068cd2  mov     [rsp+0F0h+IoStatusBlock], r9; IoStatusBlock
0x180068cd7  call    cs:__imp_NtDeviceIoControlFile
0x180068cde  nop     dword ptr [rax+rax+00h]
0x180068ce3  mov     r15d, eax
0x180068ce6  test    eax, eax
0x180068ce8  js      short loc_180068D54
0x180068cea  inc     r14d
0x180068ced  lock or dword ptr [rdi+248h], 1
0x180068cf5  cmp     eax, 103h
0x180068cfa  jnz     loc_180068DFC
0x180068d00  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180068d07  jnz     loc_180068E3D
0x180068d0d  inc     r12d
0x180068d10  add     rdi, 6F0h
0x180068d17  jmp     loc_180068C41
0x180068d1c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180068d23  jnz     loc_180068E59
0x180068d29  lea     rcx, [rsi+238h]; lpCriticalSection
0x180068d30  mov     [rsi+28h], r14d
0x180068d34  call    cs:__imp_LeaveCriticalSection
0x180068d3b  nop     dword ptr [rax+rax+00h]
0x180068d40  test    r14d, r14d
0x180068d43  jnz     loc_180068DE6
0x180068d49  test    ebx, ebx
0x180068d4b  jnz     short loc_180068D91
0x180068d4d  mov     ebx, 10D8h
0x180068d52  jmp     short loc_180068D99
0x180068d54  mov     rcx, [r13+0]; pio
0x180068d58  call    cs:__imp_CancelThreadpoolIo
0x180068d5f  nop     dword ptr [rax+rax+00h]
0x180068d64  mov     rcx, rsi; lpMem
0x180068d67  call    DeRefNbtLookupContext
0x180068d6c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180068d73  jz      short loc_180068D0D
0x180068d75  lea     rax, [rdi+8]
0x180068d79  mov     [rsp+0F0h+IoControlCode], r15d
0x180068d7e  lea     r9, [rbp+47h+netlong]
0x180068d82  mov     [rsp+0F0h+IoStatusBlock], rax
0x180068d87  call    WPP_SF__IPV4_Sd
0x180068d8c  jmp     loc_180068D0D
0x180068d91  cmp     ebx, 2522h
0x180068d97  jz      short loc_180068DEB
0x180068d99  mov     rcx, rsi; lpMem
0x180068d9c  call    DeRefNbtLookupContext
0x180068da1  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180068da8  jnz     loc_180068E77
0x180068dae  mov     eax, ebx
0x180068db0  mov     rcx, [rbp+47h+var_70]
0x180068db4  xor     rcx, rsp; StackCookie
0x180068db7  call    __security_check_cookie
0x180068dbc  lea     r11, [rsp+0F0h+var_38]
0x180068dc4  movaps  xmm6, xmmword ptr [r11-18h]
0x180068dc9  movaps  xmm7, xmmword ptr [r11-28h]
0x180068dce  mov     rsp, r11
0x180068dd1  pop     r15
0x180068dd3  pop     r14
0x180068dd5  pop     r13
0x180068dd7  pop     r12
0x180068dd9  pop     rdi
0x180068dda  pop     rsi
0x180068ddb  pop     rbx
0x180068ddc  pop     rbp
0x180068ddd  retn
0x180068ddf  mov     ebx, 7Bh ; '{'
0x180068de4  jmp     short loc_180068D99
0x180068de6  mov     ebx, 2522h
0x180068deb  mov     rcx, rsi
0x180068dee  call    AddRefNbtLookupContext
0x180068df3  mov     rax, [rbp+47h+var_80]
0x180068df7  mov     [rax], rsi
0x180068dfa  jmp     short loc_180068D99
0x180068dfc  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180068e03  jz      loc_180068D0D
0x180068e09  lea     rax, [rdi+8]
0x180068e0d  lea     r9, [rbp+47h+netlong]
0x180068e11  mov     [rsp+0F0h+IoStatusBlock], rax
0x180068e16  call    WPP_SF__IPV4_S
0x180068e1b  jmp     loc_180068D0D
0x180068e20  mov     edx, 28h ; '('
0x180068e25  lea     r9, [rbp+47h+netlong]
0x180068e29  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x180068e30  call    WPP_SF__IPV4_
0x180068e35  mov     edx, [rbp+47h+netlong]
0x180068e38  jmp     loc_180068B89
0x180068e3d  lea     rax, [rdi+8]
0x180068e41  mov     qword ptr [rsp+0F0h+IoControlCode], rdi
0x180068e46  lea     r9, [rbp+47h+netlong]
0x180068e4a  mov     [rsp+0F0h+IoStatusBlock], rax
0x180068e4f  call    WPP_SF__IPV4_Sq
0x180068e54  jmp     loc_180068D0D
0x180068e59  mov     edx, 29h ; ')'
0x180068e5e  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x180068e65  mov     ecx, 40Bh
0x180068e6a  mov     r9d, eax
0x180068e6d  call    WPP_SF_d
0x180068e72  jmp     loc_180068D29
0x180068e77  mov     edx, 2Dh ; '-'
0x180068e7c  mov     dword ptr [rsp+0F0h+IoStatusBlock], ebx
0x180068e80  lea     r9, [rbp+47h+netlong]
0x180068e84  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x180068e8b  call    WPP_SF__IPV4_d
0x180068e90  jmp     loc_180068DAE
```
