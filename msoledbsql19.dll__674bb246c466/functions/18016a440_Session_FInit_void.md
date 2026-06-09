# Session::FInit(void)

- ea: `0x18016a440`
- end: `0x18016a6ce`
- name: `?FInit@Session@@UEAAKXZ`
- size: `654`
- prototype: `unsigned int __fastcall(Session *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x180151f80`
- `0x180153190`
- `0x18015a6f0`
- `0x18015a880`
- `0x18016a440`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18016a50b`
- `KERNEL32!GetLastError` at `0x18016a5b4`
- `KERNEL32!GetLastError` at `0x18016a50b`
- `KERNEL32!GetLastError` at `0x18016a5b4`
- `KERNEL32!CreateEventW` at `0x18016a4f5`
- `KERNEL32!CreateEventW` at `0x18016a4f5`
- `KERNEL32!CloseHandle` at `0x18016a59c`
- `KERNEL32!CloseHandle` at `0x18016a59c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Session::FInit(struct CCriticalSectionNT_SNI **this)
{
  DWORD v2; // esi
  DWORD LastError; // ebx
  __int64 v4; // rcx
  struct CCriticalSectionNT_SNI *v5; // rbx
  struct CCriticalSectionNT_SNI *EventW; // rax
  __int64 v7; // r9
  struct CCriticalSectionNT_SNI *v8; // rcx
  struct CCriticalSectionNT_SNI *v9; // rcx
  BOOL v10; // eax
  struct CCriticalSectionNT_SNI *v12; // rbx
  __int64 v13; // [rsp+40h] [rbp-28h] BYREF
  __int64 v14; // [rsp+48h] [rbp-20h] BYREF

  v14 = -1;
  v2 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266AB8[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_180248060[0])(
      bidID,
      0,
      0,
      &v14,
      off_180266AB8[0],
      0);
  LastError = CCriticalSectionNT_SNI::Initialize(this + 7);
  if ( LastError )
    goto LABEL_14;
  v4 = *((_QWORD *)this[7] + 2);
  v5 = (struct CCriticalSectionNT_SNI *)(v4 + 32);
  if ( !v4 )
    v5 = 0;
  EventW = (struct CCriticalSectionNT_SNI *)CreateEventW(0, 0, 0, 0);
  this[24] = EventW;
  if ( EventW )
  {
    this[23] = v5;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( (bidGblFlags & 2) != 0 && off_1802649D8[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(off_180261690[0], 787456, off_1802649D8[0], 2);
      }
      SNISetLastError(2, LastError, 50100);
LABEL_14:
      v8 = this[7];
      if ( v8 )
      {
        (**(void (__fastcall ***)(struct CCriticalSectionNT_SNI *, __int64))v8)(v8, 1);
        this[7] = 0;
      }
      v9 = this[24];
      if ( v9 )
      {
        v10 = CloseHandle(v9);
        this[24] = 0;
        this[23] = 0;
        if ( !v10 )
          GetLastError();
      }
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802649E8[0] )
        bidTraceW(off_1802616A0[0], 812032, off_1802649E8[0], LastError);
      v2 = LastError;
      goto LABEL_23;
    }
  }
  v12 = this[6];
  v13 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266B40[0] )
    bidScopeEnterW(&v13, off_180266B40[0], *((unsigned int *)v12 + 11), v7);
  SNI_Conn::AddRef(*((_QWORD *)v12 + 4), 1);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v13);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802649E0[0] )
    bidTraceW(off_180261698[0], 794624, off_1802649E0[0], 0);
LABEL_23:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v14);
  return v2;
}

