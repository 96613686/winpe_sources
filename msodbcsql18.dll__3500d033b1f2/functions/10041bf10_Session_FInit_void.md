# Session::FInit(void)

- ea: `0x10041bf10`
- end: `0x10041c11c`
- name: `?FInit@Session@@UEAAKXZ`
- size: `524`
- prototype: `unsigned int __fastcall(Session *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x100413d10`
- `0x10041ab9c`
- `0x10041bf10`
- `0x10043a7c4`
- `0x10043a930`
- `0x100545d84`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x10041bfc1`
- `KERNEL32!CreateEventW` at `0x10041bfc1`
- `KERNEL32!GetLastError` at `0x10041bfd7`
- `KERNEL32!GetLastError` at `0x10041c079`
- `KERNEL32!GetLastError` at `0x10041bfd7`
- `KERNEL32!GetLastError` at `0x10041c079`
- `KERNEL32!CloseHandle` at `0x10041c061`
- `KERNEL32!CloseHandle` at `0x10041c061`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Session::FInit(struct CCriticalSectionNT_SNI **this)
{
  DWORD v2; // ebx
  _QWORD *v3; // r14
  DWORD LastError; // edi
  __int64 v5; // rdi
  struct CCriticalSectionNT_SNI *EventW; // rax
  struct CCriticalSectionNT_SNI *v7; // rcx
  BOOL v8; // eax
  __int64 v10; // [rsp+60h] [rbp+8h] BYREF

  v10 = -1;
  v2 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7878[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *, wchar_t *, _QWORD))off_1005D39F0)(
      bidID,
      0,
      0,
      &v10,
      off_1005E7878[0],
      0);
  v3 = this + 7;
  LastError = CCriticalSectionNT_SNI::Initialize(this + 7);
  if ( LastError )
    goto LABEL_12;
  v5 = (*(_QWORD *)(*v3 + 16LL) + 32LL) & -(__int64)(*(_QWORD *)(*v3 + 16LL) != 0);
  EventW = (struct CCriticalSectionNT_SNI *)CreateEventW(0, 0, 0, 0);
  this[24] = EventW;
  if ( EventW )
  {
    this[23] = (struct CCriticalSectionNT_SNI *)v5;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E48F8[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(0, 788480, off_1005E48F8[0], 2);
      }
      SNISetLastError(2, LastError, 50100);
LABEL_12:
      if ( *v3 )
      {
        (**(void (__fastcall ***)(_QWORD, __int64))*v3)(*v3, 1);
        *v3 = 0;
      }
      v7 = this[24];
      if ( v7 )
      {
        v8 = CloseHandle(v7);
        this[24] = 0;
        this[23] = 0;
        if ( !v8 )
          GetLastError();
      }
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4908[0] )
        bidTraceW(0, 813056, off_1005E4908[0], LastError);
      v2 = LastError;
      goto LABEL_21;
    }
  }
  Smux::AddSessionRef(this[6]);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4900[0] )
    bidTraceW(0, 795648, off_1005E4900[0], 0);
LABEL_21:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v10);
  return v2;
}

```

## disassembly

