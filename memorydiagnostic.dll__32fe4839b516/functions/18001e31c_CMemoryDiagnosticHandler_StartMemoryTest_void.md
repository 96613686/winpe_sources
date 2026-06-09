# CMemoryDiagnosticHandler::StartMemoryTest(void)

- ea: `0x18001e31c`
- end: `0x18001e50e`
- name: `?StartMemoryTest@CMemoryDiagnosticHandler@@AEAAJXZ`
- size: `498`
- prototype: `__int64 __fastcall(CMemoryDiagnosticHandler *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001ead0`

## callees

- `0x18001b364`
- `0x18001e31c`
- `0x18001f560`
- `0x18001f594`
- `0x18001f67c`

## import_xrefs

- `ntdll!NtSetSystemInformation` at `0x18001e3e8`
- `ntdll!NtSetSystemInformation` at `0x18001e3e8`
- `KERNEL32!CreateEventW` at `0x18001e365`
- `KERNEL32!CreateEventW` at `0x18001e365`
- `KERNEL32!GetTickCount64` at `0x18001e3ca`
- `KERNEL32!GetTickCount64` at `0x18001e3f6`
- `KERNEL32!GetTickCount64` at `0x18001e3ca`
- `KERNEL32!GetTickCount64` at `0x18001e3f6`
- `KERNEL32!GetLastError` at `0x18001e37d`
- `KERNEL32!GetLastError` at `0x18001e37d`

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
  __int128 SystemInformation; // [rsp+30h] [rbp-18h] BYREF

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
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, v11, (unsigned int)v9);
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
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v13, (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001e31c  mov     rax, rsp
0x18001e31f  mov     [rax+8], rbx
0x18001e323  mov     [rax+10h], rbp
0x18001e327  mov     [rax+18h], rsi
0x18001e32b  mov     [rax+20h], rdi
0x18001e32f  push    r14
0x18001e331  sub     rsp, 40h
0x18001e335  xorps   xmm0, xmm0
0x18001e338  mov     r8d, 1; int
0x18001e33e  movups  xmmword ptr [rax-18h], xmm0
0x18001e342  mov     rbp, rcx
0x18001e345  call    ?AdjustPrivilege@CMemoryDiagnosticHandler@@AEAAJPEBGH@Z; CMemoryDiagnosticHandler::AdjustPrivilege(ushort const *,int)
0x18001e34a  lea     r14, WPP_GLOBAL_Control
0x18001e351  mov     edi, eax
0x18001e353  test    eax, eax
0x18001e355  js      loc_18001E484
0x18001e35b  xor     r9d, r9d; lpName
0x18001e35e  xor     r8d, r8d; bInitialState
0x18001e361  xor     edx, edx; bManualReset
0x18001e363  xor     ecx, ecx; lpEventAttributes
0x18001e365  call    cs:__imp_CreateEventW
0x18001e36c  nop     dword ptr [rax+rax+00h]
0x18001e371  mov     [rbp+0A0h], rax
0x18001e378  test    rax, rax
0x18001e37b  jnz     short loc_18001E3C5
0x18001e37d  call    cs:__imp_GetLastError
0x18001e384  nop     dword ptr [rax+rax+00h]
0x18001e389  mov     edi, eax
0x18001e38b  test    eax, eax
0x18001e38d  jle     short loc_18001E398
0x18001e38f  movzx   edi, ax
0x18001e392  or      edi, 80070000h
0x18001e398  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e39f  cmp     rcx, r14
0x18001e3a2  jz      loc_18001E484
0x18001e3a8  test    byte ptr [rcx+1Ch], 1
0x18001e3ac  jz      loc_18001E484
0x18001e3b2  mov     rcx, [rcx+10h]
0x18001e3b6  mov     edx, 46h ; 'F'
0x18001e3bb  call    WPP_SF_
0x18001e3c0  jmp     loc_18001E484
0x18001e3c5  mov     [rsp+48h+SystemInformation], rax
0x18001e3ca  call    cs:__imp_GetTickCount64
0x18001e3d1  nop     dword ptr [rax+rax+00h]
0x18001e3d6  mov     r8d, 10h; SystemInformationLength
0x18001e3dc  lea     rdx, [rsp+48h+SystemInformation]; SystemInformation
0x18001e3e1  mov     rbx, rax
0x18001e3e4  lea     ecx, [r8+6Fh]; SystemInformationClass
0x18001e3e8  call    cs:__imp_NtSetSystemInformation
0x18001e3ef  nop     dword ptr [rax+rax+00h]
0x18001e3f4  mov     esi, eax
0x18001e3f6  call    cs:__imp_GetTickCount64
0x18001e3fd  nop     dword ptr [rax+rax+00h]
0x18001e402  mov     rcx, [rsp+48h+var_10]
0x18001e407  sub     rax, rbx
0x18001e40a  mov     [rbp+80h], rax
0x18001e411  mov     eax, 80000000h
0x18001e416  mov     [rbp+98h], rcx
0x18001e41d  lea     ecx, [rsi+rax]
0x18001e420  test    eax, ecx
0x18001e422  jnz     short loc_18001E458
0x18001e424  cmp     esi, 0C0000709h
0x18001e42a  jz      short loc_18001E458
0x18001e42c  cmp     esi, 0C0000240h
0x18001e432  jnz     loc_18001E4D1
0x18001e438  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e43f  cmp     rcx, r14
0x18001e442  jz      short loc_18001E484
0x18001e444  test    byte ptr [rcx+1Ch], 4
0x18001e448  jz      short loc_18001E45F
0x18001e44a  mov     rcx, [rcx+10h]
0x18001e44e  mov     edx, 47h ; 'G'
0x18001e453  call    WPP_SF_
0x18001e458  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e45f  cmp     rcx, r14
0x18001e462  jz      short loc_18001E484
0x18001e464  test    byte ptr [rcx+1Ch], 4
0x18001e468  jz      short loc_18001E484
0x18001e46a  mov     rax, [rsp+48h+var_10]
0x18001e46f  mov     r9, [rbp+80h]
0x18001e476  mov     rcx, [rcx+10h]
0x18001e47a  mov     [rsp+48h+var_28], rax
0x18001e47f  call    WPP_SF_IP
0x18001e484  xor     r8d, r8d; int
0x18001e487  call    ?AdjustPrivilege@CMemoryDiagnosticHandler@@AEAAJPEBGH@Z; CMemoryDiagnosticHandler::AdjustPrivilege(ushort const *,int)
0x18001e48c  test    edi, edi
0x18001e48e  jns     short loc_18001E4B3
0x18001e490  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e497  cmp     rcx, r14
0x18001e49a  jz      short loc_18001E4B3
0x18001e49c  test    byte ptr [rcx+1Ch], 1
0x18001e4a0  jz      short loc_18001E4B3
0x18001e4a2  mov     rcx, [rcx+10h]
0x18001e4a6  mov     edx, 0Ah
0x18001e4ab  mov     r9d, edi
0x18001e4ae  call    WPP_SF_D
0x18001e4b3  mov     rbx, [rsp+48h+arg_0]
0x18001e4b8  mov     eax, edi
0x18001e4ba  mov     rdi, [rsp+48h+arg_18]
0x18001e4bf  mov     rbp, [rsp+48h+arg_8]
0x18001e4c4  mov     rsi, [rsp+48h+arg_10]
0x18001e4c9  add     rsp, 40h
0x18001e4cd  pop     r14
0x18001e4cf  retn
0x18001e4d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e4d8  cmp     rcx, r14
0x18001e4db  jz      short loc_18001E4FB
0x18001e4dd  test    byte ptr [rcx+1Ch], 1
0x18001e4e1  jz      short loc_18001E4FB
0x18001e4e3  mov     rcx, [rcx+10h]
0x18001e4e7  mov     edx, 48h ; 'H'
0x18001e4ec  mov     r9d, esi
0x18001e4ef  call    WPP_SF_D
0x18001e4f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e4fb  mov     edi, esi
0x18001e4fd  or      edi, 10000000h
0x18001e503  jl      loc_18001E484
0x18001e509  jmp     loc_18001E45F
```
