# CallerIdentity::GetPackageSidFromWindow(HWND__ *,void * *)

- ea: `0x180067020`
- end: `0x180067062`
- name: `?GetPackageSidFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAX@Z`
- size: `66`
- prototype: `HRESULT __fastcall(HWND__ *hwnd, void **ppPackageSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800675dc`

## callees

- `0x180066b68`
- `0x180067020`
- `0x1800671fc`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18006703d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18006703d`

## pseudocode

```c
HRESULT __fastcall CallerIdentity::GetPackageSidFromWindow(HWND hwnd, void **ppPackageSid)
{
  HRESULT result; // eax
  unsigned int dwProcess; // [rsp+38h] [rbp+10h] BYREF

  *ppPackageSid = 0;
  dwProcess = 0;
  if ( GetWindowThreadProcessId(hwnd, &dwProcess) )
    return CallerIdentity::GetPackageSidFromProcess(dwProcess, ppPackageSid);
  result = ResultFromKnownLastError();
  if ( result >= 0 )
    return CallerIdentity::GetPackageSidFromProcess(dwProcess, ppPackageSid);
  return result;
}

```

## disassembly

```asm
0x180067020  push    rbx
0x180067022  sub     rsp, 20h
0x180067026  mov     rbx, ppPackageSid
0x180067029  mov     qword ptr [ppPackageSid], 0
0x180067030  lea     ppPackageSid, [rsp+28h+dwProcess]; lpdwProcessId
0x180067035  mov     [rsp+28h+dwProcess], 0
0x18006703d  call    cs:__imp_GetWindowThreadProcessId
0x180067043  test    eax, eax
0x180067045  jnz     short loc_180067050
0x180067047  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006704c  test    eax, eax
0x18006704e  js      short loc_18006705C
0x180067050  mov     ecx, [rsp+28h+dwProcess]; dwPid
0x180067054  mov     ppPackageSid, rbx; ppPackageSid
0x180067057  call    ?GetPackageSidFromProcess@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetPackageSidFromProcess(ulong,void * *)
0x18006705c  add     rsp, 20h
0x180067060  pop     rbx
0x180067061  retn
```
