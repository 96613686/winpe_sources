# IsValidUserSid(ushort const *)

- ea: `0x18000e0f0`
- end: `0x18000e17a`
- name: `?IsValidUserSid@@YAHPEBG@Z`
- size: `138`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180019684`
- `0x18001b0d0`

## callees

- `0x18000e0f0`
- `0x18000e180`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e14c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e165`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e14c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e165`
- `DMCmnUtils!DmGetUserTokenFromSid` at `0x18000e12c`
- `DMCmnUtils!DmGetUserTokenFromSid` at `0x18000e12c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsValidUserSid(const unsigned __int16 *a1)
{
  bool v2; // sf
  char *v3; // rax
  bool v5; // [rsp+30h] [rbp+8h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp+10h] BYREF

  if ( !a1 )
    return 0;
  v5 = 0;
  if ( (int)IsWellKnownSid(a1, &v5) < 0 || v5 )
    return 0;
  hObject = 0;
  v2 = (int)DmGetUserTokenFromSid(a1, &hObject, 0) < 0;
  v3 = (char *)hObject - 1;
  if ( v2 )
  {
    if ( (unsigned __int64)v3 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject);
    return 0;
  }
  if ( (unsigned __int64)v3 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject);
  return 1;
}

```

## disassembly

```asm
0x18000e0f0  push    rbx
0x18000e0f2  sub     rsp, 20h
0x18000e0f6  mov     rbx, rcx
0x18000e0f9  test    rcx, rcx
0x18000e0fc  jz      short loc_18000E171
0x18000e0fe  mov     [rsp+28h+arg_0], 0
0x18000e103  lea     rdx, [rsp+28h+arg_0]; bool *
0x18000e108  call    ?IsWellKnownSid@@YAJPEBGPEA_N@Z; IsWellKnownSid(ushort const *,bool *)
0x18000e10d  test    eax, eax
0x18000e10f  js      short loc_18000E171
0x18000e111  cmp     [rsp+28h+arg_0], 0
0x18000e116  jnz     short loc_18000E171
0x18000e118  mov     [rsp+28h+hObject], 0
0x18000e121  xor     r8d, r8d
0x18000e124  lea     rdx, [rsp+28h+hObject]
0x18000e129  mov     rcx, rbx
0x18000e12c  call    cs:__imp_?DmGetUserTokenFromSid@@YAJPEBGPEAPEAXPEAK@Z; DmGetUserTokenFromSid(ushort const *,void * *,ulong *)
0x18000e133  nop     dword ptr [rax+rax+00h]
0x18000e138  nop
0x18000e139  mov     rcx, [rsp+28h+hObject]; hObject
0x18000e13e  test    eax, eax
0x18000e140  lea     rax, [rcx-1]
0x18000e144  js      short loc_18000E15F
0x18000e146  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e14a  ja      short loc_18000E158
0x18000e14c  call    cs:__imp_CloseHandle
0x18000e153  nop     dword ptr [rax+rax+00h]
0x18000e158  mov     eax, 1
0x18000e15d  jmp     short loc_18000E173
0x18000e15f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e163  ja      short loc_18000E171
0x18000e165  call    cs:__imp_CloseHandle
0x18000e16c  nop     dword ptr [rax+rax+00h]
0x18000e171  xor     eax, eax
0x18000e173  add     rsp, 20h
0x18000e177  pop     rbx
0x18000e178  retn
```
