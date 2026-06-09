# CallerIdentity::GetCallingProcessPackageSidString(ushort * *)

- ea: `0x18007f268`
- end: `0x18007f30d`
- name: `?GetCallingProcessPackageSidString@CallerIdentity@@YAJPEAPEAG@Z`
- size: `165`
- prototype: `__int64 __fastcall(LPWSTR *StringSid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027b10`

## callees

- `0x180027154`
- `0x18007f268`
- `0x18007f444`
- `0x18007f470`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f2fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f2fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007f2dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007f2dc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007f2c2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007f2c2`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCallingProcessPackageSidString(
        LPWSTR *StringSid,
        unsigned __int16 **a2,
        void **a3)
{
  int CallingProcessHandle; // ebx
  void **v5; // r8
  CallerIdentity *v6; // rcx
  char *v7; // rcx
  HANDLE hObject; // [rsp+30h] [rbp+8h] BYREF
  PSID Sid; // [rsp+38h] [rbp+10h] BYREF

  *StringSid = 0;
  hObject = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(
                           (CallerIdentity *)StringSid,
                           (unsigned int)&hObject,
                           a3);
  if ( CallingProcessHandle >= 0 )
  {
    v6 = (CallerIdentity *)hObject;
    *StringSid = 0;
    Sid = 0;
    CallingProcessHandle = CallerIdentity::GetPackageSidFromProcessHandle(v6, &Sid, v5);
    if ( CallingProcessHandle >= 0 )
    {
      if ( ConvertSidToStringSidW(Sid, StringSid) )
        CallingProcessHandle = 0;
      else
        CallingProcessHandle = ResultFromKnownLastError();
      LocalFree(Sid);
    }
  }
  v7 = (char *)hObject;
  hObject = 0;
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
  return (unsigned int)CallingProcessHandle;
}

```

## disassembly

```asm
0x18007f268  mov     [rsp+arg_10], rbx
0x18007f26d  push    rdi
0x18007f26e  sub     rsp, 20h
0x18007f272  lea     rdx, [rsp+28h+hObject]; unsigned int
0x18007f277  mov     qword ptr [rcx], 0
0x18007f27e  mov     rdi, rcx
0x18007f281  mov     [rsp+28h+hObject], 0
0x18007f28a  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKPEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,void * *)
0x18007f28f  mov     ebx, eax
0x18007f291  test    eax, eax
0x18007f293  js      short loc_18007F2E2
0x18007f295  mov     rcx, [rsp+28h+hObject]; this
0x18007f29a  lea     rdx, [rsp+28h+Sid]; void *
0x18007f29f  mov     qword ptr [rdi], 0
0x18007f2a6  mov     [rsp+28h+Sid], 0
0x18007f2af  call    ?GetPackageSidFromProcessHandle@CallerIdentity@@YAJPEAXPEAPEAX@Z; CallerIdentity::GetPackageSidFromProcessHandle(void *,void * *)
0x18007f2b4  mov     ebx, eax
0x18007f2b6  test    eax, eax
0x18007f2b8  js      short loc_18007F2E2
0x18007f2ba  mov     rcx, [rsp+28h+Sid]; Sid
0x18007f2bf  mov     rdx, rdi; StringSid
0x18007f2c2  call    cs:__imp_ConvertSidToStringSidW
0x18007f2c8  test    eax, eax
0x18007f2ca  jz      short loc_18007F2D0
0x18007f2cc  xor     ebx, ebx
0x18007f2ce  jmp     short loc_18007F2D7
0x18007f2d0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18007f2d5  mov     ebx, eax
0x18007f2d7  mov     rcx, [rsp+28h+Sid]; hMem
0x18007f2dc  call    cs:__imp_LocalFree
0x18007f2e2  mov     rcx, [rsp+28h+hObject]; hObject
0x18007f2e7  mov     [rsp+28h+hObject], 0
0x18007f2f0  lea     rax, [rcx-1]
0x18007f2f4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007f2f8  ja      short loc_18007F300
0x18007f2fa  call    cs:__imp_CloseHandle
0x18007f300  mov     eax, ebx
0x18007f302  mov     rbx, [rsp+28h+arg_10]
0x18007f307  add     rsp, 20h
0x18007f30b  pop     rdi
0x18007f30c  retn
```