```asm
0x10041bf10  mov     r11, rsp
0x10041bf13  push    r14
0x10041bf15  sub     rsp, 50h
0x10041bf19  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x10041bf21  mov     [r11+10h], rbx
0x10041bf25  mov     [r11+18h], rsi
0x10041bf29  mov     [r11+20h], rdi
0x10041bf2d  mov     rsi, rcx
0x10041bf30  or      qword ptr [r11+8], 0FFFFFFFFFFFFFFFFh
0x10041bf35  mov     eax, cs:_bidGblFlags
0x10041bf3b  mov     ecx, 20004h
0x10041bf40  and     eax, ecx
0x10041bf42  xor     ebx, ebx
0x10041bf44  cmp     eax, ecx
0x10041bf46  jnz     short loc_10041BF8D
0x10041bf48  mov     rax, cs:off_1005E7878; "<Session::FInit|API|SNI> \n"
0x10041bf4f  test    rax, rax
0x10041bf52  jz      short loc_10041BF8D
0x10041bf54  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10041bf5c  jz      short loc_10041BF8D
0x10041bf5e  mov     r10, cs:off_1005D39F0
0x10041bf65  mov     [r11-30h], rbx
0x10041bf69  mov     rax, cs:off_1005E7878; "<Session::FInit|API|SNI> \n"
0x10041bf70  mov     [r11-38h], rax
0x10041bf74  lea     r9, [r11+8]
0x10041bf78  xor     r8d, r8d
0x10041bf7b  xor     edx, edx
0x10041bf7d  mov     rcx, cs:_bidID
0x10041bf84  mov     rax, r10
0x10041bf87  call    cs:__guard_dispatch_icall_fptr
0x10041bf8d  lea     r14, [rsi+38h]
0x10041bf91  mov     rcx, r14; struct CCriticalSectionNT_SNI **
0x10041bf94  call    ?Initialize@CCriticalSectionNT_SNI@@SAKPEAPEAV1@@Z; CCriticalSectionNT_SNI::Initialize(CCriticalSectionNT_SNI * *)
0x10041bf99  mov     edi, eax
0x10041bf9b  test    eax, eax
0x10041bf9d  jnz     loc_10041C039
0x10041bfa3  mov     rax, [r14]
0x10041bfa6  mov     rcx, [rax+10h]
0x10041bfaa  lea     rax, [rcx+20h]
0x10041bfae  neg     rcx
0x10041bfb1  sbb     rdi, rdi
0x10041bfb4  and     rdi, rax
0x10041bfb7  xor     r9d, r9d; lpName
0x10041bfba  xor     r8d, r8d; bInitialState
0x10041bfbd  xor     edx, edx; bManualReset
0x10041bfbf  xor     ecx, ecx; lpEventAttributes
0x10041bfc1  call    cs:__imp_CreateEventW
0x10041bfc7  mov     [rsi+0C0h], rax
0x10041bfce  test    rax, rax
0x10041bfd1  jnz     loc_10041C0D6
0x10041bfd7  call    cs:__imp_GetLastError
0x10041bfdd  mov     edi, eax
0x10041bfdf  test    eax, eax
0x10041bfe1  jz      loc_10041C0DD
0x10041bfe7  test    byte ptr cs:_bidGblFlags, 2
0x10041bfee  jz      short loc_10041C027
0x10041bff0  mov     rax, cs:off_1005E48F8; "<Session::FInit|ERR|SNI> ProviderNum: %"...
0x10041bff7  test    rax, rax
0x10041bffa  jz      short loc_10041C027
0x10041bffc  mov     ecx, 0C3B4h; unsigned int
0x10041c001  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10041c006  mov     [rsp+58h+var_30], edi
0x10041c00a  mov     [rsp+58h+var_38], eax
0x10041c00e  mov     r9d, 2
0x10041c014  mov     r8, cs:off_1005E48F8; "<Session::FInit|ERR|SNI> ProviderNum: %"...
0x10041c01b  mov     edx, 0C0800h
0x10041c020  xor     ecx, ecx
0x10041c022  call    _bidTraceW
0x10041c027  mov     r8d, 0C3B4h
0x10041c02d  mov     edx, edi
0x10041c02f  mov     ecx, 2
0x10041c034  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10041c039  mov     rcx, [r14]
0x10041c03c  test    rcx, rcx
0x10041c03f  jz      short loc_10041C055
0x10041c041  mov     rax, [rcx]
0x10041c044  mov     edx, 1
0x10041c049  mov     rax, [rax]
0x10041c04c  call    cs:__guard_dispatch_icall_fptr
0x10041c052  mov     [r14], rbx
0x10041c055  mov     rcx, [rsi+0C0h]; hObject
0x10041c05c  test    rcx, rcx
0x10041c05f  jz      short loc_10041C07F
0x10041c061  call    cs:__imp_CloseHandle
0x10041c067  mov     [rsi+0C0h], rbx
0x10041c06e  mov     [rsi+0B8h], rbx
0x10041c075  test    eax, eax
0x10041c077  jnz     short loc_10041C07F
0x10041c079  call    cs:__imp_GetLastError
0x10041c07f  mov     eax, cs:_bidGblFlags
0x10041c085  mov     ecx, 20002h
0x10041c08a  and     eax, ecx
0x10041c08c  cmp     eax, ecx
0x10041c08e  jnz     short loc_10041C0B2
0x10041c090  mov     rax, cs:off_1005E4908; "<Session::FInit|RET|SNI> %d{WINERR}\n"
0x10041c097  test    rax, rax
0x10041c09a  jz      short loc_10041C0B2
0x10041c09c  mov     r9d, edi
0x10041c09f  mov     r8, cs:off_1005E4908; "<Session::FInit|RET|SNI> %d{WINERR}\n"
0x10041c0a6  mov     edx, 0C6800h
0x10041c0ab  xor     ecx, ecx
0x10041c0ad  call    _bidTraceW
0x10041c0b2  mov     ebx, edi
0x10041c0b4  lea     rcx, [rsp+58h+arg_0]; this
0x10041c0b9  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x10041c0be  mov     eax, ebx
0x10041c0c0  mov     rbx, [rsp+58h+arg_8]
0x10041c0c5  mov     rsi, [rsp+58h+arg_10]
0x10041c0ca  mov     rdi, [rsp+58h+arg_18]
0x10041c0cf  add     rsp, 50h
0x10041c0d3  pop     r14
0x10041c0d5  retn
0x10041c0d6  mov     [rsi+0B8h], rdi
0x10041c0dd  mov     rcx, [rsi+30h]; this
0x10041c0e1  call    ?AddSessionRef@Smux@@QEAAXXZ; Smux::AddSessionRef(void)
0x10041c0e6  mov     eax, cs:_bidGblFlags
0x10041c0ec  mov     ecx, 20002h
0x10041c0f1  and     eax, ecx
0x10041c0f3  cmp     eax, ecx
0x10041c0f5  jnz     short loc_10041C0B4
0x10041c0f7  mov     rax, cs:off_1005E4900; "<Session::FInit|RET|SNI> %d{WINERR}\n"
0x10041c0fe  test    rax, rax
0x10041c101  jz      short loc_10041C0B4
0x10041c103  xor     r9d, r9d
0x10041c106  mov     r8, cs:off_1005E4900; "<Session::FInit|RET|SNI> %d{WINERR}\n"
0x10041c10d  mov     edx, 0C2400h
0x10041c112  xor     ecx, ecx
0x10041c114  call    _bidTraceW
0x10041c119  jmp     short loc_10041C0B4
```
