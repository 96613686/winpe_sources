# CString::Length(void)

- ea: `0x18001a708`
- end: `0x18001a734`
- name: `?Length@CString@@QEBAHXZ`
- size: `44`
- prototype: `__int64 __fastcall(CString *__hidden this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18001270c`
- `0x180012b10`
- `0x180013b8c`
- `0x180013d44`
- `0x180014220`
- `0x180014ca8`
- `0x18001510c`
- `0x180016470`
- `0x18001a888`
- `0x18001bb38`
- `0x18001bf58`
- `0x18001bfc8`

## callees

- `0x18001a708`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18001a721`
- `KERNEL32!lstrlenW` at `0x18001a721`

## pseudocode

```c
int __fastcall CString::Length(CString *this)
{
  __int64 v1; // rbx
  int result; // eax

  v1 = *((_QWORD *)this + 1);
  result = *(_DWORD *)(v1 + 16);
  if ( !result )
  {
    if ( *(_QWORD *)v1 )
    {
      result = lstrlenW(*(LPCWSTR *)v1);
      *(_DWORD *)(v1 + 16) = result;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001a708  push    rbx
0x18001a70a  sub     rsp, 20h
0x18001a70e  mov     rbx, [rcx+8]
0x18001a712  mov     eax, [rbx+10h]
0x18001a715  test    eax, eax
0x18001a717  jnz     short loc_18001A72E
0x18001a719  mov     rcx, [rbx]; lpString
0x18001a71c  test    rcx, rcx
0x18001a71f  jz      short loc_18001A72C
0x18001a721  call    cs:__imp_lstrlenW
0x18001a727  mov     [rbx+10h], eax
0x18001a72a  jmp     short loc_18001A72E
0x18001a72c  xor     eax, eax
0x18001a72e  add     rsp, 20h
0x18001a732  pop     rbx
0x18001a733  retn
```
