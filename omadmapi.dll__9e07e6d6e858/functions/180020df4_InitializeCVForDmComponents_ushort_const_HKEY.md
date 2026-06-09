# InitializeCVForDmComponents(ushort const *,HKEY__ *)

- ea: `0x180020df4`
- end: `0x180020eef`
- name: `?InitializeCVForDmComponents@@YAJPEBGPEAUHKEY__@@@Z`
- size: `251`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180021108`

## callees

- `0x1800031b0`
- `0x1800031d4`
- `0x180003db8`
- `0x180011b98`
- `0x180020aac`
- `0x180020df4`
- `0x180020ef8`
- `0x180021314`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InitializeCVForDmComponents(const unsigned __int16 *a1, HKEY a2)
{
  const unsigned __int16 *v4; // rcx
  int ComponentCVForEnrollmentId; // eax
  bool v6; // dl
  unsigned int v7; // ebx
  struct TraceLoggingCorrelationVector *v9; // rbx
  int v10; // eax
  unsigned int v11; // edi
  int v12; // [rsp+20h] [rbp-B8h]
  char Str; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v14[143]; // [rsp+31h] [rbp-A7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  Str = 0;
  memset_0(v14, 0, 0x80u);
  ComponentCVForEnrollmentId = GetComponentCVForEnrollmentId(v4, a1, &Str, a2);
  v7 = ComponentCVForEnrollmentId;
  if ( ComponentCVForEnrollmentId >= 0 )
  {
    v9 = TraceLoggingCorrelationVector::Set(&Str, v6);
    v10 = InitializeCVForLocalConfigSession(v9);
    v11 = v10;
    if ( v10 >= 0 )
    {
      if ( v9 )
        operator delete(v9);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
        (const char *)(unsigned int)v10,
        (int)v9);
      if ( v9 )
        operator delete(v9);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
      (const char *)(unsigned int)ComponentCVForEnrollmentId,
      v12);
    return v7;
  }
}

```

## disassembly

```asm
0x180020df4  mov     [rsp+arg_10], rbx
0x180020df9  push    rdi
0x180020dfa  sub     rsp, 0D0h
0x180020e01  mov     rax, cs:__security_cookie
0x180020e08  xor     rax, rsp
0x180020e0b  mov     [rsp+0D8h+var_18], rax
0x180020e13  mov     rbx, rdx
0x180020e16  mov     rdi, rcx
0x180020e19  mov     [rsp+0D8h+Str], 0
0x180020e1e  xor     edx, edx; Val
0x180020e20  mov     r8d, 80h; Size
0x180020e26  lea     rcx, [rsp+0D8h+var_A7]; void *
0x180020e2b  call    memset_0
0x180020e30  mov     r9, rbx; HKEY
0x180020e33  lea     r8, [rsp+0D8h+Str]; char *
0x180020e38  mov     rdx, rdi; unsigned __int16 *
0x180020e3b  call    ?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z; GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)
0x180020e40  mov     ebx, eax
0x180020e42  test    eax, eax
0x180020e44  jns     short loc_180020E66
0x180020e46  mov     rcx, [rsp+0D8h]; this
0x180020e4e  mov     r9d, eax; char *
0x180020e51  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x180020e58  mov     edx, 93h; void *
0x180020e5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020e62  mov     eax, ebx
0x180020e64  jmp     short loc_180020ECD
0x180020e66  lea     rcx, [rsp+0D8h+Str]; Str
0x180020e6b  call    ?Set@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Set(char const *,bool)
0x180020e70  mov     rbx, rax
0x180020e73  mov     qword ptr [rsp+0D8h+var_B8], rax; int
0x180020e78  mov     rcx, rax; struct TraceLoggingCorrelationVector *
0x180020e7b  call    ?InitializeCVForLocalConfigSession@@YAJPEAVTraceLoggingCorrelationVector@@@Z; InitializeCVForLocalConfigSession(TraceLoggingCorrelationVector *)
0x180020e80  mov     edi, eax
0x180020e82  test    eax, eax
0x180020e84  jns     short loc_180020EB9
0x180020e86  mov     rcx, [rsp+0D8h]; this
0x180020e8e  mov     r9d, eax; char *
0x180020e91  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x180020e98  mov     edx, 97h; void *
0x180020e9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020ea2  nop
0x180020ea3  test    rbx, rbx
0x180020ea6  jz      short loc_180020EB5
0x180020ea8  mov     edx, 90h; unsigned __int64
0x180020ead  mov     rcx, rbx; void *
0x180020eb0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020eb5  mov     eax, edi
0x180020eb7  jmp     short loc_180020ECD
0x180020eb9  test    rbx, rbx
0x180020ebc  jz      short loc_180020ECB
0x180020ebe  mov     edx, 90h; unsigned __int64
0x180020ec3  mov     rcx, rbx; void *
0x180020ec6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020ecb  xor     eax, eax
0x180020ecd  mov     rcx, [rsp+0D8h+var_18]
0x180020ed5  xor     rcx, rsp; StackCookie
0x180020ed8  call    __security_check_cookie
0x180020edd  mov     rbx, [rsp+0D8h+arg_10]
0x180020ee5  add     rsp, 0D0h
0x180020eec  pop     rdi
0x180020eed  retn
```
