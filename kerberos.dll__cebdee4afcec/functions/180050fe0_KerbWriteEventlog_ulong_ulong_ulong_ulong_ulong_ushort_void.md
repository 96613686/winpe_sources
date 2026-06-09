# KerbWriteEventlog(ulong,ulong,ulong,ulong,ulong,ushort * *,void *)

- ea: `0x180050fe0`
- end: `0x1800511cf`
- name: `?KerbWriteEventlog@@YAXKKKKKPEAPEAGPEAX@Z`
- size: `495`
- prototype: `void(unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned __int16 **, void *)`
- caller_count: `14`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800306c8`
- `0x180050078`
- `0x1800501e0`
- `0x180050934`
- `0x180060ce4`
- `0x180092c24`
- `0x180092ec0`
- `0x180092f90`
- `0x180093080`
- `0x1800934e0`
- `0x180093520`
- `0x1800935dc`
- `0x180093694`
- `0x18009378c`

## callees

- `0x1800069a0`
- `0x180033c68`
- `0x180039bac`
- `0x180050fe0`
- `0x180065c48`
- `0x18008b2f4`
- `0x18008b70c`
- `0x180092268`
- `0x180092614`

## import_xrefs

- `ntdll!NtClose` at `0x1800511a0`
- `ntdll!NtClose` at `0x1800511a0`
- `ntdll!NtOpenThreadToken` at `0x180051085`
- `ntdll!NtOpenThreadToken` at `0x180051085`
- `ntdll!NtSetInformationThread` at `0x1800510cd`
- `ntdll!NtSetInformationThread` at `0x180051196`
- `ntdll!NtSetInformationThread` at `0x1800510cd`
- `ntdll!NtSetInformationThread` at `0x180051196`

## string_xrefs

- `0x180051101`: `KerbWriteEventlog`
- `0x18005116d`: `KerbWriteEventlog`
- `0x180051160`: `KerbWriteEventlog failed to report %#x, event id %d, event type %d, category %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall KerbWriteEventlog(
        int a1,
        __int64 a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int16 **a6,
        void *a7)
{
  __int64 v7; // rbx
  unsigned __int16 **v10; // rdi
  char v11; // r14
  unsigned __int16 **v12; // rax
  __int64 v13; // r8
  NTSTATUS v14; // eax
  void *v15; // rax
  struct _RTL_CRITICAL_SECTION *v16; // rcx
  int inited; // eax
  int v18; // eax
  int v19; // [rsp+20h] [rbp-61h]
  int v20; // [rsp+28h] [rbp-59h]
  int v21; // [rsp+30h] [rbp-51h]
  size_t Size; // [rsp+50h] [rbp-31h]
  void *TokenHandle; // [rsp+60h] [rbp-21h] BYREF
  __int64 ThreadInformation; // [rsp+68h] [rbp-19h] BYREF
  _QWORD v25[10]; // [rsp+70h] [rbp-11h] BYREF

  v7 = a4;
  TokenHandle = 0;
  ThreadInformation = 0;
  v10 = a6;
  v11 = 0;
  KerbTracerT::GetCorrelationId(v25);
  if ( (_DWORD)v7 )
  {
    utl::make_unique<unsigned short * [0],0>(&a6, v7 + 1);
    v12 = a6;
    if ( a6 )
    {
      v13 = 0;
      do
      {
        v12[v13] = v10[v13];
        v13 = (unsigned int)(v13 + 1);
      }
      while ( (unsigned int)v13 < (unsigned int)v7 );
      v12[v7] = (unsigned __int16 *)v25[0];
      LOWORD(v7) = v7 + 1;
      v10 = v12;
      a6 = 0;
      v11 = 1;
    }
    utl::unique_ptr<unsigned short * [0],utl::default_delete<unsigned short * [0]>>::~unique_ptr<unsigned short * [0],utl::default_delete<unsigned short * [0]>>(&a6);
  }
  v14 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
  if ( (int)(v14 + 0x80000000) < 0 || v14 == -1073741700 )
  {
    if ( v14 == -1073741700 )
    {
      v15 = 0;
      TokenHandle = 0;
    }
    else
    {
      v15 = TokenHandle;
    }
    if ( !v15
      || NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u) >= 0 )
    {
      v16 = KerbEventLogHandle;
      if ( !KerbEventLogHandle )
      {
        inited = KerbInitEventLogHandle();
        if ( inited )
        {
          KerbTracerT::Log(
            1,
            "KerbWriteEventlog",
            140,
            "KerbReportBufferTooSmallError failed to initialize event log handle: %#x\n",
            inited);
          goto LABEL_21;
        }
        v16 = KerbEventLogHandle;
      }
      LODWORD(Size) = a5;
      v18 = NetpEventlogWriteEx3(v16, v19, v20, v21, (__int64)v10, v7, (__int64)a7, Size);
      if ( v18 && v18 != 183 )
        KerbTracerT::Log(
          1,
          "KerbWriteEventlog",
          161,
          "KerbWriteEventlog failed to report %#x, event id %d, event type %d, category %d\n",
          v18,
          a3,
          a1,
          0);
    }
  }
