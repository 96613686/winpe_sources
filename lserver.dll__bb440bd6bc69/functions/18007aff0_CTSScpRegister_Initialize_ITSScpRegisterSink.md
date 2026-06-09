# CTSScpRegister::Initialize(ITSScpRegisterSink *)

- ea: `0x18007aff0`
- end: `0x18007b2a0`
- name: `?Initialize@CTSScpRegister@@QEAAJPEAVITSScpRegisterSink@@@Z`
- size: `688`
- prototype: `__int64 __fastcall(CTSScpRegister *__hidden this, struct ITSScpRegisterSink *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180079d58`

## callees

- `0x180005665`
- `0x18001ae3c`
- `0x18001aea4`
- `0x18007aff0`
- `0x1800a5010`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x18007b0fa`
- `KERNEL32!GetComputerNameExW` at `0x18007b189`
- `KERNEL32!GetComputerNameExW` at `0x18007b0fa`
- `KERNEL32!GetComputerNameExW` at `0x18007b189`
- `KERNEL32!CreateThread` at `0x18007b217`
- `KERNEL32!CreateThread` at `0x18007b217`
- `KERNEL32!CreateEventW` at `0x18007b016`
- `KERNEL32!CreateEventW` at `0x18007b065`
- `KERNEL32!CreateEventW` at `0x18007b0ac`
- `KERNEL32!CreateEventW` at `0x18007b016`
- `KERNEL32!CreateEventW` at `0x18007b065`
- `KERNEL32!CreateEventW` at `0x18007b0ac`
- `KERNEL32!GetLastError` at `0x18007b199`
- `KERNEL32!GetLastError` at `0x18007b264`
- `KERNEL32!GetLastError` at `0x18007b199`
- `KERNEL32!GetLastError` at `0x18007b264`
- `KERNEL32!LocalAlloc` at `0x18007b10f`
- `KERNEL32!LocalAlloc` at `0x18007b10f`

## string_xrefs

- `0x18007b24d`: `CreateThread`
- `0x18007b04f`: `CreateEvent`
- `0x18007b1dd`: `"GetComputerNameEx"`

## pseudocode

```c
__int64 __fastcall CTSScpRegister::Initialize(CTSScpRegister *this, struct ITSScpRegisterSink *a2)
{
  signed int v2; // ebx
  HANDLE EventW; // rax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  const wchar_t *v7; // r9
  HANDLE v8; // rax
  HANDLE v9; // rax
  HLOCAL v10; // rax
  signed int v11; // eax
  HANDLE Thread; // rax
  signed int LastError; // eax
  struct ITSScpRegisterSink *nSize; // [rsp+48h] [rbp+10h] BYREF

  nSize = a2;
  v2 = 0;
  *((_QWORD *)this + 49) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 8) = EventW;
  if ( !EventW )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 15;
LABEL_5:
      v7 = L"CreateEvent";
LABEL_30:
      WPP_SF_S(v5[2], v6, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids, v7);
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  v8 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 9) = v8;
  if ( !v8 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 16;
      goto LABEL_5;
    }
LABEL_31:
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 < 0 )
    {
LABEL_34:
      (*(void (__fastcall **)(CTSScpRegister *))(*(_QWORD *)this + 96LL))(this);
      return (unsigned int)v2;
    }
    return (unsigned int)v2;
  }
  v9 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 10) = v9;
  if ( !v9 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 17;
      goto LABEL_5;
    }
    goto LABEL_31;
  }
  LODWORD(nSize) = 0;
  GetComputerNameExW(ComputerNameDnsFullyQualified, 0, (LPDWORD)&nSize);
  v10 = LocalAlloc(0, 2LL * (unsigned int)nSize);
  *((_QWORD *)this + 18) = v10;
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids,
        L"_T(\"LocalAlloc\")");
    v2 = -2147024882;
    goto LABEL_34;
  }
  memset_0(v10, 0, 2LL * (unsigned int)nSize);
  if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, *((LPWSTR *)this + 18), (LPDWORD)&nSize) )
  {
    v11 = GetLastError();
    v2 = v11;
    if ( v11 > 0 )
      v2 = (unsigned __int16)v11 | 0x80070000;
    if ( v2 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids,
          (unsigned int)L"\"GetComputerNameEx\"",
          v2);
      goto LABEL_34;
    }
  }
  Thread = CreateThread(0, 0, CTSScpRegister::StaticSCPWorkerThread, this, 0, 0);
  *((_QWORD *)this + 47) = Thread;
  if ( !Thread )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 20;
      v7 = L"CreateThread";
      goto LABEL_30;
    }
    goto LABEL_31;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18007aff0  mov     [rsp+arg_0], rbx
