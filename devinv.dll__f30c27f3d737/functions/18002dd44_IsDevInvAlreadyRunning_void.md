# IsDevInvAlreadyRunning(void * &)

- ea: `0x18002dd44`
- end: `0x18002df38`
- name: `?IsDevInvAlreadyRunning@@YA_NAEAPEAX@Z`
- size: `500`
- prototype: `bool __fastcall(void **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180031850`
- `0x180031e30`

## callees

- `0x180006d02`
- `0x180007014`
- `0x18002dd44`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002dd5f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002dd5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ddc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002df1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ddc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002de4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002df1b`

## string_xrefs

- `0x18002dd85`: `unable to create DevInvExclusiveEvent [%d]`
- `0x18002ddd8`: `unable to create DevInvExclusiveEvent [%d]`
- `0x18002de0d`: `unable to create DevInvExclusiveEvent [%d]`
- `0x18002de27`: `unable to create DevInvExclusiveEvent [%d]`
- `0x18002dd90`: `IsDevInvAlreadyRunning`
- `0x18002ddb3`: `IsDevInvAlreadyRunning`
- `0x18002de34`: `IsDevInvAlreadyRunning`
- `0x18002de51`: `IsDevInvAlreadyRunning`
- `0x18002dec0`: `IsDevInvAlreadyRunning`
- `0x18002de64`: `DevInvExclusiveEvent already exists`
- `0x18002de92`: `created DevInvExclusiveEvent`

## pseudocode

```c
char __fastcall IsDevInvAlreadyRunning(void **a1)
{
  HANDLE EventW; // rax
  char v3; // bp
  DWORD LastError; // eax
  FILE *v5; // rax
  DWORD v6; // ebx
  FILE *v7; // rax
  FILE *v8; // rax
  DWORD v9; // eax
  DWORD v10; // eax
  const char *v11; // rbx
  FILE *v12; // rax
  int v13; // r9d
  FILE *v14; // rax
  FILE *v15; // rax

  EventW = CreateEventW(0, 0, 0, L"Global\\DevInvExclusiveEvent");
  *a1 = EventW;
  v3 = 1;
  if ( !EventW )
  {
    LastError = GetLastError();
    AslLogCallPrintf(2, "IsDevInvAlreadyRunning", 71, "unable to create DevInvExclusiveEvent [%d]", LastError);
    if ( EnableDevInvStdErrLog )
    {
      v5 = o___acrt_iob_func_0(2u);
      fprintf(v5, "Error: %s, %u: ", "IsDevInvAlreadyRunning", 71);
      v6 = GetLastError();
      v7 = o___acrt_iob_func_0(2u);
      fprintf(v7, "unable to create DevInvExclusiveEvent [%d]", v6);
      v8 = o___acrt_iob_func_0(2u);
      fprintf(v8, "\n");
    }
    if ( g_DeviceMapLogFunction )
    {
      v9 = GetLastError();
      TraceMessageCallback(0x2000000, "unable to create DevInvExclusiveEvent [%d]", v9);
    }
    v10 = GetLastError();
    AslLogCallPrintf(1, "IsDevInvAlreadyRunning", 71, "unable to create DevInvExclusiveEvent [%d]", v10);
    goto LABEL_15;
  }
  if ( GetLastError() == 183 )
  {
    v11 = "DevInvExclusiveEvent already exists";
    AslLogCallPrintf(3, "IsDevInvAlreadyRunning", 75, "DevInvExclusiveEvent already exists");
    if ( !EnableDevInvStdErrLog )
      goto LABEL_13;
    v12 = o___acrt_iob_func_0(2u);
    v13 = 75;
  }
  else
  {
    v11 = "created DevInvExclusiveEvent";
    AslLogCallPrintf(3, "IsDevInvAlreadyRunning", 79, "created DevInvExclusiveEvent");
    if ( !EnableDevInvStdErrLog )
      goto LABEL_13;
    v12 = o___acrt_iob_func_0(2u);
    v13 = 79;
  }
  fprintf(v12, "Info: %s, %u: ", "IsDevInvAlreadyRunning", v13);
  v14 = o___acrt_iob_func_0(2u);
  fprintf(v14, v11);
  v15 = o___acrt_iob_func_0(2u);
  fprintf(v15, "\n");
LABEL_13:
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(0x4000000, v11);
LABEL_15:
  if ( *a1 && GetLastError() != 183 )
    return 0;
  return v3;
}

