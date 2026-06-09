# Imapi2Utility::SQMLogRawImageSession(long,ulong,int,int,int)

- ea: `0x180047040`
- end: `0x180047213`
- name: `?SQMLogRawImageSession@Imapi2Utility@@YAJJKHHH@Z`
- size: `467`
- prototype: `__int64 __fastcall(Imapi2Utility *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003cf30`

## callees

- `0x180047040`
- `0x1800489d0`
- `0x180048a34`
- `0x180048b14`
- `0x180048b8c`
- `0x18004984a`
- `0x180049880`

## import_xrefs

- `ole32!CoCreateGuid` at `0x1800470a4`
- `ole32!CoCreateGuid` at `0x1800470a4`
- `KERNEL32!GetVersionExW` at `0x1800470bd`
- `KERNEL32!GetVersionExW` at `0x1800470bd`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::SQMLogRawImageSession(
        Imapi2Utility *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  unsigned int v7; // esi
  HRESULT v10; // edi
  const struct _EVENT_DESCRIPTOR *v11; // rcx
  unsigned int v12; // r8d
  const struct _EVENT_DESCRIPTOR *v13; // rcx
  const struct _EVENT_DESCRIPTOR *v14; // rcx
  const struct _EVENT_DESCRIPTOR *v15; // rcx
  const struct _EVENT_DESCRIPTOR *v16; // rcx
  const struct _EVENT_DESCRIPTOR *v17; // rcx
  GUID *p_pguid; // rcx
  struct _GUID *started; // rbx
  const struct _EVENT_DESCRIPTOR *v20; // rcx
  const struct _EVENT_DESCRIPTOR *v21; // rcx
  const struct _EVENT_DESCRIPTOR *v22; // rcx
  const struct _EVENT_DESCRIPTOR *v23; // rcx
  const struct _EVENT_DESCRIPTOR *v24; // rcx
  const struct _EVENT_DESCRIPTOR *v25; // rcx
  GUID pguid; // [rsp+20h] [rbp-E0h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+30h] [rbp-D0h] BYREF

  v7 = (unsigned int)this;
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  pguid = 0;
  if ( !(unsigned int)WinSqmIsOptedIn() )
    return 1;
  v10 = CoCreateGuid(&pguid);
  if ( v10 >= 0 )
  {
    VersionInformation.dwOSVersionInfoSize = 276;
    if ( GetVersionExW(&VersionInformation) )
    {
      if ( VersionInformation.dwMajorVersion > 6
        || VersionInformation.dwMajorVersion >= 6 && VersionInformation.dwMinorVersion )
      {
        started = WinSqmStartSession(&pguid, 0x110C01u, v12);
        _WinSqmDWORDEvent(v20, started, 0x14E1u, 0x10000u);
        _WinSqmDWORDEvent(v21, started, 0x14E7u, v7);
        _WinSqmDWORDEvent(v22, started, 0x1503u, a2);
        _WinSqmDWORDEvent(v23, started, 0x14E8u, a3);
        _WinSqmDWORDEvent(v24, started, 0x14E9u, a4);
        _WinSqmDWORDEvent(v25, started, 0x14EAu, a5);
        p_pguid = started;
      }
      else
      {
        _WinSqmDWORDEvent(v11, &pguid, 0x14E1u, 0x10000u);
        _WinSqmDWORDEvent(v13, &pguid, 0x14E7u, v7);
        _WinSqmDWORDEvent(v14, &pguid, 0x1503u, a2);
        _WinSqmDWORDEvent(v15, &pguid, 0x14E8u, a3);
        _WinSqmDWORDEvent(v16, &pguid, 0x14E9u, a4);
        _WinSqmDWORDEvent(v17, &pguid, 0x14EAu, a5);
        p_pguid = &pguid;
      }
      WinSqmEndSession(p_pguid);
    }
    else
    {
      return (unsigned int)-2147418113;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180047040  push    rbp
0x180047042  push    rbx
0x180047043  push    rsi
0x180047044  push    rdi
0x180047045  push    r12
0x180047047  push    r14
0x180047049  push    r15
0x18004704b  lea     rbp, [rsp-60h]
0x180047050  sub     rsp, 160h
0x180047057  mov     rax, cs:__security_cookie
0x18004705e  xor     rax, rsp
0x180047061  mov     [rbp+90h+var_40], rax
0x180047065  mov     r15d, r8d
0x180047068  mov     r14d, edx
0x18004706b  mov     esi, ecx
0x18004706d  mov     ebx, 114h
0x180047072  mov     r8d, ebx; Size
0x180047075  lea     rcx, [rsp+190h+VersionInformation]; void *
0x18004707a  xor     edx, edx; Val
0x18004707c  mov     r12d, r9d
0x18004707f  call    memset_0
0x180047084  xorps   xmm0, xmm0
0x180047087  movups  xmmword ptr [rsp+190h+pguid.Data1], xmm0
0x18004708c  call    ?WinSqmIsOptedIn@@YAHXZ; WinSqmIsOptedIn(void)
0x180047091  test    eax, eax
0x180047093  jnz     short loc_18004709F
0x180047095  mov     eax, 1
0x18004709a  jmp     loc_1800471F5
0x18004709f  lea     rcx, [rsp+190h+pguid]; pguid
0x1800470a4  call    cs:__imp_CoCreateGuid
0x1800470aa  mov     edi, eax
0x1800470ac  test    eax, eax
0x1800470ae  js      loc_1800471F3
0x1800470b4  lea     rcx, [rsp+190h+VersionInformation]; lpVersionInformation
0x1800470b9  mov     [rsp+190h+VersionInformation.dwOSVersionInfoSize], ebx
0x1800470bd  call    cs:__imp_GetVersionExW
0x1800470c3  test    eax, eax
0x1800470c5  jnz     short loc_1800470D1
0x1800470c7  mov     edi, 8000FFFFh
0x1800470cc  jmp     loc_1800471F3
0x1800470d1  cmp     [rsp+190h+VersionInformation.dwMajorVersion], 6
0x1800470d6  ja      loc_18004716C
0x1800470dc  jb      short loc_1800470E9
0x1800470de  cmp     [rsp+190h+VersionInformation.dwMinorVersion], 0
0x1800470e3  ja      loc_18004716C
0x1800470e9  mov     r9d, 10000h; unsigned int
0x1800470ef  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x1800470f4  mov     r8d, 14E1h; unsigned int
0x1800470fa  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800470ff  mov     r9d, esi; unsigned int
0x180047102  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x180047107  mov     r8d, 14E7h; unsigned int
0x18004710d  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180047112  mov     r9d, r14d; unsigned int
0x180047115  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x18004711a  mov     r8d, 1503h; unsigned int
0x180047120  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180047125  mov     r9d, r15d; unsigned int
0x180047128  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x18004712d  mov     r8d, 14E8h; unsigned int
0x180047133  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180047138  mov     r9d, r12d; unsigned int
0x18004713b  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x180047140  mov     r8d, 14E9h; unsigned int
0x180047146  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x18004714b  mov     r9d, [rbp+90h+arg_20]; unsigned int
0x180047152  lea     rdx, [rsp+190h+pguid]; struct _GUID *
0x180047157  mov     r8d, 14EAh; unsigned int
0x18004715d  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180047162  lea     rcx, [rsp+190h+pguid]
0x180047167  jmp     loc_1800471EE
0x18004716c  mov     edx, 110C01h; unsigned int
0x180047171  lea     rcx, [rsp+190h+pguid]; struct _GUID *
0x180047176  call    ?WinSqmStartSession@@YAPEAU_GUID@@PEAU1@KK@Z; WinSqmStartSession(_GUID *,ulong,ulong)
0x18004717b  mov     r9d, 10000h; unsigned int
0x180047181  mov     r8d, 14E1h; unsigned int
0x180047187  mov     rdx, rax; struct _GUID *
0x18004718a  mov     rbx, rax
0x18004718d  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x180047192  mov     r9d, esi; unsigned int
0x180047195  mov     r8d, 14E7h; unsigned int
0x18004719b  mov     rdx, rbx; struct _GUID *
0x18004719e  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800471a3  mov     r9d, r14d; unsigned int
0x1800471a6  mov     r8d, 1503h; unsigned int
0x1800471ac  mov     rdx, rbx; struct _GUID *
0x1800471af  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800471b4  mov     r9d, r15d; unsigned int
0x1800471b7  mov     r8d, 14E8h; unsigned int
0x1800471bd  mov     rdx, rbx; struct _GUID *
0x1800471c0  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800471c5  mov     r9d, r12d; unsigned int
0x1800471c8  mov     r8d, 14E9h; unsigned int
0x1800471ce  mov     rdx, rbx; struct _GUID *
0x1800471d1  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800471d6  mov     r9d, [rbp+90h+arg_20]; unsigned int
0x1800471dd  mov     r8d, 14EAh; unsigned int
0x1800471e3  mov     rdx, rbx; struct _GUID *
0x1800471e6  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800471eb  mov     rcx, rbx; struct _GUID *
0x1800471ee  call    ?WinSqmEndSession@@YAXPEAU_GUID@@@Z; WinSqmEndSession(_GUID *)
0x1800471f3  mov     eax, edi
0x1800471f5  mov     rcx, [rbp+90h+var_40]
0x1800471f9  xor     rcx, rsp; StackCookie
0x1800471fc  call    __security_check_cookie
0x180047201  add     rsp, 160h
0x180047208  pop     r15
0x18004720a  pop     r14
0x18004720c  pop     r12
0x18004720e  pop     rdi
0x18004720f  pop     rsi
0x180047210  pop     rbx
0x180047211  pop     rbp
0x180047212  retn
```
