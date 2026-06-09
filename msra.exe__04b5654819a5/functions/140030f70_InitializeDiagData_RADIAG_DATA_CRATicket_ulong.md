# InitializeDiagData(_RADIAG_DATA *,CRATicket *,ulong)

- ea: `0x140030f70`
- end: `0x1400311b1`
- name: `?InitializeDiagData@@YAJPEAU_RADIAG_DATA@@PEAVCRATicket@@K@Z`
- size: `577`
- prototype: `__int64 __fastcall(struct _RADIAG_DATA *, struct CRATicket *this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400194c8`

## callees

- `0x14002f778`
- `0x14002f9f4`
- `0x14002fbe0`
- `0x140030f70`
- `0x140034ce4`
- `0x14003642c`
- `0x14003d088`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x140030fd8`
- `ADVAPI32!EventActivityIdControl` at `0x140030fd8`
- `KERNEL32!CreateThread` at `0x140031158`
- `KERNEL32!CreateThread` at `0x140031158`
- `KERNEL32!CreateEventW` at `0x1400310c4`
- `KERNEL32!CreateEventW` at `0x1400310ef`
- `KERNEL32!CreateEventW` at `0x140031119`
- `KERNEL32!CreateEventW` at `0x1400310c4`
- `KERNEL32!CreateEventW` at `0x1400310ef`
- `KERNEL32!CreateEventW` at `0x140031119`
- `ole32!CoCreateGuid` at `0x140030faf`
- `ole32!CoCreateGuid` at `0x140030faf`

## pseudocode

```c
__int64 __fastcall InitializeDiagData(struct _RADIAG_DATA *a1, struct CRATicket *this, int a3)
{
  unsigned int v6; // ebx
  struct _GUID *v7; // rbp
  HRESULT Guid; // eax
  CEventLogger *v9; // rcx
  CEventLogger *v10; // rcx
  unsigned int v11; // r9d
  int v12; // esi
  signed int v13; // eax
  CEventLogger *v14; // rcx
  signed int v15; // eax
  CEventLogger *v16; // rcx
  signed int UniqueName; // eax
  CEventLogger *v18; // rcx
  signed int v19; // eax
  CEventLogger *v20; // rcx
  HANDLE EventW; // rax
  HANDLE v22; // rax
  HANDLE v23; // rax
  HANDLE Thread; // rax
  CEventLogger *v25; // rcx

  if ( !this )
  {
    v6 = -2147467261;
    CEventLogger::LogError(
      a1,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      0x11Eu,
      L"InitializeDiagData",
      0x80004003);
LABEL_26:
    CleanupDiagData(a1);
    return v6;
  }
  v7 = (struct _GUID *)((char *)a1 + 64);
  *((_DWORD *)a1 + 30) = a3;
  *((_QWORD *)a1 + 7) = this;
  Guid = CoCreateGuid((GUID *)a1 + 4);
  v6 = Guid;
  if ( Guid < 0 )
  {
    CEventLogger::LogError(
      v9,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      0x12Au,
      L"InitializeDiagData",
      Guid);
    goto LABEL_26;
  }
  if ( EventActivityIdControl(2u, v7) )
  {
    v11 = 306;
LABEL_7:
    CEventLogger::LogError(
      v10,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      v11,
      L"InitializeDiagData",
      0);
    v6 = -2147467259;
    goto LABEL_26;
  }
  v12 = a3 - 2;
  if ( v12 )
  {
    if ( v12 == 1 )
    {
      v13 = BuildOutDiagData(a1);
      v6 = v13;
      if ( v13 < 0 )
      {
        CEventLogger::LogError(
          v14,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
          0x14Au,
          L"InitializeDiagData",
          v13);
        goto LABEL_26;
      }
    }
  }
  else
  {
    CRATicket::NoviceDisconnect(this);
    v15 = BuildInDiagData(a1);
    v6 = v15;
    if ( v15 < 0 )
    {
      CEventLogger::LogError(
        v16,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
        0x144u,
        L"InitializeDiagData",
        v15);
      goto LABEL_26;
    }
  }
  UniqueName = GenerateUniqueName(L"Global\\RADiagEvent-ReproStart", v7, (unsigned __int16 **)a1);
  v6 = UniqueName;
  if ( UniqueName < 0 )
  {
    CEventLogger::LogError(
      v18,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      0x155u,
      L"InitializeDiagData",
      UniqueName);
    goto LABEL_26;
  }
  v19 = GenerateUniqueName(L"Global\\RADiagEvent-ReproDone", v7, (unsigned __int16 **)a1 + 1);
  v6 = v19;
  if ( v19 < 0 )
  {
    CEventLogger::LogError(
      v20,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      0x159u,
      L"InitializeDiagData",
      v19);
    goto LABEL_26;
  }
  EventW = CreateEventW(0, 0, 0, *(LPCWSTR *)a1);
  *((_QWORD *)a1 + 2) = EventW;
  if ( !EventW )
  {
    v11 = 357;
    goto LABEL_7;
  }
  v22 = CreateEventW(0, 0, 0, *((LPCWSTR *)a1 + 1));
  *((_QWORD *)a1 + 3) = v22;
  if ( !v22 )
  {
    v11 = 364;
    goto LABEL_7;
  }
  v23 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)a1 + 4) = v23;
  if ( !v23 )
  {
    v11 = 371;
    goto LABEL_7;
  }
  Thread = CreateThread(0, 0, DiagThreadFunc, a1, 0, (LPDWORD)a1 + 12);
  *((_QWORD *)a1 + 5) = Thread;
  if ( !Thread )
  {
    v6 = -2147467259;
    CEventLogger::LogError(
      v25,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      0x185u,
      L"InitializeDiagData",
      0);
    goto LABEL_26;
  }
  return v6;
}

