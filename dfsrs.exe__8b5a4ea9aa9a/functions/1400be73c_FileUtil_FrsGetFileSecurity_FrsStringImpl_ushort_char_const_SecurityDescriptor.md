# FileUtil::FrsGetFileSecurity(FrsStringImpl<ushort,char> const &,SecurityDescriptor &)

- ea: `0x1400be73c`
- end: `0x1400be901`
- name: `?FrsGetFileSecurity@FileUtil@@SAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@AEAVSecurityDescriptor@@@Z`
- size: `453`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401f7180`
- `0x1401f7400`

## callees

- `0x14002c548`
- `0x1400be73c`
- `0x1401af7b0`
- `0x1401b9494`
- `0x1401c7384`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400be78c`
- `KERNEL32!GetLastError` at `0x1400be84d`
- `KERNEL32!GetLastError` at `0x1400be78c`
- `KERNEL32!GetLastError` at `0x1400be84d`
- `KERNEL32!GetCurrentThreadId` at `0x1400be7cd`
- `KERNEL32!GetCurrentThreadId` at `0x1400be83f`
- `KERNEL32!GetCurrentThreadId` at `0x1400be89f`
- `KERNEL32!GetCurrentThreadId` at `0x1400be7cd`
- `KERNEL32!GetCurrentThreadId` at `0x1400be83f`
- `KERNEL32!GetCurrentThreadId` at `0x1400be89f`
- `ADVAPI32!GetFileSecurityW` at `0x1400be780`
- `ADVAPI32!GetFileSecurityW` at `0x1400be82f`
- `ADVAPI32!GetFileSecurityW` at `0x1400be780`
- `ADVAPI32!GetFileSecurityW` at `0x1400be82f`

## string_xrefs

- `0x1400be79a`: `FileUtil::FrsGetFileSecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FileUtil::FrsGetFileSecurity(__int64 a1, SecurityDescriptor *a2)
{
  __int64 v4; // rsi
  DWORD v5; // ebp
  struct _SECURITY_DESCRIPTOR *v6; // rbx
  DWORD LastError; // edi
  DWORD CurrentThreadId; // eax
  __int64 v9; // rcx
  struct FrsStatus *v10; // rdi
  DWORD v11; // edi
  DWORD v12; // eax
  __int64 v13; // rcx
  DWORD v14; // eax
  __int64 v15; // rcx
  DWORD nLength; // [rsp+90h] [rbp+8h] BYREF
  struct _SECURITY_DESCRIPTOR *v18; // [rsp+A0h] [rbp+18h] BYREF

  v4 = 0;
  v5 = 0;
  nLength = 0;
  v6 = 0;
  v18 = 0;
  GetFileSecurityW((LPCWSTR)(*(_QWORD *)a1 + 18LL), 0x1000Fu, 0, 0, &nLength);
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v6 = (struct _SECURITY_DESCRIPTOR *)operator_new(nLength);
    v18 = v6;
    v5 = nLength;
  }
  else
  {
    CurrentThreadId = GetCurrentThreadId();
    v10 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v9,
                                LastError,
                                0,
                                1,
                                "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
                                "FileUtil::FrsGetFileSecurity",
                                2274,
                                CurrentThreadId,
                                0);
    if ( v10 )
    {
LABEL_7:
      v14 = GetCurrentThreadId();
      v4 = FrsStatusList::PushNewError(
             v15,
             *((unsigned int *)v10 + 1),
             *((unsigned int *)v10 + 2),
             *(unsigned int *)v10,
             "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
             "FileUtil::FrsGetFileSecurity",
             2298,
             v14,
             v10);
      goto LABEL_8;
    }
  }
  if ( !GetFileSecurityW((LPCWSTR)(*(_QWORD *)a1 + 18LL), 0x1000Fu, v6, v5, &nLength) )
  {
    v11 = GetCurrentThreadId();
    v12 = GetLastError();
    v10 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                v13,
                                v12,
                                0,
                                1,
                                "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
                                "FileUtil::FrsGetFileSecurity",
                                2289,
                                v11,
                                0);
    if ( v10 )
      goto LABEL_7;
  }
  v10 = SecurityDescriptor::Initialize(a2, v6);
  if ( v10 )
    goto LABEL_7;
LABEL_8:
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v18);
  return v4;
}

```

## disassembly

