# FindUserWithToken

- ea: `0x140001f7c`
- end: `0x140002341`
- name: `FindUserWithToken`
- size: `965`
- prototype: `__int64 __fastcall(PACCESS_TOKEN Token, char, char, __int64 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x140001e98`
- `0x140019f40`

## callees

- `0x14000160c`
- `0x140001f7c`
- `0x140005370`
- `0x14000561c`
- `0x14000572c`
- `0x140005d00`
- `0x140006000`
- `0x140014b6c`
- `0x14001b650`
- `0x14001dd40`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x140001fe9`
- `ntoskrnl!RtlEqualSid` at `0x140002015`
- `ntoskrnl!RtlEqualSid` at `0x140002041`
- `ntoskrnl!RtlEqualSid` at `0x1400020b4`
- `ntoskrnl!RtlEqualSid` at `0x140001fe9`
- `ntoskrnl!RtlEqualSid` at `0x140002015`
- `ntoskrnl!RtlEqualSid` at `0x140002041`
- `ntoskrnl!RtlEqualSid` at `0x1400020b4`
- `ntoskrnl!SeQueryServerSiloToken` at `0x140002079`
- `ntoskrnl!SeQueryServerSiloToken` at `0x140002079`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400021fb`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400021fb`
- `ntoskrnl!RtlCopySid` at `0x140002223`
- `ntoskrnl!RtlCopySid` at `0x140002223`
- `ntoskrnl!SeMarkLogonSessionForTerminationNotificationEx` at `0x1400022e1`
- `ntoskrnl!SeMarkLogonSessionForTerminationNotificationEx` at `0x1400022e1`
- `ntoskrnl!RtlLengthSid` at `0x14000216e`
- `ntoskrnl!RtlLengthSid` at `0x14000216e`
- `ntoskrnl!SeQueryInformationToken` at `0x140001fbb`
- `ntoskrnl!SeQueryInformationToken` at `0x140001fbb`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14000205c`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14000205c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000230a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002321`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000230a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002321`
- `ntoskrnl!SeExports` at `0x140001fd1`
- `ntoskrnl!SeExports` at `0x140001ffd`
- `ntoskrnl!SeExports` at `0x140002029`

## pseudocode

