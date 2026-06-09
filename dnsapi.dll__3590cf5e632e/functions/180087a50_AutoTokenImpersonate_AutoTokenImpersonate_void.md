# AutoTokenImpersonate::~AutoTokenImpersonate(void)

- ea: `0x180087a50`
- end: `0x180087ac5`
- name: `??1AutoTokenImpersonate@@QEAA@XZ`
- size: `117`
- prototype: `void __fastcall(AutoTokenImpersonate *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c9e18`
- `0x1800c9f20`

## callees

- `0x180087a50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087a89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087aab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087a89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087aab`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180087a67`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180087a67`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180087a75`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180087a75`

## pseudocode

```c
void __fastcall AutoTokenImpersonate::~AutoTokenImpersonate(HANDLE *this)
{
  HANDLE v2; // rcx

  if ( *((_DWORD *)this + 2) )
  {
    v2 = *this;
    if ( v2 )
      ImpersonateLoggedOnUser(v2);
    else
      RevertToSelf();
    if ( *this )
    {
      CloseHandle(*this);
      *this = 0;
    }
    *((_DWORD *)this + 2) = 0;
  }
  if ( *this )
  {
    CloseHandle(*this);
    *this = 0;
  }
}

```

## disassembly

```asm
0x180087a50  push    rbx
0x180087a52  sub     rsp, 20h
0x180087a56  cmp     dword ptr [rcx+8], 0
0x180087a5a  mov     rbx, rcx
0x180087a5d  jz      short loc_180087AA3
0x180087a5f  mov     rcx, [rcx]; hToken
0x180087a62  test    rcx, rcx
0x180087a65  jz      short loc_180087A75
0x180087a67  call    cs:__imp_ImpersonateLoggedOnUser
0x180087a6e  nop     dword ptr [rax+rax+00h]
0x180087a73  jmp     short loc_180087A81
0x180087a75  call    cs:__imp_RevertToSelf
0x180087a7c  nop     dword ptr [rax+rax+00h]
0x180087a81  mov     rcx, [rbx]; hObject
0x180087a84  test    rcx, rcx
0x180087a87  jz      short loc_180087A9C
0x180087a89  call    cs:__imp_CloseHandle
0x180087a90  nop     dword ptr [rax+rax+00h]
0x180087a95  mov     qword ptr [rbx], 0
0x180087a9c  mov     dword ptr [rbx+8], 0
0x180087aa3  mov     rcx, [rbx]; hObject
0x180087aa6  test    rcx, rcx
0x180087aa9  jz      short loc_180087ABE
0x180087aab  call    cs:__imp_CloseHandle
0x180087ab2  nop     dword ptr [rax+rax+00h]
0x180087ab7  mov     qword ptr [rbx], 0
0x180087abe  add     rsp, 20h
0x180087ac2  pop     rbx
0x180087ac3  retn
```
