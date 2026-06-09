# CallerIdentity::VerifyWindowIsInProcessByAppContainerSid(HWND__ *,void *)

- ea: `0x1800675dc`
- end: `0x18006765f`
- name: `?VerifyWindowIsInProcessByAppContainerSid@CallerIdentity@@YAJPEAUHWND__@@PEAX@Z`
- size: `131`
- prototype: `HRESULT __fastcall(HWND__ *hwnd, void *hProcess)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180067438`

## callees

- `0x180067020`
- `0x180067270`
- `0x18006741c`
- `0x1800675dc`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18006762e`
- `ntdll!RtlEqualSid` at `0x18006762e`

## pseudocode

```c
__int64 __fastcall CallerIdentity::VerifyWindowIsInProcessByAppContainerSid(HWND__ *hwnd, void *hProcess)
{
  int PackageSidFromProcessHandle; // ebx
  CLocalMemPtr<void> spsid2; // [rsp+40h] [rbp+18h] BYREF
  CLocalMemPtr<void> spsid1; // [rsp+48h] [rbp+20h] BYREF

  spsid1._obj = 0;
  PackageSidFromProcessHandle = CallerIdentity::GetPackageSidFromProcessHandle(hProcess, &spsid1._obj);
  if ( PackageSidFromProcessHandle >= 0 )
  {
    spsid2._obj = 0;
    PackageSidFromProcessHandle = CallerIdentity::GetPackageSidFromWindow(hwnd, &spsid2._obj);
    if ( PackageSidFromProcessHandle >= 0 && !RtlEqualSid(spsid1._obj, spsid2._obj) )
      PackageSidFromProcessHandle = -2147024891;
    CLocalMemPtr<void>::~CLocalMemPtr<void>(&spsid2);
  }
  CLocalMemPtr<void>::~CLocalMemPtr<void>(&spsid1);
  return (unsigned int)PackageSidFromProcessHandle;
}

```

## disassembly

```asm
0x1800675dc  mov     [rsp+arg_0], rbx
0x1800675e1  push    rdi
0x1800675e2  sub     rsp, 20h
0x1800675e6  mov     rax, hProcess
0x1800675e9  mov     [rsp+28h+spsid1._obj], 0
0x1800675f2  mov     rdi, hwnd
0x1800675f5  lea     hProcess, [rsp+28h+spsid1]; ppPackageSid
0x1800675fa  mov     hwnd, rax; hProcess
0x1800675fd  call    ?GetPackageSidFromProcessHandle@CallerIdentity@@YAJPEAXPEAPEAX@Z; CallerIdentity::GetPackageSidFromProcessHandle(void *,void * *)
0x180067602  mov     ebx, eax
0x180067604  test    eax, eax
0x180067606  js      short loc_180067648
0x180067608  lea     hProcess, [rsp+28h+spsid2]; ppPackageSid
0x18006760d  mov     [rsp+28h+spsid2._obj], 0
0x180067616  mov     hwnd, rdi; hwnd
0x180067619  call    ?GetPackageSidFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAX@Z; CallerIdentity::GetPackageSidFromWindow(HWND__ *,void * *)
0x18006761e  mov     ebx, eax
0x180067620  test    eax, eax
0x180067622  js      short loc_18006763E
0x180067624  mov     hProcess, [rsp+28h+spsid2._obj]; Sid2
0x180067629  mov     hwnd, [rsp+28h+spsid1._obj]; Sid1
0x18006762e  call    cs:__imp_RtlEqualSid
0x180067634  test    al, al
0x180067636  mov     ecx, 80070005h
0x18006763b  cmovz   ebx, ecx
0x18006763e  lea     hwnd, [rsp+28h+spsid2]; this
0x180067643  call    ??1?$CLocalMemPtr@X@@QEAA@XZ; CLocalMemPtr<void>::~CLocalMemPtr<void>(void)
0x180067648  lea     hwnd, [rsp+28h+spsid1]; this
0x18006764d  call    ??1?$CLocalMemPtr@X@@QEAA@XZ; CLocalMemPtr<void>::~CLocalMemPtr<void>(void)
0x180067652  mov     eax, ebx
0x180067654  mov     rbx, [rsp+28h+arg_0]
0x180067659  add     rsp, 20h
0x18006765d  pop     rdi
0x18006765e  retn
```
