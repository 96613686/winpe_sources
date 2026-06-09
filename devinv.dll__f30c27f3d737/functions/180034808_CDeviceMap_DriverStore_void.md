# CDeviceMap::DriverStore(void)

- ea: `0x180034808`
- end: `0x180034930`
- name: `?DriverStore@CDeviceMap@@QEAAPEAUHDRIVERSTORE__@@XZ`
- size: `296`
- prototype: `struct HDRIVERSTORE__ *__fastcall(CDeviceMap *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001bbd8`

## callees

- `0x180006d02`
- `0x180007014`
- `0x180034808`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `drvstore!DriverStoreOpenW` at `0x180034830`
- `drvstore!DriverStoreOpenW` at `0x180034830`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003483f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800348dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800348f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003483f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800348dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800348f7`

## string_xrefs

- `0x180034845`: `DriverStoreOpen failed [%d]`
- `0x1800348ab`: `DriverStoreOpen failed [%d]`
- `0x1800348e3`: `DriverStoreOpen failed [%d]`
- `0x1800348fd`: `DriverStoreOpen failed [%d]`

## pseudocode

```c
struct HDRIVERSTORE__ *__fastcall CDeviceMap::DriverStore(CDeviceMap *this)
{
  struct HDRIVERSTORE__ *result; // rax
  DWORD LastError; // eax
  FILE *v4; // rax
  DWORD v5; // ebx
  FILE *v6; // rax
  FILE *v7; // rax
  DWORD v8; // eax
  DWORD v9; // eax

  result = (struct HDRIVERSTORE__ *)*((_QWORD *)this + 94);
  if ( (unsigned __int64)result - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    result = (struct HDRIVERSTORE__ *)DriverStoreOpenW(0, 0, 0, 0);
    if ( result )
    {
      *((_QWORD *)this + 94) = result;
    }
    else
    {
      LastError = GetLastError();
      AslLogCallPrintf(2, "CDeviceMap::DriverStore", 2457, "DriverStoreOpen failed [%d]", LastError);
      if ( EnableDevInvStdErrLog )
      {
        v4 = o___acrt_iob_func_0(2u);
        fprintf(v4, "Error: %s, %u: ", "CDeviceMap::DriverStore", 2457);
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
      AslLogCallPrintf(1, "CDeviceMap::DriverStore", 2457, "DriverStoreOpen failed [%d]", v9);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180034808  push    rbx
0x18003480a  sub     rsp, 30h
0x18003480e  mov     rax, [rcx+2F0h]
0x180034815  mov     rbx, rcx
0x180034818  lea     rdx, [rax-1]
0x18003481c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180034820  jbe     loc_18003492A
0x180034826  xor     r9d, r9d
0x180034829  xor     r8d, r8d
0x18003482c  xor     edx, edx
0x18003482e  xor     ecx, ecx
0x180034830  call    cs:__imp_DriverStoreOpenW
0x180034836  test    rax, rax
0x180034839  jnz     loc_180034923
0x18003483f  call    cs:__imp_GetLastError
0x180034845  lea     r9, aDriverstoreope; "DriverStoreOpen failed [%d]"
0x18003484c  mov     r8d, 999h
0x180034852  lea     rdx, aCdevicemapDriv; "CDeviceMap::DriverStore"
0x180034859  mov     [rsp+38h+var_18], eax
0x18003485d  mov     ecx, 2
0x180034862  call    AslLogCallPrintf
0x180034867  cmp     cs:EnableDevInvStdErrLog, 0
0x18003486e  jz      short loc_1800348D3
0x180034870  mov     ecx, 2; Ix
0x180034875  call    _o___acrt_iob_func_0
0x18003487a  mov     rcx, rax; Stream
0x18003487d  lea     r8, aCdevicemapDriv; "CDeviceMap::DriverStore"
0x180034884  mov     r9d, 999h
0x18003488a  lea     rdx, Format; "Error: %s, %u: "
0x180034891  call    fprintf
0x180034896  call    cs:__imp_GetLastError
0x18003489c  mov     ecx, 2; Ix
0x1800348a1  mov     ebx, eax
0x1800348a3  call    _o___acrt_iob_func_0
0x1800348a8  mov     r8d, ebx
0x1800348ab  lea     rdx, aDriverstoreope; "DriverStoreOpen failed [%d]"
0x1800348b2  mov     rcx, rax; Stream
0x1800348b5  call    fprintf
0x1800348ba  mov     ecx, 2; Ix
0x1800348bf  call    _o___acrt_iob_func_0
0x1800348c4  mov     rcx, rax; Stream
0x1800348c7  lea     rdx, asc_18011EAD8; "\n"
0x1800348ce  call    fprintf
0x1800348d3  cmp     cs:g_DeviceMapLogFunction, 0
0x1800348db  jz      short loc_1800348F7
0x1800348dd  call    cs:__imp_GetLastError
0x1800348e3  lea     rdx, aDriverstoreope; "DriverStoreOpen failed [%d]"
0x1800348ea  mov     ecx, 2000000h
0x1800348ef  mov     r8d, eax
0x1800348f2  call    TraceMessageCallback
0x1800348f7  call    cs:__imp_GetLastError
0x1800348fd  lea     r9, aDriverstoreope; "DriverStoreOpen failed [%d]"
0x180034904  mov     r8d, 999h
0x18003490a  lea     rdx, aCdevicemapDriv; "CDeviceMap::DriverStore"
0x180034911  mov     [rsp+38h+var_18], eax
0x180034915  mov     ecx, 1
0x18003491a  call    AslLogCallPrintf
0x18003491f  xor     eax, eax
0x180034921  jmp     short loc_18003492A
0x180034923  mov     [rbx+2F0h], rax
0x18003492a  add     rsp, 30h
0x18003492e  pop     rbx
0x18003492f  retn
```