0x18007aff5  mov     [rsp+nSize], rdx
0x18007affa  push    rdi
0x18007affb  sub     rsp, 30h
0x18007afff  xor     ebx, ebx
0x18007b001  mov     rdi, rcx
0x18007b004  and     [rcx+188h], rbx
0x18007b00b  xor     r9d, r9d; lpName
0x18007b00e  xor     r8d, r8d; bInitialState
0x18007b011  xor     ecx, ecx; lpEventAttributes
0x18007b013  lea     edx, [rbx+1]; bManualReset
0x18007b016  call    cs:__imp_CreateEventW
0x18007b01d  nop     dword ptr [rax+rax+00h]
0x18007b022  mov     [rdi+40h], rax
0x18007b026  test    rax, rax
0x18007b029  jnz     short loc_18007B05B
0x18007b02b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b032  lea     rax, WPP_GLOBAL_Control
0x18007b039  cmp     rcx, rax
0x18007b03c  jz      loc_18007B264
0x18007b042  cmp     byte ptr [rcx+19h], 2
0x18007b046  jb      loc_18007B264
0x18007b04c  lea     edx, [rbx+0Fh]
0x18007b04f  lea     r9, aCreateevent; "CreateEvent"
0x18007b056  jmp     loc_18007B254
0x18007b05b  xor     r9d, r9d; lpName
0x18007b05e  xor     r8d, r8d; bInitialState
0x18007b061  xor     edx, edx; bManualReset
0x18007b063  xor     ecx, ecx; lpEventAttributes
0x18007b065  call    cs:__imp_CreateEventW
0x18007b06c  nop     dword ptr [rax+rax+00h]
0x18007b071  mov     [rdi+48h], rax
0x18007b075  test    rax, rax
0x18007b078  jnz     short loc_18007B0A2
0x18007b07a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b081  lea     rax, WPP_GLOBAL_Control
0x18007b088  cmp     rcx, rax
0x18007b08b  jz      loc_18007B264
0x18007b091  cmp     byte ptr [rcx+19h], 2
0x18007b095  jb      loc_18007B264
0x18007b09b  mov     edx, 10h
0x18007b0a0  jmp     short loc_18007B04F
0x18007b0a2  xor     r9d, r9d; lpName
0x18007b0a5  xor     r8d, r8d; bInitialState
0x18007b0a8  xor     edx, edx; bManualReset
0x18007b0aa  xor     ecx, ecx; lpEventAttributes
0x18007b0ac  call    cs:__imp_CreateEventW
0x18007b0b3  nop     dword ptr [rax+rax+00h]
0x18007b0b8  mov     [rdi+50h], rax
0x18007b0bc  test    rax, rax
0x18007b0bf  jnz     short loc_18007B0EC
0x18007b0c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b0c8  lea     rax, WPP_GLOBAL_Control
0x18007b0cf  cmp     rcx, rax
0x18007b0d2  jz      loc_18007B264
0x18007b0d8  cmp     byte ptr [rcx+19h], 2
0x18007b0dc  jb      loc_18007B264
0x18007b0e2  mov     edx, 11h
0x18007b0e7  jmp     loc_18007B04F
0x18007b0ec  and     dword ptr [rsp+38h+nSize], ebx
0x18007b0f0  lea     r8, [rsp+38h+nSize]; nSize
0x18007b0f5  xor     edx, edx; lpBuffer
0x18007b0f7  lea     ecx, [rdx+3]; NameType
0x18007b0fa  call    cs:__imp_GetComputerNameExW
0x18007b101  nop     dword ptr [rax+rax+00h]
0x18007b106  mov     edx, dword ptr [rsp+38h+nSize]
0x18007b10a  xor     ecx, ecx; uFlags
0x18007b10c  add     rdx, rdx; uBytes
0x18007b10f  call    cs:__imp_LocalAlloc
0x18007b116  nop     dword ptr [rax+rax+00h]
0x18007b11b  mov     [rdi+90h], rax
0x18007b122  test    rax, rax
0x18007b125  jnz     short loc_18007B166
0x18007b127  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b12e  lea     rax, WPP_GLOBAL_Control
0x18007b135  cmp     rcx, rax
0x18007b138  jz      short loc_18007B15C
0x18007b13a  cmp     byte ptr [rcx+19h], 2
0x18007b13e  jb      short loc_18007B15C
0x18007b140  mov     rcx, [rcx+10h]
0x18007b144  lea     r9, aTLocalalloc; "_T(\"LocalAlloc\")"
0x18007b14b  mov     edx, 12h
0x18007b150  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x18007b157  call    WPP_SF_S
0x18007b15c  mov     ebx, 8007000Eh
0x18007b161  jmp     loc_18007B283
0x18007b166  mov     r8d, dword ptr [rsp+38h+nSize]
0x18007b16b  xor     edx, edx; Val
0x18007b16d  add     r8, r8; Size
0x18007b170  mov     rcx, rax; void *
0x18007b173  call    memset_0
0x18007b178  mov     rdx, [rdi+90h]; lpBuffer
0x18007b17f  lea     r8, [rsp+38h+nSize]; nSize
0x18007b184  mov     ecx, 3; NameType
0x18007b189  call    cs:__imp_GetComputerNameExW
0x18007b190  nop     dword ptr [rax+rax+00h]
0x18007b195  test    eax, eax
0x18007b197  jnz     short loc_18007B1FE
0x18007b199  call    cs:__imp_GetLastError
0x18007b1a0  nop     dword ptr [rax+rax+00h]
0x18007b1a5  mov     ebx, eax
0x18007b1a7  test    eax, eax
0x18007b1a9  jle     short loc_18007B1B4
0x18007b1ab  movzx   ebx, ax
0x18007b1ae  or      ebx, 80070000h
0x18007b1b4  test    ebx, ebx
0x18007b1b6  jns     short loc_18007B1FE
0x18007b1b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b1bf  lea     rax, WPP_GLOBAL_Control
0x18007b1c6  cmp     rcx, rax
0x18007b1c9  jz      loc_18007B283
0x18007b1cf  cmp     byte ptr [rcx+19h], 2
0x18007b1d3  jb      loc_18007B283
0x18007b1d9  mov     rcx, [rcx+10h]
0x18007b1dd  lea     r9, aGetcomputernam; "\"GetComputerNameEx\""
0x18007b1e4  mov     edx, 13h
0x18007b1e9  mov     [rsp+38h+var_18], ebx
0x18007b1ed  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x18007b1f4  call    WPP_SF_SD
0x18007b1f9  jmp     loc_18007B283
0x18007b1fe  and     [rsp+38h+var_10], 0
0x18007b204  lea     r8, ?StaticSCPWorkerThread@CTSScpRegister@@CAKPEAX@Z; lpStartAddress
0x18007b20b  and     [rsp+38h+var_18], 0
0x18007b210  mov     r9, rdi; lpParameter
0x18007b213  xor     edx, edx; dwStackSize
0x18007b215  xor     ecx, ecx; lpThreadAttributes
0x18007b217  call    cs:__imp_CreateThread
0x18007b21e  nop     dword ptr [rax+rax+00h]
0x18007b223  mov     [rdi+178h], rax
0x18007b22a  test    rax, rax
0x18007b22d  jnz     short loc_18007B292
0x18007b22f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b236  lea     rax, WPP_GLOBAL_Control
0x18007b23d  cmp     rcx, rax
0x18007b240  jz      short loc_18007B264
0x18007b242  cmp     byte ptr [rcx+19h], 2
0x18007b246  jb      short loc_18007B264
0x18007b248  mov     edx, 14h
0x18007b24d  lea     r9, aCreatethread; "CreateThread"
0x18007b254  mov     rcx, [rcx+10h]
0x18007b258  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x18007b25f  call    WPP_SF_S
0x18007b264  call    cs:__imp_GetLastError
0x18007b26b  nop     dword ptr [rax+rax+00h]
0x18007b270  mov     ebx, eax
0x18007b272  test    eax, eax
0x18007b274  jle     short loc_18007B27F
0x18007b276  movzx   ebx, ax
0x18007b279  or      ebx, 80070000h
0x18007b27f  test    ebx, ebx
0x18007b281  jns     short loc_18007B292
0x18007b283  mov     rcx, [rdi]
0x18007b286  mov     rax, [rcx+60h]
0x18007b28a  mov     rcx, rdi
0x18007b28d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b292  mov     eax, ebx
0x18007b294  mov     rbx, [rsp+38h+arg_0]
0x18007b299  add     rsp, 30h
0x18007b29d  pop     rdi
0x18007b29e  retn
```
