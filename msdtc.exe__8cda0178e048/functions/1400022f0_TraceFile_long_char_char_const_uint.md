# TraceFile(long,char *,char const *,uint)

- ea: `0x1400022f0`
- end: `0x1400023bb`
- name: `?TraceFile@@YAXJPEADPEBDI@Z`
- size: `203`
- prototype: `void __fastcall(int, char *, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002010`

## callees

- `0x1400021cc`
- `0x1400022f0`
- `0x140006f10`

## import_xrefs

- `msvcrt!fprintf` at `0x140002385`
- `msvcrt!fprintf` at `0x140002385`
- `msvcrt!fflush` at `0x14000238e`
- `msvcrt!fflush` at `0x14000238e`
- `msvcrt!fclose` at `0x140002397`
- `msvcrt!fclose` at `0x140002397`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x14000231b`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x14000231b`

## string_xrefs

- `0x140002333`: `com\complus\dtc\inc\tracedstrsafe.h`
- `0x14000235e`: `failed in TracedStringCchCopyW`
- `0x140002372`: `%02ld-%02ld-%04ld %02ld:%02ld : DTC Install error = %d, %s, %s (%d) \n`

## pseudocode

```c
void __fastcall TraceFile(int a1, char *a2, const char *a3)
{
  FILE *v4; // rbx
  _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-28h] BYREF

  SystemTime = 0;
  GetLocalTime(&SystemTime);
  v4 = OpenTraceFile();
  if ( v4 )
  {
    fprintf(
      v4,
      "%02ld-%02ld-%04ld %02ld:%02ld : DTC Install error = %d, %s, %s (%d) \n",
      SystemTime.wMonth,
      SystemTime.wDay,
      SystemTime.wYear,
      SystemTime.wHour,
      SystemTime.wMinute,
      a1,
      "failed in TracedStringCchCopyW",
      "com\\complus\\dtc\\inc\\tracedstrsafe.h",
      132);
    fflush(v4);
    fclose(v4);
  }
}

```

## disassembly

```asm
0x1400022f0  mov     [rsp+arg_8], rbx
0x1400022f5  push    rdi
0x1400022f6  sub     rsp, 80h
0x1400022fd  mov     rax, cs:__security_cookie
0x140002304  xor     rax, rsp
0x140002307  mov     [rsp+88h+var_18], rax
0x14000230c  mov     edi, ecx
0x14000230e  xorps   xmm0, xmm0
0x140002311  lea     rcx, [rsp+88h+SystemTime]; lpSystemTime
0x140002316  movups  xmmword ptr [rsp+88h+SystemTime.wYear], xmm0
0x14000231b  call    cs:__imp_GetLocalTime
0x140002321  call    ?OpenTraceFile@@YAPEAU_iobuf@@XZ; OpenTraceFile(void)
0x140002326  mov     rbx, rax
0x140002329  test    rax, rax
0x14000232c  jz      short loc_14000239D
0x14000232e  movzx   edx, [rsp+88h+SystemTime.wMinute]
0x140002333  lea     rax, aComComplusDtcI; "com\\complus\\dtc\\inc\\tracedstrsafe.h"
0x14000233a  movzx   ecx, [rsp+88h+SystemTime.wYear]
0x14000233f  movzx   r10d, [rsp+88h+SystemTime.wHour]
0x140002345  movzx   r9d, [rsp+88h+SystemTime.wDay]
0x14000234b  movzx   r8d, [rsp+88h+SystemTime.wMonth]
0x140002351  mov     [rsp+88h+var_38], 84h
0x140002359  mov     [rsp+88h+var_40], rax
0x14000235e  lea     rax, aFailedInTraced_0; "failed in TracedStringCchCopyW"
0x140002365  mov     [rsp+88h+var_48], rax
0x14000236a  mov     [rsp+88h+var_50], edi
0x14000236e  mov     [rsp+88h+var_58], edx
0x140002372  lea     rdx, Format; "%02ld-%02ld-%04ld %02ld:%02ld : DTC Ins"...
0x140002379  mov     [rsp+88h+var_60], r10d
0x14000237e  mov     [rsp+88h+var_68], ecx
0x140002382  mov     rcx, rbx; Stream
0x140002385  call    cs:__imp_fprintf
0x14000238b  mov     rcx, rbx; Stream
0x14000238e  call    cs:__imp_fflush
0x140002394  mov     rcx, rbx; Stream
0x140002397  call    cs:__imp_fclose
0x14000239d  mov     rcx, [rsp+88h+var_18]
0x1400023a2  xor     rcx, rsp; StackCookie
0x1400023a5  call    __security_check_cookie
0x1400023aa  mov     rbx, [rsp+88h+arg_8]
0x1400023b2  add     rsp, 80h
0x1400023b9  pop     rdi
0x1400023ba  retn
```
