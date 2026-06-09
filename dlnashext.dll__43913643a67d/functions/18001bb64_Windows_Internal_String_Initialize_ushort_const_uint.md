# Windows::Internal::String::Initialize(ushort const *,uint)

- ea: `0x18001bb64`
- end: `0x18001bba1`
- name: `?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z`
- size: `61`
- prototype: `__int64 __fastcall(HSTRING *this, PCNZWCH sourceString, UINT32 length)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d68c`
- `0x18001cc50`

## callees

- `0x18001b3b8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001bb86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001bb86`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::Initialize(HSTRING *this, PCNZWCH sourceString, UINT32 length)
{
  HRESULT v4; // eax
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF

  string = 0;
  v4 = WindowsCreateString(sourceString, length, &string);
  return Windows::Internal::String::FreeAndAssignOnSuccess(v4, string, this);
}

```

## disassembly

```asm
0x18001bb64  push    rbx
0x18001bb66  sub     rsp, 20h
0x18001bb6a  mov     eax, r8d
0x18001bb6d  mov     [rsp+28h+string], 0
0x18001bb76  mov     r9, rdx
0x18001bb79  lea     r8, [rsp+28h+string]; string
0x18001bb7e  mov     rbx, rcx
0x18001bb81  mov     edx, eax; length
0x18001bb83  mov     rcx, r9; sourceString
0x18001bb86  call    cs:__imp_WindowsCreateString
0x18001bb8c  mov     rdx, [rsp+28h+string]; HSTRING
0x18001bb91  mov     r8, rbx; HSTRING *
0x18001bb94  mov     ecx, eax; int
0x18001bb96  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x18001bb9b  add     rsp, 20h
0x18001bb9f  pop     rbx
0x18001bba0  retn
```
