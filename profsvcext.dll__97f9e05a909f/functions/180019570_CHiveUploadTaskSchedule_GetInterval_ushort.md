# CHiveUploadTaskSchedule::GetInterval(ushort * *)

- ea: `0x180019570`
- end: `0x18001962c`
- name: `?GetInterval@CHiveUploadTaskSchedule@@QEAAJPEAPEAG@Z`
- size: `188`
- prototype: `__int64 __fastcall(CHiveUploadTaskSchedule *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018c78`

## callees

- `0x180006a9c`
- `0x180008e5c`
- `0x18000a074`
- `0x18000a520`
- `0x180019570`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800195f8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800195f8`

## string_xrefs

- `0x1800195c2`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
__int64 __fastcall CHiveUploadTaskSchedule::GetInterval(CHiveUploadTaskSchedule *this, unsigned __int16 **a2)
{
  int v3; // ebx
  __int64 v4; // rdx
  unsigned __int16 *v6; // rax
  int psz[8]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a2 = 0;
  if ( *(_DWORD *)this == 1 )
  {
    v3 = StringCchPrintfW((unsigned __int16 *)psz, 0x10u, L"PT%luH", *((unsigned int *)this + 1));
    if ( v3 < 0 )
    {
      v4 = 224;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v4,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
        (const char *)(unsigned int)v3,
        psz[0]);
      return (unsigned int)v3;
    }
  }
  else
  {
    v3 = StringCchCopyW((unsigned __int16 *)psz, 0x10u, L"PT24H");
    if ( v3 < 0 )
    {
      v4 = 228;
      goto LABEL_4;
    }
  }
  v6 = SysAllocString((const OLECHAR *)psz);
  *a2 = v6;
  if ( !v6 )
  {
    v3 = -2147024882;
    v4 = 232;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x180019570  mov     [rsp+arg_10], rbx
0x180019575  push    rdi
0x180019576  sub     rsp, 50h
0x18001957a  mov     rax, cs:__security_cookie
0x180019581  xor     rax, rsp
0x180019584  mov     [rsp+58h+var_18], rax
0x180019589  mov     qword ptr [rdx], 0
0x180019590  mov     rdi, rdx
0x180019593  cmp     dword ptr [rcx], 1
0x180019596  mov     edx, 10h; unsigned __int64
0x18001959b  jnz     short loc_1800195D5
0x18001959d  mov     r9d, [rcx+4]
0x1800195a1  lea     r8, aPtLuh; "PT%luH"
0x1800195a8  lea     rcx, [rsp+58h+psz]; unsigned __int16 *
0x1800195ad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800195b2  mov     ebx, eax
0x1800195b4  test    eax, eax
0x1800195b6  jns     short loc_1800195F3
0x1800195b8  mov     edx, 0E0h; void *
0x1800195bd  mov     rcx, [rsp+58h]; this
0x1800195c2  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x1800195c9  mov     r9d, ebx; char *
0x1800195cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800195d1  mov     eax, ebx
0x1800195d3  jmp     short loc_180019614
0x1800195d5  lea     r8, aPt24h; "PT24H"
0x1800195dc  lea     rcx, [rsp+58h+psz]; unsigned __int16 *
0x1800195e1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800195e6  mov     ebx, eax
0x1800195e8  test    eax, eax
0x1800195ea  jns     short loc_1800195F3
0x1800195ec  mov     edx, 0E4h
0x1800195f1  jmp     short loc_1800195BD
0x1800195f3  lea     rcx, [rsp+58h+psz]; psz
0x1800195f8  call    cs:__imp_SysAllocString
0x1800195fe  mov     [rdi], rax
0x180019601  test    rax, rax
0x180019604  jnz     short loc_180019612
0x180019606  mov     ebx, 8007000Eh
0x18001960b  mov     edx, 0E8h
0x180019610  jmp     short loc_1800195BD
0x180019612  xor     eax, eax
0x180019614  mov     rcx, [rsp+58h+var_18]
0x180019619  xor     rcx, rsp; StackCookie
0x18001961c  call    __security_check_cookie
0x180019621  mov     rbx, [rsp+58h+arg_10]
0x180019626  add     rsp, 50h
0x18001962a  pop     rdi
0x18001962b  retn
```
