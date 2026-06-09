# IsDll(ushort const *)

- ea: `0x140001950`
- end: `0x140001ba9`
- name: `?IsDll@@YAHPEBG@Z`
- size: `601`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x140001f28`
- `0x140004694`

## callees

- `0x140001950`
- `0x14000a10c`
- `0x14000ad80`
- `0x14000b010`
- `0x14000b898`
- `0x14000c51c`
- `0x1400102cc`
- `0x140013200`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140001b79`
- `KERNEL32!HeapFree` at `0x140001b79`
- `KERNEL32!GetProcessHeap` at `0x140001b64`
- `KERNEL32!GetProcessHeap` at `0x140001b64`

## pseudocode

```c
__int64 __fastcall IsDll(const unsigned __int16 *a1)
{
  unsigned int v1; // r9d
  unsigned int v2; // r9d
  unsigned int matched; // edi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  _DWORD v7[2]; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v8; // [rsp+30h] [rbp-D8h]
  void *v9[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+48h] [rbp-C0h]
  __int64 v11; // [rsp+50h] [rbp-B8h]
  char *v12; // [rsp+58h] [rbp-B0h]
  __int64 v13; // [rsp+60h] [rbp-A8h]
  __int64 v14; // [rsp+68h] [rbp-A0h]
  unsigned int v15; // [rsp+78h] [rbp-90h] BYREF
  __int64 v16; // [rsp+7Ch] [rbp-8Ch]
  LPVOID lpMem; // [rsp+88h] [rbp-80h]
  __int16 v18; // [rsp+90h] [rbp-78h] BYREF

  v16 = 512;
  lpMem = &v18;
  v15 = 2;
  v18 = 0;
  SString::Set((SString *)&v15, a1);
  v1 = HIDWORD(v16);
  if ( (v16 & 0x200000000LL) != 0 && ((BYTE4(v16) & 7) != 7 || SString::s_IsANSIMultibyte) )
  {
    if ( !(unsigned int)SString::ScanASCII((SString *)&v15) )
      SString::ConvertToUnicode((SString *)&v15);
    v1 = HIDWORD(v16);
  }
  if ( (v15 >> ((v1 & 1) == 0)) - 1 <= 4 )
  {
    matched = 0;
  }
  else
  {
    if ( (~(v1 >> 1) & 1) == 0 )
    {
      if ( !(unsigned int)SString::ScanASCII((SString *)&v15) )
        SString::ConvertToUnicode((SString *)&v15);
      LOBYTE(v1) = BYTE4(v16);
    }
    if ( (v1 & 0x10) != 0 )
    {
      SBuffer::ReallocateBuffer(&v15, (unsigned int)v16, 1);
      LOBYTE(v1) = BYTE4(v16);
    }
    if ( (v1 & 2) != 0 && ((v1 & 7) != 7 || SString::s_IsANSIMultibyte) )
    {
      if ( !(unsigned int)SString::ScanASCII((SString *)&v15) )
        SString::ConvertToUnicode((SString *)&v15);
      LOBYTE(v1) = BYTE4(v16);
    }
    v2 = (v1 & 1) == 0;
    v12 = (char *)lpMem + (int)(((v15 >> v2) - 1) << v2);
    LODWORD(v13) = v2;
    v10 = v13;
    v9[1] = &v12[-4 << v2];
    v11 = v14;
    v7[0] = 10;
    v7[1] = 10;
    v9[0] = L".dll";
    LODWORD(v8) = 276;
    matched = SString::MatchCaseInsensitive(
                (SString *)&v15,
                (const struct SString::CIterator *)&v9[1],
                (const struct SString *)v7,
                v2);
    if ( (v8 & 8) != 0 )
      operator delete(v9[0]);
  }
  if ( (v16 & 0x800000000LL) != 0 )
  {
    v4 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v4);
    }
  }
  return matched;
}

```

## disassembly

