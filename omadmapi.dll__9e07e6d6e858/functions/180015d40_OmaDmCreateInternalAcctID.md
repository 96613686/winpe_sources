# OmaDmCreateInternalAcctID

- ea: `0x180015d40`
- end: `0x180015ddf`
- name: `OmaDmCreateInternalAcctID`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800031b0`
- `0x180015d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180015d77`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180015d77`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180015d97`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180015d97`
- `DMCmnUtils!CopyString` at `0x180015db9`
- `DMCmnUtils!CopyString` at `0x180015db9`

## pseudocode

```c
HRESULT __fastcall OmaDmCreateInternalAcctID(__int64 a1, unsigned __int16 **a2)
{
  HRESULT result; // eax
  int v4; // eax
  GUID pguid; // [rsp+20h] [rbp-78h] BYREF
  OLECHAR sz; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int16 v7[39]; // [rsp+32h] [rbp-66h] BYREF

  pguid = 0;
  if ( !a2 )
    return -2147024809;
  result = CoCreateGuid(&pguid);
  if ( result >= 0 )
  {
    v4 = StringFromGUID2(&pguid, &sz, 39);
    if ( v4 )
      return CopyString(v7, v4 - 3, a2);
    else
      return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x180015d40  push    rbx
0x180015d42  sub     rsp, 90h
0x180015d49  mov     rax, cs:__security_cookie
0x180015d50  xor     rax, rsp
0x180015d53  mov     [rsp+98h+var_18], rax
0x180015d5b  xorps   xmm0, xmm0
0x180015d5e  mov     rbx, rdx
0x180015d61  movups  xmmword ptr [rsp+98h+pguid.Data1], xmm0
0x180015d66  test    rdx, rdx
0x180015d69  jnz     short loc_180015D72
0x180015d6b  mov     eax, 80070057h
0x180015d70  jmp     short loc_180015DC5
0x180015d72  lea     rcx, [rsp+98h+pguid]; pguid
0x180015d77  call    cs:__imp_CoCreateGuid
0x180015d7e  nop     dword ptr [rax+rax+00h]
0x180015d83  test    eax, eax
0x180015d85  js      short loc_180015DC5
0x180015d87  mov     r8d, 27h ; '''; cchMax
0x180015d8d  lea     rdx, [rsp+98h+sz]; lpsz
0x180015d92  lea     rcx, [rsp+98h+pguid]; rguid
0x180015d97  call    cs:__imp_StringFromGUID2
0x180015d9e  nop     dword ptr [rax+rax+00h]
0x180015da3  test    eax, eax
0x180015da5  jnz     short loc_180015DAE
0x180015da7  mov     eax, 80004005h
0x180015dac  jmp     short loc_180015DC5
0x180015dae  lea     edx, [rax-3]
0x180015db1  mov     r8, rbx
0x180015db4  lea     rcx, [rsp+98h+var_66]
0x180015db9  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180015dc0  nop     dword ptr [rax+rax+00h]
0x180015dc5  mov     rcx, [rsp+98h+var_18]
0x180015dcd  xor     rcx, rsp; StackCookie
0x180015dd0  call    __security_check_cookie
0x180015dd5  add     rsp, 90h
0x180015ddc  pop     rbx
0x180015ddd  retn
```
