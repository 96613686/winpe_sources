# RemovePort

- ea: `0x180014ca0`
- end: `0x180014ddf`
- name: `RemovePort`
- size: `319`
- prototype: `__int64 __fastcall(char *String1)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000d92c`
- `0x18000f53c`
- `0x180012340`
- `0x180014ca0`

## import_xrefs

- `msvcrt!_stricmp` at `0x180014ce0`
- `msvcrt!_stricmp` at `0x180014ce0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014dc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014dc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014db6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014db6`

## string_xrefs

- `0x180014cc4`: `RemovePort: %s`
- `0x180014da3`: `RemovePort: port %s not found`
- `0x180014d2f`: `RemovePort: removing %s`
- `0x180014d47`: `RemovePort: Marking %s for removal`
- `0x180014d57`: `RemovePorT: Changing state of %s from %d -> %d`
- `0x180014d92`: `RemovePort. dwnumEndPoints for port = %d`

## pseudocode

```c
__int64 __fastcall RemovePort(char *String1, __int64 a2, __int64 a3, __int64 a4)
{
  const char *v4; // rbx
  int v5; // r14d
  unsigned int v7; // ebp
  char *v8; // rdi
  __int64 v9; // rbx
  int v10; // edx
  int v11; // eax

  v4 = (const char *)RasPortsList;
  v5 = a2;
  v7 = 0;
  v8 = 0;
  GetMutex(String1, a2, a3, a4);
  RasTapiTrace("RemovePort: %s");
  if ( !v4 )
    goto LABEL_15;
  do
  {
    if ( !_stricmp(String1, v4 + 24) )
    {
      v8 = (char *)v4;
      if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v4 + 27) + 40LL) + 96LL) || *((_DWORD *)v4 + 14) == 7 )
        break;
    }
    v4 = (const char *)*((_QWORD *)v4 + 1);
  }
  while ( v4 );
  if ( v8 )
  {
    v9 = *(_QWORD *)(*((_QWORD *)v8 + 27) + 40LL);
    if ( v5 )
    {
      RasTapiTrace("RemovePort: removing %s");
      v7 = dwRemovePort(v8);
    }
    else
    {
      RasTapiTrace("RemovePort: Marking %s for removal");
      RasTapiTrace("RemovePorT: Changing state of %s from %d -> %d");
      *((_DWORD *)v8 + 276) |= 1u;
      *((_DWORD *)v8 + 14) = 7;
    }
    v10 = *(_DWORD *)(v9 + 76);
    if ( v10 )
      *(_DWORD *)(v9 + 76) = v10 - 1;
    v11 = *(_DWORD *)(v9 + 12);
    if ( v11 )
      *(_DWORD *)(v9 + 12) = v11 - 1;
    RasTapiTrace("RemovePort. dwnumEndPoints for port = %d");
  }
  else
  {
LABEL_15:
    RasTapiTrace("RemovePort: port %s not found");
  }
  if ( !ReleaseMutex(RasTapiMutex) )
    GetLastError();
  RasTapiTrace(" ");
  return v7;
}

```

## disassembly

```asm
0x180014ca0  push    rbx
0x180014ca2  push    rbp
0x180014ca3  push    rsi
0x180014ca4  push    rdi
0x180014ca5  push    r14
0x180014ca7  sub     rsp, 20h
0x180014cab  mov     rbx, cs:RasPortsList
0x180014cb2  mov     r14d, edx
0x180014cb5  mov     rsi, rcx
0x180014cb8  xor     ebp, ebp
0x180014cba  xor     edi, edi
0x180014cbc  call    GetMutex
0x180014cc1  mov     rdx, rsi
0x180014cc4  lea     rcx, aRemoveportS; "RemovePort: %s"
0x180014ccb  call    RasTapiTrace
0x180014cd0  test    rbx, rbx
0x180014cd3  jz      loc_180014DA0
0x180014cd9  lea     rdx, [rbx+18h]; String2
0x180014cdd  mov     rcx, rsi; String1
0x180014ce0  call    cs:__imp__stricmp
0x180014ce6  test    eax, eax
0x180014ce8  jnz     short loc_180014D06
0x180014cea  mov     rax, [rbx+0D8h]
0x180014cf1  mov     rdi, rbx
0x180014cf4  mov     rcx, [rax+28h]
0x180014cf8  movzx   eax, word ptr [rcx+60h]
0x180014cfc  test    eax, eax
0x180014cfe  jnz     short loc_180014D0F
0x180014d00  cmp     dword ptr [rbx+38h], 7
0x180014d04  jz      short loc_180014D0F
0x180014d06  mov     rbx, [rbx+8]
0x180014d0a  test    rbx, rbx
0x180014d0d  jnz     short loc_180014CD9
0x180014d0f  test    rdi, rdi
0x180014d12  jz      loc_180014DA0
0x180014d18  mov     rax, [rdi+0D8h]
0x180014d1f  lea     rsi, [rdi+18h]
0x180014d23  mov     rdx, rsi
0x180014d26  mov     rbx, [rax+28h]
0x180014d2a  test    r14d, r14d
0x180014d2d  jz      short loc_180014D47
0x180014d2f  lea     rcx, aRemoveportRemo; "RemovePort: removing %s"
0x180014d36  call    RasTapiTrace
0x180014d3b  mov     rcx, rdi; hMem
0x180014d3e  call    dwRemovePort
0x180014d43  mov     ebp, eax
0x180014d45  jmp     short loc_180014D7A
0x180014d47  lea     rcx, aRemoveportMark; "RemovePort: Marking %s for removal"
0x180014d4e  call    RasTapiTrace
0x180014d53  mov     r8d, [rdi+38h]
0x180014d57  lea     rcx, aRemoveportChan; "RemovePorT: Changing state of %s from %"...
0x180014d5e  mov     r9d, 7
0x180014d64  mov     rdx, rsi
0x180014d67  call    RasTapiTrace
0x180014d6c  or      dword ptr [rdi+450h], 1
0x180014d73  mov     dword ptr [rdi+38h], 7
0x180014d7a  mov     edx, [rbx+4Ch]
0x180014d7d  test    edx, edx
0x180014d7f  jz      short loc_180014D86
0x180014d81  dec     edx
0x180014d83  mov     [rbx+4Ch], edx
0x180014d86  mov     eax, [rbx+0Ch]
0x180014d89  test    eax, eax
0x180014d8b  jz      short loc_180014D92
0x180014d8d  dec     eax
0x180014d8f  mov     [rbx+0Ch], eax
0x180014d92  lea     rcx, aRemoveportDwnu; "RemovePort. dwnumEndPoints for port = %"...
0x180014d99  call    RasTapiTrace
0x180014d9e  jmp     short loc_180014DAF
0x180014da0  mov     rdx, rsi
0x180014da3  lea     rcx, aRemoveportPort; "RemovePort: port %s not found"
0x180014daa  call    RasTapiTrace
0x180014daf  mov     rcx, cs:RasTapiMutex; hMutex
0x180014db6  call    cs:__imp_ReleaseMutex
0x180014dbc  test    eax, eax
0x180014dbe  jnz     short loc_180014DC6
0x180014dc0  call    cs:__imp_GetLastError
0x180014dc6  lea     rcx, asc_18002C0B8; " "
0x180014dcd  call    RasTapiTrace
0x180014dd2  mov     eax, ebp
0x180014dd4  add     rsp, 20h
0x180014dd8  pop     r14
0x180014dda  pop     rdi
0x180014ddb  pop     rsi
0x180014ddc  pop     rbp
0x180014ddd  pop     rbx
0x180014dde  retn
```
