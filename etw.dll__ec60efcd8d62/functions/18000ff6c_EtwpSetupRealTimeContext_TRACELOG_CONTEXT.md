# EtwpSetupRealTimeContext(_TRACELOG_CONTEXT *)

- ea: `0x18000ff6c`
- end: `0x1800104b9`
- name: `?EtwpSetupRealTimeContext@@YAKPEAU_TRACELOG_CONTEXT@@@Z`
- size: `1357`
- prototype: `unsigned int __fastcall(struct _TRACELOG_CONTEXT *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18000fc74`

## callees

- `0x180001560`
- `0x180001eb2`
- `0x180001eca`
- `0x180001ee2`
- `0x180001ff0`
- `0x180002014`
- `0x180002020`
- `0x1800060b4`
- `0x18000ff6c`
- `0x180010ae0`
- `0x180010b38`
- `0x180010c5c`
- `0x1800144f8`
- `0x180015834`

## import_xrefs

- `ntdll!EtwpGetCpuSpeed` at `0x180010441`
- `ntdll!EtwpGetCpuSpeed` at `0x180010441`
- `ntdll!NtAllocateVirtualMemoryEx` at `0x180010232`
- `ntdll!NtAllocateVirtualMemoryEx` at `0x180010232`
- `ntdll!NtFreeVirtualMemory` at `0x180010487`
- `ntdll!NtFreeVirtualMemory` at `0x180010487`
- `ntdll!RtlGetNativeSystemInformation` at `0x18001011c`
- `ntdll!RtlGetNativeSystemInformation` at `0x18001011c`
- `ntdll!RtlInitializeBitMapEx` at `0x1800102ab`
- `ntdll!RtlInitializeBitMapEx` at `0x1800102ab`
- `ntdll!RtlInterlockedSetBitRunEx` at `0x1800102eb`
- `ntdll!RtlInterlockedSetBitRunEx` at `0x1800102eb`
- `ntdll!NtQueryPerformanceCounter` at `0x180010437`
- `ntdll!NtQueryPerformanceCounter` at `0x180010437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010008`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fff6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001001d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fff6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001001d`

## pseudocode

```c
signed int __fastcall EtwpSetupRealTimeContext(struct _TRACELOG_CONTEXT *a1)
{
  int v2; // eax
  HANDLE EventW; // rax
  signed int result; // eax
  HANDLE v5; // rax
  unsigned int i; // r14d
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  void *v9; // rax
  void *v10; // rsi
  unsigned int v11; // ecx
  struct _TRACE_STREAM_HEAP *v12; // rax
  unsigned int v13; // eax
  int v14; // ecx
  unsigned int v15; // ebx
  unsigned int v16; // ecx
  __int64 v17; // rdx
  unsigned int v18; // ebx
  void *v19; // rcx
  __int64 v20; // r9
  int v21; // edx
  int v22; // eax
  PVOID v23; // rdx
  unsigned int v24; // r15d
  unsigned __int64 v25; // rsi
  void *v26; // rax
  void *v27; // r14
  unsigned int v28; // ebx
  unsigned int *v29; // rsi
  unsigned int v30; // ebx
  NTSTATUS v31; // eax
  bool v32; // zf
  PVOID BaseAddress; // [rsp+40h] [rbp-C0h] BYREF
  int v34; // [rsp+48h] [rbp-B8h] BYREF
  ULONG_PTR RegionSize; // [rsp+50h] [rbp-B0h] BYREF
  union _LARGE_INTEGER Counter; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v37[4]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v38[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v39; // [rsp+88h] [rbp-78h]
  __int64 v40; // [rsp+90h] [rbp-70h]
  __int64 v41; // [rsp+98h] [rbp-68h]
  __int64 v42; // [rsp+A0h] [rbp-60h]
  char *v43; // [rsp+A8h] [rbp-58h]
  char *v44; // [rsp+B0h] [rbp-50h]
  char *v45; // [rsp+B8h] [rbp-48h]
  char *v46; // [rsp+C0h] [rbp-40h]
  __int64 v47; // [rsp+C8h] [rbp-38h]
  __int64 v48; // [rsp+D0h] [rbp-30h]
  __int64 v49; // [rsp+D8h] [rbp-28h]
  _BYTE v50[8]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v51; // [rsp+E8h] [rbp-18h]

  v34 = 0;
  memset_0(v38, 0, 0x60u);
  memset_0(v50, 0, 0x40u);
  v2 = *((_DWORD *)a1 + 50);
  *((_DWORD *)a1 + 122) = v2;
  *((_DWORD *)a1 + 26) = 0;
  *((_DWORD *)a1 + 192) = v2;
  *((_DWORD *)a1 + 216) = *((_DWORD *)a1 + 53);
  Counter.QuadPart = 0;
  *((_DWORD *)a1 + 217) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)a1 + 114) = EventW;
  if ( !EventW )
    return GetLastError();
  v5 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)a1 + 113) = v5;
  if ( !v5 )
    return GetLastError();
  for ( i = 0; i < *((_DWORD *)a1 + 216); *(_QWORD *)(*((_QWORD *)a1 + 94) + 8LL * i++) = v8 )
  {
    v7 = operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( !v7 )
      return 14;
    memset_0(v7 + 6, 0, 0x50u);
    v8[2] = -1;
    v8[3] = -1;
    v8[4] = -1;
    v8[5] = 0;
    v8[1] = v8;
    *v8 = v8;
    v9 = operator new(0x188u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v9;
    if ( v9 )
      memset_0(v9, 0, 0x188u);
    v8[7] = v10;
    if ( !v10 )
    {
      v19 = (void *)v8[2];
      if ( v19 != (void *)-1LL )
      {
        v8[3] = v19;
        operator delete(v19);
      }
      operator delete(v8);
      return 14;
    }
    *((_WORD *)v8 + 40) = 392;
  }
  v11 = 1;
  if ( (*((_DWORD *)a1 + 58) & 0x10000000) == 0 )
    v11 = *((_DWORD *)a1 + 7);
  v12 = EtwpHeapCreate(v11);
  *((_QWORD *)a1 + 110) = v12;
  if ( !v12 )
    return 14;
  result = RtlGetNativeSystemInformation(0, v50, 64);
  if ( result < 0 )
    return result;
  v13 = *((_DWORD *)a1 + 233);
  v14 = *((_DWORD *)a1 + 192) * *((_DWORD *)a1 + 216);
  v15 = v51;
  *((_DWORD *)a1 + 232) = v51;
  *((_DWORD *)a1 + 233) = 0;
  v16 = 2 * v14;
  if ( v13 )
  {
    v16 >>= 2;
    if ( v13 >= v16 )
      v16 = v13;
  }
  v17 = *((_QWORD *)a1 + 115);
  if ( v17 )
  {
    v18 = -65536;
    if ( v16 <= 0xFFFEFFFF )
      v18 = (v16 + 0xFFFF) & 0xFFFF0000;
  }
  else
  {
    v18 = v16 <= -1 - v15 ? (v15 + v16 - 1) & ~(v15 - 1) : -v15;
  }
  RegionSize = v18;
  BaseAddress = 0;
  if ( v17 )
  {
    v20 = 541069312;
    v37[2] = 3;
    v37[3] = v17;
    v21 = 2;
    v37[0] = 5;
    v37[1] = 2;
  }
  else
  {
    v20 = 4096;
    v21 = 0;
  }
  v22 = NtAllocateVirtualMemoryEx(
          -1,
          &BaseAddress,
          &RegionSize,
          v20,
          4,
          (unsigned __int64)v37 & -(__int64)(v21 != 0),
          v21);
  v23 = BaseAddress;
  if ( v22 < 0 )
    v23 = 0;
  *((_QWORD *)a1 + 117) = v23;
  if ( !v23 )
    return 14;
  v24 = v18 / v51;
  v25 = 8 * ((unsigned __int64)(v18 / v51 + 63) >> 6);
  if ( !is_mul_ok((unsigned __int64)(v18 / v51 + 63) >> 6, 8u) )
    v25 = -1;
  v26 = operator new(v25, (const struct std::nothrow_t *)&std::nothrow);
  v27 = v26;
  if ( !v26 )
  {
    BaseAddress = (PVOID)*((_QWORD *)a1 + 117);
    RegionSize = 0;
    NtFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, &RegionSize, 0x8000u);
    *((_QWORD *)a1 + 117) = 0;
    return 14;
  }
  memset_0(v26, 0, v25);
  RtlInitializeBitMapEx((char *)a1 + 944, v27, v24);
  *((_DWORD *)a1 + 233) = v18;
  if ( !*((_QWORD *)a1 + 66) )
    goto LABEL_40;
  v28 = ~(v51 - 1) & (*((_DWORD *)a1 + 158) + v51 + 71);
  RtlInterlockedSetBitRunEx((char *)a1 + 944, 0, v28 / v51);
  v29 = (unsigned int *)*((_QWORD *)a1 + 117);
  memset_0(v29, 0, v28);
  *v29 = v28;
  v29[12] = 72;
  v29[13] = 262145;
  memcpy_0(v29 + 18, *((const void **)a1 + 80), *((unsigned int *)a1 + 158));
  v29[12] += (*((_DWORD *)a1 + 158) + 7) & 0xFFFFFFF8;
  v30 = EtwpDoBufferCallback2(a1, (struct _WMI_BUFFER_HEADER *)v29);
  if ( !(unsigned int)EtwpRemovePlaybackEngineBufferReference(a1, (struct _WMI_BUFFER_HEADER *)v29) )
    EtwpFreeRtBuffer(a1, (struct _WMI_BUFFER_HEADER *)v29);
  if ( v30 )
    return v30;
