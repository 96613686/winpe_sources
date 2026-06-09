# WriteEapGetResultTelemetry(EapHost::Peer::PeerSession &,uchar,uchar,uint,uint,uint,uint,int,ulong,int)

- ea: `0x18002ba10`
- end: `0x18002bbae`
- name: `?WriteEapGetResultTelemetry@@YAXAEAVPeerSession@Peer@EapHost@@EEIIIIHKH@Z`
- size: `414`
- prototype: `void __fastcall(struct EapHost::Peer::PeerSession *, unsigned __int8, unsigned __int8, unsigned int, unsigned int, unsigned int, unsigned int, int, unsigned int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180026850`

## callees

- `0x180002af0`
- `0x180024efc`
- `0x180025428`
- `0x180025574`
- `0x1800255f4`
- `0x18002aba4`
- `0x18002ba10`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002ba59`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002ba59`

## pseudocode

```c
void __fastcall WriteEapGetResultTelemetry(
        struct EapHost::Peer::PeerSession *a1,
        unsigned __int8 a2,
        unsigned __int8 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        int a8,
        unsigned int a9,
        int a10)
{
  unsigned int v10; // ebx
  DWORD TickCount; // eax
  unsigned int v13; // r12d
  __int128 v14; // xmm0
  const wchar_t *v15; // rax
  int v16; // edx
  const wchar_t *v17; // r9
  const wchar_t *v18; // r10
  int v19; // r11d
  int v23; // [rsp+78h] [rbp-60h] BYREF
  __int128 v24; // [rsp+7Ch] [rbp-5Ch]
  int v25; // [rsp+8Ch] [rbp-4Ch]

  if ( a1 )
  {
    v10 = *((_DWORD *)a1 + 91);
    TickCount = GetTickCount();
    v13 = TickCount - v10;
    if ( TickCount < v10 )
      v13 = 0;
    EapHostTelemetry::EapGetResult(
      (const struct _GUID *)((char *)a1 + 244),
      *((_DWORD *)a1 + 14),
      *((_BYTE *)a1 + 268),
      *((_BYTE *)a1 + 132),
      a2,
      a3,
      a4,
      a5,
      a6,
      a7,
      v13,
      a8,
      a9,
      a10);
    v14 = *(_OWORD *)((char *)a1 + 244);
    v23 = 17;
    v24 = v14;
    v25 = 1;
    EapMethodIsFirstParty(a5, a4);
    EapMethodAsString(a2);
    EapMethodIsFirstParty(a7, a6);
    EapMethodAsString(a3);
    v15 = (const wchar_t *)SessionStateAsString(*((unsigned int *)a1 + 67));
    NetworkingTriageScenario::GetConnected::EAPHostResultEvent(
      (const struct NetworkingTriageScenario::GetConnected::RequiredFields *)&v23,
      *((_DWORD *)a1 + 14),
      v15,
      v17,
      v16,
      v18,
      v19,
      v13,
      a9,
      a10);
  }
}

```

## disassembly

