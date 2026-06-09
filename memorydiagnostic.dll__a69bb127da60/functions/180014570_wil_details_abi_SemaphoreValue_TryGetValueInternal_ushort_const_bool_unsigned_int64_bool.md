# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180014570`
- end: `0x1800147ff`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180008cc8`
- `0x180009098`

## callees

- `0x180002e50`
- `0x18000d448`
- `0x1800109b4`
- `0x1800109d4`
- `0x180013460`
- `0x180014570`
- `0x180015604`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180014651`
- `KERNEL32!CloseHandle` at `0x1800146c3`
- `KERNEL32!CloseHandle` at `0x1800146d4`
- `KERNEL32!CloseHandle` at `0x1800146ec`
- `KERNEL32!CloseHandle` at `0x180014711`
- `KERNEL32!CloseHandle` at `0x18001473e`
- `KERNEL32!CloseHandle` at `0x180014651`
- `KERNEL32!CloseHandle` at `0x1800146c3`
- `KERNEL32!CloseHandle` at `0x1800146d4`
- `KERNEL32!CloseHandle` at `0x1800146ec`
- `KERNEL32!CloseHandle` at `0x180014711`
- `KERNEL32!CloseHandle` at `0x18001473e`
- `KERNEL32!OpenSemaphoreW` at `0x180014604`
- `KERNEL32!OpenSemaphoreW` at `0x180014680`
- `KERNEL32!OpenSemaphoreW` at `0x180014604`
- `KERNEL32!OpenSemaphoreW` at `0x180014680`
- `KERNEL32!GetLastError` at `0x18001474d`
- `KERNEL32!GetLastError` at `0x18001474d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v20);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x180014570  push    rbp
0x180014572  push    rbx
0x180014573  push    rsi
0x180014574  push    rdi
0x180014575  push    r14
0x180014577  push    r15
0x180014579  lea     rbp, [rsp-158h]
0x180014581  sub     rsp, 258h
0x180014588  mov     rax, cs:__security_cookie
0x18001458f  xor     rax, rsp
0x180014592  mov     [rbp+180h+var_40], rax
0x180014599  xor     r15d, r15d
0x18001459c  lea     rax, [rsp+280h+Name]
0x1800145a1  mov     [r8], r15
0x1800145a4  mov     r14, r8
0x1800145a7  mov     edx, 104h
0x1800145ac  mov     r9d, 7FFFFFFEh
0x1800145b2  test    r9, r9
0x1800145b5  jz      short loc_1800145D6
0x1800145b7  movzx   r8d, word ptr [rcx]
0x1800145bb  test    r8w, r8w
0x1800145bf  jz      short loc_1800145D6
0x1800145c1  mov     [rax], r8w
0x1800145c5  add     rcx, 2
0x1800145c9  add     rax, 2
0x1800145cd  dec     r9
0x1800145d0  sub     rdx, 1; unsigned __int64
0x1800145d4  jnz     short loc_1800145B2
0x1800145d6  test    rdx, rdx
0x1800145d9  lea     rcx, [rax-2]
0x1800145dd  lea     r8, aP0; "_p0"
0x1800145e4  cmovnz  rcx, rax
0x1800145e8  mov     [rcx], r15w
0x1800145ec  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800145f1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800145f6  mov     esi, 1F0003h
0x1800145fb  lea     r8, [rsp+280h+Name]; lpName
0x180014600  mov     ecx, esi; dwDesiredAccess
0x180014602  xor     edx, edx; bInheritHandle
0x180014604  call    cs:__imp_OpenSemaphoreW
0x18001460a  mov     rbx, rax
0x18001460d  test    rax, rax
0x180014610  jz      loc_18001474D
0x180014616  lea     rdx, [rsp+280h+var_25C]; int *
0x18001461b  mov     [rsp+280h+var_25C], r15d
0x180014620  mov     rcx, rax; hHandle
0x180014623  mov     [rsp+280h+var_260], r15d; int
0x180014628  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001462d  mov     edi, eax
0x18001462f  test    eax, eax
0x180014631  jns     short loc_180014666
0x180014633  mov     rcx, [rbp+188h]; this
0x18001463a  lea     r8, aWil; "wil"
0x180014641  mov     r9d, eax; char *
0x180014644  mov     edx, 0D6h; void *
0x180014649  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001464e  mov     rcx, rbx; hObject
0x180014651  call    cs:__imp_CloseHandle
0x180014657  test    eax, eax
0x180014659  jz      loc_1800147C9
0x18001465f  mov     eax, edi
0x180014661  jmp     loc_180014774
0x180014666  lea     r8, asc_1800255B8; "h"
0x18001466d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180014672  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014677  lea     r8, [rsp+280h+Name]; lpName
0x18001467c  xor     edx, edx; bInheritHandle
0x18001467e  mov     ecx, esi; dwDesiredAccess
0x180014680  call    cs:__imp_OpenSemaphoreW
0x180014686  mov     rdi, rax
0x180014689  test    rax, rax
0x18001468c  jz      loc_180014721
0x180014692  lea     rdx, [rsp+280h+var_260]; int *
0x180014697  mov     rcx, rax; hHandle
0x18001469a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001469f  mov     esi, eax
0x1800146a1  test    eax, eax
0x1800146a3  jns     short loc_1800146E9
0x1800146a5  mov     rcx, [rbp+188h]; this
0x1800146ac  lea     r8, aWil; "wil"
0x1800146b3  mov     r9d, eax; char *
0x1800146b6  mov     edx, 0DEh; void *
0x1800146bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800146c0  mov     rcx, rdi; hObject
0x1800146c3  call    cs:__imp_CloseHandle
0x1800146c9  test    eax, eax
0x1800146cb  jz      loc_1800147DB
0x1800146d1  mov     rcx, rbx; hObject
0x1800146d4  call    cs:__imp_CloseHandle
0x1800146da  test    eax, eax
0x1800146dc  jz      loc_1800147ED
0x1800146e2  mov     eax, esi
0x1800146e4  jmp     loc_180014774
0x1800146e9  mov     rcx, rdi; hObject
0x1800146ec  call    cs:__imp_CloseHandle
0x1800146f2  test    eax, eax
0x1800146f4  jz      loc_180014793
0x1800146fa  movsxd  rax, [rsp+280h+var_25C]
0x1800146ff  movsxd  rcx, [rsp+280h+var_260]
0x180014704  shl     rcx, 1Fh
0x180014708  or      rcx, rax
0x18001470b  mov     [r14], rcx
0x18001470e  mov     rcx, rbx; hObject
0x180014711  call    cs:__imp_CloseHandle
0x180014717  test    eax, eax
0x180014719  jz      loc_1800147A5
0x18001471f  jmp     short loc_180014758
0x180014721  mov     rcx, [rbp+188h]; this
0x180014728  lea     r8, aWil; "wil"
0x18001472f  mov     edx, 0DCh; void *
0x180014734  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014739  mov     rcx, rbx; hObject
0x18001473c  mov     edi, eax
0x18001473e  call    cs:__imp_CloseHandle
0x180014744  test    eax, eax
0x180014746  jz      short loc_1800147B7
0x180014748  jmp     loc_18001465F
0x18001474d  call    cs:__imp_GetLastError
0x180014753  cmp     eax, 2
0x180014756  jnz     short loc_18001475C
0x180014758  xor     eax, eax
0x18001475a  jmp     short loc_180014774
0x18001475c  mov     rcx, [rbp+188h]; this
0x180014763  lea     r8, aWil; "wil"
0x18001476a  mov     edx, 0D0h; void *
0x18001476f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014774  mov     rcx, [rbp+180h+var_40]
0x18001477b  xor     rcx, rsp; StackCookie
0x18001477e  call    __security_check_cookie
0x180014783  add     rsp, 258h
0x18001478a  pop     r15
0x18001478c  pop     r14
0x18001478e  pop     rdi
0x18001478f  pop     rsi
0x180014790  pop     rbx
0x180014791  pop     rbp
0x180014792  retn
0x180014793  mov     rcx, [rbp+188h]; this
0x18001479a  mov     edx, 0A0Bh; void *
0x18001479f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800147a5  mov     rcx, [rbp+188h]; this
0x1800147ac  mov     edx, 0A0Bh; void *
0x1800147b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800147b7  mov     rcx, [rbp+188h]; this
0x1800147be  mov     edx, 0A0Bh; void *
0x1800147c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800147c9  mov     rcx, [rbp+188h]; this
0x1800147d0  mov     edx, 0A0Bh; void *
0x1800147d5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800147db  mov     rcx, [rbp+188h]; this
0x1800147e2  mov     edx, 0A0Bh; void *
0x1800147e7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800147ed  mov     rcx, [rbp+188h]; this
0x1800147f4  mov     edx, 0A0Bh; void *
0x1800147f9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
