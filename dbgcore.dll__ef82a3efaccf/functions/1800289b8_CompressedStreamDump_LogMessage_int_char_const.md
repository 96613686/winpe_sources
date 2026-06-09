# CompressedStreamDump::LogMessage(int,char const *,...)

- ea: `0x1800289b8`
- end: `0x180028b11`
- name: `?LogMessage@CompressedStreamDump@@YAXHPEBDZZ`
- size: `345`
- prototype: `void(CompressedStreamDump *__hidden this, int, const char *, ...)`
- caller_count: `28`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001ddd8`
- `0x18001e028`
- `0x18001e114`
- `0x18001e804`
- `0x18001e8f0`
- `0x18001ec7c`
- `0x18001ee10`
- `0x180027938`
- `0x18002811c`
- `0x180028284`
- `0x18002845c`
- `0x18002849c`
- `0x1800295f0`
- `0x1800296d0`
- `0x18002978c`
- `0x180029974`
- `0x180029b30`
- `0x180029d68`
- `0x180029ff8`
- `0x18002b30c`
- `0x18002b353`
- `0x18002b39a`
- `0x18002b3d4`
- `0x18002b41b`
- `0x18002b462`
- `0x18002b50a`
- `0x18002b551`
- `0x18002b598`

## callees

- `0x180001710`
- `0x18000204e`
- `0x18000207e`
- `0x180010548`
- `0x1800289b8`
- `0x180028f34`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180028a35`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180028a35`

## pseudocode

```c
void CompressedStreamDump::LogMessage(CompressedStreamDump *this, const char *a2, const char *a3, ...)
{
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  const char *v6; // rbx
  FILE *v7; // rbx
  unsigned __int64 *v8; // rax
  _QWORD SystemTime[3]; // [rsp+58h] [rbp-B0h] BYREF
  char Buffer[64]; // [rsp+78h] [rbp-90h] BYREF
  char Format[1024]; // [rsp+B8h] [rbp-50h] BYREF
  const char *ArgList; // [rsp+4F8h] [rbp+3F0h] BYREF

  ArgList = a3;
  v3 = (_DWORD)this - 1;
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      v5 = v4 - 2;
      if ( v5 )
      {
        if ( v5 == 4 )
          v6 = "DATA MISSING";
        else
          v6 = "UNKNOWN";
      }
      else
      {
        v6 = "ERROR";
      }
    }
    else
    {
      v6 = "WARNING";
    }
  }
  else
  {
    v6 = "INFO";
  }
  *(_OWORD *)&SystemTime[1] = 0;
  GetLocalTime((LPSYSTEMTIME)&SystemTime[1]);
  snprintf(
    Buffer,
    0x40u,
    "[%04d-%02d-%02d %02d:%02d:%02d.%03d]",
    LOWORD(SystemTime[1]),
    WORD1(SystemTime[1]),
    HIWORD(SystemTime[1]),
    LOWORD(SystemTime[2]),
    WORD1(SystemTime[2]),
    WORD2(SystemTime[2]),
    HIWORD(SystemTime[2]));
  snprintf(Format, 0x400u, "%s %s: %s", Buffer, v6, a2);
  v7 = o___acrt_iob_func_0(1u);
  v8 = _local_stdio_printf_options();
  o___stdio_common_vfprintf_s_0(*v8, v7, Format, 0, (va_list)&ArgList);
}

