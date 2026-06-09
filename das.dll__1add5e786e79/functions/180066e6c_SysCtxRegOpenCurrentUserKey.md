# _SysCtxRegOpenCurrentUserKey

- ea: `0x180066e6c`
- end: `0x18006715f`
- name: `_SysCtxRegOpenCurrentUserKey`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180065784`

## callees

- `0x180003ed0`
- `0x18003bc80`
- `0x180066d70`
- `0x180066e6c`

## import_xrefs

- `ntdll!RtlAppendUnicodeStringToString` at `0x18006709a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800670af`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18006709a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800670af`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180067026`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180067026`
- `ntdll!RtlEqualSid` at `0x180067012`
- `ntdll!RtlEqualSid` at `0x180067012`
- `ntdll!NtQueryInformationToken` at `0x180066f3d`
- `ntdll!NtQueryInformationToken` at `0x180066f7b`
- `ntdll!NtQueryInformationToken` at `0x180066fca`
- `ntdll!NtQueryInformationToken` at `0x180066f3d`
- `ntdll!NtQueryInformationToken` at `0x180066f7b`
- `ntdll!NtQueryInformationToken` at `0x180066fca`
- `ntdll!NtOpenProcessTokenEx` at `0x180066f0c`
- `ntdll!NtOpenProcessTokenEx` at `0x180066f0c`
- `ntdll!NtOpenThreadTokenEx` at `0x180066eef`
- `ntdll!NtOpenThreadTokenEx` at `0x180066eef`
- `ntdll!NtClose` at `0x180067109`
- `ntdll!NtClose` at `0x180067109`
- `ntdll!RtlSubAuthoritySid` at `0x180066fff`
- `ntdll!RtlSubAuthoritySid` at `0x180066fff`
- `ntdll!RtlInitializeSid` at `0x180066fe9`
- `ntdll!RtlInitializeSid` at `0x180066fe9`
- `ntdll!RtlFreeUnicodeString` at `0x180067113`
- `ntdll!RtlFreeUnicodeString` at `0x180067113`
- `ntdll!RtlFreeHeap` at `0x180067130`
- `ntdll!RtlFreeHeap` at `0x180067130`
- `ntdll!RtlAllocateHeap` at `0x18006706b`
- `ntdll!RtlAllocateHeap` at `0x18006706b`

## pseudocode