LABEL_40:
  v38[0] = *((_DWORD *)a1 + 190);
  v38[1] = *((_DWORD *)a1 + 233);
  v39 = *((_QWORD *)a1 + 117);
  v40 = *((_QWORD *)a1 + 119);
  v41 = *((_QWORD *)a1 + 114);
  v42 = *((_QWORD *)a1 + 113);
  v44 = (char *)a1 + 896;
  v43 = (char *)a1 + 888;
  v45 = (char *)a1 + 664;
  v46 = (char *)a1 + 668;
  v31 = NtTraceControl_0(11, v38, 96, v38, 96, &v34);
  if ( v31 < 0 )
    return RtlNtStatusToDosError_0(v31);
  v32 = (*((_BYTE *)a1 + 32) & 2) == 0;
  *((_QWORD *)a1 + 70) = v47;
  *((_DWORD *)a1 + 9) = *((_DWORD *)a1 + 118);
  if ( !v32 )
    *((_DWORD *)a1 + 9) = 0;
  NtQueryPerformanceCounter(&Counter, (PLARGE_INTEGER)a1 + 6);
  EtwpGetCpuSpeed((char *)a1 + 44);
  *((_QWORD *)a1 + 8) = v49;
  *((_QWORD *)a1 + 7) = v48;
  EtwpCalculateTimeMultipler(a1);
  return 0;
}

