# PmIsEqualName(_GUID const *,ushort const *)

- ea: `0x14000cc88`
- end: `0x14000cd0f`
- name: `?PmIsEqualName@@YAEPEBU_GUID@@PEBG@Z`
- size: `135`
- prototype: `bool __fastcall(const struct _GUID *, const unsigned __int16 *Source2)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000a21c`

## callees

- `0x14000cdac`
- `0x140010f20`
- `0x140011440`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000ccda`
- `ntoskrnl!RtlCompareMemory` at `0x14000ccda`

## pseudocode

```c
bool __fastcall PmIsEqualName(const struct _GUID *a1, const unsigned __int16 *Source2)
{
  unsigned __int16 Source1[72]; // [rsp+20h] [rbp-A8h] BYREF

  memset(Source1, 0, sizeof(Source1));
  PmNameFromGuid(a1, Source1);
  return RtlCompareMemory(Source1, Source2, 0x48u) == 72;
}

```

## disassembly

```asm
0x14000cc88  mov     [rsp+arg_10], rbx
0x14000cc8d  push    rdi
0x14000cc8e  sub     rsp, 0C0h
0x14000cc95  mov     rax, cs:__security_cookie
0x14000cc9c  xor     rax, rsp
0x14000cc9f  mov     [rsp+0C8h+var_18], rax
0x14000cca7  mov     rdi, rdx
0x14000ccaa  mov     rbx, rcx
0x14000ccad  xor     edx, edx; Val
0x14000ccaf  lea     rcx, [rsp+0C8h+Source1]; void *
0x14000ccb4  mov     r8d, 90h; Size
0x14000ccba  call    memset
0x14000ccbf  lea     rdx, [rsp+0C8h+Source1]; unsigned __int16 *
0x14000ccc4  mov     rcx, rbx; struct _GUID *
0x14000ccc7  call    ?PmNameFromGuid@@YAXPEBU_GUID@@PEAG@Z; PmNameFromGuid(_GUID const *,ushort *)
0x14000cccc  mov     r8d, 48h ; 'H'; Length
0x14000ccd2  lea     rcx, [rsp+0C8h+Source1]; Source1
0x14000ccd7  mov     rdx, rdi; Source2
0x14000ccda  call    cs:__imp_RtlCompareMemory
0x14000cce1  nop     dword ptr [rax+rax+00h]
0x14000cce6  cmp     rax, 48h ; 'H'
0x14000ccea  setz    al
0x14000cced  mov     rcx, [rsp+0C8h+var_18]
0x14000ccf5  xor     rcx, rsp; StackCookie
0x14000ccf8  call    __security_check_cookie
0x14000ccfd  mov     rbx, [rsp+0C8h+arg_10]
0x14000cd05  add     rsp, 0C0h
0x14000cd0c  pop     rdi
0x14000cd0d  retn
```