LABEL_21:
  if ( TokenHandle )
  {
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
    NtClose(TokenHandle);
  }
  if ( v11 )
    KerbFree(v10);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v25);
}

```

## disassembly

```asm
0x180050fe0  push    rbp
0x180050fe2  push    rbx
0x180050fe3  push    rsi
0x180050fe4  push    rdi
0x180050fe5  push    r12
0x180050fe7  push    r14
0x180050fe9  push    r15
0x180050feb  lea     rbp, [rsp-0Fh]
0x180050ff0  sub     rsp, 90h
0x180050ff7  mov     ebx, r9d
0x180050ffa  mov     r15d, r8d
0x180050ffd  mov     r12d, ecx
0x180051000  mov     [rbp+3Fh+TokenHandle], 0
0x180051008  mov     [rbp+3Fh+ThreadInformation], 0
0x180051010  mov     rdi, [rbp+3Fh+arg_28]
0x180051014  xor     r14b, r14b
0x180051017  lea     rcx, [rbp+3Fh+var_50]
0x18005101b  call    ?GetCorrelationId@KerbTracerT@@SA?BV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@XZ; KerbTracerT::GetCorrelationId(void)
0x180051020  nop
0x180051021  test    ebx, ebx
0x180051023  jz      short loc_18005106F
0x180051025  lea     rdx, [rbx+1]
0x180051029  lea     rcx, [rbp+3Fh+arg_28]
0x18005102d  call    ??$make_unique@$$BY0A@PEAG$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@PEAGU?$default_delete@$$BY0A@PEAG@utl@@@0@_K@Z; utl::make_unique<ushort * [0],0>(unsigned __int64)
0x180051032  mov     rax, [rbp+3Fh+arg_28]
0x180051036  test    rax, rax
0x180051039  jz      short loc_180051066
0x18005103b  xor     r8d, r8d
0x18005103e  mov     rcx, [rdi+r8*8]
0x180051042  mov     [rax+r8*8], rcx
0x180051046  inc     r8d
0x180051049  cmp     r8d, ebx
0x18005104c  jb      short loc_18005103E
0x18005104e  mov     rcx, [rbp+3Fh+var_50]
0x180051052  mov     [rax+rbx*8], rcx
0x180051056  inc     ebx
0x180051058  mov     rdi, rax
0x18005105b  mov     [rbp+3Fh+arg_28], 0
0x180051063  mov     r14b, 1
0x180051066  lea     rcx, [rbp+3Fh+arg_28]
0x18005106a  call    ??1?$unique_ptr@$$BY0A@PEAGU?$default_delete@$$BY0A@PEAG@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ushort * [0],utl::default_delete<ushort * [0]>>::~unique_ptr<ushort * [0],utl::default_delete<ushort * [0]>>(void)
0x18005106f  lea     r9, [rbp+3Fh+TokenHandle]; TokenHandle
0x180051073  mov     r8b, 1; OpenAsSelf
0x180051076  mov     edx, 0Ch; DesiredAccess
0x18005107b  mov     rsi, 0FFFFFFFFFFFFFFFEh
0x180051082  mov     rcx, rsi; ThreadHandle
0x180051085  call    cs:__imp_NtOpenThreadToken
0x18005108b  mov     edx, 80000000h
0x180051090  lea     ecx, [rax+rdx]
0x180051093  mov     r8d, 0C000007Ch
0x180051099  test    edx, ecx
0x18005109b  jnz     short loc_1800510A6
0x18005109d  cmp     eax, r8d
0x1800510a0  jnz     loc_18005117E
0x1800510a6  cmp     eax, r8d
0x1800510a9  jnz     short loc_1800510B3
0x1800510ab  xor     eax, eax
0x1800510ad  mov     [rbp+3Fh+TokenHandle], rax
0x1800510b1  jmp     short loc_1800510B7
0x1800510b3  mov     rax, [rbp+3Fh+TokenHandle]
0x1800510b7  test    rax, rax
0x1800510ba  jz      short loc_1800510DB
0x1800510bc  mov     r9d, 8; ThreadInformationLength
0x1800510c2  lea     r8, [rbp+3Fh+ThreadInformation]; ThreadInformation
0x1800510c6  lea     edx, [r9-3]; ThreadInformationClass
0x1800510ca  mov     rcx, rsi; ThreadHandle
0x1800510cd  call    cs:__imp_NtSetInformationThread
0x1800510d3  test    eax, eax
0x1800510d5  js      loc_18005117E
0x1800510db  mov     rcx, cs:?KerbEventLogHandle@@3PEAXEA; void * KerbEventLogHandle
0x1800510e2  test    rcx, rcx
0x1800510e5  jnz     short loc_18005111B
0x1800510e7  call    ?KerbInitEventLogHandle@@YAJXZ; KerbInitEventLogHandle(void)
0x1800510ec  test    eax, eax
0x1800510ee  jz      short loc_180051114
0x1800510f0  mov     [rsp+0C0h+var_A0], eax
0x1800510f4  lea     r9, aKerbreportbuff_4; "KerbReportBufferTooSmallError failed to"...
0x1800510fb  mov     r8d, 8Ch
0x180051101  lea     rdx, aKerbwriteevent; "KerbWriteEventlog"
0x180051108  mov     ecx, 1
0x18005110d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180051112  jmp     short loc_18005117E
0x180051114  mov     rcx, cs:?KerbEventLogHandle@@3PEAXEA; lpCriticalSection
0x18005111b  mov     eax, dword ptr [rbp+3Fh+arg_20]
0x18005111e  mov     dword ptr [rsp+0C0h+Size], eax; Size
0x180051122  mov     rax, [rbp+3Fh+arg_30]
0x180051126  mov     [rsp+0C0h+var_78], rax; __int64
0x18005112b  mov     dword ptr [rsp+0C0h+var_80], ebx; __int16
0x18005112f  mov     [rsp+0C0h+var_88], rdi; __int64
0x180051134  mov     r9d, r15d
0x180051137  mov     edx, r12d
0x18005113a  call    NetpEventlogWriteEx3
0x18005113f  test    eax, eax
0x180051141  jz      short loc_18005117E
0x180051143  cmp     eax, 0B7h
0x180051148  jz      short loc_18005117E
0x18005114a  mov     dword ptr [rsp+0C0h+var_88], 0
0x180051152  mov     [rsp+0C0h+var_90], r12d
0x180051157  mov     [rsp+0C0h+var_98], r15d
0x18005115c  mov     [rsp+0C0h+var_A0], eax
0x180051160  lea     r9, aKerbwriteevent_0; "KerbWriteEventlog failed to report %#x,"...
0x180051167  mov     r8d, 0A1h
0x18005116d  lea     rdx, aKerbwriteevent; "KerbWriteEventlog"
0x180051174  mov     ecx, 1
0x180051179  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18005117e  cmp     [rbp+3Fh+TokenHandle], 0
0x180051183  jz      short loc_1800511A6
0x180051185  mov     r9d, 8; ThreadInformationLength
0x18005118b  lea     r8, [rbp+3Fh+TokenHandle]; ThreadInformation
0x18005118f  lea     edx, [r9-3]; ThreadInformationClass
0x180051193  mov     rcx, rsi; ThreadHandle
0x180051196  call    cs:__imp_NtSetInformationThread
0x18005119c  mov     rcx, [rbp+3Fh+TokenHandle]; Handle
0x1800511a0  call    cs:__imp_NtClose
0x1800511a6  test    r14b, r14b
0x1800511a9  jz      short loc_1800511B4
0x1800511ab  mov     rcx, rdi
0x1800511ae  call    KerbFree
0x1800511b3  nop
0x1800511b4  lea     rcx, [rbp+3Fh+var_50]
0x1800511b8  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800511bd  add     rsp, 90h
0x1800511c4  pop     r15
0x1800511c6  pop     r14
0x1800511c8  pop     r12
0x1800511ca  pop     rdi
0x1800511cb  pop     rsi
0x1800511cc  pop     rbx
0x1800511cd  pop     rbp
0x1800511ce  retn
```
