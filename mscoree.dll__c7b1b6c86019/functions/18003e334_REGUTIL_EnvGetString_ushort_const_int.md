# REGUTIL::EnvGetString(ushort const *,int)

- ea: `0x18003e334`
- end: `0x18003e44c`
- name: `?EnvGetString@REGUTIL@@SAPEAGPEBGH@Z`
- size: `280`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003e4c0`

## callees

- `0x180003070`
- `0x180003740`
- `0x18000c1a8`
- `0x18000d614`
- `0x18003e334`
- `0x18003e6c0`
- `0x180041ac0`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x18003e3dc`
- `KERNEL32!GetEnvironmentVariableW` at `0x18003e415`
- `KERNEL32!GetEnvironmentVariableW` at `0x18003e3dc`
- `KERNEL32!GetEnvironmentVariableW` at `0x18003e415`

## string_xrefs

- `0x18003e3a7`: `COMPlus_`

## pseudocode

```c
unsigned __int16 *__fastcall REGUTIL::EnvGetString(const unsigned __int16 *a1, int a2)
{
  unsigned __int64 v3; // rax
  signed int EnvironmentVariableW; // eax
  unsigned __int64 v5; // rdi
  unsigned __int128 v6; // rax
  WCHAR *v7; // rax
  WCHAR *v8; // rbx
  WCHAR *v10; // [rsp+20h] [rbp-C8h] BYREF
  int v11; // [rsp+28h] [rbp-C0h]
  wchar_t Destination[64]; // [rsp+30h] [rbp-B8h] BYREF

  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  if ( v3 > (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 63 )
    return 0;
  if ( a2 )
  {
    if ( REGUTIL::s_fUseEnvCache
      && !(unsigned int)ProbabilisticNameSet::MayContain((ProbabilisticNameSet *)&unk_180061550, a1) )
    {
      return 0;
    }
    wcscpy_s(Destination, 0x40u, L"COMPlus_");
  }
  else
  {
    Destination[0] = 0;
  }
  wcscat_s(Destination, 0x40u, a1);
  EnvironmentVariableW = GetEnvironmentVariableW(Destination, 0, 0);
  v5 = EnvironmentVariableW;
  if ( !EnvironmentVariableW )
    return 0;
  v6 = (unsigned __int64)EnvironmentVariableW * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v5, 2u) )
    *(_QWORD *)&v6 = -1;
  v7 = (WCHAR *)operator new(v6, *((const struct NoThrow **)&v6 + 1));
  v10 = v7;
  v8 = v7;
  if ( v7 )
    GetEnvironmentVariableW(Destination, v7, v5);
  v11 = 0;
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>((__int64)&v10);
  return v8;
}

```

## disassembly

```asm
0x18003e334  push    rbx
0x18003e336  push    rbp
0x18003e337  push    rsi
0x18003e338  push    rdi
0x18003e339  sub     rsp, 0C8h
0x18003e340  mov     rax, cs:__security_cookie
0x18003e347  xor     rax, rsp
0x18003e34a  mov     [rsp+0E8h+var_38], rax
0x18003e352  mov     rbx, rcx
0x18003e355  mov     eax, edx
0x18003e357  neg     eax
0x18003e359  sbb     rcx, rcx
0x18003e35c  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18003e360  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18003e364  mov     rax, rbp
0x18003e367  add     rcx, 3Fh ; '?'
0x18003e36b  xor     esi, esi
0x18003e36d  inc     rax
0x18003e370  cmp     [rbx+rax*2], si
0x18003e374  jnz     short loc_18003E36D
0x18003e376  cmp     rax, rcx
0x18003e379  ja      loc_18003E42E
0x18003e37f  mov     edi, 40h ; '@'
0x18003e384  test    edx, edx
0x18003e386  jz      short loc_18003E3BD
0x18003e388  cmp     cs:?s_fUseEnvCache@REGUTIL@@0HA, esi; int REGUTIL::s_fUseEnvCache
0x18003e38e  jz      short loc_18003E3A7
0x18003e390  mov     rdx, rbx; unsigned __int16 *
0x18003e393  lea     rcx, unk_180061550; this
0x18003e39a  call    ?MayContain@ProbabilisticNameSet@@QEBAHPEBG@Z; ProbabilisticNameSet::MayContain(ushort const *)
0x18003e39f  test    eax, eax
0x18003e3a1  jz      loc_18003E42E
0x18003e3a7  lea     r8, aComplus; "COMPlus_"
0x18003e3ae  mov     rdx, rdi; SizeInWords
0x18003e3b1  lea     rcx, [rsp+0E8h+Destination]; Destination
0x18003e3b6  call    wcscpy_s
0x18003e3bb  jmp     short loc_18003E3C2
0x18003e3bd  mov     [rsp+0E8h+Destination], si
0x18003e3c2  mov     r8, rbx; Source
0x18003e3c5  lea     rcx, [rsp+0E8h+Destination]; Destination
0x18003e3ca  mov     rdx, rdi; SizeInWords
0x18003e3cd  call    wcscat_s
0x18003e3d2  xor     r8d, r8d; nSize
0x18003e3d5  lea     rcx, [rsp+0E8h+Destination]; lpName
0x18003e3da  xor     edx, edx; lpBuffer
0x18003e3dc  call    cs:__imp_GetEnvironmentVariableW
0x18003e3e2  movsxd  rdi, eax
0x18003e3e5  test    eax, eax
0x18003e3e7  jz      short loc_18003E42E
0x18003e3e9  mov     eax, 2
0x18003e3ee  mul     rdi
0x18003e3f1  cmovb   rax, rbp
0x18003e3f5  mov     rcx, rax; unsigned __int64
0x18003e3f8  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18003e3fd  mov     [rsp+0E8h+var_C8], rax
0x18003e402  mov     rbx, rax
0x18003e405  test    rax, rax
0x18003e408  jz      short loc_18003E41B
0x18003e40a  mov     r8d, edi; nSize
0x18003e40d  lea     rcx, [rsp+0E8h+Destination]; lpName
0x18003e412  mov     rdx, rax; lpBuffer
0x18003e415  call    cs:__imp_GetEnvironmentVariableW
0x18003e41b  lea     rcx, [rsp+0E8h+var_C8]
0x18003e420  mov     [rsp+0E8h+var_C0], esi
0x18003e424  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x18003e429  mov     rax, rbx
0x18003e42c  jmp     short loc_18003E430
0x18003e42e  xor     eax, eax
0x18003e430  mov     rcx, [rsp+0E8h+var_38]
0x18003e438  xor     rcx, rsp; StackCookie
0x18003e43b  call    __security_check_cookie
0x18003e440  add     rsp, 0C8h
0x18003e447  pop     rdi
0x18003e448  pop     rsi
0x18003e449  pop     rbp
0x18003e44a  pop     rbx
0x18003e44b  retn
```
