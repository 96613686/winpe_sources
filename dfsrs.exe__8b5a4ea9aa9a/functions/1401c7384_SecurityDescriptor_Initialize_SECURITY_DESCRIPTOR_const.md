# SecurityDescriptor::Initialize(_SECURITY_DESCRIPTOR const *)

- ea: `0x1401c7384`
- end: `0x1401c74b8`
- name: `?Initialize@SecurityDescriptor@@QEAAPEAVFrsStatus@@PEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `308`
- prototype: `struct FrsStatus *(SecurityDescriptor *__hidden this, const struct _SECURITY_DESCRIPTOR *)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400bac90`
- `0x1400be73c`
- `0x1401c4ffc`
- `0x1401c733c`
- `0x1401e8cbc`
- `0x1401ee4d4`

## callees

- `0x14000bbc5`
- `0x1401af7b0`
- `0x1401af7c0`
- `0x1401b9494`
- `0x1401c7384`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401c73ea`
- `KERNEL32!GetLastError` at `0x1401c745b`
- `KERNEL32!GetLastError` at `0x1401c73ea`
- `KERNEL32!GetLastError` at `0x1401c745b`
- `KERNEL32!GetCurrentThreadId` at `0x1401c73dc`
- `KERNEL32!GetCurrentThreadId` at `0x1401c744d`
- `KERNEL32!GetCurrentThreadId` at `0x1401c73dc`
- `KERNEL32!GetCurrentThreadId` at `0x1401c744d`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1401c743d`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1401c743d`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x1401c73cc`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x1401c73cc`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1401c739c`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1401c739c`

## string_xrefs

- `0x1401c748d`: `base\fs\remotefs\frs\src\util\securityutil.cpp`
- `0x1401c7478`: `SecurityDescriptor::Initialize`

## pseudocode

```c
struct FrsStatus *__fastcall SecurityDescriptor::Initialize(SecurityDescriptor *this, struct _SECURITY_DESCRIPTOR *a2)
{
  DWORD v4; // ebx
  DWORD v5; // eax
  __int64 v6; // rax
  struct FrsStatus *result; // rax
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  struct FrsStatus *v10; // rbx
  WORD pControl; // [rsp+70h] [rbp+8h] BYREF
  size_t Size; // [rsp+78h] [rbp+10h] BYREF
  DWORD dwRevision; // [rsp+80h] [rbp+18h] BYREF

  dwRevision = 0;
  LODWORD(Size) = GetSecurityDescriptorLength(a2);
  *((_QWORD *)this + 1) = operator_new((unsigned int)Size);
  pControl = 0;
  if ( GetSecurityDescriptorControl(a2, &pControl, &dwRevision) )
  {
    if ( (pControl & 0x8000u) == 0 )
    {
      if ( !MakeSelfRelativeSD(a2, *((PSECURITY_DESCRIPTOR *)this + 1), (LPDWORD)&Size) )
      {
        CurrentThreadId = GetCurrentThreadId();
        LastError = GetLastError();
        v6 = FrsStatusList::PushNewError(
               "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
               LastError,
               0,
               1,
               "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
               "SecurityDescriptor::Initialize",
               2053,
               CurrentThreadId,
               0);
        goto LABEL_8;
      }
    }
    else
    {
      memcpy_0(*((void **)this + 1), a2, (unsigned int)Size);
    }
    return 0;
  }
  v4 = GetCurrentThreadId();
  v5 = GetLastError();
  v6 = FrsStatusList::PushNewError(
         "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
         v5,
         0,
         1,
         "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
         "SecurityDescriptor::Initialize",
         2043,
         v4,
         0);
LABEL_8:
  v10 = (struct FrsStatus *)v6;
  operator delete[](*((void **)this + 1));
  result = v10;
  *((_QWORD *)this + 1) = 0;
  return result;
}

```

## disassembly

