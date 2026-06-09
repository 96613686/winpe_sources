# ServiceLoadPolicyModule(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180030e60`
- end: `0x180030fde`
- name: `?ServiceLoadPolicyModule@@YAKPEAUHKEY__@@PEBG111@Z`
- size: `382`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180031408`

## callees

- `0x18000575c`
- `0x180022910`
- `0x18002f800`
- `0x180030e60`
- `0x1800a0fb0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180030f39`
- `msvcrt!wcscat_s` at `0x180030f39`
- `ADVAPI32!RegQueryValueExW` at `0x180030ed8`
- `ADVAPI32!RegQueryValueExW` at `0x180030ed8`
- `KERNEL32!GetSystemDirectoryW` at `0x180030ef9`
- `KERNEL32!GetSystemDirectoryW` at `0x180030ef9`

## string_xrefs

- `0x180030e87`: `\tls236.dll`

## pseudocode

```c
__int64 __fastcall ServiceLoadPolicyModule(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  UINT SystemDirectoryW; // eax
  __int64 v7; // rcx
  int v8; // edx
  CTLSPolicyMgr *v9; // rcx
  unsigned int v10; // ebx
  __int64 *v11; // rdx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData[3]; // [rsp+34h] [rbp-CCh] BYREF
  struct _EVENT_DESCRIPTOR v15; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Source[16]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF

  cbData[0] = 4;
  wcscpy(Source, L"\\tls236.dll");
  *(_DWORD *)Data = 0;
  if ( RegQueryValueExW(a1, L"Flags", 0, 0, Data, cbData) )
    *(_DWORD *)Data = 0;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( !SystemDirectoryW )
    goto LABEL_11;
  v7 = -1;
  do
    ++v7;
  while ( Source[v7] );
  if ( (unsigned __int64)SystemDirectoryW + v7 < 0x104 )
  {
    wcscat_s(Buffer, 0x105u, Source);
    v10 = CTLSPolicyMgr::AddPolicyModule(v9, v8, a2, a3, Buffer, *(unsigned int *)Data);
    if ( v10 )
    {
      v11 = TLS_W_LOADPOLICYMODULEDENYALLREQUEST;
      if ( *(_DWORD *)Data )
        v11 = TLS_W_LOADPOLICYMODULEUSEDEFAULT;
      CrimsonHelper::RaiseEvent<unsigned short *>(CrimsonHelper::s_instance, v11, Buffer);
    }
  }
  else
  {
LABEL_11:
    v10 = -2147467259;
    if ( a3 )
    {
      v15 = (struct _EVENT_DESCRIPTOR)TLS_E_LOADPOLICY;
      TLSLogEvent(&v15, 0xC800000D, a3, a2);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180030e60  push    rbp
0x180030e62  push    rbx
0x180030e63  push    rsi
0x180030e64  push    rdi
0x180030e65  push    r14
0x180030e67  lea     rbp, [rsp-190h]
0x180030e6f  sub     rsp, 290h
0x180030e76  mov     rax, cs:__security_cookie
0x180030e7d  xor     rax, rsp
0x180030e80  mov     [rbp+1B0h+var_30], rax
0x180030e87  movups  xmm0, xmmword ptr cs:aTls236Dll; "\\tls236.dll"
0x180030e8e  lea     rax, [rsp+2B0h+cbData]
0x180030e93  mov     [rsp+2B0h+cbData], 4
0x180030e9b  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x180030ea0  mov     rdi, r8
0x180030ea3  movups  xmmword ptr [rsp+2B0h+Source], xmm0
0x180030ea8  lea     rax, [rsp+2B0h+Data]
0x180030ead  mov     rsi, rdx
0x180030eb0  movsd   xmm0, qword ptr cs:aTls236Dll+10h; "dll"
0x180030eb8  lea     rdx, aFlags; "Flags"
0x180030ebf  xor     r14d, r14d
0x180030ec2  movsd   [rsp+2B0h+var_250], xmm0
0x180030ec8  xor     r9d, r9d; lpType
0x180030ecb  mov     dword ptr [rsp+2B0h+Data], r14d
0x180030ed0  xor     r8d, r8d; lpReserved
0x180030ed3  mov     [rsp+2B0h+lpData], rax; lpData
0x180030ed8  call    cs:__imp_RegQueryValueExW
0x180030edf  nop     dword ptr [rax+rax+00h]
0x180030ee4  test    eax, eax
0x180030ee6  jz      short loc_180030EED
0x180030ee8  mov     dword ptr [rsp+2B0h+Data], r14d
0x180030eed  mov     ebx, 104h
0x180030ef2  lea     rcx, [rsp+2B0h+Buffer]; lpBuffer
0x180030ef7  mov     edx, ebx; uSize
0x180030ef9  call    cs:__imp_GetSystemDirectoryW
0x180030f00  nop     dword ptr [rax+rax+00h]
0x180030f05  test    eax, eax
0x180030f07  jz      loc_180030F92
0x180030f0d  lea     rdx, [rsp+2B0h+Source]
0x180030f12  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180030f16  inc     rcx
0x180030f19  cmp     [rdx+rcx*2], r14w
0x180030f1e  jnz     short loc_180030F16
0x180030f20  mov     eax, eax
0x180030f22  add     rcx, rax
0x180030f25  cmp     rcx, rbx
0x180030f28  jnb     short loc_180030F92
0x180030f2a  lea     r8, [rsp+2B0h+Source]; Source
0x180030f2f  mov     edx, 105h; SizeInWords
0x180030f34  lea     rcx, [rsp+2B0h+Buffer]; Destination
0x180030f39  call    cs:__imp_wcscat_s
0x180030f40  nop     dword ptr [rax+rax+00h]
0x180030f45  mov     eax, dword ptr [rsp+2B0h+Data]
0x180030f49  mov     r9, rdi; unsigned __int16 *
0x180030f4c  mov     dword ptr [rsp+2B0h+lpcbData], eax; unsigned int
0x180030f50  mov     r8, rsi; unsigned __int16 *
0x180030f53  lea     rax, [rsp+2B0h+Buffer]
0x180030f58  mov     [rsp+2B0h+lpData], rax; unsigned __int16 *
0x180030f5d  call    ?AddPolicyModule@CTLSPolicyMgr@@QEAAKHPEBG00K@Z; CTLSPolicyMgr::AddPolicyModule(int,ushort const *,ushort const *,ushort const *,ulong)
0x180030f62  mov     ebx, eax
0x180030f64  test    eax, eax
0x180030f66  jz      short loc_180030FBE
0x180030f68  cmp     dword ptr [rsp+2B0h+Data], r14d
0x180030f6d  lea     rax, TLS_W_LOADPOLICYMODULEUSEDEFAULT
0x180030f74  lea     rdx, TLS_W_LOADPOLICYMODULEDENYALLREQUEST
0x180030f7b  cmovnz  rdx, rax
0x180030f7f  lea     r8, [rsp+2B0h+Buffer]
0x180030f84  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180030f8b  call    ??$RaiseEvent@PEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG@Z; CrimsonHelper::RaiseEvent<ushort *>(_EVENT_DESCRIPTOR const &,ushort *)
0x180030f90  jmp     short loc_180030FBE
0x180030f92  mov     ebx, 80004005h
0x180030f97  test    rdi, rdi
0x180030f9a  jz      short loc_180030FBE
0x180030f9c  movups  xmm0, cs:TLS_E_LOADPOLICY
0x180030fa3  mov     r9, rsi
0x180030fa6  lea     rcx, [rsp+2B0h+var_270]; struct _EVENT_DESCRIPTOR
0x180030fab  mov     r8, rdi
0x180030fae  mov     edx, 0C800000Dh; unsigned int
0x180030fb3  movdqu  xmmword ptr [rsp+2B0h+var_270.Id], xmm0
0x180030fb9  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x180030fbe  mov     eax, ebx
0x180030fc0  mov     rcx, [rbp+1B0h+var_30]
0x180030fc7  xor     rcx, rsp; StackCookie
0x180030fca  call    __security_check_cookie
0x180030fcf  add     rsp, 290h
0x180030fd6  pop     r14
0x180030fd8  pop     rdi
0x180030fd9  pop     rsi
0x180030fda  pop     rbx
0x180030fdb  pop     rbp
0x180030fdc  retn
```
