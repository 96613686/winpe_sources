# PsmpCreateJobObject

- ea: `0x18000d7e8`
- end: `0x18000d92e`
- name: `PsmpCreateJobObject`
- size: `326`
- prototype: `__int64 __fastcall(__int64 *, void **, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000d16c`
- `0x18000d378`

## callees

- `0x18000d14c`
- `0x18000d7e8`
- `0x18001b7e0`

## import_xrefs

- `ntdll!NtClose` at `0x18000d8ee`
- `ntdll!NtClose` at `0x18000d8ee`
- `ntdll!NtCreateJobObject` at `0x18000d849`
- `ntdll!NtCreateJobObject` at `0x18000d849`
- `ntdll!TpAllocWork` at `0x18000d8a3`
- `ntdll!TpAllocWork` at `0x18000d8a3`
- `ntdll!NtSetInformationJobObject` at `0x18000d881`
- `ntdll!NtSetInformationJobObject` at `0x18000d881`

## pseudocode

```c
__int64 __fastcall PsmpCreateJobObject(__int64 *a1, void **a2, unsigned int a3, unsigned int a4)
{
  NTSTATUS v8; // edi
  void *v9; // rcx
  int v11; // ecx
  __int64 v12; // rax
  void *JobHandle; // [rsp+20h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+28h] [rbp-50h] BYREF
  __int128 JobInformation; // [rsp+58h] [rbp-20h] BYREF

  JobHandle = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  JobInformation = 0;
  v8 = NtCreateJobObject(&JobHandle, 0x1F003Fu, &ObjectAttributes);
  if ( v8 < 0
    || (a3 || a4)
    && (LODWORD(JobInformation) = 2,
        *((_QWORD *)&JobInformation + 1) = __PAIR64__(a4, a3),
        v8 = NtSetInformationJobObject(JobHandle, (JOBOBJECTINFOCLASS)18, &JobInformation, 0x10u),
        v8 < 0)
    || a1 && (v8 = TpAllocWork(a1 + 3, PsmpTerminateJobWorker, a1, 0), v8 < 0) )
  {
    v9 = JobHandle;
  }
  else
  {
    v9 = 0;
    *a2 = JobHandle;
    v8 = 0;
    JobHandle = 0;
  }
  if ( v9 )
  {
    NtClose(v9);
    if ( a1 )
    {
      PsmpHostContextCleanup(a1);
      v11 = *((_DWORD *)a1 + 4);
      v12 = *a1;
      a1[1] = 0;
      *(__int64 *)((char *)a1 + 20) = 0;
      *(__int64 *)((char *)a1 + 28) = 0;
      *((_DWORD *)a1 + 9) = 0;
      *a1 = v12;
      *((_DWORD *)a1 + 4) = v11;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d7e8  push    rbp
0x18000d7ea  push    rbx
0x18000d7eb  push    rsi
0x18000d7ec  push    rdi
0x18000d7ed  push    r14
0x18000d7ef  push    r15
0x18000d7f1  mov     rbp, rsp
0x18000d7f4  sub     rsp, 78h
0x18000d7f8  mov     rax, cs:__security_cookie
0x18000d7ff  xor     rax, rsp
0x18000d802  mov     [rbp+var_10], rax
0x18000d806  xor     eax, eax
0x18000d808  mov     [rbp+JobHandle], 0
0x18000d810  xorps   xmm0, xmm0
0x18000d813  mov     qword ptr [rbp+ObjectAttributes.Attributes], rax
0x18000d817  mov     esi, r8d
0x18000d81a  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x18000d81e  mov     r15, rdx
0x18000d821  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000d825  mov     rbx, rcx
0x18000d828  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000d830  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000d834  mov     edx, 1F003Fh; DesiredAccess
0x18000d839  lea     rcx, [rbp+JobHandle]; JobHandle
0x18000d83d  mov     r14d, r9d
0x18000d840  movups  [rbp+JobInformation], xmm0
0x18000d844  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d849  call    cs:__imp_NtCreateJobObject
0x18000d84f  mov     edi, eax
0x18000d851  test    eax, eax
0x18000d853  js      loc_18000D8DE
0x18000d859  test    esi, esi
0x18000d85b  jz      loc_18000D8E4
0x18000d861  mov     rcx, [rbp+JobHandle]; JobHandle
0x18000d865  lea     r8, [rbp+JobInformation]; JobInformation
0x18000d869  mov     r9d, 10h; JobInformationLength
0x18000d86f  mov     dword ptr [rbp+JobInformation], 2
0x18000d876  mov     dword ptr [rbp+JobInformation+8], esi
0x18000d879  mov     dword ptr [rbp+JobInformation+0Ch], r14d
0x18000d87d  lea     edx, [r9+2]; JobInformationClass
0x18000d881  call    cs:__imp_NtSetInformationJobObject
0x18000d887  mov     edi, eax
0x18000d889  test    eax, eax
0x18000d88b  js      short loc_18000D8DE
0x18000d88d  test    rbx, rbx
0x18000d890  jz      short loc_18000D8AF
0x18000d892  lea     rcx, [rbx+18h]
0x18000d896  xor     r9d, r9d
0x18000d899  mov     r8, rbx
0x18000d89c  lea     rdx, PsmpTerminateJobWorker
0x18000d8a3  call    cs:__imp_TpAllocWork
0x18000d8a9  mov     edi, eax
0x18000d8ab  test    eax, eax
0x18000d8ad  js      short loc_18000D8DE
0x18000d8af  mov     rax, [rbp+JobHandle]
0x18000d8b3  xor     ecx, ecx; Handle
0x18000d8b5  mov     [r15], rax
0x18000d8b8  xor     edi, edi
0x18000d8ba  mov     [rbp+JobHandle], rcx
0x18000d8be  test    rcx, rcx
0x18000d8c1  jnz     short loc_18000D8EE
0x18000d8c3  mov     eax, edi
0x18000d8c5  mov     rcx, [rbp+var_10]
0x18000d8c9  xor     rcx, rsp; StackCookie
0x18000d8cc  call    __security_check_cookie
0x18000d8d1  add     rsp, 78h
0x18000d8d5  pop     r15
0x18000d8d7  pop     r14
0x18000d8d9  pop     rdi
0x18000d8da  pop     rsi
0x18000d8db  pop     rbx
0x18000d8dc  pop     rbp
0x18000d8dd  retn
0x18000d8de  mov     rcx, [rbp+JobHandle]
0x18000d8e2  jmp     short loc_18000D8BE
0x18000d8e4  test    r14d, r14d
0x18000d8e7  jz      short loc_18000D88D
0x18000d8e9  jmp     loc_18000D861
0x18000d8ee  call    cs:__imp_NtClose
0x18000d8f4  test    rbx, rbx
0x18000d8f7  jz      short loc_18000D8C3
0x18000d8f9  mov     rcx, rbx
0x18000d8fc  call    PsmpHostContextCleanup
0x18000d901  mov     ecx, [rbx+10h]
0x18000d904  mov     rax, [rbx]
0x18000d907  mov     qword ptr [rbx+8], 0
0x18000d90f  mov     qword ptr [rbx+14h], 0
0x18000d917  mov     qword ptr [rbx+1Ch], 0
0x18000d91f  mov     dword ptr [rbx+24h], 0
0x18000d926  mov     [rbx], rax
0x18000d929  mov     [rbx+10h], ecx
0x18000d92c  jmp     short loc_18000D8C3
```
