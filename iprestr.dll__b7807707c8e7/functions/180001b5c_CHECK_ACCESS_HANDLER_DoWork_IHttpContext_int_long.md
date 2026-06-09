# CHECK_ACCESS_HANDLER::DoWork(IHttpContext *,int,long)

- ea: `0x180001b5c`
- end: `0x180002038`
- name: `?DoWork@CHECK_ACCESS_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@HJ@Z`
- size: `1244`
- prototype: `__int64 __fastcall(__int64, struct IHttpContext *, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180002acc`

## callees

- `0x180001b5c`
- `0x1800028b0`
- `0x180002d54`
- `0x18000369c`
- `0x180004110`
- `0x180004aa6`
- `0x180004ad0`
- `0x180005010`

## import_xrefs

- `msvcrt!strchr` at `0x180001dfa`
- `msvcrt!strchr` at `0x180001dfa`
- `msvcrt!strpbrk` at `0x180001e0f`
- `msvcrt!strpbrk` at `0x180001e0f`
- `msvcrt!strrchr` at `0x180001d82`
- `msvcrt!strrchr` at `0x180001d82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e92`
- `WS2_32!WSAStringToAddressA` at `0x180001e67`
- `WS2_32!WSAStringToAddressA` at `0x180001ec3`
- `WS2_32!WSAStringToAddressA` at `0x180001e67`
- `WS2_32!WSAStringToAddressA` at `0x180001ec3`
- `WS2_32!__imp_WSAGetLastError` at `0x180001e72`
- `WS2_32!__imp_WSAGetLastError` at `0x180001ece`
- `WS2_32!__imp_WSAGetLastError` at `0x180001e72`
- `WS2_32!__imp_WSAGetLastError` at `0x180001ece`
- `WS2_32!__imp_WSAStartup` at `0x180001dcf`
- `WS2_32!__imp_WSAStartup` at `0x180001dcf`
- `WS2_32!__imp_WSACleanup` at `0x180001ef2`
- `WS2_32!__imp_WSACleanup` at `0x180001ef2`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001efc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001efc`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180001f26`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180001f6b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180001f7b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180001f26`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180001f6b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180001f7b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001f85`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001fc7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002003`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001f85`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001fc7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002003`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001bfa`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001bfa`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180001daf`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180001daf`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180001e26`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180001e26`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001e88`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001e88`

## pseudocode

```c
__int64 __fastcall CHECK_ACCESS_HANDLER::DoWork(__int64 a1, struct IHttpContext *a2, int a3, int a4)
{
  __int64 v8; // rbx
  __int64 v9; // r14
  __int64 v10; // rax
  struct sockaddr *v11; // rbx
  int v12; // ecx
  void (*v13)(void *); // r9
  int v14; // r8d
  __int64 v15; // rax
  int v16; // r9d
  int v17; // ebx
  char *v18; // rax
  char *v19; // rsi
  int v20; // r13d
  int Error; // eax
  signed int v22; // ebx
  bool v23; // cc
  char *v24; // rax
  INT v25; // r12d
  signed int LastError; // eax
  unsigned __int16 v28; // r8
  LPINT lpAddressLength; // [rsp+20h] [rbp-E0h]
  struct STRU *v30; // [rsp+28h] [rbp-D8h]
  int AddressLength; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+54h] [rbp-ACh] BYREF
  _QWORD v33[4]; // [rsp+58h] [rbp-A8h] BYREF
  LPSOCKADDR lpAddress; // [rsp+78h] [rbp-88h]
  int v35; // [rsp+80h] [rbp-80h]
  __int16 v36; // [rsp+84h] [rbp-7Ch]
  _BYTE v37[32]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-58h]
  _BYTE v39[32]; // [rsp+C0h] [rbp-40h] BYREF
  char *v40; // [rsp+E0h] [rbp-20h]
  WSAData WSAData; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v42[64]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v8 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v32 = 0;
  v11 = *(struct sockaddr **)(v10 + 104);
  memset_0(v42, 0, sizeof(v42));
  STRU::STRU((STRU *)v37, v42, 0x40u);
  if ( !a3 )
  {
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 44LL) )
    {
      v14 = CHECK_ACCESS_HANDLER::PopulateXFFHeader((CHECK_ACCESS_HANDLER *)a1, a2);
      if ( v14 < 0 )
      {
        (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v9 + 24LL))(
          v9,
          500,
          "Internal Server Error",
          0,
          v14,
          0,
          0);
        goto LABEL_52;
      }
    }
    while ( 1 )
    {
      if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 40LL) )
      {
        AddressLength = 0;
        if ( (int)IP_RESTRICTION_LIST::ReverseDNSLookup(
                    v12,
                    v11,
                    0,
                    v13,
                    lpAddressLength,
                    (struct STRU *)v37,
                    &AddressLength,
                    &v32) < 0
          || (*(int (__fastcall **)(struct IHttpContext *, const char *, __int64))(*(_QWORD *)a2 + 136LL))(
               a2,
               "REMOTE_HOST",
               v38) < 0 )
        {
          goto LABEL_52;
        }
      }
      v17 = IP_RESTRICTION_LIST::Check(
              (IP_RESTRICTION_LIST *)(*(_QWORD *)(a1 + 16) + 16LL),
              a1 + 24,
              v11,
              (struct STRU *)v37,
              (void (*)(void *))lpAddressLength,
              v30,
              a2,
              &v32,
              (int *)(a1 + 24),
              (int *)(a1 + 28));
      if ( v17 < 0 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
        v16 = v17;
        goto LABEL_50;
      }
      if ( v32 )
      {
        STRU::~STRU((STRU *)v37);
        return 1;
      }