```asm
0x18002ba10  test    rcx, rcx
0x18002ba13  jz      locret_18002BBAC
0x18002ba19  mov     [rsp+arg_18], rbx
0x18002ba1e  push    rbp
0x18002ba1f  push    rsi
0x18002ba20  push    rdi
0x18002ba21  push    r12
0x18002ba23  push    r13
0x18002ba25  push    r14
0x18002ba27  push    r15
0x18002ba29  sub     rsp, 0A0h
0x18002ba30  mov     rax, cs:__security_cookie
0x18002ba37  xor     rax, rsp
0x18002ba3a  mov     [rsp+0D8h+var_48], rax
0x18002ba42  mov     ebx, [rcx+16Ch]
0x18002ba48  mov     r13, rcx
0x18002ba4b  mov     [rsp+0D8h+var_64], r9d
0x18002ba50  mov     [rsp+0D8h+var_67], r8b
0x18002ba55  mov     [rsp+0D8h+var_68], dl
0x18002ba59  call    cs:__imp_GetTickCount
0x18002ba60  nop     dword ptr [rax+rax+00h]
0x18002ba65  mov     r15d, [rsp+0D8h+arg_48]
0x18002ba6d  lea     rdi, [r13+0F4h]
0x18002ba74  mov     r14d, [rsp+0D8h+arg_40]
0x18002ba7c  mov     r12d, eax
0x18002ba7f  mov     ebp, [rsp+0D8h+arg_30]
0x18002ba86  xor     ecx, ecx
0x18002ba88  mov     esi, [rsp+0D8h+arg_28]
0x18002ba8f  sub     r12d, ebx
0x18002ba92  mov     r9b, [r13+84h]; unsigned __int8
0x18002ba99  cmp     eax, ebx
0x18002ba9b  mov     eax, [rsp+0D8h+arg_38]
0x18002baa2  mov     ebx, [rsp+0D8h+arg_20]
0x18002baa9  cmovb   r12d, ecx
0x18002baad  mov     r8b, [r13+10Ch]; unsigned __int8
0x18002bab4  mov     rcx, rdi; struct _GUID *
0x18002bab7  mov     edx, [r13+38h]; unsigned int
0x18002babb  mov     [rsp+0D8h+var_70], r15d; int
0x18002bac0  mov     [rsp+0D8h+var_78], r14d; unsigned int
0x18002bac5  mov     [rsp+0D8h+var_80], eax; int
0x18002bac9  mov     eax, [rsp+0D8h+var_64]
0x18002bacd  mov     [rsp+0D8h+var_88], r12d; unsigned int
0x18002bad2  mov     [rsp+0D8h+var_90], ebp; unsigned int
0x18002bad6  mov     [rsp+0D8h+var_98], esi; unsigned int
0x18002bada  mov     [rsp+0D8h+var_A0], ebx; unsigned int
0x18002bade  mov     [rsp+0D8h+var_A8], eax; unsigned int
0x18002bae2  mov     al, [rsp+0D8h+var_67]
0x18002bae6  mov     byte ptr [rsp+0D8h+var_B0], al; char
0x18002baea  mov     al, [rsp+0D8h+var_68]
0x18002baee  mov     [rsp+0D8h+var_B8], al; char
0x18002baf2  call    ?EapGetResult@EapHostTelemetry@@SAXAEBU_GUID@@IEEEEIIIIIHIH@Z; EapHostTelemetry::EapGetResult(_GUID const &,uint,uchar,uchar,uchar,uchar,uint,uint,uint,uint,uint,int,uint,int)
0x18002baf7  movups  xmm0, xmmword ptr [rdi]
0x18002bafa  mov     edx, [rsp+0D8h+var_64]; unsigned int
0x18002bafe  mov     ecx, ebx; unsigned int
0x18002bb00  mov     [rsp+0D8h+var_60], 11h
0x18002bb08  movdqu  [rsp+0D8h+var_5C], xmm0
0x18002bb0e  mov     [rsp+0D8h+var_4C], 1
0x18002bb19  call    ?EapMethodIsFirstParty@@YA_NKK@Z; EapMethodIsFirstParty(ulong,ulong)
0x18002bb1e  movzx   ecx, [rsp+0D8h+var_68]; unsigned int
0x18002bb23  movzx   r11d, al
0x18002bb27  call    ?EapMethodAsString@@YAPEB_WK@Z; EapMethodAsString(ulong)
0x18002bb2c  mov     ecx, ebp; unsigned int
0x18002bb2e  mov     edx, esi; unsigned int
0x18002bb30  mov     r10, rax
0x18002bb33  call    ?EapMethodIsFirstParty@@YA_NKK@Z; EapMethodIsFirstParty(ulong,ulong)
0x18002bb38  movzx   ecx, [rsp+0D8h+var_67]; unsigned int
0x18002bb3d  movzx   edx, al
0x18002bb40  call    ?EapMethodAsString@@YAPEB_WK@Z; EapMethodAsString(ulong)
0x18002bb45  mov     ecx, [r13+10Ch]
0x18002bb4c  mov     r9, rax
0x18002bb4f  call    ?SessionStateAsString@@YAPEB_WW4SessionStateType@SessionStateValue@Peer@EapHost@@@Z; SessionStateAsString(EapHost::Peer::SessionStateValue::SessionStateType)
0x18002bb54  mov     [rsp+0D8h+var_90], r15d; int
0x18002bb59  lea     rcx, [rsp+0D8h+var_60]; struct NetworkingTriageScenario::GetConnected::RequiredFields *
0x18002bb5e  mov     [rsp+0D8h+var_98], r14d; unsigned int
0x18002bb63  mov     r8, rax; wchar_t *
0x18002bb66  mov     [rsp+0D8h+var_A0], r12d; unsigned int
0x18002bb6b  mov     [rsp+0D8h+var_A8], r11d; int
0x18002bb70  mov     [rsp+0D8h+var_B0], r10; wchar_t *
0x18002bb75  mov     dword ptr [rsp+0D8h+var_B8], edx; int
0x18002bb79  mov     edx, [r13+38h]; unsigned int
0x18002bb7d  call    ?EAPHostResultEvent@GetConnected@NetworkingTriageScenario@@SAXAEBURequiredFields@12@IPEB_W1H1HIIH@Z; NetworkingTriageScenario::GetConnected::EAPHostResultEvent(NetworkingTriageScenario::GetConnected::RequiredFields const &,uint,wchar_t const *,wchar_t const *,int,wchar_t const *,int,uint,uint,int)
0x18002bb82  mov     rcx, [rsp+0D8h+var_48]
0x18002bb8a  xor     rcx, rsp; StackCookie
0x18002bb8d  call    __security_check_cookie
0x18002bb92  mov     rbx, [rsp+0D8h+arg_18]
0x18002bb9a  add     rsp, 0A0h
0x18002bba1  pop     r15
0x18002bba3  pop     r14
0x18002bba5  pop     r13
0x18002bba7  pop     r12
0x18002bba9  pop     rdi
0x18002bbaa  pop     rsi
0x18002bbab  pop     rbp
0x18002bbac  retn
```
