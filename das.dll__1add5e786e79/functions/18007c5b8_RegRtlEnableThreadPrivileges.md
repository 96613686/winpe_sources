# _RegRtlEnableThreadPrivileges

- ea: `0x18007c5b8`
- end: `0x18007c8c0`
- name: `_RegRtlEnableThreadPrivileges`
- size: `776`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001304`
- `0x1800026b0`
- `0x180003f50`
- `0x18007c930`

## callees

- `0x18003bc80`
- `0x18007c5b8`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18007c814`
- `ntdll!NtSetInformationThread` at `0x18007c814`
- `ntdll!NtAdjustPrivilegesToken` at `0x18007c7f5`
- `ntdll!NtAdjustPrivilegesToken` at `0x18007c7f5`
- `ntdll!NtDuplicateToken` at `0x18007c7c7`
- `ntdll!NtDuplicateToken` at `0x18007c7c7`
- `ntdll!NtOpenProcessToken` at `0x18007c6e4`
- `ntdll!NtOpenProcessToken` at `0x18007c6e4`
- `ntdll!NtOpenThreadToken` at `0x18007c6b5`
- `ntdll!NtOpenThreadToken` at `0x18007c6b5`
- `ntdll!NtClose` at `0x18007c827`
- `ntdll!NtClose` at `0x18007c846`
- `ntdll!NtClose` at `0x18007c855`
- `ntdll!NtClose` at `0x18007c827`
- `ntdll!NtClose` at `0x18007c846`
- `ntdll!NtClose` at `0x18007c855`
- `ntdll!NtQuerySecurityObject` at `0x18007c70f`
- `ntdll!NtQuerySecurityObject` at `0x18007c75f`
- `ntdll!NtQuerySecurityObject` at `0x18007c70f`
- `ntdll!NtQuerySecurityObject` at `0x18007c75f`
- `ntdll!RtlFreeHeap` at `0x18007c872`
- `ntdll!RtlFreeHeap` at `0x18007c88f`
- `ntdll!RtlFreeHeap` at `0x18007c872`
- `ntdll!RtlFreeHeap` at `0x18007c88f`
- `ntdll!RtlAllocateHeap` at `0x18007c648`
- `ntdll!RtlAllocateHeap` at `0x18007c736`
- `ntdll!RtlAllocateHeap` at `0x18007c648`
- `ntdll!RtlAllocateHeap` at `0x18007c736`

## pseudocode