```c
__int64 __fastcall FindUserWithToken(PACCESS_TOKEN Token, char a2, char a3, __int64 *a4)
{
  NTSTATUS UserProfilePaths; // ebx
  __int64 v9; // rdi
  PSID v10; // r14
  ULONG v11; // eax
  __int64 v12; // r8
  ULONG v13; // r13d
  ULONG v14; // r15d
  unsigned int v15; // ebx
  void *Pool; // rax
  __int64 v17; // rdi
  __int16 v18; // ax
  void *v19; // rcx
  __int64 v20; // rax
  PVOID v21; // rdx
  PVOID TokenInformation; // [rsp+20h] [rbp-38h] BYREF
  PVOID Object; // [rsp+28h] [rbp-30h] BYREF
  struct _LUID AuthenticationId; // [rsp+30h] [rbp-28h] BYREF
  __int64 v26; // [rsp+38h] [rbp-20h] BYREF
  void *Src; // [rsp+40h] [rbp-18h]

  AuthenticationId = 0;
  v26 = 0;
  Object = 0;
  TokenInformation = 0;
  Src = 0;
  UserProfilePaths = SeQueryInformationToken(Token, TokenUser, &TokenInformation);
  if ( UserProfilePaths >= 0 )
  {
    if ( RtlEqualSid(*(PSID *)TokenInformation, SeExports->SeLocalSystemSid)
      || RtlEqualSid(*(PSID *)TokenInformation, SeExports->SeNetworkServiceSid)
      || RtlEqualSid(*(PSID *)TokenInformation, SeExports->SeLocalServiceSid) )
    {
      UserProfilePaths = -1073741275;
LABEL_37:
      *a4 = 0;
    }
    else
    {
      UserProfilePaths = SeQueryAuthenticationIdToken(Token, &AuthenticationId);
      if ( UserProfilePaths >= 0 )
      {
        UserProfilePaths = SeQueryServerSiloToken(Token, &Object);
        if ( UserProfilePaths >= 0 )
        {
          v9 = UserList;
          v10 = *(PSID *)TokenInformation;
          while ( (__int64 *)v9 != &UserList )
          {
            if ( RtlEqualSid(*(PSID *)(v9 + 80), v10) && *(PVOID *)(v9 + 56) == Object )
            {
              if ( !a3 )
                goto LABEL_20;
              if ( *(_QWORD *)(v9 + 112) )
                goto LABEL_45;
              if ( !a2 )
              {
LABEL_15:
                UserProfilePaths = 0;
                goto LABEL_37;
              }
              UserProfilePaths = GetUserProfilePaths(v9);
              if ( UserProfilePaths >= 0 )
              {
LABEL_45:
                if ( *(_QWORD *)(v9 + 184)
                  || (UserProfilePaths = OpenProfileKey(v9 + 88, v9 + 184), UserProfilePaths >= 0)
                  && (UserProfilePaths = GetUserDesktopPath(*(_QWORD *)(v9 + 184), v9), UserProfilePaths >= 0) )
                {
LABEL_20:
                  _InterlockedExchange64((volatile __int64 *)(v9 + 16), MEMORY[0xFFFFF78000000014]);
                  *a4 = v9;
LABEL_21:
                  UserProfilePaths = 0;
                  goto LABEL_38;
                }
              }
              goto LABEL_38;
            }
            v9 = *(_QWORD *)v9;
          }
          if ( !a2 )
            goto LABEL_15;
          UserProfilePaths = LuafvConvertSidToUnicodeString(&v26, v10);
          if ( UserProfilePaths >= 0 )
          {
            v11 = RtlLengthSid(v10);
            LOBYTE(v12) = 15;
            v13 = v11;
            v14 = v11 + 1;
            v15 = ((v11 + 1) & 0xFFFFFFFE) + (unsigned __int16)v26 + 192;
            Pool = (void *)LuafvAllocatePool(1, v15, v12);
            v17 = (__int64)Pool;
            if ( !Pool )
            {
              UserProfilePaths = -1073741670;
              goto LABEL_38;
            }
            memset(Pool, 0, v15);
            *(_DWORD *)(v17 + 24) = 1;
            *(_QWORD *)(v17 + 16) = MEMORY[0xFFFFF78000000014];
            *(_QWORD *)(v17 + 40) = v17 + 32;
            *(_QWORD *)(v17 + 32) = v17 + 32;
            *(struct _LUID *)(v17 + 48) = AuthenticationId;
            if ( Object )
            {
              ObfReferenceObjectWithTag(Object, 0x6661754Cu);
              *(_QWORD *)(v17 + 56) = Object;
            }
            *(_QWORD *)(v17 + 80) = v17 + 192;
            RtlCopySid(v13, (PSID)(v17 + 192), v10);
            *(_WORD *)(v17 + 90) = v26;
            v18 = v26;
            v19 = (void *)(v17 + 192 + (v14 & 0xFFFFFFFE));
            *(_QWORD *)(v17 + 96) = v19;
            *(_WORD *)(v17 + 88) = v18;
            memmove(v19, Src, (unsigned __int16)v26);
            if ( !a3 )
              goto LABEL_33;
            UserProfilePaths = GetUserProfilePaths(v17);
            if ( UserProfilePaths < 0 || (UserProfilePaths = OpenProfileKey(v17 + 88, v17 + 184), UserProfilePaths < 0) )
            {
              LuafvFreePool(v17);
              goto LABEL_38;
            }
            UserProfilePaths = GetUserDesktopPath(*(_QWORD *)(v17 + 184), v17);
            if ( UserProfilePaths >= 0 )
            {
LABEL_33:
              v20 = UserList;
              if ( *(__int64 **)(UserList + 8) != &UserList )
                __fastfail(3u);
              *(_QWORD *)(v17 + 8) = &UserList;
              *(_QWORD *)v17 = v20;
              *(_QWORD *)(v20 + 8) = v17;
              v21 = Object;
              UserList = v17;
              *a4 = v17;
              SeMarkLogonSessionForTerminationNotificationEx(&AuthenticationId, v21);
              LuafvRunScavenger();
              goto LABEL_21;
            }
          }
        }
      }
    }
  }
LABEL_38:
  if ( Src )
    ExFreePoolWithTag(Src, 0);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  return (unsigned int)UserProfilePaths;
}

```

## disassembly