```c
__int64 __fastcall SysCtxRegOpenCurrentUserKey(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  WCHAR *v6; // rdi
  NTSTATUS appended; // ebx
  PSID v8; // rsi
  USHORT v9; // bx
  WCHAR *Heap; // rax
  int TokenInformation; // [rsp+30h] [rbp-99h] BYREF
  int v13; // [rsp+34h] [rbp-95h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-91h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-89h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+48h] [rbp-81h] BYREF
  __int64 v17; // [rsp+58h] [rbp-71h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-69h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+70h] [rbp-59h] BYREF
  _BYTE Sid[16]; // [rsp+78h] [rbp-51h] BYREF
  PSID Sid2[11]; // [rsp+88h] [rbp-41h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  Handle = 0;
  TokenInformation = 0;
  v13 = 0;
  ReturnLength = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v17 = 0;
  v6 = 0;
  UnicodeString = 0;
  Destination = 0;
  appended = NtOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, 0, &Handle);
  if ( appended == -1073741700 )
    appended = NtOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0, &Handle);
  if ( appended >= 0 )
  {
    TokenInformation = 0;
    appended = NtQueryInformationToken(Handle, TokenType, &TokenInformation, 4u, &ReturnLength);
    if ( appended >= 0 )
    {
      if ( TokenInformation == 2 )
      {
        v13 = 0;
        appended = NtQueryInformationToken(Handle, TokenImpersonationLevel, &v13, 4u, &ReturnLength);
        if ( appended < 0 )
          goto LABEL_24;
        if ( v13 < 2 )
        {
          appended = -1073741790;
          goto LABEL_24;
        }
      }
      else if ( TokenInformation != 1 )
      {
        goto LABEL_10;
      }
      appended = NtQueryInformationToken(Handle, TokenUser, Sid2, 0x54u, &ReturnLength);
      if ( appended < 0 )
        goto LABEL_24;
      v8 = Sid2[0];
      appended = RtlInitializeSid(Sid, &IdentifierAuthority, 1u);
      if ( appended < 0 )
        goto LABEL_24;
      *RtlSubAuthoritySid(Sid, 0) = 18;
      if ( !RtlEqualSid(Sid, v8) )
      {
        appended = RtlConvertSidToUnicodeString(&UnicodeString, v8, 1u);
        if ( appended >= 0 )
        {
          if ( (unsigned __int16)(UnicodeString.Length + 30) < UnicodeString.Length
            || (v9 = UnicodeString.Length + 32,
                (unsigned __int16)(UnicodeString.Length + 32) < (unsigned __int16)(UnicodeString.Length + 30)) )
          {
            appended = -1073741675;
          }
          else
          {
            Heap = (WCHAR *)RtlAllocateHeap(
                              NtCurrentPeb()->ProcessHeap,
                              8u,
                              (unsigned __int16)(UnicodeString.Length + 32));
            v6 = Heap;
            if ( Heap )
            {
              Destination.Length = 0;
              Destination.MaximumLength = v9;
              Destination.Buffer = Heap;
              appended = RtlAppendUnicodeStringToString(&Destination, &Source);
              if ( appended >= 0 )
              {
                appended = RtlAppendUnicodeStringToString(&Destination, &UnicodeString);
                if ( appended >= 0 )
                {
                  appended = SysCtxGetCachedContextBaseKey(a1, 3, &v17);
                  if ( appended >= 0 )
                    appended = SysCtxRegOpenKey(a1, v17, LODWORD(Destination.Buffer) + 30, 0, 0x2000000, a4);
                }
              }
            }
            else
            {
              appended = -1073741801;
            }
          }
        }
        goto LABEL_24;
      }
LABEL_10:
      appended = -1073741637;
    }
  }
LABEL_24:
  if ( Handle )
    NtClose(Handle);
  RtlFreeUnicodeString(&UnicodeString);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180066e6c  mov     [rsp-8+arg_8], rbx
0x180066e71  push    rbp
0x180066e72  push    rsi
0x180066e73  push    rdi
0x180066e74  push    r12
0x180066e76  push    r13
0x180066e78  push    r14
0x180066e7a  push    r15
0x180066e7c  lea     rbp, [rsp-27h]
0x180066e81  sub     rsp, 0F0h
0x180066e88  mov     rax, cs:__security_cookie
0x180066e8f  xor     rax, rsp
0x180066e92  mov     [rbp+57h+var_40], rax
0x180066e96  xor     r12d, r12d
0x180066e99  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x180066e9f  mov     r15, r9
0x180066ea2  mov     [rsp+120h+Handle], r12
0x180066ea7  mov     r14, rcx
0x180066eaa  mov     [rsp+120h+TokenInformation], r12d
0x180066eaf  xorps   xmm0, xmm0
0x180066eb2  mov     [rsp+120h+var_EC], r12d
0x180066eb7  xorps   xmm1, xmm1
0x180066eba  mov     [rsp+120h+ReturnLength], r12d
0x180066ebf  lea     rax, [rsp+120h+Handle]
0x180066ec4  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r12d
0x180066ec8  lea     esi, [r12+8]
0x180066ecd  mov     [rbp+57h+var_C8], r12
0x180066ed1  mov     edx, esi; DesiredAccess
0x180066ed3  mov     [rsp+120h+TokenHandle], rax; TokenHandle
0x180066ed8  xor     r9d, r9d; HandleAttributes
0x180066edb  lea     rcx, [r12-2]; ThreadHandle
0x180066ee0  xor     r8d, r8d; OpenAsSelf
0x180066ee3  mov     edi, r12d
0x180066ee6  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x180066eea  movups  xmmword ptr [rsp+120h+Destination.Length], xmm1
0x180066eef  call    cs:__imp_NtOpenThreadTokenEx
0x180066ef5  mov     ebx, eax
0x180066ef7  cmp     eax, 0C000007Ch
0x180066efc  jnz     short loc_180066F14
0x180066efe  lea     r9, [rsp+120h+Handle]; TokenHandle
0x180066f03  xor     r8d, r8d; HandleAttributes
0x180066f06  mov     edx, esi; DesiredAccess
0x180066f08  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180066f0c  call    cs:__imp_NtOpenProcessTokenEx
0x180066f12  mov     ebx, eax
0x180066f14  test    ebx, ebx
0x180066f16  js      loc_1800670FF
0x180066f1c  mov     rcx, [rsp+120h+Handle]; TokenHandle
0x180066f21  lea     rax, [rsp+120h+ReturnLength]
0x180066f26  mov     r9d, 4; TokenInformationLength
0x180066f2c  mov     [rsp+120h+TokenHandle], rax; ReturnLength
0x180066f31  lea     r8, [rsp+120h+TokenInformation]; TokenInformation
0x180066f36  mov     [rsp+120h+TokenInformation], r12d
0x180066f3b  mov     edx, esi; TokenInformationClass
0x180066f3d  call    cs:__imp_NtQueryInformationToken
0x180066f43  mov     ebx, eax
0x180066f45  test    eax, eax
0x180066f47  js      loc_1800670FF
0x180066f4d  mov     r13d, 2
0x180066f53  cmp     [rsp+120h+TokenInformation], r13d
0x180066f58  jnz     short loc_180066F9C
0x180066f5a  mov     rcx, [rsp+120h+Handle]; TokenHandle
0x180066f5f  lea     rax, [rsp+120h+ReturnLength]
0x180066f64  lea     r9d, [r13+2]; TokenInformationLength
0x180066f68  mov     [rsp+120h+TokenHandle], rax; ReturnLength
0x180066f6d  lea     r8, [rsp+120h+var_EC]; TokenInformation
0x180066f72  mov     [rsp+120h+var_EC], r12d
0x180066f77  lea     edx, [r13+7]; TokenInformationClass
0x180066f7b  call    cs:__imp_NtQueryInformationToken
0x180066f81  mov     ebx, eax
0x180066f83  test    eax, eax
0x180066f85  js      loc_1800670FF
0x180066f8b  cmp     [rsp+120h+var_EC], r13d
0x180066f90  jge     short loc_180066FAD
0x180066f92  mov     ebx, 0C0000022h
0x180066f97  jmp     loc_1800670FF
0x180066f9c  cmp     [rsp+120h+TokenInformation], 1
0x180066fa1  jz      short loc_180066FAD
0x180066fa3  mov     ebx, 0C00000BBh
0x180066fa8  jmp     loc_1800670FF
0x180066fad  mov     rcx, [rsp+120h+Handle]; TokenHandle
0x180066fb2  lea     rax, [rsp+120h+ReturnLength]
0x180066fb7  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180066fbd  mov     [rsp+120h+TokenHandle], rax; ReturnLength
0x180066fc2  lea     r8, [rbp+57h+Sid2]; TokenInformation
0x180066fc6  lea     edx, [r9-53h]; TokenInformationClass
0x180066fca  call    cs:__imp_NtQueryInformationToken
0x180066fd0  mov     ebx, eax
0x180066fd2  test    eax, eax
0x180066fd4  js      loc_1800670FF
0x180066fda  mov     rsi, [rbp+57h+Sid2]
0x180066fde  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180066fe2  mov     r8b, 1; SubAuthorityCount
0x180066fe5  lea     rcx, [rbp+57h+Sid]; Sid
0x180066fe9  call    cs:__imp_RtlInitializeSid
0x180066fef  mov     ebx, eax
0x180066ff1  test    eax, eax
0x180066ff3  js      loc_1800670FF
0x180066ff9  xor     edx, edx; SubAuthority
0x180066ffb  lea     rcx, [rbp+57h+Sid]; Sid
0x180066fff  call    cs:__imp_RtlSubAuthoritySid
0x180067005  mov     rdx, rsi; Sid2
0x180067008  lea     rcx, [rbp+57h+Sid]; Sid1
0x18006700c  mov     dword ptr [rax], 12h
0x180067012  call    cs:__imp_RtlEqualSid
0x180067018  test    al, al
0x18006701a  jnz     short loc_180066FA3
0x18006701c  mov     r8b, 1; AllocateDestinationString
0x18006701f  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x180067023  mov     rdx, rsi; Sid
0x180067026  call    cs:__imp_RtlConvertSidToUnicodeString
0x18006702c  mov     ebx, eax
0x18006702e  test    eax, eax
0x180067030  js      loc_1800670FF
0x180067036  movzx   eax, [rbp+57h+UnicodeString.Length]
0x18006703a  add     ax, 1Eh
0x18006703e  cmp     ax, [rbp+57h+UnicodeString.Length]
0x180067042  jb      loc_1800670FA
0x180067048  lea     ebx, [rax+r13]
0x18006704c  cmp     bx, ax
0x18006704f  jb      loc_1800670FA
0x180067055  mov     rcx, gs:60h
0x18006705e  mov     edx, 8; Flags
0x180067063  movzx   r8d, bx; Size
0x180067067  mov     rcx, [rcx+30h]; HeapHandle
0x18006706b  call    cs:__imp_RtlAllocateHeap
0x180067071  mov     rdi, rax
0x180067074  test    rax, rax
0x180067077  jnz     short loc_180067080
0x180067079  mov     ebx, 0C0000017h
0x18006707e  jmp     short loc_1800670FF
0x180067080  lea     rdx, Source; Source
0x180067087  mov     [rsp+120h+Destination.Length], r12w
0x18006708d  lea     rcx, [rsp+120h+Destination]; Destination
0x180067092  mov     [rbp+57h+Destination.MaximumLength], bx
0x180067096  mov     [rbp+57h+Destination.Buffer], rax
0x18006709a  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800670a0  mov     ebx, eax
0x1800670a2  test    eax, eax
0x1800670a4  js      short loc_1800670FF
0x1800670a6  lea     rdx, [rbp+57h+UnicodeString]; Source
0x1800670aa  lea     rcx, [rsp+120h+Destination]; Destination
0x1800670af  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800670b5  mov     ebx, eax
0x1800670b7  test    eax, eax
0x1800670b9  js      short loc_1800670FF
0x1800670bb  lea     r8, [rbp+57h+var_C8]
0x1800670bf  mov     edx, 3
0x1800670c4  mov     rcx, r14
0x1800670c7  call    _SysCtxGetCachedContextBaseKey
0x1800670cc  mov     ebx, eax
0x1800670ce  test    eax, eax
0x1800670d0  js      short loc_1800670FF
0x1800670d2  mov     r8, [rbp+57h+Destination.Buffer]
0x1800670d6  xor     r9d, r9d
0x1800670d9  mov     rdx, [rbp+57h+var_C8]
0x1800670dd  add     r8, 1Eh
0x1800670e1  mov     [rsp+120h+var_F8], r15
0x1800670e6  mov     rcx, r14
0x1800670e9  mov     dword ptr [rsp+120h+TokenHandle], 2000000h
0x1800670f1  call    _SysCtxRegOpenKey
0x1800670f6  mov     ebx, eax
0x1800670f8  jmp     short loc_1800670FF
0x1800670fa  mov     ebx, 0C0000095h
0x1800670ff  mov     rcx, [rsp+120h+Handle]; Handle
0x180067104  test    rcx, rcx
0x180067107  jz      short loc_18006710F
0x180067109  call    cs:__imp_NtClose
0x18006710f  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x180067113  call    cs:__imp_RtlFreeUnicodeString
0x180067119  test    rdi, rdi
0x18006711c  jz      short loc_180067136
0x18006711e  mov     rcx, gs:60h
0x180067127  mov     r8, rdi; P
0x18006712a  xor     edx, edx; Flags
0x18006712c  mov     rcx, [rcx+30h]; HeapHandle
0x180067130  call    cs:__imp_RtlFreeHeap
0x180067136  mov     eax, ebx
0x180067138  mov     rcx, [rbp+57h+var_40]
0x18006713c  xor     rcx, rsp; StackCookie
0x18006713f  call    __security_check_cookie
0x180067144  mov     rbx, [rsp+120h+arg_8]
0x18006714c  add     rsp, 0F0h
0x180067153  pop     r15
0x180067155  pop     r14
0x180067157  pop     r13
0x180067159  pop     r12
0x18006715b  pop     rdi
0x18006715c  pop     rsi
0x18006715d  pop     rbp
0x18006715e  retn
```