```c
__int64 __fastcall RegRtlEnableThreadPrivileges(__int64 a1, DWORD a2)
{
  __int64 v2; // r14
  PVOID v5; // rsi
  ULONG v6; // eax
  struct _TOKEN_PRIVILEGES *Heap; // rax
  struct _TOKEN_PRIVILEGES *v8; // rdi
  struct _TOKEN_PRIVILEGES *v9; // r15
  DWORD v10; // r8d
  __int64 v11; // rdx
  __int64 v12; // rcx
  NTSTATUS v13; // eax
  void *v14; // rcx
  void *TokenHandle; // [rsp+30h] [rbp-59h] BYREF
  ULONG Length; // [rsp+38h] [rbp-51h] BYREF
  HANDLE ThreadInformation; // [rsp+40h] [rbp-49h] BYREF
  LUID v19; // [rsp+48h] [rbp-41h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-39h] BYREF
  __int64 v21; // [rsp+80h] [rbp-9h] BYREF
  int v22; // [rsp+88h] [rbp-1h]
  char v23; // [rsp+90h] [rbp+7h] BYREF

  v2 = -1;
  TokenHandle = (void *)-1LL;
  ThreadInformation = (HANDLE)-1LL;
  v21 = 0;
  v22 = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !a1 || !a2 )
    return v2;
  v5 = 0;
  v6 = 12 * a2 + 4;
  Length = v6;
  if ( v6 <= 0x28 )
  {
    v8 = 0;
    Length = 40;
    v9 = (struct _TOKEN_PRIVILEGES *)&v23;
  }
  else
  {
    Heap = (struct _TOKEN_PRIVILEGES *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v6);
    v8 = Heap;
    if ( !Heap )
      goto LABEL_26;
    v9 = Heap;
  }
  v10 = 0;
  v9->PrivilegeCount = a2;
  if ( a2 )
  {
    v11 = 0;
    do
    {
      v12 = v11;
      v19 = (LUID)*(unsigned int *)(a1 + 4 * v11);
      ++v10;
      ++v11;
      v9->Privileges[v12].Luid = v19;
      v9->Privileges[v12].Attributes = 2;
    }
    while ( v10 < a2 );
  }
  v13 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x20002u, 0, &TokenHandle);
  if ( v13 < 0 )
  {
    if ( v13 != -1073741700 || NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x20002u, &TokenHandle) < 0 )
    {
LABEL_25:
      TokenHandle = (void *)-1LL;
      goto LABEL_26;
    }
    v14 = TokenHandle;
    v2 = 0;
  }
  else
  {
    v14 = TokenHandle;
    v2 = (__int64)TokenHandle;
  }
  if ( NtQuerySecurityObject(v14, 4u, 0, 0, &Length) != -1073741789
    || (v5 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Length)) == 0
    || NtQuerySecurityObject(TokenHandle, 4u, v5, Length, &Length) < 0 )
  {
LABEL_26:
    if ( ThreadInformation != (HANDLE)-1LL )
      NtClose(ThreadInformation);
    goto LABEL_28;
  }
  v21 = 0x20000000CLL;
  ObjectAttributes.SecurityQualityOfService = &v21;
  LOWORD(v22) = 1;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  ObjectAttributes.SecurityDescriptor = v5;
  if ( NtDuplicateToken(TokenHandle, 0x2Cu, &ObjectAttributes, 0, TokenImpersonation, &ThreadInformation) >= 0 )
  {
    if ( NtAdjustPrivilegesToken(ThreadInformation, 0, v9, 0, 0, 0) >= 0
      && NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u) >= 0 )
    {
      if ( TokenHandle != (void *)v2 )
        NtClose(TokenHandle);
      goto LABEL_25;
    }
    goto LABEL_26;
  }
  ThreadInformation = (HANDLE)-1LL;
LABEL_28:
  if ( TokenHandle != (void *)-1LL )
    NtClose(TokenHandle);
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  return v2;
}

```

## disassembly

