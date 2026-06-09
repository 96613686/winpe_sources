# XmlReporter::OpenReport(ushort const *)

- ea: `0x180046688`
- end: `0x1800466cb`
- name: `?OpenReport@XmlReporter@@QEAAKPEBG@Z`
- size: `67`
- prototype: `unsigned int __fastcall(XmlReporter *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800424e0`
- `0x1800566b4`
- `0x180084900`
- `0x18008f294`

## callees

- `0x180046688`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!__doserrno` at `0x1800466ad`
- `api-ms-win-crt-runtime-l1-1-0!__doserrno` at `0x1800466ad`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x1800466a3`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x1800466a3`

## pseudocode

```c
__int64 __fastcall XmlReporter::OpenReport(XmlReporter *this, const unsigned __int16 *a2)
{
  unsigned int v2; // edi

  v2 = 0;
  if ( !*(_QWORD *)this )
  {
    if ( _wfopen_s((FILE **)this, a2, L"w, ccs=UTF-8") )
      return *__doserrno();
    else
      *((_DWORD *)this + 2) = 1;
  }
  return v2;
}

```

## disassembly

```asm
0x180046688  mov     [rsp+arg_0], rbx
0x18004668d  push    rdi
0x18004668e  sub     rsp, 20h
0x180046692  xor     edi, edi
0x180046694  mov     rbx, rcx
0x180046697  cmp     [rcx], rdi
0x18004669a  jnz     short loc_1800466BE
0x18004669c  lea     r8, aWCcsUtf8; "w, ccs=UTF-8"
0x1800466a3  call    cs:__imp__wfopen_s
0x1800466a9  test    eax, eax
0x1800466ab  jz      short loc_1800466B7
0x1800466ad  call    cs:__imp___doserrno
0x1800466b3  mov     edi, [rax]
0x1800466b5  jmp     short loc_1800466BE
0x1800466b7  mov     dword ptr [rbx+8], 1
0x1800466be  mov     rbx, [rsp+28h+arg_0]
0x1800466c3  mov     eax, edi
0x1800466c5  add     rsp, 20h
0x1800466c9  pop     rdi
0x1800466ca  retn
```