```

## disassembly

```asm
0x140030f70  push    rbx
0x140030f72  push    rbp
0x140030f73  push    rsi
0x140030f74  push    rdi
0x140030f75  push    r14
0x140030f77  sub     rsp, 30h
0x140030f7b  mov     esi, r8d
0x140030f7e  mov     r14, rdx
0x140030f81  mov     rdi, rcx
0x140030f84  test    rdx, rdx
0x140030f87  jnz     short loc_140030FA1
0x140030f89  mov     ebx, 80004003h
0x140030f8e  mov     dword ptr [rsp+58h+lpThreadId], 80004003h
0x140030f96  mov     r9d, 11Eh
0x140030f9c  jmp     loc_14003117C
0x140030fa1  lea     rbp, [rcx+40h]
0x140030fa5  mov     [rcx+78h], esi
0x140030fa8  mov     [rcx+38h], r14
0x140030fac  mov     rcx, rbp; pguid
0x140030faf  call    cs:__imp_CoCreateGuid
0x140030fb6  nop     dword ptr [rax+rax+00h]
0x140030fbb  mov     ebx, eax
0x140030fbd  test    eax, eax
0x140030fbf  jns     short loc_140030FD0
0x140030fc1  mov     dword ptr [rsp+58h+lpThreadId], eax
0x140030fc5  mov     r9d, 12Ah
0x140030fcb  jmp     loc_14003117C
0x140030fd0  mov     rdx, rbp; ActivityId
0x140030fd3  mov     ecx, 2; ControlCode
0x140030fd8  call    cs:__imp_EventActivityIdControl
0x140030fdf  nop     dword ptr [rax+rax+00h]
0x140030fe4  test    eax, eax
0x140030fe6  jz      short loc_14003101F
0x140030fe8  mov     r9d, 132h; unsigned int
0x140030fee  lea     rax, aInitializediag; "InitializeDiagData"
0x140030ff5  mov     dword ptr [rsp+58h+lpThreadId], 0; unsigned int
0x140030ffd  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x140031004  mov     qword ptr [rsp+58h+dwCreationFlags], rax; unsigned __int16 *
0x140031009  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140031010  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140031015  mov     ebx, 80004005h
0x14003101a  jmp     loc_14003119B
0x14003101f  sub     esi, 2
0x140031022  jz      short loc_140031046
0x140031024  cmp     esi, 1
0x140031027  jnz     short loc_14003106B
0x140031029  mov     rcx, rdi; struct _RADIAG_DATA *
0x14003102c  call    ?BuildOutDiagData@@YAJPEAU_RADIAG_DATA@@@Z; BuildOutDiagData(_RADIAG_DATA *)
0x140031031  mov     ebx, eax
0x140031033  test    eax, eax
0x140031035  jns     short loc_14003106B
0x140031037  mov     dword ptr [rsp+58h+lpThreadId], eax
0x14003103b  mov     r9d, 14Ah
0x140031041  jmp     loc_14003117C
0x140031046  mov     rcx, r14; this
0x140031049  call    ?NoviceDisconnect@CRATicket@@QEAAJXZ; CRATicket::NoviceDisconnect(void)
0x14003104e  mov     rcx, rdi; struct _RADIAG_DATA *
0x140031051  call    ?BuildInDiagData@@YAJPEAU_RADIAG_DATA@@@Z; BuildInDiagData(_RADIAG_DATA *)
0x140031056  mov     ebx, eax
0x140031058  test    eax, eax
0x14003105a  jns     short loc_14003106B
0x14003105c  mov     dword ptr [rsp+58h+lpThreadId], eax
0x140031060  mov     r9d, 144h
0x140031066  jmp     loc_14003117C
0x14003106b  mov     r8, rdi; unsigned __int16 **
0x14003106e  lea     rcx, aGlobalRadiagev; "Global\\RADiagEvent-ReproStart"
0x140031075  mov     rdx, rbp; struct _GUID *
0x140031078  call    ?GenerateUniqueName@@YAJPEAGPEAU_GUID@@PEAPEAG@Z; GenerateUniqueName(ushort *,_GUID *,ushort * *)
0x14003107d  mov     ebx, eax
0x14003107f  test    eax, eax
0x140031081  jns     short loc_140031092
0x140031083  mov     dword ptr [rsp+58h+lpThreadId], eax
0x140031087  mov     r9d, 155h
0x14003108d  jmp     loc_14003117C
0x140031092  lea     r8, [rdi+8]; unsigned __int16 **
0x140031096  mov     rdx, rbp; struct _GUID *
0x140031099  lea     rcx, aGlobalRadiagev_0; "Global\\RADiagEvent-ReproDone"
0x1400310a0  call    ?GenerateUniqueName@@YAJPEAGPEAU_GUID@@PEAPEAG@Z; GenerateUniqueName(ushort *,_GUID *,ushort * *)
0x1400310a5  mov     ebx, eax
0x1400310a7  test    eax, eax
0x1400310a9  jns     short loc_1400310BA
0x1400310ab  mov     dword ptr [rsp+58h+lpThreadId], eax
0x1400310af  mov     r9d, 159h
0x1400310b5  jmp     loc_14003117C
0x1400310ba  mov     r9, [rdi]; lpName
0x1400310bd  xor     r8d, r8d; bInitialState
0x1400310c0  xor     edx, edx; bManualReset
0x1400310c2  xor     ecx, ecx; lpEventAttributes
0x1400310c4  call    cs:__imp_CreateEventW
0x1400310cb  nop     dword ptr [rax+rax+00h]
0x1400310d0  mov     [rdi+10h], rax
0x1400310d4  test    rax, rax
0x1400310d7  jnz     short loc_1400310E4
0x1400310d9  mov     r9d, 165h
0x1400310df  jmp     loc_140030FEE
0x1400310e4  mov     r9, [rdi+8]; lpName
0x1400310e8  xor     r8d, r8d; bInitialState
0x1400310eb  xor     edx, edx; bManualReset
0x1400310ed  xor     ecx, ecx; lpEventAttributes
0x1400310ef  call    cs:__imp_CreateEventW
0x1400310f6  nop     dword ptr [rax+rax+00h]
0x1400310fb  mov     [rdi+18h], rax
0x1400310ff  test    rax, rax
0x140031102  jnz     short loc_14003110F
0x140031104  mov     r9d, 16Ch
0x14003110a  jmp     loc_140030FEE
0x14003110f  xor     r9d, r9d; lpName
0x140031112  xor     r8d, r8d; bInitialState
0x140031115  xor     edx, edx; bManualReset
0x140031117  xor     ecx, ecx; lpEventAttributes
0x140031119  call    cs:__imp_CreateEventW
0x140031120  nop     dword ptr [rax+rax+00h]
0x140031125  mov     [rdi+20h], rax
0x140031129  test    rax, rax
0x14003112c  jnz     short loc_140031139
0x14003112e  mov     r9d, 173h
0x140031134  jmp     loc_140030FEE
0x140031139  lea     rax, [rdi+30h]
0x14003113d  mov     r9, rdi; lpParameter
0x140031140  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x140031145  lea     r8, ?DiagThreadFunc@@YAKPEAX@Z; lpStartAddress
0x14003114c  xor     edx, edx; dwStackSize
0x14003114e  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x140031156  xor     ecx, ecx; lpThreadAttributes
0x140031158  call    cs:__imp_CreateThread
0x14003115f  nop     dword ptr [rax+rax+00h]
0x140031164  mov     [rdi+28h], rax
0x140031168  test    rax, rax
0x14003116b  jnz     short loc_1400311A3
0x14003116d  mov     ebx, 80004005h
0x140031172  mov     dword ptr [rsp+58h+lpThreadId], eax; unsigned int
0x140031176  mov     r9d, 185h; unsigned int
0x14003117c  lea     rax, aInitializediag; "InitializeDiagData"
0x140031183  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x14003118a  mov     qword ptr [rsp+58h+dwCreationFlags], rax; unsigned __int16 *
0x14003118f  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140031196  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14003119b  mov     rcx, rdi; struct _RADIAG_DATA *
0x14003119e  call    ?CleanupDiagData@@YAJPEAU_RADIAG_DATA@@@Z; CleanupDiagData(_RADIAG_DATA *)
0x1400311a3  mov     eax, ebx
0x1400311a5  add     rsp, 30h
0x1400311a9  pop     r14
0x1400311ab  pop     rdi
0x1400311ac  pop     rsi
0x1400311ad  pop     rbp
0x1400311ae  pop     rbx
0x1400311af  retn
```