```

## disassembly

```asm
0x18016a440  mov     r11, rsp
0x18016a443  mov     [r11+10h], rbx
0x18016a447  mov     [r11+18h], rsi
0x18016a44b  mov     [r11+20h], rdi
0x18016a44f  push    r14
0x18016a451  sub     rsp, 60h
0x18016a455  mov     rax, cs:__security_cookie
0x18016a45c  xor     rax, rsp
0x18016a45f  mov     [rsp+68h+var_18], rax
0x18016a464  mov     rdi, rcx
0x18016a467  mov     qword ptr [r11-20h], 0FFFFFFFFFFFFFFFFh
0x18016a46f  mov     eax, cs:_bidGblFlags
0x18016a475  and     eax, 20004h
0x18016a47a  xor     esi, esi
0x18016a47c  cmp     eax, 20004h
0x18016a481  jnz     short loc_18016A4C5
0x18016a483  mov     rax, cs:off_180266AB8; "<Session::FInit|API|SNI> \n"
0x18016a48a  test    rax, rax
0x18016a48d  jz      short loc_18016A4C5
0x18016a48f  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18016a497  jz      short loc_18016A4C5
0x18016a499  mov     rax, cs:off_180248060
0x18016a4a0  mov     [r11-40h], rsi
0x18016a4a4  mov     rcx, cs:off_180266AB8; "<Session::FInit|API|SNI> \n"
0x18016a4ab  mov     [r11-48h], rcx
0x18016a4af  lea     r9, [r11-20h]
0x18016a4b3  xor     r8d, r8d
0x18016a4b6  xor     edx, edx
0x18016a4b8  mov     rcx, cs:_bidID
0x18016a4bf  call    cs:__guard_dispatch_icall_fptr
0x18016a4c5  lea     rcx, [rdi+38h]; struct CCriticalSectionNT_SNI **
0x18016a4c9  call    ?Initialize@CCriticalSectionNT_SNI@@SAKPEAPEAV1@@Z; CCriticalSectionNT_SNI::Initialize(CCriticalSectionNT_SNI * *)
0x18016a4ce  mov     ebx, eax
0x18016a4d0  test    eax, eax
0x18016a4d2  jnz     loc_18016A572
0x18016a4d8  mov     rax, [rdi+38h]
0x18016a4dc  mov     rcx, [rax+10h]
0x18016a4e0  lea     rbx, [rcx+20h]
0x18016a4e4  test    rcx, rcx
0x18016a4e7  cmovz   rbx, rsi
0x18016a4eb  xor     r9d, r9d; lpName
0x18016a4ee  xor     r8d, r8d; bInitialState
0x18016a4f1  xor     edx, edx; bManualReset
0x18016a4f3  xor     ecx, ecx; lpEventAttributes
0x18016a4f5  call    cs:__imp_CreateEventW
0x18016a4fb  mov     [rdi+0C0h], rax
0x18016a502  test    rax, rax
0x18016a505  jnz     loc_18016A626
0x18016a50b  call    cs:__imp_GetLastError
0x18016a511  mov     ebx, eax
0x18016a513  test    eax, eax
0x18016a515  jz      loc_18016A62D
0x18016a51b  test    byte ptr cs:_bidGblFlags, 2
0x18016a522  jz      short loc_18016A560
0x18016a524  mov     rax, cs:off_1802649D8; "<Session::FInit|ERR|SNI> ProviderNum: %"...
0x18016a52b  test    rax, rax
0x18016a52e  jz      short loc_18016A560
0x18016a530  mov     ecx, 0C3B4h; unsigned int
0x18016a535  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18016a53a  mov     [rsp+68h+var_40], ebx
0x18016a53e  mov     [rsp+68h+var_48], eax
0x18016a542  mov     r9d, 2
0x18016a548  mov     r8, cs:off_1802649D8; "<Session::FInit|ERR|SNI> ProviderNum: %"...
0x18016a54f  mov     edx, 0C0400h
0x18016a554  mov     rcx, cs:off_180261690; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18016a55b  call    _bidTraceW
0x18016a560  mov     r8d, 0C3B4h
0x18016a566  mov     edx, ebx
0x18016a568  mov     ecx, 2
0x18016a56d  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18016a572  mov     rcx, [rdi+38h]
0x18016a576  test    rcx, rcx
0x18016a579  jz      short loc_18016A590
0x18016a57b  mov     rax, [rcx]
0x18016a57e  mov     edx, 1
0x18016a583  mov     rax, [rax]
0x18016a586  call    cs:__guard_dispatch_icall_fptr
0x18016a58c  mov     [rdi+38h], rsi
0x18016a590  mov     rcx, [rdi+0C0h]; hObject
0x18016a597  test    rcx, rcx
0x18016a59a  jz      short loc_18016A5BA
0x18016a59c  call    cs:__imp_CloseHandle
0x18016a5a2  mov     [rdi+0C0h], rsi
0x18016a5a9  mov     [rdi+0B8h], rsi
0x18016a5b0  test    eax, eax
0x18016a5b2  jnz     short loc_18016A5BA
0x18016a5b4  call    cs:__imp_GetLastError
0x18016a5ba  mov     eax, cs:_bidGblFlags
0x18016a5c0  and     eax, 20002h
0x18016a5c5  cmp     eax, 20002h
0x18016a5ca  jnz     short loc_18016A5F3
0x18016a5cc  mov     rax, cs:off_1802649E8; "<Session::FInit|RET|SNI> %d{WINERR}\n"
0x18016a5d3  test    rax, rax
0x18016a5d6  jz      short loc_18016A5F3
0x18016a5d8  mov     r9d, ebx
0x18016a5db  mov     r8, cs:off_1802649E8; "<Session::FInit|RET|SNI> %d{WINERR}\n"
0x18016a5e2  mov     edx, 0C6400h
0x18016a5e7  mov     rcx, cs:off_1802616A0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18016a5ee  call    _bidTraceW
0x18016a5f3  mov     esi, ebx
0x18016a5f5  lea     rcx, [rsp+68h+var_20]; this
0x18016a5fa  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18016a5ff  nop
0x18016a600  mov     eax, esi
0x18016a602  mov     rcx, [rsp+68h+var_18]
0x18016a607  xor     rcx, rsp; StackCookie
0x18016a60a  call    __security_check_cookie
0x18016a60f  lea     r11, [rsp+68h+var_8]
0x18016a614  mov     rbx, [r11+18h]
0x18016a618  mov     rsi, [r11+20h]
0x18016a61c  mov     rdi, [r11+28h]
0x18016a620  mov     rsp, r11
0x18016a623  pop     r14
0x18016a625  retn
0x18016a626  mov     [rdi+0B8h], rbx
0x18016a62d  mov     rbx, [rdi+30h]
0x18016a631  mov     [rsp+68h+var_28], 0FFFFFFFFFFFFFFFFh
0x18016a63a  mov     eax, cs:_bidGblFlags
0x18016a640  and     eax, 20004h
0x18016a645  cmp     eax, 20004h
0x18016a64a  jnz     short loc_18016A66D
0x18016a64c  mov     rax, cs:off_180266B40; "<Smux::AddSessionRef|API|SNI> %u#\n"
0x18016a653  test    rax, rax
0x18016a656  jz      short loc_18016A66D
0x18016a658  mov     r8d, [rbx+2Ch]
0x18016a65c  mov     rdx, cs:off_180266B40; "<Smux::AddSessionRef|API|SNI> %u#\n"
0x18016a663  lea     rcx, [rsp+68h+var_28]
0x18016a668  call    _bidScopeEnterW
0x18016a66d  mov     edx, 1
0x18016a672  mov     rcx, [rbx+20h]
0x18016a676  call    ?AddRef@SNI_Conn@@QEAAJW4SNI_REF@@@Z; SNI_Conn::AddRef(SNI_REF)
0x18016a67b  nop
0x18016a67c  lea     rcx, [rsp+68h+var_28]; this
0x18016a681  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18016a686  nop
0x18016a687  mov     eax, cs:_bidGblFlags
0x18016a68d  and     eax, 20002h
0x18016a692  cmp     eax, 20002h
0x18016a697  jnz     loc_18016A5F5
0x18016a69d  mov     rax, cs:off_1802649E0; "<Session::FInit|RET|SNI> %d{WINERR}\n"
0x18016a6a4  test    rax, rax
0x18016a6a7  jz      loc_18016A5F5
0x18016a6ad  xor     r9d, r9d
0x18016a6b0  mov     r8, cs:off_1802649E0; "<Session::FInit|RET|SNI> %d{WINERR}\n"
0x18016a6b7  mov     edx, 0C2000h
0x18016a6bc  mov     rcx, cs:off_180261698; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18016a6c3  call    _bidTraceW
0x18016a6c8  jmp     loc_18016A5F5
```
