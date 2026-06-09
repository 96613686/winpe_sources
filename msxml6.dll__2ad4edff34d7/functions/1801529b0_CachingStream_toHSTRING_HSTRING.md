# CachingStream::toHSTRING(HSTRING__ * *)

- ea: `0x1801529b0`
- end: `0x180152adf`
- name: `?toHSTRING@CachingStream@@QEAAJPEAPEAUHSTRING__@@@Z`
- size: `303`
- prototype: `__int64 __fastcall(CachingStream *this, HSTRING__ **phstr)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800d4060`
- `0x1800f1a80`

## callees

- `0x18007e7b0`
- `0x1801529b0`
- `0x180185008`
- `0x180185d8c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180152a14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180152a14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x180152a3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x180152a3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180152a7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180152a7f`

## pseudocode

```c
__int64 __fastcall CachingStream::toHSTRING(CachingStream *this, HSTRING__ **phstr)
{
  UINT32 v3; // ebx
  HRESULT v5; // ebx
  HRESULT v6; // eax
  unsigned __int16 v7; // dx
  __int16 v8; // cx
  HSTRING_BUFFER__ *hbuf; // [rsp+40h] [rbp+8h] BYREF
  wchar_t *buf; // [rsp+48h] [rbp+10h] BYREF

  v3 = this->_cbUsed >> 1;
  buf = 0;
  hbuf = 0;
  if ( (xmmword_1801F6C20 & 0x10) != 0 )
    WPP_SF_qq(0x404u, 0x23u, WPP_66686eeb2e053756080759964cd4fee7_Traceguids, this, phstr);
  *phstr = 0;
  v5 = WindowsPreallocateStringBuffer(v3, &buf, &hbuf);
  if ( v5 < 0
    || (v5 = CachingStream::write_toBuffer(this, (unsigned __int8 *)buf, this->_cbUsed), v5 < 0)
    || (v6 = WindowsPromoteStringBuffer(hbuf, phstr), v5 = v6, v6 < 0) )
  {
    WindowsDeleteStringBuffer(hbuf);
    if ( (g_rgFastWppLevelEnabledFlags[2 * (v5 >> 31) + 4].rgbFlags[0] & 0x10) != 0 )
    {
      v7 = 37;
      v8 = (v5 >> 31) + 2;
      goto LABEL_10;
    }
  }
  else if ( (g_rgFastWppLevelEnabledFlags[2 * (v6 >> 31) + 4].rgbFlags[0] & 0x10) != 0 )
  {
    v7 = 36;
    v8 = (v6 >> 31) + 2;
LABEL_10:
    WPP_SF_d((v8 << 9) | 4, v7, WPP_66686eeb2e053756080759964cd4fee7_Traceguids, v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1801529b0  mov     rax, rsp
0x1801529b3  mov     [rax+18h], rbx
0x1801529b7  mov     [rax+20h], rsi
0x1801529bb  push    rdi
0x1801529bc  sub     rsp, 30h
0x1801529c0  mov     ebx, [this+48h]
0x1801529c3  mov     rsi, phstr
0x1801529c6  shr     ebx, 1
0x1801529c8  mov     rdi, this
0x1801529cb  mov     qword ptr [rax+10h], 0
0x1801529d3  mov     qword ptr [rax+8], 0
0x1801529db  test    byte ptr cs:xmmword_1801F6C20, 10h; __annotation("TMF:",
0x1801529e2  jz      short loc_180152A01
0x1801529e4  mov     edx, 23h ; '#'; id
0x1801529e9  mov     [rax-18h], rsi
0x1801529ed  mov     ecx, 404h; LevelKeyword
0x1801529f2  lea     r8, WPP_66686eeb2e053756080759964cd4fee7_Traceguids; TraceGuid
0x1801529f9  mov     r9, rdi; _a1
0x1801529fc  call    WPP_SF_qq
0x180152a01  lea     r8, [rsp+38h+hbuf]; bufferHandle
0x180152a06  mov     qword ptr [rsi], 0
0x180152a0d  lea     phstr, [rsp+38h+buf]; charBuffer
0x180152a12  mov     ecx, ebx; length
0x180152a14  call    cs:__imp_WindowsPreallocateStringBuffer
0x180152a1a  mov     ebx, eax
0x180152a1c  test    eax, eax
0x180152a1e  js      short $CleanUp_494
0x180152a20  mov     r8d, [rdi+48h]; cb
0x180152a24  mov     this, rdi; this
0x180152a27  mov     phstr, [rsp+38h+buf]; pbyte
0x180152a2c  call    ?write_toBuffer@CachingStream@@IEAAJPEAEK@Z; CachingStream::write_toBuffer(uchar *,ulong)
0x180152a31  mov     ebx, eax
0x180152a33  test    eax, eax
0x180152a35  js      short $CleanUp_494
0x180152a37  mov     this, [rsp+38h+hbuf]; bufferHandle
0x180152a3c  mov     phstr, rsi; string
0x180152a3f  call    cs:__imp_WindowsPromoteStringBuffer
0x180152a45  mov     ebx, eax
0x180152a47  test    eax, eax
0x180152a49  js      short $CleanUp_494
0x180152a4b  mov     r9d, eax; __annotation("TMF:",
0x180152a4e  sar     r9d, 1Fh
0x180152a52  lea     eax, ds:4[r9*2]
0x180152a5a  movsxd  this, eax
0x180152a5d  lea     rax, g_rgFastWppLevelEnabledFlags
0x180152a64  test    byte ptr [rax+this*8], 10h
0x180152a68  jz      short loc_180152ACD
0x180152a6a  add     r9w, 2
0x180152a6f  mov     edx, 24h ; '$'
0x180152a74  movzx   ecx, r9w
0x180152a78  jmp     short loc_180152AB2
0x180152a7a  mov     this, [rsp+38h+hbuf]; bufferHandle
0x180152a7f  call    cs:__imp_WindowsDeleteStringBuffer
0x180152a85  mov     r8d, ebx; __annotation("TMF:",
0x180152a88  sar     r8d, 1Fh
0x180152a8c  lea     eax, ds:4[r8*2]
0x180152a94  movsxd  this, eax
0x180152a97  lea     rax, g_rgFastWppLevelEnabledFlags
0x180152a9e  test    byte ptr [rax+this*8], 10h
0x180152aa2  jz      short loc_180152ACD
0x180152aa4  add     r8w, 2
0x180152aa9  mov     edx, 25h ; '%'; id
0x180152aae  movzx   ecx, r8w
0x180152ab2  mov     eax, 200h
0x180152ab7  lea     r8, WPP_66686eeb2e053756080759964cd4fee7_Traceguids; TraceGuid
0x180152abe  imul    ecx, eax
0x180152ac1  mov     r9d, ebx; _a1
0x180152ac4  or      cx, 4; LevelKeyword
0x180152ac8  call    WPP_SF_d
0x180152acd  mov     rsi, [rsp+38h+arg_18]
0x180152ad2  mov     eax, ebx
0x180152ad4  mov     rbx, [rsp+38h+arg_10]
0x180152ad9  add     rsp, 30h
0x180152add  pop     rdi
0x180152ade  retn
```