```

## disassembly

```asm
0x1800289b8  mov     rax, rsp
0x1800289bb  mov     [rax+10h], rdx
0x1800289bf  mov     [rax+18h], r8
0x1800289c3  mov     [rax+20h], r9
0x1800289c7  push    rbp
0x1800289c8  push    rbx
0x1800289c9  push    rdi
0x1800289ca  lea     rbp, [rax-3D8h]
0x1800289d1  sub     rsp, 4C0h
0x1800289d8  mov     rax, cs:__security_cookie
0x1800289df  xor     rax, rsp
0x1800289e2  mov     [rbp+3D0h+var_20], rax
0x1800289e9  sub     ecx, 1
0x1800289ec  jz      short loc_180028A21
0x1800289ee  sub     ecx, 1
0x1800289f1  jz      short loc_180028A18
0x1800289f3  sub     ecx, 2
0x1800289f6  jz      short loc_180028A0F
0x1800289f8  cmp     ecx, 4
0x1800289fb  jz      short loc_180028A06
0x1800289fd  lea     rbx, aUnknown; "UNKNOWN"
0x180028a04  jmp     short loc_180028A28
0x180028a06  lea     rbx, aDataMissing; "DATA MISSING"
0x180028a0d  jmp     short loc_180028A28
0x180028a0f  lea     rbx, aError; "ERROR"
0x180028a16  jmp     short loc_180028A28
0x180028a18  lea     rbx, aWarning; "WARNING"
0x180028a1f  jmp     short loc_180028A28
0x180028a21  lea     rbx, aInfo; "INFO"
0x180028a28  xorps   xmm0, xmm0
0x180028a2b  lea     rcx, [rsp+4D0h+SystemTime+8]; lpSystemTime
0x180028a30  movups  xmmword ptr [rsp+4D0h+SystemTime+8], xmm0
0x180028a35  call    cs:__imp_GetLocalTime
0x180028a3b  movzx   ecx, word ptr [rsp+4D0h+SystemTime+14h]
0x180028a40  movzx   edx, word ptr [rsp+4D0h+SystemTime+12h]
0x180028a45  movzx   r8d, word ptr [rsp+4D0h+SystemTime+10h]
0x180028a4b  movzx   eax, word ptr [rsp+4D0h+SystemTime+16h]
0x180028a50  movzx   r10d, word ptr [rsp+4D0h+SystemTime+0Eh]
0x180028a56  movzx   r11d, word ptr [rsp+4D0h+SystemTime+0Ah]
0x180028a5c  movzx   r9d, word ptr [rsp+4D0h+SystemTime+8]
0x180028a62  mov     dword ptr [rsp+4D0h+var_488], eax
0x180028a66  mov     [rsp+4D0h+var_490], ecx
0x180028a6a  lea     rcx, [rsp+4D0h+Buffer]; Buffer
0x180028a6f  mov     [rsp+4D0h+var_498], edx
0x180028a73  mov     edx, 40h ; '@'; BufferCount
0x180028a78  mov     [rsp+4D0h+var_4A0], r8d
0x180028a7d  lea     r8, a04d02d02d02d02; "[%04d-%02d-%02d %02d:%02d:%02d.%03d]"
0x180028a84  mov     [rsp+4D0h+var_4A8], r10d
0x180028a89  mov     dword ptr [rsp+4D0h+ArgList], r11d
0x180028a8e  call    snprintf
0x180028a93  mov     rax, [rbp+3D0h+arg_8]
0x180028a9a  lea     r9, [rsp+4D0h+Buffer]
0x180028a9f  mov     qword ptr [rsp+4D0h+var_4A8], rax
0x180028aa4  lea     r8, aSSS; "%s %s: %s"
0x180028aab  mov     edx, 400h; BufferCount
0x180028ab0  mov     [rsp+4D0h+ArgList], rbx
0x180028ab5  lea     rcx, [rbp+3D0h+Format]; Buffer
0x180028ab9  call    snprintf
0x180028abe  mov     ecx, 1; Ix
0x180028ac3  mov     qword ptr [rsp+4D0h+SystemTime], 0
0x180028acc  lea     rdi, [rbp+3D0h+arg_10]
0x180028ad3  call    _o___acrt_iob_func_0
0x180028ad8  mov     rbx, rax
0x180028adb  call    __local_stdio_printf_options
0x180028ae0  xor     r9d, r9d; Locale
0x180028ae3  mov     [rsp+4D0h+ArgList], rdi; ArgList
0x180028ae8  lea     r8, [rbp+3D0h+Format]; Format
0x180028aec  mov     rdx, rbx; Stream
0x180028aef  mov     rcx, [rax]; Options
0x180028af2  call    _o___stdio_common_vfprintf_s_0
0x180028af7  mov     rcx, [rbp+3D0h+var_20]
0x180028afe  xor     rcx, rsp; StackCookie
0x180028b01  call    __security_check_cookie
0x180028b06  add     rsp, 4C0h
0x180028b0d  pop     rdi
0x180028b0e  pop     rbx
0x180028b0f  pop     rbp
0x180028b10  retn
```
