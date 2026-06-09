# FileStream::Read(void *,ulong,ulong *)

- ea: `0x180013040`
- end: `0x18001307a`
- name: `?Read@FileStream@@UEAAJPEAXKPEAK@Z`
- size: `58`
- prototype: `__int64 __fastcall(HANDLE *this, void *, DWORD, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x180004a64`
- `0x180013040`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180013051`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180013051`

## pseudocode

```c
__int64 __fastcall FileStream::Read(HANDLE *this, void *a2, DWORD a3, unsigned int *a4)
{
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( ReadFile(this[1], a2, a3, a4, 0) )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x34,
             (unsigned int)"onecore\\base\\ntsetup\\provpackageapi\\inc\\FileStream.h",
             v4);
}

```

## disassembly

```asm
0x180013040  sub     rsp, 38h
0x180013044  mov     rcx, [rcx+8]; hFile
0x180013048  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180013051  call    cs:__imp_ReadFile
0x180013057  test    eax, eax
0x180013059  jnz     short loc_180013073
0x18001305b  mov     rcx, [rsp+38h]; this
0x180013060  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\provpackageapi"...
0x180013067  lea     edx, [rax+34h]; void *
0x18001306a  add     rsp, 38h
0x18001306e  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013073  xor     eax, eax
0x180013075  add     rsp, 38h
0x180013079  retn
```
