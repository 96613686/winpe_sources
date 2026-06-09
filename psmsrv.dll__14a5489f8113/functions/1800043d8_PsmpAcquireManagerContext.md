# PsmpAcquireManagerContext

- ea: `0x1800043d8`
- end: `0x180004635`
- name: `PsmpAcquireManagerContext`
- size: `605`
- prototype: `__int64 __fastcall(unsigned int, signed __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800039a8`

## callees

- `0x1800017b0`
- `0x1800043d8`
- `0x18000463c`
- `0x1800092b4`
- `0x18000b1d0`
- `0x18000b3d8`
- `0x18001b7e0`
- `0x18001c10c`
- `0x180022640`
- `0x180022c04`
- `0x180022cc4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180004588`
- `ntdll!RtlFreeHeap` at `0x180004588`
- `ntdll!NtClose` at `0x1800044a2`
- `ntdll!NtClose` at `0x1800044a2`
- `ntdll!NtOpenProcessTokenEx` at `0x180004433`
- `ntdll!NtOpenProcessTokenEx` at `0x180004433`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000453e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000453e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004592`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004592`

## pseudocode

```c
__int64 __fastcall PsmpAcquireManagerContext(unsigned int a1, signed __int64 a2)
{
  void *v4; // rcx
  volatile signed __int64 *v5; // rdi
  _QWORD *UserContext; // rsi
  NTSTATUS ClientInformation; // ebx
  __int64 ManagerContext; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rbp
  __int64 v13; // rcx
  _QWORD *v14; // rdx
  void *TokenHandle; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v16[80]; // [rsp+40h] [rbp-88h] BYREF

  memset_0(v16, 0, 0x44u);
  v4 = *(void **)(a2 + 16);
  v5 = 0;
  TokenHandle = 0;
  UserContext = 0;
  ClientInformation = NtOpenProcessTokenEx(v4, 8u, 0, &TokenHandle);
  if ( ClientInformation >= 0 )
  {
    ClientInformation = PsmpQueryClientInformation(*(HANDLE *)(a2 + 16), TokenHandle);
    if ( ClientInformation >= 0 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          &WPP_b5485372ff90327e3674091dc1985471_Traceguids,
          0,
          *(_DWORD *)(a2 + 24));
      ManagerContext = PsmpFindOrCreateManagerContext(a1, 0);
      v5 = (volatile signed __int64 *)ManagerContext;
      if ( ManagerContext )
      {
        UserContext = (_QWORD *)PsmpFindOrCreateUserContext(ManagerContext, 0, v16);
        if ( UserContext )
        {
          if ( _InterlockedCompareExchange64(v5 + 8, a2, 0) )
          {
            ClientInformation = -1073740008;
          }
          else
          {
            *(_QWORD *)(a2 + 56) = v5;
            v5 = 0;
            *(_QWORD *)(a2 + 40) = a2 + 32;
            UserContext = 0;
            *(_QWORD *)(a2 + 32) = a2 + 32;
            *(_BYTE *)(a2 + 48) = 0;
            ClientInformation = 0;
          }
        }
        else
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF__sid_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 0, ClientInformation);
          ClientInformation = -1073741670;
        }
      }
      else
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, 0, ClientInformation);
        ClientInformation = -1073741823;
      }
    }
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( UserContext )
  {
    v12 = UserContext[7];
    RtlAcquireSRWLockExclusive(v12 + 8);
    if ( (unsigned __int8)PsmpDereferenceObjectEx(UserContext, 0) )
    {
      v13 = UserContext[1];
      if ( *(_QWORD **)(v13 + 8) != UserContext + 1
        || (v14 = (_QWORD *)UserContext[2], (_QWORD *)*v14 != UserContext + 1) )
      {
        __fastfail(3u);
      }
      *v14 = v13;
      *(_QWORD *)(v13 + 8) = v14;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UserContext);
    }
    RtlReleaseSRWLockExclusive(v12 + 8);
  }
  if ( v5 )
    PsmpDereferenceManagerContext((PVOID)v5);
  return (unsigned int)ClientInformation;
}

```