```asm
0x140001950  mov     rax, rsp
0x140001953  mov     [rax+10h], rbx
0x140001957  mov     [rax+18h], rsi
0x14000195b  mov     [rax+20h], rdi
0x14000195f  push    rbp
0x140001960  lea     rbp, [rax-1A8h]
0x140001967  sub     rsp, 2A0h
0x14000196e  mov     rax, cs:__security_cookie
0x140001975  xor     rax, rsp
0x140001978  mov     [rbp+1A0h+var_10], rax
0x14000197f  xor     esi, esi
0x140001981  mov     qword ptr [rsp+2A0h+var_230], rsi
0x140001986  mov     [rsp+2A0h+var_22C], 200h
0x14000198f  mov     [rbp+1A0h+lpMem], rsi
0x140001993  lea     rax, [rbp+1A0h+var_218]
0x140001997  mov     [rbp+1A0h+lpMem], rax
0x14000199b  mov     [rsp+2A0h+var_230], 2
0x1400019a3  mov     rax, [rbp+1A0h+lpMem]
0x1400019a7  mov     [rax], si
0x1400019aa  mov     rdx, rcx; unsigned __int16 *
0x1400019ad  lea     rcx, [rsp+2A0h+var_230]; this
0x1400019b2  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x1400019b7  nop
0x1400019b8  mov     r9d, dword ptr [rsp+2A0h+var_22C+4]
0x1400019bd  test    r9b, 2
0x1400019c1  jz      short loc_1400019F2
0x1400019c3  mov     eax, r9d
0x1400019c6  and     eax, 7
0x1400019c9  cmp     al, 7
0x1400019cb  jnz     short loc_1400019D5
0x1400019cd  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, esi; int SString::s_IsANSIMultibyte
0x1400019d3  jz      short loc_1400019F2
0x1400019d5  lea     rcx, [rsp+2A0h+var_230]; this
0x1400019da  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x1400019df  test    eax, eax
0x1400019e1  jnz     short loc_1400019ED
0x1400019e3  lea     rcx, [rsp+2A0h+var_230]; this
0x1400019e8  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1400019ed  mov     r9d, dword ptr [rsp+2A0h+var_22C+4]
0x1400019f2  mov     ecx, r9d
0x1400019f5  not     ecx
0x1400019f7  mov     ebx, 1
0x1400019fc  and     ecx, ebx
0x1400019fe  mov     edx, [rsp+2A0h+var_230]
0x140001a02  shr     edx, cl
0x140001a04  sub     edx, ebx
0x140001a06  cmp     edx, 4
0x140001a09  jbe     loc_140001B46
0x140001a0f  mov     eax, r9d
0x140001a12  shr     eax, 1
0x140001a14  not     eax
0x140001a16  test    bl, al
0x140001a18  jnz     short loc_140001A37
0x140001a1a  lea     rcx, [rsp+2A0h+var_230]; this
0x140001a1f  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x140001a24  test    eax, eax
0x140001a26  jnz     short loc_140001A32
0x140001a28  lea     rcx, [rsp+2A0h+var_230]; this
0x140001a2d  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140001a32  mov     r9d, dword ptr [rsp+2A0h+var_22C+4]
0x140001a37  test    r9b, 10h
0x140001a3b  jz      short loc_140001A53
0x140001a3d  mov     r8d, ebx
0x140001a40  mov     edx, dword ptr [rsp+2A0h+var_22C]
0x140001a44  lea     rcx, [rsp+2A0h+var_230]
0x140001a49  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x140001a4e  mov     r9d, dword ptr [rsp+2A0h+var_22C+4]
0x140001a53  test    r9b, 2
0x140001a57  jz      short loc_140001A88
0x140001a59  mov     eax, r9d
0x140001a5c  and     eax, 7
0x140001a5f  cmp     al, 7
0x140001a61  jnz     short loc_140001A6B
0x140001a63  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, esi; int SString::s_IsANSIMultibyte
0x140001a69  jz      short loc_140001A88
0x140001a6b  lea     rcx, [rsp+2A0h+var_230]; this
0x140001a70  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x140001a75  test    eax, eax
0x140001a77  jnz     short loc_140001A83
0x140001a79  lea     rcx, [rsp+2A0h+var_230]; this
0x140001a7e  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140001a83  mov     r9d, dword ptr [rsp+2A0h+var_22C+4]
0x140001a88  not     r9d
0x140001a8b  and     r9d, ebx; unsigned int
0x140001a8e  mov     eax, [rsp+2A0h+var_230]
0x140001a92  mov     ecx, r9d
0x140001a95  shr     eax, cl
0x140001a97  sub     eax, ebx
0x140001a99  shl     eax, cl
0x140001a9b  movsxd  r8, eax
0x140001a9e  add     r8, [rbp+1A0h+lpMem]
0x140001aa2  mov     qword ptr [rsp+2A0h+var_258+8], r8
0x140001aa7  mov     dword ptr [rsp+2A0h+var_248], r9d
0x140001aac  movups  xmm0, [rsp+2A0h+var_258+8]
0x140001ab1  movups  xmmword ptr [rsp+2A0h+var_270+8], xmm0
0x140001ab6  movsd   xmm1, [rsp+2A0h+var_240]
0x140001abc  mov     eax, 0FFFFFFFCh
0x140001ac1  shl     eax, cl
0x140001ac3  movsxd  rcx, eax
0x140001ac6  add     rcx, r8
0x140001ac9  mov     [rsp+2A0h+var_270+8], rcx
0x140001ace  movups  xmm0, xmmword ptr [rsp+2A0h+var_270+8]
0x140001ad3  movups  xmmword ptr [rsp+2A0h+var_270+8], xmm0
0x140001ad8  movsd   qword ptr [rsp+2A0h+var_258], xmm1
0x140001ade  mov     eax, 0Ah
0x140001ae3  mov     [rsp+2A0h+var_280], eax
0x140001ae7  mov     [rsp+2A0h+var_27C], eax
0x140001aeb  mov     dword ptr [rsp+2A0h+var_278], 10h
0x140001af3  lea     rax, aDll; ".dll"
0x140001afa  mov     [rsp+2A0h+var_270], rax
0x140001aff  mov     ecx, dword ptr [rsp+2A0h+var_278]
0x140001b03  and     ecx, 0FFFFFFF8h
0x140001b06  mov     dword ptr [rsp+2A0h+var_278], ecx
0x140001b0a  mov     eax, ecx
0x140001b0c  or      eax, 4
0x140001b0f  mov     dword ptr [rsp+2A0h+var_278], eax
0x140001b13  or      ecx, 104h
0x140001b19  mov     dword ptr [rsp+2A0h+var_278], ecx
0x140001b1d  lea     r8, [rsp+2A0h+var_280]; struct SString *
0x140001b22  lea     rdx, [rsp+2A0h+var_270+8]; struct SString::CIterator *
0x140001b27  lea     rcx, [rsp+2A0h+var_230]; this
0x140001b2c  call    ?MatchCaseInsensitive@SString@@QEBAHAEBVCIterator@1@AEBV1@K@Z; SString::MatchCaseInsensitive(SString::CIterator const &,SString const &,ulong)
0x140001b31  mov     edi, eax
0x140001b33  test    byte ptr [rsp+2A0h+var_278], 8
0x140001b38  jz      short loc_140001B48
0x140001b3a  mov     rcx, [rsp+2A0h+var_270]; lpMem
0x140001b3f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001b44  jmp     short loc_140001B48
0x140001b46  mov     edi, esi
0x140001b48  test    byte ptr [rsp+2A0h+var_22C+4], 8
0x140001b4d  jz      short loc_140001B7F
0x140001b4f  mov     rbx, [rbp+1A0h+lpMem]
0x140001b53  test    rbx, rbx
0x140001b56  jz      short loc_140001B7F
0x140001b58  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140001b5f  test    rax, rax
0x140001b62  jnz     short loc_140001B71
0x140001b64  call    cs:__imp_GetProcessHeap
0x140001b6a  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140001b71  mov     r8, rbx; lpMem
0x140001b74  xor     edx, edx; dwFlags
0x140001b76  mov     rcx, rax; hHeap
0x140001b79  call    cs:__imp_HeapFree
0x140001b7f  mov     eax, edi
0x140001b81  mov     rcx, [rbp+1A0h+var_10]
0x140001b88  xor     rcx, rsp; StackCookie
0x140001b8b  call    __security_check_cookie
0x140001b90  lea     r11, [rsp+2A0h+var_s0]
0x140001b98  mov     rbx, [r11+18h]
0x140001b9c  mov     rsi, [r11+20h]
0x140001ba0  mov     rdi, [r11+28h]
0x140001ba4  mov     rsp, r11
0x140001ba7  pop     rbp
0x140001ba8  retn
```
