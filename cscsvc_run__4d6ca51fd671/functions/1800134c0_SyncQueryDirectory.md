# SyncQueryDirectory

- ea: `0x1800134c0`
- end: `0x18001395c`
- name: `SyncQueryDirectory`
- size: `1180`
- prototype: `__int64 __usercall@<rax>(HANDLE hHandle@<rcx>, FILE_INFORMATION_CLASS, char, PUNICODE_STRING, char, char)`
- caller_count: `7`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180011880`
- `0x180011ef0`
- `0x180013240`
- `0x180021040`
- `0x180036ac4`
- `0x180037420`
- `0x18007b518`

## callees

- `0x1800134c0`
- `0x1800360c0`
- `0x180036394`
- `0x18003c488`
- `0x18003e928`
- `0x180071318`
- `0x180073fe8`

## import_xrefs

- `ntdll!NtQueryDirectoryFile` at `0x18001359e`
- `ntdll!NtQueryDirectoryFile` at `0x180013686`
- `ntdll!NtQueryDirectoryFile` at `0x18001359e`
- `ntdll!NtQueryDirectoryFile` at `0x180013686`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800138ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800138ff`

## string_xrefs

- `0x180013836`: `SyncQueryDirectoryLocal: Handle: 0x%p BytesTransferred: 0x%p Buffer: 0x%p Size: %d FileInfoClass: 0x%x`
- `0x18001389f`: `SyncQueryDirectoryLocal: ReturnSingleEntry: %d FileName: 0x%p RestartScan: %d`
- `0x1800136c8`: `SyncQueryDirectoryLocal: 0x%x`
- `0x180013704`: `SyncQueryDirectory: Handle: 0x%p BytesTransferred: 0x%p Buffer: 0x%p Size: %d FileInformationClass: 0x%x`
- `0x180013765`: `SyncQueryDirectory: ReturnSingleEntry: %d FileName: 0x%p RestartScan: %d`
- `0x1800137de`: `SyncQueryDirectory: StoreHandle: %ws`
- `0x180013923`: `SyncQueryDirectory: byte transferred : %d status: 0x%x`

## pseudocode

