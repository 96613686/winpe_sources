# CMachine::QuerySmBiosData(void * *)

- ea: `0x180041584`
- end: `0x180041bb0`
- name: `?QuerySmBiosData@CMachine@@AEAAJPEAPEAX@Z`
- size: `1580`
- prototype: `__int64 __fastcall(CMachine *__hidden this, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18003ed44`

## callees

- `0x180006210`
- `0x18000624c`
- `0x180006d02`
- `0x180007014`
- `0x180041584`
- `0x18006041c`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180041639`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180041639`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004177f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004177f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004164b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004178d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004184e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800419bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004164b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004178d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004184e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800419bb`

## string_xrefs

- `0x180041598`: `Attempting to read SMBIOS data`
- `0x1800419d0`: `Unable to write to buffer with 0x%08x`
- `0x180041a66`: `Read SMBIOS data into buffer`
- `0x180041ab3`: `Read SMBIOS data into buffer`
- `0x180041adf`: `Read SMBIOS data into buffer`

## pseudocode

```c
__int64 __fastcall CMachine::QuerySmBiosData(CMachine *this, unsigned int **a2)
{
  FILE *v3; // rax
  FILE *v4; // rax
  FILE *v5; // rax
  HMODULE ModuleHandleW; // rbx
  signed int LastError; // eax
  unsigned int v8; // ebx
  const char *v9; // rdi
  __int64 v10; // rsi
  FILE *v11; // rax
  FILE *v12; // rax
  FILE *v13; // rax
  FILE *v14; // rax
  FILE *v15; // rax
  FILE *v16; // rax
  FARPROC ProcAddress; // rbx
  signed int v18; // eax
  FILE *v19; // rax
  FILE *v20; // rax
  FILE *v21; // rax
  unsigned int v22; // eax
  unsigned __int64 v23; // rsi
  signed int v24; // eax
  FILE *v25; // rax
  FILE *v26; // rax
  FILE *v27; // rax
  unsigned int *v28; // rax
  unsigned int *v29; // rdi
  FILE *v30; // rax
  FILE *v31; // rax
  FILE *v32; // rax
  unsigned int v33; // eax
  unsigned __int64 v34; // rbx
  signed int v35; // eax
  FILE *v36; // rax
  FILE *v37; // rax
  FILE *v38; // rax
  FILE *v39; // rax
  FILE *v40; // rax
  FILE *v41; // rax
  FILE *v42; // rax
  FILE *v43; // rax
  FILE *v44; // rax

  AslLogCallPrintf(3, "CMachine::QuerySmBiosData", 1055, "Attempting to read SMBIOS data");
  if ( EnableDevInvStdErrLog )
  {
    v3 = o___acrt_iob_func_0(2u);
    fprintf(v3, "Info: %s, %u: ", "CMachine::QuerySmBiosData", 1055);
    v4 = o___acrt_iob_func_0(2u);
    fprintf(v4, "Attempting to read SMBIOS data");
    v5 = o___acrt_iob_func_0(2u);
    fprintf(v5, "\n");
  }
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(0x4000000, "Attempting to read SMBIOS data");
  *a2 = 0;
  ModuleHandleW = GetModuleHandleW(L"kernel32");
  if ( !ModuleHandleW )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = "GetModuleHandle failed with 0x%08x";
    v10 = 1063;
LABEL_9:
    AslLogCallPrintf(2, "CMachine::QuerySmBiosData", v10, v9, v8);
    if ( EnableDevInvStdErrLog )
    {
      v11 = o___acrt_iob_func_0(2u);
      fprintf(v11, "Error: %s, %u: ", "CMachine::QuerySmBiosData", v10);
      v12 = o___acrt_iob_func_0(2u);
      fprintf(v12, v9, v8);
      v13 = o___acrt_iob_func_0(2u);
      fprintf(v13, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, v9, v8);
    return v8;
  }
  AslLogCallPrintf(3, "CMachine::QuerySmBiosData", 1067, "Got a handle to kernel32");
  if ( EnableDevInvStdErrLog )
  {
    v14 = o___acrt_iob_func_0(2u);
    fprintf(v14, "Info: %s, %u: ", "CMachine::QuerySmBiosData", 1067);
    v15 = o___acrt_iob_func_0(2u);
    fprintf(v15, "Got a handle to kernel32");
    v16 = o___acrt_iob_func_0(2u);
    fprintf(v16, "\n");
  }
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(0x4000000, "Got a handle to kernel32");
  ProcAddress = GetProcAddress(ModuleHandleW, "GetSystemFirmwareTable");
  if ( !ProcAddress )
  {
    v18 = GetLastError();
    v8 = v18;
    if ( v18 > 0 )
      v8 = (unsigned __int16)v18 | 0x80070000;
    v9 = "GetProcAddress failed with 0x%08x";
    v10 = 1073;
    goto LABEL_9;
  }
  AslLogCallPrintf(3, "CMachine::QuerySmBiosData", 1076, "Got function address to GetSystemFirmware");
  if ( EnableDevInvStdErrLog )
  {
    v19 = o___acrt_iob_func_0(2u);
    fprintf(v19, "Info: %s, %u: ", "CMachine::QuerySmBiosData", 1076);
    v20 = o___acrt_iob_func_0(2u);
    fprintf(v20, "Got function address to GetSystemFirmware");
    v21 = o___acrt_iob_func_0(2u);
    fprintf(v21, "\n");
  }
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(0x4000000, "Got function address to GetSystemFirmware");
  v22 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))ProcAddress)(1381190978, 0, 0, 0);
  v23 = v22;
  if ( v22 )
  {
    AslLogCallPrintf(3, "CMachine::QuerySmBiosData", 1086, "Queried SMBIOS data size");
    if ( EnableDevInvStdErrLog )
    {
      v25 = o___acrt_iob_func_0(2u);
      fprintf(v25, "Info: %s, %u: ", "CMachine::QuerySmBiosData", 1086);
      v26 = o___acrt_iob_func_0(2u);
      fprintf(v26, "Queried SMBIOS data size");
      v27 = o___acrt_iob_func_0(2u);
      fprintf(v27, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x4000000, "Queried SMBIOS data size");
    v28 = (unsigned int *)operator new[](v23, (const struct std::nothrow_t *)std::nothrow);
    v29 = v28;
    if ( v28 )
    {
      v33 = ((__int64 (__fastcall *)(__int64, _QWORD, unsigned int *, _QWORD))ProcAddress)(
              1381190978,
              0,
              v28,
              (unsigned int)v23);
      v34 = v33;
      if ( v33 )
      {
        AslLogCallPrintf(3, "CMachine::QuerySmBiosData", 1105, "Read SMBIOS data into buffer");
        if ( EnableDevInvStdErrLog )
        {
          v39 = o___acrt_iob_func_0(2u);
          fprintf(v39, "Info: %s, %u: ", "CMachine::QuerySmBiosData", 1105);
          v40 = o___acrt_iob_func_0(2u);
          fprintf(v40, "Read SMBIOS data into buffer");
          v41 = o___acrt_iob_func_0(2u);
          fprintf(v41, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x4000000, "Read SMBIOS data into buffer");
        if ( (unsigned int)v34 <= (unsigned int)v23 && (unsigned int)v34 >= 9 && (unsigned __int64)v29[1] + 8 <= v34 )
        {
          v8 = 0;
          *a2 = v29;
          return v8;
        }
        v8 = -2147418113;
        AslLogCallPrintf(2, "CMachine::QuerySmBiosData", 1115, "Bytes written to buffer does not match size of buffer");
        if ( EnableDevInvStdErrLog )
        {
          v42 = o___acrt_iob_func_0(2u);
          fprintf(v42, "Error: %s, %u: ", "CMachine::QuerySmBiosData", 1115);
          v43 = o___acrt_iob_func_0(2u);
          fprintf(v43, "Bytes written to buffer does not match size of buffer");
          v44 = o___acrt_iob_func_0(2u);
          fprintf(v44, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "Bytes written to buffer does not match size of buffer");
      }
      else
      {
        v35 = GetLastError();
        v8 = v35;
        if ( v35 > 0 )
          v8 = (unsigned __int16)v35 | 0x80070000;
        AslLogCallPrintf(2, "CMachine::QuerySmBiosData", 1102, "Unable to write to buffer with 0x%08x", v8);
        if ( EnableDevInvStdErrLog )
        {
          v36 = o___acrt_iob_func_0(2u);
          fprintf(v36, "Error: %s, %u: ", "CMachine::QuerySmBiosData", 1102);
          v37 = o___acrt_iob_func_0(2u);
          fprintf(v37, "Unable to write to buffer with 0x%08x", v8);
          v38 = o___acrt_iob_func_0(2u);
          fprintf(v38, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "Unable to write to buffer with 0x%08x", v8);
      }
      operator delete(v29);
      return v8;
    }
    v8 = -2147024882;
    AslLogCallPrintf(2, "CMachine::QuerySmBiosData", 1093, "Out of memory");
    if ( EnableDevInvStdErrLog )
    {
      v30 = o___acrt_iob_func_0(2u);
      fprintf(v30, "Error: %s, %u: ", "CMachine::QuerySmBiosData", 1093);
      v31 = o___acrt_iob_func_0(2u);
      fprintf(v31, "Out of memory");
      v32 = o___acrt_iob_func_0(2u);
      fprintf(v32, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "Out of memory");
  }
  else
  {
    v24 = GetLastError();
    v8 = v24;
    if ( v24 > 0 )
      return (unsigned __int16)v24 | 0x80070000;
  }
  return v8;
}

```

## disassembly

```asm
0x180041584  push    rbx
0x180041586  push    rbp
0x180041587  push    rsi
0x180041588  push    rdi
0x180041589  push    r12
0x18004158b  push    r13
0x18004158d  push    r14
0x18004158f  push    r15
0x180041591  sub     rsp, 38h
0x180041595  mov     r14, rdx
0x180041598  lea     rbx, aAttemptingToRe; "Attempting to read SMBIOS data"
0x18004159f  mov     esi, 41Fh
0x1800415a4  lea     r12, aCmachineQuerys; "CMachine::QuerySmBiosData"
0x1800415ab  mov     edi, 3
0x1800415b0  mov     r9, rbx
0x1800415b3  mov     r8d, esi
0x1800415b6  mov     rdx, r12
0x1800415b9  mov     ecx, edi
0x1800415bb  call    AslLogCallPrintf
0x1800415c0  xor     ebp, ebp
0x1800415c2  lea     r15d, [rdi-1]
0x1800415c6  cmp     cs:EnableDevInvStdErrLog, ebp
0x1800415cc  jz      short loc_180041615
0x1800415ce  mov     ecx, r15d; Ix
0x1800415d1  call    _o___acrt_iob_func_0
0x1800415d6  mov     rcx, rax; Stream
0x1800415d9  lea     rdx, aInfoSU; "Info: %s, %u: "
0x1800415e0  mov     r9d, esi
0x1800415e3  mov     r8, r12
0x1800415e6  call    fprintf
0x1800415eb  mov     ecx, r15d; Ix
0x1800415ee  call    _o___acrt_iob_func_0
0x1800415f3  mov     rcx, rax; Stream
0x1800415f6  mov     rdx, rbx; Format
0x1800415f9  call    fprintf
0x1800415fe  mov     ecx, r15d; Ix
0x180041601  call    _o___acrt_iob_func_0
0x180041606  mov     rcx, rax; Stream
0x180041609  lea     rdx, asc_18011EAD8; "\n"
0x180041610  call    fprintf
0x180041615  cmp     cs:g_DeviceMapLogFunction, rbp
0x18004161c  mov     r13d, 4000000h
0x180041622  jz      short loc_18004162F
0x180041624  mov     rdx, rbx
0x180041627  mov     ecx, r13d
0x18004162a  call    TraceMessageCallback
0x18004162f  lea     rcx, aKernel32; "kernel32"
0x180041636  mov     [r14], rbp
0x180041639  call    cs:__imp_GetModuleHandleW
0x18004163f  mov     rbx, rax
0x180041642  test    rax, rax
0x180041645  jnz     loc_1800416F5
0x18004164b  call    cs:__imp_GetLastError
0x180041651  mov     ebx, eax
0x180041653  test    eax, eax
0x180041655  jle     short loc_180041660
0x180041657  movzx   ebx, ax
0x18004165a  or      ebx, 80070000h
0x180041660  lea     rdi, aGetmodulehandl; "GetModuleHandle failed with 0x%08x"
0x180041667  mov     esi, 427h
0x18004166c  mov     r9, rdi
0x18004166f  mov     [rsp+78h+var_58], ebx
0x180041673  mov     r8, rsi
0x180041676  mov     rdx, r12
0x180041679  mov     ecx, r15d
0x18004167c  call    AslLogCallPrintf
0x180041681  cmp     cs:EnableDevInvStdErrLog, ebp
0x180041687  jz      short loc_1800416D3
0x180041689  mov     ecx, r15d; Ix
0x18004168c  call    _o___acrt_iob_func_0
0x180041691  mov     rcx, rax; Stream
0x180041694  lea     rdx, Format; "Error: %s, %u: "
0x18004169b  mov     r9d, esi
0x18004169e  mov     r8, r12
0x1800416a1  call    fprintf
0x1800416a6  mov     ecx, r15d; Ix
0x1800416a9  call    _o___acrt_iob_func_0
0x1800416ae  mov     rcx, rax; Stream
0x1800416b1  mov     r8d, ebx
0x1800416b4  mov     rdx, rdi; Format
0x1800416b7  call    fprintf
0x1800416bc  mov     ecx, r15d; Ix
0x1800416bf  call    _o___acrt_iob_func_0
0x1800416c4  mov     rcx, rax; Stream
0x1800416c7  lea     rdx, asc_18011EAD8; "\n"
0x1800416ce  call    fprintf
0x1800416d3  cmp     cs:g_DeviceMapLogFunction, rbp
0x1800416da  jz      loc_180041B9D
0x1800416e0  mov     r8d, ebx
0x1800416e3  mov     rdx, rdi
0x1800416e6  mov     ecx, 2000000h
0x1800416eb  call    TraceMessageCallback
0x1800416f0  jmp     loc_180041B9D
0x1800416f5  lea     rsi, aGotAHandleToKe; "Got a handle to kernel32"
0x1800416fc  mov     r8d, 42Bh
0x180041702  mov     r9, rsi
0x180041705  mov     rdx, r12
0x180041708  mov     ecx, edi
0x18004170a  call    AslLogCallPrintf
0x18004170f  cmp     cs:EnableDevInvStdErrLog, ebp
0x180041715  jz      short loc_180041761
0x180041717  mov     ecx, r15d; Ix
0x18004171a  call    _o___acrt_iob_func_0
0x18004171f  mov     rcx, rax; Stream
0x180041722  lea     rdx, aInfoSU; "Info: %s, %u: "
0x180041729  mov     r9d, 42Bh
0x18004172f  mov     r8, r12
0x180041732  call    fprintf
0x180041737  mov     ecx, r15d; Ix
0x18004173a  call    _o___acrt_iob_func_0
0x18004173f  mov     rcx, rax; Stream
0x180041742  mov     rdx, rsi; Format
0x180041745  call    fprintf
0x18004174a  mov     ecx, r15d; Ix
0x18004174d  call    _o___acrt_iob_func_0
0x180041752  mov     rcx, rax; Stream
0x180041755  lea     rdx, asc_18011EAD8; "\n"
0x18004175c  call    fprintf
0x180041761  cmp     cs:g_DeviceMapLogFunction, rbp
0x180041768  jz      short loc_180041775
0x18004176a  mov     rdx, rsi
0x18004176d  mov     ecx, r13d
0x180041770  call    TraceMessageCallback
0x180041775  lea     rdx, aGetsystemfirmw; "GetSystemFirmwareTable"
0x18004177c  mov     rcx, rbx; hModule
0x18004177f  call    cs:__imp_GetProcAddress
0x180041785  mov     rbx, rax
0x180041788  test    rax, rax
0x18004178b  jnz     short loc_1800417B3
0x18004178d  call    cs:__imp_GetLastError
0x180041793  mov     ebx, eax
0x180041795  test    eax, eax
0x180041797  jle     short loc_1800417A2
0x180041799  movzx   ebx, ax
0x18004179c  or      ebx, 80070000h
0x1800417a2  lea     rdi, aGetprocaddress_2; "GetProcAddress failed with 0x%08x"
0x1800417a9  mov     esi, 431h
0x1800417ae  jmp     loc_18004166C
0x1800417b3  lea     rsi, aGotFunctionAdd; "Got function address to GetSystemFirmwa"...
0x1800417ba  mov     r8d, 434h
0x1800417c0  mov     r9, rsi
0x1800417c3  mov     rdx, r12
0x1800417c6  mov     ecx, edi
0x1800417c8  call    AslLogCallPrintf
0x1800417cd  cmp     cs:EnableDevInvStdErrLog, ebp
0x1800417d3  jz      short loc_18004181F
0x1800417d5  mov     ecx, r15d; Ix
0x1800417d8  call    _o___acrt_iob_func_0
0x1800417dd  mov     rcx, rax; Stream
0x1800417e0  lea     rdx, aInfoSU; "Info: %s, %u: "
0x1800417e7  mov     r9d, 434h
0x1800417ed  mov     r8, r12
0x1800417f0  call    fprintf
0x1800417f5  mov     ecx, r15d; Ix
0x1800417f8  call    _o___acrt_iob_func_0
0x1800417fd  mov     rcx, rax; Stream
0x180041800  mov     rdx, rsi; Format
0x180041803  call    fprintf
0x180041808  mov     ecx, r15d; Ix
0x18004180b  call    _o___acrt_iob_func_0
0x180041810  mov     rcx, rax; Stream
0x180041813  lea     rdx, asc_18011EAD8; "\n"
0x18004181a  call    fprintf
0x18004181f  cmp     cs:g_DeviceMapLogFunction, rbp
0x180041826  jz      short loc_180041833
0x180041828  mov     rdx, rsi
0x18004182b  mov     ecx, r13d
0x18004182e  call    TraceMessageCallback
0x180041833  xor     r9d, r9d
0x180041836  xor     r8d, r8d
0x180041839  xor     edx, edx
0x18004183b  mov     ecx, 52534D42h
0x180041840  mov     rax, rbx
0x180041843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041848  mov     esi, eax
0x18004184a  test    eax, eax
0x18004184c  jnz     short loc_18004186C
0x18004184e  call    cs:__imp_GetLastError
0x180041854  mov     ebx, eax
0x180041856  test    eax, eax
0x180041858  jle     loc_180041B9D
0x18004185e  movzx   ebx, ax
0x180041861  or      ebx, 80070000h
0x180041867  jmp     loc_180041B9D
0x18004186c  lea     r9, aQueriedSmbiosD; "Queried SMBIOS data size"
0x180041873  mov     r8d, 43Eh
0x180041879  mov     rdx, r12
0x18004187c  mov     ecx, edi
0x18004187e  call    AslLogCallPrintf
0x180041883  cmp     cs:EnableDevInvStdErrLog, ebp
0x180041889  jz      short loc_1800418D9
0x18004188b  mov     ecx, r15d; Ix
0x18004188e  call    _o___acrt_iob_func_0
0x180041893  mov     rcx, rax; Stream
0x180041896  lea     rdx, aInfoSU; "Info: %s, %u: "
0x18004189d  mov     r9d, 43Eh
0x1800418a3  mov     r8, r12
0x1800418a6  call    fprintf
0x1800418ab  mov     ecx, r15d; Ix
0x1800418ae  call    _o___acrt_iob_func_0
0x1800418b3  mov     rcx, rax; Stream
0x1800418b6  lea     rdx, aQueriedSmbiosD; "Queried SMBIOS data size"
0x1800418bd  call    fprintf
0x1800418c2  mov     ecx, r15d; Ix
0x1800418c5  call    _o___acrt_iob_func_0
0x1800418ca  mov     rcx, rax; Stream
0x1800418cd  lea     rdx, asc_18011EAD8; "\n"
0x1800418d4  call    fprintf
0x1800418d9  cmp     cs:g_DeviceMapLogFunction, rbp
0x1800418e0  jz      short loc_1800418F1
0x1800418e2  lea     rdx, aQueriedSmbiosD; "Queried SMBIOS data size"
0x1800418e9  mov     ecx, r13d
0x1800418ec  call    TraceMessageCallback
0x1800418f1  mov     rcx, rsi; unsigned __int64
0x1800418f4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800418fb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180041900  mov     rdi, rax
0x180041903  test    rax, rax
0x180041906  jnz     loc_18004199C
0x18004190c  lea     rdi, aOutOfMemory_0; "Out of memory"
0x180041913  mov     esi, 445h
0x180041918  mov     r9, rdi
0x18004191b  mov     r8d, esi
0x18004191e  mov     rdx, r12
0x180041921  mov     ecx, r15d
0x180041924  mov     ebx, 8007000Eh
0x180041929  call    AslLogCallPrintf
0x18004192e  cmp     cs:EnableDevInvStdErrLog, ebp
0x180041934  jz      short loc_18004197D
0x180041936  mov     ecx, r15d; Ix
0x180041939  call    _o___acrt_iob_func_0
0x18004193e  mov     rcx, rax; Stream
0x180041941  lea     rdx, Format; "Error: %s, %u: "
0x180041948  mov     r9d, esi
0x18004194b  mov     r8, r12
0x18004194e  call    fprintf
0x180041953  mov     ecx, r15d; Ix
0x180041956  call    _o___acrt_iob_func_0
0x18004195b  mov     rcx, rax; Stream
0x18004195e  mov     rdx, rdi; Format
0x180041961  call    fprintf
0x180041966  mov     ecx, r15d; Ix
0x180041969  call    _o___acrt_iob_func_0
0x18004196e  mov     rcx, rax; Stream
0x180041971  lea     rdx, asc_18011EAD8; "\n"
0x180041978  call    fprintf
0x18004197d  cmp     cs:g_DeviceMapLogFunction, rbp
0x180041984  jz      loc_180041B9D
0x18004198a  mov     rdx, rdi
0x18004198d  mov     ecx, 2000000h
0x180041992  call    TraceMessageCallback
0x180041997  jmp     loc_180041B9D
0x18004199c  mov     r9d, esi
0x18004199f  mov     r8, rdi
0x1800419a2  xor     edx, edx
0x1800419a4  mov     ecx, 52534D42h
0x1800419a9  mov     rax, rbx
0x1800419ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800419b1  mov     ebx, eax
0x1800419b3  test    eax, eax
0x1800419b5  jnz     loc_180041A66
0x1800419bb  call    cs:__imp_GetLastError
0x1800419c1  mov     ebx, eax
0x1800419c3  test    eax, eax
0x1800419c5  jle     short loc_1800419D0
0x1800419c7  movzx   ebx, ax
0x1800419ca  or      ebx, 80070000h
0x1800419d0  lea     rsi, aUnableToWriteT; "Unable to write to buffer with 0x%08x"
0x1800419d7  mov     [rsp+78h+var_58], ebx
0x1800419db  mov     r14d, 44Eh
0x1800419e1  mov     r9, rsi
0x1800419e4  mov     r8d, r14d
0x1800419e7  mov     rdx, r12
0x1800419ea  mov     ecx, r15d
0x1800419ed  call    AslLogCallPrintf
0x1800419f2  cmp     cs:EnableDevInvStdErrLog, ebp
0x1800419f8  jz      short loc_180041A44
0x1800419fa  mov     ecx, r15d; Ix
0x1800419fd  call    _o___acrt_iob_func_0
0x180041a02  mov     rcx, rax; Stream
0x180041a05  lea     rdx, Format; "Error: %s, %u: "
0x180041a0c  mov     r9d, r14d
0x180041a0f  mov     r8, r12
0x180041a12  call    fprintf
0x180041a17  mov     ecx, r15d; Ix
0x180041a1a  call    _o___acrt_iob_func_0
0x180041a1f  mov     rcx, rax; Stream
0x180041a22  mov     r8d, ebx
0x180041a25  mov     rdx, rsi; Format
0x180041a28  call    fprintf
0x180041a2d  mov     ecx, r15d; Ix
0x180041a30  call    _o___acrt_iob_func_0
0x180041a35  mov     rcx, rax; Stream
0x180041a38  lea     rdx, asc_18011EAD8; "\n"
0x180041a3f  call    fprintf
0x180041a44  cmp     cs:g_DeviceMapLogFunction, rbp
0x180041a4b  jz      loc_180041B95
0x180041a51  mov     r8d, ebx
0x180041a54  mov     rdx, rsi
0x180041a57  mov     ecx, 2000000h
  ... truncated ...
```