```

## disassembly

```asm
0x18000ff6c  push    rbp
0x18000ff6e  push    rbx
0x18000ff6f  push    rsi
0x18000ff70  push    rdi
0x18000ff71  push    r12
0x18000ff73  push    r13
0x18000ff75  push    r14
0x18000ff77  push    r15
0x18000ff79  lea     rbp, [rsp-38h]
0x18000ff7e  sub     rsp, 138h
0x18000ff85  mov     rax, cs:__security_cookie
0x18000ff8c  xor     rax, rsp
0x18000ff8f  mov     [rbp+70h+var_50], rax
0x18000ff93  xor     r12d, r12d
0x18000ff96  mov     rdi, rcx
0x18000ff99  xor     edx, edx; Val
0x18000ff9b  mov     [rsp+170h+var_128], r12d
0x18000ffa0  lea     rcx, [rbp+70h+var_F0]; void *
0x18000ffa4  lea     r8d, [r12+60h]; Size
0x18000ffa9  call    memset_0
0x18000ffae  xor     edx, edx; Val
0x18000ffb0  lea     r8d, [r12+40h]; Size
0x18000ffb5  lea     rcx, [rbp+70h+var_90]; void *
0x18000ffb9  call    memset_0
0x18000ffbe  mov     eax, [rdi+0C8h]
0x18000ffc4  xor     r9d, r9d; lpName
0x18000ffc7  mov     [rdi+1E8h], eax
0x18000ffcd  xor     r8d, r8d; bInitialState
0x18000ffd0  mov     [rdi+68h], r12d
0x18000ffd4  xor     edx, edx; bManualReset
0x18000ffd6  mov     [rdi+300h], eax
0x18000ffdc  xor     ecx, ecx; lpEventAttributes
0x18000ffde  mov     eax, [rdi+0D4h]
0x18000ffe4  mov     [rdi+360h], eax
0x18000ffea  mov     qword ptr [rsp+170h+Counter], r12
0x18000ffef  mov     [rdi+364h], r12d
0x18000fff6  call    cs:__imp_CreateEventW
0x18000fffc  mov     [rdi+390h], rax
0x180010003  test    rax, rax
0x180010006  jnz     short loc_180010013
0x180010008  call    cs:__imp_GetLastError
0x18001000e  jmp     loc_180010499
0x180010013  xor     r9d, r9d; lpName
0x180010016  xor     r8d, r8d; bInitialState
0x180010019  xor     edx, edx; bManualReset
0x18001001b  xor     ecx, ecx; lpEventAttributes
0x18001001d  call    cs:__imp_CreateEventW
0x180010023  mov     [rdi+388h], rax
0x18001002a  test    rax, rax
0x18001002d  jz      short loc_180010008
0x18001002f  or      r13, 0FFFFFFFFFFFFFFFFh
0x180010033  mov     r14d, r12d
0x180010036  lea     eax, [r13+2]
0x18001003a  cmp     [rdi+360h], r12d
0x180010041  jbe     loc_1800100E9
0x180010047  mov     r15d, 188h
0x18001004d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010054  mov     ecx, 80h; unsigned __int64
0x180010059  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001005e  mov     rbx, rax
0x180010061  test    rax, rax
0x180010064  jz      loc_180010494
0x18001006a  xor     edx, edx; Val
0x18001006c  lea     rcx, [rax+30h]; void *
0x180010070  lea     r8d, [rdx+50h]; Size
0x180010074  call    memset_0
0x180010079  mov     [rbx+10h], r13
0x18001007d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010084  mov     [rbx+18h], r13
0x180010088  mov     rcx, r15; unsigned __int64
0x18001008b  mov     [rbx+20h], r13
0x18001008f  mov     [rbx+28h], r12
0x180010093  mov     [rbx+8], rbx
0x180010097  mov     [rbx], rbx
0x18001009a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001009f  mov     rsi, rax
0x1800100a2  test    rax, rax
0x1800100a5  jz      short loc_1800100B4
0x1800100a7  mov     r8, r15; Size
0x1800100aa  xor     edx, edx; Val
0x1800100ac  mov     rcx, rax; void *
0x1800100af  call    memset_0
0x1800100b4  mov     [rbx+38h], rsi
0x1800100b8  test    rsi, rsi
0x1800100bb  jz      loc_18001017E
0x1800100c1  mov     [rbx+50h], r15w
0x1800100c6  mov     rax, [rdi+2F0h]
0x1800100cd  mov     ecx, r14d
0x1800100d0  mov     [rax+rcx*8], rbx
0x1800100d4  mov     eax, 1
0x1800100d9  add     r14d, eax
0x1800100dc  cmp     r14d, [rdi+360h]
0x1800100e3  jb      loc_18001004D
0x1800100e9  test    dword ptr [rdi+0E8h], 10000000h
0x1800100f3  mov     ecx, eax
0x1800100f5  jnz     short loc_1800100FA
0x1800100f7  mov     ecx, [rdi+1Ch]; unsigned int
0x1800100fa  call    ?EtwpHeapCreate@@YAPEAU_TRACE_STREAM_HEAP@@K@Z; EtwpHeapCreate(ulong)
0x1800100ff  mov     [rdi+370h], rax
0x180010106  test    rax, rax
0x180010109  jz      loc_180010494
0x18001010f  xor     r9d, r9d
0x180010112  lea     rdx, [rbp+70h+var_90]
0x180010116  xor     ecx, ecx
0x180010118  lea     r8d, [r9+40h]
0x18001011c  call    cs:__imp_RtlGetNativeSystemInformation
0x180010122  test    eax, eax
0x180010124  js      loc_180010499
0x18001012a  mov     eax, [rdi+3A4h]
0x180010130  mov     ecx, [rdi+360h]
0x180010136  imul    ecx, [rdi+300h]
0x18001013d  mov     ebx, [rbp+70h+var_88]
0x180010140  mov     [rdi+3A0h], ebx
0x180010146  mov     [rdi+3A4h], r12d
0x18001014d  add     ecx, ecx
0x18001014f  test    eax, eax
0x180010151  jz      short loc_18001015B
0x180010153  shr     ecx, 2
0x180010156  cmp     eax, ecx
0x180010158  cmovnb  ecx, eax
0x18001015b  mov     rdx, [rdi+398h]
0x180010162  test    rdx, rdx
0x180010165  jz      short loc_1800101A4
0x180010167  mov     ebx, 0FFFF0000h
0x18001016c  cmp     ecx, 0FFFEFFFFh
0x180010172  ja      short loc_1800101BB
0x180010174  lea     eax, [rcx+0FFFFh]
0x18001017a  and     ebx, eax
0x18001017c  jmp     short loc_1800101BB
0x18001017e  mov     rcx, [rbx+10h]; Block
0x180010182  cmp     rcx, r13
0x180010185  jz      short loc_180010197
0x180010187  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001018e  mov     [rbx+18h], rcx
0x180010192  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010197  mov     rcx, rbx; Block
0x18001019a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001019f  jmp     loc_180010494
0x1800101a4  or      eax, 0FFFFFFFFh
0x1800101a7  sub     eax, ebx
0x1800101a9  cmp     ecx, eax
0x1800101ab  jbe     short loc_1800101B1
0x1800101ad  neg     ebx
0x1800101af  jmp     short loc_1800101BB
0x1800101b1  dec     ecx
0x1800101b3  add     ecx, ebx
0x1800101b5  dec     ebx
0x1800101b7  not     ebx
0x1800101b9  and     ebx, ecx
0x1800101bb  mov     eax, ebx
0x1800101bd  mov     [rsp+170h+RegionSize], rax
0x1800101c2  mov     eax, 2
0x1800101c7  mov     [rsp+170h+BaseAddress], r12
0x1800101cc  test    rdx, rdx
0x1800101cf  jz      short loc_1800101FC
0x1800101d1  xorps   xmm0, xmm0
0x1800101d4  mov     r9d, 20401000h
0x1800101da  movups  [rsp+170h+var_100], xmm0
0x1800101df  mov     qword ptr [rsp+170h+var_100+8], rdx
0x1800101e4  mov     edx, eax
0x1800101e6  movups  [rsp+170h+var_110], xmm0
0x1800101eb  mov     byte ptr [rsp+170h+var_110], 5
0x1800101f0  mov     qword ptr [rsp+170h+var_110+8], rax
0x1800101f5  mov     byte ptr [rsp+170h+var_100], 3
0x1800101fa  jmp     short loc_180010205
0x1800101fc  mov     r9d, 1000h
0x180010202  mov     edx, r12d
0x180010205  mov     eax, edx
0x180010207  mov     [rsp+170h+var_140], edx
0x18001020b  neg     eax
0x18001020d  lea     r8, [rsp+170h+RegionSize]
0x180010212  lea     rax, [rsp+170h+var_110]
0x180010217  sbb     rcx, rcx
0x18001021a  lea     rdx, [rsp+170h+BaseAddress]
0x18001021f  and     rcx, rax
0x180010222  mov     [rsp+170h+var_148], rcx
0x180010227  mov     rcx, r13
0x18001022a  mov     [rsp+170h+var_150], 4
0x180010232  call    cs:__imp_NtAllocateVirtualMemoryEx
0x180010238  mov     rdx, [rsp+170h+BaseAddress]
0x18001023d  test    eax, eax
0x18001023f  cmovs   rdx, r12
0x180010243  mov     [rdi+3A8h], rdx
0x18001024a  test    rdx, rdx
0x18001024d  jz      loc_180010494
0x180010253  xor     edx, edx
0x180010255  mov     eax, ebx
0x180010257  div     [rbp+70h+var_88]
0x18001025a  mov     r15d, eax
0x18001025d  lea     edx, [rax+3Fh]
0x180010260  mov     eax, 8
0x180010265  shr     rdx, 6
0x180010269  mul     rdx
0x18001026c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010273  mov     rsi, rax
0x180010276  cmovb   rsi, r13
0x18001027a  mov     rcx, rsi; unsigned __int64
0x18001027d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010282  mov     r14, rax
0x180010285  test    rax, rax
0x180010288  jz      loc_180010463
0x18001028e  mov     r8, rsi; Size
0x180010291  xor     edx, edx; Val
0x180010293  mov     rcx, rax; void *
0x180010296  call    memset_0
0x18001029b  lea     rsi, [rdi+3B0h]
0x1800102a2  mov     r8d, r15d
0x1800102a5  mov     rcx, rsi
0x1800102a8  mov     rdx, r14
0x1800102ab  call    cs:__imp_RtlInitializeBitMapEx
0x1800102b1  mov     [rdi+3A4h], ebx
0x1800102b7  cmp     [rdi+210h], r12
0x1800102be  jz      loc_18001036D
0x1800102c4  mov     r8d, [rbp+70h+var_88]
0x1800102c8  xor     edx, edx
0x1800102ca  lea     ecx, [r8+47h]
0x1800102ce  add     ecx, [rdi+278h]
0x1800102d4  lea     eax, [r8-1]
0x1800102d8  not     eax
0x1800102da  and     ecx, eax
0x1800102dc  mov     eax, ecx
0x1800102de  mov     ebx, ecx
0x1800102e0  div     r8d
0x1800102e3  xor     edx, edx
0x1800102e5  mov     rcx, rsi
0x1800102e8  mov     r8d, eax
0x1800102eb  call    cs:__imp_RtlInterlockedSetBitRunEx
0x1800102f1  mov     rsi, [rdi+3A8h]
0x1800102f8  mov     r8d, ebx; Size
0x1800102fb  mov     rcx, rsi; void *
0x1800102fe  xor     edx, edx; Val
0x180010300  call    memset_0
0x180010305  mov     [rsi], ebx
0x180010307  lea     rcx, [rsi+48h]; void *
0x18001030b  mov     dword ptr [rsi+30h], 48h ; 'H'
0x180010312  mov     dword ptr [rsi+34h], 40001h
0x180010319  mov     r8d, [rdi+278h]; Size
0x180010320  mov     rdx, [rdi+280h]; Src
0x180010327  call    memcpy_0
0x18001032c  mov     eax, [rdi+278h]
0x180010332  mov     rdx, rsi; struct _WMI_BUFFER_HEADER *
0x180010335  add     eax, 7
0x180010338  mov     rcx, rdi; struct _TRACELOG_CONTEXT *
0x18001033b  and     eax, 0FFFFFFF8h
0x18001033e  add     [rsi+30h], eax
0x180010341  call    ?EtwpDoBufferCallback2@@YAKPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z; EtwpDoBufferCallback2(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)
0x180010346  mov     rdx, rsi; struct _WMI_BUFFER_HEADER *
0x180010349  mov     rcx, rdi; struct _TRACELOG_CONTEXT *
0x18001034c  mov     ebx, eax
0x18001034e  call    ?EtwpRemovePlaybackEngineBufferReference@@YAJPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z; EtwpRemovePlaybackEngineBufferReference(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)
0x180010353  test    eax, eax
0x180010355  jnz     short loc_180010362
0x180010357  mov     rdx, rsi; struct _WMI_BUFFER_HEADER *
0x18001035a  mov     rcx, rdi; struct _TRACELOG_CONTEXT *
0x18001035d  call    ?EtwpFreeRtBuffer@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z; EtwpFreeRtBuffer(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)
0x180010362  test    ebx, ebx
0x180010364  jz      short loc_18001036D
0x180010366  mov     eax, ebx
0x180010368  jmp     loc_180010499
0x18001036d  mov     eax, [rdi+2F8h]
0x180010373  lea     r9, [rbp+70h+var_F0]
0x180010377  mov     [rbp+70h+var_F0], eax
0x18001037a  lea     rdx, [rbp+70h+var_F0]
0x18001037e  mov     eax, [rdi+3A4h]
0x180010384  mov     r8d, 60h ; '`'
0x18001038a  mov     [rbp+70h+var_EC], eax
0x18001038d  mov     rax, [rdi+3A8h]
0x180010394  mov     [rbp+70h+var_E8], rax
0x180010398  mov     rax, [rdi+3B8h]
0x18001039f  lea     ecx, [r8-55h]
0x1800103a3  mov     [rbp+70h+var_E0], rax
0x1800103a7  mov     rax, [rdi+390h]
0x1800103ae  mov     [rbp+70h+var_D8], rax
0x1800103b2  mov     rax, [rdi+388h]
0x1800103b9  mov     [rbp+70h+var_D0], rax
0x1800103bd  lea     rax, [rdi+380h]
0x1800103c4  mov     [rbp+70h+var_C0], rax
0x1800103c8  lea     rax, [rdi+378h]
0x1800103cf  mov     [rbp+70h+var_C8], rax
0x1800103d3  lea     rax, [rdi+298h]
0x1800103da  mov     [rbp+70h+var_B8], rax
0x1800103de  lea     rax, [rdi+29Ch]
0x1800103e5  mov     [rbp+70h+var_B0], rax
0x1800103e9  lea     rax, [rsp+170h+var_128]
0x1800103ee  mov     [rsp+170h+var_148], rax
0x1800103f3  mov     [rsp+170h+var_150], 60h ; '`'
0x1800103fb  call    NtTraceControl_0
0x180010400  test    eax, eax
0x180010402  jns     short loc_180010410
0x180010404  mov     ecx, eax; Status
0x180010406  call    RtlNtStatusToDosError_0
0x18001040b  jmp     loc_180010499
0x180010410  test    byte ptr [rdi+20h], 2
0x180010414  mov     rax, [rbp+70h+var_A8]
0x180010418  mov     [rdi+230h], rax
0x18001041f  mov     eax, [rdi+1D8h]
0x180010425  mov     [rdi+24h], eax
0x180010428  jz      short loc_18001042E
0x18001042a  mov     [rdi+24h], r12d
0x18001042e  lea     rdx, [rdi+30h]; Frequency
  ... truncated ...
```
