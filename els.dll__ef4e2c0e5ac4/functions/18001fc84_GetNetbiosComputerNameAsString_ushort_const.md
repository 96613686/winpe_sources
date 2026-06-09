# GetNetbiosComputerNameAsString(ushort const *)

- ea: `0x18001fc84`
- end: `0x18001fce7`
- name: `?GetNetbiosComputerNameAsString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016cd4`

## callees

- `0x180001750`
- `0x18001fc84`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x18001fcd8`
- `netutils!NetApiBufferFree` at `0x18001fcd8`
- `wkscli!NetWkstaGetInfo` at `0x18001fcaa`
- `wkscli!NetWkstaGetInfo` at `0x18001fcaa`

## pseudocode

```c
__int64 __fastcall GetNetbiosComputerNameAsString(__int64 a1, WCHAR *a2)
{
  const WCHAR *v3; // rdx
  LPBYTE bufptr; // [rsp+40h] [rbp+8h] BYREF

  bufptr = 0;
  if ( NetWkstaGetInfo(a2, 0x64u, &bufptr) )
    v3 = &String;
  else
    v3 = (const WCHAR *)*((_QWORD *)bufptr + 1);
  std::wstring::wstring(a1, v3);
  if ( bufptr )
    NetApiBufferFree(bufptr);
  return a1;
}

```

## disassembly

```asm
0x18001fc84  mov     [rsp+bufptr], rcx
0x18001fc89  push    rbx
0x18001fc8a  sub     rsp, 30h
0x18001fc8e  mov     rax, rdx
0x18001fc91  mov     [rsp+38h+bufptr], 0
0x18001fc9a  mov     rbx, rcx
0x18001fc9d  lea     r8, [rsp+38h+bufptr]; bufptr
0x18001fca2  mov     rcx, rax; servername
0x18001fca5  mov     edx, 64h ; 'd'; level
0x18001fcaa  call    cs:__imp_NetWkstaGetInfo
0x18001fcb0  test    eax, eax
0x18001fcb2  jnz     short loc_18001FCBF
0x18001fcb4  mov     rax, [rsp+38h+bufptr]
0x18001fcb9  mov     rdx, [rax+8]
0x18001fcbd  jmp     short loc_18001FCC6
0x18001fcbf  lea     rdx, String
0x18001fcc6  mov     rcx, rbx
0x18001fcc9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001fcce  mov     rcx, [rsp+38h+bufptr]; Buffer
0x18001fcd3  test    rcx, rcx
0x18001fcd6  jz      short loc_18001FCDE
0x18001fcd8  call    cs:__imp_NetApiBufferFree
0x18001fcde  mov     rax, rbx
0x18001fce1  add     rsp, 30h
0x18001fce5  pop     rbx
0x18001fce6  retn
```
