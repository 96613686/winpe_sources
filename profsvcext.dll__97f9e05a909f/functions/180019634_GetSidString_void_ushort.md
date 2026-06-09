# GetSidString(void *,ushort * *)

- ea: `0x180019634`
- end: `0x18001969f`
- name: `?GetSidString@@YAJPEAXPEAPEAG@Z`
- size: `107`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800077a0`
- `0x180019380`
- `0x180019af8`

## callees

- `0x1800045d0`
- `0x18000f9c8`
- `0x180019634`
- `0x1800197f0`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001966d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001966d`

## pseudocode

```c
__int64 __fastcall GetSidString(void *a1, unsigned __int16 **a2)
{
  int UserSid; // ebx
  BOOL v4; // eax
  PSID Sid; // [rsp+40h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp+20h] BYREF

  Sid = 0;
  UserSid = GetUserSid(a1, &Sid);
  if ( UserSid >= 0 )
  {
    StringSid = 0;
    v4 = ConvertSidToStringSidW(Sid, &StringSid);
    UserSid = ResultFromWin32Bool(v4);
    if ( UserSid >= 0 )
      *a2 = StringSid;
    ResultFromHeapFree(Sid);
  }
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x180019634  mov     [rsp+arg_0], rbx
0x180019639  push    rdi
0x18001963a  sub     rsp, 20h
0x18001963e  mov     rdi, rdx
0x180019641  mov     [rsp+28h+Sid], 0
0x18001964a  lea     rdx, [rsp+28h+Sid]; void **
0x18001964f  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x180019654  mov     ebx, eax
0x180019656  test    eax, eax
0x180019658  js      short loc_180019692
0x18001965a  mov     rcx, [rsp+28h+Sid]; Sid
0x18001965f  lea     rdx, [rsp+28h+StringSid]; StringSid
0x180019664  mov     [rsp+28h+StringSid], 0
0x18001966d  call    cs:__imp_ConvertSidToStringSidW
0x180019673  mov     ecx, eax; int
0x180019675  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18001967a  mov     ebx, eax
0x18001967c  test    eax, eax
0x18001967e  js      short loc_180019688
0x180019680  mov     rax, [rsp+28h+StringSid]
0x180019685  mov     [rdi], rax
0x180019688  mov     rcx, [rsp+28h+Sid]; lpMem
0x18001968d  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180019692  mov     eax, ebx
0x180019694  mov     rbx, [rsp+28h+arg_0]
0x180019699  add     rsp, 20h
0x18001969d  pop     rdi
0x18001969e  retn
```
