# GetSidString(void *,ushort * *)

- ea: `0x180018c68`
- end: `0x180018ce0`
- name: `?GetSidString@@YAJPEAXPEAPEAG@Z`
- size: `120`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800045bc`

## callees

- `0x180001cfc`
- `0x180001e98`
- `0x180018c68`
- `0x18001a784`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018ca1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018ca1`

## pseudocode

```c
__int64 __fastcall GetSidString(void *a1, unsigned __int16 **a2)
{
  int UserSid; // ebx
  PSID Sid; // [rsp+40h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp+20h] BYREF

  Sid = 0;
  UserSid = GetUserSid(a1, &Sid);
  if ( UserSid >= 0 )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      UserSid = 0;
    }
    else
    {
      UserSid = ResultFromKnownLastError();
      if ( UserSid < 0 )
      {
LABEL_6:
        ResultFromHeapFree(Sid);
        return (unsigned int)UserSid;
      }
    }
    *a2 = StringSid;
    goto LABEL_6;
  }
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x180018c68  mov     [rsp+arg_0], rbx
0x180018c6d  push    rdi
0x180018c6e  sub     rsp, 20h
0x180018c72  mov     rdi, rdx
0x180018c75  mov     [rsp+28h+Sid], 0
0x180018c7e  lea     rdx, [rsp+28h+Sid]; void **
0x180018c83  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x180018c88  mov     ebx, eax
0x180018c8a  test    eax, eax
0x180018c8c  js      short loc_180018CD2
0x180018c8e  mov     rcx, [rsp+28h+Sid]; Sid
0x180018c93  lea     rdx, [rsp+28h+StringSid]; StringSid
0x180018c98  mov     [rsp+28h+StringSid], 0
0x180018ca1  call    cs:__imp_ConvertSidToStringSidW
0x180018ca8  nop     dword ptr [rax+rax+00h]
0x180018cad  test    eax, eax
0x180018caf  jz      short loc_180018CB5
0x180018cb1  xor     ebx, ebx
0x180018cb3  jmp     short loc_180018CC0
0x180018cb5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180018cba  mov     ebx, eax
0x180018cbc  test    eax, eax
0x180018cbe  js      short loc_180018CC8
0x180018cc0  mov     rax, [rsp+28h+StringSid]
0x180018cc5  mov     [rdi], rax
0x180018cc8  mov     rcx, [rsp+28h+Sid]; lpMem
0x180018ccd  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180018cd2  mov     eax, ebx
0x180018cd4  mov     rbx, [rsp+28h+arg_0]
0x180018cd9  add     rsp, 20h
0x180018cdd  pop     rdi
0x180018cde  retn
```
