# TraceFileW(long,ushort *,ushort const *,uint)

- ea: `0x1400023c4`
- end: `0x14000248e`
- name: `?TraceFileW@@YAXJPEAGPEBGI@Z`
- size: `202`
- prototype: `void __fastcall(int, unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002ed4`

## callees

- `0x1400021cc`
- `0x1400023c4`
- `0x140006f10`

## import_xrefs

- `msvcrt!fflush` at `0x14000245f`
- `msvcrt!fflush` at `0x14000245f`
- `msvcrt!fclose` at `0x140002468`
- `msvcrt!fclose` at `0x140002468`
- `msvcrt!fwprintf` at `0x140002456`
- `msvcrt!fwprintf` at `0x140002456`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1400023f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1400023f7`

## string_xrefs

- `0x14000244a`: `%02ld-%02ld-%04ld %02ld:%02ld : DTC Install error = %d, %s, %s (%d) \n`
- `0x14000240f`: `com\complus\dtc\shared\util\stringutil.cpp`

## pseudocode

```c
void __fastcall TraceFileW(int a1, unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  FILE *v7; // rbx
  int wYear; // [rsp+20h] [rbp-78h]
  int wHour; // [rsp+28h] [rbp-70h]
  int wMinute; // [rsp+30h] [rbp-68h]
  int v11; // [rsp+38h] [rbp-60h]
  int v12; // [rsp+50h] [rbp-48h]
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-38h] BYREF

  SystemTime = 0;
  GetLocalTime(&SystemTime);
  v7 = OpenTraceFile();
  if ( v7 )
  {
    v12 = a4;
    v11 = a1;
    wMinute = SystemTime.wMinute;
    wHour = SystemTime.wHour;
    wYear = SystemTime.wYear;
    fwprintf(
      v7,
      L"%02ld-%02ld-%04ld %02ld:%02ld : DTC Install error = %d, %s, %s (%d) \n",
      SystemTime.wMonth,
      SystemTime.wDay,
      wYear,
      wHour,
      wMinute,
      v11,
      a2,
      L"com\\complus\\dtc\\shared\\util\\stringutil.cpp",
      v12);
    fflush(v7);
    fclose(v7);
  }
}

```

## disassembly

```asm
0x1400023c4  mov     [rsp+arg_10], rbx
0x1400023c9  push    rbp
0x1400023ca  push    rsi
0x1400023cb  push    rdi
0x1400023cc  sub     rsp, 80h
0x1400023d3  mov     rax, cs:__security_cookie
0x1400023da  xor     rax, rsp
0x1400023dd  mov     [rsp+98h+var_28], rax
0x1400023e2  mov     edi, ecx
0x1400023e4  xorps   xmm0, xmm0
0x1400023e7  lea     rcx, [rsp+98h+SystemTime]; lpSystemTime
0x1400023ec  mov     ebp, r9d
0x1400023ef  movups  xmmword ptr [rsp+98h+SystemTime.wYear], xmm0
0x1400023f4  mov     rsi, rdx
0x1400023f7  call    cs:__imp_GetLocalTime
0x1400023fd  call    ?OpenTraceFile@@YAPEAU_iobuf@@XZ; OpenTraceFile(void)
0x140002402  mov     rbx, rax
0x140002405  test    rax, rax
0x140002408  jz      short loc_14000246E
0x14000240a  movzx   ecx, [rsp+98h+SystemTime.wMinute]
0x14000240f  lea     rax, aComComplusDtcS; "com\\complus\\dtc\\shared\\util\\string"...
0x140002416  movzx   edx, [rsp+98h+SystemTime.wHour]
0x14000241b  movzx   r10d, [rsp+98h+SystemTime.wYear]
0x140002421  movzx   r9d, [rsp+98h+SystemTime.wDay]
0x140002427  movzx   r8d, [rsp+98h+SystemTime.wMonth]
0x14000242d  mov     [rsp+98h+var_48], ebp
0x140002431  mov     [rsp+98h+var_50], rax
0x140002436  mov     [rsp+98h+var_58], rsi
0x14000243b  mov     [rsp+98h+var_60], edi
0x14000243f  mov     [rsp+98h+var_68], ecx
0x140002443  mov     rcx, rbx; Stream
0x140002446  mov     [rsp+98h+var_70], edx
0x14000244a  lea     rdx, a02ld02ld04ld02; "%02ld-%02ld-%04ld %02ld:%02ld : DTC Ins"...
0x140002451  mov     [rsp+98h+var_78], r10d
0x140002456  call    cs:__imp_fwprintf
0x14000245c  mov     rcx, rbx; Stream
0x14000245f  call    cs:__imp_fflush
0x140002465  mov     rcx, rbx; Stream
0x140002468  call    cs:__imp_fclose
0x14000246e  mov     rcx, [rsp+98h+var_28]
0x140002473  xor     rcx, rsp; StackCookie
0x140002476  call    __security_check_cookie
0x14000247b  mov     rbx, [rsp+98h+arg_10]
0x140002483  add     rsp, 80h
0x14000248a  pop     rdi
0x14000248b  pop     rsi
0x14000248c  pop     rbp
0x14000248d  retn
```
