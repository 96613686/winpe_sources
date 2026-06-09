# Rdp::Stack::Driver::CDriverControl3::Stop(void)

- ea: `0x180015780`
- end: `0x1800158f3`
- name: `?Stop@CDriverControl3@Driver@Stack@Rdp@@UEAAJXZ`
- size: `371`
- prototype: `__int64 __fastcall(Rdp::Stack::Driver::CDriverControl3 *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000b1bc`
- `0x18000dbf4`
- `0x1800129cc`
- `0x180015780`
- `0x1800158fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015861`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015861`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800157e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800158b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800157e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800158b1`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Driver::CDriverControl3::Stop(Rdp::Stack::Driver::CDriverControl3 *this)
{
  char v2; // bl
  bool v3; // di
  bool v4; // r15
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  const char *v8; // r15
  bool v9; // di
  char v10; // al
  int v11; // r8d
  int v12; // edx
  int v14; // [rsp+20h] [rbp-68h]
  int v15; // [rsp+20h] [rbp-68h]
  const char *v16; // [rsp+28h] [rbp-60h]
  int v17; // [rsp+28h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v2 = 1;
  v3 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v4 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v6) = v4;
    LOBYTE(v7) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v14,
      (int)v16,
      16,
      &WPP_a030594cf1f33de86aa1e387072882dd_Traceguids,
      CurrentThreadId);
  }
  v8 = (const char *)(unsigned int)Rdp::Stack::Driver::Unbind((char *)this + 48);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x165,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    v8,
    (int)"Failed to unbind driver",
    v16);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 48,
    -1);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v2 = 0;
  }
  v9 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v10 = GetCurrentThreadId();
    LOBYTE(v11) = v9;
    LOBYTE(v12) = v2;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      v11,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v15,
      v17,
      17,
      &WPP_a030594cf1f33de86aa1e387072882dd_Traceguids,
      v10);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180015780  push    rbx
0x180015782  push    rsi
0x180015783  push    rdi
0x180015784  push    r12
0x180015786  push    r13
0x180015788  push    r14
0x18001578a  push    r15
0x18001578c  sub     rsp, 50h
0x180015790  mov     r13, rcx
0x180015793  lea     rsi, WPP_GLOBAL_Control
0x18001579a  mov     rax, cs:WPP_GLOBAL_Control
0x1800157a1  mov     bl, 1
0x1800157a3  cmp     rax, rsi
0x1800157a6  jz      short loc_1800157B8
0x1800157a8  test    [rax+1Ch], bl
0x1800157ab  jz      short loc_1800157B8
0x1800157ad  cmp     byte ptr [rax+19h], 4
0x1800157b1  jb      short loc_1800157B8
0x1800157b3  mov     dil, bl
0x1800157b6  jmp     short loc_1800157BB
0x1800157b8  xor     dil, dil
0x1800157bb  lea     r14, WPP_RECORDER_INITIALIZED
0x1800157c2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800157c9  setnz   r15b
0x1800157cd  test    dil, dil
0x1800157d0  jnz     short loc_1800157E0
0x1800157d2  test    r15b, r15b
0x1800157d5  jnz     short loc_1800157E0
0x1800157d7  lea     r12, WPP_a030594cf1f33de86aa1e387072882dd_Traceguids
0x1800157de  jmp     short loc_180015817
0x1800157e0  call    cs:__imp_GetCurrentThreadId
0x1800157e6  mov     dword ptr [rsp+88h+var_48], eax; char
0x1800157ea  lea     r12, WPP_a030594cf1f33de86aa1e387072882dd_Traceguids
0x1800157f1  mov     [rsp+88h+MessageGuid], r12; MessageGuid
0x1800157f6  mov     [rsp+88h+var_58], 10h; __int16
0x1800157fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180015804  mov     r9, [rcx+28h]; int
0x180015808  mov     r8b, r15b; int
0x18001580b  mov     dl, dil; int
0x18001580e  mov     rcx, [rcx+10h]; int
0x180015812  call    WPP_RECORDER_AND_TRACE_SF_D
0x180015817  lea     rcx, [r13+30h]
0x18001581b  call    ?Unbind@Driver@Stack@Rdp@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Rdp::Stack::Driver::Unbind(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x180015820  mov     r15d, eax
0x180015823  mov     rcx, [rsp+88h]; this
0x18001582b  lea     rax, aFailedToUnbind; "Failed to unbind driver"
0x180015832  mov     qword ptr [rsp+88h+var_68], rax; int
0x180015837  mov     r9d, r15d; char *
0x18001583a  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180015841  mov     edx, 165h; void *
0x180015846  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001584b  nop
0x18001584c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180015850  lea     rcx, [r13+30h]
0x180015854  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180015859  jmp     short loc_180015884
0x18001585b  int     3; Trap to Debugger
0x18001585c  mov     ecx, 6; dwErrCode
0x180015861  call    cs:__imp_SetLastError
0x180015867  mov     r15d, 80070006h
0x18001586d  lea     rsi, WPP_GLOBAL_Control
0x180015874  mov     bl, 1
0x180015876  lea     r14, WPP_RECORDER_INITIALIZED
0x18001587d  lea     r12, WPP_a030594cf1f33de86aa1e387072882dd_Traceguids
0x180015884  mov     rax, cs:WPP_GLOBAL_Control
0x18001588b  cmp     rax, rsi
0x18001588e  jz      short loc_18001589B
0x180015890  test    [rax+1Ch], bl
0x180015893  jz      short loc_18001589B
0x180015895  cmp     byte ptr [rax+19h], 4
0x180015899  jnb     short loc_18001589D
0x18001589b  xor     bl, bl
0x18001589d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800158a4  setnz   dil
0x1800158a8  test    bl, bl
0x1800158aa  jnz     short loc_1800158B1
0x1800158ac  test    dil, dil
0x1800158af  jz      short loc_1800158E0
0x1800158b1  call    cs:__imp_GetCurrentThreadId
0x1800158b7  mov     dword ptr [rsp+88h+var_48], eax; char
0x1800158bb  mov     [rsp+88h+MessageGuid], r12; MessageGuid
0x1800158c0  mov     [rsp+88h+var_58], 11h; __int16
0x1800158c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158ce  mov     r9, [rcx+28h]; int
0x1800158d2  mov     r8b, dil; int
0x1800158d5  mov     dl, bl; int
0x1800158d7  mov     rcx, [rcx+10h]; int
0x1800158db  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800158e0  mov     eax, r15d
0x1800158e3  add     rsp, 50h
0x1800158e7  pop     r15
0x1800158e9  pop     r14
0x1800158eb  pop     r13
0x1800158ed  pop     r12
0x1800158ef  pop     rdi
0x1800158f0  pop     rsi
0x1800158f1  pop     rbx
0x1800158f2  retn
0x1800294d2  push    rbp
0x1800294d4  sub     rsp, 50h
0x1800294d8  mov     rbp, rdx
0x1800294db  mov     rax, [rcx]
0x1800294de  xor     ecx, ecx
0x1800294e0  cmp     dword ptr [rax], 0C0000008h
0x1800294e6  setz    cl
0x1800294e9  mov     eax, ecx
0x1800294eb  add     rsp, 50h
0x1800294ef  pop     rbp
0x1800294f0  retn
```
