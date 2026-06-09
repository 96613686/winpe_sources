# CMemoryDiagnosticHandler::StartMemoryTest(void)

- ea: `0x18001d094`
- end: `0x18001d246`
- name: `?StartMemoryTest@CMemoryDiagnosticHandler@@AEAAJXZ`
- size: `434`
- prototype: `__int64 __fastcall(CMemoryDiagnosticHandler *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001d7a0`

## callees

- `0x18001a3e4`
- `0x18001d094`
- `0x18001e21c`
- `0x18001e24c`
- `0x18001e328`

## import_xrefs

- `ntdll!NtSetSystemInformation` at `0x18001d141`
- `ntdll!NtSetSystemInformation` at `0x18001d141`
- `KERNEL32!CreateEventW` at `0x18001d0d0`
- `KERNEL32!CreateEventW` at `0x18001d0d0`
- `KERNEL32!GetTickCount64` at `0x18001d129`
- `KERNEL32!GetTickCount64` at `0x18001d149`
- `KERNEL32!GetTickCount64` at `0x18001d129`
- `KERNEL32!GetTickCount64` at `0x18001d149`
- `KERNEL32!GetLastError` at `0x18001d0e2`
- `KERNEL32!GetLastError` at `0x18001d0e2`

## pseudocode

```c
__int64 __fastcall CMemoryDiagnosticHandler::StartMemoryTest(
        CMemoryDiagnosticHandler *this,
        const unsigned __int16 *a2)
{
  const unsigned __int16 *v3; // rdx
  CMemoryDiagnosticHandler *v4; // rcx
  int v5; // edi
  HANDLE EventW; // rax
  signed int LastError; // eax
  ULONGLONG TickCount64; // rbx
  NTSTATUS v9; // esi
  ULONGLONG v10; // rax
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // r8
  __int128 SystemInformation; // [rsp+30h] [rbp-38h] BYREF

  SystemInformation = 0;
  v5 = CMemoryDiagnosticHandler::AdjustPrivilege(this, a2, 1);
  if ( v5 < 0 )
    goto LABEL_18;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 20) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70);
    }
    goto LABEL_18;
  }
  *(_QWORD *)&SystemInformation = EventW;
  TickCount64 = GetTickCount64();
  v9 = NtSetSystemInformation(MaxSystemInfoClass|SystemSummaryMemoryInformation, &SystemInformation, 0x10u);
  v10 = GetTickCount64();
  v12 = *((_QWORD *)&SystemInformation + 1);
  *((_QWORD *)this + 16) = v10 - TickCount64;
  *((_QWORD *)this + 19) = v12;
  if ( (int)(v9 + 0x80000000) < 0 || v9 == -1073740023 )
  {
LABEL_14:
    v4 = WPP_GLOBAL_Control;
LABEL_15:
    if ( v4 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 )
      WPP_SF_IP(*((_QWORD *)v4 + 2), v3, v11, *((_QWORD *)this + 16), *((_QWORD *)&SystemInformation + 1));
    goto LABEL_18;
  }
  if ( v9 == -1073741248 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control )
      goto LABEL_18;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_15;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71);
    goto LABEL_14;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, v11, (unsigned int)v9);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = v9 | 0x10000000;
  if ( v9 >= 0 )
    goto LABEL_15;
LABEL_18:
  CMemoryDiagnosticHandler::AdjustPrivilege(v4, v3, 0);
  if ( v5 < 0
    && WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v13, (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001d094  push    rbx
0x18001d096  push    rbp
0x18001d097  push    rsi
0x18001d098  push    rdi
0x18001d099  push    r14
0x18001d09b  sub     rsp, 40h
0x18001d09f  xorps   xmm0, xmm0
0x18001d0a2  mov     r8d, 1; int
0x18001d0a8  movups  [rsp+68h+SystemInformation], xmm0
0x18001d0ad  mov     rbp, rcx
0x18001d0b0  call    ?AdjustPrivilege@CMemoryDiagnosticHandler@@AEAAJPEBGH@Z; CMemoryDiagnosticHandler::AdjustPrivilege(ushort const *,int)
0x18001d0b5  lea     r14, WPP_GLOBAL_Control
0x18001d0bc  mov     edi, eax
0x18001d0be  test    eax, eax
0x18001d0c0  js      loc_18001D1D1
0x18001d0c6  xor     r9d, r9d; lpName
0x18001d0c9  xor     r8d, r8d; bInitialState
0x18001d0cc  xor     edx, edx; bManualReset
0x18001d0ce  xor     ecx, ecx; lpEventAttributes
0x18001d0d0  call    cs:__imp_CreateEventW
0x18001d0d6  mov     [rbp+0A0h], rax
0x18001d0dd  test    rax, rax
0x18001d0e0  jnz     short loc_18001D124
0x18001d0e2  call    cs:__imp_GetLastError
0x18001d0e8  mov     edi, eax
0x18001d0ea  test    eax, eax
0x18001d0ec  jle     short loc_18001D0F7
0x18001d0ee  movzx   edi, ax
0x18001d0f1  or      edi, 80070000h
0x18001d0f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0fe  cmp     rcx, r14
0x18001d101  jz      loc_18001D1D1
0x18001d107  test    byte ptr [rcx+1Ch], 1
0x18001d10b  jz      loc_18001D1D1
0x18001d111  mov     rcx, [rcx+10h]
0x18001d115  mov     edx, 46h ; 'F'
0x18001d11a  call    WPP_SF_
0x18001d11f  jmp     loc_18001D1D1
0x18001d124  mov     qword ptr [rsp+68h+SystemInformation], rax
0x18001d129  call    cs:__imp_GetTickCount64
0x18001d12f  mov     r8d, 10h; SystemInformationLength
0x18001d135  lea     rdx, [rsp+68h+SystemInformation]; SystemInformation
0x18001d13a  mov     rbx, rax
0x18001d13d  lea     ecx, [r8+6Fh]; SystemInformationClass
0x18001d141  call    cs:__imp_NtSetSystemInformation
0x18001d147  mov     esi, eax
0x18001d149  call    cs:__imp_GetTickCount64
0x18001d14f  mov     rcx, qword ptr [rsp+68h+SystemInformation+8]
0x18001d154  sub     rax, rbx
0x18001d157  mov     [rbp+80h], rax
0x18001d15e  mov     eax, 80000000h
0x18001d163  mov     [rbp+98h], rcx
0x18001d16a  lea     ecx, [rsi+rax]
0x18001d16d  test    eax, ecx
0x18001d16f  jnz     short loc_18001D1A5
0x18001d171  cmp     esi, 0C0000709h
0x18001d177  jz      short loc_18001D1A5
0x18001d179  cmp     esi, 0C0000240h
0x18001d17f  jnz     loc_18001D20D
0x18001d185  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d18c  cmp     rcx, r14
0x18001d18f  jz      short loc_18001D1D1
0x18001d191  test    byte ptr [rcx+1Ch], 4
0x18001d195  jz      short loc_18001D1AC
0x18001d197  mov     rcx, [rcx+10h]
0x18001d19b  mov     edx, 47h ; 'G'
0x18001d1a0  call    WPP_SF_
0x18001d1a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1ac  cmp     rcx, r14
0x18001d1af  jz      short loc_18001D1D1
0x18001d1b1  test    byte ptr [rcx+1Ch], 4
0x18001d1b5  jz      short loc_18001D1D1
0x18001d1b7  mov     rax, qword ptr [rsp+68h+SystemInformation+8]
0x18001d1bc  mov     r9, [rbp+80h]
0x18001d1c3  mov     rcx, [rcx+10h]
0x18001d1c7  mov     [rsp+68h+var_48], rax
0x18001d1cc  call    WPP_SF_IP
0x18001d1d1  xor     r8d, r8d; int
0x18001d1d4  call    ?AdjustPrivilege@CMemoryDiagnosticHandler@@AEAAJPEBGH@Z; CMemoryDiagnosticHandler::AdjustPrivilege(ushort const *,int)
0x18001d1d9  test    edi, edi
0x18001d1db  jns     short loc_18001D200
0x18001d1dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1e4  cmp     rcx, r14
0x18001d1e7  jz      short loc_18001D200
0x18001d1e9  test    byte ptr [rcx+1Ch], 1
0x18001d1ed  jz      short loc_18001D200
0x18001d1ef  mov     rcx, [rcx+10h]
0x18001d1f3  mov     edx, 0Ah
0x18001d1f8  mov     r9d, edi
0x18001d1fb  call    WPP_SF_d
0x18001d200  mov     eax, edi
0x18001d202  add     rsp, 40h
0x18001d206  pop     r14
0x18001d208  pop     rdi
0x18001d209  pop     rsi
0x18001d20a  pop     rbp
0x18001d20b  pop     rbx
0x18001d20c  retn
0x18001d20d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d214  cmp     rcx, r14
0x18001d217  jz      short loc_18001D237
0x18001d219  test    byte ptr [rcx+1Ch], 1
0x18001d21d  jz      short loc_18001D237
0x18001d21f  mov     rcx, [rcx+10h]
0x18001d223  mov     edx, 48h ; 'H'
0x18001d228  mov     r9d, esi
0x18001d22b  call    WPP_SF_d
0x18001d230  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d237  mov     edi, esi
0x18001d239  or      edi, 10000000h
0x18001d23f  jl      short loc_18001D1D1
0x18001d241  jmp     loc_18001D1AC
```
