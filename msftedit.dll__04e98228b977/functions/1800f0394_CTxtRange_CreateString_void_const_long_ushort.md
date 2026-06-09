# CTxtRange::CreateString(void const *,long,ushort * *)

- ea: `0x1800f0394`
- end: `0x1800f03fd`
- name: `?CreateString@CTxtRange@@QEAAJPEBXJPEAPEAG@Z`
- size: `105`
- prototype: `int(CTxtRange *__hidden this, const void *, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180015720`

## callees

- `0x1800f0394`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800f03b4`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800f03b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f03e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800f03e0`

## pseudocode

```c
HRESULT __fastcall CTxtRange::CreateString(CTxtRange *this, const WCHAR *a2, signed int a3, unsigned __int16 **a4)
{
  HRESULT result; // eax
  HSTRING string; // [rsp+48h] [rbp+20h] BYREF

  if ( !a4 )
    return -2147024809;
  if ( (*((_DWORD *)this + 29) & 0x100000) != 0 )
  {
    string = 0;
    result = WindowsCreateString(a2, (unsigned __int64)a3 >> 1, &string);
    *a4 = (unsigned __int16 *)string;
  }
  else
  {
    *a4 = SysAllocStringByteLen((LPCSTR)a2, a3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800f0394  push    rbx
0x1800f0396  sub     rsp, 20h
0x1800f039a  mov     rbx, r9
0x1800f039d  mov     rax, rdx
0x1800f03a0  test    r9, r9
0x1800f03a3  jz      short loc_1800F03F6
0x1800f03a5  test    dword ptr [rcx+74h], 100000h
0x1800f03ac  mov     rcx, rdx; sourceString
0x1800f03af  jnz     short loc_1800F03CC
0x1800f03b1  mov     edx, r8d; len
0x1800f03b4  call    cs:__imp_SysAllocStringByteLen
0x1800f03bb  nop     dword ptr [rax+rax+00h]
0x1800f03c0  mov     [rbx], rax
0x1800f03c3  xor     eax, eax
0x1800f03c5  add     rsp, 20h
0x1800f03c9  pop     rbx
0x1800f03ca  retn
0x1800f03cc  movsxd  rdx, r8d
0x1800f03cf  lea     r8, [rsp+28h+string]; string
0x1800f03d4  shr     rdx, 1; length
0x1800f03d7  mov     [rsp+28h+string], 0
0x1800f03e0  call    cs:__imp_WindowsCreateString
0x1800f03e7  nop     dword ptr [rax+rax+00h]
0x1800f03ec  mov     rcx, [rsp+28h+string]
0x1800f03f1  mov     [rbx], rcx
0x1800f03f4  jmp     short loc_1800F03C5
0x1800f03f6  mov     eax, 80070057h
0x1800f03fb  jmp     short loc_1800F03C5
```