## disassembly

```asm
0x1800043d8  mov     [rsp+arg_10], rbx
0x1800043dd  push    rbp
0x1800043de  push    rsi
0x1800043df  push    rdi
0x1800043e0  push    r14
0x1800043e2  push    r15
0x1800043e4  sub     rsp, 0A0h
0x1800043eb  mov     rax, cs:__security_cookie
0x1800043f2  xor     rax, rsp
0x1800043f5  mov     [rsp+0C8h+var_38], rax
0x1800043fd  mov     rbp, rdx
0x180004400  mov     dword ptr [rsp+0C8h+var_98], 0
0x180004408  xor     edx, edx; Val
0x18000440a  mov     r15d, ecx
0x18000440d  lea     rcx, [rsp+0C8h+var_88]; void *
0x180004412  lea     r8d, [rdx+44h]; Size
0x180004416  call    memset_0
0x18000441b  mov     rcx, [rbp+10h]; ProcessHandle
0x18000441f  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x180004424  xor     edi, edi
0x180004426  xor     r8d, r8d; HandleAttributes
0x180004429  mov     [rsp+0C8h+TokenHandle], rdi
0x18000442e  xor     esi, esi
0x180004430  lea     edx, [rdi+8]; DesiredAccess
0x180004433  call    cs:__imp_NtOpenProcessTokenEx
0x180004439  mov     ebx, eax
0x18000443b  test    eax, eax
0x18000443d  js      short loc_18000445D
0x18000443f  mov     rdx, [rsp+0C8h+TokenHandle]; TokenHandle
0x180004444  lea     r9, [rsp+0C8h+var_88]
0x180004449  mov     rcx, [rbp+10h]; ProcessHandle
0x18000444d  lea     r8, [rsp+0C8h+var_98]
0x180004452  call    PsmpQueryClientInformation
0x180004457  mov     ebx, eax
0x180004459  test    eax, eax
0x18000445b  jns     short loc_1800044AA
0x18000445d  mov     rcx, [rsp+0C8h+TokenHandle]; Handle
0x180004462  test    rcx, rcx
0x180004465  jnz     short loc_1800044A2
0x180004467  test    rsi, rsi
0x18000446a  jnz     loc_180004536
0x180004470  test    rdi, rdi
0x180004473  jnz     loc_180004628
0x180004479  mov     eax, ebx
0x18000447b  mov     rcx, [rsp+0C8h+var_38]
0x180004483  xor     rcx, rsp; StackCookie
0x180004486  call    __security_check_cookie
0x18000448b  mov     rbx, [rsp+0C8h+arg_10]
0x180004493  add     rsp, 0A0h
0x18000449a  pop     r15
0x18000449c  pop     r14
0x18000449e  pop     rdi
0x18000449f  pop     rsi
0x1800044a0  pop     rbp
0x1800044a1  retn
0x1800044a2  call    cs:__imp_NtClose
0x1800044a8  jmp     short loc_180004467
0x1800044aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044b1  mov     r14d, dword ptr [rsp+0C8h+var_98]
0x1800044b6  test    byte ptr [rcx+1Ch], 2
0x1800044ba  jnz     loc_18000459D
0x1800044c0  mov     edx, r14d
0x1800044c3  mov     ecx, r15d
0x1800044c6  call    PsmpFindOrCreateManagerContext
0x1800044cb  mov     rdi, rax
0x1800044ce  test    rax, rax
0x1800044d1  jnz     short loc_1800044EE
0x1800044d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044da  test    byte ptr [rcx+1Ch], 2
0x1800044de  jnz     loc_1800045CB
0x1800044e4  mov     ebx, 0C0000001h
0x1800044e9  jmp     loc_18000445D
0x1800044ee  lea     r8, [rsp+0C8h+var_88]
0x1800044f3  mov     edx, r14d
0x1800044f6  mov     rcx, rdi
0x1800044f9  call    PsmpFindOrCreateUserContext
0x1800044fe  mov     rsi, rax
0x180004501  test    rax, rax
0x180004504  jz      loc_1800045EA
0x18000450a  xor     eax, eax
0x18000450c  lock cmpxchg [rdi+40h], rbp
0x180004512  jnz     loc_18000461E
0x180004518  mov     [rbp+38h], rdi
0x18000451c  lea     rax, [rbp+20h]
0x180004520  xor     edi, edi
0x180004522  mov     [rax+8], rax
0x180004526  xor     esi, esi
0x180004528  mov     [rax], rax
0x18000452b  mov     byte ptr [rbp+30h], 0
0x18000452f  xor     ebx, ebx
0x180004531  jmp     loc_18000445D
0x180004536  mov     rbp, [rsi+38h]
0x18000453a  lea     rcx, [rbp+8]
0x18000453e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180004544  xor     edx, edx
0x180004546  mov     rcx, rsi
0x180004549  call    PsmpDereferenceObjectEx
0x18000454e  test    al, al
0x180004550  jz      short loc_18000458E
0x180004552  lea     rax, [rsi+8]
0x180004556  mov     rcx, [rax]
0x180004559  cmp     [rcx+8], rax
0x18000455d  jnz     short loc_180004568
0x18000455f  mov     rdx, [rax+8]
0x180004563  cmp     [rdx], rax
0x180004566  jz      short loc_18000456F
0x180004568  mov     ecx, 3
0x18000456d  int     29h; Win8: RtlFailFast(ecx)
0x18000456f  mov     [rdx], rcx
0x180004572  mov     r8, rsi; P
0x180004575  mov     [rcx+8], rdx
0x180004579  xor     edx, edx; Flags
0x18000457b  mov     rcx, gs:60h
0x180004584  mov     rcx, [rcx+30h]; HeapHandle
0x180004588  call    cs:__imp_RtlFreeHeap
0x18000458e  lea     rcx, [rbp+8]
0x180004592  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180004598  jmp     loc_180004470
0x18000459d  cmp     byte ptr [rcx+19h], 4
0x1800045a1  jb      loc_1800044C0
0x1800045a7  mov     eax, [rbp+18h]
0x1800045aa  lea     r8, WPP_b5485372ff90327e3674091dc1985471_Traceguids
0x1800045b1  mov     rcx, [rcx+10h]
0x1800045b5  mov     edx, 0Ah
0x1800045ba  mov     r9d, r14d
0x1800045bd  mov     dword ptr [rsp+0C8h+var_A8], eax
0x1800045c1  call    WPP_SF_Dd
0x1800045c6  jmp     loc_1800044C0
0x1800045cb  cmp     byte ptr [rcx+19h], 2
0x1800045cf  jb      loc_1800044E4
0x1800045d5  mov     rcx, [rcx+10h]
0x1800045d9  mov     r9d, r14d
0x1800045dc  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x1800045e0  call    WPP_SF_dd
0x1800045e5  jmp     loc_1800044E4
0x1800045ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045f1  test    byte ptr [rcx+1Ch], 2
0x1800045f5  jz      short loc_180004614
0x1800045f7  cmp     byte ptr [rcx+19h], 2
0x1800045fb  jb      short loc_180004614
0x1800045fd  mov     rcx, [rcx+10h]; LoggerHandle
0x180004601  lea     r9, [rsp+0C8h+var_88]
0x180004606  mov     dword ptr [rsp+0C8h+var_A0], ebx; char
0x18000460a  mov     dword ptr [rsp+0C8h+var_A8], r14d; char
0x18000460f  call    WPP_SF__sid_dd
0x180004614  mov     ebx, 0C000009Ah
0x180004619  jmp     loc_18000445D
0x18000461e  mov     ebx, 0C0000718h
0x180004623  jmp     loc_18000445D
0x180004628  mov     rcx, rdi; P
0x18000462b  call    PsmpDereferenceManagerContext
0x180004630  jmp     loc_180004479
```