```

## disassembly

```asm
0x18002dd44  push    rbx
0x18002dd46  push    rbp
0x18002dd47  push    rsi
0x18002dd48  push    r14
0x18002dd4a  sub     rsp, 38h
0x18002dd4e  mov     r14, rcx
0x18002dd51  lea     r9, Name; "Global\\DevInvExclusiveEvent"
0x18002dd58  xor     ecx, ecx; lpEventAttributes
0x18002dd5a  xor     r8d, r8d; bInitialState
0x18002dd5d  xor     edx, edx; bManualReset
0x18002dd5f  call    cs:__imp_CreateEventW
0x18002dd65  mov     [r14], rax
0x18002dd68  mov     ebp, 1
0x18002dd6d  test    rax, rax
0x18002dd70  jnz     loc_18002DE4B
0x18002dd76  call    cs:__imp_GetLastError
0x18002dd7c  lea     esi, [rbp+1]
0x18002dd7f  mov     [rsp+58h+var_38], eax
0x18002dd83  mov     ecx, esi
0x18002dd85  lea     r9, aUnableToCreate; "unable to create DevInvExclusiveEvent ["...
0x18002dd8c  lea     r8d, [rbp+46h]
0x18002dd90  lea     rdx, aIsdevinvalread; "IsDevInvAlreadyRunning"
0x18002dd97  call    AslLogCallPrintf
0x18002dd9c  cmp     cs:EnableDevInvStdErrLog, 0
0x18002dda3  jz      short loc_18002DDFD
0x18002dda5  mov     ecx, esi; Ix
0x18002dda7  call    _o___acrt_iob_func_0
0x18002ddac  mov     rcx, rax; Stream
0x18002ddaf  lea     r9d, [rbp+46h]
0x18002ddb3  lea     r8, aIsdevinvalread; "IsDevInvAlreadyRunning"
0x18002ddba  lea     rdx, Format; "Error: %s, %u: "
0x18002ddc1  call    fprintf
0x18002ddc6  call    cs:__imp_GetLastError
0x18002ddcc  mov     ecx, esi; Ix
0x18002ddce  mov     ebx, eax
0x18002ddd0  call    _o___acrt_iob_func_0
0x18002ddd5  mov     r8d, ebx
0x18002ddd8  lea     rdx, aUnableToCreate; "unable to create DevInvExclusiveEvent ["...
0x18002dddf  mov     rcx, rax; Stream
0x18002dde2  call    fprintf
0x18002dde7  mov     ecx, esi; Ix
0x18002dde9  call    _o___acrt_iob_func_0
0x18002ddee  mov     rcx, rax; Stream
0x18002ddf1  lea     rdx, asc_18011EAD8; "\n"
0x18002ddf8  call    fprintf
0x18002ddfd  cmp     cs:g_DeviceMapLogFunction, 0
0x18002de05  jz      short loc_18002DE21
0x18002de07  call    cs:__imp_GetLastError
0x18002de0d  lea     rdx, aUnableToCreate; "unable to create DevInvExclusiveEvent ["...
0x18002de14  mov     ecx, 2000000h
0x18002de19  mov     r8d, eax
0x18002de1c  call    TraceMessageCallback
0x18002de21  call    cs:__imp_GetLastError
0x18002de27  lea     r9, aUnableToCreate; "unable to create DevInvExclusiveEvent ["...
0x18002de2e  mov     r8d, 47h ; 'G'
0x18002de34  lea     rdx, aIsdevinvalread; "IsDevInvAlreadyRunning"
0x18002de3b  mov     [rsp+58h+var_38], eax
0x18002de3f  mov     ecx, ebp
0x18002de41  call    AslLogCallPrintf
0x18002de46  jmp     loc_18002DF15
0x18002de4b  call    cs:__imp_GetLastError
0x18002de51  lea     rdx, aIsdevinvalread; "IsDevInvAlreadyRunning"
0x18002de58  mov     ecx, 3
0x18002de5d  cmp     eax, 0B7h
0x18002de62  jnz     short loc_18002DE92
0x18002de64  lea     rbx, aDevinvexclusiv; "DevInvExclusiveEvent already exists"
0x18002de6b  mov     r9, rbx
0x18002de6e  lea     r8d, [rcx+48h]
0x18002de72  call    AslLogCallPrintf
0x18002de77  cmp     cs:EnableDevInvStdErrLog, 0
0x18002de7e  jz      short loc_18002DEFE
0x18002de80  mov     esi, 2
0x18002de85  mov     ecx, esi; Ix
0x18002de87  call    _o___acrt_iob_func_0
0x18002de8c  lea     r9d, [rsi+49h]
0x18002de90  jmp     short loc_18002DEC0
0x18002de92  lea     rbx, aCreatedDevinve; "created DevInvExclusiveEvent"
0x18002de99  mov     r8d, 4Fh ; 'O'
0x18002de9f  mov     r9, rbx
0x18002dea2  call    AslLogCallPrintf
0x18002dea7  cmp     cs:EnableDevInvStdErrLog, 0
0x18002deae  jz      short loc_18002DEFE
0x18002deb0  mov     esi, 2
0x18002deb5  mov     ecx, esi; Ix
0x18002deb7  call    _o___acrt_iob_func_0
0x18002debc  lea     r9d, [rsi+4Dh]
0x18002dec0  lea     r8, aIsdevinvalread; "IsDevInvAlreadyRunning"
0x18002dec7  mov     rcx, rax; Stream
0x18002deca  lea     rdx, aInfoSU; "Info: %s, %u: "
0x18002ded1  call    fprintf
0x18002ded6  mov     ecx, esi; Ix
0x18002ded8  call    _o___acrt_iob_func_0
0x18002dedd  mov     rdx, rbx; Format
0x18002dee0  mov     rcx, rax; Stream
0x18002dee3  call    fprintf
0x18002dee8  mov     ecx, esi; Ix
0x18002deea  call    _o___acrt_iob_func_0
0x18002deef  lea     rdx, asc_18011EAD8; "\n"
0x18002def6  mov     rcx, rax; Stream
0x18002def9  call    fprintf
0x18002defe  cmp     cs:g_DeviceMapLogFunction, 0
0x18002df06  jz      short loc_18002DF15
0x18002df08  mov     rdx, rbx
0x18002df0b  mov     ecx, 4000000h
0x18002df10  call    TraceMessageCallback
0x18002df15  cmp     qword ptr [r14], 0
0x18002df19  jz      short loc_18002DF2B
0x18002df1b  call    cs:__imp_GetLastError
0x18002df21  cmp     eax, 0B7h
0x18002df26  jz      short loc_18002DF2B
0x18002df28  xor     bpl, bpl
0x18002df2b  mov     al, bpl
0x18002df2e  add     rsp, 38h
0x18002df32  pop     r14
0x18002df34  pop     rsi
0x18002df35  pop     rbp
0x18002df36  pop     rbx
0x18002df37  retn
```
