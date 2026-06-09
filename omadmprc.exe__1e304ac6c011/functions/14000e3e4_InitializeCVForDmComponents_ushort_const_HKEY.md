# InitializeCVForDmComponents(ushort const *,HKEY__ *)

- ea: `0x14000e3e4`
- end: `0x14000e4ea`
- name: `?InitializeCVForDmComponents@@YAJPEBGPEAUHKEY__@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000e710`

## callees

- `0x14000271f`
- `0x140008504`
- `0x14000da8c`
- `0x14000e3e4`
- `0x14000e4f0`
- `0x14000e934`
- `0x140015690`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000e4a2`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000e4ba`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000e4a2`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000e4ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InitializeCVForDmComponents(const unsigned __int16 *a1, HKEY a2)
{
  int ComponentCVForEnrollmentId; // eax
  bool v5; // dl
  unsigned int v6; // ebx
  struct TraceLoggingCorrelationVector *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi
  int v11; // [rsp+20h] [rbp-B8h]
  char Source; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v13[143]; // [rsp+31h] [rbp-A7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  Source = 0;
  memset_0(v13, 0, 0x80u);
  ComponentCVForEnrollmentId = GetComponentCVForEnrollmentId(L"OmaDmSession", a1, &Source, a2);
  v6 = ComponentCVForEnrollmentId;
  if ( ComponentCVForEnrollmentId >= 0 )
  {
    v8 = TraceLoggingCorrelationVector::Set(&Source, v5);
    v9 = InitializeCVForLocalConfigSession(v8);
    v10 = v9;
    if ( v9 >= 0 )
    {
      if ( v8 )
        operator delete(v8);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
        (const char *)(unsigned int)v9,
        (int)v8);
      if ( v8 )
        operator delete(v8);
      return v10;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
      (const char *)(unsigned int)ComponentCVForEnrollmentId,
      v11);
    return v6;
  }
}

```

## disassembly

```asm
0x14000e3e4  mov     [rsp+arg_10], rbx
0x14000e3e9  push    rdi
0x14000e3ea  sub     rsp, 0D0h
0x14000e3f1  mov     rax, cs:__security_cookie
0x14000e3f8  xor     rax, rsp
0x14000e3fb  mov     [rsp+0D8h+var_18], rax
0x14000e403  mov     rbx, rdx
0x14000e406  mov     rdi, rcx
0x14000e409  mov     [rsp+0D8h+Source], 0
0x14000e40e  xor     edx, edx; Val
0x14000e410  mov     r8d, 80h; Size
0x14000e416  lea     rcx, [rsp+0D8h+var_A7]; void *
0x14000e41b  call    memset_0
0x14000e420  mov     r9, rbx; HKEY
0x14000e423  lea     r8, [rsp+0D8h+Source]; char *
0x14000e428  mov     rdx, rdi; unsigned __int16 *
0x14000e42b  lea     rcx, c_szCvValueNameOmaDmSession; "OmaDmSession"
0x14000e432  call    ?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z; GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)
0x14000e437  mov     ebx, eax
0x14000e439  test    eax, eax
0x14000e43b  jns     short loc_14000E45D
0x14000e43d  mov     rcx, [rsp+0D8h]; this
0x14000e445  mov     r9d, eax; char *
0x14000e448  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x14000e44f  mov     edx, 93h; void *
0x14000e454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e459  mov     eax, ebx
0x14000e45b  jmp     short loc_14000E4C8
0x14000e45d  lea     rcx, [rsp+0D8h+Source]; Source
0x14000e462  call    ?Set@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Set(char const *,bool)
0x14000e467  mov     rbx, rax
0x14000e46a  mov     qword ptr [rsp+0D8h+var_B8], rax; int
0x14000e46f  mov     rcx, rax; struct TraceLoggingCorrelationVector *
0x14000e472  call    ?InitializeCVForLocalConfigSession@@YAJPEAVTraceLoggingCorrelationVector@@@Z; InitializeCVForLocalConfigSession(TraceLoggingCorrelationVector *)
0x14000e477  mov     edi, eax
0x14000e479  test    eax, eax
0x14000e47b  jns     short loc_14000E4B2
0x14000e47d  mov     rcx, [rsp+0D8h]; this
0x14000e485  mov     r9d, eax; char *
0x14000e488  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x14000e48f  mov     edx, 97h; void *
0x14000e494  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e499  nop
0x14000e49a  test    rbx, rbx
0x14000e49d  jz      short loc_14000E4AE
0x14000e49f  mov     rcx, rbx
0x14000e4a2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000e4a9  nop     dword ptr [rax+rax+00h]
0x14000e4ae  mov     eax, edi
0x14000e4b0  jmp     short loc_14000E4C8
0x14000e4b2  test    rbx, rbx
0x14000e4b5  jz      short loc_14000E4C6
0x14000e4b7  mov     rcx, rbx
0x14000e4ba  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000e4c1  nop     dword ptr [rax+rax+00h]
0x14000e4c6  xor     eax, eax
0x14000e4c8  mov     rcx, [rsp+0D8h+var_18]
0x14000e4d0  xor     rcx, rsp; StackCookie
0x14000e4d3  call    __security_check_cookie
0x14000e4d8  mov     rbx, [rsp+0D8h+arg_10]
0x14000e4e0  add     rsp, 0D0h
0x14000e4e7  pop     rdi
0x14000e4e8  retn
```
