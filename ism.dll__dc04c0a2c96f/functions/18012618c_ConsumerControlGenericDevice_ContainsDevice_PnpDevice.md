# ConsumerControlGenericDevice::ContainsDevice(PnpDevice *)

- ea: `0x18012618c`
- end: `0x180126221`
- name: `?ContainsDevice@ConsumerControlGenericDevice@@QEAA_NPEAVPnpDevice@@@Z`
- size: `149`
- prototype: `bool(ConsumerControlGenericDevice *__hidden this, struct PnpDevice *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800e13c8`

## callees

- `0x18008e2b4`
- `0x18012618c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801261ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801261ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801261a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012620e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801261a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012620e`

## pseudocode

```c
bool __fastcall ConsumerControlGenericDevice::ContainsDevice(ConsumerControlGenericDevice *this, struct PnpDevice *a2)
{
  bool v4; // bl
  HSTRING v5; // rcx
  INT32 result; // [rsp+40h] [rbp+18h] BYREF
  HSTRING string2; // [rsp+48h] [rbp+20h] BYREF

  string2 = 0;
  WindowsDeleteString(0);
  string2 = 0;
  if ( (int)PnpDevice::GetInterfacePath(a2, &string2) < 0 )
    goto LABEL_2;
  v5 = (HSTRING)*((_QWORD *)this + 3);
  if ( !v5 )
  {
    v4 = string2 == 0;
    goto LABEL_9;
  }
  if ( !string2 || (result = 0, WindowsCompareStringOrdinal(v5, string2, &result) < 0) || result )
LABEL_2:
    v4 = 0;
  else
    v4 = 1;
LABEL_9:
  WindowsDeleteString(string2);
  return v4;
}

```

## disassembly

```asm
0x18012618c  mov     [rsp+arg_0], rbx
0x180126191  push    rdi
0x180126192  sub     rsp, 20h
0x180126196  mov     rdi, rcx
0x180126199  mov     [rsp+28h+string2], 0
0x1801261a2  xor     ecx, ecx; string
0x1801261a4  mov     rbx, rdx
0x1801261a7  call    cs:__imp_WindowsDeleteString
0x1801261ad  lea     rdx, [rsp+28h+string2]; HSTRING *
0x1801261b2  mov     [rsp+28h+string2], 0
0x1801261bb  mov     rcx, rbx; this
0x1801261be  call    ?GetInterfacePath@PnpDevice@@QEAAJPEAPEAUHSTRING__@@@Z; PnpDevice::GetInterfacePath(HSTRING__ * *)
0x1801261c3  test    eax, eax
0x1801261c5  jns     short loc_1801261CB
0x1801261c7  xor     bl, bl
0x1801261c9  jmp     short loc_180126209
0x1801261cb  mov     rcx, [rdi+18h]; string1
0x1801261cf  mov     rax, [rsp+28h+string2]
0x1801261d4  test    rcx, rcx
0x1801261d7  jz      short loc_180126203
0x1801261d9  test    rax, rax
0x1801261dc  jz      short loc_1801261C7
0x1801261de  lea     r8, [rsp+28h+result]; result
0x1801261e3  mov     [rsp+28h+result], 0
0x1801261eb  mov     rdx, rax; string2
0x1801261ee  call    cs:__imp_WindowsCompareStringOrdinal
0x1801261f4  test    eax, eax
0x1801261f6  js      short loc_1801261C7
0x1801261f8  cmp     [rsp+28h+result], 0
0x1801261fd  jnz     short loc_1801261C7
0x1801261ff  mov     bl, 1
0x180126201  jmp     short loc_180126209
0x180126203  test    rax, rax
0x180126206  setz    bl
0x180126209  mov     rcx, [rsp+28h+string2]; string
0x18012620e  call    cs:__imp_WindowsDeleteString
0x180126214  mov     al, bl
0x180126216  mov     rbx, [rsp+28h+arg_0]
0x18012621b  add     rsp, 20h
0x18012621f  pop     rdi
0x180126220  retn
```
