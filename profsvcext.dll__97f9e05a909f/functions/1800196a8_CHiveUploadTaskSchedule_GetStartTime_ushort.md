# CHiveUploadTaskSchedule::GetStartTime(ushort * *)

- ea: `0x1800196a8`
- end: `0x1800197e8`
- name: `?GetStartTime@CHiveUploadTaskSchedule@@QEAAJPEAPEAG@Z`
- size: `320`
- prototype: `__int64 __fastcall(CHiveUploadTaskSchedule *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018c78`

## callees

- `0x180006a9c`
- `0x18000a074`
- `0x18000a520`
- `0x1800196a8`
- `0x18001a14c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800196e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800196e5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800197a8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800197a8`

## string_xrefs

- `0x180019710`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
__int64 __fastcall CHiveUploadTaskSchedule::GetStartTime(CHiveUploadTaskSchedule *this, unsigned __int16 **a2)
{
  CHiveUploadTaskSchedule *v4; // rcx
  WORD v5; // ax
  int v6; // ebx
  __int64 v7; // rdx
  bool v9; // cf
  unsigned __int16 *v10; // rax
  int v11; // [rsp+20h] [rbp-29h]
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-9h] BYREF
  OLECHAR psz[32]; // [rsp+50h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  *a2 = 0;
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  v5 = *((_WORD *)this + 2);
  if ( *(_DWORD *)this == 1 )
  {
    v6 = CHiveUploadTaskSchedule::_IncreaseTime(v4, &SystemTime, v5);
    if ( v6 < 0 )
    {
      v7 = 189;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
        (const char *)(unsigned int)v6,
        v11);
      return (unsigned int)v6;
    }
  }
  else
  {
    v9 = SystemTime.wHour < v5;
    SystemTime.wHour = *((_WORD *)this + 2);
    LOBYTE(v4) = v9;
    *(_DWORD *)&SystemTime.wMinute = 0;
    SystemTime.wMilliseconds = 0;
    if ( !v9 )
    {
      v6 = CHiveUploadTaskSchedule::_IncreaseTime(v4, &SystemTime, 0x18u);
      if ( v6 < 0 )
      {
        v7 = 203;
        goto LABEL_4;
      }
    }
  }
  v6 = StringCchPrintfW(
         psz,
         0x20u,
         L"%04u-%02u-%02dT%02u:%02u:00",
         SystemTime.wYear,
         SystemTime.wMonth,
         SystemTime.wDay,
         SystemTime.wHour,
         SystemTime.wMinute);
  if ( v6 < 0 )
  {
    v7 = 210;
    goto LABEL_4;
  }
  v10 = SysAllocString(psz);
  *a2 = v10;
  if ( !v10 )
  {
    v6 = -2147024882;
    v7 = 213;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x1800196a8  mov     [rsp-8+arg_10], rbx
0x1800196ad  mov     [rsp-8+arg_18], rdi
0x1800196b2  push    rbp
0x1800196b3  lea     rbp, [rsp-57h]
0x1800196b8  sub     rsp, 0A0h
0x1800196bf  mov     rax, cs:__security_cookie
0x1800196c6  xor     rax, rsp
0x1800196c9  mov     [rbp+57h+var_10], rax
0x1800196cd  mov     rbx, rcx
0x1800196d0  mov     qword ptr [rdx], 0
0x1800196d7  xorps   xmm0, xmm0
0x1800196da  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800196de  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800196e2  mov     rdi, rdx
0x1800196e5  call    cs:__imp_GetLocalTime
0x1800196eb  cmp     dword ptr [rbx], 1
0x1800196ee  movzx   eax, word ptr [rbx+4]
0x1800196f2  jnz     short loc_180019726
0x1800196f4  movzx   r8d, ax; unsigned __int16
0x1800196f8  lea     rdx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x1800196fc  call    ?_IncreaseTime@CHiveUploadTaskSchedule@@AEAAJAEAU_SYSTEMTIME@@G@Z; CHiveUploadTaskSchedule::_IncreaseTime(_SYSTEMTIME &,ushort)
0x180019701  mov     ebx, eax
0x180019703  test    eax, eax
0x180019705  jns     short loc_180019758
0x180019707  mov     edx, 0BDh; void *
0x18001970c  mov     rcx, [rbp+5Fh]; this
0x180019710  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180019717  mov     r9d, ebx; char *
0x18001971a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001971f  mov     eax, ebx
0x180019721  jmp     loc_1800197C7
0x180019726  cmp     [rbp+57h+SystemTime.wHour], ax
0x18001972a  mov     [rbp+57h+SystemTime.wHour], ax
0x18001972e  setb    cl; this
0x180019731  xor     eax, eax
0x180019733  mov     dword ptr [rbp+57h+SystemTime.wMinute], eax
0x180019736  mov     [rbp+57h+SystemTime.wMilliseconds], ax
0x18001973a  test    cl, cl
0x18001973c  jnz     short loc_180019758
0x18001973e  lea     r8d, [rax+18h]; unsigned __int16
0x180019742  lea     rdx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x180019746  call    ?_IncreaseTime@CHiveUploadTaskSchedule@@AEAAJAEAU_SYSTEMTIME@@G@Z; CHiveUploadTaskSchedule::_IncreaseTime(_SYSTEMTIME &,ushort)
0x18001974b  mov     ebx, eax
0x18001974d  test    eax, eax
0x18001974f  jns     short loc_180019758
0x180019751  mov     edx, 0CBh
0x180019756  jmp     short loc_18001970C
0x180019758  movzx   ecx, [rbp+57h+SystemTime.wHour]
0x18001975c  movzx   edx, [rbp+57h+SystemTime.wDay]
0x180019760  movzx   r8d, [rbp+57h+SystemTime.wMonth]
0x180019765  movzx   eax, [rbp+57h+SystemTime.wMinute]
0x180019769  movzx   r9d, [rbp+57h+SystemTime.wYear]
0x18001976e  mov     [rsp+0A0h+var_68], eax
0x180019772  mov     [rsp+0A0h+var_70], ecx
0x180019776  lea     rcx, [rbp+57h+psz]; unsigned __int16 *
0x18001977a  mov     [rsp+0A0h+var_78], edx
0x18001977e  mov     edx, 20h ; ' '; unsigned __int64
0x180019783  mov     [rsp+0A0h+var_80], r8d
0x180019788  lea     r8, a04u02u02dt02u0; "%04u-%02u-%02dT%02u:%02u:00"
0x18001978f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019794  mov     ebx, eax
0x180019796  test    eax, eax
0x180019798  jns     short loc_1800197A4
0x18001979a  mov     edx, 0D2h
0x18001979f  jmp     loc_18001970C
0x1800197a4  lea     rcx, [rbp+57h+psz]; psz
0x1800197a8  call    cs:__imp_SysAllocString
0x1800197ae  mov     [rdi], rax
0x1800197b1  test    rax, rax
0x1800197b4  jnz     short loc_1800197C5
0x1800197b6  mov     ebx, 8007000Eh
0x1800197bb  mov     edx, 0D5h
0x1800197c0  jmp     loc_18001970C
0x1800197c5  xor     eax, eax
0x1800197c7  mov     rcx, [rbp+57h+var_10]
0x1800197cb  xor     rcx, rsp; StackCookie
0x1800197ce  call    __security_check_cookie
0x1800197d3  lea     r11, [rsp+0A0h+var_s0]
0x1800197db  mov     rbx, [r11+20h]
0x1800197df  mov     rdi, [r11+28h]
0x1800197e3  mov     rsp, r11
0x1800197e6  pop     rbp
0x1800197e7  retn
```
