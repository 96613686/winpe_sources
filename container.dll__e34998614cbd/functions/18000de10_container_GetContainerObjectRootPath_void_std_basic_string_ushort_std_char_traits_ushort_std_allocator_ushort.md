# container::GetContainerObjectRootPath(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18000de10`
- end: `0x18000df71`
- name: `?GetContainerObjectRootPath@container@@YAXPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `353`
- prototype: `__int64 __fastcall(HANDLE JobHandle)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800122f0`
- `0x180025aa8`
- `0x180025ed8`
- `0x180027254`

## callees

- `0x180002ad0`
- `0x180002ee4`
- `0x180002f1c`
- `0x1800051b0`
- `0x18000b4bc`
- `0x18000ca10`
- `0x18000d668`
- `0x18000de10`

## import_xrefs

- `ntdll!NtQueryInformationJobObject` at `0x18000de63`
- `ntdll!NtQueryInformationJobObject` at `0x18000dec8`
- `ntdll!NtQueryInformationJobObject` at `0x18000de63`
- `ntdll!NtQueryInformationJobObject` at `0x18000dec8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall container::GetContainerObjectRootPath(HANDLE JobHandle, __int64 a2)
{
  void *v4; // rbx
  ULONG v5; // edi
  NTSTATUS v6; // eax
  void *v7; // r14
  void *v8; // rsi
  int ReturnLength; // [rsp+20h] [rbp-59h]
  ULONG v10; // [rsp+30h] [rbp-49h] BYREF
  void *v11; // [rsp+38h] [rbp-41h]
  __int128 v12; // [rsp+40h] [rbp-39h] BYREF
  __int64 v13; // [rsp+50h] [rbp-29h]
  __int64 v14; // [rsp+58h] [rbp-21h]
  _BYTE JobInformation[56]; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4 = 0;
  v11 = 0;
  v10 = 0;
  v5 = 52;
  v6 = NtQueryInformationJobObject(JobHandle, JobObjectSecurityLimitInformation|0x20, JobInformation, 0x34u, &v10);
  v7 = 0;
  if ( v6 == -1073741789 )
  {
    v8 = 0;
    do
    {
      if ( v5 == 52 )
        v5 = 4096;
      else
        v5 *= 2;
      v4 = operator new[](v5);
      v7 = v4;
      v11 = v4;
      if ( v8 )
        operator delete(v8);
      v6 = NtQueryInformationJobObject(JobHandle, JobObjectSecurityLimitInformation|0x20, v4, v5, &v10);
      v8 = v4;
    }
    while ( v6 == -1073741789 );
  }
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\ob_provider.cpp",
      (const char *)(unsigned int)v6,
      ReturnLength);
  v12 = 0;
  v13 = 0;
  v14 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v12);
  std::wstring::operator=(a2, &v12);
  std::wstring::~wstring(&v12);
  if ( v7 )
    operator delete(v4);
}

