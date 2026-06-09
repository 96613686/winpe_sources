# CCscProtocolHandler::_EnsureConnectedToCsc(void)

- ea: `0x180014690`
- end: `0x180014771`
- name: `?_EnsureConnectedToCsc@CCscProtocolHandler@@AEAAJXZ`
- size: `225`
- prototype: `__int64 __fastcall(CCscProtocolHandler *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013e20`
- `0x180013ef0`

## callees

- `0x18000557c`
- `0x180014690`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800146c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800146f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800146c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800146f8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014733`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014733`
- `ntdll!RtlNtStatusToDosError` at `0x18001473d`
- `ntdll!RtlNtStatusToDosError` at `0x18001473d`

## pseudocode

```c
signed int __fastcall CCscProtocolHandler::_EnsureConnectedToCsc(CCscProtocolHandler *this)
{
  signed int result; // eax
  LPVOID *ppv; // rdi
  HMODULE v4; // rcx
  FARPROC ProcAddress; // rax
  FARPROC v6; // rax
  NTSTATUS v7; // eax
  int v8; // [rsp+40h] [rbp+8h] BYREF

  result = 0;
  ppv = (LPVOID *)((char *)this + 72);
  if ( !*((_QWORD *)this + 9) )
  {
    v4 = (HMODULE)*((_QWORD *)this + 8);
    if ( v4 )
    {
      ProcAddress = GetProcAddress(v4, "OfflineFilesQueryStatus");
      if ( !ProcAddress )
        return ResultFromLastError();
      v8 = 0;
      if ( ((unsigned int (__fastcall *)(int *, _QWORD))ProcAddress)(&v8, 0) )
        return ResultFromLastError();
      if ( v8 )
      {
        v6 = GetProcAddress(*((HMODULE *)this + 8), "CscSearchApiGetInterface");
        if ( v6 )
        {
          v7 = ((__int64 (__fastcall *)(__int64, __int64, char *))v6)(65544, 2411276297LL, (char *)this + 80);
          if ( v7 >= 0 )
            return CoCreateInstance(&CLSID_OfflineFilesCache, 0, 0x15u, &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5, ppv);
          result = RtlNtStatusToDosError(v7);
          if ( !result )
            return -2147467259;
          if ( result > 0 )
            return (unsigned __int16)result | 0x80070000;
          return result;
        }
        return ResultFromLastError();
      }
    }
    return -2147216895;
  }
  return result;
}

```

## disassembly

```asm
0x180014690  mov     [rsp+arg_8], rbx
0x180014695  push    rdi
0x180014696  sub     rsp, 30h
0x18001469a  xor     eax, eax
0x18001469c  lea     rdi, [rcx+48h]
0x1800146a0  mov     rbx, rcx
0x1800146a3  cmp     [rdi], rax
0x1800146a6  jnz     loc_180014766
0x1800146ac  mov     rcx, [rcx+40h]; hModule
0x1800146b0  test    rcx, rcx
0x1800146b3  jz      loc_180014761
0x1800146b9  lea     rdx, aOfflinefilesqu; "OfflineFilesQueryStatus"
0x1800146c0  call    cs:__imp_GetProcAddress
0x1800146c6  test    rax, rax
0x1800146c9  jz      loc_18001475A
0x1800146cf  xor     edx, edx
0x1800146d1  mov     [rsp+38h+arg_0], 0
0x1800146d9  lea     rcx, [rsp+38h+arg_0]
0x1800146de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146e3  test    eax, eax
0x1800146e5  jnz     short loc_18001475A
0x1800146e7  cmp     [rsp+38h+arg_0], eax
0x1800146eb  jz      short loc_180014761
0x1800146ed  mov     rcx, [rbx+40h]; hModule
0x1800146f1  lea     rdx, aCscsearchapige; "CscSearchApiGetInterface"
0x1800146f8  call    cs:__imp_GetProcAddress
0x1800146fe  test    rax, rax
0x180014701  jz      short loc_18001475A
0x180014703  lea     r8, [rbx+50h]
0x180014707  mov     edx, 8FB92809h
0x18001470c  mov     ecx, 10008h
0x180014711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014716  test    eax, eax
0x180014718  js      short loc_18001473B
0x18001471a  xor     edx, edx; pUnkOuter
0x18001471c  mov     [rsp+38h+ppv], rdi; ppv
0x180014721  lea     r9, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; riid
0x180014728  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x18001472f  lea     r8d, [rdx+15h]; dwClsContext
0x180014733  call    cs:__imp_CoCreateInstance
0x180014739  jmp     short loc_180014766
0x18001473b  mov     ecx, eax; Status
0x18001473d  call    cs:__imp_RtlNtStatusToDosError
0x180014743  test    eax, eax
0x180014745  jz      short loc_180014753
0x180014747  jle     short loc_180014766
0x180014749  movzx   eax, ax
0x18001474c  or      eax, 80070000h
0x180014751  jmp     short loc_180014766
0x180014753  mov     eax, 80004005h
0x180014758  jmp     short loc_180014766
0x18001475a  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001475f  jmp     short loc_180014766
0x180014761  mov     eax, 80041201h
0x180014766  mov     rbx, [rsp+38h+arg_8]
0x18001476b  add     rsp, 30h
0x18001476f  pop     rdi
0x180014770  retn
```