```c
__int64 __fastcall SyncQueryDirectory(
        HANDLE hHandle,
        _DWORD *a2,
        void *a3,
        ULONG a4,
        FILE_INFORMATION_CLASS a5,
        BOOLEAN ReturnSingleEntry,
        PUNICODE_STRING FileName,
        BOOLEAN RestartScan,
        char a9)
{
  CObjectMonitor *v13; // rax
  char v14; // bp
  FILE_INFORMATION_CLASS FileInformationClass; // r13d
  unsigned int Status; // ebx
  __int64 Information_low; // rdx
  unsigned int v19; // eax
  int v20; // ebx
  unsigned int v21; // edi
  const wchar_t *v22; // rbx
  int v23; // ebx
  unsigned int v24; // edi
  PUNICODE_STRING v25; // rbp
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+20h] [rbp-88h]
  PVOID FileInformation; // [rsp+28h] [rbp-80h]
  struct _IO_STATUS_BLOCK v28; // [rsp+60h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK v29; // [rsp+70h] [rbp-38h] BYREF
  unsigned int v30; // [rsp+B8h] [rbp+10h] BYREF

  v28 = 0;
  v30 = 0;
  v13 = WPP_GLOBAL_Control;
  v14 = a9;
  FileInformationClass = a5;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncQueryDirectory: Handle: 0x%p BytesTransferred: 0x%p Buffer: 0x%p Size: %d FileInformationClass: 0x%x",
        hHandle,
        a2,
        a3,
        a4,
        a5);
      WPP_SF_qqqdD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        95,
        WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids,
        hHandle,
        a2,
        a3,
        a4,
        FileInformationClass);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != (CObjectMonitor *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v13 + 108) & 4) != 0 )
      {
        v20 = RestartScan;
        v21 = ReturnSingleEntry;
        SyncTraceOutputInternal(
          L"SyncQueryDirectory: ReturnSingleEntry: %d FileName: 0x%p RestartScan: %d",
          ReturnSingleEntry,
          FileName,
          RestartScan);
        WPP_SF_dqd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          96,
          WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids,
          v21,
          FileName,
          v20);
        v13 = WPP_GLOBAL_Control;
      }
      if ( v13 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 108) & 2) != 0 )
      {
        v22 = L"Yes";
        if ( !v14 )
          v22 = L"No";
        SyncTraceOutputInternal(L"SyncQueryDirectory: StoreHandle: %ws", v22);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 97, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, v22);
        v13 = WPP_GLOBAL_Control;
      }
    }
  }
  if ( !v14 )
  {
    Status = NtQueryDirectoryFile(
               hHandle,
               0,
               0,
               0,
               &v28,
               a3,
               a4,
               FileInformationClass,
               ReturnSingleEntry,
               FileName,
               RestartScan);
    if ( Status == 259 )
    {
      if ( WaitForSingleObject(hHandle, 0x3E8u) )
      {
        Status = 258;
        goto LABEL_37;
      }
      Status = v28.Status;
    }
    if ( (Status & 0xC0000000) == 0xC0000000 )
    {
      Information_low = 0;
LABEL_13:
      v30 = Information_low;
      goto LABEL_14;
    }
LABEL_37:
    Information_low = LODWORD(v28.Information);
    goto LABEL_13;
  }
  if ( v13 != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v13 + 108) & 4) != 0 )
    {
      LODWORD(FileInformation) = FileInformationClass;
      LODWORD(IoStatusBlock) = a4;
      SyncTraceOutputInternal(
        L"SyncQueryDirectoryLocal: Handle: 0x%p BytesTransferred: 0x%p Buffer: 0x%p Size: %d FileInfoClass: 0x%x",
        hHandle,
        &v30,
        a3,
        IoStatusBlock,
        FileInformation);
      WPP_SF_qqqdD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        50,
        WPP_f707efbc203434f979e24425cc714701_Traceguids,
        hHandle,
        &v30,
        a3,
        a4,
        FileInformationClass);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 108) & 4) != 0 )
    {
      v23 = RestartScan;
      v24 = ReturnSingleEntry;
      v25 = FileName;
      SyncTraceOutputInternal(
        L"SyncQueryDirectoryLocal: ReturnSingleEntry: %d FileName: 0x%p RestartScan: %d",
        ReturnSingleEntry,
        FileName,
        RestartScan);
      WPP_SF_dqd(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        51,
        WPP_f707efbc203434f979e24425cc714701_Traceguids,
        v24,
        v25,
        v23);
    }
  }
  v29 = 0;
  v19 = NtQueryDirectoryFile(
          hHandle,
          0,
          0,
          0,
          &v29,
          a3,
          a4,
          FileInformationClass,
          ReturnSingleEntry,
          FileName,
          RestartScan);
  Information_low = LODWORD(v29.Information);
  Status = v19;
  if ( (v19 & 0xC0000000) == 0xC0000000 )
    Information_low = 0;
  v30 = Information_low;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncQueryDirectoryLocal: 0x%x", v19);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 52, WPP_f707efbc203434f979e24425cc714701_Traceguids, Status);
    Information_low = v30;
  }
LABEL_14:
  if ( a2 )
    *a2 = Information_low;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncQueryDirectory: byte transferred : %d status: 0x%x", Information_low, Status);
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 98, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, v30, Status);
  }
  return Status;
}

```

## disassembly