```asm
0x1401c7384  mov     rax, rsp
0x1401c7387  push    rbx
0x1401c7388  push    rsi
0x1401c7389  push    rdi
0x1401c738a  sub     rsp, 50h
0x1401c738e  mov     rdi, rcx
0x1401c7391  xor     esi, esi
0x1401c7393  mov     rcx, rdx; pSecurityDescriptor
0x1401c7396  mov     [rax+18h], esi
0x1401c7399  mov     rbx, rdx
0x1401c739c  call    cs:__imp_GetSecurityDescriptorLength
0x1401c73a3  nop     dword ptr [rax+rax+00h]
0x1401c73a8  mov     ecx, eax; unsigned __int64
0x1401c73aa  mov     dword ptr [rsp+68h+Size], ecx
0x1401c73ae  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401c73b3  lea     r8, [rsp+68h+dwRevision]; lpdwRevision
0x1401c73bb  mov     [rdi+8], rax
0x1401c73bf  lea     rdx, [rsp+68h+pControl]; pControl
0x1401c73c4  mov     [rsp+68h+pControl], si
0x1401c73c9  mov     rcx, rbx; pSecurityDescriptor
0x1401c73cc  call    cs:__imp_GetSecurityDescriptorControl
0x1401c73d3  nop     dword ptr [rax+rax+00h]
0x1401c73d8  test    eax, eax
0x1401c73da  jnz     short loc_1401C7409
0x1401c73dc  call    cs:__imp_GetCurrentThreadId
0x1401c73e3  nop     dword ptr [rax+rax+00h]
0x1401c73e8  mov     ebx, eax
0x1401c73ea  call    cs:__imp_GetLastError
0x1401c73f1  nop     dword ptr [rax+rax+00h]
0x1401c73f6  mov     [rsp+68h+var_28], rsi
0x1401c73fb  mov     [rsp+68h+var_30], ebx
0x1401c73ff  mov     [rsp+68h+var_38], 7FBh
0x1401c7407  jmp     short loc_1401C7478
0x1401c7409  mov     eax, 8000h
0x1401c740e  test    [rsp+68h+pControl], ax
0x1401c7413  jz      short loc_1401C7431
0x1401c7415  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x1401c741a  mov     rdx, rbx; Src
0x1401c741d  mov     rcx, [rdi+8]; void *
0x1401c7421  call    memcpy_0
0x1401c7426  xor     eax, eax
0x1401c7428  add     rsp, 50h
0x1401c742c  pop     rdi
0x1401c742d  pop     rsi
0x1401c742e  pop     rbx
0x1401c742f  retn
0x1401c7431  mov     rdx, [rdi+8]; pSelfRelativeSecurityDescriptor
0x1401c7435  lea     r8, [rsp+68h+Size]; lpdwBufferLength
0x1401c743a  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x1401c743d  call    cs:__imp_MakeSelfRelativeSD
0x1401c7444  nop     dword ptr [rax+rax+00h]
0x1401c7449  test    eax, eax
0x1401c744b  jnz     short loc_1401C7426
0x1401c744d  call    cs:__imp_GetCurrentThreadId
0x1401c7454  nop     dword ptr [rax+rax+00h]
0x1401c7459  mov     ebx, eax
0x1401c745b  call    cs:__imp_GetLastError
0x1401c7462  nop     dword ptr [rax+rax+00h]
0x1401c7467  mov     [rsp+68h+var_28], rsi
0x1401c746c  mov     [rsp+68h+var_30], ebx
0x1401c7470  mov     [rsp+68h+var_38], 805h
0x1401c7478  lea     rcx, aSecuritydescri_1; "SecurityDescriptor::Initialize"
0x1401c747f  mov     r9d, 1
0x1401c7485  mov     [rsp+68h+var_40], rcx
0x1401c748a  xor     r8d, r8d
0x1401c748d  lea     rcx, aBaseFsRemotefs_41; "base\\fs\\remotefs\\frs\\src\\util\\sec"...
0x1401c7494  mov     edx, eax
0x1401c7496  mov     [rsp+68h+var_48], rcx
0x1401c749b  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c74a0  mov     rcx, [rdi+8]; Block
0x1401c74a4  mov     rbx, rax
0x1401c74a7  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401c74ac  mov     rax, rbx
0x1401c74af  mov     [rdi+8], rsi
0x1401c74b3  jmp     loc_1401C7428
```
