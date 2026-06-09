# SSI_REQUEST::SendDate(_SYSTEMTIME *,STRA *)

- ea: `0x180003a34`
- end: `0x180003b74`
- name: `?SendDate@SSI_REQUEST@@QEAAJPEAU_SYSTEMTIME@@PEAVSTRA@@@Z`
- size: `320`
- prototype: `int __fastcall(SSI_REQUEST *this, struct _SYSTEMTIME *, const char **)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003d8c`
- `0x180003fac`
- `0x180004afc`

## callees

- `0x180003a34`
- `0x180005548`
- `0x18000574a`
- `0x180005780`

## import_xrefs

- `msvcrt!strftime` at `0x180003b34`
- `msvcrt!strftime` at `0x180003b34`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x180003af2`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x180003af2`
- `iisutil!?AllocateSpace@CHUNK_BUFFER@@QEAAJKPEAPEAD@Z` at `0x180003b1a`
- `iisutil!?AllocateSpace@CHUNK_BUFFER@@QEAAJKPEAPEAD@Z` at `0x180003b1a`

## pseudocode

```c
int __fastcall SSI_REQUEST::SendDate(SSI_REQUEST *this, struct _SYSTEMTIME *a2, const char **a3)
{
  unsigned int wMonth; // ecx
  int wDay; // edx
  int wYear; // r9d
  int v9; // ecx
  int v10; // eax
  int result; // eax
  unsigned int v12; // eax
  char *Buffer; // [rsp+20h] [rbp-E0h] BYREF
  tm Tm; // [rsp+28h] [rbp-D8h] BYREF
  _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+50h] [rbp-B0h] BYREF

  Tm.tm_isdst = 0;
  Buffer = 0;
  memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
  wMonth = a2->wMonth;
  wDay = a2->wDay;
  wYear = a2->wYear;
  Tm.tm_sec = a2->wSecond;
  Tm.tm_min = a2->wMinute;
  Tm.tm_hour = a2->wHour;
  Tm.tm_year = wYear - 1900;
  Tm.tm_wday = a2->wDayOfWeek;
  Tm.tm_mday = wDay;
  Tm.tm_mon = wMonth - 1;
  v9 = wDay + *((_DWORD *)&g_MonthToDayCount + wMonth - 1);
  v10 = v9 - 1;
  Tm.tm_yday = v9 - 1;
  if ( Tm.tm_mon > 1 )
  {
    if ( (wYear & 3) == 0 )
      v10 = v9;
    Tm.tm_yday = v10;
  }
  Tm.tm_isdst = GetTimeZoneInformation(&TimeZoneInformation) == 2;
  result = CHUNK_BUFFER::AllocateSpace((SSI_REQUEST *)((char *)this + 800), 0x101u, &Buffer);
  if ( result >= 0 )
  {
    v12 = strftime(Buffer, 0x101u, a3[4], &Tm);
    if ( v12 )
      return SSI_VECTOR_BUFFER::AddToVector((SSI_REQUEST *)((char *)this + 800), Buffer, v12);
    else
      return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x180003a34  mov     [rsp-8+arg_18], rbx
0x180003a39  push    rbp
0x180003a3a  push    rsi
0x180003a3b  push    rdi
0x180003a3c  lea     rbp, [rsp-10h]
0x180003a41  sub     rsp, 110h
0x180003a48  mov     rax, cs:__security_cookie
0x180003a4f  xor     rax, rsp
0x180003a52  mov     [rbp+20h+var_20], rax
0x180003a56  mov     rdi, r8
0x180003a59  mov     [rsp+120h+Tm.tm_isdst], 0
0x180003a61  mov     rbx, rdx
0x180003a64  mov     [rsp+120h+Buffer], 0
0x180003a6d  mov     rsi, rcx
0x180003a70  xor     edx, edx; Val
0x180003a72  mov     r8d, 0ACh; Size
0x180003a78  lea     rcx, [rsp+120h+TimeZoneInformation]; void *
0x180003a7d  call    memset_0
0x180003a82  movzx   eax, word ptr [rbx+0Ch]
0x180003a86  movzx   ecx, word ptr [rbx+2]
0x180003a8a  movzx   edx, word ptr [rbx+6]
0x180003a8e  movzx   r9d, word ptr [rbx]
0x180003a92  mov     [rsp+120h+Tm.tm_sec], eax
0x180003a96  movzx   eax, word ptr [rbx+0Ah]
0x180003a9a  lea     r8d, [rcx-1]
0x180003a9e  mov     [rsp+120h+Tm.tm_min], eax
0x180003aa2  movzx   eax, word ptr [rbx+8]
0x180003aa6  mov     [rsp+120h+Tm.tm_hour], eax
0x180003aaa  lea     eax, [r9-76Ch]
0x180003ab1  mov     [rsp+120h+Tm.tm_year], eax
0x180003ab5  movzx   eax, word ptr [rbx+4]
0x180003ab9  mov     [rsp+120h+Tm.tm_wday], eax
0x180003abd  mov     eax, ecx
0x180003abf  lea     rcx, ?g_MonthToDayCount@@3PAIA; uint near * g_MonthToDayCount
0x180003ac6  mov     [rsp+120h+Tm.tm_mday], edx
0x180003aca  mov     [rsp+120h+Tm.tm_mon], r8d
0x180003acf  mov     ecx, [rcx+rax*4-4]
0x180003ad3  add     ecx, edx
0x180003ad5  lea     eax, [rcx-1]
0x180003ad8  mov     [rsp+120h+Tm.tm_yday], eax
0x180003adc  cmp     r8d, 1
0x180003ae0  jle     short loc_180003AED
0x180003ae2  test    r9b, 3
0x180003ae6  cmovz   eax, ecx
0x180003ae9  mov     [rsp+120h+Tm.tm_yday], eax
0x180003aed  lea     rcx, [rsp+120h+TimeZoneInformation]; lpTimeZoneInformation
0x180003af2  call    cs:__imp_GetTimeZoneInformation
0x180003af8  xor     ecx, ecx
0x180003afa  lea     rbx, [rsi+320h]
0x180003b01  cmp     eax, 2
0x180003b04  lea     r8, [rsp+120h+Buffer]
0x180003b09  mov     esi, 101h
0x180003b0e  setz    cl
0x180003b11  mov     edx, esi
0x180003b13  mov     [rsp+120h+Tm.tm_isdst], ecx
0x180003b17  mov     rcx, rbx
0x180003b1a  call    cs:__imp_?AllocateSpace@CHUNK_BUFFER@@QEAAJKPEAPEAD@Z; CHUNK_BUFFER::AllocateSpace(ulong,char * *)
0x180003b20  test    eax, eax
0x180003b22  js      short loc_180003B55
0x180003b24  mov     r8, [rdi+20h]; Format
0x180003b28  lea     r9, [rsp+120h+Tm]; Tm
0x180003b2d  mov     rcx, [rsp+120h+Buffer]; Buffer
0x180003b32  mov     edx, esi; SizeInBytes
0x180003b34  call    cs:__imp_strftime
0x180003b3a  test    eax, eax
0x180003b3c  jnz     short loc_180003B45
0x180003b3e  mov     eax, 80070057h
0x180003b43  jmp     short loc_180003B55
0x180003b45  mov     rdx, [rsp+120h+Buffer]; char *
0x180003b4a  mov     r8d, eax; unsigned int
0x180003b4d  mov     rcx, rbx; this
0x180003b50  call    ?AddToVector@SSI_VECTOR_BUFFER@@QEAAJPEADK@Z; SSI_VECTOR_BUFFER::AddToVector(char *,ulong)
0x180003b55  mov     rcx, [rbp+20h+var_20]
0x180003b59  xor     rcx, rsp; StackCookie
0x180003b5c  call    __security_check_cookie
0x180003b61  mov     rbx, [rsp+120h+arg_18]
0x180003b69  add     rsp, 110h
0x180003b70  pop     rdi
0x180003b71  pop     rsi
0x180003b72  pop     rbp
0x180003b73  retn
```