```asm
0x1800134c0  mov     rax, rsp
0x1800134c3  push    rbx
0x1800134c4  sub     rsp, 0A0h
0x1800134cb  mov     [rax+8], rbp
0x1800134cf  xorps   xmm0, xmm0
0x1800134d2  mov     [rax+18h], rsi
0x1800134d6  mov     rsi, rdx
0x1800134d9  mov     [rax+20h], rdi
0x1800134dd  mov     [rax-10h], r12
0x1800134e1  mov     r12, r8
0x1800134e4  mov     [rax-18h], r13
0x1800134e8  mov     [rax-20h], r14
0x1800134ec  mov     r14, rcx
0x1800134ef  mov     [rax-28h], r15
0x1800134f3  mov     r15d, r9d
0x1800134f6  movups  xmmword ptr [rax-48h], xmm0
0x1800134fa  mov     dword ptr [rax+10h], 0
0x180013501  mov     rax, cs:WPP_GLOBAL_Control
0x180013508  lea     rdi, WPP_GLOBAL_Control
0x18001350f  movzx   ebp, [rsp+0A8h+arg_40]
0x180013517  mov     r13d, [rsp+0A8h+arg_20]
0x18001351f  cmp     rax, rdi
0x180013522  jz      short loc_18001354C
0x180013524  test    byte ptr [rax+6Ch], 4
0x180013528  jnz     loc_1800136FF
0x18001352e  cmp     rax, rdi
0x180013531  jz      short loc_18001354C
0x180013533  test    byte ptr [rax+6Ch], 4
0x180013537  jnz     loc_18001375D
0x18001353d  cmp     rax, rdi
0x180013540  jz      short loc_18001354C
0x180013542  test    byte ptr [rax+6Ch], 2
0x180013546  jnz     loc_1800137C9
0x18001354c  test    bpl, bpl
0x18001354f  jnz     loc_18001362C
0x180013555  movzx   eax, [rsp+0A8h+arg_38]
0x18001355d  xor     r9d, r9d; ApcContext
0x180013560  mov     [rsp+0A8h+RestartScan], al; RestartScan
0x180013564  xor     r8d, r8d; ApcRoutine
0x180013567  mov     rax, [rsp+0A8h+arg_30]
0x18001356f  xor     edx, edx; Event
0x180013571  mov     [rsp+0A8h+FileName], rax; FileName
0x180013576  mov     rcx, r14; FileHandle
0x180013579  movzx   eax, [rsp+0A8h+arg_28]
0x180013581  mov     [rsp+0A8h+ReturnSingleEntry], al; ReturnSingleEntry
0x180013585  lea     rax, [rsp+0A8h+var_48]
0x18001358a  mov     [rsp+0A8h+FileInformationClass], r13d; FileInformationClass
0x18001358f  mov     [rsp+0A8h+Length], r15d; Length
0x180013594  mov     [rsp+0A8h+FileInformation], r12; FileInformation
0x180013599  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x18001359e  call    cs:__imp_NtQueryDirectoryFile
0x1800135a4  mov     ebx, eax
0x1800135a6  cmp     eax, 103h
0x1800135ab  jz      loc_1800138F7
0x1800135b1  mov     eax, ebx
0x1800135b3  and     eax, 0C0000000h
0x1800135b8  cmp     eax, 0C0000000h
0x1800135bd  jnz     loc_180013917
0x1800135c3  xor     edx, edx
0x1800135c5  mov     [rsp+0A8h+arg_8], edx
0x1800135cc  mov     r15, [rsp+0A8h+var_28]
0x1800135d4  mov     r14, [rsp+0A8h+var_20]
0x1800135dc  mov     r13, [rsp+0A8h+var_18]
0x1800135e4  mov     r12, [rsp+0A8h+var_10]
0x1800135ec  mov     rbp, [rsp+0A8h+arg_0]
0x1800135f4  test    rsi, rsi
0x1800135f7  jz      short loc_1800135FB
0x1800135f9  mov     [rsi], edx
0x1800135fb  mov     rax, cs:WPP_GLOBAL_Control
0x180013602  mov     rsi, [rsp+0A8h+arg_10]
0x18001360a  cmp     rax, rdi
0x18001360d  mov     rdi, [rsp+0A8h+arg_18]
0x180013615  jz      short loc_180013621
0x180013617  test    byte ptr [rax+6Ch], 8
0x18001361b  jnz     loc_180013920
0x180013621  mov     eax, ebx
0x180013623  add     rsp, 0A0h
0x18001362a  pop     rbx
0x18001362b  retn
0x18001362c  cmp     rax, rdi
0x18001362f  jnz     loc_180013818
0x180013635  movzx   eax, [rsp+0A8h+arg_38]
0x18001363d  xorps   xmm0, xmm0
0x180013640  mov     [rsp+0A8h+RestartScan], al; RestartScan
0x180013644  xor     r9d, r9d; ApcContext
0x180013647  mov     rax, [rsp+0A8h+arg_30]
0x18001364f  xor     r8d, r8d; ApcRoutine
0x180013652  mov     [rsp+0A8h+FileName], rax; FileName
0x180013657  xor     edx, edx; Event
0x180013659  movzx   eax, [rsp+0A8h+arg_28]
0x180013661  mov     rcx, r14; FileHandle
0x180013664  mov     [rsp+0A8h+ReturnSingleEntry], al; ReturnSingleEntry
0x180013668  lea     rax, [rsp+0A8h+var_38]
0x18001366d  mov     [rsp+0A8h+FileInformationClass], r13d; FileInformationClass
0x180013672  mov     [rsp+0A8h+Length], r15d; Length
0x180013677  mov     [rsp+0A8h+FileInformation], r12; FileInformation
0x18001367c  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x180013681  movups  xmmword ptr [rsp+0A8h+var_38], xmm0
0x180013686  call    cs:__imp_NtQueryDirectoryFile
0x18001368c  mov     edx, dword ptr [rsp+0A8h+var_38.Information]
0x180013690  mov     ecx, eax
0x180013692  mov     ebx, eax
0x180013694  and     ecx, 0C0000000h
0x18001369a  xor     eax, eax
0x18001369c  cmp     ecx, 0C0000000h
0x1800136a2  cmovz   edx, eax
0x1800136a5  mov     [rsp+0A8h+arg_8], edx
0x1800136ac  mov     rax, cs:WPP_GLOBAL_Control
0x1800136b3  cmp     rax, rdi
0x1800136b6  jz      loc_1800135CC
0x1800136bc  test    byte ptr [rax+6Ch], 8
0x1800136c0  jz      loc_1800135CC
0x1800136c6  mov     edx, ebx
0x1800136c8  lea     rcx, aSyncquerydirec_3; "SyncQueryDirectoryLocal: 0x%x"
0x1800136cf  call    SyncTraceOutputInternal
0x1800136d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136db  lea     r8, WPP_f707efbc203434f979e24425cc714701_Traceguids
0x1800136e2  mov     edx, 34h ; '4'
0x1800136e7  mov     r9d, ebx
0x1800136ea  mov     rcx, [rcx+60h]
0x1800136ee  call    WPP_SF_d
0x1800136f3  mov     edx, [rsp+0A8h+arg_8]
0x1800136fa  jmp     loc_1800135CC
0x1800136ff  mov     dword ptr [rsp+0A8h+FileInformation], r13d
0x180013704  lea     rcx, aSyncquerydirec_1; "SyncQueryDirectory: Handle: 0x%p BytesT"...
0x18001370b  mov     r9, r12
0x18001370e  mov     dword ptr [rsp+0A8h+IoStatusBlock], r15d
0x180013713  mov     r8, rsi
0x180013716  mov     rdx, r14
0x180013719  call    SyncTraceOutputInternal
0x18001371e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013725  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x18001372c  mov     [rsp+0A8h+FileInformationClass], r13d
0x180013731  mov     edx, 5Fh ; '_'
0x180013736  mov     [rsp+0A8h+Length], r15d
0x18001373b  mov     r9, r14
0x18001373e  mov     [rsp+0A8h+FileInformation], r12
0x180013743  mov     rcx, [rcx+60h]
0x180013747  mov     [rsp+0A8h+IoStatusBlock], rsi
0x18001374c  call    WPP_SF_qqqdD
0x180013751  mov     rax, cs:WPP_GLOBAL_Control
0x180013758  jmp     loc_18001352E
0x18001375d  movzx   ebx, [rsp+0A8h+arg_38]
0x180013765  lea     rcx, aSyncquerydirec_5; "SyncQueryDirectory: ReturnSingleEntry: "...
0x18001376c  movzx   edi, [rsp+0A8h+arg_28]
0x180013774  mov     r9d, ebx
0x180013777  mov     r8, [rsp+0A8h+arg_30]
0x18001377f  mov     edx, edi
0x180013781  call    SyncTraceOutputInternal
0x180013786  mov     rcx, cs:WPP_GLOBAL_Control
0x18001378d  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180013794  mov     rax, [rsp+0A8h+arg_30]
0x18001379c  mov     edx, 60h ; '`'
0x1800137a1  mov     dword ptr [rsp+0A8h+FileInformation], ebx
0x1800137a5  mov     r9d, edi
0x1800137a8  mov     [rsp+0A8h+IoStatusBlock], rax
0x1800137ad  mov     rcx, [rcx+60h]
0x1800137b1  call    WPP_SF_dqd
0x1800137b6  mov     rax, cs:WPP_GLOBAL_Control
0x1800137bd  lea     rdi, WPP_GLOBAL_Control
0x1800137c4  jmp     loc_18001353D
0x1800137c9  lea     rax, aNo; "No"
0x1800137d0  test    bpl, bpl
0x1800137d3  lea     rbx, aYes_0; "Yes"
0x1800137da  cmovz   rbx, rax
0x1800137de  lea     rcx, aSyncquerydirec_4; "SyncQueryDirectory: StoreHandle: %ws"
0x1800137e5  mov     rdx, rbx
0x1800137e8  call    SyncTraceOutputInternal
0x1800137ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137f4  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x1800137fb  mov     edx, 61h ; 'a'
0x180013800  mov     r9, rbx
0x180013803  mov     rcx, [rcx+60h]
0x180013807  call    WPP_SF_S
0x18001380c  mov     rax, cs:WPP_GLOBAL_Control
0x180013813  jmp     loc_18001354C
0x180013818  test    byte ptr [rax+6Ch], 4
0x18001381c  jz      short loc_180013884
0x18001381e  mov     dword ptr [rsp+0A8h+FileInformation], r13d
0x180013823  lea     r8, [rsp+0A8h+arg_8]
0x18001382b  mov     r9, r12
0x18001382e  mov     dword ptr [rsp+0A8h+IoStatusBlock], r15d
0x180013833  mov     rdx, r14
0x180013836  lea     rcx, aSyncquerydirec_2; "SyncQueryDirectoryLocal: Handle: 0x%p B"...
0x18001383d  call    SyncTraceOutputInternal
0x180013842  mov     rcx, cs:WPP_GLOBAL_Control
0x180013849  lea     rax, [rsp+0A8h+arg_8]
0x180013851  mov     [rsp+0A8h+FileInformationClass], r13d
0x180013856  lea     r8, WPP_f707efbc203434f979e24425cc714701_Traceguids
0x18001385d  mov     [rsp+0A8h+Length], r15d
0x180013862  mov     edx, 32h ; '2'
0x180013867  mov     [rsp+0A8h+FileInformation], r12
0x18001386c  mov     r9, r14
0x18001386f  mov     rcx, [rcx+60h]
0x180013873  mov     [rsp+0A8h+IoStatusBlock], rax
0x180013878  call    WPP_SF_qqqdD
0x18001387d  mov     rax, cs:WPP_GLOBAL_Control
0x180013884  cmp     rax, rdi
0x180013887  jz      loc_180013635
0x18001388d  test    byte ptr [rax+6Ch], 4
0x180013891  jz      loc_180013635
0x180013897  movzx   ebx, [rsp+0A8h+arg_38]
0x18001389f  lea     rcx, aSyncquerydirec; "SyncQueryDirectoryLocal: ReturnSingleEn"...
0x1800138a6  movzx   edi, [rsp+0A8h+arg_28]
0x1800138ae  mov     r9d, ebx
0x1800138b1  mov     rbp, [rsp+0A8h+arg_30]
0x1800138b9  mov     edx, edi
0x1800138bb  mov     r8, rbp
0x1800138be  call    SyncTraceOutputInternal
0x1800138c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138ca  lea     r8, WPP_f707efbc203434f979e24425cc714701_Traceguids
0x1800138d1  mov     edx, 33h ; '3'
0x1800138d6  mov     dword ptr [rsp+0A8h+FileInformation], ebx
0x1800138da  mov     r9d, edi
0x1800138dd  mov     [rsp+0A8h+IoStatusBlock], rbp
0x1800138e2  mov     rcx, [rcx+60h]
0x1800138e6  call    WPP_SF_dqd
0x1800138eb  lea     rdi, WPP_GLOBAL_Control
0x1800138f2  jmp     loc_180013635
0x1800138f7  mov     edx, 3E8h; dwMilliseconds
0x1800138fc  mov     rcx, r14; hHandle
0x1800138ff  call    cs:__imp_WaitForSingleObject
0x180013905  test    eax, eax
0x180013907  jnz     short loc_180013912
0x180013909  mov     ebx, dword ptr [rsp+0A8h+var_48]
0x18001390d  jmp     loc_1800135B1
0x180013912  mov     ebx, 102h
0x180013917  mov     edx, dword ptr [rsp+0A8h+var_48.Information]
0x18001391b  jmp     loc_1800135C5
0x180013920  mov     r8d, ebx
0x180013923  lea     rcx, aSyncquerydirec_0; "SyncQueryDirectory: byte transferred : "...
0x18001392a  call    SyncTraceOutputInternal
0x18001392f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013936  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x18001393d  mov     r9d, [rsp+0A8h+arg_8]
0x180013945  mov     edx, 62h ; 'b'
0x18001394a  mov     dword ptr [rsp+0A8h+IoStatusBlock], ebx
0x18001394e  mov     rcx, [rcx+60h]
0x180013952  call    WPP_SF_dd
0x180013957  jmp     loc_180013621
```
