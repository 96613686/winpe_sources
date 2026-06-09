# FindUserWithToken

- ea: `0x1400051a8`
- end: `0x1400054df`
- name: `FindUserWithToken`
- size: `823`
- prototype: `__int64 __fastcall(PACCESS_TOKEN Token)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x140001e98`
- `0x140019f90`

## callees

- `0x14000160c`
- `0x1400051a8`
- `0x140006080`
- `0x140006380`
- `0x140014b6c`
- `0x14001b6a0`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x140005229`
- `ntoskrnl!RtlEqualSid` at `0x140005255`
- `ntoskrnl!RtlEqualSid` at `0x140005281`
- `ntoskrnl!RtlEqualSid` at `0x1400052ed`
- `ntoskrnl!RtlEqualSid` at `0x140005229`
- `ntoskrnl!RtlEqualSid` at `0x140005255`
- `ntoskrnl!RtlEqualSid` at `0x140005281`
- `ntoskrnl!RtlEqualSid` at `0x1400052ed`
- `ntoskrnl!SeQueryServerSiloToken` at `0x1400052b9`
- `ntoskrnl!SeQueryServerSiloToken` at `0x1400052b9`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400053dc`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400053dc`
- `ntoskrnl!RtlCopySid` at `0x140005404`
- `ntoskrnl!RtlCopySid` at `0x140005404`
- `ntoskrnl!SeMarkLogonSessionForTerminationNotificationEx` at `0x140005475`
- `ntoskrnl!SeMarkLogonSessionForTerminationNotificationEx` at `0x140005475`
- `ntoskrnl!RtlLengthSid` at `0x14000534f`
- `ntoskrnl!RtlLengthSid` at `0x14000534f`
- `ntoskrnl!SeQueryInformationToken` at `0x1400051fb`
- `ntoskrnl!SeQueryInformationToken` at `0x1400051fb`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14000529c`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14000529c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400054a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400054b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400054a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400054b9`
- `ntoskrnl!SeExports` at `0x140005211`
- `ntoskrnl!SeExports` at `0x14000523d`
- `ntoskrnl!SeExports` at `0x140005269`

## pseudocode

```c
__int64 __fastcall FindUserWithToken(PACCESS_TOKEN Token, char a2, __int64 *a3)
{
  NTSTATUS v6; // ebx
  __int64 v7; // rbx
  PSID v8; // r14
  ULONG v9; // eax
  __int64 v10; // r8
  ULONG v11; // r13d
  ULONG v12; // r15d
  unsigned int v13; // ebx
  void *Pool; // rax
  __int64 v15; // rdi
  __int16 v16; // ax
  void *v17; // rcx
  __int64 v18; // rax
  PVOID v19; // rdx
  PVOID Object; // [rsp+20h] [rbp-20h] BYREF
  struct _LUID AuthenticationId; // [rsp+28h] [rbp-18h] BYREF
  __int64 v23; // [rsp+30h] [rbp-10h] BYREF
  void *Src; // [rsp+38h] [rbp-8h]
  PVOID TokenInformation; // [rsp+88h] [rbp+48h] BYREF

  AuthenticationId = 0;
  v23 = 0;
  Object = 0;
  TokenInformation = 0;
  Src = 0;
  v6 = SeQueryInformationToken(Token, TokenUser, &TokenInformation);
  if ( v6 >= 0 )
  {
    if ( RtlEqualSid(*(PSID *)TokenInformation, SeExports->SeLocalSystemSid)
      || RtlEqualSid(*(PSID *)TokenInformation, SeExports->SeNetworkServiceSid)
      || RtlEqualSid(*(PSID *)TokenInformation, SeExports->SeLocalServiceSid) )
    {
      v6 = -1073741275;
LABEL_25:
      *a3 = 0;
    }
    else
    {
      v6 = SeQueryAuthenticationIdToken(Token, &AuthenticationId);
      if ( v6 >= 0 )
      {
        v6 = SeQueryServerSiloToken(Token, &Object);
        if ( v6 >= 0 )
        {
          v7 = UserList;
          v8 = *(PSID *)TokenInformation;
          while ( (__int64 *)v7 != &UserList )
          {
            if ( RtlEqualSid(*(PSID *)(v7 + 80), v8) && *(PVOID *)(v7 + 56) == Object )
            {
              _InterlockedExchange64((volatile __int64 *)(v7 + 16), MEMORY[0xFFFFF78000000014]);
              *a3 = v7;
LABEL_15:
              v6 = 0;
              goto LABEL_26;
            }
            v7 = *(_QWORD *)v7;
          }
          if ( !a2 )
          {
            v6 = 0;
            goto LABEL_25;
          }
          v6 = LuafvConvertSidToUnicodeString(&v23, v8);
          if ( v6 >= 0 )
          {
            v9 = RtlLengthSid(v8);
            LOBYTE(v10) = 15;
            v11 = v9;
            v12 = v9 + 1;
            v13 = ((v9 + 1) & 0xFFFFFFFE) + (unsigned __int16)v23 + 192;
            Pool = (void *)LuafvAllocatePool(1, v13, v10);
            v15 = (__int64)Pool;
            if ( Pool )
            {
              memset(Pool, 0, v13);
              *(_DWORD *)(v15 + 24) = 1;
              *(_QWORD *)(v15 + 16) = MEMORY[0xFFFFF78000000014];
              *(_QWORD *)(v15 + 40) = v15 + 32;
              *(_QWORD *)(v15 + 32) = v15 + 32;
              *(struct _LUID *)(v15 + 48) = AuthenticationId;
              if ( Object )
              {
                ObfReferenceObjectWithTag(Object, 0x6661754Cu);
                *(_QWORD *)(v15 + 56) = Object;
              }
              *(_QWORD *)(v15 + 80) = v15 + 192;
              RtlCopySid(v11, (PSID)(v15 + 192), v8);
              *(_WORD *)(v15 + 90) = v23;
              v16 = v23;
              v17 = (void *)(v15 + 192 + (v12 & 0xFFFFFFFE));
              *(_QWORD *)(v15 + 96) = v17;
              *(_WORD *)(v15 + 88) = v16;
              memmove(v17, Src, (unsigned __int16)v23);
              v18 = UserList;
              if ( *(__int64 **)(UserList + 8) != &UserList )
                __fastfail(3u);
              *(_QWORD *)(v15 + 8) = &UserList;
              *(_QWORD *)v15 = v18;
              *(_QWORD *)(v18 + 8) = v15;
              v19 = Object;
              UserList = v15;
              *a3 = v15;
              SeMarkLogonSessionForTerminationNotificationEx(&AuthenticationId, v19);
              LuafvRunScavenger();
              goto LABEL_15;
            }
            v6 = -1073741670;
          }
        }
      }
    }
  }
LABEL_26:
  if ( Src )
    ExFreePoolWithTag(Src, 0);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400051a8  mov     [rsp-28h+arg_0], rbx
0x1400051ad  mov     [rsp-28h+arg_8], rsi
0x1400051b2  push    rbp
0x1400051b3  push    rdi
0x1400051b4  push    r13
0x1400051b6  push    r14
0x1400051b8  push    r15
0x1400051ba  mov     rbp, rsp
0x1400051bd  sub     rsp, 40h
0x1400051c1  mov     rsi, r8
0x1400051c4  mov     qword ptr [rbp+AuthenticationId.LowPart], 0
0x1400051cc  mov     r15b, dl
0x1400051cf  mov     [rbp+var_10], 0
0x1400051d7  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1400051db  mov     [rbp+Object], 0
0x1400051e3  mov     edx, 1; TokenInformationClass
0x1400051e8  mov     [rbp+TokenInformation], 0
0x1400051f0  mov     rdi, rcx
0x1400051f3  mov     [rbp+Src], 0
0x1400051fb  call    cs:__imp_SeQueryInformationToken
0x140005202  nop     dword ptr [rax+rax+00h]
0x140005207  mov     ebx, eax
0x140005209  test    eax, eax
0x14000520b  js      loc_140005497
0x140005211  mov     rax, cs:__imp_SeExports
0x140005218  mov     rcx, [rbp+TokenInformation]
0x14000521c  mov     rdx, [rax]
0x14000521f  mov     rcx, [rcx]; Sid1
0x140005222  mov     rdx, [rdx+108h]; Sid2
0x140005229  call    cs:__imp_RtlEqualSid
0x140005230  nop     dword ptr [rax+rax+00h]
0x140005235  test    al, al
0x140005237  jnz     loc_14000548B
0x14000523d  mov     rax, cs:__imp_SeExports
0x140005244  mov     rcx, [rbp+TokenInformation]
0x140005248  mov     rdx, [rax]
0x14000524b  mov     rcx, [rcx]; Sid1
0x14000524e  mov     rdx, [rdx+188h]; Sid2
0x140005255  call    cs:__imp_RtlEqualSid
0x14000525c  nop     dword ptr [rax+rax+00h]
0x140005261  test    al, al
0x140005263  jnz     loc_14000548B
0x140005269  mov     rax, cs:__imp_SeExports
0x140005270  mov     rcx, [rbp+TokenInformation]
0x140005274  mov     rdx, [rax]
0x140005277  mov     rcx, [rcx]; Sid1
0x14000527a  mov     rdx, [rdx+180h]; Sid2
0x140005281  call    cs:__imp_RtlEqualSid
0x140005288  nop     dword ptr [rax+rax+00h]
0x14000528d  test    al, al
0x14000528f  jnz     loc_14000548B
0x140005295  lea     rdx, [rbp+AuthenticationId]; AuthenticationId
0x140005299  mov     rcx, rdi; Token
0x14000529c  call    cs:__imp_SeQueryAuthenticationIdToken
0x1400052a3  nop     dword ptr [rax+rax+00h]
0x1400052a8  mov     ebx, eax
0x1400052aa  test    eax, eax
0x1400052ac  js      loc_140005497
0x1400052b2  lea     rdx, [rbp+Object]
0x1400052b6  mov     rcx, rdi
0x1400052b9  call    cs:__imp_SeQueryServerSiloToken
0x1400052c0  nop     dword ptr [rax+rax+00h]
0x1400052c5  mov     ebx, eax
0x1400052c7  test    eax, eax
0x1400052c9  js      loc_140005497
0x1400052cf  mov     rax, [rbp+TokenInformation]
0x1400052d3  lea     rdi, UserList
0x1400052da  mov     rbx, cs:UserList
0x1400052e1  mov     r14, [rax]
0x1400052e4  jmp     short loc_14000530A
0x1400052e6  mov     rcx, [rbx+50h]; Sid1
0x1400052ea  mov     rdx, r14; Sid2
0x1400052ed  call    cs:__imp_RtlEqualSid
0x1400052f4  nop     dword ptr [rax+rax+00h]
0x1400052f9  test    al, al
0x1400052fb  jz      short loc_140005307
0x1400052fd  mov     rax, [rbp+Object]
0x140005301  cmp     [rbx+38h], rax
0x140005305  jz      short loc_14000531B
0x140005307  mov     rbx, [rbx]
0x14000530a  cmp     rbx, rdi
0x14000530d  jnz     short loc_1400052E6
0x14000530f  test    r15b, r15b
0x140005312  jnz     short loc_140005336
0x140005314  xor     ebx, ebx
0x140005316  jmp     loc_140005490
0x14000531b  mov     rax, 0FFFFF78000000014h
0x140005325  mov     rax, [rax]
0x140005328  xchg    rax, [rbx+10h]
0x14000532c  mov     [rsi], rbx
0x14000532f  xor     ebx, ebx
0x140005331  jmp     loc_140005497
0x140005336  mov     rdx, r14
0x140005339  lea     rcx, [rbp+var_10]
0x14000533d  call    LuafvConvertSidToUnicodeString
0x140005342  mov     ebx, eax
0x140005344  test    eax, eax
0x140005346  js      loc_140005497
0x14000534c  mov     rcx, r14; Sid
0x14000534f  call    cs:__imp_RtlLengthSid
0x140005356  nop     dword ptr [rax+rax+00h]
0x14000535b  movzx   ebx, word ptr [rbp+var_10]
0x14000535f  mov     r8b, 0Fh
0x140005362  mov     r13d, eax
0x140005365  add     ebx, 0C0h
0x14000536b  mov     ecx, 1
0x140005370  lea     r15d, [rax+1]
0x140005374  mov     eax, 0FFFFFFFEh
0x140005379  mov     edx, r15d
0x14000537c  and     edx, eax
0x14000537e  add     ebx, edx
0x140005380  mov     edx, ebx
0x140005382  call    LuafvAllocatePool
0x140005387  mov     rdi, rax
0x14000538a  test    rax, rax
0x14000538d  jnz     short loc_140005399
0x14000538f  mov     ebx, 0C000009Ah
0x140005394  jmp     loc_140005497
0x140005399  mov     r8d, ebx; Size
0x14000539c  xor     edx, edx; Val
0x14000539e  mov     rcx, rdi; void *
0x1400053a1  call    memset
0x1400053a6  mov     dword ptr [rdi+18h], 1
0x1400053ad  mov     rax, ds:0FFFFF78000000014h
0x1400053b7  mov     [rdi+10h], rax
0x1400053bb  lea     rax, [rdi+20h]
0x1400053bf  mov     [rax+8], rax
0x1400053c3  mov     [rax], rax
0x1400053c6  mov     rax, qword ptr [rbp+AuthenticationId.LowPart]
0x1400053ca  mov     [rdi+30h], rax
0x1400053ce  mov     rcx, [rbp+Object]; Object
0x1400053d2  test    rcx, rcx
0x1400053d5  jz      short loc_1400053F0
0x1400053d7  mov     edx, 6661754Ch; Tag
0x1400053dc  call    cs:__imp_ObfReferenceObjectWithTag
0x1400053e3  nop     dword ptr [rax+rax+00h]
0x1400053e8  mov     rax, [rbp+Object]
0x1400053ec  mov     [rdi+38h], rax
0x1400053f0  lea     rbx, [rdi+0C0h]
0x1400053f7  mov     r8, r14; SourceSid
0x1400053fa  mov     rdx, rbx; DestinationSid
0x1400053fd  mov     [rdi+50h], rbx
0x140005401  mov     ecx, r13d; DestinationSidLength
0x140005404  call    cs:__imp_RtlCopySid
0x14000540b  nop     dword ptr [rax+rax+00h]
0x140005410  movzx   eax, word ptr [rbp+var_10]
0x140005414  mov     ecx, 0FFFFFFFEh
0x140005419  mov     [rdi+5Ah], ax
0x14000541d  and     rcx, r15
0x140005420  movzx   eax, word ptr [rbp+var_10]
0x140005424  add     rcx, rbx; void *
0x140005427  mov     [rdi+60h], rcx
0x14000542b  mov     [rdi+58h], ax
0x14000542f  movzx   r8d, word ptr [rbp+var_10]; Size
0x140005434  mov     rdx, [rbp+Src]; Src
0x140005438  call    memmove
0x14000543d  mov     rax, cs:UserList
0x140005444  lea     rcx, UserList
0x14000544b  cmp     [rax+8], rcx
0x14000544f  jz      short loc_140005458
0x140005451  mov     ecx, 3
0x140005456  int     29h; Win8: RtlFailFast(ecx)
0x140005458  mov     [rdi+8], rcx
0x14000545c  lea     rcx, [rbp+AuthenticationId]
0x140005460  mov     [rdi], rax
0x140005463  mov     [rax+8], rdi
0x140005467  mov     rdx, [rbp+Object]
0x14000546b  mov     cs:UserList, rdi
0x140005472  mov     [rsi], rdi
0x140005475  call    cs:__imp_SeMarkLogonSessionForTerminationNotificationEx
0x14000547c  nop     dword ptr [rax+rax+00h]
0x140005481  call    LuafvRunScavenger
0x140005486  jmp     loc_14000532F
0x14000548b  mov     ebx, 0C0000225h
0x140005490  mov     qword ptr [rsi], 0
0x140005497  mov     rcx, [rbp+Src]; P
0x14000549b  test    rcx, rcx
0x14000549e  jz      short loc_1400054AE
0x1400054a0  xor     edx, edx; Tag
0x1400054a2  call    cs:__imp_ExFreePoolWithTag
0x1400054a9  nop     dword ptr [rax+rax+00h]
0x1400054ae  mov     rcx, [rbp+TokenInformation]; P
0x1400054b2  test    rcx, rcx
0x1400054b5  jz      short loc_1400054C5
0x1400054b7  xor     edx, edx; Tag
0x1400054b9  call    cs:__imp_ExFreePoolWithTag
0x1400054c0  nop     dword ptr [rax+rax+00h]
0x1400054c5  mov     rsi, [rsp+40h+arg_8]
0x1400054ca  mov     eax, ebx
0x1400054cc  mov     rbx, [rsp+40h+arg_0]
0x1400054d1  add     rsp, 40h
0x1400054d5  pop     r15
0x1400054d7  pop     r14
0x1400054d9  pop     r13
0x1400054db  pop     rdi
0x1400054dc  pop     rbp
0x1400054dd  retn
```