```asm
0x18007c5b8  mov     [rsp-8+arg_0], rbx
0x18007c5bd  mov     [rsp-8+arg_10], rsi
0x18007c5c2  push    rbp
0x18007c5c3  push    rdi
0x18007c5c4  push    r12
0x18007c5c6  push    r14
0x18007c5c8  push    r15
0x18007c5ca  lea     rbp, [rsp-37h]
0x18007c5cf  sub     rsp, 0C0h
0x18007c5d6  mov     rax, cs:__security_cookie
0x18007c5dd  xor     rax, rsp
0x18007c5e0  mov     [rbp+57h+var_28], rax
0x18007c5e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007c5e8  xorps   xmm0, xmm0
0x18007c5eb  mov     r14, rax
0x18007c5ee  mov     [rbp+57h+TokenHandle], rax
0x18007c5f2  mov     [rbp+57h+ThreadInformation], rax
0x18007c5f6  mov     ebx, edx
0x18007c5f8  xor     eax, eax
0x18007c5fa  mov     r12, rcx
0x18007c5fd  mov     [rbp+57h+var_60], rax
0x18007c601  mov     [rbp+57h+var_58], eax
0x18007c604  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18007c608  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18007c60c  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18007c610  test    rcx, rcx
0x18007c613  jz      loc_18007C895
0x18007c619  test    edx, edx
0x18007c61b  jz      loc_18007C895
0x18007c621  lea     eax, [rdx+rdx*2]
0x18007c624  xor     esi, esi
0x18007c626  lea     eax, ds:4[rax*4]
0x18007c62d  mov     [rbp+57h+Length], eax
0x18007c630  cmp     eax, 28h ; '('
0x18007c633  jbe     short loc_18007C65F
0x18007c635  mov     rcx, gs:60h
0x18007c63e  lea     edx, [rsi+8]; Flags
0x18007c641  mov     r8d, eax; Size
0x18007c644  mov     rcx, [rcx+30h]; HeapHandle
0x18007c648  call    cs:__imp_RtlAllocateHeap
0x18007c64e  mov     rdi, rax
0x18007c651  test    rax, rax
0x18007c654  jz      loc_18007C82F
0x18007c65a  mov     r15, rax
0x18007c65d  jmp     short loc_18007C66C
0x18007c65f  xor     edi, edi
0x18007c661  mov     [rbp+57h+Length], 28h ; '('
0x18007c668  lea     r15, [rbp+57h+var_50]
0x18007c66c  xor     r8d, r8d
0x18007c66f  mov     [r15], ebx
0x18007c672  test    ebx, ebx
0x18007c674  jz      short loc_18007C6A3
0x18007c676  xor     edx, edx
0x18007c678  mov     eax, [r12+rdx*4]
0x18007c67c  lea     rcx, [rdx+rdx*2]
0x18007c680  mov     dword ptr [rbp+57h+var_98], eax
0x18007c683  inc     r8d
0x18007c686  mov     dword ptr [rbp+57h+var_98+4], esi
0x18007c689  inc     rdx
0x18007c68c  mov     rax, [rbp+57h+var_98]
0x18007c690  mov     [r15+rcx*4+4], rax
0x18007c695  mov     dword ptr [r15+rcx*4+0Ch], 2
0x18007c69e  cmp     r8d, ebx
0x18007c6a1  jb      short loc_18007C678
0x18007c6a3  xor     r8d, r8d; OpenAsSelf
0x18007c6a6  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18007c6aa  mov     ebx, 20002h
0x18007c6af  mov     edx, ebx; DesiredAccess
0x18007c6b1  lea     rcx, [r8-2]; ThreadHandle
0x18007c6b5  call    cs:__imp_NtOpenThreadToken
0x18007c6bb  test    eax, eax
0x18007c6bd  js      short loc_18007C6CC
0x18007c6bf  mov     rcx, [rbp+57h+TokenHandle]
0x18007c6c3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007c6c7  mov     r14, rcx
0x18007c6ca  jmp     short loc_18007C6F9
0x18007c6cc  cmp     eax, 0C000007Ch
0x18007c6d1  jnz     loc_18007C835
0x18007c6d7  mov     edx, ebx; DesiredAccess
0x18007c6d9  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18007c6dd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007c6e1  mov     rcx, rbx; ProcessHandle
0x18007c6e4  call    cs:__imp_NtOpenProcessToken
0x18007c6ea  test    eax, eax
0x18007c6ec  js      loc_18007C839
0x18007c6f2  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18007c6f6  xor     r14d, r14d
0x18007c6f9  xor     r9d, r9d; Length
0x18007c6fc  lea     rax, [rbp+57h+Length]
0x18007c700  xor     r8d, r8d; SecurityDescriptor
0x18007c703  mov     [rsp+0E0h+LengthNeeded], rax; LengthNeeded
0x18007c708  lea     r12d, [r9+4]
0x18007c70c  mov     edx, r12d; SecurityInformation
0x18007c70f  call    cs:__imp_NtQuerySecurityObject
0x18007c715  cmp     eax, 0C0000023h
0x18007c71a  jnz     loc_18007C83D
0x18007c720  mov     rcx, gs:60h
0x18007c729  lea     edx, [r12+4]; Flags
0x18007c72e  mov     r8d, [rbp+57h+Length]; Size
0x18007c732  mov     rcx, [rcx+30h]; HeapHandle
0x18007c736  call    cs:__imp_RtlAllocateHeap
0x18007c73c  mov     rsi, rax
0x18007c73f  test    rax, rax
0x18007c742  jz      loc_18007C83D
0x18007c748  mov     r9d, [rbp+57h+Length]; Length
0x18007c74c  lea     rax, [rbp+57h+Length]
0x18007c750  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18007c754  mov     r8, rsi; SecurityDescriptor
0x18007c757  mov     edx, r12d; SecurityInformation
0x18007c75a  mov     [rsp+0E0h+LengthNeeded], rax; LengthNeeded
0x18007c75f  call    cs:__imp_NtQuerySecurityObject
0x18007c765  test    eax, eax
0x18007c767  js      loc_18007C83D
0x18007c76d  lea     ecx, [r12-2]
0x18007c772  mov     dword ptr [rbp+57h+var_60], 0Ch
0x18007c779  lea     rax, [rbp+57h+var_60]
0x18007c77d  mov     dword ptr [rbp+57h+var_60+4], ecx
0x18007c780  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x18007c784  lea     edx, [rcx+2Ah]; DesiredAccess
0x18007c787  lea     rax, [rbp+57h+ThreadInformation]
0x18007c78b  mov     word ptr [rbp+57h+var_58], 1
0x18007c791  mov     [rsp+0E0h+NewTokenHandle], rax; NewTokenHandle
0x18007c796  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18007c79a  mov     dword ptr [rsp+0E0h+LengthNeeded], ecx; TokenType
0x18007c79e  xor     r9d, r9d; EffectiveOnly
0x18007c7a1  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x18007c7a5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18007c7ac  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18007c7b4  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x18007c7bb  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x18007c7c3  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rsi
0x18007c7c7  call    cs:__imp_NtDuplicateToken
0x18007c7cd  test    eax, eax
0x18007c7cf  jns     short loc_18007C7D7
0x18007c7d1  mov     [rbp+57h+ThreadInformation], rbx
0x18007c7d5  jmp     short loc_18007C84C
0x18007c7d7  mov     rcx, [rbp+57h+ThreadInformation]; TokenHandle
0x18007c7db  xor     r9d, r9d; BufferLength
0x18007c7de  mov     [rsp+0E0h+NewTokenHandle], 0; ReturnLength
0x18007c7e7  mov     r8, r15; NewState
0x18007c7ea  xor     edx, edx; DisableAllPrivileges
0x18007c7ec  mov     [rsp+0E0h+LengthNeeded], 0; PreviousState
0x18007c7f5  call    cs:__imp_NtAdjustPrivilegesToken
0x18007c7fb  test    eax, eax
0x18007c7fd  js      short loc_18007C83D
0x18007c7ff  mov     r9d, 8; ThreadInformationLength
0x18007c805  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18007c809  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18007c810  lea     edx, [r9-3]; ThreadInformationClass
0x18007c814  call    cs:__imp_NtSetInformationThread
0x18007c81a  test    eax, eax
0x18007c81c  js      short loc_18007C83D
0x18007c81e  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18007c822  cmp     rcx, r14
0x18007c825  jz      short loc_18007C839
0x18007c827  call    cs:__imp_NtClose
0x18007c82d  jmp     short loc_18007C839
0x18007c82f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007c833  jmp     short loc_18007C83D
0x18007c835  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007c839  mov     [rbp+57h+TokenHandle], rbx
0x18007c83d  mov     rcx, [rbp+57h+ThreadInformation]; Handle
0x18007c841  cmp     rcx, rbx
0x18007c844  jz      short loc_18007C84C
0x18007c846  call    cs:__imp_NtClose
0x18007c84c  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18007c850  cmp     rcx, rbx
0x18007c853  jz      short loc_18007C85B
0x18007c855  call    cs:__imp_NtClose
0x18007c85b  test    rsi, rsi
0x18007c85e  jz      short loc_18007C878
0x18007c860  mov     rcx, gs:60h
0x18007c869  mov     r8, rsi; P
0x18007c86c  xor     edx, edx; Flags
0x18007c86e  mov     rcx, [rcx+30h]; HeapHandle
0x18007c872  call    cs:__imp_RtlFreeHeap
0x18007c878  test    rdi, rdi
0x18007c87b  jz      short loc_18007C895
0x18007c87d  mov     rcx, gs:60h
0x18007c886  mov     r8, rdi; P
0x18007c889  xor     edx, edx; Flags
0x18007c88b  mov     rcx, [rcx+30h]; HeapHandle
0x18007c88f  call    cs:__imp_RtlFreeHeap
0x18007c895  mov     rax, r14
0x18007c898  mov     rcx, [rbp+57h+var_28]
0x18007c89c  xor     rcx, rsp; StackCookie
0x18007c89f  call    __security_check_cookie
0x18007c8a4  lea     r11, [rsp+0E0h+var_20]
0x18007c8ac  mov     rbx, [r11+30h]
0x18007c8b0  mov     rsi, [r11+40h]
0x18007c8b4  mov     rsp, r11
0x18007c8b7  pop     r15
0x18007c8b9  pop     r14
0x18007c8bb  pop     r12
0x18007c8bd  pop     rdi
0x18007c8be  pop     rbp
0x18007c8bf  retn
```
