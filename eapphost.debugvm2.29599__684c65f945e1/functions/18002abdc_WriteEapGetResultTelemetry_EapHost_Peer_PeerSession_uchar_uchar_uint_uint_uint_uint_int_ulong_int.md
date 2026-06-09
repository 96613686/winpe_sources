# WriteEapGetResultTelemetry(EapHost::Peer::PeerSession &,uchar,uchar,uint,uint,uint,uint,int,ulong,int)

- ea: `0x18002abdc`
- end: `0x18002ad73`
- name: `?WriteEapGetResultTelemetry@@YAXAEAVPeerSession@Peer@EapHost@@EEIIIIHKH@Z`
- size: `407`
- prototype: `void __fastcall(struct EapHost::Peer::PeerSession *, unsigned __int8, unsigned __int8, unsigned int, unsigned int, unsigned int, unsigned int, int, unsigned int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180025b18`

## callees

- `0x180002a90`
- `0x180024224`
- `0x18002474c`
- `0x180024898`
- `0x180024910`
- `0x180029d5c`
- `0x18002abdc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002ac25`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002ac25`

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
0x18002abdc  test    rcx, rcx
0x18002abdf  jz      locret_18002AD72
0x18002abe5  mov     [rsp+arg_18], rbx
0x18002abea  push    rbp
0x18002abeb  push    rsi
0x18002abec  push    rdi
0x18002abed  push    r12
0x18002abef  push    r13
0x18002abf1  push    r14
0x18002abf3  push    r15
0x18002abf5  sub     rsp, 0A0h
0x18002abfc  mov     rax, cs:__security_cookie
0x18002ac03  xor     rax, rsp
0x18002ac06  mov     [rsp+0D8h+var_48], rax
0x18002ac0e  mov     ebx, [rcx+16Ch]
0x18002ac14  mov     r13, rcx
0x18002ac17  mov     [rsp+0D8h+var_64], r9d
0x18002ac1c  mov     [rsp+0D8h+var_67], r8b
0x18002ac21  mov     [rsp+0D8h+var_68], dl
0x18002ac25  call    cs:__imp_GetTickCount
0x18002ac2b  mov     r15d, [rsp+0D8h+arg_48]
0x18002ac33  lea     rdi, [r13+0F4h]
0x18002ac3a  mov     r14d, [rsp+0D8h+arg_40]
0x18002ac42  mov     r12d, eax
0x18002ac45  mov     ebp, [rsp+0D8h+arg_30]
0x18002ac4c  xor     ecx, ecx
0x18002ac4e  mov     esi, [rsp+0D8h+arg_28]
0x18002ac55  sub     r12d, ebx
0x18002ac58  mov     r9b, [r13+84h]; unsigned __int8
0x18002ac5f  cmp     eax, ebx
0x18002ac61  mov     eax, [rsp+0D8h+arg_38]
0x18002ac68  mov     ebx, [rsp+0D8h+arg_20]
0x18002ac6f  cmovb   r12d, ecx
0x18002ac73  mov     r8b, [r13+10Ch]; unsigned __int8
0x18002ac7a  mov     rcx, rdi; struct _GUID *
0x18002ac7d  mov     edx, [r13+38h]; unsigned int
0x18002ac81  mov     [rsp+0D8h+var_70], r15d; int
0x18002ac86  mov     [rsp+0D8h+var_78], r14d; unsigned int
0x18002ac8b  mov     [rsp+0D8h+var_80], eax; int
0x18002ac8f  mov     eax, [rsp+0D8h+var_64]
0x18002ac93  mov     [rsp+0D8h+var_88], r12d; unsigned int
0x18002ac98  mov     [rsp+0D8h+var_90], ebp; unsigned int
0x18002ac9c  mov     [rsp+0D8h+var_98], esi; unsigned int
0x18002aca0  mov     [rsp+0D8h+var_A0], ebx; unsigned int
0x18002aca4  mov     [rsp+0D8h+var_A8], eax; unsigned int
0x18002aca8  mov     al, [rsp+0D8h+var_67]
0x18002acac  mov     byte ptr [rsp+0D8h+var_B0], al; char
0x18002acb0  mov     al, [rsp+0D8h+var_68]
0x18002acb4  mov     [rsp+0D8h+var_B8], al; char
0x18002acb8  call    ?EapGetResult@EapHostTelemetry@@SAXAEBU_GUID@@IEEEEIIIIIHIH@Z; EapHostTelemetry::EapGetResult(_GUID const &,uint,uchar,uchar,uchar,uchar,uint,uint,uint,uint,uint,int,uint,int)
0x18002acbd  movups  xmm0, xmmword ptr [rdi]
0x18002acc0  mov     edx, [rsp+0D8h+var_64]; unsigned int
0x18002acc4  mov     ecx, ebx; unsigned int
0x18002acc6  mov     [rsp+0D8h+var_60], 11h
0x18002acce  movdqu  [rsp+0D8h+var_5C], xmm0
0x18002acd4  mov     [rsp+0D8h+var_4C], 1
0x18002acdf  call    ?EapMethodIsFirstParty@@YA_NKK@Z; EapMethodIsFirstParty(ulong,ulong)
0x18002ace4  movzx   ecx, [rsp+0D8h+var_68]; unsigned int
0x18002ace9  movzx   r11d, al
0x18002aced  call    ?EapMethodAsString@@YAPEB_WK@Z; EapMethodAsString(ulong)
0x18002acf2  mov     ecx, ebp; unsigned int
0x18002acf4  mov     edx, esi; unsigned int
0x18002acf6  mov     r10, rax
0x18002acf9  call    ?EapMethodIsFirstParty@@YA_NKK@Z; EapMethodIsFirstParty(ulong,ulong)
0x18002acfe  movzx   ecx, [rsp+0D8h+var_67]; unsigned int
0x18002ad03  movzx   edx, al
0x18002ad06  call    ?EapMethodAsString@@YAPEB_WK@Z; EapMethodAsString(ulong)
0x18002ad0b  mov     ecx, [r13+10Ch]
0x18002ad12  mov     r9, rax
0x18002ad15  call    ?SessionStateAsString@@YAPEB_WW4SessionStateType@SessionStateValue@Peer@EapHost@@@Z; SessionStateAsString(EapHost::Peer::SessionStateValue::SessionStateType)
0x18002ad1a  mov     [rsp+0D8h+var_90], r15d; int
0x18002ad1f  lea     rcx, [rsp+0D8h+var_60]; struct NetworkingTriageScenario::GetConnected::RequiredFields *
0x18002ad24  mov     [rsp+0D8h+var_98], r14d; unsigned int
0x18002ad29  mov     r8, rax; wchar_t *
0x18002ad2c  mov     [rsp+0D8h+var_A0], r12d; unsigned int
0x18002ad31  mov     [rsp+0D8h+var_A8], r11d; int
0x18002ad36  mov     [rsp+0D8h+var_B0], r10; wchar_t *
0x18002ad3b  mov     dword ptr [rsp+0D8h+var_B8], edx; int
0x18002ad3f  mov     edx, [r13+38h]; unsigned int
0x18002ad43  call    ?EAPHostResultEvent@GetConnected@NetworkingTriageScenario@@SAXAEBURequiredFields@12@IPEB_W1H1HIIH@Z; NetworkingTriageScenario::GetConnected::EAPHostResultEvent(NetworkingTriageScenario::GetConnected::RequiredFields const &,uint,wchar_t const *,wchar_t const *,int,wchar_t const *,int,uint,uint,int)
0x18002ad48  mov     rcx, [rsp+0D8h+var_48]
0x18002ad50  xor     rcx, rsp; StackCookie
0x18002ad53  call    __security_check_cookie
0x18002ad58  mov     rbx, [rsp+0D8h+arg_18]
0x18002ad60  add     rsp, 0A0h
0x18002ad67  pop     r15
0x18002ad69  pop     r14
0x18002ad6b  pop     r13
0x18002ad6d  pop     r12
0x18002ad6f  pop     rdi
0x18002ad70  pop     rsi
0x18002ad71  pop     rbp
0x18002ad72  retn
```