```

## disassembly

```asm
0x18000de10  mov     [rsp-8+arg_10], rbx
0x18000de15  push    rbp
0x18000de16  push    rsi
0x18000de17  push    rdi
0x18000de18  push    r12
0x18000de1a  push    r13
0x18000de1c  push    r14
0x18000de1e  push    r15
0x18000de20  lea     rbp, [rsp-27h]
0x18000de25  sub     rsp, 0A0h
0x18000de2c  mov     rax, cs:__security_cookie
0x18000de33  xor     rax, rsp
0x18000de36  mov     [rbp+57h+var_38], rax
0x18000de3a  mov     r13, rdx
0x18000de3d  mov     r12, rcx
0x18000de40  xor     ebx, ebx
0x18000de42  mov     [rbp+57h+var_98], rbx
0x18000de46  mov     [rbp+57h+var_A0], ebx
0x18000de49  lea     r15, [rbp+57h+JobInformation]
0x18000de4d  lea     rax, [rbp+57h+var_A0]
0x18000de51  mov     qword ptr [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18000de56  lea     edi, [rbx+34h]
0x18000de59  mov     r9d, edi; JobInformationLength
0x18000de5c  lea     r8, [rbp+57h+JobInformation]; JobInformation
0x18000de60  lea     edx, [rbx+25h]; JobInformationClass
0x18000de63  call    cs:__imp_NtQueryInformationJobObject
0x18000de6a  nop     dword ptr [rax+rax+00h]
0x18000de6f  xor     r14d, r14d
0x18000de72  cmp     eax, 0C0000225h
0x18000de77  jz      short loc_18000DEDE
0x18000de79  cmp     eax, 0C0000023h
0x18000de7e  jnz     short loc_18000DEDE
0x18000de80  xor     esi, esi
0x18000de82  cmp     edi, 34h ; '4'
0x18000de85  jnz     short loc_18000DE8E
0x18000de87  mov     edi, 1000h
0x18000de8c  jmp     short loc_18000DE90
0x18000de8e  add     edi, edi
0x18000de90  mov     ecx, edi; unsigned __int64
0x18000de92  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000de97  mov     rbx, rax
0x18000de9a  mov     r14, rax
0x18000de9d  mov     [rbp+57h+var_98], rax
0x18000dea1  test    rsi, rsi
0x18000dea4  jz      short loc_18000DEAE
0x18000dea6  mov     rcx, rsi; void *
0x18000dea9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000deae  mov     r15, rbx
0x18000deb1  lea     rax, [rbp+57h+var_A0]
0x18000deb5  mov     qword ptr [rsp+0D0h+ReturnLength], rax; int
0x18000deba  mov     r9d, edi; JobInformationLength
0x18000debd  mov     r8, rbx; JobInformation
0x18000dec0  mov     edx, 25h ; '%'; JobInformationClass
0x18000dec5  mov     rcx, r12; JobHandle
0x18000dec8  call    cs:__imp_NtQueryInformationJobObject
0x18000decf  nop     dword ptr [rax+rax+00h]
0x18000ded4  mov     rsi, rbx
0x18000ded7  cmp     eax, 0C0000023h
0x18000dedc  jz      short loc_18000DE82
0x18000dede  mov     rcx, [rbp+5Fh]; this
0x18000dee2  test    eax, eax
0x18000dee4  js      short loc_18000DF5C
0x18000dee6  xorps   xmm0, xmm0
0x18000dee9  movups  [rbp+57h+var_90], xmm0
0x18000deed  mov     [rbp+57h+var_80], 0
0x18000def5  mov     [rbp+57h+var_78], 0
0x18000defd  movzx   r8d, word ptr [r15]
0x18000df01  shr     r8, 1
0x18000df04  mov     rdx, [r15+8]
0x18000df08  lea     rcx, [rbp+57h+var_90]
0x18000df0c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000df11  lea     rdx, [rbp+57h+var_90]
0x18000df15  mov     rcx, r13
0x18000df18  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000df1d  lea     rcx, [rbp+57h+var_90]
0x18000df21  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000df26  nop
0x18000df27  test    r14, r14
0x18000df2a  jz      short loc_18000DF34
0x18000df2c  mov     rcx, rbx; void *
0x18000df2f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000df34  mov     rcx, [rbp+57h+var_38]
0x18000df38  xor     rcx, rsp; StackCookie
0x18000df3b  call    __security_check_cookie
0x18000df40  mov     rbx, [rsp+0D0h+arg_10]
0x18000df48  add     rsp, 0A0h
0x18000df4f  pop     r15
0x18000df51  pop     r14
0x18000df53  pop     r13
0x18000df55  pop     r12
0x18000df57  pop     rdi
0x18000df58  pop     rsi
0x18000df59  pop     rbp
0x18000df5a  retn
0x18000df5c  mov     r9d, eax; char *
0x18000df5f  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\container"...
0x18000df66  mov     edx, 68h ; 'h'; void *
0x18000df6b  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
