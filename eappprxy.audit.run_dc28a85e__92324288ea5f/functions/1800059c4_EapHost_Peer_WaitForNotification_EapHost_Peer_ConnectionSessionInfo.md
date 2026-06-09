# EapHost::Peer::WaitForNotification(EapHost::Peer::ConnectionSessionInfo *)

- ea: `0x1800059c4`
- end: `0x180005aa2`
- name: `?WaitForNotification@Peer@EapHost@@YAKPEAVConnectionSessionInfo@12@@Z`
- size: `222`
- prototype: `unsigned int __fastcall(EapHost::Peer *__hidden this, struct EapHost::Peer::ConnectionSessionInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006100`

## callees

- `0x1800059c4`
- `0x18000ae28`
- `0x18000b140`
- `0x18000c6e0`
- `0x18000d1dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180005a24`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180005a24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a38`

## pseudocode

```c
__int64 __fastcall EapHost::Peer::WaitForNotification(
        EapHost::Peer *this,
        struct EapHost::Peer::ConnectionSessionInfo *a2,
        __int64 a3)
{
  DWORD LastError; // esi
  __int64 v5; // rbp
  int v6; // r8d
  int v8; // [rsp+58h] [rbp+10h] BYREF

  LastError = 0;
  v8 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, a3, (char *)this + 20);
  v5 = _o__beginthreadex(0, 0, EapHost::Peer::WaitForNotificationProc, this, 0, &v8);
  if ( v5 )
  {
    ObjectHandle::Clear((EapHost::Peer *)((char *)this + 120));
    *((_QWORD *)this + 16) = v5;
  }
  else
  {
    LastError = GetLastError();
    EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(this);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, v6, LastError, (__int64)this + 20);
  return LastError;
}

```

## disassembly

```asm
0x1800059c4  mov     [rsp+arg_0], rbx
0x1800059c9  mov     [rsp+arg_10], rbp
0x1800059ce  push    rsi
0x1800059cf  push    rdi
0x1800059d0  push    r14
0x1800059d2  sub     rsp, 30h
0x1800059d6  xor     esi, esi
0x1800059d8  mov     rdi, rcx
0x1800059db  mov     [rsp+48h+arg_8], esi
0x1800059df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059e6  lea     r14, WPP_GLOBAL_Control
0x1800059ed  cmp     rcx, r14
0x1800059f0  jz      short loc_180005A08
0x1800059f2  test    byte ptr [rcx+1Ch], 4
0x1800059f6  jz      short loc_180005A08
0x1800059f8  mov     rcx, [rcx+10h]
0x1800059fc  lea     r9, [rdi+14h]
0x180005a00  lea     edx, [rsi+38h]
0x180005a03  call    WPP_SF_S
0x180005a08  lea     rax, [rsp+48h+arg_8]
0x180005a0d  mov     r9, rdi
0x180005a10  mov     [rsp+48h+var_20], rax
0x180005a15  lea     r8, EapHost__Peer__WaitForNotificationProc
0x180005a1c  xor     edx, edx
0x180005a1e  mov     dword ptr [rsp+48h+var_28], esi
0x180005a22  xor     ecx, ecx
0x180005a24  call    cs:__imp__o__beginthreadex
0x180005a2b  nop     dword ptr [rax+rax+00h]
0x180005a30  mov     rbp, rax
0x180005a33  test    rax, rax
0x180005a36  jnz     short loc_180005A50
0x180005a38  call    cs:__imp_GetLastError
0x180005a3f  nop     dword ptr [rax+rax+00h]
0x180005a44  mov     rcx, rdi; this
0x180005a47  mov     esi, eax
0x180005a49  call    ?ReduceRefCount@ConnectionSessionInfo@Peer@EapHost@@QEAAXXZ; EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(void)
0x180005a4e  jmp     short loc_180005A60
0x180005a50  lea     rcx, [rdi+78h]; this
0x180005a54  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x180005a59  mov     [rdi+80h], rbp
0x180005a60  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a67  cmp     rcx, r14
0x180005a6a  jz      short loc_180005A8C
0x180005a6c  test    byte ptr [rcx+1Ch], 4
0x180005a70  jz      short loc_180005A8C
0x180005a72  mov     rcx, [rcx+10h]
0x180005a76  lea     rax, [rdi+14h]
0x180005a7a  mov     edx, 39h ; '9'
0x180005a7f  mov     [rsp+48h+var_28], rax
0x180005a84  mov     r9d, esi
0x180005a87  call    WPP_SF_DS
0x180005a8c  mov     rbx, [rsp+48h+arg_0]
0x180005a91  mov     eax, esi
0x180005a93  mov     rbp, [rsp+48h+arg_10]
0x180005a98  add     rsp, 30h
0x180005a9c  pop     r14
0x180005a9e  pop     rdi
0x180005a9f  pop     rsi
0x180005aa0  retn
```
