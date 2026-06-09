# Rdp::Stack::Driver::CDriverControl3::Start(void)

- ea: `0x180015650`
- end: `0x180015779`
- name: `?Start@CDriverControl3@Driver@Stack@Rdp@@UEAAJXZ`
- size: `297`
- prototype: `__int64 __fastcall(Rdp::Stack::Driver::CDriverControl3 *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000dbf4`
- `0x180014e40`
- `0x180015650`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800156b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015724`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800156b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015724`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Driver::CDriverControl3::Start(Rdp::Stack::Driver::CDriverControl3 *this)
{
  char v2; // bl
  bool v3; // di
  bool v4; // si
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  const char *v8; // r9
  bool v9; // di
  char v10; // al
  int v11; // r8d
  int v12; // edx
  __int64 result; // rax
  int v14; // [rsp+20h] [rbp-58h]
  int v15; // [rsp+28h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

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
      v15,
      14,
      &WPP_a030594cf1f33de86aa1e387072882dd_Traceguids,
      CurrentThreadId);
  }
  try
  {
    Rdp::Stack::Driver::CDriverControl3::SendLoadAvenc((Rdp::Stack::Driver::CDriverControl3 *)((char *)this - 80));
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
        v14,
        v15,
        15,
        &WPP_a030594cf1f33de86aa1e387072882dd_Traceguids,
        v10);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x14D,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180015650  mov     [rsp+arg_8], rbx
0x180015655  mov     [rsp+arg_10], rsi
0x18001565a  push    rdi
0x18001565b  push    r12
0x18001565d  push    r13
0x18001565f  push    r14
0x180015661  push    r15
0x180015663  sub     rsp, 50h
0x180015667  mov     r15, rcx
0x18001566a  lea     r12, WPP_GLOBAL_Control
0x180015671  mov     rax, cs:WPP_GLOBAL_Control
0x180015678  mov     bl, 1
0x18001567a  cmp     rax, r12
0x18001567d  jz      short loc_18001568F
0x18001567f  test    [rax+1Ch], bl
0x180015682  jz      short loc_18001568F
0x180015684  cmp     byte ptr [rax+19h], 4
0x180015688  jb      short loc_18001568F
0x18001568a  mov     dil, bl
0x18001568d  jmp     short loc_180015692
0x18001568f  xor     dil, dil
0x180015692  lea     r13, WPP_RECORDER_INITIALIZED
0x180015699  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800156a0  setnz   sil
0x1800156a4  test    dil, dil
0x1800156a7  jnz     short loc_1800156B7
0x1800156a9  test    sil, sil
0x1800156ac  jnz     short loc_1800156B7
0x1800156ae  lea     r14, WPP_a030594cf1f33de86aa1e387072882dd_Traceguids
0x1800156b5  jmp     short loc_1800156EE
0x1800156b7  call    cs:__imp_GetCurrentThreadId
0x1800156bd  mov     dword ptr [rsp+78h+var_38], eax; char
0x1800156c1  lea     r14, WPP_a030594cf1f33de86aa1e387072882dd_Traceguids
0x1800156c8  mov     [rsp+78h+MessageGuid], r14; MessageGuid
0x1800156cd  mov     [rsp+78h+var_48], 0Eh; __int16
0x1800156d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800156db  mov     r9, [rcx+28h]; int
0x1800156df  mov     r8b, sil; int
0x1800156e2  mov     dl, dil; int
0x1800156e5  mov     rcx, [rcx+10h]; int
0x1800156e9  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800156ee  lea     rcx, [r15-50h]; this
0x1800156f2  call    ?SendLoadAvenc@CDriverControl3@Driver@Stack@Rdp@@AEAAXXZ; Rdp::Stack::Driver::CDriverControl3::SendLoadAvenc(void)
0x1800156f7  mov     rax, cs:WPP_GLOBAL_Control
0x1800156fe  cmp     rax, r12
0x180015701  jz      short loc_18001570E
0x180015703  test    [rax+1Ch], bl
0x180015706  jz      short loc_18001570E
0x180015708  cmp     byte ptr [rax+19h], 4
0x18001570c  jnb     short loc_180015710
0x18001570e  xor     bl, bl
0x180015710  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180015717  setnz   dil
0x18001571b  test    bl, bl
0x18001571d  jnz     short loc_180015724
0x18001571f  test    dil, dil
0x180015722  jz      short loc_180015753
0x180015724  call    cs:__imp_GetCurrentThreadId
0x18001572a  mov     dword ptr [rsp+78h+var_38], eax; char
0x18001572e  mov     [rsp+78h+MessageGuid], r14; MessageGuid
0x180015733  mov     [rsp+78h+var_48], 0Fh; __int16
0x18001573a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015741  mov     r9, [rcx+28h]; int
0x180015745  mov     r8b, dil; int
0x180015748  mov     dl, bl; int
0x18001574a  mov     rcx, [rcx+10h]; int
0x18001574e  call    WPP_RECORDER_AND_TRACE_SF_D
0x180015753  xor     eax, eax
0x180015755  jmp     short loc_18001575E
0x180015757  mov     eax, [rsp+78h+arg_0]
0x18001575e  lea     r11, [rsp+78h+var_28]
0x180015763  mov     rbx, [r11+38h]
0x180015767  mov     rsi, [r11+40h]
0x18001576b  mov     rsp, r11
0x18001576e  pop     r15
0x180015770  pop     r14
0x180015772  pop     r13
0x180015774  pop     r12
0x180015776  pop     rdi
0x180015777  retn
```
