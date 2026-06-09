# IFS_SYSTEM::DosDriveNameToNtDriveName(WSTRING const *,WSTRING *)

- ea: `0x18007b29c`
- end: `0x18007b3a5`
- name: `?DosDriveNameToNtDriveName@IFS_SYSTEM@@SAEPEBVWSTRING@@PEAV2@@Z`
- size: `265`
- prototype: `static unsigned __int8(const struct WSTRING *, struct WSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x18001d308`

## callees

- `0x180024ca8`
- `0x18005de7c`
- `0x18005e220`
- `0x18007b29c`
- `0x180081750`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18007b392`
- `ntdll!RtlFreeUnicodeString` at `0x18007b392`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18007b347`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18007b347`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18007b2eb`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18007b387`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18007b2eb`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18007b387`

## pseudocode

```c
unsigned __int8 __fastcall IFS_SYSTEM::DosDriveNameToNtDriveName(const struct WSTRING *a1, struct WSTRING *a2)
{
  NTSTATUS v4; // ecx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int8 v8; // bl
  unsigned __int8 v9; // [rsp+28h] [rbp-240h]
  _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 v11[264]; // [rsp+40h] [rbp-228h] BYREF

  UnicodeString = 0;
  if ( !WSTRING::QueryWSTR(a1, 0, 0xFFFFFFFF, v11, 0x104u, v9) )
  {
    v4 = -1073741562;
LABEL_3:
    RtlSetLastWin32ErrorAndNtStatusFromNtStatus(v4);
    return 0;
  }
  v6 = *((unsigned int *)a1 + 6);
  v11[v6] = 92;
  if ( 2 * (unsigned __int64)(unsigned int)(v6 + 1) >= 0x20A )
    _report_rangecheckfailure();
  v11[(unsigned int)(v6 + 1)] = 0;
  v7 = RtlDosPathNameToNtPathName_U_WithStatus(v11, &UnicodeString, 0, 0);
  if ( v7 < 0 )
  {
    v4 = v7;
    goto LABEL_3;
  }
  UnicodeString.Buffer[((unsigned __int64)UnicodeString.Length >> 1) - 1] = 0;
  v8 = WSTRING::Initialize(a2, UnicodeString.Buffer, 0xFFFFFFFF);
  if ( !v8 )
    RtlSetLastWin32ErrorAndNtStatusFromNtStatus(-1073741801);
  RtlFreeUnicodeString(&UnicodeString);
  return v8;
}

```

## disassembly

```asm
0x18007b29c  mov     [rsp+arg_10], rbx
0x18007b2a1  push    rdi
0x18007b2a2  sub     rsp, 260h
0x18007b2a9  mov     rax, cs:__security_cookie
0x18007b2b0  xor     rax, rsp
0x18007b2b3  mov     [rsp+268h+var_18], rax
0x18007b2bb  mov     rdi, rdx
0x18007b2be  mov     [rsp+268h+var_248], 104h; unsigned int
0x18007b2c6  xorps   xmm0, xmm0
0x18007b2c9  lea     r9, [rsp+268h+var_228]; unsigned __int16 *
0x18007b2ce  xor     edx, edx; unsigned int
0x18007b2d0  or      r8d, 0FFFFFFFFh; unsigned int
0x18007b2d4  movups  xmmword ptr [rsp+268h+UnicodeString.Length], xmm0
0x18007b2d9  mov     rbx, rcx
0x18007b2dc  call    ?QueryWSTR@WSTRING@@QEBAPEAGKKPEAGKE@Z; WSTRING::QueryWSTR(ulong,ulong,ushort *,ulong,uchar)
0x18007b2e1  test    rax, rax
0x18007b2e4  jnz     short loc_18007B314
0x18007b2e6  mov     ecx, 0C0000106h; Status
0x18007b2eb  call    cs:__imp_RtlSetLastWin32ErrorAndNtStatusFromNtStatus
0x18007b2f1  xor     al, al
0x18007b2f3  mov     rcx, [rsp+268h+var_18]
0x18007b2fb  xor     rcx, rsp; StackCookie
0x18007b2fe  call    __security_check_cookie
0x18007b303  mov     rbx, [rsp+268h+arg_10]
0x18007b30b  add     rsp, 260h
0x18007b312  pop     rdi
0x18007b313  retn
0x18007b314  mov     eax, [rbx+18h]
0x18007b317  mov     ecx, 5Ch ; '\'
0x18007b31c  mov     [rsp+rax*2+268h+var_228], cx
0x18007b321  lea     ecx, [rax+1]
0x18007b324  add     rcx, rcx
0x18007b327  cmp     rcx, 20Ah
0x18007b32e  jnb     short loc_18007B39F
0x18007b330  xor     eax, eax
0x18007b332  lea     rdx, [rsp+268h+UnicodeString]
0x18007b337  mov     [rsp+rcx+268h+var_228], ax
0x18007b33c  xor     r9d, r9d
0x18007b33f  lea     rcx, [rsp+268h+var_228]
0x18007b344  xor     r8d, r8d
0x18007b347  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18007b34d  test    eax, eax
0x18007b34f  jns     short loc_18007B355
0x18007b351  mov     ecx, eax
0x18007b353  jmp     short loc_18007B2EB
0x18007b355  movzx   r9d, [rsp+268h+UnicodeString.Length]
0x18007b35b  xor     edx, edx
0x18007b35d  mov     rax, [rsp+268h+UnicodeString.Buffer]
0x18007b362  or      r8d, 0FFFFFFFFh; unsigned int
0x18007b366  shr     r9, 1
0x18007b369  mov     rcx, rdi; this
0x18007b36c  mov     [rax+r9*2-2], dx
0x18007b372  mov     rdx, [rsp+268h+UnicodeString.Buffer]; unsigned __int16 *
0x18007b377  call    ?Initialize@WSTRING@@QEAAEPEBGK@Z; WSTRING::Initialize(ushort const *,ulong)
0x18007b37c  mov     bl, al
0x18007b37e  test    al, al
0x18007b380  jnz     short loc_18007B38D
0x18007b382  mov     ecx, 0C0000017h; Status
0x18007b387  call    cs:__imp_RtlSetLastWin32ErrorAndNtStatusFromNtStatus
0x18007b38d  lea     rcx, [rsp+268h+UnicodeString]; UnicodeString
0x18007b392  call    cs:__imp_RtlFreeUnicodeString
0x18007b398  mov     al, bl
0x18007b39a  jmp     loc_18007B2F3
0x18007b39f  call    __report_rangecheckfailure
```
