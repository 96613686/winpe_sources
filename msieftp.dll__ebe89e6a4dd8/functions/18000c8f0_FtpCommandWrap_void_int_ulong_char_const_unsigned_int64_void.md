# FtpCommandWrap(void *,int,ulong,char const *,unsigned __int64,void * *)

- ea: `0x18000c8f0`
- end: `0x18000c934`
- name: `?FtpCommandWrap@@YAJPEAXHKPEBD_KPEAPEAX@Z`
- size: `68`
- prototype: `__int64 __fastcall(void *, int, unsigned int, const char *, unsigned __int64, HINTERNET *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ea10`
- `0x18001fa30`
- `0x180020618`

## callees

- `0x18000c8f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c917`
- `WININET!FtpCommandA` at `0x18000c90d`
- `WININET!FtpCommandA` at `0x18000c90d`

## pseudocode

```c
__int64 __fastcall FtpCommandWrap(
        void *a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        unsigned __int64 a5,
        HINTERNET *phFtpCommand)
{
  unsigned int v6; // ebx
  signed int LastError; // eax

  v6 = 0;
  if ( !FtpCommandA(a1, 0, 1u, a4, 0, phFtpCommand) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x18000c8f0  push    rbx
0x18000c8f2  sub     rsp, 30h
0x18000c8f6  mov     rax, [rsp+38h+arg_28]
0x18000c8fb  xor     ebx, ebx
0x18000c8fd  mov     [rsp+38h+phFtpCommand], rax; phFtpCommand
0x18000c902  xor     edx, edx; fExpectResponse
0x18000c904  mov     [rsp+38h+dwContext], rbx; dwContext
0x18000c909  lea     r8d, [rbx+1]; dwFlags
0x18000c90d  call    cs:__imp_FtpCommandA
0x18000c913  test    eax, eax
0x18000c915  jnz     short loc_18000C92C
0x18000c917  call    cs:__imp_GetLastError
0x18000c91d  mov     ebx, eax
0x18000c91f  test    eax, eax
0x18000c921  jle     short loc_18000C92C
0x18000c923  movzx   ebx, ax
0x18000c926  or      ebx, 80070000h
0x18000c92c  mov     eax, ebx
0x18000c92e  add     rsp, 30h
0x18000c932  pop     rbx
0x18000c933  retn
```
