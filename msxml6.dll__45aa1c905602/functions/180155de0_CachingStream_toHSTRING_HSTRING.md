# CachingStream::toHSTRING(HSTRING__ * *)

- ea: `0x180155de0`
- end: `0x180155f22`
- name: `?toHSTRING@CachingStream@@QEAAJPEAPEAUHSTRING__@@@Z`
- size: `322`
- prototype: `HRESULT __fastcall(CachingStream *this, HSTRING__ **phstr)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800d5c70`
- `0x1800f3f00`

## callees

- `0x18007e048`
- `0x180155de0`
- `0x180189008`
- `0x180189d98`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180155e44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x180155e44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x180155e75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x180155e75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180155ebb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180155ebb`

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
  if ( (xmmword_1801FAD20 & 0x10) != 0 )
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
0x180155de0  mov     rax, rsp
0x180155de3  mov     [rax+18h], rbx
0x180155de7  mov     [rax+20h], rsi
0x180155deb  push    rdi
0x180155dec  sub     rsp, 30h
0x180155df0  mov     ebx, [this+48h]
0x180155df3  mov     rsi, phstr
0x180155df6  shr     ebx, 1
0x180155df8  mov     rdi, this
0x180155dfb  mov     qword ptr [rax+10h], 0
0x180155e03  mov     qword ptr [rax+8], 0
0x180155e0b  test    byte ptr cs:xmmword_1801FAD20, 10h; __annotation("TMF:",
0x180155e12  jz      short loc_180155E31
0x180155e14  mov     edx, 23h ; '#'; id
0x180155e19  mov     [rax-18h], rsi
0x180155e1d  mov     ecx, 404h; LevelKeyword
0x180155e22  lea     r8, WPP_66686eeb2e053756080759964cd4fee7_Traceguids; TraceGuid
0x180155e29  mov     r9, rdi; _a1
0x180155e2c  call    WPP_SF_qq
0x180155e31  lea     r8, [rsp+38h+hbuf]; bufferHandle
0x180155e36  mov     qword ptr [rsi], 0
0x180155e3d  lea     phstr, [rsp+38h+buf]; charBuffer
0x180155e42  mov     ecx, ebx; length
0x180155e44  call    cs:__imp_WindowsPreallocateStringBuffer
0x180155e4b  nop     dword ptr [rax+rax+00h]
0x180155e50  mov     ebx, eax
0x180155e52  test    eax, eax
0x180155e54  js      short $CleanUp_494
0x180155e56  mov     r8d, [rdi+48h]; cb
0x180155e5a  mov     this, rdi; this
0x180155e5d  mov     phstr, [rsp+38h+buf]; pbyte
0x180155e62  call    ?write_toBuffer@CachingStream@@IEAAJPEAEK@Z; CachingStream::write_toBuffer(uchar *,ulong)
0x180155e67  mov     ebx, eax
0x180155e69  test    eax, eax
0x180155e6b  js      short $CleanUp_494
0x180155e6d  mov     this, [rsp+38h+hbuf]; bufferHandle
0x180155e72  mov     phstr, rsi; string
0x180155e75  call    cs:__imp_WindowsPromoteStringBuffer
0x180155e7c  nop     dword ptr [rax+rax+00h]
0x180155e81  mov     ebx, eax
0x180155e83  test    eax, eax
0x180155e85  js      short $CleanUp_494
0x180155e87  mov     r9d, eax; __annotation("TMF:",
0x180155e8a  sar     r9d, 1Fh
0x180155e8e  lea     eax, ds:4[r9*2]
0x180155e96  movsxd  this, eax
0x180155e99  lea     rax, g_rgFastWppLevelEnabledFlags
0x180155ea0  test    byte ptr [rax+this*8], 10h
0x180155ea4  jz      short loc_180155F0F
0x180155ea6  add     r9w, 2
0x180155eab  mov     edx, 24h ; '$'
0x180155eb0  movzx   ecx, r9w
0x180155eb4  jmp     short loc_180155EF4
0x180155eb6  mov     this, [rsp+38h+hbuf]; bufferHandle
0x180155ebb  call    cs:__imp_WindowsDeleteStringBuffer
0x180155ec2  nop     dword ptr [rax+rax+00h]
0x180155ec7  mov     r8d, ebx; __annotation("TMF:",
0x180155eca  sar     r8d, 1Fh
0x180155ece  lea     eax, ds:4[r8*2]
0x180155ed6  movsxd  this, eax
0x180155ed9  lea     rax, g_rgFastWppLevelEnabledFlags
0x180155ee0  test    byte ptr [rax+this*8], 10h
0x180155ee4  jz      short loc_180155F0F
0x180155ee6  add     r8w, 2
0x180155eeb  mov     edx, 25h ; '%'; id
0x180155ef0  movzx   ecx, r8w
0x180155ef4  mov     eax, 200h
0x180155ef9  lea     r8, WPP_66686eeb2e053756080759964cd4fee7_Traceguids; TraceGuid
0x180155f00  imul    ecx, eax
0x180155f03  mov     r9d, ebx; _a1
0x180155f06  or      cx, 4; LevelKeyword
0x180155f0a  call    WPP_SF_d
0x180155f0f  mov     rsi, [rsp+38h+arg_18]
0x180155f14  mov     eax, ebx
0x180155f16  mov     rbx, [rsp+38h+arg_10]
0x180155f1b  add     rsp, 30h
0x180155f1f  pop     rdi
0x180155f20  retn
```