```asm
0x140001f7c  push    rbp
0x140001f7e  push    rbx
0x140001f7f  push    rsi
0x140001f80  push    rdi
0x140001f81  push    r12
0x140001f83  push    r13
0x140001f85  push    r14
0x140001f87  push    r15
0x140001f89  mov     rbp, rsp
0x140001f8c  sub     rsp, 58h
0x140001f90  xor     r13d, r13d
0x140001f93  mov     r12b, r8b
0x140001f96  mov     r15b, dl
0x140001f99  mov     qword ptr [rbp+AuthenticationId.LowPart], r13
0x140001f9d  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140001fa1  mov     [rbp+var_20], r13
0x140001fa5  mov     rsi, r9
0x140001fa8  mov     [rbp+Object], r13
0x140001fac  lea     edx, [r13+1]; TokenInformationClass
0x140001fb0  mov     [rbp+TokenInformation], r13
0x140001fb4  mov     rdi, rcx
0x140001fb7  mov     [rbp+Src], r13
0x140001fbb  call    cs:__imp_SeQueryInformationToken
0x140001fc2  nop     dword ptr [rax+rax+00h]
0x140001fc7  mov     ebx, eax
0x140001fc9  test    eax, eax
0x140001fcb  js      loc_1400022FF
0x140001fd1  mov     rax, cs:__imp_SeExports
0x140001fd8  mov     rcx, [rbp+TokenInformation]
0x140001fdc  mov     rdx, [rax]
0x140001fdf  mov     rcx, [rcx]; Sid1
0x140001fe2  mov     rdx, [rdx+108h]; Sid2
0x140001fe9  call    cs:__imp_RtlEqualSid
0x140001ff0  nop     dword ptr [rax+rax+00h]
0x140001ff5  test    al, al
0x140001ff7  jnz     loc_1400022F7
0x140001ffd  mov     rax, cs:__imp_SeExports
0x140002004  mov     rcx, [rbp+TokenInformation]
0x140002008  mov     rdx, [rax]
0x14000200b  mov     rcx, [rcx]; Sid1
0x14000200e  mov     rdx, [rdx+188h]; Sid2
0x140002015  call    cs:__imp_RtlEqualSid
0x14000201c  nop     dword ptr [rax+rax+00h]
0x140002021  test    al, al
0x140002023  jnz     loc_1400022F7
0x140002029  mov     rax, cs:__imp_SeExports
0x140002030  mov     rcx, [rbp+TokenInformation]
0x140002034  mov     rdx, [rax]
0x140002037  mov     rcx, [rcx]; Sid1
0x14000203a  mov     rdx, [rdx+180h]; Sid2
0x140002041  call    cs:__imp_RtlEqualSid
0x140002048  nop     dword ptr [rax+rax+00h]
0x14000204d  test    al, al
0x14000204f  jnz     loc_1400022F7
0x140002055  lea     rdx, [rbp+AuthenticationId]; AuthenticationId
0x140002059  mov     rcx, rdi; Token
0x14000205c  call    cs:__imp_SeQueryAuthenticationIdToken
0x140002063  nop     dword ptr [rax+rax+00h]
0x140002068  mov     ebx, eax
0x14000206a  test    eax, eax
0x14000206c  js      loc_1400022FF
0x140002072  lea     rdx, [rbp+Object]
0x140002076  mov     rcx, rdi
0x140002079  call    cs:__imp_SeQueryServerSiloToken
0x140002080  nop     dword ptr [rax+rax+00h]
0x140002085  mov     ebx, eax
0x140002087  test    eax, eax
0x140002089  js      loc_1400022FF
0x14000208f  mov     rax, [rbp+TokenInformation]
0x140002093  mov     rdi, cs:UserList
0x14000209a  mov     r14, [rax]
0x14000209d  lea     rax, UserList
0x1400020a4  cmp     rdi, rax
0x1400020a7  jz      loc_140002150
0x1400020ad  mov     rcx, [rdi+50h]; Sid1
0x1400020b1  mov     rdx, r14; Sid2
0x1400020b4  call    cs:__imp_RtlEqualSid
0x1400020bb  nop     dword ptr [rax+rax+00h]
0x1400020c0  test    al, al
0x1400020c2  jz      short loc_1400020CE
0x1400020c4  mov     rax, [rbp+Object]
0x1400020c8  cmp     [rdi+38h], rax
0x1400020cc  jz      short loc_1400020D3
0x1400020ce  mov     rdi, [rdi]
0x1400020d1  jmp     short loc_14000209D
0x1400020d3  test    r12b, r12b
0x1400020d6  jz      short loc_140002134
0x1400020d8  cmp     [rdi+70h], r13
0x1400020dc  jnz     short loc_1400020FD
0x1400020de  test    r15b, r15b
0x1400020e1  jnz     short loc_1400020EB
0x1400020e3  mov     ebx, r13d
0x1400020e6  jmp     loc_1400022FC
0x1400020eb  mov     rcx, rdi
0x1400020ee  call    GetUserProfilePaths
0x1400020f3  mov     ebx, eax
0x1400020f5  test    eax, eax
0x1400020f7  js      loc_1400022FF
0x1400020fd  lea     r14, [rdi+0B8h]
0x140002104  cmp     [r14], r13
0x140002107  jnz     short loc_140002134
0x140002109  lea     rcx, [rdi+58h]
0x14000210d  mov     rdx, r14
0x140002110  call    OpenProfileKey
0x140002115  mov     ebx, eax
0x140002117  test    eax, eax
0x140002119  js      loc_1400022FF
0x14000211f  mov     rcx, [r14]
0x140002122  mov     rdx, rdi
0x140002125  call    GetUserDesktopPath
0x14000212a  mov     ebx, eax
0x14000212c  test    eax, eax
0x14000212e  js      loc_1400022FF
0x140002134  mov     rax, 0FFFFF78000000014h
0x14000213e  mov     rax, [rax]
0x140002141  xchg    rax, [rdi+10h]
0x140002145  mov     [rsi], rdi
0x140002148  mov     ebx, r13d
0x14000214b  jmp     loc_1400022FF
0x140002150  test    r15b, r15b
0x140002153  jz      short loc_1400020E3
0x140002155  mov     rdx, r14
0x140002158  lea     rcx, [rbp+var_20]
0x14000215c  call    LuafvConvertSidToUnicodeString
0x140002161  mov     ebx, eax
0x140002163  test    eax, eax
0x140002165  js      loc_1400022FF
0x14000216b  mov     rcx, r14; Sid
0x14000216e  call    cs:__imp_RtlLengthSid
0x140002175  nop     dword ptr [rax+rax+00h]
0x14000217a  movzx   ebx, word ptr [rbp+var_20]
0x14000217e  mov     r8b, 0Fh
0x140002181  mov     r13d, eax
0x140002184  add     ebx, 0C0h
0x14000218a  mov     ecx, 1
0x14000218f  lea     r15d, [rax+1]
0x140002193  mov     eax, 0FFFFFFFEh
0x140002198  mov     edx, r15d
0x14000219b  and     edx, eax
0x14000219d  add     ebx, edx
0x14000219f  mov     edx, ebx
0x1400021a1  call    LuafvAllocatePool
0x1400021a6  mov     rdi, rax
0x1400021a9  test    rax, rax
0x1400021ac  jnz     short loc_1400021B8
0x1400021ae  mov     ebx, 0C000009Ah
0x1400021b3  jmp     loc_1400022FF
0x1400021b8  mov     r8d, ebx; Size
0x1400021bb  xor     edx, edx; Val
0x1400021bd  mov     rcx, rdi; void *
0x1400021c0  call    memset
0x1400021c5  mov     dword ptr [rdi+18h], 1
0x1400021cc  mov     rax, ds:0FFFFF78000000014h
0x1400021d6  mov     [rdi+10h], rax
0x1400021da  lea     rax, [rdi+20h]
0x1400021de  mov     [rax+8], rax
0x1400021e2  mov     [rax], rax
0x1400021e5  mov     rax, qword ptr [rbp+AuthenticationId.LowPart]
0x1400021e9  mov     [rdi+30h], rax
0x1400021ed  mov     rcx, [rbp+Object]; Object
0x1400021f1  test    rcx, rcx
0x1400021f4  jz      short loc_14000220F
0x1400021f6  mov     edx, 6661754Ch; Tag
0x1400021fb  call    cs:__imp_ObfReferenceObjectWithTag
0x140002202  nop     dword ptr [rax+rax+00h]
0x140002207  mov     rax, [rbp+Object]
0x14000220b  mov     [rdi+38h], rax
0x14000220f  lea     rbx, [rdi+0C0h]
0x140002216  mov     r8, r14; SourceSid
0x140002219  mov     rdx, rbx; DestinationSid
0x14000221c  mov     [rdi+50h], rbx
0x140002220  mov     ecx, r13d; DestinationSidLength
0x140002223  call    cs:__imp_RtlCopySid
0x14000222a  nop     dword ptr [rax+rax+00h]
0x14000222f  movzx   eax, word ptr [rbp+var_20]
0x140002233  mov     ecx, 0FFFFFFFEh
0x140002238  mov     [rdi+5Ah], ax
0x14000223c  and     rcx, r15
0x14000223f  movzx   eax, word ptr [rbp+var_20]
0x140002243  add     rcx, rbx; void *
0x140002246  mov     [rdi+60h], rcx
0x14000224a  mov     [rdi+58h], ax
0x14000224e  movzx   r8d, word ptr [rbp+var_20]; Size
0x140002253  mov     rdx, [rbp+Src]; Src
0x140002257  call    memmove
0x14000225c  xor     r13d, r13d
0x14000225f  test    r12b, r12b
0x140002262  jz      short loc_1400022A9
0x140002264  mov     rcx, rdi
0x140002267  call    GetUserProfilePaths
0x14000226c  mov     ebx, eax
0x14000226e  test    eax, eax
0x140002270  jns     short loc_14000227F
0x140002272  mov     rcx, rdi
0x140002275  call    LuafvFreePool
0x14000227a  jmp     loc_1400022FF
0x14000227f  lea     r14, [rdi+0B8h]
0x140002286  mov     rdx, r14
0x140002289  lea     rcx, [rdi+58h]
0x14000228d  call    OpenProfileKey
0x140002292  mov     ebx, eax
0x140002294  test    eax, eax
0x140002296  js      short loc_140002272
0x140002298  mov     rcx, [r14]
0x14000229b  mov     rdx, rdi
0x14000229e  call    GetUserDesktopPath
0x1400022a3  mov     ebx, eax
0x1400022a5  test    eax, eax
0x1400022a7  js      short loc_1400022FF
0x1400022a9  mov     rax, cs:UserList
0x1400022b0  lea     rcx, UserList
0x1400022b7  cmp     [rax+8], rcx
0x1400022bb  jz      short loc_1400022C4
0x1400022bd  mov     ecx, 3
0x1400022c2  int     29h; Win8: RtlFailFast(ecx)
0x1400022c4  mov     [rdi+8], rcx
0x1400022c8  lea     rcx, [rbp+AuthenticationId]
0x1400022cc  mov     [rdi], rax
0x1400022cf  mov     [rax+8], rdi
0x1400022d3  mov     rdx, [rbp+Object]
0x1400022d7  mov     cs:UserList, rdi
0x1400022de  mov     [rsi], rdi
0x1400022e1  call    cs:__imp_SeMarkLogonSessionForTerminationNotificationEx
0x1400022e8  nop     dword ptr [rax+rax+00h]
0x1400022ed  call    LuafvRunScavenger
0x1400022f2  jmp     loc_140002148
0x1400022f7  mov     ebx, 0C0000225h
0x1400022fc  mov     [rsi], r13
0x1400022ff  mov     rcx, [rbp+Src]; P
0x140002303  test    rcx, rcx
0x140002306  jz      short loc_140002316
0x140002308  xor     edx, edx; Tag
0x14000230a  call    cs:__imp_ExFreePoolWithTag
0x140002311  nop     dword ptr [rax+rax+00h]
0x140002316  mov     rcx, [rbp+TokenInformation]; P
0x14000231a  test    rcx, rcx
0x14000231d  jz      short loc_14000232D
0x14000231f  xor     edx, edx; Tag
0x140002321  call    cs:__imp_ExFreePoolWithTag
0x140002328  nop     dword ptr [rax+rax+00h]
0x14000232d  mov     eax, ebx
0x14000232f  add     rsp, 58h
0x140002333  pop     r15
0x140002335  pop     r14
0x140002337  pop     r13
0x140002339  pop     r12
0x14000233b  pop     rdi
0x14000233c  pop     rsi
0x14000233d  pop     rbx
0x14000233e  pop     rbp
0x14000233f  retn
```