```asm
0x1400be73c  mov     rax, rsp
0x1400be73f  mov     [rax+10h], rbx
0x1400be743  push    rbp
0x1400be744  push    rsi
0x1400be745  push    rdi
0x1400be746  push    r12
0x1400be748  push    r13
0x1400be74a  push    r14
0x1400be74c  push    r15
0x1400be74e  sub     rsp, 50h
0x1400be752  mov     r14, rdx
0x1400be755  mov     r15, rcx
0x1400be758  xor     esi, esi
0x1400be75a  mov     ebp, esi
0x1400be75c  mov     [rax+8], esi
0x1400be75f  mov     ebx, esi
0x1400be761  mov     [rax+18h], rbx
0x1400be765  mov     rcx, [rcx]
0x1400be768  add     rcx, 12h; lpFileName
0x1400be76c  lea     rax, [rax+8]
0x1400be770  mov     [rsp+88h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1400be775  xor     r9d, r9d; nLength
0x1400be778  xor     r8d, r8d; pSecurityDescriptor
0x1400be77b  mov     edx, 1000Fh; RequestedInformation
0x1400be780  call    cs:__imp_GetFileSecurityW
0x1400be787  nop     dword ptr [rax+rax+00h]
0x1400be78c  call    cs:__imp_GetLastError
0x1400be793  nop     dword ptr [rax+rax+00h]
0x1400be798  mov     edi, eax
0x1400be79a  lea     r12, aFileutilFrsget; "FileUtil::FrsGetFileSecurity"
0x1400be7a1  lea     r13, aBaseFsRemotefs_24; "base\\fs\\remotefs\\frs\\src\\fs\\fileu"...
0x1400be7a8  cmp     eax, 7Ah ; 'z'
0x1400be7ab  jnz     short loc_1400BE7CD
0x1400be7ad  mov     ecx, [rsp+88h+nLength]; unsigned __int64
0x1400be7b4  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1400be7b9  mov     rbx, rax
0x1400be7bc  mov     [rsp+88h+arg_10], rax
0x1400be7c4  mov     ebp, [rsp+88h+nLength]
0x1400be7cb  jmp     short loc_1400BE810
0x1400be7cd  call    cs:__imp_GetCurrentThreadId
0x1400be7d4  nop     dword ptr [rax+rax+00h]
0x1400be7d9  mov     [rsp+88h+var_48], rsi
0x1400be7de  mov     [rsp+88h+var_50], eax
0x1400be7e2  mov     [rsp+88h+var_58], 8E2h
0x1400be7ea  mov     [rsp+88h+var_60], r12
0x1400be7ef  mov     [rsp+88h+lpnLengthNeeded], r13
0x1400be7f4  mov     r9d, 1
0x1400be7fa  xor     r8d, r8d
0x1400be7fd  mov     edx, edi
0x1400be7ff  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400be804  mov     rdi, rax
0x1400be807  test    rax, rax
0x1400be80a  jnz     loc_1400BE89F
0x1400be810  mov     rcx, [r15]
0x1400be813  add     rcx, 12h; lpFileName
0x1400be817  lea     rax, [rsp+88h+nLength]
0x1400be81f  mov     [rsp+88h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1400be824  mov     r9d, ebp; nLength
0x1400be827  mov     r8, rbx; pSecurityDescriptor
0x1400be82a  mov     edx, 1000Fh; RequestedInformation
0x1400be82f  call    cs:__imp_GetFileSecurityW
0x1400be836  nop     dword ptr [rax+rax+00h]
0x1400be83b  test    eax, eax
0x1400be83d  jnz     short loc_1400BE88C
0x1400be83f  call    cs:__imp_GetCurrentThreadId
0x1400be846  nop     dword ptr [rax+rax+00h]
0x1400be84b  mov     edi, eax
0x1400be84d  call    cs:__imp_GetLastError
0x1400be854  nop     dword ptr [rax+rax+00h]
0x1400be859  mov     [rsp+88h+var_48], rsi
0x1400be85e  mov     [rsp+88h+var_50], edi
0x1400be862  mov     [rsp+88h+var_58], 8F1h
0x1400be86a  mov     [rsp+88h+var_60], r12
0x1400be86f  mov     [rsp+88h+lpnLengthNeeded], r13
0x1400be874  mov     r9d, 1
0x1400be87a  xor     r8d, r8d
0x1400be87d  mov     edx, eax
0x1400be87f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400be884  mov     rdi, rax
0x1400be887  test    rax, rax
0x1400be88a  jnz     short loc_1400BE89F
0x1400be88c  mov     rdx, rbx; struct _SECURITY_DESCRIPTOR *
0x1400be88f  mov     rcx, r14; this
0x1400be892  call    ?Initialize@SecurityDescriptor@@QEAAPEAVFrsStatus@@PEBU_SECURITY_DESCRIPTOR@@@Z; SecurityDescriptor::Initialize(_SECURITY_DESCRIPTOR const *)
0x1400be897  mov     rdi, rax
0x1400be89a  test    rax, rax
0x1400be89d  jz      short loc_1400BE8D8
0x1400be89f  call    cs:__imp_GetCurrentThreadId
0x1400be8a6  nop     dword ptr [rax+rax+00h]
0x1400be8ab  mov     [rsp+88h+var_48], rdi
0x1400be8b0  mov     [rsp+88h+var_50], eax
0x1400be8b4  mov     [rsp+88h+var_58], 8FAh
0x1400be8bc  mov     [rsp+88h+var_60], r12
0x1400be8c1  mov     [rsp+88h+lpnLengthNeeded], r13
0x1400be8c6  mov     r9d, [rdi]
0x1400be8c9  mov     r8d, [rdi+8]
0x1400be8cd  mov     edx, [rdi+4]
0x1400be8d0  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400be8d5  mov     rsi, rax
0x1400be8d8  lea     rcx, [rsp+88h+arg_10]
0x1400be8e0  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1400be8e5  mov     rax, rsi
0x1400be8e8  mov     rbx, [rsp+88h+arg_8]
0x1400be8f0  add     rsp, 50h
0x1400be8f4  pop     r15
0x1400be8f6  pop     r14
0x1400be8f8  pop     r13
0x1400be8fa  pop     r12
0x1400be8fc  pop     rdi
0x1400be8fd  pop     rsi
0x1400be8fe  pop     rbp
0x1400be8ff  retn
```