LABEL_13:
      if ( !*(_DWORD *)(a1 + 24) )
      {
        v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
        v16 = -2147024891;
        goto LABEL_50;
      }
      if ( !*(_DWORD *)(a1 + 28) )
      {
        v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
        v28 = 504;
        v16 = -2147024891;
        goto LABEL_51;
      }
      if ( !*(_DWORD *)(*(_QWORD *)(a1 + 16) + 44LL) )
        goto LABEL_45;
      v33[0] = 0;
      lpAddress = (LPSOCKADDR)v33;
      v35 = 32;
      v36 = 256;
      if ( !*(_DWORD *)(a1 + 296) )
      {
        BUFFER::~BUFFER((BUFFER *)v33);
LABEL_45:
        STRU::~STRU((STRU *)v37);
        return 0;
      }
      v18 = strrchr(*(const char **)(a1 + 280), 44);
      if ( v18 )
      {
        v20 = 0;
        *v18 = 0;
        v19 = v18 + 1;
      }
      else
      {
        v19 = *(char **)(a1 + 280);
        v20 = 1;
      }
      AddressLength = 0;
      STRA::STRA((STRA *)v39);
      memset_0(&WSAData, 0, sizeof(WSAData));
      Error = WSAStartup(0x202u, &WSAData);
      v22 = Error;
      v23 = Error <= 0;
      if ( Error )
        goto LABEL_21;
      v22 = 0;
      if ( strchr(v19, 46) )
      {
        v25 = 2;
      }
      else
      {
        v24 = strpbrk(v19, "%/");
        if ( v24 )
        {
          v22 = STRA::Copy((STRA *)v39, v19, (_DWORD)v24 - (_DWORD)v19);
          if ( v22 < 0 )
            goto LABEL_38;
          v19 = v40;
        }
        v25 = 23;
      }
      AddressLength = v35;
      if ( WSAStringToAddressA(v19, v25, 0, lpAddress, &AddressLength) == -1 )
      {
        if ( WSAGetLastError() != 10014 )
          goto LABEL_36;
        if ( !BUFFER::Resize((BUFFER *)v33, AddressLength) )
        {
          LastError = GetLastError();
          v22 = LastError;
          if ( LastError > 0 )
            v22 = (unsigned __int16)LastError | 0x80070000;
          if ( v22 < 0 )
            goto LABEL_38;
        }
        if ( WSAStringToAddressA(v19, v25, 0, lpAddress, &AddressLength) == -1 )
        {
LABEL_36:
          Error = WSAGetLastError();
          v22 = Error;
          v23 = Error <= 0;
LABEL_21:
          if ( !v23 )
            v22 = (unsigned __int16)Error | 0x80070000;
          goto LABEL_38;
        }
      }
      *(_WORD *)lpAddress->sa_data = 0;
