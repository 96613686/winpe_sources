# CDriverMap::DriverStore(void)

- ea: `0x1800445d8`
- end: `0x180044700`
- name: `?DriverStore@CDriverMap@@QEAAPEAUHDRIVERSTORE__@@XZ`
- size: `296`
- prototype: `struct HDRIVERSTORE__ *__fastcall(CDriverMap *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180049694`

## callees

- `0x180006d02`
- `0x180007014`
- `0x1800445d8`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `drvstore!DriverStoreOpenW` at `0x180044600`
- `drvstore!DriverStoreOpenW` at `0x180044600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004460f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800446ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800446c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004460f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800446ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800446c7`

## string_xrefs

- `0x180044615`: `DriverStoreOpen failed [%d]`
- `0x18004467b`: `DriverStoreOpen failed [%d]`
- `0x1800446b3`: `DriverStoreOpen failed [%d]`
- `0x1800446cd`: `DriverStoreOpen failed [%d]`

## pseudocode

```c
struct HDRIVERSTORE__ *__fastcall CDriverMap::DriverStore(CDriverMap *this)
{
  struct HDRIVERSTORE__ *result; // rax
  DWORD LastError; // eax
  FILE *v4; // rax
  DWORD v5; // ebx
  FILE *v6; // rax
  FILE *v7; // rax
  DWORD v8; // eax
  DWORD v9; // eax

  result = (struct HDRIVERSTORE__ *)*((_QWORD *)this + 22);
  if ( (unsigned __int64)result - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    result = (struct HDRIVERSTORE__ *)DriverStoreOpenW(0, 0, 0, 0);
    if ( result )
    {
      *((_QWORD *)this + 22) = result;
    }
    else
    {
      LastError = GetLastError();
      AslLogCallPrintf(2, "CDriverMap::DriverStore", 2931, "DriverStoreOpen failed [%d]", LastError);
      if ( EnableDevInvStdErrLog )
      {
        v4 = o___acrt_iob_func_0(2u);
        fprintf(v4, "Error: %s, %u: ", "CDriverMap::DriverStore", 2931);
        v5 = GetLastError();
        v6 = o___acrt_iob_func_0(2u);
        fprintf(v6, "DriverStoreOpen failed [%d]", v5);
        v7 = o___acrt_iob_func_0(2u);
        fprintf(v7, "\n");
      }
      if ( g_DeviceMapLogFunction )
      {
        v8 = GetLastError();
        TraceMessageCallback(0x2000000, "DriverStoreOpen failed [%d]", v8);
      }
      v9 = GetLastError();
      AslLogCallPrintf(1, "CDriverMap::DriverStore", 2931, "DriverStoreOpen failed [%d]", v9);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800445d8  push    rbx
0x1800445da  sub     rsp, 30h
0x1800445de  mov     rax, [rcx+0B0h]
0x1800445e5  mov     rbx, rcx
0x1800445e8  lea     rdx, [rax-1]
0x1800445ec  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800445f0  jbe     loc_1800446FA
0x1800445f6  xor     r9d, r9d
0x1800445f9  xor     r8d, r8d
0x1800445fc  xor     edx, edx
0x1800445fe  xor     ecx, ecx
0x180044600  call    cs:__imp_DriverStoreOpenW
0x180044606  test    rax, rax
0x180044609  jnz     loc_1800446F3
0x18004460f  call    cs:__imp_GetLastError
0x180044615  lea     r9, aDriverstoreope; "DriverStoreOpen failed [%d]"
0x18004461c  mov     r8d, 0B73h
0x180044622  lea     rdx, aCdrivermapDriv; "CDriverMap::DriverStore"
0x180044629  mov     [rsp+38h+var_18], eax
0x18004462d  mov     ecx, 2
0x180044632  call    AslLogCallPrintf
0x180044637  cmp     cs:EnableDevInvStdErrLog, 0
0x18004463e  jz      short loc_1800446A3
0x180044640  mov     ecx, 2; Ix
0x180044645  call    _o___acrt_iob_func_0
0x18004464a  mov     rcx, rax; Stream
0x18004464d  lea     r8, aCdrivermapDriv; "CDriverMap::DriverStore"
0x180044654  mov     r9d, 0B73h
0x18004465a  lea     rdx, Format; "Error: %s, %u: "
0x180044661  call    fprintf
0x180044666  call    cs:__imp_GetLastError
0x18004466c  mov     ecx, 2; Ix
0x180044671  mov     ebx, eax
0x180044673  call    _o___acrt_iob_func_0
0x180044678  mov     r8d, ebx
0x18004467b  lea     rdx, aDriverstoreope; "DriverStoreOpen failed [%d]"
0x180044682  mov     rcx, rax; Stream
0x180044685  call    fprintf
0x18004468a  mov     ecx, 2; Ix
0x18004468f  call    _o___acrt_iob_func_0
0x180044694  mov     rcx, rax; Stream
0x180044697  lea     rdx, asc_18011EAD8; "\n"
0x18004469e  call    fprintf
0x1800446a3  cmp     cs:g_DeviceMapLogFunction, 0
0x1800446ab  jz      short loc_1800446C7
0x1800446ad  call    cs:__imp_GetLastError
0x1800446b3  lea     rdx, aDriverstoreope; "DriverStoreOpen failed [%d]"
0x1800446ba  mov     ecx, 2000000h
0x1800446bf  mov     r8d, eax
0x1800446c2  call    TraceMessageCallback
0x1800446c7  call    cs:__imp_GetLastError
0x1800446cd  lea     r9, aDriverstoreope; "DriverStoreOpen failed [%d]"
0x1800446d4  mov     r8d, 0B73h
0x1800446da  lea     rdx, aCdrivermapDriv; "CDriverMap::DriverStore"
0x1800446e1  mov     [rsp+38h+var_18], eax
0x1800446e5  mov     ecx, 1
0x1800446ea  call    AslLogCallPrintf
0x1800446ef  xor     eax, eax
0x1800446f1  jmp     short loc_1800446FA
0x1800446f3  mov     [rbx+0B0h], rax
0x1800446fa  add     rsp, 30h
0x1800446fe  pop     rbx
0x1800446ff  retn
```
