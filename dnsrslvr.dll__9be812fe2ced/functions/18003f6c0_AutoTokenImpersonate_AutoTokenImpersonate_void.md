# AutoTokenImpersonate::~AutoTokenImpersonate(void)

- ea: `0x18003f6c0`
- end: `0x18003f71c`
- name: `??1AutoTokenImpersonate@@QEAA@XZ`
- size: `92`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f3c0`

## callees

- `0x18003f6c0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f6ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f709`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f6ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f709`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003f6df`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003f6df`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003f6d7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003f6d7`

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
0x18003f6c0  push    rbx
0x18003f6c2  sub     rsp, 20h
0x18003f6c6  cmp     dword ptr [rcx+8], 0
0x18003f6ca  mov     rbx, rcx
0x18003f6cd  jz      short loc_18003F701
0x18003f6cf  mov     rcx, [rcx]; hToken
0x18003f6d2  test    rcx, rcx
0x18003f6d5  jz      short loc_18003F6DF
0x18003f6d7  call    cs:__imp_ImpersonateLoggedOnUser
0x18003f6dd  jmp     short loc_18003F6E5
0x18003f6df  call    cs:__imp_RevertToSelf
0x18003f6e5  mov     rcx, [rbx]; hObject
0x18003f6e8  test    rcx, rcx
0x18003f6eb  jz      short loc_18003F6FA
0x18003f6ed  call    cs:__imp_CloseHandle
0x18003f6f3  mov     qword ptr [rbx], 0
0x18003f6fa  mov     dword ptr [rbx+8], 0
0x18003f701  mov     rcx, [rbx]; hObject
0x18003f704  test    rcx, rcx
0x18003f707  jz      short loc_18003F716
0x18003f709  call    cs:__imp_CloseHandle
0x18003f70f  mov     qword ptr [rbx], 0
0x18003f716  add     rsp, 20h
0x18003f71a  pop     rbx
0x18003f71b  retn
```
