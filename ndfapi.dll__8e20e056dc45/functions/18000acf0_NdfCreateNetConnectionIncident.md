# NdfCreateNetConnectionIncident

- ea: `0x18000acf0`
- end: `0x18000adb7`
- name: `NdfCreateNetConnectionIncident`
- size: `199`
- prototype: `HRESULT __stdcall(NDFHANDLE *handle, GUID *__struct_ptr id)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009600`

## callees

- `0x18000721c`
- `0x1800098b0`
- `0x18000a9e0`
- `0x18000acf0`

## import_xrefs

- `wdi!WdiCancel` at `0x18000ad3d`
- `wdi!WdiCancel` at `0x18000ad3d`

## string_xrefs

- `0x18000ad15`: `NdfCreateNetConnectionIncident`

## pseudocode

```c
HRESULT __stdcall NdfCreateNetConnectionIncident(NDFHANDLE *handle, GUID *id)
{
  HRESULT result; // eax
  GUID v5; // xmm0
  size_t v6[4]; // [rsp+20h] [rbp-B8h] BYREF
  HELPER_ATTRIBUTE attributes; // [rsp+40h] [rbp-98h] BYREF

  v6[3] = 15;
  v6[2] = 0;
  LOBYTE(v6[0]) = 0;
  std::string::assign(v6, "NdfCreateNetConnectionIncident", 0x1Eu);
  TelemeterAPICall(v6);
  if ( (unsigned int)WdiCancel(0) == -2147023611 )
    return -2147467260;
  if ( !handle )
    return -2146895611;
  v5 = *id;
  attributes.type = AT_GUID;
  attributes.pwszName = L"guid";
  attributes.Guid = v5;
  result = NdfCreateIncident(L"NetConnection", 1u, &attributes, handle);
  if ( result >= 0 )
  {
    if ( *handle )
      *((_DWORD *)*handle + 4) = 6;
  }
  return result;
}

```

## disassembly

```asm
0x18000acf0  mov     [rsp+arg_0], rbx
0x18000acf5  push    rdi
0x18000acf6  sub     rsp, 0D0h
0x18000acfd  mov     rdi, rdx
0x18000ad00  mov     [rsp+0D8h+var_A0], 0Fh
0x18000ad09  mov     rbx, rcx
0x18000ad0c  mov     [rsp+0D8h+var_A8], 0
0x18000ad15  lea     rdx, aNdfcreatenetco_0; "NdfCreateNetConnectionIncident"
0x18000ad1c  mov     [rsp+0D8h+var_B8], 0
0x18000ad21  lea     rcx, [rsp+0D8h+var_B8]; void *
0x18000ad26  mov     r8d, 1Eh; Size
0x18000ad2c  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x18000ad31  lea     rcx, [rsp+0D8h+var_B8]
0x18000ad36  call    ?TelemeterAPICall@@YAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; TelemeterAPICall(std::string)
0x18000ad3b  xor     ecx, ecx
0x18000ad3d  call    cs:__imp_WdiCancel
0x18000ad43  cmp     eax, 80070505h
0x18000ad48  jnz     short loc_18000AD51
0x18000ad4a  mov     eax, 80004004h
0x18000ad4f  jmp     short loc_18000ADA6
0x18000ad51  test    rbx, rbx
0x18000ad54  jnz     short loc_18000AD5D
0x18000ad56  mov     eax, 8008F905h
0x18000ad5b  jmp     short loc_18000ADA6
0x18000ad5d  movups  xmm0, xmmword ptr [rdi]
0x18000ad60  lea     rax, aGuid; "guid"
0x18000ad67  mov     [rsp+0D8h+attributes.type], 0Bh
0x18000ad6f  mov     r9, rbx; handle
0x18000ad72  mov     [rsp+0D8h+attributes.pwszName], rax
0x18000ad77  lea     r8, [rsp+0D8h+attributes]; attributes
0x18000ad7c  mov     edx, 1; celt
0x18000ad81  lea     rcx, aNetconnection; "NetConnection"
0x18000ad88  movdqu  xmmword ptr [rsp+0D8h+attributes.10h], xmm0
0x18000ad8e  call    NdfCreateIncident
0x18000ad93  test    eax, eax
0x18000ad95  js      short loc_18000ADA6
0x18000ad97  mov     rcx, [rbx]
0x18000ad9a  test    rcx, rcx
0x18000ad9d  jz      short loc_18000ADA6
0x18000ad9f  mov     dword ptr [rcx+10h], 6
0x18000ada6  mov     rbx, [rsp+0D8h+arg_0]
0x18000adae  add     rsp, 0D0h
0x18000adb5  pop     rdi
0x18000adb6  retn
```