LABEL_38:
      WSACleanup();
      STRA::~STRA((STRA *)v39);
      if ( v22 < 0 )
      {
        (*(void (__fastcall **)(__int64, __int64, const char *, __int64, signed int, _QWORD, _DWORD))(*(_QWORD *)v9 + 24LL))(
          v9,
          400,
          "Bad Request",
          10,
          v22,
          0,
          0);
        BUFFER::~BUFFER((BUFFER *)v33);
        goto LABEL_52;
      }
      if ( v20 )
      {
        **(_BYTE **)(a1 + 280) = 0;
        *(_DWORD *)(a1 + 296) = 0;
      }
      v11 = lpAddress;
      BUFFER::~BUFFER((BUFFER *)v33);
      if ( !v11 )
        goto LABEL_45;
    }
  }
  if ( a4 >= 0 )
    goto LABEL_13;
  v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  v16 = a4;
LABEL_50:
  v28 = 503;
LABEL_51:
  *(_WORD *)(v15 + 536) = 0;
  CHECK_ACCESS_HANDLER::SetStatus((CHECK_ACCESS_HANDLER *)a1, a2, v28, v16);
LABEL_52:
  STRU::~STRU((STRU *)v37);
  return 2;
}

```

## disassembly

```asm
0x180001b5c  mov     [rsp-8+arg_10], rbx
0x180001b61  push    rbp
0x180001b62  push    rsi
0x180001b63  push    rdi
0x180001b64  push    r12
0x180001b66  push    r13
0x180001b68  push    r14
0x180001b6a  push    r15
0x180001b6c  lea     rbp, [rsp-230h]
0x180001b74  sub     rsp, 330h
0x180001b7b  mov     rax, cs:__security_cookie
0x180001b82  xor     rax, rsp
0x180001b85  mov     [rbp+260h+var_40], rax
0x180001b8c  mov     rax, [rdx]
0x180001b8f  mov     rdi, rcx
0x180001b92  mov     rcx, rdx
0x180001b95  mov     esi, r9d
0x180001b98  mov     r12d, r8d
0x180001b9b  mov     r15, rdx
0x180001b9e  mov     rax, [rax+18h]
0x180001ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ba7  mov     rcx, [r15]
0x180001baa  mov     rbx, rax
0x180001bad  mov     rax, [rcx+20h]
0x180001bb1  mov     rcx, r15
0x180001bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bb9  mov     rcx, [rbx]
0x180001bbc  mov     r14, rax
0x180001bbf  mov     rax, [rcx+8]
0x180001bc3  mov     rcx, rbx
0x180001bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bcb  xor     r13d, r13d
0x180001bce  lea     rcx, [rbp+260h+var_C0]; void *
0x180001bd5  xor     edx, edx; Val
0x180001bd7  mov     [rsp+360h+var_30C], r13d
0x180001bdc  mov     r8d, 80h; Size
0x180001be2  mov     rbx, [rax+68h]
0x180001be6  call    memset_0
0x180001beb  lea     r8d, [r13+40h]
0x180001bef  lea     rdx, [rbp+260h+var_C0]
0x180001bf6  lea     rcx, [rbp+260h+var_2D8]
0x180001bfa  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001c00  test    r12d, r12d
0x180001c03  jnz     short loc_180001C58
0x180001c05  mov     rax, [rdi+10h]
0x180001c09  cmp     [rax+2Ch], r13d
0x180001c0d  jz      short loc_180001C53
0x180001c0f  mov     rdx, r15; struct IHttpContext *
0x180001c12  mov     rcx, rdi; this
0x180001c15  call    ?PopulateXFFHeader@CHECK_ACCESS_HANDLER@@QEAAJPEAVIHttpContext@@@Z; CHECK_ACCESS_HANDLER::PopulateXFFHeader(IHttpContext *)
0x180001c1a  mov     r8d, eax
0x180001c1d  test    eax, eax
0x180001c1f  jns     short loc_180001C53
0x180001c21  mov     rcx, [r14]
0x180001c24  xor     r9d, r9d
0x180001c27  mov     dword ptr [rsp+360h+var_330], r13d
0x180001c2c  mov     edx, 1F4h
0x180001c31  mov     [rsp+360h+var_338], r13
0x180001c36  mov     dword ptr [rsp+360h+lpAddressLength], r8d
0x180001c3b  lea     r8, aInternalServer; "Internal Server Error"
0x180001c42  mov     rax, [rcx+18h]
0x180001c46  mov     rcx, r14
0x180001c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c4e  jmp     loc_180001FFF
0x180001c53  test    r12d, r12d
0x180001c56  jz      short loc_180001C7A
0x180001c58  xor     r12d, r12d
0x180001c5b  test    esi, esi
0x180001c5d  jns     loc_180001D2B
0x180001c63  mov     rax, [r14]
0x180001c66  mov     rcx, r14
0x180001c69  mov     rax, [rax+8]
0x180001c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c72  mov     r9d, esi
0x180001c75  jmp     loc_180001FE6
0x180001c7a  xor     r12d, r12d
0x180001c7d  mov     rax, [rdi+10h]
0x180001c81  cmp     [rax+28h], r12d
0x180001c85  jz      short loc_180001CE1
0x180001c87  lea     rax, [rsp+360h+var_30C]
0x180001c8c  mov     [rsp+360h+AddressLength], r12d
0x180001c91  mov     [rsp+360h+var_328], rax; int *
0x180001c96  xor     r8d, r8d; int
0x180001c99  lea     rax, [rsp+360h+AddressLength]
0x180001c9e  mov     rdx, rbx; struct sockaddr *
0x180001ca1  mov     [rsp+360h+var_330], rax; int *
0x180001ca6  lea     rax, [rbp+260h+var_2D8]
0x180001caa  mov     [rsp+360h+var_338], rax; void *
0x180001caf  call    ?ReverseDNSLookup@IP_RESTRICTION_LIST@@SAJHPEAUsockaddr@@HP6AXPEAX@Z1PEAVSTRU@@PEAJPEAH@Z; IP_RESTRICTION_LIST::ReverseDNSLookup(int,sockaddr *,int,void (*)(void *),void *,STRU *,long *,int *)
0x180001cb4  test    eax, eax
0x180001cb6  js      loc_180001FFF
0x180001cbc  mov     rax, [r15]
0x180001cbf  lea     rdx, aRemoteHost; "REMOTE_HOST"
0x180001cc6  mov     r8, [rbp+260h+var_2B8]
0x180001cca  mov     rcx, r15
0x180001ccd  mov     rax, [rax+88h]
0x180001cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cd9  test    eax, eax
0x180001cdb  js      loc_180001FFF
0x180001ce1  mov     rcx, [rdi+10h]
0x180001ce5  lea     rax, [rdi+1Ch]
0x180001ce9  mov     [rsp+360h+var_318], rax; int *
0x180001cee  lea     rdx, [rdi+18h]; int
0x180001cf2  mov     [rsp+360h+var_320], rdx; int *
0x180001cf7  lea     rax, [rsp+360h+var_30C]
0x180001cfc  mov     [rsp+360h+var_328], rax; int *
0x180001d01  lea     r9, [rbp+260h+var_2D8]; struct STRU *
0x180001d05  add     rcx, 10h; this
0x180001d09  mov     [rsp+360h+var_330], r15; struct IHttpContext *
0x180001d0e  mov     r8, rbx; struct sockaddr *
0x180001d11  call    ?Check@IP_RESTRICTION_LIST@@QEAAJHPEAUsockaddr@@AEAVSTRU@@P6AXPEAX@Z2PEAVIHttpContext@@PEAH55@Z; IP_RESTRICTION_LIST::Check(int,sockaddr *,STRU &,void (*)(void *),void *,IHttpContext *,int *,int *,int *)
0x180001d16  mov     ebx, eax
0x180001d18  test    eax, eax
0x180001d1a  js      loc_180001FD4
0x180001d20  cmp     [rsp+360h+var_30C], r12d
0x180001d25  jnz     loc_180001FC3
0x180001d2b  cmp     [rdi+18h], r12d
0x180001d2f  jz      loc_180001FAC
0x180001d35  cmp     [rdi+1Ch], r12d
0x180001d39  jz      loc_180001F8F
0x180001d3f  mov     rax, [rdi+10h]
0x180001d43  cmp     [rax+2Ch], r12d
0x180001d47  jz      loc_180001F81
0x180001d4d  lea     rax, [rsp+360h+var_308]
0x180001d52  mov     [rsp+360h+var_308], r12
0x180001d57  mov     [rsp+360h+lpAddress], rax
0x180001d5c  mov     [rbp+260h+var_2E0], 20h ; ' '
0x180001d63  mov     [rbp+260h+var_2DC], 100h
0x180001d69  cmp     [rdi+128h], r12d
0x180001d70  jz      loc_180001F76
0x180001d76  mov     rcx, [rdi+118h]; Str
0x180001d7d  mov     edx, 2Ch ; ','; Ch
0x180001d82  call    cs:__imp_strrchr
0x180001d88  mov     rsi, rax
0x180001d8b  test    rax, rax
0x180001d8e  jnz     short loc_180001D9D
0x180001d90  mov     rsi, [rdi+118h]
0x180001d97  lea     r13d, [rax+1]
0x180001d9b  jmp     short loc_180001DA6
0x180001d9d  mov     r13d, r12d
0x180001da0  mov     [rax], r12b
0x180001da3  inc     rsi
0x180001da6  lea     rcx, [rbp+260h+var_2A0]
0x180001daa  mov     [rsp+360h+AddressLength], r12d
0x180001daf  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180001db5  xor     edx, edx; Val
0x180001db7  lea     rcx, [rbp+260h+WSAData]; void *
0x180001dbb  mov     r8d, 198h; Size
0x180001dc1  call    memset_0
0x180001dc6  mov     ecx, 202h; wVersionRequested
0x180001dcb  lea     rdx, [rbp+260h+WSAData]; lpWSAData
0x180001dcf  call    cs:__imp_WSAStartup
0x180001dd5  mov     ebx, eax
0x180001dd7  test    eax, eax
0x180001dd9  jz      short loc_180001DEF
0x180001ddb  jle     loc_180001EF2
0x180001de1  movzx   ebx, ax
0x180001de4  or      ebx, 80070000h
0x180001dea  jmp     loc_180001EF2
0x180001def  mov     edx, 2Eh ; '.'; Val
0x180001df4  mov     rcx, rsi; Str
0x180001df7  mov     ebx, r12d
0x180001dfa  call    cs:__imp_strchr
0x180001e00  test    rax, rax
0x180001e03  jnz     short loc_180001E42
0x180001e05  lea     rdx, Control; "%/"
0x180001e0c  mov     rcx, rsi; Str
0x180001e0f  call    cs:__imp_strpbrk
0x180001e15  test    rax, rax
0x180001e18  jz      short loc_180001E3A
0x180001e1a  sub     eax, esi
0x180001e1c  lea     rcx, [rbp+260h+var_2A0]
0x180001e20  mov     r8d, eax
0x180001e23  mov     rdx, rsi
0x180001e26  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180001e2c  mov     ebx, eax
0x180001e2e  test    eax, eax
0x180001e30  js      loc_180001EF2
0x180001e36  mov     rsi, [rbp+260h+var_280]
0x180001e3a  mov     r12d, 17h
0x180001e40  jmp     short loc_180001E48
0x180001e42  mov     r12d, 2
0x180001e48  mov     eax, [rbp+260h+var_2E0]
0x180001e4b  xor     r8d, r8d; lpProtocolInfo
0x180001e4e  mov     r9, [rsp+360h+lpAddress]; lpAddress
0x180001e53  mov     edx, r12d; AddressFamily
0x180001e56  mov     [rsp+360h+AddressLength], eax
0x180001e5a  mov     rcx, rsi; AddressString
0x180001e5d  lea     rax, [rsp+360h+AddressLength]
0x180001e62  mov     [rsp+360h+lpAddressLength], rax; lpAddressLength
0x180001e67  call    cs:__imp_WSAStringToAddressA
0x180001e6d  cmp     eax, 0FFFFFFFFh
0x180001e70  jnz     short loc_180001EE0
0x180001e72  call    cs:__imp_WSAGetLastError
0x180001e78  cmp     eax, 271Eh
0x180001e7d  jnz     short loc_180001ECE
0x180001e7f  mov     edx, [rsp+360h+AddressLength]
0x180001e83  lea     rcx, [rsp+360h+var_308]
0x180001e88  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180001e8e  test    al, al
0x180001e90  jnz     short loc_180001EAB
0x180001e92  call    cs:__imp_GetLastError
0x180001e98  mov     ebx, eax
0x180001e9a  test    eax, eax
0x180001e9c  jle     short loc_180001EA7
0x180001e9e  movzx   ebx, ax
0x180001ea1  or      ebx, 80070000h
0x180001ea7  test    ebx, ebx
0x180001ea9  js      short loc_180001EEF
0x180001eab  mov     r9, [rsp+360h+lpAddress]; lpAddress
0x180001eb0  lea     rax, [rsp+360h+AddressLength]
0x180001eb5  xor     r8d, r8d; lpProtocolInfo
0x180001eb8  mov     [rsp+360h+lpAddressLength], rax; lpAddressLength
0x180001ebd  mov     edx, r12d; AddressFamily
0x180001ec0  mov     rcx, rsi; AddressString
0x180001ec3  call    cs:__imp_WSAStringToAddressA
0x180001ec9  cmp     eax, 0FFFFFFFFh
0x180001ecc  jnz     short loc_180001EE0
0x180001ece  call    cs:__imp_WSAGetLastError
0x180001ed4  xor     r12d, r12d
0x180001ed7  mov     ebx, eax
0x180001ed9  test    eax, eax
0x180001edb  jmp     loc_180001DDB
0x180001ee0  mov     rax, [rsp+360h+lpAddress]
0x180001ee5  xor     r12d, r12d
0x180001ee8  mov     [rax+2], r12w
0x180001eed  jmp     short loc_180001EF2
0x180001eef  xor     r12d, r12d
0x180001ef2  call    cs:__imp_WSACleanup
0x180001ef8  lea     rcx, [rbp+260h+var_2A0]
0x180001efc  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001f02  test    ebx, ebx
0x180001f04  js      short loc_180001F37
0x180001f06  test    r13d, r13d
0x180001f09  jz      short loc_180001F1C
0x180001f0b  mov     rax, [rdi+118h]
0x180001f12  mov     [rax], r12b
0x180001f15  mov     [rdi+128h], r12d
0x180001f1c  mov     rbx, [rsp+360h+lpAddress]
0x180001f21  lea     rcx, [rsp+360h+var_308]
0x180001f26  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180001f2c  test    rbx, rbx
0x180001f2f  jnz     loc_180001C7D
0x180001f35  jmp     short loc_180001F81
0x180001f37  mov     rax, [r14]
0x180001f3a  lea     r8, aBadRequest; "Bad Request"
0x180001f41  mov     dword ptr [rsp+360h+var_330], r12d
0x180001f46  mov     edx, 190h
0x180001f4b  mov     r9d, 0Ah
0x180001f51  mov     [rsp+360h+var_338], r12
0x180001f56  mov     rcx, r14
0x180001f59  mov     dword ptr [rsp+360h+lpAddressLength], ebx
0x180001f5d  mov     rax, [rax+18h]
0x180001f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f66  lea     rcx, [rsp+360h+var_308]
0x180001f6b  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180001f71  jmp     loc_180001FFF
0x180001f76  lea     rcx, [rsp+360h+var_308]
0x180001f7b  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180001f81  lea     rcx, [rbp+260h+var_2D8]
0x180001f85  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001f8b  xor     eax, eax
0x180001f8d  jmp     short loc_18000200E
0x180001f8f  mov     rax, [r14]
0x180001f92  mov     rcx, r14
0x180001f95  mov     rax, [rax+8]
0x180001f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f9e  mov     r8d, 1F8h
0x180001fa4  mov     r9d, 80070005h
0x180001faa  jmp     short loc_180001FEC
0x180001fac  mov     rax, [r14]
0x180001faf  mov     rcx, r14
0x180001fb2  mov     rax, [rax+8]
0x180001fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fbb  mov     r9d, 80070005h
0x180001fc1  jmp     short loc_180001FE6
0x180001fc3  lea     rcx, [rbp+260h+var_2D8]
0x180001fc7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001fcd  mov     eax, 1
0x180001fd2  jmp     short loc_18000200E
0x180001fd4  mov     rax, [r14]
0x180001fd7  mov     rcx, r14
0x180001fda  mov     rax, [rax+8]
0x180001fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fe3  mov     r9d, ebx; int
0x180001fe6  mov     r8d, 1F7h; unsigned __int16
0x180001fec  mov     rdx, r15; struct IHttpContext *
0x180001fef  mov     [rax+218h], r12w
0x180001ff7  mov     rcx, rdi; this
0x180001ffa  call    ?SetStatus@CHECK_ACCESS_HANDLER@@AEAAXPEAVIHttpContext@@GJ@Z; CHECK_ACCESS_HANDLER::SetStatus(IHttpContext *,ushort,long)
0x180001fff  lea     rcx, [rbp+260h+var_2D8]
0x180002003  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002009  mov     eax, 2
0x18000200e  mov     rcx, [rbp+260h+var_40]
0x180002015  xor     rcx, rsp; StackCookie
0x180002018  call    __security_check_cookie
0x18000201d  mov     rbx, [rsp+360h+arg_10]
0x180002025  add     rsp, 330h
0x18000202c  pop     r15
0x18000202e  pop     r14
  ... truncated ...
```
