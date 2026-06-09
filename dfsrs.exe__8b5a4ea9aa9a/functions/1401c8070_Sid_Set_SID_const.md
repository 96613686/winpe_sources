# Sid::Set(_SID const *)

- ea: `0x1401c8070`
- end: `0x1401c8183`
- name: `?Set@Sid@@QEAAPEAVFrsStatus@@PEBU_SID@@@Z`
- size: `275`
- prototype: `struct FrsStatus *(Sid *__hidden this, const struct _SID *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14019ac38`
- `0x1401c67b8`
- `0x1401c6c30`
- `0x1401c7b08`

## callees

- `0x1401b9494`
- `0x1401c6770`
- `0x1401c8070`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401c8149`
- `KERNEL32!GetLastError` at `0x1401c8149`
- `KERNEL32!GetCurrentThreadId` at `0x1401c8098`
- `KERNEL32!GetCurrentThreadId` at `0x1401c80f8`
- `KERNEL32!GetCurrentThreadId` at `0x1401c813b`
- `KERNEL32!GetCurrentThreadId` at `0x1401c8098`
- `KERNEL32!GetCurrentThreadId` at `0x1401c80f8`
- `KERNEL32!GetCurrentThreadId` at `0x1401c813b`
- `ADVAPI32!GetLengthSid` at `0x1401c80e7`
- `ADVAPI32!GetLengthSid` at `0x1401c80e7`
- `ADVAPI32!IsValidSid` at `0x1401c8088`
- `ADVAPI32!IsValidSid` at `0x1401c8088`
- `ADVAPI32!CopySid` at `0x1401c8128`
- `ADVAPI32!CopySid` at `0x1401c8128`

## string_xrefs

- `0x1401c80be`: `Sid::Set`
- `0x1401c80ca`: `base\fs\remotefs\frs\src\util\securityutil.cpp`

## pseudocode

```c
struct FrsStatus *__fastcall Sid::Set(Sid *this, struct _SID *a2)
{
  DWORD LengthSid; // eax
  DWORD v6; // ebx
  __int64 LastError; // rdx
  int v8; // [rsp+30h] [rbp-28h]
  DWORD CurrentThreadId; // [rsp+38h] [rbp-20h]

  Sid::Clear(this);
  if ( !IsValidSid(a2) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = 101;
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                 87,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                 "Sid::Set",
                                 v8,
                                 CurrentThreadId,
                                 0);
  }
  LengthSid = GetLengthSid(a2);
  if ( LengthSid > 0x44 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = 106;
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                 87,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                 "Sid::Set",
                                 v8,
                                 CurrentThreadId,
                                 0);
  }
  *((_DWORD *)this + 19) = 1;
  if ( CopySid(LengthSid, (char *)this + 8, a2) )
  {
    *((_DWORD *)this + 20) = 8;
    return 0;
  }
  else
  {
    *((_DWORD *)this + 19) = 0;
    v6 = GetCurrentThreadId();
    LastError = GetLastError();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                 LastError,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                 "Sid::Set",
                                 112,
                                 v6,
                                 0);
  }
}

```

## disassembly

```asm
0x1401c8070  mov     [rsp+arg_0], rbx
0x1401c8075  push    rdi
0x1401c8076  sub     rsp, 50h
0x1401c807a  mov     rdi, rdx
0x1401c807d  mov     rbx, rcx
0x1401c8080  call    ?Clear@Sid@@IEAAXXZ; Sid::Clear(void)
0x1401c8085  mov     rcx, rdi; pSid
0x1401c8088  call    cs:__imp_IsValidSid
0x1401c808f  nop     dword ptr [rax+rax+00h]
0x1401c8094  test    eax, eax
0x1401c8096  jnz     short loc_1401C80E4
0x1401c8098  call    cs:__imp_GetCurrentThreadId
0x1401c809f  nop     dword ptr [rax+rax+00h]
0x1401c80a4  and     [rsp+58h+var_18], 0
0x1401c80aa  mov     [rsp+58h+var_20], eax
0x1401c80ae  mov     [rsp+58h+var_28], 65h ; 'e'
0x1401c80b6  mov     edx, 57h ; 'W'
0x1401c80bb  xor     r8d, r8d
0x1401c80be  lea     rcx, aSidSet; "Sid::Set"
0x1401c80c5  mov     [rsp+58h+var_30], rcx
0x1401c80ca  lea     rcx, aBaseFsRemotefs_41; "base\\fs\\remotefs\\frs\\src\\util\\sec"...
0x1401c80d1  mov     [rsp+58h+var_38], rcx
0x1401c80d6  lea     r9d, [r8+1]
0x1401c80da  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c80df  jmp     loc_1401C8177
0x1401c80e4  mov     rcx, rdi; pSid
0x1401c80e7  call    cs:__imp_GetLengthSid
0x1401c80ee  nop     dword ptr [rax+rax+00h]
0x1401c80f3  cmp     eax, 44h ; 'D'
0x1401c80f6  jbe     short loc_1401C8118
0x1401c80f8  call    cs:__imp_GetCurrentThreadId
0x1401c80ff  nop     dword ptr [rax+rax+00h]
0x1401c8104  and     [rsp+58h+var_18], 0
0x1401c810a  mov     [rsp+58h+var_20], eax
0x1401c810e  mov     [rsp+58h+var_28], 6Ah ; 'j'
0x1401c8116  jmp     short loc_1401C80B6
0x1401c8118  lea     rdx, [rbx+8]; pDestinationSid
0x1401c811c  mov     dword ptr [rbx+4Ch], 1
0x1401c8123  mov     r8, rdi; pSourceSid
0x1401c8126  mov     ecx, eax; nDestinationSidLength
0x1401c8128  call    cs:__imp_CopySid
0x1401c812f  nop     dword ptr [rax+rax+00h]
0x1401c8134  test    eax, eax
0x1401c8136  jnz     short loc_1401C816E
0x1401c8138  and     [rbx+4Ch], eax
0x1401c813b  call    cs:__imp_GetCurrentThreadId
0x1401c8142  nop     dword ptr [rax+rax+00h]
0x1401c8147  mov     ebx, eax
0x1401c8149  call    cs:__imp_GetLastError
0x1401c8150  nop     dword ptr [rax+rax+00h]
0x1401c8155  and     [rsp+58h+var_18], 0
0x1401c815b  mov     edx, eax
0x1401c815d  mov     [rsp+58h+var_20], ebx
0x1401c8161  mov     [rsp+58h+var_28], 70h ; 'p'
0x1401c8169  jmp     loc_1401C80BB
0x1401c816e  mov     dword ptr [rbx+50h], 8
0x1401c8175  xor     eax, eax
0x1401c8177  mov     rbx, [rsp+58h+arg_0]
0x1401c817c  add     rsp, 50h
0x1401c8180  pop     rdi
0x1401c8181  retn
```
